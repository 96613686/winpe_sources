# CVssAsrAPIBackup::_GetCriticalVolumesFromSelectedComponents(ulong,ushort const * const *,ushort * *)

- ea: `0x1400d2194`
- end: `0x1400d24e3`
- name: `?_GetCriticalVolumesFromSelectedComponents@CVssAsrAPIBackup@@AEAAHKPEBQEBGPEAPEAG@Z`
- size: `847`
- prototype: `__int64 __fastcall(CVssAsrAPIBackup *__hidden this, unsigned int, const unsigned __int16 *const *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x140079a50`

## callees

- `0x140021ca0`
- `0x1400235a8`
- `0x140025abc`
- `0x140025b00`
- `0x14003ade4`
- `0x14003b0c0`
- `0x14005b208`
- `0x140091560`
- `0x1400d2194`
- `0x1400d2554`
- `0x1400d257c`
- `0x1400d7878`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d24af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d24af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d2299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d22bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d2299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d22bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d249b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d249b`

## string_xrefs

- `0x1400d21d8`: `CVssAsrAPIBackup::_GetCriticalVolumesFromSelectedComponents`
- `0x1400d24a1`: `CVssAsrAPIBackup::_GetCriticalVolumesFromSelectedComponents`
- `0x1400d2373`: `::StringCchCopy(ARRAY_COUNT_PARAM(wszVolumeGuidName), L"\\??\\")`

## pseudocode

```c
__int64 __fastcall CVssAsrAPIBackup::_GetCriticalVolumesFromSelectedComponents(
        CVssAsrAPIBackup *this,
        unsigned int a2,
        const unsigned __int16 *const *a3,
        unsigned __int16 **a4)
{
  unsigned int v6; // r13d
  unsigned __int16 *v7; // rbx
  unsigned int v8; // r15d
  int v9; // eax
  int v10; // eax
  DWORD LastError; // esi
  DWORD v12; // eax
  int v13; // eax
  int v14; // edx
  const char *v15; // rcx
  struct _DRIVE_LAYOUT_INFORMATION_EX *v16; // rcx
  int v17; // edx
  const char *v18; // rax
  int v19; // r9d
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v22; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *const *v23; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v24[264]; // [rsp+50h] [rbp-B0h] BYREF

  v23 = a3;
  v6 = a2;
  v22 = a2;
  TraceFunctionEnter(L"CVssAsrAPIBackup::_GetCriticalVolumesFromSelectedComponents");
  v7 = 0;
  pv = 0;
  if ( a3 )
  {
    if ( a4 )
    {
      v8 = 1;
      while ( (unsigned int)v7 < v6 )
      {
        v9 = StringCchCopyW(v24, 0x104u, L"\\??\\");
        if ( v9 < 0 )
        {
          v8 = 0;
          LastError = WIN32_FROM_HRESULT((unsigned int)v9);
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v13 = StringCchCopyW(v24, 0x104u, L"\\??\\");
            v14 = 68;
            v15 = "::StringCchCopy(ARRAY_COUNT_PARAM(wszVolumeGuidName), L\"\\\\??\\\\\")";
LABEL_21:
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              v14,
              (unsigned int)WPP_f348c201c37c322fb5c01c43990311a7_Traceguids,
              v13,
              (__int64)v15);
          }
LABEL_22:
          v7 = (unsigned __int16 *)pv;
          goto LABEL_40;
        }
        v10 = StringCchCatW(v24, 0x104u, a3[(_QWORD)v7]);
        if ( v10 < 0 )
        {
          v8 = 0;
          LastError = WIN32_FROM_HRESULT((unsigned int)v10);
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v13 = StringCchCatW(v24, 0x104u, v23[(_QWORD)v7]);
            v14 = 69;
            v15 = "::StringCchCat(ARRAY_COUNT_PARAM(wszVolumeGuidName), rgpwszVolumes[i] )";
            goto LABEL_21;
          }
          goto LABEL_22;
        }
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
        {
          WPP_SF_S(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            70,
            WPP_f348c201c37c322fb5c01c43990311a7_Traceguids,
            v24);
        }
        if ( !MwszStringAppend((unsigned __int16 **)&pv, v24) )
        {
          v8 = 0;
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v12 = GetLastError();
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              71,
              (unsigned int)WPP_f348c201c37c322fb5c01c43990311a7_Traceguids,
              v12,
              (__int64)"MwszStringAppend(&pmwszCriticalVolumes, wszVolumeGuidName)");
          }
          goto LABEL_22;
        }
        v7 = (unsigned __int16 *)(unsigned int)((_DWORD)v7 + 1);
        v6 = v22;
      }
      v7 = (unsigned __int16 *)pv;
      if ( pv )
        goto LABEL_29;
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
      {
        WPP_SF_(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          (unsigned int)((_DWORD)pv + 72),
          WPP_f348c201c37c322fb5c01c43990311a7_Traceguids);
      }
      v7 = (unsigned __int16 *)ASR_ALLOC(4u);
      if ( v7 )
      {
        *(_DWORD *)v7 = 0;
LABEL_29:
        LastError = 0;
        *a4 = v7;
        v7 = 0;
        goto LABEL_40;
      }
      v8 = 0;
      LastError = 14;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v17 = 73;
        v18 = "pmwszCriticalVolumes";
        v19 = 14;
LABEL_39:
        WPP_SF_Ds(
          *(_QWORD *)v16->Gpt.DiskId.Data4,
          v17,
          (unsigned int)WPP_f348c201c37c322fb5c01c43990311a7_Traceguids,
          v19,
          (__int64)v18);
      }
    }
    else
    {
      v8 = 0;
      v19 = 87;
      LastError = 87;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v17 = 67;
        v18 = "ppmwszCriticalVolumesOut";
        goto LABEL_39;
      }
    }
  }
  else
  {
    v8 = 0;
    v19 = 87;
    LastError = 87;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v17 = 66;
      v18 = "rgpwszVolumes";
      goto LABEL_39;
    }
  }
LABEL_40:
  CoTaskMemFree(v7);
  TraceFunctionExit(L"CVssAsrAPIBackup::_GetCriticalVolumesFromSelectedComponents");
  SetLastError(LastError);
  return v8;
}

```

## disassembly

```asm
0x1400d2194  mov     [rsp-8+arg_0], rbx
0x1400d2199  mov     [rsp-8+arg_8], rsi
0x1400d219e  push    rbp
0x1400d219f  push    rdi
0x1400d21a0  push    r12
0x1400d21a2  push    r13
0x1400d21a4  push    r15
0x1400d21a6  lea     rbp, [rsp-170h]
0x1400d21ae  sub     rsp, 270h
0x1400d21b5  mov     rax, cs:__security_cookie
0x1400d21bc  xor     rax, rsp
0x1400d21bf  mov     [rbp+190h+var_30], rax
0x1400d21c6  mov     r12, r9
0x1400d21c9  mov     rsi, r8
0x1400d21cc  mov     [rsp+290h+var_250], r8
0x1400d21d1  mov     r13d, edx
0x1400d21d4  mov     [rsp+290h+var_258], edx
0x1400d21d8  lea     rcx, aCvssasrapiback_2; "CVssAsrAPIBackup::_GetCriticalVolumesFr"...
0x1400d21df  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x1400d21e4  xor     ebx, ebx
0x1400d21e6  mov     [rsp+290h+pv], rbx
0x1400d21eb  test    rsi, rsi
0x1400d21ee  jz      loc_1400D2455
0x1400d21f4  test    r12, r12
0x1400d21f7  jz      loc_1400D2425
0x1400d21fd  lea     rdi, WPP_GLOBAL_Control
0x1400d2204  lea     r15d, [rbx+1]
0x1400d2208  cmp     ebx, r13d
0x1400d220b  jnb     loc_1400D23A3
0x1400d2211  lea     r8, asc_140135168; "\\??\\"
0x1400d2218  mov     edx, 104h; unsigned __int64
0x1400d221d  lea     rcx, [rsp+290h+var_240]; unsigned __int16 *
0x1400d2222  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400d2227  test    eax, eax
0x1400d2229  js      loc_1400D233B
0x1400d222f  mov     r8, [rsi+rbx*8]; unsigned __int16 *
0x1400d2233  mov     edx, 104h; unsigned __int64
0x1400d2238  lea     rcx, [rsp+290h+var_240]; unsigned __int16 *
0x1400d223d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400d2242  test    eax, eax
0x1400d2244  js      loc_1400D22F0
0x1400d224a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d2251  cmp     rcx, rdi
0x1400d2254  jz      short loc_1400D2276
0x1400d2256  test    byte ptr [rcx+1Ch], 2
0x1400d225a  jz      short loc_1400D2276
0x1400d225c  mov     edx, 46h ; 'F'
0x1400d2261  lea     r9, [rsp+290h+var_240]
0x1400d2266  lea     r8, WPP_f348c201c37c322fb5c01c43990311a7_Traceguids
0x1400d226d  mov     rcx, [rcx+10h]
0x1400d2271  call    WPP_SF_S
0x1400d2276  lea     rdx, [rsp+290h+var_240]; unsigned __int16 *
0x1400d227b  lea     rcx, [rsp+290h+pv]; unsigned __int16 **
0x1400d2280  call    ?MwszStringAppend@@YAHPEAPEAGPEAG@Z; MwszStringAppend(ushort * *,ushort *)
0x1400d2285  test    eax, eax
0x1400d2287  jz      short loc_1400D2296
0x1400d2289  add     ebx, r15d
0x1400d228c  mov     r13d, [rsp+290h+var_258]
0x1400d2291  jmp     loc_1400D2208
0x1400d2296  xor     r15d, r15d
0x1400d2299  call    cs:__imp_GetLastError
0x1400d229f  mov     esi, eax
0x1400d22a1  mov     rax, cs:WPP_GLOBAL_Control
0x1400d22a8  cmp     rax, rdi
0x1400d22ab  jz      loc_1400D2399
0x1400d22b1  test    byte ptr [rax+1Ch], 8
0x1400d22b5  jz      loc_1400D2399
0x1400d22bb  call    cs:__imp_GetLastError
0x1400d22c1  lea     edx, [r15+47h]
0x1400d22c5  lea     rcx, aMwszstringappe_3; "MwszStringAppend(&pmwszCriticalVolumes,"...
0x1400d22cc  mov     [rsp+290h+var_270], rcx
0x1400d22d1  mov     r9d, eax
0x1400d22d4  lea     r8, WPP_f348c201c37c322fb5c01c43990311a7_Traceguids
0x1400d22db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d22e2  mov     rcx, [rcx+10h]
0x1400d22e6  call    WPP_SF_Ds
0x1400d22eb  jmp     loc_1400D2399
0x1400d22f0  xor     r15d, r15d
0x1400d22f3  mov     ecx, eax
0x1400d22f5  call    WIN32_FROM_HRESULT
0x1400d22fa  mov     esi, eax
0x1400d22fc  mov     rax, cs:WPP_GLOBAL_Control
0x1400d2303  cmp     rax, rdi
0x1400d2306  jz      loc_1400D2399
0x1400d230c  test    byte ptr [rax+1Ch], 8
0x1400d2310  jz      loc_1400D2399
0x1400d2316  mov     r8, [rsp+290h+var_250]
0x1400d231b  mov     r8, [r8+rbx*8]; unsigned __int16 *
0x1400d231f  mov     edx, 104h; unsigned __int64
0x1400d2324  lea     rcx, [rsp+290h+var_240]; unsigned __int16 *
0x1400d2329  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400d232e  lea     edx, [r15+45h]
0x1400d2332  lea     rcx, aStringcchcatAr_2; "::StringCchCat(ARRAY_COUNT_PARAM(wszVol"...
0x1400d2339  jmp     short loc_1400D237A
0x1400d233b  xor     r15d, r15d
0x1400d233e  mov     ecx, eax
0x1400d2340  call    WIN32_FROM_HRESULT
0x1400d2345  mov     esi, eax
0x1400d2347  mov     rax, cs:WPP_GLOBAL_Control
0x1400d234e  cmp     rax, rdi
0x1400d2351  jz      short loc_1400D2399
0x1400d2353  test    byte ptr [rax+1Ch], 8
0x1400d2357  jz      short loc_1400D2399
0x1400d2359  lea     r8, asc_140135168; "\\??\\"
0x1400d2360  mov     edx, 104h; unsigned __int64
0x1400d2365  lea     rcx, [rsp+290h+var_240]; unsigned __int16 *
0x1400d236a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400d236f  lea     edx, [r15+44h]
0x1400d2373  lea     rcx, aStringcchcopyA_0; "::StringCchCopy(ARRAY_COUNT_PARAM(wszVo"...
0x1400d237a  mov     [rsp+290h+var_270], rcx
0x1400d237f  mov     r9d, eax
0x1400d2382  lea     r8, WPP_f348c201c37c322fb5c01c43990311a7_Traceguids
0x1400d2389  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d2390  mov     rcx, [rcx+10h]
0x1400d2394  call    WPP_SF_Ds
0x1400d2399  mov     rbx, [rsp+290h+pv]
0x1400d239e  jmp     loc_1400D2498
0x1400d23a3  mov     rbx, [rsp+290h+pv]
0x1400d23a8  test    rbx, rbx
0x1400d23ab  jnz     short loc_1400D23E8
0x1400d23ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d23b4  cmp     rcx, rdi
0x1400d23b7  jz      short loc_1400D23D2
0x1400d23b9  test    byte ptr [rcx+1Ch], 2
0x1400d23bd  jz      short loc_1400D23D2
0x1400d23bf  lea     edx, [rbx+48h]
0x1400d23c2  lea     r8, WPP_f348c201c37c322fb5c01c43990311a7_Traceguids
0x1400d23c9  mov     rcx, [rcx+10h]
0x1400d23cd  call    WPP_SF_
0x1400d23d2  mov     ecx, 4; Size
0x1400d23d7  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x1400d23dc  mov     rbx, rax
0x1400d23df  test    rax, rax
0x1400d23e2  jz      short loc_1400D23F5
0x1400d23e4  xor     eax, eax
0x1400d23e6  mov     [rbx], eax
0x1400d23e8  xor     esi, esi
0x1400d23ea  mov     [r12], rbx
0x1400d23ee  xor     ebx, ebx
0x1400d23f0  jmp     loc_1400D2498
0x1400d23f5  xor     r15d, r15d
0x1400d23f8  lea     esi, [r15+0Eh]
0x1400d23fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d2403  cmp     rcx, rdi
0x1400d2406  jz      loc_1400D2498
0x1400d240c  test    byte ptr [rcx+1Ch], 8
0x1400d2410  jz      loc_1400D2498
0x1400d2416  lea     edx, [rsi+3Bh]
0x1400d2419  lea     rax, aPmwszcriticalv; "pmwszCriticalVolumes"
0x1400d2420  mov     r9d, esi
0x1400d2423  jmp     short loc_1400D2483
0x1400d2425  xor     r15d, r15d
0x1400d2428  lea     r9d, [r15+57h]
0x1400d242c  mov     esi, r9d
0x1400d242f  lea     rdi, WPP_GLOBAL_Control
0x1400d2436  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d243d  cmp     rcx, rdi
0x1400d2440  jz      short loc_1400D2498
0x1400d2442  test    byte ptr [rcx+1Ch], 8
0x1400d2446  jz      short loc_1400D2498
0x1400d2448  lea     edx, [r15+43h]
0x1400d244c  lea     rax, aPpmwszcritical_1; "ppmwszCriticalVolumesOut"
0x1400d2453  jmp     short loc_1400D2483
0x1400d2455  xor     r15d, r15d
0x1400d2458  lea     r9d, [r15+57h]
0x1400d245c  mov     esi, r9d
0x1400d245f  lea     rdi, WPP_GLOBAL_Control
0x1400d2466  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d246d  cmp     rcx, rdi
0x1400d2470  jz      short loc_1400D2498
0x1400d2472  test    byte ptr [rcx+1Ch], 8
0x1400d2476  jz      short loc_1400D2498
0x1400d2478  lea     edx, [r15+42h]
0x1400d247c  lea     rax, aRgpwszvolumes; "rgpwszVolumes"
0x1400d2483  mov     [rsp+290h+var_270], rax
0x1400d2488  lea     r8, WPP_f348c201c37c322fb5c01c43990311a7_Traceguids
0x1400d248f  mov     rcx, [rcx+10h]
0x1400d2493  call    WPP_SF_Ds
0x1400d2498  mov     rcx, rbx; pv
0x1400d249b  call    cs:__imp_CoTaskMemFree
0x1400d24a1  lea     rcx, aCvssasrapiback_2; "CVssAsrAPIBackup::_GetCriticalVolumesFr"...
0x1400d24a8  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x1400d24ad  mov     ecx, esi; dwErrCode
0x1400d24af  call    cs:__imp_SetLastError
0x1400d24b5  mov     eax, r15d
0x1400d24b8  mov     rcx, [rbp+190h+var_30]
0x1400d24bf  xor     rcx, rsp; StackCookie
0x1400d24c2  call    __security_check_cookie
0x1400d24c7  lea     r11, [rsp+290h+var_20]
0x1400d24cf  mov     rbx, [r11+30h]
0x1400d24d3  mov     rsi, [r11+38h]
0x1400d24d7  mov     rsp, r11
0x1400d24da  pop     r15
0x1400d24dc  pop     r13
0x1400d24de  pop     r12
0x1400d24e0  pop     rdi
0x1400d24e1  pop     rbp
0x1400d24e2  retn
```
