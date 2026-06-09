# tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x18000dc28`
- end: `0x18000dcfc`
- name: `??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e980`
- `0x180015a68`
- `0x180016e88`

## callees

- `0x18000dc28`
- `0x180016c40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dc97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dce1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dc97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dcd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dcd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dc73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dc73`

## pseudocode

```c
tson::input_archive *__fastcall tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(
        tson::input_archive *this,
        void **a2)
{
  LPVOID v4; // rax
  void *v5; // r14
  void *v6; // rbp
  DWORD LastError; // ebx
  void *v8; // rbp
  DWORD v9; // ebx
  void *v11; // [rsp+20h] [rbp-48h] BYREF
  SIZE_T cb; // [rsp+28h] [rbp-40h]
  char v13; // [rsp+30h] [rbp-38h]
  int v14; // [rsp+31h] [rbp-37h]
  __int16 v15; // [rsp+35h] [rbp-33h]
  char v16; // [rsp+37h] [rbp-31h]

  v11 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  cb = 0;
  v13 = 0;
  tson::input_archive::loadValue(this, (struct tson::ansistring_tag *)&v11);
  if ( cb )
  {
    v4 = CoTaskMemAlloc(cb);
    v5 = *a2;
    v6 = v4;
    if ( *a2 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v5);
      SetLastError(LastError);
    }
    *a2 = v6;
    if ( v6 )
    {
      v11 = v6;
      tson::input_archive::loadValue(this, (struct tson::ansistring_tag *)&v11);
      return this;
    }
    if ( *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147024882;
  }
  v8 = *a2;
  if ( *a2 )
  {
    v9 = GetLastError();
    CoTaskMemFree(v8);
    SetLastError(v9);
  }
  *a2 = 0;
  return this;
}

```

## disassembly

```asm
0x18000dc28  push    rbx
0x18000dc2a  push    rbp
0x18000dc2b  push    rsi
0x18000dc2c  push    rdi
0x18000dc2d  push    r14
0x18000dc2f  sub     rsp, 40h
0x18000dc33  xor     eax, eax
0x18000dc35  mov     [rsp+68h+var_48], 0
0x18000dc3e  mov     rsi, rdx
0x18000dc41  mov     [rsp+68h+var_37], eax
0x18000dc45  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x18000dc4a  mov     [rsp+68h+var_33], ax
0x18000dc4f  mov     [rsp+68h+var_31], al
0x18000dc53  mov     rdi, rcx
0x18000dc56  mov     [rsp+68h+cb], 0
0x18000dc5f  mov     [rsp+68h+var_38], 0
0x18000dc64  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x18000dc69  mov     rcx, [rsp+68h+cb]; cb
0x18000dc6e  test    rcx, rcx
0x18000dc71  jz      short loc_18000DCC6
0x18000dc73  call    cs:__imp_CoTaskMemAlloc
0x18000dc79  mov     r14, [rsi]
0x18000dc7c  mov     rbp, rax
0x18000dc7f  test    r14, r14
0x18000dc82  jz      short loc_18000DC9D
0x18000dc84  call    cs:__imp_GetLastError
0x18000dc8a  mov     rcx, r14; pv
0x18000dc8d  mov     ebx, eax
0x18000dc8f  call    cs:__imp_CoTaskMemFree
0x18000dc95  mov     ecx, ebx; dwErrCode
0x18000dc97  call    cs:__imp_SetLastError
0x18000dc9d  mov     [rsi], rbp
0x18000dca0  test    rbp, rbp
0x18000dca3  jz      short loc_18000DCB9
0x18000dca5  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x18000dcaa  mov     [rsp+68h+var_48], rbp
0x18000dcaf  mov     rcx, rdi; this
0x18000dcb2  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x18000dcb7  jmp     short loc_18000DCEE
0x18000dcb9  cmp     dword ptr [rdi+8], 0
0x18000dcbd  jl      short loc_18000DCC6
0x18000dcbf  mov     dword ptr [rdi+8], 8007000Eh
0x18000dcc6  mov     rbp, [rsi]
0x18000dcc9  test    rbp, rbp
0x18000dccc  jz      short loc_18000DCE7
0x18000dcce  call    cs:__imp_GetLastError
0x18000dcd4  mov     rcx, rbp; pv
0x18000dcd7  mov     ebx, eax
0x18000dcd9  call    cs:__imp_CoTaskMemFree
0x18000dcdf  mov     ecx, ebx; dwErrCode
0x18000dce1  call    cs:__imp_SetLastError
0x18000dce7  mov     qword ptr [rsi], 0
0x18000dcee  mov     rax, rdi
0x18000dcf1  add     rsp, 40h
0x18000dcf5  pop     r14
0x18000dcf7  pop     rdi
0x18000dcf8  pop     rsi
0x18000dcf9  pop     rbp
0x18000dcfa  pop     rbx
0x18000dcfb  retn
```
