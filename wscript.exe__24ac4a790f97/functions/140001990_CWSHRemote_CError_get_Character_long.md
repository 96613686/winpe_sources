# CWSHRemote::CError::get_Character(long *)

- ea: `0x140001990`
- end: `0x1400019e8`
- name: `?get_Character@CError@CWSHRemote@@UEAAJPEAJ@Z`
- size: `88`
- prototype: `__int64 __fastcall(CWSHRemote::CError *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001990`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400019ba`
- `KERNEL32!GetCurrentThreadId` at `0x1400019ba`

## pseudocode

```c
__int64 __fastcall CWSHRemote::CError::get_Character(CWSHRemote::CError *this, int *a2)
{
  int v5; // ebx

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = *((_DWORD *)this + 3);
  if ( GetCurrentThreadId() != v5 )
    return 2147549183LL;
  *a2 = _InterlockedCompareExchange((volatile signed __int32 *)this + 6, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140001990  mov     [rsp+arg_0], rbx
0x140001995  mov     [rsp+arg_8], rsi
0x14000199a  push    rdi
0x14000199b  sub     rsp, 20h
0x14000199f  mov     rdi, rdx
0x1400019a2  mov     rsi, rcx
0x1400019a5  test    rdx, rdx
0x1400019a8  jnz     short loc_1400019B1
0x1400019aa  mov     eax, 80004003h
0x1400019af  jmp     short loc_1400019D8
0x1400019b1  mov     dword ptr [rdx], 0
0x1400019b7  mov     ebx, [rcx+0Ch]
0x1400019ba  call    cs:__imp_GetCurrentThreadId
0x1400019c0  cmp     eax, ebx
0x1400019c2  jz      short loc_1400019CB
0x1400019c4  mov     eax, 8000FFFFh
0x1400019c9  jmp     short loc_1400019D8
0x1400019cb  xor     ecx, ecx
0x1400019cd  xor     eax, eax
0x1400019cf  lock cmpxchg [rsi+18h], ecx
0x1400019d4  mov     [rdi], eax
0x1400019d6  xor     eax, eax
0x1400019d8  mov     rbx, [rsp+28h+arg_0]
0x1400019dd  mov     rsi, [rsp+28h+arg_8]
0x1400019e2  add     rsp, 20h
0x1400019e6  pop     rdi
0x1400019e7  retn
```
