# MapFromCIMOMObject(CSWbemServices *,tagVARIANT *,ISWbemInternalObject *,ushort *,long)

- ea: `0x180005bf0`
- end: `0x180005f0d`
- name: `?MapFromCIMOMObject@@YAJPEAVCSWbemServices@@PEAUtagVARIANT@@PEAUISWbemInternalObject@@PEAGJ@Z`
- size: `797`
- prototype: `__int64 __usercall@<rax>(struct CSWbemServices *@<rcx>, struct tagVARIANT *@<rdx>, struct ISWbemInternalObject *@<r8>, unsigned __int16 *@<r9>, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180003a10`
- `0x1800051d0`
- `0x1800058c0`
- `0x180024720`

## callees

- `0x180005bf0`
- `0x180009320`
- `0x18000c0b0`
- `0x180017a90`
- `0x1800188e0`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180005d98`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180005d98`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180005d7d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180005d7d`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180005dd8`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180005dd8`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180005e62`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180005e62`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005c6e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005e0d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005c6e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005e0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
HRESULT __fastcall MapFromCIMOMObject(
        struct CSWbemServices *a1,
        struct tagVARIANT *a2,
        struct ISWbemInternalObject *a3,
        unsigned __int16 *a4,
        char a5)
{
  int v9; // ebx
  HRESULT result; // eax
  void (__fastcall ***llVal)(_QWORD, GUID *, LONG *); // rcx
  struct IWbemClassObject *v12; // rcx
  CSWbemObject *v13; // rax
  CSWbemObject *v14; // rsi
  CSWbemObject *v15; // rcx
  LONGLONG v16; // rax
  int v17; // r12d
  char v18; // r13
  LONG v19; // eax
  void *v20; // rax
  CSWbemObject *v21; // r13
  __int64 v22; // [rsp+20h] [rbp-48h]
  LONG plLbound; // [rsp+30h] [rbp-38h] BYREF
  LONG plUbound[2]; // [rsp+38h] [rbp-30h] BYREF
  struct IWbemClassObject *v25; // [rsp+40h] [rbp-28h] BYREF
  __int64 pv; // [rsp+48h] [rbp-20h] BYREF
  void *v27[3]; // [rsp+50h] [rbp-18h] BYREF
  CSWbemObject *rgIndices; // [rsp+B8h] [rbp+50h] BYREF

  v9 = 0;
  if ( a2->vt == 13 )
  {
    llVal = (void (__fastcall ***)(_QWORD, GUID *, LONG *))a2->llVal;
    if ( !llVal )
      return v9;
    *(_QWORD *)plUbound = 0;
    (**llVal)(llVal, &GUID_dc12a681_737f_11cf_884d_00aa004b2e24, plUbound);
    v12 = *(struct IWbemClassObject **)plUbound;
    if ( !*(_QWORD *)plUbound )
    {
LABEL_12:
      if ( v12 )
        ((void (__fastcall *)(struct IWbemClassObject *))v12->lpVtbl->Release)(v12);
      return v9;
    }
    v13 = (CSWbemObject *)CWin32DefaultArena::WbemMemAlloc(0x78u);
    rgIndices = v13;
    if ( v13 )
      v14 = CSWbemObject::CSWbemObject(v13, a1, *(struct IWbemClassObject **)plUbound, 0, 0);
    else
      v14 = 0;
    if ( !v14 )
    {
      v9 = -2147217402;
LABEL_11:
      v12 = *(struct IWbemClassObject **)plUbound;
      goto LABEL_12;
    }
    rgIndices = 0;
    (**(void (__fastcall ***)(CSWbemObject *, GUID *, CSWbemObject **))v14)(
      v14,
      &GUID_00020400_0000_0000_c000_000000000046,
      &rgIndices);
    if ( rgIndices )
    {
      (*(void (__fastcall **)(LONGLONG))(*a2->pllVal + 16))(a2->llVal);
      v16 = (LONGLONG)rgIndices;
      v15 = 0;
      rgIndices = 0;
      a2->llVal = v16;
      a2->vt = 9;
      if ( !a3 )
      {
LABEL_18:
        if ( v15 )
          (*(void (__fastcall **)(CSWbemObject *))(*(_QWORD *)v15 + 16LL))(v15);
        goto LABEL_11;
      }
      (*(void (__fastcall **)(__int64, struct ISWbemInternalObject *, unsigned __int16 *, __int64))(*((_QWORD *)v14 + 2)
                                                                                                  + 32LL))(
        (__int64)v14 + 16,
        a3,
        a4,
        0xFFFFFFFFLL);
    }
    else
    {
      (*(void (__fastcall **)(CSWbemObject *, __int64))(*(_QWORD *)v14 + 288LL))(v14, 1);
      v9 = -2147217407;
    }
    v15 = rgIndices;
    goto LABEL_18;
  }
  if ( a2->vt != 8205 )
    return v9;
  plLbound = 0;
  plUbound[0] = 0;
  result = SafeArrayGetLBound(a2->parray, 1u, &plLbound);
  if ( result >= 0 )
  {
    result = SafeArrayGetUBound(a2->parray, 1u, plUbound);
    v17 = result;
    if ( result >= 0 )
    {
      v18 = 1;
      a5 = 1;
      v19 = plLbound;
      LODWORD(rgIndices) = plLbound;
      while ( 1 )
      {
        if ( v19 > plUbound[0] )
          return v17;
        pv = 0;
        if ( SafeArrayGetElement(a2->parray, (LONG *)&rgIndices, &pv) < 0 || !pv )
        {
          v18 = 0;
          a5 = 0;
          v17 = -2147217407;
          goto LABEL_46;
        }
        ATL::CComQIPtr<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>::CComQIPtr<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>(&v25);
        if ( v25 )
          break;
LABEL_44:
        ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>((__int64 *)&v25);
LABEL_46:
        ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&pv);
        v19 = (_DWORD)rgIndices + 1;
        LODWORD(rgIndices) = (_DWORD)rgIndices + 1;
        if ( !v18 )
          return v17;
      }
      v20 = CWin32DefaultArena::WbemMemAlloc(0x78u);
      v27[1] = v20;
      if ( v20 )
      {
        LOBYTE(v22) = 0;
        v21 = CSWbemObject::CSWbemObject((CSWbemObject *)v20, a1, v25, 0, v22);
      }
      else
      {
        v21 = 0;
      }
      if ( !v21 )
      {
        v17 = -2147217402;
        v18 = 0;
        a5 = 0;
        goto LABEL_44;
      }
      ATL::CComQIPtr<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>::CComQIPtr<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>(
        v27,
        v21);
      if ( v27[0] )
      {
        if ( SafeArrayPutElement(a2->parray, (LONG *)&rgIndices, v27[0]) < 0 )
        {
          v17 = -2147217407;
          v18 = 0;
          a5 = 0;
LABEL_42:
          ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>((__int64 *)v27);
          goto LABEL_44;
        }
        a2->vt = 8201;
        if ( a3 )
          (*(void (__fastcall **)(__int64, struct ISWbemInternalObject *, unsigned __int16 *, _QWORD))(*((_QWORD *)v21 + 2) + 32LL))(
            (__int64)v21 + 16,
            a3,
            a4,
            (unsigned int)rgIndices);
      }
      else
      {
        (*(void (__fastcall **)(CSWbemObject *, __int64))(*(_QWORD *)v21 + 288LL))(v21, 1);
        v17 = -2147217407;
      }
      v18 = a5;
      goto LABEL_42;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005bf0  push    rbp
0x180005bf2  push    rbx
0x180005bf3  push    rsi
0x180005bf4  push    rdi
0x180005bf5  push    r12
0x180005bf7  push    r13
0x180005bf9  push    r14
0x180005bfb  push    r15
0x180005bfd  mov     rbp, rsp
0x180005c00  sub     rsp, 68h
0x180005c04  mov     r15, r9
0x180005c07  mov     r14, r8
0x180005c0a  mov     rdi, rdx
0x180005c0d  mov     rsi, rcx
0x180005c10  xor     ebx, ebx
0x180005c12  movzx   eax, word ptr [rdx]
0x180005c15  cmp     ax, 0Dh
0x180005c19  jz      short loc_180005C3C
0x180005c1b  mov     ecx, 200Dh
0x180005c20  cmp     ax, cx
0x180005c23  jz      loc_180005D6A
0x180005c29  mov     eax, ebx
0x180005c2b  add     rsp, 68h
0x180005c2f  pop     r15
0x180005c31  pop     r14
0x180005c33  pop     r13
0x180005c35  pop     r12
0x180005c37  pop     rdi
0x180005c38  pop     rsi
0x180005c39  pop     rbx
0x180005c3a  pop     rbp
0x180005c3b  retn
0x180005c3c  mov     rcx, [rdx+8]
0x180005c40  test    rcx, rcx
0x180005c43  jz      short loc_180005C29
0x180005c45  mov     qword ptr [rbp+plUbound], rbx
0x180005c49  mov     rax, [rcx]
0x180005c4c  lea     r8, [rbp+plUbound]
0x180005c50  lea     rdx, _GUID_dc12a681_737f_11cf_884d_00aa004b2e24
0x180005c57  mov     rax, [rax]
0x180005c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c5f  nop
0x180005c60  mov     rcx, qword ptr [rbp+plUbound]
0x180005c64  test    rcx, rcx
0x180005c67  jz      short loc_180005CA9
0x180005c69  mov     ecx, 78h ; 'x'
0x180005c6e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180005c74  mov     [rbp+rgIndices], rax
0x180005c78  test    rax, rax
0x180005c7b  jz      loc_180005D1D
0x180005c81  mov     [rsp+68h+var_48], 0; bool
0x180005c86  xor     r9d, r9d; struct CSWbemSecurity *
0x180005c89  mov     r8, qword ptr [rbp+plUbound]; struct IWbemClassObject *
0x180005c8d  mov     rdx, rsi; struct CSWbemServices *
0x180005c90  mov     rcx, rax; this
0x180005c93  call    ??0CSWbemObject@@QEAA@PEAVCSWbemServices@@PEAUIWbemClassObject@@PEAVCSWbemSecurity@@_N@Z; CSWbemObject::CSWbemObject(CSWbemServices *,IWbemClassObject *,CSWbemSecurity *,bool)
0x180005c98  mov     rsi, rax
0x180005c9b  test    rsi, rsi
0x180005c9e  jnz     short loc_180005CC0
0x180005ca0  mov     ebx, 80041006h
0x180005ca5  mov     rcx, qword ptr [rbp+plUbound]
0x180005ca9  test    rcx, rcx
0x180005cac  jz      short loc_180005CBB
0x180005cae  mov     rdx, [rcx]
0x180005cb1  mov     rax, [rdx+10h]
0x180005cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cba  nop
0x180005cbb  jmp     loc_180005C29
0x180005cc0  mov     [rbp+rgIndices], 0
0x180005cc8  mov     rax, [rsi]
0x180005ccb  lea     r8, [rbp+rgIndices]
0x180005ccf  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x180005cd6  mov     rcx, rsi
0x180005cd9  mov     rax, [rax]
0x180005cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ce1  nop
0x180005ce2  cmp     [rbp+rgIndices], 0
0x180005ce7  jnz     short loc_180005D24
0x180005ce9  mov     rax, [rsi]
0x180005cec  mov     edx, 1
0x180005cf1  mov     rcx, rsi
0x180005cf4  mov     rax, [rax+120h]
0x180005cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d00  mov     ebx, 80041001h
0x180005d05  mov     rcx, [rbp+rgIndices]
0x180005d09  test    rcx, rcx
0x180005d0c  jz      short loc_180005D1B
0x180005d0e  mov     rax, [rcx]
0x180005d11  mov     rax, [rax+10h]
0x180005d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d1a  nop
0x180005d1b  jmp     short loc_180005CA5
0x180005d1d  xor     esi, esi
0x180005d1f  jmp     loc_180005C9B
0x180005d24  mov     rcx, [rdi+8]
0x180005d28  mov     rax, [rcx]
0x180005d2b  mov     rax, [rax+10h]
0x180005d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d34  mov     rax, [rbp+rgIndices]
0x180005d38  xor     ecx, ecx
0x180005d3a  mov     [rbp+rgIndices], rcx
0x180005d3e  mov     [rdi+8], rax
0x180005d42  mov     word ptr [rdi], 9
0x180005d47  test    r14, r14
0x180005d4a  jz      short loc_180005D09
0x180005d4c  lea     rcx, [rsi+10h]
0x180005d50  mov     rax, [rcx]
0x180005d53  mov     r9d, 0FFFFFFFFh
0x180005d59  mov     r8, r15
0x180005d5c  mov     rdx, r14
0x180005d5f  mov     rax, [rax+20h]
0x180005d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d68  jmp     short loc_180005D05
0x180005d6a  mov     [rbp+plLbound], ebx
0x180005d6d  mov     [rbp+plUbound], ebx
0x180005d70  lea     r8, [rbp+plLbound]; plLbound
0x180005d74  mov     edx, 1; nDim
0x180005d79  mov     rcx, [rdi+8]; psa
0x180005d7d  call    cs:__imp_SafeArrayGetLBound
0x180005d83  test    eax, eax
0x180005d85  js      loc_180005C2B
0x180005d8b  lea     r8, [rbp+plUbound]; plUbound
0x180005d8f  mov     edx, 1; nDim
0x180005d94  mov     rcx, [rdi+8]; psa
0x180005d98  call    cs:__imp_SafeArrayGetUBound
0x180005d9e  mov     r12d, eax
0x180005da1  test    eax, eax
0x180005da3  js      loc_180005C2B
0x180005da9  mov     r13b, 1
0x180005dac  mov     byte ptr [rbp+arg_20], r13b
0x180005db0  mov     eax, [rbp+plLbound]
0x180005db3  mov     dword ptr [rbp+rgIndices], eax
0x180005db6  mov     ebx, 80041001h
0x180005dbb  cmp     eax, [rbp+plUbound]
0x180005dbe  jg      loc_180005F05
0x180005dc4  mov     [rbp+pv], 0
0x180005dcc  lea     r8, [rbp+pv]; pv
0x180005dd0  lea     rdx, [rbp+rgIndices]; rgIndices
0x180005dd4  mov     rcx, [rdi+8]; psa
0x180005dd8  call    cs:__imp_SafeArrayGetElement
0x180005dde  test    eax, eax
0x180005de0  js      loc_180005EE1
0x180005de6  mov     rdx, [rbp+pv]
0x180005dea  test    rdx, rdx
0x180005ded  jz      loc_180005EE1
0x180005df3  lea     rcx, [rbp+var_28]
0x180005df7  call    ??0?$CComQIPtr@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>::CComQIPtr<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>(IUnknown *)
0x180005dfc  nop
0x180005dfd  cmp     [rbp+var_28], 0
0x180005e02  jz      loc_180005ED6
0x180005e08  mov     ecx, 78h ; 'x'
0x180005e0d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180005e13  mov     [rbp+var_10], rax
0x180005e17  test    rax, rax
0x180005e1a  jz      short loc_180005E38
0x180005e1c  mov     [rsp+68h+var_48], 0; bool
0x180005e21  xor     r9d, r9d; struct CSWbemSecurity *
0x180005e24  mov     r8, [rbp+var_28]; struct IWbemClassObject *
0x180005e28  mov     rdx, rsi; struct CSWbemServices *
0x180005e2b  mov     rcx, rax; this
0x180005e2e  call    ??0CSWbemObject@@QEAA@PEAVCSWbemServices@@PEAUIWbemClassObject@@PEAVCSWbemSecurity@@_N@Z; CSWbemObject::CSWbemObject(CSWbemServices *,IWbemClassObject *,CSWbemSecurity *,bool)
0x180005e33  mov     r13, rax
0x180005e36  jmp     short loc_180005E3B
0x180005e38  xor     r13d, r13d
0x180005e3b  test    r13, r13
0x180005e3e  jz      loc_180005EC9
0x180005e44  mov     rdx, r13
0x180005e47  lea     rcx, [rbp+var_18]
0x180005e4b  call    ??0?$CComQIPtr@UIDispatch@@$1?_GUID_00020400_0000_0000_c000_000000000046@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>::CComQIPtr<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>(IUnknown *)
0x180005e50  nop
0x180005e51  mov     r8, [rbp+var_18]; pv
0x180005e55  test    r8, r8
0x180005e58  jz      short loc_180005E9E
0x180005e5a  lea     rdx, [rbp+rgIndices]; rgIndices
0x180005e5e  mov     rcx, [rdi+8]; psa
0x180005e62  call    cs:__imp_SafeArrayPutElement
0x180005e68  test    eax, eax
0x180005e6a  jns     short loc_180005E78
0x180005e6c  mov     r12d, ebx
0x180005e6f  xor     r13b, r13b
0x180005e72  mov     byte ptr [rbp+arg_20], r13b
0x180005e76  jmp     short loc_180005EBE
0x180005e78  mov     word ptr [rdi], 2009h
0x180005e7d  test    r14, r14
0x180005e80  jz      short loc_180005EB9
0x180005e82  lea     rcx, [r13+10h]
0x180005e86  mov     rax, [rcx]
0x180005e89  mov     r9d, dword ptr [rbp+rgIndices]
0x180005e8d  mov     r8, r15
0x180005e90  mov     rdx, r14
0x180005e93  mov     rax, [rax+20h]
0x180005e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e9c  jmp     short loc_180005EB9
0x180005e9e  mov     rax, [r13+0]
0x180005ea2  mov     edx, 1
0x180005ea7  mov     rcx, r13
0x180005eaa  mov     rax, [rax+120h]
0x180005eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eb6  mov     r12d, ebx
0x180005eb9  movzx   r13d, byte ptr [rbp+arg_20]
0x180005ebe  lea     rcx, [rbp+var_18]
0x180005ec2  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x180005ec7  jmp     short loc_180005ED6
0x180005ec9  mov     r12d, 80041006h
0x180005ecf  xor     r13b, r13b
0x180005ed2  mov     byte ptr [rbp+arg_20], r13b
0x180005ed6  lea     rcx, [rbp+var_28]
0x180005eda  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x180005edf  jmp     short loc_180005EEB
0x180005ee1  xor     r13b, r13b
0x180005ee4  mov     byte ptr [rbp+arg_20], r13b
0x180005ee8  mov     r12d, ebx
0x180005eeb  lea     rcx, [rbp+pv]
0x180005eef  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x180005ef4  mov     eax, dword ptr [rbp+rgIndices]
0x180005ef7  inc     eax
0x180005ef9  mov     dword ptr [rbp+rgIndices], eax
0x180005efc  test    r13b, r13b
0x180005eff  jnz     loc_180005DBB
0x180005f05  mov     eax, r12d
0x180005f08  jmp     loc_180005C2B
```
