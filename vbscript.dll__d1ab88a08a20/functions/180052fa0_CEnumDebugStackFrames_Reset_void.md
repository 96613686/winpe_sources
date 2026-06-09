# CEnumDebugStackFrames::Reset(void)

- ea: `0x180052fa0`
- end: `0x180052ff6`
- name: `?Reset@CEnumDebugStackFrames@@UEAAJXZ`
- size: `86`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180045390`
- `0x180052fa0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180052fb0`
- `KERNEL32!GetCurrentThreadId` at `0x180052fb0`

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
0x180052fa0  mov     [rsp+arg_0], rbx
0x180052fa5  push    rdi
0x180052fa6  sub     rsp, 20h
0x180052faa  mov     ebx, [rcx+0Ch]
0x180052fad  mov     rdi, rcx
0x180052fb0  call    cs:__imp_GetCurrentThreadId
0x180052fb7  nop     dword ptr [rax+rax+00h]
0x180052fbc  cmp     eax, ebx
0x180052fbe  jz      short loc_180052FC7
0x180052fc0  mov     eax, 8000FFFFh
0x180052fc5  jmp     short loc_180052FEA
0x180052fc7  and     dword ptr [rdi+1Ch], 0FFFFFFFCh
0x180052fcb  mov     rcx, [rdi+20h]; this
0x180052fcf  mov     dword ptr [rdi+18h], 0
0x180052fd6  test    rcx, rcx
0x180052fd9  jz      short loc_180052FE8
0x180052fdb  call    ?Release@CDebugStackFrame@@UEAAKXZ; CDebugStackFrame::Release(void)
0x180052fe0  mov     qword ptr [rdi+20h], 0
0x180052fe8  xor     eax, eax
0x180052fea  mov     rbx, [rsp+28h+arg_0]
0x180052fef  add     rsp, 20h
0x180052ff3  pop     rdi
0x180052ff4  retn
```
