# CEnumDebugStackFrames::Reset(void)

- ea: `0x1800517b0`
- end: `0x1800517ff`
- name: `?Reset@CEnumDebugStackFrames@@UEAAJXZ`
- size: `79`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180044130`
- `0x1800517b0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800517c0`
- `KERNEL32!GetCurrentThreadId` at `0x1800517c0`

## pseudocode

```c
__int64 __fastcall CEnumDebugStackFrames::Reset(CEnumDebugStackFrames *this)
{
  int v1; // ebx
  CDebugStackFrame *v4; // rcx

  v1 = *((_DWORD *)this + 3);
  if ( GetCurrentThreadId() != v1 )
    return 2147549183LL;
  *((_DWORD *)this + 7) &= 0xFFFFFFFC;
  v4 = (CDebugStackFrame *)*((_QWORD *)this + 4);
  *((_DWORD *)this + 6) = 0;
  if ( v4 )
  {
    CDebugStackFrame::Release(v4);
    *((_QWORD *)this + 4) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800517b0  mov     [rsp+arg_0], rbx
0x1800517b5  push    rdi
0x1800517b6  sub     rsp, 20h
0x1800517ba  mov     ebx, [rcx+0Ch]
0x1800517bd  mov     rdi, rcx
0x1800517c0  call    cs:__imp_GetCurrentThreadId
0x1800517c6  cmp     eax, ebx
0x1800517c8  jz      short loc_1800517D1
0x1800517ca  mov     eax, 8000FFFFh
0x1800517cf  jmp     short loc_1800517F4
0x1800517d1  and     dword ptr [rdi+1Ch], 0FFFFFFFCh
0x1800517d5  mov     rcx, [rdi+20h]; this
0x1800517d9  mov     dword ptr [rdi+18h], 0
0x1800517e0  test    rcx, rcx
0x1800517e3  jz      short loc_1800517F2
0x1800517e5  call    ?Release@CDebugStackFrame@@UEAAKXZ; CDebugStackFrame::Release(void)
0x1800517ea  mov     qword ptr [rdi+20h], 0
0x1800517f2  xor     eax, eax
0x1800517f4  mov     rbx, [rsp+28h+arg_0]
0x1800517f9  add     rsp, 20h
0x1800517fd  pop     rdi
0x1800517fe  retn
```
