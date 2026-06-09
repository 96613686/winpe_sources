# Smb2ValidateRead

- ea: `0x1400862e0`
- end: `0x140086e21`
- name: `Smb2ValidateRead`
- size: `2881`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140073ab0`

## callees

- `0x140003bec`
- `0x140007400`
- `0x14001c8ec`
- `0x14001cef0`
- `0x14001d684`
- `0x1400222ec`
- `0x140022958`
- `0x1400229ac`
- `0x14002ad2c`
- `0x140032e3c`
- `0x140032ea4`
- `0x14005c600`
- `0x1400862e0`

## import_xrefs

- `srvnet!SrvNetIsRdmaConnection` at `0x140086646`
- `srvnet!SrvNetIsRdmaConnection` at `0x14008666f`
- `srvnet!SrvNetIsRdmaConnection` at `0x140086646`
- `srvnet!SrvNetIsRdmaConnection` at `0x14008666f`
- `srvnet!SrvNetValidateMrToken` at `0x140086703`
- `srvnet!SrvNetValidateMrToken` at `0x140086703`

## string_xrefs

- `0x140086474`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x140086903`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ac38`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ac63`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ac91`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009acaf`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009accd`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009aced`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ad11`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ad92`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009adb6`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009adda`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009adfe`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ae22`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009ae46`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`
- `0x14009aea0`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\read.c`

## pseudocode

```c
__int64 __fastcall Smb2ValidateRead(ULONG_PTR BugCheckParameter4)
{
  __int64 v1; // rbx
  __int64 v3; // rsi
  unsigned int v4; // r8d
  __int64 v5; // rbx
  __int64 v6; // r15
  int v7; // ebp
  int v8; // ebp
  __int64 v9; // r8
  __int64 v10; // r8
  int v11; // r14d
  char v12; // dl
  char v13; // dl
  __int64 v14; // rax
  int v15; // ecx
  char v16; // cl
  __int64 v17; // r8
  unsigned int v18; // r13d
  unsigned int v19; // r14d
  bool v20; // bp
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v24; // rcx
  unsigned __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // r8d
  __int64 v29; // r8
  int v30; // r9d
  char v31; // dl
  unsigned int v32; // r11d
  unsigned __int64 v33; // rcx
  __int64 v34; // r10
  __int64 v35; // r8
  int v36; // eax
  int v37; // eax
  unsigned int v38; // r8d
  _QWORD *v39; // rax
  __int64 *v40; // r9
  __int64 v41; // rcx
  __int64 *v42; // r11
  __int64 v43; // rcx
  __int64 *v44; // r10
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rdx
  int v48; // ecx
  int v49; // eax
  __int64 v50; // [rsp+98h] [rbp-60h]

  v1 = *(_QWORD *)(BugCheckParameter4 + 304);
  v3 = *(_QWORD *)(BugCheckParameter4 + 560);
  v4 = *(_DWORD *)(v1 + 36);
  if ( v4 < 0x71 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
        BugCheckParameter4,
        v4);
    }
    Smb2SetError(BugCheckParameter4, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c", 319);
    Smb2LkmdTelCollectParsingFailureReadHelper(v3, 0);
    return 0;
  }
  else
  {
    v5 = *(_QWORD *)(v1 + 24);
    if ( *(_WORD *)(v5 + 64) == 49 )
    {
      v6 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL);
      v7 = Smb2VerifySessionExEx(BugCheckParameter4, *(_QWORD *)(v5 + 40), v5, 0, 1, 0);
      if ( v7 >= 0 )
      {
        v8 = Smb2VerifyFileEx(BugCheckParameter4);
        if ( v8 >= 0 )
          goto LABEL_5;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_hq(WPP_GLOBAL_Control->AttachedDevice, 91, v9, *(unsigned __int16 *)(v5 + 12), BugCheckParameter4);
        }
        if ( v8 == -1073741528 )
        {
LABEL_5:
          v11 = Smb2VerifyTreeConnect_Old(BugCheckParameter4, *(unsigned int *)(v5 + 36), v5);
          if ( v11 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_hq(WPP_GLOBAL_Control->AttachedDevice, 92, v10, *(unsigned __int16 *)(v5 + 12), BugCheckParameter4);
            }
            goto LABEL_155;
          }
          if ( v8 == -1073741528 && *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 560) + 56LL) + 154LL) )
            *(_BYTE *)(BugCheckParameter4 + 474) = 1;
        }
        if ( v8 >= 0 )
        {
          v12 = 0;
          if ( *(_DWORD *)(*(_QWORD *)(v3 + 56) + 76LL) == 1 )
            v12 = 4;
          v13 = *(_BYTE *)(v3 + 264) & 0xFB | v12;
          v14 = *(_QWORD *)(v3 + 72);
          *(_BYTE *)(v3 + 264) = v13;
          v15 = *(_DWORD *)(v14 + 224);
          if ( (v15 & 1) == 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                13,
                &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                BugCheckParameter4);
            }
            Smb2SetError(
              BugCheckParameter4,
              3221225506LL,
              "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
              382);
            return 0;
          }
          *(_BYTE *)(v3 + 264) = v13 ^ (v13 ^ (8 * BYTE1(v15))) & 8;
          *(_BYTE *)(v5 + 67) &= *(_BYTE *)(v6 + 48);
          v16 = *(_BYTE *)(v5 + 67) & 1;
          if ( (*(_BYTE *)(v3 + 264) & 4) != 0 )
          {
            if ( v16 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF_q(
                  WPP_GLOBAL_Control->AttachedDevice,
                  14,
                  &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                  BugCheckParameter4);
              }
              Smb2SetError(
                BugCheckParameter4,
                3221225485LL,
                "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                414);
              v22 = 2;
              goto LABEL_17;
            }
          }
          else if ( v16 )
          {
            v17 = *(unsigned int *)(v5 + 68);
            v20 = 1;
            v19 = *(_DWORD *)(v5 + 68);
            v18 = 1;
LABEL_27:
            v26 = *(unsigned __int16 *)(*(_QWORD *)(v3 + 72) + 196LL);
            if ( (_WORD)v26 )
            {
              v27 = *(_QWORD *)(v5 + 72);
              if ( ((v26 - 1) & v27) != 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) )
                {
                  WPP_SF_qid(WPP_GLOBAL_Control->AttachedDevice, v27, v17, BugCheckParameter4, v27, v26);
                }
                Smb2SetError(
                  BugCheckParameter4,
                  3221225485LL,
                  "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                  451);
                return 0;
              }
              if ( (((_DWORD)v26 - 1) & (unsigned int)v17) != 0 )
              {
                v19 = v17 + v26 - 1 - ((int)v17 + (int)v26 - 1) % (unsigned int)v26;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_qDD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    16,
                    &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                    BugCheckParameter4,
                    v17,
                    v19);
                }
              }
            }
LABEL_14:
            v21 = *(unsigned int *)(v6 + 36);
            if ( v19 > (unsigned int)v21 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
              {
                if ( BYTE1(WPP_GLOBAL_Control->Timer) )
                  WPP_SF_qDD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    17,
                    &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                    BugCheckParameter4,
                    v19,
                    v21);
              }
              Smb2SetError(
                BugCheckParameter4,
                3221225485LL,
                "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                487);
              v22 = 4;
LABEL_17:
              Smb2LkmdTelCollectParsingFailureReadHelper(v3, v22);
              return 0;
            }
            v24 = *(_QWORD *)(v5 + 72);
            if ( v24 < 0 || (v25 = v24 + v19, v25 < v24) || v25 > 0x7FFFFFFFFFFFFFFFLL )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                WPP_SF_qID(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, v21, BugCheckParameter4, v24, v19);
              }
              Smb2SetError(
                BugCheckParameter4,
                3221225485LL,
                "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                512);
              v22 = 5;
              goto LABEL_17;
            }
            if ( (*(_BYTE *)(v6 + 49) & 2) != 0 )
            {
              v37 = *(_DWORD *)(v5 + 68);
              if ( v37 )
                v18 = ((unsigned int)(v37 - 1) >> 16) + 1;
              v38 = *(unsigned __int16 *)(BugCheckParameter4 + 488);
              if ( v38 < v18 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) )
                {
                  WPP_SF_qDD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    19,
                    &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                    BugCheckParameter4,
                    v38,
                    v18);
                }
                Smb2SetError(
                  BugCheckParameter4,
                  3221225485LL,
                  "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                  536);
                v22 = 6;
                goto LABEL_17;
              }
            }
            if ( *(_WORD *)(v6 + 44) < 0x300u )
            {
              *(_DWORD *)(v5 + 100) = 0;
            }
            else
            {
              v28 = *(_DWORD *)(v5 + 100);
              if ( v28 > *(_DWORD *)(v6 + 32) )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) )
                {
                  WPP_SF_qD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    20,
                    &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                    BugCheckParameter4,
                    v28);
                }
                Smb2SetError(
                  BugCheckParameter4,
                  3221225485LL,
                  "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                  556);
                v22 = 7;
                goto LABEL_17;
              }
              if ( v28 - 1 <= 1 )
              {
                if ( !(unsigned __int8)SrvNetIsRdmaConnection(*(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 480LL)) )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_q(
                      WPP_GLOBAL_Control->AttachedDevice,
                      21,
                      &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                      BugCheckParameter4);
                  }
                  Smb2SetError(
                    BugCheckParameter4,
                    3221225485LL,
                    "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                    586);
                  v22 = 8;
                  goto LABEL_17;
                }
                v32 = *(_DWORD *)(v5 + 68);
                if ( !v32 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_q(
                      WPP_GLOBAL_Control->AttachedDevice,
                      22,
                      &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                      BugCheckParameter4);
                  }
                  Smb2SetError(
                    BugCheckParameter4,
                    3221225485LL,
                    "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                    601);
                  v22 = 9;
                  goto LABEL_17;
                }
                v33 = *(unsigned __int16 *)(v5 + 108);
                if ( !(_WORD)v33 || (v34 = *(unsigned __int16 *)(v5 + 110), !(_WORD)v34) )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_q(
                      WPP_GLOBAL_Control->AttachedDevice,
                      23,
                      &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                      BugCheckParameter4);
                  }
                  Smb2SetError(
                    BugCheckParameter4,
                    3221225485LL,
                    "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                    617);
                  v22 = 10;
                  goto LABEL_17;
                }
                v35 = *(unsigned __int16 *)(v5 + 108);
                if ( v33 - 112 > 0x100
                  || (v33 + v34 >= v33
                   && v33 + v34 <= *(unsigned int *)(*(_QWORD *)(BugCheckParameter4 + 304) + 36LL)
                   && (((_BYTE)v5 + (_BYTE)v35) & 7) == 0
                    ? (v36 = 0)
                    : (v36 = -1073741811),
                      v36 < 0) )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_q(
                      WPP_GLOBAL_Control->AttachedDevice,
                      24,
                      &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                      BugCheckParameter4);
                  }
                  Smb2SetError(
                    BugCheckParameter4,
                    3221225485LL,
                    "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                    641);
                  v22 = 11;
                  goto LABEL_17;
                }
                if ( (int)SrvNetValidateMrToken(
                            v35 + v5,
                            *(unsigned __int16 *)(v5 + 110),
                            v32,
                            BugCheckParameter4 + 552) < 0 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) )
                  {
                    WPP_SF_q(
                      WPP_GLOBAL_Control->AttachedDevice,
                      25,
                      &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
                      BugCheckParameter4);
                  }
                  Smb2SetError(
                    BugCheckParameter4,
                    3221225485LL,
                    "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
                    660);
                  v22 = 12;
                  goto LABEL_17;
                }
                v30 = *(unsigned __int16 *)(v5 + 110);
                v29 = v5 + *(unsigned __int16 *)(v5 + 108);
                *(_BYTE *)(BugCheckParameter4 + 556) = *(_DWORD *)(v5 + 100) == 2;
LABEL_36:
                if ( v20 )
                {
                  v31 = *(_BYTE *)(v3 + 264);
                  if ( (v31 & 4) != 0 )
                    goto LABEL_38;
                  v31 |= 2u;
                }
                else
                {
                  v48 = *(_DWORD *)(*(_QWORD *)(v3 + 56) + 84LL);
                  if ( (v48 & 0x4000000) != 0
                    || (v48 & 0x1000000) != 0
                    || (*(_DWORD *)(*(_QWORD *)(v3 + 72) + 224LL) & 0x200) != 0 )
                  {
                    *(_BYTE *)(v3 + 264) |= 0x22u;
                  }
                  v31 = *(_BYTE *)(v3 + 264);
                  v49 = *(_DWORD *)(v3 + 8);
                  if ( v49 != 1 )
                  {
                    if ( !v29 || v49 < 2 || (*(_DWORD *)(*(_QWORD *)(v3 + 32) + 304LL) & 1) == 0 )
                      goto LABEL_38;
                    v31 = *(_BYTE *)(v3 + 264);
                  }
                  v31 |= 0x20u;
                }
                *(_BYTE *)(v3 + 264) = v31;
LABEL_38:
                *(_DWORD *)(v3 + 236) = v19;
                *(_DWORD *)(v3 + 244) = *(_DWORD *)(v5 + 68);
                *(_DWORD *)(v3 + 240) = *(_DWORD *)(v5 + 96);
                *(_QWORD *)(v3 + 192) = *(_QWORD *)(v5 + 72);
                *(_BYTE *)(v3 + 265) = *(_BYTE *)(v5 + 66);
                *(_QWORD *)(v3 + 200) = 0;
                *(_QWORD *)(v3 + 216) = v29;
                *(_DWORD *)(v3 + 232) = v30;
                *(_BYTE *)(v3 + 264) = (16 * v20) | v31 & 0xEF;
                if ( (*(_BYTE *)(v5 + 67) & 2) != 0 && !Smb2CompressionDisabled )
                  *(_DWORD *)(BugCheckParameter4 + 484) |= 0x2000u;
                if ( (Microsoft_Windows_SMBServerEnableBits & 1) != 0 )
                {
                  v39 = *(_QWORD **)(BugCheckParameter4 + 560);
                  v40 = &Srv2ZeroGuid;
                  v41 = v39[9];
                  v42 = (__int64 *)(v41 + 96);
                  if ( !v41 )
                    v42 = &Srv2ZeroGuid;
                  v43 = v39[7];
                  v44 = (__int64 *)(v43 + 24);
                  if ( !v43 )
                    v44 = &Srv2ZeroGuid;
                  v45 = v39[4];
                  if ( v45 )
                    v40 = (__int64 *)(v45 + 72);
                  v46 = *(_QWORD *)(BugCheckParameter4 + 416);
                  if ( v46 )
                    v47 = *(_QWORD *)(*(_QWORD *)(v46 + 560) + 176LL);
                  else
                    LODWORD(v47) = -1;
                  v50 = *(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 496LL) + 72LL;
                  McTemplateK0xqqxxhhqqxxqqqhhjjjj_EtwWriteTransfer(
                    v50,
                    v47,
                    BugCheckParameter4 + 584,
                    *(_QWORD *)(v5 + 40),
                    *(_DWORD *)(v5 + 32),
                    *(_DWORD *)(v5 + 36),
                    *(_QWORD *)(v5 + 24),
                    v47,
                    *(_WORD *)(v5 + 12),
                    *(_WORD *)(v5 + 14),
                    *(_DWORD *)(v5 + 16),
                    *(_DWORD *)(v5 + 68),
                    *(_QWORD *)(v5 + 72),
                    *(_QWORD *)(v5 + 80),
                    *(_DWORD *)(v5 + 96),
                    *(_DWORD *)(v5 + 100),
                    *(_DWORD *)(v5 + 104),
                    *(_WORD *)(v5 + 108),
                    *(_WORD *)(v5 + 110),
                    v50,
                    (__int64)v40,
                    (__int64)v44,
                    (__int64)v42);
                }
                if ( (unsigned __int8)SrvNetIsRdmaConnection(*(_QWORD *)(*(_QWORD *)(BugCheckParameter4 + 96) + 480LL))
                  && (*(_BYTE *)(v3 + 264) & 4) == 0
                  && (*(_DWORD *)(*(_QWORD *)(v3 + 72) + 224LL) & 0x40) == 0 )
                {
                  *(_BYTE *)(v3 + 7) = 1;
                  _InterlockedIncrement((volatile signed __int32 *)(v6 + 196));
                }
                return 3221225494LL;
              }
            }
            v29 = 0;
            v30 = 0;
            goto LABEL_36;
          }
          v17 = *(unsigned int *)(v5 + 68);
          v18 = 1;
          v19 = *(_DWORD *)(v5 + 68);
          v20 = (*(_DWORD *)(*(_QWORD *)(v3 + 88) + 80LL) & 8) != 0;
          if ( (*(_DWORD *)(*(_QWORD *)(v3 + 88) + 80LL) & 8) == 0 )
            goto LABEL_14;
          goto LABEL_27;
        }
        v11 = v8;
LABEL_155:
        Smb2SetError(
          BugCheckParameter4,
          (unsigned int)v11,
          "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
          363);
        return 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
          BugCheckParameter4);
      }
      Smb2SetError(
        BugCheckParameter4,
        (unsigned int)v7,
        "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c",
        350);
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          &WPP_464c4860859737a1da74cf96eb989b6c_Traceguids,
          BugCheckParameter4);
      }
      Smb2SetError(BugCheckParameter4, 3221225485LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\read.c", 335);
      Smb2LkmdTelCollectParsingFailureReadHelper(v3, 1);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1400862e0  mov     rax, rsp
0x1400862e3  push    rbx
0x1400862e4  push    rsi
0x1400862e5  push    rdi
0x1400862e6  push    r12
0x1400862e8  sub     rsp, 0D8h
0x1400862ef  mov     rbx, [rcx+130h]
0x1400862f6  mov     rdi, rcx
0x1400862f9  mov     rsi, [rcx+230h]
0x140086300  mov     r8d, [rbx+24h]
0x140086304  cmp     r8d, 71h ; 'q'
0x140086308  jb      loc_140086971
0x14008630e  mov     rbx, [rbx+18h]
0x140086312  mov     [rax+10h], r13
0x140086316  cmp     word ptr [rbx+40h], 31h ; '1'
0x14008631b  jnz     loc_1400869C2
0x140086321  mov     rdx, [rbx+28h]
0x140086325  xor     r9d, r9d
0x140086328  mov     [rax+8], rbp
0x14008632c  mov     r8, rbx
0x14008632f  mov     [rax-28h], r15
0x140086333  mov     rax, [rcx+60h]
0x140086337  mov     byte ptr [rsp+0F8h+var_D0], 0
0x14008633c  mov     byte ptr [rsp+0F8h+var_D8], 1
0x140086341  mov     r15, [rax+1F0h]
0x140086348  call    Smb2VerifySessionExEx
0x14008634d  mov     ebp, eax
0x14008634f  test    eax, eax
0x140086351  js      loc_140086A0E
0x140086357  movups  xmm0, xmmword ptr [rbx+50h]
0x14008635b  mov     r9b, 3
0x14008635e  mov     [rsp+0F8h+arg_10], r14
0x140086366  mov     r8, rbx
0x140086369  lea     rdx, [rsp+0F8h+var_38]
0x140086371  mov     rcx, rdi; BugCheckParameter4
0x140086374  movaps  [rsp+0F8h+var_38], xmm0
0x14008637c  call    Smb2VerifyFileEx
0x140086381  lea     r12, WPP_GLOBAL_Control
0x140086388  mov     ebp, eax
0x14008638a  test    eax, eax
0x14008638c  js      loc_140086A5A
0x140086392  mov     edx, [rbx+24h]
0x140086395  mov     r8, rbx
0x140086398  mov     rcx, rdi
0x14008639b  call    Smb2VerifyTreeConnect_Old
0x1400863a0  mov     r14d, eax
0x1400863a3  test    eax, eax
0x1400863a5  js      loc_140086A9E
0x1400863ab  cmp     ebp, 0C0000128h
0x1400863b1  jz      loc_140086AE3
0x1400863b7  test    ebp, ebp
0x1400863b9  js      loc_140086B07
0x1400863bf  mov     rax, [rsi+38h]
0x1400863c3  xor     edx, edx
0x1400863c5  mov     ecx, 4
0x1400863ca  cmp     dword ptr [rax+4Ch], 1
0x1400863ce  movzx   eax, byte ptr [rsi+108h]
0x1400863d5  cmovz   edx, ecx
0x1400863d8  and     al, 0FBh
0x1400863da  or      dl, al
0x1400863dc  mov     rax, [rsi+48h]
0x1400863e0  mov     [rsi+108h], dl
0x1400863e6  mov     ecx, [rax+0E0h]
0x1400863ec  test    cl, 1
0x1400863ef  jz      loc_140086B0F
0x1400863f5  shr     ecx, 8
0x1400863f8  shl     cl, 3
0x1400863fb  xor     cl, dl
0x1400863fd  and     cl, 8
0x140086400  xor     cl, dl
0x140086402  mov     [rsi+108h], cl
0x140086408  movzx   eax, byte ptr [r15+30h]
0x14008640d  and     [rbx+43h], al
0x140086410  movzx   ecx, byte ptr [rbx+43h]
0x140086414  and     cl, 1
0x140086417  test    byte ptr [rsi+108h], 4
0x14008641e  jnz     loc_140086B54
0x140086424  test    cl, cl
0x140086426  jnz     loc_14008652F
0x14008642c  mov     rax, [rsi+58h]
0x140086430  xor     dl, dl
0x140086432  mov     r8d, [rbx+44h]
0x140086436  mov     r13d, 1
0x14008643c  movzx   ebp, dl
0x14008643f  mov     r14d, r8d
0x140086442  mov     ecx, [rax+50h]
0x140086445  test    cl, 8
0x140086448  cmovnz  ebp, r13d
0x14008644c  test    bpl, bpl
0x14008644f  jnz     loc_14008653F
0x140086455  mov     r8d, [r15+24h]
0x140086459  cmp     r14d, r8d
0x14008645c  jbe     short loc_1400864C5
0x14008645e  mov     rcx, cs:WPP_GLOBAL_Control
0x140086465  cmp     rcx, r12
0x140086468  jnz     loc_140086BE4
0x14008646e  mov     r9d, 1E7h
0x140086474  lea     r8, aOnecoreBaseFsR_9; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14008647b  mov     edx, 0C000000Dh
0x140086480  mov     rcx, rdi
0x140086483  call    _Smb2SetError
0x140086488  mov     edx, 4
0x14008648d  mov     rcx, rsi
0x140086490  call    Smb2LkmdTelCollectParsingFailureReadHelper
0x140086495  xor     eax, eax
0x140086497  mov     r14, [rsp+0F8h+arg_10]
0x14008649f  mov     rbp, [rsp+0F8h+arg_0]
0x1400864a7  mov     r15, [rsp+0F8h+var_28]
0x1400864af  mov     r13, [rsp+0F8h+arg_8]
0x1400864b7  add     rsp, 0D8h
0x1400864be  pop     r12
0x1400864c0  pop     rdi
0x1400864c1  pop     rsi
0x1400864c2  pop     rbx
0x1400864c3  retn
0x1400864c5  mov     rcx, [rbx+48h]
0x1400864c9  test    rcx, rcx
0x1400864cc  js      short loc_1400864EC
0x1400864ce  mov     edx, r14d
0x1400864d1  add     rdx, rcx
0x1400864d4  cmp     rdx, rcx
0x1400864d7  jb      short loc_1400864EC
0x1400864d9  mov     rax, 7FFFFFFFFFFFFFFFh
0x1400864e3  cmp     rdx, rax
0x1400864e6  jbe     loc_140086578
0x1400864ec  mov     rdx, cs:WPP_GLOBAL_Control
0x1400864f3  cmp     rdx, r12
0x1400864f6  jz      loc_14009AE9A
0x1400864fc  test    dword ptr [rdx+2Ch], 800000h
0x140086503  jz      loc_14009AE9A
0x140086509  cmp     byte ptr [rdx+29h], 1
0x14008650d  jb      loc_14009AE9A
0x140086513  mov     [rsp+0F8h+var_D0], r14d
0x140086518  mov     r9, rdi
0x14008651b  mov     [rsp+0F8h+var_D8], rcx
0x140086520  mov     rcx, [rdx+18h]
0x140086524  call    WPP_SF_qID
0x140086529  nop
0x14008652a  jmp     loc_14009AE9A
0x14008652f  mov     r8d, [rbx+44h]
0x140086533  mov     bpl, 1
0x140086536  mov     r14d, r8d
0x140086539  mov     r13d, 1
0x14008653f  mov     rax, [rsi+48h]
0x140086543  movzx   ecx, word ptr [rax+0C4h]
0x14008654a  test    cx, cx
0x14008654d  jz      loc_140086455
0x140086553  mov     rdx, [rbx+48h]
0x140086557  lea     rax, [rcx-1]
0x14008655b  mov     r9d, ecx
0x14008655e  test    rdx, rax
0x140086561  jnz     loc_140086BA1
0x140086567  lea     eax, [rcx-1]
0x14008656a  test    r8d, eax
0x14008656d  jz      loc_140086455
0x140086573  jmp     loc_14009AD2B
0x140086578  test    byte ptr [r15+31h], 2
0x14008657d  jnz     loc_140086736
0x140086583  mov     eax, 300h
0x140086588  cmp     [r15+2Ch], ax
0x14008658d  jb      loc_140086DB4
0x140086593  mov     r8d, [rbx+64h]
0x140086597  cmp     r8d, [r15+20h]
0x14008659b  ja      loc_140086C22
0x1400865a1  lea     eax, [r8-1]
0x1400865a5  cmp     eax, 1
0x1400865a8  jbe     loc_140086664
0x1400865ae  xor     r8d, r8d
0x1400865b1  xor     r9d, r9d
0x1400865b4  test    bpl, bpl
0x1400865b7  jz      loc_140086DC8
0x1400865bd  movzx   edx, byte ptr [rsi+108h]
0x1400865c4  test    dl, 4
0x1400865c7  jz      loc_140086DC0
0x1400865cd  mov     [rsi+0ECh], r14d
0x1400865d4  and     dl, 0EFh
0x1400865d7  mov     eax, [rbx+44h]
0x1400865da  mov     [rsi+0F4h], eax
0x1400865e0  mov     eax, [rbx+60h]
0x1400865e3  mov     [rsi+0F0h], eax
0x1400865e9  mov     rax, [rbx+48h]
0x1400865ed  shl     bpl, 4
0x1400865f1  mov     [rsi+0C0h], rax
0x1400865f8  or      dl, bpl
0x1400865fb  movzx   eax, byte ptr [rbx+42h]
0x1400865ff  mov     [rsi+109h], al
0x140086605  mov     qword ptr [rsi+0C8h], 0
0x140086610  mov     [rsi+0D8h], r8
0x140086617  mov     [rsi+0E8h], r9d
0x14008661e  mov     [rsi+108h], dl
0x140086624  test    byte ptr [rbx+43h], 2
0x140086628  jnz     loc_140086DFC
0x14008662e  test    cs:Microsoft_Windows_SMBServerEnableBits, 1
0x140086635  jnz     loc_1400867D9
0x14008663b  mov     rcx, [rdi+60h]
0x14008663f  mov     rcx, [rcx+1E0h]
0x140086646  call    cs:__imp_SrvNetIsRdmaConnection
0x14008664d  nop     dword ptr [rax+rax+00h]
0x140086652  test    al, al
0x140086654  jnz     loc_1400867A8
0x14008665a  mov     eax, 0C0000016h
0x14008665f  jmp     loc_140086497
0x140086664  mov     rcx, [rdi+60h]
0x140086668  mov     rcx, [rcx+1E0h]
0x14008666f  call    cs:__imp_SrvNetIsRdmaConnection
0x140086676  nop     dword ptr [rax+rax+00h]
0x14008667b  test    al, al
0x14008667d  jz      loc_140086C6C
0x140086683  mov     r11d, [rbx+44h]
0x140086687  test    r11d, r11d
0x14008668a  jz      loc_1400868ED
0x140086690  movzx   ecx, word ptr [rbx+6Ch]
0x140086694  xor     eax, eax
0x140086696  cmp     ax, cx
0x140086699  jz      loc_140086D6F
0x14008669f  movzx   r10d, word ptr [rbx+6Eh]
0x1400866a4  cmp     ax, r10w
0x1400866a8  jz      loc_140086D6F
0x1400866ae  lea     rax, [rcx-70h]
0x1400866b2  mov     r8d, ecx
0x1400866b5  cmp     rax, 100h
0x1400866bb  ja      loc_140086D2A
0x1400866c1  lea     rdx, [rcx+r10]
0x1400866c5  cmp     rdx, rcx
0x1400866c8  jb      short loc_1400866E5
0x1400866ca  mov     rax, [rdi+130h]
0x1400866d1  mov     ecx, [rax+24h]
0x1400866d4  cmp     rdx, rcx
0x1400866d7  ja      short loc_1400866E5
0x1400866d9  lea     eax, [rbx+r8]
0x1400866dd  test    al, 7
0x1400866df  jz      loc_140086921
0x1400866e5  mov     eax, 0C000000Dh
0x1400866ea  test    eax, eax
0x1400866ec  js      loc_140086D2A
0x1400866f2  lea     rcx, [r8+rbx]
0x1400866f6  mov     edx, r10d
0x1400866f9  mov     r8d, r11d
0x1400866fc  lea     r9, [rdi+228h]
0x140086703  call    cs:__imp_SrvNetValidateMrToken
0x14008670a  nop     dword ptr [rax+rax+00h]
0x14008670f  test    eax, eax
0x140086711  js      loc_140086CE5
0x140086717  movzx   r8d, word ptr [rbx+6Ch]
0x14008671c  movzx   r9d, word ptr [rbx+6Eh]
0x140086721  add     r8, rbx
0x140086724  cmp     dword ptr [rbx+64h], 2
0x140086728  setz    al
0x14008672b  mov     [rdi+22Ch], al
0x140086731  jmp     loc_1400865B4
0x140086736  mov     eax, [rbx+44h]
0x140086739  test    eax, eax
0x14008673b  jz      short loc_140086748
0x14008673d  lea     r13d, [rax-1]
0x140086741  shr     r13d, 10h
0x140086745  inc     r13d
0x140086748  movzx   r8d, word ptr [rdi+1E8h]
0x140086750  cmp     r8d, r13d
0x140086753  jnb     loc_140086583
0x140086759  mov     rcx, cs:WPP_GLOBAL_Control
0x140086760  cmp     rcx, r12
0x140086763  jz      loc_14009AD8C
0x140086769  test    dword ptr [rcx+2Ch], 800000h
0x140086770  jz      loc_14009AD8C
0x140086776  cmp     byte ptr [rcx+29h], 1
0x14008677a  jb      loc_14009AD8C
0x140086780  mov     rcx, [rcx+18h]
0x140086784  mov     edx, 13h
0x140086789  mov     [rsp+0F8h+var_D0], r13d
0x14008678e  mov     r9, rdi
0x140086791  mov     dword ptr [rsp+0F8h+var_D8], r8d
0x140086796  lea     r8, WPP_464c4860859737a1da74cf96eb989b6c_Traceguids
0x14008679d  call    WPP_SF_qDD
0x1400867a2  nop
0x1400867a3  jmp     loc_14009AD8C
0x1400867a8  test    byte ptr [rsi+108h], 4
0x1400867af  jnz     loc_14008665A
0x1400867b5  mov     rax, [rsi+48h]
0x1400867b9  mov     ecx, [rax+0E0h]
0x1400867bf  test    cl, 40h
0x1400867c2  jnz     loc_14008665A
0x1400867c8  mov     byte ptr [rsi+7], 1
0x1400867cc  lock inc dword ptr [r15+0C4h]
0x1400867d4  jmp     loc_14008665A
0x1400867d9  mov     rax, [rdi+230h]
0x1400867e0  lea     r9, Srv2ZeroGuid
0x1400867e7  mov     rcx, [rax+48h]
0x1400867eb  lea     r11, [rcx+60h]
0x1400867ef  test    rcx, rcx
0x1400867f2  jnz     short loc_1400867F7
0x1400867f4  mov     r11, r9
0x1400867f7  mov     rcx, [rax+38h]
0x1400867fb  lea     r10, [rcx+18h]
0x1400867ff  test    rcx, rcx
0x140086802  jnz     short loc_140086807
0x140086804  mov     r10, r9
0x140086807  mov     rcx, [rax+20h]
0x14008680b  test    rcx, rcx
0x14008680e  jnz     loc_140086E18
0x140086814  mov     rax, [rdi+1A0h]
  ... truncated ...
```
