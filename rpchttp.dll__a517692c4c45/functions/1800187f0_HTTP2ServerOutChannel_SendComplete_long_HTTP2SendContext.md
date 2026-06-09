# HTTP2ServerOutChannel::SendComplete(long,HTTP2SendContext *)

- ea: `0x1800187f0`
- end: `0x18001891e`
- name: `?SendComplete@HTTP2ServerOutChannel@@UEAAJJPEAVHTTP2SendContext@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(HTTP2ServerOutChannel *__hidden this, int, struct HTTP2SendContext *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000a654`
- `0x1800182f0`
- `0x1800187f0`
- `0x180025010`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x180018840`
- `RPCRT4!I_RpcLogEvent` at `0x1800188a9`
- `RPCRT4!I_RpcLogEvent` at `0x180018909`
- `RPCRT4!I_RpcLogEvent` at `0x180018840`
- `RPCRT4!I_RpcLogEvent` at `0x1800188a9`
- `RPCRT4!I_RpcLogEvent` at `0x180018909`

## pseudocode

```c
__int64 __fastcall HTTP2ServerOutChannel::SendComplete(
        HTTP2ServerOutChannel *this,
        __int64 a2,
        struct HTTP2SendContext *a3)
{
  int v3; // r14d
  int v5; // r15d
  volatile signed __int32 *v6; // rdi
  BOOL v7; // ebp
  HTTP2ServerOutChannel *v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // r8d
  unsigned int v14; // ebx
  __int64 v15; // rcx
  int v16; // edx
  __int64 v17; // rdx
  signed __int32 v18[8]; // [rsp+0h] [rbp-78h] BYREF
  int v19; // [rsp+20h] [rbp-58h]
  int v20; // [rsp+28h] [rbp-50h]
  int v21; // [rsp+30h] [rbp-48h]

  v3 = *((_DWORD *)a3 + 22);
  v5 = a2;
  v6 = (volatile signed __int32 *)this;
  v7 = v3 == 2 && (*((_BYTE *)a3 + 92) & 0x48) == 0;
  v8 = this;
  LOBYTE(a2) = 111;
  LOBYTE(this) = 50;
  I_RpcLogEvent(this, a2, v8, 17104920, (_DWORD)a3, 0, 0);
  if ( (*((_BYTE *)a3 + 92) & 8) != 0 )
  {
    (*((void (__fastcall **)(_QWORD))pRuntimeImportTable + 1))(*((_QWORD *)a3 + 8));
    HTTP2ServerOutChannel::FreeLastSendContext((HTTP2ServerOutChannel *)v6, a3);
    _InterlockedOr(v18, 0);
    v11 = *((_DWORD *)v6 + 21);
    v12 = 0;
    v21 = 0;
    v20 = 0;
    if ( v3 == 2 )
      v12 = 0x1000000;
    LOBYTE(v9) = 111;
    LOBYTE(v10) = 50;
    I_RpcLogEvent(v10, v9, v6, 327704, v11 | v12, v20, v21);
    return 3221360681LL;
  }
  else
  {
    v14 = HTTP2Channel::SendComplete((HTTP2Channel *)v6, v5, a3);
    if ( v7 )
      _InterlockedDecrement(v6 + 21);
    _InterlockedOr(v18, 0);
    v15 = *((unsigned int *)v6 + 21);
    v16 = 0;
    v21 = 0;
    v20 = 0;
    if ( v3 == 2 )
      v16 = 0x1000000;
    v17 = (unsigned int)v15 | v16;
    v19 = v17;
    LOBYTE(v15) = 50;
    LOBYTE(v17) = 111;
    I_RpcLogEvent(v15, v17, v6, 327704, v19, v20, v21);
    return v14;
  }
}

```

## disassembly

```asm
0x1800187f0  push    rbx
0x1800187f2  push    rbp
0x1800187f3  push    rsi
0x1800187f4  push    rdi
0x1800187f5  push    r14
0x1800187f7  push    r15
0x1800187f9  sub     rsp, 48h
0x1800187fd  mov     r14d, [r8+58h]
0x180018801  mov     rsi, r8
0x180018804  mov     r15d, edx
0x180018807  mov     rdi, rcx
0x18001880a  cmp     r14d, 2
0x18001880e  jnz     short loc_18001881D
0x180018810  test    byte ptr [r8+5Ch], 48h
0x180018815  jnz     short loc_18001881D
0x180018817  lea     ebp, [r14-1]
0x18001881b  jmp     short loc_18001881F
0x18001881d  xor     ebp, ebp
0x18001881f  mov     [rsp+78h+var_48], 0
0x180018827  mov     r9d, 1050018h
0x18001882d  mov     [rsp+78h+var_50], 0
0x180018835  mov     r8, rdi
0x180018838  mov     dl, 6Fh ; 'o'
0x18001883a  mov     [rsp+78h+var_58], esi
0x18001883e  mov     cl, 32h ; '2'
0x180018840  call    cs:__imp_I_RpcLogEvent
0x180018846  test    byte ptr [rsi+5Ch], 8
0x18001884a  jz      short loc_1800188B6
0x18001884c  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180018853  mov     rcx, [rsi+40h]
0x180018857  mov     rax, [rax+8]
0x18001885b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018860  mov     rdx, rsi; struct HTTP2SendContext *
0x180018863  mov     rcx, rdi; this
0x180018866  call    ?FreeLastSendContext@HTTP2ServerOutChannel@@QEAAXPEAVHTTP2SendContext@@@Z; HTTP2ServerOutChannel::FreeLastSendContext(HTTP2SendContext *)
0x18001886b  lock or [rsp+78h+var_78], 0
0x180018870  mov     eax, [rdi+54h]
0x180018873  xor     r8d, r8d
0x180018876  cmp     r14d, 2
0x18001887a  mov     [rsp+78h+var_48], 0
0x180018882  mov     r9d, 1000000h
0x180018888  mov     [rsp+78h+var_50], 0
0x180018890  cmovz   r8d, r9d
0x180018894  mov     dl, 6Fh ; 'o'
0x180018896  or      r8d, eax
0x180018899  mov     r9d, 50018h
0x18001889f  mov     [rsp+78h+var_58], r8d
0x1800188a4  mov     cl, 32h ; '2'
0x1800188a6  mov     r8, rdi
0x1800188a9  call    cs:__imp_I_RpcLogEvent
0x1800188af  mov     eax, 0C0021029h
0x1800188b4  jmp     short loc_180018911
0x1800188b6  mov     r8, rsi; struct HTTP2SendContext *
0x1800188b9  mov     edx, r15d; int
0x1800188bc  mov     rcx, rdi; this
0x1800188bf  call    ?SendComplete@HTTP2Channel@@UEAAJJPEAVHTTP2SendContext@@@Z; HTTP2Channel::SendComplete(long,HTTP2SendContext *)
0x1800188c4  mov     ebx, eax
0x1800188c6  test    ebp, ebp
0x1800188c8  jz      short loc_1800188CE
0x1800188ca  lock dec dword ptr [rdi+54h]
0x1800188ce  lock or [rsp+78h+var_78], 0
0x1800188d3  mov     ecx, [rdi+54h]
0x1800188d6  xor     edx, edx
0x1800188d8  cmp     r14d, 2
0x1800188dc  mov     [rsp+78h+var_48], 0
0x1800188e4  mov     r9d, 1000000h
0x1800188ea  mov     [rsp+78h+var_50], 0
0x1800188f2  cmovz   edx, r9d
0x1800188f6  mov     r8, rdi
0x1800188f9  or      edx, ecx
0x1800188fb  mov     r9d, 50018h
0x180018901  mov     [rsp+78h+var_58], edx
0x180018905  mov     cl, 32h ; '2'
0x180018907  mov     dl, 6Fh ; 'o'
0x180018909  call    cs:__imp_I_RpcLogEvent
0x18001890f  mov     eax, ebx
0x180018911  add     rsp, 48h
0x180018915  pop     r15
0x180018917  pop     r14
0x180018919  pop     rdi
0x18001891a  pop     rsi
0x18001891b  pop     rbp
0x18001891c  pop     rbx
0x18001891d  retn
```
