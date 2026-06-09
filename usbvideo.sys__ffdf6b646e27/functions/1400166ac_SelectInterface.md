# SelectInterface

- ea: `0x1400166ac`
- end: `0x140016be9`
- name: `SelectInterface`
- size: `1341`
- prototype: `__int64 __fastcall(PVOID StartPosition)`
- caller_count: `7`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x14000a928`
- `0x14000b57c`
- `0x140015234`
- `0x140015388`
- `0x14001a50c`
- `0x140024a10`
- `0x140039650`

## callees

- `0x140009b9c`
- `0x14000c95c`
- `0x14000c9e4`
- `0x1400166ac`
- `0x14001709c`
- `0x140017e4c`
- `0x14001ab4c`
- `0x14001b15c`
- `0x14001d0cc`
- `0x140021884`
- `0x140040b40`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140016902`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001699e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016a8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016b61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016bd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016902`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001699e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016a8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016b61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016bd5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140016755`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400169c3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140016ab2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140016755`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400169c3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140016ab2`

## pseudocode

```c
__int64 __fastcall SelectInterface(unsigned __int8 *StartPosition, __int64 a2, __int64 a3)
{
  unsigned __int8 v7; // al
  unsigned __int8 v8; // r14
  bool v9; // al
  int v10; // r13d
  BOOL v11; // r12d
  unsigned int *PoolWithTag; // rax
  unsigned int *v13; // rbx
  __int64 v14; // rax
  unsigned int v15; // ecx
  unsigned int v16; // edx
  int v17; // eax
  unsigned int v18; // r15d
  __int64 v19; // rsi
  unsigned int v20; // eax
  void *v21; // rcx
  SIZE_T v22; // r14
  PVOID v23; // rax
  void *v24; // rbp
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  unsigned int v27; // ecx
  void *v28; // rcx
  SIZE_T v29; // r14
  PVOID v30; // rax
  void *v31; // rbp
  int v32; // [rsp+98h] [rbp+10h]

  if ( *(_BYTE *)a2 )
    return 3221225664LL;
  if ( (unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline() )
    v7 = IsZeroBWAltSettingEx(a2, StartPosition);
  else
    v7 = IsZeroBWAltSetting(*(PVOID *)(a2 + 32), StartPosition);
  v8 = v7;
  v9 = IsBulkVideoEndpoint(*(struct _USB_CONFIGURATION_DESCRIPTOR **)(a2 + 32), StartPosition);
  v10 = StartPosition[4];
  v11 = v9;
  PoolWithTag = (unsigned int *)ExAllocatePoolWithTag((POOL_TYPE)1536, (unsigned int)(24 * v10 + 56), 0x56425355u);
  v13 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, (unsigned int)(24 * v10 + 56));
      goto LABEL_9;
    }
    return 3221225626LL;
  }
  if ( !PoolWithTag )
    return 3221225626LL;
LABEL_9:
  memset(v13, 0, (unsigned int)(24 * v10 + 56));
  v14 = *(_QWORD *)(a2 + 32);
  v15 = 0;
  v16 = *(unsigned __int8 *)(v14 + 4);
  if ( *(_BYTE *)(v14 + 4) )
  {
    while ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a2 + 664) + 16LL * v15) + 2LL) != StartPosition[2] )
    {
      if ( ++v15 >= v16 )
        goto LABEL_12;
    }
  }
  else
  {
LABEL_12:
    if ( v15 == v16 )
    {
LABEL_33:
      ExFreePoolWithTag(v13, 0x56425355u);
      return 3221225488LL;
    }
  }
  *((_BYTE *)v13 + 34) = StartPosition[2];
  *((_WORD *)v13 + 16) = 24 * (v10 + 1);
  *((_BYTE *)v13 + 35) = StartPosition[3];
  if ( v8 )
  {
    if ( !v11 )
    {
LABEL_20:
      if ( !v10 )
        goto LABEL_22;
LABEL_21:
      v13[18] = 0;
      goto LABEL_22;
    }
LABEL_19:
    if ( a3 )
      goto LABEL_21;
    goto LABEL_20;
  }
  if ( v11 )
    goto LABEL_19;
  v13[18] = *(_DWORD *)(a2 + 704) * *(_DWORD *)(*(_QWORD *)(a3 + 16) + 28LL);
LABEL_22:
  v32 = 24 * v10 + 56;
  *(_WORD *)v13 = v32;
  *((_WORD *)v13 + 1) = 1;
  *((_QWORD *)v13 + 3) = *(_QWORD *)(a2 + 672);
  if ( (unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline()
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qdddddd(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      *((unsigned __int16 *)v13 + 16),
      a2,
      *((unsigned __int8 *)v13 + 34),
      *((unsigned __int8 *)v13 + 35),
      *((unsigned __int16 *)v13 + 16),
      v32,
      v8,
      v11);
  }
  v17 = SubmitUrbToUsbdSynch(*(_QWORD *)(a2 + 24), v13);
  v18 = v17;
  if ( v17 < 0 || (v13[1] & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, a2, v17);
    goto LABEL_74;
  }
  if ( !v8 && !v13[12] )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, a2);
    goto LABEL_33;
  }
  if ( v11 )
  {
    if ( !a3 )
      goto LABEL_68;
LABEL_53:
    v27 = v13[12];
    v19 = *(_QWORD *)(a3 + 16);
    *(_DWORD *)(v19 + 56) = v27;
    *(_QWORD *)(v19 + 72) = *((_QWORD *)v13 + 8);
    if ( v27 > 1 )
      *(_QWORD *)(v19 + 80) = *((_QWORD *)v13 + 11);
    v28 = *(void **)(v19 + 88);
    if ( v28 )
      ExFreePoolWithTag(v28, 0x56425355u);
    v29 = 24LL * *(unsigned int *)(v19 + 56);
    v30 = ExAllocatePoolWithTag((POOL_TYPE)1536, v29, 0x56425355u);
    v31 = v30;
    if ( ExPoolZeroingNativelySupported || !v30 )
    {
      *(_QWORD *)(v19 + 88) = v30;
      if ( !v30 )
      {
LABEL_67:
        ExFreePoolWithTag(v13, 0x56425355u);
        return 3221225626LL;
      }
    }
    else
    {
      memset(v30, 0, v29);
      *(_QWORD *)(v19 + 88) = v31;
    }
    memmove(v31, v13 + 14, 24LL * *(unsigned int *)(v19 + 56));
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_74;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        44,
        WPP_b11e537a527d30190cd6733beb5dc248_Traceguids,
        a2,
        *(_QWORD *)(v19 + 72));
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      goto LABEL_74;
    v26 = 45;
    goto LABEL_51;
  }
  if ( !v8 )
    goto LABEL_53;
  if ( !a3 )
  {
LABEL_68:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, a2);
    goto LABEL_74;
  }
  v19 = *(_QWORD *)(a3 + 16);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, a2);
  v20 = v13[12];
  *(_DWORD *)(v19 + 56) = v20;
  *(_QWORD *)(v19 + 72) = 0;
  if ( v20 == 1 )
    *(_QWORD *)(v19 + 80) = *((_QWORD *)v13 + 8);
  v21 = *(void **)(v19 + 88);
  if ( v21 )
    ExFreePoolWithTag(v21, 0x56425355u);
  v22 = 24LL * *(unsigned int *)(v19 + 56);
  v23 = ExAllocatePoolWithTag((POOL_TYPE)1536, v22, 0x56425355u);
  v24 = v23;
  if ( !ExPoolZeroingNativelySupported && v23 )
  {
    memset(v23, 0, v22);
    *(_QWORD *)(v19 + 88) = v24;
    goto LABEL_48;
  }
  *(_QWORD *)(v19 + 88) = v23;
  if ( !v23 )
    goto LABEL_67;
LABEL_48:
  memmove(v24, v13 + 14, 24LL * *(unsigned int *)(v19 + 56));
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    goto LABEL_74;
  v26 = 47;
LABEL_51:
  WPP_SF_qq(v25->AttachedDevice, v26, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, a2, *(_QWORD *)(v19 + 80));
LABEL_74:
  ExFreePoolWithTag(v13, 0x56425355u);
  return v18;
}

```

## disassembly

```asm
0x1400166ac  mov     [rsp+arg_0], rbx
0x1400166b1  push    rbp
0x1400166b2  push    rsi
0x1400166b3  push    rdi
0x1400166b4  push    r12
0x1400166b6  push    r13
0x1400166b8  push    r14
0x1400166ba  push    r15
0x1400166bc  sub     rsp, 50h
0x1400166c0  cmp     byte ptr [rdx], 0
0x1400166c3  mov     rbp, r8
0x1400166c6  mov     rdi, rdx
0x1400166c9  mov     rsi, rcx
0x1400166cc  jz      short loc_1400166D8
0x1400166ce  mov     eax, 0C00000C0h
0x1400166d3  jmp     loc_140016913
0x1400166d8  call    Feature_EUSB2__private_IsEnabledDeviceUsageNoInline
0x1400166dd  mov     rdx, rsi
0x1400166e0  test    eax, eax
0x1400166e2  jnz     short loc_1400166EF
0x1400166e4  mov     rcx, [rdi+20h]
0x1400166e8  call    IsZeroBWAltSetting
0x1400166ed  jmp     short loc_1400166F7
0x1400166ef  mov     rcx, rdi
0x1400166f2  call    IsZeroBWAltSettingEx
0x1400166f7  mov     rcx, [rdi+20h]; DescriptorBuffer
0x1400166fb  mov     rdx, rsi; StartPosition
0x1400166fe  mov     r14b, al
0x140016701  call    IsBulkVideoEndpoint
0x140016706  movzx   r13d, byte ptr [rsi+4]
0x14001670b  mov     edx, 1
0x140016710  add     edx, r13d
0x140016713  movzx   r12d, al
0x140016717  movzx   ecx, dx
0x14001671a  mov     r8d, 56425355h; Tag
0x140016720  add     cx, cx
0x140016723  add     dx, cx
0x140016726  lea     ecx, ds:0[r13*2]
0x14001672e  add     ecx, r13d
0x140016731  shl     dx, 3
0x140016735  mov     word ptr [rsp+88h+arg_18], dx
0x14001673d  lea     eax, ds:38h[rcx*8]
0x140016744  mov     ecx, 600h; PoolType
0x140016749  mov     edx, eax; NumberOfBytes
0x14001674b  mov     [rsp+88h+arg_8], eax
0x140016752  mov     r15d, eax
0x140016755  call    cs:__imp_ExAllocatePoolWithTag
0x14001675c  nop     dword ptr [rax+rax+00h]
0x140016761  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140016768  mov     rbx, rax
0x14001676b  jnz     loc_140016804
0x140016771  test    rax, rax
0x140016774  jz      loc_14001680D
0x14001677a  mov     r8d, r15d; Size
0x14001677d  xor     edx, edx; Val
0x14001677f  mov     rcx, rax; void *
0x140016782  call    memset
0x140016787  mov     r8, r15; Size
0x14001678a  xor     edx, edx; Val
0x14001678c  mov     rcx, rbx; void *
0x14001678f  call    memset
0x140016794  mov     rax, [rdi+20h]
0x140016798  xor     ecx, ecx
0x14001679a  movzx   edx, byte ptr [rax+4]
0x14001679e  lea     r10d, [rcx+1]
0x1400167a2  test    edx, edx
0x1400167a4  jz      short loc_1400167C7
0x1400167a6  mov     r8b, [rsi+2]
0x1400167aa  mov     r9, [rdi+298h]
0x1400167b1  mov     eax, ecx
0x1400167b3  add     rax, rax
0x1400167b6  mov     rax, [r9+rax*8]
0x1400167ba  cmp     [rax+2], r8b
0x1400167be  jz      short loc_1400167CF
0x1400167c0  add     ecx, r10d
0x1400167c3  cmp     ecx, edx
0x1400167c5  jb      short loc_1400167B1
0x1400167c7  cmp     ecx, edx
0x1400167c9  jz      loc_1400168FA
0x1400167cf  mov     al, [rsi+2]
0x1400167d2  mov     [rbx+22h], al
0x1400167d5  mov     rax, [rsp+88h+arg_18]
0x1400167dd  mov     [rbx+20h], ax
0x1400167e1  mov     al, [rsi+3]
0x1400167e4  mov     [rbx+23h], al
0x1400167e7  test    r14b, r14b
0x1400167ea  jnz     short loc_140016817
0x1400167ec  test    r12b, r12b
0x1400167ef  jnz     short loc_14001681C
0x1400167f1  mov     rax, [rbp+10h]
0x1400167f5  mov     ecx, [rax+1Ch]
0x1400167f8  imul    ecx, [rdi+2C0h]
0x1400167ff  mov     [rbx+48h], ecx
0x140016802  jmp     short loc_14001682D
0x140016804  test    rbx, rbx
0x140016807  jnz     loc_140016787
0x14001680d  mov     eax, 0C000009Ah
0x140016812  jmp     loc_140016913
0x140016817  test    r12b, r12b
0x14001681a  jz      short loc_140016821
0x14001681c  test    rbp, rbp
0x14001681f  jnz     short loc_140016826
0x140016821  test    r13d, r13d
0x140016824  jz      short loc_14001682D
0x140016826  mov     dword ptr [rbx+48h], 0
0x14001682d  mov     esi, [rsp+88h+arg_8]
0x140016834  mov     [rbx], si
0x140016837  mov     [rbx+2], r10w
0x14001683c  mov     rax, [rdi+2A0h]
0x140016843  mov     [rbx+18h], rax
0x140016847  call    Feature_EUSB2__private_IsEnabledDeviceUsageNoInline
0x14001684c  lea     r13, WPP_GLOBAL_Control
0x140016853  test    eax, eax
0x140016855  jz      short loc_1400168A4
0x140016857  mov     rcx, cs:WPP_GLOBAL_Control
0x14001685e  cmp     rcx, r13
0x140016861  jz      short loc_1400168A4
0x140016863  cmp     byte ptr [rcx+29h], 4
0x140016867  jb      short loc_1400168A4
0x140016869  movzx   r9d, byte ptr [rbx+23h]
0x14001686e  movzx   r8d, word ptr [rbx+20h]
0x140016873  movzx   r10d, byte ptr [rbx+22h]
0x140016878  mov     rcx, [rcx+18h]
0x14001687c  mov     [rsp+88h+var_40], r12d
0x140016881  movzx   edx, r14b
0x140016885  mov     [rsp+88h+var_48], edx
0x140016889  mov     [rsp+88h+var_50], esi
0x14001688d  mov     [rsp+88h+var_58], r8d
0x140016892  mov     [rsp+88h+var_60], r9d
0x140016897  mov     r9, rdi
0x14001689a  mov     dword ptr [rsp+88h+var_68], r10d
0x14001689f  call    WPP_SF_qdddddd
0x1400168a4  mov     rcx, [rdi+18h]
0x1400168a8  mov     rdx, rbx
0x1400168ab  call    SubmitUrbToUsbdSynch
0x1400168b0  mov     r15d, eax
0x1400168b3  test    eax, eax
0x1400168b5  js      loc_140016B9E
0x1400168bb  cmp     dword ptr [rbx+4], 0
0x1400168bf  jl      loc_140016B9E
0x1400168c5  test    r14b, r14b
0x1400168c8  jnz     short loc_14001692C
0x1400168ca  cmp     dword ptr [rbx+30h], 0
0x1400168ce  jnz     short loc_14001692C
0x1400168d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400168d7  cmp     rcx, r13
0x1400168da  jz      short loc_1400168FA
0x1400168dc  cmp     byte ptr [rcx+29h], 2
0x1400168e0  jb      short loc_1400168FA
0x1400168e2  mov     rcx, [rcx+18h]
0x1400168e6  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x1400168ed  mov     edx, 2Bh ; '+'
0x1400168f2  mov     r9, rdi
0x1400168f5  call    WPP_SF_q
0x1400168fa  mov     edx, 56425355h; Tag
0x1400168ff  mov     rcx, rbx; P
0x140016902  call    cs:__imp_ExFreePoolWithTag
0x140016909  nop     dword ptr [rax+rax+00h]
0x14001690e  mov     eax, 0C0000010h
0x140016913  mov     rbx, [rsp+88h+arg_0]
0x14001691b  add     rsp, 50h
0x14001691f  pop     r15
0x140016921  pop     r14
0x140016923  pop     r13
0x140016925  pop     r12
0x140016927  pop     rdi
0x140016928  pop     rsi
0x140016929  pop     rbp
0x14001692a  retn
0x14001692c  test    r12b, r12b
0x14001692f  jnz     loc_140016A57
0x140016935  test    r14b, r14b
0x140016938  jz      loc_140016A60
0x14001693e  test    rbp, rbp
0x140016941  jz      loc_140016B72
0x140016947  mov     rsi, [rbp+10h]
0x14001694b  mov     rcx, cs:WPP_GLOBAL_Control
0x140016952  cmp     rcx, r13
0x140016955  jz      short loc_140016975
0x140016957  cmp     byte ptr [rcx+29h], 5
0x14001695b  jb      short loc_140016975
0x14001695d  mov     rcx, [rcx+18h]
0x140016961  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140016968  mov     edx, 2Eh ; '.'
0x14001696d  mov     r9, rdi
0x140016970  call    WPP_SF_q
0x140016975  mov     eax, [rbx+30h]
0x140016978  mov     [rsi+38h], eax
0x14001697b  mov     qword ptr [rsi+48h], 0
0x140016983  cmp     eax, 1
0x140016986  jnz     short loc_140016990
0x140016988  mov     rax, [rbx+40h]
0x14001698c  mov     [rsi+50h], rax
0x140016990  mov     rcx, [rsi+58h]; P
0x140016994  test    rcx, rcx
0x140016997  jz      short loc_1400169AA
0x140016999  mov     edx, 56425355h; Tag
0x14001699e  call    cs:__imp_ExFreePoolWithTag
0x1400169a5  nop     dword ptr [rax+rax+00h]
0x1400169aa  mov     eax, [rsi+38h]
0x1400169ad  mov     r8d, 56425355h; Tag
0x1400169b3  mov     ecx, 600h; PoolType
0x1400169b8  lea     r14, [rax+rax*2]
0x1400169bc  shl     r14, 3
0x1400169c0  mov     rdx, r14; NumberOfBytes
0x1400169c3  call    cs:__imp_ExAllocatePoolWithTag
0x1400169ca  nop     dword ptr [rax+rax+00h]
0x1400169cf  cmp     cs:ExPoolZeroingNativelySupported, 0
0x1400169d6  mov     rbp, rax
0x1400169d9  jnz     short loc_1400169F3
0x1400169db  test    rax, rax
0x1400169de  jz      short loc_1400169F3
0x1400169e0  mov     r8, r14; Size
0x1400169e3  xor     edx, edx; Val
0x1400169e5  mov     rcx, rax; void *
0x1400169e8  call    memset
0x1400169ed  mov     [rsi+58h], rbp
0x1400169f1  jmp     short loc_140016A00
0x1400169f3  mov     [rsi+58h], rbp
0x1400169f7  test    rbp, rbp
0x1400169fa  jz      loc_140016B59
0x140016a00  mov     eax, [rsi+38h]
0x140016a03  lea     rdx, [rbx+38h]; Src
0x140016a07  mov     rcx, rbp; void *
0x140016a0a  lea     r8, [rax+rax*2]
0x140016a0e  shl     r8, 3; Size
0x140016a12  call    memmove
0x140016a17  mov     rcx, cs:WPP_GLOBAL_Control
0x140016a1e  cmp     rcx, r13
0x140016a21  jz      loc_140016BCD
0x140016a27  cmp     byte ptr [rcx+29h], 5
0x140016a2b  jb      loc_140016BCD
0x140016a31  mov     edx, 2Fh ; '/'
0x140016a36  mov     rax, [rsi+50h]
0x140016a3a  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140016a41  mov     rcx, [rcx+18h]
0x140016a45  mov     r9, rdi
0x140016a48  mov     [rsp+88h+var_68], rax
0x140016a4d  call    WPP_SF_qq
0x140016a52  jmp     loc_140016BCD
0x140016a57  test    rbp, rbp
0x140016a5a  jz      loc_140016B72
0x140016a60  mov     ecx, [rbx+30h]
0x140016a63  mov     rsi, [rbp+10h]
0x140016a67  mov     [rsi+38h], ecx
0x140016a6a  mov     rax, [rbx+40h]
0x140016a6e  mov     [rsi+48h], rax
0x140016a72  cmp     ecx, 1
0x140016a75  jbe     short loc_140016A7F
0x140016a77  mov     rax, [rbx+58h]
0x140016a7b  mov     [rsi+50h], rax
0x140016a7f  mov     rcx, [rsi+58h]; P
0x140016a83  test    rcx, rcx
0x140016a86  jz      short loc_140016A99
0x140016a88  mov     edx, 56425355h; Tag
0x140016a8d  call    cs:__imp_ExFreePoolWithTag
0x140016a94  nop     dword ptr [rax+rax+00h]
0x140016a99  mov     eax, [rsi+38h]
0x140016a9c  mov     r8d, 56425355h; Tag
0x140016aa2  mov     ecx, 600h; PoolType
0x140016aa7  lea     r14, [rax+rax*2]
0x140016aab  shl     r14, 3
0x140016aaf  mov     rdx, r14; NumberOfBytes
0x140016ab2  call    cs:__imp_ExAllocatePoolWithTag
0x140016ab9  nop     dword ptr [rax+rax+00h]
0x140016abe  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140016ac5  mov     rbp, rax
0x140016ac8  jnz     short loc_140016AE2
0x140016aca  test    rax, rax
0x140016acd  jz      short loc_140016AE2
0x140016acf  mov     r8, r14; Size
0x140016ad2  xor     edx, edx; Val
0x140016ad4  mov     rcx, rax; void *
0x140016ad7  call    memset
0x140016adc  mov     [rsi+58h], rbp
0x140016ae0  jmp     short loc_140016AEB
0x140016ae2  mov     [rsi+58h], rbp
0x140016ae6  test    rbp, rbp
0x140016ae9  jz      short loc_140016B59
0x140016aeb  mov     eax, [rsi+38h]
0x140016aee  lea     rdx, [rbx+38h]; Src
0x140016af2  mov     rcx, rbp; void *
0x140016af5  lea     r8, [rax+rax*2]
0x140016af9  shl     r8, 3; Size
0x140016afd  call    memmove
0x140016b02  mov     rcx, cs:WPP_GLOBAL_Control
0x140016b09  cmp     rcx, r13
0x140016b0c  jz      loc_140016BCD
0x140016b12  cmp     byte ptr [rcx+29h], 5
0x140016b16  jb      short loc_140016B39
0x140016b18  mov     rax, [rsi+48h]
0x140016b1c  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140016b23  mov     rcx, [rcx+18h]
0x140016b27  mov     edx, 2Ch ; ','
0x140016b2c  mov     r9, rdi
0x140016b2f  mov     [rsp+88h+var_68], rax
0x140016b34  call    WPP_SF_qq
0x140016b39  mov     rcx, cs:WPP_GLOBAL_Control
0x140016b40  cmp     rcx, r13
0x140016b43  jz      loc_140016BCD
  ... truncated ...
```
