# BiGetNtPartitionPath

- ea: `0x140030f38`
- end: `0x140031064`
- name: `BiGetNtPartitionPath`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x14002f2ec`

## callees

- `0x14000da0d`
- `0x140030f38`
- `0x140031ddc`
- `0x140032110`
- `0x140032438`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140030f9c`
- `ntoskrnl!ExAllocatePool2` at `0x140030f9c`

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
0x140030f38  mov     r11, rsp
0x140030f3b  mov     [r11+8], rbx
0x140030f3f  mov     [r11+10h], rdi
0x140030f43  push    rbp
0x140030f44  mov     rbp, rsp
0x140030f47  sub     rsp, 60h
0x140030f4b  xorps   xmm0, xmm0
0x140030f4e  mov     qword ptr [r11-40h], 0
0x140030f56  mov     rdi, rdx
0x140030f59  mov     [rbp+arg_10], 0
0x140030f61  lea     rax, [rbp+P]
0x140030f65  lea     rdx, [rbp+var_10]
0x140030f69  mov     [r11-48h], rax
0x140030f6d  lea     r9, [rbp+var_18]
0x140030f71  lea     r8, [rbp+var_10+8]
0x140030f75  movups  xmmword ptr [rbp-30h], xmm0
0x140030f79  movups  xmmword ptr [rbp-20h], xmm0
0x140030f7d  movups  [rbp+var_10], xmm0
0x140030f81  call    BiVerifyBootPartition
0x140030f86  mov     ebx, eax
0x140030f88  test    eax, eax
0x140030f8a  js      short loc_140030FF4
0x140030f8c  mov     edx, 6Ah ; 'j'
0x140030f91  mov     ecx, 102h
0x140030f96  mov     r8d, 4B444342h
0x140030f9c  call    cs:__imp_ExAllocatePool2
0x140030fa3  nop     dword ptr [rax+rax+00h]
0x140030fa8  mov     [rbp+var_20], rax
0x140030fac  test    rax, rax
0x140030faf  jnz     short loc_140030FB8
0x140030fb1  mov     ebx, 0C0000017h
0x140030fb6  jmp     short loc_140030FF8
0x140030fb8  cmp     [rbp+P], 0
0x140030fbd  jz      short loc_140030FDA
0x140030fbf  cmp     qword ptr [rbp+var_10], 0
0x140030fc4  jnz     short loc_140030FDA
0x140030fc6  movzx   eax, [rbp+var_2F]
0x140030fca  mov     ecx, 1
0x140030fcf  cmp     qword ptr [rbp+var_10+8], 0
0x140030fd4  cmovz   eax, ecx
0x140030fd7  mov     [rbp+var_2F], al
0x140030fda  lea     rdx, [rbp+var_30]
0x140030fde  call    SyspartEnumerateDisks
0x140030fe3  mov     ebx, eax
0x140030fe5  test    eax, eax
0x140030fe7  js      short loc_140030FF4
0x140030fe9  cmp     [rbp+var_30], 0
0x140030fed  jnz     short loc_140031030
0x140030fef  mov     ebx, 0C000000Dh
0x140030ff4  mov     rax, [rbp+var_20]
0x140030ff8  test    rax, rax
0x140030ffb  jz      short loc_14003100A
0x140030ffd  mov     edx, 4B444342h; Tag
0x140031002  mov     rcx, rax; P
0x140031005  call    ExFreePoolWithTag_0
0x14003100a  mov     rcx, [rbp+P]; P
0x14003100e  test    rcx, rcx
0x140031011  jz      short loc_14003101D
0x140031013  mov     edx, 4B444342h; Tag
0x140031018  call    ExFreePoolWithTag_0
0x14003101d  mov     rdi, [rsp+60h+arg_8]
0x140031022  mov     eax, ebx
0x140031024  mov     rbx, [rsp+60h+arg_0]
0x140031029  add     rsp, 60h
0x14003102d  pop     rbp
0x14003102e  retn
0x140031030  mov     rcx, [rbp+var_20]; SourceString
0x140031034  lea     rdx, [rbp+arg_10]
0x140031038  call    BiTranslateSymbolicLink
0x14003103d  test    eax, eax
0x14003103f  js      short loc_140031059
0x140031041  mov     rcx, [rbp+var_20]; P
0x140031045  mov     edx, 4B444342h; Tag
0x14003104a  call    ExFreePoolWithTag_0
0x14003104f  mov     rax, [rbp+arg_10]
0x140031053  mov     [rbp+var_20], rax
0x140031057  jmp     short loc_14003105D
0x140031059  mov     rax, [rbp+var_20]
0x14003105d  mov     [rdi], rax
0x140031060  xor     ebx, ebx
0x140031062  jmp     short loc_14003100A
```
