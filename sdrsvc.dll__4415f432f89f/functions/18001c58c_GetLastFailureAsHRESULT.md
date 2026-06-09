# GetLastFailureAsHRESULT

- ea: `0x18001c58c`
- end: `0x18001c614`
- name: `GetLastFailureAsHRESULT`
- size: `136`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `36`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000ac34`
- `0x18000b868`
- `0x18000cfb8`
- `0x18000d0a0`
- `0x18000d2bc`
- `0x18000e108`
- `0x18000e420`
- `0x18000f7c4`
- `0x180013a3c`
- `0x180014184`
- `0x18001445c`
- `0x1800148dc`
- `0x1800160c8`
- `0x180016a78`
- `0x180016f68`
- `0x180017454`
- `0x18001764c`
- `0x180017c20`
- `0x180018d38`
- `0x1800190bc`
- `0x18001a71c`
- `0x18001bc78`
- `0x18001be3c`
- `0x18001bfcc`
- `0x18001c0d8`
- `0x18001c28c`
- `0x18001cfc8`
- `0x18001d154`
- `0x18001d2a4`
- `0x18001dd98`
- `0x18001e098`
- `0x18001e2dc`
- `0x18001eda0`
- `0x18001ef88`
- `0x18001f2f4`
- `0x180020808`

## callees

- `0x18001c58c`
- `0x18001c61c`
- `0x18001c698`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c59b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c59b`
- `ntdll!RtlGetLastNtStatus` at `0x18001c5a3`
- `ntdll!RtlGetLastNtStatus` at `0x18001c5a3`

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
0x18001c58c  mov     [rsp+arg_0], rbx
0x18001c591  mov     [rsp+arg_8], rsi
0x18001c596  push    rdi
0x18001c597  sub     rsp, 30h
0x18001c59b  call    cs:__imp_GetLastError
0x18001c5a1  mov     edi, eax
0x18001c5a3  call    cs:__imp_RtlGetLastNtStatus
0x18001c5a9  mov     esi, eax
0x18001c5ab  test    edi, edi
0x18001c5ad  jg      short loc_18001C5B3
0x18001c5af  mov     ebx, edi
0x18001c5b1  jmp     short loc_18001C5BC
0x18001c5b3  movzx   ebx, di
0x18001c5b6  or      ebx, 80070000h
0x18001c5bc  test    ebx, ebx
0x18001c5be  js      short loc_18001C5D2
0x18001c5c0  mov     ecx, esi
0x18001c5c2  call    HRESULTFromNTSTATUS
0x18001c5c7  mov     ebx, eax
0x18001c5c9  test    eax, eax
0x18001c5cb  js      short loc_18001C5D2
0x18001c5cd  mov     ebx, 0C0003005h
0x18001c5d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5d9  lea     rax, WPP_GLOBAL_Control
0x18001c5e0  cmp     rcx, rax
0x18001c5e3  jz      short loc_18001C602
0x18001c5e5  test    dword ptr [rcx+1Ch], 1000000h
0x18001c5ec  jz      short loc_18001C602
0x18001c5ee  mov     rcx, [rcx+10h]
0x18001c5f2  mov     r9d, edi
0x18001c5f5  mov     [rsp+38h+var_10], ebx
0x18001c5f9  mov     [rsp+38h+var_18], esi
0x18001c5fd  call    WPP_SF_Ddd
0x18001c602  mov     rsi, [rsp+38h+arg_8]
0x18001c607  mov     eax, ebx
0x18001c609  mov     rbx, [rsp+38h+arg_0]
0x18001c60e  add     rsp, 30h
0x18001c612  pop     rdi
0x18001c613  retn
```
