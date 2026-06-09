# WcEnumerateDirectoryWithMerge

- ea: `0x140014c90`
- end: `0x1400154a3`
- name: `WcEnumerateDirectoryWithMerge`
- size: `2067`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, int, char, int, __int64, char, __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting`

## callers

- `0x14001eadc`
- `0x140030a70`

## callees

- `0x140001008`
- `0x140001030`
- `0x140001500`
- `0x140002048`
- `0x1400020c4`
- `0x140004198`
- `0x140004d7c`
- `0x140007c60`
- `0x140007dc0`
- `0x140014c90`
- `0x1400294b4`
- `0x14002b84c`
- `0x14002b9f0`
- `0x14002bd20`
- `0x14002e944`
- `0x14002fe84`
- `0x140030708`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140014fb8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014fb8`
- `ntoskrnl!KeSetEvent` at `0x14001542f`
- `ntoskrnl!KeSetEvent` at `0x14001542f`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x140015031`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x140015031`
- `ntoskrnl!IoGetSilo` at `0x1400150cb`
- `ntoskrnl!IoGetSilo` at `0x1400150cb`
- `ntoskrnl!PsGetParentSilo` at `0x1400150da`
- `ntoskrnl!PsGetParentSilo` at `0x1400150da`
- `FLTMGR!FltReleaseContext` at `0x140015447`
- `FLTMGR!FltReleaseContext` at `0x14001545f`
- `FLTMGR!FltReleaseContext` at `0x140015473`
- `FLTMGR!FltReleaseContext` at `0x140015447`
- `FLTMGR!FltReleaseContext` at `0x14001545f`
- `FLTMGR!FltReleaseContext` at `0x140015473`

## pseudocode

```c
__int64 __fastcall WcEnumerateDirectoryWithMerge(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        int a3,
        struct _UNICODE_STRING *a4,
        int a5,
        char a6,
        unsigned int a7,
        __int64 a8,
        char a9,
        _DWORD *a10)
{
  char v10; // r13
  int v13; // edx
  int SetStreamHandleContext; // r14d
  __int64 v15; // rcx
  unsigned int v16; // ecx
  unsigned int v17; // esi
  unsigned int v18; // edi
  __int64 v19; // rbx
  _QWORD *v20; // r8
  __int64 Silo; // rax
  __int64 ParentSilo; // rax
  unsigned int v23; // r9d
  char v24; // cl
  int v25; // r12d
  char v26; // dl
  __int64 v27; // rdx
  int v28; // eax
  int v29; // eax
  int v30; // eax
  unsigned int v31; // r9d
  int v32; // r9d
  int v33; // eax
  int v34; // eax
  char v36; // [rsp+30h] [rbp-D0h]
  char v37; // [rsp+38h] [rbp-C8h]
  char v38; // [rsp+40h] [rbp-C0h]
  int v39; // [rsp+48h] [rbp-B8h]
  char v40; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v41; // [rsp+74h] [rbp-8Ch]
  int v42; // [rsp+78h] [rbp-88h] BYREF
  _DWORD Size[3]; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v44; // [rsp+88h] [rbp-78h]
  PFLT_CONTEXT Context; // [rsp+90h] [rbp-70h]
  __int64 v46; // [rsp+98h] [rbp-68h] BYREF
  PFILE_OBJECT v47; // [rsp+A0h] [rbp-60h]
  PFLT_INSTANCE Instancea; // [rsp+A8h] [rbp-58h]
  PUNICODE_STRING Name; // [rsp+B0h] [rbp-50h]
  __int64 v50; // [rsp+B8h] [rbp-48h]
  void *Src; // [rsp+C0h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+D0h] [rbp-30h] BYREF
  char *v53; // [rsp+F0h] [rbp-10h]
  __int64 v54; // [rsp+F8h] [rbp-8h]
  __int64 *v55; // [rsp+100h] [rbp+0h]
  __int64 v56; // [rsp+108h] [rbp+8h]

  v10 = 0;
  Instancea = Instance;
  v50 = a8;
  Name = a4;
  v47 = FileObject;
  v46 = (__int64)a10;
  v44 = 0;
  Context = 0;
  v42 = 0;
  Src = 0;
  memset(Size, 0, sizeof(Size));
  if ( !(unsigned __int8)WcGetContextFileObject(Instance, FileObject) )
  {
    SetStreamHandleContext = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 3;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        18,
        28,
        (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
        7,
        a3);
    }
    *a10 = 0;
    goto LABEL_103;
  }
  if ( (a6 & 4) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 4;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        18,
        29,
        (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
        18);
    }
    if ( (unsigned int)dword_14000E060 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14000E060, 0x400000000000LL) )
    {
      v40 = 4;
      v53 = &v40;
      v54 = 1;
      v55 = &v46;
      v46 = 4;
      v56 = 8;
      tlgWriteTransfer_EtwWriteTransfer(v15, (unsigned __int8 *)byte_14000B551, 0, 0, 4u, &v52);
    }
    SetStreamHandleContext = -1073741637;
    goto LABEL_103;
  }
  if ( a3 <= 38 )
  {
    if ( a3 != 38 )
    {
      switch ( a3 )
      {
        case 1:
          v16 = 64;
          break;
        case 2:
          v16 = 68;
          break;
        case 3:
          v16 = 94;
          goto LABEL_24;
        case 12:
          v16 = 12;
          break;
        case 33:
          v16 = 16;
          v17 = 536;
          v18 = 33;
          goto LABEL_41;
        case 37:
          v16 = 104;
LABEL_24:
          v17 = 626;
          v18 = 79;
          goto LABEL_41;
        default:
LABEL_35:
          SetStreamHandleContext = -1073741811;
          goto LABEL_103;
      }
      goto LABEL_27;
    }
LABEL_28:
    v16 = 80;
LABEL_27:
    v17 = 600;
    v18 = 78;
    goto LABEL_41;
  }
  v18 = 60;
  switch ( a3 )
  {
    case '<':
      v16 = 88;
      v17 = 608;
      break;
    case '?':
      v16 = 114;
      v17 = 634;
      v18 = 63;
      break;
    case 'N':
      goto LABEL_28;
    case 'O':
      v16 = 106;
      goto LABEL_24;
    case 'P':
      v16 = 96;
      v17 = 616;
      v18 = 80;
      break;
    case 'Q':
      v16 = 122;
      v17 = 642;
      v18 = 81;
      break;
    default:
      goto LABEL_35;
  }
LABEL_41:
  if ( a7 < v16 )
  {
    SetStreamHandleContext = -1073741820;
    goto LABEL_103;
  }
  if ( a7 >= v17 )
  {
    if ( a7 <= 0x10000 )
    {
      v17 = a7 + a7 / ((v16 + 7) & 0xFFFFFFF8) * (((v17 + 7) & 0xFFFFFFF8) - ((v16 + 7) & 0xFFFFFFF8));
      if ( v17 > 0x10000 )
        v17 = 0x10000;
    }
    else
    {
      v17 = 0x10000;
    }
  }
  v19 = v44;
  SetStreamHandleContext = WcGetSetStreamHandleContext(Instancea, FileObject);
  if ( SetStreamHandleContext < 0 )
    goto LABEL_101;
  KeWaitForSingleObject((PVOID)(v44 + 16), Executive, 0, 0, 0);
  v10 = 1;
  LOBYTE(v44) = a6 & 1;
  if ( (a6 & 1) != 0 )
    *(_DWORD *)(v19 + 40) &= ~2u;
  LOBYTE(v41) = a6 & 0x10;
  if ( (a6 & 0x10) == 0 && (*(_DWORD *)(v19 + 40) & 2) != 0 )
  {
    SetStreamHandleContext = -2147483642;
    goto LABEL_101;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&Size[1] + 56LL) + 24LL) + 32LL) + 16LL) & 1) == 0
    && *(_QWORD *)(v19 + 48) == v19 + 48
    && Name
    && !FsRtlDoesNameContainWildCards(Name) )
  {
    SetStreamHandleContext = WcEnumerateDirectorySingleEntry(
                               *(__int64 *)&Size[1],
                               (__int64)Instancea,
                               (__int64)v47,
                               v18,
                               a3,
                               (__int64)Name,
                               v17,
                               a6,
                               **((_DWORD **)Context + 8),
                               v39,
                               a7,
                               v50,
                               a9,
                               v46);
    if ( !SetStreamHandleContext && !(_BYTE)v41 )
      *(_DWORD *)(v19 + 40) |= 2u;
    goto LABEL_101;
  }
  v20 = (_QWORD *)(v19 + 48);
  if ( (_QWORD *)*v20 != v20 )
  {
LABEL_64:
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v41 = 0;
    if ( (_BYTE)v44 )
    {
      *(_DWORD *)(v19 + 72) = 0;
      *(_DWORD *)(v19 + 596) = 0;
      *(_DWORD *)(v19 + 40) |= 4u;
    }
    else if ( (*(_DWORD *)(v19 + 40) & 4) != 0 && *(_DWORD *)(v19 + 72) && !*(_DWORD *)(v19 + 596) )
    {
      v26 = a6 | 1;
      a6 |= 1u;
      goto LABEL_67;
    }
    v26 = a6;
    while ( 1 )
    {
LABEL_67:
      if ( v24 || v23 >= a7 )
        goto LABEL_88;
      SetStreamHandleContext = WcPrepareEnumerationContexts(
                                 v19,
                                 (_DWORD)Instancea,
                                 (_DWORD)v47,
                                 (_DWORD)v20,
                                 v17,
                                 v18,
                                 v26,
                                 *(_DWORD *)(v19 + 596));
      if ( SetStreamHandleContext < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_101;
        v38 = SetStreamHandleContext;
        v32 = 30;
        v37 = a3;
        v36 = 27;
        goto LABEL_100;
      }
      SetStreamHandleContext = WcEnumerateLayeredDirectories(
                                 v19,
                                 (_DWORD)Name,
                                 (int)v19 + 76,
                                 *(_DWORD *)(v19 + 596),
                                 a5);
      if ( SetStreamHandleContext < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_101;
        v38 = SetStreamHandleContext;
        v32 = 31;
        v37 = a3;
        v36 = 39;
        goto LABEL_100;
      }
      v28 = WcMergeEnumerationResults(
              v19,
              a3,
              **((_DWORD **)Context + 8),
              a7,
              v50,
              (__int64)&v42,
              a9,
              (__int64)&Src,
              (__int64)Size);
      SetStreamHandleContext = v28;
      if ( v28 == -2147483642 || v28 == -1073741809 )
        break;
      if ( v28 == -2147483643 )
      {
        v33 = v42;
        *(_DWORD *)(v19 + 72) += v42;
        *(_DWORD *)(v19 + 40) |= 4u;
        v25 += v33;
        goto LABEL_88;
      }
      if ( v28 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_101;
        v38 = v28;
        v32 = 32;
        v37 = a3;
        v36 = 65;
LABEL_100:
        LOBYTE(v27) = 2;
        WPP_RECORDER_SF_sDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v27,
          18,
          v32,
          (__int64)WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\dir.c",
          v36,
          v37,
          v38);
        goto LABEL_101;
      }
      v29 = Size[0];
      if ( Size[0] )
      {
        memmove((void *)(v19 + 76), Src, Size[0]);
        v29 = Size[0];
      }
      *(_DWORD *)(v19 + 596) = v29;
      v30 = v42;
      if ( v42 )
      {
        v31 = v41;
        LODWORD(v20) = v19 + 48;
        *(_DWORD *)(v19 + 72) += v42;
        v23 = v30 + v31;
        v26 = a6;
        v25 += v30;
        v41 = v23;
        v24 = 1;
      }
      else
      {
        LOBYTE(v27) = 1;
        WcResetEnumContexts(v19, v27);
        LODWORD(v20) = v19 + 48;
        v23 = v41;
        v26 = a6 & 0xFE;
        v24 = 0;
        a6 &= ~1u;
        v25 += v42;
      }
    }
    v25 += v42;
LABEL_88:
    v34 = *(_DWORD *)(v19 + 40);
    if ( (v34 & 4) != 0 && SetStreamHandleContext != -2147483643 )
    {
      if ( SetStreamHandleContext == -2147483642 && !*(_DWORD *)(v19 + 72) )
        SetStreamHandleContext = -1073741809;
      *(_DWORD *)(v19 + 40) = v34 & 0xFFFFFFFB;
    }
    *(_DWORD *)v46 = v25;
    goto LABEL_101;
  }
  Silo = IoGetSilo(v47);
  ParentSilo = PsGetParentSilo(Silo);
  SetStreamHandleContext = WcCopySourceList(*(_QWORD *)&Size[1] + 56LL, ParentSilo, v19 + 48);
  if ( SetStreamHandleContext >= 0 )
  {
    *(_DWORD *)(v19 + 40) |= 4u;
    LODWORD(v20) = v19 + 48;
    goto LABEL_64;
  }
LABEL_101:
  if ( v10 )
    KeSetEvent((PRKEVENT)(v19 + 16), 0, 0);
LABEL_103:
  if ( Context )
    FltReleaseContext(Context);
  if ( *(_QWORD *)&Size[1] )
    FltReleaseContext(*(PFLT_CONTEXT *)&Size[1]);
  return (unsigned int)SetStreamHandleContext;
}

```

## disassembly

```asm
0x140014c90  push    rbp
0x140014c92  push    rbx
0x140014c93  push    rsi
0x140014c94  push    rdi
0x140014c95  push    r12
0x140014c97  push    r13
0x140014c99  push    r14
0x140014c9b  push    r15
0x140014c9d  lea     rbp, [rsp-28h]
0x140014ca2  sub     rsp, 128h
0x140014ca9  mov     rax, cs:__security_cookie
0x140014cb0  xor     rax, rsp
0x140014cb3  mov     [rbp+60h+var_50], rax
0x140014cb7  mov     rdi, [rbp+60h+arg_48]
0x140014cbe  xor     r13d, r13d
0x140014cc1  mov     rax, rcx
0x140014cc4  mov     [rbp+60h+Instance], rcx
0x140014cc8  mov     rcx, [rbp+60h+arg_38]
0x140014ccf  mov     r15d, r8d
0x140014cd2  mov     [rbp+60h+var_A8], rcx
0x140014cd6  lea     r8, [rbp+60h+Context]
0x140014cda  mov     [rbp+60h+Name], r9
0x140014cde  mov     ebx, r13d
0x140014ce1  mov     rcx, rax; Instance
0x140014ce4  mov     [rbp+60h+var_C0], rdx
0x140014ce8  lea     r9, [rbp+60h+Size+4]
0x140014cec  mov     [rbp+60h+var_C8], rdi
0x140014cf0  mov     r14, rdx
0x140014cf3  mov     [rbp+60h+var_D8], rbx
0x140014cf7  mov     qword ptr [rbp+60h+Size+4], r13
0x140014cfb  mov     [rbp+60h+Context], r13
0x140014cff  mov     [rsp+160h+var_E8], r13d
0x140014d04  mov     [rbp+60h+Src], r13
0x140014d08  mov     dword ptr [rsp+160h+Size], r13d
0x140014d0d  call    WcGetContextFileObject
0x140014d12  test    al, al
0x140014d14  jnz     short loc_140014D70
0x140014d16  mov     r14d, r13d
0x140014d19  lea     rax, WPP_RECORDER_INITIALIZED
0x140014d20  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140014d27  jz      short loc_140014D68
0x140014d29  mov     rcx, cs:WPP_GLOBAL_Control
0x140014d30  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\wcifs\\dir.c"
0x140014d37  mov     dword ptr [rsp+160h+var_128], r15d
0x140014d3c  lea     r9d, [r13+1Ch]
0x140014d40  mov     dword ptr [rsp+160h+var_130], 0E07h
0x140014d48  lea     r8d, [r13+12h]
0x140014d4c  mov     [rsp+160h+var_138], rax
0x140014d51  mov     dl, 3
0x140014d53  mov     rcx, [rcx+40h]
0x140014d57  lea     rax, WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids
0x140014d5e  mov     [rsp+160h+Timeout], rax
0x140014d63  call    WPP_RECORDER_SF_sDd
0x140014d68  mov     [rdi], r13d
0x140014d6b  jmp     loc_14001543B
0x140014d70  test    [rbp+60h+arg_28], 4
0x140014d77  jz      loc_140014E4A
0x140014d7d  lea     rax, WPP_RECORDER_INITIALIZED
0x140014d84  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140014d8b  jz      short loc_140014DC9
0x140014d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140014d94  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\wcifs\\dir.c"
0x140014d9b  mov     r9d, 1Dh
0x140014da1  mov     dword ptr [rsp+160h+var_130], 0E12h
0x140014da9  mov     [rsp+160h+var_138], rax
0x140014dae  mov     dl, 4
0x140014db0  lea     rax, WPP_c1e0b6795ecc304cffe05d8888ed3789_Traceguids
0x140014db7  mov     rcx, [rcx+40h]
0x140014dbb  lea     r8d, [r9-0Bh]
0x140014dbf  mov     [rsp+160h+Timeout], rax
0x140014dc4  call    WPP_RECORDER_SF_sD
0x140014dc9  mov     eax, cs:dword_14000E060
0x140014dcf  cmp     eax, 5
0x140014dd2  jbe     short loc_140014E3F
0x140014dd4  mov     rdx, 400000000000h
0x140014dde  lea     rcx, dword_14000E060
0x140014de5  call    _tlgKeywordOn
0x140014dea  test    al, al
0x140014dec  jz      short loc_140014E3F
0x140014dee  lea     rax, [rsp+160h+var_F0]
0x140014df3  mov     [rsp+160h+var_F0], 4
0x140014df8  mov     [rbp+60h+var_70], rax
0x140014dfc  lea     rdx, byte_14000B551
0x140014e03  lea     rax, [rbp+60h+var_C8]
0x140014e07  mov     [rbp+60h+var_68], 1
0x140014e0f  mov     [rbp+60h+var_60], rax
0x140014e13  xor     r9d, r9d
0x140014e16  lea     rax, [rbp+60h+var_90]
0x140014e1a  mov     [rbp+60h+var_C8], 4
0x140014e22  mov     [rsp+160h+var_138], rax
0x140014e27  xor     r8d, r8d
0x140014e2a  mov     dword ptr [rsp+160h+Timeout], 4
0x140014e32  mov     [rbp+60h+var_58], 8
0x140014e3a  call    _tlgWriteTransfer_EtwWriteTransfer
0x140014e3f  mov     r14d, 0C00000BBh
0x140014e45  jmp     loc_14001543B
0x140014e4a  cmp     r15d, 26h ; '&'
0x140014e4e  jg      short loc_140014EC6
0x140014e50  jz      short loc_140014EBF
0x140014e52  mov     ecx, r15d
0x140014e55  sub     ecx, 1
0x140014e58  jz      short loc_140014EAE
0x140014e5a  sub     ecx, 1
0x140014e5d  jz      short loc_140014EA7
0x140014e5f  sub     ecx, 1
0x140014e62  jz      short loc_140014E93
0x140014e64  sub     ecx, 9
0x140014e67  jz      short loc_140014E8C
0x140014e69  sub     ecx, 15h
0x140014e6c  jz      short loc_140014E7A
0x140014e6e  cmp     ecx, 4
0x140014e71  jnz     short loc_140014EEB
0x140014e73  mov     ecx, 68h ; 'h'
0x140014e78  jmp     short loc_140014E98
0x140014e7a  mov     ecx, 10h
0x140014e7f  mov     esi, 218h
0x140014e84  lea     edi, [rcx+11h]
0x140014e87  jmp     loc_140014F37
0x140014e8c  mov     ecx, 0Ch
0x140014e91  jmp     short loc_140014EB3
0x140014e93  mov     ecx, 5Eh ; '^'
0x140014e98  mov     esi, 272h
0x140014e9d  mov     edi, 4Fh ; 'O'
0x140014ea2  jmp     loc_140014F37
0x140014ea7  mov     ecx, 44h ; 'D'
0x140014eac  jmp     short loc_140014EB3
0x140014eae  mov     ecx, 40h ; '@'
0x140014eb3  mov     esi, 258h
0x140014eb8  mov     edi, 4Eh ; 'N'
0x140014ebd  jmp     short loc_140014F37
0x140014ebf  mov     ecx, 50h ; 'P'
0x140014ec4  jmp     short loc_140014EB3
0x140014ec6  mov     ecx, r15d
0x140014ec9  mov     edi, 3Ch ; '<'
0x140014ece  sub     ecx, edi
0x140014ed0  jz      short loc_140014F2D
0x140014ed2  sub     ecx, 3
0x140014ed5  jz      short loc_140014F1E
0x140014ed7  sub     ecx, 0Fh
0x140014eda  jz      short loc_140014EBF
0x140014edc  sub     ecx, 1
0x140014edf  jz      short loc_140014F14
0x140014ee1  sub     ecx, 1
0x140014ee4  jz      short loc_140014F05
0x140014ee6  cmp     ecx, 1
0x140014ee9  jz      short loc_140014EF6
0x140014eeb  mov     r14d, 0C000000Dh
0x140014ef1  jmp     loc_14001543B
0x140014ef6  mov     ecx, 7Ah ; 'z'
0x140014efb  mov     esi, 282h
0x140014f00  lea     edi, [rcx-29h]
0x140014f03  jmp     short loc_140014F37
0x140014f05  mov     ecx, 60h ; '`'
0x140014f0a  mov     esi, 268h
0x140014f0f  lea     edi, [rcx-10h]
0x140014f12  jmp     short loc_140014F37
0x140014f14  mov     ecx, 6Ah ; 'j'
0x140014f19  jmp     loc_140014E98
0x140014f1e  mov     ecx, 72h ; 'r'
0x140014f23  mov     esi, 27Ah
0x140014f28  lea     edi, [rcx-33h]
0x140014f2b  jmp     short loc_140014F37
0x140014f2d  mov     ecx, 58h ; 'X'
0x140014f32  mov     esi, 260h
0x140014f37  mov     r12d, [rbp+60h+arg_30]
0x140014f3e  cmp     r12d, ecx
0x140014f41  jnb     short loc_140014F4E
0x140014f43  mov     r14d, 0C0000004h
0x140014f49  jmp     loc_14001543B
0x140014f4e  cmp     r12d, esi
0x140014f51  jb      short loc_140014F88
0x140014f53  mov     r9d, 10000h
0x140014f59  cmp     r12d, r9d
0x140014f5c  jbe     short loc_140014F63
0x140014f5e  mov     esi, r9d
0x140014f61  jmp     short loc_140014F88
0x140014f63  add     esi, 7
0x140014f66  mov     eax, 0FFFFFFF8h
0x140014f6b  and     esi, eax
0x140014f6d  add     ecx, 7
0x140014f70  and     ecx, eax
0x140014f72  xor     edx, edx
0x140014f74  sub     esi, ecx
0x140014f76  mov     eax, r12d
0x140014f79  div     ecx
0x140014f7b  imul    esi, eax
0x140014f7e  add     esi, r12d
0x140014f81  cmp     esi, r9d
0x140014f84  cmova   esi, r9d
0x140014f88  mov     rcx, [rbp+60h+Instance]; Instance
0x140014f8c  lea     r8, [rbp+60h+var_D8]
0x140014f90  mov     rdx, r14; FileObject
0x140014f93  call    WcGetSetStreamHandleContext
0x140014f98  mov     rbx, [rbp+60h+var_D8]
0x140014f9c  mov     r14d, eax
0x140014f9f  test    eax, eax
0x140014fa1  js      loc_140015374
0x140014fa7  lea     rcx, [rbx+10h]; Object
0x140014fab  mov     [rsp+160h+Timeout], r13; Timeout
0x140014fb0  xor     r9d, r9d; Alertable
0x140014fb3  xor     r8d, r8d; WaitMode
0x140014fb6  xor     edx, edx; WaitReason
0x140014fb8  call    cs:__imp_KeWaitForSingleObject
0x140014fbf  nop     dword ptr [rax+rax+00h]
0x140014fc4  mov     al, [rbp+60h+arg_28]
0x140014fca  mov     r13d, 1
0x140014fd0  mov     cl, al
0x140014fd2  and     cl, r13b
0x140014fd5  mov     byte ptr [rbp+60h+var_D8], cl
0x140014fd8  jz      short loc_140014FDE
0x140014fda  and     dword ptr [rbx+28h], 0FFFFFFFDh
0x140014fde  and     al, 10h
0x140014fe0  mov     byte ptr [rsp+160h+var_EC], al
0x140014fe4  jnz     short loc_140014FF8
0x140014fe6  mov     eax, [rbx+28h]
0x140014fe9  test    al, 2
0x140014feb  jz      short loc_140014FF8
0x140014fed  mov     r14d, 80000006h
0x140014ff3  jmp     loc_140015374
0x140014ff8  mov     rax, qword ptr [rbp+60h+Size+4]
0x140014ffc  mov     rax, [rax+38h]
0x140015000  mov     rcx, [rax+18h]
0x140015004  mov     rax, [rcx+20h]
0x140015008  mov     ecx, [rax+10h]
0x14001500b  test    r13b, cl
0x14001500e  jnz     loc_1400150BE
0x140015014  lea     rax, [rbx+30h]
0x140015018  cmp     [rax], rax
0x14001501b  jnz     loc_1400150BE
0x140015021  mov     rax, [rbp+60h+Name]
0x140015025  test    rax, rax
0x140015028  jz      loc_1400150BE
0x14001502e  mov     rcx, rax; Name
0x140015031  call    cs:__imp_FsRtlDoesNameContainWildCards
0x140015038  nop     dword ptr [rax+rax+00h]
0x14001503d  test    al, al
0x14001503f  jnz     short loc_1400150BE
0x140015041  mov     rax, [rbp+60h+var_C8]
0x140015045  mov     r9d, edi
0x140015048  mov     rcx, [rbp+60h+Context]
0x14001504c  mov     r8, [rbp+60h+var_C0]
0x140015050  mov     rdx, [rbp+60h+Instance]
0x140015054  mov     [rsp+160h+var_F8], rax
0x140015059  mov     rcx, [rcx+40h]
0x14001505d  mov     al, [rbp+60h+arg_40]
0x140015063  mov     [rsp+160h+var_100], al
0x140015067  mov     rax, [rbp+60h+var_A8]
0x14001506b  mov     [rsp+160h+var_108], rax
0x140015070  mov     eax, [rcx]
0x140015072  mov     rcx, qword ptr [rbp+60h+Size+4]
0x140015076  mov     [rsp+160h+var_110], r12d
0x14001507b  mov     dword ptr [rsp+160h+var_120], eax
0x14001507f  mov     al, [rbp+60h+arg_28]
0x140015085  mov     byte ptr [rsp+160h+var_128], al
0x140015089  mov     rax, [rbp+60h+Name]
0x14001508d  mov     dword ptr [rsp+160h+var_130], esi
0x140015091  mov     [rsp+160h+var_138], rax
0x140015096  mov     dword ptr [rsp+160h+Timeout], r15d
0x14001509b  call    WcEnumerateDirectorySingleEntry
0x1400150a0  mov     r14d, eax
0x1400150a3  test    eax, eax
0x1400150a5  jnz     loc_140015374
0x1400150ab  cmp     byte ptr [rsp+160h+var_EC], al
0x1400150af  jnz     loc_140015374
0x1400150b5  or      dword ptr [rbx+28h], 2
0x1400150b9  jmp     loc_140015374
0x1400150be  lea     r8, [rbx+30h]
0x1400150c2  cmp     [r8], r8
0x1400150c5  jnz     short loc_14001510D
0x1400150c7  mov     rcx, [rbp+60h+var_C0]
0x1400150cb  call    cs:__imp_IoGetSilo
0x1400150d2  nop     dword ptr [rax+rax+00h]
0x1400150d7  mov     rcx, rax
0x1400150da  call    cs:__imp_PsGetParentSilo
0x1400150e1  nop     dword ptr [rax+rax+00h]
0x1400150e6  mov     rcx, qword ptr [rbp+60h+Size+4]
0x1400150ea  lea     r8, [rbx+30h]
0x1400150ee  add     rcx, 38h ; '8'
0x1400150f2  mov     rdx, rax
0x1400150f5  call    WcCopySourceList
0x1400150fa  mov     r14d, eax
0x1400150fd  test    eax, eax
0x1400150ff  js      loc_140015374
0x140015105  or      dword ptr [rbx+28h], 4
0x140015109  lea     r8, [rbx+30h]
0x14001510d  xor     r9d, r9d
0x140015110  xor     cl, cl
0x140015112  xor     r12d, r12d
0x140015115  mov     [rsp+160h+var_EC], r9d
0x14001511a  cmp     byte ptr [rbp+60h+var_D8], cl
0x14001511d  jz      loc_14001528F
0x140015123  mov     [rbx+48h], r9d
0x140015127  mov     [rbx+254h], r9d
0x14001512e  or      dword ptr [rbx+28h], 4
0x140015132  mov     dl, [rbp+60h+arg_28]
0x140015138  mov     r10d, 0C000000Fh
0x14001513e  test    cl, cl
0x140015140  jnz     loc_140015346
0x140015146  cmp     r9d, [rbp+60h+arg_30]
0x14001514d  jnb     loc_140015346
  ... truncated ...
```
