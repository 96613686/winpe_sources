# RtlCreateUserStack

- ea: `0x1400fee4c`
- end: `0x1400ff121`
- name: `RtlCreateUserStack`
- size: `725`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG_PTR, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1400af528`

## callees

- `0x1400d724c`
- `0x1400ef620`
- `0x1400ef660`
- `0x1400ef680`
- `0x1400fc664`
- `0x1400fc6a0`
- `0x1400fc6dc`
- `0x1400fee4c`

## pseudocode

```c
__int64 __fastcall RtlCreateUserStack(
        unsigned __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        ULONG_PTR a5,
        PVOID *a6)
{
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rbx
  _QWORD *StackBase; // rax
  __int64 v9; // r15
  _QWORD *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rsi
  volatile void *v14; // r14
  __int64 ULong64FromUser; // rsi
  __int64 ULongFromUser; // rax
  ULONG_PTR v17; // rsi
  unsigned __int64 v18; // rbx
  void *v19; // rax
  __int64 result; // rax
  PVOID *v21; // rdi
  char *v22; // rcx
  NTSTATUS v23; // r14d
  char *v24; // rax
  ULONG_PTR v25; // [rsp+30h] [rbp-68h] BYREF
  PVOID v26[2]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v27; // [rsp+48h] [rbp-50h] BYREF
  __int128 v28; // [rsp+58h] [rbp-40h]
  char *v29; // [rsp+68h] [rbp-30h]
  ULONG_PTR RegionSize; // [rsp+B0h] [rbp+18h] BYREF
  PVOID BaseAddress; // [rsp+B8h] [rbp+20h] BYREF

  v6 = a2;
  v7 = a1;
  a5 = 0;
  BaseAddress = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  RegionSize = 0;
  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
    StackBase = (_QWORD *)StackBase[10];
  v9 = StackBase[20];
  if ( !a1 || !a2 )
  {
    v10 = KeGetPcr()->NtTib.StackBase;
    if ( v10 )
      v11 = v10[10];
    else
      v11 = 0;
    v12 = RtlImageNtHeader(*(_QWORD *)(v11 + 176));
    v13 = v12;
    if ( !v12 )
      return 3221225595LL;
    v14 = (volatile void *)(v12 + 96);
    if ( (unsigned __int16)RtlReadUShortFromUser(v12 + 24) == 523 )
    {
      ULong64FromUser = RtlReadULong64FromUser((volatile void *)(v13 + 104));
      ULongFromUser = RtlReadULong64FromUser(v14);
    }
    else
    {
      ULong64FromUser = (unsigned int)RtlReadULongFromUser((unsigned int *)(v13 + 100));
      ULongFromUser = (unsigned int)RtlReadULongFromUser((unsigned int *)v14);
    }
    if ( !v7 )
      v7 = ULong64FromUser;
    if ( !v6 )
      v6 = ULongFromUser;
  }
  if ( !v7 )
    v7 = 0x4000;
  if ( v7 >= v6 )
    v6 = (v7 + 0xFFFFF) & 0xFFFFFFFFFFF00000uLL;
  v17 = (v7 + 4095) & 0xFFFFFFFFFFFFF000uLL;
  v18 = (v6 + 0xFFFF) & 0xFFFFFFFFFFFF0000uLL;
  v19 = (void *)RtlReadULong64FromUser((volatile void *)(v9 + 792));
  v26[1] = v19;
  if ( v19 && v17 < (unsigned __int64)v19 )
  {
    v17 = ((unsigned __int64)v19 + 4095) & 0xFFFFFFFFFFFFF000uLL;
    if ( v17 >= v18 )
      v18 = (v17 + 0xFFFFF) & 0xFFFFFFFFFFF00000uLL;
    v18 = (v18 + 0xFFFF) & 0xFFFFFFFFFFFF0000uLL;
  }
  v27 = 0u;
  v28 = v18;
  result = ZwSetInformationProcess(-1, 41, &v27);
  if ( (int)result >= 0 )
  {
    v21 = a6;
    *a6 = 0;
    v21[1] = 0;
    v22 = v29;
    v21[4] = v29;
    v21[2] = &v22[v18];
    BaseAddress = &v22[v18 - v17];
    RegionSize = v17;
    v23 = ZwAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &RegionSize, 0x1000u, 4u);
    if ( v23 < 0
      || (v24 = (char *)BaseAddress, v21[3] = BaseAddress, v18 - v17 >= 0x3000)
      && (BaseAddress = v24 - 12288,
          a5 = 12288,
          v23 = ZwAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &a5, 0x1000u, 0x104u),
          v23 < 0) )
    {
      v26[0] = v21[4];
      v25 = 0;
      ZwFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, v26, &v25, 0x8000u);
      return (unsigned int)v23;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400fee4c  mov     r11, rsp
0x1400fee4f  mov     [r11+20h], r9
0x1400fee53  mov     [r11+18h], r8
0x1400fee57  push    rbx
0x1400fee58  push    rsi
0x1400fee59  push    rdi
0x1400fee5a  push    r14
0x1400fee5c  push    r15
0x1400fee5e  sub     rsp, 70h
0x1400fee62  mov     rdi, rdx
0x1400fee65  mov     rbx, rcx
0x1400fee68  mov     qword ptr [r11+28h], 0
0x1400fee70  mov     qword ptr [r11+20h], 0
0x1400fee78  xorps   xmm0, xmm0
0x1400fee7b  xor     eax, eax
0x1400fee7d  movups  [rsp+98h+var_50], xmm0
0x1400fee82  movups  [rsp+98h+var_40], xmm0
0x1400fee87  mov     [r11-30h], rax
0x1400fee8b  mov     [r11+18h], rax
0x1400fee8f  mov     rax, gs:8
0x1400fee98  test    rax, rax
0x1400fee9b  jz      short loc_1400FEEA1
0x1400fee9d  mov     rax, [rax+50h]
0x1400feea1  mov     r15, [rax+0A0h]
0x1400feea8  test    rbx, rbx
0x1400feeab  jz      short loc_1400FEEB6
0x1400feead  test    rdi, rdi
0x1400feeb0  jnz     loc_1400FEF44
0x1400feeb6  mov     rax, gs:8
0x1400feebf  test    rax, rax
0x1400feec2  jz      short loc_1400FEECA
0x1400feec4  mov     rcx, [rax+50h]
0x1400feec8  jmp     short loc_1400FEECC
0x1400feeca  xor     ecx, ecx
0x1400feecc  mov     rcx, [rcx+0B0h]
0x1400feed3  call    RtlImageNtHeader
0x1400feed8  mov     rsi, rax
0x1400feedb  test    rax, rax
0x1400feede  jz      loc_1400FF10D
0x1400feee4  lea     rcx, [rax+18h]
0x1400feee8  call    RtlReadUShortFromUser
0x1400feeed  lea     r14, [rsi+60h]
0x1400feef1  mov     ecx, 20Bh
0x1400feef6  cmp     ax, cx
0x1400feef9  jz      short loc_1400FEF12
0x1400feefb  lea     rcx, [rsi+64h]
0x1400feeff  call    RtlReadULongFromUser
0x1400fef04  mov     esi, eax
0x1400fef06  mov     rcx, r14
0x1400fef09  call    RtlReadULongFromUser
0x1400fef0e  mov     eax, eax
0x1400fef10  jmp     short loc_1400FEF26
0x1400fef12  lea     rcx, [rsi+68h]
0x1400fef16  call    RtlReadULong64FromUser
0x1400fef1b  mov     rsi, rax
0x1400fef1e  mov     rcx, r14
0x1400fef21  call    RtlReadULong64FromUser
0x1400fef26  test    rbx, rbx
0x1400fef29  cmovz   rbx, rsi
0x1400fef2d  mov     [rsp+98h+arg_0], rbx
0x1400fef35  test    rdi, rdi
0x1400fef38  cmovz   rdi, rax
0x1400fef3c  mov     [rsp+98h+arg_8], rdi
0x1400fef44  mov     eax, 4000h
0x1400fef49  test    rbx, rbx
0x1400fef4c  cmovz   rbx, rax
0x1400fef50  cmp     rbx, rdi
0x1400fef53  jb      short loc_1400FEF63
0x1400fef55  lea     rdi, [rbx+0FFFFFh]
0x1400fef5c  and     rdi, 0FFFFFFFFFFF00000h
0x1400fef63  lea     rsi, [rbx+0FFFh]
0x1400fef6a  mov     r14, 0FFFFFFFFFFFFF000h
0x1400fef71  and     rsi, r14
0x1400fef74  lea     rbx, [rdi+0FFFFh]
0x1400fef7b  mov     rdi, 0FFFFFFFFFFFF0000h
0x1400fef82  and     rbx, rdi
0x1400fef85  lea     rcx, [r15+318h]
0x1400fef8c  call    RtlReadULong64FromUser
0x1400fef91  mov     [rsp+98h+var_58], rax
0x1400fef96  test    rax, rax
0x1400fef99  jz      short loc_1400FEFC7
0x1400fef9b  cmp     rsi, rax
0x1400fef9e  jnb     short loc_1400FEFC7
0x1400fefa0  lea     rsi, [rax+0FFFh]
0x1400fefa7  and     rsi, r14
0x1400fefaa  cmp     rsi, rbx
0x1400fefad  jb      short loc_1400FEFBD
0x1400fefaf  lea     rbx, [rsi+0FFFFFh]
0x1400fefb6  and     rbx, 0FFFFFFFFFFF00000h
0x1400fefbd  add     rbx, 0FFFFh
0x1400fefc4  and     rbx, rdi
0x1400fefc7  mov     qword ptr [rsp+98h+var_50], 0
0x1400fefd0  mov     qword ptr [rsp+98h+var_50+8], 0
0x1400fefd9  mov     qword ptr [rsp+98h+var_40], rbx
0x1400fefde  mov     qword ptr [rsp+98h+var_40+8], 0
0x1400fefe7  mov     r9d, 28h ; '('
0x1400fefed  lea     r8, [rsp+98h+var_50]
0x1400feff2  lea     edx, [r9+1]
0x1400feff6  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400feffa  mov     rcx, r15
0x1400feffd  call    ZwSetInformationProcess
0x1400ff002  test    eax, eax
0x1400ff004  js      loc_1400FF114
0x1400ff00a  mov     rdi, [rsp+98h+arg_28]
0x1400ff012  mov     qword ptr [rdi], 0
0x1400ff019  mov     qword ptr [rdi+8], 0
0x1400ff021  mov     rcx, [rsp+98h+var_30]
0x1400ff026  mov     [rdi+20h], rcx
0x1400ff02a  lea     rax, [rcx+rbx]
0x1400ff02e  mov     [rdi+10h], rax
0x1400ff032  sub     rcx, rsi
0x1400ff035  add     rcx, rbx
0x1400ff038  mov     [rsp+98h+BaseAddress], rcx
0x1400ff040  mov     [rsp+98h+RegionSize], rsi
0x1400ff048  mov     [rsp+98h+Protect], 4; Protect
0x1400ff050  mov     [rsp+98h+AllocationType], 1000h; AllocationType
0x1400ff058  lea     r9, [rsp+98h+RegionSize]; RegionSize
0x1400ff060  xor     r8d, r8d; ZeroBits
0x1400ff063  lea     rdx, [rsp+98h+BaseAddress]; BaseAddress
0x1400ff06b  mov     rcx, r15; ProcessHandle
0x1400ff06e  call    ZwAllocateVirtualMemory
0x1400ff073  mov     r14d, eax
0x1400ff076  test    eax, eax
0x1400ff078  js      short loc_1400FF0DC
0x1400ff07a  mov     rax, [rsp+98h+BaseAddress]
0x1400ff082  mov     [rdi+18h], rax
0x1400ff086  sub     rbx, rsi
0x1400ff089  mov     ecx, 3000h
0x1400ff08e  cmp     rbx, rcx
0x1400ff091  jb      short loc_1400FF0D8
0x1400ff093  sub     rax, rcx
0x1400ff096  mov     [rsp+98h+BaseAddress], rax
0x1400ff09e  mov     [rsp+98h+arg_20], rcx
0x1400ff0a6  mov     [rsp+98h+Protect], 104h; Protect
0x1400ff0ae  mov     [rsp+98h+AllocationType], 1000h; AllocationType
0x1400ff0b6  lea     r9, [rsp+98h+arg_20]; RegionSize
0x1400ff0be  xor     r8d, r8d; ZeroBits
0x1400ff0c1  lea     rdx, [rsp+98h+BaseAddress]; BaseAddress
0x1400ff0c9  mov     rcx, r15; ProcessHandle
0x1400ff0cc  call    ZwAllocateVirtualMemory
0x1400ff0d1  mov     r14d, eax
0x1400ff0d4  test    eax, eax
0x1400ff0d6  js      short loc_1400FF0DC
0x1400ff0d8  xor     eax, eax
0x1400ff0da  jmp     short loc_1400FF114
0x1400ff0dc  mov     rax, [rdi+20h]
0x1400ff0e0  mov     [rsp+98h+var_60], rax
0x1400ff0e5  mov     [rsp+98h+var_68], 0
0x1400ff0ee  mov     r9d, 8000h; FreeType
0x1400ff0f4  lea     r8, [rsp+98h+var_68]; RegionSize
0x1400ff0f9  lea     rdx, [rsp+98h+var_60]; BaseAddress
0x1400ff0fe  mov     rcx, r15; ProcessHandle
0x1400ff101  call    ZwFreeVirtualMemory
0x1400ff106  mov     eax, r14d
0x1400ff109  jmp     short loc_1400FF114
0x1400ff10b  jmp     short loc_1400FF114
0x1400ff10d  mov     eax, 0C000007Bh
0x1400ff112  jmp     short $+2
0x1400ff114  add     rsp, 70h
0x1400ff118  pop     r15
0x1400ff11a  pop     r14
0x1400ff11c  pop     rdi
0x1400ff11d  pop     rsi
0x1400ff11e  pop     rbx
0x1400ff11f  retn
```
