# CUmRdpDr::ShutdownDedicatedThreads(void)

- ea: `0x18001327c`
- end: `0x1800134c3`
- name: `?ShutdownDedicatedThreads@CUmRdpDr@@AEAAXXZ`
- size: `583`
- prototype: `void __fastcall(CUmRdpDr *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180011c40`
- `0x1800130e8`

## callees

- `0x18001327c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800132d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013357`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013370`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001340b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013428`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800132d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013357`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013370`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001340b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013428`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800132ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013325`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800132ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013325`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800133f2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800134aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800133f2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800134aa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800132b8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013313`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800132b8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013313`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001338b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013443`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001338b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013443`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800133e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800134a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800133e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800134a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800133c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800133de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001347e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013496`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800133c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800133de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001347e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013496`

## pseudocode

```c
void __fastcall CUmRdpDr::ShutdownDedicatedThreads(CUmRdpDr *this)
{
  HANDLE *v2; // rsi
  void *v3; // rcx
  void *v4; // rcx
  __int64 *v5; // rsi
  __int64 v6; // rcx
  __int64 *v7; // rax
  void *v8; // r8
  void *v9; // rcx
  void *v10; // rcx
  __int64 *v11; // rsi
  __int64 v12; // rcx
  __int64 *v13; // rax
  void *v14; // r8

  v2 = (HANDLE *)((char *)this + 2216);
  if ( *((_QWORD *)this + 276) )
  {
    *((_DWORD *)this + 572) = 1;
    if ( *v2 )
      SetEvent(*v2);
    WaitForSingleObject(*((HANDLE *)this + 276), 0x1388u);
    CloseHandle(*((HANDLE *)this + 276));
    *((_QWORD *)this + 276) = 0;
    *((_QWORD *)this + 275) = 0;
  }
  if ( *((_QWORD *)this + 288) )
  {
    *((_DWORD *)this + 596) = 1;
    v3 = (void *)*((_QWORD *)this + 289);
    if ( v3 )
      SetEvent(v3);
    WaitForSingleObject(*((HANDLE *)this + 288), 0x1388u);
    CloseHandle(*((HANDLE *)this + 288));
    *((_QWORD *)this + 288) = 0;
    *((_QWORD *)this + 287) = 0;
  }
  if ( *v2 )
  {
    CloseHandle(*v2);
    *v2 = 0;
  }
  v4 = (void *)*((_QWORD *)this + 278);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 278) = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2248));
  while ( 1 )
  {
    v5 = (__int64 *)*((_QWORD *)this + 279);
    if ( v5 == (__int64 *)((char *)this + 2232) )
      break;
    v6 = *v5;
    v7 = (__int64 *)v5[1];
    *v7 = *v5;
    *(_QWORD *)(v6 + 8) = v7;
    v8 = (void *)v5[2];
    if ( v8 )
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v8);
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v5);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2248));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 2248));
  v9 = (void *)*((_QWORD *)this + 289);
  if ( v9 )
  {
    CloseHandle(v9);
    *((_QWORD *)this + 289) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 290);
  if ( v10 )
  {
    CloseHandle(v10);
    *((_QWORD *)this + 290) = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2344));
  while ( 1 )
  {
    v11 = (__int64 *)*((_QWORD *)this + 291);
    if ( v11 == (__int64 *)((char *)this + 2328) )
      break;
    v12 = *v11;
    v13 = (__int64 *)v11[1];
    *v13 = *v11;
    *(_QWORD *)(v12 + 8) = v13;
    v14 = (void *)v11[2];
    if ( v14 )
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v14);
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v11);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2344));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 2344));
}

```

## disassembly

```asm
0x18001327c  mov     [rsp+arg_8], rbx
0x180013281  mov     [rsp+arg_10], rsi
0x180013286  push    r14
0x180013288  sub     rsp, 20h
0x18001328c  mov     rbx, rcx
0x18001328f  mov     [rsp+28h+arg_0], rcx
0x180013294  lea     rsi, [rcx+8A8h]
0x18001329b  cmp     qword ptr [rcx+8A0h], 0
0x1800132a3  jz      short loc_1800132F3
0x1800132a5  mov     dword ptr [rcx+8F0h], 1
0x1800132af  cmp     qword ptr [rsi], 0
0x1800132b3  jz      short loc_1800132BE
0x1800132b5  mov     rcx, [rsi]; hEvent
0x1800132b8  call    cs:__imp_SetEvent
0x1800132be  mov     edx, 1388h; dwMilliseconds
0x1800132c3  mov     rcx, [rbx+8A0h]; hHandle
0x1800132ca  call    cs:__imp_WaitForSingleObject
0x1800132d0  mov     rcx, [rbx+8A0h]; hObject
0x1800132d7  call    cs:__imp_CloseHandle
0x1800132dd  mov     qword ptr [rbx+8A0h], 0
0x1800132e8  mov     qword ptr [rbx+898h], 0
0x1800132f3  cmp     qword ptr [rbx+900h], 0
0x1800132fb  jz      short loc_18001334E
0x1800132fd  mov     dword ptr [rbx+950h], 1
0x180013307  mov     rcx, [rbx+908h]; hEvent
0x18001330e  test    rcx, rcx
0x180013311  jz      short loc_180013319
0x180013313  call    cs:__imp_SetEvent
0x180013319  mov     edx, 1388h; dwMilliseconds
0x18001331e  mov     rcx, [rbx+900h]; hHandle
0x180013325  call    cs:__imp_WaitForSingleObject
0x18001332b  mov     rcx, [rbx+900h]; hObject
0x180013332  call    cs:__imp_CloseHandle
0x180013338  mov     qword ptr [rbx+900h], 0
0x180013343  mov     qword ptr [rbx+8F8h], 0
0x18001334e  cmp     qword ptr [rsi], 0
0x180013352  jz      short loc_180013364
0x180013354  mov     rcx, [rsi]; hObject
0x180013357  call    cs:__imp_CloseHandle
0x18001335d  mov     qword ptr [rsi], 0
0x180013364  mov     rcx, [rbx+8B0h]; hObject
0x18001336b  test    rcx, rcx
0x18001336e  jz      short loc_180013381
0x180013370  call    cs:__imp_CloseHandle
0x180013376  mov     qword ptr [rbx+8B0h], 0
0x180013381  lea     r14, [rbx+8C8h]
0x180013388  mov     rcx, r14; lpCriticalSection
0x18001338b  call    cs:__imp_EnterCriticalSection
0x180013391  lea     rax, [rbx+8B8h]
0x180013398  mov     rsi, [rax]
0x18001339b  cmp     rsi, rax
0x18001339e  jz      short loc_1800133E6
0x1800133a0  mov     rcx, [rsi]
0x1800133a3  mov     rax, [rsi+8]
0x1800133a7  mov     [rax], rcx
0x1800133aa  mov     [rcx+8], rax
0x1800133ae  mov     r8, [rsi+10h]; lpMem
0x1800133b2  test    r8, r8
0x1800133b5  jz      short loc_1800133CC
0x1800133b7  mov     rcx, gs:60h
0x1800133c0  xor     edx, edx; dwFlags
0x1800133c2  mov     rcx, [rcx+30h]; hHeap
0x1800133c6  call    cs:__imp_HeapFree
0x1800133cc  mov     rcx, gs:60h
0x1800133d5  mov     r8, rsi; lpMem
0x1800133d8  xor     edx, edx; dwFlags
0x1800133da  mov     rcx, [rcx+30h]; hHeap
0x1800133de  call    cs:__imp_HeapFree
0x1800133e4  jmp     short loc_180013391
0x1800133e6  mov     rcx, r14; lpCriticalSection
0x1800133e9  call    cs:__imp_LeaveCriticalSection
0x1800133ef  mov     rcx, r14; lpCriticalSection
0x1800133f2  call    cs:__imp_DeleteCriticalSection
0x1800133f8  jmp     short loc_1800133FF
0x1800133fa  mov     rbx, [rsp+28h+arg_0]
0x1800133ff  mov     rcx, [rbx+908h]; hObject
0x180013406  test    rcx, rcx
0x180013409  jz      short loc_18001341C
0x18001340b  call    cs:__imp_CloseHandle
0x180013411  mov     qword ptr [rbx+908h], 0
0x18001341c  mov     rcx, [rbx+910h]; hObject
0x180013423  test    rcx, rcx
0x180013426  jz      short loc_180013439
0x180013428  call    cs:__imp_CloseHandle
0x18001342e  mov     qword ptr [rbx+910h], 0
0x180013439  lea     r14, [rbx+928h]
0x180013440  mov     rcx, r14; lpCriticalSection
0x180013443  call    cs:__imp_EnterCriticalSection
0x180013449  lea     rax, [rbx+918h]
0x180013450  mov     rsi, [rax]
0x180013453  cmp     rsi, rax
0x180013456  jz      short loc_18001349E
0x180013458  mov     rcx, [rsi]
0x18001345b  mov     rax, [rsi+8]
0x18001345f  mov     [rax], rcx
0x180013462  mov     [rcx+8], rax
0x180013466  mov     r8, [rsi+10h]; lpMem
0x18001346a  test    r8, r8
0x18001346d  jz      short loc_180013484
0x18001346f  mov     rcx, gs:60h
0x180013478  xor     edx, edx; dwFlags
0x18001347a  mov     rcx, [rcx+30h]; hHeap
0x18001347e  call    cs:__imp_HeapFree
0x180013484  mov     rcx, gs:60h
0x18001348d  mov     r8, rsi; lpMem
0x180013490  xor     edx, edx; dwFlags
0x180013492  mov     rcx, [rcx+30h]; hHeap
0x180013496  call    cs:__imp_HeapFree
0x18001349c  jmp     short loc_180013449
0x18001349e  mov     rcx, r14; lpCriticalSection
0x1800134a1  call    cs:__imp_LeaveCriticalSection
0x1800134a7  mov     rcx, r14; lpCriticalSection
0x1800134aa  call    cs:__imp_DeleteCriticalSection
0x1800134b0  jmp     short $+2
0x1800134b2  mov     rbx, [rsp+28h+arg_8]
0x1800134b7  mov     rsi, [rsp+28h+arg_10]
0x1800134bc  add     rsp, 20h
0x1800134c0  pop     r14
0x1800134c2  retn
```
