# SetSecureCommonPinContext

- ea: `0x140001160`
- end: `0x140001345`
- name: `SetSecureCommonPinContext`
- size: `485`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a928`
- `0x140039650`

## callees

- `0x140001160`
- `0x14000146c`
- `0x14001e1e4`
- `0x140040a30`

## pseudocode

```c
__int64 __fastcall SetSecureCommonPinContext(__int64 *a1)
{
  __int64 v1; // rsi
  int v3; // ecx
  __int64 v4; // rdx
  __int64 v5; // rax
  int v6; // r8d
  int *v7; // rdx
  int v8; // eax
  int v9; // eax
  unsigned int v10; // edi
  const wchar_t *v11; // r8
  __int128 v13; // [rsp+40h] [rbp-9h] BYREF
  __int128 v14; // [rsp+50h] [rbp+7h]
  __int128 v15; // [rsp+60h] [rbp+17h]
  __int64 v16; // [rsp+70h] [rbp+27h]

  v1 = *a1;
  v3 = *((_DWORD *)a1 + 6);
  v16 = 0;
  v13 = 0;
  v4 = a1[52];
  LODWORD(v13) = v3;
  v14 = 0;
  v15 = 0;
  DWORD1(v13) = *(_DWORD *)(v4 + 24);
  if ( v3 )
  {
    if ( v3 == 2 )
    {
      DWORD2(v13) = *(_DWORD *)(136LL * *(unsigned int *)(v4 + 24) + *(_QWORD *)(v1 + 744) + 8);
      goto LABEL_7;
    }
LABEL_6:
    DWORD2(v13) = -1;
    goto LABEL_7;
  }
  v5 = *(_QWORD *)(136LL * *(unsigned int *)(v4 + 24) + *(_QWORD *)(v1 + 744) + 24);
  if ( !v5 )
    goto LABEL_6;
  DWORD2(v13) = *(_DWORD *)(v5 + 24);
LABEL_7:
  v6 = *((_DWORD *)a1 + 100);
  v7 = (int *)(a1 + 51);
  if ( (v6 & 0x20) != 0 || (v8 = *v7, HIDWORD(v13) = 0, (v8 & 0x20) != 0) )
    HIDWORD(v13) = 1;
  LODWORD(v14) = *((unsigned __int8 *)a1 + 386);
  DWORD1(v14) = *((unsigned __int8 *)a1 + 387);
  DWORD2(v14) = *((_DWORD *)a1 + 95);
  DWORD1(v15) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 24) + 16LL) + 1024LL) != 0;
  BYTE12(v14) = *((_BYTE *)a1 + 377);
  LODWORD(v15) = *(_DWORD *)((char *)a1 + 210);
  HIDWORD(v15) = *((_DWORD *)a1 + 10);
  if ( (v6 & 2) != 0 || (v7 = (int *)(a1 + 51), LODWORD(v16) = 0, (a1[51] & 2) != 0) )
    LODWORD(v16) = 1;
  if ( (v6 & 4) != 0 || (v9 = *v7, DWORD2(v15) = 0, (v9 & 4) != 0) )
    DWORD2(v15) = 1;
  v10 = USBVideoCallTrustlet(*(_QWORD *)(v1 + 24), 2228256, (unsigned int)&v13, 56, 0, 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    v11 = L"Video Capture";
    if ( *((_DWORD *)a1 + 6) )
      v11 = L"Still";
    WPP_SF_qDS(
      WPP_GLOBAL_Control->AttachedDevice,
      142,
      (unsigned int)WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
      v1,
      v10,
      (__int64)v11);
  }
  return v10;
}

```

## disassembly

```asm
0x140001160  push    rbp
0x140001162  push    rbx
0x140001163  push    rsi
0x140001164  push    rdi
0x140001165  lea     rbp, [rsp-3Fh]
0x14000116a  sub     rsp, 88h
0x140001171  mov     rax, cs:__security_cookie
0x140001178  xor     rax, rsp
0x14000117b  mov     [rbp+57h+var_28], rax
0x14000117f  mov     rsi, [rcx]
0x140001182  xorps   xmm0, xmm0
0x140001185  xor     eax, eax
0x140001187  mov     rbx, rcx
0x14000118a  mov     ecx, [rcx+18h]
0x14000118d  mov     [rbp+57h+var_30], rax
0x140001191  movups  [rbp+57h+var_60], xmm0
0x140001195  mov     rdx, [rbx+1A0h]
0x14000119c  mov     dword ptr [rbp+57h+var_60], ecx
0x14000119f  movups  [rbp+57h+var_50], xmm0
0x1400011a3  movups  [rbp+57h+var_40], xmm0
0x1400011a7  mov     eax, [rdx+18h]
0x1400011aa  mov     dword ptr [rbp+57h+var_60+4], eax
0x1400011ad  test    ecx, ecx
0x1400011af  jnz     short loc_1400011D4
0x1400011b1  mov     eax, [rdx+18h]
0x1400011b4  imul    rcx, rax, 88h
0x1400011bb  mov     rax, [rsi+2E8h]
0x1400011c2  mov     rax, [rcx+rax+18h]
0x1400011c7  test    rax, rax
0x1400011ca  jz      short loc_1400011F3
0x1400011cc  mov     eax, [rax+18h]
0x1400011cf  mov     dword ptr [rbp+57h+var_60+8], eax
0x1400011d2  jmp     short loc_1400011FA
0x1400011d4  cmp     ecx, 2
0x1400011d7  jnz     short loc_1400011F3
0x1400011d9  mov     eax, [rdx+18h]
0x1400011dc  imul    rcx, rax, 88h
0x1400011e3  mov     rax, [rsi+2E8h]
0x1400011ea  mov     ecx, [rcx+rax+8]
0x1400011ee  mov     dword ptr [rbp+57h+var_60+8], ecx
0x1400011f1  jmp     short loc_1400011FA
0x1400011f3  mov     dword ptr [rbp+57h+var_60+8], 0FFFFFFFFh
0x1400011fa  mov     r8d, [rbx+190h]
0x140001201  lea     rdx, [rbx+198h]
0x140001208  mov     r9d, 1
0x14000120e  test    r8b, 20h
0x140001212  jnz     short loc_140001221
0x140001214  mov     eax, [rdx]
0x140001216  mov     dword ptr [rbp+57h+var_60+0Ch], 0
0x14000121d  test    al, 20h
0x14000121f  jz      short loc_140001225
0x140001221  mov     dword ptr [rbp+57h+var_60+0Ch], r9d
0x140001225  movzx   eax, byte ptr [rbx+182h]
0x14000122c  mov     dword ptr [rbp+57h+var_50], eax
0x14000122f  movzx   eax, byte ptr [rbx+183h]
0x140001236  mov     dword ptr [rbp+57h+var_50+4], eax
0x140001239  mov     eax, [rbx+17Ch]
0x14000123f  mov     dword ptr [rbp+57h+var_50+8], eax
0x140001242  mov     rax, [rsi+18h]
0x140001246  mov     rcx, [rax+10h]
0x14000124a  xor     eax, eax
0x14000124c  cmp     [rcx+400h], rax
0x140001253  setnz   al
0x140001256  mov     dword ptr [rbp+57h+var_40+4], eax
0x140001259  mov     al, [rbx+179h]
0x14000125f  mov     byte ptr [rbp+57h+var_50+0Ch], al
0x140001262  mov     eax, [rbx+0D2h]
0x140001268  mov     dword ptr [rbp+57h+var_40], eax
0x14000126b  mov     eax, [rbx+28h]
0x14000126e  mov     dword ptr [rbp+57h+var_40+0Ch], eax
0x140001271  test    r8b, 2
0x140001275  jnz     short loc_14000128B
0x140001277  lea     rdx, [rbx+198h]
0x14000127e  mov     dword ptr [rbp+57h+var_30], 0
0x140001285  mov     eax, [rdx]
0x140001287  test    al, 2
0x140001289  jz      short loc_14000128F
0x14000128b  mov     dword ptr [rbp+57h+var_30], r9d
0x14000128f  test    r8b, 4
0x140001293  jnz     short loc_1400012A2
0x140001295  mov     eax, [rdx]
0x140001297  mov     dword ptr [rbp+57h+var_40+8], 0
0x14000129e  test    al, 4
0x1400012a0  jz      short loc_1400012A6
0x1400012a2  mov     dword ptr [rbp+57h+var_40+8], r9d
0x1400012a6  mov     rcx, [rsi+18h]
0x1400012aa  lea     r8, [rbp+57h+var_60]
0x1400012ae  mov     [rsp+0A0h+var_70], 0
0x1400012b7  mov     r9d, 38h ; '8'
0x1400012bd  mov     dword ptr [rsp+0A0h+var_78], 0
0x1400012c5  mov     edx, 220020h
0x1400012ca  mov     [rsp+0A0h+var_80], 0
0x1400012d3  call    USBVideoCallTrustlet
0x1400012d8  mov     edi, eax
0x1400012da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400012e1  lea     rax, WPP_GLOBAL_Control
0x1400012e8  cmp     rcx, rax
0x1400012eb  jz      short loc_14000132A
0x1400012ed  cmp     byte ptr [rcx+29h], 5
0x1400012f1  jb      short loc_14000132A
0x1400012f3  cmp     dword ptr [rbx+18h], 0
0x1400012f7  lea     rax, aStill; "Still"
0x1400012fe  mov     rcx, [rcx+18h]
0x140001302  lea     r8, aVideoCapture; "Video Capture"
0x140001309  cmovnz  r8, rax
0x14000130d  mov     edx, 8Eh
0x140001312  mov     [rsp+0A0h+var_78], r8
0x140001317  mov     r9, rsi
0x14000131a  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x140001321  mov     dword ptr [rsp+0A0h+var_80], edi
0x140001325  call    WPP_SF_qDS
0x14000132a  mov     eax, edi
0x14000132c  mov     rcx, [rbp+57h+var_28]
0x140001330  xor     rcx, rsp; StackCookie
0x140001333  call    __security_check_cookie
0x140001338  add     rsp, 88h
0x14000133f  pop     rdi
0x140001340  pop     rsi
0x140001341  pop     rbx
0x140001342  pop     rbp
0x140001343  retn
```
