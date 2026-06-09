# HTTP2Channel::BeginSubmitAsync(void)

- ea: `0x1800054b8`
- end: `0x180005549`
- name: `?BeginSubmitAsync@HTTP2Channel@@QEAAJXZ`
- size: `145`
- prototype: `__int64 __fastcall(HTTP2Channel *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b380`
- `0x1800117f0`
- `0x180013200`
- `0x180015790`
- `0x180017580`
- `0x180018130`

## callees

- `0x1800043d8`
- `0x1800054b8`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x1800054ed`
- `RPCRT4!I_RpcLogEvent` at `0x180005516`
- `RPCRT4!I_RpcLogEvent` at `0x1800054ed`
- `RPCRT4!I_RpcLogEvent` at `0x180005516`

## pseudocode

```c
__int64 __fastcall HTTP2Channel::BeginSubmitAsync(HTTP2Channel *this, __int64 a2)
{
  HTTP2Channel *v2; // rbx
  signed __int32 v3; // edi
  __int64 v4; // r9
  signed __int32 v5; // edi
  HTTP2Channel *v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 result; // rax
  signed __int32 v10[8]; // [rsp+0h] [rbp-48h] BYREF

  v2 = this;
  v3 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 11, 1u);
  v4 = *((int *)this + 8);
  v5 = v3 + 1;
  v6 = this;
  LOBYTE(this) = 50;
  LOBYTE(a2) = 43;
  I_RpcLogEvent(this, a2, v6, v4, v5, 1, 1);
  _InterlockedOr(v10, 0);
  if ( *((int *)v2 + 10) <= 0 )
  {
    HTTP2Channel::AddReference(v2);
    return 0;
  }
  else
  {
    LOBYTE(v7) = 45;
    LOBYTE(v8) = 50;
    I_RpcLogEvent(v8, v7, v2, *((int *)v2 + 8), v5, 1, 1);
    _InterlockedDecrement((volatile signed __int32 *)v2 + 11);
    result = *((unsigned int *)v2 + 16);
    if ( !(_DWORD)result )
      return 3221360648LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800054b8  mov     rax, rsp
0x1800054bb  mov     [rax+8], rbx
0x1800054bf  mov     [rax+10h], rsi
0x1800054c3  push    rdi
0x1800054c4  sub     rsp, 40h
0x1800054c8  mov     esi, 1
0x1800054cd  mov     rbx, rcx
0x1800054d0  mov     edi, esi
0x1800054d2  lock xadd [rcx+2Ch], edi
0x1800054d7  movsxd  r9, dword ptr [rcx+20h]
0x1800054db  add     edi, esi
0x1800054dd  mov     [rax-18h], esi
0x1800054e0  mov     r8, rcx
0x1800054e3  mov     [rax-20h], esi
0x1800054e6  mov     cl, 32h ; '2'
0x1800054e8  mov     dl, 2Bh ; '+'
0x1800054ea  mov     [rax-28h], edi
0x1800054ed  call    cs:__imp_I_RpcLogEvent
0x1800054f3  lock or [rsp+48h+var_48], 0
0x1800054f8  mov     eax, [rbx+28h]
0x1800054fb  test    eax, eax
0x1800054fd  jle     short loc_18000552F
0x1800054ff  movsxd  r9, dword ptr [rbx+20h]
0x180005503  mov     r8, rbx
0x180005506  mov     [rsp+48h+var_18], esi
0x18000550a  mov     dl, 2Dh ; '-'
0x18000550c  mov     [rsp+48h+var_20], esi
0x180005510  mov     cl, 32h ; '2'
0x180005512  mov     [rsp+48h+var_28], edi
0x180005516  call    cs:__imp_I_RpcLogEvent
0x18000551c  lock dec dword ptr [rbx+2Ch]
0x180005520  mov     ecx, 0C0021008h
0x180005525  mov     eax, [rbx+40h]
0x180005528  test    eax, eax
0x18000552a  cmovz   eax, ecx
0x18000552d  jmp     short loc_180005539
0x18000552f  mov     rcx, rbx; this
0x180005532  call    ?AddReference@HTTP2Channel@@QEAAXXZ; HTTP2Channel::AddReference(void)
0x180005537  xor     eax, eax
0x180005539  mov     rbx, [rsp+48h+arg_0]
0x18000553e  mov     rsi, [rsp+48h+arg_8]
0x180005543  add     rsp, 40h
0x180005547  pop     rdi
0x180005548  retn
```
