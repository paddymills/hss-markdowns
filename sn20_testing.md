# SigmaNEST Testing (version: SigmaSUITE 20)

- [ ] OYS Toolbar
    - [ ] Autoprocess (`Punch, Drill, Mill`) :: issue 1
    - [ ] Web Automation :: issue #2
    - [x] Part Rotation
    - [x] Workflow Export
- [ ] SigmaNEST
    - [x] Part Import
        - [x] Faro
        - [x] NX
        - [x] ENG_mfg :: issue 3
        - [ ] Webs/Flanges
    - [x] XML Import
    - [ ] Heat Swap
    - [ ] Nesting
    - [ ] NC Validation
        - [ ] Parts
        - [ ] Webs/Flanges
- [ ] Sim Trans
    - [ ] Plate import
    - [ ] Work order import
    - [ ] Heat Swap

### Issues

1. **Waiting on SigmaTEK to fix NX import module**
2. Autoprocess button is blank in toolbar (not loading .dll)
3. Web Automation displays error (passable)
4. XML import launches x32 Sigmanest. **Requires new files** (deployment #4)
5. ENG_mfg parts import same as today, but turning off "Process Assembly Bodies" imports the wrong body
6. SimTrans development instance needs set up **(district 1)**

### Deployment

1. Database
2. Re-point posts
3. Install server filesystem
4. OYS automation files (repoint where necessary)
5. Client installs
    1. master .ini files (config and license)
    2. ProcessMapping.txt
