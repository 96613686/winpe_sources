# CUnknownImplT<CTokenActivation,0>::Release(void)

- ea: `0x18001d430`
- end: `0x18001d46a`
- name: `?Release@?$CUnknownImplT@VCTokenActivation@@$0A@@@UEAAKXZ`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d470`

## callees

- `0x18001d430`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CTokenActivation,0>::Release(volatile signed __int32 *a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement(a1 + 70);
  if ( !v1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 72LL))(a1, 1);
    _InterlockedDecrement(&CComProcessCounter<0>::g_lServerLockCount);
  }
  return v1;
}

```

## disassembly

```asm
0x18001d430  push    rbx
0x18001d432  sub     rsp, 20h
0x18001d436  or      ebx, 0FFFFFFFFh
0x18001d439  lock xadd [rcx+118h], ebx
0x18001d441  sub     ebx, 1
0x18001d444  jnz     short loc_18001D461
0x18001d446  test    rcx, rcx
0x18001d449  jz      short loc_18001D45A
0x18001d44b  mov     rdx, [rcx]
0x18001d44e  mov     rax, [rdx+48h]
0x18001d452  lea     edx, [rbx+1]
0x18001d455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d45a  lock dec cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001d461  mov     eax, ebx
0x18001d463  add     rsp, 20h
0x18001d467  pop     rbx
0x18001d468  retn
```
