# CMulticastSession::CanDelete(void)

- ea: `0x1800174cc`
- end: `0x180017543`
- name: `?CanDelete@CMulticastSession@@QEAAHXZ`
- size: `119`
- prototype: `__int64 __fastcall(CMulticastSession *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000480c`
- `0x1800197e0`
- `0x180019874`
- `0x180019a3c`
- `0x18001a514`

## callees

- `0x1800174cc`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180017515`
- `KERNEL32!LeaveCriticalSection` at `0x180017526`
- `KERNEL32!LeaveCriticalSection` at `0x180017515`
- `KERNEL32!LeaveCriticalSection` at `0x180017526`
- `KERNEL32!EnterCriticalSection` at `0x1800174e7`
- `KERNEL32!EnterCriticalSection` at `0x1800174fe`
- `KERNEL32!EnterCriticalSection` at `0x1800174e7`
- `KERNEL32!EnterCriticalSection` at `0x1800174fe`

## pseudocode

```c
_BOOL8 __fastcall CMulticastSession::CanDelete(CMulticastSession *this)
{
  BOOL v2; // esi
  signed __int32 v3; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v2 = 0;
  if ( *((_DWORD *)this + 4051) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
    v3 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 1402, 0);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
    v2 = v3 == 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return v2;
}

```

## disassembly

```asm
0x1800174cc  mov     [rsp+arg_0], rbx
0x1800174d1  mov     [rsp+arg_8], rbp
0x1800174d6  mov     [rsp+arg_10], rsi
0x1800174db  push    rdi
0x1800174dc  sub     rsp, 20h
0x1800174e0  mov     rdi, rcx
0x1800174e3  add     rcx, 8; lpCriticalSection
0x1800174e7  call    cs:__imp_EnterCriticalSection
0x1800174ed  xor     esi, esi
0x1800174ef  cmp     [rdi+3F4Ch], esi
0x1800174f5  jz      short loc_180017522
0x1800174f7  lea     rcx, [rdi+138h]; lpCriticalSection
0x1800174fe  call    cs:__imp_EnterCriticalSection
0x180017504  mov     ebx, esi
0x180017506  lock xadd [rdi+15E8h], ebx
0x18001750e  lea     rcx, [rdi+138h]; lpCriticalSection
0x180017515  call    cs:__imp_LeaveCriticalSection
0x18001751b  test    ebx, ebx
0x18001751d  jnz     short loc_180017522
0x18001751f  lea     esi, [rbx+1]
0x180017522  lea     rcx, [rdi+8]; lpCriticalSection
0x180017526  call    cs:__imp_LeaveCriticalSection
0x18001752c  mov     rbx, [rsp+28h+arg_0]
0x180017531  mov     eax, esi
0x180017533  mov     rsi, [rsp+28h+arg_10]
0x180017538  mov     rbp, [rsp+28h+arg_8]
0x18001753d  add     rsp, 20h
0x180017541  pop     rdi
0x180017542  retn
```
