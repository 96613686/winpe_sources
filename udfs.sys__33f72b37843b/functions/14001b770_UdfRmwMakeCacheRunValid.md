# UdfRmwMakeCacheRunValid

- ea: `0x14001b770`
- end: `0x14001b930`
- name: `UdfRmwMakeCacheRunValid`
- size: `448`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14000ba88`
- `0x140059540`

## callees

- `0x14000a3f0`
- `0x14000cad4`
- `0x14001b770`
- `0x14001bd80`
- `0x14001c080`
- `0x140058114`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14001b7be`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b7be`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001b7cf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001b7cf`

## pseudocode

```c
__int64 __fastcall UdfRmwMakeCacheRunValid(__int64 a1, __int64 a2, unsigned int **a3, _BYTE *a4, int a5)
{
  __int64 v7; // r12
  unsigned int v10; // r15d
  struct _ERESOURCE *v11; // rbx
  int CacheRun; // ebx
  __int64 v13; // rcx
  __int64 v14; // rdx
  _DWORD *v16; // rcx
  unsigned int i; // ebx
  __int64 v18; // rax

  v7 = (1LL << *(_DWORD *)(a2 + 12)) - 1;
  if ( *((_QWORD *)*a3 + 3) != v7 )
  {
    if ( !*a4 )
    {
      v10 = **a3;
      v11 = (struct _ERESOURCE *)(a2 + 128);
      ExReleaseResourceLite((PERESOURCE)(a2 + 128));
      ExAcquireResourceExclusiveLite(v11, 1u);
      *a4 = 1;
      if ( **a3 != v10 )
      {
        CacheRun = UdfRmwGetCacheRun(a1, a2, v10, a3, a4, a5);
        if ( CacheRun < 0 )
        {
          v13 = *(_QWORD *)&WPP_GLOBAL_Control;
          if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) == 0 )
          {
            return (unsigned int)CacheRun;
          }
          v14 = 48;
LABEL_8:
          WPP_SF_(*(_QWORD *)(v13 + 24), v14, WPP_e04914546632397e8b30a0a107c62418_Traceguids);
          return (unsigned int)CacheRun;
        }
      }
    }
    v16 = *(_DWORD **)(a1 + 16);
    if ( (v16[532] & 0x40) != 0 && (*a3)[2] >= v16[171] )
    {
      memset(*(void **)(a2 + 24), 0, (unsigned int)(*(_DWORD *)(a2 + 12) << v16[18]));
    }
    else
    {
      CacheRun = UdfRmwIssueIoRequest(a1, 0, (*a3)[2], *(_DWORD *)(a2 + 12), *(PVOID *)(a2 + 24));
      if ( CacheRun < 0 )
      {
        v13 = *(_QWORD *)&WPP_GLOBAL_Control;
        if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) == 0 )
        {
          return (unsigned int)CacheRun;
        }
        v14 = 49;
        goto LABEL_8;
      }
    }
    for ( i = 0; i < *(_DWORD *)(a2 + 12); ++i )
    {
      v18 = *((_QWORD *)*a3 + 3);
      if ( !_bittest64(&v18, i) )
        memmove(
          (void *)((i << *(_DWORD *)(*(_QWORD *)(a1 + 16) + 72LL)) + *((_QWORD *)*a3 + 2)),
          (const void *)((i << *(_DWORD *)(*(_QWORD *)(a1 + 16) + 72LL)) + *(_QWORD *)(a2 + 24)),
          (unsigned int)(1 << *(_DWORD *)(*(_QWORD *)(a1 + 16) + 72LL)));
    }
    *((_QWORD *)*a3 + 3) = v7;
  }
  return 0;
}

```

## disassembly

```asm
0x14001b770  push    rbx
0x14001b772  push    rbp
0x14001b773  push    rsi
0x14001b774  push    rdi
0x14001b775  push    r12
0x14001b777  push    r14
0x14001b779  push    r15
0x14001b77b  sub     rsp, 30h
0x14001b77f  mov     rax, [r8]
0x14001b782  mov     rbp, rcx
0x14001b785  mov     ecx, [rdx+0Ch]
0x14001b788  mov     r12d, 1
0x14001b78e  shl     r12, cl
0x14001b791  mov     r14, r9
0x14001b794  dec     r12
0x14001b797  mov     rsi, r8
0x14001b79a  mov     rdi, rdx
0x14001b79d  cmp     [rax+18h], r12
0x14001b7a1  jz      loc_14001B8C8
0x14001b7a7  cmp     byte ptr [r9], 0
0x14001b7ab  jnz     loc_14001B846
0x14001b7b1  mov     r15d, [rax]
0x14001b7b4  lea     rbx, [rdx+80h]
0x14001b7bb  mov     rcx, rbx; Resource
0x14001b7be  call    cs:__imp_ExReleaseResourceLite
0x14001b7c5  nop     dword ptr [rax+rax+00h]
0x14001b7ca  mov     dl, 1; Wait
0x14001b7cc  mov     rcx, rbx; Resource
0x14001b7cf  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001b7d6  nop     dword ptr [rax+rax+00h]
0x14001b7db  mov     byte ptr [r14], 1
0x14001b7df  mov     rax, [rsi]
0x14001b7e2  cmp     [rax], r15d
0x14001b7e5  jz      short loc_14001B846
0x14001b7e7  mov     eax, [rsp+68h+arg_20]
0x14001b7ee  mov     r9, rsi
0x14001b7f1  mov     [rsp+68h+var_40], eax
0x14001b7f5  mov     r8d, r15d
0x14001b7f8  mov     rdx, rdi
0x14001b7fb  mov     [rsp+68h+VirtualAddress], r14
0x14001b800  mov     rcx, rbp
0x14001b803  call    UdfRmwGetCacheRun
0x14001b808  mov     ebx, eax
0x14001b80a  test    eax, eax
0x14001b80c  jns     short loc_14001B846
0x14001b80e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b815  lea     rdx, WPP_GLOBAL_Control
0x14001b81c  cmp     rcx, rdx
0x14001b81f  jz      short loc_14001B83F
0x14001b821  test    dword ptr [rcx+2Ch], 20000000h
0x14001b828  jz      short loc_14001B83F
0x14001b82a  mov     edx, 30h ; '0'
0x14001b82f  mov     rcx, [rcx+18h]
0x14001b833  lea     r8, WPP_e04914546632397e8b30a0a107c62418_Traceguids
0x14001b83a  call    WPP_SF_
0x14001b83f  mov     eax, ebx
0x14001b841  jmp     loc_14001B8CA
0x14001b846  mov     rcx, [rbp+10h]
0x14001b84a  mov     eax, [rcx+850h]
0x14001b850  test    al, 40h
0x14001b852  jz      loc_14001B8DA
0x14001b858  mov     rdx, [rsi]
0x14001b85b  mov     eax, [rcx+2ACh]
0x14001b861  cmp     [rdx+8], eax
0x14001b864  jb      short loc_14001B8DA
0x14001b866  mov     ecx, [rcx+48h]
0x14001b869  xor     edx, edx; Val
0x14001b86b  mov     r8d, [rdi+0Ch]
0x14001b86f  shl     r8d, cl; Size
0x14001b872  mov     rcx, [rdi+18h]; void *
0x14001b876  call    memset
0x14001b87b  xor     ebx, ebx
0x14001b87d  cmp     [rdi+0Ch], ebx
0x14001b880  jbe     short loc_14001B8C1
0x14001b882  mov     r10, [rsi]
0x14001b885  mov     ecx, ebx
0x14001b887  mov     rax, [r10+18h]
0x14001b88b  bt      rax, rcx
0x14001b88f  jb      short loc_14001B8BA
0x14001b891  mov     rax, [rbp+10h]
0x14001b895  mov     r9d, ebx
0x14001b898  mov     rdx, [rdi+18h]
0x14001b89c  mov     r8d, 1
0x14001b8a2  mov     ecx, [rax+48h]
0x14001b8a5  shl     r9d, cl
0x14001b8a8  shl     r8d, cl; Size
0x14001b8ab  add     rdx, r9; Src
0x14001b8ae  mov     rcx, [r10+10h]
0x14001b8b2  add     rcx, r9; void *
0x14001b8b5  call    memmove
0x14001b8ba  inc     ebx
0x14001b8bc  cmp     ebx, [rdi+0Ch]
0x14001b8bf  jb      short loc_14001B882
0x14001b8c1  mov     rax, [rsi]
0x14001b8c4  mov     [rax+18h], r12
0x14001b8c8  xor     eax, eax
0x14001b8ca  add     rsp, 30h
0x14001b8ce  pop     r15
0x14001b8d0  pop     r14
0x14001b8d2  pop     r12
0x14001b8d4  pop     rdi
0x14001b8d5  pop     rsi
0x14001b8d6  pop     rbp
0x14001b8d7  pop     rbx
0x14001b8d8  retn
0x14001b8da  mov     r8, [rsi]
0x14001b8dd  xor     edx, edx; int
0x14001b8df  mov     rax, [rdi+18h]
0x14001b8e3  mov     rcx, rbp; int
0x14001b8e6  mov     r9d, [rdi+0Ch]; int
0x14001b8ea  mov     [rsp+68h+VirtualAddress], rax; VirtualAddress
0x14001b8ef  mov     r8d, [r8+8]; int
0x14001b8f3  call    UdfRmwIssueIoRequest
0x14001b8f8  mov     ebx, eax
0x14001b8fa  test    eax, eax
0x14001b8fc  jns     loc_14001B87B
0x14001b902  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b909  lea     rdx, WPP_GLOBAL_Control
0x14001b910  cmp     rcx, rdx
0x14001b913  jz      loc_14001B83F
0x14001b919  test    dword ptr [rcx+2Ch], 20000000h
0x14001b920  jz      loc_14001B83F
0x14001b926  mov     edx, 31h ; '1'
0x14001b92b  jmp     loc_14001B82F
```
