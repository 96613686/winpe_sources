# CSpCommunicator::SendCall(ulong,void *,ulong,int,void * *,ulong *)

- ea: `0x1800eb3d0`
- end: `0x1800eb67c`
- name: `?SendCall@CSpCommunicator@@UEAAJKPEAXKHPEAPEAXPEAK@Z`
- size: `684`
- prototype: `__int64 __fastcall(CSpCommunicator *this, int, void *, unsigned int, int, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180013ec0`
- `0x180045938`
- `0x18007a2dc`
- `0x18007aae4`
- `0x18007d31c`
- `0x18007d7b1`
- `0x1800eaf00`
- `0x1800eb2c0`
- `0x1800eb3d0`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eb4dd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eb664`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eb4dd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800eb664`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800eb4c7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800eb4c7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800eb57d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800eb57d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eb4ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eb4ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800eb60a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800eb60a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eb619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eb619`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800eb469`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800eb469`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSpCommunicator::SendCall(
        CSpCommunicator *this,
        int a2,
        void *a3,
        unsigned int a4,
        int a5,
        void **a6,
        unsigned int *a7)
{
  size_t v9; // rdi
  int Win32Error; // edi
  void *v11; // rsi
  void *v12; // rbx
  int v13; // eax
  __int64 v14; // rcx
  DWORD v15; // eax
  int v16; // ebx
  void *v17; // rax
  void *v19; // rax
  void *v20; // rax
  HANDLE EventW; // rax
  void *v22; // rcx
  HANDLE Handles[11]; // [rsp+20h] [rbp-58h] BYREF

  v9 = a4;
  if ( a3 && !a4 || a6 && !a5 || a7 && !a5 )
  {
    Win32Error = -2147024809;
LABEL_8:
    v11 = 0;
    v12 = 0;
LABEL_9:
    v13 = 0;
    goto LABEL_10;
  }
  if ( !*((_QWORD *)this + 11) )
  {
    Win32Error = -2147201023;
    goto LABEL_8;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 14) + 64LL))(*((_QWORD *)this + 14));
  if ( v16 == GetCurrentThreadId() )
  {
    Win32Error = -2147200945;
    goto LABEL_8;
  }
  if ( a5 )
  {
    v11 = 0;
  }
  else
  {
    v17 = malloc(v9);
    v11 = v17;
    if ( !v17 )
    {
      Win32Error = -2147024882;
LABEL_22:
      free(v11);
LABEL_23:
      DoTraceMessage(4, "SendCall failed, method id = %u, Error = %X", a2, Win32Error);
      return (unsigned int)Win32Error;
    }
    memcpy_0(v17, a3, v9);
  }
  v19 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v19;
  if ( !v19 )
  {
    Win32Error = -2147024882;
    goto LABEL_9;
  }
  memset_0(v19, 0, 0x40u);
  *(_DWORD *)v12 = a2;
  v20 = v11;
  if ( a5 )
    v20 = a3;
  *((_DWORD *)v12 + 4) = v9;
  *((_QWORD *)v12 + 1) = v20;
  *((_DWORD *)v12 + 8) = a5;
  if ( a5 )
    EventW = CreateEventW(0, 0, 0, 0);
  else
    EventW = 0;
  *((_QWORD *)v12 + 3) = EventW;
  *((_QWORD *)v12 + 7) = v12;
  Win32Error = CSpCommunicator::QueueSendCall(this, (struct SPCALL *)v12);
  if ( Win32Error < 0 )
    goto LABEL_9;
  Win32Error = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 14) + 24LL))(*((_QWORD *)this + 14));
  v13 = 1;
LABEL_10:
  if ( !a5 )
  {
    if ( Win32Error >= 0 )
      return (unsigned int)Win32Error;
    if ( v12 )
    {
      if ( !v13 || (int)CSpCommunicator::RemoveQueuedSendCall(this, (struct SPCALL *)v12) >= 0 )
      {
        free(v11);
        operator delete(v12);
      }
      goto LABEL_23;
    }
    goto LABEL_22;
  }
  if ( Win32Error < 0 )
    goto LABEL_43;
  v14 = *((_QWORD *)this + 14);
  Handles[0] = *((HANDLE *)v12 + 3);
  Handles[1] = (HANDLE)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 56LL))(v14);
  v15 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
  if ( v15 )
  {
    if ( v15 == 1 )
    {
      Win32Error = -2147200944;
      goto LABEL_43;
    }
    Win32Error = SpHrFromLastWin32Error();
  }
  else
  {
    Win32Error = *((_DWORD *)v12 + 13);
  }
  if ( Win32Error >= 0 )
  {
    if ( a6 )
    {
      *a6 = (void *)*((_QWORD *)v12 + 5);
      *((_QWORD *)v12 + 5) = 0;
    }
    if ( a7 )
    {
      *a7 = *((_DWORD *)v12 + 12);
      *((_DWORD *)v12 + 12) = 0;
    }
  }
LABEL_43:
  if ( v12 )
  {
    CSpCommunicator::RemoveQueuedSendCall(this, (struct SPCALL *)v12);
    CloseHandle(*((HANDLE *)v12 + 3));
    v22 = (void *)*((_QWORD *)v12 + 5);
    if ( v22 )
      CoTaskMemFree(v22);
    operator delete(v12);
  }
  if ( Win32Error < 0 )
    goto LABEL_23;
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x1800eb3d0  mov     [rsp+arg_8], edx
0x1800eb3d4  push    rbx
0x1800eb3d5  push    rbp
0x1800eb3d6  push    rsi
0x1800eb3d7  push    rdi
0x1800eb3d8  push    r12
0x1800eb3da  push    r13
0x1800eb3dc  push    r14
0x1800eb3de  push    r15
0x1800eb3e0  sub     rsp, 38h
0x1800eb3e4  mov     r13, [rsp+78h+arg_30]
0x1800eb3ec  mov     r15, r8
0x1800eb3ef  mov     r12, [rsp+78h+arg_28]
0x1800eb3f7  mov     r14, rcx
0x1800eb3fa  mov     ebp, [rsp+78h+arg_20]
0x1800eb401  mov     edi, r9d
0x1800eb404  test    r8, r8
0x1800eb407  jz      short loc_1800EB40E
0x1800eb409  test    r9d, r9d
0x1800eb40c  jz      short loc_1800EB420
0x1800eb40e  test    r12, r12
0x1800eb411  jz      short loc_1800EB417
0x1800eb413  test    ebp, ebp
0x1800eb415  jz      short loc_1800EB420
0x1800eb417  test    r13, r13
0x1800eb41a  jz      short loc_1800EB48C
0x1800eb41c  test    ebp, ebp
0x1800eb41e  jnz     short loc_1800EB48C
0x1800eb420  mov     edi, 80070057h
0x1800eb425  xor     esi, esi
0x1800eb427  xor     ebx, ebx
0x1800eb429  xor     eax, eax
0x1800eb42b  test    ebp, ebp
0x1800eb42d  jz      loc_1800EB639
0x1800eb433  test    edi, edi
0x1800eb435  js      loc_1800EB5F6
0x1800eb43b  mov     rax, [rbx+18h]
0x1800eb43f  mov     rcx, [r14+70h]
0x1800eb443  mov     [rsp+78h+Handles], rax
0x1800eb448  mov     rax, [rcx]
0x1800eb44b  mov     rax, [rax+38h]
0x1800eb44f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb454  xor     r8d, r8d; bWaitAll
0x1800eb457  mov     [rsp+78h+var_50], rax
0x1800eb45c  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800eb460  lea     rdx, [rsp+78h+Handles]; lpHandles
0x1800eb465  lea     ecx, [r8+2]; nCount
0x1800eb469  call    cs:__imp_WaitForMultipleObjects
0x1800eb46f  test    eax, eax
0x1800eb471  jz      loc_1800EB5C7
0x1800eb477  cmp     eax, 1
0x1800eb47a  jz      loc_1800EB5C0
0x1800eb480  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800eb485  mov     edi, eax
0x1800eb487  jmp     loc_1800EB5CA
0x1800eb48c  cmp     qword ptr [rcx+58h], 0
0x1800eb491  jnz     short loc_1800EB49A
0x1800eb493  mov     edi, 80045001h
0x1800eb498  jmp     short loc_1800EB425
0x1800eb49a  mov     rcx, [rcx+70h]
0x1800eb49e  mov     rax, [rcx]
0x1800eb4a1  mov     rax, [rax+40h]
0x1800eb4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb4aa  mov     ebx, eax
0x1800eb4ac  call    cs:__imp_GetCurrentThreadId
0x1800eb4b2  cmp     ebx, eax
0x1800eb4b4  jnz     short loc_1800EB4C0
0x1800eb4b6  mov     edi, 8004504Fh
0x1800eb4bb  jmp     loc_1800EB425
0x1800eb4c0  test    ebp, ebp
0x1800eb4c2  jnz     short loc_1800EB522
0x1800eb4c4  mov     rcx, rdi; Size
0x1800eb4c7  call    cs:__imp_malloc
0x1800eb4cd  mov     rsi, rax
0x1800eb4d0  test    rax, rax
0x1800eb4d3  jnz     short loc_1800EB512
0x1800eb4d5  mov     edi, 8007000Eh
0x1800eb4da  mov     rcx, rsi; Block
0x1800eb4dd  call    cs:__imp_free
0x1800eb4e3  mov     r8d, [rsp+78h+arg_8]
0x1800eb4eb  lea     rdx, aSendcallFailed; "SendCall failed, method id = %u, Error "...
0x1800eb4f2  mov     r9d, edi
0x1800eb4f5  mov     ecx, 4; int
0x1800eb4fa  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800eb4ff  mov     eax, edi
0x1800eb501  add     rsp, 38h
0x1800eb505  pop     r15
0x1800eb507  pop     r14
0x1800eb509  pop     r13
0x1800eb50b  pop     r12
0x1800eb50d  pop     rdi
0x1800eb50e  pop     rsi
0x1800eb50f  pop     rbp
0x1800eb510  pop     rbx
0x1800eb511  retn
0x1800eb512  mov     r8, rdi; Size
0x1800eb515  mov     rdx, r15; Src
0x1800eb518  mov     rcx, rax; void *
0x1800eb51b  call    memcpy_0
0x1800eb520  jmp     short loc_1800EB524
0x1800eb522  xor     esi, esi
0x1800eb524  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800eb52b  mov     ecx, 40h ; '@'; unsigned __int64
0x1800eb530  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800eb535  mov     rbx, rax
0x1800eb538  test    rax, rax
0x1800eb53b  jnz     short loc_1800EB547
0x1800eb53d  mov     edi, 8007000Eh
0x1800eb542  jmp     loc_1800EB429
0x1800eb547  xor     edx, edx; Val
0x1800eb549  mov     rcx, rbx; void *
0x1800eb54c  lea     r8d, [rdx+40h]; Size
0x1800eb550  call    memset_0
0x1800eb555  mov     eax, [rsp+78h+arg_8]
0x1800eb55c  test    ebp, ebp
0x1800eb55e  mov     [rbx], eax
0x1800eb560  mov     rax, rsi
0x1800eb563  cmovnz  rax, r15
0x1800eb567  mov     [rbx+10h], edi
0x1800eb56a  mov     [rbx+8], rax
0x1800eb56e  mov     [rbx+20h], ebp
0x1800eb571  jz      short loc_1800EB585
0x1800eb573  xor     r9d, r9d; lpName
0x1800eb576  xor     r8d, r8d; bInitialState
0x1800eb579  xor     edx, edx; bManualReset
0x1800eb57b  xor     ecx, ecx; lpEventAttributes
0x1800eb57d  call    cs:__imp_CreateEventW
0x1800eb583  jmp     short loc_1800EB587
0x1800eb585  xor     eax, eax
0x1800eb587  mov     rdx, rbx; struct SPCALL *
0x1800eb58a  mov     [rbx+18h], rax
0x1800eb58e  mov     rcx, r14; this
0x1800eb591  mov     [rbx+38h], rbx
0x1800eb595  call    ?QueueSendCall@CSpCommunicator@@AEAAJPEAUSPCALL@@@Z; CSpCommunicator::QueueSendCall(SPCALL *)
0x1800eb59a  mov     edi, eax
0x1800eb59c  test    eax, eax
0x1800eb59e  js      loc_1800EB429
0x1800eb5a4  mov     rcx, [r14+70h]
0x1800eb5a8  mov     rax, [rcx]
0x1800eb5ab  mov     rax, [rax+18h]
0x1800eb5af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb5b4  mov     edi, eax
0x1800eb5b6  mov     eax, 1
0x1800eb5bb  jmp     loc_1800EB42B
0x1800eb5c0  mov     edi, 80045050h
0x1800eb5c5  jmp     short loc_1800EB5F6
0x1800eb5c7  mov     edi, [rbx+34h]
0x1800eb5ca  test    edi, edi
0x1800eb5cc  js      short loc_1800EB5F6
0x1800eb5ce  test    r12, r12
0x1800eb5d1  jz      short loc_1800EB5E3
0x1800eb5d3  mov     rax, [rbx+28h]
0x1800eb5d7  mov     [r12], rax
0x1800eb5db  mov     qword ptr [rbx+28h], 0
0x1800eb5e3  test    r13, r13
0x1800eb5e6  jz      short loc_1800EB5F6
0x1800eb5e8  mov     eax, [rbx+30h]
0x1800eb5eb  mov     [r13+0], eax
0x1800eb5ef  mov     dword ptr [rbx+30h], 0
0x1800eb5f6  test    rbx, rbx
0x1800eb5f9  jz      short loc_1800EB62C
0x1800eb5fb  mov     rdx, rbx; struct SPCALL *
0x1800eb5fe  mov     rcx, r14; this
0x1800eb601  call    ?RemoveQueuedSendCall@CSpCommunicator@@AEAAJPEAUSPCALL@@@Z; CSpCommunicator::RemoveQueuedSendCall(SPCALL *)
0x1800eb606  mov     rcx, [rbx+18h]; hObject
0x1800eb60a  call    cs:__imp_CloseHandle
0x1800eb610  mov     rcx, [rbx+28h]; pv
0x1800eb614  test    rcx, rcx
0x1800eb617  jz      short loc_1800EB61F
0x1800eb619  call    cs:__imp_CoTaskMemFree
0x1800eb61f  mov     edx, 40h ; '@'
0x1800eb624  mov     rcx, rbx; Block
0x1800eb627  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eb62c  test    edi, edi
0x1800eb62e  jns     loc_1800EB4FF
0x1800eb634  jmp     loc_1800EB4E3
0x1800eb639  test    edi, edi
0x1800eb63b  jns     loc_1800EB4FF
0x1800eb641  test    rbx, rbx
0x1800eb644  jz      loc_1800EB4DA
0x1800eb64a  test    eax, eax
0x1800eb64c  jz      short loc_1800EB661
0x1800eb64e  mov     rdx, rbx; struct SPCALL *
0x1800eb651  mov     rcx, r14; this
0x1800eb654  call    ?RemoveQueuedSendCall@CSpCommunicator@@AEAAJPEAUSPCALL@@@Z; CSpCommunicator::RemoveQueuedSendCall(SPCALL *)
0x1800eb659  test    eax, eax
0x1800eb65b  js      loc_1800EB4E3
0x1800eb661  mov     rcx, rsi; Block
0x1800eb664  call    cs:__imp_free
0x1800eb66a  mov     edx, 40h ; '@'
0x1800eb66f  mov     rcx, rbx; Block
0x1800eb672  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800eb677  jmp     loc_1800EB4E3
```
