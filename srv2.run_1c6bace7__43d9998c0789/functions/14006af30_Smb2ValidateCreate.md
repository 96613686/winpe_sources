# Smb2ValidateCreate

- ea: `0x14006af30`
- end: `0x14006b7c3`
- name: `Smb2ValidateCreate`
- size: `2195`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140073ab0`

## callees

- `0x140007400`
- `0x1400151b0`
- `0x14001cef0`
- `0x14001d6e4`
- `0x14001ddb8`
- `0x14002019c`
- `0x1400222ec`
- `0x1400224b8`
- `0x140022958`
- `0x140038490`
- `0x14005c600`
- `0x140066068`
- `0x14006af30`
- `0x14007d0b0`

## import_xrefs

- `ntoskrnl!FsRtlRemoveDotsFromPath` at `0x14006b402`
- `ntoskrnl!FsRtlRemoveDotsFromPath` at `0x14006b402`
- `srvnet!SrvAdminDoesPipeAllowAnonymous` at `0x14006b29b`
- `srvnet!SrvAdminDoesPipeAllowAnonymous` at `0x14006b29b`
- `srvnet!SrvLibAllocatePipeEa_Old` at `0x14006b50e`
- `srvnet!SrvLibAllocatePipeEa_Old` at `0x14006b50e`

## string_xrefs

- `0x14006afbd`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`
- `0x14006b027`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`
- `0x14006b0fc`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`
- `0x14006b723`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`
- `0x14006b77b`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`

## pseudocode

```c
__int64 __fastcall Smb2ValidateCreate(_QWORD *a1)
{
  __int64 v1; // rbp
  __int64 v2; // rbx
  unsigned __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rbp
  unsigned __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r13
  int Client; // r14d
  __int64 v11; // r9
  __int64 v12; // rdx
  USHORT *v13; // r15
  __int16 v14; // ax
  USHORT v15; // ax
  _DWORD *v16; // rcx
  char v17; // dl
  int v18; // ecx
  int v19; // eax
  char v20; // al
  __int64 v21; // rcx
  int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  __int64 PipeEa_Old; // rax
  int v26; // edi
  __int64 v27; // rcx
  __int64 *v28; // r10
  __int64 v29; // rax
  __int64 *v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // r11
  __int64 v35; // [rsp+D0h] [rbp-88h]
  int v36; // [rsp+F0h] [rbp-68h] BYREF
  __int128 v37; // [rsp+F8h] [rbp-60h] BYREF

  v1 = a1[38];
  v2 = a1[70];
  v36 = 0;
  v4 = *(unsigned int *)(v1 + 36);
  if ( (unsigned int)v4 < 0x79 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          49,
          WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids,
          (unsigned int)v4);
    }
    Smb2SetError(a1, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\create.c", 1355);
    v5 = 0;
LABEL_122:
    Smb2LkmdTelCollectParsingFailureCreateHelper(v2, v5);
    return 0;
  }
  v6 = *(_QWORD *)(v1 + 24);
  if ( *(_WORD *)(v6 + 64) != 57 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
    }
    Smb2SetError(a1, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\create.c", 1368);
    v5 = 1;
    goto LABEL_122;
  }
  v7 = *(unsigned __int16 *)(v6 + 108);
  v8 = *(unsigned __int16 *)(v6 + 110);
  if ( v7 + v8 < v7 || v7 + v8 > v4 || (((_BYTE)v7 + (_BYTE)v6) & 1) != 0 || (unsigned int)v7 < 0x78 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
    }
    Smb2SetError(a1, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\create.c", 1392);
    v5 = 2;
    goto LABEL_122;
  }
  if ( *(unsigned __int16 *)(v6 + 110) == 0xFFFF || (v8 & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
    }
    Smb2SetError(a1, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\create.c", 1408);
    v5 = 3;
    goto LABEL_122;
  }
  v9 = *(_QWORD *)(a1[12] + 496LL);
  Client = Smb2VerifySessionExEx((_DWORD)a1, *(_QWORD *)(v6 + 40), v6, 0, 1, 0);
  if ( Client < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
    }
    v11 = 1420;
LABEL_25:
    v12 = (unsigned int)Client;
LABEL_26:
    Smb2SetError(a1, v12, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\create.c", v11);
    return 0;
  }
  *(_QWORD *)(v2 + 200) = 0;
  v13 = (USHORT *)(v2 + 192);
  v14 = *(_WORD *)(v6 + 110);
  *(_WORD *)(v2 + 194) = v14;
  *(_WORD *)(v2 + 192) = v14;
  if ( v14 )
    *(_QWORD *)(v2 + 200) = *(_QWORD *)(a1[38] + 24LL) + *(unsigned __int16 *)(v6 + 108);
  Client = Smb2VerifyTreeConnect_Old(a1, *(unsigned int *)(v6 + 36), v6);
  if ( Client < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
    }
    v11 = 1451;
    goto LABEL_25;
  }
  Client = Smb2GetClient(a1);
  if ( Client < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1, Client);
    }
    v11 = 1497;
    goto LABEL_25;
  }
  *(_QWORD *)(v2 + 208) = 0;
  *(_DWORD *)(v2 + 216) = 0;
  *(_QWORD *)(v2 + 224) = 0;
  *(_QWORD *)(v2 + 200) = 0;
  v15 = *(_WORD *)(v6 + 110);
  *(_WORD *)(v2 + 194) = v15;
  *v13 = v15;
  if ( v15 )
    *(_QWORD *)(v2 + 200) = *(_QWORD *)(a1[38] + 24LL) + *(unsigned __int16 *)(v6 + 108);
  v16 = *(_DWORD **)(v2 + 56);
  v17 = *(_BYTE *)(v6 + 67);
  *(_BYTE *)(v2 + 302) = v17;
  if ( (v16[20] & 0x20000) != 0 )
    goto LABEL_49;
  if ( v17 != 9 )
  {
    if ( !v17 )
      goto LABEL_50;
    goto LABEL_48;
  }
  if ( (v16[21] & 0x4000000) == 0 )
  {
LABEL_48:
    if ( (v16[21] & 0x1000000) == 0 )
      goto LABEL_50;
LABEL_49:
    *(_BYTE *)(v2 + 302) = 0;
    goto LABEL_50;
  }
  *(_BYTE *)(v2 + 302) = 1;
LABEL_50:
  if ( *(_BYTE *)(*(_QWORD *)(v2 + 32) + 273LL)
    && v16[19] == 1
    && !(unsigned __int8)SrvAdminDoesPipeAllowAnonymous(v2 + 192) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
    }
    v11 = 1552;
    v12 = 3221225506LL;
    goto LABEL_26;
  }
  v18 = *(_DWORD *)(v6 + 104);
  if ( (v18 & 8) != 0 )
  {
    v19 = *(_DWORD *)(v6 + 88);
    if ( (v19 & 4) != 0 )
      *(_DWORD *)(v6 + 88) = v19 & 0xFFFFFFFB;
  }
  *(_DWORD *)(v6 + 104) = v18 & 0xFF7FFECF;
  v20 = *(_BYTE *)(v2 + 302);
  if ( v20 != 1 && (unsigned __int8)(v20 - 8) > 1u )
    *(_BYTE *)(v2 + 302) = 0;
  v21 = *(_QWORD *)(*(_QWORD *)(v2 + 56) + 96LL);
  if ( *(_BYTE *)(v21 + 278) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, 3221226071LL);
    }
    v11 = 1593;
    v12 = 3221226071LL;
    goto LABEL_26;
  }
  if ( (*(_DWORD *)(v6 + 16) & 0x10000000) != 0 )
  {
    if ( *(_BYTE *)(v21 + 276) )
    {
      v22 = Smb2DfsNormalizeName(v21, v2 + 192);
      Client = v22;
      if ( v22 < 0 )
      {
        if ( v22 != -1073741225
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
        }
        v11 = 1613;
        goto LABEL_25;
      }
    }
  }
  if ( FsRtlRemoveDotsFromPath(*(PWSTR *)(v2 + 200), *v13, (USHORT *)(v2 + 192)) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids);
    }
    v11 = 1625;
    v12 = 3221225485LL;
    goto LABEL_26;
  }
  v23 = Smb2ValidateCreateContexts(a1, &v36);
  if ( v23 < 0 )
  {
    v11 = 1632;
    v12 = (unsigned int)v23;
    goto LABEL_26;
  }
  if ( (*(_BYTE *)(v9 + 49) & 4) != 0 )
  {
    v24 = *(_QWORD *)(v2 + 56);
    if ( (*(_DWORD *)(v24 + 80) & 0x4000) != 0 && !*(_DWORD *)(v24 + 76) )
    {
      *(_DWORD *)(v6 + 104) |= 2u;
      if ( !*(_BYTE *)(v2 + 379) && !*(_BYTE *)(v2 + 378) )
      {
        *(_BYTE *)(v2 + 382) = 1;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids, a1);
        }
      }
    }
  }
  if ( *(_DWORD *)(*(_QWORD *)(v2 + 56) + 76LL) == 1 )
  {
    PipeEa_Old = SrvLibAllocatePipeEa_Old(
                   a1[12] + 360LL,
                   *(_QWORD *)(*(_QWORD *)(v2 + 32) + 64LL),
                   *(unsigned int *)(v6 + 32),
                   v2 + 216);
    *(_QWORD *)(v2 + 208) = PipeEa_Old;
    if ( !PipeEa_Old )
    {
      v11 = 1679;
      v12 = 3221225626LL;
      goto LABEL_26;
    }
    *(_BYTE *)(v2 + 303) = 1;
  }
  *(_DWORD *)(v2 + 332) = *(_DWORD *)(v6 + 104);
  if ( (Microsoft_Windows_SMBServerEnableBits & 1) != 0 )
  {
    LOBYTE(v26) = 0;
    v37 = 0;
    if ( *(_BYTE *)(v2 + 306) )
    {
      v26 = *(_DWORD *)(v2 + 264);
      v37 = *(_OWORD *)(v2 + 248);
    }
    v27 = a1[70];
    v28 = &Srv2ZeroGuid;
    v29 = *(_QWORD *)(v27 + 56);
    v30 = (__int64 *)(v29 + 24);
    if ( !v29 )
      v30 = &Srv2ZeroGuid;
    v31 = *(_QWORD *)(v27 + 32);
    if ( v31 )
      v28 = (__int64 *)(v31 + 72);
    v32 = a1[52];
    if ( v32 )
      v33 = *(_QWORD *)(*(_QWORD *)(v32 + 560) + 176LL);
    else
      LOBYTE(v33) = -1;
    v35 = *(_QWORD *)(a1[12] + 496LL) + 72LL;
    McTemplateK0xqqxxhhquuqxxdddddhzr18qjqjjj_EtwWriteTransfer(
      v35,
      *(_WORD *)(v6 + 110) >> 1,
      (_DWORD)a1 + 584,
      *(_QWORD *)(v6 + 40),
      *(_DWORD *)(v6 + 32),
      *(_DWORD *)(v6 + 36),
      *(_QWORD *)(v6 + 24),
      v33,
      *(_WORD *)(v6 + 12),
      *(_WORD *)(v6 + 14),
      *(_DWORD *)(v6 + 16),
      *(_BYTE *)(v6 + 66),
      *(_BYTE *)(v6 + 67),
      *(_DWORD *)(v6 + 68),
      *(_QWORD *)(v6 + 72),
      *(_QWORD *)(v6 + 80),
      *(_DWORD *)(v6 + 88),
      *(_DWORD *)(v6 + 92),
      *(_DWORD *)(v6 + 96),
      *(_DWORD *)(v6 + 100),
      *(_DWORD *)(v6 + 104),
      *(_WORD *)(v6 + 110) >> 1,
      *(_QWORD *)(a1[38] + 24LL) + *(unsigned __int16 *)(v6 + 108),
      v36,
      (__int64)&v37,
      v26,
      v35,
      (__int64)v28,
      (__int64)v30);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x14006af30  mov     r11, rsp
0x14006af33  push    rbx
0x14006af34  push    rbp
0x14006af35  push    rsi
0x14006af36  push    rdi
0x14006af37  push    r12
0x14006af39  push    r13
0x14006af3b  push    r14
0x14006af3d  push    r15
0x14006af3f  sub     rsp, 118h
0x14006af46  mov     rax, cs:__security_cookie
0x14006af4d  xor     rax, rsp
0x14006af50  mov     [rsp+158h+var_50], rax
0x14006af58  mov     rbp, [rcx+130h]
0x14006af5f  xor     r12d, r12d
0x14006af62  mov     rbx, [rcx+230h]
0x14006af69  mov     rsi, rcx
0x14006af6c  mov     [r11-68h], r12d
0x14006af70  mov     r8d, [rbp+24h]
0x14006af74  cmp     r8d, 79h ; 'y'
0x14006af78  jnb     short loc_14006AFD8
0x14006af7a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006af81  lea     rax, WPP_GLOBAL_Control
0x14006af88  cmp     rcx, rax
0x14006af8b  jz      short loc_14006AFB7
0x14006af8d  test    dword ptr [rcx+2Ch], 100000h
0x14006af94  jz      short loc_14006AFB7
0x14006af96  lea     edi, [r12+1]
0x14006af9b  cmp     [rcx+29h], dil
0x14006af9f  jb      short loc_14006AFB7
0x14006afa1  mov     rcx, [rcx+18h]
0x14006afa5  lea     edx, [rdi+30h]
0x14006afa8  mov     r9d, r8d
0x14006afab  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006afb2  call    WPP_SF_d
0x14006afb7  mov     r9d, 54Bh
0x14006afbd  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14006afc4  mov     edx, 0C000000Dh
0x14006afc9  mov     rcx, rsi
0x14006afcc  call    _Smb2SetError
0x14006afd1  xor     edx, edx
0x14006afd3  jmp     loc_14006B794
0x14006afd8  mov     rbp, [rbp+18h]
0x14006afdc  mov     eax, 39h ; '9'
0x14006afe1  cmp     [rbp+40h], ax
0x14006afe5  jz      short loc_14006B042
0x14006afe7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006afee  lea     rax, WPP_GLOBAL_Control
0x14006aff5  mov     edi, 1
0x14006affa  cmp     rcx, rax
0x14006affd  jz      short loc_14006B021
0x14006afff  test    dword ptr [rcx+2Ch], 100000h
0x14006b006  jz      short loc_14006B021
0x14006b008  cmp     [rcx+29h], dil
0x14006b00c  jb      short loc_14006B021
0x14006b00e  mov     rcx, [rcx+18h]
0x14006b012  lea     edx, [rdi+31h]
0x14006b015  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006b01c  call    WPP_SF_
0x14006b021  mov     r9d, 558h
0x14006b027  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14006b02e  mov     edx, 0C000000Dh
0x14006b033  mov     rcx, rsi
0x14006b036  call    _Smb2SetError
0x14006b03b  mov     edx, edi
0x14006b03d  jmp     loc_14006B794
0x14006b042  movzx   ecx, word ptr [rbp+6Ch]
0x14006b046  mov     edi, 1
0x14006b04b  movzx   edx, word ptr [rbp+6Eh]
0x14006b04f  lea     r9, [rcx+rdx]
0x14006b053  cmp     r9, rcx
0x14006b056  jb      loc_14006B73E
0x14006b05c  cmp     r9, r8
0x14006b05f  ja      loc_14006B73E
0x14006b065  lea     eax, [rcx+rbp]
0x14006b068  test    dil, al
0x14006b06b  jnz     loc_14006B73E
0x14006b071  cmp     ecx, 78h ; 'x'
0x14006b074  jb      loc_14006B73E
0x14006b07a  cmp     rdx, 0FFFEh
0x14006b081  ja      loc_14006B6E6
0x14006b087  test    dil, dl
0x14006b08a  jnz     loc_14006B6E6
0x14006b090  mov     rax, [rsi+60h]
0x14006b094  xor     r9d, r9d
0x14006b097  mov     rdx, [rbp+28h]
0x14006b09b  mov     r8, rbp
0x14006b09e  mov     byte ptr [rsp+158h+var_130], r12b
0x14006b0a3  mov     rcx, rsi
0x14006b0a6  mov     byte ptr [rsp+158h+var_138], dil
0x14006b0ab  mov     r13, [rax+1F0h]
0x14006b0b2  call    Smb2VerifySessionExEx
0x14006b0b7  mov     r14d, eax
0x14006b0ba  test    eax, eax
0x14006b0bc  jns     short loc_14006B110
0x14006b0be  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006b0c5  lea     rax, WPP_GLOBAL_Control
0x14006b0cc  cmp     rcx, rax
0x14006b0cf  jz      short loc_14006B0F3
0x14006b0d1  test    dword ptr [rcx+2Ch], 100000h
0x14006b0d8  jz      short loc_14006B0F3
0x14006b0da  cmp     [rcx+29h], dil
0x14006b0de  jb      short loc_14006B0F3
0x14006b0e0  mov     rcx, [rcx+18h]
0x14006b0e4  lea     edx, [rdi+34h]
0x14006b0e7  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006b0ee  call    WPP_SF_
0x14006b0f3  mov     r9d, 58Ch
0x14006b0f9  mov     edx, r14d
0x14006b0fc  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14006b103  mov     rcx, rsi
0x14006b106  call    _Smb2SetError
0x14006b10b  jmp     loc_14006B79C
0x14006b110  mov     [rbx+0C8h], r12
0x14006b117  lea     r15, [rbx+0C0h]
0x14006b11e  movzx   eax, word ptr [rbp+6Eh]
0x14006b122  mov     [rbx+0C2h], ax
0x14006b129  mov     [r15], ax
0x14006b12d  test    ax, ax
0x14006b130  jz      short loc_14006B148
0x14006b132  mov     rax, [rsi+130h]
0x14006b139  movzx   ecx, word ptr [rbp+6Ch]
0x14006b13d  add     rcx, [rax+18h]
0x14006b141  mov     [rbx+0C8h], rcx
0x14006b148  mov     edx, [rbp+24h]
0x14006b14b  mov     r8, rbp
0x14006b14e  mov     rcx, rsi
0x14006b151  call    Smb2VerifyTreeConnect_Old
0x14006b156  mov     r14d, eax
0x14006b159  test    eax, eax
0x14006b15b  jns     short loc_14006B19F
0x14006b15d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006b164  lea     rax, WPP_GLOBAL_Control
0x14006b16b  cmp     rcx, rax
0x14006b16e  jz      short loc_14006B194
0x14006b170  test    dword ptr [rcx+2Ch], 100000h
0x14006b177  jz      short loc_14006B194
0x14006b179  cmp     [rcx+29h], dil
0x14006b17d  jb      short loc_14006B194
0x14006b17f  mov     rcx, [rcx+18h]
0x14006b183  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006b18a  mov     edx, 36h ; '6'
0x14006b18f  call    WPP_SF_
0x14006b194  mov     r9d, 5ABh
0x14006b19a  jmp     loc_14006B0F9
0x14006b19f  mov     rcx, rsi
0x14006b1a2  call    Smb2GetClient
0x14006b1a7  mov     r14d, eax
0x14006b1aa  test    eax, eax
0x14006b1ac  jns     short loc_14006B1F8
0x14006b1ae  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006b1b5  lea     rax, WPP_GLOBAL_Control
0x14006b1bc  cmp     rcx, rax
0x14006b1bf  jz      short loc_14006B1ED
0x14006b1c1  test    dword ptr [rcx+2Ch], 100000h
0x14006b1c8  jz      short loc_14006B1ED
0x14006b1ca  cmp     [rcx+29h], dil
0x14006b1ce  jb      short loc_14006B1ED
0x14006b1d0  mov     rcx, [rcx+18h]
0x14006b1d4  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006b1db  mov     edx, 38h ; '8'
0x14006b1e0  mov     [rsp+158h+var_138], r14d
0x14006b1e5  mov     r9, rsi
0x14006b1e8  call    WPP_SF_qD
0x14006b1ed  mov     r9d, 5D9h
0x14006b1f3  jmp     loc_14006B0F9
0x14006b1f8  xor     r14d, r14d
0x14006b1fb  lea     r12, [rbx+0D8h]
0x14006b202  mov     [rbx+0D0h], r14
0x14006b209  mov     [r12], r14d
0x14006b20d  mov     [rbx+0E0h], r14
0x14006b214  mov     [rbx+0C8h], r14
0x14006b21b  movzx   eax, word ptr [rbp+6Eh]
0x14006b21f  mov     [rbx+0C2h], ax
0x14006b226  mov     [r15], ax
0x14006b22a  test    ax, ax
0x14006b22d  jz      short loc_14006B245
0x14006b22f  mov     rax, [rsi+130h]
0x14006b236  movzx   ecx, word ptr [rbp+6Ch]
0x14006b23a  add     rcx, [rax+18h]
0x14006b23e  mov     [rbx+0C8h], rcx
0x14006b245  mov     rcx, [rbx+38h]
0x14006b249  mov     dl, [rbp+43h]
0x14006b24c  mov     [rbx+12Eh], dl
0x14006b252  test    dword ptr [rcx+50h], 20000h
0x14006b259  jnz     short loc_14006B27F
0x14006b25b  cmp     dl, 9
0x14006b25e  jnz     short loc_14006B272
0x14006b260  test    dword ptr [rcx+54h], 4000000h
0x14006b267  jz      short loc_14006B276
0x14006b269  mov     [rbx+12Eh], dil
0x14006b270  jmp     short loc_14006B286
0x14006b272  test    dl, dl
0x14006b274  jz      short loc_14006B286
0x14006b276  test    dword ptr [rcx+54h], 1000000h
0x14006b27d  jz      short loc_14006B286
0x14006b27f  mov     [rbx+12Eh], r14b
0x14006b286  mov     rax, [rbx+20h]
0x14006b28a  cmp     [rax+111h], r14b
0x14006b291  jz      short loc_14006B2F2
0x14006b293  cmp     [rcx+4Ch], edi
0x14006b296  jnz     short loc_14006B2F2
0x14006b298  mov     rcx, r15
0x14006b29b  call    cs:__imp_SrvAdminDoesPipeAllowAnonymous
0x14006b2a2  nop     dword ptr [rax+rax+00h]
0x14006b2a7  test    al, al
0x14006b2a9  jnz     short loc_14006B2F2
0x14006b2ab  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006b2b2  lea     rax, WPP_GLOBAL_Control
0x14006b2b9  cmp     rcx, rax
0x14006b2bc  jz      short loc_14006B2E2
0x14006b2be  test    dword ptr [rcx+2Ch], 200000h
0x14006b2c5  jz      short loc_14006B2E2
0x14006b2c7  cmp     [rcx+29h], dil
0x14006b2cb  jb      short loc_14006B2E2
0x14006b2cd  mov     rcx, [rcx+18h]
0x14006b2d1  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006b2d8  mov     edx, 39h ; '9'
0x14006b2dd  call    WPP_SF_
0x14006b2e2  mov     r9d, 610h
0x14006b2e8  mov     edx, 0C0000022h
0x14006b2ed  jmp     loc_14006B0FC
0x14006b2f2  mov     ecx, [rbp+68h]
0x14006b2f5  test    cl, 8
0x14006b2f8  jz      short loc_14006B307
0x14006b2fa  mov     eax, [rbp+58h]
0x14006b2fd  test    al, 4
0x14006b2ff  jz      short loc_14006B307
0x14006b301  and     eax, 0FFFFFFFBh
0x14006b304  mov     [rbp+58h], eax
0x14006b307  and     ecx, 0FF7FFECFh
0x14006b30d  mov     [rbp+68h], ecx
0x14006b310  mov     al, [rbx+12Eh]
0x14006b316  cmp     al, dil
0x14006b319  jz      short loc_14006B329
0x14006b31b  sub     al, 8
0x14006b31d  cmp     al, dil
0x14006b320  jbe     short loc_14006B329
0x14006b322  mov     [rbx+12Eh], r14b
0x14006b329  mov     rax, [rbx+38h]
0x14006b32d  mov     rcx, [rax+60h]
0x14006b331  cmp     [rcx+116h], r14b
0x14006b338  jz      short loc_14006B387
0x14006b33a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006b341  lea     rax, WPP_GLOBAL_Control
0x14006b348  cmp     rcx, rax
0x14006b34b  jz      short loc_14006B377
0x14006b34d  test    dword ptr [rcx+2Ch], 200000h
0x14006b354  jz      short loc_14006B377
0x14006b356  cmp     [rcx+29h], dil
0x14006b35a  jb      short loc_14006B377
0x14006b35c  mov     rcx, [rcx+18h]
0x14006b360  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006b367  mov     edx, 3Ah ; ':'
0x14006b36c  mov     r9d, 0C0000257h
0x14006b372  call    WPP_SF_d
0x14006b377  mov     r9d, 639h
0x14006b37d  mov     edx, 0C0000257h
0x14006b382  jmp     loc_14006B0FC
0x14006b387  test    dword ptr [rbp+10h], 10000000h
0x14006b38e  jz      short loc_14006B3F4
0x14006b390  cmp     [rcx+114h], r14b
0x14006b397  jz      short loc_14006B3F4
0x14006b399  mov     rdx, r15
0x14006b39c  call    Smb2DfsNormalizeName
0x14006b3a1  mov     r14d, eax
0x14006b3a4  test    eax, eax
0x14006b3a6  jns     short loc_14006B3F1
0x14006b3a8  cmp     eax, 0C0000257h
0x14006b3ad  jz      short loc_14006B3E6
0x14006b3af  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006b3b6  lea     rax, WPP_GLOBAL_Control
0x14006b3bd  cmp     rcx, rax
0x14006b3c0  jz      short loc_14006B3E6
0x14006b3c2  test    dword ptr [rcx+2Ch], 200000h
0x14006b3c9  jz      short loc_14006B3E6
0x14006b3cb  cmp     [rcx+29h], dil
0x14006b3cf  jb      short loc_14006B3E6
0x14006b3d1  mov     rcx, [rcx+18h]
0x14006b3d5  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006b3dc  mov     edx, 3Bh ; ';'
0x14006b3e1  call    WPP_SF_
0x14006b3e6  mov     r9d, 64Dh
0x14006b3ec  jmp     loc_14006B0F9
0x14006b3f1  xor     r14d, r14d
0x14006b3f4  movzx   edx, word ptr [r15]; PathLength
0x14006b3f8  mov     r8, r15; NewLength
0x14006b3fb  mov     rcx, [rbx+0C8h]; OriginalString
0x14006b402  call    cs:__imp_FsRtlRemoveDotsFromPath
0x14006b409  nop     dword ptr [rax+rax+00h]
0x14006b40e  test    eax, eax
0x14006b410  jns     short loc_14006B459
0x14006b412  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006b419  lea     rax, WPP_GLOBAL_Control
0x14006b420  cmp     rcx, rax
0x14006b423  jz      short loc_14006B449
0x14006b425  test    dword ptr [rcx+2Ch], 200000h
0x14006b42c  jz      short loc_14006B449
0x14006b42e  cmp     [rcx+29h], dil
0x14006b432  jb      short loc_14006B449
  ... truncated ...
```
