# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &> &&)

- ea: `0x180006ac4`
- end: `0x180006ba8`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `228`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005b520`

## callees

- `0x180006ac4`
- `0x18005b2d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006b1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006b1f`

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
0x180006ac4  push    rbx
0x180006ac6  push    rbp
0x180006ac7  push    rsi
0x180006ac8  push    rdi
0x180006ac9  push    r14
0x180006acb  sub     rsp, 40h
0x180006acf  mov     rax, [rdx]
0x180006ad2  mov     rdi, rcx
0x180006ad5  mov     r8b, [rdx+8]
0x180006ad9  mov     [rcx+10h], rax
0x180006add  xor     eax, eax
0x180006adf  mov     [rcx+18h], r8b
0x180006ae3  mov     rsi, [rdx+10h]
0x180006ae7  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x180006aec  mov     [rsp+68h+var_37], eax
0x180006af0  mov     [rsp+68h+var_33], ax
0x180006af5  mov     [rsp+68h+var_31], al
0x180006af9  mov     [rsp+68h+var_48], 0
0x180006b02  mov     [rsp+68h+cb], 0
0x180006b0b  mov     [rsp+68h+var_38], 0
0x180006b10  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x180006b15  mov     rcx, [rsp+68h+cb]; cb
0x180006b1a  test    rcx, rcx
0x180006b1d  jz      short loc_180006B72
0x180006b1f  call    cs:__imp_CoTaskMemAlloc
0x180006b25  mov     r14, [rsi]
0x180006b28  mov     rbp, rax
0x180006b2b  test    r14, r14
0x180006b2e  jz      short loc_180006B49
0x180006b30  call    cs:__imp_GetLastError
0x180006b36  mov     rcx, r14; pv
0x180006b39  mov     ebx, eax
0x180006b3b  call    cs:__imp_CoTaskMemFree
0x180006b41  mov     ecx, ebx; dwErrCode
0x180006b43  call    cs:__imp_SetLastError
0x180006b49  mov     [rsi], rbp
0x180006b4c  test    rbp, rbp
0x180006b4f  jz      short loc_180006B65
0x180006b51  lea     rdx, [rsp+68h+var_48]; struct tson::ansistring_tag *
0x180006b56  mov     [rsp+68h+var_48], rbp
0x180006b5b  mov     rcx, rdi; this
0x180006b5e  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x180006b63  jmp     short loc_180006B9A
0x180006b65  cmp     dword ptr [rdi+8], 0
0x180006b69  jl      short loc_180006B72
0x180006b6b  mov     dword ptr [rdi+8], 8007000Eh
0x180006b72  mov     rbp, [rsi]
0x180006b75  test    rbp, rbp
0x180006b78  jz      short loc_180006B93
0x180006b7a  call    cs:__imp_GetLastError
0x180006b80  mov     rcx, rbp; pv
0x180006b83  mov     ebx, eax
0x180006b85  call    cs:__imp_CoTaskMemFree
0x180006b8b  mov     ecx, ebx; dwErrCode
0x180006b8d  call    cs:__imp_SetLastError
0x180006b93  mov     qword ptr [rsi], 0
0x180006b9a  mov     rax, rdi
0x180006b9d  add     rsp, 40h
0x180006ba1  pop     r14
0x180006ba3  pop     rdi
0x180006ba4  pop     rsi
0x180006ba5  pop     rbp
0x180006ba6  pop     rbx
0x180006ba7  retn
```
