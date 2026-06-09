# LRPC_SCALL::SaveClientToken(void * *)

- ea: `0x180070fec`
- end: `0x180071112`
- name: `?SaveClientToken@LRPC_SCALL@@QEAAJPEAPEAX@Z`
- size: `294`
- prototype: `__int64 __fastcall(LRPC_SCALL *this, void **)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180070278`
- `0x180087400`
- `0x1800ab0c8`

## callees

- `0x1800293c4`
- `0x1800295d8`
- `0x180070fec`
- `0x1800718e0`
- `0x180071d4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071070`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180071055`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180071055`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007103c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007103c`

## pseudocode

```c
__int64 __fastcall LRPC_SCALL::SaveClientToken(LRPC_SCALL *this, void **a2)
{
  unsigned int v4; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned __int16 v7; // r8
  void *v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = 0;
  v4 = CaptureThreadToken(&v9, 0);
  if ( !v4 )
  {
    v4 = LRPC_SASSOCIATION::ImpersonateClient(*((LRPC_SASSOCIATION **)this + 38), *((struct _PORT_MESSAGE **)this + 55));
    if ( v4 )
    {
      v4 = 1749;
      v7 = 1232;
      goto LABEL_13;
    }
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, a2) )
      goto LABEL_14;
    *a2 = 0;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError == 1347 )
      goto LABEL_14;
    RpcpErrorAddRecord(2u, LastError, 0x4CEu, 0, 0);
    if ( v4 != 8 )
    {
      if ( v4 == 1008 )
      {
        v4 = 5;
        goto LABEL_10;
      }
      if ( v4 != 1450 && v4 != 1816 )
        goto LABEL_10;
    }
    v4 = 14;
LABEL_10:
    v7 = 1231;
LABEL_13:
    RpcpErrorAddRecord(2u, v4, v7, 0, 0);
LABEL_14:
    RestoreOldThreadToken(v9);
  }
  return v4;
}

```

## disassembly

```asm
0x180070fec  mov     rax, rsp
0x180070fef  mov     [rax+8], rbx
0x180070ff3  mov     [rax+10h], rsi
0x180070ff7  push    rdi
0x180070ff8  sub     rsp, 30h
0x180070ffc  mov     rsi, rdx
0x180070fff  mov     qword ptr [rax+18h], 0
0x180071007  mov     rdi, rcx
0x18007100a  xor     edx, edx; int
0x18007100c  lea     rcx, [rax+18h]; TokenHandle
0x180071010  call    ?CaptureThreadToken@@YAJPEAPEAXH@Z; CaptureThreadToken(void * *,int)
0x180071015  mov     ebx, eax
0x180071017  test    eax, eax
0x180071019  jnz     loc_1800710FF
0x18007101f  mov     rdx, [rdi+1B8h]; struct _PORT_MESSAGE *
0x180071026  mov     rcx, [rdi+130h]; this
0x18007102d  call    ?ImpersonateClient@LRPC_SASSOCIATION@@QEAAJPEAU_PORT_MESSAGE@@@Z; LRPC_SASSOCIATION::ImpersonateClient(_PORT_MESSAGE *)
0x180071032  mov     ebx, eax
0x180071034  test    eax, eax
0x180071036  jnz     loc_1800710D3
0x18007103c  call    cs:__imp_GetCurrentThread
0x180071043  nop     dword ptr [rax+rax+00h]
0x180071048  mov     r9, rsi; TokenHandle
0x18007104b  lea     edx, [rbx+0Ch]; DesiredAccess
0x18007104e  mov     rcx, rax; ThreadHandle
0x180071051  lea     r8d, [rbx+1]; OpenAsSelf
0x180071055  call    cs:__imp_OpenThreadToken
0x18007105c  nop     dword ptr [rax+rax+00h]
0x180071061  test    eax, eax
0x180071063  jnz     loc_1800710F5
0x180071069  mov     qword ptr [rsi], 0
0x180071070  call    cs:__imp_GetLastError
0x180071077  nop     dword ptr [rax+rax+00h]
0x18007107c  mov     ebx, eax
0x18007107e  cmp     eax, 543h
0x180071083  jz      short loc_1800710F5
0x180071085  xor     r9d, r9d; int
0x180071088  mov     [rsp+38h+var_18], 0; struct tagParam *
0x180071091  mov     r8d, 4CEh; unsigned __int16
0x180071097  mov     edx, eax; int
0x180071099  lea     ecx, [r9+2]; unsigned int
0x18007109d  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800710a2  cmp     ebx, 8
0x1800710a5  jz      short loc_1800710BF
0x1800710a7  cmp     ebx, 3F0h
0x1800710ad  jz      short loc_1800710CC
0x1800710af  cmp     ebx, 5AAh
0x1800710b5  jz      short loc_1800710BF
0x1800710b7  cmp     ebx, 718h
0x1800710bd  jnz     short loc_1800710C4
0x1800710bf  mov     ebx, 0Eh
0x1800710c4  mov     r8d, 4CFh
0x1800710ca  jmp     short loc_1800710DE
0x1800710cc  mov     ebx, 5
0x1800710d1  jmp     short loc_1800710C4
0x1800710d3  mov     ebx, 6D5h
0x1800710d8  mov     r8d, 4D0h; unsigned __int16
0x1800710de  xor     r9d, r9d; int
0x1800710e1  mov     [rsp+38h+var_18], 0; struct tagParam *
0x1800710ea  mov     edx, ebx; int
0x1800710ec  lea     ecx, [r9+2]; unsigned int
0x1800710f0  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800710f5  mov     rcx, [rsp+38h+arg_10]; void *
0x1800710fa  call    ?RestoreOldThreadToken@@YAXPEAX@Z; RestoreOldThreadToken(void *)
0x1800710ff  mov     rsi, [rsp+38h+arg_8]
0x180071104  mov     eax, ebx
0x180071106  mov     rbx, [rsp+38h+arg_0]
0x18007110b  add     rsp, 30h
0x18007110f  pop     rdi
0x180071110  retn
```
