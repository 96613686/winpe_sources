# TermInstallation

- ea: `0x180013498`
- end: `0x1800134fd`
- name: `TermInstallation`
- size: `101`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000fac0`

## callees

- `0x18000a210`
- `0x180017d8c`

## pseudocode

```c
int TermInstallation()
{
  pSetupBeginSynchronizedAccess(&Handles);
  pSpUtilsDestroySynchronizedAccess((__int64)&Handles);
  pSetupBeginSynchronizedAccess(&qword_1800239B0);
  pSpUtilsDestroySynchronizedAccess((__int64)&qword_1800239B0);
  pSetupBeginSynchronizedAccess(&PnpInstallThreadLock);
  PnpInstallThread = 0;
  PnpInstallThreadExit = 0;
  return pSpUtilsDestroySynchronizedAccess((__int64)&PnpInstallThreadLock);
}

```

## disassembly

```asm
0x180013498  sub     rsp, 28h
0x18001349c  lea     rcx, Handles; lpHandles
0x1800134a3  call    pSetupBeginSynchronizedAccess
0x1800134a8  lea     rcx, Handles
0x1800134af  call    _pSpUtilsDestroySynchronizedAccess
0x1800134b4  lea     rcx, qword_1800239B0; lpHandles
0x1800134bb  call    pSetupBeginSynchronizedAccess
0x1800134c0  lea     rcx, qword_1800239B0
0x1800134c7  call    _pSpUtilsDestroySynchronizedAccess
0x1800134cc  lea     rcx, PnpInstallThreadLock; lpHandles
0x1800134d3  call    pSetupBeginSynchronizedAccess
0x1800134d8  lea     rcx, PnpInstallThreadLock
0x1800134df  mov     cs:PnpInstallThread, 0
0x1800134ea  mov     cs:PnpInstallThreadExit, 0
0x1800134f4  add     rsp, 28h
0x1800134f8  jmp     _pSpUtilsDestroySynchronizedAccess
```
