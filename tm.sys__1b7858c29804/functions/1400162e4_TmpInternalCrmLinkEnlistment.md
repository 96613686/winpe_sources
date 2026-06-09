# TmpInternalCrmLinkEnlistment

- ea: `0x1400162e4`
- end: `0x140016338`
- name: `TmpInternalCrmLinkEnlistment`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400153b8`

## pseudocode

```c
__int64 __fastcall TmpInternalCrmLinkEnlistment(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax

  *(_QWORD *)(a1 + 240) = a2;
  *(_QWORD *)(a1 + 248) = a3;
  _InterlockedOr((volatile signed __int32 *)(a1 + 172), 0x20u);
  *(_OWORD *)(a1 + 264) = *(_OWORD *)(a2 + 48);
  *(_OWORD *)(a1 + 280) = *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 152) + 360LL) + 112LL);
  result = *(_QWORD *)(a2 + 152);
  *(_OWORD *)(a1 + 296) = *(_OWORD *)(result + 136);
  return result;
}

```

## disassembly

```asm
0x1400162e4  mov     [rcx+0F0h], rdx
0x1400162eb  mov     [rcx+0F8h], r8
0x1400162f2  lock or dword ptr [rcx+0ACh], 20h
0x1400162fa  movups  xmm0, xmmword ptr [rdx+30h]
0x1400162fe  movdqu  xmmword ptr [rcx+108h], xmm0
0x140016306  mov     rax, [rdx+98h]
0x14001630d  mov     r8, [rax+168h]
0x140016314  movups  xmm0, xmmword ptr [r8+70h]
0x140016319  movdqu  xmmword ptr [rcx+118h], xmm0
0x140016321  mov     rax, [rdx+98h]
0x140016328  movups  xmm1, xmmword ptr [rax+88h]
0x14001632f  movdqu  xmmword ptr [rcx+128h], xmm1
0x140016337  retn
```
