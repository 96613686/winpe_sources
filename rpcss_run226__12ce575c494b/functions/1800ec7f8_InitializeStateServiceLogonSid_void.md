# InitializeStateServiceLogonSid(void *)

- ea: `0x1800ec7f8`
- end: `0x1800eca52`
- name: `?InitializeStateServiceLogonSid@@YAJPEAX@Z`
- size: `602`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800ecb9c`
- `0x1800eeb88`

## callees

- `0x180034540`
- `0x18007e3d4`
- `0x1800ec7f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec8f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec9a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec8f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec9a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800eca10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800eca2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800eca10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800eca2f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ec8b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ec977`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ec8b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ec977`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800ec99c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800ec99c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ec82c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ec8e6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ec82c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ec8e6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ec960`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ec960`

## string_xrefs

- `0x1800ec895`: `onecore\com\combase\rpcss\olescm\scmsvc.cxx`
- `0x1800ec9f8`: `onecore\com\combase\rpcss\olescm\scmsvc.cxx`
- `0x1800ec88e`: `InitializeStateServiceLogonSid`
- `0x1800ec9f1`: `InitializeStateServiceLogonSid`

## pseudocode

```c
__int64 __fastcall InitializeStateServiceLogonSid(HANDLE TokenHandle)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  _DWORD *v4; // rdi
  signed int v5; // eax
  int v6; // r8d
  unsigned int v7; // eax
  __int64 v8; // rsi
  void *v9; // rax
  signed int v10; // eax
  SIZE_T dwBytes; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(dwBytes) = 0;
  ReturnLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenGroups, 0, 0, (PDWORD)&dwBytes) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        ComTraceMessageT<long>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmsvc.cxx",
          (unsigned int)"InitializeStateServiceLogonSid",
          382,
          0,
          (__int64)L"%!HRESULT!",
          v3);
LABEL_33:
      if ( (v3 & 0x80000000) == 0 )
        return v3;
      goto LABEL_34;
    }
  }
  v4 = HeapAlloc(g_hHeap, 0, (unsigned int)dwBytes);
  if ( v4 )
  {
    if ( !GetTokenInformation(TokenHandle, TokenGroups, v4, dwBytes, &ReturnLength) )
    {
      v5 = GetLastError();
      v3 = v5;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
        goto LABEL_32;
      v6 = 402;
      goto LABEL_31;
    }
    v3 = 0;
    v7 = 0;
    if ( *v4 )
    {
      while ( 1 )
      {
        v8 = 2LL * v7;
        if ( (v4[4 * v7 + 4] & 0xC0000000) != 0 )
          break;
        if ( ++v7 >= *v4 )
          goto LABEL_32;
      }
      LODWORD(dwBytes) = GetLengthSid(*(PSID *)&v4[4 * v7 + 2]);
      v9 = HeapAlloc(g_hHeap, 0, (unsigned int)dwBytes);
      psidStateServiceLogonSid = v9;
      if ( v9 )
      {
        if ( CopySid(dwBytes, v9, *(PSID *)&v4[2 * v8 + 2]) )
          goto LABEL_32;
        v10 = GetLastError();
        v3 = v10;
        if ( v10 > 0 )
          v3 = (unsigned __int16)v10 | 0x80070000;
        if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
          goto LABEL_32;
        v6 = 423;
LABEL_31:
        ComTraceMessageT<long>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmsvc.cxx",
          (unsigned int)"InitializeStateServiceLogonSid",
          v6,
          0,
          (__int64)L"%!HRESULT!",
          v3);
        goto LABEL_32;
      }
      v3 = -2147024882;
    }
LABEL_32:
    HeapFree(g_hHeap, 0, v4);
    goto LABEL_33;
  }
  v3 = -2147024882;
LABEL_34:
  if ( psidStateServiceLogonSid )
  {
    HeapFree(g_hHeap, 0, psidStateServiceLogonSid);
    psidStateServiceLogonSid = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x1800ec7f8  mov     rax, rsp
0x1800ec7fb  mov     [rax+8], rbx
0x1800ec7ff  mov     [rax+20h], rsi
0x1800ec803  push    rdi
0x1800ec804  sub     rsp, 30h
0x1800ec808  xor     r9d, r9d; TokenInformationLength
0x1800ec80b  mov     dword ptr [rax+10h], 0
0x1800ec812  mov     dword ptr [rax+18h], 0
0x1800ec819  lea     rax, [rax+10h]
0x1800ec81d  xor     r8d, r8d; TokenInformation
0x1800ec820  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800ec825  mov     rsi, rcx
0x1800ec828  lea     edx, [r9+2]; TokenInformationClass
0x1800ec82c  call    cs:__imp_GetTokenInformation
0x1800ec832  test    eax, eax
0x1800ec834  jnz     short loc_1800EC8A6
0x1800ec836  call    cs:__imp_GetLastError
0x1800ec83c  mov     ebx, eax
0x1800ec83e  cmp     eax, 7Ah ; 'z'
0x1800ec841  jz      short loc_1800EC8A6
0x1800ec843  test    eax, eax
0x1800ec845  jle     short loc_1800EC850
0x1800ec847  movzx   ebx, ax
0x1800ec84a  or      ebx, 80070000h
0x1800ec850  mov     eax, cs:dword_18014E4B8
0x1800ec856  test    eax, eax
0x1800ec858  jnz     short loc_1800EC875
0x1800ec85a  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800ec860  jz      loc_1800ECA16
0x1800ec866  xor     ecx, ecx
0x1800ec868  call    IsWppLevelEnabled
0x1800ec86d  test    al, al
0x1800ec86f  jz      loc_1800ECA16
0x1800ec875  lea     rax, aHresult; "%!HRESULT!"
0x1800ec87c  mov     [rsp+38h+var_10], ebx
0x1800ec880  xor     r9d, r9d
0x1800ec883  mov     [rsp+38h+ReturnLength], rax
0x1800ec888  mov     r8d, 17Eh
0x1800ec88e  lea     rdx, aInitializestat; "InitializeStateServiceLogonSid"
0x1800ec895  lea     rcx, aOnecoreComComb_99; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800ec89c  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800ec8a1  jmp     loc_1800ECA16
0x1800ec8a6  mov     r8d, dword ptr [rsp+38h+dwBytes]; dwBytes
0x1800ec8ab  xor     edx, edx; dwFlags
0x1800ec8ad  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ec8b4  call    cs:__imp_HeapAlloc
0x1800ec8ba  mov     rdi, rax
0x1800ec8bd  test    rax, rax
0x1800ec8c0  jnz     short loc_1800EC8CC
0x1800ec8c2  mov     ebx, 8007000Eh
0x1800ec8c7  jmp     loc_1800ECA1A
0x1800ec8cc  mov     r9d, dword ptr [rsp+38h+dwBytes]; TokenInformationLength
0x1800ec8d1  lea     rax, [rsp+38h+arg_10]
0x1800ec8d6  mov     r8, rdi; TokenInformation
0x1800ec8d9  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800ec8de  mov     edx, 2; TokenInformationClass
0x1800ec8e3  mov     rcx, rsi; TokenHandle
0x1800ec8e6  call    cs:__imp_GetTokenInformation
0x1800ec8ec  test    eax, eax
0x1800ec8ee  jnz     short loc_1800EC935
0x1800ec8f0  call    cs:__imp_GetLastError
0x1800ec8f6  mov     ebx, eax
0x1800ec8f8  test    eax, eax
0x1800ec8fa  jle     short loc_1800EC905
0x1800ec8fc  movzx   ebx, ax
0x1800ec8ff  or      ebx, 80070000h
0x1800ec905  mov     eax, cs:dword_18014E4B8
0x1800ec90b  test    eax, eax
0x1800ec90d  jnz     short loc_1800EC92A
0x1800ec90f  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800ec915  jz      loc_1800ECA04
0x1800ec91b  xor     ecx, ecx
0x1800ec91d  call    IsWppLevelEnabled
0x1800ec922  test    al, al
0x1800ec924  jz      loc_1800ECA04
0x1800ec92a  mov     r8d, 192h
0x1800ec930  jmp     loc_1800EC9DE
0x1800ec935  xor     ebx, ebx
0x1800ec937  xor     eax, eax
0x1800ec939  cmp     [rdi], eax
0x1800ec93b  jbe     loc_1800ECA04
0x1800ec941  mov     esi, eax
0x1800ec943  add     rsi, rsi
0x1800ec946  test    dword ptr [rdi+rsi*8+10h], 0C0000000h
0x1800ec94e  jnz     short loc_1800EC95B
0x1800ec950  inc     eax
0x1800ec952  cmp     eax, [rdi]
0x1800ec954  jb      short loc_1800EC941
0x1800ec956  jmp     loc_1800ECA04
0x1800ec95b  mov     rcx, [rdi+rsi*8+8]; pSid
0x1800ec960  call    cs:__imp_GetLengthSid
0x1800ec966  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ec96d  xor     edx, edx; dwFlags
0x1800ec96f  mov     r8d, eax; dwBytes
0x1800ec972  mov     dword ptr [rsp+38h+dwBytes], r8d
0x1800ec977  call    cs:__imp_HeapAlloc
0x1800ec97d  mov     cs:?psidStateServiceLogonSid@@3PEAXEA, rax; void * psidStateServiceLogonSid
0x1800ec984  test    rax, rax
0x1800ec987  jnz     short loc_1800EC990
0x1800ec989  mov     ebx, 8007000Eh
0x1800ec98e  jmp     short loc_1800ECA04
0x1800ec990  mov     r8, [rdi+rsi*8+8]; pSourceSid
0x1800ec995  mov     rdx, rax; pDestinationSid
0x1800ec998  mov     ecx, dword ptr [rsp+38h+dwBytes]; nDestinationSidLength
0x1800ec99c  call    cs:__imp_CopySid
0x1800ec9a2  test    eax, eax
0x1800ec9a4  jnz     short loc_1800ECA04
0x1800ec9a6  call    cs:__imp_GetLastError
0x1800ec9ac  mov     ebx, eax
0x1800ec9ae  test    eax, eax
0x1800ec9b0  jle     short loc_1800EC9BB
0x1800ec9b2  movzx   ebx, ax
0x1800ec9b5  or      ebx, 80070000h
0x1800ec9bb  mov     eax, cs:dword_18014E4B8
0x1800ec9c1  test    eax, eax
0x1800ec9c3  jnz     short loc_1800EC9D8
0x1800ec9c5  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800ec9cb  jz      short loc_1800ECA04
0x1800ec9cd  xor     ecx, ecx
0x1800ec9cf  call    IsWppLevelEnabled
0x1800ec9d4  test    al, al
0x1800ec9d6  jz      short loc_1800ECA04
0x1800ec9d8  mov     r8d, 1A7h
0x1800ec9de  lea     rax, aHresult; "%!HRESULT!"
0x1800ec9e5  mov     [rsp+38h+var_10], ebx
0x1800ec9e9  xor     r9d, r9d
0x1800ec9ec  mov     [rsp+38h+ReturnLength], rax
0x1800ec9f1  lea     rdx, aInitializestat; "InitializeStateServiceLogonSid"
0x1800ec9f8  lea     rcx, aOnecoreComComb_99; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800ec9ff  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800eca04  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800eca0b  mov     r8, rdi; lpMem
0x1800eca0e  xor     edx, edx; dwFlags
0x1800eca10  call    cs:__imp_HeapFree
0x1800eca16  test    ebx, ebx
0x1800eca18  jns     short loc_1800ECA40
0x1800eca1a  mov     r8, cs:?psidStateServiceLogonSid@@3PEAXEA; lpMem
0x1800eca21  test    r8, r8
0x1800eca24  jz      short loc_1800ECA40
0x1800eca26  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800eca2d  xor     edx, edx; dwFlags
0x1800eca2f  call    cs:__imp_HeapFree
0x1800eca35  mov     cs:?psidStateServiceLogonSid@@3PEAXEA, 0; void * psidStateServiceLogonSid
0x1800eca40  mov     rsi, [rsp+38h+arg_18]
0x1800eca45  mov     eax, ebx
0x1800eca47  mov     rbx, [rsp+38h+arg_0]
0x1800eca4c  add     rsp, 30h
0x1800eca50  pop     rdi
0x1800eca51  retn
```
