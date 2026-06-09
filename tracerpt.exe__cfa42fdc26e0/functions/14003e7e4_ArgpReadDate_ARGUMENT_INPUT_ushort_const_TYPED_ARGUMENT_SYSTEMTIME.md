# ArgpReadDate(_ARGUMENT_INPUT *,ushort const *,TYPED_ARGUMENT<_SYSTEMTIME> *)

- ea: `0x14003e7e4`
- end: `0x14003e94c`
- name: `?ArgpReadDate@@YAJPEAU_ARGUMENT_INPUT@@PEBGPEAV?$TYPED_ARGUMENT@U_SYSTEMTIME@@@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(__int64, OLECHAR *, struct _SYSTEMTIME *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14003e608`

## callees

- `0x140009b40`
- `0x14003e7e4`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003e916`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003e937`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003e916`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003e937`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e80b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e908`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e929`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e80b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e908`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e929`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003e81c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003e81c`
- `OLEAUT32!__imp_VarDateFromStr` at `0x14003e8e7`
- `OLEAUT32!__imp_VarDateFromStr` at `0x14003e8e7`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x14003e900`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x14003e900`

## pseudocode

```c
__int64 __fastcall ArgpReadDate(__int64 a1, OLECHAR *a2, struct _SYSTEMTIME *a3)
{
  HANDLE ProcessHeap; // rax
  OLECHAR *v7; // rax
  OLECHAR *v8; // rdi
  HRESULT v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rax
  OLECHAR *v12; // r8
  OLECHAR *v13; // rcx
  int v14; // eax
  HANDLE v15; // rax
  void *v16; // rdi
  HANDLE v17; // rax
  DATE pdateOut[9]; // [rsp+20h] [rbp-48h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp+20h] BYREF

  pdateOut[0] = 0.0;
  lpMem = 0;
  ProcessHeap = GetProcessHeap();
  v7 = (OLECHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
  v8 = v7;
  if ( v7 )
  {
    *v7 = 0;
    v10 = 1024;
    v11 = 2147483646;
    v12 = v8;
    do
    {
      if ( !v11 )
        break;
      if ( !*a2 )
        break;
      *v12++ = *a2++;
      --v11;
      --v10;
    }
    while ( v10 );
    v13 = v12 - 1;
    v9 = v10 == 0 ? 0x8007007A : 0;
    if ( v10 )
      v13 = v12;
    *v13 = 0;
    if ( v10 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(a1 + 8))(a1, &lpMem);
      v9 = v14;
      if ( v14 >= 0 )
      {
        if ( v14
          || (v9 = StringCchCatW(v8, 0x400u, L" "), v9 >= 0)
          && (v9 = StringCchCatW(v8, 0x400u, (const unsigned __int16 *)lpMem), v9 >= 0) )
        {
          v9 = VarDateFromStr(v8, 0x400u, 0, pdateOut);
          if ( v9 >= 0 )
            v9 = VariantTimeToSystemTime(pdateOut[0], a3 + 8);
        }
      }
    }
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v8);
  }
  else
  {
    v9 = -2147024882;
  }
  v16 = lpMem;
  if ( lpMem )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v16);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14003e7e4  mov     rax, rsp
0x14003e7e7  push    rbx
0x14003e7e8  push    rbp
0x14003e7e9  push    rsi
0x14003e7ea  push    rdi
0x14003e7eb  push    r14
0x14003e7ed  push    r15
0x14003e7ef  sub     rsp, 38h
0x14003e7f3  xorps   xmm0, xmm0
0x14003e7f6  xor     r14d, r14d
0x14003e7f9  movsd   qword ptr [rax-48h], xmm0
0x14003e7fe  mov     rbp, r8
0x14003e801  mov     [rax+20h], r14
0x14003e805  mov     rbx, rdx
0x14003e808  mov     rsi, rcx
0x14003e80b  call    cs:__imp_GetProcessHeap
0x14003e811  xor     edx, edx; dwFlags
0x14003e813  mov     r8d, 800h; dwBytes
0x14003e819  mov     rcx, rax; hHeap
0x14003e81c  call    cs:__imp_HeapAlloc
0x14003e822  mov     rdi, rax
0x14003e825  test    rax, rax
0x14003e828  jnz     short loc_14003E834
0x14003e82a  mov     ebx, 8007000Eh
0x14003e82f  jmp     loc_14003E91C
0x14003e834  mov     r15d, 400h
0x14003e83a  mov     [rax], r14w
0x14003e83e  mov     edx, r15d
0x14003e841  mov     eax, 7FFFFFFEh
0x14003e846  mov     r8, rdi
0x14003e849  test    rax, rax
0x14003e84c  jz      short loc_14003E86B
0x14003e84e  movzx   ecx, word ptr [rbx]
0x14003e851  test    cx, cx
0x14003e854  jz      short loc_14003E86B
0x14003e856  mov     [r8], cx
0x14003e85a  add     rbx, 2
0x14003e85e  add     r8, 2
0x14003e862  dec     rax
0x14003e865  sub     rdx, 1
0x14003e869  jnz     short loc_14003E849
0x14003e86b  mov     rax, rdx
0x14003e86e  lea     rcx, [r8-2]
0x14003e872  neg     rax
0x14003e875  sbb     ebx, ebx
0x14003e877  not     ebx
0x14003e879  and     ebx, 8007007Ah
0x14003e87f  test    rdx, rdx
0x14003e882  cmovnz  rcx, r8
0x14003e886  mov     [rcx], r14w
0x14003e88a  jz      short loc_14003E908
0x14003e88c  mov     rax, [rsi+8]
0x14003e890  lea     rdx, [rsp+68h+lpMem]
0x14003e898  mov     rcx, rsi
0x14003e89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e8a0  mov     ebx, eax
0x14003e8a2  test    eax, eax
0x14003e8a4  js      short loc_14003E908
0x14003e8a6  jnz     short loc_14003E8D9
0x14003e8a8  lea     r8, asc_140043268; " "
0x14003e8af  mov     rdx, r15; unsigned __int64
0x14003e8b2  mov     rcx, rdi; unsigned __int16 *
0x14003e8b5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003e8ba  mov     ebx, eax
0x14003e8bc  test    eax, eax
0x14003e8be  js      short loc_14003E908
0x14003e8c0  mov     r8, [rsp+68h+lpMem]; unsigned __int16 *
0x14003e8c8  mov     rdx, r15; unsigned __int64
0x14003e8cb  mov     rcx, rdi; unsigned __int16 *
0x14003e8ce  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14003e8d3  mov     ebx, eax
0x14003e8d5  test    eax, eax
0x14003e8d7  js      short loc_14003E908
0x14003e8d9  lea     r9, [rsp+68h+pdateOut]; pdateOut
0x14003e8de  xor     r8d, r8d; dwFlags
0x14003e8e1  mov     edx, r15d; lcid
0x14003e8e4  mov     rcx, rdi; strIn
0x14003e8e7  call    cs:__imp_VarDateFromStr
0x14003e8ed  mov     ebx, eax
0x14003e8ef  test    eax, eax
0x14003e8f1  js      short loc_14003E908
0x14003e8f3  movsd   xmm0, [rsp+68h+pdateOut]; vtime
0x14003e8f9  lea     rdx, [rbp+80h]; lpSystemTime
0x14003e900  call    cs:__imp_VariantTimeToSystemTime
0x14003e906  mov     ebx, eax
0x14003e908  call    cs:__imp_GetProcessHeap
0x14003e90e  mov     r8, rdi; lpMem
0x14003e911  xor     edx, edx; dwFlags
0x14003e913  mov     rcx, rax; hHeap
0x14003e916  call    cs:__imp_HeapFree
0x14003e91c  mov     rdi, [rsp+68h+lpMem]
0x14003e924  test    rdi, rdi
0x14003e927  jz      short loc_14003E93D
0x14003e929  call    cs:__imp_GetProcessHeap
0x14003e92f  mov     r8, rdi; lpMem
0x14003e932  xor     edx, edx; dwFlags
0x14003e934  mov     rcx, rax; hHeap
0x14003e937  call    cs:__imp_HeapFree
0x14003e93d  mov     eax, ebx
0x14003e93f  add     rsp, 38h
0x14003e943  pop     r15
0x14003e945  pop     r14
0x14003e947  pop     rdi
0x14003e948  pop     rsi
0x14003e949  pop     rbp
0x14003e94a  pop     rbx
0x14003e94b  retn
```
