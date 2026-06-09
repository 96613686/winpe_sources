# COleScript::OnEnterScript(void)

- ea: `0x18002fa68`
- end: `0x18002faea`
- name: `?OnEnterScript@COleScript@@QEAAXXZ`
- size: `130`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180023950`
- `0x18002f9ec`

## callees

- `0x180022e04`
- `0x180022e44`
- `0x18002fa68`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002fa7b`
- `KERNEL32!GetCurrentThreadId` at `0x18002fa7b`
- `KERNEL32!LeaveCriticalSection` at `0x18002fac6`
- `KERNEL32!LeaveCriticalSection` at `0x18002fac6`

## pseudocode

```c
void __fastcall COleScript::OnEnterScript(COleScript *this)
{
  int v1; // ebx
  bool v3; // zf

  v1 = *((_DWORD *)this + 61);
  if ( GetCurrentThreadId() == v1 && (unsigned int)COleScript::DisableInterrupts(this) )
  {
    v3 = ++*((_DWORD *)this + 68) == 1;
    *((_DWORD *)this + 67) = 1;
    if ( v3 )
      FreeExcepInfo((struct tagEXCEPINFO *)this + 9);
    if ( *((_DWORD *)this + 132) )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 20) + 72LL))(*((_QWORD *)this + 20));
  }
}

```

## disassembly

```asm
0x18002fa68  mov     [rsp+arg_0], rbx
0x18002fa6d  push    rdi
0x18002fa6e  sub     rsp, 20h
0x18002fa72  mov     ebx, [rcx+0F4h]
0x18002fa78  mov     rdi, rcx
0x18002fa7b  call    cs:__imp_GetCurrentThreadId
0x18002fa81  cmp     eax, ebx
0x18002fa83  jnz     short loc_18002FADF
0x18002fa85  mov     rcx, rdi; this
0x18002fa88  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x18002fa8d  test    eax, eax
0x18002fa8f  jz      short loc_18002FADF
0x18002fa91  inc     dword ptr [rdi+110h]
0x18002fa97  cmp     dword ptr [rdi+110h], 1
0x18002fa9e  mov     dword ptr [rdi+10Ch], 1
0x18002faa8  jnz     short loc_18002FAB6
0x18002faaa  lea     rcx, [rdi+240h]; struct tagEXCEPINFO *
0x18002fab1  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x18002fab6  cmp     dword ptr [rdi+210h], 0
0x18002fabd  jz      short loc_18002FACC
0x18002fabf  lea     rcx, [rdi+218h]; lpCriticalSection
0x18002fac6  call    cs:__imp_LeaveCriticalSection
0x18002facc  mov     rcx, [rdi+0A0h]
0x18002fad3  mov     rax, [rcx]
0x18002fad6  mov     rax, [rax+48h]
0x18002fada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fadf  mov     rbx, [rsp+28h+arg_0]
0x18002fae4  add     rsp, 20h
0x18002fae8  pop     rdi
0x18002fae9  retn
```
