# UdfCopyMoveMcbAllocation

- ea: `0x140030738`
- end: `0x14003080f`
- name: `UdfCopyMoveMcbAllocation`
- size: `215`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000feb4`
- `0x140051d74`

## callees

- `0x140030738`

## import_xrefs

- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x1400307a1`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x1400307a1`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x1400307f1`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x1400307f1`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x1400307c4`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x1400307c4`

## pseudocode

```c
BOOLEAN __fastcall UdfCopyMoveMcbAllocation(
        __int64 a1,
        LARGE_MCB *a2,
        LARGE_MCB *a3,
        LONGLONG a4,
        ULONG a5,
        _DWORD *a6)
{
  _DWORD *v6; // rbx
  BOOLEAN result; // al
  LONGLONG Vbn[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 SectorCountFromLbn; // [rsp+70h] [rbp+20h] BYREF
  __int64 Lbn; // [rsp+88h] [rbp+38h] BYREF

  v6 = a6;
  a5 = 0;
  *a6 = 0;
  Vbn[0] = a4;
  Lbn = 0;
  SectorCountFromLbn = 0;
  for ( result = FsRtlLookupLargeMcbEntry(a2, a4, &Lbn, &SectorCountFromLbn, 0, 0, &a5);
        result;
        result = FsRtlGetNextLargeMcbEntry(a2, a5, Vbn, &Lbn, &SectorCountFromLbn) )
  {
    if ( Lbn != -1 )
    {
      FsRtlAddLargeMcbEntry(a3, Vbn[0], Lbn, SectorCountFromLbn);
      *v6 += SectorCountFromLbn;
    }
    ++a5;
  }
  return result;
}

```

## disassembly

```asm
0x140030738  mov     r11, rsp
0x14003073b  mov     [r11+10h], rbx
0x14003073f  mov     [r11+8], rcx
0x140030743  push    rbp
0x140030744  push    rsi
0x140030745  push    rdi
0x140030746  mov     rbp, rsp
0x140030749  sub     rsp, 50h
0x14003074d  mov     rbx, [rbp+arg_28]
0x140030751  lea     rcx, [rbp+arg_20]
0x140030755  mov     rax, r9
0x140030758  mov     [r11-38h], rcx
0x14003075c  mov     rdi, rdx
0x14003075f  mov     qword ptr [r11-40h], 0
0x140030767  mov     rsi, r8
0x14003076a  mov     [rbp+arg_20], 0
0x140030771  lea     r9, [rbp+SectorCountFromLbn]; SectorCountFromLbn
0x140030775  mov     dword ptr [rbx], 0
0x14003077b  lea     r8, [rbp+Lbn]; Lbn
0x14003077f  mov     [rbp+Vbn], rax
0x140030783  mov     rdx, rax; Vbn
0x140030786  mov     [rbp+Lbn], 0
0x14003078e  mov     rcx, rdi; Mcb
0x140030791  mov     [rbp+SectorCountFromLbn], 0
0x140030799  mov     qword ptr [r11-48h], 0
0x1400307a1  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x1400307a8  nop     dword ptr [rax+rax+00h]
0x1400307ad  jmp     short loc_1400307FD
0x1400307af  mov     r8, [rbp+Lbn]; Lbn
0x1400307b3  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1400307b7  jz      short loc_1400307D5
0x1400307b9  mov     r9, [rbp+SectorCountFromLbn]; SectorCount
0x1400307bd  mov     rcx, rsi; Mcb
0x1400307c0  mov     rdx, [rbp+Vbn]; Vbn
0x1400307c4  call    cs:__imp_FsRtlAddLargeMcbEntry
0x1400307cb  nop     dword ptr [rax+rax+00h]
0x1400307d0  mov     eax, dword ptr [rbp+SectorCountFromLbn]
0x1400307d3  add     [rbx], eax
0x1400307d5  mov     edx, [rbp+arg_20]
0x1400307d8  lea     rax, [rbp+SectorCountFromLbn]
0x1400307dc  inc     edx; RunIndex
0x1400307de  mov     [rsp+50h+SectorCount], rax; SectorCount
0x1400307e3  lea     r9, [rbp+Lbn]; Lbn
0x1400307e7  mov     [rbp+arg_20], edx
0x1400307ea  lea     r8, [rbp+Vbn]; Vbn
0x1400307ee  mov     rcx, rdi; Mcb
0x1400307f1  call    cs:__imp_FsRtlGetNextLargeMcbEntry
0x1400307f8  nop     dword ptr [rax+rax+00h]
0x1400307fd  test    al, al
0x1400307ff  jnz     short loc_1400307AF
0x140030801  mov     rbx, [rsp+50h+arg_8]
0x140030806  add     rsp, 50h
0x14003080a  pop     rdi
0x14003080b  pop     rsi
0x14003080c  pop     rbp
0x14003080d  retn
```
