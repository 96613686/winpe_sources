# tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &>>(tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &> &&)

- ea: `0x180004fd0`
- end: `0x1800050d2`
- name: `??$?RV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@tson@@@input_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@1@@Z`
- size: `258`
- prototype: `tson::input_archive *__fastcall(tson::input_archive *this, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004890`

## callees

- `0x1800039c0`
- `0x180004fd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005039`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005039`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000509f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000509f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000505d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000505d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800050a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000504a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000504a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005094`

## pseudocode

```c
tson::input_archive *__fastcall tson::input_archive::operator()<tson::nvp<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &>>(
        tson::input_archive *this,
        __int64 *a2)
{
  __int64 v2; // rax
  char v4; // r8
  void **v5; // rsi
  LPVOID v6; // rax
  void *v7; // r14
  void *v8; // rbp
  DWORD LastError; // ebx
  void *v10; // rbp
  DWORD v11; // ebx
  void *v13; // [rsp+20h] [rbp-28h] BYREF
  __int64 v14; // [rsp+28h] [rbp-20h]
  char v15; // [rsp+30h] [rbp-18h]
  int v16; // [rsp+31h] [rbp-17h]
  __int16 v17; // [rsp+35h] [rbp-13h]
  char v18; // [rsp+37h] [rbp-11h]

  v2 = *a2;
  v4 = *((_BYTE *)a2 + 8);
  v13 = 0;
  v14 = 0;
  *((_QWORD *)this + 2) = v2;
  *((_BYTE *)this + 24) = v4;
  v5 = (void **)a2[2];
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v15 = 0;
  tson::input_archive::loadValue(this, (struct tson::string_tag *)&v13);
  if ( v14 )
  {
    v6 = CoTaskMemAlloc(2 * v14);
    v7 = *v5;
    v8 = v6;
    if ( *v5 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v7);
      SetLastError(LastError);
    }
    *v5 = v8;
    if ( v8 )
    {
      v13 = v8;
      tson::input_archive::loadValue(this, (struct tson::string_tag *)&v13);
      return this;
    }
    if ( *((int *)this + 2) >= 0 )
      *((_DWORD *)this + 2) = -2147024882;
  }
  v10 = *v5;
  if ( *v5 )
  {
    v11 = GetLastError();
    CoTaskMemFree(v10);
    SetLastError(v11);
  }
  *v5 = 0;
  return this;
}

```

## disassembly

```asm
0x180004fd0  mov     r11, rsp
0x180004fd3  mov     [r11+8], rbx
0x180004fd7  mov     [r11+10h], rbp
0x180004fdb  mov     [r11+18h], rsi
0x180004fdf  mov     [r11+20h], rdi
0x180004fe3  push    r14
0x180004fe5  sub     rsp, 40h
0x180004fe9  mov     rax, [rdx]
0x180004fec  mov     rdi, rcx
0x180004fef  mov     r8b, [rdx+8]
0x180004ff3  mov     qword ptr [r11-28h], 0
0x180004ffb  mov     qword ptr [r11-20h], 0
0x180005003  mov     [rcx+10h], rax
0x180005007  xor     eax, eax
0x180005009  mov     [rcx+18h], r8b
0x18000500d  mov     rsi, [rdx+10h]
0x180005011  lea     rdx, [r11-28h]; struct tson::string_tag *
0x180005015  mov     [rsp+48h+var_17], eax
0x180005019  mov     [rsp+48h+var_13], ax
0x18000501e  mov     [rsp+48h+var_11], al
0x180005022  mov     [rsp+48h+var_18], 0
0x180005027  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x18000502c  mov     rcx, [rsp+48h+var_20]
0x180005031  test    rcx, rcx
0x180005034  jz      short loc_18000508C
0x180005036  add     rcx, rcx; cb
0x180005039  call    cs:__imp_CoTaskMemAlloc
0x18000503f  mov     r14, [rsi]
0x180005042  mov     rbp, rax
0x180005045  test    r14, r14
0x180005048  jz      short loc_180005063
0x18000504a  call    cs:__imp_GetLastError
0x180005050  mov     rcx, r14; pv
0x180005053  mov     ebx, eax
0x180005055  call    cs:__imp_CoTaskMemFree
0x18000505b  mov     ecx, ebx; dwErrCode
0x18000505d  call    cs:__imp_SetLastError
0x180005063  mov     [rsi], rbp
0x180005066  test    rbp, rbp
0x180005069  jz      short loc_18000507F
0x18000506b  lea     rdx, [rsp+48h+var_28]; struct tson::string_tag *
0x180005070  mov     [rsp+48h+var_28], rbp
0x180005075  mov     rcx, rdi; this
0x180005078  call    ?loadValue@input_archive@tson@@QEAAXAEAUstring_tag@2@@Z; tson::input_archive::loadValue(tson::string_tag &)
0x18000507d  jmp     short loc_1800050B4
0x18000507f  cmp     dword ptr [rdi+8], 0
0x180005083  jl      short loc_18000508C
0x180005085  mov     dword ptr [rdi+8], 8007000Eh
0x18000508c  mov     rbp, [rsi]
0x18000508f  test    rbp, rbp
0x180005092  jz      short loc_1800050AD
0x180005094  call    cs:__imp_GetLastError
0x18000509a  mov     rcx, rbp; pv
0x18000509d  mov     ebx, eax
0x18000509f  call    cs:__imp_CoTaskMemFree
0x1800050a5  mov     ecx, ebx; dwErrCode
0x1800050a7  call    cs:__imp_SetLastError
0x1800050ad  mov     qword ptr [rsi], 0
0x1800050b4  mov     rbx, [rsp+48h+arg_0]
0x1800050b9  mov     rax, rdi
0x1800050bc  mov     rdi, [rsp+48h+arg_18]
0x1800050c1  mov     rbp, [rsp+48h+arg_8]
0x1800050c6  mov     rsi, [rsp+48h+arg_10]
0x1800050cb  add     rsp, 40h
0x1800050cf  pop     r14
0x1800050d1  retn
```
