require "yast/rake"

Yast::Tasks.configuration do |conf|
  conf.obs_api = "https://api.suse.de"
  conf.obs_target = "SUSE_SLE-15-SP3_Update_QR"
  conf.obs_sr_project = "SUSE:SLE-15-SP3:Update:QR"
  conf.obs_project = "Devel:YaST:SLE-15-SP3-QR"

  # lets ignore license check for now
  conf.skip_license_check << /.*/
end

# this special part allows using the "yupdate" script with this package,
# the location in the inst-sys is different than in the built RPM package
# so the usual "rake install" would not work here

# running in the inst-sys?
if File.exist?("/.packages.initrd")
  task :install do
    destdir = ENV["DESTDIR"] || "/"
    control = "/control.xml"
    # backup the original file
    FileUtils.cp(control, "#{control}.bak") if File.exist?(control)
    # install the new file
    FileUtils.cp("control/control.leanos.xml", File.join(destdir, control))
  end
end

