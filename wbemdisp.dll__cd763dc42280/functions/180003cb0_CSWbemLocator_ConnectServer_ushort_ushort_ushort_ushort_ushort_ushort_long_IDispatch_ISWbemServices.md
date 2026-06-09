# CSWbemLocator::ConnectServer(ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,long,IDispatch *,ISWbemServices * *)

- ea: `0x180003cb0`
- end: `0x180004133`
- name: `?ConnectServer@CSWbemLocator@@UEAAJPEAG00000JPEAUIDispatch@@PEAPEAUISWbemServices@@@Z`
- size: `1155`
- prototype: `int(CSWbemLocator *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int, struct IDispatch *, struct ISWbemServices **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180003cb0`
- `0x1800045c0`
- `0x1800050dc`
- `0x180006300`
- `0x180009c20`
- `0x180012170`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180003f44`
- `OLEAUT32!__imp_SysAllocString` at `0x180003fab`
- `OLEAUT32!__imp_SysAllocString` at `0x1800040fc`
- `OLEAUT32!__imp_SysAllocString` at `0x180003f44`
- `OLEAUT32!__imp_SysAllocString` at `0x180003fab`
- `OLEAUT32!__imp_SysAllocString` at `0x1800040fc`
- `OLEAUT32!__imp_SysFreeString` at `0x180003e22`
- `OLEAUT32!__imp_SysFreeString` at `0x180003fa2`
- `OLEAUT32!__imp_SysFreeString` at `0x180003e22`
- `OLEAUT32!__imp_SysFreeString` at `0x180003fa2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003e54`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003f53`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003e54`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003f53`

## string_xrefs

- `0x180003f3d`: `SWbemServicesEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSWbemLocator::ConnectServer(
        CSWbemLocator *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        int a8,
        struct IDispatch *a9,
        struct ISWbemServices **a10)
{
  int v14; // edi
  __int64 v15; // r12
  char v16; // r13
  unsigned __int16 *v17; // rbp
  OLECHAR *v18; // r15
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 (__fastcall *v21)(__int64, OLECHAR *, unsigned __int16 *); // r11
  const OLECHAR *v22; // r14
  unsigned __int16 *v23; // r10
  char *v25; // rbx
  unsigned __int16 *v26; // rdi
  struct IUnknown *v27; // r12
  CSWbemSecurity *v28; // rax
  unsigned int v29; // edx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 v34; // [rsp+50h] [rbp-88h] BYREF
  __int64 v35; // [rsp+58h] [rbp-80h] BYREF
  struct IUnknown *v36; // [rsp+60h] [rbp-78h]
  struct CWbemLocatorSecurity *v37; // [rsp+68h] [rbp-70h]
  unsigned __int16 *v38; // [rsp+70h] [rbp-68h]
  __int64 v39; // [rsp+78h] [rbp-60h]
  char *v40; // [rsp+80h] [rbp-58h]
  CSWbemSecurity *v41; // [rsp+88h] [rbp-50h]

  ResetLastErrors();
  if ( !a10 )
  {
    v14 = -2147217400;
LABEL_19:
    CDispatchHelp::RaiseException((CSWbemLocator *)((char *)this + 56), v14);
    return (unsigned int)v14;
  }
  v14 = -2147217407;
  if ( !*((_QWORD *)this + 6) || !*((_QWORD *)this + 5) )
    goto LABEL_19;
  v15 = -1;
  if ( !a4 )
    goto LABEL_5;
  v30 = -1;
  do
    ++v30;
  while ( a4[v30] );
  if ( v30 )
    v16 = 0;
  else
LABEL_5:
    v16 = 1;
  v17 = a7;
  if ( a7 )
  {
    v31 = -1;
    do
      ++v31;
    while ( a7[v31] );
  }
  v18 = CSWbemLocator::BuildPath(a2, a3);
  v19 = *((_QWORD *)this + 17);
  v34 = 0;
  v35 = 0;
  if ( v19
    && (*(int (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v19 + 24LL))(
         v19,
         &IID_IWbemContext,
         &IID_IWbemContext,
         &v34) < 0 )
  {
    v34 = 0;
  }
  if ( a9
    && !v34
    && ((__int64 (__fastcall *)(struct IDispatch *, GUID *, __int64 *))a9->lpVtbl->QueryInterface)(
         a9,
         &IID_ISWbemInternalContext,
         &v35) >= 0 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 24LL))(v35, &v34);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v39 = v34;
  v36 = 0;
  v20 = *((_QWORD *)this + 6);
  v21 = *(__int64 (__fastcall **)(__int64, OLECHAR *, unsigned __int16 *))(*(_QWORD *)v20 + 24LL);
  v22 = a6;
  if ( a6 )
  {
    v33 = -1;
    do
      ++v33;
    while ( a6[v33] );
  }
  v23 = 0;
  if ( !v16 )
    v23 = a4;
  v38 = v23;
  v14 = v21(v20, v18, v23);
  if ( !v14 )
  {
    v25 = (char *)CWin32DefaultArena::WbemMemAlloc(0xA8u);
    v40 = v25;
    if ( v25 )
    {
      if ( !a6 )
        goto LABEL_22;
      v32 = -1;
      do
        ++v32;
      while ( a6[v32] );
      if ( !v32 )
LABEL_22:
        v22 = 0;
      v37 = (struct CWbemLocatorSecurity *)*((_QWORD *)this + 5);
      v26 = 0;
      if ( !v16 )
        v26 = a5;
      if ( !a7 )
        goto LABEL_26;
      do
        ++v15;
      while ( a7[v15] );
      if ( !v15 )
LABEL_26:
        v17 = 0;
      v27 = v36;
      *(_QWORD *)v25 = &CSWbemServices::`vftable'{for `ISWbemServicesEx'};
      *((_QWORD *)v25 + 1) = &CSWbemServices::`vftable'{for `IDispatchEx'};
      *((_QWORD *)v25 + 2) = &CSWbemServices::`vftable'{for `ISupportErrorInfo'};
      *((_QWORD *)v25 + 3) = &CSWbemServices::`vftable'{for `ISWbemInternalServices'};
      *((_QWORD *)v25 + 4) = &CSWbemServices::`vftable'{for `IProvideClassInfo'};
      *((_QWORD *)v25 + 5) = 0;
      *((_QWORD *)v25 + 6) = 0;
      *((_QWORD *)v25 + 7) = &CDispatchHelp::`vftable';
      *((_QWORD *)v25 + 10) = 0;
      *((_QWORD *)v25 + 11) = 0;
      *((_QWORD *)v25 + 12) = 0;
      *((_QWORD *)v25 + 8) = 0;
      *((_DWORD *)v25 + 18) = 0;
      *((_QWORD *)v25 + 17) = 0;
      *((_QWORD *)v25 + 18) = 0;
      *((_QWORD *)v25 + 19) = 0;
      *((_DWORD *)v25 + 40) = 0;
      _InterlockedIncrement(&g_cObj);
      *((_QWORD *)v25 + 12) = v25;
      *(GUID *)(v25 + 104) = IID_ISWbemServicesEx;
      *(GUID *)(v25 + 120) = CLSID_SWbemServicesEx;
      *((_QWORD *)v25 + 8) = SysAllocString(L"SWbemServicesEx");
      v28 = (CSWbemSecurity *)CWin32DefaultArena::WbemMemAlloc(0x90u);
      v41 = v28;
      if ( v28 )
        v28 = CSWbemSecurity::CSWbemSecurity(v28, v27, v17, v38, v26, (struct ISWbemSecurity *)v37);
      *((_QWORD *)v25 + 17) = v28;
      if ( v22 )
        *((_QWORD *)v25 + 6) = SysAllocString(v22);
      if ( v18 )
      {
        SysFreeString(*((BSTR *)v25 + 5));
        *((_QWORD *)v25 + 5) = SysAllocString(v18);
      }
    }
    else
    {
      v25 = 0;
    }
    if ( v25 )
    {
      v14 = (**(__int64 (__fastcall ***)(void *, GUID *, struct ISWbemServices **))v25)(v25, &IID_ISWbemServices, a10);
      if ( v14 < 0 )
        CSWbemServices::`scalar deleting destructor'((CSWbemServices *)v25, v29);
    }
    else
    {
      v14 = -2147217402;
    }
    ((void (__fastcall *)(struct IUnknown *))v36->lpVtbl->Release)(v36);
  }
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  SysFreeString(v18);
  if ( v14 < 0 )
    goto LABEL_19;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180003cb0  push    rbx
0x180003cb2  push    rbp
0x180003cb3  push    rsi
0x180003cb4  push    rdi
0x180003cb5  push    r12
0x180003cb7  push    r13
0x180003cb9  push    r14
0x180003cbb  push    r15
0x180003cbd  sub     rsp, 98h
0x180003cc4  mov     rbx, r9
0x180003cc7  mov     r14, r8
0x180003cca  mov     r15, rdx
0x180003ccd  mov     rsi, rcx
0x180003cd0  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x180003cd5  cmp     [rsp+0D8h+arg_48], 0
0x180003cde  jz      loc_18000407A
0x180003ce4  mov     edi, 80041001h
0x180003ce9  cmp     qword ptr [rsi+30h], 0
0x180003cee  jz      loc_180003E42
0x180003cf4  cmp     qword ptr [rsi+28h], 0
0x180003cf9  jz      loc_180003E42
0x180003cff  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180003d06  test    rbx, rbx
0x180003d09  jnz     loc_180003FFF
0x180003d0f  mov     r13b, 1
0x180003d12  mov     rbp, [rsp+0D8h+arg_30]
0x180003d1a  test    rbp, rbp
0x180003d1d  jnz     loc_18000401D
0x180003d23  xor     dil, dil
0x180003d26  mov     rdx, r14; OLECHAR *
0x180003d29  mov     rcx, r15; psz
0x180003d2c  call    ?BuildPath@CSWbemLocator@@CAPEAGPEAG0@Z; CSWbemLocator::BuildPath(ushort *,ushort *)
0x180003d31  mov     r15, rax
0x180003d34  mov     rcx, [rsi+88h]
0x180003d3b  xor     r9d, r9d
0x180003d3e  mov     [rsp+0D8h+var_88], r9
0x180003d43  mov     [rsp+0D8h+var_80], r9
0x180003d48  test    rcx, rcx
0x180003d4b  jz      short loc_180003D78
0x180003d4d  mov     rax, [rcx]
0x180003d50  lea     r9, [rsp+0D8h+var_88]
0x180003d55  lea     r8, IID_IWbemContext
0x180003d5c  lea     rdx, IID_IWbemContext
0x180003d63  mov     rax, [rax+18h]
0x180003d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d6c  xor     r9d, r9d
0x180003d6f  test    eax, eax
0x180003d71  jns     short loc_180003D78
0x180003d73  mov     [rsp+0D8h+var_88], r9
0x180003d78  mov     rcx, [rsp+0D8h+arg_40]
0x180003d80  test    rcx, rcx
0x180003d83  jnz     loc_180004084
0x180003d89  mov     rdx, [rsp+0D8h+var_88]
0x180003d8e  mov     [rsp+0D8h+var_60], rdx
0x180003d93  mov     [rsp+0D8h+var_78], r9
0x180003d98  mov     rcx, [rsi+30h]
0x180003d9c  mov     rax, [rcx]
0x180003d9f  mov     r11, [rax+18h]
0x180003da3  mov     rax, r9
0x180003da6  test    dil, dil
0x180003da9  cmovz   rax, rbp
0x180003dad  mov     r14, [rsp+0D8h+arg_28]
0x180003db5  test    r14, r14
0x180003db8  jnz     loc_1800040DA
0x180003dbe  mov     r8, r9
0x180003dc1  mov     r10, r9
0x180003dc4  test    r13b, r13b
0x180003dc7  cmovz   r10, rbx
0x180003dcb  mov     [rsp+0D8h+var_68], r10
0x180003dd0  cmovz   r9, [rsp+0D8h+arg_20]
0x180003dd9  lea     rbx, [rsp+0D8h+var_78]
0x180003dde  mov     [rsp+0D8h+var_98], rbx
0x180003de3  mov     [rsp+0D8h+var_A0], rdx
0x180003de8  mov     [rsp+0D8h+var_A8], rax
0x180003ded  mov     eax, [rsp+0D8h+arg_38]
0x180003df4  mov     dword ptr [rsp+0D8h+var_B0], eax
0x180003df8  mov     [rsp+0D8h+var_B8], r8
0x180003dfd  mov     r8, r10
0x180003e00  mov     rdx, r15
0x180003e03  mov     rax, r11
0x180003e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e0b  mov     edi, eax
0x180003e0d  test    eax, eax
0x180003e0f  jz      short loc_180003E4F
0x180003e11  mov     rcx, [rsp+0D8h+var_60]
0x180003e16  test    rcx, rcx
0x180003e19  jnz     loc_180004122
0x180003e1f  mov     rcx, r15; bstrString
0x180003e22  call    cs:__imp_SysFreeString
0x180003e28  test    edi, edi
0x180003e2a  js      short loc_180003E42
0x180003e2c  mov     eax, edi
0x180003e2e  add     rsp, 98h
0x180003e35  pop     r15
0x180003e37  pop     r14
0x180003e39  pop     r13
0x180003e3b  pop     r12
0x180003e3d  pop     rdi
0x180003e3e  pop     rsi
0x180003e3f  pop     rbp
0x180003e40  pop     rbx
0x180003e41  retn
0x180003e42  lea     rcx, [rsi+38h]; this
0x180003e46  mov     edx, edi; int
0x180003e48  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x180003e4d  jmp     short loc_180003E2C
0x180003e4f  mov     ecx, 0A8h
0x180003e54  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180003e5a  mov     rbx, rax
0x180003e5d  mov     [rsp+0D8h+var_58], rax
0x180003e65  test    rax, rax
0x180003e68  jz      loc_180003FFB
0x180003e6e  test    r14, r14
0x180003e71  jnz     loc_18000403C
0x180003e77  xor     ecx, ecx
0x180003e79  mov     r14d, ecx
0x180003e7c  mov     rax, [rsi+28h]
0x180003e80  mov     [rsp+0D8h+var_70], rax
0x180003e85  mov     rdi, rcx
0x180003e88  test    r13b, r13b
0x180003e8b  cmovz   rdi, [rsp+0D8h+arg_20]
0x180003e94  test    rbp, rbp
0x180003e97  jnz     loc_180004060
0x180003e9d  mov     rbp, rcx
0x180003ea0  mov     r12, [rsp+0D8h+var_78]
0x180003ea5  lea     rax, ??_7CSWbemServices@@6BISWbemServicesEx@@@; const CSWbemServices::`vftable'{for `ISWbemServicesEx'}
0x180003eac  mov     [rbx], rax
0x180003eaf  lea     rax, ??_7CSWbemServices@@6BIDispatchEx@@@; const CSWbemServices::`vftable'{for `IDispatchEx'}
0x180003eb6  mov     [rbx+8], rax
0x180003eba  lea     rax, ??_7CSWbemServices@@6BISupportErrorInfo@@@; const CSWbemServices::`vftable'{for `ISupportErrorInfo'}
0x180003ec1  mov     [rbx+10h], rax
0x180003ec5  lea     rax, ??_7CSWbemServices@@6BISWbemInternalServices@@@; const CSWbemServices::`vftable'{for `ISWbemInternalServices'}
0x180003ecc  mov     [rbx+18h], rax
0x180003ed0  lea     rax, ??_7CSWbemServices@@6BIProvideClassInfo@@@; const CSWbemServices::`vftable'{for `IProvideClassInfo'}
0x180003ed7  mov     [rbx+20h], rax
0x180003edb  mov     [rbx+28h], rcx
0x180003edf  mov     [rbx+30h], rcx
0x180003ee3  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x180003eea  mov     [rbx+38h], rax
0x180003eee  mov     [rbx+50h], rcx
0x180003ef2  mov     [rbx+58h], rcx
0x180003ef6  mov     [rbx+60h], rcx
0x180003efa  mov     [rbx+40h], rcx
0x180003efe  mov     [rbx+48h], ecx
0x180003f01  mov     [rbx+88h], rcx
0x180003f08  mov     [rbx+90h], rcx
0x180003f0f  mov     [rbx+98h], rcx
0x180003f16  mov     [rbx+0A0h], ecx
0x180003f1c  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180003f23  movups  xmm1, xmmword ptr cs:CLSID_SWbemServicesEx.Data1
0x180003f2a  movups  xmm0, xmmword ptr cs:IID_ISWbemServicesEx.Data1
0x180003f31  mov     [rbx+60h], rbx
0x180003f35  movups  xmmword ptr [rbx+68h], xmm0
0x180003f39  movups  xmmword ptr [rbx+78h], xmm1
0x180003f3d  lea     rcx, aSwbemservicese; "SWbemServicesEx"
0x180003f44  call    cs:__imp_SysAllocString
0x180003f4a  mov     [rbx+40h], rax
0x180003f4e  mov     ecx, 90h
0x180003f53  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180003f59  mov     [rsp+0D8h+var_50], rax
0x180003f61  test    rax, rax
0x180003f64  jz      short loc_180003F89
0x180003f66  mov     rcx, [rsp+0D8h+var_70]
0x180003f6b  mov     [rsp+0D8h+var_B0], rcx; struct CWbemLocatorSecurity *
0x180003f70  mov     [rsp+0D8h+var_B8], rdi; unsigned __int16 *
0x180003f75  mov     r9, [rsp+0D8h+var_68]; unsigned __int16 *
0x180003f7a  mov     r8, rbp; unsigned __int16 *
0x180003f7d  mov     rdx, r12; struct IUnknown *
0x180003f80  mov     rcx, rax; this
0x180003f83  call    ??0CSWbemSecurity@@QEAA@PEAUIUnknown@@PEAG11PEAVCWbemLocatorSecurity@@@Z; CSWbemSecurity::CSWbemSecurity(IUnknown *,ushort *,ushort *,ushort *,CWbemLocatorSecurity *)
0x180003f88  nop
0x180003f89  mov     [rbx+88h], rax
0x180003f90  test    r14, r14
0x180003f93  jnz     loc_1800040F9
0x180003f99  test    r15, r15
0x180003f9c  jz      short loc_180003FB5
0x180003f9e  mov     rcx, [rbx+28h]; bstrString
0x180003fa2  call    cs:__imp_SysFreeString
0x180003fa8  mov     rcx, r15; psz
0x180003fab  call    cs:__imp_SysAllocString
0x180003fb1  mov     [rbx+28h], rax
0x180003fb5  test    rbx, rbx
0x180003fb8  jz      loc_18000410B
0x180003fbe  mov     rax, [rbx]
0x180003fc1  mov     r8, [rsp+0D8h+arg_48]
0x180003fc9  lea     rdx, IID_ISWbemServices
0x180003fd0  mov     rcx, rbx
0x180003fd3  mov     rax, [rax]
0x180003fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fdb  mov     edi, eax
0x180003fdd  test    eax, eax
0x180003fdf  js      loc_180004115
0x180003fe5  mov     rcx, [rsp+0D8h+var_78]
0x180003fea  mov     rax, [rcx]
0x180003fed  mov     rax, [rax+10h]
0x180003ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ff6  jmp     loc_180003E11
0x180003ffb  xor     ebx, ebx
0x180003ffd  jmp     short loc_180003FB5
0x180003fff  mov     rax, r12
0x180004002  inc     rax
0x180004005  cmp     word ptr [rbx+rax*2], 0
0x18000400a  jnz     short loc_180004002
0x18000400c  test    rax, rax
0x18000400f  jz      loc_180003D0F
0x180004015  xor     r13b, r13b
0x180004018  jmp     loc_180003D12
0x18000401d  mov     rax, r12
0x180004020  inc     rax
0x180004023  cmp     word ptr [rbp+rax*2+0], 0
0x180004029  jnz     short loc_180004020
0x18000402b  test    rax, rax
0x18000402e  jnz     loc_180003D23
0x180004034  mov     dil, 1
0x180004037  jmp     loc_180003D26
0x18000403c  mov     rax, r12
0x18000403f  nop
0x180004040  inc     rax
0x180004043  cmp     word ptr [r14+rax*2], 0
0x180004049  jnz     short loc_180004040
0x18000404b  test    rax, rax
0x18000404e  jz      loc_180003E77
0x180004054  xor     ecx, ecx
0x180004056  jmp     loc_180003E7C
0x180004060  inc     r12
0x180004063  cmp     word ptr [rbp+r12*2+0], 0
0x18000406a  jnz     short loc_180004060
0x18000406c  test    r12, r12
0x18000406f  jnz     loc_180003EA0
0x180004075  jmp     loc_180003E9D
0x18000407a  mov     edi, 80041008h
0x18000407f  jmp     loc_180003E42
0x180004084  cmp     [rsp+0D8h+var_88], 0
0x18000408a  jnz     loc_180003D89
0x180004090  mov     rax, [rcx]
0x180004093  lea     r8, [rsp+0D8h+var_80]
0x180004098  lea     rdx, IID_ISWbemInternalContext
0x18000409f  mov     rax, [rax]
0x1800040a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040a7  test    eax, eax
0x1800040a9  js      short loc_1800040D2
0x1800040ab  mov     rcx, [rsp+0D8h+var_80]
0x1800040b0  mov     rax, [rcx]
0x1800040b3  lea     rdx, [rsp+0D8h+var_88]
0x1800040b8  mov     rax, [rax+18h]
0x1800040bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040c1  mov     rcx, [rsp+0D8h+var_80]
0x1800040c6  mov     rax, [rcx]
0x1800040c9  mov     rax, [rax+10h]
0x1800040cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040d2  xor     r9d, r9d
0x1800040d5  jmp     loc_180003D89
0x1800040da  mov     r8, r12
0x1800040dd  inc     r8
0x1800040e0  cmp     word ptr [r14+r8*2], 0
0x1800040e6  jnz     short loc_1800040DD
0x1800040e8  test    r8, r8
0x1800040eb  mov     r8, r14
0x1800040ee  jnz     loc_180003DC1
0x1800040f4  jmp     loc_180003DBE
0x1800040f9  mov     rcx, r14; psz
0x1800040fc  call    cs:__imp_SysAllocString
0x180004102  mov     [rbx+30h], rax
0x180004106  jmp     loc_180003F99
0x18000410b  mov     edi, 80041006h
0x180004110  jmp     loc_180003FE5
0x180004115  mov     rcx, rbx; this
0x180004118  call    ??_GCSWbemServices@@QEAAPEAXI@Z; CSWbemServices::`scalar deleting destructor'(uint)
0x18000411d  jmp     loc_180003FE5
0x180004122  mov     rax, [rcx]
0x180004125  mov     rax, [rax+10h]
0x180004129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000412e  jmp     loc_180003E1F
```
