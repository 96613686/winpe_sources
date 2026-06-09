# DigestSsiCreateTokenInfo

- ea: `0x180028ef4`
- end: `0x180028fe9`
- name: `DigestSsiCreateTokenInfo`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180028ff0`

## callees

- `0x1800061a0`
- `0x180011fec`
- `0x1800185b8`
- `0x180028ef4`

## pseudocode

```c
__int64 __fastcall DigestSsiCreateTokenInfo(_QWORD *a1, __int64 *a2)
{
  unsigned int v4; // ebx
  __int64 Memory; // rax
  PVOID *v6; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
  v4 = 0;
  *a2 = 0;
  Memory = DigestAllocateMemory(0x40u);
  if ( Memory )
  {
    *(_QWORD *)(Memory + 24) = a1[19];
    *(_QWORD *)(Memory + 8) = a1[20];
    *(_DWORD *)(Memory + 16) = 7;
    *(_QWORD *)(Memory + 48) = a1[20];
    *(_QWORD *)(Memory + 32) = a1[21];
    *a2 = Memory;
    goto LABEL_9;
  }
  v4 = -2146893056;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, 2148074240LL);
LABEL_9:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && *((char *)v6 + 28) < 0 )
    WPP_SF_d(v6[2], 184, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180028ef4  push    rbx
0x180028ef6  push    rbp
0x180028ef7  push    rsi
0x180028ef8  push    rdi
0x180028ef9  sub     rsp, 28h
0x180028efd  mov     rsi, rdx
0x180028f00  mov     rdi, rcx
0x180028f03  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f0a  lea     rbp, WPP_GLOBAL_Control
0x180028f11  cmp     rcx, rbp
0x180028f14  jz      short loc_180028F31
0x180028f16  test    byte ptr [rcx+1Ch], 80h
0x180028f1a  jz      short loc_180028F31
0x180028f1c  mov     rcx, [rcx+10h]
0x180028f20  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x180028f27  mov     edx, 0B6h
0x180028f2c  call    WPP_SF_
0x180028f31  xor     ebx, ebx
0x180028f33  mov     [rsi], rbx
0x180028f36  lea     ecx, [rbx+40h]; Size
0x180028f39  call    DigestAllocateMemory
0x180028f3e  mov     rcx, rax
0x180028f41  test    rax, rax
0x180028f44  jnz     short loc_180028F7E
0x180028f46  mov     ebx, 80090300h
0x180028f4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f52  cmp     rcx, rbp
0x180028f55  jz      loc_180028FDE
0x180028f5b  test    byte ptr [rcx+1Ch], 1
0x180028f5f  jz      short loc_180028FBB
0x180028f61  mov     rcx, [rcx+10h]
0x180028f65  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x180028f6c  mov     edx, 0B7h
0x180028f71  mov     r9d, 80090300h
0x180028f77  call    WPP_SF_d
0x180028f7c  jmp     short loc_180028FB4
0x180028f7e  mov     rax, [rdi+98h]
0x180028f85  mov     [rcx+18h], rax
0x180028f89  mov     rax, [rdi+0A0h]
0x180028f90  mov     [rcx+8], rax
0x180028f94  mov     dword ptr [rcx+10h], 7
0x180028f9b  mov     rax, [rdi+0A0h]
0x180028fa2  mov     [rcx+30h], rax
0x180028fa6  mov     rax, [rdi+0A8h]
0x180028fad  mov     [rcx+20h], rax
0x180028fb1  mov     [rsi], rcx
0x180028fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180028fbb  cmp     rcx, rbp
0x180028fbe  jz      short loc_180028FDE
0x180028fc0  test    byte ptr [rcx+1Ch], 80h
0x180028fc4  jz      short loc_180028FDE
0x180028fc6  mov     rcx, [rcx+10h]
0x180028fca  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x180028fd1  mov     edx, 0B8h
0x180028fd6  mov     r9d, ebx
0x180028fd9  call    WPP_SF_d
0x180028fde  mov     eax, ebx
0x180028fe0  add     rsp, 28h
0x180028fe4  pop     rdi
0x180028fe5  pop     rsi
0x180028fe6  pop     rbp
0x180028fe7  pop     rbx
0x180028fe8  retn
```
