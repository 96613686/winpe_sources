# HTTP2ClientChannel::CheckReceiveCompleteForSync(long,tagHTTP2TrafficType,uchar *,uint)

- ea: `0x180005c50`
- end: `0x180005d10`
- name: `?CheckReceiveCompleteForSync@HTTP2ClientChannel@@UEAAJJW4tagHTTP2TrafficType@@PEAEI@Z`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005c50`
- `0x180025010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180005cf8`
- `KERNEL32!SetEvent` at `0x180005cf8`
- `RPCRT4!I_RpcLogEvent` at `0x180005c9b`
- `RPCRT4!I_RpcLogEvent` at `0x180005c9b`

## pseudocode

```c
__int64 __fastcall HTTP2ClientChannel::CheckReceiveCompleteForSync(__int64 a1, __int64 a2, int a3, __int64 a4, int a5)
{
  __int64 v5; // rbp
  __int64 v7; // rbx
  __int64 v8; // r8
  __int64 v9; // rcx
  void *v10; // rsi

  v5 = (unsigned int)a2;
  v7 = a1;
  if ( a3 == 1 || !*(_QWORD *)(a1 + 96) )
    return 0;
  v8 = a1;
  LOBYTE(a1) = 50;
  LOBYTE(a2) = 111;
  I_RpcLogEvent(a1, a2, v8, 18153489, a4, 0, 0);
  v9 = *(_QWORD *)(v7 + 104);
  *(_QWORD *)(v7 + 80) = a4;
  v10 = *(void **)(v7 + 96);
  *(_DWORD *)(v7 + 88) = a5;
  *(_QWORD *)(v7 + 72) = v5;
  if ( v9 )
  {
    (*((void (**)(void))pRuntimeImportTable + 62))();
    *(_QWORD *)(v7 + 104) = 0;
  }
  *(_QWORD *)(v7 + 104) = (*((__int64 (**)(void))pRuntimeImportTable + 60))();
  _InterlockedExchange((volatile __int32 *)(v7 + 92), 1);
  SetEvent(v10);
  return 3221360681LL;
}

```

## disassembly

```asm
0x180005c50  push    rbx
0x180005c52  push    rbp
0x180005c53  push    rsi
0x180005c54  push    rdi
0x180005c55  sub     rsp, 48h
0x180005c59  mov     edi, 1
0x180005c5e  mov     ebp, edx
0x180005c60  mov     rsi, r9
0x180005c63  mov     rbx, rcx
0x180005c66  cmp     r8d, edi
0x180005c69  jz      loc_180005D05
0x180005c6f  cmp     qword ptr [rcx+60h], 0
0x180005c74  jz      loc_180005D05
0x180005c7a  mov     [rsp+68h+var_38], 0
0x180005c82  mov     r8, rcx
0x180005c85  mov     [rsp+68h+var_40], 0
0x180005c8d  mov     cl, 32h ; '2'
0x180005c8f  mov     r9d, 1150011h
0x180005c95  mov     [rsp+68h+var_48], esi
0x180005c99  mov     dl, 6Fh ; 'o'
0x180005c9b  call    cs:__imp_I_RpcLogEvent
0x180005ca1  mov     rcx, [rbx+68h]
0x180005ca5  mov     eax, [rsp+68h+arg_20]
0x180005cac  mov     [rbx+50h], rsi
0x180005cb0  mov     rsi, [rbx+60h]
0x180005cb4  mov     [rbx+58h], eax
0x180005cb7  mov     [rbx+48h], rbp
0x180005cbb  test    rcx, rcx
0x180005cbe  jz      short loc_180005CDB
0x180005cc0  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180005cc7  mov     rax, [rax+1F0h]
0x180005cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cd3  mov     qword ptr [rbx+68h], 0
0x180005cdb  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180005ce2  mov     rax, [rax+1E0h]
0x180005ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cee  mov     [rbx+68h], rax
0x180005cf2  mov     rcx, rsi; hEvent
0x180005cf5  xchg    edi, [rbx+5Ch]
0x180005cf8  call    cs:__imp_SetEvent
0x180005cfe  mov     eax, 0C0021029h
0x180005d03  jmp     short loc_180005D07
0x180005d05  xor     eax, eax
0x180005d07  add     rsp, 48h
0x180005d0b  pop     rdi
0x180005d0c  pop     rsi
0x180005d0d  pop     rbp
0x180005d0e  pop     rbx
0x180005d0f  retn
```
