# CWSHRemote::CError::get_Line(long *)

- ea: `0x140001a80`
- end: `0x140001ad8`
- name: `?get_Line@CError@CWSHRemote@@UEAAJPEAJ@Z`
- size: `88`
- prototype: `__int64 __fastcall(CWSHRemote::CError *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001a80`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140001aaa`
- `KERNEL32!GetCurrentThreadId` at `0x140001aaa`

## pseudocode

```c
__int64 __fastcall CWSHRemote::CError::get_Line(CWSHRemote::CError *this, int *a2)
{
  int v5; // ebx

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = *((_DWORD *)this + 3);
  if ( GetCurrentThreadId() != v5 )
    return 2147549183LL;
  *a2 = _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140001a80  mov     [rsp+arg_0], rbx
0x140001a85  mov     [rsp+arg_8], rsi
0x140001a8a  push    rdi
0x140001a8b  sub     rsp, 20h
0x140001a8f  mov     rdi, rdx
0x140001a92  mov     rsi, rcx
0x140001a95  test    rdx, rdx
0x140001a98  jnz     short loc_140001AA1
0x140001a9a  mov     eax, 80004003h
0x140001a9f  jmp     short loc_140001AC8
0x140001aa1  mov     dword ptr [rdx], 0
0x140001aa7  mov     ebx, [rcx+0Ch]
0x140001aaa  call    cs:__imp_GetCurrentThreadId
0x140001ab0  cmp     eax, ebx
0x140001ab2  jz      short loc_140001ABB
0x140001ab4  mov     eax, 8000FFFFh
0x140001ab9  jmp     short loc_140001AC8
0x140001abb  xor     ecx, ecx
0x140001abd  xor     eax, eax
0x140001abf  lock cmpxchg [rsi+10h], ecx
0x140001ac4  mov     [rdi], eax
0x140001ac6  xor     eax, eax
0x140001ac8  mov     rbx, [rsp+28h+arg_0]
0x140001acd  mov     rsi, [rsp+28h+arg_8]
0x140001ad2  add     rsp, 20h
0x140001ad6  pop     rdi
0x140001ad7  retn
```
