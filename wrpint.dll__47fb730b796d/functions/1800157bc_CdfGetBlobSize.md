# CdfGetBlobSize

- ea: `0x1800157bc`
- end: `0x1800157ee`
- name: `CdfGetBlobSize`
- size: `50`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800152e4`
- `0x1800157f4`
- `0x180015994`
- `0x180015d44`
- `0x180016178`

## callees

- `0x180015280`
- `0x1800157bc`

## pseudocode

```c
__int64 __fastcall CdfGetBlobSize(__int64 a1, unsigned int a2, _QWORD *a3)
{
  *a3 = 0;
  if ( a2 >= *(_DWORD *)(*(_QWORD *)(a1 + 16) + 20LL) )
    return CdfpReportErrorInner(0xC000000D);
  *a3 = *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8LL * a2) & 0xFFFFFF;
  return 0;
}

```

## disassembly

```asm
0x1800157bc  mov     qword ptr [r8], 0
0x1800157c3  mov     r9, rcx
0x1800157c6  mov     rax, [rcx+10h]
0x1800157ca  cmp     edx, [rax+14h]
0x1800157cd  jb      short loc_1800157D9
0x1800157cf  mov     ecx, 0C000000Dh; int
0x1800157d4  jmp     ?CdfpReportErrorInner@@YAJJH@Z; CdfpReportErrorInner(long,int)
0x1800157d9  mov     rax, [r9+18h]
0x1800157dd  mov     ecx, edx
0x1800157df  mov     edx, [rax+rcx*8]
0x1800157e2  and     edx, 0FFFFFFh
0x1800157e8  mov     [r8], rdx
0x1800157eb  xor     eax, eax
0x1800157ed  retn
```
