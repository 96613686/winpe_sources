# SkpWriteThreadList

- ea: `0x1400bef5c`
- end: `0x1400bf185`
- name: `SkpWriteThreadList`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400be4f8`

## callees

- `0x140034154`
- `0x140099520`
- `0x1400b2b80`
- `0x1400be064`
- `0x1400be778`
- `0x1400becc8`
- `0x1400bef5c`
- `0x1400f3620`
- `0x1400f38f0`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkpWriteThreadList(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rcx
  ULONG_PTR NextProcessThread; // rdi
  int v9; // eax
  int v10; // ecx
  int v11; // eax
  unsigned int v12; // esi
  __int64 v13; // rdx
  int Src; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v17; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v18; // [rsp+58h] [rbp-A8h]
  __int128 v19; // [rsp+68h] [rbp-98h]
  _BYTE v20[48]; // [rsp+80h] [rbp-80h] BYREF
  int v21; // [rsp+B0h] [rbp-50h]

  memset_0(v20, 0, 0x4D0u);
  v6 = *(unsigned int *)(a2 + 44);
  v16 = 0;
  v15 = 0;
  if ( *(_QWORD *)(a2 + 160) < (unsigned __int64)(v6 + 4) )
    return 3221225485LL;
  Src = *(_DWORD *)(a3 + 188);
  v17 = 0;
  v18 = 0;
  v19 = 0;
  RtlCopyVolatileMemory((void *)(a1 + v6), &Src, 4u);
  *(_DWORD *)(a2 + 52) += 4;
  NextProcessThread = SkeGetNextProcessThread(a3, 0);
  if ( NextProcessThread )
  {
    do
    {
      if ( (PVOID)NextProcessThread == KeGetPcr()->NtTib.StackBase )
      {
        if ( *(_DWORD *)(a2 + 220) )
        {
          HIDWORD(v19) = *(_DWORD *)(a2 + 220);
          DWORD2(v19) = 1232;
        }
      }
      else
      {
        v21 = 1048587;
        DWORD2(v19) = 1232;
        if ( (int)SkpsGetSetContext(NextProcessThread) >= 0 )
        {
          v9 = SkpWriteOther(a1, a2, v20);
          v10 = HIDWORD(v19);
          if ( v9 >= 0 )
            v10 = 0;
          HIDWORD(v19) = v10;
        }
      }
      *(_QWORD *)&v18 = *(_QWORD *)(NextProcessThread + 160);
      LODWORD(v17) = *(_DWORD *)(NextProcessThread + 208);
      *(_QWORD *)((char *)&v17 + 4) = 0;
      HIDWORD(v17) = 0;
      if ( (int)SkpGetThreadUserStack(NextProcessThread, &v16, &v15) >= 0 )
      {
        v11 = *(_DWORD *)(a2 + 124);
        LODWORD(v19) = v16 - v15;
        *((_QWORD *)&v18 + 1) = v15;
        DWORD1(v19) = v11;
        SkpWriteMemoryDesc(a1, a2);
      }
      v12 = *(_DWORD *)(a2 + 56);
      v13 = *(unsigned int *)(a2 + 52);
      if ( v12 + (unsigned int)v13 > *(_DWORD *)(a2 + 44) + *(_DWORD *)(a2 + 48) )
        break;
      if ( *(_QWORD *)(a2 + 160) < (unsigned __int64)(v12 + (unsigned int)v13) )
        break;
      RtlCopyVolatileMemory((void *)(a1 + v13), &v17, v12);
      *(_DWORD *)(a2 + 52) += v12;
      NextProcessThread = SkeGetNextProcessThread(a3, NextProcessThread);
    }
    while ( NextProcessThread );
    if ( NextProcessThread )
      SkReleaseRundownProtection(NextProcessThread + 216, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1400bef5c  mov     [rsp-8+arg_18], rbx
0x1400bef61  push    rbp
0x1400bef62  push    rsi
0x1400bef63  push    rdi
0x1400bef64  push    r14
0x1400bef66  push    r15
0x1400bef68  lea     rbp, [rsp-460h]
0x1400bef70  sub     rsp, 560h
0x1400bef77  mov     rax, cs:__security_cookie
0x1400bef7e  xor     rax, rsp
0x1400bef81  mov     [rbp+480h+var_30], rax
0x1400bef88  mov     r15, r8
0x1400bef8b  mov     rbx, rdx
0x1400bef8e  mov     r14, rcx
0x1400bef91  xor     edx, edx; Val
0x1400bef93  mov     r8d, 4D0h; Size
0x1400bef99  lea     rcx, [rbp+480h+var_500]; void *
0x1400bef9d  call    memset_0
0x1400befa2  mov     ecx, [rbx+2Ch]
0x1400befa5  mov     [rsp+580h+var_540], 0
0x1400befae  mov     [rsp+580h+var_548], 0
0x1400befb7  lea     rax, [rcx+4]
0x1400befbb  cmp     [rbx+0A0h], rax
0x1400befc2  jnb     short loc_1400BEFCE
0x1400befc4  mov     eax, 0C000000Dh
0x1400befc9  jmp     loc_1400BF15E
0x1400befce  mov     eax, [r15+0BCh]
0x1400befd5  lea     rdx, [rsp+580h+Src]; Src
0x1400befda  xorps   xmm0, xmm0
0x1400befdd  mov     [rsp+580h+var_550], 0
0x1400befe5  add     rcx, r14; void *
0x1400befe8  mov     [rsp+580h+Src], eax
0x1400befec  mov     r8d, 4; Size
0x1400beff2  movups  [rsp+580h+var_538], xmm0
0x1400beff7  movups  [rsp+580h+var_528], xmm0
0x1400beffc  movups  [rsp+580h+var_518], xmm0
0x1400bf001  call    RtlCopyVolatileMemory
0x1400bf006  add     dword ptr [rbx+34h], 4
0x1400bf00a  xor     edx, edx
0x1400bf00c  mov     rcx, r15
0x1400bf00f  call    SkeGetNextProcessThread
0x1400bf014  mov     rdi, rax
0x1400bf017  test    rax, rax
0x1400bf01a  jz      loc_1400BF15C
0x1400bf020  mov     rcx, gs:8
0x1400bf029  cmp     rdi, rcx
0x1400bf02c  jnz     short loc_1400BF046
0x1400bf02e  mov     eax, [rbx+0DCh]
0x1400bf034  test    eax, eax
0x1400bf036  jz      short loc_1400BF092
0x1400bf038  mov     dword ptr [rsp+580h+var_518+0Ch], eax
0x1400bf03c  mov     dword ptr [rsp+580h+var_518+8], 4D0h
0x1400bf044  jmp     short loc_1400BF092
0x1400bf046  lea     r8, [rbp+480h+var_500]
0x1400bf04a  mov     [rbp+480h+var_4D0], 10000Bh
0x1400bf051  mov     edx, 0Eh
0x1400bf056  mov     dword ptr [rsp+580h+var_518+8], 4D0h
0x1400bf05e  mov     rcx, rdi; BugCheckParameter3
0x1400bf061  call    SkpsGetSetContext
0x1400bf066  test    eax, eax
0x1400bf068  js      short loc_1400BF092
0x1400bf06a  lea     rax, [rsp+580h+var_550]
0x1400bf06f  mov     rdx, rbx
0x1400bf072  lea     r8, [rbp+480h+var_500]
0x1400bf076  mov     [rsp+580h+var_558], rax
0x1400bf07b  mov     rcx, r14
0x1400bf07e  call    SkpWriteOther
0x1400bf083  mov     ecx, dword ptr [rsp+580h+var_518+0Ch]
0x1400bf087  test    eax, eax
0x1400bf089  cmovns  ecx, [rsp+580h+var_550]
0x1400bf08e  mov     dword ptr [rsp+580h+var_518+0Ch], ecx
0x1400bf092  mov     rax, [rdi+0A0h]
0x1400bf099  lea     r8, [rsp+580h+var_548]
0x1400bf09e  mov     qword ptr [rsp+580h+var_528], rax
0x1400bf0a3  lea     rdx, [rsp+580h+var_540]
0x1400bf0a8  mov     eax, [rdi+0D0h]
0x1400bf0ae  mov     rcx, rdi
0x1400bf0b1  mov     dword ptr [rsp+580h+var_538], eax
0x1400bf0b5  mov     qword ptr [rsp+580h+var_538+4], 0
0x1400bf0be  mov     dword ptr [rsp+580h+var_538+0Ch], 0
0x1400bf0c6  call    SkpGetThreadUserStack
0x1400bf0cb  test    eax, eax
0x1400bf0cd  js      short loc_1400BF100
0x1400bf0cf  mov     r8, [rsp+580h+var_548]
0x1400bf0d4  mov     rdx, rbx
0x1400bf0d7  mov     eax, dword ptr [rsp+580h+var_548+4]
0x1400bf0db  mov     rcx, r14
0x1400bf0de  mov     r9d, dword ptr [rsp+580h+var_540]
0x1400bf0e3  sub     r9d, r8d
0x1400bf0e6  mov     dword ptr [rsp+580h+var_528+0Ch], eax
0x1400bf0ea  mov     eax, [rbx+7Ch]
0x1400bf0ed  mov     dword ptr [rsp+580h+var_518], r9d
0x1400bf0f2  mov     dword ptr [rsp+580h+var_528+8], r8d
0x1400bf0f7  mov     dword ptr [rsp+580h+var_518+4], eax
0x1400bf0fb  call    SkpWriteMemoryDesc
0x1400bf100  mov     esi, [rbx+38h]
0x1400bf103  mov     edx, [rbx+34h]
0x1400bf106  mov     eax, [rbx+30h]
0x1400bf109  add     eax, [rbx+2Ch]
0x1400bf10c  lea     ecx, [rsi+rdx]
0x1400bf10f  cmp     ecx, eax
0x1400bf111  ja      short loc_1400BF149
0x1400bf113  mov     eax, ecx
0x1400bf115  cmp     [rbx+0A0h], rax
0x1400bf11c  jb      short loc_1400BF149
0x1400bf11e  lea     rcx, [r14+rdx]; void *
0x1400bf122  mov     r8d, esi; Size
0x1400bf125  lea     rdx, [rsp+580h+var_538]; Src
0x1400bf12a  call    RtlCopyVolatileMemory
0x1400bf12f  add     [rbx+34h], esi
0x1400bf132  mov     rdx, rdi
0x1400bf135  mov     rcx, r15
0x1400bf138  call    SkeGetNextProcessThread
0x1400bf13d  mov     rdi, rax
0x1400bf140  test    rax, rax
0x1400bf143  jnz     loc_1400BF020
0x1400bf149  test    rdi, rdi
0x1400bf14c  jz      short loc_1400BF15C
0x1400bf14e  lea     rcx, [rdi+0D8h]
0x1400bf155  xor     edx, edx
0x1400bf157  call    SkReleaseRundownProtection
0x1400bf15c  xor     eax, eax
0x1400bf15e  mov     rcx, [rbp+480h+var_30]
0x1400bf165  xor     rcx, rsp; StackCookie
0x1400bf168  call    __security_check_cookie
0x1400bf16d  mov     rbx, [rsp+580h+arg_18]
0x1400bf175  add     rsp, 560h
0x1400bf17c  pop     r15
0x1400bf17e  pop     r14
0x1400bf180  pop     rdi
0x1400bf181  pop     rsi
0x1400bf182  pop     rbp
0x1400bf183  retn
```
