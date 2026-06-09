# BuildACLObject(IWbemServices *,ushort *,IWbemContext *,CNtAcl *,IWbemClassObject *)

- ea: `0x18003b210`
- end: `0x18003b56e`
- name: `?BuildACLObject@@YAJPEAUIWbemServices@@PEAGPEAUIWbemContext@@PEAVCNtAcl@@PEAUIWbemClassObject@@@Z`
- size: `862`
- prototype: `__int64 __fastcall(struct IWbemServices *, unsigned __int16 *, struct IWbemContext *, struct CNtAcl *, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003b580`

## callees

- `0x180013564`
- `0x180014120`
- `0x18001bfe4`
- `0x18001c130`
- `0x18001c1e0`
- `0x1800269d4`
- `0x180028484`
- `0x18003a678`
- `0x18003ac1c`
- `0x18003ad34`
- `0x18003b210`
- `0x180047010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003b242`
- `OLEAUT32!__imp_VariantInit` at `0x18003b242`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18003b2dd`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18003b2dd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18003b34a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18003b3b1`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18003b3b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BuildACLObject(
        struct IWbemServices *a1,
        unsigned __int16 *a2,
        struct IWbemContext *a3,
        struct CNtAcl *a4,
        struct IWbemClassObject *a5)
{
  struct IWbemServices *v8; // rbx
  int v9; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r9
  ULONG NumAces; // r15d
  SAFEARRAY *v15; // rax
  SAFEARRAY *v16; // r14
  LONG v17; // eax
  unsigned int v18; // ecx
  CNtAce *Ace; // rax
  int v20; // eax
  HRESULT v21; // eax
  _QWORD *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // r9
  __int64 v26; // rcx
  int v27; // eax
  void *pv; // [rsp+38h] [rbp-48h] BYREF
  CNtAce *v30; // [rsp+40h] [rbp-40h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v33[24]; // [rsp+68h] [rbp-18h] BYREF
  LONG rgIndices; // [rsp+D8h] [rbp+58h] BYREF

  v8 = a1;
  VariantInit(&pvarg);
  if ( a4 )
  {
    NumAces = CNtAcl::GetNumAces(a4);
    rgsabound.cElements = NumAces;
    rgsabound.lLbound = 0;
    v15 = SafeArrayCreate(0xDu, 1u, &rgsabound);
    v16 = v15;
    if ( v15 )
    {
      MakeGuard<void * (*)(void *),unsigned short *>(v33, SafeArrayDestroy, v15);
      v17 = 0;
      v18 = 0;
      while ( 1 )
      {
        rgIndices = v17;
        if ( v18 >= NumAces )
          break;
        Ace = CNtAcl::GetAce(a4, v17);
        if ( !Ace )
        {
          v10 = -2147217407;
          CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2147217407);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v24 = 44;
            v25 = 2147749889LL;
            v26 = *((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_40:
            WPP_SF_D(v26, v24, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v25);
            goto LABEL_41;
          }
          goto LABEL_41;
        }
        v30 = Ace;
        pv = 0;
        v20 = BuildACEObject(v8, a3, Ace, (struct IWbemClassObject **)&pv);
        v10 = v20;
        if ( v20 < 0 )
        {
          CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v20);
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v23 = 45;
LABEL_24:
            WPP_SF_D(v22[2], v23, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v10);
          }
LABEL_25:
          _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&pv);
          CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(&v30);
          goto LABEL_41;
        }
        v21 = SafeArrayPutElement(v16, &rgIndices, pv);
        v10 = v21;
        if ( v21 < 0 )
        {
          CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v21);
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v23 = 46;
            goto LABEL_24;
          }
          goto LABEL_25;
        }
        _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release((__int64 *)&pv);
        CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(&v30);
        v17 = rgIndices + 1;
        v18 = rgIndices + 1;
        v8 = a1;
      }
      pvarg.vt = 8205;
      pvarg.llVal = (LONGLONG)v16;
      v33[0] = 1;
      v27 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))a5->lpVtbl->Put)(
              a5,
              a2,
              0,
              &pvarg,
              0);
      v10 = v27;
      if ( v27 < 0 )
        CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v27);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v24 = 47;
        v25 = v10;
        v26 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        goto LABEL_40;
      }
LABEL_41:
      ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>((__int64)v33);
    }
    else
    {
      v10 = -2147217402;
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2147217402);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 43;
        v13 = 2147749894LL;
        goto LABEL_13;
      }
    }
  }
  else
  {
    pvarg.vt = 1;
    v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))a5->lpVtbl->Put)(
           a5,
           a2,
           0,
           &pvarg,
           0);
    v10 = v9;
    if ( v9 < 0 )
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v9);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 42;
      v13 = v10;
LABEL_13:
      WPP_SF_D(v11[2], v12, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v13);
    }
  }
  _variant_t::~_variant_t(&pvarg);
  return v10;
}

```

## disassembly

```asm
0x18003b210  mov     [rsp-38h+arg_8], rbx
0x18003b215  mov     [rsp-38h+arg_0], rcx
0x18003b21a  push    rbp
0x18003b21b  push    rsi
0x18003b21c  push    rdi
0x18003b21d  push    r12
0x18003b21f  push    r13
0x18003b221  push    r14
0x18003b223  push    r15
0x18003b225  mov     rbp, rsp
0x18003b228  sub     rsp, 80h
0x18003b22f  mov     rsi, r9
0x18003b232  mov     r13, r8
0x18003b235  mov     r12, rdx
0x18003b238  mov     rbx, rcx
0x18003b23b  xor     r14d, r14d
0x18003b23e  lea     rcx, [rbp+pvarg]; pvarg
0x18003b242  call    cs:__imp_VariantInit
0x18003b248  nop
0x18003b249  test    rsi, rsi
0x18003b24c  jnz     short loc_18003B2BD
0x18003b24e  lea     edi, [rsi+1]
0x18003b251  mov     word ptr [rbp+pvarg], di
0x18003b255  mov     rcx, [rbp+arg_20]
0x18003b259  mov     rax, [rcx]
0x18003b25c  mov     [rsp+80h+var_60], r14d
0x18003b261  lea     r9, [rbp+pvarg]
0x18003b265  xor     r8d, r8d
0x18003b268  mov     rdx, r12
0x18003b26b  mov     rax, [rax+28h]
0x18003b26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b274  mov     ebx, eax
0x18003b276  test    eax, eax
0x18003b278  jns     short loc_18003B288
0x18003b27a  mov     edx, eax; int
0x18003b27c  lea     rcx, qword_18006A9C0; this
0x18003b283  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b288  lea     rcx, WPP_GLOBAL_Control
0x18003b28f  mov     rax, cs:WPP_GLOBAL_Control
0x18003b296  cmp     rax, rcx
0x18003b299  jz      loc_18003B548
0x18003b29f  test    [rax+1Ch], dil
0x18003b2a3  jz      loc_18003B548
0x18003b2a9  cmp     byte ptr [rax+19h], 2
0x18003b2ad  jb      loc_18003B548
0x18003b2b3  mov     edx, 2Ah ; '*'
0x18003b2b8  mov     r9d, ebx
0x18003b2bb  jmp     short loc_18003B332
0x18003b2bd  mov     rcx, rsi; this
0x18003b2c0  call    ?GetNumAces@CNtAcl@@QEAAHXZ; CNtAcl::GetNumAces(void)
0x18003b2c5  mov     r15d, eax
0x18003b2c8  mov     [rbp+rgsabound.cElements], eax
0x18003b2cb  mov     [rbp+rgsabound.lLbound], r14d
0x18003b2cf  mov     ecx, 0Dh; vt
0x18003b2d4  lea     r8, [rbp+rgsabound]; rgsabound
0x18003b2d8  lea     edi, [rcx-0Ch]
0x18003b2db  mov     edx, edi; cDims
0x18003b2dd  call    cs:__imp_SafeArrayCreate
0x18003b2e3  mov     r14, rax
0x18003b2e6  test    rax, rax
0x18003b2e9  jnz     short loc_18003B347
0x18003b2eb  mov     ebx, 80041006h
0x18003b2f0  mov     edx, ebx; int
0x18003b2f2  lea     rcx, qword_18006A9C0; this
0x18003b2f9  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b2fe  lea     rcx, WPP_GLOBAL_Control
0x18003b305  mov     rax, cs:WPP_GLOBAL_Control
0x18003b30c  cmp     rax, rcx
0x18003b30f  jz      loc_18003B548
0x18003b315  test    [rax+1Ch], dil
0x18003b319  jz      loc_18003B548
0x18003b31f  cmp     byte ptr [rax+19h], 2
0x18003b323  jb      loc_18003B548
0x18003b329  lea     edx, [rdi+2Ah]
0x18003b32c  mov     r9d, 80041006h
0x18003b332  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003b339  mov     rcx, [rax+10h]
0x18003b33d  call    WPP_SF_D
0x18003b342  jmp     loc_18003B548
0x18003b347  mov     r8, r14
0x18003b34a  mov     rdx, cs:__imp_SafeArrayDestroy
0x18003b351  lea     rcx, [rbp+var_18]
0x18003b355  call    ??$MakeGuard@P6APEAXPEAX@ZPEAG@@YA?AV?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@@P6APEAXPEAX@ZPEAG@Z; MakeGuard<void * (*)(void *),ushort *>(void * (*)(void *),ushort *)
0x18003b35a  nop
0x18003b35b  xor     eax, eax
0x18003b35d  xor     ecx, ecx
0x18003b35f  mov     [rbp+rgIndices], eax
0x18003b362  cmp     ecx, r15d
0x18003b365  jnb     loc_18003B4BE
0x18003b36b  mov     edx, eax; int
0x18003b36d  mov     rcx, rsi; this
0x18003b370  call    ?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z; CNtAcl::GetAce(int)
0x18003b375  test    rax, rax
0x18003b378  jz      loc_18003B46F
0x18003b37e  mov     [rbp+var_40], rax
0x18003b382  mov     [rbp+pv], 0
0x18003b38a  lea     r9, [rbp+pv]; struct IWbemClassObject **
0x18003b38e  mov     r8, rax; this
0x18003b391  mov     rdx, r13; struct IWbemContext *
0x18003b394  mov     rcx, rbx; struct IWbemServices *
0x18003b397  call    ?BuildACEObject@@YAJPEAUIWbemServices@@PEAUIWbemContext@@PEAVCNtAce@@PEAPEAUIWbemClassObject@@@Z; BuildACEObject(IWbemServices *,IWbemContext *,CNtAce *,IWbemClassObject * *)
0x18003b39c  mov     ebx, eax
0x18003b39e  test    eax, eax
0x18003b3a0  js      loc_18003B43B
0x18003b3a6  mov     r8, [rbp+pv]; pv
0x18003b3aa  lea     rdx, [rbp+rgIndices]; rgIndices
0x18003b3ae  mov     rcx, r14; psa
0x18003b3b1  call    cs:__imp_SafeArrayPutElement
0x18003b3b7  mov     ebx, eax
0x18003b3b9  test    eax, eax
0x18003b3bb  js      short loc_18003B3DD
0x18003b3bd  lea     rcx, [rbp+pv]
0x18003b3c1  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003b3c6  nop
0x18003b3c7  lea     rcx, [rbp+var_40]
0x18003b3cb  call    ??1?$CDeleteMe@VCNtAce@@@@QEAA@XZ; CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(void)
0x18003b3d0  mov     eax, [rbp+rgIndices]
0x18003b3d3  add     eax, edi
0x18003b3d5  mov     ecx, eax
0x18003b3d7  mov     rbx, [rbp+arg_0]
0x18003b3db  jmp     short loc_18003B35F
0x18003b3dd  mov     edx, ebx; int
0x18003b3df  lea     rcx, qword_18006A9C0; this
0x18003b3e6  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b3eb  lea     rcx, WPP_GLOBAL_Control
0x18003b3f2  mov     rax, cs:WPP_GLOBAL_Control
0x18003b3f9  cmp     rax, rcx
0x18003b3fc  jz      short loc_18003B423
0x18003b3fe  test    [rax+1Ch], dil
0x18003b402  jz      short loc_18003B423
0x18003b404  cmp     byte ptr [rax+19h], 2
0x18003b408  jb      short loc_18003B423
0x18003b40a  mov     edx, 2Eh ; '.'
0x18003b40f  mov     r9d, ebx
0x18003b412  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003b419  mov     rcx, [rax+10h]
0x18003b41d  call    WPP_SF_D
0x18003b422  nop
0x18003b423  lea     rcx, [rbp+pv]
0x18003b427  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x18003b42c  nop
0x18003b42d  lea     rcx, [rbp+var_40]
0x18003b431  call    ??1?$CDeleteMe@VCNtAce@@@@QEAA@XZ; CDeleteMe<CNtAce>::~CDeleteMe<CNtAce>(void)
0x18003b436  jmp     loc_18003B53E
0x18003b43b  mov     edx, ebx; int
0x18003b43d  lea     rcx, qword_18006A9C0; this
0x18003b444  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b449  lea     rcx, WPP_GLOBAL_Control
0x18003b450  mov     rax, cs:WPP_GLOBAL_Control
0x18003b457  cmp     rax, rcx
0x18003b45a  jz      short loc_18003B423
0x18003b45c  test    [rax+1Ch], dil
0x18003b460  jz      short loc_18003B423
0x18003b462  cmp     byte ptr [rax+19h], 2
0x18003b466  jb      short loc_18003B423
0x18003b468  mov     edx, 2Dh ; '-'
0x18003b46d  jmp     short loc_18003B40F
0x18003b46f  mov     ebx, 80041001h
0x18003b474  mov     edx, ebx; int
0x18003b476  lea     rcx, qword_18006A9C0; this
0x18003b47d  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b482  lea     rcx, WPP_GLOBAL_Control
0x18003b489  mov     rax, cs:WPP_GLOBAL_Control
0x18003b490  cmp     rax, rcx
0x18003b493  jz      loc_18003B53E
0x18003b499  test    [rax+1Ch], dil
0x18003b49d  jz      loc_18003B53E
0x18003b4a3  cmp     byte ptr [rax+19h], 2
0x18003b4a7  jb      loc_18003B53E
0x18003b4ad  mov     edx, 2Ch ; ','
0x18003b4b2  mov     r9d, 80041001h
0x18003b4b8  mov     rcx, [rax+10h]
0x18003b4bc  jmp     short loc_18003B531
0x18003b4be  mov     eax, 200Dh
0x18003b4c3  mov     word ptr [rbp+pvarg], ax
0x18003b4c7  mov     qword ptr [rbp+pvarg+8], r14
0x18003b4cb  mov     [rbp+var_18], dil
0x18003b4cf  mov     rcx, [rbp+arg_20]
0x18003b4d3  mov     rax, [rcx]
0x18003b4d6  mov     [rsp+80h+var_60], 0
0x18003b4de  lea     r9, [rbp+pvarg]
0x18003b4e2  xor     r8d, r8d
0x18003b4e5  mov     rdx, r12
0x18003b4e8  mov     rax, [rax+28h]
0x18003b4ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b4f1  mov     ebx, eax
0x18003b4f3  test    eax, eax
0x18003b4f5  jns     short loc_18003B505
0x18003b4f7  mov     edx, eax; int
0x18003b4f9  lea     rcx, qword_18006A9C0; this
0x18003b500  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b505  lea     rcx, WPP_GLOBAL_Control
0x18003b50c  mov     r10, cs:WPP_GLOBAL_Control
0x18003b513  cmp     r10, rcx
0x18003b516  jz      short loc_18003B53E
0x18003b518  test    [r10+1Ch], dil
0x18003b51c  jz      short loc_18003B53E
0x18003b51e  cmp     byte ptr [r10+19h], 2
0x18003b523  jb      short loc_18003B53E
0x18003b525  mov     edx, 2Fh ; '/'
0x18003b52a  mov     r9d, ebx
0x18003b52d  mov     rcx, [r10+10h]
0x18003b531  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003b538  call    WPP_SF_D
0x18003b53d  nop
0x18003b53e  lea     rcx, [rbp+var_18]
0x18003b542  call    ??1?$ScopeGuardImpl1@P6AXPEBUtagVARIANT@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>(void)
0x18003b547  nop
0x18003b548  lea     rcx, [rbp+pvarg]; this
0x18003b54c  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003b551  mov     eax, ebx
0x18003b553  mov     rbx, [rsp+80h+arg_8]
0x18003b55b  add     rsp, 80h
0x18003b562  pop     r15
0x18003b564  pop     r14
0x18003b566  pop     r13
0x18003b568  pop     r12
0x18003b56a  pop     rdi
0x18003b56b  pop     rsi
0x18003b56c  pop     rbp
0x18003b56d  retn
```
