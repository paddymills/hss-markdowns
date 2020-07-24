# SigmaNEST Testing (version: SigmaSUITE 20)

- [ ] OYS Toolbar
    - [ ] Autoprocess (`Punch, Drill, Mill`**) :: issue #2**
    - [ ] Web Automation :: issue #3, #6
    - [x] Part Rotation
    - [x] Workflow Export
- [ ] SigmaNEST
    - [x] Part Import
        - [x] Custom Splice (Faro/Scan)
        - [x] NX
        - [x] ENG_mfg :: issue #5
        - [ ] Webs/Flanges :: issue #1
    - [x] XML Import
    - [ ] Heat Swap :: issue #6 should be resolved first
    - [ ] Nesting
    - [ ] NC Validation
        - [ ] Parts
        - [ ] Webs/Flanges
- [ ] Sim Trans :: issue #6
    - [ ] Plate import
    - [ ] Work order import
    - [ ] Heat Swap

### Issues

1. **Waiting on SigmaTEK to fix NX import module**
    1. Splines converted to long line segments, which makes webs under size
    2. Optimize Spline Import freezes import
2. Autoprocess button is blank in toolbar (not loading .dll)
3. Web Automation displays error (passable)
4. XML import launches x32 Sigmanest. **Requires new files** (deployment #4)
5. ENG_mfg parts import same as today, but turning off "Process Assembly Bodies" imports the wrong body
6. SimTrans not working with multiple districts on different versions: dev(1) not working.

### Deployment

1. Database
2. Re-point posts
3. Install server filesystem
4. OYS automation files (repoint where necessary)
5. Client installs
    1. master .ini files (config and license)
    2. ProcessMapping.txt
