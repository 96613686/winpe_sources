# WanpCreateInterfaceContext

- ea: `0x14000ddd0`
- end: `0x14000df28`
- name: `WanpCreateInterfaceContext`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000dc5c`

## callees

- `0x14000ddd0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000ddf1`
- `ntoskrnl!ExAllocatePool2` at `0x14000ddf1`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000dee5`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000dee5`

## pseudocode

```c
__int64 __fastcall WanpCreateInterfaceContext(char a1, int a2, __int64 a3, int a4, __int64 *a5)
{
  __int64 Pool2; // rax
  __int64 v9; // rbx
  __int64 result; // rax
  char v11; // cl
  char v12; // cl
  int v13; // ecx
  int v14; // eax
  unsigned int v15; // ecx
  int v16; // eax
  NDIS_HANDLE v17; // rcx

  Pool2 = ExAllocatePool2(64, 552, 1768976983);
  v9 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  *(_BYTE *)(Pool2 + 20) = a1;
  *(_DWORD *)(Pool2 + 16) = 1953392983;
  *(_DWORD *)(Pool2 + 164) = a4;
  *(_WORD *)(Pool2 + 184) = 270;
  *(_BYTE *)(Pool2 + 186) = 0;
  v11 = byte_140009170;
  if ( !a1 )
    v11 = byte_1400093C0;
  *(_BYTE *)(Pool2 + 187) = v11;
  v12 = byte_140009171;
  if ( !a1 )
    v12 = byte_1400093C1;
  *(_DWORD *)(Pool2 + 192) = 3;
  *(_BYTE *)(Pool2 + 188) = v12;
  v13 = *(_DWORD *)(Pool2 + 212) | 0x303;
  *(_QWORD *)(Pool2 + 196) = 23;
  v14 = v13;
  *(_DWORD *)(v9 + 204) = 0;
  v15 = v13 & 0xFFFFFFCF;
  *(_DWORD *)(v9 + 32) = a2;
  v16 = v14 | 0x30;
  *(_QWORD *)(v9 + 96) = 0;
  *(_DWORD *)(v9 + 64) = 1;
  if ( !a1 )
    v15 = v16;
  *(_DWORD *)(v9 + 108) = 2;
  *(_DWORD *)(v9 + 144) = 2;
  *(_DWORD *)(v9 + 140) = 2;
  *(_DWORD *)(v9 + 212) = v15 & 0xFFFFFB33 | 0xC;
  *(_QWORD *)(v9 + 120) = 0;
  *(_QWORD *)(v9 + 128) = v9 + 120;
  KeInitializeSpinLock((PKSPIN_LOCK)(v9 + 56));
  *(_DWORD *)(v9 + 216) = 9;
  v17 = (NDIS_HANDLE)qword_1400099E8;
  if ( !a1 )
    v17 = NdisBindingHandle;
  *a5 = v9;
  result = 0;
  *(_QWORD *)(v9 + 224) = v17;
  return result;
}

```

## disassembly

```asm
0x14000ddd0  push    rbx
0x14000ddd2  push    rbp
0x14000ddd3  push    rsi
0x14000ddd4  push    rdi
0x14000ddd5  sub     rsp, 28h
0x14000ddd9  mov     ebp, edx
0x14000dddb  mov     dil, cl
0x14000ddde  mov     edx, 228h
0x14000dde3  mov     ecx, 40h ; '@'
0x14000dde8  mov     r8d, 69707257h
0x14000ddee  mov     esi, r9d
0x14000ddf1  call    cs:__imp_ExAllocatePool2
0x14000ddf8  nop     dword ptr [rax+rax+00h]
0x14000ddfd  mov     rbx, rax
0x14000de00  test    rax, rax
0x14000de03  jnz     short loc_14000DE0F
0x14000de05  mov     eax, 0C000009Ah
0x14000de0a  jmp     loc_14000DF1E
0x14000de0f  mov     [rax+14h], dil
0x14000de13  test    dil, dil
0x14000de16  mov     dword ptr [rax+10h], 746E6957h
0x14000de1d  mov     [rax+0A4h], esi
0x14000de23  mov     word ptr [rax+0B8h], 10Eh
0x14000de2c  mov     byte ptr [rax+0BAh], 0
0x14000de33  movzx   eax, cs:byte_1400093C0
0x14000de3a  movzx   ecx, cs:byte_140009170
0x14000de41  cmovz   ecx, eax
0x14000de44  mov     [rbx+0BBh], cl
0x14000de4a  movzx   eax, cs:byte_1400093C1
0x14000de51  movzx   ecx, cs:byte_140009171
0x14000de58  cmovz   ecx, eax
0x14000de5b  mov     dword ptr [rbx+0C0h], 3
0x14000de65  mov     [rbx+0BCh], cl
0x14000de6b  mov     ecx, [rbx+0D4h]
0x14000de71  or      ecx, 303h
0x14000de77  mov     qword ptr [rbx+0C4h], 17h
0x14000de82  mov     eax, ecx
0x14000de84  mov     dword ptr [rbx+0CCh], 0
0x14000de8e  and     ecx, 0FFFFFFCFh
0x14000de91  mov     [rbx+20h], ebp
0x14000de94  or      eax, 30h
0x14000de97  mov     qword ptr [rbx+60h], 0
0x14000de9f  test    dil, dil
0x14000dea2  mov     dword ptr [rbx+40h], 1
0x14000dea9  cmovz   ecx, eax
0x14000deac  mov     eax, 2
0x14000deb1  and     ecx, 0FFFFFB3Fh
0x14000deb7  mov     [rbx+6Ch], eax
0x14000deba  or      ecx, 0Ch
0x14000debd  mov     [rbx+90h], eax
0x14000dec3  mov     [rbx+8Ch], eax
0x14000dec9  lea     rax, [rbx+78h]
0x14000decd  mov     [rbx+0D4h], ecx
0x14000ded3  lea     rcx, [rbx+38h]; SpinLock
0x14000ded7  mov     qword ptr [rax], 0
0x14000dede  mov     [rbx+80h], rax
0x14000dee5  call    cs:__imp_KeInitializeSpinLock
0x14000deec  nop     dword ptr [rax+rax+00h]
0x14000def1  mov     rax, [rsp+48h+arg_20]
0x14000def6  test    dil, dil
0x14000def9  mov     dword ptr [rbx+0D8h], 9
0x14000df03  mov     rcx, cs:qword_1400099E8
0x14000df0a  cmovz   rcx, cs:NdisBindingHandle
0x14000df12  mov     [rax], rbx
0x14000df15  xor     eax, eax
0x14000df17  mov     [rbx+0E0h], rcx
0x14000df1e  add     rsp, 28h
0x14000df22  pop     rdi
0x14000df23  pop     rsi
0x14000df24  pop     rbp
0x14000df25  pop     rbx
0x14000df26  retn
```
