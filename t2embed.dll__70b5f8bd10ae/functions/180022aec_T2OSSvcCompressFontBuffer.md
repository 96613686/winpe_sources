# T2OSSvcCompressFontBuffer

- ea: `0x180022aec`
- end: `0x180022b9b`
- name: `T2OSSvcCompressFontBuffer`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020588`

## callees

- `0x18000eb94`
- `0x180019dc0`
- `0x180022aec`

## pseudocode

```c
__int64 __fastcall T2OSSvcCompressFontBuffer(void *a1, __int64 a2, __int64 a3, LPVOID *a4, __int64 a5, __int64 a6)
{
  unsigned int v7; // ebx

  v7 = 1;
  if ( (unsigned int)AgfaPack_TTF_InMemory(a1, a5) )
  {
    *(_DWORD *)(a6 + 944) = 0;
    if ( *a4 )
    {
      T2free(*a4);
      *a4 = 0;
    }
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180022aec  mov     r11, rsp
0x180022aef  mov     [r11+8], rbx
0x180022af3  mov     [r11+10h], rsi
0x180022af7  mov     [r11+20h], r9
0x180022afb  push    rdi
0x180022afc  sub     rsp, 60h
0x180022b00  mov     rdi, r9
0x180022b03  mov     qword ptr [r11-10h], 0
0x180022b0b  mov     ebx, 1
0x180022b10  mov     rsi, [rsp+68h+arg_28]
0x180022b18  mov     [r11-10h], rsi
0x180022b1c  mov     rax, [rsp+68h+arg_20]
0x180022b24  mov     [r11-48h], rax
0x180022b28  call    AgfaPack_TTF_InMemory
0x180022b2d  test    eax, eax
0x180022b2f  jz      short loc_180022B55
0x180022b31  mov     dword ptr [rsi+3B0h], 0
0x180022b3b  mov     rcx, [rdi]; lpMem
0x180022b3e  test    rcx, rcx
0x180022b41  jz      short loc_180022B4F
0x180022b43  call    T2free
0x180022b48  mov     qword ptr [rdi], 0
0x180022b4f  xor     ebx, ebx
0x180022b51  mov     [rsp+68h+var_18], ebx
0x180022b55  jmp     short loc_180022B89
0x180022b57  mov     rbx, [rsp+68h+arg_18]
0x180022b5f  cmp     qword ptr [rbx], 0
0x180022b63  jz      short loc_180022B74
0x180022b65  mov     rcx, [rbx]; lpMem
0x180022b68  call    T2free
0x180022b6d  mov     qword ptr [rbx], 0
0x180022b74  mov     rax, [rsp+68h+var_10]
0x180022b79  mov     dword ptr [rax+3B0h], 20Ah
0x180022b83  xor     ebx, ebx
0x180022b85  mov     [rsp+68h+var_18], ebx
0x180022b89  mov     eax, ebx
0x180022b8b  mov     rbx, [rsp+68h+arg_0]
0x180022b90  mov     rsi, [rsp+68h+arg_8]
0x180022b95  add     rsp, 60h
0x180022b99  pop     rdi
0x180022b9a  retn
```
