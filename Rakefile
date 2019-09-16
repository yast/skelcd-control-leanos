require "yast/rake"

Yast::Tasks.configuration do |conf|
  conf.obs_api = "https://api.suse.de"
  conf.obs_target = "SUSE_SLE-15-SP1_Update_QR"
  conf.obs_sr_project = "SUSE:SLE-15-SP1:Update:QR"
  conf.obs_project = "Devel:YaST:SLE-15-SP1-QR"

  # lets ignore license check for now
  conf.skip_license_check << /.*/
end

