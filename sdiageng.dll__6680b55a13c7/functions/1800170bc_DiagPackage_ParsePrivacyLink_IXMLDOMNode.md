# DiagPackage::ParsePrivacyLink(IXMLDOMNode *)

- ea: `0x1800170bc`
- end: `0x1800171f3`
- name: `?ParsePrivacyLink@DiagPackage@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(DiagPackage *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180016630`

## callees

- `0x1800012a4`
- `0x1800170bc`
- `0x180026fa0`
- `0x180027aa0`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800171e0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800171e0`

## string_xrefs

- `0x1800171c5`: `DiagPackage::ParsePrivacyLink`
- `0x180017144`: `Settings::set_PackagePrivacyLink`
- `0x180017177`: `Settings::set_PackagePrivacyLink`

## pseudocode

```c
__int64 __fastcall DiagPackage::ParsePrivacyLink(DiagPackage *this, struct IXMLDOMNode *a2)
{
  int v3; // ebx
  int v4; // r8d
  int v5; // eax
  int v6; // r9d
  __int64 v7; // rdi
  int v8; // eax
  unsigned __int16 *v9; // rcx
  void *v10; // rcx
  unsigned __int16 *v12; // [rsp+38h] [rbp+10h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp+18h] BYREF

  bstrString = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
    v4 = 2503;
LABEL_18:
    v6 = v3;
    goto LABEL_19;
  }
  if ( !*((_QWORD *)this + 1) )
  {
    v3 = -2147467261;
    v4 = 2504;
    goto LABEL_18;
  }
  v5 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))a2->lpVtbl->get_text)(a2, &bstrString);
  v3 = v5;
  if ( v5 < 0 )
  {
    v6 = v5;
    v4 = 2507;
LABEL_19:
    SdpDebugTrace(1u, L"DiagPackage::ParsePrivacyLink", v4, v6);
    goto LABEL_20;
  }
  v12 = 0;
  if ( !bstrString )
  {
    v3 = -2147024809;
    SdpDebugTrace(1u, L"Settings::set_PackagePrivacyLink", 1231, -2147024809);
LABEL_17:
    v4 = 2510;
    goto LABEL_18;
  }
  v7 = *((_QWORD *)this + 1);
  v8 = SdpStrCpy(&v12, bstrString);
  v3 = v8;
  if ( v8 >= 0 )
  {
    v10 = *(void **)(v7 + 40);
    if ( v10 )
      operator delete(v10);
    v9 = 0;
    *(_QWORD *)(v7 + 40) = v12;
  }
  else
  {
    SdpDebugTrace(1u, L"Settings::set_PackagePrivacyLink", 1234, v8);
    v9 = v12;
  }
  if ( v9 )
    operator delete(v9);
  if ( v3 < 0 )
    goto LABEL_17;
LABEL_20:
  if ( bstrString )
    SysFreeString(bstrString);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800170bc  mov     [rsp+arg_0], rbx
0x1800170c1  push    rdi
0x1800170c2  sub     rsp, 20h
0x1800170c6  mov     [rsp+28h+bstrString], 0
0x1800170cf  mov     r8, rdx
0x1800170d2  mov     rdi, rcx
0x1800170d5  test    rdx, rdx
0x1800170d8  jnz     short loc_1800170EA
0x1800170da  mov     ebx, 80070057h
0x1800170df  mov     r8d, 9C7h
0x1800170e5  jmp     loc_1800171C2
0x1800170ea  cmp     qword ptr [rcx+8], 0
0x1800170ef  jnz     short loc_180017101
0x1800170f1  mov     ebx, 80004003h
0x1800170f6  mov     r8d, 9C8h
0x1800170fc  jmp     loc_1800171C2
0x180017101  mov     rax, [rdx]
0x180017104  mov     rcx, r8
0x180017107  lea     rdx, [rsp+28h+bstrString]
0x18001710c  mov     rax, [rax+0D0h]
0x180017113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017118  mov     ebx, eax
0x18001711a  test    eax, eax
0x18001711c  jns     short loc_18001712C
0x18001711e  mov     r9d, eax
0x180017121  mov     r8d, 9CBh
0x180017127  jmp     loc_1800171C5
0x18001712c  mov     rdx, [rsp+28h+bstrString]; unsigned __int16 *
0x180017131  mov     [rsp+28h+arg_8], 0
0x18001713a  test    rdx, rdx
0x18001713d  jnz     short loc_180017160
0x18001713f  mov     ebx, 80070057h
0x180017144  lea     rdx, aSettingsSetPac_1; "Settings::set_PackagePrivacyLink"
0x18001714b  mov     r9d, ebx; int
0x18001714e  mov     r8d, 4CFh; int
0x180017154  mov     ecx, 1; Level
0x180017159  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001715e  jmp     short loc_1800171BC
0x180017160  mov     rdi, [rdi+8]
0x180017164  lea     rcx, [rsp+28h+arg_8]; unsigned __int16 **
0x180017169  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x18001716e  mov     ebx, eax
0x180017170  test    eax, eax
0x180017172  jns     short loc_180017195
0x180017174  mov     r9d, eax; int
0x180017177  lea     rdx, aSettingsSetPac_1; "Settings::set_PackagePrivacyLink"
0x18001717e  mov     r8d, 4D2h; int
0x180017184  mov     ecx, 1; Level
0x180017189  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001718e  mov     rcx, [rsp+28h+arg_8]
0x180017193  jmp     short loc_1800171AE
0x180017195  mov     rcx, [rdi+28h]; Block
0x180017199  test    rcx, rcx
0x18001719c  jz      short loc_1800171A3
0x18001719e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800171a3  mov     rax, [rsp+28h+arg_8]
0x1800171a8  xor     ecx, ecx; Block
0x1800171aa  mov     [rdi+28h], rax
0x1800171ae  test    rcx, rcx
0x1800171b1  jz      short loc_1800171B8
0x1800171b3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800171b8  test    ebx, ebx
0x1800171ba  jns     short loc_1800171D6
0x1800171bc  mov     r8d, 9CEh; int
0x1800171c2  mov     r9d, ebx; int
0x1800171c5  lea     rdx, aDiagpackagePar; "DiagPackage::ParsePrivacyLink"
0x1800171cc  mov     ecx, 1; Level
0x1800171d1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800171d6  mov     rcx, [rsp+28h+bstrString]; bstrString
0x1800171db  test    rcx, rcx
0x1800171de  jz      short loc_1800171E6
0x1800171e0  call    cs:__imp_SysFreeString
0x1800171e6  mov     eax, ebx
0x1800171e8  mov     rbx, [rsp+28h+arg_0]
0x1800171ed  add     rsp, 20h
0x1800171f1  pop     rdi
0x1800171f2  retn
```
