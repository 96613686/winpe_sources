# CWSHRemote::Unadvise(ulong)

- ea: `0x140002dc0`
- end: `0x140002e42`
- name: `?Unadvise@CWSHRemote@@UEAAJK@Z`
- size: `130`
- prototype: `__int64 __fastcall(CWSHRemote *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002dc0`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002dd7`
- `KERNEL32!GetCurrentThreadId` at `0x140002dd7`

## pseudocode

```c
__int64 __fastcall CWSHRemote::Unadvise(CWSHRemote *this, int a2)
{
  int v2; // ebx
  int v6; // ebx
  __int64 v7; // rcx

  v2 = *((_DWORD *)this + 4);
  if ( GetCurrentThreadId() != v2 )
    return 2147549183LL;
  v6 = a2 - 1;
  if ( (unsigned int)(a2 - 1) > 0x31 )
    return 2147746304LL;
  _mm_lfence();
  v7 = *((_QWORD *)this + v6 + 18);
  if ( !v7 )
    return 2147746304LL;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  *((_QWORD *)this + v6 + 18) = 0;
  if ( v6 < *((_DWORD *)this + 136) )
    *((_DWORD *)this + 136) = v6;
  return 0;
}

```

## disassembly

```asm
0x140002dc0  mov     [rsp+arg_0], rbx
0x140002dc5  mov     [rsp+arg_8], rsi
0x140002dca  push    rdi
0x140002dcb  sub     rsp, 20h
0x140002dcf  mov     ebx, [rcx+10h]
0x140002dd2  mov     esi, edx
0x140002dd4  mov     rdi, rcx
0x140002dd7  call    cs:__imp_GetCurrentThreadId
0x140002ddd  cmp     eax, ebx
0x140002ddf  jz      short loc_140002DE8
0x140002de1  mov     eax, 8000FFFFh
0x140002de6  jmp     short loc_140002E32
0x140002de8  lea     ebx, [rsi-1]
0x140002deb  cmp     ebx, 31h ; '1'
0x140002dee  ja      short loc_140002E2D
0x140002df0  lfence
0x140002df3  movsxd  rsi, ebx
0x140002df6  mov     rcx, [rdi+rsi*8+90h]
0x140002dfe  test    rcx, rcx
0x140002e01  jz      short loc_140002E2D
0x140002e03  mov     rax, [rcx]
0x140002e06  mov     rax, [rax+10h]
0x140002e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e0f  mov     qword ptr [rdi+rsi*8+90h], 0
0x140002e1b  cmp     ebx, [rdi+220h]
0x140002e21  jge     short loc_140002E29
0x140002e23  mov     [rdi+220h], ebx
0x140002e29  xor     eax, eax
0x140002e2b  jmp     short loc_140002E32
0x140002e2d  mov     eax, 80040200h
0x140002e32  mov     rbx, [rsp+28h+arg_0]
0x140002e37  mov     rsi, [rsp+28h+arg_8]
0x140002e3c  add     rsp, 20h
0x140002e40  pop     rdi
0x140002e41  retn
```
