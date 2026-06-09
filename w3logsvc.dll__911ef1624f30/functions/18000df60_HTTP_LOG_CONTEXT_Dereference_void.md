# HTTP_LOG_CONTEXT::Dereference(void)

- ea: `0x18000df60`
- end: `0x18000dfb4`
- name: `?Dereference@HTTP_LOG_CONTEXT@@UEAAXXZ`
- size: `84`
- prototype: `void __fastcall(HTTP_LOG_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000df60`
- `0x180010010`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x18000df88`
- `iisutil!WriteRefTraceLog` at `0x18000df88`

## pseudocode

```c
void __fastcall HTTP_LOG_CONTEXT::Dereference(HTTP_LOG_CONTEXT *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( HTTP_LOG_CONTEXT::sm_pTraceLog )
    WriteRefTraceLog(HTTP_LOG_CONTEXT::sm_pTraceLog, v2, this);
  if ( !v2 )
  {
    if ( this )
      (*(void (__fastcall **)(HTTP_LOG_CONTEXT *, __int64))(*(_QWORD *)this + 24LL))(this, 1);
  }
}

```

## disassembly

```asm
0x18000df60  mov     [rsp+arg_0], rbx
0x18000df65  push    rdi
0x18000df66  sub     rsp, 20h
0x18000df6a  mov     rbx, rcx
0x18000df6d  or      edi, 0FFFFFFFFh
0x18000df70  lock xadd [rcx+8], edi
0x18000df75  mov     rcx, cs:?sm_pTraceLog@HTTP_LOG_CONTEXT@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * HTTP_LOG_CONTEXT::sm_pTraceLog
0x18000df7c  dec     edi
0x18000df7e  test    rcx, rcx
0x18000df81  jz      short loc_18000DF8E
0x18000df83  mov     r8, rbx
0x18000df86  mov     edx, edi
0x18000df88  call    cs:__imp_WriteRefTraceLog
0x18000df8e  test    edi, edi
0x18000df90  jnz     short loc_18000DFA9
0x18000df92  test    rbx, rbx
0x18000df95  jz      short loc_18000DFA9
0x18000df97  mov     rax, [rbx]
0x18000df9a  lea     edx, [rdi+1]
0x18000df9d  mov     rcx, rbx
0x18000dfa0  mov     rax, [rax+18h]
0x18000dfa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfa9  mov     rbx, [rsp+28h+arg_0]
0x18000dfae  add     rsp, 20h
0x18000dfb2  pop     rdi
0x18000dfb3  retn
```
