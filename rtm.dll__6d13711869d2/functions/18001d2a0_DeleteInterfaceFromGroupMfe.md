# DeleteInterfaceFromGroupMfe

- ea: `0x18001d2a0`
- end: `0x18001d372`
- name: `DeleteInterfaceFromGroupMfe`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d378`

## callees

- `0x18001d2a0`
- `0x18001d908`

## pseudocode

```c
__int64 __fastcall DeleteInterfaceFromGroupMfe(__int64 a1, int a2, int a3, int a4, int a5, int a6)
{
  __int64 result; // rax
  unsigned int v7; // esi
  __int64 v10; // r14
  _QWORD **v11; // rbx
  _QWORD *v12; // rdi
  unsigned int v13; // [rsp+40h] [rbp-48h]

  result = (unsigned int)dword_18002B934;
  v7 = 0;
  v13 = 0;
  if ( dword_18002B934 )
  {
    v10 = a1 + 88;
    do
    {
      v11 = (_QWORD **)(v10 + 16LL * v7);
      v12 = *v11;
      if ( *v11 != v11 )
      {
        do
        {
          if ( *((_DWORD *)v12 + 24) )
            DeleteInterfaceFromSourceMfe(a1, (__int64)(v12 - 2), a2, a3, a4, a5, a6, 0);
          v12 = (_QWORD *)*v12;
        }
        while ( v12 != v11 );
        result = (unsigned int)dword_18002B934;
        v10 = a1 + 88;
        v7 = v13;
      }
      v13 = ++v7;
    }
    while ( v7 < (unsigned int)result );
  }
  return result;
}

```

## disassembly

```asm
0x18001d2a0  mov     [rsp+arg_0], rbx
0x18001d2a5  mov     [rsp+arg_10], r8d
0x18001d2aa  mov     [rsp+arg_8], edx
0x18001d2ae  push    rbp
0x18001d2af  push    rsi
0x18001d2b0  push    rdi
0x18001d2b1  push    r12
0x18001d2b3  push    r13
0x18001d2b5  push    r14
0x18001d2b7  push    r15
0x18001d2b9  sub     rsp, 50h
0x18001d2bd  mov     eax, cs:dword_18002B934
0x18001d2c3  xor     esi, esi
0x18001d2c5  mov     [rsp+88h+var_48], esi
0x18001d2c9  mov     r13d, r9d
0x18001d2cc  mov     rbp, rcx
0x18001d2cf  test    eax, eax
0x18001d2d1  jz      loc_18001D35A
0x18001d2d7  mov     r15d, [rsp+88h+arg_28]
0x18001d2df  lea     r14, [rcx+58h]
0x18001d2e3  mov     r12d, [rsp+88h+arg_20]
0x18001d2eb  mov     ebx, esi
0x18001d2ed  shl     rbx, 4
0x18001d2f1  add     rbx, r14
0x18001d2f4  mov     rdi, [rbx]
0x18001d2f7  cmp     rdi, rbx
0x18001d2fa  jz      short loc_18001D350
0x18001d2fc  mov     r14d, [rsp+88h+arg_10]
0x18001d304  mov     esi, [rsp+88h+arg_8]
0x18001d30b  lea     rdx, [rdi-10h]
0x18001d30f  cmp     dword ptr [rdx+70h], 0
0x18001d313  jz      short loc_18001D33A
0x18001d315  mov     [rsp+88h+var_50], 0
0x18001d31d  mov     r9d, r14d
0x18001d320  mov     [rsp+88h+var_58], r15d
0x18001d325  mov     r8d, esi
0x18001d328  mov     [rsp+88h+var_60], r12d
0x18001d32d  mov     rcx, rbp
0x18001d330  mov     [rsp+88h+var_68], r13d
0x18001d335  call    DeleteInterfaceFromSourceMfe
0x18001d33a  mov     rdi, [rdi]
0x18001d33d  cmp     rdi, rbx
0x18001d340  jnz     short loc_18001D30B
0x18001d342  mov     eax, cs:dword_18002B934
0x18001d348  lea     r14, [rbp+58h]
0x18001d34c  mov     esi, [rsp+88h+var_48]
0x18001d350  inc     esi
0x18001d352  mov     [rsp+88h+var_48], esi
0x18001d356  cmp     esi, eax
0x18001d358  jb      short loc_18001D2EB
0x18001d35a  mov     rbx, [rsp+88h+arg_0]
0x18001d362  add     rsp, 50h
0x18001d366  pop     r15
0x18001d368  pop     r14
0x18001d36a  pop     r13
0x18001d36c  pop     r12
0x18001d36e  pop     rdi
0x18001d36f  pop     rsi
0x18001d370  pop     rbp
0x18001d371  retn
```
