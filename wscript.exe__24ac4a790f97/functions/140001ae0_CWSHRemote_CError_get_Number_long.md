# CWSHRemote::CError::get_Number(long *)

- ea: `0x140001ae0`
- end: `0x140001b38`
- name: `?get_Number@CError@CWSHRemote@@UEAAJPEAJ@Z`
- size: `88`
- prototype: `__int64 __fastcall(CWSHRemote::CError *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001ae0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140001b0a`
- `KERNEL32!GetCurrentThreadId` at `0x140001b0a`

## pseudocode

```c
__int64 __fastcall CWSHRemote::CError::get_Number(CWSHRemote::CError *this, int *a2)
{
  int v5; // ebx

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = *((_DWORD *)this + 3);
  if ( GetCurrentThreadId() != v5 )
    return 2147549183LL;
  *a2 = _InterlockedCompareExchange((volatile signed __int32 *)this + 5, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140001ae0  mov     [rsp+arg_0], rbx
0x140001ae5  mov     [rsp+arg_8], rsi
0x140001aea  push    rdi
0x140001aeb  sub     rsp, 20h
0x140001aef  mov     rdi, rdx
0x140001af2  mov     rsi, rcx
0x140001af5  test    rdx, rdx
0x140001af8  jnz     short loc_140001B01
0x140001afa  mov     eax, 80004003h
0x140001aff  jmp     short loc_140001B28
0x140001b01  mov     dword ptr [rdx], 0
0x140001b07  mov     ebx, [rcx+0Ch]
0x140001b0a  call    cs:__imp_GetCurrentThreadId
0x140001b10  cmp     eax, ebx
0x140001b12  jz      short loc_140001B1B
0x140001b14  mov     eax, 8000FFFFh
0x140001b19  jmp     short loc_140001B28
0x140001b1b  xor     ecx, ecx
0x140001b1d  xor     eax, eax
0x140001b1f  lock cmpxchg [rsi+14h], ecx
0x140001b24  mov     [rdi], eax
0x140001b26  xor     eax, eax
0x140001b28  mov     rbx, [rsp+28h+arg_0]
0x140001b2d  mov     rsi, [rsp+28h+arg_8]
0x140001b32  add     rsp, 20h
0x140001b36  pop     rdi
0x140001b37  retn
```
