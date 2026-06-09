# NMP_CompleteListenAbort(void *)

- ea: `0x1800cb140`
- end: `0x1800cb31f`
- name: `?NMP_CompleteListenAbort@@YAXPEAX@Z`
- size: `479`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800cb110`

## callees

- `0x180016600`
- `0x180023a40`
- `0x180064e3c`
- `0x180072f50`
- `0x180081cf4`
- `0x1800cb140`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb1bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb20e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb2bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb1bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb20e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cb2bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800cb1d7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800cb2d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800cb1d7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800cb2d0`

## pseudocode

```c
void __fastcall NMP_CompleteListenAbort(char *a1)
{
  volatile __int32 *v2; // rdi
  int v3; // ecx
  unsigned int v4; // eax
  __int64 v5; // rsi
  unsigned int v6; // edx
  RPC_THREAD_POOL_IO *v7; // rcx
  void *v8; // rcx
  char *v9; // rdi
  char *v10; // rcx
  SIMPLE_DICT *v11; // rcx
  void *v12; // rsi
  unsigned int v13; // edx
  RPC_THREAD_POOL_IO *v14; // rcx
  unsigned int v15; // [rsp+40h] [rbp+8h] BYREF

  CSpinLock::Lock((CSpinLock *)(a1 + 120));
  v2 = (volatile __int32 *)(a1 + 120);
  if ( _InterlockedIncrement((volatile signed __int32 *)a1 + 4) == 1 )
  {
    v5 = *((_QWORD *)a1 + 25);
    *((_QWORD *)a1 + 25) = 0;
    _InterlockedExchange(v2, ((*v2 - 0x10000000) & 0xF0000000) != 0 ? *v2 - 0x10000000 : 0);
    if ( v5 )
    {
      CloseHandle(*(HANDLE *)(v5 + 56));
      WaitForThreadpoolIoCallbacks(**(PTP_IO **)(v5 + 48), 1);
      v7 = *(RPC_THREAD_POOL_IO **)(v5 + 48);
      if ( v7 )
        RPC_THREAD_POOL_IO::`scalar deleting destructor'(v7, v6);
      FreeWrapper((void *)v5);
    }
    CSpinLock::Lock((CSpinLock *)(a1 + 120));
    v8 = (void *)*((_QWORD *)a1 + 33);
    if ( v8 )
    {
      CloseHandle(v8);
      *((_QWORD *)a1 + 33) = 0;
    }
    v9 = (char *)*((_QWORD *)a1 + 37);
    while ( v9 != a1 + 296 )
    {
      v10 = v9 - 160;
      v9 = *(char **)v9;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 48LL))(v10);
    }
    v2 = (volatile __int32 *)(a1 + 208);
    _InterlockedExchange(
      (volatile __int32 *)a1 + 30,
      ((*((_DWORD *)a1 + 30) - 0x10000000) & 0xF0000000) != 0 ? *((_DWORD *)a1 + 30) - 0x10000000 : 0);
LABEL_13:
    CSpinLock::Lock((CSpinLock *)(a1 + 208));
    v15 = 0;
    while ( 1 )
    {
      v12 = SIMPLE_DICT::Next((SIMPLE_DICT *)(a1 + 216), &v15);
      if ( !v12 )
        break;
      SIMPLE_DICT::Delete(v11, v15 - 1);
      if ( *((_QWORD *)v12 + 7) )
      {
        _InterlockedExchange(
          v2,
          ((*((_DWORD *)a1 + 52) - 0x10000000) & 0xF0000000) != 0 ? *((_DWORD *)a1 + 52) - 0x10000000 : 0);
        CloseHandle(*((HANDLE *)v12 + 7));
        WaitForThreadpoolIoCallbacks(**((PTP_IO **)v12 + 6), 0);
        v14 = (RPC_THREAD_POOL_IO *)*((_QWORD *)v12 + 6);
        if ( v14 )
          RPC_THREAD_POOL_IO::`scalar deleting destructor'(v14, v13);
        FreeWrapper(v12);
        goto LABEL_13;
      }
    }
    v3 = *((_DWORD *)a1 + 52) - 0x10000000;
    v4 = v3 & 0xF0000000;
  }
  else
  {
    v3 = *v2 - 0x10000000;
    v4 = v3 & 0xF0000000;
  }
  _InterlockedExchange(v2, v4 != 0 ? v3 : 0);
}

```

## disassembly

```asm
0x1800cb140  mov     [rsp+arg_8], rbx
0x1800cb145  mov     [rsp+arg_10], rbp
0x1800cb14a  push    rsi
0x1800cb14b  push    rdi
0x1800cb14c  push    r14
0x1800cb14e  sub     rsp, 20h
0x1800cb152  mov     rbx, rcx
0x1800cb155  add     rcx, 78h ; 'x'; this
0x1800cb159  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x1800cb15e  mov     eax, 1
0x1800cb163  lea     rdi, [rbx+78h]
0x1800cb167  lock xadd [rbx+10h], eax
0x1800cb16c  inc     eax
0x1800cb16e  cmp     eax, 1
0x1800cb171  jz      short loc_1800CB187
0x1800cb173  mov     ecx, [rdi]
0x1800cb175  add     ecx, 0F0000000h
0x1800cb17b  mov     eax, ecx
0x1800cb17d  and     eax, 0F0000000h
0x1800cb182  jmp     loc_1800CB303
0x1800cb187  mov     rsi, [rbx+0C8h]
0x1800cb18e  mov     ebp, 0F0000000h
0x1800cb193  mov     qword ptr [rbx+0C8h], 0
0x1800cb19e  mov     r8d, [rdi]
0x1800cb1a1  add     r8d, 0F0000000h
0x1800cb1a8  mov     eax, r8d
0x1800cb1ab  and     eax, ebp
0x1800cb1ad  neg     eax
0x1800cb1af  sbb     ecx, ecx
0x1800cb1b1  and     ecx, r8d
0x1800cb1b4  xchg    ecx, [rdi]
0x1800cb1b6  test    rsi, rsi
0x1800cb1b9  jz      short loc_1800CB1F9
0x1800cb1bb  mov     rcx, [rsi+38h]; hObject
0x1800cb1bf  call    cs:__imp_CloseHandle
0x1800cb1c6  nop     dword ptr [rax+rax+00h]
0x1800cb1cb  mov     rcx, [rsi+30h]
0x1800cb1cf  mov     edx, 1; fCancelPendingCallbacks
0x1800cb1d4  mov     rcx, [rcx]; pio
0x1800cb1d7  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800cb1de  nop     dword ptr [rax+rax+00h]
0x1800cb1e3  mov     rcx, [rsi+30h]; this
0x1800cb1e7  test    rcx, rcx
0x1800cb1ea  jz      short loc_1800CB1F1
0x1800cb1ec  call    ??_GRPC_THREAD_POOL_IO@@QEAAPEAXI@Z; RPC_THREAD_POOL_IO::`scalar deleting destructor'(uint)
0x1800cb1f1  mov     rcx, rsi; lpMem
0x1800cb1f4  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800cb1f9  lea     rcx, [rbx+78h]; this
0x1800cb1fd  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x1800cb202  mov     rcx, [rbx+108h]; hObject
0x1800cb209  test    rcx, rcx
0x1800cb20c  jz      short loc_1800CB225
0x1800cb20e  call    cs:__imp_CloseHandle
0x1800cb215  nop     dword ptr [rax+rax+00h]
0x1800cb21a  mov     qword ptr [rbx+108h], 0
0x1800cb225  lea     rsi, [rbx+128h]
0x1800cb22c  mov     rdi, [rsi]
0x1800cb22f  jmp     short loc_1800CB247
0x1800cb231  lea     rcx, [rdi-0A0h]
0x1800cb238  mov     rdi, [rdi]
0x1800cb23b  mov     rax, [rcx]
0x1800cb23e  mov     rax, [rax+30h]
0x1800cb242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb247  cmp     rdi, rsi
0x1800cb24a  jnz     short loc_1800CB231
0x1800cb24c  mov     edx, [rbx+78h]
0x1800cb24f  lea     rdi, [rbx+0D0h]
0x1800cb256  add     edx, ebp
0x1800cb258  lea     r14, [rbx+0D8h]
0x1800cb25f  mov     eax, edx
0x1800cb261  and     eax, ebp
0x1800cb263  neg     eax
0x1800cb265  sbb     ecx, ecx
0x1800cb267  and     ecx, edx
0x1800cb269  xchg    ecx, [rbx+78h]
0x1800cb26c  mov     rcx, rdi; this
0x1800cb26f  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x1800cb274  mov     [rsp+38h+arg_0], 0
0x1800cb27c  lea     rdx, [rsp+38h+arg_0]; unsigned int *
0x1800cb281  mov     rcx, r14; this
0x1800cb284  call    ?Next@SIMPLE_DICT@@QEAAPEAXAEAI@Z; SIMPLE_DICT::Next(uint &)
0x1800cb289  mov     rsi, rax
0x1800cb28c  test    rax, rax
0x1800cb28f  jz      short loc_1800CB2F7
0x1800cb291  mov     edx, [rsp+38h+arg_0]
0x1800cb295  dec     edx; unsigned int
0x1800cb297  call    ?Delete@SIMPLE_DICT@@QEAAPEAXI@Z; SIMPLE_DICT::Delete(uint)
0x1800cb29c  cmp     qword ptr [rsi+38h], 0
0x1800cb2a1  jz      short loc_1800CB27C
0x1800cb2a3  mov     edx, [rbx+0D0h]
0x1800cb2a9  add     edx, ebp
0x1800cb2ab  mov     ecx, edx
0x1800cb2ad  and     ecx, ebp
0x1800cb2af  neg     ecx
0x1800cb2b1  sbb     eax, eax
0x1800cb2b3  and     eax, edx
0x1800cb2b5  xchg    eax, [rdi]
0x1800cb2b7  mov     rcx, [rsi+38h]; hObject
0x1800cb2bb  call    cs:__imp_CloseHandle
0x1800cb2c2  nop     dword ptr [rax+rax+00h]
0x1800cb2c7  mov     rcx, [rsi+30h]
0x1800cb2cb  xor     edx, edx; fCancelPendingCallbacks
0x1800cb2cd  mov     rcx, [rcx]; pio
0x1800cb2d0  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800cb2d7  nop     dword ptr [rax+rax+00h]
0x1800cb2dc  mov     rcx, [rsi+30h]; this
0x1800cb2e0  test    rcx, rcx
0x1800cb2e3  jz      short loc_1800CB2EA
0x1800cb2e5  call    ??_GRPC_THREAD_POOL_IO@@QEAAPEAXI@Z; RPC_THREAD_POOL_IO::`scalar deleting destructor'(uint)
0x1800cb2ea  mov     rcx, rsi; lpMem
0x1800cb2ed  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800cb2f2  jmp     loc_1800CB26C
0x1800cb2f7  mov     ecx, [rbx+0D0h]
0x1800cb2fd  add     ecx, ebp
0x1800cb2ff  mov     eax, ecx
0x1800cb301  and     eax, ebp
0x1800cb303  mov     rbx, [rsp+38h+arg_8]
0x1800cb308  neg     eax
0x1800cb30a  mov     rbp, [rsp+38h+arg_10]
0x1800cb30f  sbb     edx, edx
0x1800cb311  and     edx, ecx
0x1800cb313  xchg    edx, [rdi]
0x1800cb315  add     rsp, 20h
0x1800cb319  pop     r14
0x1800cb31b  pop     rdi
0x1800cb31c  pop     rsi
0x1800cb31d  retn
```
