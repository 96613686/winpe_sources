# CSilentProcessExitTestAutomation::WriteTestHookToRegistry(ushort const *,uchar *,ulong,ulong)

- ea: `0x180013e3c`
- end: `0x180013e65`
- name: `?WriteTestHookToRegistry@CSilentProcessExitTestAutomation@@QEAAXPEBGPEAEKK@Z`
- size: `41`
- prototype: `void(CSilentProcessExitTestAutomation *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000f834`
- `0x18000fc94`
- `0x1800105c8`

## callees

- `0x180013e3c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180013e5a`
- `ADVAPI32!RegSetValueExW` at `0x180013e5a`

## pseudocode

```c
void __fastcall CSilentProcessExitTestAutomation::WriteTestHookToRegistry(
        HKEY *this,
        const unsigned __int16 *a2,
        unsigned __int8 *lpData,
        DWORD cbData,
        DWORD dwType)
{
  HKEY v5; // rcx

  v5 = *this;
  if ( v5 )
    RegSetValueExW(v5, a2, 0, dwType, lpData, cbData);
}

```

## disassembly

```asm
0x180013e3c  sub     rsp, 38h
0x180013e40  mov     rcx, [rcx]; hKey
0x180013e43  test    rcx, rcx
0x180013e46  jz      short loc_180013E60
0x180013e48  mov     [rsp+38h+cbData], r9d; cbData
0x180013e4d  mov     r9d, [rsp+38h+dwType]; dwType
0x180013e52  mov     [rsp+38h+lpData], r8; lpData
0x180013e57  xor     r8d, r8d; Reserved
0x180013e5a  call    cs:__imp_RegSetValueExW
0x180013e60  add     rsp, 38h
0x180013e64  retn
```
