# HTTP2WinHttpTransportChannel::DirectReceiveComplete(uchar * *,ulong *,void * *)

- ea: `0x180008d20`
- end: `0x180009027`
- name: `?DirectReceiveComplete@HTTP2WinHttpTransportChannel@@QEAAJPEAPEAEPEAKPEAPEAX@Z`
- size: `775`
- prototype: `__int64 __fastcall(HTTP2WinHttpTransportChannel *__hidden this, unsigned __int8 **, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000bb50`

## callees

- `0x180005428`
- `0x180008d20`
- `0x180009d58`
- `0x180013630`
- `0x18001e4a4`
- `0x180025010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180008ed9`
- `KERNEL32!WaitForSingleObject` at `0x180008ed9`
- `KERNEL32!ResetEvent` at `0x180008e86`
- `KERNEL32!ResetEvent` at `0x180008e86`
- `RPCRT4!I_RpcLogEvent` at `0x180008d6e`
- `RPCRT4!I_RpcLogEvent` at `0x180008eaa`
- `RPCRT4!I_RpcLogEvent` at `0x180009007`
- `RPCRT4!I_RpcLogEvent` at `0x180008d6e`
- `RPCRT4!I_RpcLogEvent` at `0x180008eaa`
- `RPCRT4!I_RpcLogEvent` at `0x180009007`
- `RPCRT4!I_RpcTransGetThreadEventThreadOptional` at `0x180008e47`
- `RPCRT4!I_RpcTransGetThreadEventThreadOptional` at `0x180008e47`
- `RPCRT4!I_RpcTransGetThreadEvent` at `0x180008e76`
- `RPCRT4!I_RpcTransGetThreadEvent` at `0x180008e76`
- `WINHTTP!WinHttpReadData` at `0x180008ec0`
- `WINHTTP!WinHttpReadData` at `0x180008ec0`

## pseudocode

```c
__int64 __fastcall HTTP2WinHttpTransportChannel::DirectReceiveComplete(
        HTTP2WinHttpTransportChannel *this,
        unsigned __int8 **a2,
        unsigned int *a3,
        void **a4)
{
  unsigned int *v4; // r12
  unsigned __int8 **v7; // r15
  HTTP2WinHttpTransportChannel *v8; // rdi
  HTTP2WinHttpTransportChannel *v9; // r8
  unsigned int *v10; // r14
  __int64 v11; // r8
  unsigned int v12; // ebx
  DWORD *v13; // rsi
  unsigned int v14; // ecx
  __int64 *v15; // r15
  bool v16; // zf
  __int64 v17; // rcx
  int v18; // eax
  void *ThreadEvent; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int v22; // ebx
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v26; // [rsp+20h] [rbp-58h]
  unsigned int v27; // [rsp+80h] [rbp+8h] BYREF
  unsigned __int8 **v28; // [rsp+88h] [rbp+10h]
  __int64 v29; // [rsp+98h] [rbp+20h] BYREF

  v28 = a2;
  v4 = (unsigned int *)((char *)this + 84);
  v7 = a2;
  v27 = 0;
  v8 = this;
  v29 = 0;
  v9 = this;
  v26 = *((_DWORD *)this + 21);
  LOBYTE(a2) = 111;
  LOBYTE(this) = 50;
  I_RpcLogEvent(this, a2, v9, 17039381, v26, 0, 0);
  v10 = (unsigned int *)((char *)v8 + 40);
  v11 = *((unsigned int *)v8 + 11);
  *a4 = *(void **)(*((_QWORD *)v8 + 3) + 48LL);
  if ( (_DWORD)v11 && (_DWORD)v11 == *v10 )
  {
    *a3 = *v10;
    *((_DWORD *)v8 + 11) = 0;
    goto LABEL_24;
  }
  v12 = *v4;
  v13 = (DWORD *)((char *)v8 + 80);
  if ( *v4 )
    goto LABEL_22;
  if ( *v13 )
  {
    v14 = *v13;
    v15 = (__int64 *)((char *)v8 + 32);
    v16 = *((_QWORD *)v8 + 4) == 0;
    *v4 = 1766;
    if ( v16 )
    {
      if ( v14 <= *((_DWORD *)v8 + 12) )
        v14 = *((_DWORD *)v8 + 12);
      *v10 = v14;
      v17 = (*(__int64 (**)(void))pRuntimeImportTable)();
      *v15 = v17;
    }
    else
    {
      if ( *v10 - (unsigned int)v11 >= v14 )
      {
LABEL_16:
        if ( I_RpcTransGetThreadEventThreadOptional() )
        {
          v12 = HTTP2Channel::BeginSimpleSubmitAsync(*((HTTP2Channel **)v8 + 3));
          if ( !v12 )
          {
            ThreadEvent = (void *)I_RpcTransGetThreadEvent();
            *((_QWORD *)v8 + 21) = ThreadEvent;
            ResetEvent(ThreadEvent);
            LOBYTE(v20) = 111;
            LOBYTE(v21) = 50;
            I_RpcLogEvent(v21, v20, *((_QWORD *)v8 + 9), 25755670, *v13, 0, 0);
            WinHttpReadData(*((HINTERNET *)v8 + 9), (LPVOID)(*v15 + *((unsigned int *)v8 + 11)), *v13, 0);
            HTTP2Channel::FinishSubmitAsync(*((HTTP2Channel **)v8 + 3));
            WaitForSingleObject(*((HANDLE *)v8 + 21), 0xFFFFFFFF);
            v12 = *v4;
            *v4 = 1766;
            *((_QWORD *)v8 + 21) = 0;
            if ( v12 )
            {
              (*((void (__fastcall **)(_QWORD))pRuntimeImportTable + 67))(*((_QWORD *)v8 + 11));
              *((_QWORD *)v8 + 11) = 0;
              CompRpcpErrorAddRecord(0xDu, v12, 0x578u);
            }
          }
          goto LABEL_21;
        }
LABEL_17:
        v12 = 14;
        *v13 = 0;
LABEL_21:
        v7 = v28;
        goto LABEL_23;
      }
      v18 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD))pRuntimeImportTable + 34))(
              0,
              (__int64)v8 + 32,
              v11,
              v14 + (unsigned int)v11);
      v17 = *v15;
      if ( v18 )
      {
        (*((void (__fastcall **)(__int64))pRuntimeImportTable + 1))(v17);
        v17 = 0;
        *v15 = 0;
      }
      *v10 = *v13 + *((_DWORD *)v8 + 11);
    }
    if ( !v17 )
      goto LABEL_17;
    goto LABEL_16;
  }
  v12 = -1073606647;
LABEL_22:
  *v4 = 1766;
  (*((void (__fastcall **)(_QWORD))pRuntimeImportTable + 67))(*((_QWORD *)v8 + 11));
  *((_QWORD *)v8 + 11) = 0;
  CompRpcpErrorAddRecord(0xDu, v12, 0x579u);
LABEL_23:
  *a3 = *v13;
  if ( v12 )
  {
    v27 = 0;
    v29 = 0;
    goto LABEL_26;
  }
LABEL_24:
  v12 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, unsigned int *))(**((_QWORD **)v8 + 3) + 144LL))(
          *((_QWORD *)v8 + 3),
          &v29,
          &v27);
LABEL_26:
  v22 = HTTP2FragmentReceiver::ReceiveComplete((__int64 *)v8, v12, 4u, v7, a3);
  (*((void (__fastcall **)(_QWORD, __int64))pRuntimeImportTable + 75))(v27, v29);
  if ( !v22 && !*v7 )
    v22 = -1073606615;
  LOBYTE(v23) = 111;
  LOBYTE(v24) = 50;
  I_RpcLogEvent(v24, v23, v8, 262165, v22, 0, 0);
  return v22;
}

```

## disassembly

```asm
0x180008d20  mov     rax, rsp
0x180008d23  mov     [rax+18h], rbx
0x180008d27  mov     [rax+10h], rdx
0x180008d2b  push    rbp
0x180008d2c  push    rsi
0x180008d2d  push    rdi
0x180008d2e  push    r12
0x180008d30  push    r13
0x180008d32  push    r14
0x180008d34  push    r15
0x180008d36  sub     rsp, 40h
0x180008d3a  xor     ebp, ebp
0x180008d3c  lea     r12, [rcx+54h]
0x180008d40  mov     [rax-48h], ebp
0x180008d43  mov     r13, r8
0x180008d46  mov     [rax-50h], ebp
0x180008d49  mov     rbx, r9
0x180008d4c  mov     r15, rdx
0x180008d4f  mov     [rax+8], ebp
0x180008d52  mov     rdi, rcx
0x180008d55  mov     [rax+20h], rbp
0x180008d59  mov     eax, [r12]
0x180008d5d  mov     r8, rcx
0x180008d60  mov     r9d, 1040015h
0x180008d66  mov     dword ptr [rsp+78h+var_58], eax
0x180008d6a  mov     dl, 6Fh ; 'o'
0x180008d6c  mov     cl, 32h ; '2'
0x180008d6e  call    cs:__imp_I_RpcLogEvent
0x180008d74  mov     rax, [rdi+18h]
0x180008d78  lea     r14, [rdi+28h]
0x180008d7c  mov     r8d, [rdi+2Ch]
0x180008d80  mov     rcx, [rax+30h]
0x180008d84  mov     [rbx], rcx
0x180008d87  test    r8d, r8d
0x180008d8a  jz      short loc_180008DA0
0x180008d8c  mov     eax, [r14]
0x180008d8f  cmp     r8d, eax
0x180008d92  jnz     short loc_180008DA0
0x180008d94  mov     [r13+0], eax
0x180008d98  mov     [rdi+2Ch], ebp
0x180008d9b  jmp     loc_180008F6D
0x180008da0  mov     ebx, [r12]
0x180008da4  lea     rsi, [rdi+50h]
0x180008da8  test    ebx, ebx
0x180008daa  jnz     loc_180008F2D
0x180008db0  cmp     [rsi], ebp
0x180008db2  mov     ebp, 6E6h
0x180008db7  jnz     short loc_180008DC3
0x180008db9  mov     ebx, 0C0021009h
0x180008dbe  jmp     loc_180008F32
0x180008dc3  mov     ecx, [rsi]
0x180008dc5  lea     r15, [rdi+20h]
0x180008dc9  cmp     qword ptr [r15], 0
0x180008dcd  mov     [r12], ebp
0x180008dd1  jnz     short loc_180008DF4
0x180008dd3  cmp     ecx, [rdi+30h]
0x180008dd6  cmovbe  ecx, [rdi+30h]
0x180008dda  mov     [r14], ecx
0x180008ddd  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180008de4  mov     rax, [rax]
0x180008de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dec  mov     rcx, rax
0x180008def  mov     [r15], rax
0x180008df2  jmp     short loc_180008E42
0x180008df4  mov     eax, [r14]
0x180008df7  sub     eax, r8d
0x180008dfa  cmp     eax, ecx
0x180008dfc  jnb     short loc_180008E47
0x180008dfe  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180008e05  lea     r9d, [rcx+r8]
0x180008e09  mov     rdx, r15
0x180008e0c  xor     ecx, ecx
0x180008e0e  mov     rax, [rax+110h]
0x180008e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e1a  mov     rcx, [r15]
0x180008e1d  test    eax, eax
0x180008e1f  jz      short loc_180008E3A
0x180008e21  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180008e28  mov     rax, [rax+8]
0x180008e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e31  xor     ecx, ecx
0x180008e33  mov     qword ptr [r15], 0
0x180008e3a  mov     eax, [rdi+2Ch]
0x180008e3d  add     eax, [rsi]
0x180008e3f  mov     [r14], eax
0x180008e42  test    rcx, rcx
0x180008e45  jz      short loc_180008E52
0x180008e47  call    cs:__imp_I_RpcTransGetThreadEventThreadOptional
0x180008e4d  test    rax, rax
0x180008e50  jnz     short loc_180008E60
0x180008e52  xor     ebp, ebp
0x180008e54  mov     ebx, 0Eh
0x180008e59  mov     [rsi], ebp
0x180008e5b  jmp     loc_180008F23
0x180008e60  mov     rcx, [rdi+18h]; this
0x180008e64  call    ?BeginSimpleSubmitAsync@HTTP2Channel@@QEAAJXZ; HTTP2Channel::BeginSimpleSubmitAsync(void)
0x180008e69  xor     r14d, r14d
0x180008e6c  mov     ebx, eax
0x180008e6e  test    eax, eax
0x180008e70  jnz     loc_180008F21
0x180008e76  call    cs:__imp_I_RpcTransGetThreadEvent
0x180008e7c  mov     rcx, rax; hEvent
0x180008e7f  mov     [rdi+0A8h], rax
0x180008e86  call    cs:__imp_ResetEvent
0x180008e8c  mov     eax, [rsi]
0x180008e8e  mov     r9d, 1890016h
0x180008e94  mov     r8, [rdi+48h]
0x180008e98  mov     dl, 6Fh ; 'o'
0x180008e9a  mov     [rsp+78h+var_48], r14d
0x180008e9f  mov     cl, 32h ; '2'
0x180008ea1  mov     [rsp+78h+var_50], r14d
0x180008ea6  mov     dword ptr [rsp+78h+var_58], eax
0x180008eaa  call    cs:__imp_I_RpcLogEvent
0x180008eb0  mov     edx, [rdi+2Ch]
0x180008eb3  xor     r9d, r9d; lpdwNumberOfBytesRead
0x180008eb6  add     rdx, [r15]; lpBuffer
0x180008eb9  mov     r8d, [rsi]; dwNumberOfBytesToRead
0x180008ebc  mov     rcx, [rdi+48h]; hRequest
0x180008ec0  call    cs:__imp_WinHttpReadData
0x180008ec6  mov     rcx, [rdi+18h]; this
0x180008eca  call    ?FinishSubmitAsync@HTTP2Channel@@QEAAXXZ; HTTP2Channel::FinishSubmitAsync(void)
0x180008ecf  mov     rcx, [rdi+0A8h]; hHandle
0x180008ed6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008ed9  call    cs:__imp_WaitForSingleObject
0x180008edf  mov     ebx, [r12]
0x180008ee3  mov     [r12], ebp
0x180008ee7  xor     ebp, ebp
0x180008ee9  mov     [rdi+0A8h], r14
0x180008ef0  test    ebx, ebx
0x180008ef2  jz      short loc_180008F23
0x180008ef4  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180008efb  mov     rcx, [rdi+58h]
0x180008eff  mov     rax, [rax+218h]
0x180008f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f0b  mov     r8d, 578h; unsigned __int16
0x180008f11  mov     [rdi+58h], rbp
0x180008f15  mov     edx, ebx; unsigned int
0x180008f17  lea     ecx, [rbp+0Dh]; unsigned int
0x180008f1a  call    ?CompRpcpErrorAddRecord@@YAXKKG@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort)
0x180008f1f  jmp     short loc_180008F23
0x180008f21  xor     ebp, ebp
0x180008f23  mov     r15, [rsp+78h+arg_8]
0x180008f2b  jmp     short loc_180008F63
0x180008f2d  mov     ebp, 6E6h
0x180008f32  mov     [r12], ebp
0x180008f36  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180008f3d  mov     rcx, [rdi+58h]
0x180008f41  mov     rax, [rax+218h]
0x180008f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f4d  xor     ebp, ebp
0x180008f4f  mov     r8d, 579h; unsigned __int16
0x180008f55  mov     edx, ebx; unsigned int
0x180008f57  mov     [rdi+58h], rbp
0x180008f5b  lea     ecx, [rbp+0Dh]; unsigned int
0x180008f5e  call    ?CompRpcpErrorAddRecord@@YAXKKG@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort)
0x180008f63  mov     eax, [rsi]
0x180008f65  mov     [r13+0], eax
0x180008f69  test    ebx, ebx
0x180008f6b  jnz     short loc_180008F94
0x180008f6d  mov     rcx, [rdi+18h]
0x180008f71  lea     r8, [rsp+78h+arg_0]
0x180008f79  lea     rdx, [rsp+78h+arg_18]
0x180008f81  mov     rax, [rcx]
0x180008f84  mov     rax, [rax+90h]
0x180008f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f90  mov     ebx, eax
0x180008f92  jmp     short loc_180008FA3
0x180008f94  mov     [rsp+78h+arg_0], ebp
0x180008f9b  mov     [rsp+78h+arg_18], rbp
0x180008fa3  mov     r9, r15
0x180008fa6  mov     [rsp+78h+var_58], r13
0x180008fab  mov     r8d, 4
0x180008fb1  mov     edx, ebx
0x180008fb3  mov     rcx, rdi
0x180008fb6  call    ?ReceiveComplete@HTTP2FragmentReceiver@@UEAAJJW4tagHTTP2TrafficType@@PEAPEAEPEAI@Z; HTTP2FragmentReceiver::ReceiveComplete(long,tagHTTP2TrafficType,uchar * *,uint *)
0x180008fbb  mov     rcx, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180008fc2  mov     ebx, eax
0x180008fc4  mov     rdx, [rsp+78h+arg_18]
0x180008fcc  mov     rax, [rcx+258h]
0x180008fd3  mov     ecx, [rsp+78h+arg_0]
0x180008fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fdf  test    ebx, ebx
0x180008fe1  jnz     short loc_180008FEE
0x180008fe3  cmp     [r15], rbp
0x180008fe6  mov     eax, 0C0021029h
0x180008feb  cmovz   ebx, eax
0x180008fee  mov     [rsp+78h+var_48], ebp
0x180008ff2  mov     r9d, 40015h
0x180008ff8  mov     [rsp+78h+var_50], ebp
0x180008ffc  mov     r8, rdi
0x180008fff  mov     dl, 6Fh ; 'o'
0x180009001  mov     dword ptr [rsp+78h+var_58], ebx
0x180009005  mov     cl, 32h ; '2'
0x180009007  call    cs:__imp_I_RpcLogEvent
0x18000900d  mov     eax, ebx
0x18000900f  mov     rbx, [rsp+78h+arg_10]
0x180009017  add     rsp, 40h
0x18000901b  pop     r15
0x18000901d  pop     r14
0x18000901f  pop     r13
0x180009021  pop     r12
0x180009023  pop     rdi
0x180009024  pop     rsi
0x180009025  pop     rbp
0x180009026  retn
```
