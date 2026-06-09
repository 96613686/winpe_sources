# WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)

- ea: `0x14000fd28`
- end: `0x14000ff6f`
- name: `?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ`
- size: `583`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005f84`
- `0x1400074c8`
- `0x1400080bc`
- `0x1400089b0`
- `0x14000bda4`
- `0x140011f2c`
- `0x140012128`
- `0x1400126b8`
- `0x140012990`
- `0x1400132b0`
- `0x1400197cc`

## callees

- `0x140009084`
- `0x14000c5b0`
- `0x14000d5f4`
- `0x14000f9d0`
- `0x14000fb58`
- `0x14000fd28`
- `0x1400102e8`
- `0x14001aa60`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000ff16`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000ff28`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000ff16`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000ff28`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000fee7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000fee7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ff46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ff46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ff38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ff38`

## pseudocode

```c
void WUTrace(const char *a1, unsigned int a2, unsigned int a3, unsigned int a4, int a5, wchar_t *a6, ...)
{
  wchar_t *v8; // rcx
  unsigned __int64 v9; // rdx
  int v12; // eax
  const WCHAR *v13; // rdi
  int v14; // ebx
  wchar_t *v15; // rsi
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rax
  WCHAR *v18; // rbx
  HANDLE ProcessHeap; // rax
  wchar_t *v20; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR *p_lpOutputString; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v23; // [rsp+58h] [rbp-A8h] BYREF
  char v24; // [rsp+60h] [rbp-A0h]
  LPCWSTR lpOutputString; // [rsp+70h] [rbp-90h] BYREF
  wchar_t v26[1000]; // [rsp+80h] [rbp-80h] BYREF
  va_list va; // [rsp+8E0h] [rbp+7E0h] BYREF

  va_start(va, a6);
  lpOutputString = 0;
  v8 = v26;
  v9 = 1000;
  v21 = 1000;
  v20 = v26;
  if ( a5 < 0 )
  {
    if ( (int)StringCchPrintfExW(v26, 0x3E8u, &v20, &v21, 0, L"*FAILED* [%08X] ", a5) < 0 )
      goto LABEL_24;
    v8 = v20;
    v9 = v21;
  }
  v12 = StringCchVPrintfExW(v8, v9, &v20, &v21, 0, a6, va);
  if ( v12 >= 0 && (!a1 || (v12 = StringCchPrintfExW(v20, v21, &v20, &v21, 0, L" [%hs:%lu]", a1, a2), v12 >= 0))
    || v12 == -2147024774 )
  {
    v13 = v26;
    if ( v12 == -2147024774
      && (p_lpOutputString = &lpOutputString,
          v23 = 0,
          v24 = 1,
          v14 = WUTraceDynamicBuffer(a1, a2, a5, a6, va, &v23),
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(&p_lpOutputString),
          v14 >= 0) )
    {
      v13 = lpOutputString;
      v15 = 0;
      v16 = 0;
    }
    else
    {
      v15 = v20;
      v16 = v21;
    }
    v17 = -1;
    do
      ++v17;
    while ( v13[v17] );
    if ( v17 <= 0x3E8 )
      WUTraceString(a3, a4, v13);
    else
      WUTraceLargeString(a3, a4, v26, v13, v17);
    if ( IsDebuggerPresent() && byte_14002F0E1 && a4 <= dword_14002E140 )
    {
      if ( v16 > 1 )
        *(_DWORD *)v15 = 10;
      OutputDebugStringW(v13);
      if ( v16 <= 1 )
        OutputDebugStringW(&OutputString);
    }
  }
LABEL_24:
  v18 = (WCHAR *)lpOutputString;
  if ( lpOutputString )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v18);
  }
}

```

## disassembly

```asm
0x14000fd28  push    rbp
0x14000fd2a  push    rbx
0x14000fd2b  push    rsi
0x14000fd2c  push    rdi
0x14000fd2d  push    r12
0x14000fd2f  push    r13
0x14000fd31  push    r14
0x14000fd33  push    r15
0x14000fd35  lea     rbp, [rsp-768h]
0x14000fd3d  sub     rsp, 868h
0x14000fd44  mov     rax, cs:__security_cookie
0x14000fd4b  xor     rax, rsp
0x14000fd4e  mov     [rbp+7A0h+var_50], rax
0x14000fd55  mov     esi, [rbp+7A0h+arg_20]
0x14000fd5b  xor     r13d, r13d
0x14000fd5e  mov     [rsp+8A0h+lpOutputString], r13
0x14000fd63  mov     r10d, 3E8h
0x14000fd69  mov     r12d, edx
0x14000fd6c  mov     rbx, rcx
0x14000fd6f  lea     rcx, [rbp+7A0h+var_820]
0x14000fd73  mov     edx, r10d; unsigned __int64
0x14000fd76  mov     [rsp+8A0h+var_858], rdx
0x14000fd7b  mov     r14d, r9d
0x14000fd7e  mov     [rsp+8A0h+var_860], rcx
0x14000fd83  mov     r15d, r8d
0x14000fd86  test    esi, esi
0x14000fd88  jns     short loc_14000FDC4
0x14000fd8a  lea     rax, aFailed08x; "*FAILED* [%08X] "
0x14000fd91  mov     dword ptr [rsp+8A0h+var_870], esi
0x14000fd95  mov     [rsp+8A0h+var_878], rax; wchar_t *
0x14000fd9a  lea     r9, [rsp+8A0h+var_858]; unsigned __int64 *
0x14000fd9f  lea     r8, [rsp+8A0h+var_860]; wchar_t **
0x14000fda4  mov     [rsp+8A0h+var_880], r13; unsigned int
0x14000fda9  lea     rcx, [rbp+7A0h+var_820]; wchar_t *
0x14000fdad  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x14000fdb2  test    eax, eax
0x14000fdb4  js      loc_14000FF2E
0x14000fdba  mov     rcx, [rsp+8A0h+var_860]; wchar_t *
0x14000fdbf  mov     rdx, [rsp+8A0h+var_858]; unsigned __int64
0x14000fdc4  lea     rax, [rbp+7A0h+arg_30]
0x14000fdcb  mov     [rsp+8A0h+var_870], rax; char *
0x14000fdd0  lea     r9, [rsp+8A0h+var_858]; unsigned __int64 *
0x14000fdd5  mov     rax, [rbp+7A0h+arg_28]
0x14000fddc  lea     r8, [rsp+8A0h+var_860]; wchar_t **
0x14000fde1  mov     [rsp+8A0h+var_878], rax; wchar_t *
0x14000fde6  mov     dword ptr [rsp+8A0h+var_880], r13d; unsigned int
0x14000fdeb  call    ?StringCchVPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WPEAD@Z; StringCchVPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,char *)
0x14000fdf0  test    eax, eax
0x14000fdf2  js      short loc_14000FE31
0x14000fdf4  test    rbx, rbx
0x14000fdf7  jz      short loc_14000FE3C
0x14000fdf9  mov     rdx, [rsp+8A0h+var_858]; unsigned __int64
0x14000fdfe  lea     rax, aHsLu; " [%hs:%lu]"
0x14000fe05  mov     rcx, [rsp+8A0h+var_860]; wchar_t *
0x14000fe0a  lea     r9, [rsp+8A0h+var_858]; unsigned __int64 *
0x14000fe0f  mov     [rsp+8A0h+var_868], r12d
0x14000fe14  lea     r8, [rsp+8A0h+var_860]; wchar_t **
0x14000fe19  mov     [rsp+8A0h+var_870], rbx
0x14000fe1e  mov     [rsp+8A0h+var_878], rax; wchar_t *
0x14000fe23  mov     [rsp+8A0h+var_880], r13; unsigned int
0x14000fe28  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x14000fe2d  test    eax, eax
0x14000fe2f  jns     short loc_14000FE3C
0x14000fe31  cmp     eax, 8007007Ah
0x14000fe36  jnz     loc_14000FF2E
0x14000fe3c  lea     rdi, [rbp+7A0h+var_820]
0x14000fe40  cmp     eax, 8007007Ah
0x14000fe45  jnz     short loc_14000FEA6
0x14000fe47  mov     r9, [rbp+7A0h+arg_28]; wchar_t *
0x14000fe4e  lea     rax, [rsp+8A0h+lpOutputString]
0x14000fe53  mov     [rsp+8A0h+var_850], rax
0x14000fe58  mov     r8d, esi; int
0x14000fe5b  lea     rax, [rsp+8A0h+var_848]
0x14000fe60  mov     [rsp+8A0h+var_848], r13
0x14000fe65  mov     [rsp+8A0h+var_878], rax; wchar_t **
0x14000fe6a  mov     edx, r12d; unsigned int
0x14000fe6d  lea     rax, [rbp+7A0h+arg_30]
0x14000fe74  mov     [rsp+8A0h+var_840], 1
0x14000fe79  mov     rcx, rbx; char *
0x14000fe7c  mov     [rsp+8A0h+var_880], rax; char *
0x14000fe81  call    ?WUTraceDynamicBuffer@@YAJPEBDKJPEB_WPEADPEAPEA_W@Z; WUTraceDynamicBuffer(char const *,ulong,long,wchar_t const *,char *,wchar_t * *)
0x14000fe86  lea     rcx, [rsp+8A0h+var_850]
0x14000fe8b  mov     ebx, eax
0x14000fe8d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(void)
0x14000fe92  shr     ebx, 1Fh
0x14000fe95  test    bl, bl
0x14000fe97  jnz     short loc_14000FEA6
0x14000fe99  mov     rdi, [rsp+8A0h+lpOutputString]
0x14000fe9e  mov     rsi, r13
0x14000fea1  mov     rbx, r13
0x14000fea4  jmp     short loc_14000FEB0
0x14000fea6  mov     rsi, [rsp+8A0h+var_860]
0x14000feab  mov     rbx, [rsp+8A0h+var_858]
0x14000feb0  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000feb4  inc     rax
0x14000feb7  cmp     [rdi+rax*2], r13w
0x14000febc  jnz     short loc_14000FEB4
0x14000febe  mov     edx, r14d
0x14000fec1  mov     ecx, r15d
0x14000fec4  cmp     rax, 3E8h
0x14000feca  jbe     short loc_14000FEDF
0x14000fecc  mov     r9, rdi
0x14000fecf  mov     [rsp+8A0h+var_880], rax
0x14000fed4  lea     r8, [rbp+7A0h+var_820]
0x14000fed8  call    ?WUTraceLargeString@@YAXW4WUTraceLoggingCategory@@IPEB_W1_K@Z; WUTraceLargeString(WUTraceLoggingCategory,uint,wchar_t const *,wchar_t const *,unsigned __int64)
0x14000fedd  jmp     short loc_14000FEE7
0x14000fedf  mov     r8, rdi
0x14000fee2  call    ?WUTraceString@@YAXW4WUTraceLoggingCategory@@IPEB_W@Z; WUTraceString(WUTraceLoggingCategory,uint,wchar_t const *)
0x14000fee7  call    cs:__imp_IsDebuggerPresent
0x14000feed  test    eax, eax
0x14000feef  jz      short loc_14000FF2E
0x14000fef1  cmp     cs:byte_14002F0E1, r13b
0x14000fef8  jz      short loc_14000FF2E
0x14000fefa  cmp     r14d, cs:dword_14002E140
0x14000ff01  ja      short loc_14000FF2E
0x14000ff03  cmp     rbx, 1
0x14000ff07  setnbe  r14b
0x14000ff0b  jbe     short loc_14000FF13
0x14000ff0d  mov     dword ptr [rsi], 0Ah
0x14000ff13  mov     rcx, rdi; lpOutputString
0x14000ff16  call    cs:__imp_OutputDebugStringW
0x14000ff1c  test    r14b, r14b
0x14000ff1f  jnz     short loc_14000FF2E
0x14000ff21  lea     rcx, OutputString; lpOutputString
0x14000ff28  call    cs:__imp_OutputDebugStringW
0x14000ff2e  mov     rbx, [rsp+8A0h+lpOutputString]
0x14000ff33  test    rbx, rbx
0x14000ff36  jz      short loc_14000FF4C
0x14000ff38  call    cs:__imp_GetProcessHeap
0x14000ff3e  mov     r8, rbx; lpMem
0x14000ff41  xor     edx, edx; dwFlags
0x14000ff43  mov     rcx, rax; hHeap
0x14000ff46  call    cs:__imp_HeapFree
0x14000ff4c  mov     rcx, [rbp+7A0h+var_50]
0x14000ff53  xor     rcx, rsp; StackCookie
0x14000ff56  call    __security_check_cookie
0x14000ff5b  add     rsp, 868h
0x14000ff62  pop     r15
0x14000ff64  pop     r14
0x14000ff66  pop     r13
0x14000ff68  pop     r12
0x14000ff6a  pop     rdi
0x14000ff6b  pop     rsi
0x14000ff6c  pop     rbx
0x14000ff6d  pop     rbp
0x14000ff6e  retn
```
