# mlib::MeasureCurrentTSCFreqQPC(unsigned __int64 &)

- ea: `0x140058084`
- end: `0x140058392`
- name: `?MeasureCurrentTSCFreqQPC@mlib@@YAJAEA_K@Z`
- size: `782`
- prototype: `__int64 __fastcall(mlib *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14003bdf4`

## callees

- `0x140001abc`
- `0x140058084`
- `0x140058398`
- `0x140058488`
- `0x1400584b0`
- `0x140058570`
- `0x140058610`

## import_xrefs

- `KERNEL32!GetThreadPriority` at `0x1400580fd`
- `KERNEL32!GetThreadPriority` at `0x1400580fd`
- `KERNEL32!GetCurrentThread` at `0x1400580a9`
- `KERNEL32!GetCurrentThread` at `0x1400580f4`
- `KERNEL32!GetCurrentThread` at `0x14005811e`
- `KERNEL32!GetCurrentThread` at `0x140058147`
- `KERNEL32!GetCurrentThread` at `0x14005831d`
- `KERNEL32!GetCurrentThread` at `0x140058341`
- `KERNEL32!GetCurrentThread` at `0x1400580a9`
- `KERNEL32!GetCurrentThread` at `0x1400580f4`
- `KERNEL32!GetCurrentThread` at `0x14005811e`
- `KERNEL32!GetCurrentThread` at `0x140058147`
- `KERNEL32!GetCurrentThread` at `0x14005831d`
- `KERNEL32!GetCurrentThread` at `0x140058341`
- `KERNEL32!GetLastError` at `0x1400580c5`
- `KERNEL32!GetLastError` at `0x1400580c5`
- `KERNEL32!Sleep` at `0x140058163`
- `KERNEL32!Sleep` at `0x140058163`
- `KERNEL32!SetThreadAffinityMask` at `0x1400580b7`
- `KERNEL32!SetThreadAffinityMask` at `0x140058153`
- `KERNEL32!SetThreadAffinityMask` at `0x140058329`
- `KERNEL32!SetThreadAffinityMask` at `0x1400580b7`
- `KERNEL32!SetThreadAffinityMask` at `0x140058153`
- `KERNEL32!SetThreadAffinityMask` at `0x140058329`
- `KERNEL32!SetThreadPriority` at `0x14005812c`
- `KERNEL32!SetThreadPriority` at `0x14005834d`
- `KERNEL32!SetThreadPriority` at `0x14005812c`
- `KERNEL32!SetThreadPriority` at `0x14005834d`
- `KERNEL32!GetPriorityClass` at `0x1400580e9`
- `KERNEL32!GetPriorityClass` at `0x1400580e9`
- `KERNEL32!GetCurrentProcess` at `0x1400580e0`
- `KERNEL32!GetCurrentProcess` at `0x140058106`
- `KERNEL32!GetCurrentProcess` at `0x140058136`
- `KERNEL32!GetCurrentProcess` at `0x14005832f`
- `KERNEL32!GetCurrentProcess` at `0x1400580e0`
- `KERNEL32!GetCurrentProcess` at `0x140058106`
- `KERNEL32!GetCurrentProcess` at `0x140058136`
- `KERNEL32!GetCurrentProcess` at `0x14005832f`
- `KERNEL32!SetPriorityClass` at `0x140058114`
- `KERNEL32!SetPriorityClass` at `0x140058141`
- `KERNEL32!SetPriorityClass` at `0x14005833b`
- `KERNEL32!SetPriorityClass` at `0x140058114`
- `KERNEL32!SetPriorityClass` at `0x140058141`
- `KERNEL32!SetPriorityClass` at `0x14005833b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall mlib::MeasureCurrentTSCFreqQPC(mlib *this, unsigned __int64 *a2)
{
  HANDLE CurrentThread; // rax
  DWORD_PTR v3; // r13
  signed int result; // eax
  HANDLE CurrentProcess; // rax
  DWORD PriorityClass; // esi
  HANDLE v7; // rax
  HANDLE v8; // rax
  HANDLE v9; // rax
  HANDLE v10; // rax
  HANDLE v11; // rax
  mlib *v12; // rcx
  unsigned __int64 PerformanceFrequency64; // r15
  mlib *v14; // rcx
  unsigned __int64 v15; // r15
  unsigned __int64 *v16; // rbx
  _BYTE *v17; // rdi
  int v18; // r14d
  unsigned __int64 PerformanceCounter64; // rsi
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rsi
  unsigned __int64 v22; // r12
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rsi
  __int64 v26; // rsi
  unsigned __int64 v27; // rbx
  HANDLE v28; // rax
  HANDLE v29; // rax
  HANDLE v30; // rax
  int v31; // esi
  _QWORD v32[2]; // [rsp+20h] [rbp-60h] BYREF
  void *Block; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int64 *v34; // [rsp+38h] [rbp-48h]
  unsigned __int64 *v35; // [rsp+40h] [rbp-40h]
  __int64 v36; // [rsp+48h] [rbp-38h]
  __int64 v37; // [rsp+50h] [rbp-30h]
  __int64 v38; // [rsp+58h] [rbp-28h]
  unsigned __int64 v39; // [rsp+60h] [rbp-20h]
  __int64 v40; // [rsp+68h] [rbp-18h]
  char v41; // [rsp+70h] [rbp-10h]
  DWORD dwPriorityClass; // [rsp+C8h] [rbp+48h]
  int nPriority; // [rsp+D0h] [rbp+50h]

  *(_QWORD *)this = 0;
  CurrentThread = GetCurrentThread();
  v3 = SetThreadAffinityMask(CurrentThread, 1u);
  if ( !v3 )
    goto LABEL_2;
  CurrentProcess = GetCurrentProcess();
  PriorityClass = GetPriorityClass(CurrentProcess);
  dwPriorityClass = PriorityClass;
  v7 = GetCurrentThread();
  nPriority = GetThreadPriority(v7);
  v8 = GetCurrentProcess();
  if ( !SetPriorityClass(v8, 0x80u) )
    goto LABEL_2;
  v9 = GetCurrentThread();
  if ( !SetThreadPriority(v9, 2) )
  {
    v10 = GetCurrentProcess();
    SetPriorityClass(v10, PriorityClass);
    v11 = GetCurrentThread();
    SetThreadAffinityMask(v11, v3);
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  Sleep(0x14u);
  PerformanceFrequency64 = mlib::QueryPerformanceFrequency64(v12);
  Block = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = -1;
  v40 = 0;
  v41 = 0;
  v34 = 0;
  std::vector<SampleValue>::_Reallocate(&Block, 2048);
  v15 = 2 * (PerformanceFrequency64 / 0x3E8);
  while ( 1 )
  {
    v16 = v34;
    v17 = Block;
    if ( (unsigned __int64)(((char *)v34 - (_BYTE *)Block) >> 3) >= 0x800 )
      break;
    v18 = 256;
    do
    {
      PerformanceCounter64 = mlib::QueryPerformanceCounter64(v14);
      do
        v20 = mlib::QueryPerformanceCounter64(v14);
      while ( PerformanceCounter64 == v20 );
      v21 = v15 + v20;
      v22 = __rdtsc();
      while ( mlib::QueryPerformanceCounter64(v14) < v21 )
        ;
      v23 = __rdtsc();
      v24 = (unsigned __int64)HIDWORD(v23) << 32;
      v25 = 500 * ((v24 | (unsigned int)v23) - v22);
      v32[0] = v25;
      if ( v32 >= v16 || v17 > (_BYTE *)v32 )
      {
        if ( v16 == v35 )
        {
          std::vector<mlib::SampleValue>::_Reserve(&Block);
          v16 = v34;
          v17 = Block;
        }
        *v16 = v25;
      }
      else
      {
        v26 = ((char *)v32 - v17) >> 3;
        if ( v16 == v35 )
        {
          std::vector<mlib::SampleValue>::_Reserve(&Block);
          v16 = v34;
          v17 = Block;
        }
        *v16 = *(_QWORD *)&v17[8 * v26];
      }
      v34 = ++v16;
      --v18;
    }
    while ( v18 );
    if ( mlib::SampleManager::Process((mlib::SampleManager *)&Block, v24) )
    {
      v17 = Block;
      break;
    }
  }
  if ( v41 )
  {
    v27 = v39;
    if ( v39 - 1000000 > 0x3B8B87BF )
    {
      if ( v39 >= 0x989680 )
        v27 = 100000 * ((v39 + 500000) / 0x186A0);
    }
    else
    {
      v27 = 10000 * ((v39 + 50000) / 0x2710);
    }
  }
  else
  {
    v27 = 0;
  }
  v28 = GetCurrentThread();
  SetThreadAffinityMask(v28, v3);
  v29 = GetCurrentProcess();
  SetPriorityClass(v29, dwPriorityClass);
  v30 = GetCurrentThread();
  SetThreadPriority(v30, nPriority);
  *(_QWORD *)this = v27;
  v31 = 0;
  if ( !v27 )
    v31 = -2147467259;
  if ( v17 )
    operator delete(v17);
  return v31;
}

```

## disassembly

```asm
0x140058084  mov     [rsp-38h+arg_18], rbx
0x140058089  mov     [rsp-38h+arg_0], rcx
0x14005808e  push    rbp
0x14005808f  push    rsi
0x140058090  push    rdi
0x140058091  push    r12
0x140058093  push    r13
0x140058095  push    r14
0x140058097  push    r15
0x140058099  mov     rbp, rsp
0x14005809c  sub     rsp, 80h
0x1400580a3  xor     r12d, r12d
0x1400580a6  mov     [rcx], r12
0x1400580a9  call    cs:__imp_GetCurrentThread
0x1400580af  mov     rcx, rax; hThread
0x1400580b2  lea     edx, [r12+1]; dwThreadAffinityMask
0x1400580b7  call    cs:__imp_SetThreadAffinityMask
0x1400580bd  mov     r13, rax
0x1400580c0  test    rax, rax
0x1400580c3  jnz     short loc_1400580E0
0x1400580c5  call    cs:__imp_GetLastError
0x1400580cb  test    eax, eax
0x1400580cd  jle     loc_140058377
0x1400580d3  movzx   eax, ax
0x1400580d6  or      eax, 80070000h
0x1400580db  jmp     loc_140058377
0x1400580e0  call    cs:__imp_GetCurrentProcess
0x1400580e6  mov     rcx, rax; hProcess
0x1400580e9  call    cs:__imp_GetPriorityClass
0x1400580ef  mov     esi, eax
0x1400580f1  mov     [rbp+dwPriorityClass], eax
0x1400580f4  call    cs:__imp_GetCurrentThread
0x1400580fa  mov     rcx, rax; hThread
0x1400580fd  call    cs:__imp_GetThreadPriority
0x140058103  mov     [rbp+nPriority], eax
0x140058106  call    cs:__imp_GetCurrentProcess
0x14005810c  mov     rcx, rax; hProcess
0x14005810f  mov     edx, 80h; dwPriorityClass
0x140058114  call    cs:__imp_SetPriorityClass
0x14005811a  test    eax, eax
0x14005811c  jz      short loc_1400580C5
0x14005811e  call    cs:__imp_GetCurrentThread
0x140058124  mov     rcx, rax; hThread
0x140058127  mov     edx, 2; nPriority
0x14005812c  call    cs:__imp_SetThreadPriority
0x140058132  test    eax, eax
0x140058134  jnz     short loc_14005815E
0x140058136  call    cs:__imp_GetCurrentProcess
0x14005813c  mov     rcx, rax; hProcess
0x14005813f  mov     edx, esi; dwPriorityClass
0x140058141  call    cs:__imp_SetPriorityClass
0x140058147  call    cs:__imp_GetCurrentThread
0x14005814d  mov     rcx, rax; hThread
0x140058150  mov     rdx, r13; dwThreadAffinityMask
0x140058153  call    cs:__imp_SetThreadAffinityMask
0x140058159  jmp     loc_1400580C5
0x14005815e  mov     ecx, 14h; dwMilliseconds
0x140058163  call    cs:__imp_Sleep
0x140058169  call    ?QueryPerformanceFrequency64@mlib@@YA_KXZ; mlib::QueryPerformanceFrequency64(void)
0x14005816e  mov     r15, rax
0x140058171  mov     [rbp+Block], r12
0x140058175  mov     [rbp+var_40], r12
0x140058179  mov     [rbp+var_38], r12
0x14005817d  mov     [rbp+var_30], r12
0x140058181  mov     [rbp+var_28], r12
0x140058185  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFFh
0x14005818d  mov     [rbp+var_18], r12
0x140058191  mov     [rbp+var_10], r12b
0x140058195  mov     [rbp+var_48], r12
0x140058199  mov     edx, 800h
0x14005819e  lea     rcx, [rbp+Block]
0x1400581a2  call    ?_Reallocate@?$vector@USampleValue@@V?$allocator@USampleValue@@@std@@@std@@IEAAX_K@Z; std::vector<SampleValue>::_Reallocate(unsigned __int64)
0x1400581a7  nop
0x1400581a8  mov     rax, 624DD2F1A9FBE77h
0x1400581b2  mul     r15
0x1400581b5  sub     r15, rdx
0x1400581b8  shr     r15, 1
0x1400581bb  add     r15, rdx
0x1400581be  shr     r15, 9
0x1400581c2  add     r15, r15
0x1400581c5  mov     rbx, [rbp+var_48]
0x1400581c9  mov     rax, rbx
0x1400581cc  mov     rdi, [rbp+Block]
0x1400581d0  sub     rax, rdi
0x1400581d3  sar     rax, 3
0x1400581d7  cmp     rax, 800h
0x1400581dd  jnb     loc_1400582AD
0x1400581e3  mov     r14d, 100h
0x1400581e9  call    ?QueryPerformanceCounter64@mlib@@YA_KXZ; mlib::QueryPerformanceCounter64(void)
0x1400581ee  mov     rsi, rax
0x1400581f1  call    ?QueryPerformanceCounter64@mlib@@YA_KXZ; mlib::QueryPerformanceCounter64(void)
0x1400581f6  cmp     rsi, rax
0x1400581f9  jz      short loc_1400581F1
0x1400581fb  lea     rsi, [r15+rax]
0x1400581ff  rdtsc
0x140058201  shl     rdx, 20h
0x140058205  or      rax, rdx
0x140058208  mov     r12, rax
0x14005820b  call    ?QueryPerformanceCounter64@mlib@@YA_KXZ; mlib::QueryPerformanceCounter64(void)
0x140058210  cmp     rax, rsi
0x140058213  jb      short loc_14005820B
0x140058215  rdtsc
0x140058217  shl     rdx, 20h
0x14005821b  or      rax, rdx
0x14005821e  sub     rax, r12
0x140058221  imul    rsi, rax, 1F4h
0x140058228  mov     [rbp+var_60], rsi
0x14005822c  lea     rax, [rbp+var_60]
0x140058230  cmp     rax, rbx
0x140058233  jnb     short loc_140058269
0x140058235  lea     rax, [rbp+var_60]
0x140058239  cmp     rdi, rax
0x14005823c  ja      short loc_140058269
0x14005823e  lea     rsi, [rbp+var_60]
0x140058242  sub     rsi, rdi
0x140058245  sar     rsi, 3
0x140058249  cmp     rbx, [rbp+var_40]
0x14005824d  jnz     short loc_140058260
0x14005824f  lea     rcx, [rbp+Block]
0x140058253  call    ?_Reserve@?$vector@USampleValue@mlib@@V?$allocator@USampleValue@mlib@@@std@@@std@@IEAAX_K@Z; std::vector<mlib::SampleValue>::_Reserve(unsigned __int64)
0x140058258  mov     rbx, [rbp+var_48]
0x14005825c  mov     rdi, [rbp+Block]
0x140058260  mov     rax, [rdi+rsi*8]
0x140058264  mov     [rbx], rax
0x140058267  jmp     short loc_140058283
0x140058269  cmp     rbx, [rbp+var_40]
0x14005826d  jnz     short loc_140058280
0x14005826f  lea     rcx, [rbp+Block]
0x140058273  call    ?_Reserve@?$vector@USampleValue@mlib@@V?$allocator@USampleValue@mlib@@@std@@@std@@IEAAX_K@Z; std::vector<mlib::SampleValue>::_Reserve(unsigned __int64)
0x140058278  mov     rbx, [rbp+var_48]
0x14005827c  mov     rdi, [rbp+Block]
0x140058280  mov     [rbx], rsi
0x140058283  add     rbx, 8
0x140058287  mov     [rbp+var_48], rbx
0x14005828b  xor     r12d, r12d
0x14005828e  sub     r14d, 1
0x140058292  jnz     loc_1400581E9
0x140058298  lea     rcx, [rbp+Block]; this
0x14005829c  call    ?Process@SampleManager@mlib@@QEAA_NI@Z; mlib::SampleManager::Process(uint)
0x1400582a1  test    al, al
0x1400582a3  jz      loc_1400581C5
0x1400582a9  mov     rdi, [rbp+Block]
0x1400582ad  cmp     [rbp+var_10], r12b
0x1400582b1  jz      short loc_14005831A
0x1400582b3  mov     rbx, [rbp+var_20]
0x1400582b7  lea     rax, [rbx-0F4240h]
0x1400582be  cmp     rax, 3B8B87BFh
0x1400582c4  ja      short loc_1400582E7
0x1400582c6  lea     rcx, [rbx+0C350h]
0x1400582cd  mov     rax, 346DC5D63886594Bh
0x1400582d7  mul     rcx
0x1400582da  shr     rdx, 0Bh
0x1400582de  imul    rbx, rdx, 2710h
0x1400582e5  jmp     short loc_14005831D
0x1400582e7  cmp     rbx, 989680h
0x1400582ee  jb      short loc_14005831D
0x1400582f0  lea     rcx, [rbx+7A120h]
0x1400582f7  mov     rax, 4F8B588E368F0847h
0x140058301  mul     rcx
0x140058304  sub     rcx, rdx
0x140058307  shr     rcx, 1
0x14005830a  add     rcx, rdx
0x14005830d  shr     rcx, 10h
0x140058311  imul    rbx, rcx, 186A0h
0x140058318  jmp     short loc_14005831D
0x14005831a  mov     rbx, r12
0x14005831d  call    cs:__imp_GetCurrentThread
0x140058323  mov     rcx, rax; hThread
0x140058326  mov     rdx, r13; dwThreadAffinityMask
0x140058329  call    cs:__imp_SetThreadAffinityMask
0x14005832f  call    cs:__imp_GetCurrentProcess
0x140058335  mov     rcx, rax; hProcess
0x140058338  mov     edx, [rbp+dwPriorityClass]; dwPriorityClass
0x14005833b  call    cs:__imp_SetPriorityClass
0x140058341  call    cs:__imp_GetCurrentThread
0x140058347  mov     rcx, rax; hThread
0x14005834a  mov     edx, [rbp+nPriority]; nPriority
0x14005834d  call    cs:__imp_SetThreadPriority
0x140058353  mov     rax, [rbp+arg_0]
0x140058357  mov     [rax], rbx
0x14005835a  mov     esi, r12d
0x14005835d  mov     eax, 80004005h
0x140058362  test    rbx, rbx
0x140058365  cmovz   esi, eax
0x140058368  test    rdi, rdi
0x14005836b  jz      short loc_140058375
0x14005836d  mov     rcx, rdi; Block
0x140058370  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140058375  mov     eax, esi
0x140058377  mov     rbx, [rsp+80h+arg_18]
0x14005837f  add     rsp, 80h
0x140058386  pop     r15
0x140058388  pop     r14
0x14005838a  pop     r13
0x14005838c  pop     r12
0x14005838e  pop     rdi
0x14005838f  pop     rsi
0x140058390  pop     rbp
0x140058391  retn
```
