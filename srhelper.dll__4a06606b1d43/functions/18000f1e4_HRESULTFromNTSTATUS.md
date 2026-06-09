# HRESULTFromNTSTATUS

- ea: `0x18000f1e4`
- end: `0x18000f263`
- name: `HRESULTFromNTSTATUS`
- size: `127`
- prototype: `__int64 __fastcall(NTSTATUS)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000deac`
- `0x18000e0dc`
- `0x18000e7ec`
- `0x18000f154`

## callees

- `0x1800070d4`
- `0x18000f1e4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000f1f6`
- `ntdll!RtlNtStatusToDosError` at `0x18000f1f6`

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
0x18000f1e4  mov     [rsp+arg_0], rbx
0x18000f1e9  push    rdi
0x18000f1ea  sub     rsp, 30h
0x18000f1ee  xor     ebx, ebx
0x18000f1f0  mov     edi, ecx
0x18000f1f2  test    ecx, ecx
0x18000f1f4  jns     short loc_18000F256
0x18000f1f6  call    cs:__imp_RtlNtStatusToDosError
0x18000f1fc  mov     ebx, eax
0x18000f1fe  test    eax, eax
0x18000f200  jz      short loc_18000F218
0x18000f202  cmp     eax, 13Dh
0x18000f207  jz      short loc_18000F218
0x18000f209  test    eax, eax
0x18000f20b  jle     short loc_18000F21E
0x18000f20d  movzx   ebx, ax
0x18000f210  or      ebx, 80070000h
0x18000f216  jmp     short loc_18000F21E
0x18000f218  mov     ebx, edi
0x18000f21a  bts     ebx, 1Ch
0x18000f21e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f225  lea     rax, WPP_GLOBAL_Control
0x18000f22c  cmp     rcx, rax
0x18000f22f  jz      short loc_18000F256
0x18000f231  test    dword ptr [rcx+1Ch], 1000000h
0x18000f238  jz      short loc_18000F256
0x18000f23a  mov     rcx, [rcx+10h]
0x18000f23e  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18000f245  mov     edx, 0Fh
0x18000f24a  mov     [rsp+38h+var_18], ebx
0x18000f24e  mov     r9d, edi
0x18000f251  call    WPP_SF_dd
0x18000f256  mov     eax, ebx
0x18000f258  mov     rbx, [rsp+38h+arg_0]
0x18000f25d  add     rsp, 30h
0x18000f261  pop     rdi
0x18000f262  retn
```
