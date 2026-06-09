# UdfUpdateVatHeader

- ea: `0x140039750`
- end: `0x140039932`
- name: `UdfUpdateVatHeader`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140017fa8`

## callees

- `0x14001bd80`
- `0x1400372a4`
- `0x140039750`

## import_xrefs

- `ntoskrnl!CcUnpinData` at `0x14003991a`
- `ntoskrnl!CcUnpinData` at `0x14003991a`
- `ntoskrnl!CcPinRead` at `0x1400397c0`
- `ntoskrnl!CcPinRead` at `0x1400398a9`
- `ntoskrnl!CcPinRead` at `0x1400397c0`
- `ntoskrnl!CcPinRead` at `0x1400398a9`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x14003990a`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x14003990a`

## pseudocode

```c
void __fastcall UdfUpdateVatHeader(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  char v3; // al
  char v4; // cl
  char *v5; // rax
  _WORD *v6; // rcx
  __int128 v7; // [rsp+30h] [rbp-10h] BYREF
  PVOID Buffer; // [rsp+50h] [rbp+10h] BYREF
  PVOID BcbVoid; // [rsp+58h] [rbp+18h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+60h] [rbp+20h] BYREF

  v1 = *(_QWORD *)(a1 + 16);
  FileOffset.QuadPart = 0;
  BcbVoid = 0;
  v7 = 0;
  Buffer = 0;
  if ( *(_WORD *)(v1 + 2138) < 0x200u )
  {
    FileOffset.QuadPart = *(_QWORD *)(*(_QWORD *)(v1 + 344) + 32LL) - 36LL;
    CcPinRead(*(PFILE_OBJECT *)(*(_QWORD *)(v1 + 344) + 504LL), &FileOffset, 0x24u, 1u, &BcbVoid, &Buffer);
    *(_BYTE *)Buffer = 0;
    memmove((char *)Buffer + 1, Src, (unsigned __int16)UdfVatTableIdentifier);
    v6 = Buffer;
    *((_WORD *)Buffer + 13) = 6;
    v6[12] = *(_WORD *)(v1 + 2138);
    *((_DWORD *)v6 + 7) = 0;
    *((_DWORD *)Buffer + 8) = *(_DWORD *)(*(_QWORD *)(v1 + 464) + 12LL);
  }
  else
  {
    CcPinRead(
      *(PFILE_OBJECT *)(*(_QWORD *)(v1 + 344) + 504LL),
      &FileOffset,
      *(_DWORD *)(v1 + 68),
      1u,
      &BcbVoid,
      &Buffer);
    *((_DWORD *)Buffer + 33) = *(_DWORD *)(*(_QWORD *)(v1 + 464) + 12LL);
    *((_DWORD *)Buffer + 35) = *(_DWORD *)(v1 + 1468);
    *((_DWORD *)Buffer + 34) = *(_DWORD *)(v1 + 1464);
    v2 = *(_QWORD *)(v1 + 8);
    WORD1(v7) = *(_WORD *)(v2 + 6);
    LOWORD(v7) = WORD1(v7);
    *((_QWORD *)&v7 + 1) = v2 + 32;
    v3 = UdfConvertUnicodeToCS0Dstring(v2, &v7, 0, (char *)Buffer + 4);
    v4 = 0;
    if ( v3 != 1 )
      v4 = v3;
    *((_BYTE *)Buffer + 131) = v4;
    v5 = (char *)Buffer;
    if ( *((_WORD *)Buffer + 1) >= 0x20u )
    {
      *(_OWORD *)((char *)Buffer + 152) = UdfMsRegId;
      *(_OWORD *)(v5 + 168) = xmmword_140025350;
    }
  }
  CcSetDirtyPinnedData(BcbVoid, 0);
  CcUnpinData(BcbVoid);
}

```

## disassembly

```asm
0x140039750  mov     [rsp-8+arg_18], rbx
0x140039755  push    rbp
0x140039756  mov     rbp, rsp
0x140039759  sub     rsp, 40h
0x14003975d  mov     rbx, [rcx+10h]
0x140039761  lea     rdx, [rbp+FileOffset]; FileOffset
0x140039765  mov     eax, 200h
0x14003976a  mov     qword ptr [rbp+FileOffset], 0
0x140039772  xorps   xmm0, xmm0
0x140039775  mov     [rbp+BcbVoid], 0
0x14003977d  movups  [rbp+var_10], xmm0
0x140039781  mov     r9d, 1; Flags
0x140039787  mov     [rbp+arg_0], 0
0x14003978f  cmp     ax, [rbx+85Ah]
0x140039796  ja      loc_140039870
0x14003979c  mov     rcx, [rbx+158h]
0x1400397a3  lea     rax, [rbp+arg_0]
0x1400397a7  mov     r8d, [rbx+44h]; Length
0x1400397ab  mov     [rsp+40h+Buffer], rax; Buffer
0x1400397b0  lea     rax, [rbp+BcbVoid]
0x1400397b4  mov     [rsp+40h+Bcb], rax; Bcb
0x1400397b9  mov     rcx, [rcx+1F8h]; FileObject
0x1400397c0  call    cs:__imp_CcPinRead
0x1400397c7  nop     dword ptr [rax+rax+00h]
0x1400397cc  mov     rax, [rbx+1D0h]
0x1400397d3  lea     rdx, [rbp+var_10]
0x1400397d7  xor     r8d, r8d
0x1400397da  mov     ecx, [rax+0Ch]
0x1400397dd  mov     rax, [rbp+arg_0]
0x1400397e1  mov     [rax+84h], ecx
0x1400397e7  mov     ecx, [rbx+5BCh]
0x1400397ed  mov     rax, [rbp+arg_0]
0x1400397f1  mov     [rax+8Ch], ecx
0x1400397f7  mov     rax, [rbp+arg_0]
0x1400397fb  mov     ecx, [rbx+5B8h]
0x140039801  mov     [rax+88h], ecx
0x140039807  mov     rcx, [rbx+8]
0x14003980b  mov     r9, [rbp+arg_0]
0x14003980f  add     r9, 4
0x140039813  movzx   eax, word ptr [rcx+6]
0x140039817  mov     word ptr [rbp+var_10+2], ax
0x14003981b  mov     word ptr [rbp+var_10], ax
0x14003981f  lea     rax, [rcx+20h]
0x140039823  mov     qword ptr [rbp+var_10+8], rax
0x140039827  call    UdfConvertUnicodeToCS0Dstring
0x14003982c  movzx   eax, al
0x14003982f  xor     ecx, ecx
0x140039831  cmp     al, 1
0x140039833  cmovnz  ecx, eax
0x140039836  mov     rax, [rbp+arg_0]
0x14003983a  mov     [rax+83h], cl
0x140039840  mov     rax, [rbp+arg_0]
0x140039844  cmp     word ptr [rax+2], 20h ; ' '
0x140039849  jb      loc_140039904
0x14003984f  movups  xmm0, cs:UdfMsRegId
0x140039856  movups  xmmword ptr [rax+98h], xmm0
0x14003985d  movups  xmm1, cs:xmmword_140025350
0x140039864  movups  xmmword ptr [rax+0A8h], xmm1
0x14003986b  jmp     loc_140039904
0x140039870  mov     rax, [rbx+158h]
0x140039877  mov     r8d, 24h ; '$'; Length
0x14003987d  mov     rcx, [rax+20h]
0x140039881  lea     rax, [rbp+arg_0]
0x140039885  sub     rcx, 24h ; '$'
0x140039889  mov     [rsp+40h+Buffer], rax; Buffer
0x14003988e  mov     qword ptr [rbp+FileOffset], rcx
0x140039892  lea     rax, [rbp+BcbVoid]
0x140039896  mov     rcx, [rbx+158h]
0x14003989d  mov     [rsp+40h+Bcb], rax; Bcb
0x1400398a2  mov     rcx, [rcx+1F8h]; FileObject
0x1400398a9  call    cs:__imp_CcPinRead
0x1400398b0  nop     dword ptr [rax+rax+00h]
0x1400398b5  mov     rax, [rbp+arg_0]
0x1400398b9  mov     byte ptr [rax], 0
0x1400398bc  mov     rcx, [rbp+arg_0]
0x1400398c0  movzx   r8d, cs:UdfVatTableIdentifier; Size
0x1400398c8  inc     rcx; void *
0x1400398cb  mov     rdx, cs:Src; Src
0x1400398d2  call    memmove
0x1400398d7  mov     rcx, [rbp+arg_0]
0x1400398db  mov     word ptr [rcx+1Ah], 6
0x1400398e1  movzx   eax, word ptr [rbx+85Ah]
0x1400398e8  mov     [rcx+18h], ax
0x1400398ec  mov     dword ptr [rcx+1Ch], 0
0x1400398f3  mov     rax, [rbx+1D0h]
0x1400398fa  mov     ecx, [rax+0Ch]
0x1400398fd  mov     rax, [rbp+arg_0]
0x140039901  mov     [rax+20h], ecx
0x140039904  mov     rcx, [rbp+BcbVoid]; BcbVoid
0x140039908  xor     edx, edx; Lsn
0x14003990a  call    cs:__imp_CcSetDirtyPinnedData
0x140039911  nop     dword ptr [rax+rax+00h]
0x140039916  mov     rcx, [rbp+BcbVoid]; Bcb
0x14003991a  call    cs:__imp_CcUnpinData
0x140039921  nop     dword ptr [rax+rax+00h]
0x140039926  mov     rbx, [rsp+40h+arg_18]
0x14003992b  add     rsp, 40h
0x14003992f  pop     rbp
0x140039930  retn
```
