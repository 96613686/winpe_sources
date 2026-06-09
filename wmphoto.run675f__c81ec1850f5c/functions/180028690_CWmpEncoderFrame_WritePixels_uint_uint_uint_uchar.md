# CWmpEncoderFrame::WritePixels(uint,uint,uint,uchar *)

- ea: `0x180028690`
- end: `0x180028939`
- name: `?WritePixels@CWmpEncoderFrame@@UEAAJIIIPEAE@Z`
- size: `681`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, unsigned int, unsigned int, unsigned int, LPCVOID lpBuffer)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180028690`
- `0x180028940`
- `0x18002b160`
- `0x18002de30`
- `0x180043e40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028912`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028912`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800286cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800286cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800287c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800287c0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028805`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028841`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028805`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028841`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800287af`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800287af`

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
0x180028690  mov     [rsp-38h+arg_8], rbx
0x180028695  mov     [rsp-38h+arg_10], r8d
0x18002869a  push    rbp
0x18002869b  push    rsi
0x18002869c  push    rdi
0x18002869d  push    r12
0x18002869f  push    r13
0x1800286a1  push    r14
0x1800286a3  push    r15
0x1800286a5  mov     rbp, rsp
0x1800286a8  sub     rsp, 40h
0x1800286ac  lea     rax, [rcx-38h]
0x1800286b0  mov     r12d, r9d
0x1800286b3  lea     r13, [rax+8]
0x1800286b7  mov     r15d, edx
0x1800286ba  cmp     byte ptr [r13+28h], 0
0x1800286bf  mov     rdi, rcx
0x1800286c2  mov     [rbp+var_8], rax
0x1800286c6  mov     [rbp+NumberOfBytesWritten], r13
0x1800286ca  jz      short loc_1800286DB
0x1800286cc  mov     rcx, r13; lpCriticalSection
0x1800286cf  call    cs:__imp_EnterCriticalSection
0x1800286d6  nop     dword ptr [rax+rax+00h]
0x1800286db  mov     r14, [rbp+lpBuffer]
0x1800286df  test    r14, r14
0x1800286e2  jz      loc_1800288FA
0x1800286e8  lea     rsi, [rdi-10348h]
0x1800286ef  mov     edx, 2; int
0x1800286f4  mov     rcx, rsi; this
0x1800286f7  call    ?HrTestStateMinimum@CWmpCodecBase@@UEAAJH@Z; CWmpCodecBase::HrTestStateMinimum(int)
0x1800286fc  mov     ebx, eax
0x1800286fe  test    eax, eax
0x180028700  js      loc_1800288FF
0x180028706  mov     ecx, [rdi+10h]
0x180028709  add     ecx, r15d
0x18002870c  cmp     ecx, [rdi-102E0h]
0x180028712  ja      loc_1800288F3
0x180028718  mov     eax, [rbp+arg_10]
0x18002871b  mul     r15
0x18002871e  mov     [rbp+lpBuffer], 0
0x180028726  test    rdx, rdx
0x180028729  jnz     loc_1800288EC
0x18002872f  cmp     rax, r12
0x180028732  ja      loc_1800288FA
0x180028738  mov     rcx, rsi; this
0x18002873b  call    ?HrAllocateFrameBuffer@CWmpEncoderFrame@@MEAAJXZ; CWmpEncoderFrame::HrAllocateFrameBuffer(void)
0x180028740  mov     ebx, eax
0x180028742  test    eax, eax
0x180028744  js      loc_1800288FF
0x18002874a  mov     eax, [rdi-102E4h]
0x180028750  mul     qword ptr [rdi-102F8h]
0x180028757  mov     [rbp+lpBuffer], 0
0x18002875f  test    rdx, rdx
0x180028762  jnz     loc_1800288EC
0x180028768  lea     rbx, [rax+7]
0x18002876c  cmp     rbx, rax
0x18002876f  jb      loc_1800288EC
0x180028775  mov     esi, [rbp+arg_10]
0x180028778  shr     rbx, 3
0x18002877c  cmp     rbx, rsi
0x18002877f  ja      loc_1800288FA
0x180028785  mov     edx, [rdi+10h]
0x180028788  imul    rdx, [rdi-40h]; lDistanceToMove
0x18002878d  mov     rcx, [rdi+0C0h]; hFile
0x180028794  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180028798  jz      loc_18002886E
0x18002879e  mov     rax, rdx
0x1800287a1  lea     r8, [rbp+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x1800287a5  sar     rax, 20h
0x1800287a9  xor     r9d, r9d; dwMoveMethod
0x1800287ac  mov     [rbp+DistanceToMoveHigh], eax
0x1800287af  call    cs:__imp_SetFilePointer
0x1800287b6  nop     dword ptr [rax+rax+00h]
0x1800287bb  cmp     eax, 0FFFFFFFFh
0x1800287be  jnz     short loc_1800287D4
0x1800287c0  call    cs:__imp_GetLastError
0x1800287c7  nop     dword ptr [rax+rax+00h]
0x1800287cc  test    eax, eax
0x1800287ce  jnz     loc_18002885B
0x1800287d4  mov     byte ptr [rbp+lpBuffer], 0
0x1800287d8  xor     r12d, r12d
0x1800287db  cmp     r12d, r15d
0x1800287de  jnb     loc_1800288A2
0x1800287e4  mov     rcx, [rdi+0C0h]; hFile
0x1800287eb  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800287ef  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800287f2  mov     dword ptr [rbp+NumberOfBytesWritten], 0
0x1800287f9  mov     rdx, r14; lpBuffer
0x1800287fc  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x180028805  call    cs:__imp_WriteFile
0x18002880c  nop     dword ptr [rax+rax+00h]
0x180028811  mov     eax, dword ptr [rbp+NumberOfBytesWritten]
0x180028814  cmp     rax, rbx
0x180028817  jnz     short loc_18002885B
0x180028819  add     r14, rsi
0x18002881c  mov     esi, [rdi-40h]
0x18002881f  sub     esi, ebx
0x180028821  jmp     short loc_18002884F
0x180028823  mov     rcx, [rdi+0C0h]; hFile
0x18002882a  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002882e  mov     r8d, 1; nNumberOfBytesToWrite
0x180028834  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x18002883d  lea     rdx, [rbp+lpBuffer]; lpBuffer
0x180028841  call    cs:__imp_WriteFile
0x180028848  nop     dword ptr [rax+rax+00h]
0x18002884d  dec     esi
0x18002884f  test    esi, esi
0x180028851  jg      short loc_180028823
0x180028853  mov     esi, [rbp+arg_10]
0x180028856  inc     r12d
0x180028859  jmp     short loc_1800287DB
0x18002885b  lea     rcx, [rbp+var_8]
0x18002885f  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x180028864  mov     eax, 88982F71h
0x180028869  jmp     loc_180028920
0x18002886e  mov     rsi, [rdi-48h]
0x180028872  xor     r12d, r12d
0x180028875  add     rsi, rdx
0x180028878  test    r15d, r15d
0x18002887b  jz      short loc_1800288A2
0x18002887d  mov     r13d, [rbp+arg_10]
0x180028881  mov     r8, rbx; Size
0x180028884  mov     rdx, r14; Src
0x180028887  mov     rcx, rsi; void *
0x18002888a  call    memcpy_0
0x18002888f  add     rsi, [rdi-40h]
0x180028893  add     r14, r13
0x180028896  inc     r12d
0x180028899  cmp     r12d, r15d
0x18002889c  jb      short loc_180028881
0x18002889e  mov     r13, [rbp+NumberOfBytesWritten]
0x1800288a2  add     [rdi+10h], r15d
0x1800288a6  xor     ebx, ebx
0x1800288a8  movsd   xmm0, cs:__real@bff0000000000000
0x1800288b0  ucomisd xmm0, qword ptr [rdi-102D8h]
0x1800288b8  jp      short loc_1800288E0
0x1800288ba  jnz     short loc_1800288E0
0x1800288bc  ucomisd xmm0, qword ptr [rdi-102D0h]
0x1800288c4  jp      short loc_1800288E0
0x1800288c6  jnz     short loc_1800288E0
0x1800288c8  mov     rax, 4058000000000000h
0x1800288d2  mov     [rdi-102D0h], rax
0x1800288d9  mov     [rdi-102D8h], rax
0x1800288e0  mov     dword ptr [rdi-10338h], 3
0x1800288ea  jmp     short loc_1800288FF
0x1800288ec  mov     ebx, 80070216h
0x1800288f1  jmp     short loc_1800288FF
0x1800288f3  mov     ebx, 88982F46h
0x1800288f8  jmp     short loc_1800288FF
0x1800288fa  mov     ebx, 80070057h
0x1800288ff  lea     rax, [rdi-38h]
0x180028903  test    rax, rax
0x180028906  jz      short loc_18002891E
0x180028908  cmp     byte ptr [r13+28h], 0
0x18002890d  jz      short loc_18002891E
0x18002890f  mov     rcx, r13; lpCriticalSection
0x180028912  call    cs:__imp_LeaveCriticalSection
0x180028919  nop     dword ptr [rax+rax+00h]
0x18002891e  mov     eax, ebx
0x180028920  mov     rbx, [rsp+40h+arg_8]
0x180028928  add     rsp, 40h
0x18002892c  pop     r15
0x18002892e  pop     r14
0x180028930  pop     r13
0x180028932  pop     r12
0x180028934  pop     rdi
0x180028935  pop     rsi
0x180028936  pop     rbp
0x180028937  retn
```
