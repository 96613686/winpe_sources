# SampApplyWellKnownMemberships(_SAMP_OBJECT *,_SAMP_OBJECT *,void *,ulong,_DS_WELL_KNOWN_MEMBERSHIP_TABLE *,ulong,uchar,uchar)

- ea: `0x18006c858`
- end: `0x18006ce4a`
- name: `?SampApplyWellKnownMemberships@@YAJPEAU_SAMP_OBJECT@@0PEAXKPEAU_DS_WELL_KNOWN_MEMBERSHIP_TABLE@@KEE@Z`
- size: `1522`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, struct _SAMP_OBJECT *, void *, __int16, struct _DS_WELL_KNOWN_MEMBERSHIP_TABLE *, unsigned int, char, char)`
- caller_count: `3`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18006c580`
- `0x18006edb0`
- `0x1800728e0`

## callees

- `0x18000a570`
- `0x180021400`
- `0x180022530`
- `0x180027e24`
- `0x180027ef8`
- `0x180035ec0`
- `0x1800365c0`
- `0x180036b00`
- `0x1800372ac`
- `0x1800412cc`
- `0x1800641c0`
- `0x180064a20`
- `0x180064e80`
- `0x18006c858`
- `0x180073ce4`
- `0x180076e64`
- `0x1800b03d0`
- `0x1800bb788`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006cc97`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006cc97`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006ccce`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006ccce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cd34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cd34`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18006cd16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18006cd16`
- `ntdll!RtlNtStatusToDosError` at `0x18006ccec`
- `ntdll!RtlNtStatusToDosError` at `0x18006ccec`
- `ntdll!RtlLengthSid` at `0x18006ca06`
- `ntdll!RtlLengthSid` at `0x18006ca06`
- `ntdll!RtlInitUnicodeString` at `0x18006cd28`
- `ntdll!RtlInitUnicodeString` at `0x18006cd28`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ca15`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ca15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cd9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cdac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cdbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cdda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cd9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cdac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cdbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cdda`

## string_xrefs

- `0x18006cc8e`: `SAMSRV.DLL`
- `0x18006cbed`: `SamrRemoveMemberFromGroup`
- `0x18006cafc`: `SamrRemoveMemberFromAlias`

## pseudocode

```c
__int64 __fastcall SampApplyWellKnownMemberships(
        struct _SAMP_OBJECT *a1,
        struct _SAMP_OBJECT *a2,
        void *a3,
        __int16 a4,
        struct _DS_WELL_KNOWN_MEMBERSHIP_TABLE *a5,
        unsigned int a6,
        char a7,
        char a8)
{
  struct _SAMP_OBJECT *v8; // r10
  unsigned int v9; // edx
  struct _SAMP_OBJECT *v10; // r8
  int v11; // ebx
  __int64 v12; // rsi
  __int64 v13; // rsi
  void *v14; // r12
  unsigned __int16 v15; // ax
  char v16; // r15
  struct _SAMP_OBJECT *v17; // rdi
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  SIZE_T v21; // rbx
  HLOCAL v22; // rax
  PSID v23; // rcx
  int FullSid; // eax
  int v25; // eax
  int v26; // eax
  const char *v27; // rax
  int v28; // edx
  const char *v29; // r9
  __int64 v30; // rcx
  int v31; // eax
  int v32; // eax
  HLOCAL *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rcx
  HLOCAL *v36; // rax
  __int64 v37; // rcx
  struct _UNICODE_STRING *p_DestinationString; // rax
  HMODULE Library; // rdi
  int MessageStringsWithLanguage; // esi
  __int64 *v41; // rcx
  struct _SAMP_OBJECT *v43; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v44; // [rsp+50h] [rbp-59h]
  void *v45; // [rsp+58h] [rbp-51h]
  WCHAR Buffer[4]; // [rsp+60h] [rbp-49h] BYREF
  __int64 v47; // [rsp+68h] [rbp-41h]
  HLOCAL hMem[2]; // [rsp+70h] [rbp-39h] BYREF
  HLOCAL v49[2]; // [rsp+80h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-19h] BYREF
  struct _SAMP_OBJECT *v51; // [rsp+F8h] [rbp+4Fh]
  __int16 v54; // [rsp+110h] [rbp+67h]

  v54 = a4;
  v51 = a1;
  v8 = a2;
  v9 = 0;
  v10 = a1;
  v11 = 0;
  v44 = 0;
  if ( a6 )
  {
    v12 = 0;
    v47 = 0;
    while ( 1 )
    {
      v43 = 0;
      v13 = 6 * v12;
      v45 = 0;
      v14 = 0;
      if ( !*((_BYTE *)a5 + 8 * v13 + 32) )
      {
LABEL_17:
        v16 = 0;
        v17 = v8;
        if ( !*((_BYTE *)a5 + 8 * v13 + 28) )
          v17 = v10;
        if ( a8 )
        {
          if ( dword_1800ECEC0 == *((_DWORD *)a5 + 2 * v13 + 5) && !byte_1800ECED1 )
          {
            if ( byte_1800ECECF )
            {
              a1 = (struct _SAMP_OBJECT *)WPP_GLOBAL_Control;
              if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
                WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 150, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, 1);
            }
          }
        }
        v18 = (unsigned int)(*((_DWORD *)a5 + 2 * v13 + 6) - 2);
        if ( *((_DWORD *)a5 + 2 * v13 + 6) != 2 )
        {
          if ( *((_DWORD *)a5 + 2 * v13 + 6) != 3 )
            goto LABEL_72;
          v19 = SamrOpenAlias(v17, 0x2000000, *((unsigned int *)a5 + 2 * v13 + 5), &v43);
          v11 = v19;
          if ( v19 < 0 )
          {
            a1 = (struct _SAMP_OBJECT *)WPP_GLOBAL_Control;
            if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
            {
              v20 = 154;
              goto LABEL_61;
            }
            goto LABEL_72;
          }
          v16 = 1;
          if ( *((_BYTE *)a5 + 8 * v13 + 33) )
          {
            v21 = RtlLengthSid(**((PSID **)a5 + v13 + 5));
            v22 = LocalAlloc(0x40u, v21);
            v14 = v22;
            if ( !v22 )
            {
              v11 = -1073741670;
              goto LABEL_72;
            }
            memcpy_0(v22, **((const void ***)a5 + v13 + 5), v21);
          }
          else
          {
            v23 = a3;
            if ( *((_BYTE *)a5 + 8 * v13 + 12) )
              v23 = SampBuiltinDomainSid;
            FullSid = SampCreateFullSid(v23);
            v11 = FullSid;
            if ( FullSid < 0 )
            {
              a1 = (struct _SAMP_OBJECT *)WPP_GLOBAL_Control;
              if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
                WPP_SF_d(
                  WPP_GLOBAL_Control[3].Buffer,
                  155,
                  WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
                  (unsigned int)FullSid);
              v14 = v45;
              goto LABEL_72;
            }
            v14 = v45;
          }
          if ( a7 )
          {
            v25 = SamrAddMemberToAlias(v43);
            v11 = v25;
            if ( v25 == -1073741148 || v25 == -1073741485 )
              v11 = 0;
LABEL_49:
            if ( v11 >= 0 )
              goto LABEL_72;
            a1 = (struct _SAMP_OBJECT *)WPP_GLOBAL_Control;
            if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) >= 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
              goto LABEL_72;
            v27 = "SamrRemoveMemberFromAlias";
            v28 = 156;
            v29 = "SamrAddMemberToAlias";
LABEL_53:
            v30 = *((_QWORD *)a1 + 7);
            if ( !a7 )
              LODWORD(v29) = (_DWORD)v27;
            WPP_SF_sD(v30, v28, (unsigned int)WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (_DWORD)v29, v11);
            goto LABEL_72;
          }
          v26 = SamrRemoveMemberFromAlias(v43);
          v11 = v26;
          if ( v26 != -1073741151 && v26 != -1073741486 )
            goto LABEL_49;
LABEL_56:
          v11 = 0;
          goto LABEL_72;
        }
        v19 = SamrOpenGroup(v17, 0x2000000, *((unsigned int *)a5 + 2 * v13 + 5), &v43);
        v11 = v19;
        if ( v19 >= 0 )
        {
          v16 = 1;
          if ( a7 )
          {
            v31 = SamrAddMemberToGroup(v43, *((_DWORD *)a5 + 2 * v13 + 1));
            v11 = v31;
            if ( v31 == -1073741148 || v31 == -1073741721 )
              v11 = 0;
          }
          else
          {
            v32 = SamrRemoveMemberFromGroup(v43);
            v11 = v32;
            if ( v32 == -1073741151 || v32 == -1073741720 )
              goto LABEL_56;
          }
          if ( v11 >= 0 )
            goto LABEL_72;
          a1 = (struct _SAMP_OBJECT *)WPP_GLOBAL_Control;
          if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) >= 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
            goto LABEL_72;
          v27 = "SamrRemoveMemberFromGroup";
          v28 = 153;
          v29 = "SamrAddMemberToGroup";
          goto LABEL_53;
        }
        a1 = (struct _SAMP_OBJECT *)WPP_GLOBAL_Control;
        if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        {
          v20 = 152;
LABEL_61:
          WPP_SF_d(*((_QWORD *)a1 + 7), v20, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v19);
        }
LABEL_72:
        if ( (unsigned __int8)SampDsIsRunning(a1, v18) && (unsigned int)SampExtExistsDsTransactionDs() )
        {
          if ( v11 >= 0 )
          {
            v11 = SampExtMaybeEndDsTransactionDs(3);
            goto LABEL_76;
          }
          SampExtMaybeEndDsTransactionDs(2);
LABEL_77:
          LODWORD(v45) = 0;
          *(_QWORD *)Buffer = 0;
          v33 = hMem;
          *(_OWORD *)hMem = 0;
          v34 = 16;
          *(_OWORD *)v49 = 0;
          DestinationString = 0;
          do
          {
            *(_BYTE *)v33 = 0;
            v33 = (HLOCAL *)((char *)v33 + 1);
            --v34;
          }
          while ( v34 );
          v35 = 16;
          v36 = v49;
          do
          {
            *(_BYTE *)v36 = 0;
            v36 = (HLOCAL *)((char *)v36 + 1);
            --v35;
          }
          while ( v35 );
          v37 = 16;
          p_DestinationString = &DestinationString;
          do
          {
            LOBYTE(p_DestinationString->Length) = 0;
            p_DestinationString = (struct _UNICODE_STRING *)((char *)p_DestinationString + 1);
            --v37;
          }
          while ( v37 );
          Library = LoadLibraryExW(L"SAMSRV.DLL", 0, 0);
          if ( Library )
          {
            MessageStringsWithLanguage = SampGetMessageStringsWithLanguage(
                                           Library,
                                           0,
                                           *((_DWORD *)a5 + 2 * v13),
                                           (struct _UNICODE_STRING *)hMem,
                                           *((_DWORD *)a5 + 2 * v13 + 4),
                                           (struct _UNICODE_STRING *)v49);
            FreeLibrary(Library);
          }
          else
          {
            MessageStringsWithLanguage = -1073741687;
          }
          LODWORD(v45) = RtlNtStatusToDosError(v11);
          if ( FormatMessageW(0x1100u, 0, (DWORD)v45, 0, Buffer, 0, 0) )
          {
            RtlInitUnicodeString(&DestinationString, *(PCWSTR *)Buffer);
            *(_QWORD *)Buffer = 0;
LABEL_90:
            if ( MessageStringsWithLanguage >= 0 )
            {
              if ( v16 )
              {
                v41 = SAMMSG_MEMBERSHIP_SETUP_ERROR;
                if ( !a7 )
                  v41 = SAMMSG_MEMBERSHIP_REMOVAL_SETUP_ERROR;
              }
              else
              {
                v41 = SAMMSG_MEMBERSHIP_SETUP_ERROR_NO_GROUP;
              }
              SampWriteEventLog(v41, L"uuub", hMem, v49, &DestinationString);
            }
          }
          else if ( !GetLastError() )
          {
            goto LABEL_90;
          }
          if ( hMem[1] )
            LocalFree(hMem[1]);
          if ( v49[1] )
            LocalFree(v49[1]);
          a1 = (struct _SAMP_OBJECT *)DestinationString.Buffer;
          if ( DestinationString.Buffer )
            LocalFree(DestinationString.Buffer);
          v11 = 0;
        }
        else
        {
LABEL_76:
          if ( v11 < 0 )
            goto LABEL_77;
        }
        if ( v43 )
          SamrCloseHandle(&v43);
        if ( v14 )
          LocalFree(v14);
        v8 = a2;
        v10 = v51;
        v9 = v44;
        a4 = v54;
        goto LABEL_109;
      }
      if ( (*((_BYTE *)v10 + 192) & 2) != 0 && (!*((_BYTE *)a5 + 8 * v13 + 29) || (a4 & 1) != 0) )
        break;
LABEL_109:
      ++v9;
      v12 = v47 + 1;
      v44 = v9;
      ++v47;
      if ( v9 >= a6 )
        goto LABEL_110;
    }
    if ( (a4 & 8) != 0 )
    {
      v15 = 1280;
    }
    else
    {
      if ( (a4 & 0x400) == 0 )
      {
LABEL_12:
        if ( *((_DWORD *)a5 + 2 * v13 + 5) != 554 )
          goto LABEL_17;
        a1 = (struct _SAMP_OBJECT *)**((_QWORD **)a5 + v13 + 5);
        if ( (a4 & 0x40) != 0 )
        {
          if ( SampAuthenticatedUsersSid != a1 )
            goto LABEL_17;
        }
        else if ( SampAuthenticatedUsersSid == a1 )
        {
          goto LABEL_17;
        }
        goto LABEL_109;
      }
      v15 = 1282;
    }
    if ( *((_WORD *)a5 + 4 * v13 + 15) < v15 )
      goto LABEL_109;
    goto LABEL_12;
  }
LABEL_110:
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      157,
      WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
      (unsigned int)v11,
      v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18006c858  mov     rax, rsp
0x18006c85b  mov     [rax+20h], r9d
0x18006c85f  mov     [rax+18h], r8
0x18006c863  mov     [rax+10h], rdx
0x18006c867  mov     [rax+8], rcx
0x18006c86b  push    rbp
0x18006c86c  push    rbx
0x18006c86d  push    rsi
0x18006c86e  push    rdi
0x18006c86f  push    r12
0x18006c871  push    r13
0x18006c873  push    r14
0x18006c875  push    r15
0x18006c877  lea     rbp, [rax-47h]
0x18006c87b  sub     rsp, 0A8h
0x18006c882  mov     r14, [rbp+3Fh+arg_20]
0x18006c886  xor     edi, edi
0x18006c888  mov     r10, rdx
0x18006c88b  mov     r13b, [rbp+3Fh+arg_30]
0x18006c88f  mov     edx, edi
0x18006c891  mov     r8, rcx
0x18006c894  mov     ebx, edi
0x18006c896  mov     [rbp+3Fh+var_98], edx
0x18006c899  cmp     [rbp+3Fh+arg_28], edi
0x18006c89c  jbe     loc_18006CE08
0x18006c8a2  mov     esi, edi
0x18006c8a4  mov     [rbp+3Fh+var_80], rdi
0x18006c8a8  lea     rsi, [rsi+rsi*2]
0x18006c8ac  mov     [rbp+3Fh+var_A0], rdi
0x18006c8b0  add     rsi, rsi
0x18006c8b3  mov     [rbp+3Fh+var_90], rdi
0x18006c8b7  mov     r12, rdi
0x18006c8ba  cmp     [r14+rsi*8+20h], dil
0x18006c8bf  jz      short loc_18006C93A
0x18006c8c1  test    byte ptr [r8+0C0h], 2
0x18006c8c9  jz      loc_18006CDEF
0x18006c8cf  cmp     [r14+rsi*8+1Dh], dil
0x18006c8d4  jz      short loc_18006C8E0
0x18006c8d6  test    r9b, 1
0x18006c8da  jz      loc_18006CDEF
0x18006c8e0  test    r9b, 8
0x18006c8e4  jz      short loc_18006C8ED
0x18006c8e6  mov     eax, 500h
0x18006c8eb  jmp     short loc_18006C8F9
0x18006c8ed  bt      r9d, 0Ah
0x18006c8f2  jnb     short loc_18006C905
0x18006c8f4  mov     eax, 502h
0x18006c8f9  cmp     [r14+rsi*8+1Eh], ax
0x18006c8ff  jb      loc_18006CDEF
0x18006c905  cmp     dword ptr [r14+rsi*8+14h], 22Ah
0x18006c90e  jnz     short loc_18006C93A
0x18006c910  mov     rax, [r14+rsi*8+28h]
0x18006c915  mov     rcx, [rax]
0x18006c918  test    r9b, 40h
0x18006c91c  jnz     short loc_18006C92D
0x18006c91e  cmp     cs:SampAuthenticatedUsersSid, rcx
0x18006c925  jnz     loc_18006CDEF
0x18006c92b  jmp     short loc_18006C93A
0x18006c92d  cmp     cs:SampAuthenticatedUsersSid, rcx
0x18006c934  jz      loc_18006CDEF
0x18006c93a  xor     r15d, r15d
0x18006c93d  mov     rdi, r10
0x18006c940  cmp     [r14+rsi*8+1Ch], r15b
0x18006c945  cmovz   rdi, r8
0x18006c949  cmp     [rbp+3Fh+arg_38], r15b
0x18006c950  jz      short loc_18006C99A
0x18006c952  mov     eax, [r14+rsi*8+14h]
0x18006c957  cmp     cs:dword_1800ECEC0, eax
0x18006c95d  jnz     short loc_18006C99A
0x18006c95f  cmp     cs:byte_1800ECED1, r15b
0x18006c966  jnz     short loc_18006C99A
0x18006c968  cmp     cs:byte_1800ECECF, r15b
0x18006c96f  jz      short loc_18006C99A
0x18006c971  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c978  test    dword ptr [rcx+44h], 20000h
0x18006c97f  jz      short loc_18006C99A
0x18006c981  mov     rcx, [rcx+38h]
0x18006c985  lea     r9d, [r15+1]
0x18006c989  mov     edx, 96h
0x18006c98e  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006c995  call    WPP_SF_d
0x18006c99a  mov     edx, [r14+rsi*8+18h]
0x18006c99f  sub     edx, 2
0x18006c9a2  jz      loc_18006CB36
0x18006c9a8  cmp     edx, 1
0x18006c9ab  jnz     loc_18006CC05
0x18006c9b1  mov     r8d, [r14+rsi*8+14h]
0x18006c9b6  lea     r9, [rbp+3Fh+var_A0]
0x18006c9ba  mov     edx, 2000000h
0x18006c9bf  mov     rcx, rdi
0x18006c9c2  call    SamrOpenAlias
0x18006c9c7  xor     edi, edi
0x18006c9c9  mov     ebx, eax
0x18006c9cb  test    eax, eax
0x18006c9cd  jns     short loc_18006C9F4
0x18006c9cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c9d6  test    byte ptr [rcx+44h], 80h
0x18006c9da  jz      loc_18006CC07
0x18006c9e0  cmp     byte ptr [rcx+41h], 2
0x18006c9e4  jb      loc_18006CC07
0x18006c9ea  mov     edx, 9Ah
0x18006c9ef  jmp     loc_18006CB74
0x18006c9f4  mov     r15b, 1
0x18006c9f7  cmp     [r14+rsi*8+21h], dil
0x18006c9fc  jz      short loc_18006CA42
0x18006c9fe  mov     rcx, [r14+rsi*8+28h]
0x18006ca03  mov     rcx, [rcx]; Sid
0x18006ca06  call    cs:__imp_RtlLengthSid
0x18006ca0c  mov     edx, eax; uBytes
0x18006ca0e  mov     ecx, 40h ; '@'; uFlags
0x18006ca13  mov     ebx, eax
0x18006ca15  call    cs:__imp_LocalAlloc
0x18006ca1b  mov     r12, rax
0x18006ca1e  test    rax, rax
0x18006ca21  jnz     short loc_18006CA2D
0x18006ca23  mov     ebx, 0C000009Ah
0x18006ca28  jmp     loc_18006CC07
0x18006ca2d  mov     rdx, [r14+rsi*8+28h]
0x18006ca32  mov     r8, rbx; Size
0x18006ca35  mov     rcx, rax; void *
0x18006ca38  mov     rdx, [rdx]; Src
0x18006ca3b  call    memcpy_0
0x18006ca40  jmp     short loc_18006CA9F
0x18006ca42  cmp     [r14+rsi*8+0Ch], dil
0x18006ca47  lea     r8, [rbp+3Fh+var_90]
0x18006ca4b  mov     rcx, [rbp+3Fh+arg_10]
0x18006ca4f  cmovnz  rcx, cs:SampBuiltinDomainSid; SourceSid
0x18006ca57  mov     edx, [r14+rsi*8+4]
0x18006ca5c  call    SampCreateFullSid
0x18006ca61  mov     ebx, eax
0x18006ca63  test    eax, eax
0x18006ca65  jns     short loc_18006CA9B
0x18006ca67  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ca6e  test    byte ptr [rcx+44h], 80h
0x18006ca72  jz      short loc_18006CA92
0x18006ca74  cmp     byte ptr [rcx+41h], 2
0x18006ca78  jb      short loc_18006CA92
0x18006ca7a  mov     rcx, [rcx+38h]
0x18006ca7e  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006ca85  mov     edx, 9Bh
0x18006ca8a  mov     r9d, eax
0x18006ca8d  call    WPP_SF_d
0x18006ca92  mov     r12, [rbp+3Fh+var_90]
0x18006ca96  jmp     loc_18006CC07
0x18006ca9b  mov     r12, [rbp+3Fh+var_90]
0x18006ca9f  mov     rcx, [rbp+3Fh+var_A0]; struct _SAMP_OBJECT *
0x18006caa3  mov     rdx, r12
0x18006caa6  test    r13b, r13b
0x18006caa9  jz      short loc_18006CAC4
0x18006caab  call    SamrAddMemberToAlias
0x18006cab0  mov     ebx, eax
0x18006cab2  cmp     eax, 0C00002A4h
0x18006cab7  jz      short loc_18006CAC0
0x18006cab9  cmp     eax, 0C0000153h
0x18006cabe  jnz     short loc_18006CAD9
0x18006cac0  mov     ebx, edi
0x18006cac2  jmp     short loc_18006CAD9
0x18006cac4  call    SamrRemoveMemberFromAlias
0x18006cac9  mov     ebx, eax
0x18006cacb  cmp     eax, 0C00002A1h
0x18006cad0  jz      short loc_18006CB2F
0x18006cad2  cmp     eax, 0C0000152h
0x18006cad7  jz      short loc_18006CB2F
0x18006cad9  test    ebx, ebx
0x18006cadb  jns     loc_18006CC07
0x18006cae1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cae8  test    byte ptr [rcx+44h], 80h
0x18006caec  jz      loc_18006CC07
0x18006caf2  cmp     byte ptr [rcx+41h], 2
0x18006caf6  jb      loc_18006CC07
0x18006cafc  lea     rax, aSamrremovememb_1; "SamrRemoveMemberFromAlias"
0x18006cb03  mov     edx, 9Ch
0x18006cb08  lea     r9, aSamraddmembert_2; "SamrAddMemberToAlias"
0x18006cb0f  mov     rcx, [rcx+38h]
0x18006cb13  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006cb1a  test    r13b, r13b
0x18006cb1d  mov     dword ptr [rsp+0E0h+lpBuffer], ebx
0x18006cb21  cmovz   r9, rax
0x18006cb25  call    WPP_SF_sD
0x18006cb2a  jmp     loc_18006CC07
0x18006cb2f  mov     ebx, edi
0x18006cb31  jmp     loc_18006CC07
0x18006cb36  mov     r8d, [r14+rsi*8+14h]
0x18006cb3b  lea     r9, [rbp+3Fh+var_A0]
0x18006cb3f  mov     edx, 2000000h
0x18006cb44  mov     rcx, rdi
0x18006cb47  call    SamrOpenGroup
0x18006cb4c  xor     edi, edi
0x18006cb4e  mov     ebx, eax
0x18006cb50  test    eax, eax
0x18006cb52  jns     short loc_18006CB89
0x18006cb54  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cb5b  test    byte ptr [rcx+44h], 80h
0x18006cb5f  jz      loc_18006CC07
0x18006cb65  cmp     byte ptr [rcx+41h], 2
0x18006cb69  jb      loc_18006CC07
0x18006cb6f  mov     edx, 98h
0x18006cb74  mov     rcx, [rcx+38h]
0x18006cb78  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006cb7f  mov     r9d, eax
0x18006cb82  call    WPP_SF_d
0x18006cb87  jmp     short loc_18006CC07
0x18006cb89  mov     edx, [r14+rsi*8+4]; unsigned int
0x18006cb8e  mov     r15b, 1
0x18006cb91  mov     rcx, [rbp+3Fh+var_A0]; struct _SAMP_OBJECT *
0x18006cb95  test    r13b, r13b
0x18006cb98  jz      short loc_18006CBB9
0x18006cb9a  mov     r8d, 7
0x18006cba0  call    SamrAddMemberToGroup
0x18006cba5  mov     ebx, eax
0x18006cba7  cmp     eax, 0C00002A4h
0x18006cbac  jz      short loc_18006CBB5
0x18006cbae  cmp     eax, 0C0000067h
0x18006cbb3  jnz     short loc_18006CBD6
0x18006cbb5  mov     ebx, edi
0x18006cbb7  jmp     short loc_18006CBD6
0x18006cbb9  call    SamrRemoveMemberFromGroup
0x18006cbbe  mov     ebx, eax
0x18006cbc0  cmp     eax, 0C00002A1h
0x18006cbc5  jz      loc_18006CB2F
0x18006cbcb  cmp     eax, 0C0000068h
0x18006cbd0  jz      loc_18006CB2F
0x18006cbd6  test    ebx, ebx
0x18006cbd8  jns     short loc_18006CC07
0x18006cbda  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cbe1  test    byte ptr [rcx+44h], 80h
0x18006cbe5  jz      short loc_18006CC07
0x18006cbe7  cmp     byte ptr [rcx+41h], 2
0x18006cbeb  jb      short loc_18006CC07
0x18006cbed  lea     rax, aSamrremovememb_2; "SamrRemoveMemberFromGroup"
0x18006cbf4  mov     edx, 99h
0x18006cbf9  lea     r9, aSamraddmembert_1; "SamrAddMemberToGroup"
0x18006cc00  jmp     loc_18006CB0F
0x18006cc05  xor     edi, edi
0x18006cc07  call    SampDsIsRunning
0x18006cc0c  test    al, al
0x18006cc0e  jz      short loc_18006CC2D
0x18006cc10  call    ?SampExtExistsDsTransactionDs@@YAHXZ; SampExtExistsDsTransactionDs(void)
0x18006cc15  test    eax, eax
0x18006cc17  jz      short loc_18006CC2D
0x18006cc19  test    ebx, ebx
0x18006cc1b  js      loc_18006CCD6
0x18006cc21  mov     ecx, 3
0x18006cc26  call    ?SampExtMaybeEndDsTransactionDs@@YAJW4SAMP_DS_TRANSACTION_CONTROL@@@Z; SampExtMaybeEndDsTransactionDs(SAMP_DS_TRANSACTION_CONTROL)
0x18006cc2b  mov     ebx, eax
0x18006cc2d  test    ebx, ebx
0x18006cc2f  jns     loc_18006CDC3
0x18006cc35  xorps   xmm0, xmm0
0x18006cc38  mov     dword ptr [rbp+3Fh+var_90], edi
0x18006cc3b  xorps   xmm1, xmm1
0x18006cc3e  mov     qword ptr [rbp+3Fh+Buffer], rdi
0x18006cc42  mov     edx, 10h
0x18006cc47  lea     rax, [rbp+3Fh+hMem]
0x18006cc4b  movups  xmmword ptr [rbp+3Fh+hMem], xmm0
0x18006cc4f  mov     ecx, edx
0x18006cc51  movups  xmmword ptr [rbp+3Fh+var_68], xmm1
0x18006cc55  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x18006cc59  mov     [rax], dil
0x18006cc5c  inc     rax
0x18006cc5f  sub     rcx, 1
0x18006cc63  jnz     short loc_18006CC59
0x18006cc65  mov     rcx, rdx
0x18006cc68  lea     rax, [rbp+3Fh+var_68]
0x18006cc6c  mov     [rax], dil
0x18006cc6f  inc     rax
0x18006cc72  sub     rcx, 1
0x18006cc76  jnz     short loc_18006CC6C
0x18006cc78  mov     rcx, rdx
0x18006cc7b  lea     rax, [rbp+3Fh+DestinationString]
0x18006cc7f  mov     [rax], dil
0x18006cc82  inc     rax
0x18006cc85  sub     rcx, 1
0x18006cc89  jnz     short loc_18006CC7F
0x18006cc8b  xor     r8d, r8d; dwFlags
0x18006cc8e  lea     rcx, LibFileName; "SAMSRV.DLL"
0x18006cc95  xor     edx, edx; hFile
0x18006cc97  call    cs:__imp_LoadLibraryExW
0x18006cc9d  mov     rdi, rax
0x18006cca0  test    rax, rax
0x18006cca3  jz      short loc_18006CCE5
0x18006cca5  mov     ecx, [r14+rsi*8+10h]
0x18006ccaa  lea     rax, [rbp+3Fh+var_68]
0x18006ccae  mov     r8d, [r14+rsi*8]; unsigned int
0x18006ccb2  lea     r9, [rbp+3Fh+hMem]; struct _UNICODE_STRING *
0x18006ccb6  mov     qword ptr [rsp+0E0h+nSize], rax; struct _UNICODE_STRING *
0x18006ccbb  xor     edx, edx; unsigned int
0x18006ccbd  mov     dword ptr [rsp+0E0h+lpBuffer], ecx; unsigned int
0x18006ccc1  mov     rcx, rdi; void *
0x18006ccc4  call    ?SampGetMessageStringsWithLanguage@@YAJPEAXKKPEAU_UNICODE_STRING@@K1@Z; SampGetMessageStringsWithLanguage(void *,ulong,ulong,_UNICODE_STRING *,ulong,_UNICODE_STRING *)
0x18006ccc9  mov     rcx, rdi; hLibModule
0x18006cccc  mov     esi, eax
0x18006ccce  call    cs:__imp_FreeLibrary
0x18006ccd4  jmp     short loc_18006CCEA
0x18006ccd6  mov     ecx, 2
0x18006ccdb  call    ?SampExtMaybeEndDsTransactionDs@@YAJW4SAMP_DS_TRANSACTION_CONTROL@@@Z; SampExtMaybeEndDsTransactionDs(SAMP_DS_TRANSACTION_CONTROL)
0x18006cce0  jmp     loc_18006CC35
0x18006cce5  mov     esi, 0C0000089h
0x18006ccea  mov     ecx, ebx; Status
0x18006ccec  call    cs:__imp_RtlNtStatusToDosError
0x18006ccf2  lea     rcx, [rbp+3Fh+Buffer]
  ... truncated ...
```
