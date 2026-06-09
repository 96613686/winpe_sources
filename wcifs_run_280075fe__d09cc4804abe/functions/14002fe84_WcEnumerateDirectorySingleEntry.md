# WcEnumerateDirectorySingleEntry

- ea: `0x14002fe84`
- end: `0x140030059`
- name: `WcEnumerateDirectorySingleEntry`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140014c90`

## callees

- `0x14001414c`
- `0x140029010`
- `0x14002fe84`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140030032`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030032`
- `ntoskrnl!ExAllocatePool2` at `0x14002fed0`
- `ntoskrnl!ExAllocatePool2` at `0x14002fed0`
- `FLTMGR!FltQueryDirectoryFileEx` at `0x14002ff48`
- `FLTMGR!FltQueryDirectoryFileEx` at `0x14002ff48`

## pseudocode

```c
__int64 __fastcall WcEnumerateDirectorySingleEntry(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        unsigned int a7,
        unsigned __int8 a8,
        int a9,
        int a10,
        int a11,
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
  int v27; // r8d
  int v28; // r9d
  __int64 v31; // [rsp+B8h] [rbp+10h] BYREF
  __int64 v32; // [rsp+C0h] [rbp+18h]

  v32 = a3;
  v14 = a7;
  v15 = a3;
  a10 = 0;
  v31 = 0;
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
        v32 = v15;
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
      v15 = v32;
    }
    if ( (unsigned __int8)WcShouldSkipReparsePointInDirectoryEntry(a4, 2684354591LL, v25, Pool2) )
    {
      v19 = -1073741809;
    }
    else
    {
      LOBYTE(v28) = i;
      LOBYTE(v27) = 1;
      v19 = WcMungeDirectoryEntry(
              a4,
              a5,
              v27,
              v28,
              a9,
              268369920,
              v14,
              (__int64)Pool2,
              a11,
              a12,
              a13,
              (__int64)&v31,
              a14);
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
0x14002fe84  mov     rax, rsp
0x14002fe87  mov     [rax+20h], rbx
0x14002fe8b  mov     [rax+18h], r8
0x14002fe8f  mov     [rax+8], rcx
0x14002fe93  push    rbp
0x14002fe94  push    rsi
0x14002fe95  push    rdi
0x14002fe96  push    r12
0x14002fe98  push    r13
0x14002fe9a  push    r14
0x14002fe9c  push    r15
0x14002fe9e  sub     rsp, 70h
0x14002fea2  mov     r12d, [rsp+0A8h+arg_30]
0x14002feaa  mov     rbx, r8
0x14002fead  mov     r13, rdx
0x14002feb0  mov     dword ptr [rax+50h], 0
0x14002feb7  mov     edx, r12d
0x14002feba  mov     qword ptr [rax+10h], 0
0x14002fec2  mov     ecx, 100h
0x14002fec7  mov     r8d, 6E654357h
0x14002fecd  mov     r14d, r9d
0x14002fed0  call    cs:__imp_ExAllocatePool2
0x14002fed7  nop     dword ptr [rax+rax+00h]
0x14002fedc  mov     rsi, rax
0x14002fedf  test    rax, rax
0x14002fee2  jnz     short loc_14002FEEE
0x14002fee4  mov     ebx, 0C000009Ah
0x14002fee9  jmp     loc_14003003E
0x14002feee  movzx   r15d, [rsp+0A8h+arg_38]
0x14002fef7  xor     edi, edi
0x14002fef9  or      r15d, 10h
0x14002fefd  mov     bpl, 1
0x14002ff00  test    rdi, rdi
0x14002ff03  jz      short loc_14002FF18
0x14002ff05  mov     rax, [rdi+18h]
0x14002ff09  mov     rbx, [rax+10h]
0x14002ff0d  mov     r13, [rax]
0x14002ff10  mov     [rsp+0A8h+arg_10], rbx
0x14002ff18  lea     rax, [rsp+0A8h+arg_48]
0x14002ff20  mov     r9d, r12d
0x14002ff23  mov     [rsp+0A8h+var_70], rax
0x14002ff28  mov     r8, rsi
0x14002ff2b  mov     rax, [rsp+0A8h+arg_28]
0x14002ff33  mov     rdx, rbx
0x14002ff36  mov     [rsp+0A8h+var_78], rax
0x14002ff3b  mov     rcx, r13
0x14002ff3e  mov     [rsp+0A8h+var_80], r15d
0x14002ff43  mov     [rsp+0A8h+var_88], r14d
0x14002ff48  call    cs:__imp_FltQueryDirectoryFileEx
0x14002ff4f  nop     dword ptr [rax+rax+00h]
0x14002ff54  mov     ebx, eax
0x14002ff56  test    eax, eax
0x14002ff58  jns     short loc_14002FF9E
0x14002ff5a  cmp     eax, 0C000000Fh
0x14002ff5f  jz      short loc_14002FF6C
0x14002ff61  cmp     eax, 80000006h
0x14002ff66  jnz     loc_14003002A
0x14002ff6c  mov     rax, [rsp+0A8h+arg_0]
0x14002ff74  add     rax, 38h ; '8'
0x14002ff78  test    rdi, rdi
0x14002ff7b  jz      short loc_14002FF82
0x14002ff7d  mov     rdi, [rdi]
0x14002ff80  jmp     short loc_14002FF85
0x14002ff82  mov     rdi, [rax]
0x14002ff85  cmp     rdi, rax
0x14002ff88  jz      loc_14003002A
0x14002ff8e  mov     rbx, [rsp+0A8h+arg_10]
0x14002ff96  xor     bpl, bpl
0x14002ff99  jmp     loc_14002FF00
0x14002ff9e  mov     r9, rsi
0x14002ffa1  mov     edx, 0A000001Fh
0x14002ffa6  mov     ecx, r14d
0x14002ffa9  call    WcShouldSkipReparsePointInDirectoryEntry
0x14002ffae  test    al, al
0x14002ffb0  jz      short loc_14002FFB9
0x14002ffb2  mov     ebx, 0C000000Fh
0x14002ffb7  jmp     short loc_14003002A
0x14002ffb9  mov     rax, [rsp+0A8h+arg_68]
0x14002ffc1  mov     r9b, bpl
0x14002ffc4  mov     edx, [rsp+0A8h+arg_20]
0x14002ffcb  mov     r8b, 1
0x14002ffce  mov     [rsp+0A8h+var_48], rax
0x14002ffd3  mov     ecx, r14d
0x14002ffd6  lea     rax, [rsp+0A8h+arg_8]
0x14002ffde  mov     [rsp+0A8h+var_50], rax
0x14002ffe3  mov     al, [rsp+0A8h+arg_60]
0x14002ffea  mov     [rsp+0A8h+var_58], al
0x14002ffee  mov     rax, [rsp+0A8h+arg_58]
0x14002fff6  mov     [rsp+0A8h+var_60], rax
0x14002fffb  mov     eax, [rsp+0A8h+arg_50]
0x140030002  mov     [rsp+0A8h+var_68], eax
0x140030006  mov     eax, [rsp+0A8h+arg_40]
0x14003000d  mov     [rsp+0A8h+var_70], rsi
0x140030012  mov     dword ptr [rsp+0A8h+var_78], r12d
0x140030017  mov     [rsp+0A8h+var_80], 0FFF0000h
0x14003001f  mov     [rsp+0A8h+var_88], eax
0x140030023  call    WcMungeDirectoryEntry
0x140030028  mov     ebx, eax
0x14003002a  mov     edx, 6E654357h; Tag
0x14003002f  mov     rcx, rsi; P
0x140030032  call    cs:__imp_ExFreePoolWithTag
0x140030039  nop     dword ptr [rax+rax+00h]
0x14003003e  mov     eax, ebx
0x140030040  mov     rbx, [rsp+0A8h+arg_18]
0x140030048  add     rsp, 70h
0x14003004c  pop     r15
0x14003004e  pop     r14
0x140030050  pop     r13
0x140030052  pop     r12
0x140030054  pop     rdi
0x140030055  pop     rsi
0x140030056  pop     rbp
0x140030057  retn
```
