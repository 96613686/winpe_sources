# CSRTopicSLM::Setup(ushort const *,CEngine *,IEngineDataFileName *,IMSASRLocaleHandler *,_RTL_CRITICAL_SECTION *,bool,bool)

- ea: `0x1800999d8`
- end: `0x18009a0ea`
- name: `?Setup@CSRTopicSLM@@QEAAJPEBGPEAVCEngine@@PEAVIEngineDataFileName@@PEAUIMSASRLocaleHandler@@PEAU_RTL_CRITICAL_SECTION@@_N5@Z`
- size: `1810`
- prototype: `__int64 __usercall@<rax>(CSRTopicSLM *__hidden this@<rcx>, const unsigned __int16 *Src@<rdx>, struct CEngine *@<r8>, struct IEngineDataFileName *@<r9>, struct IMSASRLocaleHandler *, struct _RTL_CRITICAL_SECTION *, bool, bool)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000761c`
- `0x18000dd54`

## callees

- `0x180002470`
- `0x1800034b0`
- `0x1800034d4`
- `0x1800034e0`
- `0x1800035b0`
- `0x1800040b8`
- `0x180004a18`
- `0x180004a80`
- `0x1800061d0`
- `0x1800062a0`
- `0x1800136ec`
- `0x18005b974`
- `0x18009812c`
- `0x180098a48`
- `0x180098c9c`
- `0x180099058`
- `0x1800996c8`
- `0x1800999d8`
- `0x18009b218`
- `0x18009e94c`
- `0x1800a11f8`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180099b25`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180099b25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a0a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a0a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18009a047`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18009a047`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099a3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099a3b`

## string_xrefs

- `0x180099a79`: `Local\MSASR LMA Version Update`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSRTopicSLM::Setup(
        CSRTopicSLM *this,
        unsigned __int16 *Src,
        struct CEngine *a3,
        struct IEngineDataFileName *a4,
        struct IMSASRLocaleHandler *a5,
        struct _RTL_CRITICAL_SECTION *a6,
        bool a7,
        bool a8)
{
  struct TRIGRAMLM *v11; // r14
  _QWORD *v12; // r15
  __int64 v13; // rcx
  wchar_t *v14; // rcx
  errno_t FileHeader; // edi
  _QWORD *v16; // r12
  CPPT *v17; // rbx
  int *v18; // r13
  errno_t v19; // eax
  unsigned __int64 v20; // rdi
  __int64 v21; // rax
  bool v22; // cf
  SIZE_T v23; // rax
  _QWORD *v24; // rax
  int v25; // ebx
  int i; // eax
  LPVOID v27; // rcx
  void *v28; // rax
  _DWORD *v29; // r13
  CPPT *v30; // rax
  struct TRIGRAMLM *v31; // rax
  struct TRIGRAMLM *v32; // r15
  _QWORD *v33; // rax
  struct _RTL_CRITICAL_SECTION *v34; // rax
  unsigned int v35; // edx
  CMRU *v36; // rcx
  unsigned int v37; // edx
  int v39; // [rsp+50h] [rbp-A9h] BYREF
  _DWORD *v40; // [rsp+58h] [rbp-A1h] BYREF
  LPVOID v41; // [rsp+60h] [rbp-99h] BYREF
  LPVOID v42[3]; // [rsp+68h] [rbp-91h] BYREF
  _BYTE Buffer[4]; // [rsp+80h] [rbp-79h] BYREF
  int v44; // [rsp+84h] [rbp-75h]

  v40 = a3;
  v41 = 0;
  v42[0] = 0;
  memset_0(Buffer, 0, 0x68u);
  v11 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
  v12 = (_QWORD *)((char *)this + 88);
  CSpDynamicString::operator=((CSRTopicSLM *)((char *)this + 88), Src);
  *((_QWORD *)this + 2) = a4;
  *((_QWORD *)this + 3) = a5;
  (*(void (__fastcall **)(struct IMSASRLocaleHandler *))(*(_QWORD *)a5 + 8LL))(a5);
  *((_QWORD *)this + 4) = a6;
  *((_BYTE *)this + 248) = a7;
  *((_QWORD *)this + 1) = SpCreateMutex(v13, L"Local\\MSASR LMA Version Update");
  FileHeader = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, char *))(**((_QWORD **)this + 2) + 56LL))(
                 *((_QWORD *)this + 2),
                 *((_QWORD *)this + 11),
                 1,
                 (char *)this + 104);
  if ( FileHeader >= 0 )
  {
    FileHeader = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, char *))(**((_QWORD **)this + 2) + 56LL))(
                   *((_QWORD *)this + 2),
                   *v12,
                   3,
                   (char *)this + 112);
    if ( FileHeader >= 0 )
    {
      if ( Src && !*v12 || (v14 = (wchar_t *)*((_QWORD *)this + 13)) == 0 || !*((_QWORD *)this + 14) )
      {
        FileHeader = -2147024882;
        goto LABEL_67;
      }
      FileHeader = CSRTopicSLM::ReadFileHeader(v14, 0x68u, Buffer);
      if ( FileHeader >= 0 )
      {
        v16 = 0;
        v17 = 0;
        *((_DWORD *)this + 46) = v44;
        WaitForSingleObject(*((HANDLE *)this + 1), 0xFFFFFFFF);
        v18 = (int *)((char *)this + 188);
        FileHeader = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 2) + 8LL))(
                       *((_QWORD *)this + 2),
                       *v12,
                       (char *)this + 188);
        if ( FileHeader < 0 )
          goto LABEL_62;
        FileHeader = (***((__int64 (__fastcall ****)(_QWORD, _QWORD, __int64, _QWORD, _DWORD, char *, char *, _DWORD))this
                        + 2))(
                       *((_QWORD *)this + 2),
                       *v12,
                       2,
                       *((unsigned int *)this + 46),
                       0,
                       (char *)this + 120,
                       (char *)this + 188,
                       0);
        if ( !FileHeader )
        {
          v19 = (***((__int64 (__fastcall ****)(_QWORD, _QWORD, __int64, _QWORD, _DWORD, char *, char *, int))this + 2))(
                  *((_QWORD *)this + 2),
                  *v12,
                  3,
                  *((unsigned int *)this + 46),
                  0,
                  (char *)this + 128,
                  (char *)this + 188,
                  1);
          FileHeader = v19;
          if ( !v19 )
          {
            if ( !*((_QWORD *)this + 15) || !*((_QWORD *)this + 16) )
              goto LABEL_61;
            goto LABEL_17;
          }
          if ( v19 == -2147200966 )
          {
            CSpDynamicString::_free((LPVOID *)this + 15);
            goto LABEL_17;
          }
        }
        if ( FileHeader != -2147200966 )
          goto LABEL_62;
LABEL_17:
        if ( (unsigned int)CSRTopicSLM::IsAdaptable(this) )
        {
          FileHeader = (***((__int64 (__fastcall ****)(_QWORD, _QWORD, __int64, _QWORD, int, char *, _QWORD, _DWORD))this
                          + 2))(
                         *((_QWORD *)this + 2),
                         *v12,
                         4,
                         *((unsigned int *)this + 46),
                         1,
                         (char *)this + 136,
                         0,
                         0);
          if ( FileHeader < 0 )
            goto LABEL_62;
          if ( !*((_QWORD *)this + 17) )
            goto LABEL_61;
          v20 = (unsigned int)(*v18 + 1);
          v42[2] = (LPVOID)v20;
          v21 = 8 * v20;
          if ( !is_mul_ok(v20, 8u) )
            v21 = -1;
          v22 = __CFADD__(v21, 8);
          v23 = v21 + 8;
          if ( v22 )
            v23 = -1;
          v24 = CWinHeap::Alloc(&g_heap, v23, 0);
          v42[1] = v24;
          if ( v24 )
          {
            *v24 = v20;
            v16 = v24 + 1;
            `eh vector constructor iterator'(
              v24 + 1,
              8u,
              (unsigned int)v20,
              (void (*)(void *))CSpDynamicString::CSpDynamicString,
              (void (*)(void *))CSpDynamicString::~CSpDynamicString);
          }
          else
          {
            v16 = 0;
          }
          if ( !v16 )
            goto LABEL_61;
          v25 = 0;
          for ( i = *v18; ; i = v39 - 1 )
          {
            v39 = i;
            if ( (***((int (__fastcall ****)(_QWORD, _QWORD, __int64, _QWORD, _DWORD, LPVOID *, int *, _DWORD))this + 2))(
                   *((_QWORD *)this + 2),
                   *v12,
                   5,
                   *((unsigned int *)this + 46),
                   0,
                   &v41,
                   &v39,
                   0) < 0 )
              break;
            v27 = v41;
            v41 = 0;
            v16[v25] = v27;
            if ( !v39 )
              break;
            ++v25;
          }
        }
        v28 = CAllocOnSpecificHeapBase::operator_new(0x9A0u, *((struct CHeap **)this + 18), 1);
        if ( v28 )
        {
          v29 = v40;
          v30 = (CPPT *)CPPT::CPPT(v28, *((_QWORD *)this + 18), v40, 4);
          v17 = v30;
          if ( v30 )
          {
            FileHeader = CPPT::SetDLM(
                           v30,
                           *((const unsigned __int16 **)this + 13),
                           *((const unsigned __int16 **)this + 15));
            if ( FileHeader < 0 )
              goto LABEL_62;
            v31 = (struct TRIGRAMLM *)CAllocOnSpecificHeapBase::operator_new(0x90u, *((struct CHeap **)this + 18), 0);
            v11 = v31;
            if ( v31 )
            {
              *((_QWORD *)v31 + 4) = v17;
              *((_QWORD *)v31 + 5) = 0;
              *((_QWORD *)v31 + 6) = 0;
              *((_QWORD *)v31 + 7) = 0;
              *((_DWORD *)v31 + 16) = -536870912;
              *((_QWORD *)v31 + 9) = 0;
              *((_QWORD *)v31 + 10) = 0;
              *((_QWORD *)v31 + 11) = 0;
              *((_QWORD *)v31 + 13) = 0;
              *((_QWORD *)v31 + 14) = 0;
              *((_DWORD *)v31 + 30) = 0;
              *((_QWORD *)v31 + 12) = &CSequentialReadFile::`vftable';
              *((_QWORD *)v31 + 16) = 0;
              *((_BYTE *)v31 + 136) = 0;
              FileHeader = TRIGRAMLM::SetNGR(v31, *((const unsigned __int16 **)this + 14));
              if ( FileHeader < 0 )
                goto LABEL_62;
              if ( !*((_QWORD *)this + 16) )
              {
                v32 = v11;
                goto LABEL_42;
              }
              v32 = (struct TRIGRAMLM *)CAllocOnSpecificHeapBase::operator_new(0x90u, *((struct CHeap **)this + 18), 0);
              if ( v32 )
              {
                *((_QWORD *)v32 + 4) = v17;
                *((_QWORD *)v32 + 5) = 0;
                *((_QWORD *)v32 + 6) = 0;
                *((_QWORD *)v32 + 7) = 0;
                *((_DWORD *)v32 + 16) = -536870912;
                *((_QWORD *)v32 + 9) = 0;
                *((_QWORD *)v32 + 10) = 0;
                *((_QWORD *)v32 + 11) = 0;
                *((_QWORD *)v32 + 13) = 0;
                *((_QWORD *)v32 + 14) = 0;
                *((_DWORD *)v32 + 30) = 0;
                *((_QWORD *)v32 + 12) = &CSequentialReadFile::`vftable';
                *((_QWORD *)v32 + 16) = 0;
                *((_BYTE *)v32 + 136) = 0;
                FileHeader = TRIGRAMLM::SetNGR(v32, *((const unsigned __int16 **)this + 16));
                if ( FileHeader >= 0 )
                {
                  *((_QWORD *)v32 + 5) = v11;
LABEL_42:
                  *((_BYTE *)this + 196) = a8;
                  *((_QWORD *)this + 19) = v17;
                  v17 = 0;
                  *((_QWORD *)this + 20) = v32;
                  v11 = 0;
                  if ( *((_QWORD *)this + 17) && (unsigned int)CSRTopicSLM::IsAdaptable(this) )
                  {
                    v33 = CAllocOnSpecificHeapBase::operator_new(0x1A8u, *((struct CHeap **)this + 18), 0);
                    if ( v33 )
                    {
                      v33[7] = &CLmHash<HashEntryTypeWord,HashBucketBase>::`vftable';
                      v33[10] = 0;
                      v33[8] = 0;
                      v33[9] = 0;
                      v33[11] = 0;
                      v33[12] = &CLmHash<HashEntryTypeTrigram,HashBucketBase>::`vftable';
                      v33[15] = 0;
                      v33[13] = 0;
                      v33[14] = 0;
                      v33[16] = 0;
                      v33[25] = 0;
                    }
                    else
                    {
                      v33 = 0;
                    }
                    *((_QWORD *)this + 21) = v33;
                    if ( v33 )
                    {
                      v40 = 0;
                      CSpDynamicString::operator=((CSpDynamicString *)&v40, (CSRTopicSLM *)((char *)this + 136));
                      CSpDynamicString::_free((LPVOID *)&v40);
                    }
                    else
                    {
                      *((_QWORD *)this + 21) = 0;
                    }
                  }
                  v34 = (struct _RTL_CRITICAL_SECTION *)CAllocOnSpecificHeapBase::operator_new(
                                                          0x70u,
                                                          *((struct CHeap **)this + 18),
                                                          0);
                  if ( v34 )
                  {
                    v34[1].LockSemaphore = 0;
                    v34[1].SpinCount = 0;
                    v34[2].DebugInfo = 0;
                    *(_QWORD *)&v34[2].LockCount = 0;
                    v34[2].OwningThread = 0;
                    LOBYTE(v34[1].DebugInfo) = 0;
                  }
                  *((_QWORD *)this + 22) = v34;
                  if ( v34 )
                    FileHeader = CMRU::Init(v34, v29[128]);
                  v36 = (CMRU *)*((_QWORD *)this + 22);
                  if ( v36 )
                  {
                    if ( FileHeader >= 0 )
                    {
LABEL_58:
                      FileHeader = 0;
                      *((_BYTE *)this + 197) = 1;
                      goto LABEL_62;
                    }
                    CMRU::`scalar deleting destructor'(v36, v35);
                  }
                  *((_QWORD *)this + 22) = 0;
                  goto LABEL_58;
                }
LABEL_62:
                ReleaseMutex(*((HANDLE *)this + 1));
                if ( v17 )
                  CPPT::`scalar deleting destructor'(v17, v37);
                if ( v16 )
                {
                  `eh vector destructor iterator'(
                    v16,
                    8u,
                    *(v16 - 1),
                    (void (*)(void *))CSpDynamicString::~CSpDynamicString);
                  operator delete(v16 - 1, 8LL * *(v16 - 1) + 8);
                }
                goto LABEL_67;
              }
            }
            else
            {
              v11 = 0;
            }
          }
        }
        else
        {
          v17 = 0;
        }
LABEL_61:
        FileHeader = -2147024882;
        goto LABEL_62;
      }
    }
  }
LABEL_67:
  CSRTopicSLM::DeleteTrigramLMChain((CSRTopicSLM *)v14, v11);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 5);
  CSpDynamicString::_free(v42);
  CSpDynamicString::_free(&v41);
  return (unsigned int)FileHeader;
}

```

## disassembly

```asm
0x1800999d8  mov     [rsp-8+arg_18], rbx
0x1800999dd  push    rbp
0x1800999de  push    rsi
0x1800999df  push    rdi
0x1800999e0  push    r12
0x1800999e2  push    r13
0x1800999e4  push    r14
0x1800999e6  push    r15
0x1800999e8  lea     rbp, [rsp-7]
0x1800999ed  sub     rsp, 100h
0x1800999f4  mov     rax, cs:__security_cookie
0x1800999fb  xor     rax, rsp
0x1800999fe  mov     [rbp+37h+var_40], rax
0x180099a02  mov     rbx, r9
0x180099a05  mov     [rsp+130h+var_D8], r8
0x180099a0a  mov     r12, rdx
0x180099a0d  mov     rsi, rcx
0x180099a10  mov     [rsp+130h+var_D0], 0
0x180099a19  mov     [rsp+130h+var_C8], 0
0x180099a22  xor     edx, edx; Val
0x180099a24  lea     r8d, [rdx+68h]; Size
0x180099a28  lea     rcx, [rbp+37h+Buffer]; void *
0x180099a2c  call    memset_0
0x180099a31  xor     r14d, r14d
0x180099a34  lea     rcx, [rsi+0C8h]; lpCriticalSection
0x180099a3b  call    cs:__imp_EnterCriticalSection
0x180099a41  lea     r15, [rsi+58h]
0x180099a45  mov     rdx, r12; Src
0x180099a48  mov     rcx, r15; this
0x180099a4b  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x180099a50  mov     [rsi+10h], rbx
0x180099a54  mov     rcx, [rbp+37h+arg_20]
0x180099a58  mov     [rsi+18h], rcx
0x180099a5c  mov     rax, [rcx]
0x180099a5f  mov     rax, [rax+8]
0x180099a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099a68  mov     rax, [rbp+37h+arg_28]
0x180099a6c  mov     [rsi+20h], rax
0x180099a70  mov     al, [rbp+37h+arg_30]
0x180099a73  mov     [rsi+0F8h], al
0x180099a79  lea     rdx, aLocalMsasrLmaV; "Local\\MSASR LMA Version Update"
0x180099a80  call    ?SpCreateMutex@@YAPEAXHPEBGK@Z; SpCreateMutex(int,ushort const *,ulong)
0x180099a85  mov     [rsi+8], rax
0x180099a89  mov     rcx, [rsi+10h]
0x180099a8d  mov     rax, [rcx]
0x180099a90  lea     r9, [rsi+68h]
0x180099a94  lea     r8d, [r14+1]
0x180099a98  mov     rdx, [r15]
0x180099a9b  mov     rax, [rax+38h]
0x180099a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099aa4  mov     edi, eax
0x180099aa6  test    eax, eax
0x180099aa8  js      loc_18009A096
0x180099aae  mov     rcx, [rsi+10h]
0x180099ab2  mov     rax, [rcx]
0x180099ab5  lea     r9, [rsi+70h]
0x180099ab9  lea     r8d, [r14+3]
0x180099abd  mov     rdx, [r15]
0x180099ac0  mov     rax, [rax+38h]
0x180099ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099ac9  mov     edi, eax
0x180099acb  test    eax, eax
0x180099acd  js      loc_18009A096
0x180099ad3  test    r12, r12
0x180099ad6  jz      short loc_180099AE1
0x180099ad8  cmp     [r15], r14
0x180099adb  jz      loc_18009A091
0x180099ae1  mov     rcx, [rsi+68h]; FileName
0x180099ae5  test    rcx, rcx
0x180099ae8  jz      loc_18009A091
0x180099aee  cmp     [rsi+70h], r14
0x180099af2  jz      loc_18009A091
0x180099af8  lea     r8, [rbp+37h+Buffer]; Buffer
0x180099afc  mov     edx, 68h ; 'h'; ElementCount
0x180099b01  call    ?ReadFileHeader@CSRTopicSLM@@SAJPEBG_KPEAX@Z; CSRTopicSLM::ReadFileHeader(ushort const *,unsigned __int64,void *)
0x180099b06  mov     edi, eax
0x180099b08  test    eax, eax
0x180099b0a  js      loc_18009A096
0x180099b10  xor     r12d, r12d
0x180099b13  xor     ebx, ebx
0x180099b15  mov     eax, [rbp+37h+var_AC]
0x180099b18  mov     [rsi+0B8h], eax
0x180099b1e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180099b21  mov     rcx, [rsi+8]; hHandle
0x180099b25  call    cs:__imp_WaitForSingleObject
0x180099b2b  mov     rcx, [rsi+10h]
0x180099b2f  lea     r13, [rsi+0BCh]
0x180099b36  mov     rax, [rcx]
0x180099b39  mov     r8, r13
0x180099b3c  mov     rdx, [r15]
0x180099b3f  mov     rax, [rax+8]
0x180099b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099b48  mov     edi, eax
0x180099b4a  test    eax, eax
0x180099b4c  js      loc_18009A043
0x180099b52  mov     rcx, [rsi+10h]
0x180099b56  lea     rdx, [rsi+78h]
0x180099b5a  mov     rax, [rcx]
0x180099b5d  mov     [rsp+130h+var_F8], ebx
0x180099b61  mov     [rsp+130h+var_100], r13
0x180099b66  mov     [rsp+130h+var_108], rdx
0x180099b6b  mov     dword ptr [rsp+130h+var_110], ebx
0x180099b6f  mov     r9d, [rsi+0B8h]
0x180099b76  lea     r8d, [r12+2]
0x180099b7b  mov     rdx, [r15]
0x180099b7e  mov     rax, [rax]
0x180099b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099b86  mov     edi, eax
0x180099b88  test    eax, eax
0x180099b8a  jnz     short loc_180099BF7
0x180099b8c  mov     rcx, [rsi+10h]
0x180099b90  lea     rdx, [rsi+80h]
0x180099b97  mov     rax, [rcx]
0x180099b9a  mov     [rsp+130h+var_F8], 1
0x180099ba2  mov     [rsp+130h+var_100], r13
0x180099ba7  mov     [rsp+130h+var_108], rdx
0x180099bac  mov     dword ptr [rsp+130h+var_110], ebx
0x180099bb0  mov     r9d, [rsi+0B8h]
0x180099bb7  lea     r8d, [r12+3]
0x180099bbc  mov     rdx, [r15]
0x180099bbf  mov     rax, [rax]
0x180099bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099bc7  mov     edi, eax
0x180099bc9  test    eax, eax
0x180099bcb  jnz     short loc_180099BE5
0x180099bcd  cmp     [rsi+78h], rbx
0x180099bd1  jz      loc_18009A03E
0x180099bd7  cmp     [rsi+80h], rbx
0x180099bde  jnz     short loc_180099C03
0x180099be0  jmp     loc_18009A03E
0x180099be5  cmp     eax, 8004503Ah
0x180099bea  jnz     short loc_180099BF7
0x180099bec  lea     rcx, [rsi+78h]; this
0x180099bf0  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180099bf5  jmp     short loc_180099C03
0x180099bf7  cmp     edi, 8004503Ah
0x180099bfd  jnz     loc_18009A043
0x180099c03  mov     rcx, rsi; this
0x180099c06  call    ?IsAdaptable@CSRTopicSLM@@QEAAHXZ; CSRTopicSLM::IsAdaptable(void)
0x180099c0b  test    eax, eax
0x180099c0d  jz      loc_180099D54
0x180099c13  mov     rcx, [rsi+10h]
0x180099c17  lea     rdx, [rsi+88h]
0x180099c1e  mov     rax, [rcx]
0x180099c21  mov     [rsp+130h+var_F8], ebx
0x180099c25  mov     [rsp+130h+var_100], rbx
0x180099c2a  mov     [rsp+130h+var_108], rdx
0x180099c2f  mov     dword ptr [rsp+130h+var_110], 1
0x180099c37  mov     r9d, [rsi+0B8h]
0x180099c3e  mov     r8d, 4
0x180099c44  mov     rdx, [r15]
0x180099c47  mov     rax, [rax]
0x180099c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099c4f  mov     edi, eax
0x180099c51  test    eax, eax
0x180099c53  js      loc_18009A043
0x180099c59  cmp     [rsi+88h], rbx
0x180099c60  jz      loc_18009A03E
0x180099c66  mov     edi, [r13+0]
0x180099c6a  inc     edi
0x180099c6c  mov     [rsp+130h+var_B8], rdi
0x180099c71  mov     eax, 8
0x180099c76  mul     rdi
0x180099c79  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180099c80  cmovb   rax, rcx
0x180099c84  add     rax, 8
0x180099c88  cmovb   rax, rcx
0x180099c8c  xor     r8d, r8d; bool
0x180099c8f  mov     rdx, rax; unsigned __int64
0x180099c92  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180099c99  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x180099c9e  mov     [rsp+130h+var_C0], rax
0x180099ca3  test    rax, rax
0x180099ca6  jz      short loc_180099CD4
0x180099ca8  mov     [rax], rdi
0x180099cab  lea     r12, [rax+8]
0x180099caf  lea     rax, ??1CSpDynamicString@@QEAA@XZ; CSpDynamicString::~CSpDynamicString(void)
0x180099cb6  mov     [rsp+130h+var_110], rax; void (*)(void *)
0x180099cbb  lea     r9, ??0CSpDynamicString@@QEAA@XZ; void (*)(void *)
0x180099cc2  mov     r8d, edi; unsigned __int64
0x180099cc5  mov     edx, 8; unsigned __int64
0x180099cca  mov     rcx, r12; void *
0x180099ccd  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180099cd2  jmp     short loc_180099CD7
0x180099cd4  xor     r12d, r12d
0x180099cd7  test    r12, r12
0x180099cda  jz      loc_18009A03E
0x180099ce0  xor     ebx, ebx
0x180099ce2  mov     eax, [r13+0]
0x180099ce6  mov     [rsp+130h+var_E0], eax
0x180099cea  mov     rcx, [rsi+10h]
0x180099cee  mov     rax, [rcx]
0x180099cf1  mov     [rsp+130h+var_F8], 0
0x180099cf9  lea     rdx, [rsp+130h+var_E0]
0x180099cfe  mov     [rsp+130h+var_100], rdx
0x180099d03  lea     rdx, [rsp+130h+var_D0]
0x180099d08  mov     [rsp+130h+var_108], rdx
0x180099d0d  mov     dword ptr [rsp+130h+var_110], 0
0x180099d15  mov     r9d, [rsi+0B8h]
0x180099d1c  mov     r8d, 5
0x180099d22  mov     rdx, [r15]
0x180099d25  mov     rax, [rax]
0x180099d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099d2d  test    eax, eax
0x180099d2f  js      short loc_180099D54
0x180099d31  mov     rcx, [rsp+130h+var_D0]
0x180099d36  mov     [rsp+130h+var_D0], 0
0x180099d3f  movsxd  rax, ebx
0x180099d42  mov     [r12+rax*8], rcx
0x180099d46  mov     eax, [rsp+130h+var_E0]
0x180099d4a  test    eax, eax
0x180099d4c  jz      short loc_180099D54
0x180099d4e  inc     ebx
0x180099d50  dec     eax
0x180099d52  jmp     short loc_180099CE6
0x180099d54  mov     r8b, 1; bool
0x180099d57  mov     rdx, [rsi+90h]; struct CHeap *
0x180099d5e  mov     ecx, 9A0h; unsigned __int64
0x180099d63  call    ?operator_new@CAllocOnSpecificHeapBase@@SAPEAX_KPEAVCHeap@@_N@Z; CAllocOnSpecificHeapBase::operator_new(unsigned __int64,CHeap *,bool)
0x180099d68  test    rax, rax
0x180099d6b  jz      loc_18009A03C
0x180099d71  mov     r9d, 4
0x180099d77  mov     r13, [rsp+130h+var_D8]
0x180099d7c  mov     r8, r13
0x180099d7f  mov     rdx, [rsi+90h]
0x180099d86  mov     rcx, rax
0x180099d89  call    ??0CPPT@@QEAA@PEAVCHeap@@PEAVCEngine@@W4GRMTYPE@@@Z; CPPT::CPPT(CHeap *,CEngine *,GRMTYPE)
0x180099d8e  mov     rbx, rax
0x180099d91  test    rax, rax
0x180099d94  jz      loc_18009A03E
0x180099d9a  mov     r8, [rsi+78h]; unsigned __int16 *
0x180099d9e  mov     rdx, [rsi+68h]; unsigned __int16 *
0x180099da2  mov     rcx, rax; this
0x180099da5  call    ?SetDLM@CPPT@@QEAAJPEBG0@Z; CPPT::SetDLM(ushort const *,ushort const *)
0x180099daa  mov     edi, eax
0x180099dac  test    eax, eax
0x180099dae  js      loc_18009A043
0x180099db4  xor     r8d, r8d; bool
0x180099db7  mov     rdx, [rsi+90h]; struct CHeap *
0x180099dbe  mov     r15d, 90h
0x180099dc4  mov     ecx, r15d; unsigned __int64
0x180099dc7  call    ?operator_new@CAllocOnSpecificHeapBase@@SAPEAX_KPEAVCHeap@@_N@Z; CAllocOnSpecificHeapBase::operator_new(unsigned __int64,CHeap *,bool)
0x180099dcc  mov     r14, rax
0x180099dcf  test    rax, rax
0x180099dd2  jz      loc_18009A037
0x180099dd8  mov     [rax+20h], rbx
0x180099ddc  mov     qword ptr [rax+28h], 0
0x180099de4  mov     qword ptr [rax+30h], 0
0x180099dec  mov     qword ptr [rax+38h], 0
0x180099df4  mov     dword ptr [rax+40h], 0E0000000h
0x180099dfb  mov     qword ptr [rax+48h], 0
0x180099e03  mov     qword ptr [rax+50h], 0
0x180099e0b  mov     qword ptr [rax+58h], 0
0x180099e13  mov     qword ptr [rax+68h], 0
0x180099e1b  mov     qword ptr [rax+70h], 0
0x180099e23  mov     dword ptr [rax+78h], 0
0x180099e2a  lea     rax, ??_7CSequentialReadFile@@6B@; const CSequentialReadFile::`vftable'
0x180099e31  mov     [r14+60h], rax
0x180099e35  mov     qword ptr [r14+80h], 0
0x180099e40  mov     byte ptr [r14+88h], 0
0x180099e48  mov     rdx, [rsi+70h]; unsigned __int16 *
0x180099e4c  mov     rcx, r14; this
0x180099e4f  call    ?SetNGR@TRIGRAMLM@@QEAAJPEBG@Z; TRIGRAMLM::SetNGR(ushort const *)
0x180099e54  mov     edi, eax
0x180099e56  test    eax, eax
0x180099e58  js      loc_18009A043
0x180099e5e  cmp     qword ptr [rsi+80h], 0
0x180099e66  jz      loc_180099EF4
0x180099e6c  xor     r8d, r8d; bool
0x180099e6f  mov     rdx, [rsi+90h]; struct CHeap *
0x180099e76  mov     ecx, r15d; unsigned __int64
0x180099e79  call    ?operator_new@CAllocOnSpecificHeapBase@@SAPEAX_KPEAVCHeap@@_N@Z; CAllocOnSpecificHeapBase::operator_new(unsigned __int64,CHeap *,bool)
0x180099e7e  mov     r15, rax
0x180099e81  xor     eax, eax
0x180099e83  test    r15, r15
0x180099e86  jz      loc_18009A03E
0x180099e8c  mov     [r15+20h], rbx
0x180099e90  mov     [r15+28h], rax
0x180099e94  mov     [r15+30h], rax
0x180099e98  mov     [r15+38h], rax
0x180099e9c  mov     dword ptr [r15+40h], 0E0000000h
0x180099ea4  mov     [r15+48h], rax
0x180099ea8  mov     [r15+50h], rax
0x180099eac  mov     [r15+58h], rax
0x180099eb0  mov     [r15+68h], rax
0x180099eb4  mov     [r15+70h], rax
0x180099eb8  mov     [r15+78h], eax
0x180099ebc  lea     rcx, ??_7CSequentialReadFile@@6B@; const CSequentialReadFile::`vftable'
0x180099ec3  mov     [r15+60h], rcx
0x180099ec7  mov     [r15+80h], rax
0x180099ece  mov     [r15+88h], al
0x180099ed5  mov     rdx, [rsi+80h]; unsigned __int16 *
0x180099edc  mov     rcx, r15; this
0x180099edf  call    ?SetNGR@TRIGRAMLM@@QEAAJPEBG@Z; TRIGRAMLM::SetNGR(ushort const *)
0x180099ee4  mov     edi, eax
0x180099ee6  test    eax, eax
0x180099ee8  js      loc_18009A043
0x180099eee  mov     [r15+28h], r14
0x180099ef2  jmp     short loc_180099EF7
0x180099ef4  mov     r15, r14
  ... truncated ...
```
