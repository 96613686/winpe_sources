# BuildDevnodeProperties(_PRINTER_INFO_2W *,uchar *,ulong,_DEVPROPERTY * *,ulong *,_DEVPROPERTY * *,ulong *)

- ea: `0x1800114cc`
- end: `0x180011b8e`
- name: `?BuildDevnodeProperties@@YAJPEAU_PRINTER_INFO_2W@@PEAEKPEAPEAU_DEVPROPERTY@@PEAK23@Z`
- size: `1730`
- prototype: `__int64 __fastcall(struct _PRINTER_INFO_2W *, unsigned __int8 *, unsigned int, struct _DEVPROPERTY **, unsigned int *, struct _DEVPROPERTY **, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800048b4`
- `0x1800111f0`

## callees

- `0x180001b50`
- `0x180001ba0`
- `0x1800114cc`
- `0x1800141a4`
- `0x180014360`
- `0x180014854`

## string_xrefs

- `0x1800116be`: `PrintFax.Printer.Service`

## pseudocode

```c
__int64 __fastcall BuildDevnodeProperties(
        struct _PRINTER_INFO_2W *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        struct _DEVPROPERTY **a4,
        unsigned int *a5,
        struct _DEVPROPERTY **a6,
        unsigned int *a7)
{
  unsigned int *v10; // rcx
  int v11; // ebx
  unsigned int *v12; // rcx
  unsigned int v13; // r15d
  LPWSTR *p_pPrinterName; // rsi
  struct _DEVPROPERTY *v15; // r13
  __int64 v16; // rdi
  struct _DEVPROPERTY *v17; // r12
  LPWSTR v18; // rax
  unsigned int v19; // esi
  void *v20; // rdx
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // rcx
  int v22; // eax
  DWORD Attributes; // r8d
  const wchar_t *v24; // rcx
  int v25; // eax
  const wchar_t *v26; // rax
  int v27; // r8d
  bool v28; // zf
  int v30; // eax
  void *v31; // rcx
  __int64 v32; // rdx
  DEVPROPGUID v33; // xmm0
  int v34; // eax
  __int64 v35; // rcx
  void *v36; // rax
  struct _DEVPROPERTY **v37; // rsi
  unsigned int *v38; // rax
  DEVPROPGUID v39; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v40; // [rsp+38h] [rbp-D0h]
  void *v41; // [rsp+40h] [rbp-C8h]
  void *v42; // [rsp+48h] [rbp-C0h]
  GUID v43; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+68h] [rbp-A0h]
  _QWORD v45[3]; // [rsp+70h] [rbp-98h]
  int v46; // [rsp+88h] [rbp-80h]
  int v47; // [rsp+8Ch] [rbp-7Ch]
  LPWSTR v48; // [rsp+90h] [rbp-78h]
  __int128 v49; // [rsp+98h] [rbp-70h]
  int v50; // [rsp+A8h] [rbp-60h]
  int v51; // [rsp+ACh] [rbp-5Ch]
  int v52; // [rsp+B0h] [rbp-58h]
  DEVPROPGUID fmtid; // [rsp+B8h] [rbp-50h] BYREF
  DEVPROPID pid; // [rsp+C8h] [rbp-40h]
  int v55; // [rsp+CCh] [rbp-3Ch]
  LPWSTR pPrinterName; // [rsp+D0h] [rbp-38h]
  DEVPROPKEY v57; // [rsp+D8h] [rbp-30h]
  int v58; // [rsp+ECh] [rbp-1Ch]
  int v59; // [rsp+F0h] [rbp-18h]
  GUID v60; // [rsp+F8h] [rbp-10h]
  int v61; // [rsp+108h] [rbp+0h]
  int v62; // [rsp+10Ch] [rbp+4h]
  BOOL v63; // [rsp+110h] [rbp+8h]
  GUID v64; // [rsp+118h] [rbp+10h]
  int v65; // [rsp+128h] [rbp+20h]
  int v66; // [rsp+12Ch] [rbp+24h]
  int v67; // [rsp+130h] [rbp+28h]
  DEVPROPGUID v68; // [rsp+138h] [rbp+30h]
  DEVPROPID v69; // [rsp+148h] [rbp+40h]
  int v70; // [rsp+14Ch] [rbp+44h]
  int v71; // [rsp+150h] [rbp+48h]
  GUID v72; // [rsp+158h] [rbp+50h]
  int v73; // [rsp+168h] [rbp+60h]
  int v74; // [rsp+16Ch] [rbp+64h]
  int v75; // [rsp+170h] [rbp+68h]
  __int128 v76; // [rsp+178h] [rbp+70h]
  int v77; // [rsp+188h] [rbp+80h]
  int v78; // [rsp+18Ch] [rbp+84h]
  int v79; // [rsp+190h] [rbp+88h]
  DEVPROPKEY v80; // [rsp+198h] [rbp+90h]
  int v81; // [rsp+1ACh] [rbp+A4h]
  const wchar_t *v82; // [rsp+1B0h] [rbp+A8h]
  DEVPROPKEY v83; // [rsp+1B8h] [rbp+B0h]
  int v84; // [rsp+1CCh] [rbp+C4h]
  int v85; // [rsp+1D0h] [rbp+C8h]
  DEVPROPKEY v86; // [rsp+1D8h] [rbp+D0h]
  int v87; // [rsp+1ECh] [rbp+E4h]
  int v88; // [rsp+1F0h] [rbp+E8h]
  void *v89; // [rsp+238h] [rbp+130h] BYREF
  unsigned int v90; // [rsp+248h] [rbp+140h]
  struct _DEVPROPERTY **v91; // [rsp+250h] [rbp+148h]

  v91 = a4;
  v90 = a3;
  if ( a1 && a4 && (v10 = a5) != 0 )
  {
    v11 = 0;
    *a4 = 0;
    *v10 = 0;
  }
  else
  {
    v11 = -2147024809;
  }
  if ( !a6 )
  {
    if ( !a7 )
      goto LABEL_18;
LABEL_10:
    v11 = -2147024809;
    v42 = 0;
LABEL_11:
    v13 = 0;
    p_pPrinterName = &a1->pPrinterName;
    v15 = 0;
    goto LABEL_12;
  }
  v12 = a7;
  if ( !a7 )
    goto LABEL_10;
  *a6 = 0;
  *v12 = 0;
LABEL_18:
  v20 = 0;
  v42 = 0;
  v89 = 0;
  if ( v11 < 0 )
    goto LABEL_11;
  pSecurityDescriptor = a1->pSecurityDescriptor;
  if ( pSecurityDescriptor )
  {
    v22 = ConvertPrinterSDToRestrictedDeviceSD(pSecurityDescriptor, &v89);
    v20 = v89;
    v11 = v22;
    v42 = v89;
  }
  if ( v11 < 0 )
    goto LABEL_11;
  Attributes = a1->Attributes;
  if ( (Attributes & 0x4000) != 0 )
  {
LABEL_26:
    v24 = L"PrintFax.FAX";
    goto LABEL_38;
  }
  v24 = L"PrintFax.Printer";
  if ( a2 && a3 == 8 )
  {
    v25 = *((_DWORD *)a2 + 42);
    if ( (v25 & 0x40) != 0 )
      goto LABEL_26;
    if ( (v25 & 0x80u) == 0 )
    {
      if ( (v25 & 0x100) != 0 )
      {
        v24 = L"PrintFax.Printer.Virtual";
      }
      else if ( (v25 & 0x200) != 0 )
      {
        v24 = L"PrintFax.Printer.Service";
      }
      else if ( (v25 & 0x1000) != 0 )
      {
        v24 = L"PrintFax.Printer.3D";
      }
      else
      {
        v26 = L"PrintFax.Printer.Cloud";
        if ( (*((_DWORD *)a2 + 42) & 0x2000) == 0 )
          v26 = L"PrintFax.Printer";
        v24 = v26;
      }
    }
    else
    {
      v24 = L"PrintFax.Printer.File";
    }
  }
LABEL_38:
  v28 = (a1->Status & 0xA0005A) == 0;
  p_pPrinterName = &a1->pPrinterName;
  pid = DEVPKEY_Device_FriendlyName.pid;
  pPrinterName = a1->pPrinterName;
  v13 = 10;
  fmtid = DEVPKEY_Device_FriendlyName.fmtid;
  v57 = DEVPKEY_Device_FriendlyNameAttributes;
  v55 = 18;
  v63 = !v28;
  v60 = PKEY_DeviceDisplay_IsNotWorkingProperly.fmtid;
  v67 = (Attributes >> 3) & 1;
  v27 = (Attributes >> 4) & 1;
  v64 = PKEY_DeviceDisplay_IsSharedDevice.fmtid;
  v69 = DEVPKEY_DeviceContainer_IsNetworkDevice.pid;
  if ( v20 )
    v13 = 11;
  v80 = DEVPKEY_DeviceContainer_Category;
  v83 = DEVPKEY_DeviceContainer_IsShowInDisconnectedState;
  v58 = 7;
  v59 = 2;
  v62 = 17;
  v61 = 83;
  v66 = 17;
  v65 = 84;
  v70 = 17;
  v71 = v27;
  v74 = 17;
  v73 = 86;
  v75 = 0;
  v78 = 17;
  v77 = 1;
  v79 = 1;
  v81 = 8210;
  v82 = v24;
  v84 = 17;
  v85 = 1;
  v86 = DEVPKEY_Device_NoConnectSound;
  v87 = 17;
  v88 = 1;
  v68 = DEVPKEY_DeviceContainer_IsNetworkDevice.fmtid;
  v72 = PKEY_DeviceDisplay_IsDefaultDevice.fmtid;
  v76 = xmmword_18001AF08;
  if ( a2 )
  {
    if ( a3 == 1 )
    {
      v28 = *(_QWORD *)a2 == 0;
    }
    else
    {
      if ( a3 < 6 )
        goto LABEL_50;
      if ( *((_QWORD *)a2 + 1) )
        v13 += 2;
      else
        ++v13;
      v28 = *((_QWORD *)a2 + 13) == 0;
    }
    if ( !v28 )
      ++v13;
  }
LABEL_50:
  v16 = 0;
  v15 = (struct _DEVPROPERTY *)DllAllocSplMem(48 * v13);
  if ( !v15 )
  {
    v11 = -2147024882;
    v17 = 0;
    goto LABEL_52;
  }
  do
  {
    if ( (unsigned int)v16 >= 0xA )
      break;
    v30 = ConvertPrintQueuePropertyToDevProperty(
            (struct _PrintQueueProperty *)(&fmtid + 2 * (unsigned int)v16),
            &v15[v16]);
    v16 = (unsigned int)(v16 + 1);
    v11 = v30;
  }
  while ( v30 >= 0 );
  if ( v11 >= 0 )
  {
    if ( v42 )
    {
      v41 = v42;
      v40 = 0x1300000064LL;
      v39 = (DEVPROPGUID)DEVPKEY_Device_RestrictedSD;
      v11 = ConvertPrintQueuePropertyToDevProperty((struct _PrintQueueProperty *)&v39, &v15[v16]);
      v16 = (unsigned int)(v16 + 1);
    }
    if ( v11 >= 0 && a2 )
    {
      if ( a3 == 1 )
      {
        v31 = *(void **)a2;
        if ( !*(_QWORD *)a2 )
          goto LABEL_12;
        v32 = v16;
        v33 = DEVPKEY_DrvPkg_Model.fmtid;
        LODWORD(v40) = DEVPKEY_DrvPkg_Model.pid;
        goto LABEL_64;
      }
      if ( a3 >= 6 )
      {
        if ( *((_QWORD *)a2 + 1) )
        {
          v41 = (void *)*((_QWORD *)a2 + 1);
          v40 = DEVPKEY_DrvPkg_Model.pid | 0x1200000000LL;
          v39 = DEVPKEY_DrvPkg_Model.fmtid;
          v11 = ConvertPrintQueuePropertyToDevProperty((struct _PrintQueueProperty *)&v39, &v15[v16]);
          v16 = (unsigned int)(v16 + 1);
        }
        if ( v11 >= 0 )
        {
          v40 = 0x700000007LL;
          v34 = *(_DWORD *)a2;
          v39 = (DEVPROPGUID)xmmword_18001AFE8;
          LODWORD(v41) = v34;
          v11 = ConvertPrintQueuePropertyToDevProperty((struct _PrintQueueProperty *)&v39, &v15[v16]);
          if ( v11 >= 0 )
          {
            v31 = (void *)*((_QWORD *)a2 + 13);
            if ( v31 )
            {
              v33 = DEVPKEY_Device_Manufacturer.fmtid;
              LODWORD(v40) = DEVPKEY_Device_Manufacturer.pid;
              v32 = (unsigned int)(v16 + 1);
LABEL_64:
              v41 = v31;
              HIDWORD(v40) = 18;
              v39 = v33;
              v11 = ConvertPrintQueuePropertyToDevProperty((struct _PrintQueueProperty *)&v39, &v15[v32]);
            }
          }
        }
      }
    }
  }
LABEL_12:
  LODWORD(v16) = 0;
  v17 = 0;
  if ( v11 < 0 )
  {
LABEL_52:
    FreeDevPropertyList(v15, v13);
    FreeDevPropertyList(v17, v16);
    goto LABEL_53;
  }
  if ( a6 )
  {
    v18 = *p_pPrinterName;
    v19 = v90;
    v47 = 18;
    v44 = 0x120000000ALL;
    LODWORD(v16) = 3;
    v45[0] = v18;
    v46 = 2;
    v48 = v18;
    v51 = 7;
    v50 = 3;
    v52 = 1;
    v43 = PKEY_DeviceInterface_PrinterName.fmtid;
    *(GUID *)&v45[1] = PKEY_DeviceInterface_FriendlyName.fmtid;
    v49 = xmmword_18001AF20;
    if ( a2 )
    {
      if ( v90 == 1 )
      {
        LODWORD(v16) = (*(_QWORD *)a2 != 0) + 3;
      }
      else if ( v90 >= 6 && *((_QWORD *)a2 + 1) )
      {
        LODWORD(v16) = 4;
      }
    }
    v17 = (struct _DEVPROPERTY *)DllAllocSplMem((unsigned int)(48 * v16));
    if ( !v17 )
    {
      v11 = -2147024882;
      goto LABEL_52;
    }
    v35 = 0;
    LODWORD(v89) = 0;
    while ( (unsigned int)v35 < 3 )
    {
      v11 = ConvertPrintQueuePropertyToDevProperty(
              (struct _PrintQueueProperty *)(&v43 + 2 * (unsigned int)v35),
              &v17[v35]);
      v35 = (unsigned int)((_DWORD)v89 + 1);
      LODWORD(v89) = (_DWORD)v89 + 1;
      if ( v11 < 0 )
        goto LABEL_52;
    }
    if ( a2 )
    {
      if ( v19 == 1 )
      {
        v36 = *(void **)a2;
      }
      else
      {
        if ( v19 < 6 )
          goto LABEL_87;
        v36 = (void *)*((_QWORD *)a2 + 1);
      }
      v40 = 0x120000000BLL;
      v39 = PKEY_DeviceInterface_PrinterDriverName.fmtid;
      v41 = v36;
      v11 = ConvertPrintQueuePropertyToDevProperty((struct _PrintQueueProperty *)&v39, &v17[v35]);
      if ( v11 < 0 )
        goto LABEL_52;
    }
  }
LABEL_87:
  v37 = a6;
  *v91 = v15;
  *a5 = v13;
  if ( v37 )
  {
    v38 = a7;
    *v37 = v17;
    *v38 = v16;
  }
LABEL_53:
  DllFreeSplMem(v42);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800114cc  mov     rax, rsp
0x1800114cf  mov     [rax+10h], rbx
0x1800114d3  mov     [rax+20h], r9
0x1800114d7  mov     [rax+18h], r8d
0x1800114db  push    rbp
0x1800114dc  push    rsi
0x1800114dd  push    rdi
0x1800114de  push    r12
0x1800114e0  push    r13
0x1800114e2  push    r14
0x1800114e4  push    r15
0x1800114e6  lea     rbp, [rax-128h]
0x1800114ed  sub     rsp, 1F0h
0x1800114f4  mov     r14, rdx
0x1800114f7  mov     edx, 80070057h
0x1800114fc  mov     rax, r9
0x1800114ff  mov     r12d, r8d
0x180011502  mov     rdi, rcx
0x180011505  test    rcx, rcx
0x180011508  jz      short loc_180011524
0x18001150a  test    rax, rax
0x18001150d  jz      short loc_180011524
0x18001150f  mov     rcx, [rbp+120h+arg_20]
0x180011516  test    rcx, rcx
0x180011519  jz      short loc_180011524
0x18001151b  xor     ebx, ebx
0x18001151d  mov     [r9], rbx
0x180011520  mov     [rcx], ebx
0x180011522  jmp     short loc_180011526
0x180011524  mov     ebx, edx
0x180011526  mov     rax, [rbp+120h+arg_28]
0x18001152d  mov     r10d, 1
0x180011533  lea     r11d, [r10+0Ah]
0x180011537  test    rax, rax
0x18001153a  jnz     short loc_18001154A
0x18001153c  cmp     [rbp+120h+arg_30], rax
0x180011543  jnz     short loc_18001155A
0x180011545  jmp     loc_180011620
0x18001154a  mov     rcx, [rbp+120h+arg_30]
0x180011551  test    rcx, rcx
0x180011554  jnz     loc_180011613
0x18001155a  mov     ebx, edx
0x18001155c  mov     [rsp+220h+var_1E0], 0
0x180011565  xor     r15d, r15d
0x180011568  lea     rsi, [rdi+8]
0x18001156c  xor     r13d, r13d
0x18001156f  xor     edi, edi
0x180011571  xor     r12d, r12d
0x180011574  test    ebx, ebx
0x180011576  js      loc_1800118B7
0x18001157c  cmp     [rbp+120h+arg_28], rdi
0x180011583  jz      loc_180011B59
0x180011589  mov     rax, [rsi]
0x18001158c  lea     ecx, [rdi+12h]
0x18001158f  mov     esi, [rbp+120h+arg_10]
0x180011595  mov     dword ptr [rsp+220h+var_1C0+4], ecx
0x180011599  mov     [rbp+120h+var_19C], ecx
0x18001159c  lea     ecx, [rdi+3]
0x18001159f  mov     dword ptr [rsp+220h+var_1C0], 0Ah
0x1800115a7  mov     edi, ecx
0x1800115a9  mov     qword ptr [rsp+220h+var_1B8], rax
0x1800115ae  mov     [rbp+120h+var_1A0], 2
0x1800115b5  mov     [rbp+120h+var_198], rax
0x1800115b9  mov     [rbp+120h+var_17C], 7
0x1800115c0  mov     [rbp+120h+var_180], ecx
0x1800115c3  mov     [rbp+120h+var_178], 1
0x1800115ca  movups  xmm0, xmmword ptr cs:PKEY_DeviceInterface_PrinterName.fmtid.Data1
0x1800115d1  movdqu  [rsp+220h+var_1D8+8], xmm0
0x1800115d7  movups  xmm0, xmmword ptr cs:PKEY_DeviceInterface_FriendlyName.fmtid.Data1
0x1800115de  movdqu  xmmword ptr [rsp+220h+var_1B8+8], xmm0
0x1800115e4  movups  xmm0, cs:xmmword_18001AF20
0x1800115eb  movdqu  [rbp+120h+var_190], xmm0
0x1800115f0  test    r14, r14
0x1800115f3  jz      loc_180011A9F
0x1800115f9  cmp     esi, 1
0x1800115fc  jnz     loc_180011A8E
0x180011602  mov     rax, [r14]
0x180011605  neg     rax
0x180011608  sbb     edi, edi
0x18001160a  neg     edi
0x18001160c  add     edi, ecx
0x18001160e  jmp     loc_180011A9F
0x180011613  mov     qword ptr [rax], 0
0x18001161a  mov     dword ptr [rcx], 0
0x180011620  xor     edx, edx
0x180011622  mov     [rsp+220h+var_1E0], rdx
0x180011627  mov     [rbp+120h+arg_0], rdx
0x18001162e  test    ebx, ebx
0x180011630  js      loc_180011565
0x180011636  mov     rcx, [rdi+60h]; Src
0x18001163a  test    rcx, rcx
0x18001163d  jz      short loc_180011663
0x18001163f  lea     rdx, [rbp+120h+arg_0]; void **
0x180011646  call    ?ConvertPrinterSDToRestrictedDeviceSD@@YAJPEAXPEAPEAX@Z; ConvertPrinterSDToRestrictedDeviceSD(void *,void * *)
0x18001164b  mov     rdx, [rbp+120h+arg_0]
0x180011652  mov     r10d, 1
0x180011658  mov     ebx, eax
0x18001165a  mov     [rsp+220h+var_1E0], rdx
0x18001165f  lea     r11d, [r10+0Ah]
0x180011663  test    ebx, ebx
0x180011665  js      loc_180011565
0x18001166b  mov     r8d, [rdi+68h]
0x18001166f  bt      r8d, 0Eh
0x180011674  jb      short loc_180011693
0x180011676  lea     rcx, aPrintfaxPrinte_0; "PrintFax.Printer"
0x18001167d  test    r14, r14
0x180011680  jz      short loc_1800116E8
0x180011682  cmp     r12d, 8
0x180011686  jnz     short loc_1800116E8
0x180011688  mov     eax, [r14+0A8h]
0x18001168f  test    al, 40h
0x180011691  jz      short loc_18001169C
0x180011693  lea     rcx, aPrintfaxFax; "PrintFax.FAX"
0x18001169a  jmp     short loc_1800116E8
0x18001169c  test    al, al
0x18001169e  jns     short loc_1800116A9
0x1800116a0  lea     rcx, aPrintfaxPrinte; "PrintFax.Printer.File"
0x1800116a7  jmp     short loc_1800116E8
0x1800116a9  bt      eax, 8
0x1800116ad  jnb     short loc_1800116B8
0x1800116af  lea     rcx, aPrintfaxPrinte_1; "PrintFax.Printer.Virtual"
0x1800116b6  jmp     short loc_1800116E8
0x1800116b8  bt      eax, 9
0x1800116bc  jnb     short loc_1800116C7
0x1800116be  lea     rcx, aPrintfaxPrinte_4; "PrintFax.Printer.Service"
0x1800116c5  jmp     short loc_1800116E8
0x1800116c7  bt      eax, 0Ch
0x1800116cb  jnb     short loc_1800116D6
0x1800116cd  lea     rcx, aPrintfaxPrinte_3; "PrintFax.Printer.3D"
0x1800116d4  jmp     short loc_1800116E8
0x1800116d6  bt      eax, 0Dh
0x1800116da  lea     rax, aPrintfaxPrinte_2; "PrintFax.Printer.Cloud"
0x1800116e1  cmovnb  rax, rcx
0x1800116e5  mov     rcx, rax
0x1800116e8  test    dword ptr [rdi+7Ch], 0A0005Ah
0x1800116ef  lea     rsi, [rdi+8]
0x1800116f3  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data1
0x1800116fa  mov     eax, cs:DEVPKEY_Device_FriendlyName.pid
0x180011700  mov     r9d, 11h
0x180011706  mov     [rbp+120h+var_160], eax
0x180011709  mov     rax, [rsi]
0x18001170c  mov     [rbp+120h+var_158], rax
0x180011710  mov     eax, cs:DEVPKEY_Device_FriendlyNameAttributes.pid
0x180011716  lea     r15d, [r9-7]
0x18001171a  movaps  [rbp+120h+var_170], xmm0
0x18001171e  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyNameAttributes.fmtid.Data1
0x180011725  mov     [rbp+120h+var_140], eax
0x180011728  lea     eax, [r9-11h]
0x18001172c  setnz   al
0x18001172f  mov     [rbp+120h+var_15C], 12h
0x180011736  movaps  [rbp+120h+var_150], xmm0
0x18001173a  movups  xmm0, xmmword ptr cs:PKEY_DeviceDisplay_IsNotWorkingProperly.fmtid.Data1
0x180011741  mov     [rbp+120h+var_118], eax
0x180011744  mov     eax, r8d
0x180011747  shr     eax, 3
0x18001174a  movdqu  [rbp+120h+var_130], xmm0
0x18001174f  and     eax, r10d
0x180011752  shr     r8d, 4
0x180011756  movups  xmm0, xmmword ptr cs:PKEY_DeviceDisplay_IsSharedDevice.fmtid.Data1
0x18001175d  mov     [rbp+120h+var_F8], eax
0x180011760  and     r8d, r10d
0x180011763  mov     eax, cs:DEVPKEY_DeviceContainer_IsNetworkDevice.pid
0x180011769  test    rdx, rdx
0x18001176c  movdqu  [rbp+120h+var_110], xmm0
0x180011771  mov     [rbp+120h+var_E0], eax
0x180011774  cmovnz  r15d, r11d
0x180011778  mov     eax, cs:DEVPKEY_DeviceContainer_Category.pid
0x18001177e  mov     [rbp+120h+var_80], eax
0x180011784  mov     eax, cs:DEVPKEY_DeviceContainer_IsShowInDisconnectedState.pid
0x18001178a  mov     [rbp+120h+var_60], eax
0x180011790  mov     eax, cs:DEVPKEY_Device_NoConnectSound.pid
0x180011796  mov     [rbp+120h+var_13C], 7
0x18001179d  mov     [rbp+120h+var_138], 2
0x1800117a4  mov     [rbp+120h+var_11C], r9d
0x1800117a8  mov     [rbp+120h+var_120], 53h ; 'S'
0x1800117af  mov     [rbp+120h+var_FC], r9d
0x1800117b3  mov     [rbp+120h+var_100], 54h ; 'T'
0x1800117ba  mov     [rbp+120h+var_DC], r9d
0x1800117be  mov     [rbp+120h+var_D8], r8d
0x1800117c2  mov     [rbp+120h+var_BC], r9d
0x1800117c6  mov     [rbp+120h+var_C0], 56h ; 'V'
0x1800117cd  mov     [rbp+120h+var_B8], 0
0x1800117d4  mov     [rbp+120h+var_9C], r9d
0x1800117db  mov     [rbp+120h+var_A0], r10d
0x1800117e2  mov     [rbp+120h+var_98], r10d
0x1800117e9  mov     [rbp+120h+var_7C], 2012h
0x1800117f3  mov     [rbp+120h+var_78], rcx
0x1800117fa  mov     [rbp+120h+var_5C], r9d
0x180011801  mov     [rbp+120h+var_58], r10d
0x180011808  mov     [rbp+120h+var_40], eax
0x18001180e  mov     [rbp+120h+var_3C], r9d
0x180011815  mov     [rbp+120h+var_38], r10d
0x18001181c  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_IsNetworkDevice.fmtid.Data1
0x180011823  movaps  [rbp+120h+var_F0], xmm0
0x180011827  movups  xmm0, xmmword ptr cs:PKEY_DeviceDisplay_IsDefaultDevice.fmtid.Data1
0x18001182e  movdqu  [rbp+120h+var_D0], xmm0
0x180011833  movups  xmm0, cs:xmmword_18001AF08
0x18001183a  movdqu  [rbp+120h+var_B0], xmm0
0x18001183f  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_Category.fmtid.Data1
0x180011846  movaps  [rbp+120h+var_90], xmm0
0x18001184d  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_IsShowInDisconnectedState.fmtid.Data1
0x180011854  movaps  [rbp+120h+var_70], xmm0
0x18001185b  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_NoConnectSound.fmtid.Data1
0x180011862  movaps  [rbp+120h+var_50], xmm0
0x180011869  test    r14, r14
0x18001186c  jz      short loc_180011899
0x18001186e  cmp     r12d, r10d
0x180011871  jnz     short loc_180011879
0x180011873  cmp     qword ptr [r14], 0
0x180011877  jmp     short loc_180011894
0x180011879  cmp     r12d, 6
0x18001187d  jb      short loc_180011899
0x18001187f  cmp     qword ptr [r14+8], 0
0x180011884  jz      short loc_18001188C
0x180011886  add     r15d, 2
0x18001188a  jmp     short loc_18001188F
0x18001188c  add     r15d, r10d
0x18001188f  cmp     qword ptr [r14+68h], 0
0x180011894  jz      short loc_180011899
0x180011896  add     r15d, r10d
0x180011899  lea     ecx, [r15+r15*2]
0x18001189d  shl     ecx, 4
0x1800118a0  call    DllAllocSplMem
0x1800118a5  xor     edi, edi
0x1800118a7  mov     r13, rax
0x1800118aa  test    rax, rax
0x1800118ad  jnz     short loc_1800118F3
0x1800118af  mov     ebx, 8007000Eh
0x1800118b4  xor     r12d, r12d
0x1800118b7  mov     edx, r15d; unsigned int
0x1800118ba  mov     rcx, r13; struct _DEVPROPERTY *
0x1800118bd  call    ?FreeDevPropertyList@@YAXPEAU_DEVPROPERTY@@K@Z; FreeDevPropertyList(_DEVPROPERTY *,ulong)
0x1800118c2  mov     edx, edi; unsigned int
0x1800118c4  mov     rcx, r12; struct _DEVPROPERTY *
0x1800118c7  call    ?FreeDevPropertyList@@YAXPEAU_DEVPROPERTY@@K@Z; FreeDevPropertyList(_DEVPROPERTY *,ulong)
0x1800118cc  mov     rcx, [rsp+220h+var_1E0]
0x1800118d1  call    DllFreeSplMem
0x1800118d6  mov     eax, ebx
0x1800118d8  mov     rbx, [rsp+220h+arg_8]
0x1800118e0  add     rsp, 1F0h
0x1800118e7  pop     r15
0x1800118e9  pop     r14
0x1800118eb  pop     r13
0x1800118ed  pop     r12
0x1800118ef  pop     rdi
0x1800118f0  pop     rsi
0x1800118f1  pop     rbp
0x1800118f2  retn
0x1800118f3  cmp     edi, 0Ah
0x1800118f6  jnb     short loc_18001191D
0x1800118f8  mov     eax, edi
0x1800118fa  lea     rdx, [rdi+rdi*2]
0x1800118fe  shl     rdx, 4
0x180011902  lea     rcx, [rbp+120h+var_170]
0x180011906  shl     rax, 5
0x18001190a  add     rdx, r13; struct _DEVPROPERTY *
0x18001190d  add     rcx, rax; struct _PrintQueueProperty *
0x180011910  call    ?ConvertPrintQueuePropertyToDevProperty@@YAJAEAU_PrintQueueProperty@@AEAU_DEVPROPERTY@@@Z; ConvertPrintQueuePropertyToDevProperty(_PrintQueueProperty &,_DEVPROPERTY &)
0x180011915  inc     edi
0x180011917  mov     ebx, eax
0x180011919  test    eax, eax
0x18001191b  jns     short loc_1800118F3
0x18001191d  test    ebx, ebx
0x18001191f  js      loc_18001156F
0x180011925  mov     rcx, [rsp+220h+var_1E0]
0x18001192a  test    rcx, rcx
0x18001192d  jz      short loc_18001196B
0x18001192f  movups  xmm0, cs:DEVPKEY_Device_RestrictedSD
0x180011936  mov     eax, cs:dword_18001B010
0x18001193c  lea     rdx, [rdi+rdi*2]
0x180011940  shl     rdx, 4
0x180011944  mov     [rsp+220h+var_1E8], rcx
0x180011949  add     rdx, r13; struct _DEVPROPERTY *
0x18001194c  lea     rcx, [rsp+220h+var_208+8]; struct _PrintQueueProperty *
0x180011951  mov     dword ptr [rsp+220h+var_1F0], eax
0x180011955  movups  [rsp+220h+var_208+8], xmm0
0x18001195a  mov     dword ptr [rsp+220h+var_1F0+4], 13h
0x180011962  call    ?ConvertPrintQueuePropertyToDevProperty@@YAJAEAU_PrintQueueProperty@@AEAU_DEVPROPERTY@@@Z; ConvertPrintQueuePropertyToDevProperty(_PrintQueueProperty &,_DEVPROPERTY &)
0x180011967  mov     ebx, eax
0x180011969  inc     edi
0x18001196b  test    ebx, ebx
0x18001196d  js      loc_18001156F
0x180011973  test    r14, r14
0x180011976  jz      loc_18001156F
0x18001197c  cmp     r12d, 1
0x180011980  jnz     short loc_1800119CD
0x180011982  mov     rcx, [r14]
0x180011985  test    rcx, rcx
0x180011988  jz      loc_18001156F
0x18001198e  mov     eax, cs:DEVPKEY_DrvPkg_Model.pid
0x180011994  lea     rdx, [rdi+rdi*2]
0x180011998  movups  xmm0, xmmword ptr cs:DEVPKEY_DrvPkg_Model.fmtid.Data1
0x18001199f  mov     dword ptr [rsp+220h+var_1F0], eax
0x1800119a3  shl     rdx, 4
0x1800119a7  mov     [rsp+220h+var_1E8], rcx
0x1800119ac  add     rdx, r13; struct _DEVPROPERTY *
0x1800119af  lea     rcx, [rsp+220h+var_208+8]; struct _PrintQueueProperty *
0x1800119b4  mov     dword ptr [rsp+220h+var_1F0+4], 12h
0x1800119bc  movups  [rsp+220h+var_208+8], xmm0
0x1800119c1  call    ?ConvertPrintQueuePropertyToDevProperty@@YAJAEAU_PrintQueueProperty@@AEAU_DEVPROPERTY@@@Z; ConvertPrintQueuePropertyToDevProperty(_PrintQueueProperty &,_DEVPROPERTY &)
  ... truncated ...
```
