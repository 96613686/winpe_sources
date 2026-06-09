# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &> &&)

- ea: `0x18002e31c`
- end: `0x18002e42e`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `274`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800328a4`

## callees

- `0x18002e31c`
- `0x18003277c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e3b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e40c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e3b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e40c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e3ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e3ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e3a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e3fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e3a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e3fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e37a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e37a`

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
0x18002e31c  push    rbx
0x18002e31e  push    rbp
0x18002e31f  push    rsi
0x18002e320  push    rdi
0x18002e321  push    r14
0x18002e323  sub     rsp, 40h
0x18002e327  mov     rax, [rdx]
0x18002e32a  mov     rdi, rcx
0x18002e32d  mov     r8b, [rdx+8]
0x18002e331  mov     [rcx+10h], rax
0x18002e335  xor     eax, eax
0x18002e337  mov     [rcx+18h], r8b
0x18002e33b  mov     rsi, [rdx+10h]
0x18002e33f  lea     rdx, [rsp+68h+var_48]; struct tson::string_tag *
0x18002e344  mov     [rsp+68h+var_37], eax
0x18002e348  mov     [rsp+68h+var_33], ax
0x18002e34d  mov     [rsp+68h+var_31], al
0x18002e351  mov     [rsp+68h+var_48], 0
0x18002e35a  mov     [rsp+68h+var_40], 0
0x18002e363  mov     [rsp+68h+var_38], 0
0x18002e368  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x18002e36d  mov     rcx, [rsp+68h+var_40]
0x18002e372  test    rcx, rcx
0x18002e375  jz      short loc_18002E3E5
0x18002e377  add     rcx, rcx; cb
0x18002e37a  call    cs:__imp_CoTaskMemAlloc
0x18002e381  nop     dword ptr [rax+rax+00h]
0x18002e386  mov     r14, [rsi]
0x18002e389  mov     rbp, rax
0x18002e38c  test    r14, r14
0x18002e38f  jz      short loc_18002E3BC
0x18002e391  call    cs:__imp_GetLastError
0x18002e398  nop     dword ptr [rax+rax+00h]
0x18002e39d  mov     rcx, r14; pv
0x18002e3a0  mov     ebx, eax
0x18002e3a2  call    cs:__imp_CoTaskMemFree
0x18002e3a9  nop     dword ptr [rax+rax+00h]
0x18002e3ae  mov     ecx, ebx; dwErrCode
0x18002e3b0  call    cs:__imp_SetLastError
0x18002e3b7  nop     dword ptr [rax+rax+00h]
0x18002e3bc  mov     [rsi], rbp
0x18002e3bf  test    rbp, rbp
0x18002e3c2  jz      short loc_18002E3D8
0x18002e3c4  lea     rdx, [rsp+68h+var_48]; struct tson::string_tag *
0x18002e3c9  mov     [rsp+68h+var_48], rbp
0x18002e3ce  mov     rcx, rdi; this
0x18002e3d1  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x18002e3d6  jmp     short loc_18002E41F
0x18002e3d8  cmp     dword ptr [rdi+8], 0
0x18002e3dc  jl      short loc_18002E3E5
0x18002e3de  mov     dword ptr [rdi+8], 8007000Eh
0x18002e3e5  mov     rbp, [rsi]
0x18002e3e8  test    rbp, rbp
0x18002e3eb  jz      short loc_18002E418
0x18002e3ed  call    cs:__imp_GetLastError
0x18002e3f4  nop     dword ptr [rax+rax+00h]
0x18002e3f9  mov     rcx, rbp; pv
0x18002e3fc  mov     ebx, eax
0x18002e3fe  call    cs:__imp_CoTaskMemFree
0x18002e405  nop     dword ptr [rax+rax+00h]
0x18002e40a  mov     ecx, ebx; dwErrCode
0x18002e40c  call    cs:__imp_SetLastError
0x18002e413  nop     dword ptr [rax+rax+00h]
0x18002e418  mov     qword ptr [rsi], 0
0x18002e41f  mov     rax, rdi
0x18002e422  add     rsp, 40h
0x18002e426  pop     r14
0x18002e428  pop     rdi
0x18002e429  pop     rsi
0x18002e42a  pop     rbp
0x18002e42b  pop     rbx
0x18002e42c  retn
```
