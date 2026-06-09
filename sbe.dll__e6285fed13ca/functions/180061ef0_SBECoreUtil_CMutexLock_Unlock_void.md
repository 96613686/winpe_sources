# SBECoreUtil::CMutexLock::Unlock(void)

- ea: `0x180061ef0`
- end: `0x180061f2b`
- name: `?Unlock@CMutexLock@SBECoreUtil@@QEAAXXZ`
- size: `59`
- prototype: `void __fastcall(SBECoreUtil::CMutexLock *__hidden this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180060120`
- `0x1800a84a4`
- `0x1800a87c4`
- `0x1800ae184`
- `0x1800aeb28`
- `0x1800aef58`
- `0x1800af400`
- `0x1800af928`
- `0x1800afba0`
- `0x1800aff04`
- `0x1800b019c`
- `0x1800b0900`

## callees

- `0x180061ef0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180061ef9`
- `KERNEL32!GetCurrentThreadId` at `0x180061ef9`
- `KERNEL32!LeaveCriticalSection` at `0x180061f1f`
- `KERNEL32!LeaveCriticalSection` at `0x180061f1f`
- `KERNEL32!ReleaseMutex` at `0x180061f0e`
- `KERNEL32!ReleaseMutex` at `0x180061f0e`

## pseudocode

```c
void __fastcall SBECoreUtil::CMutexLock::Unlock(SBECoreUtil::CMutexLock *this)
{
  if ( *((_DWORD *)this + 18) == GetCurrentThreadId() )
  {
    if ( (*((_DWORD *)this + 4))-- == 1 )
    {
      ReleaseMutex(*((HANDLE *)this + 8));
      *((_DWORD *)this + 18) = -1;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  }
}

```

## disassembly

```asm
0x180061ef0  push    rbx
0x180061ef2  sub     rsp, 20h
0x180061ef6  mov     rbx, rcx
0x180061ef9  call    cs:__imp_GetCurrentThreadId
0x180061eff  cmp     [rbx+48h], eax
0x180061f02  jnz     short loc_180061F25
0x180061f04  sub     dword ptr [rbx+10h], 1
0x180061f08  jnz     short loc_180061F1B
0x180061f0a  mov     rcx, [rbx+40h]; hMutex
0x180061f0e  call    cs:__imp_ReleaseMutex
0x180061f14  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x180061f1b  lea     rcx, [rbx+18h]; lpCriticalSection
0x180061f1f  call    cs:__imp_LeaveCriticalSection
0x180061f25  add     rsp, 20h
0x180061f29  pop     rbx
0x180061f2a  retn
```
