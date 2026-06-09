# OsImageUtilities::Helpers::IsPreReleaseImage(ushort const *)

- ea: `0x180053bec`
- end: `0x180053e00`
- name: `?IsPreReleaseImage@Helpers@OsImageUtilities@@YA_NPEBG@Z`
- size: `532`
- prototype: `bool __fastcall(PCWSTR pszPathIn, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800542e4`

## callees

- `0x180002f50`
- `0x180006660`
- `0x18002f94c`
- `0x180034674`
- `0x180053bec`
- `0x180054f80`
- `0x180063b04`
- `0x180064fb8`
- `0x1800658a0`
- `0x180065bc0`
- `0x180065c14`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180053c44`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180053c44`
- `ntdll!RtlFreeUnicodeString` at `0x180053d63`
- `ntdll!RtlFreeUnicodeString` at `0x180053d63`

## string_xrefs

- `0x180053dc4`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180053dd9`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180053dee`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall OsImageUtilities::Helpers::IsPreReleaseImage(PCWSTR pszPathIn, const unsigned __int16 *a2)
{
  _QWORD *v2; // rcx
  int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  char v6; // bl
  int v7; // eax
  int v8; // eax
  int v9; // r8d
  int ElementDataWithFlags; // eax
  unsigned int v11; // r8d
  bool v12; // r14
  int v13; // eax
  unsigned int v14; // r8d
  bool v15; // al
  int v17; // [rsp+20h] [rbp-29h]
  int v18; // [rsp+20h] [rbp-29h]
  int v19; // [rsp+20h] [rbp-29h]
  int v20; // [rsp+30h] [rbp-19h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-9h] BYREF
  char v23; // [rsp+50h] [rbp+7h]
  __int16 v24; // [rsp+58h] [rbp+Fh] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp+17h] BYREF
  _QWORD Src[4]; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  Vml::CombineFilePath(Src, pszPathIn, L"Files\\EFI\\Microsoft\\Boot\\BCD");
  UnicodeString = 0;
  v2 = Src;
  if ( Src[3] > 7u )
    v2 = (_QWORD *)Src[0];
  v3 = RtlDosPathNameToNtPathName_U_WithStatus(v2, &UnicodeString, 0, 0);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v3,
      v17);
  v22[1] = &UnicodeString;
  v6 = 1;
  v23 = 1;
  v22[0] = 0;
  v7 = BiOpenStoreWithHash(&UnicodeString, v4, v5, v22);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x186,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v7,
      v17);
  Handle = 0;
  v8 = BcdOpenObject(v22[0], &GUID_DEFAULT_BOOT_ENTRY, &Handle);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x18A,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      (const char *)(unsigned int)v8,
      v17);
  v24 = 0;
  v20 = 2;
  ElementDataWithFlags = BcdGetElementDataWithFlags((_DWORD)Handle, 369098878, v9, (unsigned int)&v24, (__int64)&v20);
  if ( ElementDataWithFlags < 0 )
  {
    if ( ElementDataWithFlags != -1073741275 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x1A3,
        v11,
        (const char *)(unsigned int)ElementDataWithFlags,
        v18);
    v12 = 0;
  }
  else
  {
    v12 = (_BYTE)v24 == 1;
  }
  v24 = 0;
  v20 = 2;
  v13 = BcdGetElementDataWithFlags((_DWORD)Handle, 369098825, v11, (unsigned int)&v24, (__int64)&v20);
  if ( v13 < 0 )
  {
    if ( v13 != -1073741275 )
      wil::details::in1diag3::Throw_NtStatus(retaddr, (void *)0x1BE, v14, (const char *)(unsigned int)v13, v19);
    v15 = 0;
  }
  else
  {
    v15 = (_BYTE)v24 == 1;
  }
  if ( !v12 && !v15 )
    v6 = 0;
  if ( Handle )
    BcdCloseObject(Handle);
  if ( v22[0] )
    BcdCloseStore(v22[0]);
  RtlFreeUnicodeString(&UnicodeString);
  std::wstring::~wstring(Src);
  return v6;
}

```

## disassembly

```asm
0x180053bec  mov     [rsp-8+arg_8], rbx
0x180053bf1  mov     [rsp-8+arg_10], r14
0x180053bf6  push    rbp
0x180053bf7  lea     rbp, [rsp-57h]
0x180053bfc  sub     rsp, 0A0h
0x180053c03  mov     rax, cs:__security_cookie
0x180053c0a  xor     rax, rsp
0x180053c0d  mov     [rbp+57h+var_10], rax
0x180053c11  lea     r8, aFilesEfiMicros; "Files\\EFI\\Microsoft\\Boot\\BCD"
0x180053c18  mov     rdx, rcx; pszPathIn
0x180053c1b  lea     rcx, [rbp+57h+Src]; Src
0x180053c1f  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180053c24  nop
0x180053c25  xorps   xmm0, xmm0
0x180053c28  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x180053c2c  lea     rcx, [rbp+57h+Src]
0x180053c30  cmp     [rbp+57h+var_18], 7
0x180053c35  cmova   rcx, [rbp+57h+Src]
0x180053c3a  xor     r9d, r9d
0x180053c3d  xor     r8d, r8d
0x180053c40  lea     rdx, [rbp+57h+UnicodeString]
0x180053c44  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180053c4b  nop     dword ptr [rax+rax+00h]
0x180053c50  mov     rcx, [rbp+5Fh]; this
0x180053c54  test    eax, eax
0x180053c56  js      loc_180053DC1
0x180053c5c  lea     rax, [rbp+57h+UnicodeString]
0x180053c60  mov     [rbp+57h+var_58], rax
0x180053c64  mov     bl, 1
0x180053c66  mov     [rbp+57h+var_50], bl
0x180053c69  mov     [rbp+57h+var_60], 0
0x180053c71  lea     r9, [rbp+57h+var_60]
0x180053c75  lea     rcx, [rbp+57h+UnicodeString]
0x180053c79  call    BiOpenStoreWithHash
0x180053c7e  mov     rcx, [rbp+5Fh]; this
0x180053c82  test    eax, eax
0x180053c84  js      loc_180053DD6
0x180053c8a  mov     [rbp+57h+Handle], 0
0x180053c92  lea     r8, [rbp+57h+Handle]
0x180053c96  lea     rdx, GUID_DEFAULT_BOOT_ENTRY
0x180053c9d  mov     rcx, [rbp+57h+var_60]
0x180053ca1  call    BcdOpenObject
0x180053ca6  mov     rcx, [rbp+5Fh]; this
0x180053caa  test    eax, eax
0x180053cac  js      loc_180053DEB
0x180053cb2  xor     eax, eax
0x180053cb4  mov     [rbp+57h+var_48], ax
0x180053cb8  mov     [rbp+57h+var_70], 2
0x180053cbf  lea     rax, [rbp+57h+var_70]
0x180053cc3  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x180053cc8  lea     r9, [rbp+57h+var_48]
0x180053ccc  mov     edx, 1600007Eh
0x180053cd1  mov     rcx, [rbp+57h+Handle]
0x180053cd5  call    BcdGetElementDataWithFlags
0x180053cda  test    eax, eax
0x180053cdc  js      short loc_180053CE7
0x180053cde  cmp     byte ptr [rbp+57h+var_48], bl
0x180053ce1  setz    r14b
0x180053ce5  jmp     short loc_180053CF5
0x180053ce7  cmp     eax, 0C0000225h
0x180053cec  jnz     loc_180053DAF
0x180053cf2  xor     r14b, r14b
0x180053cf5  xor     eax, eax
0x180053cf7  mov     [rbp+57h+var_48], ax
0x180053cfb  mov     [rbp+57h+var_70], 2
0x180053d02  lea     rax, [rbp+57h+var_70]
0x180053d06  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x180053d0b  lea     r9, [rbp+57h+var_48]
0x180053d0f  mov     edx, 16000049h
0x180053d14  mov     rcx, [rbp+57h+Handle]
0x180053d18  call    BcdGetElementDataWithFlags
0x180053d1d  test    eax, eax
0x180053d1f  js      short loc_180053D29
0x180053d21  cmp     byte ptr [rbp+57h+var_48], bl
0x180053d24  setz    al
0x180053d27  jmp     short loc_180053D32
0x180053d29  cmp     eax, 0C0000225h
0x180053d2e  jnz     short loc_180053D9D
0x180053d30  xor     al, al
0x180053d32  test    r14b, r14b
0x180053d35  jnz     short loc_180053D3D
0x180053d37  test    al, al
0x180053d39  jnz     short loc_180053D3D
0x180053d3b  xor     bl, bl
0x180053d3d  cmp     [rbp+57h+Handle], 0
0x180053d42  jz      short loc_180053D4E
0x180053d44  mov     rcx, [rbp+57h+Handle]; Handle
0x180053d48  call    BcdCloseObject
0x180053d4d  nop
0x180053d4e  cmp     [rbp+57h+var_60], 0
0x180053d53  jz      short loc_180053D5F
0x180053d55  mov     rcx, [rbp+57h+var_60]
0x180053d59  call    BcdCloseStore
0x180053d5e  nop
0x180053d5f  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x180053d63  call    cs:__imp_RtlFreeUnicodeString
0x180053d6a  nop     dword ptr [rax+rax+00h]
0x180053d6f  nop
0x180053d70  lea     rcx, [rbp+57h+Src]
0x180053d74  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180053d79  mov     al, bl
0x180053d7b  mov     rcx, [rbp+57h+var_10]
0x180053d7f  xor     rcx, rsp; StackCookie
0x180053d82  call    __security_check_cookie
0x180053d87  lea     r11, [rsp+0A0h+var_s0]
0x180053d8f  mov     rbx, [r11+18h]
0x180053d93  mov     r14, [r11+20h]
0x180053d97  mov     rsp, r11
0x180053d9a  pop     rbp
0x180053d9b  retn
0x180053d9d  mov     rcx, [rbp+5Fh]; this
0x180053da1  mov     r9d, eax; char *
0x180053da4  mov     edx, 1BEh; void *
0x180053da9  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x180053daf  mov     rcx, [rbp+5Fh]; this
0x180053db3  mov     r9d, eax; char *
0x180053db6  mov     edx, 1A3h; void *
0x180053dbb  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x180053dc1  mov     r9d, eax; char *
0x180053dc4  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180053dcb  mov     edx, 182h; void *
0x180053dd0  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180053dd6  mov     r9d, eax; char *
0x180053dd9  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180053de0  mov     edx, 186h; void *
0x180053de5  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180053deb  mov     r9d, eax; char *
0x180053dee  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180053df5  mov     edx, 18Ah; void *
0x180053dfa  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
