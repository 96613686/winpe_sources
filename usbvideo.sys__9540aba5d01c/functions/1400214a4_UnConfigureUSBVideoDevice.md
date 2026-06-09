# UnConfigureUSBVideoDevice

- ea: `0x1400214a4`
- end: `0x14002169c`
- name: `UnConfigureUSBVideoDevice`
- size: `504`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140011354`

## callees

- `0x140009b9c`
- `0x14001ab4c`
- `0x14001b15c`
- `0x1400214a4`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140021640`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021640`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400215ac`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400215ac`

## pseudocode

```c
__int64 __fastcall UnConfigureUSBVideoDevice(__int64 a1)
{
  __int64 v1; // rbx
  unsigned int v3; // edi
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  _QWORD *PoolWithTag; // rax
  _QWORD *v7; // rsi
  int v8; // eax
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx

  v1 = *(_QWORD *)(a1 + 16);
  v3 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v1);
  if ( *(_BYTE *)v1 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v5 = 11;
LABEL_8:
      WPP_SF_q(v4->AttachedDevice, v5, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v1);
      return v3;
    }
    return v3;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v1);
  if ( *(_QWORD *)(v1 + 672) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v1);
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, 0x58u, 0x56425355u);
    v7 = PoolWithTag;
    if ( !PoolWithTag )
    {
      v3 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_b11e537a527d30190cd6733beb5dc248_Traceguids,
          v1,
          -1073741670);
      goto LABEL_34;
    }
    if ( !ExPoolZeroingNativelySupported )
      memset(PoolWithTag, 0, 0x58u);
    *(_DWORD *)v7 = 88;
    v7[3] = 0;
    v8 = SubmitUrbToUsbdSynch(a1, v7);
    v3 = v8;
    if ( v8 >= 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        goto LABEL_30;
      v10 = 16;
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        goto LABEL_30;
      v10 = 15;
    }
    WPP_SF_qD(v9->AttachedDevice, v10, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v1, v8);
LABEL_30:
    ExFreePoolWithTag(v7, 0x56425355u);
LABEL_34:
    *(_QWORD *)(v1 + 672) = 0;
    return v3;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v5 = 13;
    goto LABEL_8;
  }
  return v3;
}

```

## disassembly

```asm
0x1400214a4  push    rbx
0x1400214a6  push    rbp
0x1400214a7  push    rsi
0x1400214a8  push    rdi
0x1400214a9  push    r13
0x1400214ab  push    r15
0x1400214ad  sub     rsp, 38h
0x1400214b1  mov     rbx, [rcx+10h]
0x1400214b5  mov     rbp, rcx
0x1400214b8  xor     edi, edi
0x1400214ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400214c1  lea     r15, WPP_GLOBAL_Control
0x1400214c8  lea     r13, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x1400214cf  cmp     rcx, r15
0x1400214d2  jz      short loc_1400214EC
0x1400214d4  cmp     byte ptr [rcx+29h], 4
0x1400214d8  jb      short loc_1400214EC
0x1400214da  mov     rcx, [rcx+18h]
0x1400214de  lea     edx, [rdi+0Ah]
0x1400214e1  mov     r9, rbx
0x1400214e4  mov     r8, r13
0x1400214e7  call    WPP_SF_q
0x1400214ec  cmp     [rbx], dil
0x1400214ef  jz      short loc_140021524
0x1400214f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400214f8  cmp     rcx, r15
0x1400214fb  jz      loc_14002168C
0x140021501  cmp     byte ptr [rcx+29h], 4
0x140021505  jb      loc_14002168C
0x14002150b  mov     edx, 0Bh
0x140021510  mov     rcx, [rcx+18h]
0x140021514  mov     r9, rbx
0x140021517  mov     r8, r13
0x14002151a  call    WPP_SF_q
0x14002151f  jmp     loc_14002168C
0x140021524  mov     rcx, cs:WPP_GLOBAL_Control
0x14002152b  cmp     rcx, r15
0x14002152e  jz      short loc_14002154A
0x140021530  cmp     byte ptr [rcx+29h], 4
0x140021534  jb      short loc_14002154A
0x140021536  mov     rcx, [rcx+18h]
0x14002153a  mov     edx, 0Ch
0x14002153f  mov     r9, rbx
0x140021542  mov     r8, r13
0x140021545  call    WPP_SF_q
0x14002154a  cmp     [rbx+2A0h], rdi
0x140021551  jnz     short loc_140021574
0x140021553  mov     rcx, cs:WPP_GLOBAL_Control
0x14002155a  cmp     rcx, r15
0x14002155d  jz      loc_14002168C
0x140021563  cmp     byte ptr [rcx+29h], 4
0x140021567  jb      loc_14002168C
0x14002156d  mov     edx, 0Dh
0x140021572  jmp     short loc_140021510
0x140021574  mov     rcx, cs:WPP_GLOBAL_Control
0x14002157b  cmp     rcx, r15
0x14002157e  jz      short loc_14002159A
0x140021580  cmp     byte ptr [rcx+29h], 4
0x140021584  jb      short loc_14002159A
0x140021586  mov     rcx, [rcx+18h]
0x14002158a  mov     edx, 0Eh
0x14002158f  mov     r9, rbx
0x140021592  mov     r8, r13
0x140021595  call    WPP_SF_q
0x14002159a  mov     edi, 58h ; 'X'
0x14002159f  mov     r8d, 56425355h; Tag
0x1400215a5  mov     edx, edi; NumberOfBytes
0x1400215a7  mov     ecx, 600h; PoolType
0x1400215ac  call    cs:__imp_ExAllocatePoolWithTag
0x1400215b3  nop     dword ptr [rax+rax+00h]
0x1400215b8  mov     rsi, rax
0x1400215bb  test    rax, rax
0x1400215be  jz      loc_14002164E
0x1400215c4  cmp     cs:ExPoolZeroingNativelySupported, 0
0x1400215cb  jnz     short loc_1400215DA
0x1400215cd  mov     r8d, edi; Size
0x1400215d0  xor     edx, edx; Val
0x1400215d2  mov     rcx, rax; void *
0x1400215d5  call    memset
0x1400215da  mov     rdx, rsi
0x1400215dd  mov     [rsi], edi
0x1400215df  mov     rcx, rbp
0x1400215e2  mov     qword ptr [rsi+18h], 0
0x1400215ea  call    SubmitUrbToUsbdSynch
0x1400215ef  mov     edi, eax
0x1400215f1  test    eax, eax
0x1400215f3  jns     short loc_14002160E
0x1400215f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400215fc  cmp     rcx, r15
0x1400215ff  jz      short loc_140021638
0x140021601  cmp     byte ptr [rcx+29h], 4
0x140021605  jb      short loc_140021638
0x140021607  mov     edx, 0Fh
0x14002160c  jmp     short loc_140021625
0x14002160e  mov     rcx, cs:WPP_GLOBAL_Control
0x140021615  cmp     rcx, r15
0x140021618  jz      short loc_140021638
0x14002161a  cmp     byte ptr [rcx+29h], 4
0x14002161e  jb      short loc_140021638
0x140021620  mov     edx, 10h
0x140021625  mov     rcx, [rcx+18h]
0x140021629  mov     r9, rbx
0x14002162c  mov     r8, r13
0x14002162f  mov     [rsp+68h+var_48], eax
0x140021633  call    WPP_SF_qD
0x140021638  mov     edx, 56425355h; Tag
0x14002163d  mov     rcx, rsi; P
0x140021640  call    cs:__imp_ExFreePoolWithTag
0x140021647  nop     dword ptr [rax+rax+00h]
0x14002164c  jmp     short loc_140021681
0x14002164e  mov     edi, 0C000009Ah
0x140021653  mov     rcx, cs:WPP_GLOBAL_Control
0x14002165a  cmp     rcx, r15
0x14002165d  jz      short loc_140021681
0x14002165f  cmp     byte ptr [rcx+29h], 4
0x140021663  jb      short loc_140021681
0x140021665  mov     rcx, [rcx+18h]
0x140021669  mov     edx, 11h
0x14002166e  mov     r9, rbx
0x140021671  mov     [rsp+68h+var_48], 0C000009Ah
0x140021679  mov     r8, r13
0x14002167c  call    WPP_SF_qD
0x140021681  mov     qword ptr [rbx+2A0h], 0
0x14002168c  mov     eax, edi
0x14002168e  add     rsp, 38h
0x140021692  pop     r15
0x140021694  pop     r13
0x140021696  pop     rdi
0x140021697  pop     rsi
0x140021698  pop     rbp
0x140021699  pop     rbx
0x14002169a  retn
```
