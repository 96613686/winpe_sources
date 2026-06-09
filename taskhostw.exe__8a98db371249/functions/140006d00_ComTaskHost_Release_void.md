# ComTaskHost::Release(void)

- ea: `0x140006d00`
- end: `0x140006d7c`
- name: `?Release@ComTaskHost@@UEAAKXZ`
- size: `124`
- prototype: `__int64 __fastcall(ComTaskHost *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140009bd0`

## callees

- `0x140006d00`
- `0x1400093b0`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall ComTaskHost::Release(ComTaskHost *this)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 5);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_e3bcaed62523302f0a82482d58f13b85_Traceguids, this, v2);
  if ( !v2 && this )
    (*(void (__fastcall **)(ComTaskHost *, __int64))(*(_QWORD *)this + 40LL))(this, 1);
  return v2;
}

```

## disassembly

```asm
0x140006d00  mov     [rsp+arg_0], rbx
0x140006d05  push    rdi
0x140006d06  sub     rsp, 30h
0x140006d0a  mov     rdi, rcx
0x140006d0d  mov     ebx, 0FFFFFFFFh
0x140006d12  lock xadd [rcx+14h], ebx
0x140006d17  dec     ebx
0x140006d19  mov     rcx, cs:WPP_GLOBAL_Control
0x140006d20  lea     rax, WPP_GLOBAL_Control
0x140006d27  cmp     rcx, rax
0x140006d2a  jz      short loc_140006D32
0x140006d2c  test    byte ptr [rcx+1Ch], 4
0x140006d30  jnz     short loc_140006D5E
0x140006d32  test    ebx, ebx
0x140006d34  jz      short loc_140006D43
0x140006d36  mov     eax, ebx
0x140006d38  mov     rbx, [rsp+38h+arg_0]
0x140006d3d  add     rsp, 30h
0x140006d41  pop     rdi
0x140006d42  retn
0x140006d43  test    rdi, rdi
0x140006d46  jz      short loc_140006D36
0x140006d48  mov     rax, [rdi]
0x140006d4b  mov     edx, 1
0x140006d50  mov     rcx, rdi
0x140006d53  mov     rax, [rax+28h]
0x140006d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d5c  jmp     short loc_140006D36
0x140006d5e  mov     rcx, [rcx+10h]
0x140006d62  lea     r8, WPP_e3bcaed62523302f0a82482d58f13b85_Traceguids
0x140006d69  mov     edx, 0Dh
0x140006d6e  mov     [rsp+38h+var_18], ebx
0x140006d72  mov     r9, rdi
0x140006d75  call    WPP_SF_qd
0x140006d7a  jmp     short loc_140006D32
```
