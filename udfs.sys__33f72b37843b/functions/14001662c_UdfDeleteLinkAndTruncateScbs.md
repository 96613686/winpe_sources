# UdfDeleteLinkAndTruncateScbs

- ea: `0x14001662c`
- end: `0x1400168d0`
- name: `UdfDeleteLinkAndTruncateScbs`
- size: `676`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x140033548`
- `0x140034450`
- `0x140055060`

## callees

- `0x140005e80`
- `0x14000ca10`
- `0x14000ca54`
- `0x14000cb6c`
- `0x140016478`
- `0x14001662c`
- `0x14001758c`
- `0x1400175d0`
- `0x1400177ac`
- `0x140017ecc`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1400168b0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001dbe4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400168b0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001dbe4`

## pseudocode

```c
void __fastcall UdfDeleteLinkAndTruncateScbs(__int64 a1, __int64 a2, char *a3)
{
  __int16 *v5; // r12
  __int64 v6; // rbx
  __int64 v7; // r13
  bool v8; // r14
  bool v9; // r15
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  char v13; // r15
  __int16 v14; // cx
  char v15; // al
  char v16; // al
  _OWORD v17[2]; // [rsp+38h] [rbp-80h] BYREF
  __int64 v18; // [rsp+58h] [rbp-60h]
  __int64 v19; // [rsp+60h] [rbp-58h]
  __int64 v20; // [rsp+68h] [rbp-50h]
  __int16 *v21; // [rsp+70h] [rbp-48h]

  v5 = *(__int16 **)(a2 + 24);
  v21 = v5;
  v6 = *(_QWORD *)(a2 + 48);
  v19 = v6;
  v7 = *(_QWORD *)(v6 + 136);
  v20 = v7;
  v8 = (*(_BYTE *)(v6 + 212) & 0x10) != 0;
  v9 = *(_WORD *)v6 == 2355;
  memset(v17, 0, sizeof(v17));
  v18 = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
  {
    WPP_SF_q(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      18,
      WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids,
      v6);
  }
  v17[0] = 0;
  UdfDeleteFidForLcb(a1);
  if ( !v8 )
  {
    LOBYTE(v10) = v9;
    UdfUpdateLvidCounts(a1, v10, 0xFFFFFFFFLL);
  }
  UdfUpdateScbTimeStamps(v11, v5, 0);
  if ( v9 )
  {
    UdfPrepareModifyIcbForScb(a1, v12, v17);
    --v5[250];
    UdfFinishModifyIcb(a1, (__int64)v17, 1, v5);
  }
  if ( v8 )
  {
    UdfPrepareModifyIcbForScb(a1, *(_QWORD *)(v7 + 16), v17);
    *(_QWORD *)(*(_QWORD *)&v17[0] + 64LL) -= *(_QWORD *)(v6 + 312);
    UdfFinishModifyIcb(a1, (__int64)v17, 1, *(__int16 **)(v7 + 16));
  }
  --*(_WORD *)(v6 + 500);
  v13 = 1;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 19, WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids);
  }
  v14 = *(_WORD *)(v6 + 500);
  if ( !v14 || *(_DWORD *)(v7 + 48) && (*(_DWORD *)(v6 + 212) & 0x18) == 0 && v14 == 1 )
  {
    UdfAcquireResource(a1, *(_QWORD *)(v6 + 16), 0, 0);
    UdfPurgeAndFreeAllocationForScb(a1, v6);
    if ( !v8 && *(_DWORD *)(v7 + 48) )
      UdfRemoveAlternateDataStreams(a1, v6);
    if ( a3 )
    {
      v15 = *a3;
      if ( v8 )
        v16 = v15 | 2;
      else
        v16 = v15 | 4;
      *a3 = v16;
    }
  }
  else
  {
    UdfPrepareModifyIcbForScb(a1, v6, v17);
    UdfFinishModifyIcb(a1, (__int64)v17, 1, (__int16 *)v6);
    if ( a3 )
      *a3 |= 1u;
    v13 = 0;
  }
  if ( v13 )
    ExReleaseResourceLite(*(PERESOURCE *)(v6 + 16));
}

```

## disassembly

```asm
0x14001662c  mov     [rsp+arg_8], rdx
0x140016631  mov     [rsp+arg_0], rcx
0x140016636  push    rbx
0x140016637  push    rsi
0x140016638  push    rdi
0x140016639  push    r12
0x14001663b  push    r13
0x14001663d  push    r14
0x14001663f  push    r15
0x140016641  sub     rsp, 80h
0x140016648  mov     rdi, r8
0x14001664b  mov     rax, rdx
0x14001664e  mov     rsi, rcx
0x140016651  mov     r12, [rdx+18h]
0x140016655  mov     [rsp+0B8h+var_48], r12
0x14001665a  mov     rbx, [rdx+30h]
0x14001665e  mov     [rsp+0B8h+var_58], rbx
0x140016663  mov     r13, [rbx+88h]
0x14001666a  mov     [rsp+0B8h+var_50], r13
0x14001666f  xor     edx, edx
0x140016671  mov     [rsp+0B8h+var_88], dl
0x140016675  mov     r14b, [rbx+0D4h]
0x14001667c  shr     r14b, 4
0x140016680  and     r14b, 1
0x140016684  mov     [rsp+0B8h+arg_18], r14b
0x14001668c  mov     ecx, 933h
0x140016691  cmp     cx, [rbx]
0x140016694  setz    r15b
0x140016698  mov     [rsp+0B8h+var_84], r15b
0x14001669d  mov     [rsp+0B8h+var_87], dl
0x1400166a1  mov     [rsp+0B8h+var_85], dl
0x1400166a5  mov     [rsp+0B8h+var_86], dl
0x1400166a9  xorps   xmm0, xmm0
0x1400166ac  xor     ecx, ecx
0x1400166ae  movups  [rsp+0B8h+var_80], xmm0
0x1400166b3  movups  [rsp+0B8h+var_70], xmm0
0x1400166b8  mov     [rsp+0B8h+var_60], rcx
0x1400166bd  lea     rdx, WPP_GLOBAL_Control
0x1400166c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400166cb  cmp     rcx, rdx
0x1400166ce  jz      short loc_1400166F9
0x1400166d0  test    dword ptr [rcx+2Ch], 10000000h
0x1400166d7  jz      short loc_1400166F1
0x1400166d9  mov     edx, 12h
0x1400166de  mov     r9, rbx
0x1400166e1  lea     r8, WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids
0x1400166e8  mov     rcx, [rcx+18h]
0x1400166ec  call    WPP_SF_q
0x1400166f1  mov     rax, [rsp+0B8h+arg_8]
0x1400166f9  xorps   xmm0, xmm0
0x1400166fc  movdqu  [rsp+0B8h+var_80], xmm0
0x140016702  xor     r8d, r8d
0x140016705  mov     rdx, rax
0x140016708  mov     rcx, rsi; int
0x14001670b  call    UdfDeleteFidForLcb
0x140016710  mov     [rsp+0B8h+var_87], 1
0x140016715  test    r14b, r14b
0x140016718  jnz     short loc_140016729
0x14001671a  or      r8d, 0FFFFFFFFh
0x14001671e  mov     dl, r15b
0x140016721  mov     rcx, rsi
0x140016724  call    UdfUpdateLvidCounts
0x140016729  xor     r8d, r8d
0x14001672c  mov     rdx, r12
0x14001672f  call    UdfUpdateScbTimeStamps
0x140016734  test    r15b, r15b
0x140016737  jz      short loc_14001676A
0x140016739  lea     r8, [rsp+0B8h+var_80]
0x14001673e  mov     rcx, rsi
0x140016741  call    UdfPrepareModifyIcbForScb
0x140016746  mov     r15d, 0FFFFh
0x14001674c  add     [r12+1F4h], r15w
0x140016755  mov     r9, r12
0x140016758  mov     r8b, 1
0x14001675b  lea     rdx, [rsp+0B8h+var_80]
0x140016760  mov     rcx, rsi
0x140016763  call    UdfFinishModifyIcb
0x140016768  jmp     short loc_140016770
0x14001676a  mov     r15d, 0FFFFh
0x140016770  mov     [rsp+0B8h+var_85], 1
0x140016775  xor     r12d, r12d
0x140016778  test    r14b, r14b
0x14001677b  jz      short loc_1400167B2
0x14001677d  lea     r8, [rsp+0B8h+var_80]
0x140016782  mov     rdx, [r13+10h]
0x140016786  mov     rcx, rsi
0x140016789  call    UdfPrepareModifyIcbForScb
0x14001678e  mov     rcx, qword ptr [rsp+0B8h+var_80]
0x140016793  mov     rax, [rbx+138h]
0x14001679a  sub     [rcx+40h], rax
0x14001679e  mov     r9, [r13+10h]
0x1400167a2  mov     r8b, 1
0x1400167a5  lea     rdx, [rsp+0B8h+var_80]
0x1400167aa  mov     rcx, rsi
0x1400167ad  call    UdfFinishModifyIcb
0x1400167b2  add     [rbx+1F4h], r15w
0x1400167ba  movzx   edx, word ptr [rbx+1F4h]
0x1400167c1  mov     r15d, 1
0x1400167c7  mov     [rsp+0B8h+var_86], r15b
0x1400167cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400167d3  lea     rax, WPP_GLOBAL_Control
0x1400167da  cmp     rcx, rax
0x1400167dd  jz      short loc_1400167FF
0x1400167df  test    dword ptr [rcx+2Ch], 10000000h
0x1400167e6  jz      short loc_1400167FF
0x1400167e8  mov     r9d, edx
0x1400167eb  lea     edx, [r15+12h]
0x1400167ef  lea     r8, WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids
0x1400167f6  mov     rcx, [rcx+18h]
0x1400167fa  call    WPP_SF_d
0x1400167ff  movzx   ecx, word ptr [rbx+1F4h]
0x140016806  cmp     r12w, cx
0x14001680a  jz      short loc_14001684F
0x14001680c  cmp     [r13+30h], r12d
0x140016810  jz      short loc_140016822
0x140016812  mov     eax, [rbx+0D4h]
0x140016818  test    al, 18h
0x14001681a  jnz     short loc_140016822
0x14001681c  cmp     r15w, cx
0x140016820  jz      short loc_14001684F
0x140016822  lea     r8, [rsp+0B8h+var_80]
0x140016827  mov     rdx, rbx
0x14001682a  mov     rcx, rsi
0x14001682d  call    UdfPrepareModifyIcbForScb
0x140016832  mov     r9, rbx
0x140016835  mov     r8b, r15b
0x140016838  lea     rdx, [rsp+0B8h+var_80]
0x14001683d  mov     rcx, rsi
0x140016840  call    UdfFinishModifyIcb
0x140016845  test    rdi, rdi
0x140016848  jz      short loc_1400168A2
0x14001684a  or      [rdi], r15b
0x14001684d  jmp     short loc_1400168A2
0x14001684f  xor     r9d, r9d
0x140016852  xor     r8d, r8d
0x140016855  mov     rdx, [rbx+10h]
0x140016859  mov     rcx, rsi
0x14001685c  call    UdfAcquireResource
0x140016861  mov     [rsp+0B8h+var_88], r15b
0x140016866  mov     [rsp+0B8h+var_87], r12b
0x14001686b  mov     rdx, rbx
0x14001686e  mov     rcx, rsi
0x140016871  call    UdfPurgeAndFreeAllocationForScb
0x140016876  test    r14b, r14b
0x140016879  jnz     short loc_14001688C
0x14001687b  cmp     [r13+30h], r12d
0x14001687f  jz      short loc_14001688C
0x140016881  mov     rdx, rbx
0x140016884  mov     rcx, rsi; int
0x140016887  call    UdfRemoveAlternateDataStreams
0x14001688c  test    rdi, rdi
0x14001688f  jz      short loc_1400168A7
0x140016891  mov     al, [rdi]
0x140016893  test    r14b, r14b
0x140016896  jz      short loc_14001689E
0x140016898  or      al, 2
0x14001689a  mov     [rdi], al
0x14001689c  jmp     short loc_1400168A7
0x14001689e  or      al, 4
0x1400168a0  jmp     short loc_14001689A
0x1400168a2  mov     r15b, [rsp+0B8h+var_88]
0x1400168a7  test    r15b, r15b
0x1400168aa  jz      short loc_1400168BC
0x1400168ac  mov     rcx, [rbx+10h]; Resource
0x1400168b0  call    cs:__imp_ExReleaseResourceLite
0x1400168b7  nop     dword ptr [rax+rax+00h]
0x1400168bc  add     rsp, 80h
0x1400168c3  pop     r15
0x1400168c5  pop     r14
0x1400168c7  pop     r13
0x1400168c9  pop     r12
0x1400168cb  pop     rdi
0x1400168cc  pop     rsi
0x1400168cd  pop     rbx
0x1400168ce  retn
0x14001dbc8  push    rbx
0x14001dbca  push    rbp
0x14001dbcb  push    rsi
0x14001dbcc  push    rdi
0x14001dbcd  sub     rsp, 38h
0x14001dbd1  mov     rbp, rdx
0x14001dbd4  mov     bl, cl
0x14001dbd6  cmp     byte ptr [rbp+30h], 0
0x14001dbda  jz      short loc_14001DBF1
0x14001dbdc  mov     rcx, [rbp+60h]
0x14001dbe0  mov     rcx, [rcx+10h]; Resource
0x14001dbe4  call    cs:__imp_ExReleaseResourceLite
0x14001dbeb  nop     dword ptr [rax+rax+00h]
0x14001dbf0  nop
0x14001dbf1  test    bl, bl
0x14001dbf3  jz      loc_14001DCD3
0x14001dbf9  cmp     byte ptr [rbp+31h], 0
0x14001dbfd  jz      loc_14001DCD3
0x14001dc03  cmp     byte ptr [rbp+32h], 0
0x14001dc07  jz      short loc_14001DC5C
0x14001dc09  mov     rsi, [rbp+60h]
0x14001dc0d  inc     word ptr [rsi+1F4h]
0x14001dc14  cmp     byte ptr [rbp+0D8h], 0
0x14001dc1b  jz      short loc_14001DC5C
0x14001dc1d  lea     r8, [rbp+38h]
0x14001dc21  mov     rbx, [rbp+68h]
0x14001dc25  mov     rdx, [rbx+10h]
0x14001dc29  mov     rcx, [rbp+0C0h]
0x14001dc30  call    UdfPrepareModifyIcbForScb
0x14001dc35  mov     rdx, [rsi+138h]
0x14001dc3c  mov     rax, [rbp+38h]
0x14001dc40  add     [rax+40h], rdx
0x14001dc44  mov     r9, [rbx+10h]
0x14001dc48  mov     r8b, 1
0x14001dc4b  lea     rdx, [rbp+38h]
0x14001dc4f  mov     rcx, [rbp+0C0h]
0x14001dc56  call    UdfFinishModifyIcb
0x14001dc5b  nop
0x14001dc5c  cmp     byte ptr [rbp+33h], 0
0x14001dc60  jz      short loc_14001DC9D
0x14001dc62  cmp     byte ptr [rbp+34h], 0
0x14001dc66  jz      short loc_14001DC9D
0x14001dc68  lea     r8, [rbp+38h]
0x14001dc6c  mov     rbx, [rbp+70h]
0x14001dc70  mov     rdx, rbx
0x14001dc73  mov     rcx, [rbp+0C0h]
0x14001dc7a  call    UdfPrepareModifyIcbForScb
0x14001dc7f  inc     word ptr [rbx+1F4h]
0x14001dc86  mov     r9, rbx
0x14001dc89  mov     r8b, 1
0x14001dc8c  lea     rdx, [rbp+38h]
0x14001dc90  mov     rcx, [rbp+0C0h]
0x14001dc97  call    UdfFinishModifyIcb
0x14001dc9c  nop
0x14001dc9d  cmp     byte ptr [rbp+0D8h], 0
0x14001dca4  jnz     short loc_14001DCBC
0x14001dca6  mov     r8d, 1
0x14001dcac  mov     dl, [rbp+34h]
0x14001dcaf  mov     rcx, [rbp+0C0h]
0x14001dcb6  call    UdfUpdateLvidCounts
0x14001dcbb  nop
0x14001dcbc  mov     r8b, 1
0x14001dcbf  mov     rdx, [rbp+0C8h]
0x14001dcc6  mov     rcx, [rbp+0C0h]; int
0x14001dccd  call    UdfDeleteFidForLcb
0x14001dcd2  nop
0x14001dcd3  add     rsp, 38h
0x14001dcd7  pop     rdi
0x14001dcd8  pop     rsi
0x14001dcd9  pop     rbp
0x14001dcda  pop     rbx
0x14001dcdb  retn
```
