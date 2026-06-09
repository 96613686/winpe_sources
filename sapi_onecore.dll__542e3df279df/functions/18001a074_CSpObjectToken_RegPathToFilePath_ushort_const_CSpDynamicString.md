# CSpObjectToken::RegPathToFilePath(ushort const *,CSpDynamicString &)

- ea: `0x18001a074`
- end: `0x18001a3a0`
- name: `?RegPathToFilePath@CSpObjectToken@@AEAAJPEBGAEAVCSpDynamicString@@@Z`
- size: `812`
- prototype: `int(CSpObjectToken *__hidden this, const unsigned __int16 *, struct CSpDynamicString *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ee584`
- `0x1800ef150`

## callees

- `0x18000cdb0`
- `0x180016c20`
- `0x18001a074`
- `0x180079e30`
- `0x18007d7b1`
- `0x18025a1e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001a0e5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001a0e5`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001a0b9`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001a0b9`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001a15d`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001a2e9`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001a15d`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001a2e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a14f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a2db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a14f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a2db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a21b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a331`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a33e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a21b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a331`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a33e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a324`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a324`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a1e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a291`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a1e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a291`

## pseudocode

```c
__int64 __fastcall CSpObjectToken::RegPathToFilePath(CSpObjectToken *this, const unsigned __int16 *a2, const void **a3)
{
  unsigned int v5; // esi
  const wchar_t *v6; // rdi
  unsigned int v7; // edx
  int v8; // ecx
  const void *v9; // rdi
  __int64 v10; // r15
  __int64 v11; // rbp
  HANDLE v12; // rax
  SIZE_T v13; // rdx
  unsigned __int64 v14; // rdx
  unsigned __int64 k; // rcx
  _WORD *v16; // rdi
  __int64 j; // rcx
  __int64 v18; // rdi
  SIZE_T v19; // rcx
  const void *v20; // rax
  DWORD v21; // ecx
  wchar_t *v22; // r12
  __int64 v23; // rcx
  _WORD *v24; // rax
  unsigned int v25; // edx
  __int64 v26; // rbx
  __int64 v27; // r15
  unsigned __int64 v28; // rcx
  __int64 v29; // rsi
  char *v30; // rax
  char *v31; // rdi
  size_t v32; // rbx
  void *v33; // rbx
  HANDLE ProcessHeap; // rax
  SIZE_T v35; // rcx
  SIZE_T v36; // rcx
  _WORD *v37; // rdi
  __int64 i; // rcx
  wchar_t *EndPtr; // [rsp+20h] [rbp-268h] BYREF
  unsigned __int16 Src[264]; // [rsp+30h] [rbp-258h] BYREF

  v5 = 0;
  if ( *a2 != 37 )
  {
    CSpDynamicString::operator=(a3, a2);
    if ( *a3 )
      return v5;
    return (unsigned int)-2147024882;
  }
  EndPtr = wcsrchr(a2, 0x25u);
  if ( !EndPtr )
    return (unsigned int)-2147024809;
  v6 = a2 + 1;
  wcstoul(v6, &EndPtr, 16);
  v8 = 0;
  v5 = -2147024809;
  if ( EndPtr == v6 )
    v8 = -2147024809;
  if ( *++EndPtr == 92 )
  {
    Src[0] = 0;
    v5 = v8;
    if ( v8 >= 0 )
    {
      SpGetSharedLexiconFolder(v8, v7, Src);
      v9 = *a3;
      v10 = -1;
      v11 = 8;
      if ( Src == *a3 )
      {
LABEL_31:
        v22 = EndPtr;
        v5 = 0;
        if ( !EndPtr )
          return v5;
        v23 = -1;
        do
          ++v23;
        while ( EndPtr[v23] );
        v24 = *a3;
        if ( (_DWORD)v23 )
        {
          v25 = 0;
          if ( v24 )
          {
            do
              ++v10;
            while ( v24[v10] );
            v25 = v10;
          }
          v26 = v25;
          v27 = (unsigned int)v23;
          v28 = v25 + (unsigned __int64)(unsigned int)v23;
          if ( v28 > v25 )
          {
            if ( (unsigned int)v28 < 0x4FFFFFFF )
            {
              v29 = (unsigned int)v28;
              if ( 2 * (unsigned __int64)(unsigned int)(v28 + 1) > (unsigned int)v28 )
              {
                v30 = (char *)CoTaskMemAlloc(2LL * (unsigned int)(v28 + 1));
                v31 = v30;
                if ( v30 )
                {
                  *(_WORD *)&v30[2 * v29] = 0;
                  v32 = 2 * v26;
                  v5 = 0;
                  memcpy_0(v30, *a3, v32);
                  memcpy_0(&v31[v32], v22, 2 * v27);
                  v33 = (void *)*a3;
                  *a3 = v31;
                  if ( v33 )
                  {
                    ProcessHeap = GetProcessHeap();
                    v35 = HeapSize(ProcessHeap, 0, v33);
                    if ( v35 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
                    {
                      v36 = v35 >> 1;
                      if ( v36 - 1 >= 8 || (v11 = v36 - 1, v36 != 1) )
                      {
                        v37 = v33;
                        for ( i = v11; i; --i )
                          *v37++ = -8531;
                      }
                    }
                    CoTaskMemFree(v33);
                  }
                  return v5;
                }
                SetLastError(0xEu);
                return (unsigned int)-2147024882;
              }
            }
            SetLastError(0x216u);
          }
          return (unsigned int)-2147024362;
        }
        if ( !v24 )
          return (unsigned int)CSpDynamicString::_allocate((CSpDynamicString *)a3, 0);
        return v5;
      }
      if ( !v9 )
      {
LABEL_22:
        v18 = -1;
        do
          ++v18;
        while ( Src[v18] );
        if ( (unsigned int)v18 >= 0x4FFFFFFF || (v19 = 2LL * (unsigned int)(v18 + 1), v19 <= (unsigned int)v18) )
        {
          v21 = 534;
        }
        else
        {
          v20 = CoTaskMemAlloc(v19);
          *a3 = v20;
          if ( v20 )
          {
            *((_WORD *)v20 + (unsigned int)v18) = 0;
            memcpy_0((void *)*a3, Src, 2 * v18);
            goto LABEL_31;
          }
          v21 = 14;
        }
        SetLastError(v21);
        goto LABEL_31;
      }
      v12 = GetProcessHeap();
      v13 = HeapSize(v12, 0, v9);
      if ( v13 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
      {
        v14 = (v13 >> 1) - 1;
        if ( v14 >= 8 )
        {
          v16 = *a3;
          if ( *a3 > a3 || (k = 0, v14 = 8, v16 + 7 < (_WORD *)a3) )
          {
            for ( j = 8; j; --j )
              *v16++ = -8531;
            goto LABEL_21;
          }
          goto LABEL_16;
        }
        if ( v14 )
        {
          for ( k = 0; k < v14; ++k )
LABEL_16:
            *((_WORD *)*a3 + k) = -8531;
        }
      }
LABEL_21:
      CoTaskMemFree((LPVOID)*a3);
      *a3 = 0;
      goto LABEL_22;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001a074  mov     [rsp+arg_0], rbx
0x18001a079  push    rbp
0x18001a07a  push    rsi
0x18001a07b  push    rdi
0x18001a07c  push    r12
0x18001a07e  push    r13
0x18001a080  push    r14
0x18001a082  push    r15
0x18001a084  sub     rsp, 250h
0x18001a08b  mov     rax, cs:__security_cookie
0x18001a092  xor     rax, rsp
0x18001a095  mov     [rsp+288h+var_48], rax
0x18001a09d  xor     r13d, r13d
0x18001a0a0  mov     rdi, rdx
0x18001a0a3  mov     r14, r8
0x18001a0a6  mov     esi, r13d
0x18001a0a9  lea     edx, [r13+25h]; Ch
0x18001a0ad  cmp     [rdi], dx
0x18001a0b0  jnz     loc_18001A35E
0x18001a0b6  mov     rcx, rdi; Str
0x18001a0b9  call    cs:__imp_wcsrchr
0x18001a0bf  mov     [rsp+288h+EndPtr], rax
0x18001a0c4  test    rax, rax
0x18001a0c7  jnz     short loc_18001A0D3
0x18001a0c9  mov     esi, 80070057h
0x18001a0ce  jmp     loc_18001A373
0x18001a0d3  add     rdi, 2
0x18001a0d7  lea     rdx, [rsp+288h+EndPtr]; EndPtr
0x18001a0dc  mov     rcx, rdi; String
0x18001a0df  mov     r8d, 10h; Radix
0x18001a0e5  call    cs:__imp_wcstoul
0x18001a0eb  mov     rax, [rsp+288h+EndPtr]
0x18001a0f0  mov     ecx, r13d
0x18001a0f3  cmp     rax, rdi
0x18001a0f6  mov     esi, 80070057h
0x18001a0fb  cmovz   ecx, esi; int
0x18001a0fe  add     rax, 2
0x18001a102  mov     [rsp+288h+EndPtr], rax
0x18001a107  cmp     word ptr [rax], 5Ch ; '\'
0x18001a10b  jnz     loc_18001A373
0x18001a111  mov     [rsp+288h+Src], r13w
0x18001a117  mov     esi, ecx
0x18001a119  test    ecx, ecx
0x18001a11b  js      loc_18001A373
0x18001a121  lea     r8, [rsp+288h+Src]; unsigned __int16 *
0x18001a126  call    ?SpGetSharedLexiconFolder@@YAJHKPEAG@Z; SpGetSharedLexiconFolder(int,ulong,ushort *)
0x18001a12b  mov     rdi, [r14]
0x18001a12e  lea     rax, [rsp+288h+Src]
0x18001a133  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001a137  mov     ebp, 8
0x18001a13c  mov     ebx, 0DEADh
0x18001a141  cmp     rax, rdi
0x18001a144  jz      loc_18001A221
0x18001a14a  test    rdi, rdi
0x18001a14d  jz      short loc_18001A1C2
0x18001a14f  call    cs:__imp_GetProcessHeap
0x18001a155  mov     r8, rdi; lpMem
0x18001a158  xor     edx, edx; dwFlags
0x18001a15a  mov     rcx, rax; hHeap
0x18001a15d  call    cs:__imp_HeapSize
0x18001a163  mov     rdx, rax
0x18001a166  add     rax, 0FFFFFFFFFFFFFFFDh
0x18001a16a  cmp     rax, 0FFFFFFFFFFFFFFFBh
0x18001a16e  ja      short loc_18001A1B6
0x18001a170  shr     rdx, 1
0x18001a173  dec     rdx
0x18001a176  cmp     rdx, rbp
0x18001a179  jnb     short loc_18001A185
0x18001a17b  test    rdx, rdx
0x18001a17e  jz      short loc_18001A1B6
0x18001a180  mov     rcx, r13
0x18001a183  jmp     short loc_18001A19C
0x18001a185  mov     rdi, [r14]
0x18001a188  cmp     rdi, r14
0x18001a18b  ja      short loc_18001A1AD
0x18001a18d  lea     rax, [rdi+0Eh]
0x18001a191  mov     rcx, r13
0x18001a194  mov     rdx, rbp
0x18001a197  cmp     rax, r14
0x18001a19a  jb      short loc_18001A1AD
0x18001a19c  mov     rax, [r14]
0x18001a19f  mov     [rax+rcx*2], bx
0x18001a1a3  inc     rcx
0x18001a1a6  cmp     rcx, rdx
0x18001a1a9  jb      short loc_18001A19C
0x18001a1ab  jmp     short loc_18001A1B6
0x18001a1ad  movzx   eax, bx
0x18001a1b0  mov     rcx, rbp
0x18001a1b3  rep stosw
0x18001a1b6  mov     rcx, [r14]; pv
0x18001a1b9  call    cs:__imp_CoTaskMemFree
0x18001a1bf  mov     [r14], r13
0x18001a1c2  lea     rax, [rsp+288h+Src]
0x18001a1c7  mov     rdi, r15
0x18001a1ca  inc     rdi
0x18001a1cd  cmp     [rax+rdi*2], r13w
0x18001a1d2  jnz     short loc_18001A1CA
0x18001a1d4  cmp     edi, 4FFFFFFFh
0x18001a1da  jnb     short loc_18001A216
0x18001a1dc  lea     ecx, [rdi+1]
0x18001a1df  mov     ebx, edi
0x18001a1e1  add     rcx, rcx; cb
0x18001a1e4  cmp     rcx, rbx
0x18001a1e7  jbe     short loc_18001A216
0x18001a1e9  call    cs:__imp_CoTaskMemAlloc
0x18001a1ef  mov     [r14], rax
0x18001a1f2  test    rax, rax
0x18001a1f5  jz      short loc_18001A20F
0x18001a1f7  mov     [rax+rbx*2], r13w
0x18001a1fc  lea     r8, [rdi+rdi]; Size
0x18001a200  mov     rcx, [r14]; void *
0x18001a203  lea     rdx, [rsp+288h+Src]; Src
0x18001a208  call    memcpy_0
0x18001a20d  jmp     short loc_18001A221
0x18001a20f  mov     ecx, 0Eh
0x18001a214  jmp     short loc_18001A21B
0x18001a216  mov     ecx, 216h; dwErrCode
0x18001a21b  call    cs:__imp_SetLastError
0x18001a221  mov     r12, [rsp+288h+EndPtr]
0x18001a226  mov     esi, r13d
0x18001a229  test    r12, r12
0x18001a22c  jz      loc_18001A373
0x18001a232  mov     rcx, r15
0x18001a235  inc     rcx
0x18001a238  cmp     [r12+rcx*2], r13w
0x18001a23d  jnz     short loc_18001A235
0x18001a23f  mov     rax, [r14]
0x18001a242  test    ecx, ecx
0x18001a244  jz      loc_18001A34B
0x18001a24a  mov     edx, r13d
0x18001a24d  test    rax, rax
0x18001a250  jz      short loc_18001A25F
0x18001a252  inc     r15
0x18001a255  cmp     [rax+r15*2], r13w
0x18001a25a  jnz     short loc_18001A252
0x18001a25c  mov     rdx, r15
0x18001a25f  mov     ebx, edx
0x18001a261  mov     r15d, ecx
0x18001a264  lea     rcx, [rbx+r15]
0x18001a268  cmp     rcx, rbx
0x18001a26b  jbe     loc_18001A344
0x18001a271  cmp     ecx, 4FFFFFFFh
0x18001a277  jnb     loc_18001A339
0x18001a27d  lea     edx, [rcx+1]
0x18001a280  mov     esi, ecx
0x18001a282  add     rdx, rdx
0x18001a285  cmp     rdx, rsi
0x18001a288  jbe     loc_18001A339
0x18001a28e  mov     rcx, rdx; cb
0x18001a291  call    cs:__imp_CoTaskMemAlloc
0x18001a297  mov     rdi, rax
0x18001a29a  test    rax, rax
0x18001a29d  jz      loc_18001A32C
0x18001a2a3  mov     [rax+rsi*2], r13w
0x18001a2a8  add     rbx, rbx
0x18001a2ab  mov     rdx, [r14]; Src
0x18001a2ae  mov     r8, rbx; Size
0x18001a2b1  mov     rcx, rax; void *
0x18001a2b4  mov     esi, r13d
0x18001a2b7  call    memcpy_0
0x18001a2bc  lea     r8, [r15+r15]; Size
0x18001a2c0  mov     rdx, r12; Src
0x18001a2c3  lea     rcx, [rbx+rdi]; void *
0x18001a2c7  call    memcpy_0
0x18001a2cc  mov     rbx, [r14]
0x18001a2cf  mov     [r14], rdi
0x18001a2d2  test    rbx, rbx
0x18001a2d5  jz      loc_18001A373
0x18001a2db  call    cs:__imp_GetProcessHeap
0x18001a2e1  mov     r8, rbx; lpMem
0x18001a2e4  xor     edx, edx; dwFlags
0x18001a2e6  mov     rcx, rax; hHeap
0x18001a2e9  call    cs:__imp_HeapSize
0x18001a2ef  mov     rcx, rax
0x18001a2f2  add     rax, 0FFFFFFFFFFFFFFFDh
0x18001a2f6  cmp     rax, 0FFFFFFFFFFFFFFFBh
0x18001a2fa  ja      short loc_18001A321
0x18001a2fc  shr     rcx, 1
0x18001a2ff  lea     rax, [rcx-1]
0x18001a303  cmp     rax, rbp
0x18001a306  jnb     short loc_18001A310
0x18001a308  mov     rbp, rax
0x18001a30b  test    rax, rax
0x18001a30e  jz      short loc_18001A321
0x18001a310  mov     eax, 0DEADh
0x18001a315  mov     rdi, rbx
0x18001a318  movzx   eax, ax
0x18001a31b  mov     rcx, rbp
0x18001a31e  rep stosw
0x18001a321  mov     rcx, rbx; pv
0x18001a324  call    cs:__imp_CoTaskMemFree
0x18001a32a  jmp     short loc_18001A373
0x18001a32c  mov     ecx, 0Eh; dwErrCode
0x18001a331  call    cs:__imp_SetLastError
0x18001a337  jmp     short loc_18001A36E
0x18001a339  mov     ecx, 216h; dwErrCode
0x18001a33e  call    cs:__imp_SetLastError
0x18001a344  mov     esi, 80070216h
0x18001a349  jmp     short loc_18001A373
0x18001a34b  test    rax, rax
0x18001a34e  jnz     short loc_18001A373
0x18001a350  xor     edx, edx; unsigned int
0x18001a352  mov     rcx, r14; this
0x18001a355  call    ?_allocate@CSpDynamicString@@AEAAJK@Z; CSpDynamicString::_allocate(ulong)
0x18001a35a  mov     esi, eax
0x18001a35c  jmp     short loc_18001A373
0x18001a35e  mov     rdx, rdi
0x18001a361  mov     rcx, r14
0x18001a364  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x18001a369  cmp     [r14], r13
0x18001a36c  jnz     short loc_18001A373
0x18001a36e  mov     esi, 8007000Eh
0x18001a373  mov     eax, esi
0x18001a375  mov     rcx, [rsp+288h+var_48]
0x18001a37d  xor     rcx, rsp; StackCookie
0x18001a380  call    __security_check_cookie
0x18001a385  mov     rbx, [rsp+288h+arg_0]
0x18001a38d  add     rsp, 250h
0x18001a394  pop     r15
0x18001a396  pop     r14
0x18001a398  pop     r13
0x18001a39a  pop     r12
0x18001a39c  pop     rdi
0x18001a39d  pop     rsi
0x18001a39e  pop     rbp
0x18001a39f  retn
```
