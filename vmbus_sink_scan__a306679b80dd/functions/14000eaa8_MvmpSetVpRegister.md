# MvmpSetVpRegister

- ea: `0x14000eaa8`
- end: `0x14000eb0f`
- name: `MvmpSetVpRegister`
- size: `103`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e008`
- `0x14000e0f0`
- `0x14000e408`
- `0x14000e910`

## callees

- `0x14000eaa8`
- `0x14000eb18`
- `0x1400170d0`

## pseudocode

```c
__int64 __fastcall MvmpSetVpRegister(__int64 a1, __int64 a2, unsigned int a3, unsigned __int64 a4, int a5)
{
  unsigned int v5; // r10d
  __int64 result; // rax

  v5 = a3;
  if ( a5 == 1 )
    goto LABEL_7;
  if ( *(_DWORD *)(a1 + 216) != 2 )
  {
    if ( !a5 )
    {
LABEL_9:
      result = a4;
      __writemsr(v5, a4);
      return result;
    }
LABEL_7:
    if ( *(_BYTE *)(a1 + 185) )
      v5 = a3 + 4096;
    goto LABEL_9;
  }
  if ( a2 )
    return MvmpSetVpRegisterInHostWithGhcb(a2, a3, a4);
  else
    return MvmpSetVpRegisterInHostDirect(a3, a4);
}

```

## disassembly

```asm
0x14000eaa8  sub     rsp, 28h
0x14000eaac  mov     rax, rdx
0x14000eaaf  mov     r10d, r8d
0x14000eab2  mov     edx, [rsp+28h+arg_20]
0x14000eab6  cmp     edx, 1
0x14000eab9  jz      short loc_14000EAEA
0x14000eabb  cmp     dword ptr [rcx+0D8h], 2
0x14000eac2  jnz     short loc_14000EAE6
0x14000eac4  test    rax, rax
0x14000eac7  jz      short loc_14000EAD9
0x14000eac9  mov     r8, r9
0x14000eacc  mov     edx, r10d
0x14000eacf  mov     rcx, rax
0x14000ead2  call    MvmpSetVpRegisterInHostWithGhcb
0x14000ead7  jmp     short loc_14000EB09
0x14000ead9  mov     rdx, r9
0x14000eadc  mov     ecx, r10d
0x14000eadf  call    MvmpSetVpRegisterInHostDirect
0x14000eae4  jmp     short loc_14000EB09
0x14000eae6  test    edx, edx
0x14000eae8  jz      short loc_14000EAFA
0x14000eaea  cmp     byte ptr [rcx+0B9h], 0
0x14000eaf1  jz      short loc_14000EAFA
0x14000eaf3  add     r10d, 1000h
0x14000eafa  mov     rdx, r9
0x14000eafd  mov     rax, r9
0x14000eb00  shr     rdx, 20h
0x14000eb04  mov     ecx, r10d
0x14000eb07  wrmsr
0x14000eb09  add     rsp, 28h
0x14000eb0d  retn
```
