# Rootcause::AddXmlToReport(ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,ushort *)

- ea: `0x180018718`
- end: `0x180018a93`
- name: `?AddXmlToReport@Rootcause@@QEAAJPEAG000000@Z`
- size: `891`
- prototype: `__int64 __fastcall(Rootcause *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, wchar_t *String1, wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180014544`

## callees

- `0x180004d58`
- `0x180018718`
- `0x180019b88`
- `0x180019f40`
- `0x180026fa0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001884e`
- `msvcrt!_wcsicmp` at `0x18001886b`
- `msvcrt!_wcsicmp` at `0x18001898c`
- `msvcrt!_wcsicmp` at `0x18001884e`
- `msvcrt!_wcsicmp` at `0x18001886b`
- `msvcrt!_wcsicmp` at `0x18001898c`

## string_xrefs

- `0x180018a71`: `Rootcause::AddXmlToReport`

## pseudocode

```c
__int64 __fastcall Rootcause::AddXmlToReport(
        Rootcause *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        wchar_t *String1,
        wchar_t *a8)
{
  int v12; // r9d
  int v13; // r8d
  unsigned int v14; // ebx
  unsigned __int16 *v15; // r14
  __int64 v16; // rax
  wchar_t *v17; // r8
  int Instance; // eax
  __int64 v19; // rcx
  __int64 v20; // rdx
  struct IXMLDOMDocument2 *v21; // rdx
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v22; // rax
  struct IXMLDOMDocument2 *v23; // rdx
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v25; // [rsp+88h] [rbp+10h] BYREF

  v25 = 0;
  if ( !a2 )
  {
    v12 = -2147024809;
    v13 = 1570;
    v14 = -2147024809;
LABEL_51:
    SdpDebugTrace(1u, L"Rootcause::AddXmlToReport", v13, v12);
    return v14;
  }
  if ( !a3 )
  {
    v12 = -2147024809;
    v13 = 1571;
    v14 = -2147024809;
    goto LABEL_51;
  }
  if ( !a4 )
  {
    v12 = -2147024809;
    v13 = 1572;
    v14 = -2147024809;
    goto LABEL_51;
  }
  if ( !a5 )
  {
    v12 = -2147024809;
    v13 = 1573;
    v14 = -2147024809;
    goto LABEL_51;
  }
  v15 = a6;
  if ( !a6 )
  {
    v12 = -2147024809;
    v13 = 1574;
    v14 = -2147024809;
    goto LABEL_51;
  }
  if ( !String1 )
  {
    v12 = -2147024809;
    v13 = 1575;
    v14 = -2147024809;
    goto LABEL_51;
  }
  if ( !a8 )
  {
    v12 = -2147024809;
    v13 = 1576;
    v14 = -2147024809;
    goto LABEL_51;
  }
  v16 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
  {
    v12 = -2147467261;
    v13 = 1578;
    v14 = -2147467261;
    goto LABEL_51;
  }
  if ( *(_DWORD *)(v16 + 88) == 3 )
  {
    if ( _wcsicmp(String1, *((const wchar_t **)this + 5)) )
    {
      return 1;
    }
    else
    {
      Instance = Rootcause::GetInstance(this, *((struct _LIST_ENTRY **)this + 15), a8, &v25);
      v14 = Instance;
      if ( Instance < 0 )
      {
        v13 = 1590;
        goto LABEL_50;
      }
      v22 = v25;
      if ( !v25 )
      {
        Instance = Rootcause::CreateInstance(this, *((_QWORD *)this + 15), a8, 0, 0, 0, &v25);
        v14 = Instance;
        if ( Instance < 0 )
        {
          v13 = 1603;
          goto LABEL_50;
        }
        v22 = v25;
      }
      v23 = (struct IXMLDOMDocument2 *)*((_QWORD *)v22 + 6);
      if ( !v23 )
      {
        v12 = -2147467261;
        v13 = 1606;
        v14 = -2147467261;
        goto LABEL_51;
      }
      Instance = SdpUpdateReportData(*(struct Settings **)this, v23, a5, a2, a3, a4, v15);
      v14 = Instance;
      if ( Instance < 0 )
      {
        v13 = 1615;
        goto LABEL_50;
      }
    }
  }
  else
  {
    if ( *(_DWORD *)(v16 + 88) != 5 )
    {
      v14 = -2147020579;
      v13 = 1653;
      v12 = -2147020579;
      goto LABEL_51;
    }
    if ( _wcsicmp(String1, &word_18002DFCC) || _wcsicmp(a8, &word_18002DFCC) )
    {
      v12 = -2147024809;
      v13 = 1623;
      v14 = -2147024809;
      goto LABEL_51;
    }
    v17 = (wchar_t *)*((_QWORD *)this + 14);
    if ( !v17 )
    {
      v12 = -2147467261;
      v13 = 1626;
      v14 = -2147467261;
      goto LABEL_51;
    }
    Instance = Rootcause::GetInstance(this, *((struct _LIST_ENTRY **)this + 15), v17, &v25);
    v14 = Instance;
    if ( Instance < 0 )
    {
      v13 = 1628;
LABEL_50:
      v12 = Instance;
      goto LABEL_51;
    }
    if ( !v25 )
    {
      v12 = -2147467261;
      v13 = 1629;
      v14 = -2147467261;
      goto LABEL_51;
    }
    v19 = *((int *)this + 26);
    if ( (int)v19 < 0 || (unsigned int)v19 >= *((_DWORD *)v25 + 16) )
    {
      v14 = -2147418113;
      v13 = 1634;
      v12 = -2147418113;
      goto LABEL_51;
    }
    v20 = *((_QWORD *)v25 + 7);
    if ( !v20 )
    {
      v12 = -2147467261;
      v13 = 1637;
      v14 = -2147467261;
      goto LABEL_51;
    }
    v21 = *(struct IXMLDOMDocument2 **)(v20 + 16 * v19 + 8);
    if ( !v21 )
    {
      v12 = -2147467261;
      v13 = 1638;
      v14 = -2147467261;
      goto LABEL_51;
    }
    Instance = SdpUpdateReportData(*(struct Settings **)this, v21, a5, a2, a3, a4, v15);
    v14 = Instance;
    if ( Instance < 0 )
    {
      v13 = 1647;
      goto LABEL_50;
    }
  }
  return v14;
}

```

## disassembly

```asm
0x180018718  mov     rax, rsp
0x18001871b  push    rbx
0x18001871c  push    rdi
0x18001871d  push    r12
0x18001871f  push    r13
0x180018721  push    r14
0x180018723  push    r15
0x180018725  sub     rsp, 48h
0x180018729  mov     qword ptr [rax+10h], 0
0x180018731  mov     r15, r9
0x180018734  mov     r12, r8
0x180018737  mov     r13, rdx
0x18001873a  mov     rdi, rcx
0x18001873d  test    rdx, rdx
0x180018740  jnz     short loc_180018756
0x180018742  mov     r9d, 80070057h
0x180018748  mov     r8d, 622h
0x18001874e  mov     ebx, r9d
0x180018751  jmp     loc_180018A71
0x180018756  test    r12, r12
0x180018759  jnz     short loc_18001876F
0x18001875b  mov     r9d, 80070057h
0x180018761  mov     r8d, 623h
0x180018767  mov     ebx, r9d
0x18001876a  jmp     loc_180018A71
0x18001876f  test    r15, r15
0x180018772  jnz     short loc_180018788
0x180018774  mov     r9d, 80070057h
0x18001877a  mov     r8d, 624h
0x180018780  mov     ebx, r9d
0x180018783  jmp     loc_180018A71
0x180018788  cmp     [rsp+78h+arg_20], 0
0x180018791  jnz     short loc_1800187A7
0x180018793  mov     r9d, 80070057h
0x180018799  mov     r8d, 625h
0x18001879f  mov     ebx, r9d
0x1800187a2  jmp     loc_180018A71
0x1800187a7  mov     r14, [rsp+78h+arg_28]
0x1800187af  test    r14, r14
0x1800187b2  jnz     short loc_1800187C8
0x1800187b4  mov     r9d, 80070057h
0x1800187ba  mov     r8d, 626h
0x1800187c0  mov     ebx, r9d
0x1800187c3  jmp     loc_180018A71
0x1800187c8  mov     rcx, [rsp+78h+String1]; String1
0x1800187d0  test    rcx, rcx
0x1800187d3  jnz     short loc_1800187E9
0x1800187d5  mov     r9d, 80070057h
0x1800187db  mov     r8d, 627h
0x1800187e1  mov     ebx, r9d
0x1800187e4  jmp     loc_180018A71
0x1800187e9  cmp     [rsp+78h+arg_38], 0
0x1800187f2  jnz     short loc_180018808
0x1800187f4  mov     r9d, 80070057h
0x1800187fa  mov     r8d, 628h
0x180018800  mov     ebx, r9d
0x180018803  jmp     loc_180018A71
0x180018808  mov     rax, [rdi]
0x18001880b  test    rax, rax
0x18001880e  jnz     short loc_180018824
0x180018810  mov     r9d, 80004003h
0x180018816  mov     r8d, 62Ah
0x18001881c  mov     ebx, r9d
0x18001881f  jmp     loc_180018A71
0x180018824  cmp     dword ptr [rax+58h], 3
0x180018828  jz      loc_180018988
0x18001882e  cmp     dword ptr [rax+58h], 5
0x180018832  jz      short loc_180018847
0x180018834  mov     ebx, 800710DDh
0x180018839  mov     r8d, 675h
0x18001883f  mov     r9d, ebx
0x180018842  jmp     loc_180018A71
0x180018847  lea     rdx, word_18002DFCC; String2
0x18001884e  call    cs:__imp__wcsicmp
0x180018854  test    eax, eax
0x180018856  jnz     loc_180018974
0x18001885c  mov     rcx, [rsp+78h+arg_38]; String1
0x180018864  lea     rdx, word_18002DFCC; String2
0x18001886b  call    cs:__imp__wcsicmp
0x180018871  test    eax, eax
0x180018873  jnz     loc_180018974
0x180018879  mov     r8, [rdi+70h]; String1
0x18001887d  test    r8, r8
0x180018880  jnz     short loc_180018896
0x180018882  mov     r9d, 80004003h
0x180018888  mov     r8d, 65Ah
0x18001888e  mov     ebx, r9d
0x180018891  jmp     loc_180018A71
0x180018896  mov     rdx, [rdi+78h]; struct _LIST_ENTRY *
0x18001889a  lea     r9, [rsp+78h+arg_8]; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **
0x1800188a2  mov     rcx, rdi; this
0x1800188a5  call    ?GetInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEBGPEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::GetInstance(_LIST_ENTRY *,ushort const *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x1800188aa  mov     ebx, eax
0x1800188ac  test    eax, eax
0x1800188ae  jns     short loc_1800188BB
0x1800188b0  mov     r8d, 65Ch
0x1800188b6  jmp     loc_180018A6E
0x1800188bb  mov     rax, [rsp+78h+arg_8]
0x1800188c3  test    rax, rax
0x1800188c6  jnz     short loc_1800188DC
0x1800188c8  mov     r9d, 80004003h
0x1800188ce  mov     r8d, 65Dh
0x1800188d4  mov     ebx, r9d
0x1800188d7  jmp     loc_180018A71
0x1800188dc  movsxd  rcx, dword ptr [rdi+68h]
0x1800188e0  test    ecx, ecx
0x1800188e2  js      short loc_180018961
0x1800188e4  cmp     ecx, [rax+40h]
0x1800188e7  jnb     short loc_180018961
0x1800188e9  mov     rdx, [rax+38h]
0x1800188ed  test    rdx, rdx
0x1800188f0  jnz     short loc_180018906
0x1800188f2  mov     r9d, 80004003h
0x1800188f8  mov     r8d, 665h
0x1800188fe  mov     ebx, r9d
0x180018901  jmp     loc_180018A71
0x180018906  mov     rax, rcx
0x180018909  add     rax, rax
0x18001890c  mov     rdx, [rdx+rax*8+8]; struct IXMLDOMDocument2 *
0x180018911  test    rdx, rdx
0x180018914  jnz     short loc_18001892A
0x180018916  mov     r9d, 80004003h
0x18001891c  mov     r8d, 666h
0x180018922  mov     ebx, r9d
0x180018925  jmp     loc_180018A71
0x18001892a  mov     r8, [rsp+78h+arg_20]; unsigned __int16 *
0x180018932  mov     r9, r13; unsigned __int16 *
0x180018935  mov     rcx, [rdi]; struct Settings *
0x180018938  mov     [rsp+78h+var_48], r14; unsigned __int16 *
0x18001893d  mov     [rsp+78h+var_50], r15; unsigned __int16 *
0x180018942  mov     [rsp+78h+var_58], r12; unsigned __int16 *
0x180018947  call    ?SdpUpdateReportData@@YAJPEAVSettings@@PEAUIXMLDOMDocument2@@PEAG2222@Z; SdpUpdateReportData(Settings *,IXMLDOMDocument2 *,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18001894c  mov     ebx, eax
0x18001894e  test    eax, eax
0x180018950  jns     loc_180018A82
0x180018956  mov     r8d, 66Fh
0x18001895c  jmp     loc_180018A6E
0x180018961  mov     ebx, 8000FFFFh
0x180018966  mov     r8d, 662h
0x18001896c  mov     r9d, ebx
0x18001896f  jmp     loc_180018A71
0x180018974  mov     r9d, 80070057h
0x18001897a  mov     r8d, 657h
0x180018980  mov     ebx, r9d
0x180018983  jmp     loc_180018A71
0x180018988  mov     rdx, [rdi+28h]; String2
0x18001898c  call    cs:__imp__wcsicmp
0x180018992  test    eax, eax
0x180018994  jz      short loc_1800189A0
0x180018996  mov     ebx, 1
0x18001899b  jmp     loc_180018A82
0x1800189a0  mov     r8, [rsp+78h+arg_38]; String1
0x1800189a8  lea     r9, [rsp+78h+arg_8]; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **
0x1800189b0  mov     rdx, [rdi+78h]; struct _LIST_ENTRY *
0x1800189b4  mov     rcx, rdi; this
0x1800189b7  call    ?GetInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEBGPEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::GetInstance(_LIST_ENTRY *,ushort const *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x1800189bc  mov     ebx, eax
0x1800189be  test    eax, eax
0x1800189c0  jns     short loc_1800189CD
0x1800189c2  mov     r8d, 636h
0x1800189c8  jmp     loc_180018A6E
0x1800189cd  mov     rax, [rsp+78h+arg_8]
0x1800189d5  test    rax, rax
0x1800189d8  jnz     short loc_180018A26
0x1800189da  mov     r8, [rsp+78h+arg_38]
0x1800189e2  lea     rax, [rsp+78h+arg_8]
0x1800189ea  mov     rdx, [rdi+78h]
0x1800189ee  xor     r9d, r9d
0x1800189f1  mov     [rsp+78h+var_48], rax
0x1800189f6  mov     rcx, rdi
0x1800189f9  mov     [rsp+78h+var_50], 0
0x180018a02  mov     [rsp+78h+var_58], 0
0x180018a0b  call    ?CreateInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEBGW4SDIAG_ROOTCAUSE_STATUS@1@PEAUtagSAFEARRAY@@3PEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::CreateInstance(_LIST_ENTRY *,ushort const *,Rootcause::SDIAG_ROOTCAUSE_STATUS,tagSAFEARRAY *,tagSAFEARRAY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x180018a10  mov     ebx, eax
0x180018a12  test    eax, eax
0x180018a14  jns     short loc_180018A1E
0x180018a16  mov     r8d, 643h
0x180018a1c  jmp     short loc_180018A6E
0x180018a1e  mov     rax, [rsp+78h+arg_8]
0x180018a26  mov     rdx, [rax+30h]; struct IXMLDOMDocument2 *
0x180018a2a  test    rdx, rdx
0x180018a2d  jnz     short loc_180018A40
0x180018a2f  mov     r9d, 80004003h
0x180018a35  mov     r8d, 646h
0x180018a3b  mov     ebx, r9d
0x180018a3e  jmp     short loc_180018A71
0x180018a40  mov     r8, [rsp+78h+arg_20]; unsigned __int16 *
0x180018a48  mov     r9, r13; unsigned __int16 *
0x180018a4b  mov     rcx, [rdi]; struct Settings *
0x180018a4e  mov     [rsp+78h+var_48], r14; unsigned __int16 *
0x180018a53  mov     [rsp+78h+var_50], r15; unsigned __int16 *
0x180018a58  mov     [rsp+78h+var_58], r12; unsigned __int16 *
0x180018a5d  call    ?SdpUpdateReportData@@YAJPEAVSettings@@PEAUIXMLDOMDocument2@@PEAG2222@Z; SdpUpdateReportData(Settings *,IXMLDOMDocument2 *,ushort *,ushort *,ushort *,ushort *,ushort *)
0x180018a62  mov     ebx, eax
0x180018a64  test    eax, eax
0x180018a66  jns     short loc_180018A82
0x180018a68  mov     r8d, 64Fh; int
0x180018a6e  mov     r9d, eax; int
0x180018a71  lea     rdx, aRootcauseAddxm; "Rootcause::AddXmlToReport"
0x180018a78  mov     ecx, 1; Level
0x180018a7d  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180018a82  mov     eax, ebx
0x180018a84  add     rsp, 48h
0x180018a88  pop     r15
0x180018a8a  pop     r14
0x180018a8c  pop     r13
0x180018a8e  pop     r12
0x180018a90  pop     rdi
0x180018a91  pop     rbx
0x180018a92  retn
```
