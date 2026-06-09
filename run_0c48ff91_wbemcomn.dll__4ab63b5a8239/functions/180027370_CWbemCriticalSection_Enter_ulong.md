# CWbemCriticalSection::Enter(ulong)

- ea: `0x180027370`
- end: `0x1800273c8`
- name: `?Enter@CWbemCriticalSection@@QEAAHK@Z`
- size: `88`
- prototype: `int(CWbemCriticalSection *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002be90`

## callees

- `0x180027370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800273b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800273b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002737e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002737e`

## pseudocode

```c
__int64 __fastcall CWbemCriticalSection::Enter(CWbemCriticalSection *this, DWORD a2)
{
  DWORD CurrentThreadId; // eax
  bool v5; // zf
  unsigned int v6; // ebx
  DWORD v7; // esi
  __int64 result; // rax

  CurrentThreadId = GetCurrentThreadId();
  v5 = CurrentThreadId == *((_DWORD *)this + 2);
  v6 = 1;
  v7 = CurrentThreadId;
  result = 1;
  if ( v5 )
  {
    _InterlockedAdd((volatile signed __int32 *)this + 1, 1u);
  }
  else
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)this, 1u) == -1
      || !WaitForSingleObject(*((HANDLE *)this + 2), a2) )
    {
      *((_DWORD *)this + 2) = v7;
      *((_DWORD *)this + 1) = 1;
    }
    else
    {
      v6 = 0;
      _InterlockedDecrement((volatile signed __int32 *)this);
    }
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180027370  push    rbx
0x180027372  push    rbp
0x180027373  push    rsi
0x180027374  push    rdi
0x180027375  sub     rsp, 28h
0x180027379  mov     ebp, edx
0x18002737b  mov     rdi, rcx
0x18002737e  call    cs:__imp_GetCurrentThreadId
0x180027384  cmp     eax, [rdi+8]
0x180027387  mov     ebx, 1
0x18002738c  mov     esi, eax
0x18002738e  mov     eax, ebx
0x180027390  jz      short loc_1800273AB
0x180027392  lock xadd [rdi], eax
0x180027396  add     eax, ebx
0x180027398  jnz     short loc_1800273B1
0x18002739a  mov     [rdi+8], esi
0x18002739d  mov     [rdi+4], ebx
0x1800273a0  mov     eax, ebx
0x1800273a2  add     rsp, 28h
0x1800273a6  pop     rdi
0x1800273a7  pop     rsi
0x1800273a8  pop     rbp
0x1800273a9  pop     rbx
0x1800273aa  retn
0x1800273ab  lock add [rdi+4], ebx
0x1800273af  jmp     short loc_1800273A2
0x1800273b1  mov     rcx, [rdi+10h]; hHandle
0x1800273b5  mov     edx, ebp; dwMilliseconds
0x1800273b7  call    cs:__imp_WaitForSingleObject
0x1800273bd  test    eax, eax
0x1800273bf  jz      short loc_18002739A
0x1800273c1  xor     ebx, ebx
0x1800273c3  lock dec dword ptr [rdi]
0x1800273c6  jmp     short loc_1800273A0
```
