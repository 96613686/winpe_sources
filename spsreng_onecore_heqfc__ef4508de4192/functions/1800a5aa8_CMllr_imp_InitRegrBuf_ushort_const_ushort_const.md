# CMllr_imp::InitRegrBuf(ushort const *,ushort const *)

- ea: `0x1800a5aa8`
- end: `0x1800a6127`
- name: `?InitRegrBuf@CMllr_imp@@QEAAJPEBG0@Z`
- size: `1663`
- prototype: `__int64 __fastcall(CMllr_imp *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x1800056fc`
- `0x180013e90`

## callees

- `0x180002aac`
- `0x1800034b0`
- `0x180004010`
- `0x1800055cc`
- `0x1800136ec`
- `0x18001474c`
- `0x18009f17c`
- `0x1800a446c`
- `0x1800a44b4`
- `0x1800a4654`
- `0x1800a5394`
- `0x1800a5990`
- `0x1800a5aa8`
- `0x1800a6620`
- `0x1800a6930`
- `0x1800a6cb4`
- `0x1800c77ac`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800a5de4`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800a5de4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a5d68`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a5d68`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a5dd2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a5dd2`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800a5da7`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800a5da7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5d91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5d91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a604c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a60e3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a604c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a60e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800a6069`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800a60fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800a6069`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800a60fc`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a5e48`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a5e48`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800a5e24`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800a5e24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMllr_imp::InitRegrBuf(CMllr_imp *this, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  int inited; // esi
  int v5; // eax
  bool v6; // r15
  int v7; // eax
  int v8; // eax
  int v9; // r9d
  int v10; // r8d
  int v11; // eax
  double v12; // xmm8_8
  double v13; // xmm6_8
  double v14; // xmm6_8
  int v15; // r14d
  int v16; // r12d
  int v17; // edi
  int v18; // r13d
  HANDLE FileW; // rax
  LONG v20; // edi
  DWORD FileSize; // eax
  bool v22; // r12
  unsigned int Win32Error; // ebx
  HANDLE FileMappingW; // rax
  char *v26; // rdi
  unsigned __int16 *v27; // rax
  unsigned __int16 v28; // dx
  unsigned __int16 *v29; // r14
  int v30; // ecx
  unsigned int v31; // r8d
  unsigned __int16 *v32; // rax
  unsigned __int16 v33; // dx
  unsigned __int16 *v34; // r14
  int v35; // ecx
  unsigned int v36; // r8d
  int v37; // eax
  int v38; // eax
  __int64 v39; // rax
  unsigned int v40; // r8d
  int v41[2]; // [rsp+78h] [rbp-90h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-88h]
  unsigned __int16 *v43; // [rsp+88h] [rbp-80h]
  void **v44; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int16 *v45; // [rsp+A0h] [rbp-68h]
  unsigned int v46; // [rsp+A8h] [rbp-60h]
  __int16 v47; // [rsp+B0h] [rbp-58h] BYREF

  v43 = a3;
  lpFileName = a2;
  v46 = 0x80000000;
  v45 = (unsigned __int16 *)&v47;
  v47 = 0;
  v44 = &CQuickStringW<260>::`vftable';
  inited = CMllr_imp::InitIndexTables(this);
  if ( inited < 0 )
    goto LABEL_22;
  v41[0] = 0;
  CMllr_imp::GetBaseClassCount(this, v41);
  *((_WORD *)this + 256) = 0;
  *((_BYTE *)this + 514) = 31;
  *((_DWORD *)this + 172) = 1075419546;
  *((_DWORD *)this + 173) = 1082130432;
  v5 = CMllr_imp::RegBufOption(this);
  *((_DWORD *)this + 87) = v5;
  v6 = 1;
  if ( v5 )
  {
    v7 = v5 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        if ( v8 == 1 )
        {
          *((_DWORD *)this + 236) = 0;
          *((_DWORD *)this + 238) = 0;
          v9 = *((_DWORD *)this + 190);
          v10 = *((_DWORD *)this + 9) / v9;
          *((_DWORD *)this + 237) = 8
                                  * (v9 * v10 * v10 + *((_DWORD *)this + 9) * (v10 + 1 + v10 + (v10 + 1) * v10 / 2 + 2))
                                  + 24;
        }
      }
      else
      {
        v11 = *((_DWORD *)this + 9) + 1;
        *((_DWORD *)this + 236) = v11;
        *((_DWORD *)this + 238) = v11;
        v12 = o_log_0(2.0);
        *((_BYTE *)this + 513) = (int)(31.0 - o_log_0((double)*((int *)this + 129)) / v12 - 1.0);
        *((_BYTE *)this + 512) = (int)(31.0 - o_log_0((double)v41[0]) / v12 - 1.0);
        *((_DWORD *)this + 237) = 0;
      }
    }
    else
    {
      *((_QWORD *)this + 118) = 0;
      *((_DWORD *)this + 238) = *((_DWORD *)this + 9) * (*((_DWORD *)this + 9) + *((_DWORD *)this + 130) + 1) + 1;
      v13 = o_log_0((double)v41[0]);
      *((_BYTE *)this + 512) = (int)(32.0 - v13 / o_log_0(2.0) - 1.0);
    }
  }
  else
  {
    *((_DWORD *)this + 236) = *((_DWORD *)this + 9) + 1;
    *(_QWORD *)((char *)this + 948) = 0;
    v14 = o_log_0((double)*((int *)this + 129));
    *((_BYTE *)this + 513) = (int)(32.0 - v14 / o_log_0(2.0) - 1.0);
  }
  v15 = *((_DWORD *)this + 236);
  v16 = *((_DWORD *)this + 129);
  v17 = *((_DWORD *)this + 238);
  v18 = *((_DWORD *)this + 237);
  FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 4u, 0x10000080u, 0);
  *((_QWORD *)this + 53) = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_17;
  v20 = v18 + 4 * (v16 * v15 + v41[0] * v17) + 12;
  if ( GetLastError() == 183 )
  {
    FileSize = GetFileSize(*((HANDLE *)this + 53), 0);
    v6 = FileSize != v20;
    v22 = FileSize != v20;
    if ( FileSize == v20 )
      goto LABEL_18;
  }
  else
  {
    v22 = 0;
  }
  if ( SetFilePointer(*((HANDLE *)this + 53), v20, 0, 0) == -1 || !SetEndOfFile(*((HANDLE *)this + 53)) )
    goto LABEL_17;
LABEL_18:
  FileMappingW = CreateFileMappingW(*((HANDLE *)this + 53), 0, 0x8000004u, 0, 0, 0);
  *((_QWORD *)this + 54) = FileMappingW;
  if ( !FileMappingW || (v26 = (char *)MapViewOfFile(FileMappingW, 2u, 0, 0, 0), (*((_QWORD *)this + 55) = v26) == 0) )
  {
LABEL_17:
    Win32Error = HrFromLastWin32Error();
    CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v44);
    return Win32Error;
  }
  CWinHeap::Free((CWinHeap *)&g_heap, *((void **)this + 48));
  v27 = CHeap::WcsDup((CHeap *)&g_heap, lpFileName);
  *((_QWORD *)this + 48) = v27;
  if ( !v27 )
    goto LABEL_21;
  v29 = wcsrchr(v27, v28);
  if ( v29 )
  {
    CQuickStringW<260>::Append(&v44, L"Local\\");
    CQuickStringW<260>::Append(&v44, v29 + 1);
    *((_QWORD *)this + 49) = SpCreateMutex(v30, v45, v31);
  }
  if ( !*((_QWORD *)this + 49) )
    goto LABEL_17;
  CWinHeap::Free((CWinHeap *)&g_heap, *((void **)this + 50));
  *((_QWORD *)this + 50) = 0;
  if ( !v43 )
  {
LABEL_31:
    *((_QWORD *)this + 57) = 0;
    v37 = *((_DWORD *)this + 238);
    if ( v37 )
    {
      *((_QWORD *)this + 57) = v26;
      v26 += 4 * (unsigned int)(v41[0] * v37);
    }
    *((_QWORD *)this + 56) = 0;
    v38 = *((_DWORD *)this + 236);
    if ( v38 )
    {
      *((_QWORD *)this + 56) = v26;
      v26 += 4 * (unsigned int)(*((_DWORD *)this + 129) * v38);
    }
    *((_QWORD *)this + 58) = 0;
    v39 = *((unsigned int *)this + 237);
    if ( (_DWORD)v39 )
    {
      *((_QWORD *)this + 58) = v26;
      v26 += v39;
    }
    *((_QWORD *)this + 61) = v26;
    *((_QWORD *)this + 62) = v26 + 4;
    *((_QWORD *)this + 63) = v26 + 8;
    if ( v6 )
    {
      if ( WaitForSingleObject(*((HANDLE *)this + 49), 0xFFFFFFFF) != -1 )
      {
        CMllr_imp::ClearAdaptationData(this);
        ReleaseMutex(*((HANDLE *)this + 49));
        if ( v22 )
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(*((_QWORD *)this + 2) + 16LL) + 128LL))(
            *(_QWORD *)(*((_QWORD *)this + 2) + 16LL),
            2135,
            2);
      }
    }
    else
    {
      if ( (unsigned int)CMllr_imp::fCorruptedRegBuf(this)
        && WaitForSingleObject(*((HANDLE *)this + 49), 0xFFFFFFFF) != -1 )
      {
        CMllr_imp::RestoreRegBuf(this);
        ReleaseMutex(*((HANDLE *)this + 49));
      }
      v40 = *((_DWORD *)this + 237);
      if ( v40 )
        CMllr_imp::SetPersistentData(this, *((const unsigned __int8 **)this + 58), v40);
    }
    goto LABEL_22;
  }
  v32 = CHeap::WcsDup((CHeap *)&g_heap, v43);
  *((_QWORD *)this + 50) = v32;
  if ( v32 )
  {
    v34 = wcsrchr(v32, v33);
    if ( v34 )
    {
      v46 &= 0x80000000;
      *v45 = 0;
      CQuickStringW<260>::Append(&v44, L"Local\\");
      CQuickStringW<260>::Append(&v44, v34 + 1);
      *((_QWORD *)this + 51) = SpCreateMutex(v35, v45, v36);
    }
    if ( !*((_QWORD *)this + 51) )
      goto LABEL_17;
    goto LABEL_31;
  }
LABEL_21:
  inited = -2147024882;
LABEL_22:
  CQuickStringTBase::~CQuickStringTBase((CQuickStringTBase *)&v44);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800a5aa8  mov     rax, rsp
0x1800a5aab  mov     [rax+20h], rbx
0x1800a5aaf  push    rbp
0x1800a5ab0  push    rsi
0x1800a5ab1  push    rdi
0x1800a5ab2  push    r12
0x1800a5ab4  push    r13
0x1800a5ab6  push    r14
0x1800a5ab8  push    r15
0x1800a5aba  lea     rbp, [rax-238h]
0x1800a5ac1  sub     rsp, 300h
0x1800a5ac8  movaps  xmmword ptr [rax-48h], xmm6
0x1800a5acc  movaps  xmmword ptr [rax-58h], xmm7
0x1800a5ad0  movaps  xmmword ptr [rax-68h], xmm8
0x1800a5ad5  mov     rax, cs:__security_cookie
0x1800a5adc  xor     rax, rsp
0x1800a5adf  mov     [rbp+230h+var_70], rax
0x1800a5ae6  mov     [rbp+230h+var_2B0], r8
0x1800a5aea  mov     [rsp+330h+lpFileName], rdx
0x1800a5aef  mov     rbx, rcx
0x1800a5af2  mov     [rbp+230h+var_290], 80000000h
0x1800a5af9  lea     rax, [rbp+230h+var_288]
0x1800a5afd  mov     [rbp+230h+var_298], rax
0x1800a5b01  xor     edi, edi
0x1800a5b03  mov     [rbp+230h+var_288], di
0x1800a5b07  lea     rax, ??_7?$CQuickStringW@$0BAE@@@6B@; const CQuickStringW<260>::`vftable'
0x1800a5b0e  mov     [rbp+230h+var_2A0], rax
0x1800a5b12  call    ?InitIndexTables@CMllr_imp@@AEAAJXZ; CMllr_imp::InitIndexTables(void)
0x1800a5b17  mov     esi, eax
0x1800a5b19  test    eax, eax
0x1800a5b1b  js      loc_1800A5E92
0x1800a5b21  mov     [rsp+330h+var_2C0], edi
0x1800a5b25  lea     rdx, [rsp+330h+var_2C0]; int *
0x1800a5b2a  mov     rcx, rbx; this
0x1800a5b2d  call    ?GetBaseClassCount@CMllr_imp@@AEAAXPEAH@Z; CMllr_imp::GetBaseClassCount(int *)
0x1800a5b32  mov     [rbx+200h], di
0x1800a5b39  mov     byte ptr [rbx+202h], 1Fh
0x1800a5b40  mov     dword ptr [rbx+2B0h], 4019999Ah
0x1800a5b4a  mov     dword ptr [rbx+2B4h], 40800000h
0x1800a5b54  mov     rcx, rbx
0x1800a5b57  call    ?RegBufOption@CMllr_imp@@AEAA?AW4RegBufType@@XZ; CMllr_imp::RegBufOption(void)
0x1800a5b5c  mov     [rbx+15Ch], eax
0x1800a5b62  lea     r10d, [rdi+2]
0x1800a5b66  lea     r15d, [rdi+1]
0x1800a5b6a  test    eax, eax
0x1800a5b6c  jz      loc_1800A5CCB
0x1800a5b72  sub     eax, r15d
0x1800a5b75  jz      loc_1800A5C69
0x1800a5b7b  sub     eax, r15d
0x1800a5b7e  jz      short loc_1800A5BD9
0x1800a5b80  cmp     eax, r15d
0x1800a5b83  jnz     loc_1800A5D23
0x1800a5b89  mov     [rbx+3B0h], edi
0x1800a5b8f  mov     [rbx+3B8h], edi
0x1800a5b95  mov     r9d, [rbx+2F8h]
0x1800a5b9c  mov     eax, [rbx+24h]
0x1800a5b9f  cdq
0x1800a5ba0  idiv    r9d
0x1800a5ba3  mov     r8d, eax
0x1800a5ba6  lea     ecx, [rax+1]
0x1800a5ba9  imul    eax, ecx
0x1800a5bac  cdq
0x1800a5bad  idiv    r10d
0x1800a5bb0  add     eax, r10d
0x1800a5bb3  add     eax, r8d
0x1800a5bb6  add     eax, ecx
0x1800a5bb8  imul    eax, [rbx+24h]
0x1800a5bbc  imul    r8d, r8d
0x1800a5bc0  imul    r8d, r9d
0x1800a5bc4  add     eax, r8d
0x1800a5bc7  lea     eax, ds:18h[rax*8]
0x1800a5bce  mov     [rbx+3B4h], eax
0x1800a5bd4  jmp     loc_1800A5D23
0x1800a5bd9  mov     eax, [rbx+24h]
0x1800a5bdc  inc     eax
0x1800a5bde  mov     [rbx+3B0h], eax
0x1800a5be4  mov     [rbx+3B8h], eax
0x1800a5bea  movsd   xmm0, cs:__real@4000000000000000; X
0x1800a5bf2  call    _o_log_0
0x1800a5bf7  movaps  xmm8, xmm0
0x1800a5bfb  mov     eax, [rbx+204h]
0x1800a5c01  xorps   xmm0, xmm0
0x1800a5c04  cvtsi2sd xmm0, rax; X
0x1800a5c09  call    _o_log_0
0x1800a5c0e  divsd   xmm0, xmm8
0x1800a5c13  movsd   xmm7, cs:__real@403f000000000000
0x1800a5c1b  movaps  xmm1, xmm7
0x1800a5c1e  subsd   xmm1, xmm0
0x1800a5c22  subsd   xmm1, cs:__real@3ff0000000000000
0x1800a5c2a  cvttsd2si eax, xmm1
0x1800a5c2e  mov     [rbx+201h], al
0x1800a5c34  movd    xmm0, [rsp+330h+var_2C0]
0x1800a5c3a  cvtdq2pd xmm0, xmm0; X
0x1800a5c3e  call    _o_log_0
0x1800a5c43  divsd   xmm0, xmm8
0x1800a5c48  subsd   xmm7, xmm0
0x1800a5c4c  subsd   xmm7, cs:__real@3ff0000000000000
0x1800a5c54  cvttsd2si eax, xmm7
0x1800a5c58  mov     [rbx+200h], al
0x1800a5c5e  mov     [rbx+3B4h], edi
0x1800a5c64  jmp     loc_1800A5D23
0x1800a5c69  mov     [rbx+3B0h], rdi
0x1800a5c70  mov     edx, [rbx+208h]
0x1800a5c76  inc     edx
0x1800a5c78  add     edx, [rbx+24h]
0x1800a5c7b  imul    edx, [rbx+24h]
0x1800a5c7f  add     edx, r15d
0x1800a5c82  mov     [rbx+3B8h], edx
0x1800a5c88  movd    xmm0, [rsp+330h+var_2C0]
0x1800a5c8e  cvtdq2pd xmm0, xmm0; X
0x1800a5c92  call    _o_log_0
0x1800a5c97  movaps  xmm6, xmm0
0x1800a5c9a  movsd   xmm0, cs:__real@4000000000000000; X
0x1800a5ca2  call    _o_log_0
0x1800a5ca7  divsd   xmm6, xmm0
0x1800a5cab  movsd   xmm1, cs:__real@4040000000000000
0x1800a5cb3  subsd   xmm1, xmm6
0x1800a5cb7  subsd   xmm1, cs:__real@3ff0000000000000
0x1800a5cbf  cvttsd2si eax, xmm1
0x1800a5cc3  mov     [rbx+200h], al
0x1800a5cc9  jmp     short loc_1800A5D23
0x1800a5ccb  mov     eax, [rbx+24h]
0x1800a5cce  add     eax, r15d
0x1800a5cd1  mov     [rbx+3B0h], eax
0x1800a5cd7  mov     [rbx+3B4h], rdi
0x1800a5cde  mov     eax, [rbx+204h]
0x1800a5ce4  xorps   xmm0, xmm0
0x1800a5ce7  cvtsi2sd xmm0, rax; X
0x1800a5cec  call    _o_log_0
0x1800a5cf1  movaps  xmm6, xmm0
0x1800a5cf4  movsd   xmm0, cs:__real@4000000000000000; X
0x1800a5cfc  call    _o_log_0
0x1800a5d01  divsd   xmm6, xmm0
0x1800a5d05  movsd   xmm1, cs:__real@4040000000000000
0x1800a5d0d  subsd   xmm1, xmm6
0x1800a5d11  subsd   xmm1, cs:__real@3ff0000000000000
0x1800a5d19  cvttsd2si eax, xmm1
0x1800a5d1d  mov     [rbx+201h], al
0x1800a5d23  mov     r14d, [rbx+3B0h]
0x1800a5d2a  mov     r12d, [rbx+204h]
0x1800a5d31  mov     edi, [rbx+3B8h]
0x1800a5d37  mov     r13d, [rbx+3B4h]
0x1800a5d3e  mov     [rsp+330h+hTemplateFile], 0; hTemplateFile
0x1800a5d47  mov     [rsp+330h+dwFlagsAndAttributes], 10000080h; dwFlagsAndAttributes
0x1800a5d4f  mov     [rsp+330h+dwCreationDisposition], 4; dwCreationDisposition
0x1800a5d57  xor     r9d, r9d; lpSecurityAttributes
0x1800a5d5a  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a5d5f  lea     r8d, [r9+3]; dwShareMode
0x1800a5d63  mov     rcx, [rsp+330h+lpFileName]; lpFileName
0x1800a5d68  call    cs:__imp_CreateFileW
0x1800a5d6e  mov     [rbx+1A8h], rax
0x1800a5d75  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a5d79  jz      short loc_1800A5DEE
0x1800a5d7b  imul    edi, [rsp+330h+var_2C0]
0x1800a5d80  imul    r14d, r12d
0x1800a5d84  add     edi, r14d
0x1800a5d87  lea     edi, ds:0Ch[rdi*4]
0x1800a5d8e  add     edi, r13d
0x1800a5d91  call    cs:__imp_GetLastError
0x1800a5d97  cmp     eax, 0B7h
0x1800a5d9c  jnz     short loc_1800A5DBD
0x1800a5d9e  xor     edx, edx; lpFileSizeHigh
0x1800a5da0  mov     rcx, [rbx+1A8h]; hFile
0x1800a5da7  call    cs:__imp_GetFileSize
0x1800a5dad  cmp     eax, edi
0x1800a5daf  setnz   r15b
0x1800a5db3  mov     r12b, r15b
0x1800a5db6  jz      short loc_1800A5E05
0x1800a5db8  xor     r13d, r13d
0x1800a5dbb  jmp     short loc_1800A5DC3
0x1800a5dbd  xor     r13d, r13d
0x1800a5dc0  mov     r12b, r13b
0x1800a5dc3  xor     r9d, r9d; dwMoveMethod
0x1800a5dc6  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800a5dc9  mov     edx, edi; lDistanceToMove
0x1800a5dcb  mov     rcx, [rbx+1A8h]; hFile
0x1800a5dd2  call    cs:__imp_SetFilePointer
0x1800a5dd8  cmp     eax, 0FFFFFFFFh
0x1800a5ddb  jz      short loc_1800A5DEE
0x1800a5ddd  mov     rcx, [rbx+1A8h]; hFile
0x1800a5de4  call    cs:__imp_SetEndOfFile
0x1800a5dea  test    eax, eax
0x1800a5dec  jnz     short loc_1800A5E08
0x1800a5dee  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800a5df3  mov     ebx, eax
0x1800a5df5  lea     rcx, [rbp+230h+var_2A0]; this
0x1800a5df9  call    ??1CQuickStringTBase@@MEAA@XZ; CQuickStringTBase::~CQuickStringTBase(void)
0x1800a5dfe  mov     eax, ebx
0x1800a5e00  jmp     loc_1800A5E9D
0x1800a5e05  xor     r13d, r13d
0x1800a5e08  mov     qword ptr [rsp+330h+dwFlagsAndAttributes], r13; lpName
0x1800a5e0d  mov     [rsp+330h+dwCreationDisposition], r13d; dwMaximumSizeLow
0x1800a5e12  xor     r9d, r9d; dwMaximumSizeHigh
0x1800a5e15  xor     edx, edx; lpFileMappingAttributes
0x1800a5e17  mov     r8d, 8000004h; flProtect
0x1800a5e1d  mov     rcx, [rbx+1A8h]; hFile
0x1800a5e24  call    cs:__imp_CreateFileMappingW
0x1800a5e2a  mov     [rbx+1B0h], rax
0x1800a5e31  test    rax, rax
0x1800a5e34  jz      short loc_1800A5DEE
0x1800a5e36  mov     qword ptr [rsp+330h+dwCreationDisposition], r13; dwNumberOfBytesToMap
0x1800a5e3b  xor     r9d, r9d; dwFileOffsetLow
0x1800a5e3e  xor     r8d, r8d; dwFileOffsetHigh
0x1800a5e41  lea     edx, [r9+2]; dwDesiredAccess
0x1800a5e45  mov     rcx, rax; hFileMappingObject
0x1800a5e48  call    cs:__imp_MapViewOfFile
0x1800a5e4e  mov     rdi, rax
0x1800a5e51  mov     [rbx+1B8h], rax
0x1800a5e58  test    rax, rax
0x1800a5e5b  jz      short loc_1800A5DEE
0x1800a5e5d  mov     rdx, [rbx+180h]; void *
0x1800a5e64  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800a5e6b  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800a5e70  mov     rdx, [rsp+330h+lpFileName]; unsigned __int16 *
0x1800a5e75  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800a5e7c  call    ?WcsDup@CHeap@@QEAAPEAGPEBG@Z; CHeap::WcsDup(ushort const *)
0x1800a5e81  mov     [rbx+180h], rax
0x1800a5e88  test    rax, rax
0x1800a5e8b  jnz     short loc_1800A5ED6
0x1800a5e8d  mov     esi, 8007000Eh
0x1800a5e92  lea     rcx, [rbp+230h+var_2A0]; this
0x1800a5e96  call    ??1CQuickStringTBase@@MEAA@XZ; CQuickStringTBase::~CQuickStringTBase(void)
0x1800a5e9b  mov     eax, esi
0x1800a5e9d  mov     rcx, [rbp+230h+var_70]
0x1800a5ea4  xor     rcx, rsp; StackCookie
0x1800a5ea7  call    __security_check_cookie
0x1800a5eac  lea     r11, [rsp+330h+var_30]
0x1800a5eb4  mov     rbx, [r11+58h]
0x1800a5eb8  movaps  xmm6, xmmword ptr [r11-10h]
0x1800a5ebd  movaps  xmm7, xmmword ptr [r11-20h]
0x1800a5ec2  movaps  xmm8, xmmword ptr [r11-30h]
0x1800a5ec7  mov     rsp, r11
0x1800a5eca  pop     r15
0x1800a5ecc  pop     r14
0x1800a5ece  pop     r13
0x1800a5ed0  pop     r12
0x1800a5ed2  pop     rdi
0x1800a5ed3  pop     rsi
0x1800a5ed4  pop     rbp
0x1800a5ed5  retn
0x1800a5ed6  mov     rcx, rax; unsigned __int16 *
0x1800a5ed9  call    ?wcsrchr@@YAPEAGPEAGG@Z; wcsrchr(ushort *,ushort)
0x1800a5ede  mov     r14, rax
0x1800a5ee1  test    rax, rax
0x1800a5ee4  jz      short loc_1800A5F13
0x1800a5ee6  lea     rdx, aLocal; "Local\\"
0x1800a5eed  lea     rcx, [rbp+230h+var_2A0]
0x1800a5ef1  call    ?Append@?$CQuickStringW@$0BAE@@@QEAAJQEBG@Z; CQuickStringW<260>::Append(ushort const * const)
0x1800a5ef6  lea     rdx, [r14+2]
0x1800a5efa  lea     rcx, [rbp+230h+var_2A0]
0x1800a5efe  call    ?Append@?$CQuickStringW@$0BAE@@@QEAAJQEBG@Z; CQuickStringW<260>::Append(ushort const * const)
0x1800a5f03  mov     rdx, [rbp+230h+var_298]; unsigned __int16 *
0x1800a5f07  call    ?SpCreateMutex@@YAPEAXHPEBGK@Z; SpCreateMutex(int,ushort const *,ulong)
0x1800a5f0c  mov     [rbx+188h], rax
0x1800a5f13  cmp     [rbx+188h], r13
0x1800a5f1a  jz      loc_1800A5DEE
0x1800a5f20  mov     rdx, [rbx+190h]; void *
0x1800a5f27  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800a5f2e  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800a5f33  mov     [rbx+190h], r13
0x1800a5f3a  mov     rax, [rbp+230h+var_2B0]
0x1800a5f3e  test    rax, rax
0x1800a5f41  jz      short loc_1800A5FBB
0x1800a5f43  mov     rdx, rax; unsigned __int16 *
0x1800a5f46  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800a5f4d  call    ?WcsDup@CHeap@@QEAAPEAGPEBG@Z; CHeap::WcsDup(ushort const *)
0x1800a5f52  mov     [rbx+190h], rax
0x1800a5f59  test    rax, rax
0x1800a5f5c  jz      loc_1800A5E8D
0x1800a5f62  mov     rcx, rax; unsigned __int16 *
0x1800a5f65  call    ?wcsrchr@@YAPEAGPEAGG@Z; wcsrchr(ushort *,ushort)
0x1800a5f6a  mov     r14, rax
0x1800a5f6d  test    rax, rax
0x1800a5f70  jz      short loc_1800A5FAE
0x1800a5f72  and     [rbp+230h+var_290], 80000000h
0x1800a5f79  mov     rcx, [rbp+230h+var_298]
0x1800a5f7d  mov     [rcx], r13w
0x1800a5f81  lea     rdx, aLocal; "Local\\"
0x1800a5f88  lea     rcx, [rbp+230h+var_2A0]
0x1800a5f8c  call    ?Append@?$CQuickStringW@$0BAE@@@QEAAJQEBG@Z; CQuickStringW<260>::Append(ushort const * const)
0x1800a5f91  lea     rdx, [r14+2]
0x1800a5f95  lea     rcx, [rbp+230h+var_2A0]
0x1800a5f99  call    ?Append@?$CQuickStringW@$0BAE@@@QEAAJQEBG@Z; CQuickStringW<260>::Append(ushort const * const)
0x1800a5f9e  mov     rdx, [rbp+230h+var_298]; unsigned __int16 *
0x1800a5fa2  call    ?SpCreateMutex@@YAPEAXHPEBGK@Z; SpCreateMutex(int,ushort const *,ulong)
0x1800a5fa7  mov     [rbx+198h], rax
0x1800a5fae  cmp     [rbx+198h], r13
0x1800a5fb5  jz      loc_1800A5DEE
0x1800a5fbb  mov     [rbx+1C8h], r13
0x1800a5fc2  mov     eax, [rbx+3B8h]
0x1800a5fc8  test    eax, eax
0x1800a5fca  jz      short loc_1800A5FDC
0x1800a5fcc  mov     [rbx+1C8h], rdi
0x1800a5fd3  imul    eax, [rsp+330h+var_2C0]
0x1800a5fd8  lea     rdi, [rdi+rax*4]
0x1800a5fdc  mov     [rbx+1C0h], r13
0x1800a5fe3  mov     eax, [rbx+3B0h]
0x1800a5fe9  test    eax, eax
0x1800a5feb  jz      short loc_1800A5FFF
0x1800a5fed  mov     [rbx+1C0h], rdi
  ... truncated ...
```
