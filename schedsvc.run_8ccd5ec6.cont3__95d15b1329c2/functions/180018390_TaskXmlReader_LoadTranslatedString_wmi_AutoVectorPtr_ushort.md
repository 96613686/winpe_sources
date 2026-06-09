# TaskXmlReader::LoadTranslatedString(wmi::AutoVectorPtr<ushort> &)

- ea: `0x180018390`
- end: `0x180018898`
- name: `?LoadTranslatedString@TaskXmlReader@@SAJAEAV?$AutoVectorPtr@G@wmi@@@Z`
- size: `1288`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x1800188a0`

## callees

- `0x18000cc40`
- `0x180018390`
- `0x18005a2bc`

## import_xrefs

- `msvcrt!wcschr` at `0x1800183f8`
- `msvcrt!wcschr` at `0x180018410`
- `msvcrt!wcschr` at `0x1800183f8`
- `msvcrt!wcschr` at `0x180018410`
- `msvcrt!_wtol` at `0x1800185b3`
- `msvcrt!_wtol` at `0x1800185b3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001869a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018864`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001869a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018864`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018624`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018624`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180018676`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180018676`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800186b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800186cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800186e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018710`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800186b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800186cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800186e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018710`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018466`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001852a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800185d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001864f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018466`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001852a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800185d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001864f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180018605`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180018605`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TaskXmlReader::LoadTranslatedString(const wchar_t **a1)
{
  const wchar_t *v2; // rcx
  __int64 v3; // rsi
  wchar_t *v4; // rbx
  wchar_t *v5; // rax
  wchar_t *v6; // r14
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rdi
  SIZE_T v9; // rax
  WCHAR *v10; // rax
  WCHAR *v11; // r9
  WCHAR *v12; // rcx
  WCHAR *v13; // rdx
  int v14; // r12d
  int v15; // r8d
  WCHAR v16; // ax
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // rdi
  SIZE_T v19; // rax
  _WORD *v20; // rax
  void *v21; // r15
  __int16 *v22; // rcx
  _WORD *v23; // rdx
  __int16 v24; // ax
  UINT v25; // r14d
  WCHAR *v26; // rax
  WCHAR *v27; // rbx
  HMODULE Library; // rdi
  WCHAR *v29; // rax
  WCHAR *v30; // rsi
  WCHAR *v32; // rcx
  void **pExceptionObject; // [rsp+28h] [rbp-40h] BYREF
  char v34; // [rsp+30h] [rbp-38h]
  const unsigned __int16 *v35; // [rsp+38h] [rbp-30h]
  __int64 v36; // [rsp+40h] [rbp-28h]
  __int64 v37; // [rsp+48h] [rbp-20h]
  int v38; // [rsp+50h] [rbp-18h]
  __int64 v39; // [rsp+54h] [rbp-14h]
  WCHAR *lpSrc; // [rsp+B0h] [rbp+48h]

  v2 = *a1;
  v3 = -1;
  do
    ++v3;
  while ( v2[v3] );
  if ( (unsigned int)v3 < 8 )
    return 1;
  if ( *v2 != 36 )
    return 1;
  if ( v2[1] != 40 )
    return 1;
  if ( v2[2] != 64 )
    return 1;
  v4 = wcschr(v2, 0x2Cu);
  v5 = wcschr(*a1, 0x2Du);
  v6 = v5;
  if ( !v4 || !v5 || (char *)v5 - (char *)v4 != 2 )
    return 1;
  v7 = v4 - *a1 - 3;
  v8 = v7 + 1;
  v9 = 2 * (v7 + 1);
  if ( !is_mul_ok(v7 + 1, 2u) )
    v9 = -1;
  v10 = (WCHAR *)HeapAlloc(g_PrivateHeap, 0, v9);
  v11 = v10;
  lpSrc = v10;
  if ( !v10 )
  {
    v34 = 0;
    v35 = &qword_1800A8718;
    v36 = 0;
    v37 = 0;
    v38 = 14;
    v39 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  if ( v7 == -1 )
    goto LABEL_48;
  if ( v8 > 0x7FFFFFFF || v7 > 0x7FFFFFFE )
  {
    *v10 = 0;
LABEL_48:
    v32 = v11;
    goto LABEL_46;
  }
  v12 = (WCHAR *)(*a1 + 3);
  v13 = v10;
  v14 = 0;
  v15 = 0;
  while ( v7 )
  {
    v16 = *v12;
    if ( !*v12 )
    {
      if ( !v8 )
      {
LABEL_20:
        --v13;
        v15 = -2147024774;
        break;
      }
      break;
    }
    ++v12;
    *v13++ = v16;
    --v7;
    if ( !--v8 )
      goto LABEL_20;
  }
  *v13 = 0;
  if ( v15 < 0 )
    goto LABEL_48;
  v17 = (unsigned int)v3 - (v6 - *a1);
  v18 = v17 + 1;
  v19 = 2 * (v17 + 1);
  if ( !is_mul_ok(v17 + 1, 2u) )
    v19 = -1;
  v20 = HeapAlloc(g_PrivateHeap, 0, v19);
  v21 = v20;
  if ( !v20 )
  {
    v34 = 0;
    v35 = &qword_1800A8718;
    v36 = 0;
    v37 = 0;
    v38 = 14;
    v39 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  if ( v17 == -1 )
    goto LABEL_45;
  if ( v18 > 0x7FFFFFFF || v17 > 0x7FFFFFFE )
  {
    *v20 = 0;
LABEL_45:
    operator delete(v21);
    v32 = lpSrc;
LABEL_46:
    operator delete(v32);
    return 1;
  }
  v22 = (__int16 *)(v6 + 1);
  v23 = v20;
  while ( v17 )
  {
    v24 = *v22;
    if ( !*v22 )
    {
      if ( !v18 )
      {
LABEL_33:
        --v23;
        v14 = -2147024774;
        break;
      }
      break;
    }
    ++v22;
    *v23++ = v24;
    --v17;
    if ( !--v18 )
      goto LABEL_33;
  }
  *v23 = 0;
  if ( v14 < 0 )
    goto LABEL_45;
  v25 = _wtol((const wchar_t *)v21);
  if ( !v25 )
    goto LABEL_45;
  v26 = (WCHAR *)HeapAlloc(g_PrivateHeap, 0, 0x208u);
  v27 = v26;
  if ( !v26 )
  {
    v34 = 0;
    v35 = &qword_1800A8718;
    v36 = 0;
    v37 = 0;
    v38 = 14;
    v39 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  if ( !ExpandEnvironmentStringsW(lpSrc, v26, 0x103u) || (Library = LoadLibraryExW(v27, 0, 2u)) == 0 )
  {
    operator delete(v27);
    operator delete(v21);
    v32 = lpSrc;
    goto LABEL_46;
  }
  v29 = (WCHAR *)HeapAlloc(g_PrivateHeap, 0, 0xA000u);
  v30 = v29;
  if ( !v29 )
  {
    v34 = 0;
    v35 = &qword_1800A8718;
    v36 = 0;
    v37 = 0;
    v38 = 14;
    v39 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  if ( !LoadStringW(Library, v25, v29, 20479) )
  {
    operator delete(v30);
    FreeLibrary(Library);
    operator delete(v27);
    goto LABEL_45;
  }
  if ( *a1 )
    HeapFree(g_PrivateHeap, 0, (LPVOID)*a1);
  *a1 = v30;
  FreeLibrary(Library);
  HeapFree(g_PrivateHeap, 0, v27);
  HeapFree(g_PrivateHeap, 0, v21);
  HeapFree(g_PrivateHeap, 0, lpSrc);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180018390  push    rbp
0x180018392  push    rbx
0x180018393  push    rsi
0x180018394  push    rdi
0x180018395  push    r12
0x180018397  push    r13
0x180018399  push    r14
0x18001839b  push    r15
0x18001839d  mov     rbp, rsp
0x1800183a0  sub     rsp, 68h
0x1800183a4  mov     r13, rcx
0x1800183a7  mov     rcx, [rcx]; Str
0x1800183aa  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800183b1  mov     rsi, r15
0x1800183b4  inc     rsi
0x1800183b7  cmp     word ptr [rcx+rsi*2], 0
0x1800183bc  jnz     short loc_1800183B4
0x1800183be  cmp     esi, 8
0x1800183c1  jb      loc_180018733
0x1800183c7  mov     eax, 24h ; '$'
0x1800183cc  cmp     ax, [rcx]
0x1800183cf  jnz     loc_180018733
0x1800183d5  mov     eax, 28h ; '('
0x1800183da  cmp     ax, [rcx+2]
0x1800183de  jnz     loc_180018733
0x1800183e4  mov     eax, 40h ; '@'
0x1800183e9  cmp     ax, [rcx+4]
0x1800183ed  jnz     loc_180018733
0x1800183f3  mov     edx, 2Ch ; ','; Ch
0x1800183f8  call    cs:__imp_wcschr
0x1800183ff  nop     dword ptr [rax+rax+00h]
0x180018404  mov     rbx, rax
0x180018407  mov     edx, 2Dh ; '-'; Ch
0x18001840c  mov     rcx, [r13+0]; Str
0x180018410  call    cs:__imp_wcschr
0x180018417  nop     dword ptr [rax+rax+00h]
0x18001841c  mov     r14, rax
0x18001841f  test    rbx, rbx
0x180018422  jz      loc_180018733
0x180018428  test    rax, rax
0x18001842b  jz      loc_180018733
0x180018431  mov     rcx, rax
0x180018434  sub     rcx, rbx
0x180018437  cmp     rcx, 2
0x18001843b  jnz     loc_180018733
0x180018441  sub     rbx, [r13+0]
0x180018445  sar     rbx, 1
0x180018448  add     rbx, 0FFFFFFFFFFFFFFFDh
0x18001844c  lea     rdi, [rbx+1]
0x180018450  mov     rax, rcx
0x180018453  mul     rdi
0x180018456  cmovb   rax, r15
0x18001845a  mov     r8, rax; dwBytes
0x18001845d  xor     edx, edx; dwFlags
0x18001845f  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180018466  call    cs:__imp_HeapAlloc
0x18001846d  nop     dword ptr [rax+rax+00h]
0x180018472  mov     r9, rax
0x180018475  mov     [rbp+lpSrc], rax
0x180018479  test    rax, rax
0x18001847c  jz      loc_18001873F
0x180018482  mov     [rbp+arg_8], rax
0x180018486  test    rdi, rdi
0x180018489  jz      loc_18001873A
0x18001848f  cmp     rdi, 7FFFFFFFh
0x180018496  ja      loc_18001877F
0x18001849c  cmp     rbx, 7FFFFFFEh
0x1800184a3  ja      loc_18001877F
0x1800184a9  mov     rcx, [r13+0]
0x1800184ad  add     rcx, 6
0x1800184b1  mov     rdx, rax
0x1800184b4  xor     r12d, r12d
0x1800184b7  mov     r8d, r12d
0x1800184ba  nop     word ptr [rax+rax+00h]
0x1800184c0  test    rbx, rbx
0x1800184c3  jz      short loc_1800184F2
0x1800184c5  movzx   eax, word ptr [rcx]
0x1800184c8  test    ax, ax
0x1800184cb  jz      short loc_1800184ED
0x1800184cd  add     rcx, 2
0x1800184d1  mov     [rdx], ax
0x1800184d4  add     rdx, 2
0x1800184d8  dec     rbx
0x1800184db  sub     rdi, 1
0x1800184df  jnz     short loc_1800184C0
0x1800184e1  sub     rdx, 2
0x1800184e5  mov     r8d, 8007007Ah
0x1800184eb  jmp     short loc_1800184F2
0x1800184ed  test    rdi, rdi
0x1800184f0  jz      short loc_1800184E1
0x1800184f2  mov     [rdx], r12w
0x1800184f6  test    r8d, r8d
0x1800184f9  js      loc_18001873A
0x1800184ff  mov     rax, r14
0x180018502  sub     rax, [r13+0]
0x180018506  sar     rax, 1
0x180018509  mov     ebx, esi
0x18001850b  sub     rbx, rax
0x18001850e  lea     rdi, [rbx+1]
0x180018512  mov     eax, 2
0x180018517  mul     rdi
0x18001851a  cmovb   rax, r15
0x18001851e  mov     r8, rax; dwBytes
0x180018521  xor     edx, edx; dwFlags
0x180018523  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18001852a  call    cs:__imp_HeapAlloc
0x180018531  nop     dword ptr [rax+rax+00h]
0x180018536  mov     r15, rax
0x180018539  test    rax, rax
0x18001853c  jz      loc_180018787
0x180018542  mov     [rbp+arg_10], rax
0x180018546  test    rdi, rdi
0x180018549  jz      loc_180018721
0x18001854f  cmp     rdi, 7FFFFFFFh
0x180018556  ja      loc_1800187C9
0x18001855c  cmp     rbx, 7FFFFFFEh
0x180018563  ja      loc_1800187C9
0x180018569  lea     rcx, [r14+2]
0x18001856d  mov     rdx, rax
0x180018570  test    rbx, rbx
0x180018573  jz      short loc_1800185A2
0x180018575  movzx   eax, word ptr [rcx]
0x180018578  test    ax, ax
0x18001857b  jz      short loc_18001859D
0x18001857d  add     rcx, 2
0x180018581  mov     [rdx], ax
0x180018584  add     rdx, 2
0x180018588  dec     rbx
0x18001858b  sub     rdi, 1
0x18001858f  jnz     short loc_180018570
0x180018591  sub     rdx, 2
0x180018595  mov     r12d, 8007007Ah
0x18001859b  jmp     short loc_1800185A2
0x18001859d  test    rdi, rdi
0x1800185a0  jz      short loc_180018591
0x1800185a2  xor     edi, edi
0x1800185a4  mov     [rdx], di
0x1800185a7  test    r12d, r12d
0x1800185aa  js      loc_180018721
0x1800185b0  mov     rcx, r15; String
0x1800185b3  call    cs:__imp__wtol
0x1800185ba  nop     dword ptr [rax+rax+00h]
0x1800185bf  mov     r14d, eax
0x1800185c2  test    eax, eax
0x1800185c4  jz      loc_180018721
0x1800185ca  xor     edx, edx; dwFlags
0x1800185cc  mov     r8d, 208h; dwBytes
0x1800185d2  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800185d9  call    cs:__imp_HeapAlloc
0x1800185e0  nop     dword ptr [rax+rax+00h]
0x1800185e5  mov     rbx, rax
0x1800185e8  test    rax, rax
0x1800185eb  jz      loc_1800187D2
0x1800185f1  mov     [rbp+arg_18], rax
0x1800185f5  mov     r8d, 103h; nSize
0x1800185fb  mov     rdx, rax; lpDst
0x1800185fe  mov     rsi, [rbp+lpSrc]
0x180018602  mov     rcx, rsi; lpSrc
0x180018605  call    cs:__imp_ExpandEnvironmentStringsW
0x18001860c  nop     dword ptr [rax+rax+00h]
0x180018611  test    eax, eax
0x180018613  jz      loc_18001887E
0x180018619  xor     edx, edx; hFile
0x18001861b  mov     r8d, 2; dwFlags
0x180018621  mov     rcx, rbx; lpLibFileName
0x180018624  call    cs:__imp_LoadLibraryExW
0x18001862b  nop     dword ptr [rax+rax+00h]
0x180018630  mov     rdi, rax
0x180018633  test    rax, rax
0x180018636  jz      loc_18001887E
0x18001863c  mov     [rbp+var_48], rax
0x180018640  xor     edx, edx; dwFlags
0x180018642  mov     r8d, 0A000h; dwBytes
0x180018648  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18001864f  call    cs:__imp_HeapAlloc
0x180018656  nop     dword ptr [rax+rax+00h]
0x18001865b  mov     rsi, rax
0x18001865e  test    rax, rax
0x180018661  jz      loc_180018814
0x180018667  mov     r9d, 4FFFh; cchBufferMax
0x18001866d  mov     r8, rax; lpBuffer
0x180018670  mov     edx, r14d; uID
0x180018673  mov     rcx, rdi; hInstance
0x180018676  call    cs:__imp_LoadStringW
0x18001867d  nop     dword ptr [rax+rax+00h]
0x180018682  test    eax, eax
0x180018684  jz      loc_180018858
0x18001868a  mov     r8, [r13+0]; lpMem
0x18001868e  test    r8, r8
0x180018691  jnz     short loc_180018707
0x180018693  mov     [r13+0], rsi
0x180018697  mov     rcx, rdi; hLibModule
0x18001869a  call    cs:__imp_FreeLibrary
0x1800186a1  nop     dword ptr [rax+rax+00h]
0x1800186a6  nop
0x1800186a7  mov     r8, rbx; lpMem
0x1800186aa  xor     edx, edx; dwFlags
0x1800186ac  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800186b3  call    cs:__imp_HeapFree
0x1800186ba  nop     dword ptr [rax+rax+00h]
0x1800186bf  nop
0x1800186c0  mov     r8, r15; lpMem
0x1800186c3  xor     edx, edx; dwFlags
0x1800186c5  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800186cc  call    cs:__imp_HeapFree
0x1800186d3  nop     dword ptr [rax+rax+00h]
0x1800186d8  nop
0x1800186d9  mov     r8, [rbp+lpSrc]; lpMem
0x1800186dd  xor     edx, edx; dwFlags
0x1800186df  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800186e6  call    cs:__imp_HeapFree
0x1800186ed  nop     dword ptr [rax+rax+00h]
0x1800186f2  mov     eax, r12d
0x1800186f5  add     rsp, 68h
0x1800186f9  pop     r15
0x1800186fb  pop     r14
0x1800186fd  pop     r13
0x1800186ff  pop     r12
0x180018701  pop     rdi
0x180018702  pop     rsi
0x180018703  pop     rbx
0x180018704  pop     rbp
0x180018705  retn
0x180018707  xor     edx, edx; dwFlags
0x180018709  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180018710  call    cs:__imp_HeapFree
0x180018717  nop     dword ptr [rax+rax+00h]
0x18001871c  jmp     loc_180018693
0x180018721  mov     rcx, r15; void *
0x180018724  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018729  nop
0x18001872a  mov     rcx, [rbp+lpSrc]; void *
0x18001872e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018733  mov     eax, 1
0x180018738  jmp     short loc_1800186F5
0x18001873a  mov     rcx, r9
0x18001873d  jmp     short loc_18001872E
0x18001873f  mov     [rbp+var_38], 0
0x180018743  lea     rax, qword_1800A8718
0x18001874a  mov     [rbp+var_30], rax
0x18001874e  xor     eax, eax
0x180018750  mov     [rbp+var_28], rax
0x180018754  mov     [rbp+var_20], rax
0x180018758  mov     [rbp+var_18], 0Eh
0x18001875f  mov     [rbp+var_14], r15
0x180018763  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001876a  mov     [rbp+pExceptionObject], rax
0x18001876e  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180018775  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180018779  call    _CxxThrowException_0
0x18001877f  xor     eax, eax
0x180018781  mov     [r9], ax
0x180018785  jmp     short loc_18001873A
0x180018787  mov     [rbp+var_38], r12b
0x18001878b  lea     rax, qword_1800A8718
0x180018792  mov     [rbp+var_30], rax
0x180018796  mov     [rbp+var_28], r12
0x18001879a  mov     [rbp+var_20], r12
0x18001879e  mov     [rbp+var_18], 0Eh
0x1800187a5  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x1800187ad  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800187b4  mov     [rbp+pExceptionObject], rax
0x1800187b8  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x1800187bf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800187c3  call    _CxxThrowException_0
0x1800187c9  mov     [rax], r12w
0x1800187cd  jmp     loc_180018721
0x1800187d2  mov     [rbp+var_38], dil
0x1800187d6  lea     rax, qword_1800A8718
0x1800187dd  mov     [rbp+var_30], rax
0x1800187e1  mov     [rbp+var_28], rdi
0x1800187e5  mov     [rbp+var_20], rdi
0x1800187e9  mov     [rbp+var_18], 0Eh
0x1800187f0  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x1800187f8  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800187ff  mov     [rbp+pExceptionObject], rax
0x180018803  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001880a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001880e  call    _CxxThrowException_0
0x180018814  mov     [rbp+var_38], 0
0x180018818  lea     rax, qword_1800A8718
0x18001881f  mov     [rbp+var_30], rax
0x180018823  xor     eax, eax
0x180018825  mov     [rbp+var_28], rax
0x180018829  mov     [rbp+var_20], rax
0x18001882d  mov     [rbp+var_18], 0Eh
0x180018834  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001883c  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180018843  mov     [rbp+pExceptionObject], rax
0x180018847  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001884e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180018852  call    _CxxThrowException_0
0x180018858  mov     rcx, rsi; void *
0x18001885b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018860  nop
0x180018861  mov     rcx, rdi; hLibModule
0x180018864  call    cs:__imp_FreeLibrary
0x18001886b  nop     dword ptr [rax+rax+00h]
0x180018870  nop
0x180018871  mov     rcx, rbx; void *
  ... truncated ...
```
