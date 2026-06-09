# CWbemNamespace::GetParentInheritableAces(CNtSecurityDescriptor &,bool,bool)

- ea: `0x1800be2d0`
- end: `0x1800be700`
- name: `?GetParentInheritableAces@CWbemNamespace@@QEAAJAEAVCNtSecurityDescriptor@@_N1@Z`
- size: `1072`
- prototype: `__int64 __fastcall(CWbemNamespace *__hidden this, struct CNtSecurityDescriptor *, bool, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007ebf4`

## callees

- `0x18000b140`
- `0x18001d390`
- `0x1800231e8`
- `0x180025890`
- `0x18002ab80`
- `0x18002ca8c`
- `0x18002dd24`
- `0x180036db0`
- `0x18003cfe0`
- `0x1800bdac0`
- `0x1800bde98`
- `0x1800be2d0`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800be381`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800be381`
- `wbemcomn!GetMemLogObject` at `0x1800be304`
- `wbemcomn!GetMemLogObject` at `0x1800be38f`
- `wbemcomn!GetMemLogObject` at `0x1800be406`
- `wbemcomn!GetMemLogObject` at `0x1800be47b`
- `wbemcomn!GetMemLogObject` at `0x1800be4e2`
- `wbemcomn!GetMemLogObject` at `0x1800be58b`
- `wbemcomn!GetMemLogObject` at `0x1800be5d8`
- `wbemcomn!GetMemLogObject` at `0x1800be636`
- `wbemcomn!GetMemLogObject` at `0x1800be681`
- `wbemcomn!GetMemLogObject` at `0x1800be304`
- `wbemcomn!GetMemLogObject` at `0x1800be38f`
- `wbemcomn!GetMemLogObject` at `0x1800be406`
- `wbemcomn!GetMemLogObject` at `0x1800be47b`
- `wbemcomn!GetMemLogObject` at `0x1800be4e2`
- `wbemcomn!GetMemLogObject` at `0x1800be58b`
- `wbemcomn!GetMemLogObject` at `0x1800be5d8`
- `wbemcomn!GetMemLogObject` at `0x1800be636`
- `wbemcomn!GetMemLogObject` at `0x1800be681`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be314`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be39f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be412`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be48b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be4ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be596`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be5e3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be641`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be68c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be314`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be39f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be412`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be48b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be4ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be596`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be5e3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be641`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800be68c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemNamespace::GetParentInheritableAces(
        CWbemNamespace *this,
        struct CNtSecurityDescriptor *a2,
        char a3,
        char a4)
{
  __int64 v5; // rax
  CMemoryLog *MemLogObject; // rax
  int v7; // ebx
  CClientCnt *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v12; // rbx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // r12
  CMemoryLog *v15; // rax
  int v16; // r15d
  CMemoryLog *v17; // rax
  unsigned __int16 *i; // rcx
  IUnknown *Instance; // rax
  IUnknown *v20; // r15
  CMemoryLog *v21; // rax
  CClientCnt *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  CClientCnt *v27; // rcx
  __int64 v28; // rdx
  CMemoryLog *v29; // rax
  struct CNtSecurityDescriptor *v30; // r12
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  void *v33; // [rsp+68h] [rbp-9h] BYREF
  void *v34[11]; // [rsp+70h] [rbp-1h] BYREF
  void *v35; // [rsp+D8h] [rbp+67h] BYREF
  struct CNtSecurityDescriptor *v36; // [rsp+E0h] [rbp+6Fh]
  char v37; // [rsp+E8h] [rbp+77h]
  char v38; // [rsp+F0h] [rbp+7Fh]

  v38 = a4;
  v37 = a3;
  v36 = a2;
  v5 = *((_QWORD *)this + 12);
  if ( !v5 )
  {
    MemLogObject = GetMemLogObject();
    v7 = -2147217398;
    CMemoryLog::Write(MemLogObject, -2147217398);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v7;
    }
    v9 = 120;
    v10 = 2147749898LL;
LABEL_6:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, v10);
    return (unsigned int)v7;
  }
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(v5 + 2 * v12) );
  v13 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((int)v12 + 1, 2u));
  v14 = v13;
  if ( !v13 )
  {
    v15 = GetMemLogObject();
    v7 = -2147217402;
    CMemoryLog::Write(v15, -2147217402);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v7;
    }
    v9 = 121;
    v10 = 2147749894LL;
    goto LABEL_6;
  }
  v34[0] = v13;
  v34[1] = 0;
  v16 = StringCchCopyW(v13, (int)v12 + 1, *((const unsigned __int16 **)this + 12));
  if ( v16 < 0 )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, v16);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        122,
        WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
        (unsigned int)v16);
    }
  }
  for ( i = &v14[(int)v12 - 1]; ; --i )
  {
    if ( i < v14 )
      goto LABEL_62;
    if ( *i == 92 || *i == 47 )
      break;
  }
  *i = 0;
  Instance = (IUnknown *)CWbemNamespace::CreateInstance();
  v20 = Instance;
  if ( !Instance )
  {
    v21 = GetMemLogObject();
    v7 = -2147217402;
    CMemoryLog::Write(v21, -2147217402);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_60;
    }
    v23 = 123;
    v24 = 2147749894LL;
    goto LABEL_35;
  }
  v33 = 0;
  v7 = CWbemNamespace::QueryInterface(Instance, &IID_IUnknown, &v33);
  if ( v7 < 0 )
  {
    v25 = GetMemLogObject();
    CMemoryLog::Write(v25, v7);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_60;
    }
    v23 = 124;
    v24 = (unsigned int)v7;
LABEL_35:
    WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, v24);
LABEL_60:
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v34);
    return (unsigned int)v7;
  }
  CWbemNamespace::Release((CWbemNamespace *)v20);
  v35 = v33;
  v7 = CWbemNamespace::Initialize(
         (CWbemNamespace *)v20,
         v14,
         0,
         *((_DWORD *)this + 27),
         *((_DWORD *)this + 26),
         *((_DWORD *)this + 32),
         0,
         0,
         0xFFFFFFFF,
         0,
         0,
         0);
  if ( v7 < 0 )
  {
    v26 = GetMemLogObject();
    CMemoryLog::Write(v26, v7);
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_59;
    }
    v28 = 125;
LABEL_58:
    WPP_SF_d(*((_QWORD *)v27 + 2), v28, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, (unsigned int)v7);
LABEL_59:
    CReleaseMe::release((CReleaseMe *)&v35);
    goto LABEL_60;
  }
  v7 = CWbemNamespace::EnsureSecurity((CWbemNamespace *)v20);
  if ( v7 < 0 )
  {
    v29 = GetMemLogObject();
    CMemoryLog::Write(v29, v7);
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_59;
    }
    v28 = 126;
    goto LABEL_58;
  }
  v30 = v36;
  if ( v37 )
  {
    v7 = CopyInheritedDACLAces(v36, (struct CNtSecurityDescriptor *)&v20[27]);
    if ( v7 < 0 )
    {
      v31 = GetMemLogObject();
      CMemoryLog::Write(v31, v7);
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_59;
      }
      v28 = 127;
      goto LABEL_58;
    }
  }
  if ( v38 )
  {
    v7 = (unsigned int)CopyInheritedSACLAces(v30, (struct CNtSecurityDescriptor *)&v20[27]);
    if ( v7 < 0 )
    {
      v32 = GetMemLogObject();
      CMemoryLog::Write(v32, v7);
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_59;
      }
      v28 = 128;
      goto LABEL_58;
    }
  }
  CReleaseMe::release((CReleaseMe *)&v35);
LABEL_62:
  CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v34);
  return 0;
}

```

## disassembly

```asm
0x1800be2d0  mov     rax, rsp
0x1800be2d3  mov     [rax+20h], r9b
0x1800be2d7  mov     [rax+18h], r8b
0x1800be2db  mov     [rax+10h], rdx
0x1800be2df  push    rbp
0x1800be2e0  push    rbx
0x1800be2e1  push    rsi
0x1800be2e2  push    rdi
0x1800be2e3  push    r12
0x1800be2e5  push    r13
0x1800be2e7  push    r14
0x1800be2e9  push    r15
0x1800be2eb  lea     rbp, [rax-5Fh]
0x1800be2ef  sub     rsp, 88h
0x1800be2f6  mov     r13, rcx
0x1800be2f9  mov     rax, [rcx+60h]
0x1800be2fd  xor     esi, esi
0x1800be2ff  test    rax, rax
0x1800be302  jnz     short loc_1800BE35C
0x1800be304  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800be30a  mov     ebx, 8004100Ah
0x1800be30f  mov     edx, ebx
0x1800be311  mov     rcx, rax
0x1800be314  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800be31a  lea     r14, WPP_GLOBAL_Control
0x1800be321  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be328  cmp     rcx, r14
0x1800be32b  jz      short loc_1800BE355
0x1800be32d  mov     dil, 1
0x1800be330  test    [rcx+1Ch], dil
0x1800be334  jz      short loc_1800BE355
0x1800be336  cmp     byte ptr [rcx+19h], 2
0x1800be33a  jb      short loc_1800BE355
0x1800be33c  lea     edx, [rsi+78h]
0x1800be33f  mov     r9d, 8004100Ah
0x1800be345  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800be34c  mov     rcx, [rcx+10h]
0x1800be350  call    WPP_SF_d
0x1800be355  mov     eax, ebx
0x1800be357  jmp     loc_1800BE6EC
0x1800be35c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800be360  mov     rbx, rcx
0x1800be363  inc     rbx
0x1800be366  cmp     [rax+rbx*2], si
0x1800be36a  jnz     short loc_1800BE363
0x1800be36c  lea     eax, [rbx+1]
0x1800be36f  movsxd  rdi, eax
0x1800be372  mov     eax, 2
0x1800be377  mul     rdi
0x1800be37a  cmovb   rax, rcx
0x1800be37e  mov     rcx, rax
0x1800be381  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800be387  mov     r12, rax
0x1800be38a  test    rax, rax
0x1800be38d  jnz     short loc_1800BE3D7
0x1800be38f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800be395  mov     ebx, 80041006h
0x1800be39a  mov     edx, ebx
0x1800be39c  mov     rcx, rax
0x1800be39f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800be3a5  lea     r14, WPP_GLOBAL_Control
0x1800be3ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be3b3  cmp     rcx, r14
0x1800be3b6  jz      short loc_1800BE355
0x1800be3b8  mov     dil, 1
0x1800be3bb  test    [rcx+1Ch], dil
0x1800be3bf  jz      short loc_1800BE355
0x1800be3c1  cmp     byte ptr [rcx+19h], 2
0x1800be3c5  jb      short loc_1800BE355
0x1800be3c7  lea     edx, [r12+79h]
0x1800be3cc  mov     r9d, 80041006h
0x1800be3d2  jmp     loc_1800BE345
0x1800be3d7  mov     [rbp+57h+var_58], r12
0x1800be3db  mov     [rbp+57h+var_50], rsi
0x1800be3df  mov     r8, [r13+60h]; unsigned __int16 *
0x1800be3e3  mov     rdx, rdi; unsigned __int64
0x1800be3e6  mov     rcx, r12; unsigned __int16 *
0x1800be3e9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800be3ee  mov     r15d, eax
0x1800be3f1  lea     rsi, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800be3f8  mov     dil, 1
0x1800be3fb  lea     r14, WPP_GLOBAL_Control
0x1800be402  test    eax, eax
0x1800be404  jns     short loc_1800BE444
0x1800be406  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800be40c  mov     edx, r15d
0x1800be40f  mov     rcx, rax
0x1800be412  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800be418  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be41f  cmp     rcx, r14
0x1800be422  jz      short loc_1800BE444
0x1800be424  test    [rcx+1Ch], dil
0x1800be428  jz      short loc_1800BE444
0x1800be42a  cmp     byte ptr [rcx+19h], 2
0x1800be42e  jb      short loc_1800BE444
0x1800be430  mov     edx, 7Ah ; 'z'
0x1800be435  mov     r9d, r15d
0x1800be438  mov     r8, rsi
0x1800be43b  mov     rcx, [rcx+10h]
0x1800be43f  call    WPP_SF_d
0x1800be444  movsxd  rcx, ebx
0x1800be447  dec     rcx
0x1800be44a  lea     rcx, [r12+rcx*2]
0x1800be44e  cmp     rcx, r12
0x1800be451  jb      loc_1800BE6E1
0x1800be457  cmp     word ptr [rcx], 5Ch ; '\'
0x1800be45b  jz      short loc_1800BE469
0x1800be45d  cmp     word ptr [rcx], 2Fh ; '/'
0x1800be461  jz      short loc_1800BE469
0x1800be463  sub     rcx, 2
0x1800be467  jmp     short loc_1800BE44E
0x1800be469  xor     eax, eax
0x1800be46b  mov     [rcx], ax
0x1800be46e  call    ?CreateInstance@CWbemNamespace@@SAPEAV1@XZ; CWbemNamespace::CreateInstance(void)
0x1800be473  mov     r15, rax
0x1800be476  test    rax, rax
0x1800be479  jnz     short loc_1800BE4C1
0x1800be47b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800be481  mov     ebx, 80041006h
0x1800be486  mov     edx, ebx
0x1800be488  mov     rcx, rax
0x1800be48b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800be491  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be498  cmp     rcx, r14
0x1800be49b  jz      loc_1800BE6C9
0x1800be4a1  test    [rcx+1Ch], dil
0x1800be4a5  jz      loc_1800BE6C9
0x1800be4ab  cmp     byte ptr [rcx+19h], 2
0x1800be4af  jb      loc_1800BE6C9
0x1800be4b5  lea     edx, [r15+7Bh]
0x1800be4b9  mov     r9d, 80041006h
0x1800be4bf  jmp     short loc_1800BE51F
0x1800be4c1  mov     [rbp+57h+var_60], 0
0x1800be4c9  lea     r8, [rbp+57h+var_60]; void **
0x1800be4cd  lea     rdx, IID_IUnknown; struct _GUID *
0x1800be4d4  mov     rcx, r15; pUnkOuter
0x1800be4d7  call    ?QueryInterface@CWbemNamespace@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWbemNamespace::QueryInterface(_GUID const &,void * *)
0x1800be4dc  mov     ebx, eax
0x1800be4de  test    eax, eax
0x1800be4e0  jns     short loc_1800BE530
0x1800be4e2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800be4e8  mov     edx, ebx
0x1800be4ea  mov     rcx, rax
0x1800be4ed  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800be4f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be4fa  cmp     rcx, r14
0x1800be4fd  jz      loc_1800BE6C9
0x1800be503  test    [rcx+1Ch], dil
0x1800be507  jz      loc_1800BE6C9
0x1800be50d  cmp     byte ptr [rcx+19h], 2
0x1800be511  jb      loc_1800BE6C9
0x1800be517  mov     edx, 7Ch ; '|'
0x1800be51c  mov     r9d, ebx
0x1800be51f  mov     r8, rsi
0x1800be522  mov     rcx, [rcx+10h]
0x1800be526  call    WPP_SF_d
0x1800be52b  jmp     loc_1800BE6C9
0x1800be530  mov     rcx, r15; this
0x1800be533  call    ?Release@CWbemNamespace@@UEAAKXZ; CWbemNamespace::Release(void)
0x1800be538  mov     rax, [rbp+57h+var_60]
0x1800be53c  mov     [rbp+57h+arg_0], rax
0x1800be540  xor     eax, eax
0x1800be542  mov     [rsp+58h], eax; unsigned int
0x1800be546  mov     [rsp+0C0h+var_70], rax; struct IWmiDbSession *
0x1800be54b  mov     [rsp+0C0h+var_78], eax; int
0x1800be54f  mov     [rsp+0C0h+var_80], 0FFFFFFFFh; unsigned int
0x1800be557  mov     [rsp+0C0h+var_88], rax; unsigned __int16 *
0x1800be55c  mov     [rsp+0C0h+var_90], eax; int
0x1800be560  mov     eax, [r13+80h]
0x1800be567  mov     [rsp+0C0h+var_98], eax; int
0x1800be56b  mov     eax, [r13+68h]
0x1800be56f  mov     [rsp+0C0h+var_A0], eax; unsigned int
0x1800be573  mov     r9d, [r13+6Ch]; unsigned int
0x1800be577  xor     r8d, r8d; Src
0x1800be57a  mov     rdx, r12; unsigned __int16 *
0x1800be57d  mov     rcx, r15; this
0x1800be580  call    ?Initialize@CWbemNamespace@@QEAAJPEAG0KKHHPEBGKHPEAUIWmiDbSession@@K@Z; CWbemNamespace::Initialize(ushort *,ushort *,ulong,ulong,int,int,ushort const *,ulong,int,IWmiDbSession *,ulong)
0x1800be585  mov     ebx, eax
0x1800be587  test    eax, eax
0x1800be589  jns     short loc_1800BE5CA
0x1800be58b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800be591  mov     edx, ebx
0x1800be593  mov     rcx, rax
0x1800be596  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800be59c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be5a3  cmp     rcx, r14
0x1800be5a6  jz      loc_1800BE6BF
0x1800be5ac  test    [rcx+1Ch], dil
0x1800be5b0  jz      loc_1800BE6BF
0x1800be5b6  cmp     byte ptr [rcx+19h], 2
0x1800be5ba  jb      loc_1800BE6BF
0x1800be5c0  mov     edx, 7Dh ; '}'
0x1800be5c5  jmp     loc_1800BE6AF
0x1800be5ca  mov     rcx, r15; this
0x1800be5cd  call    ?EnsureSecurity@CWbemNamespace@@QEAAJXZ; CWbemNamespace::EnsureSecurity(void)
0x1800be5d2  mov     ebx, eax
0x1800be5d4  test    eax, eax
0x1800be5d6  jns     short loc_1800BE617
0x1800be5d8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800be5de  mov     edx, ebx
0x1800be5e0  mov     rcx, rax
0x1800be5e3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800be5e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be5f0  cmp     rcx, r14
0x1800be5f3  jz      loc_1800BE6BF
0x1800be5f9  test    [rcx+1Ch], dil
0x1800be5fd  jz      loc_1800BE6BF
0x1800be603  cmp     byte ptr [rcx+19h], 2
0x1800be607  jb      loc_1800BE6BF
0x1800be60d  mov     edx, 7Eh ; '~'
0x1800be612  jmp     loc_1800BE6AF
0x1800be617  mov     r12, [rbp+57h+arg_8]
0x1800be61b  cmp     [rbp+57h+arg_10], 0
0x1800be61f  jz      short loc_1800BE666
0x1800be621  lea     rdx, [r15+0D8h]; struct CNtSecurityDescriptor *
0x1800be628  mov     rcx, r12; struct CNtSecurityDescriptor *
0x1800be62b  call    ?CopyInheritedDACLAces@@YAJAEAVCNtSecurityDescriptor@@0@Z; CopyInheritedDACLAces(CNtSecurityDescriptor &,CNtSecurityDescriptor &)
0x1800be630  mov     ebx, eax
0x1800be632  test    eax, eax
0x1800be634  jns     short loc_1800BE666
0x1800be636  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800be63c  mov     edx, ebx
0x1800be63e  mov     rcx, rax
0x1800be641  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800be647  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be64e  cmp     rcx, r14
0x1800be651  jz      short loc_1800BE6BF
0x1800be653  test    [rcx+1Ch], dil
0x1800be657  jz      short loc_1800BE6BF
0x1800be659  cmp     byte ptr [rcx+19h], 2
0x1800be65d  jb      short loc_1800BE6BF
0x1800be65f  mov     edx, 7Fh
0x1800be664  jmp     short loc_1800BE6AF
0x1800be666  cmp     [rbp+57h+arg_18], 0
0x1800be66a  jz      short loc_1800BE6D7
0x1800be66c  lea     rdx, [r15+0D8h]; struct CNtSecurityDescriptor *
0x1800be673  mov     rcx, r12; struct CNtSecurityDescriptor *
0x1800be676  call    ?CopyInheritedSACLAces@@YAJAEAVCNtSecurityDescriptor@@0@Z; CopyInheritedSACLAces(CNtSecurityDescriptor &,CNtSecurityDescriptor &)
0x1800be67b  mov     ebx, eax
0x1800be67d  test    eax, eax
0x1800be67f  jns     short loc_1800BE6D7
0x1800be681  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800be687  mov     edx, ebx
0x1800be689  mov     rcx, rax
0x1800be68c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800be692  mov     rcx, cs:WPP_GLOBAL_Control
0x1800be699  cmp     rcx, r14
0x1800be69c  jz      short loc_1800BE6BF
0x1800be69e  test    [rcx+1Ch], dil
0x1800be6a2  jz      short loc_1800BE6BF
0x1800be6a4  cmp     byte ptr [rcx+19h], 2
0x1800be6a8  jb      short loc_1800BE6BF
0x1800be6aa  mov     edx, 80h
0x1800be6af  mov     r9d, ebx
0x1800be6b2  mov     r8, rsi
0x1800be6b5  mov     rcx, [rcx+10h]
0x1800be6b9  call    WPP_SF_d
0x1800be6be  nop
0x1800be6bf  lea     rcx, [rbp+57h+arg_0]; this
0x1800be6c3  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800be6c8  nop
0x1800be6c9  lea     rcx, [rbp+57h+var_58]
0x1800be6cd  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x1800be6d2  jmp     loc_1800BE355
0x1800be6d7  lea     rcx, [rbp+57h+arg_0]; this
0x1800be6db  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x1800be6e0  nop
0x1800be6e1  lea     rcx, [rbp+57h+var_58]
0x1800be6e5  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x1800be6ea  xor     eax, eax
0x1800be6ec  add     rsp, 88h
0x1800be6f3  pop     r15
0x1800be6f5  pop     r14
0x1800be6f7  pop     r13
0x1800be6f9  pop     r12
0x1800be6fb  pop     rdi
0x1800be6fc  pop     rsi
0x1800be6fd  pop     rbx
0x1800be6fe  pop     rbp
0x1800be6ff  retn
```
