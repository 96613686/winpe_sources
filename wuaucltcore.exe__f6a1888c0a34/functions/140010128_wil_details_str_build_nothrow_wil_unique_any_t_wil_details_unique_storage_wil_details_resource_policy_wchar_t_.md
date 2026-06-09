# wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x140010128`
- end: `0x1400102e1`
- name: `??$str_build_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEB_WPEB_WPEB_WPEB_W@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W111@Z`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f9d0`

## callees

- `0x140002ac0`
- `0x1400092bc`
- `0x14000b224`
- `0x14000cff8`
- `0x140010128`
- `0x14001aa60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400101d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010283`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400102d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400101d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010283`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400102d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400101c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010275`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400102cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400101c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010275`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400102cb`

## string_xrefs

- `0x1400101f3`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1400102b7`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v6; // rsi
  _QWORD *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  void *v10; // rbx
  HANDLE ProcessHeap; // rax
  STRSAFE_LPWSTR v12; // rbx
  unsigned int v13; // edi
  wchar_t *v14; // rcx
  wchar_t *v15; // r14
  const wchar_t **v16; // rsi
  int v17; // eax
  STRSAFE_LPWSTR v18; // rbx
  HANDLE v19; // rax
  HANDLE v21; // rax
  int v22; // [rsp+20h] [rbp-50h]
  int v23; // [rsp+20h] [rbp-50h]
  STRSAFE_LPWSTR pszDest; // [rsp+30h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v26[4]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v27[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v26[3] = a5;
  v6 = 0;
  v26[0] = a2;
  v26[1] = a3;
  v7 = v26;
  v26[2] = a4;
  do
  {
    if ( *v7 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)(*v7 + 2 * v8) );
    }
    else
    {
      v8 = 0;
    }
    v6 += v8;
    ++v7;
  }
  while ( v7 != v27 );
  pszDest = 0;
  v9 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
         &lpMem,
         0,
         v6);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
    &pszDest,
    v9);
  v10 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  v12 = pszDest;
  v13 = pszDest == 0 ? 0x8007000E : 0;
  if ( pszDest )
  {
    v14 = pszDest;
    v15 = &pszDest[v6 + 1];
    v16 = (const wchar_t **)v26;
    do
    {
      if ( *v16 )
      {
        v17 = StringCchCopyExW(v14, v15 - v14, *v16, &pszDest, 0, 0x100u);
        v13 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x73F,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v17,
            v23);
          v21 = GetProcessHeap();
          HeapFree(v21, 0, v12);
          return v13;
        }
        v14 = pszDest;
      }
      ++v16;
    }
    while ( v16 != v27 );
    pszDest = v12;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
      a1,
      &pszDest);
    v18 = pszDest;
    if ( pszDest )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v18);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x737,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)v13,
      v22);
  }
  return v13;
}

```

## disassembly

```asm
0x140010128  mov     [rsp-28h+arg_8], rbx
0x14001012d  mov     [rsp-28h+arg_10], rsi
0x140010132  push    rbp
0x140010133  push    rdi
0x140010134  push    r12
0x140010136  push    r14
0x140010138  push    r15
0x14001013a  mov     rbp, rsp
0x14001013d  sub     rsp, 70h
0x140010141  mov     rax, cs:__security_cookie
0x140010148  xor     rax, rsp
0x14001014b  mov     [rbp+var_10], rax
0x14001014f  mov     rax, [rbp+arg_20]
0x140010153  xor     r12d, r12d
0x140010156  mov     r15, rcx
0x140010159  mov     [rbp+var_18], rax
0x14001015d  mov     esi, r12d
0x140010160  mov     [rbp+var_30], rdx
0x140010164  mov     [rbp+var_28], r8
0x140010168  lea     rcx, [rbp+var_30]
0x14001016c  mov     [rbp+var_20], r9
0x140010170  mov     rdx, [rcx]
0x140010173  test    rdx, rdx
0x140010176  jz      short loc_140010188
0x140010178  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001017c  inc     rax
0x14001017f  cmp     [rdx+rax*2], r12w
0x140010184  jnz     short loc_14001017C
0x140010186  jmp     short loc_14001018B
0x140010188  mov     rax, r12
0x14001018b  add     rsi, rax
0x14001018e  add     rcx, 8
0x140010192  lea     rax, [rbp+var_10]
0x140010196  cmp     rcx, rax
0x140010199  jnz     short loc_140010170
0x14001019b  mov     r8, rsi
0x14001019e  mov     [rbp+pszDest], r12
0x1400101a2  xor     edx, edx
0x1400101a4  lea     rcx, [rbp+lpMem]
0x1400101a8  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x1400101ad  mov     rdx, rax
0x1400101b0  lea     rcx, [rbp+pszDest]
0x1400101b4  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x1400101b9  mov     rbx, [rbp+lpMem]
0x1400101bd  test    rbx, rbx
0x1400101c0  jz      short loc_1400101D6
0x1400101c2  call    cs:__imp_GetProcessHeap
0x1400101c8  mov     r8, rbx; lpMem
0x1400101cb  xor     edx, edx; dwFlags
0x1400101cd  mov     rcx, rax; hHeap
0x1400101d0  call    cs:__imp_HeapFree
0x1400101d6  mov     rbx, [rbp+pszDest]
0x1400101da  mov     rax, rbx
0x1400101dd  neg     rax
0x1400101e0  sbb     edi, edi
0x1400101e2  not     edi
0x1400101e4  and     edi, 8007000Eh
0x1400101ea  test    rbx, rbx
0x1400101ed  jnz     short loc_14001020C
0x1400101ef  mov     rcx, [rbp+28h]; this
0x1400101f3  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1400101fa  mov     r9d, edi; char *
0x1400101fd  mov     edx, 737h; void *
0x140010202  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010207  jmp     loc_14001028C
0x14001020c  inc     rsi
0x14001020f  mov     [rbp+pszDest], rbx
0x140010213  mov     rcx, rbx; pszDest
0x140010216  lea     r14, [rbx+rsi*2]
0x14001021a  lea     rsi, [rbp+var_30]
0x14001021e  mov     r8, [rsi]; wchar_t *
0x140010221  test    r8, r8
0x140010224  jz      short loc_14001024F
0x140010226  mov     rdx, r14
0x140010229  mov     [rsp+70h+var_48], 100h; unsigned int
0x140010231  sub     rdx, rcx
0x140010234  mov     [rsp+70h+var_50], r12; int
0x140010239  sar     rdx, 1; unsigned __int64
0x14001023c  lea     r9, [rbp+pszDest]; wchar_t **
0x140010240  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x140010245  mov     edi, eax
0x140010247  test    eax, eax
0x140010249  js      short loc_1400102B3
0x14001024b  mov     rcx, [rbp+pszDest]
0x14001024f  add     rsi, 8
0x140010253  lea     rax, [rbp+var_10]
0x140010257  cmp     rsi, rax
0x14001025a  jnz     short loc_14001021E
0x14001025c  lea     rdx, [rbp+pszDest]
0x140010260  mov     [rbp+pszDest], rbx
0x140010264  mov     rcx, r15
0x140010267  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x14001026c  mov     rbx, [rbp+pszDest]
0x140010270  test    rbx, rbx
0x140010273  jz      short loc_140010289
0x140010275  call    cs:__imp_GetProcessHeap
0x14001027b  mov     r8, rbx; lpMem
0x14001027e  xor     edx, edx; dwFlags
0x140010280  mov     rcx, rax; hHeap
0x140010283  call    cs:__imp_HeapFree
0x140010289  mov     edi, r12d
0x14001028c  mov     eax, edi
0x14001028e  mov     rcx, [rbp+var_10]
0x140010292  xor     rcx, rsp; StackCookie
0x140010295  call    __security_check_cookie
0x14001029a  lea     r11, [rsp+70h+var_s0]
0x14001029f  mov     rbx, [r11+38h]
0x1400102a3  mov     rsi, [r11+40h]
0x1400102a7  mov     rsp, r11
0x1400102aa  pop     r15
0x1400102ac  pop     r14
0x1400102ae  pop     r12
0x1400102b0  pop     rdi
0x1400102b1  pop     rbp
0x1400102b2  retn
0x1400102b3  mov     rcx, [rbp+28h]; this
0x1400102b7  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1400102be  mov     r9d, eax; char *
0x1400102c1  mov     edx, 73Fh; void *
0x1400102c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400102cb  call    cs:__imp_GetProcessHeap
0x1400102d1  mov     r8, rbx; lpMem
0x1400102d4  xor     edx, edx; dwFlags
0x1400102d6  mov     rcx, rax; hHeap
0x1400102d9  call    cs:__imp_HeapFree
0x1400102df  jmp     short loc_14001028C
```
