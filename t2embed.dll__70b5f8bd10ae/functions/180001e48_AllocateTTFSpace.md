# AllocateTTFSpace

- ea: `0x180001e48`
- end: `0x180001f1a`
- name: `AllocateTTFSpace`
- size: `210`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ce4`
- `0x180001f60`
- `0x180002bd0`
- `0x18000b540`
- `0x18000bde0`

## callees

- `0x180001e48`
- `0x18000ddd4`

## import_xrefs

- `msvcrt!longjmp` at `0x180001e6f`
- `msvcrt!longjmp` at `0x180001ee3`
- `msvcrt!longjmp` at `0x180001e6f`
- `msvcrt!longjmp` at `0x180001ee3`

## pseudocode

```c
__int64 __fastcall AllocateTTFSpace(__int64 a1, __int64 *a2, int a3, int a4, unsigned int *a5)
{
  __int64 result; // rax
  unsigned int v8; // edx
  unsigned int v9; // ecx
  unsigned int v10; // r8d
  __int64 v11; // rcx

  if ( a3 < 0
    || a4 < 0
    || (result = *a5, (int)result < 0)
    || (v8 = a3 + a4, a3 + a4 < (unsigned int)a3)
    || (v9 = v8 + 4, v8 + 4 < v8) )
  {
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 96) + 48LL), 3321);
  }
  if ( v9 > (unsigned int)result )
  {
    v10 = v9 + ((unsigned int)result >> 1) + 2;
    if ( v10 < v9 || v10 > 0x7FFFFFFF )
    {
      *a5 = 0x7FFFFFFF;
      v10 = 0x7FFFFFFF;
    }
    else
    {
      *a5 = v10;
    }
    v11 = MTX_mem_realloc(*(_QWORD *)(a1 + 96), *a2, v10);
    if ( !v11 )
      longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 96) + 48LL), 3321);
    result = *a2;
    if ( *a2 == *(_QWORD *)a1 )
    {
      result = *a5;
      *(_DWORD *)(a1 + 8) = result;
      *(_QWORD *)a1 = v11;
    }
    else if ( result == *(_QWORD *)(a1 + 32) )
    {
      result = *a5;
      *(_DWORD *)(a1 + 40) = result;
      *(_QWORD *)(a1 + 32) = v11;
    }
    *a2 = v11;
  }
  return result;
}

```

## disassembly

```asm
0x180001e48  mov     [rsp+arg_0], rbx
0x180001e4d  mov     [rsp+arg_8], rsi
0x180001e52  push    rdi
0x180001e53  sub     rsp, 20h
0x180001e57  mov     rsi, rdx
0x180001e5a  mov     rbx, rcx
0x180001e5d  test    r8d, r8d
0x180001e60  jns     short loc_180001E76
0x180001e62  mov     rcx, [rbx+60h]
0x180001e66  mov     edx, 0CF9h; Value
0x180001e6b  add     rcx, 30h ; '0'; Buf
0x180001e6f  call    cs:__imp_longjmp
0x180001e76  test    r9d, r9d
0x180001e79  js      short loc_180001E62
0x180001e7b  mov     rdi, [rsp+28h+arg_20]
0x180001e80  mov     eax, [rdi]
0x180001e82  test    eax, eax
0x180001e84  js      short loc_180001E62
0x180001e86  lea     edx, [r8+r9]
0x180001e8a  cmp     edx, r8d
0x180001e8d  jb      short loc_180001E62
0x180001e8f  lea     ecx, [rdx+4]
0x180001e92  cmp     ecx, edx
0x180001e94  jb      short loc_180001E62
0x180001e96  cmp     ecx, eax
0x180001e98  ja      short loc_180001EAA
0x180001e9a  mov     rbx, [rsp+28h+arg_0]
0x180001e9f  mov     rsi, [rsp+28h+arg_8]
0x180001ea4  add     rsp, 20h
0x180001ea8  pop     rdi
0x180001ea9  retn
0x180001eaa  shr     eax, 1
0x180001eac  lea     r8d, [rax+2]
0x180001eb0  mov     eax, 7FFFFFFFh
0x180001eb5  add     r8d, ecx
0x180001eb8  cmp     r8d, ecx
0x180001ebb  jnb     short loc_180001EEA
0x180001ebd  mov     [rdi], eax
0x180001ebf  mov     r8d, eax
0x180001ec2  mov     rdx, [rsi]
0x180001ec5  mov     rcx, [rbx+60h]
0x180001ec9  call    MTX_mem_realloc
0x180001ece  mov     rcx, rax
0x180001ed1  test    rax, rax
0x180001ed4  jnz     short loc_180001EF4
0x180001ed6  mov     rcx, [rbx+60h]
0x180001eda  mov     edx, 0CF9h; Value
0x180001edf  add     rcx, 30h ; '0'; Buf
0x180001ee3  call    cs:__imp_longjmp
0x180001eea  cmp     r8d, eax
0x180001eed  ja      short loc_180001EBD
0x180001eef  mov     [rdi], r8d
0x180001ef2  jmp     short loc_180001EC2
0x180001ef4  mov     rax, [rsi]
0x180001ef7  cmp     rax, [rbx]
0x180001efa  jnz     short loc_180001F06
0x180001efc  mov     eax, [rdi]
0x180001efe  mov     [rbx+8], eax
0x180001f01  mov     [rbx], rcx
0x180001f04  jmp     short loc_180001F15
0x180001f06  cmp     rax, [rbx+20h]
0x180001f0a  jnz     short loc_180001F15
0x180001f0c  mov     eax, [rdi]
0x180001f0e  mov     [rbx+28h], eax
0x180001f11  mov     [rbx+20h], rcx
0x180001f15  mov     [rsi], rcx
0x180001f18  jmp     short loc_180001E9A
```
