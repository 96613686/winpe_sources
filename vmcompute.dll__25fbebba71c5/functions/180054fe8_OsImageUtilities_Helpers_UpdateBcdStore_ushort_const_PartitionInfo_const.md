# OsImageUtilities::Helpers::UpdateBcdStore(ushort const *,PartitionInfo const &)

- ea: `0x180054fe8`
- end: `0x18005529f`
- name: `?UpdateBcdStore@Helpers@OsImageUtilities@@YAXPEBGAEBUPartitionInfo@@@Z`
- size: `695`
- prototype: `void __fastcall(PCWSTR pszPathIn, const unsigned __int16 *, const struct PartitionInfo *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800542e4`

## callees

- `0x180002f50`
- `0x180006660`
- `0x18002f94c`
- `0x180034674`
- `0x180054fe8`
- `0x180063dcc`
- `0x180064fb8`
- `0x1800658a0`
- `0x180065bc0`
- `0x180065c14`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180055043`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180055043`
- `ntdll!RtlFreeUnicodeString` at `0x1800551d7`
- `ntdll!RtlFreeUnicodeString` at `0x1800551d7`

## string_xrefs

- `0x18005520f`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180055224`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180055239`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18005524e`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180055263`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180055278`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x18005528d`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall OsImageUtilities::Helpers::UpdateBcdStore(
        PCWSTR pszPathIn,
        const unsigned __int16 *a2,
        const struct PartitionInfo *a3)
{
  _QWORD *v4; // rcx
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  int v9; // eax
  int v10; // r8d
  int v11; // eax
  int v12; // r8d
  int v13; // eax
  int v14; // r8d
  int v15; // eax
  int v16; // r8d
  int v17; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  HANDLE Handle; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v24[2]; // [rsp+38h] [rbp-C8h] BYREF
  char v25; // [rsp+48h] [rbp-B8h]
  char v26; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD Src[4]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v29[60]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v30; // [rsp+C8h] [rbp-38h] BYREF
  int v31; // [rsp+D8h] [rbp-28h]
  _BYTE v32[40]; // [rsp+DCh] [rbp-24h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+18h]

  Vml::CombineFilePath(Src, pszPathIn, L"EFI\\Microsoft\\Boot\\BCD");
  UnicodeString = 0;
  v4 = Src;
  if ( Src[3] > 7u )
    v4 = (_QWORD *)Src[0];
  v5 = RtlDosPathNameToNtPathName_U_WithStatus(v4, &UnicodeString, 0, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v5,
      v18);
  v24[1] = &UnicodeString;
  v25 = 1;
  v24[0] = 0;
  v8 = BiOpenStoreWithHash(&UnicodeString, v6, v7, v24);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v8,
      v18);
  Handle = 0;
  v9 = BcdOpenObject(v24[0], &GUID_DEFAULT_BOOT_ENTRY, &Handle);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v9,
      v18);
  v30 = 0;
  v31 = 0;
  memset(&v32[12], 0, 28);
  LODWORD(v30) = 7;
  *(GUID *)v32 = GUID_VMBFS_BOOT_INSTANCE;
  v11 = BcdSetElementDataWithFlags((_DWORD)Handle, 285212673, v10, (unsigned int)&v30, 60);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v11,
      v19);
  v13 = BcdSetElementDataWithFlags((_DWORD)Handle, 553648129, v12, (unsigned int)&v30, 60);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v13,
      v20);
  memset(v29, 0, 48);
  *(_DWORD *)v29 = 6;
  *(_DWORD *)&v29[20] = 1;
  *(_OWORD *)&v29[28] = *((_OWORD *)a2 + 2);
  *(_OWORD *)&v29[44] = *((_OWORD *)a2 + 3);
  v15 = BcdSetElementDataWithFlags((_DWORD)Handle, 553648465, v14, (unsigned int)v29, 60);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v15,
      v21);
  v26 = 1;
  v17 = BcdSetElementDataWithFlags((_DWORD)Handle, 369098835, v16, (unsigned int)&v26, 1);
  if ( v17 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v17,
      v22);
  if ( Handle )
    BcdCloseObject(Handle);
  if ( v24[0] )
    BcdCloseStore(v24[0]);
  RtlFreeUnicodeString(&UnicodeString);
  std::wstring::~wstring(Src);
}

```

## disassembly

```asm
0x180054fe8  mov     [rsp-8+arg_10], rsi
0x180054fed  push    rbp
0x180054fee  lea     rbp, [rsp-10h]
0x180054ff3  sub     rsp, 110h
0x180054ffa  mov     rax, cs:__security_cookie
0x180055001  xor     rax, rsp
0x180055004  mov     [rbp+10h+var_8], rax
0x180055008  mov     rsi, rdx
0x18005500b  lea     r8, aEfiMicrosoftBo; "EFI\\Microsoft\\Boot\\BCD"
0x180055012  mov     rdx, rcx; pszPathIn
0x180055015  lea     rcx, [rsp+110h+Src]; Src
0x18005501a  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18005501f  nop
0x180055020  xorps   xmm0, xmm0
0x180055023  movups  xmmword ptr [rsp+110h+UnicodeString.Length], xmm0
0x180055028  lea     rcx, [rsp+110h+Src]
0x18005502d  cmp     [rbp+10h+var_90], 7
0x180055032  cmova   rcx, [rsp+110h+Src]
0x180055038  xor     r9d, r9d
0x18005503b  xor     r8d, r8d
0x18005503e  lea     rdx, [rsp+110h+UnicodeString]
0x180055043  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18005504a  nop     dword ptr [rax+rax+00h]
0x18005504f  mov     rcx, [rbp+18h]; this
0x180055053  test    eax, eax
0x180055055  js      loc_180055221
0x18005505b  lea     rax, [rsp+110h+UnicodeString]
0x180055060  mov     [rsp+110h+var_D0], rax
0x180055065  mov     [rsp+110h+var_C8], 1
0x18005506a  mov     [rsp+110h+var_D8], 0
0x180055073  lea     r9, [rsp+110h+var_D8]
0x180055078  lea     rcx, [rsp+110h+UnicodeString]
0x18005507d  call    BiOpenStoreWithHash
0x180055082  mov     rcx, [rbp+18h]; this
0x180055086  test    eax, eax
0x180055088  js      loc_180055236
0x18005508e  mov     [rsp+110h+Handle], 0
0x180055097  lea     r8, [rsp+110h+Handle]
0x18005509c  lea     rdx, GUID_DEFAULT_BOOT_ENTRY
0x1800550a3  mov     rcx, [rsp+110h+var_D8]
0x1800550a8  call    BcdOpenObject
0x1800550ad  mov     rcx, [rbp+18h]; this
0x1800550b1  test    eax, eax
0x1800550b3  js      loc_18005524B
0x1800550b9  xorps   xmm0, xmm0
0x1800550bc  movups  [rbp+10h+var_48], xmm0
0x1800550c0  movups  xmmword ptr [rbp+10h+var_38.Data1], xmm0
0x1800550c4  movups  [rbp+10h+var_28], xmm0
0x1800550c8  movups  [rbp+10h+var_28+0Ch], xmm0
0x1800550cc  mov     dword ptr [rbp+10h+var_48], 7
0x1800550d3  movups  xmm0, xmmword ptr cs:GUID_VMBFS_BOOT_INSTANCE.Data1
0x1800550da  movdqu  xmmword ptr [rbp+10h+var_38.Data2], xmm0
0x1800550df  mov     [rsp+110h+var_F0], 3Ch ; '<'; int
0x1800550e7  lea     r9, [rbp+10h+var_48]
0x1800550eb  mov     edx, 11000001h
0x1800550f0  mov     rcx, [rsp+110h+Handle]
0x1800550f5  call    BcdSetElementDataWithFlags
0x1800550fa  mov     rcx, [rbp+18h]; this
0x1800550fe  test    eax, eax
0x180055100  js      loc_180055260
0x180055106  mov     [rsp+110h+var_F0], 3Ch ; '<'; int
0x18005510e  lea     r9, [rbp+10h+var_48]
0x180055112  mov     edx, 21000001h
0x180055117  mov     rcx, [rsp+110h+Handle]
0x18005511c  call    BcdSetElementDataWithFlags
0x180055121  mov     rcx, [rbp+18h]; this
0x180055125  test    eax, eax
0x180055127  js      loc_180055275
0x18005512d  xorps   xmm0, xmm0
0x180055130  movups  [rbp+10h+var_88], xmm0
0x180055134  movups  [rbp+10h+var_78], xmm0
0x180055138  movups  [rbp+10h+var_68], xmm0
0x18005513c  mov     dword ptr [rbp+10h+var_88], 6
0x180055143  mov     dword ptr [rbp+10h+var_78+4], 1
0x18005514a  movups  xmm0, xmmword ptr [rsi+20h]
0x18005514e  movdqu  [rbp+10h+var_78+0Ch], xmm0
0x180055153  movups  xmm1, xmmword ptr [rsi+30h]
0x180055157  movdqu  [rbp+10h+var_68+0Ch], xmm1
0x18005515c  mov     [rsp+110h+var_F0], 3Ch ; '<'; int
0x180055164  lea     r9, [rbp+10h+var_88]
0x180055168  mov     edx, 21000151h
0x18005516d  mov     rcx, [rsp+110h+Handle]
0x180055172  call    BcdSetElementDataWithFlags
0x180055177  mov     rcx, [rbp+18h]; this
0x18005517b  test    eax, eax
0x18005517d  js      loc_18005528A
0x180055183  mov     [rsp+110h+var_C0], 1
0x180055188  mov     [rsp+110h+var_F0], 1; int
0x180055190  lea     r9, [rsp+110h+var_C0]
0x180055195  mov     edx, 16000053h
0x18005519a  mov     rcx, [rsp+110h+Handle]
0x18005519f  call    BcdSetElementDataWithFlags
0x1800551a4  mov     rcx, [rbp+18h]; this
0x1800551a8  test    eax, eax
0x1800551aa  js      short loc_18005520C
0x1800551ac  cmp     [rsp+110h+Handle], 0
0x1800551b2  jz      short loc_1800551BF
0x1800551b4  mov     rcx, [rsp+110h+Handle]; Handle
0x1800551b9  call    BcdCloseObject
0x1800551be  nop
0x1800551bf  cmp     [rsp+110h+var_D8], 0
0x1800551c5  jz      short loc_1800551D2
0x1800551c7  mov     rcx, [rsp+110h+var_D8]
0x1800551cc  call    BcdCloseStore
0x1800551d1  nop
0x1800551d2  lea     rcx, [rsp+110h+UnicodeString]; UnicodeString
0x1800551d7  call    cs:__imp_RtlFreeUnicodeString
0x1800551de  nop     dword ptr [rax+rax+00h]
0x1800551e3  nop
0x1800551e4  lea     rcx, [rsp+110h+Src]
0x1800551e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800551ee  mov     rcx, [rbp+10h+var_8]
0x1800551f2  xor     rcx, rsp; StackCookie
0x1800551f5  call    __security_check_cookie
0x1800551fa  mov     rsi, [rsp+110h+arg_10]
0x180055202  add     rsp, 110h
0x180055209  pop     rbp
0x18005520a  retn
0x18005520c  mov     r9d, eax; char *
0x18005520f  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180055216  mov     edx, 0CBh; void *
0x18005521b  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180055221  mov     r9d, eax; char *
0x180055224  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18005522b  mov     edx, 0A3h; void *
0x180055230  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180055236  mov     r9d, eax; char *
0x180055239  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180055240  mov     edx, 0A7h; void *
0x180055245  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18005524b  mov     r9d, eax; char *
0x18005524e  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180055255  mov     edx, 0AAh; void *
0x18005525a  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180055260  mov     r9d, eax; char *
0x180055263  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18005526a  mov     edx, 0B3h; void *
0x18005526f  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180055275  mov     r9d, eax; char *
0x180055278  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18005527f  mov     edx, 0B8h; void *
0x180055284  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18005528a  mov     r9d, eax; char *
0x18005528d  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180055294  mov     edx, 0C3h; void *
0x180055299  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
