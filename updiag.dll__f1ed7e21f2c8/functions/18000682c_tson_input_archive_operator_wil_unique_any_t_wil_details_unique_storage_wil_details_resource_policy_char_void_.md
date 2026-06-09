# tson::input_archive::operator()<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x18000682c`
- end: `0x18000691b`
- name: `??$?RAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@QEAAAEAV01@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `239`
- prototype: `tson::input_archive *__fastcall(tson::input_archive *this, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004890`
- `0x180005e00`
- `0x180007748`

## callees

- `0x1800038a0`
- `0x18000682c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000689e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800068e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000689e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800068e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068dd`

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
  void *v11; // [rsp+20h] [rbp-28h] BYREF
  SIZE_T cb; // [rsp+28h] [rbp-20h]
  char v13; // [rsp+30h] [rbp-18h]
  int v14; // [rsp+31h] [rbp-17h]
  __int16 v15; // [rsp+35h] [rbp-13h]
  char v16; // [rsp+37h] [rbp-11h]

  v11 = 0;
  cb = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
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
0x18000682c  mov     rax, rsp
0x18000682f  mov     [rax+8], rbx
0x180006833  mov     [rax+10h], rbp
0x180006837  mov     [rax+18h], rsi
0x18000683b  mov     [rax+20h], rdi
0x18000683f  push    r14
0x180006841  sub     rsp, 40h
0x180006845  mov     qword ptr [rax-28h], 0
0x18000684d  mov     rsi, rdx
0x180006850  mov     qword ptr [rax-20h], 0
0x180006858  lea     rdx, [rsp+48h+var_28]; struct tson::ansistring_tag *
0x18000685d  mov     byte ptr [rax-18h], 0
0x180006861  mov     rdi, rcx
0x180006864  xor     eax, eax
0x180006866  mov     [rsp+48h+var_17], eax
0x18000686a  mov     [rsp+48h+var_13], ax
0x18000686f  mov     [rsp+48h+var_11], al
0x180006873  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x180006878  mov     rcx, [rsp+48h+cb]; cb
0x18000687d  test    rcx, rcx
0x180006880  jz      short loc_1800068D5
0x180006882  call    cs:__imp_CoTaskMemAlloc
0x180006888  mov     r14, [rsi]
0x18000688b  mov     rbp, rax
0x18000688e  test    r14, r14
0x180006891  jz      short loc_1800068AC
0x180006893  call    cs:__imp_GetLastError
0x180006899  mov     rcx, r14; pv
0x18000689c  mov     ebx, eax
0x18000689e  call    cs:__imp_CoTaskMemFree
0x1800068a4  mov     ecx, ebx; dwErrCode
0x1800068a6  call    cs:__imp_SetLastError
0x1800068ac  mov     [rsi], rbp
0x1800068af  test    rbp, rbp
0x1800068b2  jz      short loc_1800068C8
0x1800068b4  lea     rdx, [rsp+48h+var_28]; struct tson::ansistring_tag *
0x1800068b9  mov     [rsp+48h+var_28], rbp
0x1800068be  mov     rcx, rdi; this
0x1800068c1  call    ?loadValue@input_archive@tson@@QEAAXAEAUansistring_tag@2@@Z; tson::input_archive::loadValue(tson::ansistring_tag &)
0x1800068c6  jmp     short loc_1800068FD
0x1800068c8  cmp     dword ptr [rdi+8], 0
0x1800068cc  jl      short loc_1800068D5
0x1800068ce  mov     dword ptr [rdi+8], 8007000Eh
0x1800068d5  mov     rbp, [rsi]
0x1800068d8  test    rbp, rbp
0x1800068db  jz      short loc_1800068F6
0x1800068dd  call    cs:__imp_GetLastError
0x1800068e3  mov     rcx, rbp; pv
0x1800068e6  mov     ebx, eax
0x1800068e8  call    cs:__imp_CoTaskMemFree
0x1800068ee  mov     ecx, ebx; dwErrCode
0x1800068f0  call    cs:__imp_SetLastError
0x1800068f6  mov     qword ptr [rsi], 0
0x1800068fd  mov     rbx, [rsp+48h+arg_0]
0x180006902  mov     rax, rdi
0x180006905  mov     rdi, [rsp+48h+arg_18]
0x18000690a  mov     rbp, [rsp+48h+arg_8]
0x18000690f  mov     rsi, [rsp+48h+arg_10]
0x180006914  add     rsp, 40h
0x180006918  pop     r14
0x18000691a  retn
```
