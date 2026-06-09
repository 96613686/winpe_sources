# HTTP_LOG_CONTEXT::HandleQueryCompletion(void *,ulong)

- ea: `0x18000a2f8`
- end: `0x18000a366`
- name: `?HandleQueryCompletion@HTTP_LOG_CONTEXT@@QEAAJPEAXK@Z`
- size: `110`
- prototype: `__int64 __fastcall(HTTP_LOG_CONTEXT *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009720`

## callees

- `0x180001008`
- `0x1800062c4`
- `0x18000a2f8`

## import_xrefs

- `iisutil!??0MULTISZ@@QEAA@PEBG@Z` at `0x18000a34c`
- `iisutil!??0MULTISZ@@QEAA@PEBG@Z` at `0x18000a34c`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_CONTEXT::HandleQueryCompletion(HTTP_LOG_CONTEXT *this, const unsigned __int16 *a2, int a3)
{
  MULTISZ *v6; // rax

  if ( !a3 )
  {
    *((_QWORD *)this + 102) = 0;
    return LOG_WRITER::Write(*((RTL_SRWLOCK **)this + 148), this);
  }
  v6 = (MULTISZ *)operator new(0x38u);
  if ( v6 )
    v6 = MULTISZ::MULTISZ(v6, a2);
  *((_QWORD *)this + 102) = v6;
  if ( v6 )
    return LOG_WRITER::Write(*((RTL_SRWLOCK **)this + 148), this);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000a2f8  mov     [rsp+arg_0], rbx
0x18000a2fd  push    rdi
0x18000a2fe  sub     rsp, 20h
0x18000a302  mov     rdi, rdx
0x18000a305  mov     rbx, rcx
0x18000a308  test    r8d, r8d
0x18000a30b  jnz     short loc_18000A332
0x18000a30d  mov     qword ptr [rcx+330h], 0
0x18000a318  mov     rdx, rbx; struct HTTP_LOG_CONTEXT *
0x18000a31b  mov     rcx, [rbx+4A0h]; this
0x18000a322  call    ?Write@LOG_WRITER@@QEAAJPEAVHTTP_LOG_CONTEXT@@@Z; LOG_WRITER::Write(HTTP_LOG_CONTEXT *)
0x18000a327  mov     rbx, [rsp+28h+arg_0]
0x18000a32c  add     rsp, 20h
0x18000a330  pop     rdi
0x18000a331  retn
0x18000a332  mov     ecx, 38h ; '8'; Size
0x18000a337  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a33c  mov     [rsp+28h+arg_18], rax
0x18000a341  test    rax, rax
0x18000a344  jz      short loc_18000A353
0x18000a346  mov     rdx, rdi
0x18000a349  mov     rcx, rax
0x18000a34c  call    cs:__imp_??0MULTISZ@@QEAA@PEBG@Z; MULTISZ::MULTISZ(ushort const *)
0x18000a352  nop
0x18000a353  mov     [rbx+330h], rax
0x18000a35a  test    rax, rax
0x18000a35d  jnz     short loc_18000A318
0x18000a35f  mov     eax, 8007000Eh
0x18000a364  jmp     short loc_18000A327
```
