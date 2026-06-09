# sub_1800EACB8

- ea: `0x1800eacb8`
- end: `0x1800eaf61`
- name: `sub_1800EACB8`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800eac6c`

## callees

- `0x1800994a0`
- `0x180099ee0`
- `0x18009a540`
- `0x1800eacb8`
- `0x1800eaf68`
- `0x1800eaff8`
- `0x1800eb60c`
- `0x1800eb724`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800eae0b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800eaf36`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800eae0b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800eaf36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800eaced`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800eaced`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ead10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800eadeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800eaf16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ead10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800eadeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800eaf16`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800ead23`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800eadfd`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800eaf28`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800ead23`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800eadfd`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800eaf28`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessAffinityMask` at `0x1800ead04`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessAffinityMask` at `0x1800ead04`

## pseudocode

```c
void sub_1800EACB8()
{
  HANDLE CurrentProcess; // rax
  HANDLE CurrentThread; // rax
  DWORD_PTR v2; // rax
  DWORD_PTR v3; // r15
  DWORD_PTR v4; // rdi
  char v5; // r14
  unsigned int v6; // ebx
  unsigned int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // edx
  unsigned int v11; // ebx
  unsigned int v12; // eax
  __int64 v13; // rcx
  HANDLE v14; // rax
  __int64 v15; // rdx
  char v16; // r8
  unsigned int v17; // ebx
  unsigned int v18; // ecx
  int v19; // r8d
  unsigned int v20; // edx
  __int64 i; // r8
  __int64 v22; // r10
  unsigned int v23; // r9d
  int v24; // edx
  HANDLE v25; // rax
  ULONG_PTR ProcessAffinityMask; // [rsp+20h] [rbp-49h] BYREF
  ULONG_PTR SystemAffinityMask; // [rsp+28h] [rbp-41h] BYREF
  _BYTE v28[16]; // [rsp+30h] [rbp-39h] BYREF
  _OWORD v29[4]; // [rsp+40h] [rbp-29h] BYREF

  ProcessAffinityMask = 0;
  SystemAffinityMask = 0;
  CurrentProcess = GetCurrentProcess();
  GetProcessAffinityMask(CurrentProcess, &ProcessAffinityMask, &SystemAffinityMask);
  CurrentThread = GetCurrentThread();
  v2 = SetThreadAffinityMask(CurrentThread, ProcessAffinityMask);
  dword_180290D08 = 0;
  dword_180290D24 = 0;
  v3 = v2;
  memset(qword_18028DEE0, 0, sizeof(qword_18028DEE0));
  memset(v29, 0, sizeof(v29));
  v4 = 1;
  v5 = 0;
  sub_1800EB60C();
  v6 = ((__int64 (*)(void))sub_1800EAF68)();
  v7 = (unsigned __int8)word_180290CF2;
  if ( !(unsigned int)sub_1800EAFF8() || (dword_180290D00 & 0x10000000) != 0 )
  {
    v10 = v7 % v6;
    v11 = v7 / v6;
    sub_1800EAF68(v9, v10);
    while ( v11 > 1 )
    {
      ++v5;
      v11 >>= 1;
    }
  }
  else
  {
    sub_1800EAF68(v9, v8);
  }
  v12 = dword_180290D08;
  v13 = (unsigned int)dword_180290D24;
  do
  {
    if ( v4 > SystemAffinityMask )
      break;
    if ( (v4 & ProcessAffinityMask) != 0 )
    {
      v14 = GetCurrentThread();
      SetThreadAffinityMask(v14, v4);
      Sleep(0);
      sub_18009A540(v28, 1);
      v15 = 0;
      v16 = v28[7] >> v5;
      v13 = (unsigned int)dword_180290D24;
      if ( !dword_180290D24 )
        goto LABEL_37;
      do
      {
        if ( *((_BYTE *)v29 + v15) == v16 )
          break;
        v15 = (unsigned int)(v15 + 1);
      }
      while ( (unsigned int)v15 < dword_180290D24 );
      if ( (unsigned int)v15 < 0x40 )
      {
LABEL_37:
        qword_18028DEE0[v15] |= v4;
        if ( (_DWORD)v15 == (_DWORD)v13 )
        {
          v13 = (unsigned int)(v13 + 1);
          *((_BYTE *)v29 + v15) = v16;
          dword_180290D24 = v13;
        }
      }
      v12 = ++dword_180290D08;
    }
    v4 *= 2LL;
  }
  while ( v4 );
  v17 = v12 / (unsigned int)v13;
  sub_1800EB724(v13, v12 % (unsigned int)v13);
  v18 = dword_180290D24;
  v19 = dword_180282E90;
  if ( dword_180290D24 > (unsigned int)dword_180282E90 )
  {
    v20 = dword_180282E90;
    do
    {
      if ( v20 < 0x40 )
        qword_18028DEE0[v20] = 0;
      ++v20;
    }
    while ( v20 < v18 );
    v18 = v19;
    dword_180290D24 = v19;
    dword_180290D08 = v17 * v19;
  }
  if ( !dword_180282E94 && v17 > 1 )
  {
    for ( i = 0; (unsigned int)i < v18; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i < 0x40 )
      {
        v22 = qword_18028DEE0[i];
        v23 = 0;
        v24 = 1;
        do
        {
          if ( (v24 & (unsigned int)v22) != 0 )
            break;
          ++v23;
          v24 *= 2;
        }
        while ( v23 < 0x20 );
        qword_18028DEE0[i] = (unsigned int)v22 & v24;
      }
    }
    dword_180290D08 = v18;
  }
  v25 = GetCurrentThread();
  SetThreadAffinityMask(v25, v3);
  Sleep(0);
}

```

## disassembly

```asm
0x1800eacb8  push    rbp
0x1800eacba  push    rbx
0x1800eacbb  push    rsi
0x1800eacbc  push    rdi
0x1800eacbd  push    r12
0x1800eacbf  push    r14
0x1800eacc1  push    r15
0x1800eacc3  lea     rbp, [rsp-27h]
0x1800eacc8  sub     rsp, 90h
0x1800eaccf  mov     rax, cs:__security_cookie
0x1800eacd6  xor     rax, rsp
0x1800eacd9  mov     [rbp+57h+var_40], rax
0x1800eacdd  mov     [rbp+57h+ProcessAffinityMask], 0
0x1800eace5  mov     [rbp+57h+SystemAffinityMask], 0
0x1800eaced  call    cs:GetCurrentProcess
0x1800eacf4  nop     dword ptr [rax+rax+00h]
0x1800eacf9  mov     rcx, rax; hProcess
0x1800eacfc  lea     r8, [rbp+57h+SystemAffinityMask]; lpSystemAffinityMask
0x1800ead00  lea     rdx, [rbp+57h+ProcessAffinityMask]; lpProcessAffinityMask
0x1800ead04  call    cs:GetProcessAffinityMask
0x1800ead0b  nop     dword ptr [rax+rax+00h]
0x1800ead10  call    cs:GetCurrentThread
0x1800ead17  nop     dword ptr [rax+rax+00h]
0x1800ead1c  mov     rdx, [rbp+57h+ProcessAffinityMask]; dwThreadAffinityMask
0x1800ead20  mov     rcx, rax; hThread
0x1800ead23  call    cs:SetThreadAffinityMask
0x1800ead2a  nop     dword ptr [rax+rax+00h]
0x1800ead2f  xor     edx, edx; Val
0x1800ead31  mov     cs:dword_180290D08, 0
0x1800ead3b  mov     r8d, 200h; Size
0x1800ead41  mov     cs:dword_180290D24, 0
0x1800ead4b  lea     rcx, qword_18028DEE0; void *
0x1800ead52  mov     r15, rax
0x1800ead55  call    memset
0x1800ead5a  xorps   xmm0, xmm0
0x1800ead5d  mov     r12d, 1
0x1800ead63  movups  [rbp+57h+var_80], xmm0
0x1800ead67  mov     edi, r12d
0x1800ead6a  xor     r14b, r14b
0x1800ead6d  movups  [rbp+57h+var_70], xmm0
0x1800ead71  movups  [rbp+57h+var_60], xmm0
0x1800ead75  movups  [rbp+57h+var_50], xmm0
0x1800ead79  call    sub_1800EB60C
0x1800ead7e  call    sub_1800EAF68
0x1800ead83  movsx   ecx, cs:word_180290CF2
0x1800ead8a  mov     ebx, eax
0x1800ead8c  movzx   esi, cl
0x1800ead8f  call    sub_1800EAFF8
0x1800ead94  test    eax, eax
0x1800ead96  jz      short loc_1800EADAB
0x1800ead98  test    cs:dword_180290D00, 10000000h
0x1800eada2  jnz     short loc_1800EADAB
0x1800eada4  call    sub_1800EAF68
0x1800eada9  jmp     short loc_1800EADC4
0x1800eadab  mov     eax, esi
0x1800eadad  xor     edx, edx
0x1800eadaf  div     ebx
0x1800eadb1  mov     ebx, eax
0x1800eadb3  call    sub_1800EAF68
0x1800eadb8  jmp     short loc_1800EADBF
0x1800eadba  add     r14b, r12b
0x1800eadbd  shr     ebx, 1
0x1800eadbf  cmp     ebx, r12d
0x1800eadc2  ja      short loc_1800EADBA
0x1800eadc4  mov     eax, cs:dword_180290D08
0x1800eadca  lea     rsi, qword_18028DEE0
0x1800eadd1  mov     ecx, cs:dword_180290D24
0x1800eadd7  cmp     rdi, [rbp+57h+SystemAffinityMask]
0x1800eaddb  ja      loc_1800EAE7E
0x1800eade1  test    [rbp+57h+ProcessAffinityMask], rdi
0x1800eade5  jz      loc_1800EAE75
0x1800eadeb  call    cs:GetCurrentThread
0x1800eadf2  nop     dword ptr [rax+rax+00h]
0x1800eadf7  mov     rcx, rax; hThread
0x1800eadfa  mov     rdx, rdi; dwThreadAffinityMask
0x1800eadfd  call    cs:SetThreadAffinityMask
0x1800eae04  nop     dword ptr [rax+rax+00h]
0x1800eae09  xor     ecx, ecx; dwMilliseconds
0x1800eae0b  call    cs:Sleep
0x1800eae12  nop     dword ptr [rax+rax+00h]
0x1800eae17  mov     edx, r12d
0x1800eae1a  lea     rcx, [rbp+57h+var_90]
0x1800eae1e  call    sub_18009A540
0x1800eae23  mov     r8d, [rbp+57h+var_8C]
0x1800eae27  mov     cl, r14b
0x1800eae2a  shr     r8d, 18h
0x1800eae2e  xor     edx, edx
0x1800eae30  shr     r8b, cl
0x1800eae33  mov     ecx, cs:dword_180290D24
0x1800eae39  test    ecx, ecx
0x1800eae3b  jz      short loc_1800EAE50
0x1800eae3d  cmp     byte ptr [rbp+rdx+57h+var_80], r8b
0x1800eae42  jz      short loc_1800EAE4B
0x1800eae44  add     edx, r12d
0x1800eae47  cmp     edx, ecx
0x1800eae49  jb      short loc_1800EAE3D
0x1800eae4b  cmp     edx, 40h ; '@'
0x1800eae4e  jnb     short loc_1800EAE66
0x1800eae50  or      [rsi+rdx*8], rdi
0x1800eae54  cmp     edx, ecx
0x1800eae56  jnz     short loc_1800EAE66
0x1800eae58  add     ecx, r12d
0x1800eae5b  mov     byte ptr [rbp+rdx+57h+var_80], r8b
0x1800eae60  mov     cs:dword_180290D24, ecx
0x1800eae66  mov     eax, cs:dword_180290D08
0x1800eae6c  add     eax, r12d
0x1800eae6f  mov     cs:dword_180290D08, eax
0x1800eae75  add     rdi, rdi
0x1800eae78  jnz     loc_1800EADD7
0x1800eae7e  xor     edx, edx
0x1800eae80  div     ecx
0x1800eae82  mov     ebx, eax
0x1800eae84  call    sub_1800EB724
0x1800eae89  mov     ecx, cs:dword_180290D24
0x1800eae8f  mov     r8d, cs:dword_180282E90
0x1800eae96  cmp     ecx, r8d
0x1800eae99  jbe     short loc_1800EAEC8
0x1800eae9b  mov     edx, r8d
0x1800eae9e  cmp     edx, 40h ; '@'
0x1800eaea1  jnb     short loc_1800EAEAD
0x1800eaea3  mov     eax, edx
0x1800eaea5  mov     qword ptr [rsi+rax*8], 0
0x1800eaead  add     edx, r12d
0x1800eaeb0  cmp     edx, ecx
0x1800eaeb2  jb      short loc_1800EAE9E
0x1800eaeb4  mov     ecx, r8d
0x1800eaeb7  imul    r8d, ebx
0x1800eaebb  mov     cs:dword_180290D24, ecx
0x1800eaec1  mov     cs:dword_180290D08, r8d
0x1800eaec8  cmp     cs:dword_180282E94, 0
0x1800eaecf  jnz     short loc_1800EAF16
0x1800eaed1  cmp     ebx, r12d
0x1800eaed4  jbe     short loc_1800EAF16
0x1800eaed6  xor     r8d, r8d
0x1800eaed9  test    ecx, ecx
0x1800eaedb  jz      short loc_1800EAF10
0x1800eaedd  cmp     r8d, 40h ; '@'
0x1800eaee1  jnb     short loc_1800EAF08
0x1800eaee3  mov     r10, [rsi+r8*8]
0x1800eaee7  xor     r9d, r9d
0x1800eaeea  mov     edx, r12d
0x1800eaeed  mov     eax, edx
0x1800eaeef  test    r10, rax
0x1800eaef2  jnz     short loc_1800EAEFF
0x1800eaef4  add     r9d, r12d
0x1800eaef7  add     edx, edx
0x1800eaef9  cmp     r9d, 20h ; ' '
0x1800eaefd  jb      short loc_1800EAEED
0x1800eaeff  mov     eax, edx
0x1800eaf01  and     rax, r10
0x1800eaf04  mov     [rsi+r8*8], rax
0x1800eaf08  add     r8d, r12d
0x1800eaf0b  cmp     r8d, ecx
0x1800eaf0e  jb      short loc_1800EAEDD
0x1800eaf10  mov     cs:dword_180290D08, ecx
0x1800eaf16  call    cs:GetCurrentThread
0x1800eaf1d  nop     dword ptr [rax+rax+00h]
0x1800eaf22  mov     rcx, rax; hThread
0x1800eaf25  mov     rdx, r15; dwThreadAffinityMask
0x1800eaf28  call    cs:SetThreadAffinityMask
0x1800eaf2f  nop     dword ptr [rax+rax+00h]
0x1800eaf34  xor     ecx, ecx; dwMilliseconds
0x1800eaf36  call    cs:Sleep
0x1800eaf3d  nop     dword ptr [rax+rax+00h]
0x1800eaf42  mov     rcx, [rbp+57h+var_40]
0x1800eaf46  xor     rcx, rsp; StackCookie
0x1800eaf49  call    __security_check_cookie
0x1800eaf4e  add     rsp, 90h
0x1800eaf55  pop     r15
0x1800eaf57  pop     r14
0x1800eaf59  pop     r12
0x1800eaf5b  pop     rdi
0x1800eaf5c  pop     rsi
0x1800eaf5d  pop     rbx
0x1800eaf5e  pop     rbp
0x1800eaf5f  retn
```
