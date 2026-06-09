# DPA_InsertPtr

- ea: `0x180003520`
- end: `0x1800035af`
- name: `DPA_InsertPtr`
- size: `143`
- prototype: `int __stdcall(HDPA hdpa, int i, void *p)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002150`

## callees

- `0x180003484`
- `0x180003520`
- `0x180003696`

## pseudocode

```c
int __stdcall DPA_InsertPtr(HDPA hdpa, int i, void *p)
{
  int v4; // edi
  unsigned int v6; // eax
  unsigned int v7; // edx
  int result; // eax

  v4 = i;
  if ( !hdpa || i < 0 )
    return -1;
  v6 = *(_DWORD *)hdpa;
  if ( i > *(_DWORD *)hdpa )
    v4 = *(_DWORD *)hdpa;
  v7 = v6 + 1;
  if ( v6 + 1 < v6 || *((int *)hdpa + 6) < 0 || v7 > *((_DWORD *)hdpa + 6) && !DPA_Grow(hdpa, v7) )
    return -1;
  if ( v4 < *(_DWORD *)hdpa )
    memmove_0(
      (void *)(*((_QWORD *)hdpa + 1) + 8LL * (v4 + 1)),
      (const void *)(*((_QWORD *)hdpa + 1) + 8LL * v4),
      8LL * (*(_DWORD *)hdpa - v4));
  result = v4;
  *(_QWORD *)(*((_QWORD *)hdpa + 1) + 8LL * v4) = p;
  ++*(_DWORD *)hdpa;
  return result;
}

```

## disassembly

```asm
0x180003520  mov     [rsp+arg_0], rbx
0x180003525  mov     [rsp+arg_8], rsi
0x18000352a  push    rdi
0x18000352b  sub     rsp, 20h
0x18000352f  mov     rsi, r8
0x180003532  mov     edi, edx
0x180003534  mov     rbx, rcx
0x180003537  test    rcx, rcx
0x18000353a  jz      short loc_18000359C
0x18000353c  test    edx, edx
0x18000353e  js      short loc_18000359C
0x180003540  mov     eax, [rcx]
0x180003542  cmp     edx, eax
0x180003544  cmovg   edi, eax
0x180003547  lea     edx, [rax+1]; cp
0x18000354a  cmp     edx, eax
0x18000354c  jb      short loc_18000359C
0x18000354e  cmp     dword ptr [rcx+18h], 0
0x180003552  jl      short loc_18000359C
0x180003554  cmp     edx, [rcx+18h]
0x180003557  jbe     short loc_180003562
0x180003559  call    DPA_Grow
0x18000355e  test    eax, eax
0x180003560  jz      short loc_18000359C
0x180003562  mov     eax, [rbx]
0x180003564  cmp     edi, eax
0x180003566  jge     short loc_18000358B
0x180003568  mov     r9, [rbx+8]
0x18000356c  sub     eax, edi
0x18000356e  movsxd  r8, eax
0x180003571  movsxd  rax, edi
0x180003574  shl     r8, 3; Size
0x180003578  lea     rdx, [r9+rax*8]; Src
0x18000357c  lea     eax, [rdi+1]
0x18000357f  movsxd  rcx, eax
0x180003582  lea     rcx, [r9+rcx*8]; void *
0x180003586  call    memmove_0
0x18000358b  mov     rcx, [rbx+8]
0x18000358f  mov     eax, edi
0x180003591  movsxd  rdx, edi
0x180003594  mov     [rcx+rdx*8], rsi
0x180003598  inc     dword ptr [rbx]
0x18000359a  jmp     short loc_18000359F
0x18000359c  or      eax, 0FFFFFFFFh
0x18000359f  mov     rbx, [rsp+28h+arg_0]
0x1800035a4  mov     rsi, [rsp+28h+arg_8]
0x1800035a9  add     rsp, 20h
0x1800035ad  pop     rdi
0x1800035ae  retn
```
