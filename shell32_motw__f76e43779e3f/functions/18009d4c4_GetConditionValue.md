# GetConditionValue

- ea: `0x18009d4c4`
- end: `0x18009d740`
- name: `GetConditionValue`
- size: `636`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009c7d0`

## callees

- `0x180026890`
- `0x180038608`
- `0x18003d01c`
- `0x18009d4c4`
- `0x180249490`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d5c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d5dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d636`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d677`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d68c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d69f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d6ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d5c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d5dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d636`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d677`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d68c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d69f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009d6ec`
- `OLEAUT32!__imp_VariantClear` at `0x18009d5b3`
- `OLEAUT32!__imp_VariantClear` at `0x18009d662`
- `OLEAUT32!__imp_VariantClear` at `0x18009d71b`
- `OLEAUT32!__imp_VariantClear` at `0x18009d5b3`
- `OLEAUT32!__imp_VariantClear` at `0x18009d662`
- `OLEAUT32!__imp_VariantClear` at `0x18009d71b`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18009d528`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18009d528`
- `PROPSYS!PSPropertyBag_ReadType` at `0x18009d57c`
- `PROPSYS!PSPropertyBag_ReadType` at `0x18009d57c`
- `PROPSYS!VariantToPropVariant` at `0x18009d599`
- `PROPSYS!VariantToPropVariant` at `0x18009d599`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetConditionValue(unsigned int a1, IPropertyBag *a2, PROPVARIANT *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  WCHAR *v8; // rbx
  HRESULT v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  WCHAR *v12; // rdi
  HRESULT v13; // eax
  unsigned int v14; // esi
  HRESULT v15; // eax
  LPCWSTR v17; // [rsp+20h] [rbp-40h] BYREF
  LPCWSTR propName; // [rsp+28h] [rbp-38h] BYREF
  DWORD value; // [rsp+30h] [rbp-30h] BYREF
  VARIANT var; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  propName = 0;
  v6 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         &propName,
         L"LeafCondition_%d_ValueType",
         a1);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x191,
      (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
      (const char *)(unsigned int)v6,
      (int)v17);
    if ( propName )
      CoTaskMemFree((LPVOID)propName);
    return v7;
  }
  else
  {
    value = 0;
    v8 = (WCHAR *)propName;
    v9 = PSPropertyBag_ReadDWORD(a2, propName, &value);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x194,
        (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
        (const char *)(unsigned int)v9,
        (int)v17);
    }
    else
    {
      v17 = 0;
      v11 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &v17,
              L"LeafCondition_%d_Value",
              a1);
      v10 = v11;
      if ( v11 >= 0 )
      {
        var.vt = 0;
        v12 = (WCHAR *)v17;
        v13 = PSPropertyBag_ReadType(a2, v17, &var, value);
        v14 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x19A,
            (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
            (const char *)(unsigned int)v13,
            (int)v17);
          VariantClear(&var);
          if ( v12 )
            CoTaskMemFree(v12);
          if ( v8 )
            CoTaskMemFree(v8);
        }
        else
        {
          v15 = VariantToPropVariant(&var, a3);
          v14 = v15;
          if ( v15 >= 0 )
          {
            VariantClear(&var);
            if ( v12 )
              CoTaskMemFree(v12);
            if ( v8 )
              CoTaskMemFree(v8);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x19B,
            (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
            (const char *)(unsigned int)v15,
            (int)v17);
          VariantClear(&var);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v17);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&propName);
        }
        return v14;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x197,
        (unsigned int)"shell\\shell32\\libraryqueryfolder.cpp",
        (const char *)(unsigned int)v11,
        (int)v17);
      if ( v17 )
        CoTaskMemFree((LPVOID)v17);
    }
    if ( v8 )
      CoTaskMemFree(v8);
    return v10;
  }
}

```

## disassembly

```asm
0x18009d4c4  mov     [rsp-28h+arg_18], rbx
0x18009d4c9  push    rbp
0x18009d4ca  push    rsi
0x18009d4cb  push    rdi
0x18009d4cc  push    r14
0x18009d4ce  push    r15
0x18009d4d0  mov     rbp, rsp
0x18009d4d3  sub     rsp, 60h
0x18009d4d7  mov     rax, cs:__security_cookie
0x18009d4de  xor     rax, rsp
0x18009d4e1  mov     [rbp+var_10], rax
0x18009d4e5  mov     r15, r8
0x18009d4e8  mov     rsi, rdx
0x18009d4eb  mov     r14d, ecx
0x18009d4ee  mov     [rbp+propName], 0
0x18009d4f6  mov     r8d, ecx
0x18009d4f9  lea     rdx, aLeafconditionD; "LeafCondition_%d_ValueType"
0x18009d500  lea     rcx, [rbp+propName]
0x18009d504  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18009d509  mov     ebx, eax
0x18009d50b  test    eax, eax
0x18009d50d  js      loc_18009D6CA
0x18009d513  mov     [rbp+value], 0
0x18009d51a  lea     r8, [rbp+value]; value
0x18009d51e  mov     rbx, [rbp+propName]
0x18009d522  mov     rdx, rbx; propName
0x18009d525  mov     rcx, rsi; propBag
0x18009d528  call    cs:__imp_PSPropertyBag_ReadDWORD
0x18009d52f  nop     dword ptr [rax+rax+00h]
0x18009d534  mov     edi, eax
0x18009d536  test    eax, eax
0x18009d538  js      loc_18009D6AD
0x18009d53e  mov     [rbp+var_40], 0
0x18009d546  mov     r8d, r14d
0x18009d549  lea     rdx, aLeafconditionD_0; "LeafCondition_%d_Value"
0x18009d550  lea     rcx, [rbp+var_40]
0x18009d554  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18009d559  mov     edi, eax
0x18009d55b  test    eax, eax
0x18009d55d  js      loc_18009D60C
0x18009d563  xor     eax, eax
0x18009d565  mov     word ptr [rbp+var], ax
0x18009d569  movzx   r9d, word ptr [rbp+value]; type
0x18009d56e  lea     r8, [rbp+var]; var
0x18009d572  mov     rdi, [rbp+var_40]
0x18009d576  mov     rdx, rdi; propName
0x18009d579  mov     rcx, rsi; propBag
0x18009d57c  call    cs:__imp_PSPropertyBag_ReadType
0x18009d583  nop     dword ptr [rax+rax+00h]
0x18009d588  mov     esi, eax
0x18009d58a  test    eax, eax
0x18009d58c  js      loc_18009D646
0x18009d592  mov     rdx, r15; pPropVar
0x18009d595  lea     rcx, [rbp+var]; pVar
0x18009d599  call    cs:__imp_VariantToPropVariant
0x18009d5a0  nop     dword ptr [rax+rax+00h]
0x18009d5a5  mov     esi, eax
0x18009d5a7  test    eax, eax
0x18009d5a9  js      loc_18009D6FF
0x18009d5af  lea     rcx, [rbp+var]; pvarg
0x18009d5b3  call    cs:__imp_VariantClear
0x18009d5ba  nop     dword ptr [rax+rax+00h]
0x18009d5bf  nop
0x18009d5c0  test    rdi, rdi
0x18009d5c3  jz      short loc_18009D5D5
0x18009d5c5  mov     rcx, rdi; pv
0x18009d5c8  call    cs:__imp_CoTaskMemFree
0x18009d5cf  nop     dword ptr [rax+rax+00h]
0x18009d5d4  nop
0x18009d5d5  test    rbx, rbx
0x18009d5d8  jz      short loc_18009D5E9
0x18009d5da  mov     rcx, rbx; pv
0x18009d5dd  call    cs:__imp_CoTaskMemFree
0x18009d5e4  nop     dword ptr [rax+rax+00h]
0x18009d5e9  xor     eax, eax
0x18009d5eb  mov     rcx, [rbp+var_10]
0x18009d5ef  xor     rcx, rsp; StackCookie
0x18009d5f2  call    __security_check_cookie
0x18009d5f7  mov     rbx, [rsp+60h+arg_18]
0x18009d5ff  add     rsp, 60h
0x18009d603  pop     r15
0x18009d605  pop     r14
0x18009d607  pop     rdi
0x18009d608  pop     rsi
0x18009d609  pop     rbp
0x18009d60a  retn
0x18009d60c  mov     rcx, [rbp+28h]; this
0x18009d610  mov     r9d, edi; char *
0x18009d613  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x18009d61a  mov     edx, 197h; void *
0x18009d61f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d624  nop
0x18009d625  mov     rcx, [rbp+var_40]; pv
0x18009d629  test    rcx, rcx
0x18009d62c  jnz     short loc_18009D69F
0x18009d62e  test    rbx, rbx
0x18009d631  jz      short loc_18009D642
0x18009d633  mov     rcx, rbx; pv
0x18009d636  call    cs:__imp_CoTaskMemFree
0x18009d63d  nop     dword ptr [rax+rax+00h]
0x18009d642  mov     eax, edi
0x18009d644  jmp     short loc_18009D5EB
0x18009d646  mov     rcx, [rbp+28h]; this
0x18009d64a  mov     r9d, esi; char *
0x18009d64d  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x18009d654  mov     edx, 19Ah; void *
0x18009d659  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d65e  lea     rcx, [rbp+var]; pvarg
0x18009d662  call    cs:__imp_VariantClear
0x18009d669  nop     dword ptr [rax+rax+00h]
0x18009d66e  nop
0x18009d66f  test    rdi, rdi
0x18009d672  jz      short loc_18009D684
0x18009d674  mov     rcx, rdi; pv
0x18009d677  call    cs:__imp_CoTaskMemFree
0x18009d67e  nop     dword ptr [rax+rax+00h]
0x18009d683  nop
0x18009d684  test    rbx, rbx
0x18009d687  jz      short loc_18009D698
0x18009d689  mov     rcx, rbx; pv
0x18009d68c  call    cs:__imp_CoTaskMemFree
0x18009d693  nop     dword ptr [rax+rax+00h]
0x18009d698  mov     eax, esi
0x18009d69a  jmp     loc_18009D5EB
0x18009d69f  call    cs:__imp_CoTaskMemFree
0x18009d6a6  nop     dword ptr [rax+rax+00h]
0x18009d6ab  jmp     short loc_18009D62E
0x18009d6ad  mov     rcx, [rbp+28h]; this
0x18009d6b1  mov     r9d, edi; char *
0x18009d6b4  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x18009d6bb  mov     edx, 194h; void *
0x18009d6c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d6c5  jmp     loc_18009D62E
0x18009d6ca  mov     rcx, [rbp+28h]; this
0x18009d6ce  mov     r9d, ebx; char *
0x18009d6d1  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x18009d6d8  mov     edx, 191h; void *
0x18009d6dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d6e2  nop
0x18009d6e3  mov     rcx, [rbp+propName]; pv
0x18009d6e7  test    rcx, rcx
0x18009d6ea  jz      short loc_18009D6F8
0x18009d6ec  call    cs:__imp_CoTaskMemFree
0x18009d6f3  nop     dword ptr [rax+rax+00h]
0x18009d6f8  mov     eax, ebx
0x18009d6fa  jmp     loc_18009D5EB
0x18009d6ff  mov     rcx, [rbp+28h]; this
0x18009d703  mov     r9d, esi; char *
0x18009d706  lea     r8, aShellShell32Li; "shell\\shell32\\libraryqueryfolder.cpp"
0x18009d70d  mov     edx, 19Bh; void *
0x18009d712  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009d717  lea     rcx, [rbp+var]; pvarg
0x18009d71b  call    cs:__imp_VariantClear
0x18009d722  nop     dword ptr [rax+rax+00h]
0x18009d727  nop
0x18009d728  lea     rcx, [rbp+var_40]; void *
0x18009d72c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18009d731  nop
0x18009d732  lea     rcx, [rbp+propName]; void *
0x18009d736  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18009d73b  jmp     loc_18009D698
```
