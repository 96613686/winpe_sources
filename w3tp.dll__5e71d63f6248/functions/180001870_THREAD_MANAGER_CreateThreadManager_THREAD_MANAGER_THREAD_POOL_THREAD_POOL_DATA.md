# THREAD_MANAGER::CreateThreadManager(THREAD_MANAGER * *,THREAD_POOL *,THREAD_POOL_DATA *)

- ea: `0x180001870`
- end: `0x180001a91`
- name: `?CreateThreadManager@THREAD_MANAGER@@SAJPEAPEAV1@PEAVTHREAD_POOL@@PEAVTHREAD_POOL_DATA@@@Z`
- size: `545`
- prototype: `__int64 __fastcall(struct THREAD_MANAGER **, struct THREAD_POOL *, struct THREAD_POOL_DATA *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800017a0`

## callees

- `0x180001870`
- `0x180001f4c`
- `0x180001f8c`
- `0x180002954`
- `0x180002f8c`

## import_xrefs

- `api-ms-win-core-systemtopology-l1-1-0!GetNumaHighestNodeNumber` at `0x180001979`
- `api-ms-win-core-systemtopology-l1-1-0!GetNumaHighestNodeNumber` at `0x180001979`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000192a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000192a`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180001a0e`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x180001a0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001996`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001a2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001996`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001a2c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800019af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001a3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800019af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001a3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a18`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessAffinityMask` at `0x18000193d`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessAffinityMask` at `0x18000193d`

## pseudocode

```c
__int64 __fastcall THREAD_MANAGER::CreateThreadManager(
        struct THREAD_MANAGER **a1,
        struct THREAD_POOL *a2,
        struct THREAD_POOL_DATA *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // r14
  HANDLE CurrentProcess; // rax
  __int64 v9; // rax
  int v10; // edi
  HANDLE ProcessHeap; // rax
  LPVOID v12; // rax
  signed int LastError; // eax
  unsigned int v14; // edi
  __int64 result; // rax
  int v16; // esi
  SIZE_T v17; // rdi
  HANDLE v18; // rax
  LPVOID v19; // rax
  ULONG_PTR SystemAffinityMask; // [rsp+50h] [rbp+8h] BYREF
  ULONG_PTR ProcessAffinityMask; // [rsp+68h] [rbp+20h] BYREF

  ProcessAffinityMask = 0;
  SystemAffinityMask = 0;
  if ( !a1 || !a2 || !a3 )
    return 2147942487LL;
  v6 = operator new(0xC0u);
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  *(_DWORD *)v6 = 1312902484;
  v6[6] = 0;
  v6[7] = 0;
  v6[8] = 0;
  *(_QWORD *)((char *)v6 + 76) = 0;
  v6[11] = 0;
  v6[12] = 0;
  v6[13] = a2;
  v6[14] = a3;
  v6[17] = 0;
  *((_DWORD *)v6 + 36) = 0;
  v6[19] = 0;
  *((_DWORD *)v6 + 40) = 0;
  v6[21] = 0;
  v6[22] = 0;
  *((_DWORD *)v6 + 46) = 0;
  v6[16] = 0;
  v6[15] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !GetProcessAffinityMask(CurrentProcess, &ProcessAffinityMask, &SystemAffinityMask)
    || ProcessAffinityMask != SystemAffinityMask
    || (v9 = v7[14], *(_DWORD *)(v9 + 92) != 1)
    || *(_DWORD *)(v9 + 88)
    || !GetNumaHighestNodeNumber((PULONG)v7 + 40)
    || (v10 = *((_DWORD *)v7 + 40)) == 0 )
  {
    v16 = 0;
    goto LABEL_22;
  }
  ProcessHeap = GetProcessHeap();
  v12 = HeapAlloc(ProcessHeap, 8u, 24LL * (unsigned int)(v10 + 1));
  v7[19] = v12;
  if ( !v12 )
  {
    LastError = GetLastError();
    v14 = LastError;
LABEL_13:
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_15;
  }
  v16 = 1;
  if ( !InitializeProcThreadAttributeList(0, 1u, 0, v7 + 22) )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError != 122 )
      goto LABEL_13;
  }
  v17 = v7[22];
  v18 = GetProcessHeap();
  v19 = HeapAlloc(v18, 8u, v17);
  v7[21] = v19;
  if ( v19 )
  {
LABEL_22:
    *((_DWORD *)v7 + 36) = v16;
    result = THREAD_MANAGER::Initialize((THREAD_MANAGER *)v7);
    v14 = result;
    if ( (int)result >= 0 )
    {
      *a1 = (struct THREAD_MANAGER *)v7;
      return result;
    }
    goto LABEL_15;
  }
  v14 = -2147024882;
LABEL_15:
  THREAD_MANAGER::~THREAD_MANAGER((THREAD_MANAGER *)v7);
  operator delete(v7);
  return v14;
}

```

## disassembly

```asm
0x180001870  push    rbx
0x180001872  push    rbp
0x180001873  push    rsi
0x180001874  push    rdi
0x180001875  sub     rsp, 28h
0x180001879  xor     ebp, ebp
0x18000187b  mov     rdi, r8
0x18000187e  mov     [rsp+48h+ProcessAffinityMask], rbp
0x180001883  mov     rsi, rdx
0x180001886  mov     [rsp+48h+SystemAffinityMask], rbp
0x18000188b  mov     rbx, rcx
0x18000188e  test    rcx, rcx
0x180001891  jz      loc_180001A83
0x180001897  test    rdx, rdx
0x18000189a  jz      loc_180001A83
0x1800018a0  test    r8, r8
0x1800018a3  jz      loc_180001A83
0x1800018a9  mov     ecx, 0C0h; Size
0x1800018ae  mov     [rsp+48h+arg_8], r14
0x1800018b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800018b8  mov     r14, rax
0x1800018bb  test    rax, rax
0x1800018be  jz      loc_180001A79
0x1800018c4  mov     dword ptr [rax], 4E414D54h
0x1800018ca  mov     [rax+30h], rbp
0x1800018ce  mov     [rax+38h], rbp
0x1800018d2  mov     [rax+40h], rbp
0x1800018d6  mov     [rax+4Ch], rbp
0x1800018da  mov     [rax+58h], rbp
0x1800018de  mov     [rax+60h], rbp
0x1800018e2  mov     [rax+68h], rsi
0x1800018e6  mov     [rax+70h], rdi
0x1800018ea  mov     [rax+88h], rbp
0x1800018f1  mov     [rax+90h], ebp
0x1800018f7  mov     [rax+98h], rbp
0x1800018fe  mov     [rax+0A0h], ebp
0x180001904  mov     [rax+0A8h], rbp
0x18000190b  mov     [rax+0B0h], rbp
0x180001912  mov     [rax+0B8h], ebp
0x180001918  xor     eax, eax
0x18000191a  mov     [r14+80h], rax
0x180001921  mov     [r14+78h], rax
0x180001925  mov     [rsp+48h+var_28], r15
0x18000192a  call    cs:__imp_GetCurrentProcess
0x180001930  mov     rcx, rax; hProcess
0x180001933  lea     r8, [rsp+48h+SystemAffinityMask]; lpSystemAffinityMask
0x180001938  lea     rdx, [rsp+48h+ProcessAffinityMask]; lpProcessAffinityMask
0x18000193d  call    cs:__imp_GetProcessAffinityMask
0x180001943  test    eax, eax
0x180001945  jz      loc_180001A56
0x18000194b  mov     rax, [rsp+48h+SystemAffinityMask]
0x180001950  cmp     [rsp+48h+ProcessAffinityMask], rax
0x180001955  jnz     loc_180001A56
0x18000195b  mov     rax, [r14+70h]
0x18000195f  cmp     dword ptr [rax+5Ch], 1
0x180001963  jnz     loc_180001A56
0x180001969  cmp     [rax+58h], ebp
0x18000196c  jnz     loc_180001A56
0x180001972  lea     rcx, [r14+0A0h]; HighestNodeNumber
0x180001979  call    cs:__imp_GetNumaHighestNodeNumber
0x18000197f  test    eax, eax
0x180001981  jz      loc_180001A56
0x180001987  mov     edi, [r14+0A0h]
0x18000198e  test    edi, edi
0x180001990  jz      loc_180001A56
0x180001996  call    cs:__imp_GetProcessHeap
0x18000199c  lea     ecx, [rdi+1]
0x18000199f  mov     edx, 8; dwFlags
0x1800019a4  lea     r8, [rcx+rcx*2]
0x1800019a8  mov     rcx, rax; hHeap
0x1800019ab  shl     r8, 3; dwBytes
0x1800019af  call    cs:__imp_HeapAlloc
0x1800019b5  mov     [r14+98h], rax
0x1800019bc  test    rax, rax
0x1800019bf  jnz     short loc_1800019FB
0x1800019c1  call    cs:__imp_GetLastError
0x1800019c7  mov     edi, eax
0x1800019c9  test    eax, eax
0x1800019cb  jle     short loc_1800019D6
0x1800019cd  movzx   edi, ax
0x1800019d0  or      edi, 80070000h
0x1800019d6  mov     rcx, r14; this
0x1800019d9  call    ??1THREAD_MANAGER@@AEAA@XZ; THREAD_MANAGER::~THREAD_MANAGER(void)
0x1800019de  mov     rcx, r14; Block
0x1800019e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800019e6  mov     eax, edi
0x1800019e8  mov     r15, [rsp+48h+var_28]
0x1800019ed  mov     r14, [rsp+48h+arg_8]
0x1800019f2  add     rsp, 28h
0x1800019f6  pop     rdi
0x1800019f7  pop     rsi
0x1800019f8  pop     rbp
0x1800019f9  pop     rbx
0x1800019fa  retn
0x1800019fb  mov     esi, 1
0x180001a00  lea     r9, [r14+0B0h]; lpSize
0x180001a07  mov     edx, esi; dwAttributeCount
0x180001a09  xor     r8d, r8d; dwFlags
0x180001a0c  xor     ecx, ecx; lpAttributeList
0x180001a0e  call    cs:__imp_InitializeProcThreadAttributeList
0x180001a14  test    eax, eax
0x180001a16  jnz     short loc_180001A25
0x180001a18  call    cs:__imp_GetLastError
0x180001a1e  mov     edi, eax
0x180001a20  cmp     eax, 7Ah ; 'z'
0x180001a23  jnz     short loc_1800019C9
0x180001a25  mov     rdi, [r14+0B0h]
0x180001a2c  call    cs:__imp_GetProcessHeap
0x180001a32  mov     r8, rdi; dwBytes
0x180001a35  mov     edx, 8; dwFlags
0x180001a3a  mov     rcx, rax; hHeap
0x180001a3d  call    cs:__imp_HeapAlloc
0x180001a43  mov     [r14+0A8h], rax
0x180001a4a  test    rax, rax
0x180001a4d  jnz     short loc_180001A58
0x180001a4f  mov     edi, 8007000Eh
0x180001a54  jmp     short loc_1800019D6
0x180001a56  mov     esi, ebp
0x180001a58  mov     rcx, r14; this
0x180001a5b  mov     [r14+90h], esi
0x180001a62  call    ?Initialize@THREAD_MANAGER@@AEAAJXZ; THREAD_MANAGER::Initialize(void)
0x180001a67  mov     edi, eax
0x180001a69  test    eax, eax
0x180001a6b  js      loc_1800019D6
0x180001a71  mov     [rbx], r14
0x180001a74  jmp     loc_1800019E8
0x180001a79  mov     eax, 8007000Eh
0x180001a7e  jmp     loc_1800019ED
0x180001a83  mov     eax, 80070057h
0x180001a88  add     rsp, 28h
0x180001a8c  pop     rdi
0x180001a8d  pop     rsi
0x180001a8e  pop     rbp
0x180001a8f  pop     rbx
0x180001a90  retn
```
