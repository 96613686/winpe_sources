# HTTP2Channel::BeginSimpleSubmitAsync(void)

- ea: `0x180005428`
- end: `0x1800054b1`
- name: `?BeginSimpleSubmitAsync@HTTP2Channel@@QEAAJXZ`
- size: `137`
- prototype: `__int64 __fastcall(HTTP2Channel *__hidden this)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180007f88`
- `0x1800081e8`
- `0x180008d20`
- `0x180009d9c`
- `0x180010940`
- `0x180010a60`
- `0x180011390`
- `0x1800114d0`
- `0x180012110`
- `0x180013200`
- `0x180013920`
- `0x1800158e0`
- `0x1800189a0`
- `0x1800190d0`
- `0x180019490`
- `0x18001964c`
- `0x180019858`
- `0x18001ac8c`

## callees

- `0x180005428`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x18000545d`
- `RPCRT4!I_RpcLogEvent` at `0x180005486`
- `RPCRT4!I_RpcLogEvent` at `0x18000545d`
- `RPCRT4!I_RpcLogEvent` at `0x180005486`

## pseudocode

```c
__int64 __fastcall HTTP2Channel::BeginSimpleSubmitAsync(HTTP2Channel *this, __int64 a2)
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
    return 0;
  LOBYTE(v7) = 45;
  LOBYTE(v8) = 50;
  I_RpcLogEvent(v8, v7, v2, *((int *)v2 + 8), v5, 1, 1);
  _InterlockedDecrement((volatile signed __int32 *)v2 + 11);
  result = *((unsigned int *)v2 + 16);
  if ( !(_DWORD)result )
    return 3221360648LL;
  return result;
}

```

## disassembly

```asm
0x180005428  mov     rax, rsp
0x18000542b  mov     [rax+8], rbx
0x18000542f  mov     [rax+10h], rsi
0x180005433  push    rdi
0x180005434  sub     rsp, 40h
0x180005438  mov     esi, 1
0x18000543d  mov     rbx, rcx
0x180005440  mov     edi, esi
0x180005442  lock xadd [rcx+2Ch], edi
0x180005447  movsxd  r9, dword ptr [rcx+20h]
0x18000544b  add     edi, esi
0x18000544d  mov     [rax-18h], esi
0x180005450  mov     r8, rcx
0x180005453  mov     [rax-20h], esi
0x180005456  mov     cl, 32h ; '2'
0x180005458  mov     dl, 2Bh ; '+'
0x18000545a  mov     [rax-28h], edi
0x18000545d  call    cs:__imp_I_RpcLogEvent
0x180005463  lock or [rsp+48h+var_48], 0
0x180005468  mov     eax, [rbx+28h]
0x18000546b  test    eax, eax
0x18000546d  jle     short loc_18000549F
0x18000546f  movsxd  r9, dword ptr [rbx+20h]
0x180005473  mov     r8, rbx
0x180005476  mov     [rsp+48h+var_18], esi
0x18000547a  mov     dl, 2Dh ; '-'
0x18000547c  mov     [rsp+48h+var_20], esi
0x180005480  mov     cl, 32h ; '2'
0x180005482  mov     [rsp+48h+var_28], edi
0x180005486  call    cs:__imp_I_RpcLogEvent
0x18000548c  lock dec dword ptr [rbx+2Ch]
0x180005490  mov     ecx, 0C0021008h
0x180005495  mov     eax, [rbx+40h]
0x180005498  test    eax, eax
0x18000549a  cmovz   eax, ecx
0x18000549d  jmp     short loc_1800054A1
0x18000549f  xor     eax, eax
0x1800054a1  mov     rbx, [rsp+48h+arg_0]
0x1800054a6  mov     rsi, [rsp+48h+arg_8]
0x1800054ab  add     rsp, 40h
0x1800054af  pop     rdi
0x1800054b0  retn
```
