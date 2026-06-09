# CStringBlobT<ulong>::Add(ulong const *,ulong *,ulong *)

- ea: `0x180075b38`
- end: `0x180075cb4`
- name: `?Add@?$CStringBlobT@K@@QEAAJPEBKPEAK1@Z`
- size: `380`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180079660`
- `0x18007d724`

## callees

- `0x180004312`
- `0x18004c204`
- `0x180075b38`
- `0x180079b90`
- `0x18007cda8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180075c18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180075c18`

## pseudocode

```c
__int64 __fastcall CStringBlobT<unsigned long>::Add(__int64 a1, _DWORD *a2, _DWORD *a3)
{
  int v6; // ecx
  __int64 result; // rax
  __int64 Index; // r14
  int v9; // eax
  int v10; // ecx
  _DWORD *v11; // rax
  int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // rbp
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // rdi
  _DWORD *v17; // rax
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // edx

  if ( !a2 )
    goto LABEL_18;
  v6 = *(_DWORD *)(a1 + 24);
  if ( (unsigned int)(2 * v6) < *(_DWORD *)(a1 + 40)
    || (result = CStringBlobT<unsigned long>::SetHashSize(a1, (unsigned int)(v6 + 2 * v6 + 17)), (int)result >= 0) )
  {
    Index = (unsigned int)CStringBlobT<unsigned long>::FindIndex(a1, a2);
    v9 = *(_DWORD *)(*(_QWORD *)(a1 + 32) + 4 * Index);
    if ( v9 )
      goto LABEL_17;
    v10 = *(_DWORD *)(a1 + 24);
    if ( (unsigned int)(v10 + 1) >= *(_DWORD *)(a1 + 28) )
    {
      v11 = heap_realloc(*(void **)(a1 + 16), 4LL * (unsigned int)(v10 + 100));
      if ( !v11 )
        return 2147942414LL;
      v12 = *(_DWORD *)(a1 + 24);
      *(_QWORD *)(a1 + 16) = v11;
      *(_DWORD *)(a1 + 28) = v12 + 100;
      *v11 = 1;
    }
    v13 = 0;
    if ( *a2 )
    {
      do
        ++v13;
      while ( a2[v13] );
    }
    v14 = v13 + 1;
    v15 = *(unsigned int *)(a1 + 8);
    if ( v13 + 1 + (unsigned __int64)*(unsigned int *)(*(_QWORD *)(a1 + 16) + 4LL * *(unsigned int *)(a1 + 24)) > v15 )
    {
      v16 = (4 * (v15 + v14) + 8195) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v16 > 0x70000000 )
        return 2147942414LL;
      v17 = CoTaskMemRealloc(*(LPVOID *)a1, (4 * (v15 + v14) + 8195) & 0xFFFFFFFFFFFFFFFCuLL);
      if ( !v17 )
        return 2147942414LL;
      *(_QWORD *)a1 = v17;
      *v17 = 0;
      *(_DWORD *)(a1 + 8) = (unsigned int)v16 >> 2;
    }
    memcpy_0(
      (void *)(*(_QWORD *)a1 + 4LL * *(unsigned int *)(*(_QWORD *)(a1 + 16) + 4LL * *(unsigned int *)(a1 + 24))),
      a2,
      4 * v14);
    v18 = *(unsigned int *)(a1 + 24);
    v19 = *(_QWORD *)(a1 + 16);
    v20 = (unsigned int)(v18 + 1);
    *(_DWORD *)(a1 + 24) = v20;
    *(_DWORD *)(v19 + 4 * v20) = v14 + *(_DWORD *)(v19 + 4 * v18);
    v21 = *(unsigned int *)(a1 + 24);
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 16) + 4 * v21) < *(_DWORD *)(*(_QWORD *)(a1 + 16) + 4LL * (unsigned int)(v21 - 1)) )
      return 2147942414LL;
    *(_DWORD *)(*(_QWORD *)(a1 + 32) + 4 * Index) = v21;
    v9 = *(_DWORD *)(a1 + 24);
    if ( v9 )
    {
LABEL_17:
      v22 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 4LL * (unsigned int)(v9 - 1));
LABEL_19:
      *a3 = v22;
      return 0;
    }
LABEL_18:
    v22 = 0;
    goto LABEL_19;
  }
  return result;
}

```

## disassembly

```asm
0x180075b38  push    rbx
0x180075b3a  push    rbp
0x180075b3b  push    rsi
0x180075b3c  push    rdi
0x180075b3d  push    r14
0x180075b3f  push    r15
0x180075b41  sub     rsp, 28h
0x180075b45  mov     r15, r8
0x180075b48  mov     rsi, rdx
0x180075b4b  mov     rbx, rcx
0x180075b4e  test    rdx, rdx
0x180075b51  jz      loc_180075CA0
0x180075b57  mov     ecx, [rcx+18h]
0x180075b5a  lea     eax, [rcx+rcx]
0x180075b5d  cmp     eax, [rbx+28h]
0x180075b60  jb      short loc_180075B7B
0x180075b62  lea     edx, ds:11h[rcx*2]
0x180075b69  add     edx, ecx
0x180075b6b  mov     rcx, rbx
0x180075b6e  call    ?SetHashSize@?$CStringBlobT@K@@QEAAJK@Z; CStringBlobT<ulong>::SetHashSize(ulong)
0x180075b73  test    eax, eax
0x180075b75  js      loc_180075CA7
0x180075b7b  mov     rdx, rsi
0x180075b7e  mov     rcx, rbx
0x180075b81  call    ?FindIndex@?$CStringBlobT@K@@QEAAKPEBK@Z; CStringBlobT<ulong>::FindIndex(ulong const *)
0x180075b86  mov     r14d, eax
0x180075b89  mov     rax, [rbx+20h]
0x180075b8d  mov     eax, [rax+r14*4]
0x180075b91  test    eax, eax
0x180075b93  jnz     loc_180075C94
0x180075b99  mov     ecx, [rbx+18h]
0x180075b9c  lea     eax, [rcx+1]
0x180075b9f  cmp     eax, [rbx+1Ch]
0x180075ba2  jb      short loc_180075BD0
0x180075ba4  lea     edx, [rcx+64h]
0x180075ba7  mov     rcx, [rbx+10h]; lpMem
0x180075bab  shl     rdx, 2; unsigned __int64
0x180075baf  call    ?heap_realloc@@YAPEAXPEAX_K@Z; heap_realloc(void *,unsigned __int64)
0x180075bb4  test    rax, rax
0x180075bb7  jz      loc_180075C7E
0x180075bbd  mov     ecx, [rbx+18h]
0x180075bc0  add     ecx, 64h ; 'd'
0x180075bc3  mov     [rbx+10h], rax
0x180075bc7  mov     [rbx+1Ch], ecx
0x180075bca  mov     dword ptr [rax], 1
0x180075bd0  xor     eax, eax
0x180075bd2  cmp     [rsi], eax
0x180075bd4  jz      short loc_180075BDF
0x180075bd6  inc     rax
0x180075bd9  cmp     dword ptr [rsi+rax*4], 0
0x180075bdd  jnz     short loc_180075BD6
0x180075bdf  mov     ecx, [rbx+18h]
0x180075be2  lea     rbp, [rax+1]
0x180075be6  mov     rax, [rbx+10h]
0x180075bea  mov     r8d, [rbx+8]
0x180075bee  mov     edx, [rax+rcx*4]
0x180075bf1  add     rdx, rbp
0x180075bf4  cmp     rdx, r8
0x180075bf7  jbe     short loc_180075C32
0x180075bf9  lea     rax, [r8+rbp]
0x180075bfd  lea     rdi, ds:2003h[rax*4]
0x180075c05  and     rdi, 0FFFFFFFFFFFFFFFCh
0x180075c09  cmp     rdi, 70000000h
0x180075c10  ja      short loc_180075C7E
0x180075c12  mov     rcx, [rbx]; pv
0x180075c15  mov     rdx, rdi; cb
0x180075c18  call    cs:__imp_CoTaskMemRealloc
0x180075c1e  test    rax, rax
0x180075c21  jz      short loc_180075C7E
0x180075c23  mov     [rbx], rax
0x180075c26  shr     edi, 2
0x180075c29  mov     dword ptr [rax], 0
0x180075c2f  mov     [rbx+8], edi
0x180075c32  mov     ecx, [rbx+18h]
0x180075c35  lea     r8, ds:0[rbp*4]; Size
0x180075c3d  mov     rax, [rbx+10h]
0x180075c41  mov     edx, [rax+rcx*4]
0x180075c44  mov     rax, [rbx]
0x180075c47  lea     rcx, [rax+rdx*4]; void *
0x180075c4b  mov     rdx, rsi; Src
0x180075c4e  call    memcpy_0
0x180075c53  mov     eax, [rbx+18h]
0x180075c56  mov     r8, [rbx+10h]
0x180075c5a  lea     r9d, [rax+1]
0x180075c5e  mov     [rbx+18h], r9d
0x180075c62  mov     edx, [r8+rax*4]
0x180075c66  add     edx, ebp
0x180075c68  mov     [r8+r9*4], edx
0x180075c6c  mov     edx, [rbx+18h]
0x180075c6f  mov     rcx, [rbx+10h]
0x180075c73  lea     eax, [rdx-1]
0x180075c76  mov     eax, [rcx+rax*4]
0x180075c79  cmp     [rcx+rdx*4], eax
0x180075c7c  jnb     short loc_180075C85
0x180075c7e  mov     eax, 8007000Eh
0x180075c83  jmp     short loc_180075CA7
0x180075c85  mov     rax, [rbx+20h]
0x180075c89  mov     [rax+r14*4], edx
0x180075c8d  mov     eax, [rbx+18h]
0x180075c90  test    eax, eax
0x180075c92  jz      short loc_180075CA0
0x180075c94  lea     ecx, [rax-1]
0x180075c97  mov     rax, [rbx+10h]
0x180075c9b  mov     edx, [rax+rcx*4]
0x180075c9e  jmp     short loc_180075CA2
0x180075ca0  xor     edx, edx
0x180075ca2  mov     [r15], edx
0x180075ca5  xor     eax, eax
0x180075ca7  add     rsp, 28h
0x180075cab  pop     r15
0x180075cad  pop     r14
0x180075caf  pop     rdi
0x180075cb0  pop     rsi
0x180075cb1  pop     rbp
0x180075cb2  pop     rbx
0x180075cb3  retn
```
