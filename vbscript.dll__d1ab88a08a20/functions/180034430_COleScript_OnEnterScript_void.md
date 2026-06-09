# COleScript::OnEnterScript(void)

- ea: `0x180034430`
- end: `0x1800344bf`
- name: `?OnEnterScript@COleScript@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001ef50`
- `0x1800343a0`

## callees

- `0x18001e2e4`
- `0x18001e32c`
- `0x180034430`
- `0x18007a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180034443`
- `KERNEL32!GetCurrentThreadId` at `0x180034443`
- `KERNEL32!LeaveCriticalSection` at `0x180034494`
- `KERNEL32!LeaveCriticalSection` at `0x180034494`

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
0x180034430  mov     [rsp+arg_0], rbx
0x180034435  push    rdi
0x180034436  sub     rsp, 20h
0x18003443a  mov     ebx, [rcx+0F4h]
0x180034440  mov     rdi, rcx
0x180034443  call    cs:__imp_GetCurrentThreadId
0x18003444a  nop     dword ptr [rax+rax+00h]
0x18003444f  cmp     eax, ebx
0x180034451  jnz     short loc_1800344B3
0x180034453  mov     rcx, rdi; this
0x180034456  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x18003445b  test    eax, eax
0x18003445d  jz      short loc_1800344B3
0x18003445f  inc     dword ptr [rdi+110h]
0x180034465  cmp     dword ptr [rdi+110h], 1
0x18003446c  mov     dword ptr [rdi+10Ch], 1
0x180034476  jnz     short loc_180034484
0x180034478  lea     rcx, [rdi+240h]; struct tagEXCEPINFO *
0x18003447f  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x180034484  cmp     dword ptr [rdi+210h], 0
0x18003448b  jz      short loc_1800344A0
0x18003448d  lea     rcx, [rdi+218h]; lpCriticalSection
0x180034494  call    cs:__imp_LeaveCriticalSection
0x18003449b  nop     dword ptr [rax+rax+00h]
0x1800344a0  mov     rcx, [rdi+0A0h]
0x1800344a7  mov     rax, [rcx]
0x1800344aa  mov     rax, [rax+48h]
0x1800344ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344b3  mov     rbx, [rsp+28h+arg_0]
0x1800344b8  add     rsp, 20h
0x1800344bc  pop     rdi
0x1800344bd  retn
```
