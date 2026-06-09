# Windows::System::Internal::Implementation::RegUtil::WriteValue<Windows::Foundation::IPropertyValue *>(HKEY__ *,ushort const *,Windows::Foundation::IPropertyValue *)

- ea: `0x18004cba8`
- end: `0x18004ceeb`
- name: `??$WriteValue@PEAUIPropertyValue@Foundation@Windows@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAUIPropertyValue@Foundation@4@@Z`
- size: `835`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004bfc0`

## callees

- `0x18000acdc`
- `0x18004b4a8`
- `0x18004c320`
- `0x18004cba8`
- `0x18004cef4`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cccb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cc7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cccb`

## string_xrefs

- `0x18004cbeb`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004cc57`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004cca5`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004ccfb`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004cd43`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004cd7b`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004cdc6`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004ce06`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004ce3c`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004ce79`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004ceb4`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::System::Internal::Implementation::RegUtil::WriteValue<Windows::Foundation::IPropertyValue *>(
        HKEY a1,
        const WCHAR *a2,
        __int64 a3)
{
  int v6; // eax
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  int v9; // eax
  __int64 v10; // r8
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING string; // [rsp+50h] [rbp+30h] BYREF
  int v22; // [rsp+58h] [rbp+38h] BYREF

  v22 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a3 + 48LL))(a3, &v22);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11B,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
      (const char *)(unsigned int)v6,
      savedregs);
  switch ( v22 )
  {
    case 1:
      LOBYTE(string) = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 64LL))(a3, &string);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x13D,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
          (const char *)(unsigned int)v17,
          savedregs);
      v10 = (unsigned __int8)string;
      goto LABEL_38;
    case 2:
      LOWORD(string) = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 72LL))(a3, &string);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x128,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
          (const char *)(unsigned int)v16,
          savedregs);
      v10 = (unsigned int)(__int16)string;
      goto LABEL_38;
    case 3:
      LOWORD(string) = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 80LL))(a3, &string);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x144,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
          (const char *)(unsigned int)v15,
          savedregs);
      v10 = (unsigned __int16)string;
      goto LABEL_38;
    case 4:
      LODWORD(string) = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 88LL))(a3, &string);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x12F,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
          (const char *)(unsigned int)v14,
          savedregs);
      goto LABEL_26;
    case 5:
      LODWORD(string) = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 96LL))(a3, &string);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x14B,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
          (const char *)(unsigned int)v13,
          savedregs);
LABEL_26:
      v10 = (unsigned int)string;
LABEL_38:
      Windows::System::Internal::Implementation::RegUtil::WriteValue<unsigned long>(a1, a2, v10);
      return 0;
    case 6:
      string = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 104LL))(a3, &string);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x136,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
          (const char *)(unsigned int)v12,
          savedregs);
      goto LABEL_23;
    case 7:
      string = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 112LL))(a3, &string);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x152,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
          (const char *)(unsigned int)v11,
          savedregs);
LABEL_23:
      Windows::System::Internal::Implementation::RegUtil::WriteValue<unsigned __int64>(a1, a2, string);
      return 0;
    case 11:
      LOBYTE(string) = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 144LL))(a3, &string);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x121,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
          (const char *)(unsigned int)v9,
          savedregs);
      v10 = (_BYTE)string != 0;
      goto LABEL_38;
  }
  if ( v22 != 12 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
      (const char *)0x8000FFFFLL,
      savedregs);
  string = 0;
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 152LL);
  WindowsDeleteString(0);
  string = 0;
  v8 = v7(a3, &string);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x159,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
      (const char *)(unsigned int)v8,
      savedregs);
  Windows::System::Internal::Implementation::RegUtil::WriteValue<HSTRING__ *>(a1, a2, string);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x18004cba8  mov     [rsp-18h+arg_0], rbx
0x18004cbad  mov     [rsp-18h+arg_8], rsi
0x18004cbb2  push    rbp
0x18004cbb3  push    rdi
0x18004cbb4  push    r14; int
0x18004cbb6  mov     rbp, rsp
0x18004cbb9  sub     rsp, 20h
0x18004cbbd  mov     rdi, r8
0x18004cbc0  mov     rsi, rdx
0x18004cbc3  mov     r14, rcx
0x18004cbc6  mov     [rbp+arg_18], 0
0x18004cbcd  mov     rax, [r8]
0x18004cbd0  lea     rdx, [rbp+arg_18]
0x18004cbd4  mov     rcx, r8
0x18004cbd7  mov     rax, [rax+30h]
0x18004cbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbe0  mov     rcx, [rbp+18h]; this
0x18004cbe4  test    eax, eax
0x18004cbe6  jns     short loc_18004CBFD
0x18004cbe8  mov     r9d, eax; char *
0x18004cbeb  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004cbf2  mov     edx, 11Bh; void *
0x18004cbf7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004cbfd  mov     ecx, [rbp+arg_18]
0x18004cc00  sub     ecx, 1
0x18004cc03  jz      loc_18004CE92
0x18004cc09  sub     ecx, 1
0x18004cc0c  jz      loc_18004CE55
0x18004cc12  sub     ecx, 1
0x18004cc15  jz      loc_18004CE18
0x18004cc1b  sub     ecx, 1
0x18004cc1e  jz      loc_18004CDE1
0x18004cc24  sub     ecx, 1
0x18004cc27  jz      loc_18004CDA1
0x18004cc2d  sub     ecx, 1
0x18004cc30  jz      loc_18004CD55
0x18004cc36  sub     ecx, 1
0x18004cc39  jz      loc_18004CD1D
0x18004cc3f  sub     ecx, 4
0x18004cc42  jz      loc_18004CCD6
0x18004cc48  cmp     ecx, 1
0x18004cc4b  jz      short loc_18004CC69
0x18004cc4d  mov     rcx, [rbp+18h]; this
0x18004cc51  mov     r9d, 8000FFFFh; char *
0x18004cc57  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004cc5e  mov     edx, 15Eh; void *
0x18004cc63  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004cc69  mov     [rbp+string], 0
0x18004cc71  mov     rax, [rdi]
0x18004cc74  mov     rbx, [rax+98h]
0x18004cc7b  xor     ecx, ecx; string
0x18004cc7d  call    cs:__imp_WindowsDeleteString
0x18004cc83  mov     [rbp+string], 0
0x18004cc8b  lea     rdx, [rbp+string]
0x18004cc8f  mov     rcx, rdi
0x18004cc92  mov     rax, rbx
0x18004cc95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc9a  mov     rcx, [rbp+18h]; this
0x18004cc9e  test    eax, eax
0x18004cca0  jns     short loc_18004CCB7
0x18004cca2  mov     r9d, eax; char *
0x18004cca5  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004ccac  mov     edx, 159h; void *
0x18004ccb1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ccb7  mov     r8, [rbp+string]
0x18004ccbb  mov     rdx, rsi
0x18004ccbe  mov     rcx, r14
0x18004ccc1  call    ??$WriteValue@PEAUHSTRING__@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAUHSTRING__@@@Z; Windows::System::Internal::Implementation::RegUtil::WriteValue<HSTRING__ *>(HKEY__ *,ushort const *,HSTRING__ *)
0x18004ccc6  nop
0x18004ccc7  mov     rcx, [rbp+string]; string
0x18004cccb  call    cs:__imp_WindowsDeleteString
0x18004ccd1  jmp     loc_18004CED6
0x18004ccd6  mov     byte ptr [rbp+string], 0
0x18004ccda  mov     rax, [rdi]
0x18004ccdd  lea     rdx, [rbp+string]
0x18004cce1  mov     rcx, rdi
0x18004cce4  mov     rax, [rax+90h]
0x18004cceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ccf0  test    eax, eax
0x18004ccf2  jns     short loc_18004CD0D
0x18004ccf4  mov     rcx, [rbp+18h]; this
0x18004ccf8  mov     r9d, eax; char *
0x18004ccfb  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004cd02  mov     edx, 121h; void *
0x18004cd07  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004cd0d  xor     r8d, r8d
0x18004cd10  cmp     byte ptr [rbp+string], r8b
0x18004cd14  setnz   r8b
0x18004cd18  jmp     loc_18004CECB
0x18004cd1d  mov     [rbp+string], 0
0x18004cd25  mov     rax, [rdi]
0x18004cd28  lea     rdx, [rbp+string]
0x18004cd2c  mov     rcx, rdi
0x18004cd2f  mov     rax, [rax+70h]
0x18004cd33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd38  test    eax, eax
0x18004cd3a  jns     short loc_18004CD8D
0x18004cd3c  mov     rcx, [rbp+18h]; this
0x18004cd40  mov     r9d, eax; char *
0x18004cd43  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004cd4a  mov     edx, 152h; void *
0x18004cd4f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004cd55  mov     [rbp+string], 0
0x18004cd5d  mov     rax, [rdi]
0x18004cd60  lea     rdx, [rbp+string]
0x18004cd64  mov     rcx, rdi
0x18004cd67  mov     rax, [rax+68h]
0x18004cd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd70  test    eax, eax
0x18004cd72  jns     short loc_18004CD8D
0x18004cd74  mov     rcx, [rbp+18h]; this
0x18004cd78  mov     r9d, eax; char *
0x18004cd7b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004cd82  mov     edx, 136h; void *
0x18004cd87  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004cd8d  mov     r8, [rbp+string]
0x18004cd91  mov     rdx, rsi
0x18004cd94  mov     rcx, r14
0x18004cd97  call    ??$WriteValue@_K@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBG_K@Z; Windows::System::Internal::Implementation::RegUtil::WriteValue<unsigned __int64>(HKEY__ *,ushort const *,unsigned __int64)
0x18004cd9c  jmp     loc_18004CED6
0x18004cda1  mov     dword ptr [rbp+string], 0
0x18004cda8  mov     rax, [rdi]
0x18004cdab  lea     rdx, [rbp+string]
0x18004cdaf  mov     rcx, rdi
0x18004cdb2  mov     rax, [rax+60h]
0x18004cdb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cdbb  test    eax, eax
0x18004cdbd  jns     short loc_18004CDD8
0x18004cdbf  mov     rcx, [rbp+18h]; this
0x18004cdc3  mov     r9d, eax; char *
0x18004cdc6  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004cdcd  mov     edx, 14Bh; void *
0x18004cdd2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004cdd8  mov     r8d, dword ptr [rbp+string]
0x18004cddc  jmp     loc_18004CECB
0x18004cde1  mov     dword ptr [rbp+string], 0
0x18004cde8  mov     rax, [rdi]
0x18004cdeb  lea     rdx, [rbp+string]
0x18004cdef  mov     rcx, rdi
0x18004cdf2  mov     rax, [rax+58h]
0x18004cdf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cdfb  test    eax, eax
0x18004cdfd  jns     short loc_18004CDD8
0x18004cdff  mov     rcx, [rbp+18h]; this
0x18004ce03  mov     r9d, eax; char *
0x18004ce06  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004ce0d  mov     edx, 12Fh; void *
0x18004ce12  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ce18  xor     eax, eax
0x18004ce1a  mov     word ptr [rbp+string], ax
0x18004ce1e  mov     rax, [rdi]
0x18004ce21  lea     rdx, [rbp+string]
0x18004ce25  mov     rcx, rdi
0x18004ce28  mov     rax, [rax+50h]
0x18004ce2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce31  test    eax, eax
0x18004ce33  jns     short loc_18004CE4E
0x18004ce35  mov     rcx, [rbp+18h]; this
0x18004ce39  mov     r9d, eax; char *
0x18004ce3c  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004ce43  mov     edx, 144h; void *
0x18004ce48  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ce4e  movzx   r8d, word ptr [rbp+string]
0x18004ce53  jmp     short loc_18004CECB
0x18004ce55  xor     eax, eax
0x18004ce57  mov     word ptr [rbp+string], ax
0x18004ce5b  mov     rax, [rdi]
0x18004ce5e  lea     rdx, [rbp+string]
0x18004ce62  mov     rcx, rdi
0x18004ce65  mov     rax, [rax+48h]
0x18004ce69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce6e  test    eax, eax
0x18004ce70  jns     short loc_18004CE8B
0x18004ce72  mov     rcx, [rbp+18h]; this
0x18004ce76  mov     r9d, eax; char *
0x18004ce79  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004ce80  mov     edx, 128h; void *
0x18004ce85  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ce8b  movsx   r8d, word ptr [rbp+string]
0x18004ce90  jmp     short loc_18004CECB
0x18004ce92  mov     byte ptr [rbp+string], 0
0x18004ce96  mov     rax, [rdi]
0x18004ce99  lea     rdx, [rbp+string]
0x18004ce9d  mov     rcx, rdi
0x18004cea0  mov     rax, [rax+40h]
0x18004cea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cea9  test    eax, eax
0x18004ceab  jns     short loc_18004CEC6
0x18004cead  mov     rcx, [rbp+18h]; this
0x18004ceb1  mov     r9d, eax; char *
0x18004ceb4  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004cebb  mov     edx, 13Dh; void *
0x18004cec0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004cec6  movzx   r8d, byte ptr [rbp+string]
0x18004cecb  mov     rdx, rsi
0x18004cece  mov     rcx, r14
0x18004ced1  call    ??$WriteValue@K@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGK@Z; Windows::System::Internal::Implementation::RegUtil::WriteValue<ulong>(HKEY__ *,ushort const *,ulong)
0x18004ced6  xor     eax, eax
0x18004ced8  mov     rbx, [rsp+20h+arg_0]
0x18004cedd  mov     rsi, [rsp+20h+arg_8]
0x18004cee2  add     rsp, 20h
0x18004cee6  pop     r14
0x18004cee8  pop     rdi
0x18004cee9  pop     rbp
0x18004ceea  retn
```
