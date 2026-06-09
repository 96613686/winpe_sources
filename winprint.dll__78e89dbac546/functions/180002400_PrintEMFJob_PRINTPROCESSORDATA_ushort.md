# PrintEMFJob(_PRINTPROCESSORDATA *,ushort *)

- ea: `0x180002400`
- end: `0x180002ca1`
- name: `?PrintEMFJob@@YAHPEAU_PRINTPROCESSORDATA@@PEAG@Z`
- size: `2209`
- prototype: `__int64 __fastcall(struct _PRINTPROCESSORDATA *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800061f0`

## callees

- `0x180002400`
- `0x180002cb0`
- `0x180002eb0`
- `0x180003890`
- `0x1800044a0`
- `0x1800044c0`
- `0x1800045d0`
- `0x180004c80`
- `0x180006770`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bc0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002c41`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002c4f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002c41`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002c4f`
- `GDI32!GdiGetPageCount` at `0x180002768`
- `GDI32!GdiGetPageCount` at `0x180002ade`
- `GDI32!GdiGetPageCount` at `0x180002768`
- `GDI32!GdiGetPageCount` at `0x180002ade`
- `GDI32!GetWorldTransform` at `0x180002b71`
- `GDI32!GetWorldTransform` at `0x180002b71`
- `GDI32!GdiGetDevmodeForPage` at `0x1800026b8`
- `GDI32!GdiGetDevmodeForPage` at `0x1800026b8`
- `GDI32!SetGraphicsMode` at `0x180002b5c`
- `GDI32!SetGraphicsMode` at `0x180002b5c`
- `GDI32!GdiGetSpoolFileHandle` at `0x1800025de`
- `GDI32!GdiGetSpoolFileHandle` at `0x1800025de`
- `GDI32!GdiGetDC` at `0x1800025f7`
- `GDI32!GdiGetDC` at `0x1800025f7`
- `GDI32!GdiDeleteSpoolFileHandle` at `0x180002c5e`
- `GDI32!GdiDeleteSpoolFileHandle` at `0x180002c5e`
- `GDI32!SetWorldTransform` at `0x180002c2e`
- `GDI32!SetWorldTransform` at `0x180002c2e`
- `GDI32!GetDeviceCaps` at `0x180002623`
- `GDI32!GetDeviceCaps` at `0x18000263a`
- `GDI32!GetDeviceCaps` at `0x180002651`
- `GDI32!GetDeviceCaps` at `0x180002668`
- `GDI32!GetDeviceCaps` at `0x18000267f`
- `GDI32!GetDeviceCaps` at `0x180002696`
- `GDI32!GetDeviceCaps` at `0x180002623`
- `GDI32!GetDeviceCaps` at `0x18000263a`
- `GDI32!GetDeviceCaps` at `0x180002651`
- `GDI32!GetDeviceCaps` at `0x180002668`
- `GDI32!GetDeviceCaps` at `0x18000267f`
- `GDI32!GetDeviceCaps` at `0x180002696`
- `WINSPOOL!ClosePrinter` at `0x180002c0c`
- `WINSPOOL!ClosePrinter` at `0x180002c0c`
- `WINSPOOL!OpenPrinterW` at `0x1800027f0`
- `WINSPOOL!OpenPrinterW` at `0x1800027f0`
- `WINSPOOL!GetPrinterDataW` at `0x180002826`
- `WINSPOOL!GetPrinterDataW` at `0x180002826`

## pseudocode

```c
__int64 __fastcall PrintEMFJob(struct _PRINTPROCESSORDATA *a1, unsigned __int16 *a2)
{
  void *v3; // r14
  int v4; // eax
  LPDEVMODEW v5; // rdi
  LPWSTR *v6; // r15
  int v7; // r13d
  DWORD *p_dmFields; // rsi
  DWORD dmFields; // eax
  __int16 dmCollate; // cx
  __int16 dmCopies; // ax
  HANDLE v12; // rax
  HDC DC; // rax
  PDEVMODEW v14; // rcx
  unsigned int v15; // eax
  __int16 v16; // dx
  int v17; // eax
  int v18; // ecx
  BOOL v19; // r15d
  int v20; // r10d
  unsigned int v21; // esi
  DWORD dwDrvNumberOfPagesPerSide; // r9d
  DWORD dwJobNumberOfPagesPerSide; // ecx
  DWORD dwNupBorderFlags; // edx
  unsigned int v25; // eax
  int v26; // ecx
  int v27; // r12d
  int v28; // ecx
  int v29; // ecx
  int v30; // r8d
  PDEVMODEW v31; // r13
  void *v32; // rcx
  HDC hdc; // [rsp+40h] [rbp-178h]
  __int16 v35; // [rsp+48h] [rbp-170h]
  __int16 v36; // [rsp+4Ch] [rbp-16Ch]
  unsigned int v37; // [rsp+58h] [rbp-160h]
  PDEVMODEW pCurrDM; // [rsp+60h] [rbp-158h] BYREF
  DWORD dwErrCode; // [rsp+68h] [rbp-150h]
  unsigned int v40; // [rsp+6Ch] [rbp-14Ch]
  LPDEVMODEW pDevmode; // [rsp+70h] [rbp-148h] BYREF
  BYTE pData[4]; // [rsp+78h] [rbp-140h] BYREF
  int v43; // [rsp+7Ch] [rbp-13Ch]
  HANDLE SpoolFileHandle; // [rsp+80h] [rbp-138h]
  DWORD pcbNeeded; // [rsp+88h] [rbp-130h] BYREF
  DWORD PageCount; // [rsp+8Ch] [rbp-12Ch]
  struct _PAGE_NUMBER *v47; // [rsp+90h] [rbp-128h] BYREF
  HANDLE phPrinter; // [rsp+98h] [rbp-120h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp-118h] BYREF
  LPWSTR pwszDocName; // [rsp+A8h] [rbp-110h]
  struct _PRINTPROCESSORDATA *v51; // [rsp+B0h] [rbp-108h]
  struct _PRINTPROCESSORDATA *v52; // [rsp+B8h] [rbp-100h]
  char *v53; // [rsp+C0h] [rbp-F8h]
  DWORD *v54; // [rsp+C8h] [rbp-F0h]
  _ATTRIBUTE_INFO_4 v55; // [rsp+D0h] [rbp-E8h] BYREF
  __int128 v56; // [rsp+110h] [rbp-A8h] BYREF
  __int128 v57; // [rsp+120h] [rbp-98h]
  __int128 v58; // [rsp+130h] [rbp-88h]
  __int128 v59; // [rsp+140h] [rbp-78h]
  __int128 v60; // [rsp+150h] [rbp-68h]
  __int128 v61; // [rsp+160h] [rbp-58h]
  struct tagXFORM xf; // [rsp+170h] [rbp-48h] BYREF

  pwszDocName = a2;
  v51 = a1;
  v52 = a1;
  v3 = 0;
  SpoolFileHandle = 0;
  dwErrCode = 0;
  hdc = 0;
  v40 = 0;
  v43 = 1;
  memset(&xf, 0, sizeof(xf));
  hMem = 0;
  v47 = 0;
  memset(&v55, 0, sizeof(v55));
  pDevmode = 0;
  pCurrDM = 0;
  *(_DWORD *)pData = 0;
  pcbNeeded = 0;
  phPrinter = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  HIDWORD(v57) = -1;
  LODWORD(v56) = 828796261;
  v4 = CopyDevmode(a1, &pDevmode);
  v5 = pDevmode;
  if ( !v4 )
    goto LABEL_107;
  if ( !pDevmode )
    goto LABEL_107;
  if ( pDevmode->dmSize < 0x62u )
    goto LABEL_107;
  v6 = (LPWSTR *)((char *)a1 + 48);
  v53 = (char *)a1 + 48;
  if ( !(unsigned int)PrintProcGetJobAttributesEx(*((LPWSTR *)a1 + 6), pDevmode, &v55) )
    goto LABEL_107;
  v7 = 0;
  if ( v55.dwColorOptimization && (v5->dmPrintQuality != v55.dmPrintQuality || v5->dmYResolution != v55.dmYResolution) )
  {
    v5->dmPrintQuality = v55.dmPrintQuality;
    v5->dmYResolution = v55.dmYResolution;
    v7 = 1;
  }
  p_dmFields = &v5->dmFields;
  v54 = &v5->dmFields;
  dmFields = v5->dmFields;
  if ( (dmFields & 0x8000) != 0 )
    dmCollate = v5->dmCollate;
  else
    dmCollate = 0;
  v35 = dmCollate;
  if ( (dmFields & 0x100) != 0 )
    dmCopies = v5->dmCopies;
  else
    dmCopies = 0;
  v36 = dmCopies;
  v12 = GdiGetSpoolFileHandle(*v6, v5, pwszDocName);
  v3 = v12;
  SpoolFileHandle = v12;
  if ( v12 )
  {
    DC = GdiGetDC(v12);
    hdc = DC;
  }
  else
  {
    DC = 0;
  }
  if ( DC && v3 )
  {
    DWORD1(v56) = GetDeviceCaps(DC, 88);
    DWORD2(v56) = GetDeviceCaps(hdc, 90);
    DWORD1(v57) = GetDeviceCaps(hdc, 118);
    DWORD2(v57) = GetDeviceCaps(hdc, 117);
    HIDWORD(v56) = GetDeviceCaps(hdc, 110);
    LODWORD(v57) = GetDeviceCaps(hdc, 111);
    pCurrDM = 0;
    if ( GdiGetDevmodeForPage(v3, 1u, &pCurrDM, 0) && pCurrDM && (unsigned int)BIsDevmodeOfLeastAcceptableSize(pCurrDM) )
    {
      if ( (v14->dmFields & 0x100) != 0 )
      {
        *p_dmFields |= 0x100u;
        v5->dmCopies = pCurrDM->dmCopies;
        v14 = pCurrDM;
      }
      if ( (v14->dmFields & 0x8000) != 0 && v5->dmSize >= 0x66u )
      {
        *p_dmFields |= 0x8000u;
        v5->dmCollate = pCurrDM->dmCollate;
      }
    }
    if ( (*p_dmFields & 0x100) != 0 )
      v15 = *((_DWORD *)a1 + 23) * v5->dmCopies;
    else
      v15 = *((_DWORD *)a1 + 23);
    pwszDocName = (LPWSTR)&v5->dmCopies;
    v5->dmCopies = v15;
    *p_dmFields |= 0x100u;
    if ( (*p_dmFields & 0x8000) == 0 || v5->dmCollate != 1 )
      goto LABEL_44;
    if ( v15 <= 1 )
    {
      if ( v55.dwDrvNumberOfPagesPerSide <= 1 )
      {
        v16 = v35;
        if ( v35 == 1 )
          goto LABEL_45;
      }
    }
    else
    {
      PageCount = GdiGetPageCount(v3);
      if ( PageCount > v55.dwDrvNumberOfPagesPerSide )
      {
LABEL_44:
        v16 = v35;
LABEL_45:
        if ( (v7 || v5->dmCopies != v36 || (*p_dmFields & 0x8000) != 0 && v5->dmCollate != v16)
          && !(unsigned int)PrintProcGetJobAttributesEx(*v6, v5, &v55) )
        {
          goto LABEL_107;
        }
        v17 = v55.dwJobPageOrderFlags & 2;
        v18 = v55.dwDrvPageOrderFlags & 2;
        v19 = v17 != v18;
        DWORD1(v61) = (*p_dmFields & 0x8000) != 0 && v5->dmCollate == 1;
        if ( (*p_dmFields & 0x1000) == 0 || (v20 = 1, v5->dmDuplex == 1) )
          v20 = 0;
        if ( !v55.dwJobNumberOfCopies )
        {
          v40 = 1;
LABEL_107:
          DC = hdc;
          goto LABEL_108;
        }
        v21 = 0;
        if ( v20 )
        {
          LOBYTE(v21) = v5->dmDuplex == 3;
          ++v21;
        }
        if ( v17 == v18 )
        {
          dwJobNumberOfPagesPerSide = v55.dwJobNumberOfPagesPerSide;
          dwDrvNumberOfPagesPerSide = v55.dwDrvNumberOfPagesPerSide;
        }
        else
        {
          dwDrvNumberOfPagesPerSide = 1;
          if ( v20 )
          {
            dwJobNumberOfPagesPerSide = 2;
          }
          else
          {
            v19 = 0;
            dwJobNumberOfPagesPerSide = 1;
          }
        }
        if ( dwDrvNumberOfPagesPerSide == 1 )
        {
          dwNupBorderFlags = v55.dwNupBorderFlags;
          v25 = dwJobNumberOfPagesPerSide;
          if ( dwJobNumberOfPagesPerSide != 1 )
            goto LABEL_71;
        }
        else
        {
          v25 = 1;
        }
        dwNupBorderFlags = 1;
LABEL_71:
        if ( v55.dwColorOptimization != 1 || v20 || (v37 = 1, dwJobNumberOfPagesPerSide != 1) )
          v37 = 0;
        if ( v25 > 0x10 )
          goto LABEL_107;
        v26 = 66134;
        if ( !_bittest(&v26, v25) )
          goto LABEL_107;
        v27 = (LOBYTE(v55.dwJobPageOrderFlags) ^ LOBYTE(v55.dwDrvPageOrderFlags)) & 1;
        v28 = 0;
        if ( !v19 )
        {
          switch ( v55.dwNupDirection )
          {
            case 2u:
              v28 = 1;
              break;
            case 4u:
              v28 = 2;
              break;
            case 8u:
              v28 = 3;
              break;
          }
        }
        HIDWORD(v59) = v28;
        v29 = 0;
        if ( v19 )
        {
          if ( !v55.dwBookletFlags || (v29 = 2, v55.dwBookletFlags != 1) )
            v29 = 1;
        }
        LODWORD(v60) = v29;
        HIDWORD(v60) = v19;
        DWORD2(v60) = (LOBYTE(v55.dwJobPageOrderFlags) ^ LOBYTE(v55.dwDrvPageOrderFlags)) & 1;
        *((_QWORD *)&v58 + 1) = __PAIR64__(v55.dwJobNumberOfCopies, dwNupBorderFlags);
        *(_QWORD *)&v58 = __PAIR64__(dwDrvNumberOfPagesPerSide, v25);
        *(_QWORD *)&v59 = __PAIR64__(v21, v55.dwDrvNumberOfCopies);
        *((float *)&v61 + 2) = (float)(int)EnsureProperValuesForScalingPercent(v55.dwScalingPercentX) / 100.0;
        *((float *)&v61 + 3) = (float)(int)EnsureProperValuesForScalingPercent(v55.dwScalingPercentY) / 100.0;
        if ( (v55.dwDuplexFlags & 1) != 0 )
          v30 = 0;
        LODWORD(v61) = v30;
        if ( (v55.dwDuplexFlags & 2) != 0 )
          DWORD2(v59) |= 2u;
        v31 = v5;
        if ( pCurrDM )
          v31 = pCurrDM;
        v31->dmPrintQuality = v5->dmPrintQuality;
        v31->dmYResolution = v5->dmYResolution;
        if ( v27 || v19 )
        {
          PageCount = GdiGetPageCount(v3);
          HIDWORD(v57) = PageCount;
          if ( v19 )
          {
            if ( !(unsigned int)GetStartPageListBooklet(
                                  (struct _EMF_ATTRIBUTE_INFO *)&v56,
                                  (struct _PAGE_NUMBER **)&hMem,
                                  &v47) )
              goto LABEL_107;
          }
          else if ( v27
                 && !(unsigned int)GetStartPageListReverseOrder(
                                     v32,
                                     (struct _EMF_ATTRIBUTE_INFO *)&v56,
                                     v31,
                                     (struct _PAGE_NUMBER **)&hMem,
                                     &v47) )
          {
            goto LABEL_107;
          }
        }
        if ( SetGraphicsMode(hdc, 2) && GetWorldTransform(hdc, &xf) )
        {
          v40 = BPrintEMFJobNow(v3, hdc, (struct _EMF_ATTRIBUTE_INFO *)&v56, v37, v31, v47, v51);
          if ( v40 )
            dwErrCode = 0;
          else
            dwErrCode = GetLastError();
        }
        else
        {
          v43 = 0;
        }
        goto LABEL_107;
      }
    }
    if ( !OpenPrinterW(*v6, &phPrinter, 0)
      || GetPrinterDataW(phPrinter, (LPWSTR)L"SinglePageKeepCollate", 0, pData, 4u, &pcbNeeded)
      || *(_DWORD *)pData != 1 )
    {
      v5->dmCollate = 0;
      if ( pCurrDM )
      {
        if ( pCurrDM->dmSize >= 0x66u )
          pCurrDM->dmCollate = 0;
      }
    }
    goto LABEL_44;
  }
LABEL_108:
  if ( phPrinter )
  {
    ClosePrinter(phPrinter);
    DC = hdc;
  }
  if ( v43 && DC )
    SetWorldTransform(DC, &xf);
  if ( hMem )
    LocalFree(hMem);
  if ( v5 )
    LocalFree(v5);
  if ( v3 )
    GdiDeleteSpoolFileHandle(v3);
  SetLastError(dwErrCode);
  return v40;
}

```

## disassembly

```asm
0x180002400  mov     r11, rsp
0x180002403  mov     [r11+18h], rbx
0x180002407  mov     [r11+20h], rsi
0x18000240b  push    rdi
0x18000240c  push    r12
0x18000240e  push    r13
0x180002410  push    r14
0x180002412  push    r15
0x180002414  sub     rsp, 190h
0x18000241b  mov     rax, cs:__security_cookie
0x180002422  xor     rax, rsp
0x180002425  mov     [rsp+1B8h+var_30], rax
0x18000242d  mov     [rsp+1B8h+pwszDocName], rdx
0x180002435  mov     r12, rcx
0x180002438  mov     [rsp+1B8h+var_108], rcx
0x180002440  mov     [rsp+1B8h+var_100], rcx
0x180002448  xor     ebx, ebx
0x18000244a  mov     r14d, ebx
0x18000244d  mov     [r11-138h], rbx
0x180002454  mov     [rsp+1B8h+dwErrCode], ebx
0x180002458  mov     [rsp+1B8h+hdc], rbx
0x18000245d  mov     [rsp+1B8h+var_14C], ebx
0x180002461  mov     esi, 1
0x180002466  mov     [rsp+1B8h+var_13C], esi
0x18000246a  xorps   xmm0, xmm0
0x18000246d  xor     eax, eax
0x18000246f  movups  xmmword ptr [r11-48h], xmm0
0x180002474  mov     [r11-38h], rax
0x180002478  mov     [r11-118h], rbx
0x18000247f  mov     [r11-128h], rbx
0x180002486  movups  xmmword ptr [rsp+1B8h+var_E8.dwJobNumberOfPagesPerSide], xmm0
0x18000248e  movups  xmmword ptr [rsp+1B8h+var_E8.dwDrvPageOrderFlags], xmm0
0x180002496  movups  xmmword ptr [rsp+1B8h+var_E8.dmPrintQuality], xmm0
0x18000249e  mov     [r11-0B8h], rax
0x1800024a5  mov     [rsp+1B8h+pDevmode], rbx
0x1800024aa  mov     [rsp+1B8h+pCurrDM], rbx
0x1800024af  mov     dword ptr [rsp+1B8h+pData], ebx
0x1800024b3  mov     [rsp+1B8h+var_130], ebx
0x1800024ba  mov     [r11-120h], rbx
0x1800024c1  movups  [rsp+1B8h+var_A8], xmm0
0x1800024c9  movups  [rsp+1B8h+var_98], xmm0
0x1800024d1  movups  [rsp+1B8h+var_88], xmm0
0x1800024d9  movups  xmmword ptr [r11-78h], xmm0
0x1800024de  movups  xmmword ptr [r11-68h], xmm0
0x1800024e3  movups  xmmword ptr [r11-58h], xmm0
0x1800024e8  mov     dword ptr [rsp+1B8h+var_98+0Ch], 0FFFFFFFFh
0x1800024f3  mov     dword ptr [rsp+1B8h+var_A8], 31666D65h
0x1800024fe  lea     rdx, [rsp+1B8h+pDevmode]; struct _devicemodeW **
0x180002503  call    ?CopyDevmode@@YAHPEAU_PRINTPROCESSORDATA@@PEAPEAU_devicemodeW@@@Z; CopyDevmode(_PRINTPROCESSORDATA *,_devicemodeW * *)
0x180002508  mov     rdi, [rsp+1B8h+pDevmode]
0x18000250d  test    eax, eax
0x18000250f  jz      loc_180002BFA
0x180002515  test    rdi, rdi
0x180002518  jz      loc_180002BFA
0x18000251e  cmp     word ptr [rdi+44h], 62h ; 'b'
0x180002523  jb      loc_180002BFA
0x180002529  lea     r15, [r12+30h]
0x18000252e  mov     [rsp+1B8h+var_F8], r15
0x180002536  lea     r8, [rsp+1B8h+var_E8]; struct _ATTRIBUTE_INFO_4 *
0x18000253e  mov     rdx, rdi; struct _devicemodeW *
0x180002541  mov     rcx, [r15]; pPrinterName
0x180002544  call    ?PrintProcGetJobAttributesEx@@YAHPEBGPEAU_devicemodeW@@PEAU_ATTRIBUTE_INFO_4@@@Z; PrintProcGetJobAttributesEx(ushort const *,_devicemodeW *,_ATTRIBUTE_INFO_4 *)
0x180002549  test    eax, eax
0x18000254b  jz      loc_180002BFA
0x180002551  mov     r13d, ebx
0x180002554  mov     [rsp+1B8h+var_160], ebx
0x180002558  cmp     [rsp+1B8h+var_E8.dwColorOptimization], ebx
0x18000255f  jz      short loc_180002594
0x180002561  movzx   ecx, [rsp+1B8h+var_E8.dmPrintQuality]
0x180002569  cmp     [rdi+5Ah], cx
0x18000256d  jnz     short loc_18000257D
0x18000256f  movzx   eax, [rsp+1B8h+var_E8.dmYResolution]
0x180002577  cmp     [rdi+60h], ax
0x18000257b  jz      short loc_180002594
0x18000257d  mov     [rdi+5Ah], cx
0x180002581  movzx   eax, [rsp+1B8h+var_E8.dmYResolution]
0x180002589  mov     [rdi+60h], ax
0x18000258d  mov     r13d, esi
0x180002590  mov     [rsp+1B8h+var_160], esi
0x180002594  lea     rsi, [rdi+48h]
0x180002598  mov     [rsp+1B8h+var_F0], rsi
0x1800025a0  mov     eax, [rsi]
0x1800025a2  bt      eax, 0Fh
0x1800025a6  jnb     short loc_1800025AE
0x1800025a8  movzx   ecx, word ptr [rdi+64h]
0x1800025ac  jmp     short loc_1800025B0
0x1800025ae  mov     ecx, ebx
0x1800025b0  mov     [rsp+1B8h+var_168], cx
0x1800025b5  mov     [rsp+1B8h+var_170], ecx
0x1800025b9  bt      eax, 8
0x1800025bd  jnb     short loc_1800025C5
0x1800025bf  movzx   eax, word ptr [rdi+56h]
0x1800025c3  jmp     short loc_1800025C7
0x1800025c5  mov     eax, ebx
0x1800025c7  mov     [rsp+1B8h+var_164], ax
0x1800025cc  mov     [rsp+1B8h+var_16C], eax
0x1800025d0  mov     r8, [rsp+1B8h+pwszDocName]; pwszDocName
0x1800025d8  mov     rdx, rdi; pDevmode
0x1800025db  mov     rcx, [r15]; pwszPrinterName
0x1800025de  call    cs:__imp_GdiGetSpoolFileHandle
0x1800025e4  mov     r14, rax
0x1800025e7  mov     [rsp+1B8h+SpoolFileHandle], rax
0x1800025ef  test    rax, rax
0x1800025f2  jz      short loc_180002604
0x1800025f4  mov     rcx, rax; SpoolFileHandle
0x1800025f7  call    cs:__imp_GdiGetDC
0x1800025fd  mov     [rsp+1B8h+hdc], rax
0x180002602  jmp     short loc_180002609
0x180002604  mov     rax, [rsp+1B8h+hdc]
0x180002609  test    rax, rax
0x18000260c  jz      loc_180002BFF
0x180002612  test    r14, r14
0x180002615  jz      loc_180002BFF
0x18000261b  mov     edx, 58h ; 'X'; index
0x180002620  mov     rcx, rax; hdc
0x180002623  call    cs:__imp_GetDeviceCaps
0x180002629  mov     dword ptr [rsp+1B8h+var_A8+4], eax
0x180002630  mov     edx, 5Ah ; 'Z'; index
0x180002635  mov     rcx, [rsp+1B8h+hdc]; hdc
0x18000263a  call    cs:__imp_GetDeviceCaps
0x180002640  mov     dword ptr [rsp+1B8h+var_A8+8], eax
0x180002647  mov     edx, 76h ; 'v'; index
0x18000264c  mov     rcx, [rsp+1B8h+hdc]; hdc
0x180002651  call    cs:__imp_GetDeviceCaps
0x180002657  mov     dword ptr [rsp+1B8h+var_98+4], eax
0x18000265e  mov     edx, 75h ; 'u'; index
0x180002663  mov     rcx, [rsp+1B8h+hdc]; hdc
0x180002668  call    cs:__imp_GetDeviceCaps
0x18000266e  mov     dword ptr [rsp+1B8h+var_98+8], eax
0x180002675  mov     edx, 6Eh ; 'n'; index
0x18000267a  mov     rcx, [rsp+1B8h+hdc]; hdc
0x18000267f  call    cs:__imp_GetDeviceCaps
0x180002685  mov     dword ptr [rsp+1B8h+var_A8+0Ch], eax
0x18000268c  mov     edx, 6Fh ; 'o'; index
0x180002691  mov     rcx, [rsp+1B8h+hdc]; hdc
0x180002696  call    cs:__imp_GetDeviceCaps
0x18000269c  mov     dword ptr [rsp+1B8h+var_98], eax
0x1800026a3  mov     [rsp+1B8h+pCurrDM], rbx
0x1800026a8  xor     r9d, r9d; pLastDM
0x1800026ab  lea     r8, [rsp+1B8h+pCurrDM]; pCurrDM
0x1800026b0  mov     edx, 1; dwPageNumber
0x1800026b5  mov     rcx, r14; SpoolFileHandle
0x1800026b8  call    cs:__imp_GdiGetDevmodeForPage
0x1800026be  test    eax, eax
0x1800026c0  jz      short loc_180002719
0x1800026c2  mov     rcx, [rsp+1B8h+pCurrDM]; struct _devicemodeW *
0x1800026c7  test    rcx, rcx
0x1800026ca  jz      short loc_180002719
0x1800026cc  call    ?BIsDevmodeOfLeastAcceptableSize@@YAHPEAU_devicemodeW@@@Z; BIsDevmodeOfLeastAcceptableSize(_devicemodeW *)
0x1800026d1  test    eax, eax
0x1800026d3  jz      short loc_180002719
0x1800026d5  test    dword ptr [rcx+48h], 100h
0x1800026dc  jz      short loc_1800026F6
0x1800026de  or      dword ptr [rsi], 100h
0x1800026e4  mov     rax, [rsp+1B8h+pCurrDM]
0x1800026e9  movzx   ecx, word ptr [rax+56h]
0x1800026ed  mov     [rdi+56h], cx
0x1800026f1  mov     rcx, [rsp+1B8h+pCurrDM]
0x1800026f6  test    dword ptr [rcx+48h], 8000h
0x1800026fd  jz      short loc_180002719
0x1800026ff  cmp     word ptr [rdi+44h], 66h ; 'f'
0x180002704  jb      short loc_180002719
0x180002706  or      dword ptr [rsi], 8000h
0x18000270c  mov     rax, [rsp+1B8h+pCurrDM]
0x180002711  movzx   ecx, word ptr [rax+64h]
0x180002715  mov     [rdi+64h], cx
0x180002719  test    dword ptr [rsi], 100h
0x18000271f  jz      short loc_18000272D
0x180002721  movsx   eax, word ptr [rdi+56h]
0x180002725  imul    eax, [r12+5Ch]
0x18000272b  jmp     short loc_180002732
0x18000272d  mov     eax, [r12+5Ch]
0x180002732  lea     r12, [rdi+56h]
0x180002736  mov     [rsp+1B8h+pwszDocName], r12
0x18000273e  mov     [r12], ax
0x180002743  or      dword ptr [rsi], 100h
0x180002749  test    dword ptr [rsi], 8000h
0x18000274f  jz      loc_180002850
0x180002755  cmp     word ptr [rdi+64h], 1
0x18000275a  jnz     loc_180002850
0x180002760  cmp     eax, 1
0x180002763  jbe     short loc_1800027CE
0x180002765  mov     rcx, r14; SpoolFileHandle
0x180002768  call    cs:__imp_GdiGetPageCount
0x18000276e  mov     [rsp+1B8h+var_12C], eax
0x180002775  cmp     eax, [rsp+1B8h+var_E8.dwDrvNumberOfPagesPerSide]
0x18000277c  jbe     short loc_1800027E2
0x18000277e  jmp     loc_180002850
0x180002783  xor     ebx, ebx
0x180002785  mov     r14, [rsp+1B8h+SpoolFileHandle]
0x18000278d  mov     r13d, [rsp+1B8h+var_160]
0x180002792  movzx   edx, [rsp+1B8h+var_168]
0x180002797  movzx   ecx, [rsp+1B8h+var_164]
0x18000279c  mov     rdi, [rsp+1B8h+pDevmode]
0x1800027a1  mov     rax, [rsp+1B8h+var_100]
0x1800027a9  mov     [rsp+1B8h+var_108], rax
0x1800027b1  mov     r15, [rsp+1B8h+var_F8]
0x1800027b9  mov     rsi, [rsp+1B8h+var_F0]
0x1800027c1  mov     r12, [rsp+1B8h+pwszDocName]
0x1800027c9  jmp     loc_180002858
0x1800027ce  cmp     [rsp+1B8h+var_E8.dwDrvNumberOfPagesPerSide], 1
0x1800027d6  ja      short loc_1800027E2
0x1800027d8  mov     edx, [rsp+1B8h+var_170]
0x1800027dc  cmp     dx, 1
0x1800027e0  jz      short loc_180002854
0x1800027e2  xor     r8d, r8d; pDefault
0x1800027e5  lea     rdx, [rsp+1B8h+phPrinter]; phPrinter
0x1800027ed  mov     rcx, [r15]; pPrinterName
0x1800027f0  call    cs:__imp_OpenPrinterW
0x1800027f6  test    eax, eax
0x1800027f8  jz      short loc_180002837
0x1800027fa  lea     rax, [rsp+1B8h+var_130]
0x180002802  mov     [rsp+1B8h+pcbNeeded], rax; pcbNeeded
0x180002807  mov     [rsp+1B8h+nSize], 4; nSize
0x18000280f  lea     r9, [rsp+1B8h+pData]; pData
0x180002814  xor     r8d, r8d; pType
0x180002817  lea     rdx, pValueName; "SinglePageKeepCollate"
0x18000281e  mov     rcx, [rsp+1B8h+phPrinter]; hPrinter
0x180002826  call    cs:__imp_GetPrinterDataW
0x18000282c  test    eax, eax
0x18000282e  jnz     short loc_180002837
0x180002830  cmp     dword ptr [rsp+1B8h+pData], 1
0x180002835  jz      short loc_180002850
0x180002837  mov     [rdi+64h], bx
0x18000283b  mov     rax, [rsp+1B8h+pCurrDM]
0x180002840  test    rax, rax
0x180002843  jz      short loc_180002850
0x180002845  cmp     word ptr [rax+44h], 66h ; 'f'
0x18000284a  jb      short loc_180002850
0x18000284c  mov     [rax+64h], bx
0x180002850  mov     edx, [rsp+1B8h+var_170]
0x180002854  mov     ecx, [rsp+1B8h+var_16C]
0x180002858  test    r13d, r13d
0x18000285b  jnz     short loc_180002872
0x18000285d  cmp     [r12], cx
0x180002862  jnz     short loc_180002872
0x180002864  test    dword ptr [rsi], 8000h
0x18000286a  jz      short loc_18000288D
0x18000286c  cmp     [rdi+64h], dx
0x180002870  jz      short loc_18000288D
0x180002872  lea     r8, [rsp+1B8h+var_E8]; struct _ATTRIBUTE_INFO_4 *
0x18000287a  mov     rdx, rdi; struct _devicemodeW *
0x18000287d  mov     rcx, [r15]; pPrinterName
0x180002880  call    ?PrintProcGetJobAttributesEx@@YAHPEBGPEAU_devicemodeW@@PEAU_ATTRIBUTE_INFO_4@@@Z; PrintProcGetJobAttributesEx(ushort const *,_devicemodeW *,_ATTRIBUTE_INFO_4 *)
0x180002885  test    eax, eax
0x180002887  jz      loc_180002BFA
0x18000288d  mov     r13d, [rsp+1B8h+var_E8.dwJobNumberOfCopies]
0x180002895  mov     r11d, [rsp+1B8h+var_E8.dwJobPageOrderFlags]
0x18000289d  mov     eax, r11d
0x1800028a0  and     eax, 2
0x1800028a3  mov     r12d, [rsp+1B8h+var_E8.dwDrvPageOrderFlags]
0x1800028ab  mov     ecx, r12d
0x1800028ae  and     ecx, 2
0x1800028b1  mov     r15d, ebx
0x1800028b4  cmp     eax, ecx
0x1800028b6  setnz   r15b
0x1800028ba  test    dword ptr [rsi], 8000h
0x1800028c0  jz      short loc_1800028D9
0x1800028c2  cmp     word ptr [rdi+64h], 1
0x1800028c7  jnz     short loc_1800028D9
0x1800028c9  mov     r8d, 1
0x1800028cf  mov     [rsp+1B8h+var_54], r8d
0x1800028d7  jmp     short loc_1800028E6
0x1800028d9  mov     [rsp+1B8h+var_54], ebx
0x1800028e0  mov     r8d, 1
0x1800028e6  test    dword ptr [rsi], 1000h
0x1800028ec  jz      short loc_1800028F8
0x1800028ee  cmp     word ptr [rdi+5Eh], 1
0x1800028f3  mov     r10d, r8d
0x1800028f6  jnz     short loc_1800028FB
0x1800028f8  mov     r10d, ebx
0x1800028fb  test    r13d, r13d
0x1800028fe  jnz     short loc_18000290A
0x180002900  mov     [rsp+1B8h+var_14C], r8d
0x180002905  jmp     loc_180002BFA
0x18000290a  mov     esi, ebx
0x18000290c  test    r10d, r10d
0x18000290f  jz      short loc_18000291C
0x180002911  cmp     word ptr [rdi+5Eh], 3
0x180002916  setz    sil
0x18000291a  inc     esi
0x18000291c  cmp     eax, ecx
0x18000291e  jz      short loc_180002937
0x180002920  mov     r9d, r8d
0x180002923  test    r10d, r10d
0x180002926  jnz     short loc_180002930
0x180002928  mov     r15d, ebx
0x18000292b  mov     ecx, r8d
0x18000292e  jmp     short loc_180002946
0x180002930  mov     ecx, 2
0x180002935  jmp     short loc_180002946
0x180002937  mov     ecx, [rsp+1B8h+var_E8.dwJobNumberOfPagesPerSide]
0x18000293e  mov     r9d, [rsp+1B8h+var_E8.dwDrvNumberOfPagesPerSide]
0x180002946  cmp     r9d, 1
0x18000294a  jnz     short loc_18000295C
0x18000294c  mov     edx, [rsp+1B8h+var_E8.dwNupBorderFlags]
0x180002953  mov     eax, ecx
0x180002955  cmp     ecx, r9d
0x180002958  jz      short loc_18000295F
0x18000295a  jmp     short loc_180002962
  ... truncated ...
```
