# OutCompletePacketToClient

- ea: `0x140004860`
- end: `0x1400048ab`
- name: `OutCompletePacketToClient`
- size: `75`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400037e0`
- `0x1400068c0`
- `0x140008c7c`
- `0x140009a34`
- `0x14000d9b0`

## callees

- `0x140004860`
- `0x140011ed0`

## pseudocode

```c
__int64 __fastcall OutCompletePacketToClient(__int64 a1, __int64 a2, unsigned int a3)
{
  bool v3; // zf
  __int64 v4; // r10
  __int64 (__fastcall *v5)(__int64, __int64, __int64, _QWORD); // rax

  v3 = (*(_BYTE *)(a1 + 62) & 0x40) == 0;
  v4 = *(_QWORD *)(a1 + 104);
  v5 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(a1 + 88);
  *(_DWORD *)(a1 + 24) = 1;
  *(_BYTE *)(a1 + 61) = 0;
  *(_DWORD *)(a1 + 116) = a3;
  if ( v3 )
    return v5(a1, a2, v4, a3);
  else
    return ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, unsigned int))v5)(
             a1,
             *(_QWORD *)(a1 + 96),
             (unsigned int)a2,
             v4,
             a3);
}

```

## disassembly

```asm
0x140004860  sub     rsp, 38h
0x140004864  test    byte ptr [rcx+3Eh], 40h
0x140004868  mov     r11, [rcx+58h]
0x14000486c  mov     r10, [rcx+68h]
0x140004870  mov     rax, r11
0x140004873  mov     dword ptr [rcx+18h], 1
0x14000487a  mov     byte ptr [rcx+3Dh], 0
0x14000487e  mov     [rcx+74h], r8d
0x140004882  jz      short loc_14000489E
0x140004884  mov     [rsp+38h+var_18], r8d
0x140004889  mov     r9, r10
0x14000488c  mov     r8d, edx
0x14000488f  mov     rdx, [rcx+60h]
0x140004893  call    _guard_dispatch_icall
0x140004898  add     rsp, 38h
0x14000489c  retn
0x14000489e  mov     r9d, r8d
0x1400048a1  mov     r8, r10
0x1400048a4  call    _guard_dispatch_icall
0x1400048a9  jmp     short loc_140004898
```
