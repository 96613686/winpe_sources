# WritePropertiesToItem(OOEntry *,ISubscriptionItem *)

- ea: `0x18000ddd8`
- end: `0x18000e108`
- name: `?WritePropertiesToItem@@YAJPEFAUOOEntry@@PEAUISubscriptionItem@@@Z`
- size: `816`
- prototype: `int(struct OOEntry *, struct ISubscriptionItem *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000b514`
- `0x18000e3c4`

## callees

- `0x18000d97c`
- `0x18000ddd8`
- `0x18001dc38`
- `0x18001dc84`
- `0x18001dd88`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000de10`
- `OLEAUT32!__imp_VariantInit` at `0x18000de10`
- `OLEAUT32!__imp_VariantClear` at `0x18000de51`
- `OLEAUT32!__imp_VariantClear` at `0x18000de8f`
- `OLEAUT32!__imp_VariantClear` at `0x18000dedf`
- `OLEAUT32!__imp_VariantClear` at `0x18000e01b`
- `OLEAUT32!__imp_VariantClear` at `0x18000de51`
- `OLEAUT32!__imp_VariantClear` at `0x18000de8f`
- `OLEAUT32!__imp_VariantClear` at `0x18000dedf`
- `OLEAUT32!__imp_VariantClear` at `0x18000e01b`

## string_xrefs

- `0x18000df02`: `DesktopComponent`

## pseudocode

```c
__int64 __fastcall WritePropertiesToItem(struct OOEntry *a1, struct ISubscriptionItem *a2)
{
  int v4; // esi
  const unsigned __int16 *v5; // rdx
  unsigned int v6; // r8d
  const unsigned __int16 *v7; // rdx
  unsigned int v9; // r8d
  unsigned int v10; // r8d
  struct ISubscriptionItemVtbl *lpVtbl; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-50h] BYREF
  _OWORD v13[3]; // [rsp+38h] [rbp-38h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( (*((_BYTE *)a1 + 4) & 0x10) != 0 )
  {
    if ( TSTR2BSTR(&pvarg, (const unsigned __int16 *)((char *)a1 + *((_QWORD *)a1 + 24))) < 0 )
      return 2147500037LL;
    WriteVariant(a2, L"URL", &pvarg);
    VariantClear(&pvarg);
  }
  if ( (*((_BYTE *)a1 + 4) & 0x20) != 0 )
  {
    if ( TSTR2BSTR(&pvarg, (const unsigned __int16 *)((char *)a1 + *((_QWORD *)a1 + 25))) < 0 )
      return 2147500037LL;
    WriteVariant(a2, L"Name", &pvarg);
    VariantClear(&pvarg);
  }
  v4 = 1;
  if ( (*((_DWORD *)a1 + 1) & 0x100) == 0 )
    goto LABEL_12;
  v5 = (const unsigned __int16 *)((char *)a1 + *((_QWORD *)a1 + 22));
  if ( *v5 )
  {
    if ( TSTR2BSTR(&pvarg, v5) >= 0 )
    {
      WriteVariant(a2, L"Username", &pvarg);
      VariantClear(&pvarg);
      goto LABEL_12;
    }
    return 2147500037LL;
  }
  WriteEMPTY(a2, L"Username");
  v4 = 0;
LABEL_12:
  if ( (*((_DWORD *)a1 + 1) & 0x200) != 0 )
  {
    if ( *((_DWORD *)a1 + 11) )
      WriteDWORD(a2, L"DesktopComponent", 1u);
    else
      WriteEMPTY(a2, L"DesktopComponent");
  }
  if ( (*((_DWORD *)a1 + 1) & 0x4000) != 0 )
  {
    if ( *((_DWORD *)a1 + 12) )
      WriteDWORD(a2, L"Channel", 1u);
    else
      WriteEMPTY(a2, L"Channel");
  }
  if ( (*((_DWORD *)a1 + 1) & 0x10000) != 0 )
  {
    if ( *((_DWORD *)a1 + 14) )
      WriteDWORD(a2, L"EnableShortcutGleam", 1u);
    else
      WriteEMPTY(a2, L"EnableShortcutGleam");
  }
  if ( (*((_DWORD *)a1 + 1) & 0x20000) != 0 )
  {
    if ( *((_DWORD *)a1 + 15) )
      WriteDWORD(a2, L"CheckChangesOnly", 1u);
    else
      WriteEMPTY(a2, L"CheckChangesOnly");
  }
  if ( (*((_DWORD *)a1 + 1) & 0x40000) != 0 )
  {
    v6 = *((_DWORD *)a1 + 29);
    if ( v6 )
      WriteDWORD(a2, L"ChannelFlags", v6);
    else
      WriteEMPTY(a2, L"ChannelFlags");
  }
  if ( (*((_BYTE *)a1 + 4) & 0x40) != 0 )
  {
    if ( *((_DWORD *)a1 + 13) )
      WriteDWORD(a2, L"EmailNotification", 1u);
    else
      WriteEMPTY(a2, L"EmailNotification");
  }
  if ( *((char *)a1 + 4) < 0 )
  {
    v7 = (const unsigned __int16 *)((char *)a1 + *((_QWORD *)a1 + 23));
    if ( *v7 )
    {
      if ( v4 )
      {
        if ( TSTR2BSTR(&pvarg, v7) < 0 )
          return 2147500037LL;
        VariantClear(&pvarg);
      }
    }
  }
  if ( (*((_BYTE *)a1 + 4) & 4) != 0 )
  {
    v9 = *((_DWORD *)a1 + 8);
    if ( v9 )
      WriteDWORD(a2, L"RecurseLevels", v9);
    else
      WriteEMPTY(a2, L"RecurseLevels");
  }
  if ( (*((_BYTE *)a1 + 4) & 2) != 0 )
    WriteDWORD(a2, L"RecurseFlags", *((_DWORD *)a1 + 9));
  if ( (*((_BYTE *)a1 + 4) & 8) != 0 )
    WriteDWORD(a2, L"ActualSizeKB", *((_DWORD *)a1 + 7));
  if ( (*((_BYTE *)a1 + 4) & 1) != 0 )
  {
    v10 = *((_DWORD *)a1 + 6);
    if ( v10 )
      WriteDWORD(a2, L"MaxSizeKB", v10);
    else
      WriteEMPTY(a2, L"MaxSizeKB");
  }
  lpVtbl = a2->lpVtbl;
  memset(v13, 0, 44);
  LODWORD(v13[0]) = 44;
  if ( ((int (__fastcall *)(struct ISubscriptionItem *, _OWORD *))lpVtbl->GetSubscriptionItemInfo)(a2, v13) >= 0 )
  {
    DWORD1(v13[0]) = *((_DWORD *)a1 + 38);
    ((void (__fastcall *)(struct ISubscriptionItem *, _OWORD *))a2->lpVtbl->SetSubscriptionItemInfo)(a2, v13);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ddd8  mov     [rsp-28h+arg_10], rbx
0x18000dddd  push    rbp
0x18000ddde  push    rsi
0x18000dddf  push    rdi
0x18000dde0  push    r14
0x18000dde2  push    r15
0x18000dde4  mov     rbp, rsp
0x18000dde7  sub     rsp, 70h
0x18000ddeb  mov     rax, cs:__security_cookie
0x18000ddf2  xor     rax, rsp
0x18000ddf5  mov     [rbp+var_8], rax
0x18000ddf9  mov     rbx, rcx
0x18000ddfc  xorps   xmm0, xmm0
0x18000ddff  xor     eax, eax
0x18000de01  lea     rcx, [rbp+pvarg]; pvarg
0x18000de05  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000de09  mov     qword ptr [rbp+pvarg+10h], rax
0x18000de0d  mov     rdi, rdx
0x18000de10  call    cs:__imp_VariantInit
0x18000de16  xor     r14d, r14d
0x18000de19  test    byte ptr [rbx+4], 10h
0x18000de1d  jz      short loc_18000DE57
0x18000de1f  mov     rdx, [rbx+0C0h]
0x18000de26  lea     rcx, [rbp+pvarg]; struct tagVARIANT *
0x18000de2a  add     rdx, rbx; unsigned __int16 *
0x18000de2d  call    ?TSTR2BSTR@@YAJPEAUtagVARIANT@@PEBG@Z; TSTR2BSTR(tagVARIANT *,ushort const *)
0x18000de32  test    eax, eax
0x18000de34  js      loc_18000E00D
0x18000de3a  lea     r8, [rbp+pvarg]; struct tagVARIANT *
0x18000de3e  mov     rcx, rdi; struct ISubscriptionItem *
0x18000de41  lea     rdx, ?c_szPropURL@@3QBGB; "URL"
0x18000de48  call    ?WriteVariant@@YAJPEAUISubscriptionItem@@PEBGPEBUtagVARIANT@@@Z; WriteVariant(ISubscriptionItem *,ushort const *,tagVARIANT const *)
0x18000de4d  lea     rcx, [rbp+pvarg]; pvarg
0x18000de51  call    cs:__imp_VariantClear
0x18000de57  test    byte ptr [rbx+4], 20h
0x18000de5b  jz      short loc_18000DE95
0x18000de5d  mov     rdx, [rbx+0C8h]
0x18000de64  lea     rcx, [rbp+pvarg]; struct tagVARIANT *
0x18000de68  add     rdx, rbx; unsigned __int16 *
0x18000de6b  call    ?TSTR2BSTR@@YAJPEAUtagVARIANT@@PEBG@Z; TSTR2BSTR(tagVARIANT *,ushort const *)
0x18000de70  test    eax, eax
0x18000de72  js      loc_18000E00D
0x18000de78  lea     r8, [rbp+pvarg]; struct tagVARIANT *
0x18000de7c  mov     rcx, rdi; struct ISubscriptionItem *
0x18000de7f  lea     rdx, ?c_szPropName@@3QBGB; "Name"
0x18000de86  call    ?WriteVariant@@YAJPEAUISubscriptionItem@@PEBGPEBUtagVARIANT@@@Z; WriteVariant(ISubscriptionItem *,ushort const *,tagVARIANT const *)
0x18000de8b  lea     rcx, [rbp+pvarg]; pvarg
0x18000de8f  call    cs:__imp_VariantClear
0x18000de95  test    dword ptr [rbx+4], 100h
0x18000de9c  mov     r15d, 1
0x18000dea2  mov     esi, r15d
0x18000dea5  jz      short loc_18000DEF9
0x18000dea7  mov     rdx, [rbx+0B0h]
0x18000deae  add     rdx, rbx; unsigned __int16 *
0x18000deb1  cmp     [rdx], r14w
0x18000deb5  jz      short loc_18000DEE7
0x18000deb7  lea     rcx, [rbp+pvarg]; struct tagVARIANT *
0x18000debb  call    ?TSTR2BSTR@@YAJPEAUtagVARIANT@@PEBG@Z; TSTR2BSTR(tagVARIANT *,ushort const *)
0x18000dec0  test    eax, eax
0x18000dec2  js      loc_18000E00D
0x18000dec8  lea     r8, [rbp+pvarg]; struct tagVARIANT *
0x18000decc  mov     rcx, rdi; struct ISubscriptionItem *
0x18000decf  lea     rdx, ?c_szPropCrawlUsername@@3QBGB; "Username"
0x18000ded6  call    ?WriteVariant@@YAJPEAUISubscriptionItem@@PEBGPEBUtagVARIANT@@@Z; WriteVariant(ISubscriptionItem *,ushort const *,tagVARIANT const *)
0x18000dedb  lea     rcx, [rbp+pvarg]; pvarg
0x18000dedf  call    cs:__imp_VariantClear
0x18000dee5  jmp     short loc_18000DEF9
0x18000dee7  lea     rdx, ?c_szPropCrawlUsername@@3QBGB; "Username"
0x18000deee  mov     rcx, rdi; struct ISubscriptionItem *
0x18000def1  call    ?WriteEMPTY@@YAJPEAUISubscriptionItem@@PEBG@Z; WriteEMPTY(ISubscriptionItem *,ushort const *)
0x18000def6  mov     esi, r14d
0x18000def9  test    dword ptr [rbx+4], 200h
0x18000df00  jz      short loc_18000DF21
0x18000df02  lea     rdx, ?c_szPropDesktopComponent@@3QBGB; "DesktopComponent"
0x18000df09  mov     rcx, rdi; struct ISubscriptionItem *
0x18000df0c  cmp     [rbx+2Ch], r14d
0x18000df10  jz      short loc_18000DF1C
0x18000df12  mov     r8d, r15d; unsigned int
0x18000df15  call    ?WriteDWORD@@YAJPEAUISubscriptionItem@@PEBGK@Z; WriteDWORD(ISubscriptionItem *,ushort const *,ulong)
0x18000df1a  jmp     short loc_18000DF21
0x18000df1c  call    ?WriteEMPTY@@YAJPEAUISubscriptionItem@@PEBG@Z; WriteEMPTY(ISubscriptionItem *,ushort const *)
0x18000df21  test    dword ptr [rbx+4], 4000h
0x18000df28  jz      short loc_18000DF49
0x18000df2a  lea     rdx, ?c_szPropChannel@@3QBGB; "Channel"
0x18000df31  mov     rcx, rdi; struct ISubscriptionItem *
0x18000df34  cmp     [rbx+30h], r14d
0x18000df38  jz      short loc_18000DF44
0x18000df3a  mov     r8d, r15d; unsigned int
0x18000df3d  call    ?WriteDWORD@@YAJPEAUISubscriptionItem@@PEBGK@Z; WriteDWORD(ISubscriptionItem *,ushort const *,ulong)
0x18000df42  jmp     short loc_18000DF49
0x18000df44  call    ?WriteEMPTY@@YAJPEAUISubscriptionItem@@PEBG@Z; WriteEMPTY(ISubscriptionItem *,ushort const *)
0x18000df49  test    dword ptr [rbx+4], 10000h
0x18000df50  jz      short loc_18000DF71
0x18000df52  lea     rdx, ?c_szPropEnableShortcutGleam@@3QBGB; "EnableShortcutGleam"
0x18000df59  mov     rcx, rdi; struct ISubscriptionItem *
0x18000df5c  cmp     [rbx+38h], r14d
0x18000df60  jz      short loc_18000DF6C
0x18000df62  mov     r8d, r15d; unsigned int
0x18000df65  call    ?WriteDWORD@@YAJPEAUISubscriptionItem@@PEBGK@Z; WriteDWORD(ISubscriptionItem *,ushort const *,ulong)
0x18000df6a  jmp     short loc_18000DF71
0x18000df6c  call    ?WriteEMPTY@@YAJPEAUISubscriptionItem@@PEBG@Z; WriteEMPTY(ISubscriptionItem *,ushort const *)
0x18000df71  test    dword ptr [rbx+4], 20000h
0x18000df78  jz      short loc_18000DF99
0x18000df7a  lea     rdx, ?c_szPropCrawlChangesOnly@@3QBGB; "CheckChangesOnly"
0x18000df81  mov     rcx, rdi; struct ISubscriptionItem *
0x18000df84  cmp     [rbx+3Ch], r14d
0x18000df88  jz      short loc_18000DF94
0x18000df8a  mov     r8d, r15d; unsigned int
0x18000df8d  call    ?WriteDWORD@@YAJPEAUISubscriptionItem@@PEBGK@Z; WriteDWORD(ISubscriptionItem *,ushort const *,ulong)
0x18000df92  jmp     short loc_18000DF99
0x18000df94  call    ?WriteEMPTY@@YAJPEAUISubscriptionItem@@PEBG@Z; WriteEMPTY(ISubscriptionItem *,ushort const *)
0x18000df99  test    dword ptr [rbx+4], 40000h
0x18000dfa0  jz      short loc_18000DFC1
0x18000dfa2  mov     r8d, [rbx+74h]; unsigned int
0x18000dfa6  lea     rdx, ?c_szPropChannelFlags@@3QBGB; "ChannelFlags"
0x18000dfad  mov     rcx, rdi; struct ISubscriptionItem *
0x18000dfb0  test    r8d, r8d
0x18000dfb3  jz      short loc_18000DFBC
0x18000dfb5  call    ?WriteDWORD@@YAJPEAUISubscriptionItem@@PEBGK@Z; WriteDWORD(ISubscriptionItem *,ushort const *,ulong)
0x18000dfba  jmp     short loc_18000DFC1
0x18000dfbc  call    ?WriteEMPTY@@YAJPEAUISubscriptionItem@@PEBG@Z; WriteEMPTY(ISubscriptionItem *,ushort const *)
0x18000dfc1  test    byte ptr [rbx+4], 40h
0x18000dfc5  jz      short loc_18000DFE6
0x18000dfc7  lea     rdx, ?c_szPropEmailNotf@@3QBGB; "EmailNotification"
0x18000dfce  mov     rcx, rdi; struct ISubscriptionItem *
0x18000dfd1  cmp     [rbx+34h], r14d
0x18000dfd5  jz      short loc_18000DFE1
0x18000dfd7  mov     r8d, r15d; unsigned int
0x18000dfda  call    ?WriteDWORD@@YAJPEAUISubscriptionItem@@PEBGK@Z; WriteDWORD(ISubscriptionItem *,ushort const *,ulong)
0x18000dfdf  jmp     short loc_18000DFE6
0x18000dfe1  call    ?WriteEMPTY@@YAJPEAUISubscriptionItem@@PEBG@Z; WriteEMPTY(ISubscriptionItem *,ushort const *)
0x18000dfe6  test    byte ptr [rbx+4], 80h
0x18000dfea  jz      short loc_18000E021
0x18000dfec  mov     rdx, [rbx+0B8h]
0x18000dff3  add     rdx, rbx; unsigned __int16 *
0x18000dff6  cmp     [rdx], r14w
0x18000dffa  jz      short loc_18000E021
0x18000dffc  test    esi, esi
0x18000dffe  jz      short loc_18000E021
0x18000e000  lea     rcx, [rbp+pvarg]; struct tagVARIANT *
0x18000e004  call    ?TSTR2BSTR@@YAJPEAUtagVARIANT@@PEBG@Z; TSTR2BSTR(tagVARIANT *,ushort const *)
0x18000e009  test    eax, eax
0x18000e00b  jns     short loc_18000E017
0x18000e00d  mov     eax, 80004005h
0x18000e012  jmp     loc_18000E0E8
0x18000e017  lea     rcx, [rbp+pvarg]; pvarg
0x18000e01b  call    cs:__imp_VariantClear
0x18000e021  test    byte ptr [rbx+4], 4
0x18000e025  jz      short loc_18000E046
0x18000e027  mov     r8d, [rbx+20h]; unsigned int
0x18000e02b  lea     rdx, ?c_szPropCrawlLevels@@3QBGB; "RecurseLevels"
0x18000e032  mov     rcx, rdi; struct ISubscriptionItem *
0x18000e035  test    r8d, r8d
0x18000e038  jz      short loc_18000E041
0x18000e03a  call    ?WriteDWORD@@YAJPEAUISubscriptionItem@@PEBGK@Z; WriteDWORD(ISubscriptionItem *,ushort const *,ulong)
0x18000e03f  jmp     short loc_18000E046
0x18000e041  call    ?WriteEMPTY@@YAJPEAUISubscriptionItem@@PEBG@Z; WriteEMPTY(ISubscriptionItem *,ushort const *)
0x18000e046  test    byte ptr [rbx+4], 2
0x18000e04a  jz      short loc_18000E05F
0x18000e04c  mov     r8d, [rbx+24h]; unsigned int
0x18000e050  lea     rdx, ?c_szPropCrawlFlags@@3QBGB; "RecurseFlags"
0x18000e057  mov     rcx, rdi; struct ISubscriptionItem *
0x18000e05a  call    ?WriteDWORD@@YAJPEAUISubscriptionItem@@PEBGK@Z; WriteDWORD(ISubscriptionItem *,ushort const *,ulong)
0x18000e05f  test    byte ptr [rbx+4], 8
0x18000e063  jz      short loc_18000E078
0x18000e065  mov     r8d, [rbx+1Ch]; unsigned int
0x18000e069  lea     rdx, ?c_szPropCrawlActualSize@@3QBGB; "ActualSizeKB"
0x18000e070  mov     rcx, rdi; struct ISubscriptionItem *
0x18000e073  call    ?WriteDWORD@@YAJPEAUISubscriptionItem@@PEBGK@Z; WriteDWORD(ISubscriptionItem *,ushort const *,ulong)
0x18000e078  test    [rbx+4], r15b
0x18000e07c  jz      short loc_18000E09D
0x18000e07e  mov     r8d, [rbx+18h]; unsigned int
0x18000e082  lea     rdx, ?c_szPropCrawlMaxSize@@3QBGB; "MaxSizeKB"
0x18000e089  mov     rcx, rdi; struct ISubscriptionItem *
0x18000e08c  test    r8d, r8d
0x18000e08f  jz      short loc_18000E098
0x18000e091  call    ?WriteDWORD@@YAJPEAUISubscriptionItem@@PEBGK@Z; WriteDWORD(ISubscriptionItem *,ushort const *,ulong)
0x18000e096  jmp     short loc_18000E09D
0x18000e098  call    ?WriteEMPTY@@YAJPEAUISubscriptionItem@@PEBG@Z; WriteEMPTY(ISubscriptionItem *,ushort const *)
0x18000e09d  mov     rax, [rdi]
0x18000e0a0  lea     rdx, [rbp+var_38]
0x18000e0a4  xorps   xmm0, xmm0
0x18000e0a7  mov     rcx, rdi
0x18000e0aa  movups  [rbp+var_38], xmm0
0x18000e0ae  mov     dword ptr [rbp+var_38], 2Ch ; ','
0x18000e0b5  mov     rax, [rax+20h]
0x18000e0b9  movups  xmmword ptr [rbp+var_28], xmm0
0x18000e0bd  movups  xmmword ptr [rbp+var_28+0Ch], xmm0
0x18000e0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0c6  test    eax, eax
0x18000e0c8  js      short loc_18000E0E6
0x18000e0ca  mov     eax, [rbx+98h]
0x18000e0d0  lea     rdx, [rbp+var_38]
0x18000e0d4  mov     dword ptr [rbp+var_38+4], eax
0x18000e0d7  mov     rcx, rdi
0x18000e0da  mov     rax, [rdi]
0x18000e0dd  mov     rax, [rax+28h]
0x18000e0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0e6  xor     eax, eax
0x18000e0e8  mov     rcx, [rbp+var_8]
0x18000e0ec  xor     rcx, rsp; StackCookie
0x18000e0ef  call    __security_check_cookie
0x18000e0f4  mov     rbx, [rsp+70h+arg_10]
0x18000e0fc  add     rsp, 70h
0x18000e100  pop     r15
0x18000e102  pop     r14
0x18000e104  pop     rdi
0x18000e105  pop     rsi
0x18000e106  pop     rbp
0x18000e107  retn
```
