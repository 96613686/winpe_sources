# DavReturnSessionPath

- ea: `0x18000656c`
- end: `0x180006610`
- name: `DavReturnSessionPath`
- size: `164`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x180003458`
- `0x180003a9c`

## callees

- `0x1800056f4`
- `0x18000656c`
- `0x18000b7dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065ca`
- `KERNEL32!DosPathToSessionPathW` at `0x1800065c0`
- `KERNEL32!DosPathToSessionPathW` at `0x1800065c0`

## pseudocode

```c
__int64 __fastcall DavReturnSessionPath(__int64 a1)
{
  unsigned int SessionId; // eax
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  v7 = 0;
  SessionId = DavImpersonateAndGetSessionId(&v6);
  if ( SessionId )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v4 = 246;
LABEL_9:
    WPP_SF_d(v3[2], v4, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, SessionId);
    return 0;
  }
  if ( !(unsigned int)DosPathToSessionPathW(v6, a1, &v7) )
  {
    SessionId = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v4 = 247;
    goto LABEL_9;
  }
  return v7;
}

```

## disassembly

```asm
0x18000656c  push    rbx
0x18000656e  sub     rsp, 20h
0x180006572  mov     rbx, rcx
0x180006575  mov     [rsp+28h+arg_8], 0
0x18000657d  lea     rcx, [rsp+28h+arg_8]
0x180006582  mov     [rsp+28h+arg_10], 0
0x18000658b  call    DavImpersonateAndGetSessionId
0x180006590  test    eax, eax
0x180006592  jz      short loc_1800065B4
0x180006594  mov     rcx, cs:WPP_GLOBAL_Control
0x18000659b  lea     rdx, WPP_GLOBAL_Control
0x1800065a2  cmp     rcx, rdx
0x1800065a5  jz      short loc_180006601
0x1800065a7  test    byte ptr [rcx+1Ch], 1
0x1800065ab  jz      short loc_180006601
0x1800065ad  mov     edx, 0F6h
0x1800065b2  jmp     short loc_1800065EE
0x1800065b4  mov     ecx, [rsp+28h+arg_8]
0x1800065b8  lea     r8, [rsp+28h+arg_10]
0x1800065bd  mov     rdx, rbx
0x1800065c0  call    cs:__imp_DosPathToSessionPathW
0x1800065c6  test    eax, eax
0x1800065c8  jnz     short loc_180006605
0x1800065ca  call    cs:__imp_GetLastError
0x1800065d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065d7  lea     rdx, WPP_GLOBAL_Control
0x1800065de  cmp     rcx, rdx
0x1800065e1  jz      short loc_180006601
0x1800065e3  test    byte ptr [rcx+1Ch], 1
0x1800065e7  jz      short loc_180006601
0x1800065e9  mov     edx, 0F7h
0x1800065ee  mov     rcx, [rcx+10h]
0x1800065f2  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x1800065f9  mov     r9d, eax
0x1800065fc  call    WPP_SF_d
0x180006601  xor     eax, eax
0x180006603  jmp     short loc_18000660A
0x180006605  mov     rax, [rsp+28h+arg_10]
0x18000660a  add     rsp, 20h
0x18000660e  pop     rbx
0x18000660f  retn
```
