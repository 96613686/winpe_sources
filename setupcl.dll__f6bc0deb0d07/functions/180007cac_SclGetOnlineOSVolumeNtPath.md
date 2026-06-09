# SclGetOnlineOSVolumeNtPath

- ea: `0x180007cac`
- end: `0x180007d05`
- name: `SclGetOnlineOSVolumeNtPath`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1800065f8`
- `0x18000b90c`

## callees

- `0x180007ac4`
- `0x180007b30`
- `0x180007cac`
- `0x1800179e0`

## pseudocode

```c
__int64 __fastcall SclGetOnlineOSVolumeNtPath(_QWORD *a1)
{
  __int64 result; // rax
  _BYTE v3[528]; // [rsp+20h] [rbp-228h] BYREF

  result = SclExpandString(L"%SYSTEMDRIVE%\\", v3);
  if ( (int)result >= 0 )
    return SclDosPathToNtPath((__int64)v3, a1);
  return result;
}

```

## disassembly

```asm
0x180007cac  push    rbx
0x180007cae  sub     rsp, 240h
0x180007cb5  mov     rax, cs:__security_cookie
0x180007cbc  xor     rax, rsp
0x180007cbf  mov     [rsp+248h+var_18], rax
0x180007cc7  mov     rbx, rcx
0x180007cca  lea     rdx, [rsp+248h+var_228]; void *
0x180007ccf  lea     rcx, aSystemdrive_0; "%SYSTEMDRIVE%\\"
0x180007cd6  call    SclExpandString
0x180007cdb  test    eax, eax
0x180007cdd  js      short loc_180007CEC
0x180007cdf  mov     rdx, rbx
0x180007ce2  lea     rcx, [rsp+248h+var_228]
0x180007ce7  call    SclDosPathToNtPath
0x180007cec  mov     rcx, [rsp+248h+var_18]
0x180007cf4  xor     rcx, rsp; StackCookie
0x180007cf7  call    __security_check_cookie
0x180007cfc  add     rsp, 240h
0x180007d03  pop     rbx
0x180007d04  retn
```
