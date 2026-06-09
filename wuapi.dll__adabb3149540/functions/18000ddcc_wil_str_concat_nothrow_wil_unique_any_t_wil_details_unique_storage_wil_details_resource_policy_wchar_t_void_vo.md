# wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> const &)

- ea: `0x18000ddcc`
- end: `0x18000df7d`
- name: `??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@V12@V12@V12@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@AEBV10@11@Z`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d684`

## callees

- `0x180003760`
- `0x1800087e4`
- `0x18000a198`
- `0x18000b108`
- `0x18000ddcc`
- `0x18000fce0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000df1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000df75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000df1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000df75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df67`

## string_xrefs

- `0x18000de9f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x18000df53`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

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
0x18000ddcc  mov     [rsp-28h+arg_8], rbx
0x18000ddd1  mov     [rsp-28h+arg_10], rsi
0x18000ddd6  push    rbp
0x18000ddd7  push    rdi
0x18000ddd8  push    r12
0x18000ddda  push    r14
0x18000dddc  push    r15
0x18000ddde  mov     rbp, rsp
0x18000dde1  sub     rsp, 70h
0x18000dde5  mov     rax, cs:__security_cookie
0x18000ddec  xor     rax, rsp
0x18000ddef  mov     [rbp+var_10], rax
0x18000ddf3  mov     rax, [rcx]
0x18000ddf6  xor     r12d, r12d
0x18000ddf9  mov     [rbp+var_30], rax
0x18000ddfd  mov     r15, rcx
0x18000de00  mov     rax, [rdx]
0x18000de03  lea     rcx, [rbp+var_30]
0x18000de07  mov     [rbp+var_28], rax
0x18000de0b  mov     esi, r12d
0x18000de0e  mov     rax, [r8]
0x18000de11  mov     [rbp+var_20], rax
0x18000de15  mov     rax, [r9]
0x18000de18  mov     [rbp+var_18], rax
0x18000de1c  mov     rdx, [rcx]
0x18000de1f  test    rdx, rdx
0x18000de22  jz      short loc_18000DE34
0x18000de24  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000de28  inc     rax
0x18000de2b  cmp     [rdx+rax*2], r12w
0x18000de30  jnz     short loc_18000DE28
0x18000de32  jmp     short loc_18000DE37
0x18000de34  mov     rax, r12
0x18000de37  add     rsi, rax
0x18000de3a  add     rcx, 8
0x18000de3e  lea     rax, [rbp+var_10]
0x18000de42  cmp     rcx, rax
0x18000de45  jnz     short loc_18000DE1C
0x18000de47  mov     r8, rsi
0x18000de4a  mov     [rbp+var_40], r12
0x18000de4e  xor     edx, edx
0x18000de50  lea     rcx, [rbp+lpMem]
0x18000de54  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x18000de59  mov     rdx, rax
0x18000de5c  lea     rcx, [rbp+var_40]
0x18000de60  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x18000de65  mov     rbx, [rbp+lpMem]
0x18000de69  test    rbx, rbx
0x18000de6c  jz      short loc_18000DE82
0x18000de6e  call    cs:__imp_GetProcessHeap
0x18000de74  mov     r8, rbx; lpMem
0x18000de77  xor     edx, edx; dwFlags
0x18000de79  mov     rcx, rax; hHeap
0x18000de7c  call    cs:__imp_HeapFree
0x18000de82  mov     rbx, [rbp+var_40]
0x18000de86  mov     rax, rbx
0x18000de89  neg     rax
0x18000de8c  sbb     edi, edi
0x18000de8e  not     edi
0x18000de90  and     edi, 8007000Eh
0x18000de96  test    rbx, rbx
0x18000de99  jnz     short loc_18000DEB5
0x18000de9b  mov     rcx, [rbp+28h]; this
0x18000de9f  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000dea6  mov     r9d, edi; char *
0x18000dea9  mov     edx, 737h; void *
0x18000deae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000deb3  jmp     short loc_18000DF28
0x18000deb5  inc     rsi
0x18000deb8  mov     [rbp+var_40], rbx
0x18000debc  mov     rcx, rbx; wchar_t *
0x18000debf  lea     r14, [rbx+rsi*2]
0x18000dec3  lea     rsi, [rbp+var_30]
0x18000dec7  mov     r8, [rsi]; wchar_t *
0x18000deca  test    r8, r8
0x18000decd  jz      short loc_18000DEEB
0x18000decf  mov     rdx, r14
0x18000ded2  lea     r9, [rbp+var_40]; wchar_t **
0x18000ded6  sub     rdx, rcx
0x18000ded9  sar     rdx, 1; unsigned __int64
0x18000dedc  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000dee1  mov     edi, eax
0x18000dee3  test    eax, eax
0x18000dee5  js      short loc_18000DF4F
0x18000dee7  mov     rcx, [rbp+var_40]
0x18000deeb  add     rsi, 8
0x18000deef  lea     rax, [rbp+var_10]
0x18000def3  cmp     rsi, rax
0x18000def6  jnz     short loc_18000DEC7
0x18000def8  lea     rdx, [rbp+var_40]
0x18000defc  mov     [rbp+var_40], rbx
0x18000df00  mov     rcx, r15
0x18000df03  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x18000df08  mov     rbx, [rbp+var_40]
0x18000df0c  test    rbx, rbx
0x18000df0f  jz      short loc_18000DF25
0x18000df11  call    cs:__imp_GetProcessHeap
0x18000df17  mov     r8, rbx; lpMem
0x18000df1a  xor     edx, edx; dwFlags
0x18000df1c  mov     rcx, rax; hHeap
0x18000df1f  call    cs:__imp_HeapFree
0x18000df25  mov     edi, r12d
0x18000df28  mov     eax, edi
0x18000df2a  mov     rcx, [rbp+var_10]
0x18000df2e  xor     rcx, rsp; StackCookie
0x18000df31  call    __security_check_cookie
0x18000df36  lea     r11, [rsp+70h+var_s0]
0x18000df3b  mov     rbx, [r11+38h]
0x18000df3f  mov     rsi, [r11+40h]
0x18000df43  mov     rsp, r11
0x18000df46  pop     r15
0x18000df48  pop     r14
0x18000df4a  pop     r12
0x18000df4c  pop     rdi
0x18000df4d  pop     rbp
0x18000df4e  retn
0x18000df4f  mov     rcx, [rbp+28h]; this
0x18000df53  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000df5a  mov     r9d, eax; char *
0x18000df5d  mov     edx, 73Fh; void *
0x18000df62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df67  call    cs:__imp_GetProcessHeap
0x18000df6d  mov     r8, rbx; lpMem
0x18000df70  xor     edx, edx; dwFlags
0x18000df72  mov     rcx, rax; hHeap
0x18000df75  call    cs:__imp_HeapFree
0x18000df7b  jmp     short loc_18000DF28
```
