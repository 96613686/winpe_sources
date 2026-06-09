# COleScript::OnLeaveScript(void)

- ea: `0x18000516c`
- end: `0x1800051e1`
- name: `?OnLeaveScript@COleScript@@QEAAXXZ`
- size: `117`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180004ad0`
- `0x180004d80`
- `0x180006230`
- `0x180007de0`
- `0x180008040`
- `0x180023950`

## callees

- `0x18000516c`
- `0x180022e04`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000517f`
- `KERNEL32!GetCurrentThreadId` at `0x18000517f`
- `KERNEL32!LeaveCriticalSection` at `0x1800051d0`
- `KERNEL32!LeaveCriticalSection` at `0x1800051d0`

## pseudocode

```c
void __fastcall COleScript::OnLeaveScript(COleScript *this)
{
  int v1; // ebx
  __int64 v3; // rcx

  v1 = *((_DWORD *)this + 61);
  if ( GetCurrentThreadId() == v1 )
  {
    v3 = *((_QWORD *)this + 20);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 80LL))(v3);
    if ( (unsigned int)COleScript::DisableInterrupts(this) )
    {
      if ( (*((_DWORD *)this + 68))-- == 1 )
        *((_DWORD *)this + 67) = 0;
      if ( *((_DWORD *)this + 132) )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
    }
  }
}

```

## disassembly

```asm
0x18000516c  mov     [rsp+arg_8], rbx
0x180005171  push    rdi
0x180005172  sub     rsp, 20h
0x180005176  mov     ebx, [rcx+0F4h]
0x18000517c  mov     rdi, rcx
0x18000517f  call    cs:__imp_GetCurrentThreadId
0x180005185  cmp     eax, ebx
0x180005187  jnz     short loc_1800051D6
0x180005189  mov     rcx, [rdi+0A0h]
0x180005190  test    rcx, rcx
0x180005193  jz      short loc_1800051A1
0x180005195  mov     rax, [rcx]
0x180005198  mov     rax, [rax+50h]
0x18000519c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051a1  mov     rcx, rdi; this
0x1800051a4  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x1800051a9  test    eax, eax
0x1800051ab  jz      short loc_1800051D6
0x1800051ad  add     dword ptr [rdi+110h], 0FFFFFFFFh
0x1800051b4  jnz     short loc_1800051C0
0x1800051b6  mov     dword ptr [rdi+10Ch], 0
0x1800051c0  cmp     dword ptr [rdi+210h], 0
0x1800051c7  jz      short loc_1800051D6
0x1800051c9  lea     rcx, [rdi+218h]; lpCriticalSection
0x1800051d0  call    cs:__imp_LeaveCriticalSection
0x1800051d6  mov     rbx, [rsp+28h+arg_8]
0x1800051db  add     rsp, 20h
0x1800051df  pop     rdi
0x1800051e0  retn
```
