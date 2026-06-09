# InitializeStateServiceLogonSid(void *)

- ea: `0x1800f4234`
- end: `0x1800f44d4`
- name: `?InitializeStateServiceLogonSid@@YAJPEAX@Z`
- size: `672`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800f4638`
- `0x1800f6770`

## callees

- `0x180034260`
- `0x18008172c`
- `0x1800f4234`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4344`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4344`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4415`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f4485`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f44aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f4485`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f44aa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f42fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f43d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f42fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f43d7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800f4405`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800f4405`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f4268`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f4334`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f4268`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f4334`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800f43ba`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800f43ba`

## string_xrefs

- `0x1800f42dd`: `onecore\com\combase\rpcss\olescm\scmsvc.cxx`
- `0x1800f446d`: `onecore\com\combase\rpcss\olescm\scmsvc.cxx`
- `0x1800f42d6`: `InitializeStateServiceLogonSid`
- `0x1800f4466`: `InitializeStateServiceLogonSid`

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
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
      if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
        if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
0x1800f4234  mov     rax, rsp
0x1800f4237  mov     [rax+8], rbx
0x1800f423b  mov     [rax+20h], rsi
0x1800f423f  push    rdi
0x1800f4240  sub     rsp, 30h
0x1800f4244  xor     r9d, r9d; TokenInformationLength
0x1800f4247  mov     dword ptr [rax+10h], 0
0x1800f424e  mov     dword ptr [rax+18h], 0
0x1800f4255  lea     rax, [rax+10h]
0x1800f4259  xor     r8d, r8d; TokenInformation
0x1800f425c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800f4261  mov     rsi, rcx
0x1800f4264  lea     edx, [r9+2]; TokenInformationClass
0x1800f4268  call    cs:__imp_GetTokenInformation
0x1800f426f  nop     dword ptr [rax+rax+00h]
0x1800f4274  test    eax, eax
0x1800f4276  jnz     short loc_1800F42EE
0x1800f4278  call    cs:__imp_GetLastError
0x1800f427f  nop     dword ptr [rax+rax+00h]
0x1800f4284  mov     ebx, eax
0x1800f4286  cmp     eax, 7Ah ; 'z'
0x1800f4289  jz      short loc_1800F42EE
0x1800f428b  test    eax, eax
0x1800f428d  jle     short loc_1800F4298
0x1800f428f  movzx   ebx, ax
0x1800f4292  or      ebx, 80070000h
0x1800f4298  mov     eax, cs:dword_1801574B8
0x1800f429e  test    eax, eax
0x1800f42a0  jnz     short loc_1800F42BD
0x1800f42a2  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f42a8  jz      loc_1800F4491
0x1800f42ae  xor     ecx, ecx
0x1800f42b0  call    IsWppLevelEnabled
0x1800f42b5  test    al, al
0x1800f42b7  jz      loc_1800F4491
0x1800f42bd  lea     rax, aHresult; "%!HRESULT!"
0x1800f42c4  mov     [rsp+38h+var_10], ebx
0x1800f42c8  xor     r9d, r9d
0x1800f42cb  mov     [rsp+38h+ReturnLength], rax
0x1800f42d0  mov     r8d, 17Eh
0x1800f42d6  lea     rdx, aInitializestat; "InitializeStateServiceLogonSid"
0x1800f42dd  lea     rcx, aOnecoreComComb_99; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800f42e4  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800f42e9  jmp     loc_1800F4491
0x1800f42ee  mov     r8d, dword ptr [rsp+38h+dwBytes]; dwBytes
0x1800f42f3  xor     edx, edx; dwFlags
0x1800f42f5  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f42fc  call    cs:__imp_HeapAlloc
0x1800f4303  nop     dword ptr [rax+rax+00h]
0x1800f4308  mov     rdi, rax
0x1800f430b  test    rax, rax
0x1800f430e  jnz     short loc_1800F431A
0x1800f4310  mov     ebx, 8007000Eh
0x1800f4315  jmp     loc_1800F4495
0x1800f431a  mov     r9d, dword ptr [rsp+38h+dwBytes]; TokenInformationLength
0x1800f431f  lea     rax, [rsp+38h+arg_10]
0x1800f4324  mov     r8, rdi; TokenInformation
0x1800f4327  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800f432c  mov     edx, 2; TokenInformationClass
0x1800f4331  mov     rcx, rsi; TokenHandle
0x1800f4334  call    cs:__imp_GetTokenInformation
0x1800f433b  nop     dword ptr [rax+rax+00h]
0x1800f4340  test    eax, eax
0x1800f4342  jnz     short loc_1800F438F
0x1800f4344  call    cs:__imp_GetLastError
0x1800f434b  nop     dword ptr [rax+rax+00h]
0x1800f4350  mov     ebx, eax
0x1800f4352  test    eax, eax
0x1800f4354  jle     short loc_1800F435F
0x1800f4356  movzx   ebx, ax
0x1800f4359  or      ebx, 80070000h
0x1800f435f  mov     eax, cs:dword_1801574B8
0x1800f4365  test    eax, eax
0x1800f4367  jnz     short loc_1800F4384
0x1800f4369  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f436f  jz      loc_1800F4479
0x1800f4375  xor     ecx, ecx
0x1800f4377  call    IsWppLevelEnabled
0x1800f437c  test    al, al
0x1800f437e  jz      loc_1800F4479
0x1800f4384  mov     r8d, 192h
0x1800f438a  jmp     loc_1800F4453
0x1800f438f  xor     ebx, ebx
0x1800f4391  xor     eax, eax
0x1800f4393  cmp     [rdi], eax
0x1800f4395  jbe     loc_1800F4479
0x1800f439b  mov     esi, eax
0x1800f439d  add     rsi, rsi
0x1800f43a0  test    dword ptr [rdi+rsi*8+10h], 0C0000000h
0x1800f43a8  jnz     short loc_1800F43B5
0x1800f43aa  inc     eax
0x1800f43ac  cmp     eax, [rdi]
0x1800f43ae  jb      short loc_1800F439B
0x1800f43b0  jmp     loc_1800F4479
0x1800f43b5  mov     rcx, [rdi+rsi*8+8]; pSid
0x1800f43ba  call    cs:__imp_GetLengthSid
0x1800f43c1  nop     dword ptr [rax+rax+00h]
0x1800f43c6  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f43cd  xor     edx, edx; dwFlags
0x1800f43cf  mov     r8d, eax; dwBytes
0x1800f43d2  mov     dword ptr [rsp+38h+dwBytes], r8d
0x1800f43d7  call    cs:__imp_HeapAlloc
0x1800f43de  nop     dword ptr [rax+rax+00h]
0x1800f43e3  mov     cs:?psidStateServiceLogonSid@@3PEAXEA, rax; void * psidStateServiceLogonSid
0x1800f43ea  test    rax, rax
0x1800f43ed  jnz     short loc_1800F43F9
0x1800f43ef  mov     ebx, 8007000Eh
0x1800f43f4  jmp     loc_1800F4479
0x1800f43f9  mov     r8, [rdi+rsi*8+8]; pSourceSid
0x1800f43fe  mov     rdx, rax; pDestinationSid
0x1800f4401  mov     ecx, dword ptr [rsp+38h+dwBytes]; nDestinationSidLength
0x1800f4405  call    cs:__imp_CopySid
0x1800f440c  nop     dword ptr [rax+rax+00h]
0x1800f4411  test    eax, eax
0x1800f4413  jnz     short loc_1800F4479
0x1800f4415  call    cs:__imp_GetLastError
0x1800f441c  nop     dword ptr [rax+rax+00h]
0x1800f4421  mov     ebx, eax
0x1800f4423  test    eax, eax
0x1800f4425  jle     short loc_1800F4430
0x1800f4427  movzx   ebx, ax
0x1800f442a  or      ebx, 80070000h
0x1800f4430  mov     eax, cs:dword_1801574B8
0x1800f4436  test    eax, eax
0x1800f4438  jnz     short loc_1800F444D
0x1800f443a  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f4440  jz      short loc_1800F4479
0x1800f4442  xor     ecx, ecx
0x1800f4444  call    IsWppLevelEnabled
0x1800f4449  test    al, al
0x1800f444b  jz      short loc_1800F4479
0x1800f444d  mov     r8d, 1A7h
0x1800f4453  lea     rax, aHresult; "%!HRESULT!"
0x1800f445a  mov     [rsp+38h+var_10], ebx
0x1800f445e  xor     r9d, r9d
0x1800f4461  mov     [rsp+38h+ReturnLength], rax
0x1800f4466  lea     rdx, aInitializestat; "InitializeStateServiceLogonSid"
0x1800f446d  lea     rcx, aOnecoreComComb_99; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800f4474  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800f4479  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f4480  mov     r8, rdi; lpMem
0x1800f4483  xor     edx, edx; dwFlags
0x1800f4485  call    cs:__imp_HeapFree
0x1800f448c  nop     dword ptr [rax+rax+00h]
0x1800f4491  test    ebx, ebx
0x1800f4493  jns     short loc_1800F44C1
0x1800f4495  mov     r8, cs:?psidStateServiceLogonSid@@3PEAXEA; lpMem
0x1800f449c  test    r8, r8
0x1800f449f  jz      short loc_1800F44C1
0x1800f44a1  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f44a8  xor     edx, edx; dwFlags
0x1800f44aa  call    cs:__imp_HeapFree
0x1800f44b1  nop     dword ptr [rax+rax+00h]
0x1800f44b6  mov     cs:?psidStateServiceLogonSid@@3PEAXEA, 0; void * psidStateServiceLogonSid
0x1800f44c1  mov     rsi, [rsp+38h+arg_18]
0x1800f44c6  mov     eax, ebx
0x1800f44c8  mov     rbx, [rsp+38h+arg_0]
0x1800f44cd  add     rsp, 30h
0x1800f44d1  pop     rdi
0x1800f44d2  retn
```
