# ComTaskHost::AddRef(void)

- ea: `0x140006e00`
- end: `0x140006e51`
- name: `?AddRef@ComTaskHost@@UEAAKXZ`
- size: `81`
- prototype: `__int64 __fastcall(ComTaskHost *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140009bb0`

## callees

- `0x140006e00`
- `0x1400093b0`

## pseudocode

```c
__int64 __fastcall ComTaskHost::AddRef(ComTaskHost *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedIncrement((volatile signed __int32 *)this + 5);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e3bcaed62523302f0a82482d58f13b85_Traceguids, this, v1);
  return v1;
}

```

## disassembly

```asm
0x140006e00  push    rbx
0x140006e02  sub     rsp, 30h
0x140006e06  mov     r9, rcx
0x140006e09  mov     ebx, 1
0x140006e0e  lock xadd [rcx+14h], ebx
0x140006e13  inc     ebx
0x140006e15  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e1c  lea     rax, WPP_GLOBAL_Control
0x140006e23  cmp     rcx, rax
0x140006e26  jz      short loc_140006E2E
0x140006e28  test    byte ptr [rcx+1Ch], 4
0x140006e2c  jnz     short loc_140006E36
0x140006e2e  mov     eax, ebx
0x140006e30  add     rsp, 30h
0x140006e34  pop     rbx
0x140006e35  retn
0x140006e36  mov     rcx, [rcx+10h]
0x140006e3a  lea     r8, WPP_e3bcaed62523302f0a82482d58f13b85_Traceguids
0x140006e41  mov     edx, 0Ch
0x140006e46  mov     [rsp+38h+var_18], ebx
0x140006e4a  call    WPP_SF_qd
0x140006e4f  jmp     short loc_140006E2E
```
