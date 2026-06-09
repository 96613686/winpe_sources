# VsmmMemPartIoctlOpen

- ea: `0x1400a5704`
- end: `0x1400a5932`
- name: `VsmmMemPartIoctlOpen`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400377bc`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140016c50`
- `0x140021650`
- `0x1400a5704`
- `0x1400fbd7c`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a5865`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a5865`
- `ntoskrnl!PsPartitionType` at `0x1400a584c`
- `ntoskrnl!NtClose` at `0x1400a5909`
- `ntoskrnl!NtClose` at `0x1400a5909`

## string_xrefs

- `0x1400a579a`: `VsmmMemPartIoctlOpen`
- `0x1400a5897`: `VsmmMemPartIoctlOpen`

## pseudocode

```c
__int64 __fastcall VsmmMemPartIoctlOpen(__int64 a1, ACCESS_MASK a2, HANDLE *a3)
{
  int v5; // esi
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // eax
  void *PartitionObject; // r10
  NTSTATUS v11; // ebx
  __int16 *v12; // rdx
  __int64 v13; // r8
  int *v14; // rax
  int v16; // [rsp+40h] [rbp-79h] BYREF
  int v17; // [rsp+44h] [rbp-75h] BYREF
  NTSTATUS v18; // [rsp+48h] [rbp-71h] BYREF
  int v19; // [rsp+4Ch] [rbp-6Dh] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-69h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v22[16]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v23[16]; // [rsp+90h] [rbp-29h] BYREF
  int *v24; // [rsp+A0h] [rbp-19h]
  __int64 v25; // [rsp+A8h] [rbp-11h]
  int *v26; // [rsp+B0h] [rbp-9h]
  __int64 v27; // [rsp+B8h] [rbp-1h]
  int *v28; // [rsp+C0h] [rbp+7h]
  __int64 v29; // [rsp+C8h] [rbp+Fh]
  int *v30; // [rsp+D0h] [rbp+17h]
  __int64 v31; // [rsp+D8h] [rbp+1Fh]

  Handle = 0;
  v5 = a1;
  v6 = VsmmMemReserveMemPartGet(a1);
  v8 = v6;
  if ( v6 && ((v9 = *(_DWORD *)(v6 + 32), (v9 & 0xFFFFFFFA) != 0) || v9 == 1) )
  {
    PartitionObject = (void *)VsmmMemPartGetPartitionObject(v8, v7);
    if ( PartitionObject )
    {
      v11 = ObOpenObjectByPointer(PartitionObject, 0, 0, a2, PsPartitionType, 1, &Handle);
      if ( v11 >= 0 )
      {
        v11 = 0;
        *a3 = Handle;
        return (unsigned int)v11;
      }
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v22, "VsmmMemPartIoctlOpen");
        tlgCreate1Sz_char(v23, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
        v19 = 447;
        v24 = &v19;
        v12 = (__int16 *)byte_14004C633;
        v18 = v11;
        v26 = &v18;
        v28 = &v17;
        v14 = &v16;
        v17 = v5;
        v16 = a2;
        goto LABEL_8;
      }
    }
    else
    {
      v11 = -1073741661;
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v22, "VsmmMemPartIoctlOpen");
        tlgCreate1Sz_char(v23, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
        v16 = 425;
        v24 = &v16;
        v12 = &word_14004C696;
        v17 = -1073741661;
        v26 = &v17;
        v28 = &v18;
        v19 = *(_DWORD *)(v13 + 32);
        v14 = &v19;
        v18 = v5;
LABEL_8:
        v30 = v14;
        v31 = 4;
        v29 = 4;
        v27 = 4;
        v25 = 4;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v12, 0, 0, 8, v21);
      }
    }
  }
  else
  {
    v11 = -1073741275;
  }
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400a5704  push    rbp
0x1400a5706  push    rbx
0x1400a5707  push    rsi
0x1400a5708  push    rdi
0x1400a5709  push    r14
0x1400a570b  lea     rbp, [rsp-37h]
0x1400a5710  sub     rsp, 0F0h
0x1400a5717  mov     rax, cs:__security_cookie
0x1400a571e  xor     rax, rsp
0x1400a5721  mov     [rbp+57h+var_30], rax
0x1400a5725  mov     rdi, r8
0x1400a5728  mov     [rbp+57h+var_C0], 0
0x1400a5730  mov     r14d, edx
0x1400a5733  mov     esi, ecx
0x1400a5735  call    VsmmMemReserveMemPartGet
0x1400a573a  mov     r8, rax
0x1400a573d  test    rax, rax
0x1400a5740  jz      loc_1400A58FB
0x1400a5746  mov     eax, [rax+20h]
0x1400a5749  test    eax, 0FFFFFFFAh
0x1400a574e  jnz     short loc_1400A5759
0x1400a5750  cmp     eax, 1
0x1400a5753  jnz     loc_1400A58FB
0x1400a5759  mov     rcx, r8
0x1400a575c  call    VsmmMemPartGetPartitionObject
0x1400a5761  mov     r10, rax
0x1400a5764  test    rax, rax
0x1400a5767  jnz     loc_1400A583D
0x1400a576d  mov     eax, cs:dword_140064110
0x1400a5773  mov     ebx, 0C00000A3h
0x1400a5778  cmp     eax, 2
0x1400a577b  jbe     loc_1400A5900
0x1400a5781  mov     edx, 100h
0x1400a5786  lea     rcx, dword_140064110
0x1400a578d  call    _tlgKeywordOn
0x1400a5792  test    al, al
0x1400a5794  jz      loc_1400A5900
0x1400a579a  lea     rdx, aVsmmmempartioc_0; "VsmmMemPartIoctlOpen"
0x1400a57a1  lea     rcx, [rbp+57h+var_90]
0x1400a57a5  call    _tlgCreate1Sz_char
0x1400a57aa  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a57b1  lea     rcx, [rbp+57h+var_80]
0x1400a57b5  call    _tlgCreate1Sz_char
0x1400a57ba  lea     rax, [rbp+57h+var_D0]
0x1400a57be  mov     [rbp+57h+var_D0], 1A9h
0x1400a57c5  mov     [rbp+57h+var_70], rax
0x1400a57c9  lea     rdx, word_14004C696
0x1400a57d0  lea     rax, [rbp+57h+var_CC]
0x1400a57d4  mov     [rbp+57h+var_CC], ebx
0x1400a57d7  mov     [rbp+57h+var_60], rax
0x1400a57db  lea     rax, [rbp+57h+var_C8]
0x1400a57df  mov     [rbp+57h+var_50], rax
0x1400a57e3  mov     eax, [r8+20h]
0x1400a57e7  mov     [rbp+57h+var_C4], eax
0x1400a57ea  lea     rax, [rbp+57h+var_C4]
0x1400a57ee  mov     [rbp+57h+var_C8], esi
0x1400a57f1  mov     [rbp+57h+var_40], rax
0x1400a57f5  lea     rcx, dword_140064110
0x1400a57fc  lea     rax, [rbp+57h+var_B0]
0x1400a5800  mov     [rbp+57h+var_38], 4
0x1400a5808  mov     qword ptr [rsp+110h+AccessMode], rax
0x1400a580d  xor     r9d, r9d
0x1400a5810  xor     r8d, r8d
0x1400a5813  mov     dword ptr [rsp+110h+ObjectType], 8
0x1400a581b  mov     [rbp+57h+var_48], 4
0x1400a5823  mov     [rbp+57h+var_58], 4
0x1400a582b  mov     [rbp+57h+var_68], 4
0x1400a5833  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400a5838  jmp     loc_1400A5900
0x1400a583d  lea     rax, [rbp+57h+var_C0]
0x1400a5841  mov     r9d, r14d; DesiredAccess
0x1400a5844  mov     [rsp+110h+Handle], rax; Handle
0x1400a5849  xor     r8d, r8d; PassedAccessState
0x1400a584c  mov     rax, cs:__imp_PsPartitionType
0x1400a5853  xor     edx, edx; HandleAttributes
0x1400a5855  mov     [rsp+110h+AccessMode], 1; AccessMode
0x1400a585a  mov     rcx, [rax]
0x1400a585d  mov     [rsp+110h+ObjectType], rcx; ObjectType
0x1400a5862  mov     rcx, r10; Object
0x1400a5865  call    cs:__imp_ObOpenObjectByPointer
0x1400a586c  nop     dword ptr [rax+rax+00h]
0x1400a5871  mov     ebx, eax
0x1400a5873  test    eax, eax
0x1400a5875  jns     short loc_1400A58F0
0x1400a5877  mov     ecx, cs:dword_140064110
0x1400a587d  cmp     ecx, 2
0x1400a5880  jbe     short loc_1400A5900
0x1400a5882  mov     edx, 100h
0x1400a5887  lea     rcx, dword_140064110
0x1400a588e  call    _tlgKeywordOn
0x1400a5893  test    al, al
0x1400a5895  jz      short loc_1400A5900
0x1400a5897  lea     rdx, aVsmmmempartioc_0; "VsmmMemPartIoctlOpen"
0x1400a589e  lea     rcx, [rbp+57h+var_90]
0x1400a58a2  call    _tlgCreate1Sz_char
0x1400a58a7  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a58ae  lea     rcx, [rbp+57h+var_80]
0x1400a58b2  call    _tlgCreate1Sz_char
0x1400a58b7  lea     rax, [rbp+57h+var_C4]
0x1400a58bb  mov     [rbp+57h+var_C4], 1BFh
0x1400a58c2  mov     [rbp+57h+var_70], rax
0x1400a58c6  lea     rdx, byte_14004C633
0x1400a58cd  lea     rax, [rbp+57h+var_C8]
0x1400a58d1  mov     [rbp+57h+var_C8], ebx
0x1400a58d4  mov     [rbp+57h+var_60], rax
0x1400a58d8  lea     rax, [rbp+57h+var_CC]
0x1400a58dc  mov     [rbp+57h+var_50], rax
0x1400a58e0  lea     rax, [rbp+57h+var_D0]
0x1400a58e4  mov     [rbp+57h+var_CC], esi
0x1400a58e7  mov     [rbp+57h+var_D0], r14d
0x1400a58eb  jmp     loc_1400A57F1
0x1400a58f0  mov     rax, [rbp+57h+var_C0]
0x1400a58f4  xor     ebx, ebx
0x1400a58f6  mov     [rdi], rax
0x1400a58f9  jmp     short loc_1400A5915
0x1400a58fb  mov     ebx, 0C0000225h
0x1400a5900  mov     rcx, [rbp+57h+var_C0]; Handle
0x1400a5904  test    rcx, rcx
0x1400a5907  jz      short loc_1400A5915
0x1400a5909  call    cs:__imp_NtClose
0x1400a5910  nop     dword ptr [rax+rax+00h]
0x1400a5915  mov     eax, ebx
0x1400a5917  mov     rcx, [rbp+57h+var_30]
0x1400a591b  xor     rcx, rsp; StackCookie
0x1400a591e  call    __security_check_cookie
0x1400a5923  add     rsp, 0F0h
0x1400a592a  pop     r14
0x1400a592c  pop     rdi
0x1400a592d  pop     rsi
0x1400a592e  pop     rbx
0x1400a592f  pop     rbp
0x1400a5930  retn
```
