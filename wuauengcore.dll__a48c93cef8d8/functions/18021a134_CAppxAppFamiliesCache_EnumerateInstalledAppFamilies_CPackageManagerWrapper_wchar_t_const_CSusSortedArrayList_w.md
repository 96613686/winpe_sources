# CAppxAppFamiliesCache::EnumerateInstalledAppFamilies(CPackageManagerWrapper *,wchar_t const *,CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> &)

- ea: `0x18021a134`
- end: `0x18021a489`
- name: `?EnumerateInstalledAppFamilies@CAppxAppFamiliesCache@@AEBAJPEAVCPackageManagerWrapper@@PEB_WAEAV?$CSusSortedArrayList@PEA_WVCSusSortedArrayListItemOpsLPWSTR@@@@@Z`
- size: `853`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180219df0`

## callees

- `0x18021a134`
- `0x18021a5fc`
- `0x18021a680`
- `0x18021a858`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021a1d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021a1ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021a379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021a389`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021a3ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021a3fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021a1d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021a1ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021a379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021a389`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021a3ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18021a3fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021a308`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021a350`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021a308`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021a350`

## pseudocode

```c
// Hidden C++ exception states: #wind=43
__int64 __fastcall CAppxAppFamiliesCache::EnumerateInstalledAppFamilies(__int64 a1, __int64 a2, HSTRING a3, __int64 a4)
{
  HSTRING v5; // rsi
  int IsInstalled; // edi
  HSTRING v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, __int64 *); // rdi
  __int64 v12; // rcx
  int i; // eax
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, __int64 *); // rdi
  __int64 v16; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v18; // rcx
  unsigned int v19; // eax
  int v20; // ecx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  HSTRING v28; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v29[8]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v30; // [rsp+40h] [rbp-30h] BYREF
  __int64 v31; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-20h] BYREF
  __int64 v33; // [rsp+58h] [rbp-18h] BYREF
  __int64 v34; // [rsp+60h] [rbp-10h] BYREF

  v5 = a3;
  v28 = a3;
  v33 = 0;
  v31 = 0;
  if ( a3 )
  {
    string = 0;
    IsInstalled = Windows::Internal::String::Initialize<wchar_t const *>(&string, &v28);
    v8 = string;
    if ( IsInstalled < 0 )
      goto LABEL_9;
    v9 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    IsInstalled = (*(__int64 (__fastcall **)(_QWORD, HSTRING, __int64, __int64 *))(**(_QWORD **)(a2 + 24) + 80LL))(
                    *(_QWORD *)(a2 + 24),
                    v8,
                    63,
                    &v33);
    if ( IsInstalled < 0 )
    {
LABEL_9:
      if ( v8 )
        WindowsDeleteString(v8);
      goto LABEL_46;
    }
    if ( v8 )
      WindowsDeleteString(v8);
    v5 = v28;
  }
  else
  {
    IsInstalled = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**(_QWORD **)(a2 + 24) + 72LL))(
                    *(_QWORD *)(a2 + 24),
                    63,
                    &v33);
    if ( IsInstalled < 0 )
      goto LABEL_46;
  }
  v10 = v33;
  v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 48LL);
  v12 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  IsInstalled = v11(v10, &v31);
  if ( IsInstalled >= 0 )
  {
    v29[0] = 0;
    for ( i = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v31 + 56LL))(v31, v29);
          ;
          i = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v31 + 64LL))(v31, v29) )
    {
      IsInstalled = i;
      if ( i < 0 || !v29[0] )
        break;
      v34 = 0;
      v30 = 0;
      string = 0;
      IsInstalled = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 48LL))(v31, &v34);
      if ( IsInstalled < 0 )
        goto LABEL_40;
      v14 = v34;
      v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 48LL);
      v16 = v30;
      if ( v30 )
      {
        v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      IsInstalled = v15(v14, &v30);
      if ( IsInstalled < 0 )
        goto LABEL_40;
      IsInstalled = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 104LL))(v30, &string);
      if ( IsInstalled < 0 )
        goto LABEL_40;
      if ( v5 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        IsInstalled = CAppxAppFamiliesCache::AddFamilyUser(v18, StringRawBuffer, v5, a4);
        if ( IsInstalled < 0 )
          goto LABEL_40;
      }
      else
      {
        v28 = 0;
        IsInstalled = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 96LL))(v30, &v28);
        if ( IsInstalled < 0
          || (v19 = (unsigned int)WindowsGetStringRawBuffer(string, 0),
              IsInstalled = CAppxAppFamiliesCache::AddFamilyForMachineIfPackageIsInstalled(
                              v20,
                              a2,
                              (_DWORD)v28,
                              v19,
                              a4),
              IsInstalled < 0) )
        {
          if ( v28 )
            WindowsDeleteString(v28);
LABEL_40:
          if ( string )
            WindowsDeleteString(string);
          v23 = v30;
          if ( v30 )
          {
            v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          }
          v24 = v34;
          if ( v34 )
          {
            v34 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          }
          break;
        }
        if ( v28 )
          WindowsDeleteString(v28);
      }
      if ( string )
        WindowsDeleteString(string);
      v21 = v30;
      if ( v30 )
      {
        v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      v22 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
  }
LABEL_46:
  v25 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v26 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  return (unsigned int)IsInstalled;
}

```

## disassembly

```asm
0x18021a134  push    rbp
0x18021a136  push    rbx
0x18021a137  push    rsi
0x18021a138  push    rdi
0x18021a139  push    r12
0x18021a13b  push    r14
0x18021a13d  push    r15
0x18021a13f  mov     rbp, rsp
0x18021a142  sub     rsp, 70h
0x18021a146  mov     rax, cs:__security_cookie
0x18021a14d  xor     rax, rsp
0x18021a150  mov     [rbp+var_8], rax
0x18021a154  mov     r15, r9
0x18021a157  mov     rsi, r8
0x18021a15a  mov     r14, rdx
0x18021a15d  mov     [rbp+var_40], r8
0x18021a161  xor     r12d, r12d
0x18021a164  mov     [rbp+var_18], r12
0x18021a168  mov     [rbp+var_28], r12
0x18021a16c  test    r8, r8
0x18021a16f  jz      loc_18021A1F8
0x18021a175  mov     [rbp+string], r12
0x18021a179  lea     rdx, [rbp+var_40]
0x18021a17d  lea     rcx, [rbp+string]
0x18021a181  call    ??$Initialize@PEB_W@String@Internal@Windows@@QEAAJAEBQEB_WUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<wchar_t const *>(wchar_t const * const &,Windows::Internal::_StringDetail::dummy_t)
0x18021a186  mov     edi, eax
0x18021a188  mov     rbx, [rbp+string]
0x18021a18c  test    eax, eax
0x18021a18e  js      short loc_18021A1E1
0x18021a190  mov     rcx, [rbp+var_18]
0x18021a194  test    rcx, rcx
0x18021a197  jz      short loc_18021A1AA
0x18021a199  mov     [rbp+var_18], r12
0x18021a19d  mov     rax, [rcx]
0x18021a1a0  mov     rax, [rax+10h]
0x18021a1a4  call    _guard_dispatch_icall
0x18021a1a9  nop
0x18021a1aa  mov     rcx, [r14+18h]
0x18021a1ae  mov     rax, [rcx]
0x18021a1b1  lea     r9, [rbp+var_18]
0x18021a1b5  mov     r8d, 3Fh ; '?'
0x18021a1bb  mov     rdx, rbx
0x18021a1be  mov     rax, [rax+50h]
0x18021a1c2  call    _guard_dispatch_icall
0x18021a1c7  mov     edi, eax
0x18021a1c9  test    eax, eax
0x18021a1cb  js      short loc_18021A1E1
0x18021a1cd  test    rbx, rbx
0x18021a1d0  jz      short loc_18021A1DB
0x18021a1d2  mov     rcx, rbx; string
0x18021a1d5  call    cs:__imp_WindowsDeleteString
0x18021a1db  mov     rsi, [rbp+var_40]
0x18021a1df  jmp     short loc_18021A21B
0x18021a1e1  test    rbx, rbx
0x18021a1e4  jz      loc_18021A438
0x18021a1ea  mov     rcx, rbx; string
0x18021a1ed  call    cs:__imp_WindowsDeleteString
0x18021a1f3  jmp     loc_18021A438
0x18021a1f8  mov     rcx, [rdx+18h]
0x18021a1fc  mov     rax, [rcx]
0x18021a1ff  lea     r8, [rbp+var_18]
0x18021a203  mov     edx, 3Fh ; '?'
0x18021a208  mov     rax, [rax+48h]
0x18021a20c  call    _guard_dispatch_icall
0x18021a211  mov     edi, eax
0x18021a213  test    eax, eax
0x18021a215  js      loc_18021A438
0x18021a21b  mov     rbx, [rbp+var_18]
0x18021a21f  mov     rax, [rbx]
0x18021a222  mov     rdi, [rax+30h]
0x18021a226  mov     rcx, [rbp+var_28]
0x18021a22a  test    rcx, rcx
0x18021a22d  jz      short loc_18021A240
0x18021a22f  mov     [rbp+var_28], r12
0x18021a233  mov     rdx, [rcx]
0x18021a236  mov     rax, [rdx+10h]
0x18021a23a  call    _guard_dispatch_icall
0x18021a23f  nop
0x18021a240  lea     rdx, [rbp+var_28]
0x18021a244  mov     rcx, rbx
0x18021a247  mov     rax, rdi
0x18021a24a  call    _guard_dispatch_icall
0x18021a24f  mov     edi, eax
0x18021a251  test    eax, eax
0x18021a253  js      loc_18021A438
0x18021a259  mov     [rbp+var_38], r12b
0x18021a25d  mov     rcx, [rbp+var_28]
0x18021a261  mov     rax, [rcx]
0x18021a264  mov     rax, [rax+38h]
0x18021a268  jmp     loc_18021A3CF
0x18021a26d  cmp     [rbp+var_38], r12b
0x18021a271  jz      loc_18021A438
0x18021a277  mov     [rbp+var_10], r12
0x18021a27b  mov     [rbp+var_30], r12
0x18021a27f  mov     [rbp+string], r12
0x18021a283  mov     rcx, [rbp+var_28]
0x18021a287  mov     rax, [rcx]
0x18021a28a  lea     rdx, [rbp+var_10]
0x18021a28e  mov     rax, [rax+30h]
0x18021a292  call    _guard_dispatch_icall
0x18021a297  mov     edi, eax
0x18021a299  test    eax, eax
0x18021a29b  js      loc_18021A3F4
0x18021a2a1  mov     rbx, [rbp+var_10]
0x18021a2a5  mov     rax, [rbx]
0x18021a2a8  mov     rdi, [rax+30h]
0x18021a2ac  mov     rcx, [rbp+var_30]
0x18021a2b0  test    rcx, rcx
0x18021a2b3  jz      short loc_18021A2C6
0x18021a2b5  mov     [rbp+var_30], r12
0x18021a2b9  mov     rdx, [rcx]
0x18021a2bc  mov     rax, [rdx+10h]
0x18021a2c0  call    _guard_dispatch_icall
0x18021a2c5  nop
0x18021a2c6  lea     rdx, [rbp+var_30]
0x18021a2ca  mov     rcx, rbx
0x18021a2cd  mov     rax, rdi
0x18021a2d0  call    _guard_dispatch_icall
0x18021a2d5  mov     edi, eax
0x18021a2d7  test    eax, eax
0x18021a2d9  js      loc_18021A3F4
0x18021a2df  mov     rcx, [rbp+var_30]
0x18021a2e3  mov     rax, [rcx]
0x18021a2e6  lea     rdx, [rbp+string]
0x18021a2ea  mov     rax, [rax+68h]
0x18021a2ee  call    _guard_dispatch_icall
0x18021a2f3  mov     edi, eax
0x18021a2f5  test    eax, eax
0x18021a2f7  js      loc_18021A3F4
0x18021a2fd  test    rsi, rsi
0x18021a300  jz      short loc_18021A328
0x18021a302  xor     edx, edx; length
0x18021a304  mov     rcx, [rbp+string]; string
0x18021a308  call    cs:__imp_WindowsGetStringRawBuffer
0x18021a30e  mov     r9, r15
0x18021a311  mov     r8, rsi
0x18021a314  mov     rdx, rax
0x18021a317  call    ?AddFamilyUser@CAppxAppFamiliesCache@@AEBAJPEB_W0AEAV?$CSusSortedArrayList@PEA_WVCSusSortedArrayListItemOpsLPWSTR@@@@@Z; CAppxAppFamiliesCache::AddFamilyUser(wchar_t const *,wchar_t const *,CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> &)
0x18021a31c  mov     edi, eax
0x18021a31e  test    eax, eax
0x18021a320  js      loc_18021A3F4
0x18021a326  jmp     short loc_18021A380
0x18021a328  mov     [rbp+var_40], r12
0x18021a32c  mov     rcx, [rbp+var_30]
0x18021a330  mov     rax, [rcx]
0x18021a333  lea     rdx, [rbp+var_40]
0x18021a337  mov     rax, [rax+60h]
0x18021a33b  call    _guard_dispatch_icall
0x18021a340  mov     edi, eax
0x18021a342  test    eax, eax
0x18021a344  js      loc_18021A3E4
0x18021a34a  xor     edx, edx; length
0x18021a34c  mov     rcx, [rbp+string]; string
0x18021a350  call    cs:__imp_WindowsGetStringRawBuffer
0x18021a356  mov     [rsp+70h+var_50], r15
0x18021a35b  mov     r9, rax
0x18021a35e  mov     r8, [rbp+var_40]
0x18021a362  mov     rdx, r14
0x18021a365  call    ?AddFamilyForMachineIfPackageIsInstalled@CAppxAppFamiliesCache@@AEBAJPEAVCPackageManagerWrapper@@QEAUHSTRING__@@QEB_WAEAV?$CSusSortedArrayList@PEA_WVCSusSortedArrayListItemOpsLPWSTR@@@@@Z; CAppxAppFamiliesCache::AddFamilyForMachineIfPackageIsInstalled(CPackageManagerWrapper *,HSTRING__ * const,wchar_t const * const,CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> &)
0x18021a36a  mov     edi, eax
0x18021a36c  test    eax, eax
0x18021a36e  js      short loc_18021A3E4
0x18021a370  mov     rcx, [rbp+var_40]; string
0x18021a374  test    rcx, rcx
0x18021a377  jz      short loc_18021A380
0x18021a379  call    cs:__imp_WindowsDeleteString
0x18021a37f  nop
0x18021a380  mov     rcx, [rbp+string]; string
0x18021a384  test    rcx, rcx
0x18021a387  jz      short loc_18021A390
0x18021a389  call    cs:__imp_WindowsDeleteString
0x18021a38f  nop
0x18021a390  mov     rcx, [rbp+var_30]
0x18021a394  test    rcx, rcx
0x18021a397  jz      short loc_18021A3AA
0x18021a399  mov     [rbp+var_30], r12
0x18021a39d  mov     rax, [rcx]
0x18021a3a0  mov     rax, [rax+10h]
0x18021a3a4  call    _guard_dispatch_icall
0x18021a3a9  nop
0x18021a3aa  mov     rcx, [rbp+var_10]
0x18021a3ae  test    rcx, rcx
0x18021a3b1  jz      short loc_18021A3C4
0x18021a3b3  mov     [rbp+var_10], r12
0x18021a3b7  mov     rax, [rcx]
0x18021a3ba  mov     rax, [rax+10h]
0x18021a3be  call    _guard_dispatch_icall
0x18021a3c3  nop
0x18021a3c4  mov     rcx, [rbp+var_28]
0x18021a3c8  mov     rax, [rcx]
0x18021a3cb  mov     rax, [rax+40h]
0x18021a3cf  lea     rdx, [rbp+var_38]
0x18021a3d3  call    _guard_dispatch_icall
0x18021a3d8  test    eax, eax
0x18021a3da  mov     edi, eax
0x18021a3dc  jns     loc_18021A26D
0x18021a3e2  jmp     short loc_18021A438
0x18021a3e4  mov     rcx, [rbp+var_40]; string
0x18021a3e8  test    rcx, rcx
0x18021a3eb  jz      short loc_18021A3F4
0x18021a3ed  call    cs:__imp_WindowsDeleteString
0x18021a3f3  nop
0x18021a3f4  mov     rcx, [rbp+string]; string
0x18021a3f8  test    rcx, rcx
0x18021a3fb  jz      short loc_18021A404
0x18021a3fd  call    cs:__imp_WindowsDeleteString
0x18021a403  nop
0x18021a404  mov     rcx, [rbp+var_30]
0x18021a408  test    rcx, rcx
0x18021a40b  jz      short loc_18021A41E
0x18021a40d  mov     [rbp+var_30], r12
0x18021a411  mov     rax, [rcx]
0x18021a414  mov     rax, [rax+10h]
0x18021a418  call    _guard_dispatch_icall
0x18021a41d  nop
0x18021a41e  mov     rcx, [rbp+var_10]
0x18021a422  test    rcx, rcx
0x18021a425  jz      short loc_18021A438
0x18021a427  mov     [rbp+var_10], r12
0x18021a42b  mov     rax, [rcx]
0x18021a42e  mov     rax, [rax+10h]
0x18021a432  call    _guard_dispatch_icall
0x18021a437  nop
0x18021a438  mov     rcx, [rbp+var_28]
0x18021a43c  test    rcx, rcx
0x18021a43f  jz      short loc_18021A452
0x18021a441  mov     [rbp+var_28], r12
0x18021a445  mov     rax, [rcx]
0x18021a448  mov     rax, [rax+10h]
0x18021a44c  call    _guard_dispatch_icall
0x18021a451  nop
0x18021a452  mov     rcx, [rbp+var_18]
0x18021a456  test    rcx, rcx
0x18021a459  jz      short loc_18021A46C
0x18021a45b  mov     [rbp+var_18], r12
0x18021a45f  mov     rax, [rcx]
0x18021a462  mov     rax, [rax+10h]
0x18021a466  call    _guard_dispatch_icall
0x18021a46b  nop
0x18021a46c  mov     eax, edi
0x18021a46e  mov     rcx, [rbp+var_8]
0x18021a472  xor     rcx, rsp; StackCookie
0x18021a475  call    __security_check_cookie
0x18021a47a  add     rsp, 70h
0x18021a47e  pop     r15
0x18021a480  pop     r14
0x18021a482  pop     r12
0x18021a484  pop     rdi
0x18021a485  pop     rsi
0x18021a486  pop     rbx
0x18021a487  pop     rbp
0x18021a488  retn
```
