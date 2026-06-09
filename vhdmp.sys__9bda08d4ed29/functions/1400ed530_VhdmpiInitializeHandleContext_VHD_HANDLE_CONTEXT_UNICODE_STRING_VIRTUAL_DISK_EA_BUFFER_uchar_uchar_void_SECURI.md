# VhdmpiInitializeHandleContext(_VHD_HANDLE_CONTEXT *,_UNICODE_STRING *,_VIRTUAL_DISK_EA_BUFFER *,uchar,uchar,void *,_SECURITY_SUBJECT_CONTEXT *)

- ea: `0x1400ed530`
- end: `0x1400ed9d7`
- name: `?VhdmpiInitializeHandleContext@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_UNICODE_STRING@@PEAU_VIRTUAL_DISK_EA_BUFFER@@EEPEAXPEAU_SECURITY_SUBJECT_CONTEXT@@@Z`
- size: `1191`
- prototype: `__int64 __fastcall(struct _VHD_HANDLE_CONTEXT *, struct _UNICODE_STRING *, struct _VIRTUAL_DISK_EA_BUFFER *, unsigned __int8, char, _OWORD *, struct _SECURITY_SUBJECT_CONTEXT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400e9d84`

## callees

- `0x14001e0e4`
- `0x140020800`
- `0x140023980`
- `0x140026e20`
- `0x140036284`
- `0x14005dce0`
- `0x14005e100`
- `0x14009df3c`
- `0x1400e6dfc`
- `0x1400e8f68`
- `0x1400ed530`

## import_xrefs

- `ntoskrnl!SeTokenType` at `0x1400ed6d8`
- `ntoskrnl!SeTokenType` at `0x1400ed749`
- `ntoskrnl!SeTokenType` at `0x1400ed6d8`
- `ntoskrnl!SeTokenType` at `0x1400ed749`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400ed978`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400ed98e`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400ed978`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400ed98e`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400ed99d`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400ed99d`
- `ntoskrnl!KeInitializeMutex` at `0x1400ed58a`
- `ntoskrnl!KeInitializeMutex` at `0x1400ed58a`
- `ntoskrnl!KeInitializeEvent` at `0x1400ed5a7`
- `ntoskrnl!KeInitializeEvent` at `0x1400ed5c0`
- `ntoskrnl!KeInitializeEvent` at `0x1400ed5a7`
- `ntoskrnl!KeInitializeEvent` at `0x1400ed5c0`

## string_xrefs

- `0x1400ed675`: `Failed to impersonate.`
- `0x1400ed71f`: `Incorrect impersonation level provided.`
- `0x1400ed7ea`: `OPEN_VIRTUAL_DISK_FLAG_NO_PARENTS and OPEN_VIRTUAL_DISK_FLAG_CUSTOM_DIFF_CHAIN are mutually exclusive`

## pseudocode

```c
__int64 __fastcall VhdmpiInitializeHandleContext(
        struct _VHD_HANDLE_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _VIRTUAL_DISK_EA_BUFFER *a3,
        unsigned __int8 a4,
        char a5,
        _OWORD *a6,
        struct _SECURITY_SUBJECT_CONTEXT *a7)
{
  unsigned int v10; // r12d
  int v11; // eax
  int v12; // eax
  int v13; // eax
  PACCESS_TOKEN ClientToken; // rbp
  __int64 v15; // rdx
  int v16; // ebx
  __int64 v17; // r8
  void *v18; // rcx
  int v19; // edx
  int v20; // ecx
  int v21; // eax
  int v22; // eax
  int v23; // ecx
  char v25; // [rsp+28h] [rbp-60h]
  _OWORD v26[5]; // [rsp+30h] [rbp-58h] BYREF

  memset((char *)a1 + 4, 0, 0x1BCu);
  *(_DWORD *)a1 = 1481917270;
  v26[0] = 0;
  v10 = 0;
  *((_DWORD *)a1 + 74) = VhdmpiGetDriveType((char *)a3 + 16, 0);
  KeInitializeMutex((PRKMUTEX)((char *)a1 + 128), 0);
  KeInitializeEvent((PRKEVENT)a1 + 8, NotificationEvent, 1u);
  KeInitializeEvent((PRKEVENT)((char *)a1 + 224), SynchronizationEvent, 1u);
  VhdmpiInitializePassiveLock((char *)a1 + 104);
  v11 = *((_DWORD *)a3 + 13);
  if ( v11 != 1 )
  {
    if ( v11 != 2 )
      goto LABEL_13;
    if ( *((_DWORD *)a3 + 14) )
    {
      *((_DWORD *)a1 + 1) |= 0x10u;
      v10 = 1;
    }
    if ( *((_DWORD *)a3 + 15) == 1 )
      *((_DWORD *)a1 + 1) |= 0x80u;
    goto LABEL_11;
  }
  *((_DWORD *)a1 + 1) |= 1u;
  v12 = *((_DWORD *)a3 + 11);
  *((_DWORD *)a1 + 2) = v12;
  if ( (v12 & 0x30000) != 0 )
  {
    v12 |= 0x40000u;
    *((_DWORD *)a1 + 2) = v12;
  }
  if ( (v12 & 0x320000) != 0 )
  {
LABEL_11:
    v13 = *((_DWORD *)a3 + 12);
    goto LABEL_12;
  }
  *((_DWORD *)a1 + 1) |= 0x80u;
  v13 = 0;
LABEL_12:
  *((_DWORD *)a1 + 3) = v13;
LABEL_13:
  ClientToken = a7->ClientToken;
  if ( !a7->ClientToken )
    ClientToken = a7->PrimaryToken;
  v16 = VhdmpiBeginImpersonation(ClientToken);
  if ( v16 < 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 1) )
      TraceEvents((int)"VhdmpiInitializeHandleContext", 3298, 2, 1, "Failed to impersonate.", v25);
    return (unsigned int)v16;
  }
  v17 = *((_DWORD *)a1 + 1) >> 7;
  LOBYTE(v15) = a5;
  LOBYTE(v17) = (*((_DWORD *)a1 + 1) & 0x80) != 0;
  VhdmpiInitializeSecurityContextFromScope((char *)a1 + 16, v15, v17);
  VhdmpiEndImpersonation(v26);
  if ( a5 )
  {
    v18 = (void *)*((_QWORD *)a1 + 2);
    if ( !v18 )
      v18 = (void *)*((_QWORD *)a1 + 4);
    if ( SeTokenType(v18) == TokenImpersonation && *((int *)a1 + 6) < 2 )
    {
      if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 1) )
        return (unsigned int)-1073741659;
      v20 = 3323;
LABEL_27:
      TraceEvents((int)"VhdmpiInitializeHandleContext", v20, 2, v19, "Incorrect impersonation level provided.", v25);
      return (unsigned int)-1073741659;
    }
  }
  else if ( SeTokenType(ClientToken) == TokenImpersonation && a7->ImpersonationLevel < SecurityImpersonation )
  {
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 1) )
      return (unsigned int)-1073741659;
    v20 = 3336;
    goto LABEL_27;
  }
  if ( *((_DWORD *)a1 + 74) == 4
    && ((unsigned int)VhdmpiGetDriveTypeFromFileName(a2) != 4
     || *((_DWORD *)a3 + 13) == 1
     || (*((_DWORD *)a3 + 10) & 0x14) != 0) )
  {
    return (unsigned int)-1073741811;
  }
  v21 = *((_DWORD *)a3 + 10);
  if ( (v21 & 1) != 0 && (v21 & 0x10) != 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents(
        (int)"VhdmpiInitializeHandleContext",
        3359,
        2,
        16,
        "OPEN_VIRTUAL_DISK_FLAG_NO_PARENTS and OPEN_VIRTUAL_DISK_FLAG_CUSTOM_DIFF_CHAIN are mutually exclusive",
        v25);
    return (unsigned int)-1073741811;
  }
  if ( (v21 & 0x40) != 0 )
  {
    if ( *((_DWORD *)a1 + 74) != 4 || (*((_DWORD *)a3 + 10) & 1) != 0 )
      return (unsigned int)-1073741811;
    *((_DWORD *)a1 + 1) |= 0x800u;
  }
  if ( (*((_DWORD *)a3 + 10) & 1) != 0 )
    *((_DWORD *)a1 + 1) |= 2u;
  if ( (*((_DWORD *)a3 + 10) & 2) != 0 )
  {
    *((_DWORD *)a1 + 1) |= 4u;
    ++v10;
  }
  if ( (*((_DWORD *)a3 + 10) & 4) != 0 )
  {
    *((_DWORD *)a1 + 1) |= 8u;
    ++v10;
  }
  if ( (*((_DWORD *)a3 + 10) & 8) != 0 )
    *((_DWORD *)a1 + 1) |= 0x20u;
  if ( (*((_DWORD *)a3 + 10) & 0x20) != 0 )
    *((_DWORD *)a1 + 1) |= 0x60u;
  if ( *((int *)a3 + 10) < 0 )
    *((_DWORD *)a1 + 1) |= 0x400u;
  if ( (*((_DWORD *)a3 + 10) & 0x10) != 0 )
  {
    v22 = *((_DWORD *)a1 + 1);
    if ( (v22 & 0x80u) == 0 || (v22 & 0x10) != 0 )
      return (unsigned int)-1073741811;
    *((_DWORD *)a1 + 1) = v22 | 0x102;
  }
  if ( (*((_DWORD *)a3 + 10) & 0x80u) != 0 )
    *((_DWORD *)a1 + 1) |= 0x2000u;
  if ( (*((_DWORD *)a3 + 10) & 0x100) != 0 )
    *((_DWORD *)a1 + 1) |= 0x4000u;
  if ( (*((_DWORD *)a3 + 10) & 0x200) != 0 )
    *((_DWORD *)a1 + 1) |= 0x8000u;
  if ( (*((_DWORD *)a3 + 10) & 0x400) != 0 )
    *((_DWORD *)a1 + 1) |= 0x10000u;
  if ( (*((_DWORD *)a3 + 10) & 0x800) != 0 )
    *((_DWORD *)a1 + 1) |= 0x20000u;
  if ( memcmp((char *)a3 + 64, &VhdmpZeroGuid, 0x10u) )
  {
    if ( *((_DWORD *)a1 + 74) != 4 )
      return (unsigned int)-1073741811;
    if ( *((_BYTE *)a3 + 80) == 1 )
    {
      if ( (*((_DWORD *)a1 + 1) & 0x80u) == 0 )
        return (unsigned int)-1073741811;
    }
    else if ( *((_BYTE *)a3 + 80) != 4 )
    {
      return (unsigned int)-1073741811;
    }
    *((_DWORD *)a1 + 1) |= 0x1000u;
    *(_OWORD *)((char *)a1 + 312) = *((_OWORD *)a3 + 4);
    *((_WORD *)a1 + 164) = *((unsigned __int8 *)a3 + 80);
  }
  if ( v10 > 1 )
    return (unsigned int)-1073741811;
  v23 = *((_DWORD *)a1 + 1) ^ (*((_DWORD *)a1 + 1) ^ (a4 << 9)) & 0x200;
  *((_DWORD *)a1 + 1) = v23;
  if ( a6 && (v23 & 0x10) == 0 )
    *(_OWORD *)((char *)a1 + 248) = *a6;
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)a1 + 33);
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)a1 + 34);
  ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)a1 + 34);
  *((_QWORD *)a1 + 49) = _InterlockedIncrement64(&HandleContextNextEventIdentifier);
  return 0;
}

```

## disassembly

```asm
0x1400ed530  mov     [rsp+arg_18], r9b
0x1400ed535  push    rbx
0x1400ed536  push    rbp
0x1400ed537  push    rsi
0x1400ed538  push    rdi
0x1400ed539  push    r12
0x1400ed53b  push    r13
0x1400ed53d  push    r14
0x1400ed53f  push    r15
0x1400ed541  sub     rsp, 48h
0x1400ed545  mov     rsi, r8
0x1400ed548  mov     r13, rdx
0x1400ed54b  mov     rdi, rcx
0x1400ed54e  xor     edx, edx; Val
0x1400ed550  add     rcx, 4; void *
0x1400ed554  mov     r8d, 1BCh; Size
0x1400ed55a  call    memset
0x1400ed55f  xorps   xmm0, xmm0
0x1400ed562  mov     dword ptr [rdi], 58544356h
0x1400ed568  lea     rcx, [rsi+10h]
0x1400ed56c  xor     edx, edx
0x1400ed56e  movups  [rsp+88h+var_58], xmm0
0x1400ed573  xor     r12d, r12d
0x1400ed576  call    VhdmpiGetDriveType
0x1400ed57b  lea     rcx, [rdi+80h]; Mutex
0x1400ed582  mov     [rdi+128h], eax
0x1400ed588  xor     edx, edx; Level
0x1400ed58a  call    cs:__imp_KeInitializeMutex
0x1400ed591  nop     dword ptr [rax+rax+00h]
0x1400ed596  lea     r15d, [r12+1]
0x1400ed59b  xor     edx, edx; Type
0x1400ed59d  mov     r8b, r15b; State
0x1400ed5a0  lea     rcx, [rdi+0C0h]; Event
0x1400ed5a7  call    cs:__imp_KeInitializeEvent
0x1400ed5ae  nop     dword ptr [rax+rax+00h]
0x1400ed5b3  lea     rcx, [rdi+0E0h]; Event
0x1400ed5ba  mov     r8b, r15b; State
0x1400ed5bd  mov     edx, r15d; Type
0x1400ed5c0  call    cs:__imp_KeInitializeEvent
0x1400ed5c7  nop     dword ptr [rax+rax+00h]
0x1400ed5cc  lea     rcx, [rdi+68h]
0x1400ed5d0  call    VhdmpiInitializePassiveLock
0x1400ed5d5  mov     eax, [rsi+34h]
0x1400ed5d8  lea     edx, [r15+7Fh]
0x1400ed5dc  cmp     eax, r15d
0x1400ed5df  jnz     short loc_1400ED607
0x1400ed5e1  or      [rdi+4], r15d
0x1400ed5e5  mov     eax, [rsi+2Ch]
0x1400ed5e8  mov     [rdi+8], eax
0x1400ed5eb  test    eax, 30000h
0x1400ed5f0  jz      short loc_1400ED5F9
0x1400ed5f2  bts     eax, 12h
0x1400ed5f6  mov     [rdi+8], eax
0x1400ed5f9  test    eax, 320000h
0x1400ed5fe  jnz     short loc_1400ED622
0x1400ed600  or      [rdi+4], edx
0x1400ed603  xor     eax, eax
0x1400ed605  jmp     short loc_1400ED625
0x1400ed607  cmp     eax, 2
0x1400ed60a  jnz     short loc_1400ED628
0x1400ed60c  cmp     [rsi+38h], r12d
0x1400ed610  jz      short loc_1400ED619
0x1400ed612  or      dword ptr [rdi+4], 10h
0x1400ed616  mov     r12d, r15d
0x1400ed619  cmp     [rsi+3Ch], r15d
0x1400ed61d  jnz     short loc_1400ED622
0x1400ed61f  or      [rdi+4], edx
0x1400ed622  mov     eax, [rsi+30h]
0x1400ed625  mov     [rdi+0Ch], eax
0x1400ed628  mov     r14, [rsp+88h+arg_30]
0x1400ed630  mov     rbp, [r14]
0x1400ed633  test    rbp, rbp
0x1400ed636  jnz     short loc_1400ED63C
0x1400ed638  mov     rbp, [r14+10h]
0x1400ed63c  lea     rdx, [rsp+88h+var_58]
0x1400ed641  mov     rcx, rbp; Token
0x1400ed644  call    VhdmpiBeginImpersonation
0x1400ed649  mov     ebx, eax
0x1400ed64b  test    eax, eax
0x1400ed64d  jns     short loc_1400ED6A0
0x1400ed64f  mov     ecx, cs:dword_1400876D0
0x1400ed655  cmp     ecx, 2
0x1400ed658  jbe     loc_1400ED9C3
0x1400ed65e  mov     rdx, r15
0x1400ed661  lea     rcx, dword_1400876D0
0x1400ed668  call    _tlgKeywordOn
0x1400ed66d  test    al, al
0x1400ed66f  jz      loc_1400ED9C3
0x1400ed675  lea     rax, aFailedToImpers_0; "Failed to impersonate."
0x1400ed67c  mov     edx, 0CE2h; int
0x1400ed681  mov     r9d, r15d; int
0x1400ed684  mov     [rsp+88h+var_68], rax; char *
0x1400ed689  mov     r8d, 2; int
0x1400ed68f  lea     rcx, aVhdmpiinitiali_35; "VhdmpiInitializeHandleContext"
0x1400ed696  call    TraceEvents
0x1400ed69b  jmp     loc_1400ED9C3
0x1400ed6a0  mov     r8d, [rdi+4]
0x1400ed6a4  lea     rcx, [rdi+10h]
0x1400ed6a8  mov     bl, [rsp+88h+arg_20]
0x1400ed6af  shr     r8d, 7
0x1400ed6b3  mov     dl, bl
0x1400ed6b5  and     r8b, r15b
0x1400ed6b8  call    VhdmpiInitializeSecurityContextFromScope
0x1400ed6bd  lea     rcx, [rsp+88h+var_58]
0x1400ed6c2  call    VhdmpiEndImpersonation
0x1400ed6c7  test    bl, bl
0x1400ed6c9  jz      short loc_1400ED746
0x1400ed6cb  mov     rcx, [rdi+10h]
0x1400ed6cf  test    rcx, rcx
0x1400ed6d2  jnz     short loc_1400ED6D8
0x1400ed6d4  mov     rcx, [rdi+20h]; Token
0x1400ed6d8  call    cs:__imp_SeTokenType
0x1400ed6df  nop     dword ptr [rax+rax+00h]
0x1400ed6e4  mov     ebx, 2
0x1400ed6e9  cmp     eax, ebx
0x1400ed6eb  jnz     loc_1400ED788
0x1400ed6f1  cmp     [rdi+18h], ebx
0x1400ed6f4  jge     loc_1400ED788
0x1400ed6fa  mov     eax, cs:dword_1400876D0
0x1400ed700  cmp     eax, ebx
0x1400ed702  jbe     short loc_1400ED73C
0x1400ed704  mov     rdx, r15
0x1400ed707  lea     rcx, dword_1400876D0
0x1400ed70e  call    _tlgKeywordOn
0x1400ed713  test    al, al
0x1400ed715  jz      short loc_1400ED73C
0x1400ed717  mov     ecx, 0CFBh
0x1400ed71c  mov     r9d, edx; int
0x1400ed71f  lea     rax, aIncorrectImper; "Incorrect impersonation level provided."
0x1400ed726  mov     edx, ecx; int
0x1400ed728  mov     [rsp+88h+var_68], rax; char *
0x1400ed72d  lea     rcx, aVhdmpiinitiali_35; "VhdmpiInitializeHandleContext"
0x1400ed734  mov     r8d, ebx; int
0x1400ed737  call    TraceEvents
0x1400ed73c  mov     ebx, 0C00000A5h
0x1400ed741  jmp     loc_1400ED9C3
0x1400ed746  mov     rcx, rbp; Token
0x1400ed749  call    cs:__imp_SeTokenType
0x1400ed750  nop     dword ptr [rax+rax+00h]
0x1400ed755  mov     ebx, 2
0x1400ed75a  cmp     eax, ebx
0x1400ed75c  jnz     short loc_1400ED788
0x1400ed75e  cmp     [r14+8], ebx
0x1400ed762  jge     short loc_1400ED788
0x1400ed764  mov     eax, cs:dword_1400876D0
0x1400ed76a  cmp     eax, ebx
0x1400ed76c  jbe     short loc_1400ED73C
0x1400ed76e  mov     rdx, r15
0x1400ed771  lea     rcx, dword_1400876D0
0x1400ed778  call    _tlgKeywordOn
0x1400ed77d  test    al, al
0x1400ed77f  jz      short loc_1400ED73C
0x1400ed781  mov     ecx, 0D08h
0x1400ed786  jmp     short loc_1400ED71C
0x1400ed788  mov     ebp, 4
0x1400ed78d  cmp     [rdi+128h], ebp
0x1400ed793  jnz     short loc_1400ED7B8
0x1400ed795  mov     rcx, r13
0x1400ed798  call    VhdmpiGetDriveTypeFromFileName
0x1400ed79d  cmp     eax, ebp
0x1400ed79f  jnz     short loc_1400ED7AE
0x1400ed7a1  cmp     [rsi+34h], r15d
0x1400ed7a5  jz      short loc_1400ED7AE
0x1400ed7a7  mov     eax, [rsi+28h]
0x1400ed7aa  test    al, 14h
0x1400ed7ac  jz      short loc_1400ED7B8
0x1400ed7ae  mov     ebx, 0C000000Dh
0x1400ed7b3  jmp     loc_1400ED9C3
0x1400ed7b8  mov     eax, [rsi+28h]
0x1400ed7bb  mov     r14d, 10h
0x1400ed7c1  mov     ecx, eax
0x1400ed7c3  and     ecx, r15d
0x1400ed7c6  jz      short loc_1400ED80F
0x1400ed7c8  test    r14b, al
0x1400ed7cb  jz      short loc_1400ED80F
0x1400ed7cd  mov     eax, cs:dword_1400876D0
0x1400ed7d3  cmp     eax, ebx
0x1400ed7d5  jbe     short loc_1400ED7AE
0x1400ed7d7  mov     edx, r14d
0x1400ed7da  lea     rcx, dword_1400876D0
0x1400ed7e1  call    _tlgKeywordOn
0x1400ed7e6  test    al, al
0x1400ed7e8  jz      short loc_1400ED7AE
0x1400ed7ea  lea     rax, aOpenVirtualDis; "OPEN_VIRTUAL_DISK_FLAG_NO_PARENTS and O"...
0x1400ed7f1  mov     edx, 0D1Fh; int
0x1400ed7f6  mov     r9d, r14d; int
0x1400ed7f9  mov     [rsp+88h+var_68], rax; char *
0x1400ed7fe  mov     r8d, ebx; int
0x1400ed801  lea     rcx, aVhdmpiinitiali_35; "VhdmpiInitializeHandleContext"
0x1400ed808  call    TraceEvents
0x1400ed80d  jmp     short loc_1400ED7AE
0x1400ed80f  mov     edx, 800h
0x1400ed814  test    al, 40h
0x1400ed816  jz      short loc_1400ED827
0x1400ed818  cmp     [rdi+128h], ebp
0x1400ed81e  jnz     short loc_1400ED7AE
0x1400ed820  test    ecx, ecx
0x1400ed822  jnz     short loc_1400ED7AE
0x1400ed824  or      [rdi+4], edx
0x1400ed827  mov     eax, [rsi+28h]
0x1400ed82a  test    r15b, al
0x1400ed82d  jz      short loc_1400ED832
0x1400ed82f  or      [rdi+4], ebx
0x1400ed832  mov     eax, [rsi+28h]
0x1400ed835  test    bl, al
0x1400ed837  jz      short loc_1400ED83F
0x1400ed839  or      [rdi+4], ebp
0x1400ed83c  inc     r12d
0x1400ed83f  mov     eax, [rsi+28h]
0x1400ed842  test    bpl, al
0x1400ed845  jz      short loc_1400ED84E
0x1400ed847  or      dword ptr [rdi+4], 8
0x1400ed84b  inc     r12d
0x1400ed84e  mov     eax, [rsi+28h]
0x1400ed851  test    al, 8
0x1400ed853  jz      short loc_1400ED859
0x1400ed855  or      dword ptr [rdi+4], 20h
0x1400ed859  mov     eax, [rsi+28h]
0x1400ed85c  test    al, 20h
0x1400ed85e  jz      short loc_1400ED864
0x1400ed860  or      dword ptr [rdi+4], 60h
0x1400ed864  cmp     dword ptr [rsi+28h], 0
0x1400ed868  mov     ecx, 400h
0x1400ed86d  jge     short loc_1400ED872
0x1400ed86f  or      [rdi+4], ecx
0x1400ed872  mov     eax, [rsi+28h]
0x1400ed875  test    r14b, al
0x1400ed878  jz      short loc_1400ED896
0x1400ed87a  mov     eax, [rdi+4]
0x1400ed87d  test    al, al
0x1400ed87f  jns     loc_1400ED7AE
0x1400ed885  test    r14b, al
0x1400ed888  jnz     loc_1400ED7AE
0x1400ed88e  or      eax, 102h
0x1400ed893  mov     [rdi+4], eax
0x1400ed896  mov     eax, [rsi+28h]
0x1400ed899  test    al, al
0x1400ed89b  jns     short loc_1400ED8A2
0x1400ed89d  bts     dword ptr [rdi+4], 0Dh
0x1400ed8a2  test    dword ptr [rsi+28h], 100h
0x1400ed8a9  jz      short loc_1400ED8B0
0x1400ed8ab  bts     dword ptr [rdi+4], 0Eh
0x1400ed8b0  mov     r15d, 200h
0x1400ed8b6  test    [rsi+28h], r15d
0x1400ed8ba  jz      short loc_1400ED8C1
0x1400ed8bc  bts     dword ptr [rdi+4], 0Fh
0x1400ed8c1  test    [rsi+28h], ecx
0x1400ed8c4  jz      short loc_1400ED8CB
0x1400ed8c6  bts     dword ptr [rdi+4], 10h
0x1400ed8cb  test    [rsi+28h], edx
0x1400ed8ce  jz      short loc_1400ED8D5
0x1400ed8d0  bts     dword ptr [rdi+4], 11h
0x1400ed8d5  mov     r8, r14; Size
0x1400ed8d8  lea     rdx, VhdmpZeroGuid; Buf2
0x1400ed8df  lea     rcx, [rsi+40h]; Buf1
0x1400ed8e3  call    memcmp
0x1400ed8e8  test    eax, eax
0x1400ed8ea  jz      short loc_1400ED932
0x1400ed8ec  cmp     [rdi+128h], ebp
0x1400ed8f2  jnz     loc_1400ED7AE
0x1400ed8f8  movzx   ecx, byte ptr [rsi+50h]
0x1400ed8fc  sub     ecx, 1
0x1400ed8ff  jz      short loc_1400ED90B
0x1400ed901  cmp     ecx, 3
0x1400ed904  jz      short loc_1400ED916
0x1400ed906  jmp     loc_1400ED7AE
0x1400ed90b  mov     eax, [rdi+4]
0x1400ed90e  test    al, al
0x1400ed910  jns     loc_1400ED7AE
0x1400ed916  bts     dword ptr [rdi+4], 0Ch
0x1400ed91b  movups  xmm0, xmmword ptr [rsi+40h]
0x1400ed91f  movdqu  xmmword ptr [rdi+138h], xmm0
0x1400ed927  movzx   eax, byte ptr [rsi+50h]
0x1400ed92b  mov     [rdi+148h], ax
0x1400ed932  cmp     r12d, 1
0x1400ed936  ja      loc_1400ED7AE
0x1400ed93c  mov     eax, [rdi+4]
0x1400ed93f  movzx   ecx, [rsp+88h+arg_18]
0x1400ed947  shl     ecx, 9
0x1400ed94a  xor     ecx, eax
0x1400ed94c  and     ecx, r15d
0x1400ed94f  xor     ecx, eax
0x1400ed951  mov     rax, [rsp+88h+arg_28]
0x1400ed959  mov     [rdi+4], ecx
0x1400ed95c  test    rax, rax
0x1400ed95f  jz      short loc_1400ED971
0x1400ed961  test    r14b, cl
0x1400ed964  jnz     short loc_1400ED971
0x1400ed966  movups  xmm0, xmmword ptr [rax]
0x1400ed969  movdqu  xmmword ptr [rdi+0F8h], xmm0
0x1400ed971  lea     rcx, [rdi+108h]; RunRef
0x1400ed978  call    cs:__imp_ExInitializeRundownProtection
0x1400ed97f  nop     dword ptr [rax+rax+00h]
0x1400ed984  lea     rbx, [rdi+110h]
0x1400ed98b  mov     rcx, rbx; RunRef
0x1400ed98e  call    cs:__imp_ExInitializeRundownProtection
0x1400ed995  nop     dword ptr [rax+rax+00h]
0x1400ed99a  mov     rcx, rbx; RunRef
0x1400ed99d  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400ed9a4  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
