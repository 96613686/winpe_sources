# GenerateUniqueID

- ea: `0x180004ed0`
- end: `0x180004f51`
- name: `GenerateUniqueID`
- size: `129`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002740`
- `0x180006aac`
- `0x18000a3f8`

## callees

- `0x180004ed0`
- `0x180005730`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180004f13`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180004f13`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004f00`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004f00`
- `ext-ms-win-cng-rng-l1-1-1!ProcessPrngGuid` at `0x180004ef0`
- `ext-ms-win-cng-rng-l1-1-1!ProcessPrngGuid` at `0x180004ef0`

## pseudocode

```c
__int64 __fastcall GenerateUniqueID(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  _SYSTEMTIME SystemTime; // [rsp+20h] [rbp-28h] BYREF

  SystemTime = 0;
  result = ProcessPrngGuid(a1, a2);
  if ( !(_DWORD)result )
  {
    *(_DWORD *)a1 = GetTickCount();
    GetSystemTime(&SystemTime);
    *(_WORD *)(a1 + 4) = SystemTime.wMilliseconds;
    *(_WORD *)(a1 + 6) = SystemTime.wSecond;
    result = SystemTime.wMinute;
    *(_WORD *)(a1 + 12) = SystemTime.wMinute;
    *(_DWORD *)(a1 + 8) = a1;
  }
  return result;
}

```

## disassembly

```asm
0x180004ed0  push    rbx
0x180004ed2  sub     rsp, 40h
0x180004ed6  mov     rax, cs:__security_cookie
0x180004edd  xor     rax, rsp
0x180004ee0  mov     [rsp+48h+var_18], rax
0x180004ee5  xorps   xmm0, xmm0
0x180004ee8  mov     rbx, rcx
0x180004eeb  movups  xmmword ptr [rsp+48h+SystemTime.wYear], xmm0
0x180004ef0  call    cs:__imp_ProcessPrngGuid
0x180004ef7  nop     dword ptr [rax+rax+00h]
0x180004efc  test    eax, eax
0x180004efe  jnz     short loc_180004F3D
0x180004f00  call    cs:__imp_GetTickCount
0x180004f07  nop     dword ptr [rax+rax+00h]
0x180004f0c  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x180004f11  mov     [rbx], eax
0x180004f13  call    cs:__imp_GetSystemTime
0x180004f1a  nop     dword ptr [rax+rax+00h]
0x180004f1f  movzx   eax, [rsp+48h+SystemTime.wMilliseconds]
0x180004f24  mov     [rbx+4], ax
0x180004f28  movzx   eax, [rsp+48h+SystemTime.wSecond]
0x180004f2d  mov     [rbx+6], ax
0x180004f31  movzx   eax, [rsp+48h+SystemTime.wMinute]
0x180004f36  mov     [rbx+0Ch], ax
0x180004f3a  mov     [rbx+8], ebx
0x180004f3d  mov     rcx, [rsp+48h+var_18]
0x180004f42  xor     rcx, rsp; StackCookie
0x180004f45  call    __security_check_cookie
0x180004f4a  add     rsp, 40h
0x180004f4e  pop     rbx
0x180004f4f  retn
```
