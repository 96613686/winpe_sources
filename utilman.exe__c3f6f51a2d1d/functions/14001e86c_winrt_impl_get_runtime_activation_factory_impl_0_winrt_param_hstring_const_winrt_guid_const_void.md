# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x14001e86c`
- end: `0x14001eb25`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `697`
- prototype: ``
- caller_count: `7`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001e66c`
- `0x140023e7c`
- `0x140023ee0`
- `0x140023f44`
- `0x140023fa8`
- `0x14002400c`
- `0x140024070`

## callees

- `0x14000213c`
- `0x140002480`
- `0x1400032f8`
- `0x140003304`
- `0x140003470`
- `0x140003551`
- `0x140003569`
- `0x140003581`
- `0x140009ee0`
- `0x14001e288`
- `0x14001e40c`
- `0x14001e86c`
- `0x140022d84`
- `0x140022e08`
- `0x1400232fc`
- `0x140029010`

## string_xrefs

- `0x14001e8d4`: `combase.dll`
- `0x14001ea60`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // edi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  const unsigned __int16 *v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rdx
  unsigned __int64 v17; // r8
  __int64 v18; // r14
  unsigned __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 last_trivial_2; // rax
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  const WCHAR *v27; // rax
  HMODULE v28; // rbx
  FARPROC v29; // rax
  bool v30; // zf
  unsigned int (__fastcall ***v32)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  __int128 Src; // [rsp+40h] [rbp-38h] BYREF
  __int64 v35; // [rsp+50h] [rbp-28h]
  __int64 v36; // [rsp+58h] [rbp-20h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, __int64))winrt_activation_handler)(v8, a3, a4);
    return a1;
  }
  ActivationFactory_0 = RoGetActivationFactory_0(v8, a3, a4);
  if ( ActivationFactory_0 == -2147221008 )
  {
    Library = LoadLibraryExW_0(L"combase.dll", 0, 0x1000u);
    ProcAddress = WINRT_IMPL_GetProcAddress(Library, "CoIncrementMTAUsage");
    if ( !ProcAddress )
    {
      *a1 = -2147221008;
      return a1;
    }
    v32 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v32);
    ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  Src = 0;
  v35 = 0;
  v36 = 0;
  v12 = *a2;
  if ( *a2 )
  {
    v13 = *(const unsigned __int16 **)(v12 + 16);
    v14 = *(unsigned int *)(v12 + 4);
  }
  else
  {
    v13 = &qword_14002C590;
    v14 = 0;
  }
  std::wstring::_Construct<1,unsigned short const *>(&Src, v13, v14);
  while ( 1 )
  {
    do
    {
      v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Src, v35, -1);
      v18 = v15;
      if ( !v16 )
        goto LABEL_31;
      v19 = v16 - 1;
      if ( v16 - 1 >= v17 )
        v19 = v17;
      v20 = v15 + 2 + 2 * v19;
      last_trivial_2 = _std_find_last_trivial_2(v15, v20, 46);
      if ( last_trivial_2 == v20 || (v22 = (last_trivial_2 - v18) >> 1, v22 == -1) )
      {
LABEL_31:
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        std::wstring::_Tidy_deallocate(&Src);
        v30 = pperrinfo == 0;
        goto LABEL_32;
      }
      std::wstring::resize(&Src, v22);
      v23 = v35;
      if ( (unsigned __int64)(v36 - v35) < 4 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          &Src,
          4);
      }
      else
      {
        v35 += 4;
        v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Src, v35, v23);
        *(_QWORD *)(v24 + 2 * v26) = 0x6C006C0064002ELL;
        *(_WORD *)(v24 + 2 * v25) = 0;
      }
      v27 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Src, v25, v26);
      v28 = LoadLibraryExW_0(v27, 0, 0x1000u);
      std::wstring::resize(&Src, v35 - 4);
    }
    while ( !v28 );
    v29 = WINRT_IMPL_GetProcAddress(v28, "DllGetActivationFactory");
    if ( v29 )
      break;
LABEL_27:
    WINRT_IMPL_FreeLibrary(v28);
  }
  v32 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v29)(*a2, &v32)
    || (**v32)(v32, a3, a4) )
  {
    if ( v32 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v32);
    goto LABEL_27;
  }
  *a1 = 0;
  if ( v32 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v32);
  std::wstring::_Tidy_deallocate(&Src);
  v30 = pperrinfo == 0;
LABEL_32:
  if ( !v30 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x14001e86c  push    rbp
0x14001e86e  push    rbx
0x14001e86f  push    rsi
0x14001e870  push    rdi
0x14001e871  push    r12
0x14001e873  push    r13
0x14001e875  push    r14
0x14001e877  push    r15
0x14001e879  mov     rbp, rsp
0x14001e87c  sub     rsp, 78h
0x14001e880  mov     rax, cs:__security_cookie
0x14001e887  xor     rax, rsp
0x14001e88a  mov     [rbp+var_18], rax
0x14001e88e  mov     r13, r9
0x14001e891  mov     r12, r8
0x14001e894  mov     r15, rdx
0x14001e897  mov     rsi, rcx
0x14001e89a  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x14001e8a1  xor     r14d, r14d
0x14001e8a4  mov     r8, r9
0x14001e8a7  mov     rdx, r12
0x14001e8aa  mov     rcx, [r15]
0x14001e8ad  test    rax, rax
0x14001e8b0  jz      short loc_14001E8BE
0x14001e8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e8b7  mov     [rsi], eax
0x14001e8b9  jmp     loc_14001EB04
0x14001e8be  call    RoGetActivationFactory_0
0x14001e8c3  mov     edi, eax
0x14001e8c5  cmp     eax, 800401F0h
0x14001e8ca  jnz     short loc_14001E91C
0x14001e8cc  xor     edx, edx; hFile
0x14001e8ce  mov     r8d, 1000h; dwFlags
0x14001e8d4  lea     rcx, LibFileName; "combase.dll"
0x14001e8db  call    LoadLibraryExW_0
0x14001e8e0  lea     rdx, aCoincrementmta; "CoIncrementMTAUsage"
0x14001e8e7  mov     rcx, rax; hModule
0x14001e8ea  call    WINRT_IMPL_GetProcAddress
0x14001e8ef  test    rax, rax
0x14001e8f2  jnz     short loc_14001E8FF
0x14001e8f4  mov     dword ptr [rsi], 800401F0h
0x14001e8fa  jmp     loc_14001EB04
0x14001e8ff  mov     [rbp+var_48], r14
0x14001e903  lea     rcx, [rbp+var_48]
0x14001e907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e90c  mov     r8, r13
0x14001e90f  mov     rdx, r12
0x14001e912  mov     rcx, [r15]
0x14001e915  call    RoGetActivationFactory_0
0x14001e91a  mov     edi, eax
0x14001e91c  test    edi, edi
0x14001e91e  jnz     short loc_14001E928
0x14001e920  mov     [rsi], r14d
0x14001e923  jmp     loc_14001EB04
0x14001e928  mov     [rbp+pperrinfo], r14
0x14001e92c  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x14001e930  xor     ecx, ecx; dwReserved
0x14001e932  call    GetErrorInfo_0
0x14001e937  xorps   xmm0, xmm0
0x14001e93a  movups  [rbp+Src], xmm0
0x14001e93e  mov     [rbp+var_28], r14
0x14001e942  mov     [rbp+var_20], r14
0x14001e946  mov     rax, [r15]
0x14001e949  test    rax, rax
0x14001e94c  jz      short loc_14001E958
0x14001e94e  mov     rdx, [rax+10h]
0x14001e952  mov     r8d, [rax+4]
0x14001e956  jmp     short loc_14001E962
0x14001e958  lea     rdx, qword_14002C590
0x14001e95f  mov     r8, r14
0x14001e962  lea     rcx, [rbp+Src]
0x14001e966  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001e96b  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001e96f  mov     rdx, [rbp+var_28]
0x14001e973  lea     rcx, [rbp+Src]
0x14001e977  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14001e97c  mov     r14, rax
0x14001e97f  test    rdx, rdx
0x14001e982  jz      loc_14001EADE
0x14001e988  lea     rcx, [rdx-1]
0x14001e98c  cmp     rcx, r8
0x14001e98f  cmovnb  rcx, r8
0x14001e993  add     rax, 2
0x14001e997  lea     rbx, [rax+rcx*2]
0x14001e99b  mov     r8d, 2Eh ; '.'
0x14001e9a1  mov     rdx, rbx
0x14001e9a4  mov     rcx, r14
0x14001e9a7  call    __std_find_last_trivial_2
0x14001e9ac  cmp     rax, rbx
0x14001e9af  jz      loc_14001EADE
0x14001e9b5  sub     rax, r14
0x14001e9b8  sar     rax, 1
0x14001e9bb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001e9bf  jz      loc_14001EADE
0x14001e9c5  mov     rdx, rax
0x14001e9c8  lea     rcx, [rbp+Src]
0x14001e9cc  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14001e9d1  mov     r8, [rbp+var_28]
0x14001e9d5  mov     rax, [rbp+var_20]
0x14001e9d9  sub     rax, r8
0x14001e9dc  mov     ecx, 4
0x14001e9e1  cmp     rax, rcx
0x14001e9e4  jb      short loc_14001EA0F
0x14001e9e6  lea     rdx, [r8+4]
0x14001e9ea  mov     [rbp+var_28], rdx
0x14001e9ee  lea     rcx, [rbp+Src]
0x14001e9f2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14001e9f7  mov     rcx, 6C006C0064002Eh
0x14001ea01  mov     [rax+r8*2], rcx
0x14001ea05  xor     r14d, r14d
0x14001ea08  mov     [rax+rdx*2], r14w
0x14001ea0d  jmp     short loc_14001EA23
0x14001ea0f  mov     [rsp+78h+var_58], rcx; __int64
0x14001ea14  mov     rdx, rcx
0x14001ea17  lea     rcx, [rbp+Src]; Src
0x14001ea1b  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x14001ea20  xor     r14d, r14d
0x14001ea23  lea     rcx, [rbp+Src]
0x14001ea27  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14001ea2c  mov     rcx, rax; lpLibFileName
0x14001ea2f  xor     edx, edx; hFile
0x14001ea31  mov     r8d, 1000h; dwFlags
0x14001ea37  call    LoadLibraryExW_0
0x14001ea3c  mov     rbx, rax
0x14001ea3f  mov     rdx, [rbp+var_28]
0x14001ea43  add     rdx, 0FFFFFFFFFFFFFFFCh
0x14001ea47  lea     rcx, [rbp+Src]
0x14001ea4b  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x14001ea50  test    rbx, rbx
0x14001ea53  mov     r8, 0FFFFFFFFFFFFFFFFh
0x14001ea5a  jz      loc_14001E96F
0x14001ea60  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x14001ea67  mov     rcx, rbx; hModule
0x14001ea6a  call    WINRT_IMPL_GetProcAddress
0x14001ea6f  test    rax, rax
0x14001ea72  jz      short loc_14001EAB0
0x14001ea74  mov     [rbp+var_48], r14
0x14001ea78  lea     rdx, [rbp+var_48]
0x14001ea7c  mov     rcx, [r15]
0x14001ea7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ea84  test    eax, eax
0x14001ea86  jnz     short loc_14001EAA1
0x14001ea88  mov     rcx, [rbp+var_48]
0x14001ea8c  mov     rax, [rcx]
0x14001ea8f  mov     r8, r13
0x14001ea92  mov     rdx, r12
0x14001ea95  mov     rax, [rax]
0x14001ea98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ea9d  test    eax, eax
0x14001ea9f  jz      short loc_14001EABD
0x14001eaa1  cmp     [rbp+var_48], r14
0x14001eaa5  jz      short loc_14001EAB0
0x14001eaa7  lea     rcx, [rbp+var_48]
0x14001eaab  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14001eab0  mov     rcx, rbx; hLibModule
0x14001eab3  call    WINRT_IMPL_FreeLibrary
0x14001eab8  jmp     loc_14001E96B
0x14001eabd  mov     [rsi], r14d
0x14001eac0  cmp     [rbp+var_48], r14
0x14001eac4  jz      short loc_14001EACF
0x14001eac6  lea     rcx, [rbp+var_48]
0x14001eaca  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14001eacf  lea     rcx, [rbp+Src]
0x14001ead3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001ead8  cmp     [rbp+pperrinfo], r14
0x14001eadc  jmp     short loc_14001EAF9
0x14001eade  mov     rdx, [rbp+pperrinfo]; perrinfo
0x14001eae2  xor     ecx, ecx; dwReserved
0x14001eae4  call    SetErrorInfo_0
0x14001eae9  mov     [rsi], edi
0x14001eaeb  lea     rcx, [rbp+Src]
0x14001eaef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001eaf4  cmp     [rbp+pperrinfo], 0
0x14001eaf9  jz      short loc_14001EB04
0x14001eafb  lea     rcx, [rbp+pperrinfo]
0x14001eaff  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14001eb04  mov     rax, rsi
0x14001eb07  mov     rcx, [rbp+var_18]
0x14001eb0b  xor     rcx, rsp; StackCookie
0x14001eb0e  call    __security_check_cookie
0x14001eb13  add     rsp, 78h
0x14001eb17  pop     r15
0x14001eb19  pop     r14
0x14001eb1b  pop     r13
0x14001eb1d  pop     r12
0x14001eb1f  pop     rdi
0x14001eb20  pop     rsi
0x14001eb21  pop     rbx
0x14001eb22  pop     rbp
0x14001eb23  retn
```
