# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &> &&)

- ea: `0x180006bb0`
- end: `0x180006c97`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `231`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005b520`

## callees

- `0x180006bb0`
- `0x18005b3f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006c0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006c0e`

## pseudocode

```c
tson::input_archive *__fastcall tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>> &>>(
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
  __int64 v13; // [rsp+28h] [rbp-40h]
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
  v13 = 0;
  v14 = 0;
  tson::input_archive::loadValue(this, (struct tson::string_tag *)&v12);
  if ( v13 )
  {
    v5 = CoTaskMemAlloc(2 * v13);
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
      tson::input_archive::loadValue(this, (struct tson::string_tag *)&v12);
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
0x180006bb0  push    rbx
0x180006bb2  push    rbp
0x180006bb3  push    rsi
0x180006bb4  push    rdi
0x180006bb5  push    r14
0x180006bb7  sub     rsp, 40h
0x180006bbb  mov     rax, [rdx]
0x180006bbe  mov     rdi, rcx
0x180006bc1  mov     r8b, [rdx+8]
0x180006bc5  mov     [rcx+10h], rax
0x180006bc9  xor     eax, eax
0x180006bcb  mov     [rcx+18h], r8b
0x180006bcf  mov     rsi, [rdx+10h]
0x180006bd3  lea     rdx, [rsp+68h+var_48]; struct tson::string_tag *
0x180006bd8  mov     [rsp+68h+var_37], eax
0x180006bdc  mov     [rsp+68h+var_33], ax
0x180006be1  mov     [rsp+68h+var_31], al
0x180006be5  mov     [rsp+68h+var_48], 0
0x180006bee  mov     [rsp+68h+var_40], 0
0x180006bf7  mov     [rsp+68h+var_38], 0
0x180006bfc  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x180006c01  mov     rcx, [rsp+68h+var_40]
0x180006c06  test    rcx, rcx
0x180006c09  jz      short loc_180006C61
0x180006c0b  add     rcx, rcx; cb
0x180006c0e  call    cs:__imp_CoTaskMemAlloc
0x180006c14  mov     r14, [rsi]
0x180006c17  mov     rbp, rax
0x180006c1a  test    r14, r14
0x180006c1d  jz      short loc_180006C38
0x180006c1f  call    cs:__imp_GetLastError
0x180006c25  mov     rcx, r14; pv
0x180006c28  mov     ebx, eax
0x180006c2a  call    cs:__imp_CoTaskMemFree
0x180006c30  mov     ecx, ebx; dwErrCode
0x180006c32  call    cs:__imp_SetLastError
0x180006c38  mov     [rsi], rbp
0x180006c3b  test    rbp, rbp
0x180006c3e  jz      short loc_180006C54
0x180006c40  lea     rdx, [rsp+68h+var_48]; struct tson::string_tag *
0x180006c45  mov     [rsp+68h+var_48], rbp
0x180006c4a  mov     rcx, rdi; this
0x180006c4d  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x180006c52  jmp     short loc_180006C89
0x180006c54  cmp     dword ptr [rdi+8], 0
0x180006c58  jl      short loc_180006C61
0x180006c5a  mov     dword ptr [rdi+8], 8007000Eh
0x180006c61  mov     rbp, [rsi]
0x180006c64  test    rbp, rbp
0x180006c67  jz      short loc_180006C82
0x180006c69  call    cs:__imp_GetLastError
0x180006c6f  mov     rcx, rbp; pv
0x180006c72  mov     ebx, eax
0x180006c74  call    cs:__imp_CoTaskMemFree
0x180006c7a  mov     ecx, ebx; dwErrCode
0x180006c7c  call    cs:__imp_SetLastError
0x180006c82  mov     qword ptr [rsi], 0
0x180006c89  mov     rax, rdi
0x180006c8c  add     rsp, 40h
0x180006c90  pop     r14
0x180006c92  pop     rdi
0x180006c93  pop     rsi
0x180006c94  pop     rbp
0x180006c95  pop     rbx
0x180006c96  retn
```
