# MsxmlDomElement::GetSingleAttribute(wchar_t const *)

- ea: `0x140012710`
- end: `0x1400128e2`
- name: `?GetSingleAttribute@MsxmlDomElement@@UEAA?AV?$AutoRef@VAbstractDomAttribute@@@wmi@@PEB_W@Z`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140002bd0`
- `0x140011570`
- `0x14001159c`
- `0x140012710`
- `0x140022cec`
- `0x14002f6c8`
- `0x140031810`
- `0x140034010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140012731`
- `OLEAUT32!__imp_SysAllocString` at `0x140012731`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall MsxmlDomElement::GetSingleAttribute(__int64 a1, _QWORD *a2, const OLECHAR *a3)
{
  BSTR v5; // rax
  const char *v6; // r8
  int v7; // ebx
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  __int64 v10; // rdi
  _DWORD *v12; // [rsp+28h] [rbp-38h] BYREF
  BSTR v13; // [rsp+30h] [rbp-30h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+38h] [rbp-28h] BYREF
  int v15; // [rsp+50h] [rbp-10h]
  __int64 v16; // [rsp+54h] [rbp-Ch]
  char v17; // [rsp+5Ch] [rbp-4h]
  __int64 v18; // [rsp+98h] [rbp+38h] BYREF

  v5 = SysAllocString(a3);
  v13 = v5;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_fda289614a233b29151e0c0c410d9667_Traceguids, 2147942414LL);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x8007000E, v6, 95);
    throw (EvtException *)pExceptionObject;
  }
  v18 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, BSTR, __int64 *))(**(_QWORD **)(a1 + 32) + 376LL))(
         *(_QWORD *)(a1 + 32),
         v5,
         &v18);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_fda289614a233b29151e0c0c410d9667_Traceguids,
        (unsigned int)v7);
    }
    pExceptionObject[0] = word_14003838A;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v15 = v7;
    v16 = -1;
    v17 = 0;
    throw (EvtException *)pExceptionObject;
  }
  if ( v7 || (v8 = operator new(0x28u), v9 = v8, (v12 = v8) == 0) )
  {
    *a2 = 0;
  }
  else
  {
    v10 = v18;
    v18 = 0;
    v12 = (_DWORD *)v10;
    *(_QWORD *)v8 = &wmi::RefBase::`vftable';
    v8[2] = 0;
    *(_QWORD *)v8 = &MsxmlDomAttribute::`vftable';
    *((_QWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 3) = 0;
    *((_QWORD *)v8 + 4) = v10;
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
      winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref((__int64 *)&v12);
    }
    *a2 = v9;
    if ( v9 )
      _InterlockedIncrement(v9 + 2);
  }
  if ( v18 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v18);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v13);
  return a2;
}

```

## disassembly

```asm
0x140012710  mov     [rsp-18h+arg_0], rbx
0x140012715  mov     [rsp-18h+arg_8], rsi
0x14001271a  push    rbp
0x14001271b  push    rdi
0x14001271c  push    r14
0x14001271e  mov     rbp, rsp
0x140012721  sub     rsp, 60h
0x140012725  mov     rsi, rdx
0x140012728  mov     rbx, rcx
0x14001272b  xor     r14d, r14d
0x14001272e  mov     rcx, r8; psz
0x140012731  call    cs:__imp_SysAllocString
0x140012737  mov     [rbp+var_30], rax
0x14001273b  test    rax, rax
0x14001273e  jnz     short loc_1400127A1
0x140012740  lea     rax, WPP_GLOBAL_Control
0x140012747  mov     rcx, cs:WPP_GLOBAL_Control
0x14001274e  cmp     rcx, rax
0x140012751  jz      short loc_14001277C
0x140012753  test    dword ptr [rcx+1Ch], 400000h
0x14001275a  jz      short loc_14001277C
0x14001275c  cmp     byte ptr [rcx+19h], 2
0x140012760  jb      short loc_14001277C
0x140012762  lea     edx, [r14+11h]
0x140012766  mov     r9d, 8007000Eh
0x14001276c  lea     r8, WPP_fda289614a233b29151e0c0c410d9667_Traceguids
0x140012773  mov     rcx, [rcx+10h]
0x140012777  call    WPP_SF_d
0x14001277c  mov     edx, 8007000Eh; unsigned int
0x140012781  mov     r9d, 5Fh ; '_'; int
0x140012787  lea     rcx, [rbp+pExceptionObject]; this
0x14001278b  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140012790  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140012797  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14001279b  call    _CxxThrowException_0
0x1400127a1  mov     [rbp+arg_18], r14
0x1400127a5  mov     rcx, [rbx+20h]
0x1400127a9  mov     rdx, [rcx]
0x1400127ac  mov     r9, [rdx+178h]
0x1400127b3  lea     r8, [rbp+arg_18]
0x1400127b7  mov     rdx, rax
0x1400127ba  mov     rax, r9
0x1400127bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400127c2  mov     ebx, eax
0x1400127c4  test    eax, eax
0x1400127c6  jns     short loc_140012835
0x1400127c8  lea     rax, WPP_GLOBAL_Control
0x1400127cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400127d6  cmp     rcx, rax
0x1400127d9  jz      short loc_140012802
0x1400127db  test    dword ptr [rcx+1Ch], 400000h
0x1400127e2  jz      short loc_140012802
0x1400127e4  cmp     byte ptr [rcx+19h], 2
0x1400127e8  jb      short loc_140012802
0x1400127ea  mov     edx, 12h
0x1400127ef  mov     r9d, ebx
0x1400127f2  lea     r8, WPP_fda289614a233b29151e0c0c410d9667_Traceguids
0x1400127f9  mov     rcx, [rcx+10h]
0x1400127fd  call    WPP_SF_d
0x140012802  lea     rax, word_14003838A
0x140012809  mov     [rbp+pExceptionObject], rax
0x14001280d  mov     [rbp+var_20], r14
0x140012811  mov     [rbp+var_18], r14
0x140012815  mov     [rbp+var_10], ebx
0x140012818  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x140012820  mov     [rbp+var_4], r14b
0x140012824  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001282b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14001282f  call    _CxxThrowException_0
0x140012835  test    ebx, ebx
0x140012837  jnz     short loc_1400128AE
0x140012839  lea     ecx, [rbx+28h]; dwBytes
0x14001283c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012841  mov     rbx, rax
0x140012844  mov     [rbp+var_38], rax
0x140012848  test    rax, rax
0x14001284b  jz      short loc_1400128AE
0x14001284d  mov     rdi, [rbp+arg_18]
0x140012851  mov     [rbp+arg_18], r14
0x140012855  mov     [rbp+var_38], rdi
0x140012859  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x140012860  mov     [rbx], rax
0x140012863  mov     [rbx+8], r14d
0x140012867  lea     rax, ??_7MsxmlDomAttribute@@6B@; const MsxmlDomAttribute::`vftable'
0x14001286e  mov     [rbx], rax
0x140012871  mov     [rbx+10h], r14
0x140012875  mov     [rbx+18h], r14
0x140012879  mov     [rbx+20h], rdi
0x14001287d  test    rdi, rdi
0x140012880  jz      short loc_140012892
0x140012882  mov     rax, [rdi]
0x140012885  mov     rcx, rdi
0x140012888  mov     rax, [rax+8]
0x14001288c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012891  nop
0x140012892  test    rdi, rdi
0x140012895  jz      short loc_1400128A0
0x140012897  lea     rcx, [rbp+var_38]
0x14001289b  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x1400128a0  mov     [rsi], rbx
0x1400128a3  test    rbx, rbx
0x1400128a6  jz      short loc_1400128B1
0x1400128a8  lock inc dword ptr [rbx+8]
0x1400128ac  jmp     short loc_1400128B1
0x1400128ae  mov     [rsi], r14
0x1400128b1  cmp     [rbp+arg_18], r14
0x1400128b5  jz      short loc_1400128C1
0x1400128b7  lea     rcx, [rbp+arg_18]
0x1400128bb  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x1400128c0  nop
0x1400128c1  lea     rcx, [rbp+var_30]
0x1400128c5  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1400128ca  mov     rax, rsi
0x1400128cd  lea     r11, [rsp+60h+var_s0]
0x1400128d2  mov     rbx, [r11+20h]
0x1400128d6  mov     rsi, [r11+28h]
0x1400128da  mov     rsp, r11
0x1400128dd  pop     r14
0x1400128df  pop     rdi
0x1400128e0  pop     rbp
0x1400128e1  retn
```
