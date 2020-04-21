require "yast/rake"

Yast::Tasks.submit_to :sle15sp2

Yast::Tasks.configuration do |conf|
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

