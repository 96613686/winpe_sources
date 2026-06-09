# CWmpEncoderFrame::WritePixels(uint,uint,uint,uchar *)

- ea: `0x180028530`
- end: `0x1800287b0`
- name: `?WritePixels@CWmpEncoderFrame@@UEAAJIIIPEAE@Z`
- size: `640`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *this, unsigned int, unsigned int, unsigned int, char *lpBuffer)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180028530`
- `0x180028870`
- `0x180028980`
- `0x18002db34`
- `0x180043630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028790`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028790`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002856f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002856f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028654`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002868f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800286c5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002868f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800286c5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180028649`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180028649`

## pseudocode

```c
__int64 __fastcall CWmpEncoderFrame::WritePixels(
        CWmpEncoderFrame *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        char *lpBuffer)
{
  unsigned __int64 v5; // r12
  struct _RTL_CRITICAL_SECTION *v6; // r13
  unsigned __int64 v7; // r15
  bool v8; // zf
  char *v10; // r14
  int FrameBuffer; // ebx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // kr00_8
  unsigned __int64 v14; // kr10_8
  __int64 v15; // rsi
  unsigned __int64 v16; // rbx
  __int64 v17; // rdx
  void *v18; // rcx
  unsigned int i; // r12d
  void *v20; // rcx
  int j; // esi
  unsigned int v23; // r12d
  char *v24; // rsi
  __int64 v25; // r13
  LONG DistanceToMoveHigh; // [rsp+30h] [rbp-10h] BYREF
  char *v27; // [rsp+38h] [rbp-8h] BYREF
  struct _RTL_CRITICAL_SECTION *NumberOfBytesWritten; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v29; // [rsp+90h] [rbp+50h]

  v29 = a3;
  v5 = a4;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 48);
  v7 = a2;
  v8 = *((_BYTE *)this - 8) == 0;
  v27 = (char *)this - 56;
  NumberOfBytesWritten = v6;
  if ( !v8 )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 48));
  v10 = lpBuffer;
  if ( !lpBuffer )
    goto LABEL_33;
  FrameBuffer = CWmpCodecBase::HrTestStateMinimum((CWmpEncoderFrame *)((char *)this - 66376), 2);
  if ( FrameBuffer < 0 )
    goto LABEL_34;
  if ( (unsigned int)(v7 + *((_DWORD *)this + 4)) > *((_DWORD *)this - 16568) )
  {
    FrameBuffer = -2003292346;
    goto LABEL_34;
  }
  lpBuffer = 0;
  if ( !is_mul_ok(v7, v29) )
    goto LABEL_31;
  if ( v7 * v29 > v5 )
  {
LABEL_33:
    FrameBuffer = -2147024809;
    goto LABEL_34;
  }
  FrameBuffer = CWmpEncoderFrame::HrAllocateFrameBuffer((CWmpEncoderFrame *)((char *)this - 66376));
  if ( FrameBuffer < 0 )
    goto LABEL_34;
  v13 = *((_QWORD *)this - 8287);
  v14 = *((unsigned int *)this - 16569);
  v12 = v13 * v14;
  lpBuffer = 0;
  if ( !is_mul_ok(v13, v14) || v12 + 7 < v12 )
  {
LABEL_31:
    FrameBuffer = -2147024362;
    goto LABEL_34;
  }
  v15 = v29;
  v16 = (v12 + 7) >> 3;
  if ( v16 > v29 )
    goto LABEL_33;
  v17 = *((_QWORD *)this - 8) * *((unsigned int *)this + 4);
  v18 = (void *)*((_QWORD *)this + 24);
  if ( v18 == (void *)-1LL )
  {
    v23 = 0;
    v24 = (char *)(v17 + *((_QWORD *)this - 9));
    if ( (_DWORD)v7 )
    {
      v25 = v29;
      do
      {
        memcpy_0(v24, v10, v16);
        v24 += *((_QWORD *)this - 8);
        v10 += v25;
        ++v23;
      }
      while ( v23 < (unsigned int)v7 );
      v6 = NumberOfBytesWritten;
    }
  }
  else
  {
    DistanceToMoveHigh = (*((_QWORD *)this - 8) * (unsigned __int64)*((unsigned int *)this + 4)) >> 32;
    if ( SetFilePointer(v18, v17, &DistanceToMoveHigh, 0) == -1 && GetLastError() )
    {
LABEL_22:
      CGuard<CMTALock>::~CGuard<CMTALock>(&v27);
      return 2291674993LL;
    }
    LOBYTE(lpBuffer) = 0;
    for ( i = 0; i < (unsigned int)v7; ++i )
    {
      v20 = (void *)*((_QWORD *)this + 24);
      LODWORD(NumberOfBytesWritten) = 0;
      WriteFile(v20, v10, v16, (LPDWORD)&NumberOfBytesWritten, 0);
      if ( (unsigned int)NumberOfBytesWritten != v16 )
        goto LABEL_22;
      v10 += v15;
      for ( j = *((_DWORD *)this - 16) - v16; j > 0; --j )
        WriteFile(*((HANDLE *)this + 24), &lpBuffer, 1u, (LPDWORD)&NumberOfBytesWritten, 0);
      v15 = v29;
    }
  }
  *((_DWORD *)this + 4) += v7;
  FrameBuffer = 0;
  if ( -1.0 == *((double *)this - 8283) && -1.0 == *((double *)this - 8282) )
  {
    *((_QWORD *)this - 8282) = 0x4058000000000000LL;
    *((_QWORD *)this - 8283) = 0x4058000000000000LL;
  }
  *((_DWORD *)this - 16590) = 3;
LABEL_34:
  if ( this != (CWmpEncoderFrame *)56 && LOBYTE(v6[1].DebugInfo) )
    LeaveCriticalSection(v6);
  return (unsigned int)FrameBuffer;
}

```

## disassembly

```asm
0x180028530  mov     [rsp-38h+arg_8], rbx
0x180028535  mov     [rsp-38h+arg_10], r8d
0x18002853a  push    rbp
0x18002853b  push    rsi
0x18002853c  push    rdi
0x18002853d  push    r12
0x18002853f  push    r13
0x180028541  push    r14
0x180028543  push    r15
0x180028545  mov     rbp, rsp
0x180028548  sub     rsp, 40h
0x18002854c  lea     rax, [rcx-38h]
0x180028550  mov     r12d, r9d
0x180028553  lea     r13, [rax+8]
0x180028557  mov     r15d, edx
0x18002855a  cmp     byte ptr [r13+28h], 0
0x18002855f  mov     rdi, rcx
0x180028562  mov     [rbp+var_8], rax
0x180028566  mov     [rbp+NumberOfBytesWritten], r13
0x18002856a  jz      short loc_180028575
0x18002856c  mov     rcx, r13; lpCriticalSection
0x18002856f  call    cs:__imp_EnterCriticalSection
0x180028575  mov     r14, [rbp+lpBuffer]
0x180028579  test    r14, r14
0x18002857c  jz      loc_180028778
0x180028582  lea     rsi, [rdi-10348h]
0x180028589  mov     edx, 2; int
0x18002858e  mov     rcx, rsi; this
0x180028591  call    ?HrTestStateMinimum@CWmpCodecBase@@UEAAJH@Z; CWmpCodecBase::HrTestStateMinimum(int)
0x180028596  mov     ebx, eax
0x180028598  test    eax, eax
0x18002859a  js      loc_18002877D
0x1800285a0  mov     ecx, [rdi+10h]
0x1800285a3  add     ecx, r15d
0x1800285a6  cmp     ecx, [rdi-102E0h]
0x1800285ac  ja      loc_180028771
0x1800285b2  mov     eax, [rbp+arg_10]
0x1800285b5  mul     r15
0x1800285b8  mov     [rbp+lpBuffer], 0
0x1800285c0  test    rdx, rdx
0x1800285c3  jnz     loc_18002876A
0x1800285c9  cmp     rax, r12
0x1800285cc  ja      loc_180028778
0x1800285d2  mov     rcx, rsi; this
0x1800285d5  call    ?HrAllocateFrameBuffer@CWmpEncoderFrame@@MEAAJXZ; CWmpEncoderFrame::HrAllocateFrameBuffer(void)
0x1800285da  mov     ebx, eax
0x1800285dc  test    eax, eax
0x1800285de  js      loc_18002877D
0x1800285e4  mov     eax, [rdi-102E4h]
0x1800285ea  mul     qword ptr [rdi-102F8h]
0x1800285f1  mov     [rbp+lpBuffer], 0
0x1800285f9  test    rdx, rdx
0x1800285fc  jnz     loc_18002876A
0x180028602  lea     rbx, [rax+7]
0x180028606  cmp     rbx, rax
0x180028609  jb      loc_18002876A
0x18002860f  mov     esi, [rbp+arg_10]
0x180028612  shr     rbx, 3
0x180028616  cmp     rbx, rsi
0x180028619  ja      loc_180028778
0x18002861f  mov     edx, [rdi+10h]
0x180028622  imul    rdx, [rdi-40h]; lDistanceToMove
0x180028627  mov     rcx, [rdi+0C0h]; hFile
0x18002862e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180028632  jz      loc_1800286EC
0x180028638  mov     rax, rdx
0x18002863b  lea     r8, [rbp+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18002863f  sar     rax, 20h
0x180028643  xor     r9d, r9d; dwMoveMethod
0x180028646  mov     [rbp+DistanceToMoveHigh], eax
0x180028649  call    cs:__imp_SetFilePointer
0x18002864f  cmp     eax, 0FFFFFFFFh
0x180028652  jnz     short loc_18002865E
0x180028654  call    cs:__imp_GetLastError
0x18002865a  test    eax, eax
0x18002865c  jnz     short loc_1800286D9
0x18002865e  mov     byte ptr [rbp+lpBuffer], 0
0x180028662  xor     r12d, r12d
0x180028665  cmp     r12d, r15d
0x180028668  jnb     loc_180028720
0x18002866e  mov     rcx, [rdi+0C0h]; hFile
0x180028675  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180028679  mov     r8d, ebx; nNumberOfBytesToWrite
0x18002867c  mov     dword ptr [rbp+NumberOfBytesWritten], 0
0x180028683  mov     rdx, r14; lpBuffer
0x180028686  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x18002868f  call    cs:__imp_WriteFile
0x180028695  mov     eax, dword ptr [rbp+NumberOfBytesWritten]
0x180028698  cmp     rax, rbx
0x18002869b  jnz     short loc_1800286D9
0x18002869d  add     r14, rsi
0x1800286a0  mov     esi, [rdi-40h]
0x1800286a3  sub     esi, ebx
0x1800286a5  jmp     short loc_1800286CD
0x1800286a7  mov     rcx, [rdi+0C0h]; hFile
0x1800286ae  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800286b2  mov     r8d, 1; nNumberOfBytesToWrite
0x1800286b8  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x1800286c1  lea     rdx, [rbp+lpBuffer]; lpBuffer
0x1800286c5  call    cs:__imp_WriteFile
0x1800286cb  dec     esi
0x1800286cd  test    esi, esi
0x1800286cf  jg      short loc_1800286A7
0x1800286d1  mov     esi, [rbp+arg_10]
0x1800286d4  inc     r12d
0x1800286d7  jmp     short loc_180028665
0x1800286d9  lea     rcx, [rbp+var_8]
0x1800286dd  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x1800286e2  mov     eax, 88982F71h
0x1800286e7  jmp     loc_180028798
0x1800286ec  mov     rsi, [rdi-48h]
0x1800286f0  xor     r12d, r12d
0x1800286f3  add     rsi, rdx
0x1800286f6  test    r15d, r15d
0x1800286f9  jz      short loc_180028720
0x1800286fb  mov     r13d, [rbp+arg_10]
0x1800286ff  mov     r8, rbx; Size
0x180028702  mov     rdx, r14; Src
0x180028705  mov     rcx, rsi; void *
0x180028708  call    memcpy_0
0x18002870d  add     rsi, [rdi-40h]
0x180028711  add     r14, r13
0x180028714  inc     r12d
0x180028717  cmp     r12d, r15d
0x18002871a  jb      short loc_1800286FF
0x18002871c  mov     r13, [rbp+NumberOfBytesWritten]
0x180028720  add     [rdi+10h], r15d
0x180028724  xor     ebx, ebx
0x180028726  movsd   xmm0, cs:__real@bff0000000000000
0x18002872e  ucomisd xmm0, qword ptr [rdi-102D8h]
0x180028736  jp      short loc_18002875E
0x180028738  jnz     short loc_18002875E
0x18002873a  ucomisd xmm0, qword ptr [rdi-102D0h]
0x180028742  jp      short loc_18002875E
0x180028744  jnz     short loc_18002875E
0x180028746  mov     rax, 4058000000000000h
0x180028750  mov     [rdi-102D0h], rax
0x180028757  mov     [rdi-102D8h], rax
0x18002875e  mov     dword ptr [rdi-10338h], 3
0x180028768  jmp     short loc_18002877D
0x18002876a  mov     ebx, 80070216h
0x18002876f  jmp     short loc_18002877D
0x180028771  mov     ebx, 88982F46h
0x180028776  jmp     short loc_18002877D
0x180028778  mov     ebx, 80070057h
0x18002877d  lea     rax, [rdi-38h]
0x180028781  test    rax, rax
0x180028784  jz      short loc_180028796
0x180028786  cmp     byte ptr [r13+28h], 0
0x18002878b  jz      short loc_180028796
0x18002878d  mov     rcx, r13; lpCriticalSection
0x180028790  call    cs:__imp_LeaveCriticalSection
0x180028796  mov     eax, ebx
0x180028798  mov     rbx, [rsp+40h+arg_8]
0x1800287a0  add     rsp, 40h
0x1800287a4  pop     r15
0x1800287a6  pop     r14
0x1800287a8  pop     r13
0x1800287aa  pop     r12
0x1800287ac  pop     rdi
0x1800287ad  pop     rsi
0x1800287ae  pop     rbp
0x1800287af  retn
```
