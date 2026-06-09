# Smb2ValidateCreate

- ea: `0x14006aee0`
- end: `0x14006b773`
- name: `Smb2ValidateCreate`
- size: `2195`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140073a60`

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
- `0x14006aee0`
- `0x14007d060`

## import_xrefs

- `ntoskrnl!FsRtlRemoveDotsFromPath` at `0x14006b3b2`
- `ntoskrnl!FsRtlRemoveDotsFromPath` at `0x14006b3b2`
- `srvnet!SrvAdminDoesPipeAllowAnonymous` at `0x14006b24b`
- `srvnet!SrvAdminDoesPipeAllowAnonymous` at `0x14006b24b`
- `srvnet!SrvLibAllocatePipeEa_Old` at `0x14006b4be`
- `srvnet!SrvLibAllocatePipeEa_Old` at `0x14006b4be`

## string_xrefs

- `0x14006af6d`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`
- `0x14006afd7`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`
- `0x14006b0ac`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`
- `0x14006b6d3`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`
- `0x14006b72b`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`

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
0x14006aee0  mov     r11, rsp
0x14006aee3  push    rbx
0x14006aee4  push    rbp
0x14006aee5  push    rsi
0x14006aee6  push    rdi
0x14006aee7  push    r12
0x14006aee9  push    r13
0x14006aeeb  push    r14
0x14006aeed  push    r15
0x14006aeef  sub     rsp, 118h
0x14006aef6  mov     rax, cs:__security_cookie
0x14006aefd  xor     rax, rsp
0x14006af00  mov     [rsp+158h+var_50], rax
0x14006af08  mov     rbp, [rcx+130h]
0x14006af0f  xor     r12d, r12d
0x14006af12  mov     rbx, [rcx+230h]
0x14006af19  mov     rsi, rcx
0x14006af1c  mov     [r11-68h], r12d
0x14006af20  mov     r8d, [rbp+24h]
0x14006af24  cmp     r8d, 79h ; 'y'
0x14006af28  jnb     short loc_14006AF88
0x14006af2a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006af31  lea     rax, WPP_GLOBAL_Control
0x14006af38  cmp     rcx, rax
0x14006af3b  jz      short loc_14006AF67
0x14006af3d  test    dword ptr [rcx+2Ch], 100000h
0x14006af44  jz      short loc_14006AF67
0x14006af46  lea     edi, [r12+1]
0x14006af4b  cmp     [rcx+29h], dil
0x14006af4f  jb      short loc_14006AF67
0x14006af51  mov     rcx, [rcx+18h]
0x14006af55  lea     edx, [rdi+30h]
0x14006af58  mov     r9d, r8d
0x14006af5b  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006af62  call    WPP_SF_d
0x14006af67  mov     r9d, 54Bh
0x14006af6d  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14006af74  mov     edx, 0C000000Dh
0x14006af79  mov     rcx, rsi
0x14006af7c  call    _Smb2SetError
0x14006af81  xor     edx, edx
0x14006af83  jmp     loc_14006B744
0x14006af88  mov     rbp, [rbp+18h]
0x14006af8c  mov     eax, 39h ; '9'
0x14006af91  cmp     [rbp+40h], ax
0x14006af95  jz      short loc_14006AFF2
0x14006af97  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006af9e  lea     rax, WPP_GLOBAL_Control
0x14006afa5  mov     edi, 1
0x14006afaa  cmp     rcx, rax
0x14006afad  jz      short loc_14006AFD1
0x14006afaf  test    dword ptr [rcx+2Ch], 100000h
0x14006afb6  jz      short loc_14006AFD1
0x14006afb8  cmp     [rcx+29h], dil
0x14006afbc  jb      short loc_14006AFD1
0x14006afbe  mov     rcx, [rcx+18h]
0x14006afc2  lea     edx, [rdi+31h]
0x14006afc5  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006afcc  call    WPP_SF_
0x14006afd1  mov     r9d, 558h
0x14006afd7  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14006afde  mov     edx, 0C000000Dh
0x14006afe3  mov     rcx, rsi
0x14006afe6  call    _Smb2SetError
0x14006afeb  mov     edx, edi
0x14006afed  jmp     loc_14006B744
0x14006aff2  movzx   ecx, word ptr [rbp+6Ch]
0x14006aff6  mov     edi, 1
0x14006affb  movzx   edx, word ptr [rbp+6Eh]
0x14006afff  lea     r9, [rcx+rdx]
0x14006b003  cmp     r9, rcx
0x14006b006  jb      loc_14006B6EE
0x14006b00c  cmp     r9, r8
0x14006b00f  ja      loc_14006B6EE
0x14006b015  lea     eax, [rcx+rbp]
0x14006b018  test    dil, al
0x14006b01b  jnz     loc_14006B6EE
0x14006b021  cmp     ecx, 78h ; 'x'
0x14006b024  jb      loc_14006B6EE
0x14006b02a  cmp     rdx, 0FFFEh
0x14006b031  ja      loc_14006B696
0x14006b037  test    dil, dl
0x14006b03a  jnz     loc_14006B696
0x14006b040  mov     rax, [rsi+60h]
0x14006b044  xor     r9d, r9d
0x14006b047  mov     rdx, [rbp+28h]
0x14006b04b  mov     r8, rbp
0x14006b04e  mov     byte ptr [rsp+158h+var_130], r12b
0x14006b053  mov     rcx, rsi
0x14006b056  mov     byte ptr [rsp+158h+var_138], dil
0x14006b05b  mov     r13, [rax+1F0h]
0x14006b062  call    Smb2VerifySessionExEx
0x14006b067  mov     r14d, eax
0x14006b06a  test    eax, eax
0x14006b06c  jns     short loc_14006B0C0
0x14006b06e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006b075  lea     rax, WPP_GLOBAL_Control
0x14006b07c  cmp     rcx, rax
0x14006b07f  jz      short loc_14006B0A3
0x14006b081  test    dword ptr [rcx+2Ch], 100000h
0x14006b088  jz      short loc_14006B0A3
0x14006b08a  cmp     [rcx+29h], dil
0x14006b08e  jb      short loc_14006B0A3
0x14006b090  mov     rcx, [rcx+18h]
0x14006b094  lea     edx, [rdi+34h]
0x14006b097  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006b09e  call    WPP_SF_
0x14006b0a3  mov     r9d, 58Ch
0x14006b0a9  mov     edx, r14d
0x14006b0ac  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14006b0b3  mov     rcx, rsi
0x14006b0b6  call    _Smb2SetError
0x14006b0bb  jmp     loc_14006B74C
0x14006b0c0  mov     [rbx+0C8h], r12
0x14006b0c7  lea     r15, [rbx+0C0h]
0x14006b0ce  movzx   eax, word ptr [rbp+6Eh]
0x14006b0d2  mov     [rbx+0C2h], ax
0x14006b0d9  mov     [r15], ax
0x14006b0dd  test    ax, ax
0x14006b0e0  jz      short loc_14006B0F8
0x14006b0e2  mov     rax, [rsi+130h]
0x14006b0e9  movzx   ecx, word ptr [rbp+6Ch]
0x14006b0ed  add     rcx, [rax+18h]
0x14006b0f1  mov     [rbx+0C8h], rcx
0x14006b0f8  mov     edx, [rbp+24h]
0x14006b0fb  mov     r8, rbp
0x14006b0fe  mov     rcx, rsi
0x14006b101  call    Smb2VerifyTreeConnect_Old
0x14006b106  mov     r14d, eax
0x14006b109  test    eax, eax
0x14006b10b  jns     short loc_14006B14F
0x14006b10d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006b114  lea     rax, WPP_GLOBAL_Control
0x14006b11b  cmp     rcx, rax
0x14006b11e  jz      short loc_14006B144
0x14006b120  test    dword ptr [rcx+2Ch], 100000h
0x14006b127  jz      short loc_14006B144
0x14006b129  cmp     [rcx+29h], dil
0x14006b12d  jb      short loc_14006B144
0x14006b12f  mov     rcx, [rcx+18h]
0x14006b133  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006b13a  mov     edx, 36h ; '6'
0x14006b13f  call    WPP_SF_
0x14006b144  mov     r9d, 5ABh
0x14006b14a  jmp     loc_14006B0A9
0x14006b14f  mov     rcx, rsi
0x14006b152  call    Smb2GetClient
0x14006b157  mov     r14d, eax
0x14006b15a  test    eax, eax
0x14006b15c  jns     short loc_14006B1A8
0x14006b15e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006b165  lea     rax, WPP_GLOBAL_Control
0x14006b16c  cmp     rcx, rax
0x14006b16f  jz      short loc_14006B19D
0x14006b171  test    dword ptr [rcx+2Ch], 100000h
0x14006b178  jz      short loc_14006B19D
0x14006b17a  cmp     [rcx+29h], dil
0x14006b17e  jb      short loc_14006B19D
0x14006b180  mov     rcx, [rcx+18h]
0x14006b184  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006b18b  mov     edx, 38h ; '8'
0x14006b190  mov     [rsp+158h+var_138], r14d
0x14006b195  mov     r9, rsi
0x14006b198  call    WPP_SF_qD
0x14006b19d  mov     r9d, 5D9h
0x14006b1a3  jmp     loc_14006B0A9
0x14006b1a8  xor     r14d, r14d
0x14006b1ab  lea     r12, [rbx+0D8h]
0x14006b1b2  mov     [rbx+0D0h], r14
0x14006b1b9  mov     [r12], r14d
0x14006b1bd  mov     [rbx+0E0h], r14
0x14006b1c4  mov     [rbx+0C8h], r14
0x14006b1cb  movzx   eax, word ptr [rbp+6Eh]
0x14006b1cf  mov     [rbx+0C2h], ax
0x14006b1d6  mov     [r15], ax
0x14006b1da  test    ax, ax
0x14006b1dd  jz      short loc_14006B1F5
0x14006b1df  mov     rax, [rsi+130h]
0x14006b1e6  movzx   ecx, word ptr [rbp+6Ch]
0x14006b1ea  add     rcx, [rax+18h]
0x14006b1ee  mov     [rbx+0C8h], rcx
0x14006b1f5  mov     rcx, [rbx+38h]
0x14006b1f9  mov     dl, [rbp+43h]
0x14006b1fc  mov     [rbx+12Eh], dl
0x14006b202  test    dword ptr [rcx+50h], 20000h
0x14006b209  jnz     short loc_14006B22F
0x14006b20b  cmp     dl, 9
0x14006b20e  jnz     short loc_14006B222
0x14006b210  test    dword ptr [rcx+54h], 4000000h
0x14006b217  jz      short loc_14006B226
0x14006b219  mov     [rbx+12Eh], dil
0x14006b220  jmp     short loc_14006B236
0x14006b222  test    dl, dl
0x14006b224  jz      short loc_14006B236
0x14006b226  test    dword ptr [rcx+54h], 1000000h
0x14006b22d  jz      short loc_14006B236
0x14006b22f  mov     [rbx+12Eh], r14b
0x14006b236  mov     rax, [rbx+20h]
0x14006b23a  cmp     [rax+111h], r14b
0x14006b241  jz      short loc_14006B2A2
0x14006b243  cmp     [rcx+4Ch], edi
0x14006b246  jnz     short loc_14006B2A2
0x14006b248  mov     rcx, r15
0x14006b24b  call    cs:__imp_SrvAdminDoesPipeAllowAnonymous
0x14006b252  nop     dword ptr [rax+rax+00h]
0x14006b257  test    al, al
0x14006b259  jnz     short loc_14006B2A2
0x14006b25b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006b262  lea     rax, WPP_GLOBAL_Control
0x14006b269  cmp     rcx, rax
0x14006b26c  jz      short loc_14006B292
0x14006b26e  test    dword ptr [rcx+2Ch], 200000h
0x14006b275  jz      short loc_14006B292
0x14006b277  cmp     [rcx+29h], dil
0x14006b27b  jb      short loc_14006B292
0x14006b27d  mov     rcx, [rcx+18h]
0x14006b281  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006b288  mov     edx, 39h ; '9'
0x14006b28d  call    WPP_SF_
0x14006b292  mov     r9d, 610h
0x14006b298  mov     edx, 0C0000022h
0x14006b29d  jmp     loc_14006B0AC
0x14006b2a2  mov     ecx, [rbp+68h]
0x14006b2a5  test    cl, 8
0x14006b2a8  jz      short loc_14006B2B7
0x14006b2aa  mov     eax, [rbp+58h]
0x14006b2ad  test    al, 4
0x14006b2af  jz      short loc_14006B2B7
0x14006b2b1  and     eax, 0FFFFFFFBh
0x14006b2b4  mov     [rbp+58h], eax
0x14006b2b7  and     ecx, 0FF7FFECFh
0x14006b2bd  mov     [rbp+68h], ecx
0x14006b2c0  mov     al, [rbx+12Eh]
0x14006b2c6  cmp     al, dil
0x14006b2c9  jz      short loc_14006B2D9
0x14006b2cb  sub     al, 8
0x14006b2cd  cmp     al, dil
0x14006b2d0  jbe     short loc_14006B2D9
0x14006b2d2  mov     [rbx+12Eh], r14b
0x14006b2d9  mov     rax, [rbx+38h]
0x14006b2dd  mov     rcx, [rax+60h]
0x14006b2e1  cmp     [rcx+116h], r14b
0x14006b2e8  jz      short loc_14006B337
0x14006b2ea  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006b2f1  lea     rax, WPP_GLOBAL_Control
0x14006b2f8  cmp     rcx, rax
0x14006b2fb  jz      short loc_14006B327
0x14006b2fd  test    dword ptr [rcx+2Ch], 200000h
0x14006b304  jz      short loc_14006B327
0x14006b306  cmp     [rcx+29h], dil
0x14006b30a  jb      short loc_14006B327
0x14006b30c  mov     rcx, [rcx+18h]
0x14006b310  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006b317  mov     edx, 3Ah ; ':'
0x14006b31c  mov     r9d, 0C0000257h
0x14006b322  call    WPP_SF_d
0x14006b327  mov     r9d, 639h
0x14006b32d  mov     edx, 0C0000257h
0x14006b332  jmp     loc_14006B0AC
0x14006b337  test    dword ptr [rbp+10h], 10000000h
0x14006b33e  jz      short loc_14006B3A4
0x14006b340  cmp     [rcx+114h], r14b
0x14006b347  jz      short loc_14006B3A4
0x14006b349  mov     rdx, r15
0x14006b34c  call    Smb2DfsNormalizeName
0x14006b351  mov     r14d, eax
0x14006b354  test    eax, eax
0x14006b356  jns     short loc_14006B3A1
0x14006b358  cmp     eax, 0C0000257h
0x14006b35d  jz      short loc_14006B396
0x14006b35f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006b366  lea     rax, WPP_GLOBAL_Control
0x14006b36d  cmp     rcx, rax
0x14006b370  jz      short loc_14006B396
0x14006b372  test    dword ptr [rcx+2Ch], 200000h
0x14006b379  jz      short loc_14006B396
0x14006b37b  cmp     [rcx+29h], dil
0x14006b37f  jb      short loc_14006B396
0x14006b381  mov     rcx, [rcx+18h]
0x14006b385  lea     r8, WPP_d5ef7076187a3415c3b406ca614154e2_Traceguids
0x14006b38c  mov     edx, 3Bh ; ';'
0x14006b391  call    WPP_SF_
0x14006b396  mov     r9d, 64Dh
0x14006b39c  jmp     loc_14006B0A9
0x14006b3a1  xor     r14d, r14d
0x14006b3a4  movzx   edx, word ptr [r15]; PathLength
0x14006b3a8  mov     r8, r15; NewLength
0x14006b3ab  mov     rcx, [rbx+0C8h]; OriginalString
0x14006b3b2  call    cs:__imp_FsRtlRemoveDotsFromPath
0x14006b3b9  nop     dword ptr [rax+rax+00h]
0x14006b3be  test    eax, eax
0x14006b3c0  jns     short loc_14006B409
0x14006b3c2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006b3c9  lea     rax, WPP_GLOBAL_Control
0x14006b3d0  cmp     rcx, rax
0x14006b3d3  jz      short loc_14006B3F9
0x14006b3d5  test    dword ptr [rcx+2Ch], 200000h
0x14006b3dc  jz      short loc_14006B3F9
0x14006b3de  cmp     [rcx+29h], dil
0x14006b3e2  jb      short loc_14006B3F9
  ... truncated ...
```
