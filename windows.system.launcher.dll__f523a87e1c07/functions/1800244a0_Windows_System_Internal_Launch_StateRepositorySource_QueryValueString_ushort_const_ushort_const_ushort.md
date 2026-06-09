# Windows::System::Internal::Launch::StateRepositorySource::QueryValueString(ushort const *,ushort const *,ushort * *)

- ea: `0x1800244a0`
- end: `0x1800247bc`
- name: `?QueryValueString@StateRepositorySource@Launch@Internal@System@Windows@@UEAAJPEBG0PEAPEAG@Z`
- size: `796`
- prototype: `int(Windows::System::Internal::Launch::StateRepositorySource *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180010c04`
- `0x180023fcc`
- `0x1800244a0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024503`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024537`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002455b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002457f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800245a3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024767`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024797`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024503`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024537`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002455b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002457f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800245a3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024767`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024797`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800244e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800245ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024671`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800246b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800246eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024720`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002474c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002477c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800244e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800245ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024671`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800246b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800246eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024720`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002474c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002477c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800245bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002462f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800245bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002462f`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800245f6`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18002467d`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800246c2`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800246f7`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18002472c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800245f6`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18002467d`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800246c2`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800246f7`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18002472c`

## string_xrefs

- `0x18002475d`: `Shell\Open`

## pseudocode

```c
__int64 __fastcall Windows::System::Internal::Launch::StateRepositorySource::QueryValueString(
        Windows::System::Internal::Launch::StateRepositorySource *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  const WCHAR *v5; // rbx
  HSTRING v7; // rcx
  const WCHAR *StringRawBuffer; // rax
  __int64 v9; // rcx
  HRESULT v10; // ebx
  const WCHAR *v11; // rax
  HRESULT v12; // eax
  HSTRING v14; // rcx
  const WCHAR *v15; // rax
  __int64 v16; // rdx
  HSTRING v17; // rcx
  const WCHAR *v18; // rax
  HSTRING v19; // rcx
  const WCHAR *v20; // rax
  HSTRING v21; // rcx
  const WCHAR *v22; // rax
  const WCHAR *v23; // rax
  const WCHAR *v24; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING string; // [rsp+58h] [rbp+10h] BYREF

  *a4 = 0;
  v5 = a3;
  if ( a3 )
    goto LABEL_7;
  if ( a2 )
  {
    v5 = a2;
    goto LABEL_7;
  }
  v7 = (HSTRING)*((_QWORD *)this + 12);
  if ( !v7 )
  {
    v5 = L"FriendlyTypeName";
    goto LABEL_7;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v7, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"Shell", -1, 1) == 2
    || (v23 = WindowsGetStringRawBuffer(*((HSTRING *)this + 12), 0),
        CompareStringOrdinal(v23, -1, L"Shell\\Open", -1, 1) == 2) )
  {
    v5 = L"DefaultVerb";
  }
  else
  {
    v24 = WindowsGetStringRawBuffer(*((HSTRING *)this + 12), 0);
    if ( CompareStringOrdinal(v24, -1, L"DefaultIcon", -1, 1) == 2 )
    {
      v5 = L"DefaultIcon";
      goto LABEL_7;
    }
  }
  if ( v5 )
  {
LABEL_7:
    if ( CompareStringOrdinal(v5, -1, L"ddeexec", -1, 1) == 2 && (v14 = (HSTRING)*((_QWORD *)this + 21)) != 0 )
    {
      v15 = WindowsGetStringRawBuffer(v14, 0);
      v10 = SHStrDupW(v15, a4);
      if ( v10 < 0 )
      {
        v16 = 316;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.queryassociations.cpp",
          (const char *)(unsigned int)v10,
          bIgnoreCase);
        return (unsigned int)v10;
      }
    }
    else if ( CompareStringOrdinal(v5, -1, L"ddeexec\\ifexec", -1, 1) == 2
           && (v17 = (HSTRING)*((_QWORD *)this + 24)) != 0 )
    {
      v18 = WindowsGetStringRawBuffer(v17, 0);
      v10 = SHStrDupW(v18, a4);
      if ( v10 < 0 )
      {
        v16 = 320;
        goto LABEL_23;
      }
    }
    else if ( CompareStringOrdinal(v5, -1, L"ddeexec\\application", -1, 1) == 2
           && (v19 = (HSTRING)*((_QWORD *)this + 22)) != 0 )
    {
      v20 = WindowsGetStringRawBuffer(v19, 0);
      v10 = SHStrDupW(v20, a4);
      if ( v10 < 0 )
      {
        v16 = 324;
        goto LABEL_23;
      }
    }
    else
    {
      if ( CompareStringOrdinal(v5, -1, L"ddeexec\\topic", -1, 1) != 2 || (v21 = (HSTRING)*((_QWORD *)this + 23)) == 0 )
      {
        string = 0;
        WindowsDeleteString(0);
        v9 = *((_QWORD *)this + 13);
        string = 0;
        v10 = LookupValueStringForKey(v9, v5, &string);
        if ( v10 >= 0 )
        {
          v11 = WindowsGetStringRawBuffer(string, 0);
          v12 = SHStrDupW(v11, a4);
          v10 = v12;
          if ( v12 >= 0 )
          {
            WindowsDeleteString(string);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x14F,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.queryassociations.cpp",
            (const char *)(unsigned int)v12,
            bIgnoreCase);
        }
        WindowsDeleteString(string);
        return (unsigned int)v10;
      }
      v22 = WindowsGetStringRawBuffer(v21, 0);
      v10 = SHStrDupW(v22, a4);
      if ( v10 < 0 )
      {
        v16 = 328;
        goto LABEL_23;
      }
    }
    return 0;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800244a0  mov     [rsp+arg_0], rbx
0x1800244a5  mov     [rsp+arg_10], rsi
0x1800244aa  push    rdi
0x1800244ab  push    r14
0x1800244ad  push    r15
0x1800244af  sub     rsp, 30h
0x1800244b3  or      r14d, 0FFFFFFFFh
0x1800244b7  mov     qword ptr [r9], 0
0x1800244be  mov     rsi, r9
0x1800244c1  mov     rbx, r8
0x1800244c4  mov     rdi, rcx
0x1800244c7  mov     r15d, 1
0x1800244cd  test    r8, r8
0x1800244d0  jnz     short loc_180024522
0x1800244d2  test    rdx, rdx
0x1800244d5  jnz     loc_18002464B
0x1800244db  mov     rcx, [rcx+60h]; string
0x1800244df  test    rcx, rcx
0x1800244e2  jz      loc_180024653
0x1800244e8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800244ee  mov     r9d, r14d; cchCount2
0x1800244f1  mov     [rsp+48h+bIgnoreCase], r15d; bIgnoreCase
0x1800244f6  mov     rcx, rax; lpString1
0x1800244f9  lea     r8, String2; "Shell"
0x180024500  mov     edx, r14d; cchCount1
0x180024503  call    cs:__imp_CompareStringOrdinal
0x180024509  cmp     eax, 2
0x18002450c  jnz     loc_180024746
0x180024512  lea     rbx, aDefaultverb; "DefaultVerb"
0x180024519  test    rbx, rbx
0x18002451c  jz      loc_1800247B2
0x180024522  mov     r9d, r14d; cchCount2
0x180024525  mov     [rsp+48h+bIgnoreCase], r15d; int
0x18002452a  lea     r8, aDdeexec; "ddeexec"
0x180024531  mov     edx, r14d; cchCount1
0x180024534  mov     rcx, rbx; lpString1
0x180024537  call    cs:__imp_CompareStringOrdinal
0x18002453d  cmp     eax, 2
0x180024540  jz      loc_18002465F
0x180024546  mov     r9d, r14d; cchCount2
0x180024549  mov     [rsp+48h+bIgnoreCase], r15d; bIgnoreCase
0x18002454e  lea     r8, aDdeexecIfexec; "ddeexec\\ifexec"
0x180024555  mov     edx, r14d; cchCount1
0x180024558  mov     rcx, rbx; lpString1
0x18002455b  call    cs:__imp_CompareStringOrdinal
0x180024561  cmp     eax, 2
0x180024564  jz      loc_1800246A4
0x18002456a  mov     r9d, r14d; cchCount2
0x18002456d  mov     [rsp+48h+bIgnoreCase], r15d; bIgnoreCase
0x180024572  lea     r8, aDdeexecApplica; "ddeexec\\application"
0x180024579  mov     edx, r14d; cchCount1
0x18002457c  mov     rcx, rbx; lpString1
0x18002457f  call    cs:__imp_CompareStringOrdinal
0x180024585  cmp     eax, 2
0x180024588  jz      loc_1800246D9
0x18002458e  mov     r9d, r14d; cchCount2
0x180024591  mov     [rsp+48h+bIgnoreCase], r15d; int
0x180024596  lea     r8, aDdeexecTopic; "ddeexec\\topic"
0x18002459d  mov     edx, r14d; cchCount1
0x1800245a0  mov     rcx, rbx; lpString1
0x1800245a3  call    cs:__imp_CompareStringOrdinal
0x1800245a9  cmp     eax, 2
0x1800245ac  jz      loc_18002470E
0x1800245b2  xor     ecx, ecx; string
0x1800245b4  mov     [rsp+48h+string], 0
0x1800245bd  call    cs:__imp_WindowsDeleteString
0x1800245c3  mov     rcx, [rdi+68h]
0x1800245c7  lea     r8, [rsp+48h+string]
0x1800245cc  mov     rdx, rbx
0x1800245cf  mov     [rsp+48h+string], 0
0x1800245d8  call    ?LookupValueStringForKey@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; LookupValueStringForKey(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800245dd  mov     ebx, eax
0x1800245df  test    eax, eax
0x1800245e1  js      short loc_18002462A
0x1800245e3  mov     rcx, [rsp+48h+string]; string
0x1800245e8  xor     edx, edx; length
0x1800245ea  call    cs:__imp_WindowsGetStringRawBuffer
0x1800245f0  mov     rcx, rax; psz
0x1800245f3  mov     rdx, rsi; ppwsz
0x1800245f6  call    cs:__imp_SHStrDupW
0x1800245fc  mov     ebx, eax
0x1800245fe  test    eax, eax
0x180024600  js      short loc_180024611
0x180024602  mov     rcx, [rsp+48h+string]; string
0x180024607  call    cs:__imp_WindowsDeleteString
0x18002460d  xor     eax, eax
0x18002460f  jmp     short loc_180024637
0x180024611  mov     rcx, [rsp+48h]; this
0x180024616  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\windows.system.launc"...
0x18002461d  mov     r9d, eax; char *
0x180024620  mov     edx, 14Fh; void *
0x180024625  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002462a  mov     rcx, [rsp+48h+string]; string
0x18002462f  call    cs:__imp_WindowsDeleteString
0x180024635  mov     eax, ebx
0x180024637  mov     rbx, [rsp+48h+arg_0]
0x18002463c  mov     rsi, [rsp+48h+arg_10]
0x180024641  add     rsp, 30h
0x180024645  pop     r15
0x180024647  pop     r14
0x180024649  pop     rdi
0x18002464a  retn
0x18002464b  mov     rbx, rdx
0x18002464e  jmp     loc_180024522
0x180024653  lea     rbx, aFriendlytypena; "FriendlyTypeName"
0x18002465a  jmp     loc_180024522
0x18002465f  mov     rcx, [rdi+0A8h]; string
0x180024666  test    rcx, rcx
0x180024669  jz      loc_180024546
0x18002466f  xor     edx, edx; length
0x180024671  call    cs:__imp_WindowsGetStringRawBuffer
0x180024677  mov     rcx, rax; psz
0x18002467a  mov     rdx, rsi; ppwsz
0x18002467d  call    cs:__imp_SHStrDupW
0x180024683  mov     ebx, eax
0x180024685  test    eax, eax
0x180024687  jns     short loc_18002460D
0x180024689  mov     edx, 13Ch; void *
0x18002468e  mov     rcx, [rsp+48h]; this
0x180024693  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\windows.system.launc"...
0x18002469a  mov     r9d, ebx; char *
0x18002469d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800246a2  jmp     short loc_180024635
0x1800246a4  mov     rcx, [rdi+0C0h]; string
0x1800246ab  test    rcx, rcx
0x1800246ae  jz      loc_18002456A
0x1800246b4  xor     edx, edx; length
0x1800246b6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800246bc  mov     rcx, rax; psz
0x1800246bf  mov     rdx, rsi; ppwsz
0x1800246c2  call    cs:__imp_SHStrDupW
0x1800246c8  mov     ebx, eax
0x1800246ca  test    eax, eax
0x1800246cc  jns     loc_18002460D
0x1800246d2  mov     edx, 140h
0x1800246d7  jmp     short loc_18002468E
0x1800246d9  mov     rcx, [rdi+0B0h]; string
0x1800246e0  test    rcx, rcx
0x1800246e3  jz      loc_18002458E
0x1800246e9  xor     edx, edx; length
0x1800246eb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800246f1  mov     rcx, rax; psz
0x1800246f4  mov     rdx, rsi; ppwsz
0x1800246f7  call    cs:__imp_SHStrDupW
0x1800246fd  mov     ebx, eax
0x1800246ff  test    eax, eax
0x180024701  jns     loc_18002460D
0x180024707  mov     edx, 144h
0x18002470c  jmp     short loc_18002468E
0x18002470e  mov     rcx, [rdi+0B8h]; string
0x180024715  test    rcx, rcx
0x180024718  jz      loc_1800245B2
0x18002471e  xor     edx, edx; length
0x180024720  call    cs:__imp_WindowsGetStringRawBuffer
0x180024726  mov     rcx, rax; psz
0x180024729  mov     rdx, rsi; ppwsz
0x18002472c  call    cs:__imp_SHStrDupW
0x180024732  mov     ebx, eax
0x180024734  test    eax, eax
0x180024736  jns     loc_18002460D
0x18002473c  mov     edx, 148h
0x180024741  jmp     loc_18002468E
0x180024746  mov     rcx, [rdi+60h]; string
0x18002474a  xor     edx, edx; length
0x18002474c  call    cs:__imp_WindowsGetStringRawBuffer
0x180024752  mov     r9d, r14d; cchCount2
0x180024755  mov     [rsp+48h+bIgnoreCase], r15d; bIgnoreCase
0x18002475a  mov     rcx, rax; lpString1
0x18002475d  lea     r8, aShellOpen; "Shell\\Open"
0x180024764  mov     edx, r14d; cchCount1
0x180024767  call    cs:__imp_CompareStringOrdinal
0x18002476d  cmp     eax, 2
0x180024770  jz      loc_180024512
0x180024776  mov     rcx, [rdi+60h]; string
0x18002477a  xor     edx, edx; length
0x18002477c  call    cs:__imp_WindowsGetStringRawBuffer
0x180024782  mov     r9d, r14d; cchCount2
0x180024785  mov     [rsp+48h+bIgnoreCase], r15d; bIgnoreCase
0x18002478a  mov     rcx, rax; lpString1
0x18002478d  lea     r8, aDefaulticon_0; "DefaultIcon"
0x180024794  mov     edx, r14d; cchCount1
0x180024797  call    cs:__imp_CompareStringOrdinal
0x18002479d  cmp     eax, 2
0x1800247a0  jnz     loc_180024519
0x1800247a6  lea     rbx, aDefaulticon_0; "DefaultIcon"
0x1800247ad  jmp     loc_180024522
0x1800247b2  mov     eax, 80070057h
0x1800247b7  jmp     loc_180024637
```
