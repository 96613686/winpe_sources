# NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::RemoveAtHead(void)

- ea: `0x140013adc`
- end: `0x140013b1e`
- name: `?RemoveAtHead@?$TList@VTWorkItem@NThreadingLibrary@@@NCoreLibrary@@QEAAPEAVTWorkItem@NThreadingLibrary@@XZ`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140013640`
- `0x140013b24`

## callees

- `0x140013adc`

## pseudocode

```c
__int64 __fastcall NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::RemoveAtHead(__int64 a1)
{
  __int64 v1; // r8

  v1 = *(_QWORD *)(a1 + 24);
  *(_QWORD *)(*(_QWORD *)(v1 + 16) + 24LL) = *(_QWORD *)(v1 + 24);
  *(_QWORD *)(*(_QWORD *)(v1 + 24) + 16LL) = *(_QWORD *)(v1 + 16);
  *(_QWORD *)(v1 + 16) = v1;
  *(_QWORD *)(v1 + 24) = v1;
  if ( v1 == a1 + 8 )
    return 0;
  else
    return (v1 - 32) & -(__int64)(v1 != 0);
}

```

## disassembly

```asm
0x140013adc  lea     rdx, [rcx+8]
0x140013ae0  mov     r8, [rdx+10h]
0x140013ae4  mov     rcx, [r8+10h]
0x140013ae8  mov     rax, [r8+18h]
0x140013aec  mov     [rcx+18h], rax
0x140013af0  mov     rcx, [r8+18h]
0x140013af4  mov     rax, [r8+10h]
0x140013af8  mov     [rcx+10h], rax
0x140013afc  mov     [r8+10h], r8
0x140013b00  mov     [r8+18h], r8
0x140013b04  cmp     r8, rdx
0x140013b07  jz      short loc_140013B18
0x140013b09  lea     rax, [r8-20h]
0x140013b0d  neg     r8
0x140013b10  sbb     rcx, rcx
0x140013b13  and     rcx, rax
0x140013b16  jmp     short loc_140013B1A
0x140013b18  xor     ecx, ecx
0x140013b1a  mov     rax, rcx
0x140013b1d  retn
```
