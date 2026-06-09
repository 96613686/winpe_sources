# WcmSetParameterTraceLogging(_GUID const *,ulong,ulong,ulong,uchar const *)

- ea: `0x1800031e0`
- end: `0x180003c21`
- name: `?WcmSetParameterTraceLogging@@YAXPEBU_GUID@@KKKPEBE@Z`
- size: `2625`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned int, unsigned int, const unsigned __int8 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e00`
- `0x180013990`

## callees

- `0x1800031e0`
- `0x180008a90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180003bfc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180003bfc`

## pseudocode

```c
void __fastcall WcmSetParameterTraceLogging(
        const struct _GUID *a1,
        unsigned int a2,
        int a3,
        unsigned int a4,
        const unsigned __int8 *a5)
{
  unsigned int v6; // r9d
  char *v7; // rax
  EVENT_DESCRIPTOR *p_EventDescriptor; // rdx
  char *v9; // rax
  unsigned int v10; // r9d
  unsigned int v11; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v12; // [rsp+34h] [rbp-CCh] BYREF
  int v13; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v14; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v16; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v17; // [rsp+4Ah] [rbp-B6h] BYREF
  unsigned int v18; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v19; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v20; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v21; // [rsp+58h] [rbp-A8h] BYREF
  int v22; // [rsp+5Ch] [rbp-A4h] BYREF
  int v23; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+64h] [rbp-9Ch] BYREF
  int v25; // [rsp+68h] [rbp-98h] BYREF
  int v26; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h] BYREF
  EVENT_DESCRIPTOR v29; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-70h] BYREF
  __int16 *v31; // [rsp+A0h] [rbp-60h]
  int v32; // [rsp+A8h] [rbp-58h]
  int v33; // [rsp+ACh] [rbp-54h]
  const struct _GUID *v34; // [rsp+B0h] [rbp-50h]
  __int64 v35; // [rsp+B8h] [rbp-48h]
  const struct _GUID *v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  __int64 *v38; // [rsp+D0h] [rbp-30h]
  __int64 v39; // [rsp+D8h] [rbp-28h]
  __int64 *v40; // [rsp+E0h] [rbp-20h]
  __int64 v41; // [rsp+E8h] [rbp-18h]
  int *v42; // [rsp+F0h] [rbp-10h]
  __int64 v43; // [rsp+F8h] [rbp-8h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+100h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v45; // [rsp+110h] [rbp+10h] BYREF
  char *v46; // [rsp+120h] [rbp+20h]
  int v47; // [rsp+128h] [rbp+28h]
  int v48; // [rsp+12Ch] [rbp+2Ch]
  unsigned int *v49; // [rsp+130h] [rbp+30h]
  __int64 v50; // [rsp+138h] [rbp+38h]
  const struct _GUID *v51; // [rsp+140h] [rbp+40h]
  __int64 v52; // [rsp+148h] [rbp+48h]
  unsigned int *v53; // [rsp+150h] [rbp+50h]
  __int64 v54; // [rsp+158h] [rbp+58h]
  EVENT_DESCRIPTOR *v55; // [rsp+160h] [rbp+60h]
  __int64 v56; // [rsp+168h] [rbp+68h]
  unsigned int *v57; // [rsp+170h] [rbp+70h]
  __int64 v58; // [rsp+178h] [rbp+78h]
  int *v59; // [rsp+180h] [rbp+80h]
  __int64 v60; // [rsp+188h] [rbp+88h]
  int *v61; // [rsp+190h] [rbp+90h]
  __int64 v62; // [rsp+198h] [rbp+98h]
  __int64 *v63; // [rsp+1A0h] [rbp+A0h]
  __int64 v64; // [rsp+1A8h] [rbp+A8h]
  int *v65; // [rsp+1B0h] [rbp+B0h]
  __int64 v66; // [rsp+1B8h] [rbp+B8h]
  unsigned int *v67; // [rsp+1C0h] [rbp+C0h]
  __int64 v68; // [rsp+1C8h] [rbp+C8h]
  unsigned int *v69; // [rsp+1D0h] [rbp+D0h]
  __int64 v70; // [rsp+1D8h] [rbp+D8h]
  unsigned int *v71; // [rsp+1E0h] [rbp+E0h]
  __int64 v72; // [rsp+1E8h] [rbp+E8h]
  unsigned int *v73; // [rsp+1F0h] [rbp+F0h]
  __int64 v74; // [rsp+1F8h] [rbp+F8h]
  __int16 *v75; // [rsp+200h] [rbp+100h]
  __int64 v76; // [rsp+208h] [rbp+108h]
  __int16 *v77; // [rsp+210h] [rbp+110h]
  __int64 v78; // [rsp+218h] [rbp+118h]
  int *v79; // [rsp+220h] [rbp+120h]
  __int64 v80; // [rsp+228h] [rbp+128h]
  int *v81; // [rsp+230h] [rbp+130h]
  __int64 v82; // [rsp+238h] [rbp+138h]
  int *v83; // [rsp+240h] [rbp+140h]
  __int64 v84; // [rsp+248h] [rbp+148h]
  __int64 *v85; // [rsp+250h] [rbp+150h]
  __int64 v86; // [rsp+258h] [rbp+158h]

  if ( a2 > 0x106 )
  {
    switch ( a2 )
    {
      case 0x120u:
        goto LABEL_41;
      case 0x123u:
        if ( a1 && a5 && a4 == 4 )
        {
          v10 = *(_DWORD *)a5;
          if ( (unsigned int)dword_18002A000 <= 5
            || (qword_18002A010 & 0x400000000000LL) == 0
            || (qword_18002A018 & 0x400000000000LL) != qword_18002A018 )
          {
            return;
          }
          v15 = 2048;
          v40 = &v15;
          v38 = (__int64 *)&v13;
          v36 = (const struct _GUID *)&v12;
          UserData.Ptr = (ULONGLONG)off_18002A008;
          v13 = a3;
          v12 = v10;
          v41 = 8;
          v39 = 4;
          v37 = 4;
          v34 = a1;
          v35 = 16;
          *(_QWORD *)&v29.Id = 0x50B000000LL;
          v29.Keyword = 0x400000000000LL;
          UserData.Size = *(unsigned __int16 *)off_18002A008;
          v7 = &byte_180024EDF;
          v32 = 69;
          goto LABEL_24;
        }
        if ( (unsigned int)dword_18002A000 <= 5
          || (qword_18002A010 & 0x400000000000LL) == 0
          || (qword_18002A018 & 0x400000000000LL) != qword_18002A018 )
        {
          return;
        }
        v15 = 2048;
        v38 = &v15;
        v36 = (const struct _GUID *)&v13;
        v34 = (const struct _GUID *)&v12;
        UserData.Ptr = (ULONGLONG)off_18002A008;
        v13 = a3;
        v12 = a4;
        v39 = 8;
        v37 = 4;
        v35 = 4;
        *(_QWORD *)&v29.Id = 0x50B000000LL;
        v29.Keyword = 0x400000000000LL;
        UserData.Size = *(unsigned __int16 *)off_18002A008;
        v9 = byte_180024E95;
        v32 = 62;
        break;
      case 0x124u:
        if ( a1 && a5 && a4 == 4 )
        {
          v6 = *(_DWORD *)a5;
          if ( (unsigned int)dword_18002A000 <= 5
            || (qword_18002A010 & 0x400000000000LL) == 0
            || (qword_18002A018 & 0x400000000000LL) != qword_18002A018 )
          {
            return;
          }
          v15 = 2048;
          v40 = &v15;
          v38 = (__int64 *)&v13;
          v36 = (const struct _GUID *)&v12;
          UserData.Ptr = (ULONGLONG)off_18002A008;
          v13 = a3;
          v12 = v6;
          v41 = 8;
          v39 = 4;
          v37 = 4;
          v34 = a1;
          v35 = 16;
          *(_QWORD *)&v29.Id = 0x50B000000LL;
          v29.Keyword = 0x400000000000LL;
          UserData.Size = *(unsigned __int16 *)off_18002A008;
          v7 = byte_180024E25;
          v32 = 100;
LABEL_24:
          v31 = (__int16 *)v7;
          UserData.Reserved = 2;
          v33 = 1;
          v11 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          p_EventDescriptor = &v29;
          goto LABEL_52;
        }
        if ( (unsigned int)dword_18002A000 <= 5
          || (qword_18002A010 & 0x400000000000LL) == 0
          || (qword_18002A018 & 0x400000000000LL) != qword_18002A018 )
        {
          return;
        }
        v15 = 2048;
        v38 = &v15;
        v36 = (const struct _GUID *)&v13;
        v34 = (const struct _GUID *)&v12;
        UserData.Ptr = (ULONGLONG)off_18002A008;
        v13 = a3;
        v12 = a4;
        v39 = 8;
        v37 = 4;
        v35 = 4;
        *(_QWORD *)&v29.Id = 0x50B000000LL;
        v29.Keyword = 0x400000000000LL;
        UserData.Size = *(unsigned __int16 *)off_18002A008;
        v9 = byte_180024DCD;
        v32 = 76;
        break;
      default:
        return;
    }
    v31 = (__int16 *)v9;
    UserData.Reserved = 2;
    v33 = 1;
    v11 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    goto LABEL_13;
  }
  if ( a2 != 262 )
  {
    if ( a2 == 4 )
    {
LABEL_6:
      if ( a1 && a5 && a4 == 8 )
      {
        if ( (unsigned int)dword_18002A000 > 5 )
        {
          v12 = *((_DWORD *)a5 + 1);
          v11 = *(_DWORD *)a5;
          v42 = &v13;
          v40 = (__int64 *)&v12;
          v38 = (__int64 *)&v11;
          v34 = (const struct _GUID *)&v14;
          UserData.Ptr = (ULONGLONG)off_18002A008;
          v29.Keyword = 0;
          v13 = a3;
          v14 = a2;
          v43 = 4;
          v41 = 4;
          v39 = 4;
          v36 = a1;
          v37 = 16;
          v35 = 4;
          *(_QWORD *)&v29.Id = 0x50B000000LL;
          UserData.Size = *(unsigned __int16 *)off_18002A008;
          v31 = (__int16 *)&byte_180025187;
          UserData.Reserved = 2;
          v32 = 79;
          v33 = 1;
          v18 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &v29, 0, 0, 7u, &UserData);
        }
        return;
      }
      if ( (unsigned int)dword_18002A000 <= 5 )
        return;
      v13 = a3;
      v29.Keyword = 0;
      v38 = (__int64 *)&v13;
      v12 = a4;
      v36 = (const struct _GUID *)&v12;
      v34 = (const struct _GUID *)&v11;
      UserData.Ptr = (ULONGLONG)off_18002A008;
      v11 = a2;
      v39 = 4;
      v37 = 4;
      v35 = 4;
      *(_QWORD *)&v29.Id = 0x50B000000LL;
      UserData.Size = *(unsigned __int16 *)off_18002A008;
      v31 = word_180025142;
      UserData.Reserved = 2;
      v32 = 57;
      v33 = 1;
      v14 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
LABEL_13:
      EventWriteTransfer(RegHandle, &v29, 0, 0, 5u, &UserData);
      return;
    }
    if ( a2 != 5 )
    {
      if ( a2 - 260 > 1 )
        return;
      goto LABEL_6;
    }
  }
LABEL_41:
  if ( !a1 || !a5 || a4 != 60 )
  {
    if ( (unsigned int)dword_18002A000 <= 5
      || (qword_18002A010 & 0x400000000000LL) == 0
      || (qword_18002A018 & 0x400000000000LL) != qword_18002A018 )
    {
      return;
    }
    EventDescriptor.Keyword = 0x400000000000LL;
    v40 = (__int64 *)&v29;
    *(_QWORD *)&v29.Id = 2048;
    v38 = &v15;
    p_EventDescriptor = &EventDescriptor;
    LODWORD(v15) = a3;
    v36 = (const struct _GUID *)&v21;
    v34 = (const struct _GUID *)&v20;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18002A008;
    v21 = a4;
    v20 = a2;
    v41 = 8;
    v39 = 4;
    v37 = 4;
    v35 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)off_18002A008;
    v31 = (__int16 *)&unk_180024F30;
    UserData.Reserved = 2;
    v32 = 73;
    v33 = 1;
    v19 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
LABEL_52:
    EventWriteTransfer(RegHandle, p_EventDescriptor, 0, 0, 6u, &UserData);
    return;
  }
  if ( (unsigned int)dword_18002A000 > 5
    && (qword_18002A010 & 0x400000000000LL) != 0
    && (qword_18002A018 & 0x400000000000LL) == qword_18002A018 )
  {
    v23 = *((_DWORD *)a5 + 13);
    v24 = *((_DWORD *)a5 + 12);
    v16 = *((_WORD *)a5 + 22);
    v17 = *((_WORD *)a5 + 21);
    LOWORD(v18) = *((_WORD *)a5 + 20);
    LOWORD(v14) = *((_WORD *)a5 + 19);
    LOWORD(v11) = *((_WORD *)a5 + 18);
    LOWORD(v12) = *((_WORD *)a5 + 17);
    LOWORD(v13) = *((_WORD *)a5 + 16);
    v28 = *((_QWORD *)a5 + 3);
    v25 = *((_DWORD *)a5 + 5);
    v26 = *((_DWORD *)a5 + 4);
    v19 = *((_DWORD *)a5 + 3);
    *(_QWORD *)&v29.Id = *(_QWORD *)(a5 + 4);
    v20 = *(_DWORD *)a5;
    v85 = &v27;
    v83 = &v22;
    v81 = &v23;
    v79 = &v24;
    v77 = &v16;
    v75 = &v17;
    v73 = &v18;
    v71 = &v14;
    v69 = &v11;
    v67 = &v12;
    v65 = &v13;
    v63 = &v28;
    v61 = &v25;
    v59 = &v26;
    v57 = &v19;
    v55 = &v29;
    v27 = 2048;
    v22 = a3;
    v21 = a2;
    v86 = 8;
    v84 = 4;
    v82 = 4;
    v80 = 4;
    v78 = 2;
    v76 = 2;
    v74 = 2;
    v72 = 2;
    v70 = 2;
    v68 = 2;
    v66 = 2;
    v64 = 8;
    v62 = 4;
    v60 = 4;
    v58 = 4;
    v56 = 8;
    EventDescriptor.Keyword = 0x400000000000LL;
    v53 = &v20;
    v54 = 4;
    v49 = &v21;
    *(_DWORD *)&EventDescriptor.Level = 5;
    v45.Ptr = (ULONGLONG)off_18002A008;
    v51 = a1;
    v52 = 16;
    v50 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    v45.Size = *(unsigned __int16 *)off_18002A008;
    v46 = byte_180024F85;
    v45.Reserved = 2;
    v47 = 433;
    v48 = 1;
    LODWORD(v15) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0x15u, &v45);
  }
}

```

## disassembly

```asm
0x1800031e0  push    rbp
0x1800031e2  lea     rbp, [rsp-170h]
0x1800031ea  sub     rsp, 270h
0x1800031f1  mov     rax, cs:__security_cookie
0x1800031f8  xor     rax, rsp
0x1800031fb  mov     [rbp+170h+var_10], rax
0x180003202  mov     r11d, edx
0x180003205  mov     r10, rcx
0x180003208  cmp     edx, 106h
0x18000320e  ja      loc_180003418
0x180003214  jz      loc_1800037EC
0x18000321a  mov     eax, edx
0x18000321c  sub     eax, 4
0x18000321f  jz      short loc_18000323A
0x180003221  sub     eax, 1
0x180003224  jz      loc_1800037EC
0x18000322a  sub     eax, 0FFh
0x18000322f  jz      short loc_18000323A
0x180003231  cmp     eax, 1
0x180003234  jnz     loc_180003C08
0x18000323a  test    r10, r10
0x18000323d  jz      loc_18000334D
0x180003243  mov     rcx, [rbp+170h+arg_20]
0x18000324a  test    rcx, rcx
0x18000324d  jz      loc_18000334D
0x180003253  cmp     r9d, 8
0x180003257  jnz     loc_18000334D
0x18000325d  mov     eax, cs:dword_18002A000
0x180003263  cmp     eax, 5
0x180003266  jbe     loc_180003C08
0x18000326c  mov     eax, [rcx+4]
0x18000326f  lea     rdx, [rbp+170h+var_1F0]
0x180003273  mov     [rsp+270h+var_23C], eax
0x180003277  mov     eax, [rcx]
0x180003279  xor     ecx, ecx
0x18000327b  mov     [rsp+270h+var_240], eax
0x18000327f  lea     rax, [rsp+270h+var_238]
0x180003284  mov     [rbp+170h+var_180], rax
0x180003288  lea     rax, [rsp+270h+var_23C]
0x18000328d  mov     [rbp+170h+var_190], rax
0x180003291  lea     rax, [rsp+270h+var_240]
0x180003296  mov     [rbp+170h+var_1A0], rax
0x18000329a  lea     rax, [rsp+270h+var_234]
0x18000329f  mov     [rbp+170h+var_1C0], rax
0x1800032a3  movzx   eax, cs:word_18002517D
0x1800032aa  mov     dword ptr [rbp+170h+var_1F0+4], eax
0x1800032ad  mov     rax, cs:off_18002A008
0x1800032b4  mov     [rbp+170h+var_1E0.Ptr], rax
0x1800032b8  mov     [rbp+170h+var_1E8], rcx
0x1800032bc  lea     rcx, _TraceLoggingMetadata
0x1800032c3  mov     [rsp+270h+var_238], r8d
0x1800032c8  mov     [rsp+270h+var_234], r11d
0x1800032cd  mov     [rbp+170h+var_178], 4
0x1800032d5  mov     [rbp+170h+var_188], 4
0x1800032dd  mov     [rbp+170h+var_198], 4
0x1800032e5  mov     [rbp+170h+var_1B0], r10
0x1800032e9  mov     [rbp+170h+var_1A8], 10h
0x1800032f1  mov     [rbp+170h+var_1B8], 4
0x1800032f9  mov     dword ptr [rbp+170h+var_1F0], 0B000000h
0x180003300  movzx   eax, word ptr [rax]
0x180003303  mov     [rbp+170h+var_1E0.Size], eax
0x180003306  lea     rax, byte_180025187
0x18000330d  mov     [rbp+170h+var_1D0], rax
0x180003311  lea     rax, _TraceLoggingMetadataEnd
0x180003318  sub     eax, ecx
0x18000331a  mov     dword ptr [rbp+170h+var_1E0.0Ch], 2
0x180003321  mov     [rbp+170h+var_1C8], 4Fh ; 'O'
0x180003328  mov     [rbp+170h+var_1C4], 1
0x18000332f  mov     [rsp+270h+var_224], eax
0x180003333  mov     eax, [rsp+270h+var_224]
0x180003337  lea     rax, [rbp+170h+var_1E0]
0x18000333b  mov     [rsp+270h+UserData], rax
0x180003340  mov     [rsp+270h+UserDataCount], 7
0x180003348  jmp     loc_180003BEF
0x18000334d  mov     eax, cs:dword_18002A000
0x180003353  cmp     eax, 5
0x180003356  jbe     loc_180003C08
0x18000335c  xor     ecx, ecx
0x18000335e  mov     [rsp+270h+var_238], r8d
0x180003363  mov     [rbp+170h+var_1E8], rcx
0x180003367  lea     rax, [rsp+270h+var_238]
0x18000336c  mov     [rbp+170h+var_1A0], rax
0x180003370  lea     rcx, _TraceLoggingMetadata
0x180003377  lea     rax, [rsp+270h+var_23C]
0x18000337c  mov     [rsp+270h+var_23C], r9d
0x180003381  mov     [rbp+170h+var_1B0], rax
0x180003385  lea     rax, [rsp+270h+var_240]
0x18000338a  mov     [rbp+170h+var_1C0], rax
0x18000338e  movzx   eax, cs:word_180025138
0x180003395  mov     dword ptr [rbp+170h+var_1F0+4], eax
0x180003398  mov     rax, cs:off_18002A008
0x18000339f  mov     [rbp+170h+var_1E0.Ptr], rax
0x1800033a3  mov     [rsp+270h+var_240], r11d
0x1800033a8  mov     [rbp+170h+var_198], 4
0x1800033b0  mov     [rbp+170h+var_1A8], 4
0x1800033b8  mov     [rbp+170h+var_1B8], 4
0x1800033c0  mov     dword ptr [rbp+170h+var_1F0], 0B000000h
0x1800033c7  movzx   eax, word ptr [rax]
0x1800033ca  mov     [rbp+170h+var_1E0.Size], eax
0x1800033cd  lea     rax, word_180025142
0x1800033d4  mov     [rbp+170h+var_1D0], rax
0x1800033d8  lea     rax, _TraceLoggingMetadataEnd
0x1800033df  sub     eax, ecx
0x1800033e1  mov     dword ptr [rbp+170h+var_1E0.0Ch], 2
0x1800033e8  mov     [rbp+170h+var_1C8], 39h ; '9'
0x1800033ef  mov     [rbp+170h+var_1C4], 1
0x1800033f6  mov     [rsp+270h+var_234], eax
0x1800033fa  mov     eax, [rsp+270h+var_234]
0x1800033fe  lea     rax, [rbp+170h+var_1E0]
0x180003402  mov     [rsp+270h+UserData], rax
0x180003407  lea     rdx, [rbp+170h+var_1F0]
0x18000340b  mov     [rsp+270h+UserDataCount], 5
0x180003413  jmp     loc_180003BEF
0x180003418  mov     eax, r11d
0x18000341b  sub     eax, 120h
0x180003420  jz      loc_1800037EC
0x180003426  sub     eax, 3
0x180003429  jz      loc_18000363E
0x18000342f  cmp     eax, 1
0x180003432  jnz     loc_180003C08
0x180003438  test    r10, r10
0x18000343b  jz      loc_180003556
0x180003441  mov     rax, [rbp+170h+arg_20]
0x180003448  test    rax, rax
0x18000344b  jz      loc_180003556
0x180003451  cmp     r9d, 4
0x180003455  jnz     loc_180003556
0x18000345b  mov     r9d, [rax]
0x18000345e  mov     eax, cs:dword_18002A000
0x180003464  cmp     eax, 5
0x180003467  jbe     loc_180003C08
0x18000346d  mov     rcx, cs:qword_18002A018
0x180003474  mov     rdx, 400000000000h
0x18000347e  mov     rax, cs:qword_18002A010
0x180003485  test    rdx, rax
0x180003488  jz      loc_180003C08
0x18000348e  mov     rax, rcx
0x180003491  and     rax, rdx
0x180003494  cmp     rax, rcx
0x180003497  jnz     loc_180003C08
0x18000349d  lea     rax, [rsp+270h+var_230]
0x1800034a2  mov     [rsp+270h+var_230], 800h
0x1800034ab  mov     [rbp+170h+var_190], rax
0x1800034af  lea     rax, [rsp+270h+var_238]
0x1800034b4  mov     [rbp+170h+var_1A0], rax
0x1800034b8  lea     rax, [rsp+270h+var_23C]
0x1800034bd  mov     [rbp+170h+var_1B0], rax
0x1800034c1  movzx   eax, cs:word_180024E1B
0x1800034c8  mov     dword ptr [rbp+170h+var_1F0+4], eax
0x1800034cb  mov     rax, cs:off_18002A008
0x1800034d2  mov     [rbp+170h+var_1E0.Ptr], rax
0x1800034d6  mov     [rsp+270h+var_238], r8d
0x1800034db  mov     [rsp+270h+var_23C], r9d
0x1800034e0  mov     [rbp+170h+var_188], 8
0x1800034e8  mov     [rbp+170h+var_198], 4
0x1800034f0  mov     [rbp+170h+var_1A8], 4
0x1800034f8  mov     [rbp+170h+var_1C0], r10
0x1800034fc  mov     [rbp+170h+var_1B8], 10h
0x180003504  mov     dword ptr [rbp+170h+var_1F0], 0B000000h
0x18000350b  mov     [rbp+170h+var_1E8], rdx
0x18000350f  movzx   eax, word ptr [rax]
0x180003512  mov     [rbp+170h+var_1E0.Size], eax
0x180003515  lea     rax, byte_180024E25
0x18000351c  mov     [rbp+170h+var_1C8], 64h ; 'd'
0x180003523  mov     [rbp+170h+var_1D0], rax
0x180003527  lea     rcx, _TraceLoggingMetadata
0x18000352e  lea     rax, _TraceLoggingMetadataEnd
0x180003535  mov     dword ptr [rbp+170h+var_1E0.0Ch], 2
0x18000353c  sub     eax, ecx
0x18000353e  mov     [rbp+170h+var_1C4], 1
0x180003545  mov     [rsp+270h+var_240], eax
0x180003549  lea     rdx, [rbp+170h+var_1F0]
0x18000354d  mov     eax, [rsp+270h+var_240]
0x180003551  jmp     loc_180003BDE
0x180003556  mov     eax, cs:dword_18002A000
0x18000355c  cmp     eax, 5
0x18000355f  jbe     loc_180003C08
0x180003565  mov     rcx, cs:qword_18002A018
0x18000356c  mov     rdx, 400000000000h
0x180003576  mov     rax, cs:qword_18002A010
0x18000357d  test    rdx, rax
0x180003580  jz      loc_180003C08
0x180003586  mov     rax, rcx
0x180003589  and     rax, rdx
0x18000358c  cmp     rax, rcx
0x18000358f  jnz     loc_180003C08
0x180003595  lea     rax, [rsp+270h+var_230]
0x18000359a  mov     [rsp+270h+var_230], 800h
0x1800035a3  mov     [rbp+170h+var_1A0], rax
0x1800035a7  lea     rax, [rsp+270h+var_238]
0x1800035ac  mov     [rbp+170h+var_1B0], rax
0x1800035b0  lea     rax, [rsp+270h+var_23C]
0x1800035b5  mov     [rbp+170h+var_1C0], rax
0x1800035b9  movzx   eax, cs:word_180024DC3
0x1800035c0  mov     dword ptr [rbp+170h+var_1F0+4], eax
0x1800035c3  mov     rax, cs:off_18002A008
0x1800035ca  mov     [rbp+170h+var_1E0.Ptr], rax
0x1800035ce  mov     [rsp+270h+var_238], r8d
0x1800035d3  mov     [rsp+270h+var_23C], r9d
0x1800035d8  mov     [rbp+170h+var_198], 8
0x1800035e0  mov     [rbp+170h+var_1A8], 4
0x1800035e8  mov     [rbp+170h+var_1B8], 4
0x1800035f0  mov     dword ptr [rbp+170h+var_1F0], 0B000000h
0x1800035f7  mov     [rbp+170h+var_1E8], rdx
0x1800035fb  movzx   eax, word ptr [rax]
0x1800035fe  mov     [rbp+170h+var_1E0.Size], eax
0x180003601  lea     rax, byte_180024DCD
0x180003608  mov     [rbp+170h+var_1C8], 4Ch ; 'L'
0x18000360f  mov     [rbp+170h+var_1D0], rax
0x180003613  lea     rcx, _TraceLoggingMetadata
0x18000361a  lea     rax, _TraceLoggingMetadataEnd
0x180003621  mov     dword ptr [rbp+170h+var_1E0.0Ch], 2
0x180003628  sub     eax, ecx
0x18000362a  mov     [rbp+170h+var_1C4], 1
0x180003631  mov     [rsp+270h+var_240], eax
0x180003635  mov     eax, [rsp+270h+var_240]
0x180003639  jmp     loc_1800033FE
0x18000363e  test    r10, r10
0x180003641  jz      loc_18000372E
0x180003647  mov     rax, [rbp+170h+arg_20]
0x18000364e  test    rax, rax
0x180003651  jz      loc_18000372E
0x180003657  cmp     r9d, 4
0x18000365b  jnz     loc_18000372E
0x180003661  mov     r9d, [rax]
0x180003664  mov     eax, cs:dword_18002A000
0x18000366a  cmp     eax, 5
0x18000366d  jbe     loc_180003C08
0x180003673  mov     rcx, cs:qword_18002A018
0x18000367a  mov     rdx, 400000000000h
0x180003684  mov     rax, cs:qword_18002A010
0x18000368b  test    rdx, rax
0x18000368e  jz      loc_180003C08
0x180003694  mov     rax, rcx
0x180003697  and     rax, rdx
0x18000369a  cmp     rax, rcx
0x18000369d  jnz     loc_180003C08
0x1800036a3  lea     rax, [rsp+270h+var_230]
0x1800036a8  mov     [rsp+270h+var_230], 800h
0x1800036b1  mov     [rbp+170h+var_190], rax
0x1800036b5  lea     rax, [rsp+270h+var_238]
0x1800036ba  mov     [rbp+170h+var_1A0], rax
0x1800036be  lea     rax, [rsp+270h+var_23C]
0x1800036c3  mov     [rbp+170h+var_1B0], rax
0x1800036c7  movzx   eax, cs:word_180024ED5
0x1800036ce  mov     dword ptr [rbp+170h+var_1F0+4], eax
0x1800036d1  mov     rax, cs:off_18002A008
0x1800036d8  mov     [rbp+170h+var_1E0.Ptr], rax
0x1800036dc  mov     [rsp+270h+var_238], r8d
0x1800036e1  mov     [rsp+270h+var_23C], r9d
0x1800036e6  mov     [rbp+170h+var_188], 8
0x1800036ee  mov     [rbp+170h+var_198], 4
0x1800036f6  mov     [rbp+170h+var_1A8], 4
0x1800036fe  mov     [rbp+170h+var_1C0], r10
0x180003702  mov     [rbp+170h+var_1B8], 10h
0x18000370a  mov     dword ptr [rbp+170h+var_1F0], 0B000000h
0x180003711  mov     [rbp+170h+var_1E8], rdx
0x180003715  movzx   eax, word ptr [rax]
0x180003718  mov     [rbp+170h+var_1E0.Size], eax
0x18000371b  lea     rax, byte_180024EDF
0x180003722  mov     [rbp+170h+var_1C8], 45h ; 'E'
0x180003729  jmp     loc_180003523
0x18000372e  mov     eax, cs:dword_18002A000
0x180003734  cmp     eax, 5
0x180003737  jbe     loc_180003C08
0x18000373d  mov     rcx, cs:qword_18002A018
0x180003744  mov     rdx, 400000000000h
0x18000374e  mov     rax, cs:qword_18002A010
0x180003755  test    rdx, rax
0x180003758  jz      loc_180003C08
0x18000375e  mov     rax, rcx
0x180003761  and     rax, rdx
0x180003764  cmp     rax, rcx
0x180003767  jnz     loc_180003C08
0x18000376d  lea     rax, [rsp+270h+var_230]
0x180003772  mov     [rsp+270h+var_230], 800h
0x18000377b  mov     [rbp+170h+var_1A0], rax
0x18000377f  lea     rax, [rsp+270h+var_238]
0x180003784  mov     [rbp+170h+var_1B0], rax
0x180003788  lea     rax, [rsp+270h+var_23C]
0x18000378d  mov     [rbp+170h+var_1C0], rax
0x180003791  movzx   eax, cs:word_180024E8B
0x180003798  mov     dword ptr [rbp+170h+var_1F0+4], eax
0x18000379b  mov     rax, cs:off_18002A008
0x1800037a2  mov     [rbp+170h+var_1E0.Ptr], rax
0x1800037a6  mov     [rsp+270h+var_238], r8d
0x1800037ab  mov     [rsp+270h+var_23C], r9d
0x1800037b0  mov     [rbp+170h+var_198], 8
0x1800037b8  mov     [rbp+170h+var_1A8], 4
0x1800037c0  mov     [rbp+170h+var_1B8], 4
0x1800037c8  mov     dword ptr [rbp+170h+var_1F0], 0B000000h
0x1800037cf  mov     [rbp+170h+var_1E8], rdx
0x1800037d3  movzx   eax, word ptr [rax]
0x1800037d6  mov     [rbp+170h+var_1E0.Size], eax
0x1800037d9  lea     rax, byte_180024E95
0x1800037e0  mov     [rbp+170h+var_1C8], 3Eh ; '>'
0x1800037e7  jmp     loc_18000360F
0x1800037ec  test    r10, r10
0x1800037ef  jz      loc_180003AE3
0x1800037f5  mov     rcx, [rbp+170h+arg_20]
  ... truncated ...
```
