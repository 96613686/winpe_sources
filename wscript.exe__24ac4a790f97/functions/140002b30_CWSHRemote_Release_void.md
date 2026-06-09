# CWSHRemote::Release(void)

- ea: `0x140002b30`
- end: `0x140002b8c`
- name: `?Release@CWSHRemote@@UEAAKXZ`
- size: `92`
- prototype: `unsigned int __fastcall(CWSHRemote *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140002ba0`
- `0x140002bb0`
- `0x140002bc0`

## callees

- `0x140001048`
- `0x140001dd8`
- `0x140002b30`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002b4a`
- `KERNEL32!GetCurrentThreadId` at `0x140002b4a`
- `USER32!PostThreadMessageA` at `0x140002b79`
- `USER32!PostThreadMessageA` at `0x140002b79`

## pseudocode

```c
__int64 __fastcall CWSHRemote::Release(CWSHRemote *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( !v2 )
  {
    if ( GetCurrentThreadId() == *((_DWORD *)this + 10) )
    {
      CWSHRemote::~CWSHRemote(this);
      operator delete(this);
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 8);
      PostThreadMessageA(*((_DWORD *)this + 10), 0x40Bu, (WPARAM)this, 0);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140002b30  mov     [rsp+arg_0], rbx
0x140002b35  push    rdi
0x140002b36  sub     rsp, 20h
0x140002b3a  mov     rbx, rcx
0x140002b3d  or      edi, 0FFFFFFFFh
0x140002b40  lock xadd [rcx+20h], edi
0x140002b45  sub     edi, 1
0x140002b48  jnz     short loc_140002B7F
0x140002b4a  call    cs:__imp_GetCurrentThreadId
0x140002b50  cmp     eax, [rbx+28h]
0x140002b53  jnz     short loc_140002B67
0x140002b55  mov     rcx, rbx; this
0x140002b58  call    ??1CWSHRemote@@QEAA@XZ; CWSHRemote::~CWSHRemote(void)
0x140002b5d  mov     rcx, rbx; Block
0x140002b60  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002b65  jmp     short loc_140002B7F
0x140002b67  lock inc dword ptr [rbx+20h]
0x140002b6b  mov     ecx, [rbx+28h]; idThread
0x140002b6e  xor     r9d, r9d; lParam
0x140002b71  mov     r8, rbx; wParam
0x140002b74  mov     edx, 40Bh; Msg
0x140002b79  call    cs:__imp_PostThreadMessageA
0x140002b7f  mov     rbx, [rsp+28h+arg_0]
0x140002b84  mov     eax, edi
0x140002b86  add     rsp, 20h
0x140002b8a  pop     rdi
0x140002b8b  retn
```
