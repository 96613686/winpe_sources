# CGeneratedPlaylistContainer::ExecuteQuery(ushort const *,ushort const *,bool,bool,CShellQueryResults * *)

- ea: `0x140085860`
- end: `0x140085ad3`
- name: `?ExecuteQuery@CGeneratedPlaylistContainer@@UEAAJPEBG0_N1PEAPEAVCShellQueryResults@@@Z`
- size: `627`
- prototype: `__int64 __usercall@<rax>(struct IUnknown *this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, bool@<r9b>, bool, struct CShellQueryResults **)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x140006d70`
- `0x14000c920`
- `0x14000cb74`
- `0x14000f274`
- `0x140024688`
- `0x140037478`
- `0x14003fb84`
- `0x140072f38`
- `0x140082bb8`
- `0x140083480`
- `0x140085860`
- `0x1400863c4`
- `0x140089658`
- `0x1400897c4`
- `0x14009e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400858b5`
- `KERNEL32!EnterCriticalSection` at `0x1400858b5`
- `KERNEL32!LeaveCriticalSection` at `0x140085a38`
- `KERNEL32!LeaveCriticalSection` at `0x140085a38`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x1400858dc`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x1400858dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CGeneratedPlaylistContainer::ExecuteQuery(
        struct IUnknown *this,
        char *a2,
        char *a3,
        __int64 a4,
        char a5,
        struct IUnknown ***a6)
{
  HRESULT Command; // ebx
  struct IUnknown **v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // r8
  CShellCommandFactory *v13; // rax
  void *v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  void *ppv; // [rsp+50h] [rbp-69h] BYREF
  void *v19; // [rsp+58h] [rbp-61h] BYREF
  void *v20; // [rsp+60h] [rbp-59h] BYREF
  void *v21; // [rsp+68h] [rbp-51h] BYREF
  _QWORD v22[3]; // [rsp+70h] [rbp-49h] BYREF
  int v23; // [rsp+88h] [rbp-31h]
  _BYTE v24[112]; // [rsp+90h] [rbp-29h] BYREF

  ppv = 0;
  Command = ATL::CComObject<CShellQueryResults>::CreateInstance(&ppv);
  v10 = (struct IUnknown **)ppv;
  if ( Command < 0 )
    goto LABEL_15;
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 8LL))(ppv);
  EnterCriticalSection(&CShellLock::_ShellLock);
  if ( this[8].lpVtbl )
    goto LABEL_6;
  ppv = 0;
  Command = SHCreateItemFromParsingName((PCWSTR)this[7].lpVtbl, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  if ( Command >= 0 )
    Command = SHLoadPlaylistFromItem(ppv, v11, v12, &this[8]);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  if ( Command >= 0 )
  {
LABEL_6:
    ppv = 0;
    v13 = (CShellCommandFactory *)((__int64 (__fastcall *)(struct IUnknown *))this->lpVtbl[4].QueryInterface)(this);
    Command = CShellCommandFactory::CreateCommand(v13, (struct ICommandText **)&ppv);
    if ( Command >= 0 )
    {
      memset(v22, 0, sizeof(v22));
      v23 = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        &v21,
        (char *)&Password);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        &v20,
        a3);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        &v19,
        a2);
      v14 = ppv;
      v15 = ((__int64 (__fastcall *)(struct IUnknown *))this->lpVtbl[4].QueryInterface)(this);
      CShellSearchQuery::CShellSearchQuery(
        (__int64)v24,
        v15 + 16,
        a5,
        (__int64)v14,
        (const void **)&v19,
        (const void **)&v20,
        7,
        0,
        (const void **)&v21);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v19);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v20);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v21);
      Command = CShellSearchQuery::Execute(v24, v22);
      if ( Command >= 0 )
        CGeneratedPlaylistContainer::FilterResultSet(this, v22, v10 + 8);
      CShellSearchQuery::~CShellSearchQuery((CShellSearchQuery *)v24);
      ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::~CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>((__int64)v22);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  }
  LeaveCriticalSection(&CShellLock::_ShellLock);
  if ( Command < 0 )
  {
LABEL_15:
    if ( v10 )
      ((void (__fastcall *)(struct IUnknown **))(*v10)[2].lpVtbl)(v10);
  }
  else
  {
    if ( v10[3] != this )
      ATL::AtlComPtrAssign(v10 + 3, this);
    *a6 = v10;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v16 = ((__int64 (__fastcall *)(struct IUnknown *))this->lpVtbl[2].AddRef)(this);
    WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, Command);
  }
  return (unsigned int)Command;
}

```

## disassembly

```asm
0x140085860  push    rbp
0x140085862  push    rbx
0x140085863  push    rsi
0x140085864  push    rdi
0x140085865  push    r12
0x140085867  push    r14
0x140085869  push    r15
0x14008586b  lea     rbp, [rsp-17h]
0x140085870  sub     rsp, 0D0h
0x140085877  mov     r12, r8
0x14008587a  mov     r15, rdx
0x14008587d  mov     rdi, rcx
0x140085880  mov     [rbp+47h+ppv], 0
0x140085888  lea     rcx, [rbp+47h+ppv]
0x14008588c  call    ?CreateInstance@?$CComObject@VCShellQueryResults@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CShellQueryResults>::CreateInstance(ATL::CComObject<CShellQueryResults> * *)
0x140085891  mov     ebx, eax
0x140085893  mov     rsi, [rbp+47h+ppv]
0x140085897  test    eax, eax
0x140085899  js      loc_140085A5C
0x14008589f  mov     rax, [rsi]
0x1400858a2  mov     rcx, rsi
0x1400858a5  mov     rax, [rax+8]
0x1400858a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400858ae  lea     rcx, ?_ShellLock@CShellLock@@0V1@A; lpCriticalSection
0x1400858b5  call    cs:__imp_EnterCriticalSection
0x1400858bb  nop
0x1400858bc  cmp     qword ptr [rdi+40h], 0
0x1400858c1  jnz     short loc_140085908
0x1400858c3  mov     [rbp+47h+ppv], 0
0x1400858cb  lea     r9, [rbp+47h+ppv]; ppv
0x1400858cf  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1400858d6  xor     edx, edx; pbc
0x1400858d8  mov     rcx, [rdi+38h]; pszPath
0x1400858dc  call    cs:__imp_SHCreateItemFromParsingName
0x1400858e2  mov     ebx, eax
0x1400858e4  test    eax, eax
0x1400858e6  js      short loc_1400858F7
0x1400858e8  lea     r9, [rdi+40h]
0x1400858ec  mov     rcx, [rbp+47h+ppv]
0x1400858f0  call    SHLoadPlaylistFromItem
0x1400858f5  mov     ebx, eax
0x1400858f7  lea     rcx, [rbp+47h+ppv]
0x1400858fb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140085900  test    ebx, ebx
0x140085902  js      loc_140085A31
0x140085908  mov     [rbp+47h+ppv], 0
0x140085910  mov     rax, [rdi]
0x140085913  mov     rcx, rdi
0x140085916  mov     rax, [rax+60h]
0x14008591a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008591f  lea     rdx, [rbp+47h+ppv]; struct ICommandText **
0x140085923  mov     rcx, rax; this
0x140085926  call    ?CreateCommand@CShellCommandFactory@@QEBAJPEAPEAUICommandText@@@Z; CShellCommandFactory::CreateCommand(ICommandText * *)
0x14008592b  mov     ebx, eax
0x14008592d  test    eax, eax
0x14008592f  js      loc_140085A27
0x140085935  mov     [rbp+47h+var_90], 0
0x14008593d  mov     [rbp+47h+var_88], 0
0x140085945  mov     [rbp+47h+var_80], 0
0x14008594d  mov     [rbp+47h+var_78], 0
0x140085954  lea     rdx, Password
0x14008595b  lea     rcx, [rbp+47h+var_98]
0x14008595f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140085964  nop
0x140085965  mov     rdx, r12
0x140085968  lea     rcx, [rbp+47h+var_A0]
0x14008596c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140085971  nop
0x140085972  mov     rdx, r15
0x140085975  lea     rcx, [rbp+47h+var_A8]
0x140085979  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14008597e  nop
0x14008597f  mov     rbx, [rbp+47h+ppv]
0x140085983  mov     rax, [rdi]
0x140085986  mov     rcx, rdi
0x140085989  mov     rax, [rax+60h]
0x14008598d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140085992  lea     rdx, [rax+10h]
0x140085996  lea     rax, [rbp+47h+var_98]
0x14008599a  mov     [rsp+100h+var_C0], rax
0x14008599f  mov     [rsp+100h+var_C8], 0
0x1400859a7  mov     [rsp+100h+var_D0], 7
0x1400859af  lea     rax, [rbp+47h+var_A0]
0x1400859b3  mov     qword ptr [rsp+100h+var_D8], rax
0x1400859b8  lea     rax, [rbp+47h+var_A8]
0x1400859bc  mov     [rsp+100h+var_E0], rax
0x1400859c1  mov     r9, rbx
0x1400859c4  mov     r8b, [rbp+47h+arg_20]
0x1400859c8  lea     rcx, [rbp+47h+var_70]
0x1400859cc  call    ??0CShellSearchQuery@@QEAA@PEBVCShellLibraryCache@@_NPEAUICommandText@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@3W4MediaCacheSchema@@K3@Z; CShellSearchQuery::CShellSearchQuery(CShellLibraryCache const *,bool,ICommandText *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,MediaCacheSchema,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x1400859d1  nop
0x1400859d2  lea     rcx, [rbp+47h+var_A8]
0x1400859d6  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400859db  nop
0x1400859dc  lea     rcx, [rbp+47h+var_A0]
0x1400859e0  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400859e5  nop
0x1400859e6  lea     rcx, [rbp+47h+var_98]
0x1400859ea  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400859ef  lea     rdx, [rbp+47h+var_90]
0x1400859f3  lea     rcx, [rbp+47h+var_70]
0x1400859f7  call    ?Execute@CShellSearchQuery@@QEAAJAEAV?$CInterfaceArray@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@@Z; CShellSearchQuery::Execute(ATL::CInterfaceArray<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99> &)
0x1400859fc  mov     ebx, eax
0x1400859fe  test    eax, eax
0x140085a00  js      short loc_140085A13
0x140085a02  lea     r8, [rsi+40h]
0x140085a06  lea     rdx, [rbp+47h+var_90]
0x140085a0a  mov     rcx, rdi
0x140085a0d  call    ?FilterResultSet@CGeneratedPlaylistContainer@@IEAAXAEBV?$CInterfaceArray@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@AEAV23@@Z; CGeneratedPlaylistContainer::FilterResultSet(ATL::CInterfaceArray<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99> const &,ATL::CInterfaceArray<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99> &)
0x140085a12  nop
0x140085a13  lea     rcx, [rbp+47h+var_70]; this
0x140085a17  call    ??1CShellSearchQuery@@QEAA@XZ; CShellSearchQuery::~CShellSearchQuery(void)
0x140085a1c  nop
0x140085a1d  lea     rcx, [rbp+47h+var_90]
0x140085a21  call    ??1?$CAtlArray@V?$CComQIPtr@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>::~CAtlArray<ATL::CComQIPtr<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>,ATL::CComQIPtrElementTraits<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99>>(void)
0x140085a26  nop
0x140085a27  lea     rcx, [rbp+47h+ppv]
0x140085a2b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140085a30  nop
0x140085a31  lea     rcx, ?_ShellLock@CShellLock@@0V1@A; lpCriticalSection
0x140085a38  call    cs:__imp_LeaveCriticalSection
0x140085a3e  test    ebx, ebx
0x140085a40  js      short loc_140085A5C
0x140085a42  lea     rcx, [rsi+18h]; struct IUnknown **
0x140085a46  cmp     [rcx], rdi
0x140085a49  jz      short loc_140085A53
0x140085a4b  mov     rdx, rdi; struct IUnknown *
0x140085a4e  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x140085a53  mov     rax, [rbp+47h+arg_28]
0x140085a57  mov     [rax], rsi
0x140085a5a  jmp     short loc_140085A70
0x140085a5c  test    rsi, rsi
0x140085a5f  jz      short loc_140085A70
0x140085a61  mov     rax, [rsi]
0x140085a64  mov     rcx, rsi
0x140085a67  mov     rax, [rax+10h]
0x140085a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140085a70  lea     rcx, WPP_GLOBAL_Control
0x140085a77  mov     rax, cs:WPP_GLOBAL_Control
0x140085a7e  cmp     rax, rcx
0x140085a81  jz      short loc_140085ABF
0x140085a83  test    byte ptr [rax+1Ch], 2
0x140085a87  jz      short loc_140085ABF
0x140085a89  cmp     byte ptr [rax+19h], 5
0x140085a8d  jb      short loc_140085ABF
0x140085a8f  mov     rax, [rdi]
0x140085a92  mov     rcx, rdi
0x140085a95  mov     rax, [rax+38h]
0x140085a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140085a9e  mov     edx, 1Bh
0x140085aa3  mov     dword ptr [rsp+100h+var_D8], ebx; char
0x140085aa7  mov     [rsp+100h+var_E0], rax; __int64
0x140085aac  mov     r9, r15
0x140085aaf  mov     rcx, cs:WPP_GLOBAL_Control
0x140085ab6  mov     rcx, [rcx+10h]; LoggerHandle
0x140085aba  call    WPP_SF_SSD
0x140085abf  mov     eax, ebx
0x140085ac1  add     rsp, 0D0h
0x140085ac8  pop     r15
0x140085aca  pop     r14
0x140085acc  pop     r12
0x140085ace  pop     rdi
0x140085acf  pop     rsi
0x140085ad0  pop     rbx
0x140085ad1  pop     rbp
0x140085ad2  retn
```
