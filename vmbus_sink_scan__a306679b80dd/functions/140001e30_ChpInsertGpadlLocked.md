# ChpInsertGpadlLocked

- ea: `0x140001e30`
- end: `0x140001ff2`
- name: `ChpInsertGpadlLocked`
- size: `450`
- prototype: `__int64 __fastcall(__int64, __int64, signed __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f158`

## callees

- `0x140001e30`
- `0x14001016c`
- `0x140016e58`
- `0x140017240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001f4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001f4c`
- `ntoskrnl!ExAllocatePool2` at `0x140001ed4`
- `ntoskrnl!ExAllocatePool2` at `0x140001ed4`

## pseudocode

```c
__int64 __fastcall ChpInsertGpadlLocked(__int64 a1, __int64 a2, signed __int64 a3)
{
  __int64 v6; // r14
  unsigned int v7; // ebp
  unsigned int v8; // ecx
  __int64 result; // rax
  unsigned int v10; // edx
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  _QWORD *Pool2; // rax
  _QWORD *v15; // r15
  __int64 v16; // r8
  unsigned int i; // edx
  __int64 v18; // rax
  __int64 v19; // rcx
  void *v20; // rcx
  signed __int64 *v21; // r8
  signed __int64 v22; // rax
  int v23; // r9d
  signed __int64 v24; // rdx
  __int64 v25; // r10
  __int64 v26; // rsi
  signed __int64 *v27; // rax

  if ( !**(_DWORD **)(a1 + 736) )
  {
    v6 = *(unsigned int *)(a1 + 744);
    v7 = *(_DWORD *)(a1 + 748);
    v8 = v6 + 1;
    if ( (int)v6 + 1 > v7 )
      return 3221225540LL;
    v10 = 2 * v6;
    v11 = v6 + 1;
    if ( v8 < 8 )
      v11 = 8;
    if ( v11 <= v10 )
    {
      v12 = 2 * v6;
    }
    else
    {
      v12 = v6 + 1;
      if ( v8 < 8 )
        v12 = 8;
    }
    if ( v7 >= v12 )
    {
      v13 = v6 + 1;
      if ( v8 < 8 )
        v13 = 8;
      if ( v13 <= v10 )
      {
        v7 = 2 * v6;
      }
      else
      {
        v7 = v6 + 1;
        if ( v8 < 8 )
          v7 = 8;
      }
    }
    Pool2 = (_QWORD *)ExAllocatePool2(*(_QWORD *)(a1 + 760), 8LL * v7, *(unsigned int *)(a1 + 752));
    v15 = Pool2;
    if ( !Pool2 )
      return 3221225626LL;
    memmove(Pool2, *(const void **)(a1 + 736), 8 * v6);
    v16 = v7 - 1;
    for ( i = v16; i >= (unsigned int)v6; v15[v18] = v19 )
    {
      v18 = i;
      v19 = i-- + 1;
    }
    DvpPushFreeEntries(v15, (unsigned int)v6, &v15[v16]);
    v20 = *(void **)(a1 + 736);
    if ( v20 != (void *)(a1 + 768) )
      ExFreePoolWithTag(v20, *(_DWORD *)(a1 + 752));
    *(_QWORD *)(a1 + 736) = v15;
    *(_DWORD *)(a1 + 744) = v7;
  }
  v21 = *(signed __int64 **)(a1 + 736);
  _m_prefetchw(v21);
  v22 = *v21;
  do
  {
    if ( !v22 )
    {
      v23 = 0;
      goto LABEL_32;
    }
    v23 = v22;
    v24 = v22;
    v25 = (unsigned int)v22;
    v22 = _InterlockedCompareExchange64(v21, v21[v25], v22);
  }
  while ( v22 != v24 );
  if ( v23 )
    v21[v25] = a3;
LABEL_32:
  *(_DWORD *)(a3 + 64) = v23;
  *(_QWORD *)(a3 + 56) = a2;
  ChReferenceChannelInternal(a2, 22, 176);
  v26 = a2 + 736;
  v27 = *(signed __int64 **)(v26 + 8);
  if ( *v27 != v26 )
    __fastfail(3u);
  *(_QWORD *)(a3 + 8) = v27;
  *(_QWORD *)a3 = v26;
  *v27 = a3;
  result = 0;
  *(_QWORD *)(v26 + 8) = a3;
  return result;
}

```

## disassembly

```asm
0x140001e30  push    rbx
0x140001e32  push    rbp
0x140001e33  push    rsi
0x140001e34  push    rdi
0x140001e35  push    r14
0x140001e37  push    r15
0x140001e39  sub     rsp, 28h
0x140001e3d  mov     rax, [rcx+2E0h]
0x140001e44  mov     rdi, r8
0x140001e47  mov     rsi, rdx
0x140001e4a  mov     rbx, rcx
0x140001e4d  cmp     dword ptr [rax], 0
0x140001e50  jnz     loc_140001F65
0x140001e56  mov     r14d, [rcx+2E8h]
0x140001e5d  mov     ebp, [rbx+2ECh]
0x140001e63  lea     ecx, [r14+1]
0x140001e67  cmp     ecx, ebp
0x140001e69  jbe     short loc_140001E7E
0x140001e6b  mov     eax, 0C0000044h
0x140001e70  add     rsp, 28h
0x140001e74  pop     r15
0x140001e76  pop     r14
0x140001e78  pop     rdi
0x140001e79  pop     rsi
0x140001e7a  pop     rbp
0x140001e7b  pop     rbx
0x140001e7c  retn
0x140001e7e  mov     r8d, 8
0x140001e84  lea     edx, [r14+r14]
0x140001e88  cmp     ecx, r8d
0x140001e8b  mov     eax, ecx
0x140001e8d  cmovb   eax, r8d
0x140001e91  cmp     eax, edx
0x140001e93  jbe     short loc_140001EA0
0x140001e95  cmp     ecx, r8d
0x140001e98  mov     eax, ecx
0x140001e9a  cmovb   eax, r8d
0x140001e9e  jmp     short loc_140001EA2
0x140001ea0  mov     eax, edx
0x140001ea2  cmp     ebp, eax
0x140001ea4  jb      short loc_140001EC0
0x140001ea6  cmp     ecx, r8d
0x140001ea9  mov     eax, ecx
0x140001eab  cmovb   eax, r8d
0x140001eaf  cmp     eax, edx
0x140001eb1  jbe     short loc_140001EBE
0x140001eb3  cmp     ecx, r8d
0x140001eb6  mov     ebp, ecx
0x140001eb8  cmovb   ebp, r8d
0x140001ebc  jmp     short loc_140001EC0
0x140001ebe  mov     ebp, edx
0x140001ec0  mov     r8d, [rbx+2F0h]
0x140001ec7  mov     rcx, [rbx+2F8h]
0x140001ece  mov     edx, ebp
0x140001ed0  shl     rdx, 3
0x140001ed4  call    cs:__imp_ExAllocatePool2
0x140001edb  nop     dword ptr [rax+rax+00h]
0x140001ee0  mov     r15, rax
0x140001ee3  test    rax, rax
0x140001ee6  jnz     short loc_140001EF2
0x140001ee8  mov     eax, 0C000009Ah
0x140001eed  jmp     loc_140001FE4
0x140001ef2  mov     rdx, [rbx+2E0h]; Src
0x140001ef9  mov     r8, r14
0x140001efc  shl     r8, 3; Size
0x140001f00  mov     rcx, r15; void *
0x140001f03  call    memmove
0x140001f08  lea     r8d, [rbp-1]
0x140001f0c  mov     edx, r8d
0x140001f0f  cmp     r8d, r14d
0x140001f12  jb      short loc_140001F24
0x140001f14  mov     eax, edx
0x140001f16  lea     ecx, [rdx+1]
0x140001f19  dec     edx
0x140001f1b  mov     [r15+rax*8], rcx
0x140001f1f  cmp     edx, r14d
0x140001f22  jnb     short loc_140001F14
0x140001f24  lea     r8, [r15+r8*8]
0x140001f28  mov     edx, r14d
0x140001f2b  mov     rcx, r15
0x140001f2e  call    DvpPushFreeEntries
0x140001f33  mov     rcx, [rbx+2E0h]; P
0x140001f3a  lea     rax, [rbx+300h]
0x140001f41  cmp     rcx, rax
0x140001f44  jz      short loc_140001F58
0x140001f46  mov     edx, [rbx+2F0h]; Tag
0x140001f4c  call    cs:__imp_ExFreePoolWithTag
0x140001f53  nop     dword ptr [rax+rax+00h]
0x140001f58  mov     [rbx+2E0h], r15
0x140001f5f  mov     [rbx+2E8h], ebp
0x140001f65  mov     r8, [rbx+2E0h]
0x140001f6c  prefetchw byte ptr [r8]
0x140001f70  mov     rax, [r8]
0x140001f73  test    rax, rax
0x140001f76  jz      short loc_140001F9F
0x140001f78  mov     r9d, eax
0x140001f7b  mov     rdx, rax
0x140001f7e  lea     r10, ds:0[r9*8]
0x140001f86  mov     rcx, [r10+r8]
0x140001f8a  lock cmpxchg [r8], rcx
0x140001f8f  cmp     rax, rdx
0x140001f92  jnz     short loc_140001F73
0x140001f94  test    r9d, r9d
0x140001f97  jz      short loc_140001FA2
0x140001f99  mov     [r10+r8], rdi
0x140001f9d  jmp     short loc_140001FA2
0x140001f9f  xor     r9d, r9d
0x140001fa2  mov     edx, 16h
0x140001fa7  mov     [rdi+40h], r9d
0x140001fab  mov     r8d, 0B0h
0x140001fb1  mov     [rdi+38h], rsi
0x140001fb5  mov     rcx, rsi
0x140001fb8  call    ChReferenceChannelInternal
0x140001fbd  add     rsi, 2E0h
0x140001fc4  mov     rax, [rsi+8]
0x140001fc8  cmp     [rax], rsi
0x140001fcb  jz      short loc_140001FD4
0x140001fcd  mov     ecx, 3
0x140001fd2  int     29h; Win8: RtlFailFast(ecx)
0x140001fd4  mov     [rdi+8], rax
0x140001fd8  mov     [rdi], rsi
0x140001fdb  mov     [rax], rdi
0x140001fde  xor     eax, eax
0x140001fe0  mov     [rsi+8], rdi
0x140001fe4  add     rsp, 28h
0x140001fe8  pop     r15
0x140001fea  pop     r14
0x140001fec  pop     rdi
0x140001fed  pop     rsi
0x140001fee  pop     rbp
0x140001fef  pop     rbx
0x140001ff0  retn
```
