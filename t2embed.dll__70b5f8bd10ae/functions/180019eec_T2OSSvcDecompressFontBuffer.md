# T2OSSvcDecompressFontBuffer

- ea: `0x180019eec`
- end: `0x180019f93`
- name: `T2OSSvcDecompressFontBuffer`
- size: `167`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800190a4`
- `0x18001d488`

## callees

- `0x180019dc0`
- `0x180019eec`
- `0x18001a414`

## pseudocode

```c
__int64 __fastcall T2OSSvcDecompressFontBuffer(void *a1, __int64 a2, LPVOID *a3, __int64 a4, __int64 a5)
{
  unsigned int v6; // ebx

  v6 = 1;
  if ( (unsigned int)AgfaUnPack_TTF_InMemory(a1, a4) )
  {
    *(_DWORD *)(a5 + 944) = 0;
    if ( *a3 )
    {
      T2free(*a3);
      *a3 = 0;
    }
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180019eec  mov     rax, rsp
0x180019eef  mov     [rax+8], rbx
0x180019ef3  mov     [rax+10h], rsi
0x180019ef7  mov     [rax+18h], r8
0x180019efb  push    rdi
0x180019efc  sub     rsp, 50h
0x180019f00  mov     rdi, r8
0x180019f03  mov     qword ptr [rax-10h], 0
0x180019f0b  mov     ebx, 1
0x180019f10  mov     rsi, [rsp+58h+arg_20]
0x180019f18  mov     [rax-10h], rsi
0x180019f1c  mov     [rax-38h], r9
0x180019f20  mov     r9, r8
0x180019f23  call    AgfaUnPack_TTF_InMemory
0x180019f28  test    eax, eax
0x180019f2a  jz      short loc_180019F50
0x180019f2c  mov     dword ptr [rsi+3B0h], 0
0x180019f36  mov     rcx, [rdi]; lpMem
0x180019f39  test    rcx, rcx
0x180019f3c  jz      short loc_180019F4A
0x180019f3e  call    T2free
0x180019f43  mov     qword ptr [rdi], 0
0x180019f4a  xor     ebx, ebx
0x180019f4c  mov     [rsp+58h+var_18], ebx
0x180019f50  jmp     short loc_180019F81
0x180019f52  mov     rbx, [rsp+58h+arg_10]
0x180019f57  cmp     qword ptr [rbx], 0
0x180019f5b  jz      short loc_180019F6C
0x180019f5d  mov     rcx, [rbx]; lpMem
0x180019f60  call    T2free
0x180019f65  mov     qword ptr [rbx], 0
0x180019f6c  mov     rax, [rsp+58h+var_10]
0x180019f71  mov     dword ptr [rax+3B0h], 209h
0x180019f7b  xor     ebx, ebx
0x180019f7d  mov     [rsp+58h+var_18], ebx
0x180019f81  mov     eax, ebx
0x180019f83  mov     rbx, [rsp+58h+arg_0]
0x180019f88  mov     rsi, [rsp+58h+arg_8]
0x180019f8d  add     rsp, 50h
0x180019f91  pop     rdi
0x180019f92  retn
```
