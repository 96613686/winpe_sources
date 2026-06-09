# ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &,bool)

- ea: `0x14004fe34`
- end: `0x14004ff93`
- name: `??$get_bool_or@UValueSet@Collections@Foundation@Windows@winrt@@@details@ValueSetUtils@@YA_NAEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@_N@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140057574`

## callees

- `0x14000a310`
- `0x14000cc7c`
- `0x14004fe34`
- `0x140051a3c`
- `0x140051ab8`
- `0x140052bf8`
- `0x140057804`
- `0x140058254`
- `0x14005be5c`
- `0x14005fcbc`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14004ff29`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14004ff57`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14004ff29`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14004ff57`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(
        _QWORD *a1,
        _QWORD *a2)
{
  void (__fastcall ***v4)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v5; // rbx
  char v6; // bl
  const WCHAR *v7; // rax
  const WCHAR *v8; // rax
  __int64 v10; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v11[5]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v12; // [rsp+88h] [rbp+28h] BYREF
  char v13; // [rsp+98h] [rbp+38h] BYREF

  if ( *a2 )
  {
    v11[0] = *a1;
    if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(
                            a2,
                            v11) )
    {
      v11[0] = *a1;
      v4 = *(void (__fastcall ****)(_QWORD, __int64 *, __int64 *))winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                                                                    a2,
                                                                    &v10,
                                                                    v11);
      v12 = 0;
      if ( v4 )
      {
        (**v4)(v4, winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>, &v12);
        v5 = v12;
      }
      else
      {
        v5 = 0;
      }
      if ( v10 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v10);
      if ( v5 )
      {
        if ( (unsigned int)winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::Type(&v12) == 11 )
        {
          v6 = winrt::impl::unbox_value_type<bool,winrt::Windows::Foundation::IInspectable const &>(&v12);
LABEL_16:
          winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v12);
          return v6;
        }
        if ( (unsigned int)winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::Type(&v12) == 12 )
        {
          winrt::impl::unbox_value_type<winrt::hstring,winrt::Windows::Foundation::IInspectable const &>(&v13, &v12);
          v7 = winrt::hstring::c_str((winrt::hstring *)&v13);
          v6 = 1;
          if ( CompareStringOrdinal(v7, -1, L"true", -1, 1) == 2 )
          {
            std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v13);
            goto LABEL_16;
          }
          v8 = winrt::hstring::c_str((winrt::hstring *)&v13);
          if ( CompareStringOrdinal(v8, -1, L"false", -1, 1) == 2 )
          {
            std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v13);
            v6 = 0;
            goto LABEL_16;
          }
          std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v13);
        }
      }
      winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v12);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14004fe34  push    rbp
0x14004fe36  push    rbx
0x14004fe37  push    rdi
0x14004fe38  mov     rbp, rsp
0x14004fe3b  sub     rsp, 60h
0x14004fe3f  mov     rbx, rdx
0x14004fe42  mov     rdi, rcx
0x14004fe45  cmp     qword ptr [rdx], 0
0x14004fe49  jz      loc_14004FF89
0x14004fe4f  mov     rax, [rcx]
0x14004fe52  mov     [rbp+var_28], rax
0x14004fe56  lea     rdx, [rbp+var_28]
0x14004fe5a  mov     rcx, rbx
0x14004fe5d  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(winrt::param::hstring const &)
0x14004fe62  test    al, al
0x14004fe64  jz      loc_14004FF89
0x14004fe6a  mov     rax, [rdi]
0x14004fe6d  mov     [rbp+var_28], rax
0x14004fe71  lea     r8, [rbp+var_28]
0x14004fe75  lea     rdx, [rbp+var_30]
0x14004fe79  mov     rcx, rbx
0x14004fe7c  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x14004fe81  mov     rcx, [rax]
0x14004fe84  mov     [rbp+arg_8], 0
0x14004fe8c  test    rcx, rcx
0x14004fe8f  jnz     short loc_14004FE95
0x14004fe91  xor     ebx, ebx
0x14004fe93  jmp     short loc_14004FEB3
0x14004fe95  mov     rax, [rcx]
0x14004fe98  lea     r8, [rbp+arg_8]
0x14004fe9c  lea     rdx, ??$guid_v@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>
0x14004fea3  mov     rax, [rax]
0x14004fea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004feab  mov     rbx, [rbp+arg_8]
0x14004feaf  mov     [rbp+arg_8], rbx
0x14004feb3  cmp     [rbp+var_30], 0
0x14004feb8  jz      short loc_14004FEC3
0x14004feba  lea     rcx, [rbp+var_30]
0x14004febe  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14004fec3  test    rbx, rbx
0x14004fec6  jz      loc_14004FF80
0x14004fecc  lea     rcx, [rbp+arg_8]
0x14004fed0  call    ?Type@?$consume_Windows_Foundation_IPropertyValue@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::Type(void)
0x14004fed5  lea     rcx, [rbp+arg_8]
0x14004fed9  cmp     eax, 0Bh
0x14004fedc  jnz     short loc_14004FEEA
0x14004fede  call    ??$unbox_value_type@_NAEBUIInspectable@Foundation@Windows@winrt@@@impl@winrt@@YA_NAEBUIInspectable@Foundation@Windows@1@@Z; winrt::impl::unbox_value_type<bool,winrt::Windows::Foundation::IInspectable const &>(winrt::Windows::Foundation::IInspectable const &)
0x14004fee3  mov     bl, al
0x14004fee5  jmp     loc_14004FF6D
0x14004feea  call    ?Type@?$consume_Windows_Foundation_IPropertyValue@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::Type(void)
0x14004feef  cmp     eax, 0Ch
0x14004fef2  jnz     loc_14004FF80
0x14004fef8  lea     rdx, [rbp+arg_8]
0x14004fefc  lea     rcx, [rbp+arg_18]
0x14004ff00  call    ??$unbox_value_type@Uhstring@winrt@@AEBUIInspectable@Foundation@Windows@2@@impl@winrt@@YA?AUhstring@1@AEBUIInspectable@Foundation@Windows@1@@Z; winrt::impl::unbox_value_type<winrt::hstring,winrt::Windows::Foundation::IInspectable const &>(winrt::Windows::Foundation::IInspectable const &)
0x14004ff05  lea     rcx, [rbp+arg_18]; this
0x14004ff09  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x14004ff0e  mov     rcx, rax; lpString1
0x14004ff11  mov     ebx, 1
0x14004ff16  mov     [rsp+60h+bIgnoreCase], ebx; bIgnoreCase
0x14004ff1a  or      edi, 0FFFFFFFFh
0x14004ff1d  mov     r9d, edi; cchCount2
0x14004ff20  lea     r8, String2; "true"
0x14004ff27  mov     edx, edi; cchCount1
0x14004ff29  call    cs:__imp_CompareStringOrdinal
0x14004ff2f  lea     rcx, [rbp+arg_18]; this
0x14004ff33  cmp     eax, 2
0x14004ff36  jnz     short loc_14004FF3F
0x14004ff38  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x14004ff3d  jmp     short loc_14004FF6D
0x14004ff3f  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x14004ff44  mov     rcx, rax; lpString1
0x14004ff47  mov     [rsp+60h+bIgnoreCase], ebx; bIgnoreCase
0x14004ff4b  mov     r9d, edi; cchCount2
0x14004ff4e  lea     r8, aFalse_0; "false"
0x14004ff55  mov     edx, edi; cchCount1
0x14004ff57  call    cs:__imp_CompareStringOrdinal
0x14004ff5d  lea     rcx, [rbp+arg_18]
0x14004ff61  cmp     eax, 2
0x14004ff64  jnz     short loc_14004FF7A
0x14004ff66  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x14004ff6b  xor     bl, bl
0x14004ff6d  lea     rcx, [rbp+arg_8]; this
0x14004ff71  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14004ff76  mov     al, bl
0x14004ff78  jmp     short loc_14004FF8B
0x14004ff7a  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x14004ff7f  nop
0x14004ff80  lea     rcx, [rbp+arg_8]; this
0x14004ff84  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14004ff89  xor     al, al
0x14004ff8b  add     rsp, 60h
0x14004ff8f  pop     rdi
0x14004ff90  pop     rbx
0x14004ff91  pop     rbp
0x14004ff92  retn
```
