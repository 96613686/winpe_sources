# HTTP2SocketTransportChannel::Send(HTTP2SendContext *)

- ea: `0x180017c20`
- end: `0x180017d86`
- name: `?Send@HTTP2SocketTransportChannel@@UEAAJPEAVHTTP2SendContext@@@Z`
- size: `358`
- prototype: `__int64 __fastcall(HTTP2SocketTransportChannel *__hidden this, struct HTTP2SendContext *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017b20`

## callees

- `0x180017c20`
- `0x180025010`

## import_xrefs

- `KERNEL32!CancelThreadpoolIo` at `0x180017d11`
- `KERNEL32!CancelThreadpoolIo` at `0x180017d11`
- `KERNEL32!StartThreadpoolIo` at `0x180017c82`
- `KERNEL32!StartThreadpoolIo` at `0x180017c82`
- `RPCRT4!I_RpcLogEvent` at `0x180017c5b`
- `RPCRT4!I_RpcLogEvent` at `0x180017d3c`
- `RPCRT4!I_RpcLogEvent` at `0x180017d6e`
- `RPCRT4!I_RpcLogEvent` at `0x180017c5b`
- `RPCRT4!I_RpcLogEvent` at `0x180017d3c`
- `RPCRT4!I_RpcLogEvent` at `0x180017d6e`

## pseudocode

```c
__int64 __fastcall HTTP2SocketTransportChannel::Send(HTTP2SocketTransportChannel *this, struct HTTP2SendContext *a2)
{
  struct HTTP2SendContext *v2; // rdi
  HTTP2SocketTransportChannel *v3; // rbx
  HTTP2SocketTransportChannel *v4; // r8
  __int64 v5; // rdx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v12; // [rsp+20h] [rbp-28h]
  int v13; // [rsp+50h] [rbp+8h] BYREF

  v2 = a2;
  v3 = this;
  v4 = this;
  v12 = (int)a2;
  LOBYTE(a2) = 111;
  v13 = 0;
  LOBYTE(this) = 50;
  I_RpcLogEvent(this, a2, v4, 16842753, v12, 0, 0);
  *((_QWORD *)v2 + 4) = 0;
  *(_QWORD *)v2 = *((_QWORD *)v3 + 4);
  StartThreadpoolIo(**(PTP_IO **)(*((_QWORD *)v3 + 4) + 144LL));
  if ( *((_DWORD *)v2 + 22) != 2
    || (*((_BYTE *)v2 + 92) & 0x58) != 0
    || (v5 = *((_QWORD *)v3 + 4), (unsigned int)(*(_DWORD *)(v5 + 12) - 13) <= 1) )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int *, __int64))(**((_QWORD **)v3 + 4) + 32LL))(
           *((_QWORD *)v3 + 4),
           *(_QWORD *)(*((_QWORD *)v3 + 4) + 40LL),
           *((_QWORD *)v2 + 6),
           *((unsigned int *)v2 + 14),
           &v13,
           (__int64)v2 + 8);
  }
  else
  {
    v6 = (*((__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int *, __int64))pRuntimeImportTable + 53))(
           v5 + 480,
           *(_QWORD *)(v5 + 40),
           *((_QWORD *)v2 + 6),
           *((unsigned int *)v2 + 14),
           &v13,
           (__int64)v2 + 8);
  }
  if ( !v6 || v6 == 997 )
  {
    LOBYTE(v7) = 111;
    LOBYTE(v8) = 50;
    I_RpcLogEvent(v8, v7, v3, 65537, 0, 0, 0);
    return 0;
  }
  else
  {
    CancelThreadpoolIo(**(PTP_IO **)(*((_QWORD *)v3 + 4) + 144LL));
    LOBYTE(v9) = 111;
    LOBYTE(v10) = 50;
    I_RpcLogEvent(v10, v9, v3, 65537, -1073606646, 0, 0);
    return 3221360650LL;
  }
}

```

## disassembly

```asm
0x180017c20  mov     rax, rsp
0x180017c23  mov     [rax+10h], rbx
0x180017c27  mov     [rax+18h], rsi
0x180017c2b  push    rdi
0x180017c2c  sub     rsp, 40h
0x180017c30  mov     rdi, rdx
0x180017c33  mov     dword ptr [rax-18h], 0
0x180017c3a  mov     rbx, rcx
0x180017c3d  mov     dword ptr [rax-20h], 0
0x180017c44  mov     r8, rcx
0x180017c47  mov     [rax-28h], edi
0x180017c4a  mov     dl, 6Fh ; 'o'
0x180017c4c  mov     dword ptr [rax+8], 0
0x180017c53  mov     cl, 32h ; '2'
0x180017c55  mov     r9d, 1010001h
0x180017c5b  call    cs:__imp_I_RpcLogEvent
0x180017c61  lea     rsi, [rdi+8]
0x180017c65  mov     qword ptr [rsi+18h], 0
0x180017c6d  mov     rax, [rbx+20h]
0x180017c71  mov     [rdi], rax
0x180017c74  mov     rax, [rbx+20h]
0x180017c78  mov     rcx, [rax+90h]
0x180017c7f  mov     rcx, [rcx]; pio
0x180017c82  call    cs:__imp_StartThreadpoolIo
0x180017c88  cmp     dword ptr [rdi+58h], 2
0x180017c8c  jnz     short loc_180017CCD
0x180017c8e  test    byte ptr [rdi+5Ch], 58h
0x180017c92  jnz     short loc_180017CCD
0x180017c94  mov     rdx, [rbx+20h]
0x180017c98  mov     eax, [rdx+0Ch]
0x180017c9b  sub     eax, 0Dh
0x180017c9e  cmp     eax, 1
0x180017ca1  jbe     short loc_180017CCD
0x180017ca3  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180017caa  lea     r8, [rsp+48h+arg_0]
0x180017caf  lea     rcx, [rdx+1E0h]
0x180017cb6  mov     [rsp+48h+var_20], rsi
0x180017cbb  mov     rdx, [rdx+28h]
0x180017cbf  mov     [rsp+48h+var_28], r8
0x180017cc4  mov     rax, [rax+1A8h]
0x180017ccb  jmp     short loc_180017CEB
0x180017ccd  mov     rcx, [rbx+20h]
0x180017cd1  lea     rdx, [rsp+48h+arg_0]
0x180017cd6  mov     [rsp+48h+var_20], rsi
0x180017cdb  mov     [rsp+48h+var_28], rdx
0x180017ce0  mov     rax, [rcx]
0x180017ce3  mov     rdx, [rcx+28h]
0x180017ce7  mov     rax, [rax+20h]
0x180017ceb  mov     r9d, [rdi+38h]
0x180017cef  mov     r8, [rdi+30h]
0x180017cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cf8  test    eax, eax
0x180017cfa  jz      short loc_180017D49
0x180017cfc  cmp     eax, 3E5h
0x180017d01  jz      short loc_180017D49
0x180017d03  mov     rax, [rbx+20h]
0x180017d07  mov     rcx, [rax+90h]
0x180017d0e  mov     rcx, [rcx]; pio
0x180017d11  call    cs:__imp_CancelThreadpoolIo
0x180017d17  mov     [rsp+48h+var_18], 0
0x180017d1f  mov     r9d, 10001h
0x180017d25  mov     dword ptr [rsp+48h+var_20], 0
0x180017d2d  mov     r8, rbx
0x180017d30  mov     dl, 6Fh ; 'o'
0x180017d32  mov     dword ptr [rsp+48h+var_28], 0C002100Ah
0x180017d3a  mov     cl, 32h ; '2'
0x180017d3c  call    cs:__imp_I_RpcLogEvent
0x180017d42  mov     eax, 0C002100Ah
0x180017d47  jmp     short loc_180017D76
0x180017d49  mov     [rsp+48h+var_18], 0
0x180017d51  mov     r9d, 10001h
0x180017d57  mov     dword ptr [rsp+48h+var_20], 0
0x180017d5f  mov     r8, rbx
0x180017d62  mov     dl, 6Fh ; 'o'
0x180017d64  mov     dword ptr [rsp+48h+var_28], 0
0x180017d6c  mov     cl, 32h ; '2'
0x180017d6e  call    cs:__imp_I_RpcLogEvent
0x180017d74  xor     eax, eax
0x180017d76  mov     rbx, [rsp+48h+arg_8]
0x180017d7b  mov     rsi, [rsp+48h+arg_10]
0x180017d80  add     rsp, 40h
0x180017d84  pop     rdi
0x180017d85  retn
```
