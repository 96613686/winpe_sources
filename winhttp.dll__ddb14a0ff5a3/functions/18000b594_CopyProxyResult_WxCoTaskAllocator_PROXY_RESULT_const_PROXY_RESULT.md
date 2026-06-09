# CopyProxyResult<WxCoTaskAllocator>(_PROXY_RESULT const *,_PROXY_RESULT *)

- ea: `0x18000b594`
- end: `0x18000b8c9`
- name: `??$CopyProxyResult@VWxCoTaskAllocator@@@@YAJPEBU_PROXY_RESULT@@PEAU0@@Z`
- size: `821`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b2c0`

## callees

- `0x180009070`
- `0x18000b594`
- `0x18000b8d0`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b756`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b756`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b85c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b869`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b85c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b869`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b825`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8be`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000b894`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000b894`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b634`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b634`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7c6`

## pseudocode

```c
__int64 __fastcall CopyProxyResult<WxCoTaskAllocator>(__int64 a1, _OWORD *a2)
{
  __int128 v2; // xmm6
  void *v3; // rbx
  __int64 v6; // rcx
  _BYTE *v7; // rax
  signed int v8; // edi
  SIZE_T v9; // rdi
  char *v10; // rax
  char *v11; // r14
  unsigned int v12; // r12d
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rsi
  __int64 v16; // rax
  __int128 v17; // xmm0
  unsigned int i; // esi
  int v20; // eax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  void *v23; // rsi
  void *v24; // rdi
  HANDLE v25; // rax
  unsigned int v26; // [rsp+48h] [rbp-39h]
  void *v27; // [rsp+50h] [rbp-31h] BYREF
  LPVOID pv[2]; // [rsp+58h] [rbp-29h]
  __int128 v29; // [rsp+68h] [rbp-19h]
  HANDLE TargetHandle; // [rsp+78h] [rbp-9h] BYREF

  v2 = 0;
  v3 = 0;
  v27 = 0;
  TargetHandle = 0;
  *(_OWORD *)pv = 0;
  v29 = 0;
  if ( a2 )
  {
    v6 = 32;
    v7 = a2;
    do
    {
      *v7++ = 0;
      --v6;
    }
    while ( v6 );
  }
  if ( !a1 || !a2 )
    goto LABEL_13;
  v8 = 0;
  if ( !*(_DWORD *)a1 )
  {
    v12 = _mm_cvtsi128_si32((__m128i)0LL);
    v11 = (char *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    goto LABEL_16;
  }
  if ( !*(_QWORD *)(a1 + 8) )
  {
LABEL_13:
    v8 = -2147024809;
LABEL_14:
    v11 = (char *)pv[1];
    v12 = (unsigned int)pv[0];
    goto LABEL_18;
  }
  v9 = (unsigned int)(32 * *(_DWORD *)a1);
  v10 = (char *)CoTaskMemAlloc(v9);
  v11 = v10;
  if ( !v10 )
  {
    v8 = -2147024882;
    goto LABEL_14;
  }
  memset_0(v10, 0, (unsigned int)v9);
  pv[1] = v11;
  v12 = (unsigned int)pv[0];
  v8 = 0;
  v13 = 0;
  while ( 1 )
  {
    v26 = v13;
    if ( v13 >= *(_DWORD *)a1 )
      break;
    v14 = *(_QWORD *)(a1 + 8);
    v15 = 32LL * v13;
    if ( *(_DWORD *)(v15 + v14) )
    {
      v20 = WxNewStringW<WxCoTaskAllocator>(*(_QWORD *)(v15 + v14 + 16), &v27);
      v3 = v27;
      v8 = v20;
      if ( v20 < 0 )
        goto LABEL_18;
    }
    v16 = *(_QWORD *)(a1 + 8);
    LODWORD(pv[0]) = ++v12;
    *(_DWORD *)&v11[v15] = *(_DWORD *)(v15 + v16);
    *(_DWORD *)&v11[v15 + 4] = *(_DWORD *)(v15 + *(_QWORD *)(a1 + 8) + 4);
    *(_DWORD *)&v11[v15 + 8] = *(_DWORD *)(v15 + *(_QWORD *)(a1 + 8) + 8);
    *(_WORD *)&v11[v15 + 24] = *(_WORD *)(v15 + *(_QWORD *)(a1 + 8) + 24);
    *(_QWORD *)&v11[v15 + 16] = v3;
    v3 = 0;
    v13 = v26 + 1;
    v27 = 0;
  }
  v2 = *(_OWORD *)pv;
LABEL_16:
  if ( !*(_QWORD *)(a1 + 16) )
  {
LABEL_17:
    DWORD2(v29) = *(_DWORD *)(a1 + 24);
    v17 = v29;
    *a2 = v2;
    a2[1] = v17;
    v12 = _mm_cvtsi128_si32((__m128i)0LL);
    v11 = (char *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    goto LABEL_18;
  }
  CurrentProcess = GetCurrentProcess();
  v23 = *(void **)(a1 + 16);
  v24 = CurrentProcess;
  v25 = GetCurrentProcess();
  if ( DuplicateHandle(v25, v23, v24, &TargetHandle, 0, 0, 2u) )
  {
    v8 = 0;
    *(_QWORD *)&v29 = TargetHandle;
    TargetHandle = 0;
    goto LABEL_17;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( v8 >= 0 )
    v8 = -2147418113;
LABEL_18:
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  if ( v11 )
  {
    for ( i = 0; i < v12; ++i )
      FreeProxyResultEntry<WxCoTaskAllocator>(&v11[32 * i]);
    CoTaskMemFree(v11);
  }
  if ( v3 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v3);
    else
      HeapFree(g_hWxProcessHeap, 0, v3);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000b594  mov     rax, rsp
0x18000b597  mov     [rax+18h], rbx
0x18000b59b  push    rbp
0x18000b59c  push    rsi
0x18000b59d  push    rdi
0x18000b59e  push    r12
0x18000b5a0  push    r13
0x18000b5a2  push    r14
0x18000b5a4  push    r15
0x18000b5a6  lea     rbp, [rax-5Fh]
0x18000b5aa  sub     rsp, 0A0h
0x18000b5b1  movaps  xmmword ptr [rax-48h], xmm6
0x18000b5b5  movaps  xmmword ptr [rax-58h], xmm7
0x18000b5b9  mov     rax, cs:__security_cookie
0x18000b5c0  xor     rax, rsp
0x18000b5c3  mov     [rbp+57h+var_58], rax
0x18000b5c7  xor     esi, esi
0x18000b5c9  xorps   xmm6, xmm6
0x18000b5cc  mov     [rbp+57h+var_8C], esi
0x18000b5cf  mov     ebx, esi
0x18000b5d1  mov     [rbp+57h+var_88], rbx
0x18000b5d5  xorps   xmm7, xmm7
0x18000b5d8  mov     [rbp+57h+TargetHandle], rsi
0x18000b5dc  mov     r13, rdx
0x18000b5df  mov     r15, rcx
0x18000b5e2  movups  xmmword ptr [rbp+57h+pv], xmm6
0x18000b5e6  movups  [rbp+57h+var_70], xmm7
0x18000b5ea  test    rdx, rdx
0x18000b5ed  jz      short loc_18000B601
0x18000b5ef  lea     ecx, [rsi+20h]
0x18000b5f2  mov     rax, rdx
0x18000b5f5  mov     [rax], sil
0x18000b5f8  inc     rax
0x18000b5fb  sub     rcx, 1
0x18000b5ff  jnz     short loc_18000B5F5
0x18000b601  test    r15, r15
0x18000b604  jz      loc_18000B6CA
0x18000b60a  test    r13, r13
0x18000b60d  jz      loc_18000B6CA
0x18000b613  mov     eax, [r15]
0x18000b616  mov     edi, esi
0x18000b618  test    eax, eax
0x18000b61a  jz      loc_18000B78F
0x18000b620  cmp     [r15+8], rsi
0x18000b624  jz      loc_18000B850
0x18000b62a  shl     eax, 5
0x18000b62d  mov     ecx, eax; cb
0x18000b62f  mov     [rbp+57h+var_8C], esi
0x18000b632  mov     edi, eax
0x18000b634  call    cs:__imp_CoTaskMemAlloc
0x18000b63a  mov     r14, rax
0x18000b63d  test    rax, rax
0x18000b640  jz      loc_18000B7D1
0x18000b646  mov     r8d, edi; Size
0x18000b649  xor     edx, edx; Val
0x18000b64b  mov     rcx, rax; void *
0x18000b64e  call    memset_0
0x18000b653  mov     [rbp+57h+pv+8], r14
0x18000b657  mov     r12d, dword ptr [rbp+57h+pv]
0x18000b65b  mov     edi, esi
0x18000b65d  mov     eax, esi
0x18000b65f  mov     [rbp+57h+var_90], eax
0x18000b662  cmp     eax, [r15]
0x18000b665  jnb     short loc_18000B6E0
0x18000b667  mov     rcx, [r15+8]
0x18000b66b  mov     esi, eax
0x18000b66d  shl     rsi, 5
0x18000b671  cmp     dword ptr [rsi+rcx], 0
0x18000b675  jnz     loc_18000B7FD
0x18000b67b  mov     rax, [r15+8]
0x18000b67f  inc     r12d
0x18000b682  mov     dword ptr [rbp+57h+pv], r12d
0x18000b686  mov     ecx, [rsi+rax]
0x18000b689  mov     [rsi+r14], ecx
0x18000b68d  mov     rax, [r15+8]
0x18000b691  mov     ecx, [rsi+rax+4]
0x18000b695  mov     [rsi+r14+4], ecx
0x18000b69a  mov     rax, [r15+8]
0x18000b69e  mov     ecx, [rsi+rax+8]
0x18000b6a2  mov     [rsi+r14+8], ecx
0x18000b6a7  mov     rax, [r15+8]
0x18000b6ab  movzx   ecx, word ptr [rsi+rax+18h]
0x18000b6b0  mov     eax, [rbp+57h+var_90]
0x18000b6b3  mov     [rsi+r14+18h], cx
0x18000b6b9  mov     [rsi+r14+10h], rbx
0x18000b6be  xor     esi, esi
0x18000b6c0  mov     ebx, esi
0x18000b6c2  inc     eax
0x18000b6c4  mov     [rbp+57h+var_88], rbx
0x18000b6c8  jmp     short loc_18000B65F
0x18000b6ca  mov     [rbp+57h+var_8C], 291h
0x18000b6d1  mov     edi, 80070057h
0x18000b6d6  mov     r14, [rbp+57h+pv+8]
0x18000b6da  mov     r12d, dword ptr [rbp+57h+pv]
0x18000b6de  jmp     short loc_18000B718
0x18000b6e0  movups  xmm6, xmmword ptr [rbp+57h+pv]
0x18000b6e4  cmp     [r15+10h], rsi
0x18000b6e8  jnz     loc_18000B85C
0x18000b6ee  mov     eax, [r15+18h]
0x18000b6f2  xorps   xmm7, xmm7
0x18000b6f5  mov     dword ptr [rbp+57h+var_70+8], eax
0x18000b6f8  movups  xmm0, [rbp+57h+var_70]
0x18000b6fc  movups  xmmword ptr [r13+0], xmm6
0x18000b701  movups  xmmword ptr [r13+10h], xmm0
0x18000b706  xorps   xmm0, xmm0
0x18000b709  movd    r12d, xmm7
0x18000b70e  psrldq  xmm0, 8
0x18000b713  movq    r14, xmm0
0x18000b718  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x18000b71c  test    rcx, rcx
0x18000b71f  jnz     loc_18000B8B3
0x18000b725  movq    rcx, xmm7; hObject
0x18000b72a  test    rcx, rcx
0x18000b72d  jnz     loc_18000B8BE
0x18000b733  test    r14, r14
0x18000b736  jnz     short loc_18000B7A7
0x18000b738  test    rbx, rbx
0x18000b73b  jz      short loc_18000B75C
0x18000b73d  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x18000b744  jnz     loc_18000B7E9
0x18000b74a  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18000b751  mov     r8, rbx; lpMem
0x18000b754  xor     edx, edx; dwFlags
0x18000b756  call    cs:__imp_HeapFree
0x18000b75c  mov     eax, edi
0x18000b75e  mov     rcx, [rbp+57h+var_58]
0x18000b762  xor     rcx, rsp; StackCookie
0x18000b765  call    __security_check_cookie
0x18000b76a  lea     r11, [rsp+0D0h+var_30]
0x18000b772  mov     rbx, [r11+50h]
0x18000b776  movaps  xmm6, xmmword ptr [r11-10h]
0x18000b77b  movaps  xmm7, xmmword ptr [r11-20h]
0x18000b780  mov     rsp, r11
0x18000b783  pop     r15
0x18000b785  pop     r14
0x18000b787  pop     r13
0x18000b789  pop     r12
0x18000b78b  pop     rdi
0x18000b78c  pop     rsi
0x18000b78d  pop     rbp
0x18000b78e  retn
0x18000b78f  movdqa  xmm0, xmm6
0x18000b793  movd    r12d, xmm6
0x18000b798  psrldq  xmm0, 8
0x18000b79d  movq    r14, xmm0
0x18000b7a2  jmp     loc_18000B6E4
0x18000b7a7  xor     esi, esi
0x18000b7a9  test    r12d, r12d
0x18000b7ac  jz      short loc_18000B7C3
0x18000b7ae  mov     ecx, esi
0x18000b7b0  shl     rcx, 5
0x18000b7b4  add     rcx, r14
0x18000b7b7  call    ??$FreeProxyResultEntry@VWxCoTaskAllocator@@@@YAXPEAU_PROXY_RESULT_ENTRY@@@Z; FreeProxyResultEntry<WxCoTaskAllocator>(_PROXY_RESULT_ENTRY *)
0x18000b7bc  inc     esi
0x18000b7be  cmp     esi, r12d
0x18000b7c1  jb      short loc_18000B7AE
0x18000b7c3  mov     rcx, r14; pv
0x18000b7c6  call    cs:__imp_CoTaskMemFree
0x18000b7cc  jmp     loc_18000B738
0x18000b7d1  mov     [rbp+57h+var_8C], 4Ch ; 'L'
0x18000b7d8  mov     edi, 8007000Eh
0x18000b7dd  mov     [rbp+57h+var_8C], 298h
0x18000b7e4  jmp     loc_18000B6D6
0x18000b7e9  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x18000b7f0  mov     rcx, rbx
0x18000b7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7f8  jmp     loc_18000B75C
0x18000b7fd  mov     rcx, [rsi+rcx+10h]
0x18000b802  lea     rdx, [rbp+57h+var_88]
0x18000b806  call    ??$WxNewStringW@VWxCoTaskAllocator@@@@YAJPEBGPEAPEAG@Z; WxNewStringW<WxCoTaskAllocator>(ushort const *,ushort * *)
0x18000b80b  mov     rbx, [rbp+57h+var_88]
0x18000b80f  mov     edi, eax
0x18000b811  test    eax, eax
0x18000b813  jns     loc_18000B67B
0x18000b819  mov     [rbp+57h+var_8C], 2A0h
0x18000b820  jmp     loc_18000B718
0x18000b825  call    cs:__imp_GetLastError
0x18000b82b  mov     edi, eax
0x18000b82d  test    eax, eax
0x18000b82f  jle     short loc_18000B83A
0x18000b831  movzx   edi, ax
0x18000b834  or      edi, 80070000h
0x18000b83a  test    edi, edi
0x18000b83c  mov     [rbp+57h+var_8C], 2BBh
0x18000b843  mov     eax, 8000FFFFh
0x18000b848  cmovns  edi, eax
0x18000b84b  jmp     loc_18000B718
0x18000b850  mov     [rbp+57h+var_8C], 295h
0x18000b857  jmp     loc_18000B6D1
0x18000b85c  call    cs:__imp_GetCurrentProcess
0x18000b862  mov     rsi, [r15+10h]
0x18000b866  mov     rdi, rax
0x18000b869  call    cs:__imp_GetCurrentProcess
0x18000b86f  mov     [rsp+0D0h+dwOptions], 2; dwOptions
0x18000b877  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x18000b87b  mov     rcx, rax; hSourceProcessHandle
0x18000b87e  mov     [rsp+0D0h+bInheritHandle], 0; bInheritHandle
0x18000b886  mov     r8, rdi; hTargetProcessHandle
0x18000b889  mov     [rsp+0D0h+dwDesiredAccess], 0; dwDesiredAccess
0x18000b891  mov     rdx, rsi; hSourceHandle
0x18000b894  call    cs:__imp_DuplicateHandle
0x18000b89a  xor     esi, esi
0x18000b89c  test    eax, eax
0x18000b89e  jz      short loc_18000B825
0x18000b8a0  mov     rax, [rbp+57h+TargetHandle]
0x18000b8a4  mov     edi, esi
0x18000b8a6  mov     qword ptr [rbp+57h+var_70], rax
0x18000b8aa  mov     [rbp+57h+TargetHandle], rsi
0x18000b8ae  jmp     loc_18000B6EE
0x18000b8b3  call    cs:__imp_CloseHandle
0x18000b8b9  jmp     loc_18000B725
0x18000b8be  call    cs:__imp_CloseHandle
0x18000b8c4  jmp     loc_18000B733
```
