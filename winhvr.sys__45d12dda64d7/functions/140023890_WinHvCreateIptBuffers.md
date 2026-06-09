# WinHvCreateIptBuffers

- ea: `0x140023890`
- end: `0x14002390c`
- name: `WinHvCreateIptBuffers`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001ef0`
- `0x140023890`

## pseudocode

```c
__int64 __fastcall WinHvCreateIptBuffers(int a1, char a2, _QWORD *a3)
{
  __int64 result; // rax
  __int64 Src; // [rsp+60h] [rbp+18h] BYREF
  __int64 v6; // [rsp+68h] [rbp+20h] BYREF

  Src = 0;
  v6 = 0;
  if ( !a3 )
    return 3221225485LL;
  LODWORD(Src) = a1;
  BYTE4(Src) = a2;
  result = WinHvpAllocatingHypercall(-1, 0x8000FFFF, 231, 0, &Src, 8u, &v6, 8u);
  if ( (int)result >= 0 )
    *a3 = v6;
  return result;
}

```

## disassembly

```asm
0x140023890  push    rbx
0x140023892  sub     rsp, 40h
0x140023896  mov     [rsp+48h+arg_10], 0
0x14002389f  mov     rbx, r8
0x1400238a2  mov     [rsp+48h+arg_18], 0
0x1400238ab  test    r8, r8
0x1400238ae  jnz     short loc_1400238B7
0x1400238b0  mov     eax, 0C000000Dh
0x1400238b5  jmp     short loc_140023905
0x1400238b7  mov     dword ptr [rsp+48h+arg_10], ecx
0x1400238bb  lea     rax, [rsp+48h+arg_18]
0x1400238c0  mov     ecx, 8
0x1400238c5  mov     byte ptr [rsp+48h+arg_10+4], dl
0x1400238c9  mov     [rsp+48h+var_10], rcx; size_t
0x1400238ce  xor     r9d, r9d; int
0x1400238d1  mov     [rsp+48h+var_18], rax; void *
0x1400238d6  mov     edx, 8000FFFFh; int
0x1400238db  mov     [rsp+48h+Size], rcx; Size
0x1400238e0  lea     rax, [rsp+48h+arg_10]
0x1400238e5  or      rcx, 0FFFFFFFFFFFFFFFFh; int
0x1400238e9  mov     [rsp+48h+Src], rax; Src
0x1400238ee  mov     r8d, 0E7h; int
0x1400238f4  call    WinHvpAllocatingHypercall
0x1400238f9  test    eax, eax
0x1400238fb  js      short loc_140023905
0x1400238fd  mov     rcx, [rsp+48h+arg_18]
0x140023902  mov     [rbx], rcx
0x140023905  add     rsp, 40h
0x140023909  pop     rbx
0x14002390a  retn
```
