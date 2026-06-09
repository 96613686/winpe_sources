# GetLastFailureAsHRESULT

- ea: `0x18000f154`
- end: `0x18000f1dc`
- name: `GetLastFailureAsHRESULT`
- size: `136`
- prototype: `__int64()`
- caller_count: `23`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002054`
- `0x1800022e4`
- `0x1800029d8`
- `0x180002e9c`
- `0x180003360`
- `0x180003550`
- `0x180004928`
- `0x180004c2c`
- `0x180004e20`
- `0x18000572c`
- `0x180005e30`
- `0x1800062e8`
- `0x180006840`
- `0x180006b50`
- `0x18000d69c`
- `0x18000dd64`
- `0x18000deac`
- `0x18000e3b8`
- `0x18000e554`
- `0x18000ea60`
- `0x18000ee14`
- `0x18000ef70`
- `0x18000f310`

## callees

- `0x18000f154`
- `0x18000f1e4`
- `0x18000f26c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f163`
- `KERNEL32!GetLastError` at `0x18000f163`
- `ntdll!RtlGetLastNtStatus` at `0x18000f16b`
- `ntdll!RtlGetLastNtStatus` at `0x18000f16b`

## pseudocode

```c
__int64 GetLastFailureAsHRESULT()
{
  signed int LastError; // edi
  unsigned int LastNtStatus; // eax
  __int64 v2; // rdx
  __int64 v3; // r8
  unsigned int v4; // esi
  signed int v5; // ebx

  LastError = GetLastError();
  LastNtStatus = RtlGetLastNtStatus();
  v4 = LastNtStatus;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  else
    v5 = LastError;
  if ( v5 >= 0 )
  {
    v5 = HRESULTFromNTSTATUS(LastNtStatus);
    if ( v5 >= 0 )
      v5 = -1073729531;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
    WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v2, v3, (unsigned int)LastError, v4, v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f154  mov     [rsp+arg_0], rbx
0x18000f159  mov     [rsp+arg_8], rsi
0x18000f15e  push    rdi
0x18000f15f  sub     rsp, 30h
0x18000f163  call    cs:__imp_GetLastError
0x18000f169  mov     edi, eax
0x18000f16b  call    cs:__imp_RtlGetLastNtStatus
0x18000f171  mov     esi, eax
0x18000f173  test    edi, edi
0x18000f175  jg      short loc_18000F17B
0x18000f177  mov     ebx, edi
0x18000f179  jmp     short loc_18000F184
0x18000f17b  movzx   ebx, di
0x18000f17e  or      ebx, 80070000h
0x18000f184  test    ebx, ebx
0x18000f186  js      short loc_18000F19A
0x18000f188  mov     ecx, esi
0x18000f18a  call    HRESULTFromNTSTATUS
0x18000f18f  mov     ebx, eax
0x18000f191  test    eax, eax
0x18000f193  js      short loc_18000F19A
0x18000f195  mov     ebx, 0C0003005h
0x18000f19a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1a1  lea     rax, WPP_GLOBAL_Control
0x18000f1a8  cmp     rcx, rax
0x18000f1ab  jz      short loc_18000F1CA
0x18000f1ad  test    dword ptr [rcx+1Ch], 1000000h
0x18000f1b4  jz      short loc_18000F1CA
0x18000f1b6  mov     rcx, [rcx+10h]
0x18000f1ba  mov     r9d, edi
0x18000f1bd  mov     [rsp+38h+var_10], ebx
0x18000f1c1  mov     [rsp+38h+var_18], esi
0x18000f1c5  call    WPP_SF_Ddd
0x18000f1ca  mov     rsi, [rsp+38h+arg_8]
0x18000f1cf  mov     eax, ebx
0x18000f1d1  mov     rbx, [rsp+38h+arg_0]
0x18000f1d6  add     rsp, 30h
0x18000f1da  pop     rdi
0x18000f1db  retn
```
