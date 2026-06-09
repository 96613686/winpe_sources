# CWSHRemoteFactory::LockServer(int)

- ea: `0x140001cf0`
- end: `0x140001d2a`
- name: `?LockServer@CWSHRemoteFactory@@UEAAJH@Z`
- size: `58`
- prototype: `__int64 __fastcall(CWSHRemoteFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001cf0`

## import_xrefs

- `USER32!PostThreadMessageA` at `0x140001d1d`
- `USER32!PostThreadMessageA` at `0x140001d1d`

## pseudocode

```c
__int64 __fastcall CWSHRemoteFactory::LockServer(CWSHRemoteFactory *this, int a2)
{
  if ( a2 )
  {
    _InterlockedIncrement(&dword_1400207D0);
  }
  else if ( _InterlockedExchangeAdd(&dword_1400207D0, 0xFFFFFFFF) == 1 )
  {
    PostThreadMessageA(*((_DWORD *)this + 3), 0x12u, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140001cf0  sub     rsp, 28h
0x140001cf4  test    edx, edx
0x140001cf6  jz      short loc_140001D01
0x140001cf8  lock inc cs:dword_1400207D0
0x140001cff  jmp     short loc_140001D23
0x140001d01  or      eax, 0FFFFFFFFh
0x140001d04  lock xadd cs:dword_1400207D0, eax
0x140001d0c  cmp     eax, 1
0x140001d0f  jnz     short loc_140001D23
0x140001d11  mov     ecx, [rcx+0Ch]; idThread
0x140001d14  lea     edx, [rax+11h]; Msg
0x140001d17  xor     r9d, r9d; lParam
0x140001d1a  xor     r8d, r8d; wParam
0x140001d1d  call    cs:__imp_PostThreadMessageA
0x140001d23  xor     eax, eax
0x140001d25  add     rsp, 28h
0x140001d29  retn
```
