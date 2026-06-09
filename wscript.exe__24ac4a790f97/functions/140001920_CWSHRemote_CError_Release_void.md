# CWSHRemote::CError::Release(void)

- ea: `0x140001920`
- end: `0x14000197c`
- name: `?Release@CError@CWSHRemote@@UEAAKXZ`
- size: `92`
- prototype: `unsigned int __fastcall(CWSHRemote::CError *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x140001048`
- `0x1400014c0`
- `0x140001920`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000193a`
- `KERNEL32!GetCurrentThreadId` at `0x14000193a`
- `USER32!PostThreadMessageA` at `0x140001969`
- `USER32!PostThreadMessageA` at `0x140001969`

## pseudocode

```c
__int64 __fastcall CWSHRemote::CError::Release(CWSHRemote::CError *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 )
  {
    if ( GetCurrentThreadId() == *((_DWORD *)this + 3) )
    {
      CWSHRemote::CError::~CError(this);
      operator delete(this);
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 2);
      PostThreadMessageA(*((_DWORD *)this + 3), 0x40Bu, (WPARAM)this, 0);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140001920  mov     [rsp+arg_0], rbx
0x140001925  push    rdi
0x140001926  sub     rsp, 20h
0x14000192a  mov     rbx, rcx
0x14000192d  or      edi, 0FFFFFFFFh
0x140001930  lock xadd [rcx+8], edi
0x140001935  sub     edi, 1
0x140001938  jnz     short loc_14000196F
0x14000193a  call    cs:__imp_GetCurrentThreadId
0x140001940  cmp     eax, [rbx+0Ch]
0x140001943  jnz     short loc_140001957
0x140001945  mov     rcx, rbx; this
0x140001948  call    ??1CError@CWSHRemote@@AEAA@XZ; CWSHRemote::CError::~CError(void)
0x14000194d  mov     rcx, rbx; Block
0x140001950  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001955  jmp     short loc_14000196F
0x140001957  lock inc dword ptr [rbx+8]
0x14000195b  mov     ecx, [rbx+0Ch]; idThread
0x14000195e  xor     r9d, r9d; lParam
0x140001961  mov     r8, rbx; wParam
0x140001964  mov     edx, 40Bh; Msg
0x140001969  call    cs:__imp_PostThreadMessageA
0x14000196f  mov     rbx, [rsp+28h+arg_0]
0x140001974  mov     eax, edi
0x140001976  add     rsp, 20h
0x14000197a  pop     rdi
0x14000197b  retn
```
