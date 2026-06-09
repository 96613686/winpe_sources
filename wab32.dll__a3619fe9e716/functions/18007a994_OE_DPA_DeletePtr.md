# OE_DPA_DeletePtr

- ea: `0x18007a994`
- end: `0x18007aa60`
- name: `OE_DPA_DeletePtr`
- size: `204`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18007dae0`
- `0x18008579c`
- `0x180091450`

## callees

- `0x18007a994`

## import_xrefs

- `KERNEL32!HeapReAlloc` at `0x18007aa16`
- `KERNEL32!HeapReAlloc` at `0x18007aa16`
- `KERNEL32!GetProcessHeap` at `0x18007a9fc`
- `KERNEL32!GetProcessHeap` at `0x18007aa2c`
- `KERNEL32!GetProcessHeap` at `0x18007a9fc`
- `KERNEL32!GetProcessHeap` at `0x18007aa2c`
- `KERNEL32!HeapFree` at `0x18007aa3a`
- `KERNEL32!HeapFree` at `0x18007aa3a`
- `KERNEL32!RtlMoveMemory` at `0x18007a9de`
- `KERNEL32!RtlMoveMemory` at `0x18007a9de`

## pseudocode

```c
__int64 __fastcall OE_DPA_DeletePtr(unsigned int *a1, unsigned int a2)
{
  unsigned int v3; // r8d
  __int64 v4; // r9
  __int64 *v5; // rcx
  __int64 v6; // r14
  unsigned int v7; // esi
  unsigned int v8; // ebp
  void *v9; // rbx
  HANDLE v10; // rax
  LPVOID v11; // rax
  HANDLE ProcessHeap; // rax

  if ( !a1 )
    return 0;
  v3 = *a1;
  if ( a2 >= *a1 )
    return 0;
  v4 = *((_QWORD *)a1 + 1);
  v5 = (__int64 *)(v4 + 8LL * a2);
  v6 = *v5;
  if ( a2 < v3 - 1 )
    RtlMoveMemory(v5, (const void *)(v4 + 8LL * (a2 + 1)), 8 * (v3 - a2) - 8);
  --*a1;
  v7 = a1[4];
  v8 = a1[5];
  if ( v7 - *a1 > v8 )
  {
    v9 = (void *)*((_QWORD *)a1 + 1);
    if ( v7 <= v8 )
    {
      if ( v9 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v9);
        *((_QWORD *)a1 + 1) = 0;
      }
    }
    else
    {
      v10 = GetProcessHeap();
      v11 = HeapReAlloc(v10, 8u, v9, 8LL * (v7 - v8));
      if ( v11 )
        *((_QWORD *)a1 + 1) = v11;
    }
    a1[4] -= a1[5];
  }
  return v6;
}

```

## disassembly

```asm
0x18007a994  push    rbx
0x18007a996  push    rbp
0x18007a997  push    rsi
0x18007a998  push    rdi
0x18007a999  push    r14
0x18007a99b  sub     rsp, 20h
0x18007a99f  mov     rdi, rcx
0x18007a9a2  test    rcx, rcx
0x18007a9a5  jz      loc_18007AA53
0x18007a9ab  mov     r8d, [rcx]
0x18007a9ae  cmp     edx, r8d
0x18007a9b1  jnb     loc_18007AA53
0x18007a9b7  mov     r9, [rcx+8]
0x18007a9bb  mov     eax, edx
0x18007a9bd  lea     rcx, [r9+rax*8]; Destination
0x18007a9c1  mov     r14, [rcx]
0x18007a9c4  lea     eax, [r8-1]
0x18007a9c8  cmp     edx, eax
0x18007a9ca  jnb     short loc_18007A9E4
0x18007a9cc  sub     r8d, edx
0x18007a9cf  lea     eax, [rdx+1]
0x18007a9d2  lea     rdx, [r9+rax*8]; Source
0x18007a9d6  lea     r8d, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Length
0x18007a9de  call    cs:__imp_RtlMoveMemory
0x18007a9e4  dec     dword ptr [rdi]
0x18007a9e6  mov     esi, [rdi+10h]
0x18007a9e9  mov     eax, esi
0x18007a9eb  sub     eax, [rdi]
0x18007a9ed  mov     ebp, [rdi+14h]
0x18007a9f0  cmp     eax, ebp
0x18007a9f2  jbe     short loc_18007AA4E
0x18007a9f4  mov     rbx, [rdi+8]
0x18007a9f8  cmp     esi, ebp
0x18007a9fa  jbe     short loc_18007AA27
0x18007a9fc  call    cs:__imp_GetProcessHeap
0x18007aa02  sub     esi, ebp
0x18007aa04  mov     r8, rbx; lpMem
0x18007aa07  mov     r9d, esi
0x18007aa0a  mov     edx, 8; dwFlags
0x18007aa0f  shl     r9, 3; dwBytes
0x18007aa13  mov     rcx, rax; hHeap
0x18007aa16  call    cs:__imp_HeapReAlloc
0x18007aa1c  test    rax, rax
0x18007aa1f  jz      short loc_18007AA48
0x18007aa21  mov     [rdi+8], rax
0x18007aa25  jmp     short loc_18007AA48
0x18007aa27  test    rbx, rbx
0x18007aa2a  jz      short loc_18007AA48
0x18007aa2c  call    cs:__imp_GetProcessHeap
0x18007aa32  mov     r8, rbx; lpMem
0x18007aa35  xor     edx, edx; dwFlags
0x18007aa37  mov     rcx, rax; hHeap
0x18007aa3a  call    cs:__imp_HeapFree
0x18007aa40  mov     qword ptr [rdi+8], 0
0x18007aa48  mov     ecx, [rdi+14h]
0x18007aa4b  sub     [rdi+10h], ecx
0x18007aa4e  mov     rax, r14
0x18007aa51  jmp     short loc_18007AA55
0x18007aa53  xor     eax, eax
0x18007aa55  add     rsp, 20h
0x18007aa59  pop     r14
0x18007aa5b  pop     rdi
0x18007aa5c  pop     rsi
0x18007aa5d  pop     rbp
0x18007aa5e  pop     rbx
0x18007aa5f  retn
```
