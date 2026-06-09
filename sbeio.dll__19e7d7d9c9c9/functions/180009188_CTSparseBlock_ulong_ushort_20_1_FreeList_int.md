# CTSparseBlock<ulong,ushort *,20,1>::FreeList(int)

- ea: `0x180009188`
- end: `0x1800091fb`
- name: `?FreeList@?$CTSparseBlock@KPEAG$0BE@$00@@QEAAJH@Z`
- size: `115`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180007bb4`
- `0x180007bd8`
- `0x18000ebd0`
- `0x1800117c0`
- `0x180018074`
- `0x1800182d4`
- `0x180018344`
- `0x1800209d0`

## callees

- `0x180001f1c`
- `0x180009188`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,unsigned short *,20,1>::FreeList(__int64 a1)
{
  __int64 v2; // rdi
  __int64 result; // rax
  __int64 v4; // rdx

  *(_DWORD *)(a1 + 12) &= ~1u;
  *(_DWORD *)(a1 + 8) = 0;
  *(_WORD *)(a1 + 24) = 0;
  *(_BYTE *)(a1 + 26) = 0;
  memset_0((void *)(a1 + 32), 0, 0xA0u);
  v2 = *(_QWORD *)(a1 + 192);
  result = 0;
  *(_QWORD *)(a1 + 192) = 0;
  do
  {
    if ( !v2 )
      break;
    v4 = v2;
    v2 = *(_QWORD *)(v2 + 192);
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, v4);
  }
  while ( (int)result >= 0 );
  return result;
}

```

## disassembly

```asm
0x180009188  mov     [rsp+arg_0], rbx
0x18000918d  push    rdi
0x18000918e  sub     rsp, 20h
0x180009192  and     dword ptr [rcx+0Ch], 0FFFFFFFEh
0x180009196  xor     eax, eax
0x180009198  mov     dword ptr [rcx+8], 0
0x18000919f  mov     rbx, rcx
0x1800091a2  mov     [rcx+18h], ax
0x1800091a6  xor     edx, edx; Val
0x1800091a8  mov     [rcx+1Ah], al
0x1800091ab  mov     r8d, 0A0h; Size
0x1800091b1  add     rcx, 20h ; ' '; void *
0x1800091b5  call    memset_0
0x1800091ba  mov     rdi, [rbx+0C0h]
0x1800091c1  xor     eax, eax
0x1800091c3  mov     qword ptr [rbx+0C0h], 0
0x1800091ce  test    rdi, rdi
0x1800091d1  jz      short loc_1800091F0
0x1800091d3  mov     rax, [rbx]
0x1800091d6  mov     rdx, rdi
0x1800091d9  mov     rdi, [rdi+0C0h]
0x1800091e0  mov     rcx, rbx
0x1800091e3  mov     rax, [rax+8]
0x1800091e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091ec  test    eax, eax
0x1800091ee  jns     short loc_1800091CE
0x1800091f0  mov     rbx, [rsp+28h+arg_0]
0x1800091f5  add     rsp, 20h
0x1800091f9  pop     rdi
0x1800091fa  retn
```
