# BiGetNtPartitionPath

- ea: `0x140030ee8`
- end: `0x140031014`
- name: `BiGetNtPartitionPath`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x14002f29c`

## callees

- `0x14000da0d`
- `0x140030ee8`
- `0x140031d8c`
- `0x1400320c0`
- `0x1400323e8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140030f4c`
- `ntoskrnl!ExAllocatePool2` at `0x140030f4c`

## pseudocode

```c
__int64 __fastcall BiGetNtPartitionPath(int a1, PWSTR *a2)
{
  int v3; // ebx
  void *Pool2; // rax
  __int64 v5; // rcx
  char v6; // al
  PWSTR v8; // rax
  __int128 v9; // [rsp+30h] [rbp-30h] BYREF
  __int128 v10; // [rsp+40h] [rbp-20h] BYREF
  __int128 v11; // [rsp+50h] [rbp-10h] BYREF
  PWSTR v12; // [rsp+80h] [rbp+20h] BYREF

  v12 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v3 = BiVerifyBootPartition(
         a1,
         (unsigned int)&v11,
         (unsigned int)&v11 + 8,
         (unsigned int)&v10 + 8,
         (__int64)&v9 + 8,
         0);
  if ( v3 >= 0 )
  {
    Pool2 = (void *)ExAllocatePool2(258, 106, 1262764866);
    *(_QWORD *)&v10 = Pool2;
    if ( !Pool2 )
    {
      v3 = -1073741801;
      goto LABEL_13;
    }
    if ( *((_QWORD *)&v9 + 1) && !(_QWORD)v11 )
    {
      v6 = BYTE1(v9);
      v5 = 1;
      if ( !*((_QWORD *)&v11 + 1) )
        v6 = 1;
      BYTE1(v9) = v6;
    }
    v3 = SyspartEnumerateDisks(v5, (__int64)&v9);
    if ( v3 >= 0 )
    {
      if ( (_BYTE)v9 )
      {
        if ( BiTranslateSymbolicLink((PCWSTR)v10, &v12) < 0 )
        {
          v8 = (PWSTR)v10;
        }
        else
        {
          ExFreePoolWithTag_0((PVOID)v10, 0x4B444342u);
          v8 = v12;
          *(_QWORD *)&v10 = v12;
        }
        *a2 = v8;
        v3 = 0;
        goto LABEL_15;
      }
      v3 = -1073741811;
    }
  }
  Pool2 = (void *)v10;
LABEL_13:
  if ( Pool2 )
    ExFreePoolWithTag_0(Pool2, 0x4B444342u);
LABEL_15:
  if ( *((_QWORD *)&v9 + 1) )
    ExFreePoolWithTag_0(*((PVOID *)&v9 + 1), 0x4B444342u);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140030ee8  mov     r11, rsp
0x140030eeb  mov     [r11+8], rbx
0x140030eef  mov     [r11+10h], rdi
0x140030ef3  push    rbp
0x140030ef4  mov     rbp, rsp
0x140030ef7  sub     rsp, 60h
0x140030efb  xorps   xmm0, xmm0
0x140030efe  mov     qword ptr [r11-40h], 0
0x140030f06  mov     rdi, rdx
0x140030f09  mov     [rbp+arg_10], 0
0x140030f11  lea     rax, [rbp+P]
0x140030f15  lea     rdx, [rbp+var_10]
0x140030f19  mov     [r11-48h], rax
0x140030f1d  lea     r9, [rbp+var_18]
0x140030f21  lea     r8, [rbp+var_10+8]
0x140030f25  movups  xmmword ptr [rbp-30h], xmm0
0x140030f29  movups  xmmword ptr [rbp-20h], xmm0
0x140030f2d  movups  [rbp+var_10], xmm0
0x140030f31  call    BiVerifyBootPartition
0x140030f36  mov     ebx, eax
0x140030f38  test    eax, eax
0x140030f3a  js      short loc_140030FA4
0x140030f3c  mov     edx, 6Ah ; 'j'
0x140030f41  mov     ecx, 102h
0x140030f46  mov     r8d, 4B444342h
0x140030f4c  call    cs:__imp_ExAllocatePool2
0x140030f53  nop     dword ptr [rax+rax+00h]
0x140030f58  mov     [rbp+var_20], rax
0x140030f5c  test    rax, rax
0x140030f5f  jnz     short loc_140030F68
0x140030f61  mov     ebx, 0C0000017h
0x140030f66  jmp     short loc_140030FA8
0x140030f68  cmp     [rbp+P], 0
0x140030f6d  jz      short loc_140030F8A
0x140030f6f  cmp     qword ptr [rbp+var_10], 0
0x140030f74  jnz     short loc_140030F8A
0x140030f76  movzx   eax, [rbp+var_2F]
0x140030f7a  mov     ecx, 1
0x140030f7f  cmp     qword ptr [rbp+var_10+8], 0
0x140030f84  cmovz   eax, ecx
0x140030f87  mov     [rbp+var_2F], al
0x140030f8a  lea     rdx, [rbp+var_30]
0x140030f8e  call    SyspartEnumerateDisks
0x140030f93  mov     ebx, eax
0x140030f95  test    eax, eax
0x140030f97  js      short loc_140030FA4
0x140030f99  cmp     [rbp+var_30], 0
0x140030f9d  jnz     short loc_140030FE0
0x140030f9f  mov     ebx, 0C000000Dh
0x140030fa4  mov     rax, [rbp+var_20]
0x140030fa8  test    rax, rax
0x140030fab  jz      short loc_140030FBA
0x140030fad  mov     edx, 4B444342h; Tag
0x140030fb2  mov     rcx, rax; P
0x140030fb5  call    ExFreePoolWithTag_0
0x140030fba  mov     rcx, [rbp+P]; P
0x140030fbe  test    rcx, rcx
0x140030fc1  jz      short loc_140030FCD
0x140030fc3  mov     edx, 4B444342h; Tag
0x140030fc8  call    ExFreePoolWithTag_0
0x140030fcd  mov     rdi, [rsp+60h+arg_8]
0x140030fd2  mov     eax, ebx
0x140030fd4  mov     rbx, [rsp+60h+arg_0]
0x140030fd9  add     rsp, 60h
0x140030fdd  pop     rbp
0x140030fde  retn
0x140030fe0  mov     rcx, [rbp+var_20]; SourceString
0x140030fe4  lea     rdx, [rbp+arg_10]
0x140030fe8  call    BiTranslateSymbolicLink
0x140030fed  test    eax, eax
0x140030fef  js      short loc_140031009
0x140030ff1  mov     rcx, [rbp+var_20]; P
0x140030ff5  mov     edx, 4B444342h; Tag
0x140030ffa  call    ExFreePoolWithTag_0
0x140030fff  mov     rax, [rbp+arg_10]
0x140031003  mov     [rbp+var_20], rax
0x140031007  jmp     short loc_14003100D
0x140031009  mov     rax, [rbp+var_20]
0x14003100d  mov     [rdi], rax
0x140031010  xor     ebx, ebx
0x140031012  jmp     short loc_140030FBA
```
