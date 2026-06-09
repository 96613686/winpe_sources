# CEnumDebugStackFrames::Skip(ulong)

- ea: `0x180053200`
- end: `0x180053244`
- name: `?Skip@CEnumDebugStackFrames@@UEAAJK@Z`
- size: `68`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180053200`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180053217`
- `KERNEL32!GetCurrentThreadId` at `0x180053217`

## pseudocode

```c
__int64 __fastcall CEnumDebugStackFrames::Skip(CEnumDebugStackFrames *this, int a2)
{
  int v2; // ebx

  v2 = *((_DWORD *)this + 3);
  if ( GetCurrentThreadId() != v2 )
    return 2147549183LL;
  *((_DWORD *)this + 6) += a2;
  return 0;
}

```

## disassembly

```asm
0x180053200  mov     [rsp+arg_0], rbx
0x180053205  mov     [rsp+arg_8], rsi
0x18005320a  push    rdi
0x18005320b  sub     rsp, 20h
0x18005320f  mov     ebx, [rcx+0Ch]
0x180053212  mov     esi, edx
0x180053214  mov     rdi, rcx
0x180053217  call    cs:__imp_GetCurrentThreadId
0x18005321e  nop     dword ptr [rax+rax+00h]
0x180053223  cmp     eax, ebx
0x180053225  jz      short loc_18005322E
0x180053227  mov     eax, 8000FFFFh
0x18005322c  jmp     short loc_180053233
0x18005322e  add     [rdi+18h], esi
0x180053231  xor     eax, eax
0x180053233  mov     rbx, [rsp+28h+arg_0]
0x180053238  mov     rsi, [rsp+28h+arg_8]
0x18005323d  add     rsp, 20h
0x180053241  pop     rdi
0x180053242  retn
```
