# sub_1800EACF8

- ea: `0x1800eacf8`
- end: `0x1800eafa1`
- name: `sub_1800EACF8`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800eacac`

## callees

- `0x1800994a0`
- `0x180099ee0`
- `0x18009a540`
- `0x1800eacf8`
- `0x1800eafa8`
- `0x1800eb038`
- `0x1800eb64c`
- `0x1800eb764`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800eae4b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800eaf76`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800eae4b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800eaf76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ead2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ead2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ead50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800eae2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800eaf56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ead50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800eae2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800eaf56`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessAffinityMask` at `0x1800ead44`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessAffinityMask` at `0x1800ead44`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800ead63`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800eae3d`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800eaf68`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800ead63`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800eae3d`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800eaf68`

## pseudocode

```c
void sub_1800EACF8()
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
  dword_18028FD08 = 0;
  dword_18028FD24 = 0;
  v3 = v2;
  memset(qword_18028CEE0, 0, sizeof(qword_18028CEE0));
  memset(v29, 0, sizeof(v29));
  v4 = 1;
  v5 = 0;
  sub_1800EB64C();
  v6 = ((__int64 (*)(void))sub_1800EAFA8)();
  v7 = (unsigned __int8)word_18028FCF2;
  if ( !(unsigned int)sub_1800EB038() || (dword_18028FD00 & 0x10000000) != 0 )
  {
    v10 = v7 % v6;
    v11 = v7 / v6;
    sub_1800EAFA8(v9, v10);
    while ( v11 > 1 )
    {
      ++v5;
      v11 >>= 1;
    }
  }
  else
  {
    sub_1800EAFA8(v9, v8);
  }
  v12 = dword_18028FD08;
  v13 = (unsigned int)dword_18028FD24;
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
      v13 = (unsigned int)dword_18028FD24;
      if ( !dword_18028FD24 )
        goto LABEL_37;
      do
      {
        if ( *((_BYTE *)v29 + v15) == v16 )
          break;
        v15 = (unsigned int)(v15 + 1);
      }
      while ( (unsigned int)v15 < dword_18028FD24 );
      if ( (unsigned int)v15 < 0x40 )
      {
LABEL_37:
        qword_18028CEE0[v15] |= v4;
        if ( (_DWORD)v15 == (_DWORD)v13 )
        {
          v13 = (unsigned int)(v13 + 1);
          *((_BYTE *)v29 + v15) = v16;
          dword_18028FD24 = v13;
        }
      }
      v12 = ++dword_18028FD08;
    }
    v4 *= 2LL;
  }
  while ( v4 );
  v17 = v12 / (unsigned int)v13;
  sub_1800EB764(v13, v12 % (unsigned int)v13);
  v18 = dword_18028FD24;
  v19 = dword_180281E90;
  if ( dword_18028FD24 > (unsigned int)dword_180281E90 )
  {
    v20 = dword_180281E90;
    do
    {
      if ( v20 < 0x40 )
        qword_18028CEE0[v20] = 0;
      ++v20;
    }
    while ( v20 < v18 );
    v18 = v19;
    dword_18028FD24 = v19;
    dword_18028FD08 = v17 * v19;
  }
  if ( !dword_180281E94 && v17 > 1 )
  {
    for ( i = 0; (unsigned int)i < v18; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i < 0x40 )
      {
        v22 = qword_18028CEE0[i];
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
        qword_18028CEE0[i] = (unsigned int)v22 & v24;
      }
    }
    dword_18028FD08 = v18;
  }
  v25 = GetCurrentThread();
  SetThreadAffinityMask(v25, v3);
  Sleep(0);
}

```

## disassembly

```asm
0x1800eacf8  push    rbp
0x1800eacfa  push    rbx
0x1800eacfb  push    rsi
0x1800eacfc  push    rdi
0x1800eacfd  push    r12
0x1800eacff  push    r14
0x1800ead01  push    r15
0x1800ead03  lea     rbp, [rsp-27h]
0x1800ead08  sub     rsp, 90h
0x1800ead0f  mov     rax, cs:__security_cookie
0x1800ead16  xor     rax, rsp
0x1800ead19  mov     [rbp+57h+var_40], rax
0x1800ead1d  mov     [rbp+57h+ProcessAffinityMask], 0
0x1800ead25  mov     [rbp+57h+SystemAffinityMask], 0
0x1800ead2d  call    cs:GetCurrentProcess
0x1800ead34  nop     dword ptr [rax+rax+00h]
0x1800ead39  mov     rcx, rax; hProcess
0x1800ead3c  lea     r8, [rbp+57h+SystemAffinityMask]; lpSystemAffinityMask
0x1800ead40  lea     rdx, [rbp+57h+ProcessAffinityMask]; lpProcessAffinityMask
0x1800ead44  call    cs:GetProcessAffinityMask
0x1800ead4b  nop     dword ptr [rax+rax+00h]
0x1800ead50  call    cs:GetCurrentThread
0x1800ead57  nop     dword ptr [rax+rax+00h]
0x1800ead5c  mov     rdx, [rbp+57h+ProcessAffinityMask]; dwThreadAffinityMask
0x1800ead60  mov     rcx, rax; hThread
0x1800ead63  call    cs:SetThreadAffinityMask
0x1800ead6a  nop     dword ptr [rax+rax+00h]
0x1800ead6f  xor     edx, edx; Val
0x1800ead71  mov     cs:dword_18028FD08, 0
0x1800ead7b  mov     r8d, 200h; Size
0x1800ead81  mov     cs:dword_18028FD24, 0
0x1800ead8b  lea     rcx, qword_18028CEE0; void *
0x1800ead92  mov     r15, rax
0x1800ead95  call    memset
0x1800ead9a  xorps   xmm0, xmm0
0x1800ead9d  mov     r12d, 1
0x1800eada3  movups  [rbp+57h+var_80], xmm0
0x1800eada7  mov     edi, r12d
0x1800eadaa  xor     r14b, r14b
0x1800eadad  movups  [rbp+57h+var_70], xmm0
0x1800eadb1  movups  [rbp+57h+var_60], xmm0
0x1800eadb5  movups  [rbp+57h+var_50], xmm0
0x1800eadb9  call    sub_1800EB64C
0x1800eadbe  call    sub_1800EAFA8
0x1800eadc3  movsx   ecx, cs:word_18028FCF2
0x1800eadca  mov     ebx, eax
0x1800eadcc  movzx   esi, cl
0x1800eadcf  call    sub_1800EB038
0x1800eadd4  test    eax, eax
0x1800eadd6  jz      short loc_1800EADEB
0x1800eadd8  test    cs:dword_18028FD00, 10000000h
0x1800eade2  jnz     short loc_1800EADEB
0x1800eade4  call    sub_1800EAFA8
0x1800eade9  jmp     short loc_1800EAE04
0x1800eadeb  mov     eax, esi
0x1800eaded  xor     edx, edx
0x1800eadef  div     ebx
0x1800eadf1  mov     ebx, eax
0x1800eadf3  call    sub_1800EAFA8
0x1800eadf8  jmp     short loc_1800EADFF
0x1800eadfa  add     r14b, r12b
0x1800eadfd  shr     ebx, 1
0x1800eadff  cmp     ebx, r12d
0x1800eae02  ja      short loc_1800EADFA
0x1800eae04  mov     eax, cs:dword_18028FD08
0x1800eae0a  lea     rsi, qword_18028CEE0
0x1800eae11  mov     ecx, cs:dword_18028FD24
0x1800eae17  cmp     rdi, [rbp+57h+SystemAffinityMask]
0x1800eae1b  ja      loc_1800EAEBE
0x1800eae21  test    [rbp+57h+ProcessAffinityMask], rdi
0x1800eae25  jz      loc_1800EAEB5
0x1800eae2b  call    cs:GetCurrentThread
0x1800eae32  nop     dword ptr [rax+rax+00h]
0x1800eae37  mov     rcx, rax; hThread
0x1800eae3a  mov     rdx, rdi; dwThreadAffinityMask
0x1800eae3d  call    cs:SetThreadAffinityMask
0x1800eae44  nop     dword ptr [rax+rax+00h]
0x1800eae49  xor     ecx, ecx; dwMilliseconds
0x1800eae4b  call    cs:Sleep
0x1800eae52  nop     dword ptr [rax+rax+00h]
0x1800eae57  mov     edx, r12d
0x1800eae5a  lea     rcx, [rbp+57h+var_90]
0x1800eae5e  call    sub_18009A540
0x1800eae63  mov     r8d, [rbp+57h+var_8C]
0x1800eae67  mov     cl, r14b
0x1800eae6a  shr     r8d, 18h
0x1800eae6e  xor     edx, edx
0x1800eae70  shr     r8b, cl
0x1800eae73  mov     ecx, cs:dword_18028FD24
0x1800eae79  test    ecx, ecx
0x1800eae7b  jz      short loc_1800EAE90
0x1800eae7d  cmp     byte ptr [rbp+rdx+57h+var_80], r8b
0x1800eae82  jz      short loc_1800EAE8B
0x1800eae84  add     edx, r12d
0x1800eae87  cmp     edx, ecx
0x1800eae89  jb      short loc_1800EAE7D
0x1800eae8b  cmp     edx, 40h ; '@'
0x1800eae8e  jnb     short loc_1800EAEA6
0x1800eae90  or      [rsi+rdx*8], rdi
0x1800eae94  cmp     edx, ecx
0x1800eae96  jnz     short loc_1800EAEA6
0x1800eae98  add     ecx, r12d
0x1800eae9b  mov     byte ptr [rbp+rdx+57h+var_80], r8b
0x1800eaea0  mov     cs:dword_18028FD24, ecx
0x1800eaea6  mov     eax, cs:dword_18028FD08
0x1800eaeac  add     eax, r12d
0x1800eaeaf  mov     cs:dword_18028FD08, eax
0x1800eaeb5  add     rdi, rdi
0x1800eaeb8  jnz     loc_1800EAE17
0x1800eaebe  xor     edx, edx
0x1800eaec0  div     ecx
0x1800eaec2  mov     ebx, eax
0x1800eaec4  call    sub_1800EB764
0x1800eaec9  mov     ecx, cs:dword_18028FD24
0x1800eaecf  mov     r8d, cs:dword_180281E90
0x1800eaed6  cmp     ecx, r8d
0x1800eaed9  jbe     short loc_1800EAF08
0x1800eaedb  mov     edx, r8d
0x1800eaede  cmp     edx, 40h ; '@'
0x1800eaee1  jnb     short loc_1800EAEED
0x1800eaee3  mov     eax, edx
0x1800eaee5  mov     qword ptr [rsi+rax*8], 0
0x1800eaeed  add     edx, r12d
0x1800eaef0  cmp     edx, ecx
0x1800eaef2  jb      short loc_1800EAEDE
0x1800eaef4  mov     ecx, r8d
0x1800eaef7  imul    r8d, ebx
0x1800eaefb  mov     cs:dword_18028FD24, ecx
0x1800eaf01  mov     cs:dword_18028FD08, r8d
0x1800eaf08  cmp     cs:dword_180281E94, 0
0x1800eaf0f  jnz     short loc_1800EAF56
0x1800eaf11  cmp     ebx, r12d
0x1800eaf14  jbe     short loc_1800EAF56
0x1800eaf16  xor     r8d, r8d
0x1800eaf19  test    ecx, ecx
0x1800eaf1b  jz      short loc_1800EAF50
0x1800eaf1d  cmp     r8d, 40h ; '@'
0x1800eaf21  jnb     short loc_1800EAF48
0x1800eaf23  mov     r10, [rsi+r8*8]
0x1800eaf27  xor     r9d, r9d
0x1800eaf2a  mov     edx, r12d
0x1800eaf2d  mov     eax, edx
0x1800eaf2f  test    r10, rax
0x1800eaf32  jnz     short loc_1800EAF3F
0x1800eaf34  add     r9d, r12d
0x1800eaf37  add     edx, edx
0x1800eaf39  cmp     r9d, 20h ; ' '
0x1800eaf3d  jb      short loc_1800EAF2D
0x1800eaf3f  mov     eax, edx
0x1800eaf41  and     rax, r10
0x1800eaf44  mov     [rsi+r8*8], rax
0x1800eaf48  add     r8d, r12d
0x1800eaf4b  cmp     r8d, ecx
0x1800eaf4e  jb      short loc_1800EAF1D
0x1800eaf50  mov     cs:dword_18028FD08, ecx
0x1800eaf56  call    cs:GetCurrentThread
0x1800eaf5d  nop     dword ptr [rax+rax+00h]
0x1800eaf62  mov     rcx, rax; hThread
0x1800eaf65  mov     rdx, r15; dwThreadAffinityMask
0x1800eaf68  call    cs:SetThreadAffinityMask
0x1800eaf6f  nop     dword ptr [rax+rax+00h]
0x1800eaf74  xor     ecx, ecx; dwMilliseconds
0x1800eaf76  call    cs:Sleep
0x1800eaf7d  nop     dword ptr [rax+rax+00h]
0x1800eaf82  mov     rcx, [rbp+57h+var_40]
0x1800eaf86  xor     rcx, rsp; StackCookie
0x1800eaf89  call    __security_check_cookie
0x1800eaf8e  add     rsp, 90h
0x1800eaf95  pop     r15
0x1800eaf97  pop     r14
0x1800eaf99  pop     r12
0x1800eaf9b  pop     rdi
0x1800eaf9c  pop     rsi
0x1800eaf9d  pop     rbx
0x1800eaf9e  pop     rbp
0x1800eaf9f  retn
```
