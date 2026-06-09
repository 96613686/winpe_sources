# wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> const &)

- ea: `0x18000de40`
- end: `0x18000dff1`
- name: `??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@V12@V12@V12@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@AEBV10@11@Z`
- size: `433`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d6f8`

## callees

- `0x180003760`
- `0x1800069a0`
- `0x180008b20`
- `0x18000b0b4`
- `0x18000de40`
- `0x18000fc90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000def0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000df93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dfe9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000def0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000df93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dfe9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dee2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dfdb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dee2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dfdb`

## string_xrefs

- `0x18000df13`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x18000dfc7`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  _QWORD *v5; // rcx
  __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rax
  void *v9; // rbx
  HANDLE ProcessHeap; // rax
  wchar_t *v11; // rbx
  unsigned int v12; // edi
  wchar_t *v13; // rcx
  wchar_t *v14; // r14
  const wchar_t **v15; // rsi
  int v16; // eax
  wchar_t *v17; // rbx
  HANDLE v18; // rax
  HANDLE v20; // rax
  unsigned __int64 *v21; // [rsp+20h] [rbp-50h]
  unsigned int v22; // [rsp+28h] [rbp-48h]
  wchar_t *v23; // [rsp+30h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v25[4]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v26[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v25[0] = *a1;
  v5 = v25;
  v25[1] = *a2;
  v6 = 0;
  v25[2] = *a3;
  v25[3] = *a4;
  do
  {
    if ( *v5 )
    {
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)(*v5 + 2 * v7) );
    }
    else
    {
      v7 = 0;
    }
    v6 += v7;
    ++v5;
  }
  while ( v5 != v26 );
  v23 = 0;
  v8 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
         &lpMem,
         0,
         v6);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
    &v23,
    v8);
  v9 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9);
  }
  v11 = v23;
  v12 = v23 == 0 ? 0x8007000E : 0;
  if ( v23 )
  {
    v13 = v23;
    v14 = &v23[v6 + 1];
    v15 = (const wchar_t **)v25;
    do
    {
      if ( *v15 )
      {
        v16 = StringCchCopyExW(v13, v14 - v13, *v15, &v23, v21, v22);
        v12 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x73F,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v16,
            (int)v21);
          v20 = GetProcessHeap();
          HeapFree(v20, 0, v11);
          return v12;
        }
        v13 = v23;
      }
      ++v15;
    }
    while ( v15 != v26 );
    v23 = v11;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
      a1,
      &v23);
    v17 = v23;
    if ( v23 )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v17);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x737,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)v12,
      (int)v21);
  }
  return v12;
}

```

## disassembly

```asm
0x18000de40  mov     [rsp-28h+arg_8], rbx
0x18000de45  mov     [rsp-28h+arg_10], rsi
0x18000de4a  push    rbp
0x18000de4b  push    rdi
0x18000de4c  push    r12
0x18000de4e  push    r14
0x18000de50  push    r15
0x18000de52  mov     rbp, rsp
0x18000de55  sub     rsp, 70h
0x18000de59  mov     rax, cs:__security_cookie
0x18000de60  xor     rax, rsp
0x18000de63  mov     [rbp+var_10], rax
0x18000de67  mov     rax, [rcx]
0x18000de6a  xor     r12d, r12d
0x18000de6d  mov     [rbp+var_30], rax
0x18000de71  mov     r15, rcx
0x18000de74  mov     rax, [rdx]
0x18000de77  lea     rcx, [rbp+var_30]
0x18000de7b  mov     [rbp+var_28], rax
0x18000de7f  mov     esi, r12d
0x18000de82  mov     rax, [r8]
0x18000de85  mov     [rbp+var_20], rax
0x18000de89  mov     rax, [r9]
0x18000de8c  mov     [rbp+var_18], rax
0x18000de90  mov     rdx, [rcx]
0x18000de93  test    rdx, rdx
0x18000de96  jz      short loc_18000DEA8
0x18000de98  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000de9c  inc     rax
0x18000de9f  cmp     [rdx+rax*2], r12w
0x18000dea4  jnz     short loc_18000DE9C
0x18000dea6  jmp     short loc_18000DEAB
0x18000dea8  mov     rax, r12
0x18000deab  add     rsi, rax
0x18000deae  add     rcx, 8
0x18000deb2  lea     rax, [rbp+var_10]
0x18000deb6  cmp     rcx, rax
0x18000deb9  jnz     short loc_18000DE90
0x18000debb  mov     r8, rsi
0x18000debe  mov     [rbp+var_40], r12
0x18000dec2  xor     edx, edx
0x18000dec4  lea     rcx, [rbp+lpMem]
0x18000dec8  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x18000decd  mov     rdx, rax
0x18000ded0  lea     rcx, [rbp+var_40]
0x18000ded4  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x18000ded9  mov     rbx, [rbp+lpMem]
0x18000dedd  test    rbx, rbx
0x18000dee0  jz      short loc_18000DEF6
0x18000dee2  call    cs:__imp_GetProcessHeap
0x18000dee8  mov     r8, rbx; lpMem
0x18000deeb  xor     edx, edx; dwFlags
0x18000deed  mov     rcx, rax; hHeap
0x18000def0  call    cs:__imp_HeapFree
0x18000def6  mov     rbx, [rbp+var_40]
0x18000defa  mov     rax, rbx
0x18000defd  neg     rax
0x18000df00  sbb     edi, edi
0x18000df02  not     edi
0x18000df04  and     edi, 8007000Eh
0x18000df0a  test    rbx, rbx
0x18000df0d  jnz     short loc_18000DF29
0x18000df0f  mov     rcx, [rbp+28h]; this
0x18000df13  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000df1a  mov     r9d, edi; char *
0x18000df1d  mov     edx, 737h; void *
0x18000df22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df27  jmp     short loc_18000DF9C
0x18000df29  inc     rsi
0x18000df2c  mov     [rbp+var_40], rbx
0x18000df30  mov     rcx, rbx; wchar_t *
0x18000df33  lea     r14, [rbx+rsi*2]
0x18000df37  lea     rsi, [rbp+var_30]
0x18000df3b  mov     r8, [rsi]; wchar_t *
0x18000df3e  test    r8, r8
0x18000df41  jz      short loc_18000DF5F
0x18000df43  mov     rdx, r14
0x18000df46  lea     r9, [rbp+var_40]; wchar_t **
0x18000df4a  sub     rdx, rcx
0x18000df4d  sar     rdx, 1; unsigned __int64
0x18000df50  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000df55  mov     edi, eax
0x18000df57  test    eax, eax
0x18000df59  js      short loc_18000DFC3
0x18000df5b  mov     rcx, [rbp+var_40]
0x18000df5f  add     rsi, 8
0x18000df63  lea     rax, [rbp+var_10]
0x18000df67  cmp     rsi, rax
0x18000df6a  jnz     short loc_18000DF3B
0x18000df6c  lea     rdx, [rbp+var_40]
0x18000df70  mov     [rbp+var_40], rbx
0x18000df74  mov     rcx, r15
0x18000df77  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x18000df7c  mov     rbx, [rbp+var_40]
0x18000df80  test    rbx, rbx
0x18000df83  jz      short loc_18000DF99
0x18000df85  call    cs:__imp_GetProcessHeap
0x18000df8b  mov     r8, rbx; lpMem
0x18000df8e  xor     edx, edx; dwFlags
0x18000df90  mov     rcx, rax; hHeap
0x18000df93  call    cs:__imp_HeapFree
0x18000df99  mov     edi, r12d
0x18000df9c  mov     eax, edi
0x18000df9e  mov     rcx, [rbp+var_10]
0x18000dfa2  xor     rcx, rsp; StackCookie
0x18000dfa5  call    __security_check_cookie
0x18000dfaa  lea     r11, [rsp+70h+var_s0]
0x18000dfaf  mov     rbx, [r11+38h]
0x18000dfb3  mov     rsi, [r11+40h]
0x18000dfb7  mov     rsp, r11
0x18000dfba  pop     r15
0x18000dfbc  pop     r14
0x18000dfbe  pop     r12
0x18000dfc0  pop     rdi
0x18000dfc1  pop     rbp
0x18000dfc2  retn
0x18000dfc3  mov     rcx, [rbp+28h]; this
0x18000dfc7  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000dfce  mov     r9d, eax; char *
0x18000dfd1  mov     edx, 73Fh; void *
0x18000dfd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dfdb  call    cs:__imp_GetProcessHeap
0x18000dfe1  mov     r8, rbx; lpMem
0x18000dfe4  xor     edx, edx; dwFlags
0x18000dfe6  mov     rcx, rax; hHeap
0x18000dfe9  call    cs:__imp_HeapFree
0x18000dfef  jmp     short loc_18000DF9C
```
