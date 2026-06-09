# MincryptFreePolicyInfo

- ea: `0x180018a04`
- end: `0x180018a34`
- name: `MincryptFreePolicyInfo`
- size: `48`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180044a70`
- `0x18004a128`
- `0x18004a2cc`
- `0x18004a858`
- `0x18004a8c0`
- `0x18004a948`
- `0x18004adbc`

## callees

- `0x1800187d4`
- `0x180018a04`

## pseudocode

```c
__int64 __fastcall MincryptFreePolicyInfo(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
  {
    if ( *(_DWORD *)a1 )
    {
      result = SIPolicyFree(*(_QWORD *)(a1 + 16));
      *(_OWORD *)a1 = 0;
      *(_OWORD *)(a1 + 16) = 0;
      *(_OWORD *)(a1 + 32) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018a04  test    rcx, rcx
0x180018a07  jz      short locret_180018A32
0x180018a09  push    rbx
0x180018a0a  sub     rsp, 20h
0x180018a0e  cmp     dword ptr [rcx], 0
0x180018a11  mov     rbx, rcx
0x180018a14  jz      short loc_180018A2D
0x180018a16  mov     rcx, [rcx+10h]
0x180018a1a  call    SIPolicyFree
0x180018a1f  xorps   xmm0, xmm0
0x180018a22  movups  xmmword ptr [rbx], xmm0
0x180018a25  movups  xmmword ptr [rbx+10h], xmm0
0x180018a29  movups  xmmword ptr [rbx+20h], xmm0
0x180018a2d  add     rsp, 20h
0x180018a31  pop     rbx
0x180018a32  retn
```
