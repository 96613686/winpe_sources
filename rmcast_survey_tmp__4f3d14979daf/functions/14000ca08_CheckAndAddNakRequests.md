# CheckAndAddNakRequests

- ea: `0x14000ca08`
- end: `0x14000cdf5`
- name: `CheckAndAddNakRequests`
- size: `1005`
- prototype: `__int64 __fastcall(__int64, int *, _QWORD *, int, char)`
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14000e03c`
- `0x14000f2d8`
- `0x140010ae4`
- `0x140012efc`
- `0x140013d90`

## callees

- `0x1400050ac`
- `0x140005168`
- `0x140008388`
- `0x140008944`
- `0x140009f50`
- `0x14000ca08`
- `0x14001c8f4`
- `0x14001d300`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000cba0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000cba0`

## pseudocode

```c
__int64 __fastcall CheckAndAddNakRequests(__int64 a1, int *a2, _QWORD *a3, int a4, char a5)
{
  __int64 v7; // rsi
  int v8; // r8d
  __int64 v9; // r9
  unsigned int v10; // r15d
  int v12; // r14d
  __int64 v13; // r9
  int v14; // ecx
  _QWORD *ReceiverEntry; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v16; // rcx
  _QWORD *v17; // rax
  unsigned __int8 v18; // dl
  unsigned __int8 i; // r8
  __int64 v20; // rax
  unsigned int v21; // ecx
  char *v22; // rax
  _QWORD *v23; // rcx
  int v24; // ecx
  int v25; // edx
  int v26; // [rsp+40h] [rbp-58h]
  unsigned int v27; // [rsp+44h] [rbp-54h]
  int v28; // [rsp+48h] [rbp-50h]
  char *v29; // [rsp+50h] [rbp-48h]
  unsigned int RandomInteger; // [rsp+A0h] [rbp+8h]
  unsigned int Size; // [rsp+A8h] [rbp+10h]

  v28 = *a2;
  v7 = *(_QWORD *)(a1 + 48);
  v8 = *(_DWORD *)(v7 + 56);
  if ( *a2 - v8 < 0 )
  {
    if ( a3 )
      *a3 = 0;
    return 0;
  }
  v9 = *(unsigned int *)(v7 + 52);
  v26 = *(unsigned __int8 *)(a1 + 160) - 1;
  v10 = *a2 & ~v26;
  if ( (int)(v10 - v9 - 5000) > 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_DDd(
        WPP_GLOBAL_Control->AttachedDevice,
        70,
        WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
        v9,
        v10,
        v10 - v9 + 1);
    *(_DWORD *)(a1 + 32) |= 0x100u;
    return 3221225626LL;
  }
  v12 = *(_DWORD *)(v7 + 60);
  Size = 40 * v26 + 136;
  v13 = v10 - v12;
  v29 = (char *)WPP_MAIN_CB.Dpc.SystemArgument1 + 2;
  if ( (int)v13 - 1000 > 0
    && (*(_DWORD *)(a1 + 32) & 8) == 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    WPP_SF_dddd(
      WPP_GLOBAL_Control->AttachedDevice,
      71,
      WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
      v13,
      v8,
      v12,
      v10);
  }
  v14 = *(_DWORD *)(*(_QWORD *)(v7 + 24) + 56LL) & 0x10;
  v27 = v14 != 0 ? 50 : 750;
  RandomInteger = GetRandomInteger(v14 != 0 ? 2 : 50, v14 != 0 ? 20 : 100);
  ReceiverEntry = 0;
  while ( (int)(v12 - v10) < 0 )
  {
    v16 = (struct _NPAGED_LOOKASIDE_LIST *)(v7 + 576);
    if ( !*(_BYTE *)(a1 + 161) )
      v16 = (struct _NPAGED_LOOKASIDE_LIST *)(v7 + 448);
    v17 = ExAllocateFromNPagedLookasideList(v16);
    ReceiverEntry = v17;
    if ( !v17 )
    {
      *(_DWORD *)(v7 + 64) += v26;
      *(_DWORD *)(v7 + 60) = v12;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids, Size, v12);
      return 3221225626LL;
    }
    memset(v17, 0, Size);
    if ( *(_BYTE *)(a1 + 161) )
    {
      v18 = *(_BYTE *)(a1 + 160);
      *((_BYTE *)ReceiverEntry + 57) = v18;
      *((_BYTE *)ReceiverEntry + 62) = v18;
      if ( v18 )
      {
        for ( i = 0; i < v18; ++i )
        {
          v20 = i;
          BYTE5(ReceiverEntry[5 * v20 + 14]) = v18;
          v18 = *((_BYTE *)ReceiverEntry + 62);
        }
      }
    }
    else
    {
      *((_BYTE *)ReceiverEntry + 57) = 1;
      *((_BYTE *)ReceiverEntry + 62) = 1;
      *((_BYTE *)ReceiverEntry + 117) = 1;
    }
    v12 += *(unsigned __int8 *)(a1 + 160);
    *((_DWORD *)ReceiverEntry + 4) = v12;
    *((_WORD *)ReceiverEntry + 27) = *(_WORD *)(a1 + 154);
    if ( a4 == 3 )
    {
      ReceiverEntry[4] = (char *)WPP_MAIN_CB.Dpc.SystemArgument1 + *(_QWORD *)(v7 + 80);
      ReceiverEntry[3] = 0;
      *((_BYTE *)ReceiverEntry + 56) = 0;
      goto LABEL_36;
    }
    ReceiverEntry[4] = 0;
    if ( a4 )
    {
      if ( a4 == 1 )
      {
        v21 = RandomInteger / *(unsigned __int8 *)(a1 + 160);
      }
      else
      {
        if ( a4 != 2 )
          goto LABEL_36;
        v21 = v27 + RandomInteger / *(unsigned __int8 *)(a1 + 160);
      }
      v22 = (char *)WPP_MAIN_CB.Dpc.SystemArgument1 + v21 / 0x14;
    }
    else
    {
      v22 = v29;
    }
    ReceiverEntry[3] = v22;
LABEL_36:
    v23 = *(_QWORD **)(v7 + 144);
    if ( *v23 != v7 + 136 )
      __fastfail(3u);
    ReceiverEntry[1] = v23;
    *ReceiverEntry = v7 + 136;
    *v23 = ReceiverEntry;
    *(_QWORD *)(v7 + 144) = ReceiverEntry;
    AppendPendingReceiverEntry(v7, (__int64)ReceiverEntry);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        73,
        WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
        *((unsigned int *)ReceiverEntry + 4),
        v12);
  }
  v24 = v28;
  v25 = *(_DWORD *)(v7 + 64);
  *(_DWORD *)(v7 + 60) = v12;
  if ( v28 - v25 > 0 )
  {
    if ( a5 )
      goto LABEL_48;
    if ( v12 - v25 > 0 )
    {
      v24 = v12 + v26;
LABEL_48:
      *(_DWORD *)(v7 + 64) = v24;
    }
  }
  if ( ReceiverEntry )
  {
    ReceiverEntry[3] = (char *)WPP_MAIN_CB.Dpc.SystemArgument1 + v27 / 0x14;
    if ( !a3 )
      return 0;
  }
  else
  {
    if ( !a3 )
      return 0;
    if ( *(_QWORD *)(v7 + 136) != v7 + 136 )
      ReceiverEntry = FindReceiverEntry(v7, v10);
  }
  *a3 = ReceiverEntry;
  return 0;
}

```

## disassembly

```asm
0x14000ca08  mov     [rsp+arg_18], r9d
0x14000ca0d  push    rbx
0x14000ca0e  push    rbp
0x14000ca0f  push    rsi
0x14000ca10  push    r12
0x14000ca12  push    r13
0x14000ca14  push    r14
0x14000ca16  push    r15
0x14000ca18  sub     rsp, 60h
0x14000ca1c  mov     rbp, rcx
0x14000ca1f  mov     r12, r8
0x14000ca22  mov     ecx, [rdx]
0x14000ca24  mov     [rsp+98h+var_50], ecx
0x14000ca28  mov     rsi, [rbp+30h]
0x14000ca2c  mov     r8d, [rsi+38h]
0x14000ca30  cmp     ecx, r8d
0x14000ca33  jns     short loc_14000CA4B
0x14000ca35  test    r12, r12
0x14000ca38  jz      loc_14000CDE2
0x14000ca3e  mov     qword ptr [r12], 0
0x14000ca46  jmp     loc_14000CDE2
0x14000ca4b  movzx   r10d, byte ptr [rbp+0A0h]
0x14000ca53  mov     r9d, [rsi+34h]
0x14000ca57  dec     r10d
0x14000ca5a  mov     r15d, r10d
0x14000ca5d  mov     [rsp+98h+var_58], r10d
0x14000ca62  not     r15d
0x14000ca65  and     r15d, ecx
0x14000ca68  mov     edx, r15d
0x14000ca6b  sub     edx, r9d
0x14000ca6e  lea     eax, [rdx-1388h]
0x14000ca74  test    eax, eax
0x14000ca76  jle     short loc_14000CAC2
0x14000ca78  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ca7f  lea     r13, WPP_GLOBAL_Control
0x14000ca86  cmp     rcx, r13
0x14000ca89  jz      short loc_14000CAB3
0x14000ca8b  mov     eax, [rcx+2Ch]
0x14000ca8e  test    al, 2
0x14000ca90  jz      short loc_14000CAB3
0x14000ca92  mov     rcx, [rcx+18h]
0x14000ca96  lea     eax, [rdx+1]
0x14000ca99  mov     [rsp+98h+var_70], eax
0x14000ca9d  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14000caa4  mov     edx, 46h ; 'F'
0x14000caa9  mov     [rsp+98h+var_78], r15d
0x14000caae  call    WPP_SF_DDd
0x14000cab3  bts     dword ptr [rbp+20h], 8
0x14000cab8  mov     eax, 0C000009Ah
0x14000cabd  jmp     loc_14000CDE4
0x14000cac2  mov     r14d, [rsi+3Ch]
0x14000cac6  lea     eax, [r10+r10*4]
0x14000caca  lea     eax, ds:88h[rax*8]
0x14000cad1  mov     r9d, r15d
0x14000cad4  mov     dword ptr [rsp+98h+Size], eax
0x14000cadb  lea     r13, WPP_GLOBAL_Control
0x14000cae2  mov     rax, cs:WPP_MAIN_CB.Dpc.SystemArgument1
0x14000cae9  sub     r9d, r14d
0x14000caec  add     rax, 2
0x14000caf0  mov     [rsp+98h+var_48], rax
0x14000caf5  lea     eax, [r9-3E8h]
0x14000cafc  test    eax, eax
0x14000cafe  jle     short loc_14000CB3E
0x14000cb00  mov     eax, [rbp+20h]
0x14000cb03  test    al, 8
0x14000cb05  jnz     short loc_14000CB3E
0x14000cb07  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb0e  cmp     rcx, r13
0x14000cb11  jz      short loc_14000CB3E
0x14000cb13  mov     eax, [rcx+2Ch]
0x14000cb16  test    al, 4
0x14000cb18  jz      short loc_14000CB3E
0x14000cb1a  mov     rcx, [rcx+18h]
0x14000cb1e  mov     edx, 47h ; 'G'
0x14000cb23  mov     [rsp+98h+var_68], r15d
0x14000cb28  mov     [rsp+98h+var_70], r14d
0x14000cb2d  mov     [rsp+98h+var_78], r8d
0x14000cb32  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14000cb39  call    WPP_SF_dddd
0x14000cb3e  mov     rax, [rsi+18h]
0x14000cb42  mov     ecx, [rax+38h]
0x14000cb45  and     ecx, 10h
0x14000cb48  mov     eax, ecx
0x14000cb4a  neg     eax
0x14000cb4c  sbb     eax, eax
0x14000cb4e  and     eax, 0FFFFFD44h
0x14000cb53  add     eax, 2EEh
0x14000cb58  mov     [rsp+98h+var_54], eax
0x14000cb5c  mov     eax, ecx
0x14000cb5e  neg     eax
0x14000cb60  sbb     edx, edx
0x14000cb62  and     edx, 0FFFFFFB0h
0x14000cb65  add     edx, 64h ; 'd'
0x14000cb68  neg     ecx
0x14000cb6a  sbb     ecx, ecx
0x14000cb6c  and     ecx, 0FFFFFFD0h
0x14000cb6f  add     ecx, 32h ; '2'
0x14000cb72  call    GetRandomInteger
0x14000cb77  mov     [rsp+98h+arg_0], eax
0x14000cb7e  xor     ebx, ebx
0x14000cb80  cmp     r14d, r15d
0x14000cb83  jns     loc_14000CD6A
0x14000cb89  cmp     byte ptr [rbp+0A1h], 0
0x14000cb90  lea     rcx, [rsi+240h]
0x14000cb97  jnz     short loc_14000CBA0
0x14000cb99  lea     rcx, [rsi+1C0h]; Lookaside
0x14000cba0  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000cba7  nop     dword ptr [rax+rax+00h]
0x14000cbac  mov     rbx, rax
0x14000cbaf  test    rax, rax
0x14000cbb2  jz      loc_14000CD1D
0x14000cbb8  mov     r8d, dword ptr [rsp+98h+Size]; Size
0x14000cbc0  xor     edx, edx; Val
0x14000cbc2  mov     rcx, rax; void *
0x14000cbc5  call    memset
0x14000cbca  cmp     byte ptr [rbp+0A1h], 0
0x14000cbd1  jz      short loc_14000CBFF
0x14000cbd3  mov     dl, [rbp+0A0h]
0x14000cbd9  mov     [rbx+39h], dl
0x14000cbdc  mov     [rbx+3Eh], dl
0x14000cbdf  test    dl, dl
0x14000cbe1  jz      short loc_14000CC0B
0x14000cbe3  xor     r8b, r8b
0x14000cbe6  movzx   eax, r8b
0x14000cbea  inc     r8b
0x14000cbed  lea     rcx, [rax+rax*4]
0x14000cbf1  mov     [rbx+rcx*8+75h], dl
0x14000cbf5  mov     dl, [rbx+3Eh]
0x14000cbf8  cmp     r8b, dl
0x14000cbfb  jb      short loc_14000CBE6
0x14000cbfd  jmp     short loc_14000CC0B
0x14000cbff  mov     byte ptr [rbx+39h], 1
0x14000cc03  mov     byte ptr [rbx+3Eh], 1
0x14000cc07  mov     byte ptr [rbx+75h], 1
0x14000cc0b  movzx   eax, byte ptr [rbp+0A0h]
0x14000cc12  mov     ecx, [rsp+98h+arg_18]
0x14000cc19  add     r14d, eax
0x14000cc1c  mov     [rbx+10h], r14d
0x14000cc20  movzx   eax, word ptr [rbp+9Ah]
0x14000cc27  mov     [rbx+36h], ax
0x14000cc2b  cmp     ecx, 3
0x14000cc2e  jnz     short loc_14000CC4D
0x14000cc30  mov     rcx, [rsi+50h]
0x14000cc34  add     rcx, cs:WPP_MAIN_CB.Dpc.SystemArgument1
0x14000cc3b  mov     [rbx+20h], rcx
0x14000cc3f  mov     qword ptr [rbx+18h], 0
0x14000cc47  mov     byte ptr [rbx+38h], 0
0x14000cc4b  jmp     short loc_14000CCAF
0x14000cc4d  mov     qword ptr [rbx+20h], 0
0x14000cc55  test    ecx, ecx
0x14000cc57  jz      short loc_14000CCA6
0x14000cc59  sub     ecx, 1
0x14000cc5c  jz      short loc_14000CC90
0x14000cc5e  cmp     ecx, 1
0x14000cc61  jnz     short loc_14000CCAF
0x14000cc63  movzx   ecx, byte ptr [rbp+0A0h]
0x14000cc6a  xor     edx, edx
0x14000cc6c  mov     eax, [rsp+98h+arg_0]
0x14000cc73  div     ecx
0x14000cc75  mov     ecx, eax
0x14000cc77  add     ecx, [rsp+98h+var_54]
0x14000cc7b  mov     eax, 0CCCCCCCDh
0x14000cc80  mul     ecx
0x14000cc82  shr     edx, 4
0x14000cc85  mov     eax, edx
0x14000cc87  add     rax, cs:WPP_MAIN_CB.Dpc.SystemArgument1
0x14000cc8e  jmp     short loc_14000CCAB
0x14000cc90  movzx   ecx, byte ptr [rbp+0A0h]
0x14000cc97  xor     edx, edx
0x14000cc99  mov     eax, [rsp+98h+arg_0]
0x14000cca0  div     ecx
0x14000cca2  mov     ecx, eax
0x14000cca4  jmp     short loc_14000CC7B
0x14000cca6  mov     rax, [rsp+98h+var_48]
0x14000ccab  mov     [rbx+18h], rax
0x14000ccaf  lea     rax, [rsi+88h]
0x14000ccb6  mov     rcx, [rax+8]
0x14000ccba  cmp     [rcx], rax
0x14000ccbd  jnz     short loc_14000CD16
0x14000ccbf  mov     [rbx+8], rcx
0x14000ccc3  mov     rdx, rbx
0x14000ccc6  mov     [rbx], rax
0x14000ccc9  mov     [rcx], rbx
0x14000cccc  mov     rcx, rsi
0x14000cccf  mov     [rax+8], rbx
0x14000ccd3  call    AppendPendingReceiverEntry
0x14000ccd8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ccdf  cmp     rcx, r13
0x14000cce2  jz      loc_14000CB80
0x14000cce8  mov     eax, [rcx+2Ch]
0x14000cceb  test    al, 20h
0x14000cced  jz      loc_14000CB80
0x14000ccf3  mov     r9d, [rbx+10h]
0x14000ccf7  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14000ccfe  mov     rcx, [rcx+18h]
0x14000cd02  mov     edx, 49h ; 'I'
0x14000cd07  mov     [rsp+98h+var_78], r14d
0x14000cd0c  call    WPP_SF_Dd
0x14000cd11  jmp     loc_14000CB80
0x14000cd16  mov     ecx, 3
0x14000cd1b  int     29h; Win8: RtlFailFast(ecx)
0x14000cd1d  mov     eax, [rsp+98h+var_58]
0x14000cd21  add     [rsi+40h], eax
0x14000cd24  mov     [rsi+3Ch], r14d
0x14000cd28  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cd2f  cmp     rcx, r13
0x14000cd32  jz      loc_14000CAB8
0x14000cd38  mov     eax, [rcx+2Ch]
0x14000cd3b  test    al, 2
0x14000cd3d  jz      loc_14000CAB8
0x14000cd43  mov     r9d, dword ptr [rsp+98h+Size]
0x14000cd4b  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14000cd52  mov     rcx, [rcx+18h]
0x14000cd56  mov     edx, 48h ; 'H'
0x14000cd5b  mov     [rsp+98h+var_78], r14d
0x14000cd60  call    WPP_SF_Dd
0x14000cd65  jmp     loc_14000CAB8
0x14000cd6a  mov     ecx, [rsp+98h+var_50]
0x14000cd6e  mov     eax, ecx
0x14000cd70  mov     edx, [rsi+40h]
0x14000cd73  sub     eax, edx
0x14000cd75  mov     [rsi+3Ch], r14d
0x14000cd79  test    eax, eax
0x14000cd7b  jle     short loc_14000CD9A
0x14000cd7d  cmp     [rsp+98h+arg_20], 0
0x14000cd85  jnz     short loc_14000CD97
0x14000cd87  mov     ecx, r14d
0x14000cd8a  sub     ecx, edx
0x14000cd8c  test    ecx, ecx
0x14000cd8e  jle     short loc_14000CD9A
0x14000cd90  mov     ecx, [rsp+98h+var_58]
0x14000cd94  add     ecx, r14d
0x14000cd97  mov     [rsi+40h], ecx
0x14000cd9a  test    rbx, rbx
0x14000cd9d  jz      short loc_14000CDBF
0x14000cd9f  mov     eax, 0CCCCCCCDh
0x14000cda4  mul     [rsp+98h+var_54]
0x14000cda8  shr     edx, 4
0x14000cdab  mov     eax, edx
0x14000cdad  add     rax, cs:WPP_MAIN_CB.Dpc.SystemArgument1
0x14000cdb4  mov     [rbx+18h], rax
0x14000cdb8  test    r12, r12
0x14000cdbb  jz      short loc_14000CDE2
0x14000cdbd  jmp     short loc_14000CDDE
0x14000cdbf  test    r12, r12
0x14000cdc2  jz      short loc_14000CDE2
0x14000cdc4  lea     rax, [rsi+88h]
0x14000cdcb  cmp     [rax], rax
0x14000cdce  jz      short loc_14000CDDE
0x14000cdd0  mov     edx, r15d
0x14000cdd3  mov     rcx, rsi
0x14000cdd6  call    FindReceiverEntry
0x14000cddb  mov     rbx, rax
0x14000cdde  mov     [r12], rbx
0x14000cde2  xor     eax, eax
0x14000cde4  add     rsp, 60h
0x14000cde8  pop     r15
0x14000cdea  pop     r14
0x14000cdec  pop     r13
0x14000cdee  pop     r12
0x14000cdf0  pop     rsi
0x14000cdf1  pop     rbp
0x14000cdf2  pop     rbx
0x14000cdf3  retn
```
