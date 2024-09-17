
# Notes

## SLE Quarterly Updates

The SLE15 media are quarterly rebuilt with the latest updated packages. These
media have the self-update mechanism disabled for several reasons. That is
implemented in separate `SLE-15-SP*-QR` branches.

*Whenever you update any `SLE-15-SP*` branch do not forget to merge the change
also to the respective `SLE-15-SP*-QR` branch if it exists.*

After merging the change submit the package manually using the `rake osc:sr`
command. (It submits to a special quarterly update project, not to the standard
maintenance project as usually.)
