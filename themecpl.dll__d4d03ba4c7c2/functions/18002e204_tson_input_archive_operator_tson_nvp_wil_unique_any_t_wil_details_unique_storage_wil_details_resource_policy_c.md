# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &> &&)

- ea: `0x18002e204`
- end: `0x18002e313`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `271`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800328a4`

## callees

- `0x18002e204`
- `0x18003265c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e295`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e2f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e295`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e2f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e287`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e2e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e287`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e2e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e25f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e25f`

## pseudocode

```c
tson::input_archive *__fastcall tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(
        tson::input_archive *this,
        __int64 a2)
{
  char v3; // r8
  void **v4; // rsi
  LPVOID v5; // rax
  void *v6; // r14
  void *v7; // rbp
  DWORD LastError; // ebx
  void *v9; // rbp
  DWORD v10; // ebx
  void *v12; // [rsp+20h] [rbp-48h] BYREF
  SIZE_T cb; // [rsp+28h] [rbp-40h]
  char v14; // [rsp+30h] [rbp-38h]
  int v15; // [rsp+31h] [rbp-37h]
  __int16 v16; // [rsp+35h] [rbp-33h]
  char v17; // [rsp+37h] [rbp-31h]

  v3 = *(_BYTE *)(a2 + 8);
  *((_QWORD *)this + 2) = *(_QWORD *)a2;
  *((_BYTE *)this + 24) = v3;
  v4 = *(void ***)(a2 + 16);
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v12 = 0;
  cb = 0;
  v14 = 0;
  tson::input_archive::loadValue(this, (struct tson::ansistring_tag *)&v12);
  if ( cb )
  {
    v5 = CoTaskMemAlloc(cb);
    v6 = *v4;
    v7 = v5;
    if ( *v4 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v6);
      SetLastError(LastError);
    }
    *v4 = v7;
    if ( v7 )
    {
      v12 = v7;
      tson::input_archive::loadValue(this, (struct tson::ansistring_tag *)&v12);
      return this;
    }
    if ( *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147024882;
  }
  v9 = *v4;
  if ( *v4 )
  {
    v10 = GetLastError();
    CoTaskMemFree(v9);
    SetLastError(v10);
  }
  *v4 = 0;
  return this;
}

```

## disassembly

```asm
0x18002e204  push    rbx
0x18002e206  push    rbp
0x18002e207  push    rsi
0x18002e208  push    rdi
0x18002e209  push    r14
0x18002e20b  sub     rsp, 40h
0x18002e20f  mov     rax, [rdx]
0x18002e212  mov     rdi, rcx
0x18002e215  mov     r8b, [rdx+8]
0x18002e219  mov     [rcx+10h], rax
0x18002e21d  xor     eax, eax
0x18002e21f  mov     [rcx+18h], r8b
0x18002e223  mov     rsi, [rdx+10h]
0x18002e227  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x18002e22c  mov     [rsp+68h+var_37], eax
0x18002e230  mov     [rsp+68h+var_33], ax
0x18002e235  mov     [rsp+68h+var_31], al
0x18002e239  mov     [rsp+68h+var_48], 0
0x18002e242  mov     [rsp+68h+cb], 0
0x18002e24b  mov     [rsp+68h+var_38], 0
0x18002e250  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x18002e255  mov     rcx, [rsp+68h+cb]; cb
0x18002e25a  test    rcx, rcx
0x18002e25d  jz      short loc_18002E2CA
0x18002e25f  call    cs:__imp_CoTaskMemAlloc
0x18002e266  nop     dword ptr [rax+rax+00h]
0x18002e26b  mov     r14, [rsi]
0x18002e26e  mov     rbp, rax
0x18002e271  test    r14, r14
0x18002e274  jz      short loc_18002E2A1
0x18002e276  call    cs:__imp_GetLastError
0x18002e27d  nop     dword ptr [rax+rax+00h]
0x18002e282  mov     rcx, r14; pv
0x18002e285  mov     ebx, eax
0x18002e287  call    cs:__imp_CoTaskMemFree
0x18002e28e  nop     dword ptr [rax+rax+00h]
0x18002e293  mov     ecx, ebx; dwErrCode
0x18002e295  call    cs:__imp_SetLastError
0x18002e29c  nop     dword ptr [rax+rax+00h]
0x18002e2a1  mov     [rsi], rbp
0x18002e2a4  test    rbp, rbp
0x18002e2a7  jz      short loc_18002E2BD
0x18002e2a9  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x18002e2ae  mov     [rsp+68h+var_48], rbp
0x18002e2b3  mov     rcx, rdi; this
0x18002e2b6  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x18002e2bb  jmp     short loc_18002E304
0x18002e2bd  cmp     dword ptr [rdi+8], 0
0x18002e2c1  jl      short loc_18002E2CA
0x18002e2c3  mov     dword ptr [rdi+8], 8007000Eh
0x18002e2ca  mov     rbp, [rsi]
0x18002e2cd  test    rbp, rbp
0x18002e2d0  jz      short loc_18002E2FD
0x18002e2d2  call    cs:__imp_GetLastError
0x18002e2d9  nop     dword ptr [rax+rax+00h]
0x18002e2de  mov     rcx, rbp; pv
0x18002e2e1  mov     ebx, eax
0x18002e2e3  call    cs:__imp_CoTaskMemFree
0x18002e2ea  nop     dword ptr [rax+rax+00h]
0x18002e2ef  mov     ecx, ebx; dwErrCode
0x18002e2f1  call    cs:__imp_SetLastError
0x18002e2f8  nop     dword ptr [rax+rax+00h]
0x18002e2fd  mov     qword ptr [rsi], 0
0x18002e304  mov     rax, rdi
0x18002e307  add     rsp, 40h
0x18002e30b  pop     r14
0x18002e30d  pop     rdi
0x18002e30e  pop     rsi
0x18002e30f  pop     rbp
0x18002e310  pop     rbx
0x18002e311  retn
```
