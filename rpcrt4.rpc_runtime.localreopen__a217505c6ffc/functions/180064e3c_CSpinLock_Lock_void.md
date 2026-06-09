# CSpinLock::Lock(void)

- ea: `0x180064e3c`
- end: `0x180064ea5`
- name: `?Lock@CSpinLock@@QEAAXXZ`
- size: `105`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017460`
- `0x180063b68`
- `0x180063d88`
- `0x180063e30`
- `0x18006403c`
- `0x180064504`
- `0x18006493c`
- `0x180064b74`
- `0x180064c44`
- `0x180066478`
- `0x180066d20`
- `0x180081d30`
- `0x1800caa30`
- `0x1800cab90`
- `0x1800cad80`
- `0x1800cadf0`
- `0x1800caed0`
- `0x1800cb140`
- `0x1800cb390`
- `0x1800cb4a0`

## callees

- `0x180064e3c`
- `0x180066948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064e4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064e6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064e4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064e6b`

## pseudocode

```c
void __fastcall CSpinLock::Lock(CSpinLock *this)
{
  if ( *(_DWORD *)this
    || _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFF | 0x10000000, 0) )
  {
    if ( (*(_DWORD *)this & 0xFFFFFFF) == (GetCurrentThreadId() & 0xFFFFFFF) )
      _InterlockedExchange((volatile __int32 *)this, *(_DWORD *)this + 0x10000000);
    else
      CSpinLock::_LockSpin(this);
  }
}

```

## disassembly

```asm
0x180064e3c  push    rbx
0x180064e3e  sub     rsp, 20h
0x180064e42  mov     eax, [rcx]
0x180064e44  mov     rbx, rcx
0x180064e47  test    eax, eax
0x180064e49  jnz     short loc_180064E6B
0x180064e4b  call    cs:__imp_GetCurrentThreadId
0x180064e52  nop     dword ptr [rax+rax+00h]
0x180064e57  mov     edx, eax
0x180064e59  and     edx, 0FFFFFFFh
0x180064e5f  bts     edx, 1Ch
0x180064e63  xor     eax, eax
0x180064e65  lock cmpxchg [rbx], edx
0x180064e69  jz      short loc_180064E91
0x180064e6b  call    cs:__imp_GetCurrentThreadId
0x180064e72  nop     dword ptr [rax+rax+00h]
0x180064e77  mov     ecx, [rbx]
0x180064e79  and     eax, 0FFFFFFFh
0x180064e7e  and     ecx, 0FFFFFFFh
0x180064e84  cmp     ecx, eax
0x180064e86  jnz     short loc_180064E98
0x180064e88  mov     eax, [rbx]
0x180064e8a  add     eax, 10000000h
0x180064e8f  xchg    eax, [rbx]
0x180064e91  add     rsp, 20h
0x180064e95  pop     rbx
0x180064e96  retn
0x180064e98  mov     rcx, rbx; this
0x180064e9b  add     rsp, 20h
0x180064e9f  pop     rbx
0x180064ea0  jmp     ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
```
