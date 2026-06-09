# WlRemindersDisplay(WlReminderType,void *,void *,int)

- ea: `0x140077464`
- end: `0x140077e7e`
- name: `?WlRemindersDisplay@@YAKW4WlReminderType@@PEAX1H@Z`
- size: `2586`
- prototype: ``
- caller_count: `11`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14002d59c`
- `0x1400332c0`
- `0x140047370`
- `0x1400656f0`
- `0x14006cb70`
- `0x14006def0`
- `0x14006e0f0`
- `0x14006e850`
- `0x140071dc0`
- `0x140072040`
- `0x1400822c0`

## callees

- `0x1400057f4`
- `0x1400064b0`
- `0x14000d4e0`
- `0x1400198e0`
- `0x14001a200`
- `0x14001a520`
- `0x140027310`
- `0x140041c34`
- `0x1400544e0`
- `0x140077464`
- `0x140078138`
- `0x1400784e0`
- `0x1400787d4`
- `0x140078a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140077cd9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140077cd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140077d4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140077d4a`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x140077a00`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x140077a00`

## string_xrefs

- `0x140077aa0`: `shell32.dll,-194`
- `0x140077614`: `shell32.dll,-220`
- `0x1400777ef`: `shell32.dll,-11`
- `0x14007770f`: `shell32.dll,-48`
- `0x140077942`: `shell32.dll,-48`
- `0x140077c0d`: `shell32.dll,-48`
- `0x140077831`: `Microsoft.CachedLogon`

## pseudocode

```c
__int64 __fastcall WlRemindersDisplay(int a1, unsigned __int16 *a2, _BYTE *a3, int a4)
{
  unsigned int v7; // ebx
  unsigned __int16 *String; // rsi
  unsigned __int16 *v9; // rdi
  unsigned __int16 *v10; // r12
  __int64 v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  unsigned __int16 *v14; // rax
  unsigned int v15; // ebx
  char v16; // al
  unsigned __int16 *v17; // rax
  unsigned __int16 v18; // cx
  int v19; // eax
  unsigned __int16 *v20; // rax
  unsigned __int16 v21; // cx
  unsigned __int16 *v22; // rax
  unsigned __int16 v23; // cx
  unsigned __int16 *v24; // r13
  unsigned int v25; // r13d
  unsigned __int16 v26; // cx
  unsigned __int16 *v27; // r14
  struct CUser *v28; // rbx
  int SystemMetrics; // eax
  _BYTE *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rax
  unsigned __int64 v34; // rbx
  unsigned __int16 *v35; // rax
  unsigned __int16 v36; // cx
  int v37; // ebx
  int v38; // r12d
  int v39; // edx
  int v40; // r8d
  CUser *v41; // rcx
  HANDLE *v42; // r12
  unsigned __int16 *v44; // [rsp+48h] [rbp-110h]
  unsigned __int16 *v45; // [rsp+50h] [rbp-108h] BYREF
  unsigned __int16 *v46; // [rsp+58h] [rbp-100h] BYREF
  unsigned __int16 *v47; // [rsp+60h] [rbp-F8h] BYREF
  unsigned __int16 *v48; // [rsp+68h] [rbp-F0h] BYREF
  __int128 v49; // [rsp+70h] [rbp-E8h] BYREF
  unsigned __int16 *v50[2]; // [rsp+80h] [rbp-D8h]
  __int128 v51; // [rsp+90h] [rbp-C8h]
  __int128 v52; // [rsp+A0h] [rbp-B8h]
  __int128 v53; // [rsp+B0h] [rbp-A8h]
  int v54; // [rsp+C0h] [rbp-98h]
  _OWORD v55[5]; // [rsp+D0h] [rbp-88h] BYREF
  _BYTE *v56; // [rsp+120h] [rbp-38h]

  v7 = 87;
  memset_0(&v49, 0, 0x50u);
  *(_QWORD *)&v55[0] = 0;
  memset_0((char *)v55 + 8, 0, 0x50u);
  v45 = 0;
  String = 0;
  v46 = 0;
  v9 = 0;
  v47 = 0;
  v10 = 0;
  v44 = 0;
  v48 = 0;
  if ( !qword_1400D2560 )
    goto LABEL_112;
  if ( a1 > 6 )
  {
    switch ( a1 )
    {
      case 7:
        if ( a2 )
        {
          LODWORD(v49) = 80;
          *((_QWORD *)&v49 + 1) = L"Microsoft.SubscriberFailed";
          String = AllocAndLoadString(0x76Eu, qword_1400D2560);
          v50[0] = String;
          v46 = String;
          v50[1] = a2;
          goto LABEL_86;
        }
        goto LABEL_112;
      case 8:
        LODWORD(v49) = 80;
        *((_QWORD *)&v49 + 1) = L"Microsoft.SmartCardUnlockRequired";
        v35 = AllocAndLoadString(0x801u, qword_1400D2560);
        v36 = 2048;
        break;
      case 9:
        LODWORD(v49) = 80;
        *((_QWORD *)&v49 + 1) = L"Microsoft.SmartCardUnlockRequired";
        v35 = AllocAndLoadString(0x803u, qword_1400D2560);
        v36 = 2050;
        break;
      case 10:
      case 11:
        goto LABEL_51;
      case 13:
        LODWORD(v49) = 80;
        *((_QWORD *)&v49 + 1) = L"Microsoft.NTLMDisabledWarning";
        String = AllocAndLoadString(0x807u, qword_1400D2560);
        v50[0] = String;
        v46 = String;
        v22 = AllocAndLoadString(0x808u, qword_1400D2560);
        v23 = 2054;
LABEL_50:
        v50[1] = v22;
        v47 = v22;
        v9 = v22;
        v24 = AllocAndLoadString(v23, qword_1400D2560);
        *(_QWORD *)&v51 = v24;
        v48 = v24;
        *((_QWORD *)&v51 + 1) = L"shell32.dll,-48";
        HIDWORD(v53) = 2;
        LODWORD(v53) = 60000;
        goto LABEL_88;
      default:
LABEL_45:
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            WPP_45f944bba9fd33a68794881c2280ffd4_Traceguids,
            (unsigned int)a1);
        }
        goto LABEL_112;
    }
    v50[0] = v35;
    v46 = v35;
    String = v35;
    v22 = AllocAndLoadString(v36, qword_1400D2560);
    v23 = 2040;
    goto LABEL_50;
  }
  switch ( a1 )
  {
    case 6:
      LODWORD(v49) = 80;
      *((_QWORD *)&v49 + 1) = L"Microsoft.CachedLogon";
      v20 = AllocAndLoadString(0x7FBu, qword_1400D2560);
      v21 = 2044;
      goto LABEL_36;
    case 0:
LABEL_51:
      if ( a4 || !a2 )
        goto LABEL_112;
      v25 = *(_DWORD *)a2;
      v54 = 0;
      if ( v25 == -1 )
      {
        if ( a1 == 10 )
          a1 = 12;
        v26 = 2009;
      }
      else if ( v25 )
      {
        v26 = 2011;
        if ( v25 == 1 )
          v26 = 2027;
      }
      else
      {
        v26 = 2012;
      }
      v27 = AllocAndLoadString(v26, qword_1400D2560);
      v45 = v27;
      if ( v27 )
      {
        if ( a1 )
        {
          v30 = a3;
          if ( !a3 )
            goto LABEL_63;
          if ( a1 != 12 )
          {
            v10 = AllocAndLoadString(0x805u, qword_1400D2560);
            v44 = v10;
            v48 = v10;
            v30 = a3;
          }
          v56 = v30;
        }
        else
        {
          v28 = qword_1400D2560;
          SystemMetrics = GetSystemMetrics(4096);
          v10 = AllocAndLoadString(SystemMetrics != 0 ? 2046 : 2028, v28);
          v44 = v10;
          v48 = v10;
        }
        LODWORD(v49) = 80;
        *((_QWORD *)&v49 + 1) = L"Microsoft.PasswordExpiryWarning";
        String = AllocAndLoadString(0x7DAu, qword_1400D2560);
        v50[0] = String;
        v46 = String;
        *((_QWORD *)&v51 + 1) = L"shell32.dll,-194";
        HIDWORD(v53) = 1;
        LODWORD(v53) = 60000;
        v31 = -1;
        v32 = -1;
        do
          ++v32;
        while ( v27[v32] );
        v33 = (unsigned int)(v32 + 11);
        v54 = v33;
        if ( v10 )
        {
          do
            ++v31;
          while ( v10[v31] );
          v33 = (unsigned int)(v31 + v33);
          v54 = v33;
        }
        v34 = (unsigned int)v33;
        v9 = (unsigned __int16 *)WLAlloc(2 * v33);
        v50[1] = v9;
        v47 = v9;
        if ( v9 )
        {
          if ( v25 - 2 > 0xFFFFFFFC )
            StringCchCopyW(v9, (unsigned int)v34, v27);
          else
            StringCchPrintfW(v9, (unsigned int)v34, v27, v25);
          if ( v10 )
            StringCchCatW(v50[1], v34, v10);
          goto LABEL_87;
        }
      }
      v7 = 14;
LABEL_63:
      v24 = v44;
      goto LABEL_114;
    case 1:
      LODWORD(v49) = 80;
      *((_QWORD *)&v49 + 1) = L"Microsoft.NetDriveReconnectFailed";
      String = AllocAndLoadString(0x7D0u, qword_1400D2560);
      v50[0] = String;
      v46 = String;
      v9 = AllocAndLoadString(0x7D1u, qword_1400D2560);
      v50[1] = v9;
      v47 = v9;
      *((_QWORD *)&v51 + 1) = L"shell32.dll,-11";
      HIDWORD(v53) = 2;
      LODWORD(v53) = 120000;
      *(_QWORD *)&v52 = L"::{20D04FE0-3AEA-1069-A2D8-08002B30309D}";
      goto LABEL_87;
    case 2:
      LODWORD(v49) = 80;
      *((_QWORD *)&v49 + 1) = L"Microsoft.AuditingLogIsFull";
      v20 = AllocAndLoadString(0x7DDu, qword_1400D2560);
      v21 = 2014;
LABEL_36:
      v50[0] = v20;
      v46 = v20;
      String = v20;
      v9 = AllocAndLoadString(v21, qword_1400D2560);
      v50[1] = v9;
      v47 = v9;
      goto LABEL_86;
    case 3:
      if ( a2 )
        v15 = *(_DWORD *)a2;
      else
        v15 = 0;
      if ( a3 )
        v16 = *a3;
      else
        v16 = 0;
      LODWORD(v49) = 80;
      *((_QWORD *)&v49 + 1) = L"Microsoft.LogoffWarning";
      if ( v16 )
      {
        v17 = AllocAndLoadString(0x804u, qword_1400D2560);
      }
      else
      {
        v18 = 2045;
        if ( v15 != -1 )
          v18 = 2017;
        v17 = AllocAndLoadString(v18, qword_1400D2560);
      }
      v50[0] = v17;
      v46 = v17;
      String = v17;
      v50[1] = &qword_1400D2588;
      *((_QWORD *)&v51 + 1) = L"shell32.dll,-48";
      HIDWORD(v53) = (v15 != -1) + 1;
      v19 = 120000;
      if ( v15 <= 0x258 )
        v19 = -1;
      LODWORD(v53) = v19;
      goto LABEL_87;
  }
  if ( a1 != 4 )
  {
    if ( a1 == 5 )
    {
      LODWORD(v49) = 80;
      *((_QWORD *)&v49 + 1) = L"Microsoft.KerbCredentialsExpired";
      String = AllocAndLoadString(0x7F9u, qword_1400D2560);
      v50[0] = String;
      v46 = String;
      v9 = AllocAndLoadString(0x7FAu, qword_1400D2560);
      v50[1] = v9;
      v47 = v9;
      v44 = AllocAndLoadString(0x7F8u, qword_1400D2560);
      *(_QWORD *)&v51 = v44;
      v48 = v44;
LABEL_86:
      *((_QWORD *)&v51 + 1) = L"shell32.dll,-48";
      HIDWORD(v53) = 2;
      LODWORD(v53) = 60000;
      goto LABEL_87;
    }
    goto LABEL_45;
  }
  if ( a2 )
  {
    v45 = AllocAndLoadString(*(_DWORD *)a2, qword_1400D2560);
    if ( !v45 )
      goto LABEL_14;
    LODWORD(v49) = 80;
    *((_QWORD *)&v49 + 1) = L"Microsoft.LogonHoursWarning";
    String = AllocAndLoadString(0x7DFu, qword_1400D2560);
    v50[0] = String;
    v46 = String;
    *((_QWORD *)&v51 + 1) = L"shell32.dll,-220";
    HIDWORD(v53) = 2;
    v11 = -1;
    v12 = -1;
    if ( *((_DWORD *)a2 + 1) > 2u )
      v12 = 60000;
    LODWORD(v53) = v12;
    do
      ++v11;
    while ( v45[v11] );
    v13 = v11 + 12;
    v14 = (unsigned __int16 *)WLAlloc(2LL * (unsigned int)(v11 + 12));
    v9 = v14;
    v50[1] = v14;
    v47 = v14;
    if ( !v14 )
    {
LABEL_14:
      v7 = 14;
      goto LABEL_112;
    }
    StringCchPrintfW(v14, v13, v45, *((unsigned int *)a2 + 1));
LABEL_87:
    v24 = v44;
LABEL_88:
    v37 = 0;
    if ( !v50[1] )
    {
      v7 = 14;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_45f944bba9fd33a68794881c2280ffd4_Traceguids);
      }
      goto LABEL_113;
    }
    v38 = a4;
    if ( a4 )
    {
      v37 = WlRemindersiAddPostShell((struct _tagSHELLREMINDER *)&v49);
      v41 = WPP_GLOBAL_Control;
      goto LABEL_106;
    }
    v42 = (HANDLE *)&qword_1400D2D10[a1];
    if ( *v42 && WaitForSingleObject(*v42, 0) == 258 )
    {
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_105;
      }
      WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v39, v40, (unsigned int)*v42, (__int64)v50[0], (__int64)v50[1]);
    }
    else
    {
      if ( *v42 )
      {
        CloseHandle(*v42);
        *v42 = 0;
      }
      v55[0] = v49;
      v55[1] = *(_OWORD *)v50;
      v55[2] = v51;
      v55[3] = v52;
      v55[4] = v53;
      v37 = WlRemindersiDisplayNow(v55, (unsigned int)a1, &qword_1400D2D10[a1]);
    }
    v41 = WPP_GLOBAL_Control;
LABEL_105:
    v38 = 0;
LABEL_106:
    if ( v37 && v41 != (CUser *)&WPP_GLOBAL_Control && (*((_BYTE *)v41 + 28) & 0x20) != 0 && *((_BYTE *)v41 + 25) >= 2u )
      WPP_SF_dSSl(*((_QWORD *)v41 + 2), v39, v40, v38, (__int64)v50[0], (__int64)v50[1], v37);
    v7 = 0;
    goto LABEL_113;
  }
LABEL_112:
  v24 = 0;
LABEL_113:
  v27 = v45;
LABEL_114:
  if ( String )
    UHHeapFree(&v46);
  if ( v9 )
    UHHeapFree(&v47);
  if ( v24 )
    UHHeapFree(&v48);
  if ( v27 )
    UHHeapFree(&v45);
  return v7;
}

```

## disassembly

```asm
0x140077464  mov     rax, rsp
0x140077467  mov     [rax+8], rbx
0x14007746b  mov     [rax+10h], rsi
0x14007746f  mov     [rax+20h], r9d
0x140077473  mov     [rax+18h], r8
0x140077477  push    rdi
0x140077478  push    r12
0x14007747a  push    r13
0x14007747c  push    r14
0x14007747e  push    r15
0x140077480  sub     rsp, 130h
0x140077487  mov     r13, r8
0x14007748a  mov     r14, rdx
0x14007748d  mov     r15d, ecx
0x140077490  mov     ebx, 57h ; 'W'
0x140077495  lea     edi, [rbx-7]
0x140077498  mov     r8d, edi; Size
0x14007749b  xor     edx, edx; Val
0x14007749d  lea     rcx, [rsp+158h+var_E8]; void *
0x1400774a2  call    memset_0
0x1400774a7  xor     edx, edx; Val
0x1400774a9  mov     qword ptr [rsp+158h+var_88], rdx
0x1400774b1  xor     eax, eax
0x1400774b3  mov     r8d, edi; Size
0x1400774b6  lea     rcx, [rsp+158h+var_88+8]; void *
0x1400774be  call    memset_0
0x1400774c3  xor     ecx, ecx
0x1400774c5  mov     [rsp+158h+var_108], rcx
0x1400774ca  mov     esi, ecx
0x1400774cc  mov     [rsp+158h+var_100], rcx
0x1400774d1  mov     edi, ecx
0x1400774d3  mov     [rsp+158h+var_F8], rcx
0x1400774d8  mov     r12d, ecx
0x1400774db  mov     [rsp+158h+var_110], rcx
0x1400774e0  mov     [rsp+158h+var_F0], rcx
0x1400774e5  mov     rdx, cs:qword_1400D2560; struct CUser *
0x1400774ec  test    rdx, rdx
0x1400774ef  jz      loc_140077E19
0x1400774f5  cmp     r15d, 6
0x1400774f9  jg      loc_140077851
0x1400774ff  jz      loc_140077829
0x140077505  mov     ecx, r15d
0x140077508  xor     r8d, r8d
0x14007750b  test    r15d, r15d
0x14007750e  jz      loc_14007796D
0x140077514  sub     ecx, 1
0x140077517  jz      loc_1400777A0
0x14007751d  sub     ecx, 1
0x140077520  jz      loc_14007774C
0x140077526  sub     ecx, 1
0x140077529  jz      loc_140077696
0x14007752f  sub     ecx, 1
0x140077532  jz      loc_1400775B8
0x140077538  cmp     ecx, 1
0x14007753b  jnz     loc_140077886
0x140077541  mov     dword ptr [rsp+158h+var_E8], 50h ; 'P'
0x140077549  lea     rax, aMicrosoftKerbc; "Microsoft.KerbCredentialsExpired"
0x140077550  mov     qword ptr [rsp+158h+var_E8+8], rax
0x140077555  mov     ecx, 7F9h; unsigned int
0x14007755a  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x14007755f  mov     rsi, rax
0x140077562  mov     [rsp+158h+var_D8], rax
0x14007756a  mov     [rsp+158h+var_100], rax
0x14007756f  mov     rdx, cs:qword_1400D2560; struct CUser *
0x140077576  mov     ecx, 7FAh; unsigned int
0x14007757b  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x140077580  mov     rdi, rax
0x140077583  mov     [rsp+158h+var_D8+8], rax
0x14007758b  mov     [rsp+158h+var_F8], rax
0x140077590  mov     rdx, cs:qword_1400D2560; struct CUser *
0x140077597  mov     ecx, 7F8h; unsigned int
0x14007759c  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x1400775a1  mov     [rsp+158h+var_110], rax
0x1400775a6  mov     qword ptr [rsp+158h+var_C8], rax
0x1400775ae  mov     [rsp+158h+var_F0], rax
0x1400775b3  jmp     loc_140077C0D
0x1400775b8  test    r14, r14
0x1400775bb  jnz     short loc_1400775C6
0x1400775bd  mov     [rsp+158h+var_118], ebx
0x1400775c1  jmp     loc_140077E19
0x1400775c6  mov     ecx, [r14]; unsigned int
0x1400775c9  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x1400775ce  mov     [rsp+158h+var_108], rax
0x1400775d3  test    rax, rax
0x1400775d6  jnz     short loc_1400775DF
0x1400775d8  mov     ebx, 0Eh
0x1400775dd  jmp     short loc_1400775BD
0x1400775df  mov     dword ptr [rsp+158h+var_E8], 50h ; 'P'
0x1400775e7  lea     rax, aMicrosoftLogon; "Microsoft.LogonHoursWarning"
0x1400775ee  mov     qword ptr [rsp+158h+var_E8+8], rax
0x1400775f3  mov     rdx, cs:qword_1400D2560; struct CUser *
0x1400775fa  mov     ecx, 7DFh; unsigned int
0x1400775ff  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x140077604  mov     rsi, rax
0x140077607  mov     [rsp+158h+var_D8], rax
0x14007760f  mov     [rsp+158h+var_100], rax
0x140077614  lea     rax, aShell32Dll220; "shell32.dll,-220"
0x14007761b  mov     qword ptr [rsp+158h+var_C8+8], rax
0x140077623  mov     dword ptr [rsp+158h+var_A8+0Ch], 2
0x14007762e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140077632  mov     eax, ecx
0x140077634  mov     edx, 0EA60h
0x140077639  cmp     dword ptr [r14+4], 2
0x14007763e  cmova   eax, edx
0x140077641  mov     dword ptr [rsp+158h+var_A8], eax
0x140077648  mov     r12, [rsp+158h+var_108]
0x14007764d  xor     edx, edx
0x14007764f  inc     rcx
0x140077652  cmp     [r12+rcx*2], dx
0x140077657  jnz     short loc_14007764F
0x140077659  lea     eax, [rcx+0Ch]
0x14007765c  mov     ebx, eax
0x14007765e  lea     rcx, [rax+rax]; unsigned __int64
0x140077662  call    ?WLAlloc@@YAPEAX_K@Z; WLAlloc(unsigned __int64)
0x140077667  mov     rdi, rax
0x14007766a  mov     [rsp+158h+var_D8+8], rax
0x140077672  mov     [rsp+158h+var_F8], rax
0x140077677  test    rax, rax
0x14007767a  jz      loc_1400775D8
0x140077680  mov     r9d, [r14+4]
0x140077684  mov     r8, r12; unsigned __int16 *
0x140077687  mov     edx, ebx; unsigned __int64
0x140077689  mov     rcx, rax; unsigned __int16 *
0x14007768c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140077691  jmp     loc_140077C33
0x140077696  test    r14, r14
0x140077699  jz      short loc_1400776A0
0x14007769b  mov     ebx, [r14]
0x14007769e  jmp     short loc_1400776A3
0x1400776a0  mov     ebx, r8d
0x1400776a3  test    r13, r13
0x1400776a6  jz      short loc_1400776AE
0x1400776a8  mov     al, [r13+0]
0x1400776ac  jmp     short loc_1400776B1
0x1400776ae  mov     al, r8b
0x1400776b1  mov     dword ptr [rsp+158h+var_E8], 50h ; 'P'
0x1400776b9  lea     rcx, aMicrosoftLogof; "Microsoft.LogoffWarning"
0x1400776c0  mov     qword ptr [rsp+158h+var_E8+8], rcx
0x1400776c5  test    al, al
0x1400776c7  jz      short loc_1400776D9
0x1400776c9  mov     ecx, 804h; unsigned int
0x1400776ce  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x1400776d3  or      r14d, 0FFFFFFFFh
0x1400776d7  jmp     short loc_1400776F0
0x1400776d9  mov     ecx, 7FDh
0x1400776de  lea     eax, [rcx-1Ch]
0x1400776e1  or      r14d, 0FFFFFFFFh
0x1400776e5  cmp     ebx, r14d
0x1400776e8  cmovnz  ecx, eax; unsigned int
0x1400776eb  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x1400776f0  mov     [rsp+158h+var_D8], rax
0x1400776f8  mov     [rsp+158h+var_100], rax
0x1400776fd  mov     rsi, rax
0x140077700  lea     rax, qword_1400D2588
0x140077707  mov     [rsp+158h+var_D8+8], rax
0x14007770f  lea     rax, aShell32Dll48; "shell32.dll,-48"
0x140077716  mov     qword ptr [rsp+158h+var_C8+8], rax
0x14007771e  xor     edx, edx
0x140077720  mov     eax, edx
0x140077722  cmp     ebx, r14d
0x140077725  setnz   al
0x140077728  inc     eax
0x14007772a  mov     dword ptr [rsp+158h+var_A8+0Ch], eax
0x140077731  mov     eax, 1D4C0h
0x140077736  cmp     ebx, 258h
0x14007773c  cmovbe  eax, r14d
0x140077740  mov     dword ptr [rsp+158h+var_A8], eax
0x140077747  jmp     loc_140077C33
0x14007774c  mov     dword ptr [rsp+158h+var_E8], 50h ; 'P'
0x140077754  lea     rax, aMicrosoftAudit; "Microsoft.AuditingLogIsFull"
0x14007775b  mov     qword ptr [rsp+158h+var_E8+8], rax
0x140077760  mov     ecx, 7DDh; unsigned int
0x140077765  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x14007776a  mov     ecx, 7DEh; unsigned int
0x14007776f  mov     [rsp+158h+var_D8], rax
0x140077777  mov     [rsp+158h+var_100], rax
0x14007777c  mov     rdx, cs:qword_1400D2560; struct CUser *
0x140077783  mov     rsi, rax
0x140077786  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x14007778b  mov     rdi, rax
0x14007778e  mov     [rsp+158h+var_D8+8], rax
0x140077796  mov     [rsp+158h+var_F8], rax
0x14007779b  jmp     loc_140077C0D
0x1400777a0  mov     dword ptr [rsp+158h+var_E8], 50h ; 'P'
0x1400777a8  lea     rax, aMicrosoftNetdr; "Microsoft.NetDriveReconnectFailed"
0x1400777af  mov     qword ptr [rsp+158h+var_E8+8], rax
0x1400777b4  mov     ecx, 7D0h; unsigned int
0x1400777b9  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x1400777be  mov     rsi, rax
0x1400777c1  mov     [rsp+158h+var_D8], rax
0x1400777c9  mov     [rsp+158h+var_100], rax
0x1400777ce  mov     rdx, cs:qword_1400D2560; struct CUser *
0x1400777d5  mov     ecx, 7D1h; unsigned int
0x1400777da  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x1400777df  mov     rdi, rax
0x1400777e2  mov     [rsp+158h+var_D8+8], rax
0x1400777ea  mov     [rsp+158h+var_F8], rax
0x1400777ef  lea     rax, aShell32Dll11; "shell32.dll,-11"
0x1400777f6  mov     qword ptr [rsp+158h+var_C8+8], rax
0x1400777fe  mov     dword ptr [rsp+158h+var_A8+0Ch], 2
0x140077809  mov     eax, 1D4C0h
0x14007780e  mov     dword ptr [rsp+158h+var_A8], eax
0x140077815  lea     rax, a20d04fe03aea10; "::{20D04FE0-3AEA-1069-A2D8-08002B30309D"...
0x14007781c  mov     qword ptr [rsp+158h+var_B8], rax
0x140077824  jmp     loc_140077C33
0x140077829  mov     dword ptr [rsp+158h+var_E8], 50h ; 'P'
0x140077831  lea     rax, aMicrosoftCache; "Microsoft.CachedLogon"
0x140077838  mov     qword ptr [rsp+158h+var_E8+8], rax
0x14007783d  mov     ecx, 7FBh; unsigned int
0x140077842  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x140077847  mov     ecx, 7FCh
0x14007784c  jmp     loc_14007776F
0x140077851  mov     ecx, r15d
0x140077854  sub     ecx, 7
0x140077857  jz      loc_140077BCE
0x14007785d  sub     ecx, 1
0x140077860  jz      loc_140077B85
0x140077866  sub     ecx, 1
0x140077869  jz      loc_140077B60
0x14007786f  sub     ecx, 1
0x140077872  jz      loc_14007796D
0x140077878  sub     ecx, 1
0x14007787b  jz      loc_14007796D
0x140077881  cmp     ecx, 2
0x140077884  jz      short loc_1400778D2
0x140077886  mov     [rsp+158h+var_118], ebx
0x14007788a  lea     r14, WPP_GLOBAL_Control
0x140077891  mov     rcx, cs:WPP_GLOBAL_Control
0x140077898  cmp     rcx, r14
0x14007789b  jz      loc_140077E19
0x1400778a1  test    byte ptr [rcx+1Ch], 20h
0x1400778a5  jz      loc_140077E19
0x1400778ab  cmp     byte ptr [rcx+19h], 2
0x1400778af  jb      loc_140077E19
0x1400778b5  mov     edx, 10h
0x1400778ba  mov     r9d, r15d
0x1400778bd  lea     r8, WPP_45f944bba9fd33a68794881c2280ffd4_Traceguids
0x1400778c4  mov     rcx, [rcx+10h]
0x1400778c8  call    WPP_SF_d
0x1400778cd  jmp     loc_140077E19
0x1400778d2  mov     dword ptr [rsp+158h+var_E8], 50h ; 'P'
0x1400778da  lea     rax, aMicrosoftNtlmd; "Microsoft.NTLMDisabledWarning"
0x1400778e1  mov     qword ptr [rsp+158h+var_E8+8], rax
0x1400778e6  mov     ecx, 807h; unsigned int
0x1400778eb  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x1400778f0  mov     rsi, rax
0x1400778f3  mov     [rsp+158h+var_D8], rax
0x1400778fb  mov     [rsp+158h+var_100], rax
0x140077900  mov     rdx, cs:qword_1400D2560; struct CUser *
0x140077907  mov     ecx, 808h; unsigned int
0x14007790c  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x140077911  mov     ecx, 806h; unsigned int
0x140077916  mov     [rsp+158h+var_D8+8], rax
0x14007791e  mov     [rsp+158h+var_F8], rax
0x140077923  mov     rdx, cs:qword_1400D2560; struct CUser *
0x14007792a  mov     rdi, rax
0x14007792d  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x140077932  mov     r13, rax
0x140077935  mov     qword ptr [rsp+158h+var_C8], rax
0x14007793d  mov     [rsp+158h+var_F0], rax
0x140077942  lea     rax, aShell32Dll48; "shell32.dll,-48"
0x140077949  mov     qword ptr [rsp+158h+var_C8+8], rax
0x140077951  mov     dword ptr [rsp+158h+var_A8+0Ch], 2
0x14007795c  mov     edx, 0EA60h
0x140077961  mov     dword ptr [rsp+158h+var_A8], edx
0x140077968  jmp     loc_140077C38
0x14007796d  xor     ecx, ecx
0x14007796f  cmp     [rsp+158h+arg_18], ecx
0x140077976  jnz     loc_1400775BD
0x14007797c  test    r14, r14
0x14007797f  jz      loc_1400775BD
0x140077985  mov     r13d, [r14]
0x140077988  mov     [rsp+158h+var_98], ecx
0x14007798f  or      r14d, 0FFFFFFFFh
0x140077993  cmp     r13d, r14d
0x140077996  jnz     short loc_1400779AF
0x140077998  lea     eax, [rcx+0Ch]
0x14007799b  cmp     r15d, 0Ah
0x14007799f  cmovz   r15d, eax
0x1400779a3  cmp     r13d, r14d
0x1400779a6  jnz     short loc_1400779AF
0x1400779a8  mov     ecx, 7D9h
0x1400779ad  jmp     short loc_1400779CA
0x1400779af  test    r13d, r13d
0x1400779b2  jnz     short loc_1400779BB
0x1400779b4  mov     ecx, 7DCh
0x1400779b9  jmp     short loc_1400779CA
0x1400779bb  mov     ecx, 7DBh
0x1400779c0  lea     eax, [rcx+10h]
0x1400779c3  cmp     r13d, 1
0x1400779c7  cmovz   ecx, eax; unsigned int
0x1400779ca  call    ?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z; AllocAndLoadString(uint,CUser *)
0x1400779cf  mov     r14, rax
0x1400779d2  mov     [rsp+158h+var_108], rax
0x1400779d7  test    rax, rax
0x1400779da  jnz     short loc_1400779EF
0x1400779dc  mov     ebx, 0Eh
0x1400779e1  mov     [rsp+158h+var_118], ebx
0x1400779e5  mov     r13, [rsp+158h+var_110]
0x1400779ea  jmp     loc_140077E23
  ... truncated ...
```
