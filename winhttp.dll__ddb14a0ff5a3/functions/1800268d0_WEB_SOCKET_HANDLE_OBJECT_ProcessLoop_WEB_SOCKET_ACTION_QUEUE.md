# WEB_SOCKET_HANDLE_OBJECT::ProcessLoop(_WEB_SOCKET_ACTION_QUEUE)

- ea: `0x1800268d0`
- end: `0x180026b6a`
- name: `?ProcessLoop@WEB_SOCKET_HANDLE_OBJECT@@AEAAKW4_WEB_SOCKET_ACTION_QUEUE@@@Z`
- size: `666`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180027334`
- `0x1800273d4`
- `0x180027514`
- `0x180028768`
- `0x1800b0b60`
- `0x1800c6024`
- `0x1800c6ae8`
- `0x1800c6ca8`

## callees

- `0x1800268d0`
- `0x180026b70`
- `0x180026bf8`
- `0x180026d14`
- `0x180026f88`
- `0x18007f184`
- `0x18007f23c`
- `0x180098f1c`
- `0x18009a7d4`
- `0x1800a1d10`
- `0x1800c6280`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026a4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026aae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026b4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026a4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026aae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026b4b`
- `websocket!WebSocketGetAction` at `0x180026966`
- `websocket!WebSocketGetAction` at `0x180026966`
- `websocket!WebSocketCompleteAction` at `0x1800269fa`
- `websocket!WebSocketCompleteAction` at `0x180026a33`
- `websocket!WebSocketCompleteAction` at `0x1800269fa`
- `websocket!WebSocketCompleteAction` at `0x180026a33`

## pseudocode

```c
__int64 __fastcall WEB_SOCKET_HANDLE_OBJECT::ProcessLoop(__int64 a1, unsigned int a2)
{
  __int64 *v4; // rcx
  __int64 v5; // rcx
  int Action; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned int v10; // eax
  unsigned int v11; // [rsp+40h] [rbp-9h] BYREF
  void *v12; // [rsp+48h] [rbp-1h] BYREF
  __int64 v13; // [rsp+50h] [rbp+7h] BYREF
  int v14; // [rsp+58h] [rbp+Fh] BYREF
  unsigned int v15; // [rsp+5Ch] [rbp+13h] BYREF
  unsigned int v16; // [rsp+60h] [rbp+17h] BYREF
  _OWORD v17[2]; // [rsp+68h] [rbp+1Fh] BYREF

  while ( 1 )
  {
    v4 = *(__int64 **)(a1 + 800);
    v15 = 2;
    v16 = -1;
    v14 = -1;
    v12 = 0;
    memset(v17, 0, sizeof(v17));
    v13 = 0;
    v5 = *v4;
    v11 = 0;
    Action = WebSocketGetAction(v5, a2, v17, &v15, &v14, &v16, &v13, &v12);
    if ( Action >= 0 )
    {
      v7 = 0;
      goto LABEL_3;
    }
    if ( Action != -2147483634 )
    {
      if ( Action == -2147024882 )
      {
        v7 = 8;
        goto LABEL_3;
      }
      if ( Action != -2147024809 && (Action == -2089418751 || Action == -2089418750) )
      {
        v7 = 12152;
        goto LABEL_3;
      }
    }
    v7 = 12004;
LABEL_3:
    if ( !v14 )
      break;
    if ( v7 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 816));
      WEB_SOCKET_HANDLE_OBJECT::LockedAbortConnection((WEB_SOCKET_HANDLE_OBJECT *)a1, v7);
    }
    if ( v14 == 1 )
    {
      if ( a2 == 2 )
        v8 = WEB_SOCKET_HANDLE_OBJECT::QueueSendOperation(
               (WEB_SOCKET_HANDLE_OBJECT *)a1,
               v12,
               (union _WEB_SOCKET_BUFFER *)v17,
               v15);
      else
        v8 = WEB_SOCKET_HANDLE_OBJECT::BeginSendBytes(
               (WEB_SOCKET_HANDLE_OBJECT *)a1,
               v12,
               (union _WEB_SOCKET_BUFFER *)v17,
               v15,
               &v11);
LABEL_10:
      v7 = v8;
      goto LABEL_11;
    }
    if ( v14 != 2 )
    {
      if ( v14 == 3 )
      {
        v8 = WEB_SOCKET_HANDLE_OBJECT::BeginReceiveBytes(
               (WEB_SOCKET_HANDLE_OBJECT *)a1,
               v12,
               (union _WEB_SOCKET_BUFFER *)v17,
               v15,
               &v11);
      }
      else
      {
        if ( v14 != 4 )
        {
          v7 = 12004;
LABEL_19:
          WebSocketCompleteAction(**(_QWORD **)(a1 + 800), v12, v11);
          goto LABEL_12;
        }
        v8 = WEB_SOCKET_HANDLE_OBJECT::EndBackgroundReceive(a1, v12, v16, v17);
      }
      goto LABEL_10;
    }
    if ( !v13 )
    {
      if ( *(_DWORD *)(a1 + 612) )
        v10 = WEB_SOCKET_HANDLE_OBJECT::EndShutdown((WEB_SOCKET_HANDLE_OBJECT *)a1, v12);
      else
        v10 = WEB_SOCKET_HANDLE_OBJECT::EndSend((WEB_SOCKET_HANDLE_OBJECT *)a1, v12);
      v7 = v10;
    }
    if ( v13 == 2 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 816));
      *(_DWORD *)(a1 + 496) = 2;
      WEB_SOCKET_HANDLE_OBJECT::EndClose((WEB_SOCKET_HANDLE_OBJECT *)a1);
    }
LABEL_11:
    if ( v7 != 997 )
      goto LABEL_19;
LABEL_12:
    if ( v14 == 4 )
      v7 = WEB_SOCKET_HANDLE_OBJECT::BeginBackgroundReceiveInline((WEB_SOCKET_HANDLE_OBJECT *)a1);
    if ( v7 && v7 != 997 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 816));
      WEB_SOCKET_HANDLE_OBJECT::LockedAbortConnection((WEB_SOCKET_HANDLE_OBJECT *)a1, v7);
    }
    if ( !v14 )
      return v7;
  }
  WebSocketCompleteAction(**(_QWORD **)(a1 + 800), v12, 0);
  return v7;
}

```

## disassembly

```asm
0x1800268d0  mov     [rsp-8+arg_10], rbx
0x1800268d5  push    rbp
0x1800268d6  push    rsi
0x1800268d7  push    rdi
0x1800268d8  lea     rbp, [rsp-47h]
0x1800268dd  sub     rsp, 90h
0x1800268e4  mov     rax, cs:__security_cookie
0x1800268eb  xor     rax, rsp
0x1800268ee  mov     [rbp+57h+var_18], rax
0x1800268f2  mov     esi, edx
0x1800268f4  mov     rdi, rcx
0x1800268f7  mov     rcx, [rdi+320h]
0x1800268fe  lea     rax, [rbp+57h+var_58]
0x180026902  mov     [rsp+0A0h+var_68], rax
0x180026907  lea     r9, [rbp+57h+var_44]
0x18002690b  xorps   xmm0, xmm0
0x18002690e  mov     [rbp+57h+var_44], 2
0x180026915  lea     rax, [rbp+57h+var_50]
0x180026919  mov     [rbp+57h+var_40], 0FFFFFFFFh
0x180026920  mov     [rsp+0A0h+var_70], rax
0x180026925  lea     r8, [rbp+57h+var_38]
0x180026929  lea     rax, [rbp+57h+var_40]
0x18002692d  mov     [rbp+57h+var_48], 0FFFFFFFFh
0x180026934  mov     [rsp+0A0h+var_78], rax
0x180026939  mov     edx, esi
0x18002693b  lea     rax, [rbp+57h+var_48]
0x18002693f  mov     [rbp+57h+var_58], 0
0x180026947  movups  [rbp+57h+var_38], xmm0
0x18002694b  mov     [rbp+57h+var_50], 0
0x180026953  movups  [rbp+57h+var_28], xmm0
0x180026957  mov     rcx, [rcx]
0x18002695a  mov     [rsp+0A0h+var_80], rax
0x18002695f  mov     [rbp+57h+var_60], 0
0x180026966  call    cs:__imp_WebSocketGetAction
0x18002696c  test    eax, eax
0x18002696e  js      loc_180026B03
0x180026974  xor     ebx, ebx
0x180026976  cmp     [rbp+57h+var_48], 0
0x18002697a  jz      short loc_1800269E9
0x18002697c  test    ebx, ebx
0x18002697e  jnz     loc_180026B44
0x180026984  mov     ecx, [rbp+57h+var_48]
0x180026987  sub     ecx, 1
0x18002698a  jz      loc_180026ACB
0x180026990  sub     ecx, 1
0x180026993  jz      loc_180026A7E
0x180026999  sub     ecx, 1
0x18002699c  jnz     loc_180026A5C
0x1800269a2  mov     r9d, [rbp+57h+var_44]; unsigned int
0x1800269a6  lea     rax, [rbp+57h+var_60]
0x1800269aa  mov     rdx, [rbp+57h+var_58]; void *
0x1800269ae  lea     r8, [rbp+57h+var_38]; union _WEB_SOCKET_BUFFER *
0x1800269b2  mov     rcx, rdi; this
0x1800269b5  mov     [rsp+0A0h+var_80], rax; unsigned int *
0x1800269ba  call    ?BeginReceiveBytes@WEB_SOCKET_HANDLE_OBJECT@@AEAAKPEAXPEAT_WEB_SOCKET_BUFFER@@KPEAK@Z; WEB_SOCKET_HANDLE_OBJECT::BeginReceiveBytes(void *,_WEB_SOCKET_BUFFER *,ulong,ulong *)
0x1800269bf  mov     ebx, eax
0x1800269c1  cmp     ebx, 3E5h
0x1800269c7  jnz     short loc_180026A21
0x1800269c9  cmp     [rbp+57h+var_48], 4
0x1800269cd  jnz     short loc_1800269D9
0x1800269cf  mov     rcx, rdi; this
0x1800269d2  call    ?BeginBackgroundReceiveInline@WEB_SOCKET_HANDLE_OBJECT@@AEAAKXZ; WEB_SOCKET_HANDLE_OBJECT::BeginBackgroundReceiveInline(void)
0x1800269d7  mov     ebx, eax
0x1800269d9  test    ebx, ebx
0x1800269db  jnz     short loc_180026A3B
0x1800269dd  cmp     [rbp+57h+var_48], 0
0x1800269e1  jnz     loc_1800268F7
0x1800269e7  jmp     short loc_180026A00
0x1800269e9  mov     rcx, [rdi+320h]
0x1800269f0  xor     r8d, r8d
0x1800269f3  mov     rdx, [rbp+57h+var_58]
0x1800269f7  mov     rcx, [rcx]
0x1800269fa  call    cs:__imp_WebSocketCompleteAction
0x180026a00  mov     eax, ebx
0x180026a02  mov     rcx, [rbp+57h+var_18]
0x180026a06  xor     rcx, rsp; StackCookie
0x180026a09  call    __security_check_cookie
0x180026a0e  mov     rbx, [rsp+0A0h+arg_10]
0x180026a16  add     rsp, 90h
0x180026a1d  pop     rdi
0x180026a1e  pop     rsi
0x180026a1f  pop     rbp
0x180026a20  retn
0x180026a21  mov     rcx, [rdi+320h]
0x180026a28  mov     r8d, [rbp+57h+var_60]
0x180026a2c  mov     rdx, [rbp+57h+var_58]
0x180026a30  mov     rcx, [rcx]
0x180026a33  call    cs:__imp_WebSocketCompleteAction
0x180026a39  jmp     short loc_1800269C9
0x180026a3b  cmp     ebx, 3E5h
0x180026a41  jz      short loc_1800269DD
0x180026a43  lea     rcx, [rdi+330h]; lpCriticalSection
0x180026a4a  call    cs:__imp_EnterCriticalSection
0x180026a50  mov     edx, ebx; unsigned int
0x180026a52  mov     rcx, rdi; this
0x180026a55  call    ?LockedAbortConnection@WEB_SOCKET_HANDLE_OBJECT@@AEAAXK@Z; WEB_SOCKET_HANDLE_OBJECT::LockedAbortConnection(ulong)
0x180026a5a  jmp     short loc_1800269DD
0x180026a5c  cmp     ecx, 1
0x180026a5f  jnz     loc_180026B60
0x180026a65  mov     r8d, [rbp+57h+var_40]
0x180026a69  lea     r9, [rbp+57h+var_38]
0x180026a6d  mov     rdx, [rbp+57h+var_58]
0x180026a71  mov     rcx, rdi
0x180026a74  call    ?EndBackgroundReceive@WEB_SOCKET_HANDLE_OBJECT@@AEAAKPEAXW4_WEB_SOCKET_BUFFER_TYPE@@PEAT_WEB_SOCKET_BUFFER@@@Z; WEB_SOCKET_HANDLE_OBJECT::EndBackgroundReceive(void *,_WEB_SOCKET_BUFFER_TYPE,_WEB_SOCKET_BUFFER *)
0x180026a79  jmp     loc_1800269BF
0x180026a7e  cmp     [rbp+57h+var_50], 0
0x180026a83  jnz     short loc_180026A9C
0x180026a85  cmp     dword ptr [rdi+264h], 0
0x180026a8c  mov     rcx, rdi; this
0x180026a8f  mov     rdx, [rbp+57h+var_58]; void *
0x180026a93  jz      short loc_180026AF2
0x180026a95  call    ?EndShutdown@WEB_SOCKET_HANDLE_OBJECT@@AEAAKPEAX@Z; WEB_SOCKET_HANDLE_OBJECT::EndShutdown(void *)
0x180026a9a  mov     ebx, eax
0x180026a9c  cmp     [rbp+57h+var_50], 2
0x180026aa1  jnz     loc_1800269C1
0x180026aa7  lea     rcx, [rdi+330h]; lpCriticalSection
0x180026aae  call    cs:__imp_EnterCriticalSection
0x180026ab4  mov     rcx, rdi; this
0x180026ab7  mov     dword ptr [rdi+1F0h], 2
0x180026ac1  call    ?EndClose@WEB_SOCKET_HANDLE_OBJECT@@AEAAHXZ; WEB_SOCKET_HANDLE_OBJECT::EndClose(void)
0x180026ac6  jmp     loc_1800269C1
0x180026acb  mov     r9d, [rbp+57h+var_44]; unsigned int
0x180026acf  lea     r8, [rbp+57h+var_38]; union _WEB_SOCKET_BUFFER *
0x180026ad3  mov     rdx, [rbp+57h+var_58]; void *
0x180026ad7  mov     rcx, rdi; this
0x180026ada  cmp     esi, 2
0x180026add  jz      short loc_180026AF9
0x180026adf  lea     rax, [rbp+57h+var_60]
0x180026ae3  mov     [rsp+0A0h+var_80], rax; unsigned int *
0x180026ae8  call    ?BeginSendBytes@WEB_SOCKET_HANDLE_OBJECT@@AEAAKPEAXPEAT_WEB_SOCKET_BUFFER@@KPEAK@Z; WEB_SOCKET_HANDLE_OBJECT::BeginSendBytes(void *,_WEB_SOCKET_BUFFER *,ulong,ulong *)
0x180026aed  jmp     loc_1800269BF
0x180026af2  call    ?EndSend@WEB_SOCKET_HANDLE_OBJECT@@AEAAKPEAX@Z; WEB_SOCKET_HANDLE_OBJECT::EndSend(void *)
0x180026af7  jmp     short loc_180026A9A
0x180026af9  call    ?QueueSendOperation@WEB_SOCKET_HANDLE_OBJECT@@AEAAKPEAXPEAT_WEB_SOCKET_BUFFER@@K@Z; WEB_SOCKET_HANDLE_OBJECT::QueueSendOperation(void *,_WEB_SOCKET_BUFFER *,ulong)
0x180026afe  jmp     loc_1800269BF
0x180026b03  cmp     eax, 8000000Eh
0x180026b08  jz      short loc_180026B3A
0x180026b0a  cmp     eax, 8007000Eh
0x180026b0f  jz      short loc_180026B30
0x180026b11  cmp     eax, 80070057h
0x180026b16  jz      short loc_180026B3A
0x180026b18  cmp     eax, 83760001h
0x180026b1d  jz      short loc_180026B26
0x180026b1f  cmp     eax, 83760002h
0x180026b24  jnz     short loc_180026B3A
0x180026b26  mov     ebx, 2F78h
0x180026b2b  jmp     loc_180026976
0x180026b30  mov     ebx, 8
0x180026b35  jmp     loc_180026976
0x180026b3a  mov     ebx, 2EE4h
0x180026b3f  jmp     loc_180026976
0x180026b44  lea     rcx, [rdi+330h]; lpCriticalSection
0x180026b4b  call    cs:__imp_EnterCriticalSection
0x180026b51  mov     edx, ebx; unsigned int
0x180026b53  mov     rcx, rdi; this
0x180026b56  call    ?LockedAbortConnection@WEB_SOCKET_HANDLE_OBJECT@@AEAAXK@Z; WEB_SOCKET_HANDLE_OBJECT::LockedAbortConnection(ulong)
0x180026b5b  jmp     loc_180026984
0x180026b60  mov     ebx, 2EE4h
0x180026b65  jmp     loc_180026A21
```
