# BASE_HTTP2_CONNECTION::ProcessReceiveComplete(ulong,uchar * *,uint *)

- ea: `0x180010f70`
- end: `0x180011098`
- name: `?ProcessReceiveComplete@BASE_HTTP2_CONNECTION@@UEAAJKPEAPEAEPEAI@Z`
- size: `296`
- prototype: `__int64 __fastcall(BASE_HTTP2_CONNECTION *this, __int64, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180010f70`
- `0x180025010`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x180011051`
- `RPCRT4!I_RpcLogEvent` at `0x180011051`

## pseudocode

```c
__int64 __fastcall BASE_HTTP2_CONNECTION::ProcessReceiveComplete(
        BASE_HTTP2_CONNECTION *this,
        __int64 a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  __int64 v7; // rcx
  unsigned int v8; // ebx
  unsigned int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64, _QWORD, _DWORD); // r10

  if ( *((_DWORD *)this + 4) )
  {
    v7 = *((_QWORD *)this + 5);
    goto LABEL_3;
  }
  if ( !(_DWORD)a2 )
  {
    v8 = -1073606648;
    goto LABEL_10;
  }
  v10 = (*((__int64 (__fastcall **)(BASE_HTTP2_CONNECTION *, __int64, unsigned int *))this + 3))(this, a2, a4);
  v8 = v10;
  if ( v10 == -1073606622 )
    return 3221360674LL;
  if ( !v10 )
  {
    v7 = *((_QWORD *)this + 5);
LABEL_3:
    v8 = (*((__int64 (__fastcall **)(__int64))pRuntimeImportTable + 56))(v7);
    if ( v8 == -1073606622 )
      return 3221360674LL;
  }
LABEL_10:
  if ( *((_DWORD *)pRuntimeImportTable + 146)
    && *(_DWORD *)((*((__int64 (**)(void))pRuntimeImportTable + 70))() + 12)
    && !v8
    && (*a3)[2] == 20 )
  {
    v11 = (*((__int64 (**)(void))pRuntimeImportTable + 70))();
    (*(void (__fastcall **)(_QWORD, unsigned int *, unsigned __int8 **))(v11 + 176))(0, a4, a3);
    LOBYTE(v12) = 78;
    LOBYTE(v13) = 79;
    I_RpcLogEvent(v13, v12, *a3, this, *a4, 0, 0);
  }
  v14 = *((_QWORD *)this + 1);
  v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _DWORD))(*(_QWORD *)v14 + 32LL);
  if ( v8 )
    return v15(v14, v8, 4, 0, 0);
  else
    return v15(v14, 0, 4, *a3, *a4);
}

```

## disassembly

```asm
0x180010f70  push    rbx
0x180010f72  push    rsi
0x180010f73  push    rdi
0x180010f74  push    r14
0x180010f76  sub     rsp, 48h
0x180010f7a  cmp     dword ptr [rcx+10h], 0
0x180010f7e  mov     rsi, r9
0x180010f81  mov     r14, r8
0x180010f84  mov     rdi, rcx
0x180010f87  jz      short loc_180010FB3
0x180010f89  mov     rcx, [rcx+28h]
0x180010f8d  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180010f94  mov     rax, [rax+1C0h]
0x180010f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fa0  mov     ebx, eax
0x180010fa2  cmp     eax, 0C0021022h
0x180010fa7  jnz     short loc_180010FE3
0x180010fa9  mov     eax, 0C0021022h
0x180010fae  jmp     loc_18001108E
0x180010fb3  test    edx, edx
0x180010fb5  jz      short loc_180010FDE
0x180010fb7  mov     rax, [rcx+18h]
0x180010fbb  mov     r8, rsi
0x180010fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fc3  mov     ebx, eax
0x180010fc5  cmp     eax, 0C0021022h
0x180010fca  jz      short loc_180010FA9
0x180010fcc  test    eax, eax
0x180010fce  jnz     short loc_180010FE3
0x180010fd0  mov     edx, [rsi]
0x180010fd2  mov     r9, rsi
0x180010fd5  mov     rcx, [rdi+28h]
0x180010fd9  mov     r8, r14
0x180010fdc  jmp     short loc_180010F8D
0x180010fde  mov     ebx, 0C0021008h
0x180010fe3  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180010fea  cmp     dword ptr [rax+248h], 0
0x180010ff1  jz      short loc_180011057
0x180010ff3  mov     rax, [rax+230h]
0x180010ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fff  cmp     dword ptr [rax+0Ch], 0
0x180011003  jz      short loc_180011057
0x180011005  test    ebx, ebx
0x180011007  jnz     short loc_180011057
0x180011009  mov     rax, [r14]
0x18001100c  cmp     byte ptr [rax+2], 14h
0x180011010  jnz     short loc_180011057
0x180011012  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180011019  mov     rax, [rax+230h]
0x180011020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011025  mov     r8, r14
0x180011028  mov     rdx, rsi
0x18001102b  xor     ecx, ecx
0x18001102d  mov     rax, [rax+0B0h]
0x180011034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011039  mov     eax, [rsi]
0x18001103b  mov     r9, rdi
0x18001103e  mov     r8, [r14]
0x180011041  mov     dl, 4Eh ; 'N'
0x180011043  mov     [rsp+68h+var_38], ebx
0x180011047  mov     cl, 4Fh ; 'O'
0x180011049  mov     [rsp+68h+var_40], ebx
0x18001104d  mov     [rsp+68h+var_48], eax
0x180011051  call    cs:__imp_I_RpcLogEvent
0x180011057  mov     rcx, [rdi+8]
0x18001105b  mov     r8d, 4
0x180011061  mov     rax, [rcx]
0x180011064  mov     r10, [rax+20h]
0x180011068  test    ebx, ebx
0x18001106a  jnz     short loc_180011079
0x18001106c  mov     eax, [rsi]
0x18001106e  xor     edx, edx
0x180011070  mov     r9, [r14]
0x180011073  mov     [rsp+68h+var_48], eax
0x180011077  jmp     short loc_180011086
0x180011079  mov     [rsp+68h+var_48], 0
0x180011081  xor     r9d, r9d
0x180011084  mov     edx, ebx
0x180011086  mov     rax, r10
0x180011089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001108e  add     rsp, 48h
0x180011092  pop     r14
0x180011094  pop     rdi
0x180011095  pop     rsi
0x180011096  pop     rbx
0x180011097  retn
```
