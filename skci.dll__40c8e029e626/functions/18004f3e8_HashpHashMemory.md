# HashpHashMemory

- ea: `0x18004f3e8`
- end: `0x18004f4cc`
- name: `HashpHashMemory`
- size: `228`
- prototype: ``
- caller_count: `11`
- callee_count: `7`
- tags: ``

## callers

- `0x180010ab0`
- `0x18001156c`
- `0x1800145f4`
- `0x180014a14`
- `0x1800150c0`
- `0x180015360`
- `0x180015550`
- `0x180015624`
- `0x18001673c`
- `0x180016f2c`
- `0x180017f60`

## callees

- `0x180018f84`
- `0x180018fb0`
- `0x180033950`
- `0x18004c0c8`
- `0x18004c134`
- `0x18004c1ac`
- `0x18004f3e8`

## pseudocode

```c
__int64 __fastcall HashpHashMemory(int a1, unsigned int a2, __int64 a3, void *a4, __int64 a5)
{
  _DWORD *v9; // rax
  _DWORD *v10; // rdi
  int inited; // esi
  size_t v12; // r8
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  unsigned int i; // ebx
  __int64 v18; // r8

  v9 = (_DWORD *)MincryptAlloc(240);
  v10 = v9;
  if ( v9 )
  {
    *v9 = a1;
    inited = HashpInitHash(v9, a5);
    if ( inited >= 0 )
    {
      for ( i = 0; i < a2; ++i )
      {
        v18 = *(unsigned int *)(a3 + 16LL * i);
        if ( (_DWORD)v18 )
          HashpHashBytes(v10, *(_QWORD *)(a3 + 16LL * i + 8), v18);
      }
      HashpFinalizeHash(v10, a4);
      goto LABEL_20;
    }
  }
  else
  {
    inited = -1073741801;
  }
  v12 = 0;
  v13 = a1 - 32771;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( v14 )
    {
      v15 = v14 - 8;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( v16 )
        {
          if ( v16 == 1 )
            v12 = 64;
        }
        else
        {
          v12 = 48;
        }
      }
      else
      {
        v12 = 32;
      }
    }
    else
    {
      v12 = 20;
    }
  }
  else
  {
    v12 = 16;
  }
  memset_0(a4, 0, v12);
  if ( v10 )
LABEL_20:
    MincryptFree(v10);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18004f3e8  push    rbx
0x18004f3ea  push    rbp
0x18004f3eb  push    rsi
0x18004f3ec  push    rdi
0x18004f3ed  push    r14
0x18004f3ef  push    r15
0x18004f3f1  sub     rsp, 28h
0x18004f3f5  mov     ebx, ecx
0x18004f3f7  mov     r15, r9
0x18004f3fa  mov     ecx, 0F0h
0x18004f3ff  mov     r14, r8
0x18004f402  mov     ebp, edx
0x18004f404  call    MincryptAlloc
0x18004f409  mov     rdi, rax
0x18004f40c  test    rax, rax
0x18004f40f  jnz     short loc_18004F43B
0x18004f411  mov     esi, 0C0000017h
0x18004f416  xor     r8d, r8d
0x18004f419  sub     ebx, 8003h
0x18004f41f  jz      short loc_18004F49F
0x18004f421  sub     ebx, 1
0x18004f424  jz      short loc_18004F497
0x18004f426  sub     ebx, 8
0x18004f429  jz      short loc_18004F48F
0x18004f42b  sub     ebx, 1
0x18004f42e  jz      short loc_18004F487
0x18004f430  cmp     ebx, 1
0x18004f433  jnz     short loc_18004F4A5
0x18004f435  lea     r8d, [rbx+3Fh]
0x18004f439  jmp     short loc_18004F4A5
0x18004f43b  mov     rdx, [rsp+58h+arg_20]
0x18004f443  mov     rcx, rdi
0x18004f446  mov     [rax], ebx
0x18004f448  call    HashpInitHash
0x18004f44d  mov     esi, eax
0x18004f44f  test    eax, eax
0x18004f451  js      short loc_18004F416
0x18004f453  xor     ebx, ebx
0x18004f455  test    ebp, ebp
0x18004f457  jz      short loc_18004F47A
0x18004f459  mov     edx, ebx
0x18004f45b  add     rdx, rdx
0x18004f45e  mov     r8d, [r14+rdx*8]
0x18004f462  test    r8d, r8d
0x18004f465  jz      short loc_18004F474
0x18004f467  mov     rdx, [r14+rdx*8+8]
0x18004f46c  mov     rcx, rdi
0x18004f46f  call    HashpHashBytes
0x18004f474  inc     ebx
0x18004f476  cmp     ebx, ebp
0x18004f478  jb      short loc_18004F459
0x18004f47a  mov     rdx, r15
0x18004f47d  mov     rcx, rdi
0x18004f480  call    HashpFinalizeHash
0x18004f485  jmp     short loc_18004F4B4
0x18004f487  mov     r8d, 30h ; '0'
0x18004f48d  jmp     short loc_18004F4A5
0x18004f48f  mov     r8d, 20h ; ' '
0x18004f495  jmp     short loc_18004F4A5
0x18004f497  mov     r8d, 14h
0x18004f49d  jmp     short loc_18004F4A5
0x18004f49f  mov     r8d, 10h; Size
0x18004f4a5  xor     edx, edx; Val
0x18004f4a7  mov     rcx, r15; void *
0x18004f4aa  call    memset_0
0x18004f4af  test    rdi, rdi
0x18004f4b2  jz      short loc_18004F4BC
0x18004f4b4  mov     rcx, rdi
0x18004f4b7  call    MincryptFree
0x18004f4bc  mov     eax, esi
0x18004f4be  add     rsp, 28h
0x18004f4c2  pop     r15
0x18004f4c4  pop     r14
0x18004f4c6  pop     rdi
0x18004f4c7  pop     rsi
0x18004f4c8  pop     rbp
0x18004f4c9  pop     rbx
0x18004f4ca  retn
```
