# VhdmpiInitializeHandleContext(_VHD_HANDLE_CONTEXT *,_UNICODE_STRING *,_VIRTUAL_DISK_EA_BUFFER *,uchar,uchar,void *,_SECURITY_SUBJECT_CONTEXT *)

- ea: `0x1400ed5a0`
- end: `0x1400eda47`
- name: `?VhdmpiInitializeHandleContext@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_UNICODE_STRING@@PEAU_VIRTUAL_DISK_EA_BUFFER@@EEPEAXPEAU_SECURITY_SUBJECT_CONTEXT@@@Z`
- size: `1191`
- prototype: `__int64 __fastcall(struct _VHD_HANDLE_CONTEXT *, struct _UNICODE_STRING *, struct _VIRTUAL_DISK_EA_BUFFER *, unsigned __int8, char, _OWORD *, struct _SECURITY_SUBJECT_CONTEXT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400e9df4`

## callees

- `0x14001dcc4`
- `0x1400203e0`
- `0x140023560`
- `0x140026a00`
- `0x140035e94`
- `0x14005d8e0`
- `0x14005dd00`
- `0x14009df3c`
- `0x1400e6e6c`
- `0x1400e8fd8`
- `0x1400ed5a0`

## import_xrefs

- `ntoskrnl!SeTokenType` at `0x1400ed748`
- `ntoskrnl!SeTokenType` at `0x1400ed7b9`
- `ntoskrnl!SeTokenType` at `0x1400ed748`
- `ntoskrnl!SeTokenType` at `0x1400ed7b9`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400ed9e8`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400ed9fe`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400ed9e8`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400ed9fe`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400eda0d`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400eda0d`
- `ntoskrnl!KeInitializeMutex` at `0x1400ed5fa`
- `ntoskrnl!KeInitializeMutex` at `0x1400ed5fa`
- `ntoskrnl!KeInitializeEvent` at `0x1400ed617`
- `ntoskrnl!KeInitializeEvent` at `0x1400ed630`
- `ntoskrnl!KeInitializeEvent` at `0x1400ed617`
- `ntoskrnl!KeInitializeEvent` at `0x1400ed630`

## string_xrefs

- `0x1400ed78f`: `Incorrect impersonation level provided.`
- `0x1400ed85a`: `OPEN_VIRTUAL_DISK_FLAG_NO_PARENTS and OPEN_VIRTUAL_DISK_FLAG_CUSTOM_DIFF_CHAIN are mutually exclusive`
- `0x1400ed6e5`: `Failed to impersonate.`

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
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 1) )
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
      if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 1) )
        return (unsigned int)-1073741659;
      v20 = 3323;
LABEL_27:
      TraceEvents((int)"VhdmpiInitializeHandleContext", v20, 2, v19, "Incorrect impersonation level provided.", v25);
      return (unsigned int)-1073741659;
    }
  }
  else if ( SeTokenType(ClientToken) == TokenImpersonation && a7->ImpersonationLevel < SecurityImpersonation )
  {
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 1) )
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
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
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
0x1400ed5a0  mov     [rsp+arg_18], r9b
0x1400ed5a5  push    rbx
0x1400ed5a6  push    rbp
0x1400ed5a7  push    rsi
0x1400ed5a8  push    rdi
0x1400ed5a9  push    r12
0x1400ed5ab  push    r13
0x1400ed5ad  push    r14
0x1400ed5af  push    r15
0x1400ed5b1  sub     rsp, 48h
0x1400ed5b5  mov     rsi, r8
0x1400ed5b8  mov     r13, rdx
0x1400ed5bb  mov     rdi, rcx
0x1400ed5be  xor     edx, edx; Val
0x1400ed5c0  add     rcx, 4; void *
0x1400ed5c4  mov     r8d, 1BCh; Size
0x1400ed5ca  call    memset
0x1400ed5cf  xorps   xmm0, xmm0
0x1400ed5d2  mov     dword ptr [rdi], 58544356h
0x1400ed5d8  lea     rcx, [rsi+10h]
0x1400ed5dc  xor     edx, edx
0x1400ed5de  movups  [rsp+88h+var_58], xmm0
0x1400ed5e3  xor     r12d, r12d
0x1400ed5e6  call    VhdmpiGetDriveType
0x1400ed5eb  lea     rcx, [rdi+80h]; Mutex
0x1400ed5f2  mov     [rdi+128h], eax
0x1400ed5f8  xor     edx, edx; Level
0x1400ed5fa  call    cs:__imp_KeInitializeMutex
0x1400ed601  nop     dword ptr [rax+rax+00h]
0x1400ed606  lea     r15d, [r12+1]
0x1400ed60b  xor     edx, edx; Type
0x1400ed60d  mov     r8b, r15b; State
0x1400ed610  lea     rcx, [rdi+0C0h]; Event
0x1400ed617  call    cs:__imp_KeInitializeEvent
0x1400ed61e  nop     dword ptr [rax+rax+00h]
0x1400ed623  lea     rcx, [rdi+0E0h]; Event
0x1400ed62a  mov     r8b, r15b; State
0x1400ed62d  mov     edx, r15d; Type
0x1400ed630  call    cs:__imp_KeInitializeEvent
0x1400ed637  nop     dword ptr [rax+rax+00h]
0x1400ed63c  lea     rcx, [rdi+68h]
0x1400ed640  call    VhdmpiInitializePassiveLock
0x1400ed645  mov     eax, [rsi+34h]
0x1400ed648  lea     edx, [r15+7Fh]
0x1400ed64c  cmp     eax, r15d
0x1400ed64f  jnz     short loc_1400ED677
0x1400ed651  or      [rdi+4], r15d
0x1400ed655  mov     eax, [rsi+2Ch]
0x1400ed658  mov     [rdi+8], eax
0x1400ed65b  test    eax, 30000h
0x1400ed660  jz      short loc_1400ED669
0x1400ed662  bts     eax, 12h
0x1400ed666  mov     [rdi+8], eax
0x1400ed669  test    eax, 320000h
0x1400ed66e  jnz     short loc_1400ED692
0x1400ed670  or      [rdi+4], edx
0x1400ed673  xor     eax, eax
0x1400ed675  jmp     short loc_1400ED695
0x1400ed677  cmp     eax, 2
0x1400ed67a  jnz     short loc_1400ED698
0x1400ed67c  cmp     [rsi+38h], r12d
0x1400ed680  jz      short loc_1400ED689
0x1400ed682  or      dword ptr [rdi+4], 10h
0x1400ed686  mov     r12d, r15d
0x1400ed689  cmp     [rsi+3Ch], r15d
0x1400ed68d  jnz     short loc_1400ED692
0x1400ed68f  or      [rdi+4], edx
0x1400ed692  mov     eax, [rsi+30h]
0x1400ed695  mov     [rdi+0Ch], eax
0x1400ed698  mov     r14, [rsp+88h+arg_30]
0x1400ed6a0  mov     rbp, [r14]
0x1400ed6a3  test    rbp, rbp
0x1400ed6a6  jnz     short loc_1400ED6AC
0x1400ed6a8  mov     rbp, [r14+10h]
0x1400ed6ac  lea     rdx, [rsp+88h+var_58]
0x1400ed6b1  mov     rcx, rbp; Token
0x1400ed6b4  call    VhdmpiBeginImpersonation
0x1400ed6b9  mov     ebx, eax
0x1400ed6bb  test    eax, eax
0x1400ed6bd  jns     short loc_1400ED710
0x1400ed6bf  mov     ecx, cs:dword_140087708
0x1400ed6c5  cmp     ecx, 2
0x1400ed6c8  jbe     loc_1400EDA33
0x1400ed6ce  mov     rdx, r15
0x1400ed6d1  lea     rcx, dword_140087708
0x1400ed6d8  call    _tlgKeywordOn
0x1400ed6dd  test    al, al
0x1400ed6df  jz      loc_1400EDA33
0x1400ed6e5  lea     rax, aFailedToImpers_0; "Failed to impersonate."
0x1400ed6ec  mov     edx, 0CE2h; int
0x1400ed6f1  mov     r9d, r15d; int
0x1400ed6f4  mov     [rsp+88h+var_68], rax; char *
0x1400ed6f9  mov     r8d, 2; int
0x1400ed6ff  lea     rcx, aVhdmpiinitiali_35; "VhdmpiInitializeHandleContext"
0x1400ed706  call    TraceEvents
0x1400ed70b  jmp     loc_1400EDA33
0x1400ed710  mov     r8d, [rdi+4]
0x1400ed714  lea     rcx, [rdi+10h]
0x1400ed718  mov     bl, [rsp+88h+arg_20]
0x1400ed71f  shr     r8d, 7
0x1400ed723  mov     dl, bl
0x1400ed725  and     r8b, r15b
0x1400ed728  call    VhdmpiInitializeSecurityContextFromScope
0x1400ed72d  lea     rcx, [rsp+88h+var_58]
0x1400ed732  call    VhdmpiEndImpersonation
0x1400ed737  test    bl, bl
0x1400ed739  jz      short loc_1400ED7B6
0x1400ed73b  mov     rcx, [rdi+10h]
0x1400ed73f  test    rcx, rcx
0x1400ed742  jnz     short loc_1400ED748
0x1400ed744  mov     rcx, [rdi+20h]; Token
0x1400ed748  call    cs:__imp_SeTokenType
0x1400ed74f  nop     dword ptr [rax+rax+00h]
0x1400ed754  mov     ebx, 2
0x1400ed759  cmp     eax, ebx
0x1400ed75b  jnz     loc_1400ED7F8
0x1400ed761  cmp     [rdi+18h], ebx
0x1400ed764  jge     loc_1400ED7F8
0x1400ed76a  mov     eax, cs:dword_140087708
0x1400ed770  cmp     eax, ebx
0x1400ed772  jbe     short loc_1400ED7AC
0x1400ed774  mov     rdx, r15
0x1400ed777  lea     rcx, dword_140087708
0x1400ed77e  call    _tlgKeywordOn
0x1400ed783  test    al, al
0x1400ed785  jz      short loc_1400ED7AC
0x1400ed787  mov     ecx, 0CFBh
0x1400ed78c  mov     r9d, edx; int
0x1400ed78f  lea     rax, aIncorrectImper; "Incorrect impersonation level provided."
0x1400ed796  mov     edx, ecx; int
0x1400ed798  mov     [rsp+88h+var_68], rax; char *
0x1400ed79d  lea     rcx, aVhdmpiinitiali_35; "VhdmpiInitializeHandleContext"
0x1400ed7a4  mov     r8d, ebx; int
0x1400ed7a7  call    TraceEvents
0x1400ed7ac  mov     ebx, 0C00000A5h
0x1400ed7b1  jmp     loc_1400EDA33
0x1400ed7b6  mov     rcx, rbp; Token
0x1400ed7b9  call    cs:__imp_SeTokenType
0x1400ed7c0  nop     dword ptr [rax+rax+00h]
0x1400ed7c5  mov     ebx, 2
0x1400ed7ca  cmp     eax, ebx
0x1400ed7cc  jnz     short loc_1400ED7F8
0x1400ed7ce  cmp     [r14+8], ebx
0x1400ed7d2  jge     short loc_1400ED7F8
0x1400ed7d4  mov     eax, cs:dword_140087708
0x1400ed7da  cmp     eax, ebx
0x1400ed7dc  jbe     short loc_1400ED7AC
0x1400ed7de  mov     rdx, r15
0x1400ed7e1  lea     rcx, dword_140087708
0x1400ed7e8  call    _tlgKeywordOn
0x1400ed7ed  test    al, al
0x1400ed7ef  jz      short loc_1400ED7AC
0x1400ed7f1  mov     ecx, 0D08h
0x1400ed7f6  jmp     short loc_1400ED78C
0x1400ed7f8  mov     ebp, 4
0x1400ed7fd  cmp     [rdi+128h], ebp
0x1400ed803  jnz     short loc_1400ED828
0x1400ed805  mov     rcx, r13
0x1400ed808  call    VhdmpiGetDriveTypeFromFileName
0x1400ed80d  cmp     eax, ebp
0x1400ed80f  jnz     short loc_1400ED81E
0x1400ed811  cmp     [rsi+34h], r15d
0x1400ed815  jz      short loc_1400ED81E
0x1400ed817  mov     eax, [rsi+28h]
0x1400ed81a  test    al, 14h
0x1400ed81c  jz      short loc_1400ED828
0x1400ed81e  mov     ebx, 0C000000Dh
0x1400ed823  jmp     loc_1400EDA33
0x1400ed828  mov     eax, [rsi+28h]
0x1400ed82b  mov     r14d, 10h
0x1400ed831  mov     ecx, eax
0x1400ed833  and     ecx, r15d
0x1400ed836  jz      short loc_1400ED87F
0x1400ed838  test    r14b, al
0x1400ed83b  jz      short loc_1400ED87F
0x1400ed83d  mov     eax, cs:dword_140087708
0x1400ed843  cmp     eax, ebx
0x1400ed845  jbe     short loc_1400ED81E
0x1400ed847  mov     edx, r14d
0x1400ed84a  lea     rcx, dword_140087708
0x1400ed851  call    _tlgKeywordOn
0x1400ed856  test    al, al
0x1400ed858  jz      short loc_1400ED81E
0x1400ed85a  lea     rax, aOpenVirtualDis; "OPEN_VIRTUAL_DISK_FLAG_NO_PARENTS and O"...
0x1400ed861  mov     edx, 0D1Fh; int
0x1400ed866  mov     r9d, r14d; int
0x1400ed869  mov     [rsp+88h+var_68], rax; char *
0x1400ed86e  mov     r8d, ebx; int
0x1400ed871  lea     rcx, aVhdmpiinitiali_35; "VhdmpiInitializeHandleContext"
0x1400ed878  call    TraceEvents
0x1400ed87d  jmp     short loc_1400ED81E
0x1400ed87f  mov     edx, 800h
0x1400ed884  test    al, 40h
0x1400ed886  jz      short loc_1400ED897
0x1400ed888  cmp     [rdi+128h], ebp
0x1400ed88e  jnz     short loc_1400ED81E
0x1400ed890  test    ecx, ecx
0x1400ed892  jnz     short loc_1400ED81E
0x1400ed894  or      [rdi+4], edx
0x1400ed897  mov     eax, [rsi+28h]
0x1400ed89a  test    r15b, al
0x1400ed89d  jz      short loc_1400ED8A2
0x1400ed89f  or      [rdi+4], ebx
0x1400ed8a2  mov     eax, [rsi+28h]
0x1400ed8a5  test    bl, al
0x1400ed8a7  jz      short loc_1400ED8AF
0x1400ed8a9  or      [rdi+4], ebp
0x1400ed8ac  inc     r12d
0x1400ed8af  mov     eax, [rsi+28h]
0x1400ed8b2  test    bpl, al
0x1400ed8b5  jz      short loc_1400ED8BE
0x1400ed8b7  or      dword ptr [rdi+4], 8
0x1400ed8bb  inc     r12d
0x1400ed8be  mov     eax, [rsi+28h]
0x1400ed8c1  test    al, 8
0x1400ed8c3  jz      short loc_1400ED8C9
0x1400ed8c5  or      dword ptr [rdi+4], 20h
0x1400ed8c9  mov     eax, [rsi+28h]
0x1400ed8cc  test    al, 20h
0x1400ed8ce  jz      short loc_1400ED8D4
0x1400ed8d0  or      dword ptr [rdi+4], 60h
0x1400ed8d4  cmp     dword ptr [rsi+28h], 0
0x1400ed8d8  mov     ecx, 400h
0x1400ed8dd  jge     short loc_1400ED8E2
0x1400ed8df  or      [rdi+4], ecx
0x1400ed8e2  mov     eax, [rsi+28h]
0x1400ed8e5  test    r14b, al
0x1400ed8e8  jz      short loc_1400ED906
0x1400ed8ea  mov     eax, [rdi+4]
0x1400ed8ed  test    al, al
0x1400ed8ef  jns     loc_1400ED81E
0x1400ed8f5  test    r14b, al
0x1400ed8f8  jnz     loc_1400ED81E
0x1400ed8fe  or      eax, 102h
0x1400ed903  mov     [rdi+4], eax
0x1400ed906  mov     eax, [rsi+28h]
0x1400ed909  test    al, al
0x1400ed90b  jns     short loc_1400ED912
0x1400ed90d  bts     dword ptr [rdi+4], 0Dh
0x1400ed912  test    dword ptr [rsi+28h], 100h
0x1400ed919  jz      short loc_1400ED920
0x1400ed91b  bts     dword ptr [rdi+4], 0Eh
0x1400ed920  mov     r15d, 200h
0x1400ed926  test    [rsi+28h], r15d
0x1400ed92a  jz      short loc_1400ED931
0x1400ed92c  bts     dword ptr [rdi+4], 0Fh
0x1400ed931  test    [rsi+28h], ecx
0x1400ed934  jz      short loc_1400ED93B
0x1400ed936  bts     dword ptr [rdi+4], 10h
0x1400ed93b  test    [rsi+28h], edx
0x1400ed93e  jz      short loc_1400ED945
0x1400ed940  bts     dword ptr [rdi+4], 11h
0x1400ed945  mov     r8, r14; Size
0x1400ed948  lea     rdx, VhdmpZeroGuid; Buf2
0x1400ed94f  lea     rcx, [rsi+40h]; Buf1
0x1400ed953  call    memcmp
0x1400ed958  test    eax, eax
0x1400ed95a  jz      short loc_1400ED9A2
0x1400ed95c  cmp     [rdi+128h], ebp
0x1400ed962  jnz     loc_1400ED81E
0x1400ed968  movzx   ecx, byte ptr [rsi+50h]
0x1400ed96c  sub     ecx, 1
0x1400ed96f  jz      short loc_1400ED97B
0x1400ed971  cmp     ecx, 3
0x1400ed974  jz      short loc_1400ED986
0x1400ed976  jmp     loc_1400ED81E
0x1400ed97b  mov     eax, [rdi+4]
0x1400ed97e  test    al, al
0x1400ed980  jns     loc_1400ED81E
0x1400ed986  bts     dword ptr [rdi+4], 0Ch
0x1400ed98b  movups  xmm0, xmmword ptr [rsi+40h]
0x1400ed98f  movdqu  xmmword ptr [rdi+138h], xmm0
0x1400ed997  movzx   eax, byte ptr [rsi+50h]
0x1400ed99b  mov     [rdi+148h], ax
0x1400ed9a2  cmp     r12d, 1
0x1400ed9a6  ja      loc_1400ED81E
0x1400ed9ac  mov     eax, [rdi+4]
0x1400ed9af  movzx   ecx, [rsp+88h+arg_18]
0x1400ed9b7  shl     ecx, 9
0x1400ed9ba  xor     ecx, eax
0x1400ed9bc  and     ecx, r15d
0x1400ed9bf  xor     ecx, eax
0x1400ed9c1  mov     rax, [rsp+88h+arg_28]
0x1400ed9c9  mov     [rdi+4], ecx
0x1400ed9cc  test    rax, rax
0x1400ed9cf  jz      short loc_1400ED9E1
0x1400ed9d1  test    r14b, cl
0x1400ed9d4  jnz     short loc_1400ED9E1
0x1400ed9d6  movups  xmm0, xmmword ptr [rax]
0x1400ed9d9  movdqu  xmmword ptr [rdi+0F8h], xmm0
0x1400ed9e1  lea     rcx, [rdi+108h]; RunRef
0x1400ed9e8  call    cs:__imp_ExInitializeRundownProtection
0x1400ed9ef  nop     dword ptr [rax+rax+00h]
0x1400ed9f4  lea     rbx, [rdi+110h]
0x1400ed9fb  mov     rcx, rbx; RunRef
0x1400ed9fe  call    cs:__imp_ExInitializeRundownProtection
0x1400eda05  nop     dword ptr [rax+rax+00h]
0x1400eda0a  mov     rcx, rbx; RunRef
0x1400eda0d  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400eda14  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
