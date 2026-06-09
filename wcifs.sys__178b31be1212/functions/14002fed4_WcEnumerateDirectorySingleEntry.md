# WcEnumerateDirectorySingleEntry

- ea: `0x14002fed4`
- end: `0x1400300a9`
- name: `WcEnumerateDirectorySingleEntry`
- size: `469`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, __int64, unsigned int, unsigned __int8, int, int, unsigned int, __int64, char, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140014c90`

## callees

- `0x14001414c`
- `0x140029060`
- `0x14002fed4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140030082`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030082`
- `ntoskrnl!ExAllocatePool2` at `0x14002ff20`
- `ntoskrnl!ExAllocatePool2` at `0x14002ff20`
- `FLTMGR!FltQueryDirectoryFileEx` at `0x14002ff98`
- `FLTMGR!FltQueryDirectoryFileEx` at `0x14002ff98`

## pseudocode

```c
__int64 __fastcall WcEnumerateDirectorySingleEntry(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        unsigned __int8 a8,
        int a9,
        int a10,
        unsigned int a11,
        __int64 a12,
        char a13,
        __int64 a14)
{
  unsigned int v14; // r12d
  __int64 v15; // rbx
  void *Pool2; // rsi
  unsigned int v19; // ebx
  _QWORD *v20; // rdi
  int v21; // r15d
  char i; // bp
  __int64 *v23; // rax
  int v24; // eax
  __int64 v25; // r8
  _QWORD *v26; // rax
  __int64 v27; // r9
  __int64 v30; // [rsp+B8h] [rbp+10h] BYREF
  __int64 v31; // [rsp+C0h] [rbp+18h]

  v31 = a3;
  v14 = a7;
  v15 = a3;
  a10 = 0;
  v30 = 0;
  Pool2 = (void *)ExAllocatePool2(256, a7, 1852130135);
  if ( Pool2 )
  {
    v20 = 0;
    v21 = a8 | 0x10;
    for ( i = 1; ; i = 0 )
    {
      if ( v20 )
      {
        v23 = (__int64 *)v20[3];
        v15 = v23[2];
        a2 = *v23;
        v31 = v15;
      }
      v24 = FltQueryDirectoryFileEx(a2, v15, Pool2, v14, a4, v21, a6, &a10);
      v19 = v24;
      if ( v24 >= 0 )
        break;
      if ( v24 != -1073741809 && v24 != -2147483642 )
        goto LABEL_17;
      v26 = (_QWORD *)(a1 + 56);
      v20 = (_QWORD *)(v20 ? *v20 : *v26);
      if ( v20 == v26 )
        goto LABEL_17;
      v15 = v31;
    }
    if ( (unsigned __int8)WcShouldSkipReparsePointInDirectoryEntry(a4, 2684354591LL, v25, Pool2) )
    {
      v19 = -1073741809;
    }
    else
    {
      LOBYTE(v27) = i;
      v19 = WcMungeDirectoryEntry(a4, a5, 1, v27, a9, 268369920, v14, (__int64)Pool2, a11, a12, a13, (__int64)&v30, a14);
    }
LABEL_17:
    ExFreePoolWithTag(Pool2, 0x6E654357u);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v19;
}

```

## disassembly

```asm
0x14002fed4  mov     rax, rsp
0x14002fed7  mov     [rax+20h], rbx
0x14002fedb  mov     [rax+18h], r8
0x14002fedf  mov     [rax+8], rcx
0x14002fee3  push    rbp
0x14002fee4  push    rsi
0x14002fee5  push    rdi
0x14002fee6  push    r12
0x14002fee8  push    r13
0x14002feea  push    r14
0x14002feec  push    r15
0x14002feee  sub     rsp, 70h
0x14002fef2  mov     r12d, [rsp+0A8h+arg_30]
0x14002fefa  mov     rbx, r8
0x14002fefd  mov     r13, rdx
0x14002ff00  mov     dword ptr [rax+50h], 0
0x14002ff07  mov     edx, r12d
0x14002ff0a  mov     qword ptr [rax+10h], 0
0x14002ff12  mov     ecx, 100h
0x14002ff17  mov     r8d, 6E654357h
0x14002ff1d  mov     r14d, r9d
0x14002ff20  call    cs:__imp_ExAllocatePool2
0x14002ff27  nop     dword ptr [rax+rax+00h]
0x14002ff2c  mov     rsi, rax
0x14002ff2f  test    rax, rax
0x14002ff32  jnz     short loc_14002FF3E
0x14002ff34  mov     ebx, 0C000009Ah
0x14002ff39  jmp     loc_14003008E
0x14002ff3e  movzx   r15d, [rsp+0A8h+arg_38]
0x14002ff47  xor     edi, edi
0x14002ff49  or      r15d, 10h
0x14002ff4d  mov     bpl, 1
0x14002ff50  test    rdi, rdi
0x14002ff53  jz      short loc_14002FF68
0x14002ff55  mov     rax, [rdi+18h]
0x14002ff59  mov     rbx, [rax+10h]
0x14002ff5d  mov     r13, [rax]
0x14002ff60  mov     [rsp+0A8h+arg_10], rbx
0x14002ff68  lea     rax, [rsp+0A8h+arg_48]
0x14002ff70  mov     r9d, r12d
0x14002ff73  mov     [rsp+0A8h+var_70], rax
0x14002ff78  mov     r8, rsi
0x14002ff7b  mov     rax, [rsp+0A8h+arg_28]
0x14002ff83  mov     rdx, rbx
0x14002ff86  mov     [rsp+0A8h+var_78], rax
0x14002ff8b  mov     rcx, r13
0x14002ff8e  mov     [rsp+0A8h+var_80], r15d
0x14002ff93  mov     [rsp+0A8h+var_88], r14d
0x14002ff98  call    cs:__imp_FltQueryDirectoryFileEx
0x14002ff9f  nop     dword ptr [rax+rax+00h]
0x14002ffa4  mov     ebx, eax
0x14002ffa6  test    eax, eax
0x14002ffa8  jns     short loc_14002FFEE
0x14002ffaa  cmp     eax, 0C000000Fh
0x14002ffaf  jz      short loc_14002FFBC
0x14002ffb1  cmp     eax, 80000006h
0x14002ffb6  jnz     loc_14003007A
0x14002ffbc  mov     rax, [rsp+0A8h+arg_0]
0x14002ffc4  add     rax, 38h ; '8'
0x14002ffc8  test    rdi, rdi
0x14002ffcb  jz      short loc_14002FFD2
0x14002ffcd  mov     rdi, [rdi]
0x14002ffd0  jmp     short loc_14002FFD5
0x14002ffd2  mov     rdi, [rax]
0x14002ffd5  cmp     rdi, rax
0x14002ffd8  jz      loc_14003007A
0x14002ffde  mov     rbx, [rsp+0A8h+arg_10]
0x14002ffe6  xor     bpl, bpl
0x14002ffe9  jmp     loc_14002FF50
0x14002ffee  mov     r9, rsi
0x14002fff1  mov     edx, 0A000001Fh
0x14002fff6  mov     ecx, r14d
0x14002fff9  call    WcShouldSkipReparsePointInDirectoryEntry
0x14002fffe  test    al, al
0x140030000  jz      short loc_140030009
0x140030002  mov     ebx, 0C000000Fh
0x140030007  jmp     short loc_14003007A
0x140030009  mov     rax, [rsp+0A8h+arg_68]
0x140030011  mov     r9b, bpl
0x140030014  mov     edx, [rsp+0A8h+arg_20]
0x14003001b  mov     r8b, 1
0x14003001e  mov     [rsp+0A8h+var_48], rax
0x140030023  mov     ecx, r14d
0x140030026  lea     rax, [rsp+0A8h+arg_8]
0x14003002e  mov     [rsp+0A8h+var_50], rax
0x140030033  mov     al, [rsp+0A8h+arg_60]
0x14003003a  mov     [rsp+0A8h+var_58], al
0x14003003e  mov     rax, [rsp+0A8h+arg_58]
0x140030046  mov     [rsp+0A8h+var_60], rax
0x14003004b  mov     eax, [rsp+0A8h+arg_50]
0x140030052  mov     [rsp+0A8h+var_68], eax
0x140030056  mov     eax, [rsp+0A8h+arg_40]
0x14003005d  mov     [rsp+0A8h+var_70], rsi
0x140030062  mov     dword ptr [rsp+0A8h+var_78], r12d
0x140030067  mov     [rsp+0A8h+var_80], 0FFF0000h
0x14003006f  mov     [rsp+0A8h+var_88], eax
0x140030073  call    WcMungeDirectoryEntry
0x140030078  mov     ebx, eax
0x14003007a  mov     edx, 6E654357h; Tag
0x14003007f  mov     rcx, rsi; P
0x140030082  call    cs:__imp_ExFreePoolWithTag
0x140030089  nop     dword ptr [rax+rax+00h]
0x14003008e  mov     eax, ebx
0x140030090  mov     rbx, [rsp+0A8h+arg_18]
0x140030098  add     rsp, 70h
0x14003009c  pop     r15
0x14003009e  pop     r14
0x1400300a0  pop     r13
0x1400300a2  pop     r12
0x1400300a4  pop     rdi
0x1400300a5  pop     rsi
0x1400300a6  pop     rbp
0x1400300a7  retn
```
