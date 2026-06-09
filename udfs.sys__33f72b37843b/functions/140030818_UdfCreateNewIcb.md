# UdfCreateNewIcb

- ea: `0x140030818`
- end: `0x140030d36`
- name: `UdfCreateNewIcb`
- size: `1310`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, installer_update`

## callers

- `0x140031144`
- `0x1400312c0`

## callees

- `0x140004484`
- `0x1400062c0`
- `0x14000653c`
- `0x140009450`
- `0x14000a870`
- `0x140010b58`
- `0x14001636c`
- `0x140016c88`
- `0x140016cc8`
- `0x140018690`
- `0x14001c080`
- `0x1400300ec`
- `0x140030818`
- `0x14003a0c8`
- `0x14004d45c`

## pseudocode

```c
__int64 __fastcall UdfCreateNewIcb(__int64 a1, __int64 a2, __int64 a3, char a4, unsigned int *a5, _QWORD *a6, int a7)
{
  int v8; // r12d
  __int64 v11; // r15
  unsigned int v12; // r13d
  unsigned int BlockForIcb; // edi
  __int64 UniqueId; // rax
  __int16 v15; // r9
  __int64 v16; // r9
  _WORD *v17; // rsi
  __int64 v18; // r9
  __int16 v19; // r10
  __int16 v20; // ax
  __int64 v21; // rbx
  __int64 v22; // r8
  __int64 v23; // rcx
  char *v24; // rdx
  __int64 v25; // rcx
  __int16 v26; // cx
  char *v27; // rax
  __int64 v28; // rdi
  unsigned int v29; // r12d
  __int16 v30; // r8
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rax
  char *v34; // rcx
  __int64 v35; // rax
  int v36; // r9d
  __int64 v37; // rbx
  __int16 v38; // r8
  unsigned int v39; // edx
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rcx
  int v43; // eax
  __int64 v44; // rcx
  __int64 v46; // [rsp+58h] [rbp-80h]
  _QWORD v47[2]; // [rsp+60h] [rbp-78h] BYREF
  void *v48[2]; // [rsp+70h] [rbp-68h] BYREF
  __int128 v49; // [rsp+80h] [rbp-58h]
  __int64 v50; // [rsp+90h] [rbp-48h]
  unsigned int v52; // [rsp+F8h] [rbp+20h]

  v8 = (unsigned __int8)a3;
  v11 = *(_QWORD *)(a1 + 16);
  v47[1] = v11;
  v12 = (*(_DWORD *)(v11 + 48) >> 26) & 1;
  *(_OWORD *)v48 = 0;
  v49 = 0;
  v50 = 0;
  v47[0] = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
  {
    LOBYTE(a3) = a4 != 0 ? 89 : 78;
    WPP_SF_qDcD(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 1, a3, a2, v8, (_BYTE)a3, a7);
  }
  *(_OWORD *)v48 = 0;
  v49 = 0;
  v50 = 0;
  UdfMarkVolumeOpenAndQueueCloseDpc(a1);
  BlockForIcb = UdfAllocateBlockForIcb(a1, v12);
  v52 = BlockForIcb;
  if ( a4 || (_BYTE)v8 == 13 )
    UniqueId = *(_QWORD *)(*(_QWORD *)(a2 + 136) + 96LL);
  else
    UniqueId = UdfAssignNextUniqueId(a1);
  v46 = UniqueId;
  if ( *(_QWORD *)(v11 + 352) )
  {
    v15 = *(_WORD *)(*(_QWORD *)(v11 + 16) + 90LL);
  }
  else
  {
    v16 = *(_QWORD *)(v11 + 16);
    if ( (*(_DWORD *)(v11 + 48) & 0x4000000) != 0 )
      v15 = *(_WORD *)(v16 + 84);
    else
      v15 = *(_WORD *)(v16 + 92);
  }
  UdfMapMetadataView(a1, (__int64)v48, v11, v15, BlockForIcb, *(_DWORD *)(v11 + 68), 28);
  memset(v48[0], 0, *(unsigned int *)(v11 + 68));
  v17 = v48[0];
  v18 = 266;
  if ( *(_WORD *)(v11 + 2136) != 10 )
    LOWORD(v18) = 261;
  UdfInitializeDescriptorTag(a1, v48[0], BlockForIcb, v18);
  v17[10] = 4;
  v17[12] = 1;
  *((_BYTE *)v17 + 27) = v8;
  v20 = a4 != 0 ? 8195 : 3;
  v17[17] = v20;
  if ( (a7 & 4) != 0 )
  {
    v20 |= 0x400u;
    v17[17] = v20;
  }
  if ( (a7 & 0x20) != 0 )
    v17[17] = v20 | 0x20;
  *((_DWORD *)v17 + 9) = -1;
  *((_DWORD *)v17 + 10) = -1;
  *((_DWORD *)v17 + 11) = 0x7FFF;
  if ( (a7 & 1) != 0 )
  {
    *((_DWORD *)v17 + 11) = 15855;
    if ( (_BYTE)v8 != 4 )
      *((_DWORD *)v17 + 11) = 13741;
  }
  v17[24] = (_BYTE)v8 != 13;
  v47[0] = MEMORY[0xFFFFF78000000014];
  v21 = 36;
  v22 = 36;
  if ( *v17 != v19 )
    v22 = 40;
  UdfConvertNtTimeToUdfTime(1, v47, &v17[v22]);
  if ( *v17 != 261 )
    v21 = 40;
  v23 = 42;
  if ( *v17 != 261 )
    v23 = 46;
  *(_QWORD *)&v17[v23] = *(_QWORD *)&v17[v21];
  *(_DWORD *)&v17[v23 + 4] = *(_DWORD *)&v17[v21 + 4];
  v24 = (char *)(v17 + 40);
  if ( *v17 == 261 )
    v24 = (char *)(v17 + 36);
  v25 = 48;
  if ( *v17 != 261 )
    v25 = 58;
  *(_QWORD *)&v17[v25] = *(_QWORD *)v24;
  *(_DWORD *)&v17[v25 + 4] = *((_DWORD *)v24 + 2);
  if ( *v17 == 266 )
  {
    *((_QWORD *)v17 + 13) = *((_QWORD *)v17 + 10);
    *((_DWORD *)v17 + 28) = *((_DWORD *)v17 + 22);
  }
  else
  {
    UdfCreateFileTimesEa(a1, v17);
  }
  v26 = *v17;
  v27 = (char *)(v17 + 64);
  if ( *v17 == 266 )
    *(_DWORD *)v27 = 1;
  else
    *((_DWORD *)v17 + 27) = 1;
  if ( v26 == 266 )
    *((_QWORD *)v17 + 25) = v46;
  else
    *((_QWORD *)v17 + 20) = v46;
  if ( v26 != 261 )
    v27 = (char *)(v17 + 84);
  *(_OWORD *)v27 = UdfMsRegId;
  *((_OWORD *)v27 + 1) = xmmword_140025350;
  if ( (_BYTE)v8 == 13 || (_BYTE)v8 == 4 )
  {
    v30 = *v17;
    v28 = 86;
    v31 = 86;
    if ( *v17 != 261 )
      v31 = 106;
    v32 = *(unsigned int *)&v17[v31];
    v33 = 84;
    if ( v30 != 261 )
      v33 = 104;
    v34 = (char *)v17 + *(unsigned int *)&v17[v33];
    v35 = 216;
    v36 = 176;
    if ( v30 != 266 )
      v35 = 176;
    v37 = (__int64)&v34[v32 + v35];
    *(_OWORD *)v37 = 0;
    *(_OWORD *)(v37 + 16) = 0;
    *(_QWORD *)(v37 + 30) = 0;
    LOBYTE(v36) = *(_BYTE *)(a2 + 502) == 4;
    v29 = v52;
    UdfInitializeFid(
      a1,
      v35 + v32 + (_DWORD)v34,
      v52,
      v36,
      0,
      a2 + 184,
      *(_DWORD *)(*(_QWORD *)(a2 + 136) + 96LL),
      0,
      0,
      0);
    UdfUpdateChecksumAndCrc(v37, (*(unsigned __int16 *)(v37 + 36) + 41 + *(unsigned __int8 *)(v37 + 19)) & 0xFFFFFFFC);
    v38 = *v17;
    v39 = (*(unsigned __int8 *)(v37 + 19) + *(unsigned __int16 *)(v37 + 36) + 41) & 0xFFFFFFFC;
    if ( *v17 == 266 )
      *((_DWORD *)v17 + 53) = v39;
    else
      *((_DWORD *)v17 + 43) = v39;
    v40 = 86;
    if ( v38 != 261 )
      v40 = 106;
    v41 = *(unsigned int *)&v17[v40];
    *((_QWORD *)v17 + 7) = v41;
    if ( v38 == 266 )
      *((_QWORD *)v17 + 8) = v41;
  }
  else
  {
    v17[17] |= 0x20u;
    v28 = 86;
    v29 = v52;
  }
  v42 = 84;
  if ( *v17 != 261 )
  {
    v28 = 106;
    v42 = 104;
  }
  v43 = 216;
  if ( *v17 != 266 )
    v43 = 176;
  UdfUpdateChecksumAndCrc(v17, (unsigned int)(v43 + *(_DWORD *)&v17[v42] + *(_DWORD *)&v17[v28]));
  UdfSetMetaSectorState(a1, HIDWORD(v49), 1, v48);
  *a5 = v29;
  v44 = 80;
  if ( *v17 != 261 )
    v44 = 100;
  *a6 = *(_QWORD *)&v17[v44];
  if ( (*(_DWORD *)(a1 + 28) & 0x80000) != 0 )
    UdfVmcbNoOpRead(a1, v11, v12, v29, 0);
  return UdfUnpinView(a1, v48);
}

```

## disassembly

```asm
0x140030818  mov     r11, rsp
0x14003081b  mov     [r11+10h], rdx
0x14003081f  mov     [r11+8], rcx
0x140030823  push    rbx
0x140030824  push    rsi
0x140030825  push    rdi
0x140030826  push    r12
0x140030828  push    r13
0x14003082a  push    r14
0x14003082c  push    r15
0x14003082e  sub     rsp, 0A0h
0x140030835  mov     bl, r9b
0x140030838  movzx   r12d, r8b
0x14003083c  mov     rsi, rdx
0x14003083f  mov     r14, rcx
0x140030842  mov     r15, [rcx+10h]
0x140030846  mov     [rsp+0D8h+var_70], r15
0x14003084b  mov     r13d, [r15+30h]
0x14003084f  shr     r13d, 1Ah
0x140030853  mov     edx, 1
0x140030858  and     r13d, edx
0x14003085b  mov     [rsp+0D8h+var_88], r13d
0x140030860  xorps   xmm0, xmm0
0x140030863  xor     eax, eax
0x140030865  movups  xmmword ptr [rsp+0D8h+var_68], xmm0
0x14003086a  movups  xmmword ptr [r11-58h], xmm0
0x14003086f  mov     [r11-48h], rax
0x140030873  mov     [r11-78h], rax
0x140030877  lea     rax, WPP_GLOBAL_Control
0x14003087e  mov     rcx, cs:WPP_GLOBAL_Control
0x140030885  cmp     rcx, rax
0x140030888  jz      short loc_1400308C1
0x14003088a  mov     eax, [rcx+2Ch]
0x14003088d  test    dl, al
0x14003088f  jz      short loc_1400308C1
0x140030891  mov     al, bl
0x140030893  neg     al
0x140030895  sbb     r8b, r8b
0x140030898  and     r8b, 0Bh
0x14003089c  add     r8b, 4Eh ; 'N'
0x1400308a0  mov     eax, [rsp+0D8h+arg_30]
0x1400308a7  mov     [rsp+0D8h+var_A8], eax
0x1400308ab  mov     byte ptr [rsp+0D8h+var_B0], r8b
0x1400308b0  mov     [rsp+0D8h+var_B8], r12d
0x1400308b5  mov     r9, rsi
0x1400308b8  mov     rcx, [rcx+18h]
0x1400308bc  call    WPP_SF_qDcD
0x1400308c1  xorps   xmm0, xmm0
0x1400308c4  xor     eax, eax
0x1400308c6  movups  xmmword ptr [rsp+0D8h+var_68], xmm0
0x1400308cb  movups  [rsp+0D8h+var_58], xmm0
0x1400308d3  mov     [rsp+0D8h+var_48], rax
0x1400308db  mov     rcx, r14
0x1400308de  call    UdfMarkVolumeOpenAndQueueCloseDpc
0x1400308e3  mov     edx, r13d
0x1400308e6  mov     rcx, r14
0x1400308e9  call    UdfAllocateBlockForIcb
0x1400308ee  mov     edi, eax
0x1400308f0  mov     [rsp+0D8h+arg_18], eax
0x1400308f7  test    bl, bl
0x1400308f9  jnz     short loc_14003090B
0x1400308fb  cmp     r12b, 0Dh
0x1400308ff  jz      short loc_14003090B
0x140030901  mov     rcx, r14
0x140030904  call    UdfAssignNextUniqueId
0x140030909  jmp     short loc_140030916
0x14003090b  mov     rax, [rsi+88h]
0x140030912  mov     rax, [rax+60h]
0x140030916  mov     [rsp+0D8h+var_80], rax
0x14003091b  cmp     qword ptr [r15+160h], 0
0x140030923  jz      short loc_140030930
0x140030925  mov     rax, [r15+10h]
0x140030929  movzx   r9d, word ptr [rax+5Ah]
0x14003092e  jmp     short loc_14003094A
0x140030930  mov     r9, [r15+10h]
0x140030934  test    dword ptr [r15+30h], 4000000h
0x14003093c  jz      short loc_140030945
0x14003093e  movzx   r9d, word ptr [r9+54h]
0x140030943  jmp     short loc_14003094A
0x140030945  movzx   r9d, word ptr [r9+5Ch]
0x14003094a  mov     [rsp+0D8h+var_A8], 1Ch
0x140030952  mov     eax, [r15+44h]
0x140030956  mov     dword ptr [rsp+0D8h+var_B0], eax
0x14003095a  mov     [rsp+0D8h+var_B8], edi
0x14003095e  mov     r8, r15
0x140030961  lea     rdx, [rsp+0D8h+var_68]
0x140030966  mov     rcx, r14
0x140030969  call    UdfMapMetadataView
0x14003096e  mov     r8d, [r15+44h]; Size
0x140030972  xor     edx, edx; Val
0x140030974  mov     rcx, [rsp+0D8h+var_68]; void *
0x140030979  call    memset
0x14003097e  mov     rsi, [rsp+0D8h+var_68]
0x140030983  mov     eax, 0Ah
0x140030988  mov     r9d, 10Ah
0x14003098e  lea     r10d, [r9-5]
0x140030992  cmp     ax, [r15+858h]
0x14003099a  cmovnz  r9w, r10w
0x14003099f  mov     r8d, edi
0x1400309a2  mov     rdx, rsi
0x1400309a5  mov     rcx, r14
0x1400309a8  call    UdfInitializeDescriptorTag
0x1400309ad  mov     edx, 4
0x1400309b2  mov     [rsi+14h], dx
0x1400309b6  lea     ecx, [rdx-3]
0x1400309b9  mov     [rsi+18h], cx
0x1400309bd  mov     [rsi+1Bh], r12b
0x1400309c1  neg     bl
0x1400309c3  sbb     ax, ax
0x1400309c6  and     ax, 2000h
0x1400309ca  add     ax, 3
0x1400309ce  mov     [rsi+22h], ax
0x1400309d2  test    byte ptr [rsp+0D8h+arg_30], dl
0x1400309d9  jz      short loc_1400309EA
0x1400309db  mov     ecx, 400h
0x1400309e0  or      ax, cx
0x1400309e3  mov     [rsi+22h], ax
0x1400309e7  lea     ecx, [rdx-3]
0x1400309ea  test    byte ptr [rsp+0D8h+arg_30], 20h
0x1400309f2  jz      short loc_1400309FC
0x1400309f4  or      ax, 20h
0x1400309f8  mov     [rsi+22h], ax
0x1400309fc  or      eax, 0FFFFFFFFh
0x1400309ff  mov     [rsi+24h], eax
0x140030a02  mov     [rsi+28h], eax
0x140030a05  mov     dword ptr [rsi+2Ch], 7FFFh
0x140030a0c  test    byte ptr [rsp+0D8h+arg_30], cl
0x140030a13  jz      short loc_140030A28
0x140030a15  mov     dword ptr [rsi+2Ch], 3DEFh
0x140030a1c  cmp     r12b, dl
0x140030a1f  jz      short loc_140030A28
0x140030a21  mov     dword ptr [rsi+2Ch], 35ADh
0x140030a28  xor     eax, eax
0x140030a2a  cmp     r12b, 0Dh
0x140030a2e  setnz   al
0x140030a31  mov     [rsi+30h], ax
0x140030a35  mov     rax, 0FFFFF78000000014h
0x140030a3f  mov     rax, [rax]
0x140030a42  mov     [rsp+0D8h+var_78], rax
0x140030a47  lea     rdi, [rsi+48h]
0x140030a4b  mov     ebx, 48h ; 'H'
0x140030a50  mov     r8d, ebx
0x140030a53  lea     eax, [rbx+8]
0x140030a56  cmp     [rsi], r10w
0x140030a5a  cmovnz  r8d, eax
0x140030a5e  add     r8, rsi
0x140030a61  lea     rdx, [rsp+0D8h+var_78]
0x140030a66  call    UdfConvertNtTimeToUdfTime
0x140030a6b  mov     r10d, 105h
0x140030a71  cmp     [rsi], r10w
0x140030a75  lea     ecx, [rbx+8]
0x140030a78  cmovnz  ebx, ecx
0x140030a7b  mov     ecx, 54h ; 'T'
0x140030a80  lea     edx, [rcx+8]
0x140030a83  cmovnz  ecx, edx
0x140030a86  movsd   xmm0, qword ptr [rbx+rsi]
0x140030a8b  movsd   qword ptr [rcx+rsi], xmm0
0x140030a90  mov     eax, [rbx+rsi+8]
0x140030a94  mov     [rcx+rsi+8], eax
0x140030a98  lea     rdx, [rsi+50h]
0x140030a9c  cmp     [rsi], r10w
0x140030aa0  cmovz   rdx, rdi
0x140030aa4  mov     ecx, 60h ; '`'
0x140030aa9  lea     r9d, [rcx+14h]
0x140030aad  cmovnz  ecx, r9d
0x140030ab1  movsd   xmm0, qword ptr [rdx]
0x140030ab5  movsd   qword ptr [rcx+rsi], xmm0
0x140030aba  mov     eax, [rdx+8]
0x140030abd  mov     [rcx+rsi+8], eax
0x140030ac1  lea     ebx, [r10+5]
0x140030ac5  cmp     [rsi], bx
0x140030ac8  jz      short loc_140030ADB
0x140030aca  mov     rdx, rsi
0x140030acd  mov     rcx, r14
0x140030ad0  call    UdfCreateFileTimesEa
0x140030ad5  lea     r10d, [rbx-5]
0x140030ad9  jmp     short loc_140030AEB
0x140030adb  movsd   xmm0, qword ptr [rsi+50h]
0x140030ae0  movsd   qword ptr [rsi+68h], xmm0
0x140030ae5  mov     eax, [rsi+58h]
0x140030ae8  mov     [rsi+70h], eax
0x140030aeb  movzx   ecx, word ptr [rsi]
0x140030aee  lea     rax, [rsi+80h]
0x140030af5  cmp     cx, bx
0x140030af8  jnz     short loc_140030B02
0x140030afa  mov     dword ptr [rax], 1
0x140030b00  jmp     short loc_140030B09
0x140030b02  mov     dword ptr [rsi+6Ch], 1
0x140030b09  mov     rdx, [rsp+0D8h+var_80]
0x140030b0e  jnz     short loc_140030B19
0x140030b10  mov     [rsi+0C8h], rdx
0x140030b17  jmp     short loc_140030B20
0x140030b19  mov     [rsi+0A0h], rdx
0x140030b20  cmp     cx, r10w
0x140030b24  jz      short loc_140030B2D
0x140030b26  lea     rax, [rsi+0A8h]
0x140030b2d  movups  xmm0, cs:UdfMsRegId
0x140030b34  movups  xmmword ptr [rax], xmm0
0x140030b37  movups  xmm1, cs:xmmword_140025350
0x140030b3e  movups  xmmword ptr [rax+10h], xmm1
0x140030b42  cmp     r12b, 0Dh
0x140030b46  jz      short loc_140030B68
0x140030b48  cmp     r12b, 4
0x140030b4c  jz      short loc_140030B68
0x140030b4e  or      word ptr [rsi+22h], 20h
0x140030b53  mov     edi, 0ACh
0x140030b58  lea     edx, [rdi+28h]
0x140030b5b  mov     r12d, [rsp+0D8h+arg_18]
0x140030b63  jmp     loc_140030C74
0x140030b68  movzx   r8d, word ptr [rsi]
0x140030b6c  mov     edi, 0ACh
0x140030b71  mov     eax, edi
0x140030b73  lea     ecx, [rdi+28h]
0x140030b76  cmp     r8w, r10w
0x140030b7a  cmovnz  eax, ecx
0x140030b7d  mov     edx, [rax+rsi]
0x140030b80  lea     eax, [rdi-4]
0x140030b83  lea     ecx, [rdi+24h]
0x140030b86  cmovnz  eax, ecx
0x140030b89  mov     ecx, [rax+rsi]
0x140030b8c  add     rcx, rsi
0x140030b8f  lea     eax, [rdi+2Ch]
0x140030b92  lea     r9d, [rdi+4]
0x140030b96  cmp     r8w, bx
0x140030b9a  cmovnz  eax, r9d
0x140030b9e  lea     rbx, [rdx+rcx]
0x140030ba2  add     rbx, rax
0x140030ba5  xorps   xmm0, xmm0
0x140030ba8  xor     eax, eax
0x140030baa  movups  xmmword ptr [rbx], xmm0
0x140030bad  movups  xmmword ptr [rbx+10h], xmm0
0x140030bb1  mov     [rbx+1Eh], rax
0x140030bb5  mov     rdx, [rsp+0D8h+arg_8]
0x140030bbd  mov     rax, [rdx+88h]
0x140030bc4  lea     rcx, [rdx+0B8h]
0x140030bcb  cmp     byte ptr [rdx+1F6h], 4
0x140030bd2  setz    r9b
0x140030bd6  xor     edx, edx
0x140030bd8  mov     [rsp+0D8h+var_90], dl
0x140030bdc  mov     [rsp+0D8h+var_98], rdx
0x140030be1  mov     [rsp+0D8h+var_A0], edx
0x140030be5  mov     eax, [rax+60h]
0x140030be8  mov     [rsp+0D8h+var_A8], eax
0x140030bec  mov     [rsp+0D8h+var_B0], rcx
0x140030bf1  mov     byte ptr [rsp+0D8h+var_B8], dl
0x140030bf5  mov     r12d, [rsp+0D8h+arg_18]
0x140030bfd  mov     r8d, r12d
0x140030c00  mov     rdx, rbx
0x140030c03  mov     rcx, r14
0x140030c06  call    UdfInitializeFid
0x140030c0b  movzx   ecx, word ptr [rbx+24h]
0x140030c0f  movzx   edx, byte ptr [rbx+13h]
0x140030c13  add     ecx, 29h ; ')'
0x140030c16  add     edx, ecx
0x140030c18  and     edx, 0FFFFFFFCh
0x140030c1b  mov     rcx, rbx
0x140030c1e  call    UdfUpdateChecksumAndCrc
0x140030c23  movzx   r8d, word ptr [rsi]
0x140030c27  movzx   ecx, byte ptr [rbx+13h]
0x140030c2b  movzx   edx, word ptr [rbx+24h]
0x140030c2f  add     edx, 29h ; ')'
0x140030c32  add     edx, ecx
0x140030c34  and     edx, 0FFFFFFFCh
0x140030c37  lea     ebx, [rdi+5Eh]
0x140030c3a  cmp     r8w, bx
0x140030c3e  jnz     short loc_140030C48
0x140030c40  mov     [rsi+0D4h], edx
0x140030c46  jmp     short loc_140030C4E
0x140030c48  mov     [rsi+0ACh], edx
0x140030c4e  mov     rax, rdi
0x140030c51  mov     r10d, 105h
0x140030c57  cmp     r8w, r10w
0x140030c5b  lea     edx, [r10-31h]
0x140030c5f  cmovnz  rax, rdx
0x140030c63  mov     ecx, [rax+rsi]
0x140030c66  mov     [rsi+38h], rcx
0x140030c6a  cmp     r8w, bx
0x140030c6e  jnz     short loc_140030C74
0x140030c70  mov     [rsi+40h], rcx
0x140030c74  mov     ecx, 0A8h
0x140030c79  lea     r8d, [rcx+8]
0x140030c7d  lea     r9d, [rcx+28h]
0x140030c81  movzx   eax, word ptr [rsi]
0x140030c84  cmp     ax, r10w
0x140030c88  cmovnz  rdi, rdx
0x140030c8c  cmovnz  ecx, r9d
0x140030c90  mov     edx, [rdi+rsi]
0x140030c93  add     edx, [rcx+rsi]
0x140030c96  cmp     ax, bx
0x140030c99  lea     eax, [r8+28h]
0x140030c9d  cmovnz  eax, r8d
0x140030ca1  add     edx, eax
0x140030ca3  mov     rcx, rsi
0x140030ca6  call    UdfUpdateChecksumAndCrc
0x140030cab  lea     r9, [rsp+0D8h+var_68]
0x140030cb0  mov     r8d, 1
0x140030cb6  mov     edx, dword ptr [rsp+0D8h+var_58+0Ch]
0x140030cbd  mov     rcx, r14
0x140030cc0  call    UdfSetMetaSectorState
0x140030cc5  mov     rax, [rsp+0D8h+arg_20]
  ... truncated ...
```
