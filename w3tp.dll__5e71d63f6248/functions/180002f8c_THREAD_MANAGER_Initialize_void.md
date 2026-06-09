# THREAD_MANAGER::Initialize(void)

- ea: `0x180002f8c`
- end: `0x1800031c7`
- name: `?Initialize@THREAD_MANAGER@@AEAAJXZ`
- size: `571`
- prototype: `__int64 __fastcall(THREAD_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001870`

## callees

- `0x180001f4c`
- `0x180002ddc`
- `0x180002f8c`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-systemtopology-l1-1-0!GetNumaNodeProcessorMaskEx` at `0x18000308a`
- `api-ms-win-core-systemtopology-l1-1-0!GetNumaNodeProcessorMaskEx` at `0x18000308a`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18000317f`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18000317f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000314b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003196`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000314b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003196`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003159`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800031a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003159`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800031a4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800030db`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800030db`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002fd1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002fee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002fd1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002fee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180002fb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180002fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000310c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000310c`

## pseudocode

```c
__int64 __fastcall THREAD_MANAGER::Initialize(THREAD_MANAGER *this)
{
  HANDLE *v2; // rbx
  HANDLE EventW; // rax
  HANDLE v4; // rax
  AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *v5; // rax
  AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *v6; // rcx
  signed int v7; // edi
  USHORT i; // di
  __int64 v9; // r14
  __int64 v10; // rdx
  unsigned int j; // ecx
  signed int LastError; // eax
  void *v13; // rcx
  void (__fastcall ***v14)(_QWORD, __int64); // rcx
  void *v15; // rbx
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v17; // rcx
  void *v18; // rbx
  HANDLE v19; // rax

  v2 = (HANDLE *)((char *)this + 88);
  if ( !GetModuleFileNameW(g_hModuleW3TP, &g_szModuleName, 0x104u)
    || (EventW = CreateEventW(0, 0, 0, 0), (*v2 = EventW) == 0)
    || (v4 = CreateEventW(0, 1, 0, 0), (*((_QWORD *)this + 12) = v4) == 0) )
  {
LABEL_25:
    v7 = -2147467259;
    goto LABEL_26;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 14) + 88LL) != 1 )
  {
LABEL_11:
    if ( *((_DWORD *)this + 36) )
    {
      for ( i = 0; (unsigned int)i <= *((_DWORD *)this + 40); ++i )
      {
        v9 = *((_QWORD *)this + 19) + 24LL * i;
        if ( !GetNumaNodeProcessorMaskEx(i, (PGROUP_AFFINITY)v9) )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          if ( v7 >= 0 )
            return (unsigned int)v7;
          goto LABEL_26;
        }
        v10 = *(_QWORD *)v9;
        for ( j = 0; j < 0x40; ++j )
        {
          if ( _bittest64(&v10, j) )
            ++*(_BYTE *)(v9 + 16);
        }
      }
    }
    if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 8), 0x80000000) )
      return 0;
    goto LABEL_25;
  }
  v5 = (AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *)operator new(0x18u);
  v6 = v5;
  if ( v5 )
  {
    *(_QWORD *)v5 = &AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::`vftable';
    *((_WORD *)v5 + 4) = 0;
    *((_DWORD *)v5 + 3) = 0;
    *((_QWORD *)v5 + 2) = 0;
  }
  else
  {
    v6 = 0;
  }
  *((_QWORD *)this + 17) = v6;
  if ( v6 )
  {
    v7 = AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::Initialize(v6);
    if ( v7 < 0 )
      goto LABEL_26;
    goto LABEL_11;
  }
  v7 = -2147024888;
LABEL_26:
  if ( *v2 )
  {
    CloseHandle(*v2);
    *v2 = 0;
  }
  v13 = (void *)*((_QWORD *)this + 12);
  if ( v13 )
  {
    CloseHandle(v13);
    *((_QWORD *)this + 12) = 0;
  }
  v14 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 17);
  if ( v14 )
  {
    (**v14)(v14, 1);
    *((_QWORD *)this + 17) = 0;
  }
  v15 = (void *)*((_QWORD *)this + 19);
  if ( v15 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v15);
    *((_QWORD *)this + 19) = 0;
  }
  v17 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)*((_QWORD *)this + 21);
  if ( v17 )
  {
    if ( *((_DWORD *)this + 46) )
    {
      DeleteProcThreadAttributeList(v17);
      *((_DWORD *)this + 46) = 0;
    }
    v18 = (void *)*((_QWORD *)this + 21);
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v18);
    *((_QWORD *)this + 21) = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002f8c  push    rbx
0x180002f8e  push    rsi
0x180002f8f  push    rdi
0x180002f90  push    r14
0x180002f92  push    r15
0x180002f94  sub     rsp, 20h
0x180002f98  mov     rsi, rcx
0x180002f9b  lea     rbx, [rcx+58h]
0x180002f9f  mov     rcx, cs:?g_hModuleW3TP@@3PEAUHINSTANCE__@@EA; hModule
0x180002fa6  lea     rdx, ?g_szModuleName@@3PAGA; lpFilename
0x180002fad  mov     r8d, 104h; nSize
0x180002fb3  call    cs:__imp_GetModuleFileNameW
0x180002fb9  mov     r15d, 1
0x180002fbf  test    eax, eax
0x180002fc1  jz      loc_1800030E9
0x180002fc7  xor     r9d, r9d; lpName
0x180002fca  xor     r8d, r8d; bInitialState
0x180002fcd  xor     edx, edx; bManualReset
0x180002fcf  xor     ecx, ecx; lpEventAttributes
0x180002fd1  call    cs:__imp_CreateEventW
0x180002fd7  mov     [rbx], rax
0x180002fda  test    rax, rax
0x180002fdd  jz      loc_1800030E9
0x180002fe3  xor     r9d, r9d; lpName
0x180002fe6  xor     r8d, r8d; bInitialState
0x180002fe9  mov     edx, r15d; bManualReset
0x180002fec  xor     ecx, ecx; lpEventAttributes
0x180002fee  call    cs:__imp_CreateEventW
0x180002ff4  mov     [rsi+60h], rax
0x180002ff8  test    rax, rax
0x180002ffb  jz      loc_1800030E9
0x180003001  mov     rax, [rsi+70h]
0x180003005  cmp     [rax+58h], r15d
0x180003009  jnz     short loc_18000305C
0x18000300b  lea     ecx, [r15+17h]; Size
0x18000300f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003014  mov     rcx, rax
0x180003017  test    rax, rax
0x18000301a  jz      short loc_180003035
0x18000301c  lea     rax, ??_7AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@6B@; const AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::`vftable'
0x180003023  mov     [rcx], rax
0x180003026  xor     eax, eax
0x180003028  mov     [rcx+8], ax
0x18000302c  mov     [rcx+0Ch], eax
0x18000302f  mov     [rcx+10h], rax
0x180003033  jmp     short loc_180003037
0x180003035  xor     ecx, ecx; this
0x180003037  mov     [rsi+88h], rcx
0x18000303e  test    rcx, rcx
0x180003041  jnz     short loc_18000304D
0x180003043  mov     edi, 80070008h
0x180003048  jmp     loc_1800030EE
0x18000304d  call    ?Initialize@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@QEAAJXZ; AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::Initialize(void)
0x180003052  mov     edi, eax
0x180003054  test    eax, eax
0x180003056  js      loc_1800030EE
0x18000305c  cmp     dword ptr [rsi+90h], 0
0x180003063  jz      short loc_1800030D2
0x180003065  xor     edi, edi
0x180003067  movzx   eax, di
0x18000306a  cmp     eax, [rsi+0A0h]
0x180003070  ja      short loc_1800030D2
0x180003072  movzx   eax, di
0x180003075  lea     rcx, [rax+rax*2]
0x180003079  mov     rax, [rsi+98h]
0x180003080  lea     r14, [rax+rcx*8]
0x180003084  movzx   ecx, di; Node
0x180003087  mov     rdx, r14; ProcessorMask
0x18000308a  call    cs:__imp_GetNumaNodeProcessorMaskEx
0x180003090  test    eax, eax
0x180003092  jz      short loc_1800030B3
0x180003094  mov     rdx, [r14]
0x180003097  xor     ecx, ecx
0x180003099  mov     eax, ecx
0x18000309b  bt      rdx, rax
0x18000309f  jnb     short loc_1800030A5
0x1800030a1  add     [r14+10h], r15b
0x1800030a5  add     ecx, r15d
0x1800030a8  cmp     ecx, 40h ; '@'
0x1800030ab  jb      short loc_180003099
0x1800030ad  add     di, r15w
0x1800030b1  jmp     short loc_180003067
0x1800030b3  call    cs:__imp_GetLastError
0x1800030b9  mov     edi, eax
0x1800030bb  test    eax, eax
0x1800030bd  jle     short loc_1800030C8
0x1800030bf  movzx   edi, ax
0x1800030c2  or      edi, 80070000h
0x1800030c8  test    edi, edi
0x1800030ca  jns     loc_1800031B9
0x1800030d0  jmp     short loc_1800030EE
0x1800030d2  lea     rcx, [rsi+8]; lpCriticalSection
0x1800030d6  mov     edx, 80000000h; dwSpinCount
0x1800030db  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800030e1  test    eax, eax
0x1800030e3  jnz     loc_1800031B7
0x1800030e9  mov     edi, 80004005h
0x1800030ee  mov     rcx, [rbx]; hObject
0x1800030f1  test    rcx, rcx
0x1800030f4  jz      short loc_180003103
0x1800030f6  call    cs:__imp_CloseHandle
0x1800030fc  mov     qword ptr [rbx], 0
0x180003103  mov     rcx, [rsi+60h]; hObject
0x180003107  test    rcx, rcx
0x18000310a  jz      short loc_18000311A
0x18000310c  call    cs:__imp_CloseHandle
0x180003112  mov     qword ptr [rsi+60h], 0
0x18000311a  mov     rcx, [rsi+88h]
0x180003121  test    rcx, rcx
0x180003124  jz      short loc_18000313F
0x180003126  mov     rax, [rcx]
0x180003129  mov     edx, r15d
0x18000312c  mov     rax, [rax]
0x18000312f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003134  mov     qword ptr [rsi+88h], 0
0x18000313f  mov     rbx, [rsi+98h]
0x180003146  test    rbx, rbx
0x180003149  jz      short loc_18000316A
0x18000314b  call    cs:__imp_GetProcessHeap
0x180003151  mov     r8, rbx; lpMem
0x180003154  xor     edx, edx; dwFlags
0x180003156  mov     rcx, rax; hHeap
0x180003159  call    cs:__imp_HeapFree
0x18000315f  mov     qword ptr [rsi+98h], 0
0x18000316a  mov     rcx, [rsi+0A8h]; lpAttributeList
0x180003171  test    rcx, rcx
0x180003174  jz      short loc_1800031B9
0x180003176  cmp     dword ptr [rsi+0B8h], 0
0x18000317d  jz      short loc_18000318F
0x18000317f  call    cs:__imp_DeleteProcThreadAttributeList
0x180003185  mov     dword ptr [rsi+0B8h], 0
0x18000318f  mov     rbx, [rsi+0A8h]
0x180003196  call    cs:__imp_GetProcessHeap
0x18000319c  mov     r8, rbx; lpMem
0x18000319f  xor     edx, edx; dwFlags
0x1800031a1  mov     rcx, rax; hHeap
0x1800031a4  call    cs:__imp_HeapFree
0x1800031aa  mov     qword ptr [rsi+0A8h], 0
0x1800031b5  jmp     short loc_1800031B9
0x1800031b7  xor     edi, edi
0x1800031b9  mov     eax, edi
0x1800031bb  add     rsp, 20h
0x1800031bf  pop     r15
0x1800031c1  pop     r14
0x1800031c3  pop     rdi
0x1800031c4  pop     rsi
0x1800031c5  pop     rbx
0x1800031c6  retn
```
