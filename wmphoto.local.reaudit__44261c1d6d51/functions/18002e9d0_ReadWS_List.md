# ReadWS_List

- ea: `0x18002e9d0`
- end: `0x18002ea83`
- name: `ReadWS_List`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002e9d0`
- `0x180043e40`

## pseudocode

```c
__int64 __fastcall ReadWS_List(_QWORD *a1, char *a2, unsigned __int64 a3)
{
  unsigned __int64 v4; // rdi
  size_t v5; // rcx
  unsigned int v7; // ebp
  __int64 v8; // rdx
  size_t v9; // rbx
  __int64 v10; // rdx

  v4 = a3;
  v5 = a1[2];
  if ( v5 + a3 < v5 )
  {
    return (unsigned int)-103;
  }
  else
  {
    v7 = 0;
    v8 = a1[3] << 12;
    if ( a1[1] < a3 + v8 + v5 )
      v4 = a1[1] - v8 - v5;
    while ( v4 )
    {
      v9 = v4;
      if ( 4096 - v5 <= v4 )
        v9 = 4096 - v5;
      memcpy_0(a2, (const void *)(v5 + *a1), v9);
      a2 += v9;
      v5 = v9 + a1[2];
      v4 -= v9;
      a1[2] = v5;
      if ( v5 == 4096 )
      {
        v10 = *(_QWORD *)(*a1 - 8LL);
        ++a1[3];
        *a1 = v10 + 8;
        v5 = 0;
        a1[2] = 0;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18002e9d0  push    rbx
0x18002e9d2  push    rbp
0x18002e9d3  push    rsi
0x18002e9d4  push    rdi
0x18002e9d5  push    r14
0x18002e9d7  sub     rsp, 20h
0x18002e9db  mov     rsi, rcx
0x18002e9de  mov     rdi, r8
0x18002e9e1  mov     rcx, [rcx+10h]
0x18002e9e5  mov     r14, rdx
0x18002e9e8  lea     rax, [rcx+r8]
0x18002e9ec  cmp     rax, rcx
0x18002e9ef  jb      short loc_18002EA64
0x18002e9f1  mov     rdx, [rsi+18h]
0x18002e9f5  xor     ebp, ebp
0x18002e9f7  shl     rdx, 0Ch
0x18002e9fb  lea     rax, [rdx+rcx]
0x18002e9ff  add     rax, r8
0x18002ea02  cmp     [rsi+8], rax
0x18002ea06  jb      short loc_18002EA77
0x18002ea08  test    rdi, rdi
0x18002ea0b  jz      short loc_18002EA69
0x18002ea0d  mov     rdx, [rsi]
0x18002ea10  mov     eax, 1000h
0x18002ea15  sub     rax, rcx
0x18002ea18  mov     rbx, rdi
0x18002ea1b  cmp     rax, rdi
0x18002ea1e  cmovbe  rbx, rax
0x18002ea22  add     rdx, rcx; Src
0x18002ea25  mov     r8, rbx; Size
0x18002ea28  mov     rcx, r14; void *
0x18002ea2b  call    memcpy_0
0x18002ea30  mov     rcx, [rsi+10h]
0x18002ea34  add     r14, rbx
0x18002ea37  add     rcx, rbx
0x18002ea3a  sub     rdi, rbx
0x18002ea3d  mov     [rsi+10h], rcx
0x18002ea41  cmp     rcx, 1000h
0x18002ea48  jnz     short loc_18002EA08
0x18002ea4a  mov     rcx, [rsi]
0x18002ea4d  mov     rdx, [rcx-8]
0x18002ea51  inc     qword ptr [rsi+18h]
0x18002ea55  add     rdx, 8
0x18002ea59  mov     [rsi], rdx
0x18002ea5c  xor     ecx, ecx
0x18002ea5e  mov     [rsi+10h], rbp
0x18002ea62  jmp     short loc_18002EA08
0x18002ea64  mov     ebp, 0FFFFFF99h
0x18002ea69  mov     eax, ebp
0x18002ea6b  add     rsp, 20h
0x18002ea6f  pop     r14
0x18002ea71  pop     rdi
0x18002ea72  pop     rsi
0x18002ea73  pop     rbp
0x18002ea74  pop     rbx
0x18002ea75  retn
0x18002ea77  mov     rdi, [rsi+8]
0x18002ea7b  sub     rdi, rdx
0x18002ea7e  sub     rdi, rcx
0x18002ea81  jmp     short loc_18002EA08
```
