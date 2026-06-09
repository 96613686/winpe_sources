# RemoveTrackedPath(_UNICODE_STRING const *)

- ea: `0x140006bd4`
- end: `0x140006f71`
- name: `?RemoveTrackedPath@@YAJPEBU_UNICODE_STRING@@@Z`
- size: `925`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x14001e464`

## callees

- `0x140002644`
- `0x140003944`
- `0x140006bd4`
- `0x14000e1d0`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x140006ca5`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140006dc2`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140006ca5`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140006dc2`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x140006cc4`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x140006cc4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140006e27`
- `ntoskrnl!ExReleaseFastMutex` at `0x140006f31`
- `ntoskrnl!ExReleaseFastMutex` at `0x140006e27`
- `ntoskrnl!ExReleaseFastMutex` at `0x140006f31`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006c6a`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006c6a`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140006da9`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140006da9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006ce8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006eff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006f19`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006f49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006ce8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006eff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006f19`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006f49`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140006c90`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140006dec`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140006c90`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140006dec`
- `FLTMGR!FltDetachVolume` at `0x140006e81`
- `FLTMGR!FltDetachVolume` at `0x140006e81`
- `FLTMGR!FltGetVolumeFromName` at `0x140006e61`
- `FLTMGR!FltGetVolumeFromName` at `0x140006e61`
- `FLTMGR!FltObjectDereference` at `0x140006ee2`
- `FLTMGR!FltObjectDereference` at `0x140006ee2`

## string_xrefs

- `0x140006c21`: `Failed to convert path [%wZ] to NT (0x%08X)`

## pseudocode

```c
__int64 __fastcall RemoveTrackedPath(const struct _UNICODE_STRING *a1)
{
  char *v1; // r14
  int NtPath; // eax
  unsigned int v4; // edi
  char v5; // r15
  BOOLEAN i; // dl
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  struct _UNICODE_PREFIX_TABLE_ENTRY *v8; // rsi
  struct _RTL_SPLAY_LINKS *RightChild; // rcx
  struct _RTL_SPLAY_LINKS *v10; // rcx
  struct _RTL_SPLAY_LINKS *LeftChild; // rcx
  struct _RTL_SPLAY_LINKS *v12; // rcx
  struct _RTL_SPLAY_LINKS *Parent; // rbx
  struct _UNICODE_PREFIX_TABLE_ENTRY *NextPrefixTree; // rcx
  BOOLEAN j; // dl
  PUNICODE_PREFIX_TABLE_ENTRY v16; // rax
  char *v17; // rbx
  _QWORD *v18; // rsi
  BOOLEAN v19; // al
  PVOID v20; // rcx
  char *v21; // rbx
  NTSTATUS VolumeFromName; // eax
  NTSTATUS v23; // eax
  void *v24; // rcx
  UNICODE_STRING String2; // [rsp+20h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-10h] BYREF
  PFLT_VOLUME RetVolume; // [rsp+78h] [rbp+38h] BYREF

  v1 = 0;
  String2 = 0;
  RetVolume = 0;
  String1 = 0;
  NtPath = GetNtPath(a1, &String2, &String1);
  v4 = NtPath;
  if ( NtPath >= 0 )
  {
    if ( String2.Length >= 2u && String2.Buffer[((unsigned __int64)String2.Length >> 1) - 1] == 92 )
      String2.Length -= 2;
    ExAcquireFastMutex(&stru_140019468);
    v5 = 1;
    for ( i = 1; ; i = 0 )
    {
      UnicodePrefix = RtlNextUnicodePrefix(&g_TrackingInfo, i);
      v8 = UnicodePrefix;
      if ( !UnicodePrefix )
        break;
      if ( RtlEqualUnicodeString((PCUNICODE_STRING)&UnicodePrefix[1], &String2, 1u) )
      {
        RtlRemoveUnicodePrefix(&g_TrackingInfo, v8);
        while ( 1 )
        {
          Parent = v8[1].Links.Parent;
          if ( !Parent )
            break;
          v8[1].Links.Parent = Parent->Parent;
          RightChild = Parent[2].RightChild;
          if ( RightChild )
          {
            ExFreePoolWithTag(RightChild, 0x6E6D7377u);
            Parent[2].RightChild = 0;
          }
          v10 = Parent[2].Parent;
          if ( v10 )
          {
            ExFreePoolWithTag(v10, 0x6E6D7377u);
            Parent[2].Parent = 0;
          }
          LeftChild = Parent[1].LeftChild;
          if ( LeftChild )
          {
            ExFreePoolWithTag(LeftChild, 0x6E6D7377u);
            Parent[1].LeftChild = 0;
          }
          v12 = Parent->RightChild;
          if ( v12 )
          {
            ExFreePoolWithTag(v12, 0x6E6D7377u);
            Parent->RightChild = 0;
          }
          ExFreePoolWithTag(Parent, 0x6E6D7377u);
        }
        NextPrefixTree = v8[1].NextPrefixTree;
        if ( NextPrefixTree )
        {
          ExFreePoolWithTag(NextPrefixTree, 0x6E6D7377u);
          v8[1].NextPrefixTree = 0;
        }
        ExFreePoolWithTag(v8, 0x6E6D7377u);
        for ( j = 1; ; j = 0 )
        {
          v16 = RtlNextUnicodePrefix(&g_TrackingInfo, j);
          if ( !v16 )
            break;
          if ( RtlPrefixUnicodeString(&String1, (PCUNICODE_STRING)&v16[1], 1u) )
            goto LABEL_36;
        }
        v17 = (char *)qword_140019448;
        v18 = 0;
        if ( qword_140019448 )
        {
          while ( 1 )
          {
            v19 = RtlEqualUnicodeString((PCUNICODE_STRING)(v17 + 8), &String1, 1u);
            v20 = *(PVOID *)v17;
            if ( v19 )
              break;
            v18 = v17;
            v17 = *(char **)v17;
            if ( !v20 )
              goto LABEL_36;
          }
          if ( v18 )
            *v18 = v20;
          else
            qword_140019448 = *(PVOID *)v17;
          v1 = v17;
        }
LABEL_36:
        ExReleaseFastMutex(&stru_140019468);
        v5 = 0;
        if ( v1 )
        {
          v21 = v1 + 8;
          if ( !IsLogPathUnderPath((const struct _UNICODE_STRING *)(v1 + 8)) )
          {
            VolumeFromName = FltGetVolumeFromName((PFLT_FILTER)FilterHandle, (PCUNICODE_STRING)(v1 + 8), &RetVolume);
            v4 = VolumeFromName;
            if ( VolumeFromName < 0 )
            {
              if ( VolumeFromName == -1073741766 || VolumeFromName == -1071906805 || VolumeFromName == -1071906796 )
              {
                WriteLogMessage(
                  1,
                  L"Volume [%wZ] is not available (0x%08X); no need to detach",
                  v1 + 8,
                  (unsigned int)VolumeFromName,
                  *(_QWORD *)&String2.Length);
                v4 = 0;
              }
              else
              {
                WriteLogMessage(
                  3,
                  L"Failed to get volume object for [%wZ] (0x%08X)",
                  v21,
                  (unsigned int)VolumeFromName,
                  *(_QWORD *)&String2.Length);
              }
            }
            else
            {
              v23 = FltDetachVolume((PFLT_FILTER)FilterHandle, RetVolume, 0);
              v4 = v23;
              if ( v23 < 0 )
                WriteLogMessage(
                  3,
                  L"Failed to detach from volume [%wZ] (0x%08X)",
                  v21,
                  (unsigned int)v23,
                  *(_QWORD *)&String2.Length);
            }
          }
        }
        break;
      }
    }
  }
  else
  {
    v5 = 0;
    WriteLogMessage(
      3,
      L"Failed to convert path [%wZ] to NT (0x%08X)",
      a1,
      (unsigned int)NtPath,
      *(_QWORD *)&String2.Length);
  }
  if ( RetVolume )
    FltObjectDereference(RetVolume);
  if ( v1 )
  {
    v24 = (void *)*((_QWORD *)v1 + 2);
    if ( v24 )
    {
      ExFreePoolWithTag(v24, 0x6E6D7377u);
      *((_QWORD *)v1 + 2) = 0;
    }
    ExFreePoolWithTag(v1, 0x6E6D7377u);
  }
  if ( v5 )
    ExReleaseFastMutex(&stru_140019468);
  if ( String2.Buffer )
    ExFreePoolWithTag(String2.Buffer, 0x6E6D7377u);
  return v4;
}

```

## disassembly

```asm
0x140006bd4  mov     [rsp-28h+arg_0], rbx
0x140006bd9  mov     [rsp-28h+arg_10], rsi
0x140006bde  push    rbp
0x140006bdf  push    rdi
0x140006be0  push    r13
0x140006be2  push    r14
0x140006be4  push    r15
0x140006be6  mov     rbp, rsp
0x140006be9  sub     rsp, 40h
0x140006bed  xorps   xmm0, xmm0
0x140006bf0  lea     r8, [rbp+String1]; struct _UNICODE_STRING *
0x140006bf4  xorps   xmm1, xmm1
0x140006bf7  lea     rdx, [rbp+String2]; DestinationString
0x140006bfb  xor     r14d, r14d
0x140006bfe  mov     rbx, rcx
0x140006c01  movups  xmmword ptr [rbp+String2.Length], xmm0
0x140006c05  mov     [rbp+RetVolume], r14
0x140006c09  movups  xmmword ptr [rbp+String1.Length], xmm1
0x140006c0d  call    ?GetNtPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x140006c12  mov     edi, eax
0x140006c14  mov     r13d, 6E6D7377h
0x140006c1a  test    eax, eax
0x140006c1c  jns     short loc_140006C3D
0x140006c1e  xor     r15b, r15b
0x140006c21  lea     rdx, aFailedToConver; "Failed to convert path [%wZ] to NT (0x%"...
0x140006c28  mov     r9d, eax
0x140006c2b  mov     r8, rbx
0x140006c2e  mov     ecx, 3
0x140006c33  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140006c38  jmp     loc_140006ED9
0x140006c3d  movzx   edx, [rbp+String2.Length]
0x140006c41  cmp     edx, 2
0x140006c44  jb      short loc_140006C63
0x140006c46  mov     rax, [rbp+String2.Buffer]
0x140006c4a  mov     ecx, edx
0x140006c4c  shr     rcx, 1
0x140006c4f  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140006c55  jnz     short loc_140006C63
0x140006c57  mov     eax, 0FFFEh
0x140006c5c  add     dx, ax
0x140006c5f  mov     [rbp+String2.Length], dx
0x140006c63  lea     rcx, stru_140019468; FastMutex
0x140006c6a  call    cs:__imp_ExAcquireFastMutex
0x140006c71  nop     dword ptr [rax+rax+00h]
0x140006c76  mov     r15b, 1
0x140006c79  lea     rbx, ?g_TrackingInfo@@3U_TRACKED_PATHS_TABLE@@A; _TRACKED_PATHS_TABLE g_TrackingInfo
0x140006c80  mov     dl, r15b
0x140006c83  jmp     short loc_140006CA2
0x140006c85  lea     rcx, [rsi+38h]; String1
0x140006c89  mov     r8b, r15b; CaseInSensitive
0x140006c8c  lea     rdx, [rbp+String2]; String2
0x140006c90  call    cs:__imp_RtlEqualUnicodeString
0x140006c97  nop     dword ptr [rax+rax+00h]
0x140006c9c  test    al, al
0x140006c9e  jnz     short loc_140006CBE
0x140006ca0  xor     edx, edx; Restart
0x140006ca2  mov     rcx, rbx; PrefixTable
0x140006ca5  call    cs:__imp_RtlNextUnicodePrefix
0x140006cac  nop     dword ptr [rax+rax+00h]
0x140006cb1  mov     rsi, rax
0x140006cb4  test    rax, rax
0x140006cb7  jnz     short loc_140006C85
0x140006cb9  jmp     loc_140006ED9
0x140006cbe  mov     rdx, rsi; PrefixTableEntry
0x140006cc1  mov     rcx, rbx; PrefixTable
0x140006cc4  call    cs:__imp_RtlRemoveUnicodePrefix
0x140006ccb  nop     dword ptr [rax+rax+00h]
0x140006cd0  jmp     loc_140006D5E
0x140006cd5  mov     rax, [rbx]
0x140006cd8  mov     [rsi+50h], rax
0x140006cdc  mov     rcx, [rbx+40h]; P
0x140006ce0  test    rcx, rcx
0x140006ce3  jz      short loc_140006CF8
0x140006ce5  mov     edx, r13d; Tag
0x140006ce8  call    cs:__imp_ExFreePoolWithTag
0x140006cef  nop     dword ptr [rax+rax+00h]
0x140006cf4  mov     [rbx+40h], r14
0x140006cf8  mov     rcx, [rbx+30h]; P
0x140006cfc  test    rcx, rcx
0x140006cff  jz      short loc_140006D14
0x140006d01  mov     edx, r13d; Tag
0x140006d04  call    cs:__imp_ExFreePoolWithTag
0x140006d0b  nop     dword ptr [rax+rax+00h]
0x140006d10  mov     [rbx+30h], r14
0x140006d14  mov     rcx, [rbx+20h]; P
0x140006d18  test    rcx, rcx
0x140006d1b  jz      short loc_140006D30
0x140006d1d  mov     edx, r13d; Tag
0x140006d20  call    cs:__imp_ExFreePoolWithTag
0x140006d27  nop     dword ptr [rax+rax+00h]
0x140006d2c  mov     [rbx+20h], r14
0x140006d30  mov     rcx, [rbx+10h]; P
0x140006d34  test    rcx, rcx
0x140006d37  jz      short loc_140006D4C
0x140006d39  mov     edx, r13d; Tag
0x140006d3c  call    cs:__imp_ExFreePoolWithTag
0x140006d43  nop     dword ptr [rax+rax+00h]
0x140006d48  mov     [rbx+10h], r14
0x140006d4c  mov     edx, r13d; Tag
0x140006d4f  mov     rcx, rbx; P
0x140006d52  call    cs:__imp_ExFreePoolWithTag
0x140006d59  nop     dword ptr [rax+rax+00h]
0x140006d5e  mov     rbx, [rsi+50h]
0x140006d62  test    rbx, rbx
0x140006d65  jnz     loc_140006CD5
0x140006d6b  mov     rcx, [rsi+40h]; P
0x140006d6f  test    rcx, rcx
0x140006d72  jz      short loc_140006D87
0x140006d74  mov     edx, r13d; Tag
0x140006d77  call    cs:__imp_ExFreePoolWithTag
0x140006d7e  nop     dword ptr [rax+rax+00h]
0x140006d83  mov     [rsi+40h], r14
0x140006d87  mov     edx, r13d; Tag
0x140006d8a  mov     rcx, rsi; P
0x140006d8d  call    cs:__imp_ExFreePoolWithTag
0x140006d94  nop     dword ptr [rax+rax+00h]
0x140006d99  mov     dl, r15b
0x140006d9c  jmp     short loc_140006DBB
0x140006d9e  lea     rdx, [rax+38h]; String2
0x140006da2  mov     r8b, r15b; CaseInSensitive
0x140006da5  lea     rcx, [rbp+String1]; String1
0x140006da9  call    cs:__imp_RtlPrefixUnicodeString
0x140006db0  nop     dword ptr [rax+rax+00h]
0x140006db5  test    al, al
0x140006db7  jnz     short loc_140006E20
0x140006db9  xor     edx, edx; Restart
0x140006dbb  lea     rcx, ?g_TrackingInfo@@3U_TRACKED_PATHS_TABLE@@A; PrefixTable
0x140006dc2  call    cs:__imp_RtlNextUnicodePrefix
0x140006dc9  nop     dword ptr [rax+rax+00h]
0x140006dce  test    rax, rax
0x140006dd1  jnz     short loc_140006D9E
0x140006dd3  mov     rbx, cs:qword_140019448
0x140006dda  xor     esi, esi
0x140006ddc  test    rbx, rbx
0x140006ddf  jz      short loc_140006E20
0x140006de1  lea     rcx, [rbx+8]; String1
0x140006de5  mov     r8b, r15b; CaseInSensitive
0x140006de8  lea     rdx, [rbp+String1]; String2
0x140006dec  call    cs:__imp_RtlEqualUnicodeString
0x140006df3  nop     dword ptr [rax+rax+00h]
0x140006df8  mov     rcx, [rbx]
0x140006dfb  test    al, al
0x140006dfd  jnz     short loc_140006E0C
0x140006dff  mov     rsi, rbx
0x140006e02  mov     rbx, rcx
0x140006e05  test    rcx, rcx
0x140006e08  jnz     short loc_140006DE1
0x140006e0a  jmp     short loc_140006E20
0x140006e0c  test    rsi, rsi
0x140006e0f  jz      short loc_140006E16
0x140006e11  mov     [rsi], rcx
0x140006e14  jmp     short loc_140006E1D
0x140006e16  mov     cs:qword_140019448, rcx
0x140006e1d  mov     r14, rbx
0x140006e20  lea     rcx, stru_140019468; FastMutex
0x140006e27  call    cs:__imp_ExReleaseFastMutex
0x140006e2e  nop     dword ptr [rax+rax+00h]
0x140006e33  xor     r15b, r15b
0x140006e36  test    r14, r14
0x140006e39  jz      loc_140006ED9
0x140006e3f  lea     rbx, [r14+8]
0x140006e43  mov     rcx, rbx; struct _UNICODE_STRING *
0x140006e46  call    ?IsLogPathUnderPath@@YAEPEBU_UNICODE_STRING@@@Z; IsLogPathUnderPath(_UNICODE_STRING const *)
0x140006e4b  test    al, al
0x140006e4d  jnz     loc_140006ED9
0x140006e53  mov     rcx, cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA; Filter
0x140006e5a  lea     r8, [rbp+RetVolume]; RetVolume
0x140006e5e  mov     rdx, rbx; VolumeName
0x140006e61  call    cs:__imp_FltGetVolumeFromName
0x140006e68  nop     dword ptr [rax+rax+00h]
0x140006e6d  mov     edi, eax
0x140006e6f  test    eax, eax
0x140006e71  js      short loc_140006E9F
0x140006e73  mov     rdx, [rbp+RetVolume]; Volume
0x140006e77  xor     r8d, r8d; InstanceName
0x140006e7a  mov     rcx, cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA; Filter
0x140006e81  call    cs:__imp_FltDetachVolume
0x140006e88  nop     dword ptr [rax+rax+00h]
0x140006e8d  mov     edi, eax
0x140006e8f  test    eax, eax
0x140006e91  jns     short loc_140006ED9
0x140006e93  lea     rdx, aFailedToDetach_0; "Failed to detach from volume [%wZ] (0x%"...
0x140006e9a  jmp     loc_140006C28
0x140006e9f  cmp     eax, 0C000003Ah
0x140006ea4  jz      short loc_140006EC0
0x140006ea6  cmp     eax, 0C01C000Bh
0x140006eab  jz      short loc_140006EC0
0x140006ead  cmp     eax, 0C01C0014h
0x140006eb2  jz      short loc_140006EC0
0x140006eb4  lea     rdx, aFailedToGetVol_0; "Failed to get volume object for [%wZ] ("...
0x140006ebb  jmp     loc_140006C28
0x140006ec0  mov     r9d, eax
0x140006ec3  lea     rdx, aVolumeWzIsNotA; "Volume [%wZ] is not available (0x%08X);"...
0x140006eca  mov     r8, rbx
0x140006ecd  mov     ecx, 1
0x140006ed2  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140006ed7  xor     edi, edi
0x140006ed9  mov     rcx, [rbp+RetVolume]; FltObject
0x140006edd  test    rcx, rcx
0x140006ee0  jz      short loc_140006EEE
0x140006ee2  call    cs:__imp_FltObjectDereference
0x140006ee9  nop     dword ptr [rax+rax+00h]
0x140006eee  test    r14, r14
0x140006ef1  jz      short loc_140006F25
0x140006ef3  mov     rcx, [r14+10h]; P
0x140006ef7  test    rcx, rcx
0x140006efa  jz      short loc_140006F13
0x140006efc  mov     edx, r13d; Tag
0x140006eff  call    cs:__imp_ExFreePoolWithTag
0x140006f06  nop     dword ptr [rax+rax+00h]
0x140006f0b  mov     qword ptr [r14+10h], 0
0x140006f13  mov     edx, r13d; Tag
0x140006f16  mov     rcx, r14; P
0x140006f19  call    cs:__imp_ExFreePoolWithTag
0x140006f20  nop     dword ptr [rax+rax+00h]
0x140006f25  test    r15b, r15b
0x140006f28  jz      short loc_140006F3D
0x140006f2a  lea     rcx, stru_140019468; FastMutex
0x140006f31  call    cs:__imp_ExReleaseFastMutex
0x140006f38  nop     dword ptr [rax+rax+00h]
0x140006f3d  mov     rcx, [rbp+String2.Buffer]; P
0x140006f41  test    rcx, rcx
0x140006f44  jz      short loc_140006F55
0x140006f46  mov     edx, r13d; Tag
0x140006f49  call    cs:__imp_ExFreePoolWithTag
0x140006f50  nop     dword ptr [rax+rax+00h]
0x140006f55  lea     r11, [rsp+40h+var_s0]
0x140006f5a  mov     eax, edi
0x140006f5c  mov     rbx, [r11+30h]
0x140006f60  mov     rsi, [r11+40h]
0x140006f64  mov     rsp, r11
0x140006f67  pop     r15
0x140006f69  pop     r14
0x140006f6b  pop     r13
0x140006f6d  pop     rdi
0x140006f6e  pop     rbp
0x140006f6f  retn
```
