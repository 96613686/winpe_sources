# HandleDomHierRoleChangeEvent(void *,uchar)

- ea: `0x18002d250`
- end: `0x18002d50f`
- name: `?HandleDomHierRoleChangeEvent@@YAXPEAXE@Z`
- size: `703`
- prototype: `void __fastcall(int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18000e758`
- `0x180039100`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18002aca4`
- `0x18002d250`
- `0x18003081c`
- `0x180031358`
- `0x18004cd1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002d2aa`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002d446`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002d2aa`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18002d446`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d46c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d46c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d3b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d3b2`
- `logoncli!NetLogonGetTimeServiceParentDomain` at `0x18002d35f`
- `logoncli!NetLogonGetTimeServiceParentDomain` at `0x18002d35f`
- `ntdll!RtlNtStatusToDosError` at `0x18002d317`
- `ntdll!RtlNtStatusToDosError` at `0x18002d317`
- `DSROLE!DsRoleFreeMemory` at `0x18002d485`
- `DSROLE!DsRoleFreeMemory` at `0x18002d485`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18002d2cc`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18002d2cc`
- `netutils!NetApiBufferFree` at `0x18002d49b`
- `netutils!NetApiBufferFree` at `0x18002d49b`

## string_xrefs

- `0x18002d4da`: `Failed in handling domain hierarchy role change, restart service async`

## pseudocode

```c
void __fastcall HandleDomHierRoleChangeEvent(int *a1)
{
  signed int PrimaryDomainInformation; // eax
  int updated; // ebx
  PBYTE v3; // rcx
  NTSTATUS v4; // eax
  signed int v5; // eax
  int TimeServiceParentDomain; // eax
  char v7; // r14
  unsigned int v8; // r15d
  char v9; // al
  bool v10; // sf
  char v11; // [rsp+20h] [rbp-78h]
  BOOL v12; // [rsp+28h] [rbp-70h]
  LPVOID v13; // [rsp+30h] [rbp-68h] BYREF
  __int64 v14; // [rsp+38h] [rbp-60h]
  int v16; // [rsp+B0h] [rbp+18h] BYREF
  PBYTE Buffer; // [rsp+B8h] [rbp+20h] BYREF

  v11 = 0;
  v16 = 0;
  Buffer = 0;
  v13 = 0;
  v12 = 0;
  if ( (unsigned __int8)FileLogAllowEntry(52) )
    FileLogAdd(L"  DomainHierarchy: LSA role change notification. Redetecting.\n");
  v14 = _set_se_translator(SeTransFunc);
  PrimaryDomainInformation = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer);
  if ( PrimaryDomainInformation )
  {
    if ( PrimaryDomainInformation > 0 )
      updated = (unsigned __int16)PrimaryDomainInformation | 0x80070000;
    else
      updated = PrimaryDomainInformation;
    goto LABEL_30;
  }
  v3 = Buffer;
  dword_1800A45C0 = *(_DWORD *)Buffer;
  if ( (*(_DWORD *)Buffer & 0xFFFFFFFD) != 0 )
  {
    v4 = NlWaitForNetlogon((unsigned int)Buffer);
    if ( v4 < 0 )
    {
      v5 = RtlNtStatusToDosError(v4);
      updated = v5;
      if ( v5 > 0 )
        updated = (unsigned __int16)v5 | 0x80070000;
      goto LABEL_30;
    }
    v3 = Buffer;
  }
  if ( (unsigned int)(*(_DWORD *)v3 - 4) > 1 )
    goto LABEL_28;
  TimeServiceParentDomain = NetLogonGetTimeServiceParentDomain(0, &v13, &v16);
  updated = TimeServiceParentDomain;
  if ( !TimeServiceParentDomain || TimeServiceParentDomain == 1355 )
  {
    v7 = *(_DWORD *)Buffer == 5 && !v13;
    EnterCriticalSection(&CriticalSection);
    v11 = 1;
    if ( v7 != byte_1800A45BC )
    {
      byte_1800A45BC = v7;
      v8 = dword_1800A468C;
      updated = UpdateNetlogonServiceBits(0);
      if ( updated < 0 )
      {
LABEL_29:
        LeaveCriticalSection(&CriticalSection);
        goto LABEL_30;
      }
      v12 = v8 != dword_1800A468C;
      v9 = FileLogAllowEntry(52);
      if ( v7 )
      {
        if ( v9 )
          FileLogAdd(L"    DomainHierarchy:  we are now the domain root.  Should be advertised as reliable\n");
      }
      else if ( v9 )
      {
        FileLogAdd(L"    DomainHierarchy:  we are no longer the domain root.  Should NOT be advertised as reliable\n");
      }
    }
LABEL_28:
    _set_se_translator(v14);
    _InterlockedExchange(&s_bNetlogonSuccessfullyChecked, 1);
    updated = 0;
    if ( !v11 )
      goto LABEL_30;
    goto LABEL_29;
  }
  if ( TimeServiceParentDomain > 0 )
    updated = (unsigned __int16)TimeServiceParentDomain | 0x80070000;
LABEL_30:
  if ( Buffer )
    DsRoleFreeMemory(Buffer);
  if ( v13 )
    NetApiBufferFree(v13);
  if ( v12 )
  {
    v10 = updated < 0;
    if ( updated )
      goto LABEL_38;
    SetNetlogonServiceBitsActual(dword_1800A468C);
  }
  v10 = updated < 0;
LABEL_38:
  if ( v10 )
  {
    if ( a1 )
    {
      *a1 = updated;
    }
    else
    {
      if ( (unsigned __int8)FileLogAllowEntry(73) )
        FileLogAdd(L"Failed in handling domain hierarchy role change, restart service async");
      NotifyShutdown(updated);
    }
  }
}

```

## disassembly

```asm
0x18002d250  mov     rax, rsp
0x18002d253  mov     [rax+10h], rbx
0x18002d257  mov     [rax+8], rcx
0x18002d25b  push    rsi
0x18002d25c  push    r14
0x18002d25e  push    r15
0x18002d260  sub     rsp, 80h
0x18002d267  mov     byte ptr [rax-78h], 0
0x18002d26b  mov     dword ptr [rax+18h], 0
0x18002d272  mov     qword ptr [rax+20h], 0
0x18002d27a  mov     qword ptr [rax-68h], 0
0x18002d282  mov     dword ptr [rax-70h], 0
0x18002d289  mov     ecx, 34h ; '4'
0x18002d28e  call    FileLogAllowEntry
0x18002d293  test    al, al
0x18002d295  jz      short loc_18002D2A3
0x18002d297  lea     rcx, aDomainhierarch; "  DomainHierarchy: LSA role change noti"...
0x18002d29e  call    FileLogAdd
0x18002d2a3  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18002d2aa  call    cs:__imp__set_se_translator
0x18002d2b1  nop     dword ptr [rax+rax+00h]
0x18002d2b6  mov     [rsp+98h+var_60], rax
0x18002d2bb  xor     ebx, ebx
0x18002d2bd  lea     r8, [rsp+98h+Buffer]; Buffer
0x18002d2c5  lea     esi, [rbx+1]
0x18002d2c8  mov     edx, esi; InfoLevel
0x18002d2ca  xor     ecx, ecx; lpServer
0x18002d2cc  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x18002d2d3  nop     dword ptr [rax+rax+00h]
0x18002d2d8  test    eax, eax
0x18002d2da  jz      short loc_18002D2F4
0x18002d2dc  jg      short loc_18002D2E2
0x18002d2de  mov     ebx, eax
0x18002d2e0  jmp     short loc_18002D2EB
0x18002d2e2  movzx   ebx, ax
0x18002d2e5  or      ebx, 80070000h
0x18002d2eb  mov     [rsp+98h+var_74], ebx
0x18002d2ef  jmp     loc_18002D478
0x18002d2f4  mov     rcx, [rsp+98h+Buffer]; unsigned int
0x18002d2fc  mov     eax, [rcx]
0x18002d2fe  mov     cs:dword_1800A45C0, eax
0x18002d304  test    dword ptr [rcx], 0FFFFFFFDh
0x18002d30a  jz      short loc_18002D343
0x18002d30c  call    ?NlWaitForNetlogon@@YAJK@Z; NlWaitForNetlogon(ulong)
0x18002d311  test    eax, eax
0x18002d313  jns     short loc_18002D33B
0x18002d315  mov     ecx, eax; Status
0x18002d317  call    cs:__imp_RtlNtStatusToDosError
0x18002d31e  nop     dword ptr [rax+rax+00h]
0x18002d323  mov     ebx, eax
0x18002d325  test    eax, eax
0x18002d327  jle     short loc_18002D332
0x18002d329  movzx   ebx, ax
0x18002d32c  or      ebx, 80070000h
0x18002d332  mov     [rsp+98h+var_74], ebx
0x18002d336  jmp     loc_18002D478
0x18002d33b  mov     rcx, [rsp+98h+Buffer]
0x18002d343  mov     eax, [rcx]
0x18002d345  sub     eax, 4
0x18002d348  cmp     eax, esi
0x18002d34a  ja      loc_18002D432
0x18002d350  lea     r8, [rsp+98h+arg_10]
0x18002d358  lea     rdx, [rsp+98h+var_68]
0x18002d35d  xor     ecx, ecx
0x18002d35f  call    cs:__imp_NetLogonGetTimeServiceParentDomain
0x18002d366  nop     dword ptr [rax+rax+00h]
0x18002d36b  mov     ebx, eax
0x18002d36d  test    eax, eax
0x18002d36f  jz      short loc_18002D38E
0x18002d371  cmp     eax, 54Bh
0x18002d376  jz      short loc_18002D38E
0x18002d378  test    eax, eax
0x18002d37a  jle     short loc_18002D385
0x18002d37c  movzx   ebx, ax
0x18002d37f  or      ebx, 80070000h
0x18002d385  mov     [rsp+98h+var_74], ebx
0x18002d389  jmp     loc_18002D478
0x18002d38e  mov     rax, [rsp+98h+Buffer]
0x18002d396  cmp     dword ptr [rax], 5
0x18002d399  jnz     short loc_18002D3A8
0x18002d39b  cmp     [rsp+98h+var_68], 0
0x18002d3a1  jnz     short loc_18002D3A8
0x18002d3a3  mov     r14b, sil
0x18002d3a6  jmp     short loc_18002D3AB
0x18002d3a8  xor     r14b, r14b
0x18002d3ab  lea     rcx, CriticalSection; lpCriticalSection
0x18002d3b2  call    cs:__imp_EnterCriticalSection
0x18002d3b9  nop     dword ptr [rax+rax+00h]
0x18002d3be  xor     ebx, ebx
0x18002d3c0  mov     [rsp+98h+var_74], ebx
0x18002d3c4  mov     [rsp+98h+var_78], sil
0x18002d3c9  cmp     r14b, cs:byte_1800A45BC
0x18002d3d0  jz      short loc_18002D432
0x18002d3d2  mov     cs:byte_1800A45BC, r14b
0x18002d3d9  mov     r15d, cs:dword_1800A468C
0x18002d3e0  xor     ecx, ecx; bool
0x18002d3e2  call    ?UpdateNetlogonServiceBits@@YAJ_N@Z; UpdateNetlogonServiceBits(bool)
0x18002d3e7  mov     ebx, eax
0x18002d3e9  mov     [rsp+98h+var_74], eax
0x18002d3ed  test    eax, eax
0x18002d3ef  jns     short loc_18002D3F3
0x18002d3f1  jmp     short loc_18002D465
0x18002d3f3  mov     eax, cs:dword_1800A468C
0x18002d3f9  xor     edx, edx
0x18002d3fb  cmp     r15d, eax
0x18002d3fe  setnz   dl
0x18002d401  mov     [rsp+98h+var_70], edx
0x18002d405  mov     ecx, 34h ; '4'
0x18002d40a  call    FileLogAllowEntry
0x18002d40f  test    r14b, r14b
0x18002d412  jz      short loc_18002D421
0x18002d414  test    al, al
0x18002d416  jz      short loc_18002D432
0x18002d418  lea     rcx, aDomainhierarch_0; "    DomainHierarchy:  we are now the do"...
0x18002d41f  jmp     short loc_18002D42C
0x18002d421  test    al, al
0x18002d423  jz      short loc_18002D432
0x18002d425  lea     rcx, aDomainhierarch_1; "    DomainHierarchy:  we are no longer "...
0x18002d42c  call    FileLogAdd
0x18002d431  nop
0x18002d432  jmp     short loc_18002D441
0x18002d434  jmp     short loc_18002D438
0x18002d436  jmp     short $+2
0x18002d438  mov     esi, 1
0x18002d43d  mov     ebx, [rsp+98h+var_74]
0x18002d441  mov     rcx, [rsp+98h+var_60]
0x18002d446  call    cs:__imp__set_se_translator
0x18002d44d  nop     dword ptr [rax+rax+00h]
0x18002d452  test    ebx, ebx
0x18002d454  js      short loc_18002D45E
0x18002d456  xchg    esi, cs:?s_bNetlogonSuccessfullyChecked@@3HC; int volatile s_bNetlogonSuccessfullyChecked
0x18002d45c  xor     ebx, ebx
0x18002d45e  cmp     [rsp+98h+var_78], 0
0x18002d463  jz      short loc_18002D478
0x18002d465  lea     rcx, CriticalSection; lpCriticalSection
0x18002d46c  call    cs:__imp_LeaveCriticalSection
0x18002d473  nop     dword ptr [rax+rax+00h]
0x18002d478  mov     rcx, [rsp+98h+Buffer]; Buffer
0x18002d480  test    rcx, rcx
0x18002d483  jz      short loc_18002D491
0x18002d485  call    cs:__imp_DsRoleFreeMemory
0x18002d48c  nop     dword ptr [rax+rax+00h]
0x18002d491  mov     rcx, [rsp+98h+var_68]; Buffer
0x18002d496  test    rcx, rcx
0x18002d499  jz      short loc_18002D4A7
0x18002d49b  call    cs:__imp_NetApiBufferFree
0x18002d4a2  nop     dword ptr [rax+rax+00h]
0x18002d4a7  cmp     [rsp+98h+var_70], 0
0x18002d4ac  jz      short loc_18002D4BD
0x18002d4ae  test    ebx, ebx
0x18002d4b0  jnz     short loc_18002D4BF
0x18002d4b2  mov     ecx, cs:dword_1800A468C; unsigned int
0x18002d4b8  call    ?SetNetlogonServiceBitsActual@@YAJK@Z; SetNetlogonServiceBitsActual(ulong)
0x18002d4bd  test    ebx, ebx
0x18002d4bf  jns     short loc_18002D4F9
0x18002d4c1  cmp     [rsp+98h+arg_0], 0
0x18002d4ca  jnz     short loc_18002D4EF
0x18002d4cc  mov     ecx, 49h ; 'I'
0x18002d4d1  call    FileLogAllowEntry
0x18002d4d6  test    al, al
0x18002d4d8  jz      short loc_18002D4E6
0x18002d4da  lea     rcx, aFailedInHandli_0; "Failed in handling domain hierarchy rol"...
0x18002d4e1  call    FileLogAdd
0x18002d4e6  mov     ecx, ebx; unsigned int
0x18002d4e8  call    ?NotifyShutdown@@YAJK@Z; NotifyShutdown(ulong)
0x18002d4ed  jmp     short loc_18002D4F9
0x18002d4ef  mov     rax, [rsp+98h+arg_0]
0x18002d4f7  mov     [rax], ebx
0x18002d4f9  mov     rbx, [rsp+98h+arg_8]
0x18002d501  add     rsp, 80h
0x18002d508  pop     r15
0x18002d50a  pop     r14
0x18002d50c  pop     rsi
0x18002d50d  retn
```
