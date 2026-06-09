# SBECoreUtil::CMutexLock::~CMutexLock(void)

- ea: `0x180060120`
- end: `0x180060176`
- name: `??1CMutexLock@SBECoreUtil@@UEAA@XZ`
- size: `86`
- prototype: `void __fastcall(SBECoreUtil::CMutexLock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800603b0`

## callees

- `0x180060120`
- `0x180061ef0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180060140`
- `KERNEL32!GetCurrentThreadId` at `0x180060140`
- `KERNEL32!CloseHandle` at `0x18006015b`
- `KERNEL32!CloseHandle` at `0x18006015b`
- `KERNEL32!DeleteCriticalSection` at `0x18006016f`

## pseudocode

```c
void __fastcall SBECoreUtil::CMutexLock::~CMutexLock(SBECoreUtil::CMutexLock *this)
{
  bool v1; // cc
  int v3; // ebx
  void *v4; // rcx

  v1 = *((_DWORD *)this + 4) <= 0;
  *(_QWORD *)this = &SBECoreUtil::CMutexLock::`vftable';
  if ( !v1 )
  {
    v3 = *((_DWORD *)this + 18);
    if ( v3 == GetCurrentThreadId() )
      SBECoreUtil::CMutexLock::Unlock(this);
  }
  v4 = (void *)*((_QWORD *)this + 8);
  if ( v4 )
    CloseHandle(v4);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x180060120  mov     [rsp+arg_0], rbx
0x180060125  push    rdi
0x180060126  sub     rsp, 20h
0x18006012a  cmp     dword ptr [rcx+10h], 0
0x18006012e  lea     rax, ??_7CMutexLock@SBECoreUtil@@6B@; const SBECoreUtil::CMutexLock::`vftable'
0x180060135  mov     [rcx], rax
0x180060138  mov     rdi, rcx
0x18006013b  jle     short loc_180060152
0x18006013d  mov     ebx, [rcx+48h]
0x180060140  call    cs:__imp_GetCurrentThreadId
0x180060146  cmp     ebx, eax
0x180060148  jnz     short loc_180060152
0x18006014a  mov     rcx, rdi; this
0x18006014d  call    ?Unlock@CMutexLock@SBECoreUtil@@QEAAXXZ; SBECoreUtil::CMutexLock::Unlock(void)
0x180060152  mov     rcx, [rdi+40h]; hObject
0x180060156  test    rcx, rcx
0x180060159  jz      short loc_180060161
0x18006015b  call    cs:__imp_CloseHandle
0x180060161  lea     rcx, [rdi+18h]
0x180060165  mov     rbx, [rsp+28h+arg_0]
0x18006016a  add     rsp, 20h
0x18006016e  pop     rdi
0x18006016f  jmp     cs:__imp_DeleteCriticalSection
```
