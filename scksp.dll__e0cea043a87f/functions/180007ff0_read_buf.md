# read_buf

- ea: `0x180007ff0`
- end: `0x180008090`
- name: `read_buf`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180005630`
- `0x180007b40`

## callees

- `0x1800042f0`
- `0x1800046a0`
- `0x180007ff0`
- `0x180009e76`

## pseudocode

```c
__int64 __fastcall read_buf(__int64 a1, void *a2, unsigned int a3)
{
  unsigned int v3; // eax
  unsigned int v5; // edi
  __int64 result; // rax
  const void *v8; // rdx
  int v9; // ecx
  int v10; // eax

  v3 = *(_DWORD *)(a1 + 8);
  v5 = v3;
  if ( v3 > a3 )
    v5 = a3;
  if ( !v5 )
    return 0;
  v8 = *(const void **)a1;
  *(_DWORD *)(a1 + 8) = v3 - v5;
  memcpy_0(a2, v8, v5);
  v9 = *(_DWORD *)(*(_QWORD *)(a1 + 40) + 44LL);
  if ( v9 == 1 )
  {
    v10 = adler32(*(unsigned int *)(a1 + 76), a2);
LABEL_9:
    *(_DWORD *)(a1 + 76) = v10;
    goto LABEL_10;
  }
  if ( v9 == 2 )
  {
    v10 = crc32(*(unsigned int *)(a1 + 76), a2);
    goto LABEL_9;
  }
LABEL_10:
  *(_QWORD *)a1 += v5;
  result = v5;
  *(_DWORD *)(a1 + 12) += v5;
  return result;
}

```

## disassembly

```asm
0x180007ff0  mov     [rsp+arg_8], rbx
0x180007ff5  mov     [rsp+arg_10], rsi
0x180007ffa  push    rdi
0x180007ffb  sub     rsp, 20h
0x180007fff  mov     eax, [rcx+8]
0x180008002  mov     rsi, rdx
0x180008005  cmp     eax, r8d
0x180008008  mov     edi, eax
0x18000800a  mov     rbx, rcx
0x18000800d  cmova   edi, r8d
0x180008011  test    edi, edi
0x180008013  jnz     short loc_180008027
0x180008015  xor     eax, eax
0x180008017  mov     rbx, [rsp+28h+arg_8]
0x18000801c  mov     rsi, [rsp+28h+arg_10]
0x180008021  add     rsp, 20h
0x180008025  pop     rdi
0x180008026  retn
0x180008027  mov     rdx, [rcx]; Src
0x18000802a  sub     eax, edi
0x18000802c  mov     [rcx+8], eax
0x18000802f  mov     rcx, rsi; void *
0x180008032  mov     [rsp+28h+arg_0], rbp
0x180008037  mov     r8d, edi; Size
0x18000803a  mov     ebp, edi
0x18000803c  call    memcpy_0
0x180008041  mov     rax, [rbx+28h]
0x180008045  mov     ecx, [rax+2Ch]
0x180008048  cmp     ecx, 1
0x18000804b  jnz     short loc_18000805D
0x18000804d  mov     ecx, [rbx+4Ch]
0x180008050  mov     r8d, edi
0x180008053  mov     rdx, rsi
0x180008056  call    adler32
0x18000805b  jmp     short loc_180008070
0x18000805d  cmp     ecx, 2
0x180008060  jnz     short loc_180008073
0x180008062  mov     ecx, [rbx+4Ch]
0x180008065  mov     r8d, edi
0x180008068  mov     rdx, rsi
0x18000806b  call    crc32
0x180008070  mov     [rbx+4Ch], eax
0x180008073  add     [rbx], rbp
0x180008076  mov     eax, edi
0x180008078  add     [rbx+0Ch], edi
0x18000807b  mov     rbx, [rsp+28h+arg_8]
0x180008080  mov     rbp, [rsp+28h+arg_0]
0x180008085  mov     rsi, [rsp+28h+arg_10]
0x18000808a  add     rsp, 20h
0x18000808e  pop     rdi
0x18000808f  retn
```
