# wistd::__function::__func<`wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &)'::`2'::_lambda_1_,long (wchar_t *,unsigned __int64,unsigned __int64 *)>::operator()(wchar_t * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x18000bb20`
- end: `0x18000bbd6`
- name: `??R?$__func@V_lambda_1_@?1???$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@2@@Z@$$A6AJPEA_W_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEA_W$$QEA_K$$QEAPEA_K@Z`
- size: `182`
- prototype: `__int64 __fastcall(__int64, WCHAR **, unsigned __int64 *, __int64 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005ea4`
- `0x18000bb20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000bb77`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000bb77`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18000bb59`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18000bb59`

## string_xrefs

- `0x18000bba2`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::Z::$$A6AJPEA_W_KPEA_K::Z::__func<`wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>'::`2'::_lambda_1_,AJPEAXPEAUHINSTANCE__,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &>::operator()(
        __int64 a1,
        WCHAR **a2,
        unsigned __int64 *a3,
        __int64 **a4)
{
  unsigned int v4; // ebx
  __int64 *v5; // rsi
  unsigned __int64 v6; // rdi
  WCHAR *v7; // rdx
  void *v8; // r10
  HMODULE *v9; // rax
  DWORD ModuleFileName; // eax
  const char *v11; // r9
  __int64 v12; // rdx
  bool v13; // r8
  bool v14; // cf
  DWORD ModuleFileNameW; // eax
  int v16; // ecx
  __int64 v17; // rdx
  __int64 v18; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = 0;
  v5 = *a4;
  v6 = *a3;
  v7 = *a2;
  v8 = **(void ***)(a1 + 8);
  v9 = *(HMODULE **)(a1 + 16);
  if ( v8 )
  {
    ModuleFileName = K32GetModuleFileNameExW(v8, *v9, v7, v6);
    v12 = ModuleFileName;
    v13 = ModuleFileName == 0;
    if ( ModuleFileName )
    {
      v14 = ModuleFileName < v6 - 1;
      goto LABEL_6;
    }
  }
  else
  {
    ModuleFileNameW = GetModuleFileNameW(*v9, v7, v6);
    v12 = ModuleFileNameW;
    v13 = ModuleFileNameW == 0;
    if ( ModuleFileNameW )
    {
      v14 = ModuleFileNameW < v6;
LABEL_6:
      v16 = 1;
      if ( v14 )
        goto LABEL_8;
    }
  }
  v16 = 0;
LABEL_8:
  v17 = v12 + 1;
  if ( v13 )
  {
    return (unsigned int)wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x205,
                           (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opens"
                                         "ource\\wil\\win32_helpers.h",
                           v11);
  }
  else
  {
    v18 = 2 * v6;
    if ( v16 )
      v18 = v17;
    *v5 = v18;
  }
  return v4;
}

```

## disassembly

```asm
0x18000bb20  mov     [rsp+arg_0], rbx
0x18000bb25  mov     [rsp+arg_8], rsi
0x18000bb2a  push    rdi
0x18000bb2b  sub     rsp, 20h
0x18000bb2f  mov     rax, [rcx+8]
0x18000bb33  xor     ebx, ebx
0x18000bb35  mov     rsi, [r9]
0x18000bb38  mov     rdi, [r8]
0x18000bb3b  mov     rdx, [rdx]; lpFilename
0x18000bb3e  mov     r10, [rax]
0x18000bb41  mov     rax, [rcx+10h]
0x18000bb45  mov     rcx, [rax]; hModule
0x18000bb48  test    r10, r10
0x18000bb4b  jz      short loc_18000BB74
0x18000bb4d  mov     r8, rdx; lpFilename
0x18000bb50  mov     r9d, edi; nSize
0x18000bb53  mov     rdx, rcx; hModule
0x18000bb56  mov     rcx, r10; hProcess
0x18000bb59  call    cs:__imp_K32GetModuleFileNameExW
0x18000bb5f  test    eax, eax
0x18000bb61  mov     edx, eax
0x18000bb63  setz    r8b
0x18000bb67  test    eax, eax
0x18000bb69  jz      short loc_18000BB93
0x18000bb6b  lea     rax, [rdi-1]
0x18000bb6f  cmp     rdx, rax
0x18000bb72  jmp     short loc_18000BB8C
0x18000bb74  mov     r8d, edi; nSize
0x18000bb77  call    cs:__imp_GetModuleFileNameW
0x18000bb7d  test    eax, eax
0x18000bb7f  mov     edx, eax
0x18000bb81  setz    r8b
0x18000bb85  test    eax, eax
0x18000bb87  jz      short loc_18000BB93
0x18000bb89  cmp     rdx, rdi
0x18000bb8c  mov     ecx, 1
0x18000bb91  jb      short loc_18000BB95
0x18000bb93  mov     ecx, ebx
0x18000bb95  inc     rdx
0x18000bb98  test    r8b, r8b
0x18000bb9b  jz      short loc_18000BBB7
0x18000bb9d  mov     rcx, [rsp+28h]; this
0x18000bba2  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000bba9  mov     edx, 205h; void *
0x18000bbae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bbb3  mov     ebx, eax
0x18000bbb5  jmp     short loc_18000BBC4
0x18000bbb7  test    ecx, ecx
0x18000bbb9  lea     rax, [rdi+rdi]
0x18000bbbd  cmovnz  rax, rdx
0x18000bbc1  mov     [rsi], rax
0x18000bbc4  mov     rsi, [rsp+28h+arg_8]
0x18000bbc9  mov     eax, ebx
0x18000bbcb  mov     rbx, [rsp+28h+arg_0]
0x18000bbd0  add     rsp, 20h
0x18000bbd4  pop     rdi
0x18000bbd5  retn
```
