# DPA_Search

- ea: `0x180008d90`
- end: `0x180008ea0`
- name: `DPA_Search`
- size: `272`
- prototype: `int __stdcall(HDPA hdpa, void *pFind, int iStart, PFNDACOMPARE pfnCompare, LPARAM lParam, UINT options)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007e40`

## callees

- `0x180008d90`
- `0x180017010`

## pseudocode

```c
int __stdcall DPA_Search(HDPA hdpa, void *pFind, int iStart, PFNDACOMPARE pfnCompare, LPARAM lParam, UINT options)
{
  int v7; // edi
  int result; // eax
  int v12; // ecx
  int v13; // r12d
  __int64 v14; // rbx
  int v15; // edi
  int v16; // eax

  v7 = *(_DWORD *)hdpa;
  if ( (options & 1) != 0 )
  {
    v12 = 0;
    v13 = 0;
    LODWORD(v14) = 0;
    v15 = v7 - 1;
    while ( v13 <= v15 )
    {
      v14 = (v15 + v13) / 2;
      v16 = ((__int64 (__fastcall *)(void *, _QWORD, LPARAM))pfnCompare)(
              pFind,
              *(_QWORD *)(*((_QWORD *)hdpa + 1) + 8 * v14),
              lParam);
      v12 = v16;
      if ( v16 >= 0 )
      {
        if ( v16 <= 0 )
        {
          for ( ; (int)v14 > 0; LODWORD(v14) = v14 - 1 )
          {
            if ( ((unsigned int (__fastcall *)(void *, _QWORD, LPARAM))pfnCompare)(
                   pFind,
                   *(_QWORD *)(*((_QWORD *)hdpa + 1) + 8LL * (unsigned int)v14 - 8),
                   lParam) )
            {
              break;
            }
          }
          return v14;
        }
        v13 = v14 + 1;
      }
      else
      {
        v15 = v14 - 1;
      }
    }
    result = -1;
    if ( (options & 6) != 0 )
    {
      result = v14;
      if ( v12 > 0 )
        return v13;
    }
  }
  else
  {
    while ( iStart < v7 )
    {
      if ( !((unsigned int (__fastcall *)(void *, _QWORD, LPARAM))pfnCompare)(
              pFind,
              *(_QWORD *)(*((_QWORD *)hdpa + 1) + 8LL * iStart),
              lParam) )
        return iStart;
      ++iStart;
    }
    return -1;
  }
  return result;
}

```

## disassembly

```asm
0x180008d90  push    rbx
0x180008d92  push    rbp
0x180008d93  push    rsi
0x180008d94  push    rdi
0x180008d95  push    r14
0x180008d97  push    r15
0x180008d99  sub     rsp, 28h
0x180008d9d  mov     ebp, [rsp+58h+options]
0x180008da4  mov     r14, r9
0x180008da7  mov     edi, [rcx]
0x180008da9  mov     ebx, r8d
0x180008dac  mov     r15, rdx
0x180008daf  mov     rsi, rcx
0x180008db2  test    bpl, 1
0x180008db6  jnz     short loc_180008DFE
0x180008db8  mov     rbp, [rsp+58h+lParam]
0x180008dc0  cmp     ebx, edi
0x180008dc2  jge     short loc_180008DF4
0x180008dc4  mov     rdx, [rsi+8]
0x180008dc8  mov     r8, rbp
0x180008dcb  movsxd  rax, ebx
0x180008dce  mov     rcx, r15
0x180008dd1  mov     rdx, [rdx+rax*8]
0x180008dd5  mov     rax, r14
0x180008dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ddd  test    eax, eax
0x180008ddf  jz      short loc_180008DE5
0x180008de1  inc     ebx
0x180008de3  jmp     short loc_180008DC0
0x180008de5  mov     eax, ebx
0x180008de7  add     rsp, 28h
0x180008deb  pop     r15
0x180008ded  pop     r14
0x180008def  pop     rdi
0x180008df0  pop     rsi
0x180008df1  pop     rbp
0x180008df2  pop     rbx
0x180008df3  retn
0x180008df4  mov     eax, 0FFFFFFFFh
0x180008df9  jmp     loc_180008E93
0x180008dfe  mov     [rsp+58h+arg_0], r12
0x180008e03  xor     ecx, ecx
0x180008e05  xor     r12d, r12d
0x180008e08  xor     ebx, ebx
0x180008e0a  dec     edi
0x180008e0c  cmp     r12d, edi
0x180008e0f  jg      short loc_180008E7B
0x180008e11  mov     r8, [rsp+58h+lParam]
0x180008e19  lea     eax, [rdi+r12]
0x180008e1d  cdq
0x180008e1e  mov     rcx, r15
0x180008e21  sub     eax, edx
0x180008e23  mov     rdx, [rsi+8]
0x180008e27  sar     eax, 1
0x180008e29  movsxd  rbx, eax
0x180008e2c  mov     rax, r14
0x180008e2f  mov     rdx, [rdx+rbx*8]
0x180008e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e38  mov     ecx, eax
0x180008e3a  test    eax, eax
0x180008e3c  jns     short loc_180008E43
0x180008e3e  lea     edi, [rbx-1]
0x180008e41  jmp     short loc_180008E0C
0x180008e43  jle     short loc_180008E4B
0x180008e45  lea     r12d, [rbx+1]
0x180008e49  jmp     short loc_180008E0C
0x180008e4b  test    ebx, ebx
0x180008e4d  jle     short loc_180008E77
0x180008e4f  mov     rdx, [rsi+8]
0x180008e53  mov     rcx, r15
0x180008e56  mov     r8, [rsp+58h+lParam]
0x180008e5e  mov     eax, ebx
0x180008e60  mov     rdx, [rdx+rax*8-8]
0x180008e65  mov     rax, r14
0x180008e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e6d  test    eax, eax
0x180008e6f  jnz     short loc_180008E77
0x180008e71  dec     ebx
0x180008e73  test    ebx, ebx
0x180008e75  jg      short loc_180008E4F
0x180008e77  mov     eax, ebx
0x180008e79  jmp     short loc_180008E8E
0x180008e7b  mov     eax, 0FFFFFFFFh
0x180008e80  test    bpl, 6
0x180008e84  jz      short loc_180008E8E
0x180008e86  test    ecx, ecx
0x180008e88  mov     eax, ebx
0x180008e8a  cmovg   eax, r12d
0x180008e8e  mov     r12, [rsp+58h+arg_0]
0x180008e93  add     rsp, 28h
0x180008e97  pop     r15
0x180008e99  pop     r14
0x180008e9b  pop     rdi
0x180008e9c  pop     rsi
0x180008e9d  pop     rbp
0x180008e9e  pop     rbx
0x180008e9f  retn
```
