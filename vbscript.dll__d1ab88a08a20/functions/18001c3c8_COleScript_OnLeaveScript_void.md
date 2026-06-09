# COleScript::OnLeaveScript(void)

- ea: `0x18001c3c8`
- end: `0x18001c44a`
- name: `?OnLeaveScript@COleScript@@QEAAXXZ`
- size: `130`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800040a0`
- `0x180005e40`
- `0x1800060c0`
- `0x18001af30`
- `0x18001c5c0`
- `0x18001ef50`

## callees

- `0x18001c3c8`
- `0x18001e2e4`
- `0x18007a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001c3db`
- `KERNEL32!GetCurrentThreadId` at `0x18001c3db`
- `KERNEL32!LeaveCriticalSection` at `0x18001c432`
- `KERNEL32!LeaveCriticalSection` at `0x18001c432`

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
0x18001c3c8  mov     [rsp+arg_8], rbx
0x18001c3cd  push    rdi
0x18001c3ce  sub     rsp, 20h
0x18001c3d2  mov     ebx, [rcx+0F4h]
0x18001c3d8  mov     rdi, rcx
0x18001c3db  call    cs:__imp_GetCurrentThreadId
0x18001c3e2  nop     dword ptr [rax+rax+00h]
0x18001c3e7  cmp     eax, ebx
0x18001c3e9  jnz     short loc_18001C43E
0x18001c3eb  mov     rcx, [rdi+0A0h]
0x18001c3f2  test    rcx, rcx
0x18001c3f5  jz      short loc_18001C403
0x18001c3f7  mov     rax, [rcx]
0x18001c3fa  mov     rax, [rax+50h]
0x18001c3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c403  mov     rcx, rdi; this
0x18001c406  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x18001c40b  test    eax, eax
0x18001c40d  jz      short loc_18001C43E
0x18001c40f  add     dword ptr [rdi+110h], 0FFFFFFFFh
0x18001c416  jnz     short loc_18001C422
0x18001c418  mov     dword ptr [rdi+10Ch], 0
0x18001c422  cmp     dword ptr [rdi+210h], 0
0x18001c429  jz      short loc_18001C43E
0x18001c42b  lea     rcx, [rdi+218h]; lpCriticalSection
0x18001c432  call    cs:__imp_LeaveCriticalSection
0x18001c439  nop     dword ptr [rax+rax+00h]
0x18001c43e  mov     rbx, [rsp+28h+arg_8]
0x18001c443  add     rsp, 20h
0x18001c447  pop     rdi
0x18001c448  retn
```
