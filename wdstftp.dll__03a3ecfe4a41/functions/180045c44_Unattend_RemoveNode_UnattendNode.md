# Unattend::RemoveNode(UnattendNode)

- ea: `0x180045c44`
- end: `0x180045d7a`
- name: `?RemoveNode@Unattend@@QEAAJVUnattendNode@@@Z`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800413ac`

## callees

- `0x1800370f4`
- `0x180043e58`
- `0x180045c44`
- `0x1800478e8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180045cfe`
- `ntdll!RtlNtStatusToDosError` at `0x180045cfe`

## string_xrefs

- `0x180045cc0`: `onecore\base\xml\udom_modify.cpp`
- `0x180045d2c`: `onecore\base\xml\udom_modify.cpp`
- `0x180045ce1`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x180045d4d`: `pToRemove != 0`
- `0x180045cd6`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveElement`
- `0x180045d42`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveElement`

## pseudocode

```c
__int64 __fastcall Unattend::RemoveNode(__int64 a1, __int128 *a2)
{
  bool v2; // zf
  __int128 v4; // xmm0
  __int64 v5; // rax
  struct CChildNode *v6; // rdx
  unsigned int ModifyContext; // ecx
  __int128 *v8; // rcx
  NTSTATUS v9; // eax
  signed int v10; // eax
  CElementModification *v11; // rcx
  struct CChildNode *v12; // [rsp+20h] [rbp-49h] BYREF
  __int128 v13; // [rsp+30h] [rbp-39h] BYREF
  int v14; // [rsp+40h] [rbp-29h]
  const char *v15; // [rsp+48h] [rbp-21h]
  _QWORD v16[2]; // [rsp+50h] [rbp-19h] BYREF
  int v17; // [rsp+60h] [rbp-9h]
  const char *v18; // [rsp+68h] [rbp-1h]
  void **v19; // [rsp+70h] [rbp+7h] BYREF
  int v20; // [rsp+78h] [rbp+Fh]
  int v21; // [rsp+7Ch] [rbp+13h]
  __int128 v22; // [rsp+80h] [rbp+17h]
  __int64 v23; // [rsp+A0h] [rbp+37h]
  char v24; // [rsp+A8h] [rbp+3Fh]
  int v25; // [rsp+ACh] [rbp+43h]
  __int64 v26; // [rsp+B0h] [rbp+47h]
  __int64 v27; // [rsp+B8h] [rbp+4Fh]

  v20 = 0;
  v21 = 0;
  v23 = 0;
  v2 = *(_DWORD *)(a1 + 16) == 0;
  v22 = 0;
  v19 = &SetStringIter::`vftable';
  if ( v2 )
    return 2147942432LL;
  v4 = *a2;
  v5 = *(_QWORD *)(a1 + 8);
  v25 = 0;
  v27 = 0;
  v24 = 1;
  v26 = v5;
  v13 = v4;
  ModifyContext = SetStringIter::GetModifyContext(&v19, a1, &v13, &v12);
  if ( (ModifyContext & 0x80000000) == 0 )
  {
    if ( !v26 )
    {
      v14 = 1838;
      *(_QWORD *)&v13 = "onecore\\base\\xml\\udom_modify.cpp";
      v8 = &v13;
      *((_QWORD *)&v13 + 1) = "Windows::uDom::Rtl::RtlMicrodomUpdateRemoveElement";
      v15 = "RtlIsMicrodomUpdateContextValid(HostUpdate)";
LABEL_6:
      RtlReportErrorOrigination(v8, v6, 3221225485LL);
      v9 = -1073741811;
LABEL_7:
      v10 = RtlNtStatusToDosError(v9);
      ModifyContext = (unsigned __int16)v10 | 0x80070000;
      if ( v10 <= 0 )
        return (unsigned int)v10;
      return ModifyContext;
    }
    v6 = v12;
    if ( !v12 )
    {
      v17 = 1839;
      v16[0] = "onecore\\base\\xml\\udom_modify.cpp";
      v8 = (__int128 *)v16;
      v16[1] = "Windows::uDom::Rtl::RtlMicrodomUpdateRemoveElement";
      v18 = "pToRemove != 0";
      goto LABEL_6;
    }
    v11 = *(CElementModification **)(*((_QWORD *)v12 + 7) + 112LL);
    if ( v11 )
    {
      v9 = CElementModification::RemoveChild(v11, v12);
      if ( v9 < 0 )
        goto LABEL_7;
    }
    return 0;
  }
  return ModifyContext;
}

```

## disassembly

```asm
0x180045c44  push    rbp
0x180045c46  lea     rbp, [rsp-57h]
0x180045c4b  sub     rsp, 0C0h
0x180045c52  and     [rbp+57h+var_48], 0
0x180045c56  lea     rax, ??_7SetStringIter@@6B@; const SetStringIter::`vftable'
0x180045c5d  and     [rbp+57h+var_44], 0
0x180045c61  xorps   xmm0, xmm0
0x180045c64  and     [rbp+57h+var_20], 0
0x180045c69  cmp     dword ptr [rcx+10h], 0
0x180045c6d  movdqa  [rbp+57h+var_40], xmm0
0x180045c72  mov     [rbp+57h+var_50], rax
0x180045c76  jnz     short loc_180045C82
0x180045c78  mov     eax, 80070020h
0x180045c7d  jmp     loc_180045D1A
0x180045c82  movaps  xmm0, xmmword ptr [rdx]
0x180045c85  lea     r9, [rbp+57h+var_A0]
0x180045c89  mov     rax, [rcx+8]
0x180045c8d  lea     r8, [rbp+57h+var_90]
0x180045c91  and     [rbp+57h+var_14], 0
0x180045c95  mov     rdx, rcx
0x180045c98  and     [rbp+57h+var_8], 0
0x180045c9d  lea     rcx, [rbp+57h+var_50]
0x180045ca1  mov     [rbp+57h+var_18], 1
0x180045ca5  mov     [rbp+57h+var_10], rax
0x180045ca9  movdqa  [rbp+57h+var_90], xmm0
0x180045cae  call    ?GetModifyContext@SetStringIter@@QEAAJAEAVUnattend@@VUnattendNode@@AEAUModifyContext@1@@Z; SetStringIter::GetModifyContext(Unattend &,UnattendNode,SetStringIter::ModifyContext &)
0x180045cb3  mov     ecx, eax
0x180045cb5  test    eax, eax
0x180045cb7  js      short loc_180045D18
0x180045cb9  cmp     [rbp+57h+var_10], 0
0x180045cbe  jnz     short loc_180045D23
0x180045cc0  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180045cc7  mov     [rbp+57h+var_80], 72Eh
0x180045cce  mov     qword ptr [rbp+57h+var_90], rax
0x180045cd2  lea     rcx, [rbp+57h+var_90]
0x180045cd6  lea     rax, aWindowsUdomRtl_1; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x180045cdd  mov     qword ptr [rbp+57h+var_90+8], rax
0x180045ce1  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x180045ce8  mov     [rbp+57h+var_78], rax
0x180045cec  mov     r8d, 0C000000Dh
0x180045cf2  call    RtlReportErrorOrigination
0x180045cf7  mov     eax, 0C000000Dh
0x180045cfc  mov     ecx, eax; Status
0x180045cfe  call    cs:__imp_RtlNtStatusToDosError
0x180045d05  nop     dword ptr [rax+rax+00h]
0x180045d0a  movzx   ecx, ax
0x180045d0d  or      ecx, 80070000h
0x180045d13  test    eax, eax
0x180045d15  cmovle  ecx, eax
0x180045d18  mov     eax, ecx
0x180045d1a  add     rsp, 0C0h
0x180045d21  pop     rbp
0x180045d22  retn
0x180045d23  mov     rdx, [rbp+57h+var_A0]; struct CChildNode *
0x180045d27  test    rdx, rdx
0x180045d2a  jnz     short loc_180045D5A
0x180045d2c  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\udom_modify.cpp"
0x180045d33  mov     [rbp+57h+var_60], 72Fh
0x180045d3a  mov     [rbp+57h+var_70], rax
0x180045d3e  lea     rcx, [rbp+57h+var_70]
0x180045d42  lea     rax, aWindowsUdomRtl_1; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x180045d49  mov     [rbp+57h+var_68], rax
0x180045d4d  lea     rax, aPtoremove0; "pToRemove != 0"
0x180045d54  mov     [rbp+57h+var_58], rax
0x180045d58  jmp     short loc_180045CEC
0x180045d5a  mov     rax, [rdx+38h]
0x180045d5e  mov     rcx, [rax+70h]; this
0x180045d62  test    rcx, rcx
0x180045d65  jz      short loc_180045D70
0x180045d67  call    ?RemoveChild@CElementModification@@QEAAJPEAVCChildNode@@@Z; CElementModification::RemoveChild(CChildNode *)
0x180045d6c  test    eax, eax
0x180045d6e  js      short loc_180045CFC
0x180045d70  xor     eax, eax
0x180045d72  test    eax, eax
0x180045d74  js      short loc_180045CFC
0x180045d76  xor     ecx, ecx
0x180045d78  jmp     short loc_180045D18
```
