# HTTP2ClientChannel::SendComplete(long,HTTP2SendContext *)

- ea: `0x180018340`
- end: `0x1800183d1`
- name: `?SendComplete@HTTP2ClientChannel@@UEAAJJPEAVHTTP2SendContext@@@Z`
- size: `145`
- prototype: `__int64 __fastcall(HTTP2ClientChannel *__hidden this, int, struct HTTP2SendContext *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180005d18`
- `0x18000a44c`
- `0x18000f3fc`
- `0x180018340`
- `0x18001ac60`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2ClientChannel::SendComplete(
        HTTP2ClientChannel *this,
        unsigned int a2,
        struct HTTP2SendContext *a3)
{
  __int64 result; // rax
  __int64 v7; // rdx
  struct HTTP2VirtualConnection *v8; // r8
  struct HTTP2VirtualConnection *v9; // rax

  result = HTTP2Channel::CheckSendCompleteForSync(this, a2, a3);
  if ( (_DWORD)result != -1073606615 )
  {
    if ( *((_DWORD *)a3 + 22) == 4 )
    {
      if ( a2 )
      {
        v9 = HTTP2Channel::LockParentPointer(this);
        v8 = v9;
        if ( v9 )
        {
          (*(void (__fastcall **)(struct HTTP2VirtualConnection *, _QWORD))(*(_QWORD *)v9 + 64LL))(v9, 0);
          HTTP2Channel::UnlockParentPointer(this);
        }
      }
      (*((void (__fastcall **)(struct HTTP2SendContext *, __int64, struct HTTP2VirtualConnection *))pRuntimeImportTable
       + 1))(
        a3,
        v7,
        v8);
      return 3221360681LL;
    }
    else if ( !(_DWORD)result )
    {
      return HTTP2Channel::ForwardUpSendComplete(this, a2, a3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018340  mov     [rsp+arg_0], rbx
0x180018345  mov     [rsp+arg_8], rsi
0x18001834a  push    rdi
0x18001834b  sub     rsp, 20h
0x18001834f  mov     rbx, r8
0x180018352  mov     edi, edx
0x180018354  mov     rsi, rcx
0x180018357  call    ?CheckSendCompleteForSync@HTTP2Channel@@IEAAJJPEAVHTTP2SendContext@@@Z; HTTP2Channel::CheckSendCompleteForSync(long,HTTP2SendContext *)
0x18001835c  cmp     eax, 0C0021029h
0x180018361  jz      short loc_1800183C1
0x180018363  cmp     dword ptr [rbx+58h], 4
0x180018367  jnz     short loc_1800183B0
0x180018369  test    edi, edi
0x18001836b  jz      short loc_180018396
0x18001836d  mov     rcx, rsi; this
0x180018370  call    ?LockParentPointer@HTTP2Channel@@QEAAPEAVHTTP2VirtualConnection@@XZ; HTTP2Channel::LockParentPointer(void)
0x180018375  mov     r8, rax
0x180018378  test    rax, rax
0x18001837b  jz      short loc_180018396
0x18001837d  mov     rcx, [rax]
0x180018380  xor     edx, edx
0x180018382  mov     rax, [rcx+40h]
0x180018386  mov     rcx, r8
0x180018389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001838e  mov     rcx, rsi; this
0x180018391  call    ?UnlockParentPointer@HTTP2Channel@@QEAAXXZ; HTTP2Channel::UnlockParentPointer(void)
0x180018396  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18001839d  mov     rcx, rbx
0x1800183a0  mov     rax, [rax+8]
0x1800183a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183a9  mov     eax, 0C0021029h
0x1800183ae  jmp     short loc_1800183C1
0x1800183b0  test    eax, eax
0x1800183b2  jnz     short loc_1800183C1
0x1800183b4  mov     r8, rbx; struct HTTP2SendContext *
0x1800183b7  mov     edx, edi; int
0x1800183b9  mov     rcx, rsi; this
0x1800183bc  call    ?ForwardUpSendComplete@HTTP2Channel@@IEAAJJPEAVHTTP2SendContext@@@Z; HTTP2Channel::ForwardUpSendComplete(long,HTTP2SendContext *)
0x1800183c1  mov     rbx, [rsp+28h+arg_0]
0x1800183c6  mov     rsi, [rsp+28h+arg_8]
0x1800183cb  add     rsp, 20h
0x1800183cf  pop     rdi
0x1800183d0  retn
```
