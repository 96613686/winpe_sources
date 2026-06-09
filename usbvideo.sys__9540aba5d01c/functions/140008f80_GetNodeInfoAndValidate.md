# GetNodeInfoAndValidate

- ea: `0x140008f80`
- end: `0x1400091bb`
- name: `GetNodeInfoAndValidate`
- size: `571`
- prototype: ``
- caller_count: `68`
- callee_count: `2`
- tags: ``

## callers

- `0x140006640`
- `0x1400068c0`
- `0x1400069d0`
- `0x140007570`
- `0x1400079a0`
- `0x140007aa0`
- `0x140007bb0`
- `0x140008500`
- `0x14000a130`
- `0x14000a370`
- `0x140012b70`
- `0x140013280`
- `0x140014080`
- `0x140014370`
- `0x140019570`
- `0x140019690`
- `0x140019850`
- `0x140019a90`
- `0x140025f90`
- `0x140026090`
- `0x140026170`
- `0x140026270`
- `0x140026380`
- `0x140026470`
- `0x140026560`
- `0x140026640`
- `0x140026720`
- `0x140026820`
- `0x140026980`
- `0x140026c30`
- `0x140026d90`
- `0x140026e90`
- `0x140026fa0`
- `0x1400270a0`
- `0x1400271c0`
- `0x1400272f0`
- `0x140027410`
- `0x1400276e0`
- `0x140027970`
- `0x140027e00`
- `0x1400291e0`
- `0x1400294e0`
- `0x140029590`
- `0x140029750`
- `0x1400299d0`
- `0x140029c00`
- `0x140029dd0`
- `0x140029fb0`
- `0x14002a0a0`
- `0x14002a190`

## callees

- `0x140008f80`
- `0x140040e40`

## import_xrefs

- `ks!KsGetFilterFromIrp` at `0x140008f9a`
- `ks!KsGetFilterFromIrp` at `0x140008f9a`

## pseudocode

```c
__int64 __fastcall GetNodeInfoAndValidate(
        IRP *a1,
        _DWORD *a2,
        int *a3,
        unsigned __int16 a4,
        unsigned __int8 a5,
        _BYTE *a6,
        _BYTE *a7,
        _QWORD *a8,
        _QWORD *a9,
        _QWORD *a10)
{
  __int64 v10; // r15
  PKSFILTER FilterFromIrp; // rax
  int v15; // r8d
  _QWORD *Context; // r14
  int v17; // ecx
  int *v18; // r11
  char *v19; // rbx
  unsigned int v20; // eax
  __int64 v21; // rdi
  __int64 v22; // rcx
  size_t Information; // r8
  int v25; // edi
  __int64 v26; // rax
  _DWORD *v27; // rcx
  int v28; // r10d
  BOOL v29; // r15d
  int v30; // r11d
  int v31; // ecx

  v10 = a4;
  FilterFromIrp = KsGetFilterFromIrp(a1);
  if ( !FilterFromIrp )
    return 3221225473LL;
  v15 = a2[5];
  Context = FilterFromIrp->Context;
  if ( (v15 & 0x10000000) != 0 )
  {
    v17 = a2[6];
    v18 = a3 + 8;
    if ( v17 != -1 )
      goto LABEL_4;
  }
  else
  {
    v18 = a3 + 6;
  }
  v17 = *((_DWORD *)Context + a5 + 4);
LABEL_4:
  v19 = (char *)FilterFromIrp->Descriptor->NodeDescriptors + FilterFromIrp->Descriptor->NodeDescriptorSize * v17;
  v20 = a2[4];
  if ( a5 == 6 )
  {
    if ( v20 <= 6 && v20 != 4 )
      goto LABEL_15;
    if ( (unsigned int)v10 <= 0x10 )
    {
      v31 = 69760;
      if ( _bittest(&v31, v10) )
      {
        v25 = -*v18;
        if ( *v18 > 0 )
          v25 = *v18;
LABEL_16:
        v26 = *(_QWORD *)&v19[8 * v10 + 56];
        if ( v26 )
          v27 = *(_DWORD **)(*(_QWORD *)(v26 + 32) + 16LL);
        else
          v27 = 0;
        v28 = 1;
        v29 = (*(_DWORD *)&v19[4 * v10 + 312] & 1) == 0 || (v18[1] & 1) == 0;
        if ( v27 && (v27[2] > v25 || v27[3] < v25) )
        {
          v30 = 1;
        }
        else
        {
          v30 = 0;
          if ( !v27 )
            goto LABEL_26;
        }
        if ( *v27 && (unsigned int)(v25 - v27[2]) % *v27 )
        {
LABEL_27:
          if ( (v15 & 2) != 0 && v29 && (v30 || v28) )
            return 3221225485LL;
          goto LABEL_6;
        }
LABEL_26:
        v28 = 0;
        goto LABEL_27;
      }
    }
  }
  else if ( a5 == 5 && v20 <= 0xB && (unsigned __int16)(v10 - 17) > 1u )
  {
LABEL_15:
    v25 = *v18;
    goto LABEL_16;
  }
LABEL_6:
  v21 = *((_QWORD *)v19 + 4);
  if ( (v15 & 1) != 0 )
  {
    Information = a1->IoStatus.Information;
    if ( Information <= a1->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length )
      memset(a3, 0, Information);
  }
  if ( a10 )
    *a10 = v19 + 312;
  *a6 = *(_BYTE *)(v21 + 3);
  *a7 = v19[40];
  v22 = *Context;
  *a8 = v19;
  *a9 = v22;
  return 0;
}

```

## disassembly

```asm
0x140008f80  mov     [rsp+arg_18], rbp
0x140008f85  push    rsi
0x140008f86  push    rdi
0x140008f87  push    r15
0x140008f89  sub     rsp, 20h
0x140008f8d  movzx   r15d, r9w
0x140008f91  mov     rbp, r8
0x140008f94  mov     rdi, rdx
0x140008f97  mov     rsi, rcx
0x140008f9a  call    cs:__imp_KsGetFilterFromIrp
0x140008fa1  nop     dword ptr [rax+rax+00h]
0x140008fa6  test    rax, rax
0x140008fa9  jz      loc_140009150
0x140008faf  mov     r8d, [rdi+14h]
0x140008fb3  movzx   r9d, [rsp+38h+arg_20]
0x140008fb9  mov     [rsp+38h+arg_0], rbx
0x140008fbe  mov     [rsp+38h+arg_10], r14
0x140008fc3  mov     r14, [rax+10h]
0x140008fc7  bt      r8d, 1Ch
0x140008fcc  jnb     loc_140009142
0x140008fd2  mov     ecx, [rdi+18h]
0x140008fd5  lea     r11, [rbp+20h]
0x140008fd9  cmp     ecx, 0FFFFFFFFh
0x140008fdc  jz      loc_140009146
0x140008fe2  mov     rax, [rax]
0x140008fe5  imul    ecx, [rax+44h]
0x140008fe9  mov     ebx, ecx
0x140008feb  add     rbx, [rax+48h]
0x140008fef  mov     eax, [rdi+10h]
0x140008ff2  cmp     r9b, 6
0x140008ff6  jz      loc_140009170
0x140008ffc  cmp     r9b, 5
0x140009000  jz      loc_14000908D
0x140009006  mov     rdi, [rbx+20h]
0x14000900a  test    r8b, 1
0x14000900e  jnz     short loc_14000906E
0x140009010  mov     rcx, [rsp+38h+arg_48]
0x140009018  test    rcx, rcx
0x14000901b  jz      short loc_140009027
0x14000901d  lea     rax, [rbx+138h]
0x140009024  mov     [rcx], rax
0x140009027  movzx   ecx, byte ptr [rdi+3]
0x14000902b  mov     rax, [rsp+38h+arg_28]
0x140009030  mov     [rax], cl
0x140009032  mov     rax, [rsp+38h+arg_30]
0x140009037  movzx   ecx, byte ptr [rbx+28h]
0x14000903b  mov     [rax], cl
0x14000903d  mov     rax, [rsp+38h+arg_38]
0x140009042  mov     rcx, [r14]
0x140009045  mov     [rax], rbx
0x140009048  mov     rax, [rsp+38h+arg_40]
0x140009050  mov     [rax], rcx
0x140009053  xor     eax, eax
0x140009055  mov     rbx, [rsp+38h+arg_0]
0x14000905a  mov     r14, [rsp+38h+arg_10]
0x14000905f  mov     rbp, [rsp+38h+arg_18]
0x140009064  add     rsp, 20h
0x140009068  pop     r15
0x14000906a  pop     rdi
0x14000906b  pop     rsi
0x14000906c  retn
0x14000906e  mov     rax, [rsi+0B8h]
0x140009075  mov     r8, [rsi+38h]; Size
0x140009079  mov     ecx, [rax+8]
0x14000907c  cmp     r8, rcx
0x14000907f  ja      short loc_140009010
0x140009081  xor     edx, edx; Val
0x140009083  mov     rcx, rbp; void *
0x140009086  call    memset
0x14000908b  jmp     short loc_140009010
0x14000908d  cmp     eax, 0Bh
0x140009090  ja      loc_140009006
0x140009096  lea     eax, [r15-11h]
0x14000909a  cmp     ax, 1
0x14000909e  jbe     loc_140009006
0x1400090a4  mov     edi, [r11]
0x1400090a7  mov     rax, [rbx+r15*8+38h]
0x1400090ac  test    rax, rax
0x1400090af  jz      loc_140009169
0x1400090b5  mov     rax, [rax+20h]
0x1400090b9  mov     rcx, [rax+10h]
0x1400090bd  mov     eax, [rbx+r15*4+138h]
0x1400090c5  mov     r9d, r8d
0x1400090c8  and     r9d, 2
0x1400090cc  mov     r10d, 1
0x1400090d2  test    r10b, al
0x1400090d5  jnz     loc_1400091A6
0x1400090db  mov     r15d, r10d
0x1400090de  mov     [rsp+38h+arg_8], r12
0x1400090e3  test    rcx, rcx
0x1400090e6  jz      short loc_1400090F2
0x1400090e8  cmp     [rcx+8], edi
0x1400090eb  jg      short loc_140009164
0x1400090ed  cmp     [rcx+0Ch], edi
0x1400090f0  jl      short loc_140009164
0x1400090f2  xor     r11d, r11d
0x1400090f5  test    rcx, rcx
0x1400090f8  jz      short loc_140009110
0x1400090fa  mov     r12d, [rcx]
0x1400090fd  test    r12d, r12d
0x140009100  jz      short loc_140009110
0x140009102  sub     edi, [rcx+8]
0x140009105  xor     edx, edx
0x140009107  mov     eax, edi
0x140009109  div     r12d
0x14000910c  test    edx, edx
0x14000910e  jnz     short loc_140009113
0x140009110  xor     r10d, r10d
0x140009113  mov     r12, [rsp+38h+arg_8]
0x140009118  test    r9d, r9d
0x14000911b  jz      loc_140009006
0x140009121  test    r15d, r15d
0x140009124  jz      loc_140009006
0x14000912a  test    r11d, r11d
0x14000912d  jnz     short loc_140009138
0x14000912f  test    r10d, r10d
0x140009132  jz      loc_140009006
0x140009138  mov     eax, 0C000000Dh
0x14000913d  jmp     loc_140009055
0x140009142  lea     r11, [rbp+18h]
0x140009146  mov     ecx, [r14+r9*4+10h]
0x14000914b  jmp     loc_140008FE2
0x140009150  mov     rbp, [rsp+38h+arg_18]
0x140009155  mov     eax, 0C0000001h
0x14000915a  add     rsp, 20h
0x14000915e  pop     r15
0x140009160  pop     rdi
0x140009161  pop     rsi
0x140009162  retn
0x140009164  mov     r11d, r10d
0x140009167  jmp     short loc_1400090FA
0x140009169  xor     ecx, ecx
0x14000916b  jmp     loc_1400090BD
0x140009170  cmp     eax, 6
0x140009173  ja      short loc_14000917E
0x140009175  cmp     eax, 4
0x140009178  jnz     loc_1400090A4
0x14000917e  cmp     r15d, 10h
0x140009182  ja      loc_140009006
0x140009188  mov     ecx, 11080h
0x14000918d  bt      ecx, r15d
0x140009191  jnb     loc_140009006
0x140009197  mov     eax, [r11]
0x14000919a  mov     edi, eax
0x14000919c  neg     edi
0x14000919e  cmovs   edi, eax
0x1400091a1  jmp     loc_1400090A7
0x1400091a6  mov     eax, [r11+4]
0x1400091aa  test    r10b, al
0x1400091ad  jz      loc_1400090DB
0x1400091b3  xor     r15d, r15d
0x1400091b6  jmp     loc_1400090DE
```
