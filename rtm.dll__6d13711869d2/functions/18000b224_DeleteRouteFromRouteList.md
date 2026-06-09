# DeleteRouteFromRouteList

- ea: `0x18000b224`
- end: `0x18000b28e`
- name: `DeleteRouteFromRouteList`
- size: `106`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b440`
- `0x18000c560`
- `0x18000cf90`

## callees

- `0x18000b224`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000b275`
- `KERNEL32!GetProcessHeap` at `0x18000b275`
- `KERNEL32!HeapFree` at `0x18000b283`
- `KERNEL32!HeapFree` at `0x18000b283`

## pseudocode

```c
__int64 __fastcall DeleteRouteFromRouteList(_QWORD **a1, __int64 a2)
{
  _QWORD *v3; // rbx
  _QWORD *v4; // rax
  _QWORD *v6; // rdx
  HANDLE ProcessHeap; // rax

  if ( !a1 )
    return 0;
  v3 = *a1;
  if ( !*a1 || !a2 )
    return 0;
  v4 = 0;
  while ( *v3 != a2 )
  {
    v4 = v3;
    v3 = (_QWORD *)v3[1];
    if ( !v3 )
      return 0;
  }
  v6 = (_QWORD *)v3[1];
  if ( v4 )
    v4[1] = v6;
  else
    *a1 = v6;
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v3);
  return a2;
}

```

## disassembly

```asm
0x18000b224  mov     [rsp+arg_0], rbx
0x18000b229  push    rdi
0x18000b22a  sub     rsp, 20h
0x18000b22e  mov     rdi, rdx
0x18000b231  test    rcx, rcx
0x18000b234  jz      short loc_18000B256
0x18000b236  mov     rbx, [rcx]
0x18000b239  test    rbx, rbx
0x18000b23c  jz      short loc_18000B256
0x18000b23e  test    rdx, rdx
0x18000b241  jz      short loc_18000B256
0x18000b243  xor     eax, eax
0x18000b245  cmp     [rbx], rdi
0x18000b248  jz      short loc_18000B263
0x18000b24a  mov     rax, rbx
0x18000b24d  mov     rbx, [rbx+8]
0x18000b251  test    rbx, rbx
0x18000b254  jnz     short loc_18000B245
0x18000b256  xor     eax, eax
0x18000b258  mov     rbx, [rsp+28h+arg_0]
0x18000b25d  add     rsp, 20h
0x18000b261  pop     rdi
0x18000b262  retn
0x18000b263  mov     rdx, [rbx+8]
0x18000b267  test    rax, rax
0x18000b26a  jnz     short loc_18000B271
0x18000b26c  mov     [rcx], rdx
0x18000b26f  jmp     short loc_18000B275
0x18000b271  mov     [rax+8], rdx
0x18000b275  call    cs:__imp_GetProcessHeap
0x18000b27b  mov     r8, rbx; lpMem
0x18000b27e  xor     edx, edx; dwFlags
0x18000b280  mov     rcx, rax; hHeap
0x18000b283  call    cs:__imp_HeapFree
0x18000b289  mov     rax, rdi
0x18000b28c  jmp     short loc_18000B258
```
