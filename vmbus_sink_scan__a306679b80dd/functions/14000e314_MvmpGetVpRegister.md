# MvmpGetVpRegister

- ea: `0x14000e314`
- end: `0x14000e36d`
- name: `MvmpGetVpRegister`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d300`
- `0x14000d910`
- `0x14000da50`
- `0x14000dde8`
- `0x14000e0f0`
- `0x14000e408`

## callees

- `0x14000e314`
- `0x14000e374`
- `0x1400170a0`

## pseudocode

```c
__int64 __fastcall MvmpGetVpRegister(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  if ( a4 == 1 )
    goto LABEL_7;
  if ( *(_DWORD *)(a1 + 216) != 2 )
  {
    if ( !a4 )
      return __readmsr(a3);
LABEL_7:
    if ( *(_BYTE *)(a1 + 185) )
      a3 += 4096;
    return __readmsr(a3);
  }
  if ( a2 )
    return MvmpGetVpRegisterFromHostWithGhcb(a2, a3);
  else
    return MvmpGetVpRegisterFromHostDirect(a3);
}

```

## disassembly

```asm
0x14000e314  sub     rsp, 28h
0x14000e318  mov     rax, rdx
0x14000e31b  cmp     r9d, 1
0x14000e31f  jz      short loc_14000E34B
0x14000e321  cmp     dword ptr [rcx+0D8h], 2
0x14000e328  jnz     short loc_14000E346
0x14000e32a  test    rax, rax
0x14000e32d  jz      short loc_14000E33C
0x14000e32f  mov     edx, r8d
0x14000e332  mov     rcx, rax
0x14000e335  call    MvmpGetVpRegisterFromHostWithGhcb
0x14000e33a  jmp     short loc_14000E367
0x14000e33c  mov     ecx, r8d
0x14000e33f  call    MvmpGetVpRegisterFromHostDirect
0x14000e344  jmp     short loc_14000E367
0x14000e346  test    r9d, r9d
0x14000e349  jz      short loc_14000E35B
0x14000e34b  cmp     byte ptr [rcx+0B9h], 0
0x14000e352  jz      short loc_14000E35B
0x14000e354  add     r8d, 1000h
0x14000e35b  mov     ecx, r8d
0x14000e35e  rdmsr
0x14000e360  shl     rdx, 20h
0x14000e364  or      rax, rdx
0x14000e367  add     rsp, 28h
0x14000e36b  retn
```
