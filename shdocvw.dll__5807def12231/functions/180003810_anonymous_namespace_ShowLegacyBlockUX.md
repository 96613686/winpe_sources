# _anonymous_namespace_::ShowLegacyBlockUX

- ea: `0x180003810`
- end: `0x180003b21`
- name: `_anonymous_namespace_::ShowLegacyBlockUX`
- size: `785`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003660`

## callees

- `0x180003810`
- `0x1800056b4`
- `0x180008320`
- `0x180009018`
- `0x18000bf34`
- `0x180015e40`
- `0x180017084`
- `0x180017c18`
- `0x1800188b0`
- `0x18001a59c`
- `0x18001d454`
- `0x18002760c`
- `0x180027c30`

## import_xrefs

- `SHELL32!__imp_PathIsTemporaryW` at `0x180003938`
- `SHELL32!__imp_PathIsTemporaryW` at `0x180003938`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x180003949`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x180003949`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800039f0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800039f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800039be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800039be`
- `WINTRUST!WTGetSignatureInfo` at `0x1800038e9`
- `WINTRUST!WTGetSignatureInfo` at `0x1800038e9`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::ShowLegacyBlockUX(
        __int64 a1,
        const unsigned __int16 *a2,
        bool a3,
        __int64 a4,
        char a5,
        unsigned __int8 a6)
{
  int v10; // eax
  unsigned int v11; // r8d
  char IsUntrustedLocation; // r13
  const CHAR *v13; // rdx
  int v14; // r12d
  __int64 v15; // rdx
  int v16; // ebx
  __int64 v17; // rdx
  __int64 v18; // rcx
  HWND v19; // rbx
  unsigned int v20; // edi
  HWND v21; // r8
  __int64 result; // rax
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  int v25; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v26; // [rsp+44h] [rbp-BCh]
  __int128 v27; // [rsp+54h] [rbp-ACh]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int16 *v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+70h] [rbp-90h]
  int v31; // [rsp+74h] [rbp-8Ch]
  __int16 *v32; // [rsp+78h] [rbp-88h]
  int v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+84h] [rbp-7Ch]
  int v35; // [rsp+94h] [rbp-6Ch]
  _DWORD v36[3]; // [rsp+A0h] [rbp-60h] BYREF
  int v37; // [rsp+ACh] [rbp-54h]
  WCHAR *v38; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v39; // [rsp+B8h] [rbp-48h]
  __int64 v40; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v41; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v42; // [rsp+D0h] [rbp-30h]
  __int64 v43; // [rsp+D8h] [rbp-28h]
  int v44; // [rsp+E0h] [rbp-20h]
  int v45; // [rsp+E4h] [rbp-1Ch]
  int v46; // [rsp+E8h] [rbp-18h]
  int v47; // [rsp+ECh] [rbp-14h]
  char v48; // [rsp+F0h] [rbp-10h]
  int v49; // [rsp+F1h] [rbp-Fh]
  __int16 v50; // [rsp+F5h] [rbp-Bh]
  char v51; // [rsp+F7h] [rbp-9h]
  int *v52; // [rsp+F8h] [rbp-8h]
  __int128 v53; // [rsp+100h] [rbp+0h]
  __int128 v54; // [rsp+110h] [rbp+10h]
  __int128 v55; // [rsp+120h] [rbp+20h]
  __int64 v56; // [rsp+130h] [rbp+30h]
  __int16 v57; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v58[254]; // [rsp+142h] [rbp+42h] BYREF
  WCHAR Buffer[96]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v60; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v61[4174]; // [rsp+302h] [rbp+202h] BYREF
  __int16 v62; // [rsp+1350h] [rbp+1250h] BYREF
  _BYTE v63[4174]; // [rsp+1352h] [rbp+1252h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+23F8h] [rbp+22F8h]

  v57 = 0;
  memset_0(v58, 0, sizeof(v58));
  v62 = 0;
  memset_0(v63, 0, 0x1046u);
  v25 = 88;
  v35 = 0;
  v31 = 0;
  v28 = 0;
  v32 = &v62;
  v33 = 2084;
  v29 = &v57;
  v26 = 0;
  v30 = 128;
  v27 = 0;
  v34 = 0;
  v10 = WTGetSignatureInfo(a2, -1, 1, &v25);
  if ( v10 < 0 || (v10 = EnsurePublisherName(a3, (struct SIGNATURE_INFO *)&v25), v10 < 0) )
  {
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x6FD, v11, (const char *)(unsigned int)v10, 0);
    return 0;
  }
  else
  {
    IsUntrustedLocation = anonymous_namespace_::IsUntrustedLocation(a2, &v25);
    if ( (_DWORD)v26 == 7
      || (unsigned int)PathIsTemporaryW(a2)
      || SHWindowsPolicy(POLID_HideZoneInfoOnProperties, v13)
      || (v14 = 1, (a5 & 1) == 0) )
    {
      v14 = 0;
    }
    v60 = 0;
    memset_0(v61, 0, 0x1046u);
    v23 = 1;
    hMem = 0;
    if ( (int)GetHostDisplayNameFromUrlInternal(a2, v15, &hMem, &v23) < 0 )
    {
      StringCchCopyW(&v60, 0x824u, a2);
      v16 = 1;
    }
    else
    {
      StringCchCopyW(&v60, 0x824u, (const unsigned __int16 *)hMem);
      LocalFree(hMem);
      v16 = v23;
    }
    LoadStringW(g_hinst, 0x8535u, Buffer, 96);
    v40 = a4;
    v36[0] = 1;
    v36[1] = 2;
    v37 = v14;
    v36[2] = a3;
    v38 = Buffer;
    v41 = &v60;
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v52 = &v25;
    v56 = 0;
    v39 = a2;
    v42 = a2;
    v43 = 0;
    v44 = 0;
    v45 = a6;
    v46 = 0;
    v47 = v16;
    v48 = IsUntrustedLocation;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v19 = (HWND)anonymous_namespace_::HandleImmersiveHwnd(a1);
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v18, v17, a2);
    v20 = _ShowSafeOpenDialog(v19, v17, (struct SAFEOPENDLGPARAM *)v36);
    if ( v37 == 2 )
    {
      v21 = 0;
      if ( a6 )
        v21 = v19;
      RemoveZoneIdentifier(a2, a6, v21);
    }
    result = 0;
    if ( v20 != 1 )
      return 1223;
  }
  return result;
}

```

## disassembly

```asm
0x180003810  push    rbp
0x180003812  push    rbx
0x180003813  push    rsi
0x180003814  push    rdi
0x180003815  push    r14
0x180003817  push    r15
0x180003819  lea     rbp, [rsp-22C8h]
0x180003821  mov     eax, 23C8h
0x180003826  call    _alloca_probe
0x18000382b  sub     rsp, rax
0x18000382e  mov     rax, cs:__security_cookie
0x180003835  xor     rax, rsp
0x180003838  mov     [rbp+22F0h+var_50], rax
0x18000383f  movzx   edi, r8b
0x180003843  mov     rsi, rdx
0x180003846  mov     r14, rcx
0x180003849  xor     ebx, ebx
0x18000384b  xor     edx, edx; Val
0x18000384d  mov     [rbp+22F0h+var_22B0], bx
0x180003851  mov     r8d, 0FEh; Size
0x180003857  lea     rcx, [rbp+22F0h+var_22AE]; void *
0x18000385b  mov     r15, r9
0x18000385e  call    memset_0
0x180003863  xor     edx, edx; Val
0x180003865  mov     [rbp+22F0h+var_10A0], bx
0x18000386c  mov     r8d, 1046h; Size
0x180003872  lea     rcx, [rbp+22F0h+var_109E]; void *
0x180003879  call    memset_0
0x18000387e  xorps   xmm0, xmm0
0x180003881  mov     qword ptr [rsp+23F0h+var_23C8], rbx; int
0x180003886  xor     eax, eax
0x180003888  mov     [rsp+23F0h+var_23B0], 58h ; 'X'
0x180003890  mov     [rbp+22F0h+var_235C], eax
0x180003893  lea     r9, [rsp+23F0h+var_23B0]
0x180003898  movups  [rsp+23F0h+var_237C], xmm0
0x18000389d  lea     rax, [rbp+22F0h+var_10A0]
0x1800038a4  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800038ab  movups  [rsp+23F0h+var_238C], xmm0
0x1800038b0  mov     qword ptr [rsp+23F0h+var_237C+4], rax
0x1800038b5  mov     r8d, 1
0x1800038bb  lea     rax, [rbp+22F0h+var_22B0]
0x1800038bf  mov     dword ptr [rbp+22F0h+var_237C+0Ch], 824h
0x1800038c6  mov     rcx, rsi
0x1800038c9  mov     qword ptr [rsp+23F0h+var_238C+4], rax
0x1800038ce  movups  [rsp+23F0h+var_23AC], xmm0
0x1800038d3  mov     dword ptr [rsp+23F0h+var_238C+0Ch], 80h
0x1800038db  movups  [rsp+23F0h+var_239C], xmm0
0x1800038e0  mov     qword ptr [rsp+23F0h+var_23D0], rbx; int
0x1800038e5  movups  [rbp+22F0h+var_236C], xmm0
0x1800038e9  call    cs:__imp_WTGetSignatureInfo
0x1800038ef  test    eax, eax
0x1800038f1  js      loc_180003AEC
0x1800038f7  lea     rdx, [rsp+23F0h+var_23B0]; struct SIGNATURE_INFO *
0x1800038fc  movzx   ecx, dil; bool
0x180003900  call    ?EnsurePublisherName@@YAJ_NPEAUSIGNATURE_INFO@@@Z; EnsurePublisherName(bool,SIGNATURE_INFO *)
0x180003905  test    eax, eax
0x180003907  js      loc_180003AEC
0x18000390d  mov     [rsp+23F0h+var_30], r12
0x180003915  lea     rdx, [rsp+23F0h+var_23B0]
0x18000391a  mov     rcx, rsi
0x18000391d  mov     [rsp+23F0h+var_38], r13
0x180003925  call    _anonymous_namespace___IsUntrustedLocation
0x18000392a  cmp     dword ptr [rsp+23F0h+var_23AC], 7
0x18000392f  movzx   r13d, al
0x180003933  jz      short loc_180003962
0x180003935  mov     rcx, rsi
0x180003938  call    cs:__imp_PathIsTemporaryW
0x18000393e  test    eax, eax
0x180003940  jnz     short loc_180003962
0x180003942  lea     rcx, POLID_HideZoneInfoOnProperties; "\b"
0x180003949  call    cs:__imp_SHWindowsPolicy
0x18000394f  test    eax, eax
0x180003951  jnz     short loc_180003962
0x180003953  test    [rbp+22F0h+arg_20], 1
0x18000395a  mov     r12d, 1
0x180003960  jnz     short loc_180003965
0x180003962  mov     r12d, ebx
0x180003965  xor     edx, edx; Val
0x180003967  mov     [rbp+22F0h+var_20F0], bx
0x18000396e  mov     r8d, 1046h; Size
0x180003974  lea     rcx, [rbp+22F0h+var_20EE]; void *
0x18000397b  call    memset_0
0x180003980  lea     r9, [rsp+23F0h+var_23C0]; int *
0x180003985  mov     [rsp+23F0h+var_23C0], 1
0x18000398d  lea     r8, [rsp+23F0h+hMem]; unsigned __int16 **
0x180003992  mov     [rsp+23F0h+hMem], rbx
0x180003997  mov     rcx, rsi; unsigned __int16 *
0x18000399a  call    ?GetHostDisplayNameFromUrlInternal@@YAJPEBGIPEAPEAGPEAHHH@Z; GetHostDisplayNameFromUrlInternal(ushort const *,uint,ushort * *,int *,int,int)
0x18000399f  lea     rcx, [rbp+22F0h+var_20F0]; unsigned __int16 *
0x1800039a6  mov     edx, 824h; unsigned __int64
0x1800039ab  test    eax, eax
0x1800039ad  js      short loc_1800039CA
0x1800039af  mov     r8, [rsp+23F0h+hMem]; unsigned __int16 *
0x1800039b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800039b9  mov     rcx, [rsp+23F0h+hMem]; hMem
0x1800039be  call    cs:__imp_LocalFree
0x1800039c4  mov     ebx, [rsp+23F0h+var_23C0]
0x1800039c8  jmp     short loc_1800039D7
0x1800039ca  mov     r8, rsi; unsigned __int16 *
0x1800039cd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800039d2  mov     ebx, 1
0x1800039d7  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x1800039de  lea     r8, [rbp+22F0h+Buffer]; lpBuffer
0x1800039e5  mov     r9d, 60h ; '`'; cchBufferMax
0x1800039eb  mov     edx, 8535h; uID
0x1800039f0  call    cs:__imp_LoadStringW
0x1800039f6  xor     eax, eax
0x1800039f8  mov     [rbp+22F0h+var_2330], r15
0x1800039fc  movzx   r15d, [rbp+22F0h+arg_28]
0x180003a04  xorps   xmm0, xmm0
0x180003a07  test    dil, dil
0x180003a0a  mov     [rbp+22F0h+var_2350], 1
0x180003a11  mov     rcx, r14
0x180003a14  mov     [rbp+22F0h+var_234C], 2
0x180003a1b  setnz   al
0x180003a1e  mov     [rbp+22F0h+var_2344], r12d
0x180003a22  mov     [rbp+22F0h+var_2348], eax
0x180003a25  lea     rax, [rbp+22F0h+Buffer]
0x180003a2c  mov     [rbp+22F0h+var_2340], rax
0x180003a30  lea     rax, [rbp+22F0h+var_20F0]
0x180003a37  mov     [rbp+22F0h+var_2328], rax
0x180003a3b  xor     eax, eax
0x180003a3d  mov     [rbp+22F0h+var_22FF], eax
0x180003a40  mov     [rbp+22F0h+var_22FB], ax
0x180003a44  mov     [rbp+22F0h+var_22F9], al
0x180003a47  lea     rax, [rsp+23F0h+var_23B0]
0x180003a4c  mov     [rbp+22F0h+var_22F8], rax
0x180003a50  xor     eax, eax
0x180003a52  mov     [rbp+22F0h+var_22C0], rax
0x180003a56  mov     [rbp+22F0h+var_2338], rsi
0x180003a5a  mov     [rbp+22F0h+var_2320], rsi
0x180003a5e  mov     [rbp+22F0h+var_2318], 0
0x180003a66  mov     [rbp+22F0h+var_2310], 0
0x180003a6d  mov     [rbp+22F0h+var_230C], r15d
0x180003a71  mov     [rbp+22F0h+var_2308], 0
0x180003a78  mov     [rbp+22F0h+var_2304], ebx
0x180003a7b  mov     [rbp+22F0h+var_2300], r13b
0x180003a7f  movups  [rbp+22F0h+var_22F0], xmm0
0x180003a83  movups  [rbp+22F0h+var_22E0], xmm0
0x180003a87  movups  [rbp+22F0h+var_22D0], xmm0
0x180003a8b  call    _anonymous_namespace___HandleImmersiveHwnd
0x180003a90  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180003a97  mov     rbx, rax
0x180003a9a  mov     r13, [rsp+23F0h+var_38]
0x180003aa2  jz      short loc_180003AAC
0x180003aa4  mov     r8, rsi
0x180003aa7  call    McTemplateU0z_EventWriteTransfer
0x180003aac  lea     r8, [rbp+22F0h+var_2350]; struct SAFEOPENDLGPARAM *
0x180003ab0  mov     rcx, rbx; hWndParent
0x180003ab3  call    ?_ShowSafeOpenDialog@@YAIPEAUHWND__@@IPEAUSAFEOPENDLGPARAM@@@Z; _ShowSafeOpenDialog(HWND__ *,uint,SAFEOPENDLGPARAM *)
0x180003ab8  cmp     [rbp+22F0h+var_2344], 2
0x180003abc  mov     edi, eax
0x180003abe  jnz     short loc_180003AD5
0x180003ac0  xor     r8d, r8d
0x180003ac3  mov     edx, r15d; int
0x180003ac6  test    r15b, r15b
0x180003ac9  mov     rcx, rsi; unsigned __int16 *
0x180003acc  cmovnz  r8, rbx; HWND
0x180003ad0  call    ?RemoveZoneIdentifier@@YAJPEBGHPEAUHWND__@@@Z; RemoveZoneIdentifier(ushort const *,int,HWND__ *)
0x180003ad5  mov     r12, [rsp+23F0h+var_30]
0x180003add  xor     eax, eax
0x180003adf  cmp     edi, 1
0x180003ae2  mov     ecx, 4C7h
0x180003ae7  cmovnz  eax, ecx
0x180003aea  jmp     short loc_180003B02
0x180003aec  mov     rcx, [rbp+22F8h]; this
0x180003af3  mov     r9d, eax; char *
0x180003af6  mov     edx, 6FDh; void *
0x180003afb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003b00  xor     eax, eax
0x180003b02  mov     rcx, [rbp+22F0h+var_50]
0x180003b09  xor     rcx, rsp; StackCookie
0x180003b0c  call    __security_check_cookie
0x180003b11  add     rsp, 23C8h
0x180003b18  pop     r15
0x180003b1a  pop     r14
0x180003b1c  pop     rdi
0x180003b1d  pop     rsi
0x180003b1e  pop     rbx
0x180003b1f  pop     rbp
0x180003b20  retn
```
