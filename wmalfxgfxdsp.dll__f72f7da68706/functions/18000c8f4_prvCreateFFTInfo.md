# prvCreateFFTInfo

- ea: `0x18000c8f4`
- end: `0x18000c998`
- name: `prvCreateFFTInfo`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c774`

## callees

- `0x18000c8f4`
- `0x1800150c4`
- `0x180015ea8`

## pseudocode

```c
__int64 __fastcall prvCreateFFTInfo(_QWORD *a1, unsigned int a2, unsigned int a3)
{
  unsigned int v6; // ebx
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  unsigned int v9; // ebp
  void *v10; // rax
  unsigned int v11; // ebx

  if ( !a1 )
    return (unsigned int)-2147024809;
  if ( *a1 )
    return (unsigned int)-2147024809;
  if ( a3 < a2 )
    return (unsigned int)-2147024809;
  v6 = a3 - a2;
  if ( a3 - a2 + 1 < a3 - a2 )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v7 = operator new(0x18u);
    v8 = v7;
    if ( v7 )
    {
      v7[1] = 0;
      v7[2] = 0;
      *((_DWORD *)v7 + 1) = a3;
      *(_DWORD *)v7 = a2;
      v9 = 32 * (v6 + 1);
      v10 = operator new(v9);
      v8[1] = v10;
      if ( v10 )
      {
        v11 = 0;
        memset_0(v10, 0, v9);
      }
      else
      {
        v11 = -2147024882;
      }
      *a1 = v8;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18000c8f4  push    rbx
0x18000c8f6  push    rbp
0x18000c8f7  push    rsi
0x18000c8f8  push    rdi
0x18000c8f9  push    r14
0x18000c8fb  sub     rsp, 20h
0x18000c8ff  mov     ebp, r8d
0x18000c902  mov     r14d, edx
0x18000c905  mov     rsi, rcx
0x18000c908  test    rcx, rcx
0x18000c90b  jz      short loc_18000C983
0x18000c90d  cmp     qword ptr [rcx], 0
0x18000c911  jnz     short loc_18000C983
0x18000c913  cmp     r8d, edx
0x18000c916  jb      short loc_18000C983
0x18000c918  mov     ebx, r8d
0x18000c91b  sub     ebx, edx
0x18000c91d  lea     eax, [rbx+1]
0x18000c920  cmp     eax, ebx
0x18000c922  jb      short loc_18000C983
0x18000c924  mov     ecx, 18h; Size
0x18000c929  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c92e  mov     rdi, rax
0x18000c931  test    rax, rax
0x18000c934  jz      short loc_18000C98A
0x18000c936  mov     qword ptr [rax+8], 0
0x18000c93e  mov     qword ptr [rax+10h], 0
0x18000c946  mov     [rax+4], ebp
0x18000c949  mov     [rax], r14d
0x18000c94c  lea     eax, [rbx+1]
0x18000c94f  shl     eax, 5
0x18000c952  mov     ecx, eax; Size
0x18000c954  mov     ebp, eax
0x18000c956  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c95b  mov     [rdi+8], rax
0x18000c95f  test    rax, rax
0x18000c962  jz      short loc_18000C991
0x18000c964  xor     ebx, ebx
0x18000c966  mov     r8d, ebp; Size
0x18000c969  xor     edx, edx; Val
0x18000c96b  mov     rcx, rax; void *
0x18000c96e  call    memset_0
0x18000c973  mov     [rsi], rdi
0x18000c976  mov     eax, ebx
0x18000c978  add     rsp, 20h
0x18000c97c  pop     r14
0x18000c97e  pop     rdi
0x18000c97f  pop     rsi
0x18000c980  pop     rbp
0x18000c981  pop     rbx
0x18000c982  retn
0x18000c983  mov     ebx, 80070057h
0x18000c988  jmp     short loc_18000C976
0x18000c98a  mov     ebx, 8007000Eh
0x18000c98f  jmp     short loc_18000C976
0x18000c991  mov     ebx, 8007000Eh
0x18000c996  jmp     short loc_18000C973
```
