# SqospHandleControlRequest

- ea: `0x140014d10`
- end: `0x140015565`
- name: `SqospHandleControlRequest`
- size: `2133`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140014950`

## callees

- `0x140003940`
- `0x1400039c0`
- `0x140003d90`
- `0x140003fc0`
- `0x140004520`
- `0x14000603c`
- `0x140006188`
- `0x140006324`
- `0x140006424`
- `0x14000666c`
- `0x140007e78`
- `0x14000829c`
- `0x140008304`
- `0x140008368`
- `0x1400117e4`
- `0x140014d10`

## import_xrefs

- `ntoskrnl!SeAccessCheck` at `0x140015101`
- `ntoskrnl!SeAccessCheck` at `0x140015101`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400150bb`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400150bb`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140015119`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140015119`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400150aa`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400150aa`
- `FLTMGR!FltGetStreamHandleContext` at `0x14001513c`
- `FLTMGR!FltGetStreamHandleContext` at `0x14001513c`
- `FLTMGR!FltReleaseContext` at `0x1400154bf`
- `FLTMGR!FltReleaseContext` at `0x1400154f2`
- `FLTMGR!FltReleaseContext` at `0x1400154bf`
- `FLTMGR!FltReleaseContext` at `0x1400154f2`
- `FLTMGR!FltGetInstanceContext` at `0x14001521a`
- `FLTMGR!FltGetInstanceContext` at `0x14001521a`

## pseudocode

```c
__int64 __fastcall SqospHandleControlRequest(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  unsigned int v6; // ecx
  unsigned __int16 *v7; // rsi
  __int64 v8; // r15
  int v9; // ebx
  unsigned int v10; // edx
  unsigned int v11; // eax
  unsigned int v12; // r8d
  __int64 v13; // rsi
  __int64 v14; // r12
  unsigned __int64 v15; // r9
  unsigned __int64 v16; // rax
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  unsigned int v20; // ecx
  int v21; // eax
  unsigned int v22; // ecx
  KPROCESSOR_MODE AccessMode; // di
  struct _GENERIC_MAPPING *GenericMapping; // rax
  __int64 v25; // r8
  int v26; // r9d
  __int64 StreamHandleContextClient; // rax
  __int64 v28; // rdx
  int v29; // eax
  int StreamHandleContext; // eax
  __int64 v31; // rcx
  PDEVICE_OBJECT v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rax
  int PreviouslyGrantedAccess; // [rsp+28h] [rbp-39h]
  PFLT_CONTEXT Context; // [rsp+58h] [rbp-9h] BYREF
  PFLT_CONTEXT v38; // [rsp+60h] [rbp-1h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+68h] [rbp+7h] BYREF
  int AccessStatus; // [rsp+C8h] [rbp+67h] BYREF
  unsigned int v41; // [rsp+D8h] [rbp+77h]
  DWORD GrantedAccess; // [rsp+E0h] [rbp+7Fh] BYREF

  v3 = *(_QWORD *)(a1 + 16);
  AccessStatus = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  GrantedAccess = 0;
  Context = 0;
  v38 = 0;
  if ( *(_DWORD *)(v3 + 32) < 8u )
  {
    v6 = -1073741811;
    AccessStatus = -1073741811;
    goto LABEL_146;
  }
  v7 = *(unsigned __int16 **)(v3 + 48);
  v8 = 0;
  v9 = *((_DWORD *)v7 + 1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_DDq(WPP_GLOBAL_Control->AttachedDevice, a2, a3, *v7, v9, *(_QWORD *)(a2 + 32));
  }
  if ( *v7 == 256 )
  {
    v10 = 112;
    v11 = 88;
    goto LABEL_12;
  }
  if ( *v7 == 257 )
  {
    v10 = 128;
    v11 = 96;
LABEL_12:
    v12 = *(_DWORD *)(v3 + 32);
    v41 = v11;
    if ( v12 < v10 || !v9 )
      goto LABEL_138;
    v13 = *(_QWORD *)(v3 + 48);
    v14 = 0;
    if ( (v9 & 8) != 0 )
    {
      if ( *(_DWORD *)(v3 + 24) < v11 )
      {
LABEL_138:
        v6 = -1073741811;
        goto LABEL_139;
      }
      v14 = *(_QWORD *)(v3 + 48);
    }
    if ( (v9 & 4) != 0 && (unsigned __int8)SqospIsNullGuid(v13 + 8) )
      goto LABEL_138;
    if ( (v9 & 6) != 0 )
    {
      if ( (unsigned __int8)SqospIsNullGuid(v13 + 24) )
      {
        if ( v15 > 0x3B9ACA00
          || *(_WORD *)v13 >= 0x101u && *(_QWORD *)(v13 + 112) > 0x3B9ACA00u
          || (v16 = *(_QWORD *)(v13 + 64), v16 > 0x3B9ACA00)
          || v15 && v15 < v16 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_III(WPP_GLOBAL_Control->AttachedDevice);
          }
          goto LABEL_138;
        }
      }
      else if ( v15 || *(_QWORD *)(v13 + 64) || *(_WORD *)v13 >= 0x101u && *(_QWORD *)(v13 + 112) )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_138;
        }
        v18 = 35;
        goto LABEL_137;
      }
    }
    v19 = *(unsigned __int16 *)(v13 + 74);
    if ( *(_DWORD *)(v13 + 72) )
    {
      if ( (v19 & 1) != 0 || (unsigned __int16)v19 > 0x200u )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_138;
        }
        v18 = 36;
        goto LABEL_137;
      }
      v20 = *(unsigned __int16 *)(v13 + 72);
      if ( v20 < v10 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_138;
        }
        v18 = 37;
        goto LABEL_137;
      }
      if ( v20 + v19 > v12 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_138;
        }
        v18 = 38;
        goto LABEL_137;
      }
    }
    v21 = *(unsigned __int16 *)(v13 + 78);
    if ( !*(_DWORD *)(v13 + 76) )
      goto LABEL_65;
    if ( (v21 & 1) == 0 && (unsigned __int16)v21 <= 0x200u )
    {
      v22 = *(unsigned __int16 *)(v13 + 76);
      if ( v22 < v10 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_138;
        }
        v18 = 40;
        goto LABEL_137;
      }
      if ( v22 + v21 > v12 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_138;
        }
        v18 = 41;
        goto LABEL_137;
      }
LABEL_65:
      if ( *(_BYTE *)(a1 + 80) )
      {
        SeCaptureSubjectContext(&SubjectContext);
        AccessMode = *(_BYTE *)(a1 + 80);
        GenericMapping = IoGetFileObjectGenericMapping();
        if ( SeAccessCheck(
               SecurityDescriptor,
               &SubjectContext,
               0,
               2u,
               0,
               0,
               GenericMapping,
               AccessMode,
               &GrantedAccess,
               &AccessStatus) )
        {
          AccessStatus = 0;
        }
        SeReleaseSubjectContext(&SubjectContext);
        v6 = AccessStatus;
        if ( AccessStatus < 0 )
          goto LABEL_140;
      }
      AccessStatus = FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context);
      v6 = AccessStatus;
      if ( (int)(AccessStatus + 0x80000000) >= 0 && AccessStatus != -1073741275 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            42,
            WPP_97d16c38264433ff5e04fa48b3a3652b_Traceguids,
            (unsigned int)AccessStatus);
          v6 = AccessStatus;
        }
        goto LABEL_140;
      }
      if ( Context )
      {
        StreamHandleContextClient = SqospGetStreamHandleContextClient(Context);
        v8 = StreamHandleContextClient;
        if ( StreamHandleContextClient && !*(_BYTE *)(StreamHandleContextClient + 124) )
          v9 &= ~4u;
        v6 = AccessStatus;
      }
      if ( (v9 & 0x10000000) != 0 && (v9 & 1) == 0 )
        v9 &= ~0x10000000u;
      if ( (v9 & 5) == 0 )
        goto LABEL_100;
      if ( v8 )
      {
        v28 = *(_QWORD *)(v8 + 88) - *(_QWORD *)(v13 + 8);
        if ( !v28 )
          v28 = *(_QWORD *)(v8 + 96) - *(_QWORD *)(v13 + 16);
        if ( !v28 )
        {
          if ( (v9 & 1) == 0 )
            goto LABEL_100;
          goto LABEL_92;
        }
        SqospReleaseClient((PVOID)v8);
        v8 = 0;
      }
      AccessStatus = FltGetInstanceContext(*(PFLT_INSTANCE *)(a2 + 24), &v38);
      if ( AccessStatus < 0 )
      {
        v6 = -1073741591;
        goto LABEL_139;
      }
      if ( (unsigned __int8)SqospIsNullGuid(v13 + 8) )
      {
        SqospAddRefClient(*((_QWORD *)v38 + 22));
        v8 = *((_QWORD *)v38 + 22);
      }
      else
      {
        v8 = SqospLookupClient(v31, v38, a1);
        if ( !v8 )
        {
          v6 = -1073741670;
          goto LABEL_139;
        }
      }
LABEL_92:
      v29 = v9 & 0x10000000;
      if ( Context )
      {
        LOBYTE(PreviouslyGrantedAccess) = v29 != 0;
        StreamHandleContext = SqospModifyStreamHandleContext(a1, a2, Context, v8, PreviouslyGrantedAccess);
      }
      else
      {
        LOBYTE(v26) = v29 != 0;
        StreamHandleContext = SqospCreateStreamHandleContext(a1, a2, v8, v26, 1, (__int64)&Context);
      }
      AccessStatus = StreamHandleContext;
      v6 = StreamHandleContext;
      if ( StreamHandleContext < 0 )
        goto LABEL_140;
LABEL_100:
      if ( !Context )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        {
          goto LABEL_106;
        }
        v33 = 43;
LABEL_105:
        WPP_SF_q(v32->AttachedDevice, v33, v25, *(_QWORD *)(a2 + 32));
LABEL_106:
        v6 = -1073741275;
        goto LABEL_139;
      }
      if ( (v9 & 6) != 0 )
      {
        if ( *(_BYTE *)(v8 + 124) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_97d16c38264433ff5e04fa48b3a3652b_Traceguids, v6);
            v6 = -1073741275;
            goto LABEL_139;
          }
          goto LABEL_106;
        }
        if ( (v9 & 2) != 0 || !(unsigned __int8)SqospProbeClientPolicy((PKSPIN_LOCK)v8) )
        {
          AccessStatus = SqospUpdateClientPolicy((PKSPIN_LOCK)v8, v13);
          v6 = AccessStatus;
          if ( AccessStatus < 0 )
            goto LABEL_140;
        }
      }
      if ( v14 )
      {
        if ( *(_BYTE *)(v8 + 124) )
        {
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
          {
            goto LABEL_106;
          }
          v33 = 45;
          goto LABEL_105;
        }
      }
      else if ( (v9 & 0x10) == 0 )
      {
LABEL_125:
        if ( v14 )
        {
          *(_WORD *)v14 = *(_WORD *)v13;
          v34 = v41;
          *(_DWORD *)(v14 + 4) = 0;
        }
        else
        {
          v34 = 0;
        }
        *(_QWORD *)(a1 + 32) = v34;
        v6 = 0;
        goto LABEL_139;
      }
      SqospGetClientStatusInfo((PKSPIN_LOCK)v8);
      goto LABEL_125;
    }
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_138;
    }
    v18 = 39;
LABEL_137:
    WPP_SF_(v17->AttachedDevice, v18, WPP_97d16c38264433ff5e04fa48b3a3652b_Traceguids);
    goto LABEL_138;
  }
  v6 = -1073741735;
LABEL_139:
  AccessStatus = v6;
LABEL_140:
  if ( Context )
  {
    FltReleaseContext(Context);
    v6 = AccessStatus;
  }
  if ( v8 )
  {
    SqospReleaseClient((PVOID)v8);
    v6 = AccessStatus;
  }
  if ( v38 )
  {
    FltReleaseContext(v38);
    v6 = AccessStatus;
  }
LABEL_146:
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
  {
    return v6;
  }
  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_97d16c38264433ff5e04fa48b3a3652b_Traceguids, v6);
  return (unsigned int)AccessStatus;
}

```

## disassembly

```asm
0x140014d10  mov     rax, rsp
0x140014d13  push    rbp
0x140014d14  lea     rbp, [rax-5Fh]
0x140014d18  sub     rsp, 0B0h
0x140014d1f  xor     r11d, r11d
0x140014d22  mov     [rax-18h], rdi
0x140014d26  mov     rdi, [rcx+10h]
0x140014d2a  xorps   xmm0, xmm0
0x140014d2d  mov     [rax-20h], r12
0x140014d31  lea     r12, WPP_GLOBAL_Control
0x140014d38  mov     [rax-28h], r13
0x140014d3c  mov     r13, rdx
0x140014d3f  mov     [rbp+57h+AccessStatus], r11d
0x140014d43  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x140014d47  mov     [rbp+57h+arg_18], r11d
0x140014d4b  movups  xmmword ptr [rbp+17h], xmm0
0x140014d4f  mov     [rbp+57h+Context], r11
0x140014d53  mov     [rbp+57h+var_58], r11
0x140014d57  cmp     dword ptr [rdi+20h], 8
0x140014d5b  mov     [rax-30h], r14
0x140014d5f  mov     r14, rcx
0x140014d62  jnb     short loc_140014D71
0x140014d64  mov     ecx, 0C000000Dh
0x140014d69  mov     [rbp+57h+AccessStatus], ecx
0x140014d6c  jmp     loc_140015501
0x140014d71  mov     [rsp+0B0h+arg_8], rbx
0x140014d79  mov     [rsp+0A8h], rsi
0x140014d81  mov     rsi, [rdi+30h]
0x140014d85  mov     [rsp+0B0h+var_30], r15
0x140014d8d  mov     r15, r11
0x140014d90  mov     ebx, [rsi+4]
0x140014d93  mov     rcx, cs:WPP_GLOBAL_Control
0x140014d9a  cmp     rcx, r12
0x140014d9d  jz      short loc_140014DC9
0x140014d9f  mov     eax, [rcx+2Ch]
0x140014da2  test    al, 4
0x140014da4  jz      short loc_140014DC9
0x140014da6  cmp     byte ptr [rcx+29h], 4
0x140014daa  jb      short loc_140014DC9
0x140014dac  mov     rax, [rdx+20h]
0x140014db0  movzx   r9d, word ptr [rsi]
0x140014db4  mov     rcx, [rcx+18h]
0x140014db8  mov     [rsp+0B0h+Privileges], rax
0x140014dbd  mov     [rsp+0B0h+PreviouslyGrantedAccess], ebx
0x140014dc1  call    WPP_SF_DDq
0x140014dc6  xor     r11d, r11d
0x140014dc9  movzx   ecx, word ptr [rsi]
0x140014dcc  sub     ecx, 100h
0x140014dd2  jz      short loc_140014DEF
0x140014dd4  cmp     ecx, 1
0x140014dd7  jz      short loc_140014DE3
0x140014dd9  mov     ecx, 0C0000059h
0x140014dde  jmp     loc_1400154A0
0x140014de3  mov     edx, 80h
0x140014de8  mov     eax, 60h ; '`'
0x140014ded  jmp     short loc_140014DF9
0x140014def  mov     edx, 70h ; 'p'
0x140014df4  mov     eax, 58h ; 'X'
0x140014df9  mov     r8d, [rdi+20h]
0x140014dfd  mov     [rbp+57h+arg_10], eax
0x140014e00  cmp     r8d, edx
0x140014e03  jb      loc_14001549B
0x140014e09  test    ebx, ebx
0x140014e0b  jz      loc_14001549B
0x140014e11  mov     rsi, [rdi+30h]
0x140014e15  mov     r12, r11
0x140014e18  test    bl, 8
0x140014e1b  jz      short loc_140014E31
0x140014e1d  cmp     [rdi+18h], eax
0x140014e20  jnb     short loc_140014E2E
0x140014e22  lea     r12, WPP_GLOBAL_Control
0x140014e29  jmp     loc_14001549B
0x140014e2e  mov     r12, rsi
0x140014e31  test    bl, 4
0x140014e34  jz      short loc_140014E4F
0x140014e36  lea     rcx, [rsi+8]
0x140014e3a  call    SqospIsNullGuid
0x140014e3f  test    al, al
0x140014e41  jz      short loc_140014E4F
0x140014e43  lea     r12, WPP_GLOBAL_Control
0x140014e4a  jmp     loc_14001549B
0x140014e4f  test    bl, 6
0x140014e52  jz      loc_140014F54
0x140014e58  mov     r9, [rsi+38h]
0x140014e5c  lea     rcx, [rsi+18h]
0x140014e60  call    SqospIsNullGuid
0x140014e65  test    al, al
0x140014e67  jz      loc_140014F01
0x140014e6d  mov     r10d, 101h
0x140014e73  cmp     r9, 3B9ACA00h
0x140014e7a  ja      short loc_140014EAA
0x140014e7c  cmp     [rsi], r10w
0x140014e80  jb      short loc_140014E8C
0x140014e82  cmp     qword ptr [rsi+70h], 3B9ACA00h
0x140014e8a  ja      short loc_140014EAA
0x140014e8c  mov     rax, [rsi+40h]
0x140014e90  cmp     rax, 3B9ACA00h
0x140014e96  ja      short loc_140014EAA
0x140014e98  test    r9, r9
0x140014e9b  jz      loc_140014F54
0x140014ea1  cmp     r9, rax
0x140014ea4  jnb     loc_140014F54
0x140014eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x140014eb1  lea     r12, WPP_GLOBAL_Control
0x140014eb8  cmp     rcx, r12
0x140014ebb  jz      loc_14001549B
0x140014ec1  mov     eax, [rcx+2Ch]
0x140014ec4  test    al, 4
0x140014ec6  jz      loc_14001549B
0x140014ecc  cmp     byte ptr [rcx+29h], 2
0x140014ed0  jb      loc_14001549B
0x140014ed6  cmp     [rsi], r10w
0x140014eda  jb      short loc_140014EE2
0x140014edc  mov     rax, [rsi+70h]
0x140014ee0  jmp     short loc_140014EE5
0x140014ee2  mov     rax, r11
0x140014ee5  mov     rcx, [rcx+18h]
0x140014ee9  mov     [rsp+0B0h+Privileges], rax
0x140014eee  mov     rax, [rsi+40h]
0x140014ef2  mov     qword ptr [rsp+0B0h+PreviouslyGrantedAccess], rax
0x140014ef7  call    WPP_SF_III
0x140014efc  jmp     loc_14001549B
0x140014f01  test    r9, r9
0x140014f04  jnz     short loc_140014F1E
0x140014f06  cmp     [rsi+40h], r15
0x140014f0a  jnz     short loc_140014F1E
0x140014f0c  mov     r10d, 101h
0x140014f12  cmp     [rsi], r10w
0x140014f16  jb      short loc_140014F54
0x140014f18  cmp     [rsi+70h], r15
0x140014f1c  jz      short loc_140014F54
0x140014f1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f25  lea     r12, WPP_GLOBAL_Control
0x140014f2c  cmp     rcx, r12
0x140014f2f  jz      loc_14001549B
0x140014f35  mov     eax, [rcx+2Ch]
0x140014f38  test    al, 4
0x140014f3a  jz      loc_14001549B
0x140014f40  cmp     byte ptr [rcx+29h], 2
0x140014f44  jb      loc_14001549B
0x140014f4a  mov     edx, 23h ; '#'
0x140014f4f  jmp     loc_14001548B
0x140014f54  movzx   eax, word ptr [rsi+4Ah]
0x140014f58  mov     r9d, 200h
0x140014f5e  test    ax, ax
0x140014f61  jnz     short loc_140014F6E
0x140014f63  cmp     [rsi+48h], r15w
0x140014f68  jbe     loc_140014FFB
0x140014f6e  test    al, 1
0x140014f70  jnz     loc_140015466
0x140014f76  cmp     ax, r9w
0x140014f7a  ja      loc_140015466
0x140014f80  movzx   ecx, word ptr [rsi+48h]
0x140014f84  cmp     ecx, edx
0x140014f86  jnb     short loc_140014FBE
0x140014f88  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f8f  lea     r12, WPP_GLOBAL_Control
0x140014f96  cmp     rcx, r12
0x140014f99  jz      loc_14001549B
0x140014f9f  mov     eax, [rcx+2Ch]
0x140014fa2  test    al, 4
0x140014fa4  jz      loc_14001549B
0x140014faa  cmp     byte ptr [rcx+29h], 2
0x140014fae  jb      loc_14001549B
0x140014fb4  mov     edx, 25h ; '%'
0x140014fb9  jmp     loc_14001548B
0x140014fbe  add     eax, ecx
0x140014fc0  cmp     eax, r8d
0x140014fc3  jbe     short loc_140014FFB
0x140014fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140014fcc  lea     r12, WPP_GLOBAL_Control
0x140014fd3  cmp     rcx, r12
0x140014fd6  jz      loc_14001549B
0x140014fdc  mov     eax, [rcx+2Ch]
0x140014fdf  test    al, 4
0x140014fe1  jz      loc_14001549B
0x140014fe7  cmp     byte ptr [rcx+29h], 2
0x140014feb  jb      loc_14001549B
0x140014ff1  mov     edx, 26h ; '&'
0x140014ff6  jmp     loc_14001548B
0x140014ffb  movzx   eax, word ptr [rsi+4Eh]
0x140014fff  test    ax, ax
0x140015002  jnz     short loc_14001500F
0x140015004  cmp     [rsi+4Ch], r15w
0x140015009  jbe     loc_14001509C
0x14001500f  test    al, 1
0x140015011  jnz     loc_14001543F
0x140015017  cmp     ax, r9w
0x14001501b  ja      loc_14001543F
0x140015021  movzx   ecx, word ptr [rsi+4Ch]
0x140015025  cmp     ecx, edx
0x140015027  jnb     short loc_14001505F
0x140015029  mov     rcx, cs:WPP_GLOBAL_Control
0x140015030  lea     r12, WPP_GLOBAL_Control
0x140015037  cmp     rcx, r12
0x14001503a  jz      loc_14001549B
0x140015040  mov     eax, [rcx+2Ch]
0x140015043  test    al, 4
0x140015045  jz      loc_14001549B
0x14001504b  cmp     byte ptr [rcx+29h], 2
0x14001504f  jb      loc_14001549B
0x140015055  mov     edx, 28h ; '('
0x14001505a  jmp     loc_14001548B
0x14001505f  add     eax, ecx
0x140015061  cmp     eax, r8d
0x140015064  jbe     short loc_14001509C
0x140015066  mov     rcx, cs:WPP_GLOBAL_Control
0x14001506d  lea     r12, WPP_GLOBAL_Control
0x140015074  cmp     rcx, r12
0x140015077  jz      loc_14001549B
0x14001507d  mov     eax, [rcx+2Ch]
0x140015080  test    al, 4
0x140015082  jz      loc_14001549B
0x140015088  cmp     byte ptr [rcx+29h], 2
0x14001508c  jb      loc_14001549B
0x140015092  mov     edx, 29h ; ')'
0x140015097  jmp     loc_14001548B
0x14001509c  cmp     [r14+50h], r15b
0x1400150a0  jz      loc_140015130
0x1400150a6  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400150aa  call    cs:__imp_SeCaptureSubjectContext
0x1400150b1  nop     dword ptr [rax+rax+00h]
0x1400150b6  movzx   edi, byte ptr [r14+50h]
0x1400150bb  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400150c2  nop     dword ptr [rax+rax+00h]
0x1400150c7  lea     rcx, [rbp+57h+AccessStatus]
0x1400150cb  mov     r9d, 2; DesiredAccess
0x1400150d1  mov     [rsp+48h], rcx; AccessStatus
0x1400150d6  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x1400150da  lea     rcx, [rbp+57h+arg_18]
0x1400150de  xor     r8d, r8d; SubjectContextLocked
0x1400150e1  mov     [rsp+0B0h+GrantedAccess], rcx; GrantedAccess
0x1400150e6  mov     rcx, cs:SecurityDescriptor; SecurityDescriptor
0x1400150ed  mov     [rsp+0B0h+AccessMode], dil; AccessMode
0x1400150f2  mov     [rsp+0B0h+GenericMapping], rax; GenericMapping
0x1400150f7  mov     [rsp+0B0h+Privileges], r15; Privileges
0x1400150fc  mov     [rsp+0B0h+PreviouslyGrantedAccess], r15d; PreviouslyGrantedAccess
0x140015101  call    cs:__imp_SeAccessCheck
0x140015108  nop     dword ptr [rax+rax+00h]
0x14001510d  test    al, al
0x14001510f  jz      short loc_140015115
0x140015111  mov     [rbp+57h+AccessStatus], r15d
0x140015115  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140015119  call    cs:__imp_SeReleaseSubjectContext
0x140015120  nop     dword ptr [rax+rax+00h]
0x140015125  mov     ecx, [rbp+57h+AccessStatus]
0x140015128  test    ecx, ecx
0x14001512a  js      loc_1400153B2
0x140015130  mov     rdx, [r13+20h]; FileObject
0x140015134  lea     r8, [rbp+57h+Context]; Context
0x140015138  mov     rcx, [r13+18h]; Instance
0x14001513c  call    cs:__imp_FltGetStreamHandleContext
0x140015143  nop     dword ptr [rax+rax+00h]
0x140015148  mov     edx, 80000000h
0x14001514d  mov     [rbp+57h+AccessStatus], eax
0x140015150  mov     ecx, eax
0x140015152  add     eax, edx
0x140015154  test    edx, eax
0x140015156  jnz     short loc_1400151AE
0x140015158  cmp     ecx, 0C0000225h
0x14001515e  jz      short loc_1400151AE
0x140015160  mov     r10, cs:WPP_GLOBAL_Control
0x140015167  lea     r12, WPP_GLOBAL_Control
0x14001516e  cmp     r10, r12
0x140015171  jz      loc_1400154A3
0x140015177  mov     eax, [r10+2Ch]
0x14001517b  test    al, 4
0x14001517d  jz      loc_1400154A3
0x140015183  cmp     byte ptr [r10+29h], 2
0x140015188  jb      loc_1400154A3
0x14001518e  mov     r9d, ecx
0x140015191  lea     r8, WPP_97d16c38264433ff5e04fa48b3a3652b_Traceguids
0x140015198  mov     rcx, [r10+18h]
0x14001519c  mov     edx, 2Ah ; '*'
0x1400151a1  call    WPP_SF_d
0x1400151a6  mov     ecx, [rbp+57h+AccessStatus]
0x1400151a9  jmp     loc_1400154A3
0x1400151ae  mov     rdx, [rbp+57h+Context]
0x1400151b2  test    rdx, rdx
0x1400151b5  jz      short loc_1400151D3
0x1400151b7  mov     rcx, rdx
0x1400151ba  call    SqospGetStreamHandleContextClient
0x1400151bf  mov     r15, rax
0x1400151c2  test    rax, rax
0x1400151c5  jz      short loc_1400151D0
0x1400151c7  cmp     byte ptr [rax+7Ch], 0
0x1400151cb  jnz     short loc_1400151D0
0x1400151cd  and     ebx, 0FFFFFFFBh
0x1400151d0  mov     ecx, [rbp+57h+AccessStatus]
0x1400151d3  bt      ebx, 1Ch
0x1400151d7  jnb     short loc_1400151E2
0x1400151d9  test    bl, 1
0x1400151dc  jnz     short loc_1400151E2
0x1400151de  btr     ebx, 1Ch
0x1400151e2  test    bl, 5
0x1400151e5  jz      loc_1400152EE
0x1400151eb  test    r15, r15
0x1400151ee  jz      short loc_140015212
0x1400151f0  mov     rdx, [r15+58h]
0x1400151f4  sub     rdx, [rsi+8]
  ... truncated ...
```
