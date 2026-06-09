# PinCachePresentPin

- ea: `0x180039670`
- end: `0x180039824`
- name: `PinCachePresentPin`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003a1a4`

## callees

- `0x18000d9d0`
- `0x180038e28`
- `0x180039670`
- `0x18003982c`
- `0x18003a700`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039716`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039716`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800397d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800397d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039705`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800397c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039705`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800397c6`

## pseudocode

```c
__int64 __fastcall PinCachePresentPin(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v5; // esi
  _BYTE *v7; // rdx
  _BYTE *v10; // rdi
  __int64 v11; // r12
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  HANDLE v14; // rax
  SIZE_T v15; // r8
  _BYTE *v16; // rax
  unsigned int v17; // eax
  __int64 v18; // rcx
  _BYTE *v19; // rax
  HANDLE ProcessHeap; // rax
  __int64 v21; // rax
  __int128 v23; // [rsp+30h] [rbp-40h] BYREF
  __int128 v24; // [rsp+40h] [rbp-30h]
  __int128 v25; // [rsp+50h] [rbp-20h]
  _BYTE *v26; // [rsp+60h] [rbp-10h]
  unsigned int v27; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int dwBytes; // [rsp+C8h] [rbp+58h] BYREF
  int dwBytes_4; // [rsp+CCh] [rbp+5Ch]

  dwBytes_4 = HIDWORD(a4);
  v5 = 0;
  dwBytes = 0;
  v7 = 0;
  v27 = 0;
  v26 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  if ( a2 - 1 <= 7 )
  {
    v10 = 0;
    if ( !a1 || (v11 = *(_QWORD *)(a1 + 8LL * (a2 - 1))) == 0 )
    {
LABEL_12:
      v12 = -2146434961;
LABEL_13:
      if ( v10 )
      {
        v18 = v5;
        v19 = v10;
        if ( v5 )
        {
          do
          {
            *v19++ = 0;
            --v18;
          }
          while ( v18 );
        }
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v10);
        v7 = v26;
      }
      goto LABEL_18;
    }
    v12 = PinCacheQuery(a1, a2, a3, 0, &dwBytes, &v27, v23, *((_QWORD *)&v23 + 1), v24, *((_QWORD *)&v24 + 1), v25);
    if ( v12 )
      goto LABEL_9;
    v13 = dwBytes;
    v14 = GetProcessHeap();
    v15 = v13;
    v12 = 8;
    v16 = HeapAlloc(v14, 8u, v15);
    v10 = v16;
    if ( !v16 )
      return v12;
    v12 = PinCacheQuery(a1, a2, a3, v16, &dwBytes, &v27, v23, *((_QWORD *)&v23 + 1), v24, *((_QWORD *)&v24 + 1), v25);
    if ( v12 )
    {
LABEL_9:
      v5 = dwBytes;
    }
    else
    {
      v5 = dwBytes;
      HIDWORD(v23) = dwBytes;
      *(_QWORD *)&v23 = __PAIR64__(v27, a2);
      *(_QWORD *)&v24 = v10;
      v17 = VerifyCachedPinCallback(&v23, a5);
      v7 = v26;
      v12 = v17;
      if ( !v26 )
        goto LABEL_11;
      v12 = I_CommitPinToCache(v11, (_DWORD)v26, DWORD2(v25), a3, 1);
    }
    v7 = v26;
LABEL_11:
    if ( v12 != 4306 )
      goto LABEL_13;
    goto LABEL_12;
  }
  v12 = 160;
LABEL_18:
  if ( v7 )
  {
    v21 = DWORD2(v25);
    if ( DWORD2(v25) )
    {
      do
      {
        *v7++ = 0;
        --v21;
      }
      while ( v21 );
      v7 = v26;
    }
    CspFreeH(v7);
  }
  return v12;
}

```

## disassembly

```asm
0x180039670  mov     [rsp-38h+arg_8], rbx
0x180039675  mov     [rsp-38h+dwBytes], r9
0x18003967a  push    rbp
0x18003967b  push    rsi
0x18003967c  push    rdi
0x18003967d  push    r12
0x18003967f  push    r13
0x180039681  push    r14
0x180039683  push    r15
0x180039685  mov     rbp, rsp
0x180039688  sub     rsp, 70h
0x18003968c  xor     esi, esi
0x18003968e  xorps   xmm0, xmm0
0x180039691  mov     r15d, edx
0x180039694  mov     dword ptr [rbp+dwBytes], esi
0x180039697  xor     edx, edx
0x180039699  mov     [rbp+arg_0], esi
0x18003969c  mov     r13, r8
0x18003969f  mov     [rbp+var_10], rdx
0x1800396a3  mov     r14, rcx
0x1800396a6  lea     eax, [r15-1]
0x1800396aa  movups  [rbp+var_40], xmm0
0x1800396ae  movups  [rbp+var_30], xmm0
0x1800396b2  movups  [rbp+var_20], xmm0
0x1800396b6  cmp     eax, 7
0x1800396b9  ja      loc_1800397E0
0x1800396bf  xor     edi, edi
0x1800396c1  test    rcx, rcx
0x1800396c4  jz      loc_1800397A7
0x1800396ca  lea     eax, [r15-1]
0x1800396ce  mov     r12, [rcx+rax*8]
0x1800396d2  test    r12, r12
0x1800396d5  jz      loc_1800397A7
0x1800396db  lea     rax, [rbp+arg_0]
0x1800396df  xor     r9d, r9d
0x1800396e2  mov     [rsp+70h+var_48], rax
0x1800396e7  mov     edx, r15d
0x1800396ea  lea     rax, [rbp+dwBytes]
0x1800396ee  mov     [rsp+70h+var_50], rax
0x1800396f3  call    PinCacheQuery
0x1800396f8  mov     ebx, eax
0x1800396fa  test    eax, eax
0x1800396fc  jnz     loc_180039798
0x180039702  mov     ebx, dword ptr [rbp+dwBytes]
0x180039705  call    cs:__imp_GetProcessHeap
0x18003970b  mov     r8d, ebx; dwBytes
0x18003970e  lea     ebx, [rsi+8]
0x180039711  mov     edx, ebx; dwFlags
0x180039713  mov     rcx, rax; hHeap
0x180039716  call    cs:__imp_HeapAlloc
0x18003971c  mov     rdi, rax
0x18003971f  test    rax, rax
0x180039722  jz      loc_18003980A
0x180039728  lea     rax, [rbp+arg_0]
0x18003972c  mov     r9, rdi
0x18003972f  mov     [rsp+70h+var_48], rax
0x180039734  mov     r8, r13
0x180039737  lea     rax, [rbp+dwBytes]
0x18003973b  mov     edx, r15d
0x18003973e  mov     rcx, r14
0x180039741  mov     [rsp+70h+var_50], rax
0x180039746  call    PinCacheQuery
0x18003974b  mov     ebx, eax
0x18003974d  test    eax, eax
0x18003974f  jnz     short loc_180039798
0x180039751  mov     eax, [rbp+arg_0]
0x180039754  lea     rcx, [rbp+var_40]
0x180039758  mov     esi, dword ptr [rbp+dwBytes]
0x18003975b  mov     rdx, [rbp+arg_20]
0x18003975f  mov     dword ptr [rbp+var_40+4], eax
0x180039762  mov     dword ptr [rbp+var_40+0Ch], esi
0x180039765  mov     dword ptr [rbp+var_40], r15d
0x180039769  mov     qword ptr [rbp+var_30], rdi
0x18003976d  call    VerifyCachedPinCallback
0x180039772  mov     rdx, [rbp+var_10]
0x180039776  mov     ebx, eax
0x180039778  test    rdx, rdx
0x18003977b  jz      short loc_18003979F
0x18003977d  mov     r8d, dword ptr [rbp+var_20+8]
0x180039781  mov     r9, r13
0x180039784  mov     rcx, r12
0x180039787  mov     dword ptr [rsp+70h+var_50], 1
0x18003978f  call    I_CommitPinToCache
0x180039794  mov     ebx, eax
0x180039796  jmp     short loc_18003979B
0x180039798  mov     esi, dword ptr [rbp+dwBytes]
0x18003979b  mov     rdx, [rbp+var_10]
0x18003979f  cmp     ebx, 10D2h
0x1800397a5  jnz     short loc_1800397AC
0x1800397a7  mov     ebx, 8010006Fh
0x1800397ac  test    rdi, rdi
0x1800397af  jz      short loc_1800397E5
0x1800397b1  mov     ecx, esi
0x1800397b3  mov     rax, rdi
0x1800397b6  test    esi, esi
0x1800397b8  jz      short loc_1800397C6
0x1800397ba  mov     byte ptr [rax], 0
0x1800397bd  inc     rax
0x1800397c0  sub     rcx, 1
0x1800397c4  jnz     short loc_1800397BA
0x1800397c6  call    cs:__imp_GetProcessHeap
0x1800397cc  mov     r8, rdi; lpMem
0x1800397cf  xor     edx, edx; dwFlags
0x1800397d1  mov     rcx, rax; hHeap
0x1800397d4  call    cs:__imp_HeapFree
0x1800397da  mov     rdx, [rbp+var_10]
0x1800397de  jmp     short loc_1800397E5
0x1800397e0  mov     ebx, 0A0h
0x1800397e5  test    rdx, rdx
0x1800397e8  jz      short loc_18003980A
0x1800397ea  mov     eax, dword ptr [rbp+var_20+8]
0x1800397ed  test    rax, rax
0x1800397f0  jz      short loc_180039802
0x1800397f2  mov     byte ptr [rdx], 0
0x1800397f5  inc     rdx
0x1800397f8  sub     rax, 1
0x1800397fc  jnz     short loc_1800397F2
0x1800397fe  mov     rdx, [rbp+var_10]
0x180039802  mov     rcx, rdx
0x180039805  call    CspFreeH
0x18003980a  mov     eax, ebx
0x18003980c  mov     rbx, [rsp+70h+arg_8]
0x180039814  add     rsp, 70h
0x180039818  pop     r15
0x18003981a  pop     r14
0x18003981c  pop     r13
0x18003981e  pop     r12
0x180039820  pop     rdi
0x180039821  pop     rsi
0x180039822  pop     rbp
0x180039823  retn
```
