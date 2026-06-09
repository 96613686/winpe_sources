# CDataPackage::SetSourceAppId(ushort const *)

- ea: `0x18004c9e0`
- end: `0x18004caa6`
- name: `?SetSourceAppId@CDataPackage@@UEAAJPEBG@Z`
- size: `198`
- prototype: `__int64 __fastcall(CDataPackage *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180010f08`
- `0x180048954`
- `0x18004c9e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ca56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ca56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ca43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ca43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ca4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ca6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ca4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ca6d`

## pseudocode

```c
__int64 __fastcall CDataPackage::SetSourceAppId(CDataPackage *this, const unsigned __int16 *a2)
{
  LPVOID *v2; // rdi
  LPVOID v3; // rbp
  void *v4; // rcx
  void *v5; // rsi
  DWORD LastError; // ebx
  void *v8; // [rsp+20h] [rbp-38h] BYREF
  LPVOID pv[6]; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (LPVOID *)((char *)this + 384);
  if ( a2 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v8,
      a2,
      -1);
    if ( v2 == &v8 )
    {
      v4 = v8;
      goto LABEL_11;
    }
    v3 = v8;
  }
  else
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      pv,
      &sourceString,
      -1);
    if ( v2 == pv )
    {
      v4 = pv[0];
      goto LABEL_11;
    }
    v3 = pv[0];
  }
  v5 = *v2;
  if ( *v2 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v5);
    SetLastError(LastError);
  }
  *v2 = v3;
  v4 = 0;
LABEL_11:
  if ( v4 )
    CoTaskMemFree(v4);
  if ( *v2 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E69,
    (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
    (const char *)0x8007000ELL,
    (int)v8);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18004c9e0  push    rbx
0x18004c9e2  push    rbp
0x18004c9e3  push    rsi
0x18004c9e4  push    rdi
0x18004c9e5  sub     rsp, 38h
0x18004c9e9  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004c9ed  lea     rdi, [rcx+180h]
0x18004c9f4  test    rdx, rdx
0x18004c9f7  jz      short loc_18004CA1B
0x18004c9f9  lea     rcx, [rsp+58h+var_38]
0x18004c9fe  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004ca03  lea     rax, [rsp+58h+var_38]
0x18004ca08  cmp     rdi, rax
0x18004ca0b  jz      short loc_18004CA14
0x18004ca0d  mov     rbp, [rsp+58h+var_38]
0x18004ca12  jmp     short loc_18004CA3B
0x18004ca14  mov     rcx, [rsp+58h+var_38]
0x18004ca19  jmp     short loc_18004CA68
0x18004ca1b  lea     rdx, sourceString
0x18004ca22  lea     rcx, [rsp+58h+pv]
0x18004ca27  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004ca2c  lea     rax, [rsp+58h+pv]
0x18004ca31  cmp     rdi, rax
0x18004ca34  jz      short loc_18004CA63
0x18004ca36  mov     rbp, [rsp+58h+pv]
0x18004ca3b  mov     rsi, [rdi]
0x18004ca3e  test    rsi, rsi
0x18004ca41  jz      short loc_18004CA5C
0x18004ca43  call    cs:__imp_GetLastError
0x18004ca49  mov     rcx, rsi; pv
0x18004ca4c  mov     ebx, eax
0x18004ca4e  call    cs:__imp_CoTaskMemFree
0x18004ca54  mov     ecx, ebx; dwErrCode
0x18004ca56  call    cs:__imp_SetLastError
0x18004ca5c  mov     [rdi], rbp
0x18004ca5f  xor     ecx, ecx
0x18004ca61  jmp     short loc_18004CA68
0x18004ca63  mov     rcx, [rsp+58h+pv]; pv
0x18004ca68  test    rcx, rcx
0x18004ca6b  jz      short loc_18004CA73
0x18004ca6d  call    cs:__imp_CoTaskMemFree
0x18004ca73  cmp     qword ptr [rdi], 0
0x18004ca77  jnz     short loc_18004CA9B
0x18004ca79  mov     rcx, [rsp+58h]; this
0x18004ca7e  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x18004ca85  mov     ebx, 8007000Eh
0x18004ca8a  mov     edx, 1E69h; void *
0x18004ca8f  mov     r9d, ebx; char *
0x18004ca92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ca97  mov     eax, ebx
0x18004ca99  jmp     short loc_18004CA9D
0x18004ca9b  xor     eax, eax
0x18004ca9d  add     rsp, 38h
0x18004caa1  pop     rdi
0x18004caa2  pop     rsi
0x18004caa3  pop     rbp
0x18004caa4  pop     rbx
0x18004caa5  retn
```
