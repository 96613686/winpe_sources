# PfScDbTrimProcessPrivates

- ea: `0x180013068`
- end: `0x180013407`
- name: `PfScDbTrimProcessPrivates`
- size: `927`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180073b08`

## callees

- `0x18000c000`
- `0x180013068`
- `0x180014320`
- `0x18002341c`
- `0x18002af98`
- `0x18002c990`
- `0x18002fcb8`
- `0x1800b645a`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18001320e`
- `ntdll!NtQueryInformationThread` at `0x18001320e`
- `ntdll!RtlNtStatusToDosError` at `0x1800133ce`
- `ntdll!RtlNtStatusToDosError` at `0x1800133fa`
- `ntdll!RtlNtStatusToDosError` at `0x1800133ce`
- `ntdll!RtlNtStatusToDosError` at `0x1800133fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013391`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013391`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800131c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800131d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800131e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001321f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013249`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013266`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013367`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001337e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800131c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800131d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800131e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001321f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013249`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013266`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013367`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001337e`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800131ca`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800131ca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800131e1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180013255`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180013373`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800131e1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180013255`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180013373`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800130b1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800130b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800133ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800133ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800130e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800130e3`

## pseudocode

```c
__int64 __fastcall PfScDbTrimProcessPrivates(__int64 a1, _DWORD *a2)
{
  bool v2; // zf
  HANDLE v5; // r14
  unsigned int *v6; // rbx
  _QWORD *v7; // r15
  unsigned int v8; // ebx
  _BYTE *Next; // rax
  _BYTE *v10; // rdx
  _BYTE *v11; // rcx
  __int64 v12; // r9
  int v13; // ecx
  __int64 v14; // r8
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // r8
  __int64 v17; // rax
  HANDLE CurrentThread; // rax
  int ThreadPriority; // r13d
  HANDLE v20; // rax
  HANDLE v21; // rax
  int v22; // eax
  int v23; // edi
  HANDLE v24; // rax
  NTSTATUS v25; // eax
  HANDLE v26; // rax
  HANDLE v27; // rax
  unsigned __int64 v28; // r14
  unsigned int i; // r12d
  __int64 v30; // rdx
  __int64 v31; // rcx
  ULONG LastError; // ebx
  unsigned __int64 v33; // rax
  bool v34; // cf
  HANDLE v35; // rax
  HANDLE v36; // rax
  _BYTE *v38; // [rsp+40h] [rbp-69h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-61h]
  unsigned int *v40; // [rsp+50h] [rbp-59h]
  __int128 v41; // [rsp+58h] [rbp-51h] BYREF
  __int128 v42; // [rsp+68h] [rbp-41h]
  __int128 v43; // [rsp+78h] [rbp-31h]
  _BYTE v44[112]; // [rsp+90h] [rbp-19h] BYREF
  int ThreadInformation; // [rsp+118h] [rbp+6Fh] BYREF
  unsigned int v47; // [rsp+120h] [rbp+77h]
  int v48; // [rsp+128h] [rbp+7Fh] BYREF

  v2 = a2[4] == 2;
  v41 = 0;
  v42 = 0;
  v48 = 0;
  if ( v2 )
  {
    hObject = OpenProcess(0x1000u, 0, a2[5]);
    v5 = hObject;
    if ( hObject )
    {
      v6 = a2 + 14;
      v40 = v6;
      v7 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 16LL * *v6);
      if ( v7 )
      {
        memset_0(v44, 0, 0x40u);
        BtDbIteratorAttachToContainer(a1, v6, v44);
        v8 = 0;
        v47 = 0;
        Next = (_BYTE *)BtDbIteratorGetNext(v44);
        v38 = Next;
        if ( Next )
        {
          v10 = Next;
          v11 = Next;
          do
          {
            v12 = (unsigned __int8)v11[1];
            v13 = *((_DWORD *)v10 + 1);
            v14 = *((unsigned __int16 *)v10 + 1);
            if ( (*Next & 1) != 0 )
            {
              v33 = v14 | ((unsigned __int64)(v13 & 0x7FFFF) << 16);
              v34 = (v13 & 0x80000) != 0;
              v15 = v33 + 0xFFFF800000000LL;
              if ( !v34 )
                v15 = v33;
            }
            else
            {
              v15 = v14 | ((unsigned __int64)(v13 & 0x7F) << 16);
            }
            v16 = v12 + v15 + 1;
            if ( v15 < v16 )
            {
              do
              {
                if ( v15 << 12 <= *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 848LL) )
                {
                  v17 = 2LL * v8++;
                  v7[v17] = v15 << 12;
                }
                ++v15;
              }
              while ( v15 < v16 );
              v47 = v8;
            }
            Next = (_BYTE *)BtDbIteratorGetNext(v44);
            v10 = Next;
            v11 = Next;
          }
          while ( Next );
          v38 = 0;
        }
        *(_QWORD *)&v42 = 16LL * v8;
        *(_QWORD *)&v41 = 0x200000000LL;
        *((_QWORD *)&v42 + 1) = v5;
        *((_QWORD *)&v41 + 1) = v7;
        CurrentThread = GetCurrentThread();
        ThreadPriority = GetThreadPriority(CurrentThread);
        v20 = GetCurrentThread();
        SetThreadPriority(v20, 15);
        v21 = GetCurrentThread();
        ThreadInformation = 0;
        v22 = NtQueryInformationThread(v21, ThreadPagePriority, &ThreadInformation, 4u, 0);
        if ( v22 < 0 )
        {
          v23 = 8;
          RtlNtStatusToDosError(v22);
        }
        else
        {
          v23 = ThreadInformation;
        }
        v24 = GetCurrentThread();
        PfSetPagePriorityThread(v24);
        v25 = PfsVirtualQuery(&v41);
        if ( v25 < 0 )
        {
          LastError = RtlNtStatusToDosError(v25);
        }
        else
        {
          if ( ThreadPriority != 32 )
          {
            v26 = GetCurrentThread();
            SetThreadPriority(v26, ThreadPriority);
            ThreadPriority = 32;
          }
          if ( v23 != 8 )
          {
            v27 = GetCurrentThread();
            PfSetPagePriorityThread(v27);
            v23 = 8;
          }
          v43 = 0;
          LODWORD(v43) = 1;
          v28 = 17;
          for ( i = 0; i < v8; ++i )
          {
            v30 = 2LL * i;
            v31 = v7[v30 + 1];
            if ( (v31 & 1) == 0
              && (((v7[v30 + 1] & 0xC00000LL) - 0x400000) & 0xFFFFFFFFFFBFFFFFuLL) != 0
              && (v31 & 0x200000) == 0 )
            {
              v28 ^= (v7[v30] ^ v28) & 0xFFFFFFFFFFFFF000uLL;
              LastError = BtDbBreakupRange(a1, (_DWORD)v40, v28 >> 12, 0, 1, (__int64)&v48, (__int64)&v38);
              if ( LastError )
                goto LABEL_34;
              BtDbRangeDelete(a1, v38);
              v8 = v47;
            }
          }
          LastError = 0;
LABEL_34:
          v5 = hObject;
        }
        if ( ThreadPriority != 32 )
        {
          v35 = GetCurrentThread();
          SetThreadPriority(v35, ThreadPriority);
        }
        if ( v23 != 8 )
        {
          v36 = GetCurrentThread();
          PfSetPagePriorityThread(v36);
        }
      }
      else
      {
        LastError = 8;
      }
      CloseHandle(v5);
      if ( v7 )
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v7);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError == 87 )
        return 1067;
    }
  }
  else
  {
    return 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x180013068  mov     [rsp-8+arg_0], rcx
0x18001306d  push    rbp
0x18001306e  push    rbx
0x18001306f  push    rdi
0x180013070  push    r12
0x180013072  push    r13
0x180013074  push    r14
0x180013076  push    r15
0x180013078  lea     rbp, [rsp-27h]
0x18001307d  sub     rsp, 0D0h
0x180013084  cmp     dword ptr [rdx+10h], 2
0x180013088  xorps   xmm0, xmm0
0x18001308b  movups  [rbp+57h+var_A8], xmm0
0x18001308f  mov     rbx, rdx
0x180013092  mov     rdi, rcx
0x180013095  movups  [rbp+57h+var_98], xmm0
0x180013099  mov     [rbp+57h+arg_18], 0
0x1800130a0  jnz     loc_1800133D9
0x1800130a6  mov     r8d, [rdx+14h]; dwProcessId
0x1800130aa  mov     ecx, 1000h; dwDesiredAccess
0x1800130af  xor     edx, edx; bInheritHandle
0x1800130b1  call    cs:__imp_OpenProcess
0x1800130b7  mov     [rbp+57h+hObject], rax
0x1800130bb  mov     r14, rax
0x1800130be  test    rax, rax
0x1800130c1  jz      loc_1800133DD
0x1800130c7  mov     rcx, cs:PfSvcGlobals
0x1800130ce  add     rbx, 38h ; '8'
0x1800130d2  xor     edx, edx; dwFlags
0x1800130d4  mov     [rbp+57h+var_B0], rbx
0x1800130d8  mov     r8d, [rbx]
0x1800130db  mov     rcx, [rcx+58h]; hHeap
0x1800130df  shl     r8, 4; dwBytes
0x1800130e3  call    cs:__imp_HeapAlloc
0x1800130e9  mov     r15, rax
0x1800130ec  test    rax, rax
0x1800130ef  jz      loc_1800133F1
0x1800130f5  xor     edx, edx; Val
0x1800130f7  lea     rcx, [rbp+57h+var_70]; void *
0x1800130fb  lea     r8d, [rdx+40h]; Size
0x1800130ff  call    memset_0
0x180013104  lea     r8, [rbp+57h+var_70]
0x180013108  mov     rdx, rbx
0x18001310b  mov     rcx, rdi
0x18001310e  call    BtDbIteratorAttachToContainer
0x180013113  xor     ebx, ebx
0x180013115  lea     rcx, [rbp+57h+var_70]
0x180013119  mov     [rbp+57h+arg_10], ebx
0x18001311c  call    BtDbIteratorGetNext
0x180013121  mov     [rbp+57h+var_C0], rax
0x180013125  test    rax, rax
0x180013128  jz      short loc_1800131A1
0x18001312a  mov     rdx, rax
0x18001312d  mov     rcx, rax
0x180013130  test    byte ptr [rax], 1
0x180013133  movzx   r9d, byte ptr [rcx+1]
0x180013138  mov     ecx, [rdx+4]
0x18001313b  movzx   r8d, word ptr [rdx+2]
0x180013140  jnz     loc_180013331
0x180013146  and     ecx, 7Fh
0x180013149  shl     rcx, 10h
0x18001314d  or      rcx, r8
0x180013150  lea     r8, [rcx+1]
0x180013154  add     r8, r9
0x180013157  cmp     rcx, r8
0x18001315a  jnb     short loc_180013189
0x18001315c  mov     rax, cs:PfSvcGlobals
0x180013163  mov     rdx, rcx
0x180013166  shl     rdx, 0Ch
0x18001316a  cmp     rdx, [rax+350h]
0x180013171  ja      short loc_18001317E
0x180013173  mov     eax, ebx
0x180013175  add     rax, rax
0x180013178  inc     ebx
0x18001317a  mov     [r15+rax*8], rdx
0x18001317e  inc     rcx
0x180013181  cmp     rcx, r8
0x180013184  jb      short loc_18001315C
0x180013186  mov     [rbp+57h+arg_10], ebx
0x180013189  lea     rcx, [rbp+57h+var_70]
0x18001318d  call    BtDbIteratorGetNext
0x180013192  mov     rdx, rax
0x180013195  mov     rcx, rax
0x180013198  test    rax, rax
0x18001319b  jnz     short loc_180013130
0x18001319d  mov     [rbp+57h+var_C0], rax
0x1800131a1  mov     eax, ebx
0x1800131a3  shl     rax, 4
0x1800131a7  mov     qword ptr [rbp+57h+var_98], rax
0x1800131ab  mov     dword ptr [rbp+57h+var_A8], 0
0x1800131b2  mov     qword ptr [rbp+57h+var_98+8], r14
0x1800131b6  mov     qword ptr [rbp+57h+var_A8+8], r15
0x1800131ba  mov     dword ptr [rbp+57h+var_A8+4], 2
0x1800131c1  call    cs:__imp_GetCurrentThread
0x1800131c7  mov     rcx, rax; hThread
0x1800131ca  call    cs:__imp_GetThreadPriority
0x1800131d0  mov     r13d, eax
0x1800131d3  call    cs:__imp_GetCurrentThread
0x1800131d9  mov     rcx, rax; hThread
0x1800131dc  mov     edx, 0Fh; nPriority
0x1800131e1  call    cs:__imp_SetThreadPriority
0x1800131e7  call    cs:__imp_GetCurrentThread
0x1800131ed  mov     r9d, 4; ThreadInformationLength
0x1800131f3  mov     [rbp+57h+ThreadInformation], 0
0x1800131fa  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x1800131fe  mov     [rsp+100h+ReturnLength], 0; ReturnLength
0x180013207  mov     rcx, rax; ThreadHandle
0x18001320a  lea     edx, [r9+14h]; ThreadInformationClass
0x18001320e  call    cs:__imp_NtQueryInformationThread
0x180013214  test    eax, eax
0x180013216  js      loc_1800133C7
0x18001321c  mov     edi, [rbp+57h+ThreadInformation]
0x18001321f  call    cs:__imp_GetCurrentThread
0x180013225  mov     rcx, rax; ThreadHandle
0x180013228  mov     edx, 1
0x18001322d  call    PfSetPagePriorityThread
0x180013232  lea     rcx, [rbp+57h+var_A8]
0x180013236  call    PfsVirtualQuery
0x18001323b  test    eax, eax
0x18001323d  js      loc_1800133F8
0x180013243  cmp     r13d, 20h ; ' '
0x180013247  jz      short loc_180013261
0x180013249  call    cs:__imp_GetCurrentThread
0x18001324f  mov     rcx, rax; hThread
0x180013252  mov     edx, r13d; nPriority
0x180013255  call    cs:__imp_SetThreadPriority
0x18001325b  mov     r13d, 20h ; ' '
0x180013261  cmp     edi, 8
0x180013264  jz      short loc_18001327B
0x180013266  call    cs:__imp_GetCurrentThread
0x18001326c  mov     rcx, rax; ThreadHandle
0x18001326f  mov     edx, edi
0x180013271  call    PfSetPagePriorityThread
0x180013276  mov     edi, 8
0x18001327b  xorps   xmm0, xmm0
0x18001327e  movups  [rbp+57h+var_88], xmm0
0x180013282  mov     dword ptr [rbp+57h+var_88], 1
0x180013289  mov     r14, qword ptr [rbp+57h+var_88]
0x18001328d  and     r14d, 0FE7h
0x180013294  or      r14, 10h
0x180013298  xor     r12d, r12d
0x18001329b  cmp     r12d, ebx
0x18001329e  jnb     loc_18001335B
0x1800132a4  mov     edx, r12d
0x1800132a7  shl     rdx, 4
0x1800132ab  mov     rcx, [rdx+r15+8]
0x1800132b0  test    cl, 1
0x1800132b3  jz      short loc_1800132BA
0x1800132b5  inc     r12d
0x1800132b8  jmp     short loc_18001329B
0x1800132ba  mov     rax, rcx
0x1800132bd  and     eax, 0C00000h
0x1800132c2  sub     rax, 400000h
0x1800132c8  test    rax, 0FFFFFFFFFFBFFFFFh
0x1800132ce  jz      short loc_1800132B5
0x1800132d0  bt      rcx, 15h
0x1800132d5  jb      short loc_1800132B5
0x1800132d7  mov     rcx, [rbp+57h+arg_0]
0x1800132db  mov     rax, r14
0x1800132de  xor     r14, [rdx+r15]
0x1800132e2  xor     r9d, r9d
0x1800132e5  mov     rdx, [rbp+57h+var_B0]
0x1800132e9  and     r14, 0FFFFFFFFFFFFF000h
0x1800132f0  xor     r14, rax
0x1800132f3  lea     rax, [rbp+57h+var_C0]
0x1800132f7  mov     [rsp+100h+var_D0], rax
0x1800132fc  mov     r8, r14
0x1800132ff  lea     rax, [rbp+57h+arg_18]
0x180013303  shr     r8, 0Ch
0x180013307  mov     [rsp+100h+var_D8], rax
0x18001330c  mov     dword ptr [rsp+100h+ReturnLength], 1
0x180013314  call    BtDbBreakupRange
0x180013319  mov     ebx, eax
0x18001331b  test    eax, eax
0x18001331d  jnz     short loc_18001335D
0x18001331f  mov     rdx, [rbp+57h+var_C0]
0x180013323  mov     rcx, [rbp+57h+arg_0]
0x180013327  call    BtDbRangeDelete
0x18001332c  mov     ebx, [rbp+57h+arg_10]
0x18001332f  jmp     short loc_1800132B5
0x180013331  mov     rax, rcx
0x180013334  and     eax, 7FFFFh
0x180013339  shl     rax, 10h
0x18001333d  or      rax, r8
0x180013340  bt      ecx, 13h
0x180013344  mov     rcx, 0FFFF800000000h
0x18001334e  lea     rcx, [rax+rcx]
0x180013352  cmovnb  rcx, rax
0x180013356  jmp     loc_180013150
0x18001335b  xor     ebx, ebx
0x18001335d  mov     r14, [rbp+57h+hObject]
0x180013361  cmp     r13d, 20h ; ' '
0x180013365  jz      short loc_180013379
0x180013367  call    cs:__imp_GetCurrentThread
0x18001336d  mov     rcx, rax; hThread
0x180013370  mov     edx, r13d; nPriority
0x180013373  call    cs:__imp_SetThreadPriority
0x180013379  cmp     edi, 8
0x18001337c  jz      short loc_18001338E
0x18001337e  call    cs:__imp_GetCurrentThread
0x180013384  mov     rcx, rax; ThreadHandle
0x180013387  mov     edx, edi
0x180013389  call    PfSetPagePriorityThread
0x18001338e  mov     rcx, r14; hObject
0x180013391  call    cs:__imp_CloseHandle
0x180013397  test    r15, r15
0x18001339a  jz      short loc_1800133B2
0x18001339c  mov     rcx, cs:PfSvcGlobals
0x1800133a3  mov     r8, r15; lpMem
0x1800133a6  xor     edx, edx; dwFlags
0x1800133a8  mov     rcx, [rcx+58h]; hHeap
0x1800133ac  call    cs:__imp_HeapFree
0x1800133b2  mov     eax, ebx
0x1800133b4  add     rsp, 0D0h
0x1800133bb  pop     r15
0x1800133bd  pop     r14
0x1800133bf  pop     r13
0x1800133c1  pop     r12
0x1800133c3  pop     rdi
0x1800133c4  pop     rbx
0x1800133c5  pop     rbp
0x1800133c6  retn
0x1800133c7  mov     ecx, eax; Status
0x1800133c9  mov     edi, 8
0x1800133ce  call    cs:__imp_RtlNtStatusToDosError
0x1800133d4  jmp     loc_18001321F
0x1800133d9  xor     ebx, ebx
0x1800133db  jmp     short loc_1800133B2
0x1800133dd  call    cs:__imp_GetLastError
0x1800133e3  mov     ebx, eax
0x1800133e5  cmp     eax, 57h ; 'W'
0x1800133e8  jnz     short loc_1800133B2
0x1800133ea  mov     ebx, 42Bh
0x1800133ef  jmp     short loc_1800133B2
0x1800133f1  mov     ebx, 8
0x1800133f6  jmp     short loc_18001338E
0x1800133f8  mov     ecx, eax; Status
0x1800133fa  call    cs:__imp_RtlNtStatusToDosError
0x180013400  mov     ebx, eax
0x180013402  jmp     loc_180013361
```
