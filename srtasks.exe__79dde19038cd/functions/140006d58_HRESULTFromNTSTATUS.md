# HRESULTFromNTSTATUS

- ea: `0x140006d58`
- end: `0x140006dd7`
- name: `HRESULTFromNTSTATUS`
- size: `127`
- prototype: `__int64 __fastcall(NTSTATUS)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140006cc8`
- `0x14000771c`
- `0x140007954`

## callees

- `0x140002e84`
- `0x140006d58`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x140006d6a`
- `ntdll!RtlNtStatusToDosError` at `0x140006d6a`

## pseudocode

```c
__int64 __fastcall HRESULTFromNTSTATUS(NTSTATUS a1)
{
  unsigned int v1; // ebx
  signed int v3; // eax

  v1 = 0;
  if ( a1 < 0 )
  {
    v3 = RtlNtStatusToDosError(a1);
    v1 = v3;
    if ( !v3 || v3 == 317 )
    {
      v1 = a1 | 0x10000000;
    }
    else if ( v3 > 0 )
    {
      v1 = (unsigned __int16)v3 | 0x80070000;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids,
        (unsigned int)a1,
        v1);
  }
  return v1;
}

```

## disassembly

```asm
0x140006d58  mov     [rsp+arg_0], rbx
0x140006d5d  push    rdi
0x140006d5e  sub     rsp, 30h
0x140006d62  xor     ebx, ebx
0x140006d64  mov     edi, ecx
0x140006d66  test    ecx, ecx
0x140006d68  jns     short loc_140006DCA
0x140006d6a  call    cs:__imp_RtlNtStatusToDosError
0x140006d70  mov     ebx, eax
0x140006d72  test    eax, eax
0x140006d74  jz      short loc_140006D8C
0x140006d76  cmp     eax, 13Dh
0x140006d7b  jz      short loc_140006D8C
0x140006d7d  test    eax, eax
0x140006d7f  jle     short loc_140006D92
0x140006d81  movzx   ebx, ax
0x140006d84  or      ebx, 80070000h
0x140006d8a  jmp     short loc_140006D92
0x140006d8c  mov     ebx, edi
0x140006d8e  bts     ebx, 1Ch
0x140006d92  mov     rcx, cs:WPP_GLOBAL_Control
0x140006d99  lea     rax, WPP_GLOBAL_Control
0x140006da0  cmp     rcx, rax
0x140006da3  jz      short loc_140006DCA
0x140006da5  test    dword ptr [rcx+1Ch], 1000000h
0x140006dac  jz      short loc_140006DCA
0x140006dae  mov     rcx, [rcx+10h]
0x140006db2  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x140006db9  mov     edx, 0Fh
0x140006dbe  mov     [rsp+38h+var_18], ebx
0x140006dc2  mov     r9d, edi
0x140006dc5  call    WPP_SF_dd
0x140006dca  mov     eax, ebx
0x140006dcc  mov     rbx, [rsp+38h+arg_0]
0x140006dd1  add     rsp, 30h
0x140006dd5  pop     rdi
0x140006dd6  retn
```
