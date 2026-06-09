# VsmmMemPartSetupPhase0

- ea: `0x1400a6268`
- end: `0x1400a64b8`
- name: `VsmmMemPartSetupPhase0`
- size: `592`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1400beccc`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x1400a5938`
- `0x1400a6268`
- `0x1400a6f44`
- `0x1400bdfc8`

## import_xrefs

- `ntoskrnl!ZwOpenPartition` at `0x1400a6311`
- `ntoskrnl!ZwOpenPartition` at `0x1400a6311`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400a63bc`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400a63bc`

## pseudocode

```c
__int64 __fastcall VsmmMemPartSetupPhase0(__int64 a1, const UNICODE_STRING *a2)
{
  char UseNonMirroredPartitionForVsmmp; // al
  char v5; // cl
  int v6; // ebx
  unsigned __int8 *v7; // rdx
  int *v8; // rax
  int v10; // [rsp+30h] [rbp-89h] BYREF
  int v11; // [rsp+34h] [rbp-85h] BYREF
  int v12; // [rsp+38h] [rbp-81h] BYREF
  _QWORD v13[2]; // [rsp+40h] [rbp-79h] BYREF
  _BYTE v14[48]; // [rsp+50h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v16[16]; // [rsp+A0h] [rbp-19h] BYREF
  _BYTE v17[16]; // [rsp+B0h] [rbp-9h] BYREF
  int *v18; // [rsp+C0h] [rbp+7h]
  __int64 v19; // [rsp+C8h] [rbp+Fh]
  int *v20; // [rsp+D0h] [rbp+17h]
  __int64 v21; // [rsp+D8h] [rbp+1Fh]
  int *v22; // [rsp+E0h] [rbp+27h]
  __int64 v23; // [rsp+E8h] [rbp+2Fh]

  v13[0] = 4325440;
  v13[1] = L"\\KernelObjects\\NonMirroredMemory";
  memset(v14, 0, 44);
  if ( *(_DWORD *)(a1 + 28) )
    UseNonMirroredPartitionForVsmmp = VsmmMemReserveQueryUseNonMirroredPartitionForVsmmp();
  else
    UseNonMirroredPartitionForVsmmp = 1;
  v5 = 0;
  if ( (*(_DWORD *)(a1 + 160) & 0x40) == 0 )
    v5 = UseNonMirroredPartitionForVsmmp;
  if ( v5 )
  {
    *(_DWORD *)v14 = 48;
    *(_QWORD *)&v14[16] = v13;
    *(_QWORD *)&v14[8] = 0;
    *(_DWORD *)&v14[24] = 512;
    *(_OWORD *)&v14[32] = 0;
    ZwOpenPartition(a1 + 96, 2031619, v14);
  }
  if ( !*(_QWORD *)(a1 + 96) )
  {
    v6 = VsmmMemPartOpenSystemMemoryPartition(a1 + 96);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_18;
      tlgCreate1Sz_char(v16, "VsmmMemPartSetupPhase0");
      tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
      v10 = 805;
      v18 = &v10;
      v7 = (unsigned __int8 *)&dword_14004C4D4;
      v20 = &v11;
      v12 = *(_DWORD *)(a1 + 28);
      v8 = &v12;
      goto LABEL_17;
    }
  }
  v6 = RtlDuplicateUnicodeString(0, a2, (PUNICODE_STRING)(a1 + 224));
  if ( v6 >= 0 )
    return 0;
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v16, "VsmmMemPartSetupPhase0");
    tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
    v12 = 819;
    v18 = &v12;
    v7 = (unsigned __int8 *)word_14004C52A;
    v20 = &v11;
    v10 = *(_DWORD *)(a1 + 28);
    v8 = &v10;
LABEL_17:
    v22 = v8;
    v19 = 4;
    v11 = v6;
    v21 = 4;
    v23 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140064110, v7, 0, 0, 7u, &v15);
  }
LABEL_18:
  VsmmMemPartTeardown(a1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400a6268  mov     [rsp-8+arg_10], rbx
0x1400a626d  push    rbp
0x1400a626e  push    rsi
0x1400a626f  push    rdi
0x1400a6270  lea     rbp, [rsp-47h]
0x1400a6275  sub     rsp, 100h
0x1400a627c  mov     rax, cs:__security_cookie
0x1400a6283  xor     rax, rsp
0x1400a6286  mov     [rbp+57h+var_20], rax
0x1400a628a  xorps   xmm0, xmm0
0x1400a628d  mov     [rbp+57h+var_D0], 420040h
0x1400a6295  lea     rax, aKernelobjectsN; "\\KernelObjects\\NonMirroredMemory"
0x1400a629c  mov     rsi, rdx
0x1400a629f  mov     [rbp+57h+var_C8], rax
0x1400a62a3  mov     rdi, rcx
0x1400a62a6  xor     eax, eax
0x1400a62a8  mov     ebx, 40h ; '@'
0x1400a62ad  movups  [rbp+57h+var_B0], xmm0
0x1400a62b1  movups  [rbp+57h+var_C0], xmm0
0x1400a62b5  movups  [rbp+57h+var_B0+0Ch], xmm0
0x1400a62b9  cmp     [rcx+1Ch], eax
0x1400a62bc  jnz     short loc_1400A62C2
0x1400a62be  mov     al, 1
0x1400a62c0  jmp     short loc_1400A62C7
0x1400a62c2  call    VsmmMemReserveQueryUseNonMirroredPartitionForVsmmp
0x1400a62c7  mov     ecx, [rdi+0A0h]
0x1400a62cd  test    bl, cl
0x1400a62cf  mov     ecx, 0
0x1400a62d4  movzx   eax, al
0x1400a62d7  cmovz   ecx, eax
0x1400a62da  test    cl, cl
0x1400a62dc  jz      short loc_1400A631D
0x1400a62de  lea     rax, [rbp+57h+var_D0]
0x1400a62e2  mov     dword ptr [rbp+57h+var_C0], 30h ; '0'
0x1400a62e9  xorps   xmm0, xmm0
0x1400a62ec  mov     qword ptr [rbp+57h+var_B0], rax
0x1400a62f0  lea     rcx, [rdi+60h]
0x1400a62f4  mov     qword ptr [rbp+57h+var_C0+8], 0
0x1400a62fc  lea     r8, [rbp+57h+var_C0]
0x1400a6300  mov     dword ptr [rbp+57h+var_B0+8], 200h
0x1400a6307  mov     edx, 1F0003h
0x1400a630c  movdqu  [rbp+57h+var_A0], xmm0
0x1400a6311  call    cs:__imp_ZwOpenPartition
0x1400a6318  nop     dword ptr [rax+rax+00h]
0x1400a631d  lea     rcx, [rdi+60h]
0x1400a6321  cmp     qword ptr [rcx], 0
0x1400a6325  jnz     loc_1400A63B0
0x1400a632b  call    VsmmMemPartOpenSystemMemoryPartition
0x1400a6330  mov     ebx, eax
0x1400a6332  test    eax, eax
0x1400a6334  jns     short loc_1400A63B0
0x1400a6336  mov     ecx, cs:dword_140064110
0x1400a633c  cmp     ecx, 2
0x1400a633f  jbe     loc_1400A648A
0x1400a6345  mov     edx, 100h
0x1400a634a  lea     rcx, dword_140064110
0x1400a6351  call    _tlgKeywordOn
0x1400a6356  test    al, al
0x1400a6358  jz      loc_1400A648A
0x1400a635e  lea     rdx, aVsmmmempartset_3; "VsmmMemPartSetupPhase0"
0x1400a6365  lea     rcx, [rbp+57h+var_70]
0x1400a6369  call    _tlgCreate1Sz_char
0x1400a636e  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a6375  lea     rcx, [rbp+57h+var_60]
0x1400a6379  call    _tlgCreate1Sz_char
0x1400a637e  lea     rax, [rsp+110h+var_E0]
0x1400a6383  mov     [rsp+110h+var_E0], 325h
0x1400a638b  mov     [rbp+57h+var_50], rax
0x1400a638f  lea     rdx, dword_14004C4D4
0x1400a6396  lea     rax, [rsp+110h+var_DC]
0x1400a639b  mov     [rbp+57h+var_40], rax
0x1400a639f  mov     eax, [rdi+1Ch]
0x1400a63a2  mov     [rsp+110h+var_D8], eax
0x1400a63a6  lea     rax, [rsp+110h+var_D8]
0x1400a63ab  jmp     loc_1400A6447
0x1400a63b0  lea     r8, [rdi+0E0h]; StringOut
0x1400a63b7  mov     rdx, rsi; StringIn
0x1400a63ba  xor     ecx, ecx; Flags
0x1400a63bc  call    cs:__imp_RtlDuplicateUnicodeString
0x1400a63c3  nop     dword ptr [rax+rax+00h]
0x1400a63c8  mov     ebx, eax
0x1400a63ca  test    eax, eax
0x1400a63cc  jns     loc_1400A6494
0x1400a63d2  mov     eax, cs:dword_140064110
0x1400a63d8  cmp     eax, 2
0x1400a63db  jbe     loc_1400A648A
0x1400a63e1  mov     edx, 100h
0x1400a63e6  lea     rcx, dword_140064110
0x1400a63ed  call    _tlgKeywordOn
0x1400a63f2  test    al, al
0x1400a63f4  jz      loc_1400A648A
0x1400a63fa  lea     rdx, aVsmmmempartset_3; "VsmmMemPartSetupPhase0"
0x1400a6401  lea     rcx, [rbp+57h+var_70]
0x1400a6405  call    _tlgCreate1Sz_char
0x1400a640a  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a6411  lea     rcx, [rbp+57h+var_60]
0x1400a6415  call    _tlgCreate1Sz_char
0x1400a641a  lea     rax, [rsp+110h+var_D8]
0x1400a641f  mov     [rsp+110h+var_D8], 333h
0x1400a6427  mov     [rbp+57h+var_50], rax
0x1400a642b  lea     rdx, word_14004C52A
0x1400a6432  lea     rax, [rsp+110h+var_DC]
0x1400a6437  mov     [rbp+57h+var_40], rax
0x1400a643b  mov     eax, [rdi+1Ch]
0x1400a643e  mov     [rsp+110h+var_E0], eax
0x1400a6442  lea     rax, [rsp+110h+var_E0]
0x1400a6447  mov     [rbp+57h+var_30], rax
0x1400a644b  lea     rcx, dword_140064110
0x1400a6452  lea     rax, [rbp+57h+var_90]
0x1400a6456  mov     [rbp+57h+var_48], 4
0x1400a645e  mov     [rsp+110h+var_E8], rax
0x1400a6463  xor     r9d, r9d
0x1400a6466  xor     r8d, r8d
0x1400a6469  mov     [rsp+110h+var_F0], 7
0x1400a6471  mov     [rsp+110h+var_DC], ebx
0x1400a6475  mov     [rbp+57h+var_38], 4
0x1400a647d  mov     [rbp+57h+var_28], 4
0x1400a6485  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400a648a  mov     rcx, rdi
0x1400a648d  call    VsmmMemPartTeardown
0x1400a6492  jmp     short loc_1400A6496
0x1400a6494  xor     ebx, ebx
0x1400a6496  mov     eax, ebx
0x1400a6498  mov     rcx, [rbp+57h+var_20]
0x1400a649c  xor     rcx, rsp; StackCookie
0x1400a649f  call    __security_check_cookie
0x1400a64a4  mov     rbx, [rsp+110h+arg_10]
0x1400a64ac  add     rsp, 100h
0x1400a64b3  pop     rdi
0x1400a64b4  pop     rsi
0x1400a64b5  pop     rbp
0x1400a64b6  retn
```
