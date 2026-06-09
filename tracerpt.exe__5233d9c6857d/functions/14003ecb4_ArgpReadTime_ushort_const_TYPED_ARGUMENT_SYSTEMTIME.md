# ArgpReadTime(ushort const *,TYPED_ARGUMENT<_SYSTEMTIME> *)

- ea: `0x14003ecb4`
- end: `0x14003eea4`
- name: `?ArgpReadTime@@YAJPEBGPEAV?$TYPED_ARGUMENT@U_SYSTEMTIME@@@@@Z`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14003e608`

## callees

- `0x140002bd4`
- `0x14003e564`
- `0x14003ecb4`
- `0x140040130`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003ee7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003ee7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ecef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ee71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ecef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003ee71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003ed00`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003ed00`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x14003ed33`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x14003ed33`

## pseudocode

```c
__int64 __fastcall ArgpReadTime(wchar_t *a1, _WORD *a2)
{
  HANDLE ProcessHeap; // rax
  WCHAR *v5; // rax
  wchar_t *v6; // r14
  signed int v7; // edi
  __int64 v8; // r15
  __int64 v9; // rbx
  int LocaleInfoW; // eax
  __int64 v11; // r8
  __int64 v12; // rax
  wchar_t *v13; // rdx
  wchar_t *v14; // rcx
  wchar_t *v15; // rcx
  wchar_t *v16; // rax
  wchar_t *v17; // rcx
  wchar_t *v18; // rax
  unsigned int i; // ebx
  wchar_t **v20; // r8
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  __int16 v23; // ax
  HANDLE v24; // rax
  _WORD v26[2]; // [rsp+20h] [rbp-38h] BYREF
  __int16 v27; // [rsp+24h] [rbp-34h]
  __int16 v28; // [rsp+28h] [rbp-30h]
  wchar_t Delimiter[2]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v30; // [rsp+34h] [rbp-24h]
  int v31; // [rsp+3Ch] [rbp-1Ch]

  wcscpy(Delimiter, L":");
  v30 = 0;
  v31 = 0;
  ProcessHeap = GetProcessHeap();
  v5 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
  v6 = v5;
  if ( v5 )
  {
    v8 = 8;
    *v5 = 0;
    v9 = 1024;
    LocaleInfoW = GetLocaleInfoW(0x400u, 0x1Eu, v5, 8);
    v11 = 2147483646;
    if ( LocaleInfoW > 1 )
    {
      v12 = 2147483646;
      v13 = Delimiter;
      v14 = v6;
      do
      {
        if ( !v12 )
          break;
        if ( !*v14 )
          break;
        *v13++ = *v14++;
        --v12;
        --v8;
      }
      while ( v8 );
      v15 = v13 - 1;
      v7 = v8 == 0 ? 0x8007007A : 0;
      if ( v8 )
        v15 = v13;
      *v15 = 0;
      if ( !v8 )
        goto LABEL_30;
    }
    v16 = v6;
    do
    {
      if ( !v11 )
        break;
      if ( !*a1 )
        break;
      *v16++ = *a1++;
      --v11;
      --v9;
    }
    while ( v9 );
    v17 = v16 - 1;
    if ( v9 )
      v17 = v16;
    *v17 = 0;
    v7 = v9 == 0 ? 0x8007007A : 0;
    if ( !v9 )
      goto LABEL_30;
    v18 = wcstok_mvcrt_legacy_two_parameter_form(v6, Delimiter, (wchar_t **)v11);
    for ( i = 0; i < 3; ++i )
    {
      if ( !v18 )
        break;
      v7 = ArgpParseNumber(v18, (unsigned int *)&v26[2 * i]);
      if ( v7 < 0 )
        goto LABEL_30;
      v18 = wcstok_mvcrt_legacy_two_parameter_form(0, Delimiter, v20);
    }
    v21 = i - 1;
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( v22 )
      {
        if ( v22 != 1 )
        {
          v7 = -2147024809;
LABEL_30:
          v24 = GetProcessHeap();
          HeapFree(v24, 0, v6);
          return (unsigned int)v7;
        }
        a2[68] = v26[0];
        a2[69] = v27;
        v23 = v28;
      }
      else
      {
        a2[69] = v26[0];
        v23 = v27;
      }
    }
    else
    {
      v23 = v26[0];
    }
    a2[70] = v23;
    goto LABEL_30;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x14003ecb4  push    rbp
0x14003ecb6  push    rbx
0x14003ecb7  push    rsi
0x14003ecb8  push    rdi
0x14003ecb9  push    r12
0x14003ecbb  push    r13
0x14003ecbd  push    r14
0x14003ecbf  push    r15
0x14003ecc1  mov     rbp, rsp
0x14003ecc4  sub     rsp, 58h
0x14003ecc8  mov     rax, cs:__security_cookie
0x14003eccf  xor     rax, rsp
0x14003ecd2  mov     [rbp+var_18], rax
0x14003ecd6  xor     eax, eax
0x14003ecd8  mov     dword ptr [rbp+Delimiter], 3Ah ; ':'
0x14003ecdf  mov     [rbp+var_24], rax
0x14003ece3  mov     rsi, rdx
0x14003ece6  mov     [rbp+var_1C], eax
0x14003ece9  mov     r12, rcx
0x14003ecec  xor     r13d, r13d
0x14003ecef  call    cs:__imp_GetProcessHeap
0x14003ecf5  xor     edx, edx; dwFlags
0x14003ecf7  mov     r8d, 800h; dwBytes
0x14003ecfd  mov     rcx, rax; hHeap
0x14003ed00  call    cs:__imp_HeapAlloc
0x14003ed06  mov     r14, rax
0x14003ed09  test    rax, rax
0x14003ed0c  jnz     short loc_14003ED18
0x14003ed0e  mov     edi, 8007000Eh
0x14003ed13  jmp     loc_14003EE85
0x14003ed18  mov     r15d, 8
0x14003ed1e  mov     [rax], r13w
0x14003ed22  mov     ebx, 400h
0x14003ed27  mov     r9d, r15d; cchData
0x14003ed2a  mov     r8, r14; lpLCData
0x14003ed2d  mov     ecx, ebx; Locale
0x14003ed2f  lea     edx, [r15+16h]; LCType
0x14003ed33  call    cs:__imp_GetLocaleInfoW
0x14003ed39  mov     r8d, 7FFFFFFEh
0x14003ed3f  mov     r10d, 8007007Ah
0x14003ed45  cmp     eax, 1
0x14003ed48  jle     short loc_14003ED9A
0x14003ed4a  mov     eax, r8d
0x14003ed4d  lea     rdx, [rbp+Delimiter]
0x14003ed51  mov     rcx, r14
0x14003ed54  test    rax, rax
0x14003ed57  jz      short loc_14003ED78
0x14003ed59  movzx   r9d, word ptr [rcx]
0x14003ed5d  test    r9w, r9w
0x14003ed61  jz      short loc_14003ED78
0x14003ed63  mov     [rdx], r9w
0x14003ed67  add     rcx, 2
0x14003ed6b  add     rdx, 2
0x14003ed6f  dec     rax
0x14003ed72  sub     r15, 1
0x14003ed76  jnz     short loc_14003ED54
0x14003ed78  mov     rax, r15
0x14003ed7b  lea     rcx, [rdx-2]
0x14003ed7f  neg     rax
0x14003ed82  sbb     edi, edi
0x14003ed84  not     edi
0x14003ed86  and     edi, r10d
0x14003ed89  test    r15, r15
0x14003ed8c  cmovnz  rcx, rdx
0x14003ed90  mov     [rcx], r13w
0x14003ed94  jz      loc_14003EE71
0x14003ed9a  mov     rax, r14
0x14003ed9d  test    r8, r8
0x14003eda0  jz      short loc_14003EDC0
0x14003eda2  movzx   ecx, word ptr [r12]
0x14003eda7  test    cx, cx
0x14003edaa  jz      short loc_14003EDC0
0x14003edac  mov     [rax], cx
0x14003edaf  add     r12, 2
0x14003edb3  add     rax, 2
0x14003edb7  dec     r8; Context
0x14003edba  sub     rbx, 1
0x14003edbe  jnz     short loc_14003ED9D
0x14003edc0  test    rbx, rbx
0x14003edc3  lea     rcx, [rax-2]
0x14003edc7  cmovnz  rcx, rax
0x14003edcb  mov     rax, rbx
0x14003edce  neg     rax
0x14003edd1  sbb     edi, edi
0x14003edd3  not     edi
0x14003edd5  mov     [rcx], r13w
0x14003edd9  and     edi, r10d
0x14003eddc  test    rbx, rbx
0x14003eddf  jz      loc_14003EE71
0x14003ede5  lea     rdx, [rbp+Delimiter]; Delimiter
0x14003ede9  mov     rcx, r14; String
0x14003edec  call    wcstok_mvcrt_legacy_two_parameter_form
0x14003edf1  mov     ebx, r13d
0x14003edf4  test    rax, rax
0x14003edf7  jz      short loc_14003EE23
0x14003edf9  mov     ecx, ebx
0x14003edfb  lea     rdx, [rbp+var_38]
0x14003edff  lea     rdx, [rdx+rcx*4]; unsigned int *
0x14003ee03  mov     rcx, rax; psz
0x14003ee06  call    ?ArgpParseNumber@@YAJPEBGPEAK@Z; ArgpParseNumber(ushort const *,ulong *)
0x14003ee0b  mov     edi, eax
0x14003ee0d  test    eax, eax
0x14003ee0f  js      short loc_14003EE71
0x14003ee11  lea     rdx, [rbp+Delimiter]; Delimiter
0x14003ee15  xor     ecx, ecx; String
0x14003ee17  inc     ebx
0x14003ee19  call    wcstok_mvcrt_legacy_two_parameter_form
0x14003ee1e  cmp     ebx, 3
0x14003ee21  jb      short loc_14003EDF4
0x14003ee23  sub     ebx, 1
0x14003ee26  jz      short loc_14003EE66
0x14003ee28  sub     ebx, 1
0x14003ee2b  jz      short loc_14003EE55
0x14003ee2d  cmp     ebx, 1
0x14003ee30  jz      short loc_14003EE39
0x14003ee32  mov     edi, 80070057h
0x14003ee37  jmp     short loc_14003EE71
0x14003ee39  movzx   eax, [rbp+var_38]
0x14003ee3d  mov     [rsi+88h], ax
0x14003ee44  movzx   eax, [rbp+var_34]
0x14003ee48  mov     [rsi+8Ah], ax
0x14003ee4f  movzx   eax, [rbp+var_30]
0x14003ee53  jmp     short loc_14003EE6A
0x14003ee55  movzx   eax, [rbp+var_38]
0x14003ee59  mov     [rsi+8Ah], ax
0x14003ee60  movzx   eax, [rbp+var_34]
0x14003ee64  jmp     short loc_14003EE6A
0x14003ee66  movzx   eax, [rbp+var_38]
0x14003ee6a  mov     [rsi+8Ch], ax
0x14003ee71  call    cs:__imp_GetProcessHeap
0x14003ee77  mov     r8, r14; lpMem
0x14003ee7a  xor     edx, edx; dwFlags
0x14003ee7c  mov     rcx, rax; hHeap
0x14003ee7f  call    cs:__imp_HeapFree
0x14003ee85  mov     eax, edi
0x14003ee87  mov     rcx, [rbp+var_18]
0x14003ee8b  xor     rcx, rsp; StackCookie
0x14003ee8e  call    __security_check_cookie
0x14003ee93  add     rsp, 58h
0x14003ee97  pop     r15
0x14003ee99  pop     r14
0x14003ee9b  pop     r13
0x14003ee9d  pop     r12
0x14003ee9f  pop     rdi
0x14003eea0  pop     rsi
0x14003eea1  pop     rbx
0x14003eea2  pop     rbp
0x14003eea3  retn
```
