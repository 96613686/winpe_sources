# CZipFolder::InvokeCommand(_CMINVOKECOMMANDINFO *)

- ea: `0x18003fde0`
- end: `0x180040338`
- name: `?InvokeCommand@CZipFolder@@UEAAJPEAU_CMINVOKECOMMANDINFO@@@Z`
- size: `1368`
- prototype: `__int64 __fastcall(CZipFolder *__hidden this, struct _CMINVOKECOMMANDINFO *)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d4e4`
- `0x18000fe10`
- `0x1800106c0`
- `0x180011534`
- `0x180013448`
- `0x18001f13c`
- `0x18001f680`
- `0x180027764`
- `0x180029994`
- `0x180036f50`
- `0x180037958`
- `0x18003ef3c`
- `0x18003fd28`
- `0x18003fde0`
- `0x180040340`
- `0x180040460`
- `0x180044e60`
- `0x180047b7c`
- `0x18006e9a0`
- `0x180071010`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x180040226`
- `SHELL32!SHChangeNotify` at `0x180040226`
- `SHLWAPI!PathFindFileNameW` at `0x1800400ea`
- `SHLWAPI!PathFindFileNameW` at `0x1800400ea`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x1800402c0`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x1800402c0`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18003fe8a`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18003fe8a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004009b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004009b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004019f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004019f`
- `KERNEL32!lstrcmpW` at `0x1800402d2`
- `KERNEL32!lstrcmpW` at `0x1800402f8`
- `KERNEL32!lstrcmpW` at `0x1800402d2`
- `KERNEL32!lstrcmpW` at `0x1800402f8`

## pseudocode

```c
__int64 __fastcall CZipFolder::InvokeCommand(CZipFolder *this, struct _CMINVOKECOMMANDINFO *a2)
{
  const CHAR *lpVerb; // rcx
  int CountOfZipMembers; // edi
  char IsEnabled; // al
  __int64 v7; // rcx
  HWND v8; // rdx
  HWND v10; // rdx
  void (*SetTitle)(void); // rax
  int DecryptPassword; // eax
  struct IProgressDialog *v13; // rcx
  int v14; // esi
  const unsigned __int16 *FileNameW; // rax
  unsigned int v16; // edx
  int v17; // r12d
  int v18; // eax
  HGLOBAL v19; // r12
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  HGLOBAL hMem; // [rsp+38h] [rbp-C8h]
  struct IProgressDialog *v23; // [rsp+40h] [rbp-C0h] BYREF
  HWND hWnd; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pwszDst[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v27; // [rsp+64h] [rbp-9Ch]
  const WCHAR *v28; // [rsp+70h] [rbp-90h]
  int v29; // [rsp+78h] [rbp-88h]
  int v30; // [rsp+8Ch] [rbp-74h]
  __int64 v31; // [rsp+90h] [rbp-70h]
  WCHAR *v32; // [rsp+D4h] [rbp-2Ch]
  _BYTE v33[4240]; // [rsp+810h] [rbp+710h] BYREF
  WCHAR Buffer[20]; // [rsp+18A0h] [rbp+17A0h] BYREF

  lpVerb = a2->lpVerb;
  if ( (unsigned __int64)lpVerb >= 0x10000 )
  {
    SHAnsiToUnicode(lpVerb, pwszDst, 260);
    if ( !lstrcmpW(L"paste", pwszDst) )
      return (unsigned int)CZipFolder::PasteToZipFolder((CZipFolder *)((char *)this - 16));
    CountOfZipMembers = -2147024809;
    if ( lstrcmpW(L"extract", pwszDst) )
      return (unsigned int)CountOfZipMembers;
    return (unsigned int)ExtractZipFile((const unsigned __int16 *)this + 28, 0);
  }
  if ( !(_WORD)lpVerb )
    return (unsigned int)ExtractZipFile((const unsigned __int16 *)this + 28, 0);
  if ( (unsigned __int16)lpVerb != 1 )
    return (unsigned int)-2147467259;
  if ( (unsigned int)CheckDiskSpace((LPCWSTR)this + 28) )
  {
    v23 = 0;
    CountOfZipMembers = CreateProgressDialog(&v23);
    if ( CountOfZipMembers >= 0 )
    {
      v21 = 0;
      memset_0(v33, 0, 0x1086u);
      CountOfZipMembers = DZ_GetCountOfZipMembers(a2->hwnd, (const unsigned __int16 *)this + 28, &v21);
      if ( CountOfZipMembers >= 0 )
      {
        memset_0(pwszDst, 0, 0x7A4u);
        CountOfZipMembers = InitUNZIPCMDSTRUCT(
                              (struct UNZIPCMDSTRUCT *)pwszDst,
                              (const unsigned __int16 *)this + 28,
                              0,
                              0,
                              0);
        if ( CountOfZipMembers >= 0 )
        {
          v10 = a2->hwnd;
          v28 = L"*.*";
          v27 = 7;
          v32 = (WCHAR *)v33;
          v29 = 0;
          v30 = 0;
          v31 = 1;
          CountOfZipMembers = ((__int64 (__fastcall *)(struct IProgressDialog *, HWND, _QWORD, __int64, _QWORD))v23->lpVtbl->SetAnimation)(
                                v23,
                                v10,
                                0,
                                3,
                                0);
          if ( CountOfZipMembers < 0 )
          {
            ((void (__fastcall *)(struct IProgressDialog *, _QWORD, _QWORD))v23->lpVtbl->SetProgress64)(v23, 0, 0);
            SetTitle = (void (*)(void))v23->lpVtbl->SetTitle;
LABEL_15:
            SetTitle();
            return (unsigned int)CountOfZipMembers;
          }
          hWnd = a2->hwnd;
          v25 = 0;
          if ( ((__int64 (__fastcall *)(struct IProgressDialog *, GUID *, __int64 *))v23->lpVtbl->StartProgressDialog)(
                 v23,
                 &GUID_00000114_0000_0000_c000_000000000046,
                 &v25) >= 0 )
          {
            (*(void (__fastcall **)(__int64, HWND *))(*(_QWORD *)v25 + 24LL))(v25, &hWnd);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          dword_18008BBC0 = 1;
          DecryptPassword = CPassword::GetDecryptPassword(
                              (CPassword *)&g_password,
                              hWnd,
                              (const unsigned __int16 *)this + 28);
          v13 = v23;
          CountOfZipMembers = DecryptPassword;
          dword_18008BBC0 = 0;
          if ( DecryptPassword < 0 )
          {
LABEL_19:
            ((void (__fastcall *)(struct IProgressDialog *, _QWORD, _QWORD))v13->lpVtbl->SetProgress64)(v13, 0, 0);
            ((void (__fastcall *)(struct IProgressDialog *))v23->lpVtbl->HasUserCancelled)(v23);
            SetTitle = (void (*)(void))v23->lpVtbl->SetTitle;
            goto LABEL_15;
          }
          ::SetTitle(v23, 0x2791u);
          hMem = 0;
          LoadStringW(g_hmodThisDll, 0x272Cu, Buffer, 20);
          v14 = 0;
          if ( v21 > 0 )
          {
            while ( 1 )
            {
              v29 = v14;
              if ( (unsigned int)dunzip(pwszDst) )
                goto LABEL_32;
              if ( (v32[12] & 0x10) == 0 && (unsigned int)IsValidZipItemPath(v32 + 51) )
                break;
LABEL_34:
              if ( ++v14 >= v21 )
                goto LABEL_35;
            }
            FileNameW = PathFindFileNameW(v32 + 51);
            SetLine(v23, v16, FileNameW);
            do
            {
              v17 = UnzipToMemory((unsigned __int16 *)this + 28, hWnd);
              if ( v17 != 1 )
                break;
              dword_18008BBC0 = 1;
              v18 = CPassword::GetDecryptPassword((CPassword *)&g_password, hWnd, (const unsigned __int16 *)this + 28);
              dword_18008BBC0 = 0;
              CountOfZipMembers = v18;
              if ( v18 < 0 )
              {
                v13 = v23;
                goto LABEL_19;
              }
            }
            while ( !v18 );
            if ( v17 < 0 )
            {
              ((void (__fastcall *)(struct IProgressDialog *, _QWORD, _QWORD))v23->lpVtbl->SetProgress64)(v23, 0, 0);
              ((void (__fastcall *)(struct IProgressDialog *))v23->lpVtbl->HasUserCancelled)(v23);
              ((void (__fastcall *)(struct IProgressDialog *))v23->lpVtbl->SetTitle)(v23);
              return (unsigned int)v17;
            }
            v19 = hMem;
            CountOfZipMembers = ZipFromMemory((unsigned __int16 *)this + 28);
            if ( CountOfZipMembers < 0 )
            {
              ((void (__fastcall *)(struct IProgressDialog *, _QWORD, _QWORD))v23->lpVtbl->SetProgress64)(v23, 0, 0);
              ((void (__fastcall *)(struct IProgressDialog *))v23->lpVtbl->HasUserCancelled)(v23);
              ((void (__fastcall *)(struct IProgressDialog *))v23->lpVtbl->SetTitle)(v23);
              return 2147500037LL;
            }
            *((_DWORD *)this + 280) = 0;
            *((_DWORD *)this + 281) = 1;
            if ( v19 )
              GlobalFree(v19);
LABEL_32:
            if ( ((unsigned int (__fastcall *)(struct IProgressDialog *))v23->lpVtbl->SetLine)(v23) )
              goto LABEL_35;
            ((void (__fastcall *)(struct IProgressDialog *, _QWORD, _QWORD))v23->lpVtbl->SetCancelMsg)(
              v23,
              (unsigned int)(v14 + 1),
              (unsigned int)v21);
            goto LABEL_34;
          }
LABEL_35:
          ((void (__fastcall *)(struct IProgressDialog *, _QWORD, _QWORD))v23->lpVtbl->SetProgress64)(v23, 0, 0);
          ((void (__fastcall *)(struct IProgressDialog *))v23->lpVtbl->HasUserCancelled)(v23);
          ((void (__fastcall *)(struct IProgressDialog *))v23->lpVtbl->SetTitle)(v23);
        }
      }
    }
    SHChangeNotify(0x2000, 5u, (char *)this + 56, 0);
    return (unsigned int)CountOfZipMembers;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl);
  v8 = a2->hwnd;
  if ( IsEnabled )
    MessageBoxHelper::ShellMessageBoxTextScaled___0(v7, v8);
  else
    ShellMessageBoxW(g_hmodThisDll, v8, (LPCWSTR)0x27D0, (LPCWSTR)0x2747, 0x40u);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18003fde0  mov     [rsp-8+arg_10], rsi
0x18003fde5  push    rbp
0x18003fde6  push    rdi
0x18003fde7  push    r12
0x18003fde9  push    r14
0x18003fdeb  push    r15
0x18003fded  lea     rbp, [rsp-17D0h]
0x18003fdf5  mov     eax, 18D0h
0x18003fdfa  call    _alloca_probe
0x18003fdff  sub     rsp, rax
0x18003fe02  mov     rax, cs:__security_cookie
0x18003fe09  xor     rax, rsp
0x18003fe0c  mov     [rbp+17F0h+var_28], rax
0x18003fe13  mov     r15, rcx
0x18003fe16  mov     rsi, rdx
0x18003fe19  mov     rcx, [rdx+10h]; pszSrc
0x18003fe1d  cmp     rcx, 10000h
0x18003fe24  jnb     loc_1800402B5
0x18003fe2a  movzx   eax, cx
0x18003fe2d  test    eax, eax
0x18003fe2f  jz      loc_180040302
0x18003fe35  cmp     eax, 1
0x18003fe38  jz      short loc_18003FE44
0x18003fe3a  mov     edi, 80004005h
0x18003fe3f  jmp     loc_18004030F
0x18003fe44  lea     r14, [r15+38h]
0x18003fe48  mov     rcx, r14; pszPath
0x18003fe4b  call    ?CheckDiskSpace@@YAHPEBG@Z; CheckDiskSpace(ushort const *)
0x18003fe50  test    eax, eax
0x18003fe52  jnz     short loc_18003FE9A
0x18003fe54  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x18003fe5b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x18003fe60  mov     rdx, [rsi+8]; hWnd
0x18003fe64  test    al, al
0x18003fe66  jz      short loc_18003FE6F
0x18003fe68  call    MessageBoxHelper__ShellMessageBoxTextScaled___0
0x18003fe6d  jmp     short loc_18003FE90
0x18003fe6f  mov     rcx, cs:g_hmodThisDll; hAppInst
0x18003fe76  mov     r9d, 2747h; lpcTitle
0x18003fe7c  mov     r8d, 27D0h; lpcText
0x18003fe82  mov     [rsp+18F0h+fuStyle], 40h ; '@'; fuStyle
0x18003fe8a  call    cs:__imp_ShellMessageBoxW
0x18003fe90  mov     eax, 80004005h
0x18003fe95  jmp     loc_180040311
0x18003fe9a  lea     rcx, [rsp+18F0h+var_18B0]; struct IProgressDialog **
0x18003fe9f  mov     [rsp+18F0h+var_18B0], 0
0x18003fea8  call    ?CreateProgressDialog@@YAJPEAPEAUIProgressDialog@@@Z; CreateProgressDialog(IProgressDialog * *)
0x18003fead  mov     edi, eax
0x18003feaf  test    eax, eax
0x18003feb1  js      loc_180040217
0x18003feb7  xor     edx, edx; Val
0x18003feb9  mov     [rsp+18F0h+var_18C0], 0
0x18003fec1  mov     r8d, 1086h; Size
0x18003fec7  lea     rcx, [rbp+17F0h+var_10E0]; void *
0x18003fece  call    memset_0
0x18003fed3  mov     rcx, [rsi+8]; HWND
0x18003fed7  lea     r8, [rsp+18F0h+var_18C0]; int *
0x18003fedc  mov     rdx, r14; unsigned __int16 *
0x18003fedf  call    ?DZ_GetCountOfZipMembers@@YAJPEAUHWND__@@PEBGPEAH@Z; DZ_GetCountOfZipMembers(HWND__ *,ushort const *,int *)
0x18003fee4  mov     edi, eax
0x18003fee6  test    eax, eax
0x18003fee8  js      loc_180040217
0x18003feee  xor     edx, edx; Val
0x18003fef0  lea     rcx, [rsp+18F0h+pwszDst]; void *
0x18003fef5  mov     r8d, 7A4h; Size
0x18003fefb  call    memset_0
0x18003ff00  xor     r9d, r9d; unsigned __int16 *
0x18003ff03  mov     qword ptr [rsp+18F0h+fuStyle], 0; unsigned __int16 *
0x18003ff0c  xor     r8d, r8d; unsigned __int16 *
0x18003ff0f  lea     rcx, [rsp+18F0h+pwszDst]; struct UNZIPCMDSTRUCT *
0x18003ff14  mov     rdx, r14; unsigned __int16 *
0x18003ff17  call    ?InitUNZIPCMDSTRUCT@@YAJPEAUUNZIPCMDSTRUCT@@PEBG111@Z; InitUNZIPCMDSTRUCT(UNZIPCMDSTRUCT *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18003ff1c  mov     edi, eax
0x18003ff1e  test    eax, eax
0x18003ff20  js      loc_180040217
0x18003ff26  mov     rcx, [rsp+18F0h+var_18B0]
0x18003ff2b  lea     rax, pszMore; "*.*"
0x18003ff32  mov     rdx, [rsi+8]
0x18003ff36  mov     r9d, 3
0x18003ff3c  mov     [rsp+18F0h+var_1880], rax
0x18003ff41  xor     r8d, r8d
0x18003ff44  lea     rax, [rbp+17F0h+var_10E0]
0x18003ff4b  mov     [rsp+18F0h+var_188C], 7
0x18003ff53  mov     [rbp+17F0h+var_181C], rax
0x18003ff57  mov     [rsp+18F0h+var_1878], 0
0x18003ff5f  mov     [rbp+17F0h+var_1864], 0
0x18003ff66  mov     [rbp+17F0h+var_1860], 1
0x18003ff6e  mov     rax, [rcx]
0x18003ff71  mov     qword ptr [rsp+18F0h+fuStyle], 0
0x18003ff7a  mov     rax, [rax+18h]
0x18003ff7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff83  mov     rcx, [rsp+18F0h+var_18B0]
0x18003ff88  mov     edi, eax
0x18003ff8a  test    eax, eax
0x18003ff8c  jns     short loc_18003FFB5
0x18003ff8e  mov     rdx, [rcx]
0x18003ff91  xor     r8d, r8d
0x18003ff94  mov     rax, [rdx+30h]
0x18003ff98  xor     edx, edx
0x18003ff9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff9f  mov     rcx, [rsp+18F0h+var_18B0]
0x18003ffa4  mov     rdx, [rcx]
0x18003ffa7  mov     rax, [rdx+10h]
0x18003ffab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffb0  jmp     loc_18004030F
0x18003ffb5  mov     rax, [rsi+8]
0x18003ffb9  lea     r8, [rsp+18F0h+var_18A0]
0x18003ffbe  mov     [rsp+18F0h+hWnd], rax
0x18003ffc3  lea     rdx, _GUID_00000114_0000_0000_c000_000000000046
0x18003ffca  mov     [rsp+18F0h+var_18A0], 0
0x18003ffd3  mov     rax, [rcx]
0x18003ffd6  mov     rax, [rax]
0x18003ffd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffde  test    eax, eax
0x18003ffe0  js      short loc_180040009
0x18003ffe2  mov     rcx, [rsp+18F0h+var_18A0]
0x18003ffe7  lea     rdx, [rsp+18F0h+hWnd]
0x18003ffec  mov     rax, [rcx]
0x18003ffef  mov     rax, [rax+18h]
0x18003fff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fff8  mov     rcx, [rsp+18F0h+var_18A0]
0x18003fffd  mov     rax, [rcx]
0x180040000  mov     rax, [rax+10h]
0x180040004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040009  mov     rdx, [rsp+18F0h+hWnd]; HWND
0x18004000e  lea     rcx, ?g_password@@3VCPassword@@A; this
0x180040015  mov     r8, r14; unsigned __int16 *
0x180040018  mov     cs:dword_18008BBC0, 1
0x180040022  call    ?GetDecryptPassword@CPassword@@QEAAJPEAUHWND__@@PEFBG@Z; CPassword::GetDecryptPassword(HWND__ *,ushort const *)
0x180040027  mov     rcx, [rsp+18F0h+var_18B0]; struct IProgressDialog *
0x18004002c  mov     edi, eax
0x18004002e  mov     cs:dword_18008BBC0, 0
0x180040038  test    eax, eax
0x18004003a  jns     short loc_18004006F
0x18004003c  mov     rax, [rcx]
0x18004003f  xor     r8d, r8d
0x180040042  xor     edx, edx
0x180040044  mov     rax, [rax+30h]
0x180040048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004004d  mov     rcx, [rsp+18F0h+var_18B0]
0x180040052  mov     rax, [rcx]
0x180040055  mov     rax, [rax+20h]
0x180040059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004005e  mov     rcx, [rsp+18F0h+var_18B0]
0x180040063  mov     rax, [rcx]
0x180040066  mov     rax, [rax+10h]
0x18004006a  jmp     loc_18003FFAB
0x18004006f  mov     edx, 2791h; unsigned int
0x180040074  call    ?SetTitle@@YAXPEAUIProgressDialog@@I@Z; SetTitle(IProgressDialog *,uint)
0x180040079  mov     rcx, cs:g_hmodThisDll; hInstance
0x180040080  lea     r8, [rbp+17F0h+Buffer]; lpBuffer
0x180040087  mov     r9d, 14h; cchBufferMax
0x18004008d  mov     [rsp+18F0h+hMem], 0
0x180040096  mov     edx, 272Ch; uID
0x18004009b  call    cs:__imp_LoadStringW
0x1800400a1  xor     esi, esi
0x1800400a3  cmp     [rsp+18F0h+var_18C0], esi
0x1800400a7  jle     loc_1800401DF
0x1800400ad  lea     rcx, [rsp+18F0h+pwszDst]
0x1800400b2  mov     [rsp+18F0h+var_1878], esi
0x1800400b6  call    dunzip
0x1800400bb  test    eax, eax
0x1800400bd  jnz     loc_1800401A5
0x1800400c3  mov     rcx, [rbp+17F0h+var_181C]
0x1800400c7  test    byte ptr [rcx+18h], 10h
0x1800400cb  jnz     loc_1800401D3
0x1800400d1  add     rcx, 66h ; 'f'; unsigned __int16 *
0x1800400d5  call    ?IsValidZipItemPath@@YAHPEBG@Z; IsValidZipItemPath(ushort const *)
0x1800400da  test    eax, eax
0x1800400dc  jz      loc_1800401D3
0x1800400e2  mov     rcx, [rbp+17F0h+var_181C]
0x1800400e6  add     rcx, 66h ; 'f'; pszPath
0x1800400ea  call    cs:__imp_PathFindFileNameW
0x1800400f0  mov     rcx, [rsp+18F0h+var_18B0]; struct IProgressDialog *
0x1800400f5  mov     r8, rax; unsigned __int16 *
0x1800400f8  call    ?SetLine@@YAXPEAUIProgressDialog@@KPEBG@Z; SetLine(IProgressDialog *,ulong,ushort const *)
0x1800400fd  mov     rax, [rsp+18F0h+hWnd]
0x180040102  lea     rdx, [rsp+18F0h+hMem]
0x180040107  mov     r8, [rbp+17F0h+var_181C]
0x18004010b  mov     r9d, esi
0x18004010e  mov     rcx, r14; unsigned __int16 *
0x180040111  mov     qword ptr [rsp+18F0h+fuStyle], rax; hWnd
0x180040116  call    UnzipToMemory
0x18004011b  mov     r12d, eax
0x18004011e  cmp     eax, 1
0x180040121  jnz     short loc_180040155
0x180040123  mov     rdx, [rsp+18F0h+hWnd]; HWND
0x180040128  lea     rcx, ?g_password@@3VCPassword@@A; this
0x18004012f  mov     r8, r14; unsigned __int16 *
0x180040132  mov     cs:dword_18008BBC0, eax
0x180040138  call    ?GetDecryptPassword@CPassword@@QEAAJPEAUHWND__@@PEFBG@Z; CPassword::GetDecryptPassword(HWND__ *,ushort const *)
0x18004013d  mov     cs:dword_18008BBC0, 0
0x180040147  mov     edi, eax
0x180040149  test    eax, eax
0x18004014b  js      loc_180040231
0x180040151  test    eax, eax
0x180040153  jz      short loc_1800400FD
0x180040155  test    r12d, r12d
0x180040158  js      loc_180040278
0x18004015e  mov     r12, [rsp+18F0h+hMem]
0x180040163  mov     rcx, r14; unsigned __int16 *
0x180040166  mov     r9, [rsp+18F0h+hWnd]
0x18004016b  mov     rdx, r12
0x18004016e  mov     r8, [rbp+17F0h+var_181C]
0x180040172  call    ZipFromMemory
0x180040177  mov     edi, eax
0x180040179  test    eax, eax
0x18004017b  js      loc_18004023B
0x180040181  mov     dword ptr [r15+460h], 0
0x18004018c  mov     dword ptr [r15+464h], 1
0x180040197  test    r12, r12
0x18004019a  jz      short loc_1800401A5
0x18004019c  mov     rcx, r12; hMem
0x18004019f  call    cs:__imp_GlobalFree
0x1800401a5  mov     rcx, [rsp+18F0h+var_18B0]
0x1800401aa  mov     rax, [rcx]
0x1800401ad  mov     rax, [rax+38h]
0x1800401b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401b6  test    eax, eax
0x1800401b8  jnz     short loc_1800401DF
0x1800401ba  mov     rcx, [rsp+18F0h+var_18B0]
0x1800401bf  lea     edx, [rsi+1]
0x1800401c2  mov     r8d, [rsp+18F0h+var_18C0]
0x1800401c7  mov     rax, [rcx]
0x1800401ca  mov     rax, [rax+40h]
0x1800401ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401d3  inc     esi
0x1800401d5  cmp     esi, [rsp+18F0h+var_18C0]
0x1800401d9  jl      loc_1800400AD
0x1800401df  mov     rcx, [rsp+18F0h+var_18B0]
0x1800401e4  xor     r8d, r8d
0x1800401e7  xor     edx, edx
0x1800401e9  mov     rax, [rcx]
0x1800401ec  mov     rax, [rax+30h]
0x1800401f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401f5  mov     rcx, [rsp+18F0h+var_18B0]
0x1800401fa  mov     rax, [rcx]
0x1800401fd  mov     rax, [rax+20h]
0x180040201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040206  mov     rcx, [rsp+18F0h+var_18B0]
0x18004020b  mov     rax, [rcx]
0x18004020e  mov     rax, [rax+10h]
0x180040212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040217  xor     r9d, r9d; dwItem2
0x18004021a  mov     r8, r14; dwItem1
0x18004021d  mov     ecx, 2000h; wEventId
0x180040222  lea     edx, [r9+5]; uFlags
0x180040226  call    cs:__imp_SHChangeNotify
0x18004022c  jmp     loc_18004030F
0x180040231  mov     rcx, [rsp+18F0h+var_18B0]
0x180040236  jmp     loc_18004003C
0x18004023b  mov     rcx, [rsp+18F0h+var_18B0]
0x180040240  xor     r8d, r8d
0x180040243  xor     edx, edx
0x180040245  mov     rax, [rcx]
0x180040248  mov     rax, [rax+30h]
0x18004024c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040251  mov     rcx, [rsp+18F0h+var_18B0]
0x180040256  mov     rax, [rcx]
0x180040259  mov     rax, [rax+20h]
0x18004025d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040262  mov     rcx, [rsp+18F0h+var_18B0]
0x180040267  mov     rax, [rcx]
0x18004026a  mov     rax, [rax+10h]
0x18004026e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040273  jmp     loc_18003FE90
0x180040278  mov     rcx, [rsp+18F0h+var_18B0]
0x18004027d  xor     r8d, r8d
0x180040280  xor     edx, edx
0x180040282  mov     rax, [rcx]
0x180040285  mov     rax, [rax+30h]
0x180040289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004028e  mov     rcx, [rsp+18F0h+var_18B0]
0x180040293  mov     rax, [rcx]
0x180040296  mov     rax, [rax+20h]
0x18004029a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004029f  mov     rcx, [rsp+18F0h+var_18B0]
0x1800402a4  mov     rax, [rcx]
0x1800402a7  mov     rax, [rax+10h]
0x1800402ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402b0  mov     eax, r12d
0x1800402b3  jmp     short loc_180040311
0x1800402b5  mov     r8d, 104h; cwchBuf
0x1800402bb  lea     rdx, [rsp+18F0h+pwszDst]; pwszDst
0x1800402c0  call    cs:__imp_SHAnsiToUnicode
0x1800402c6  lea     rdx, [rsp+18F0h+pwszDst]; lpString2
0x1800402cb  lea     rcx, String1; "paste"
0x1800402d2  call    cs:__imp_lstrcmpW
0x1800402d8  test    eax, eax
0x1800402da  jnz     short loc_1800402E7
0x1800402dc  lea     rcx, [r15-10h]; this
0x1800402e0  call    ?PasteToZipFolder@CZipFolder@@QEAAJXZ; CZipFolder::PasteToZipFolder(void)
0x1800402e5  jmp     short loc_18004030D
0x1800402e7  lea     rdx, [rsp+18F0h+pwszDst]; lpString2
0x1800402ec  mov     edi, 80070057h
0x1800402f1  lea     rcx, aExtract; "extract"
0x1800402f8  call    cs:__imp_lstrcmpW
0x1800402fe  test    eax, eax
0x180040300  jnz     short loc_18004030F
0x180040302  xor     edx, edx; unsigned __int16 *
  ... truncated ...
```
