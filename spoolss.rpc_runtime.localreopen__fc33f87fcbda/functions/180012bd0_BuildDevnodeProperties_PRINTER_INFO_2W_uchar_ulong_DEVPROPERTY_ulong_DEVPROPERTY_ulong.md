# BuildDevnodeProperties(_PRINTER_INFO_2W *,uchar *,ulong,_DEVPROPERTY * *,ulong *,_DEVPROPERTY * *,ulong *)

- ea: `0x180012bd0`
- end: `0x180013293`
- name: `?BuildDevnodeProperties@@YAJPEAU_PRINTER_INFO_2W@@PEAEKPEAPEAU_DEVPROPERTY@@PEAK23@Z`
- size: `1731`
- prototype: `__int64 __fastcall(struct _PRINTER_INFO_2W *, unsigned __int8 *, unsigned int, struct _DEVPROPERTY **, unsigned int *, struct _DEVPROPERTY **, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004bf4`
- `0x18001285c`

## callees

- `0x180001b60`
- `0x180001bb0`
- `0x180012bd0`
- `0x180015aa4`
- `0x180015c64`
- `0x1800161e8`

## string_xrefs

- `0x180012dc2`: `PrintFax.Printer.Service`

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
  v76 = xmmword_18001BF10;
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
          v39 = (DEVPROPGUID)xmmword_18001BFF0;
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
    v49 = xmmword_18001BF28;
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
0x180012bd0  mov     rax, rsp
0x180012bd3  mov     [rax+10h], rbx
0x180012bd7  mov     [rax+20h], r9
0x180012bdb  mov     [rax+18h], r8d
0x180012bdf  push    rbp
0x180012be0  push    rsi
0x180012be1  push    rdi
0x180012be2  push    r12
0x180012be4  push    r13
0x180012be6  push    r14
0x180012be8  push    r15
0x180012bea  lea     rbp, [rax-128h]
0x180012bf1  sub     rsp, 1F0h
0x180012bf8  mov     r14, rdx
0x180012bfb  mov     edx, 80070057h
0x180012c00  mov     rax, r9
0x180012c03  mov     r12d, r8d
0x180012c06  mov     rdi, rcx
0x180012c09  test    rcx, rcx
0x180012c0c  jz      short loc_180012C28
0x180012c0e  test    rax, rax
0x180012c11  jz      short loc_180012C28
0x180012c13  mov     rcx, [rbp+120h+arg_20]
0x180012c1a  test    rcx, rcx
0x180012c1d  jz      short loc_180012C28
0x180012c1f  xor     ebx, ebx
0x180012c21  mov     [r9], rbx
0x180012c24  mov     [rcx], ebx
0x180012c26  jmp     short loc_180012C2A
0x180012c28  mov     ebx, edx
0x180012c2a  mov     rax, [rbp+120h+arg_28]
0x180012c31  mov     r10d, 1
0x180012c37  lea     r11d, [r10+0Ah]
0x180012c3b  test    rax, rax
0x180012c3e  jnz     short loc_180012C4E
0x180012c40  cmp     [rbp+120h+arg_30], rax
0x180012c47  jnz     short loc_180012C5E
0x180012c49  jmp     loc_180012D24
0x180012c4e  mov     rcx, [rbp+120h+arg_30]
0x180012c55  test    rcx, rcx
0x180012c58  jnz     loc_180012D17
0x180012c5e  mov     ebx, edx
0x180012c60  mov     [rsp+220h+var_1E0], 0
0x180012c69  xor     r15d, r15d
0x180012c6c  lea     rsi, [rdi+8]
0x180012c70  xor     r13d, r13d
0x180012c73  xor     edi, edi
0x180012c75  xor     r12d, r12d
0x180012c78  test    ebx, ebx
0x180012c7a  js      loc_180012FBB
0x180012c80  cmp     [rbp+120h+arg_28], rdi
0x180012c87  jz      loc_18001325E
0x180012c8d  mov     rax, [rsi]
0x180012c90  lea     ecx, [rdi+12h]
0x180012c93  mov     esi, [rbp+120h+arg_10]
0x180012c99  mov     dword ptr [rsp+220h+var_1C0+4], ecx
0x180012c9d  mov     [rbp+120h+var_19C], ecx
0x180012ca0  lea     ecx, [rdi+3]
0x180012ca3  mov     dword ptr [rsp+220h+var_1C0], 0Ah
0x180012cab  mov     edi, ecx
0x180012cad  mov     qword ptr [rsp+220h+var_1B8], rax
0x180012cb2  mov     [rbp+120h+var_1A0], 2
0x180012cb9  mov     [rbp+120h+var_198], rax
0x180012cbd  mov     [rbp+120h+var_17C], 7
0x180012cc4  mov     [rbp+120h+var_180], ecx
0x180012cc7  mov     [rbp+120h+var_178], 1
0x180012cce  movups  xmm0, xmmword ptr cs:PKEY_DeviceInterface_PrinterName.fmtid.Data1
0x180012cd5  movdqu  [rsp+220h+var_1D8+8], xmm0
0x180012cdb  movups  xmm0, xmmword ptr cs:PKEY_DeviceInterface_FriendlyName.fmtid.Data1
0x180012ce2  movdqu  xmmword ptr [rsp+220h+var_1B8+8], xmm0
0x180012ce8  movups  xmm0, cs:xmmword_18001BF28
0x180012cef  movdqu  [rbp+120h+var_190], xmm0
0x180012cf4  test    r14, r14
0x180012cf7  jz      loc_1800131A4
0x180012cfd  cmp     esi, 1
0x180012d00  jnz     loc_180013193
0x180012d06  mov     rax, [r14]
0x180012d09  neg     rax
0x180012d0c  sbb     edi, edi
0x180012d0e  neg     edi
0x180012d10  add     edi, ecx
0x180012d12  jmp     loc_1800131A4
0x180012d17  mov     qword ptr [rax], 0
0x180012d1e  mov     dword ptr [rcx], 0
0x180012d24  xor     edx, edx
0x180012d26  mov     [rsp+220h+var_1E0], rdx
0x180012d2b  mov     [rbp+120h+arg_0], rdx
0x180012d32  test    ebx, ebx
0x180012d34  js      loc_180012C69
0x180012d3a  mov     rcx, [rdi+60h]; Src
0x180012d3e  test    rcx, rcx
0x180012d41  jz      short loc_180012D67
0x180012d43  lea     rdx, [rbp+120h+arg_0]; void **
0x180012d4a  call    ?ConvertPrinterSDToRestrictedDeviceSD@@YAJPEAXPEAPEAX@Z; ConvertPrinterSDToRestrictedDeviceSD(void *,void * *)
0x180012d4f  mov     rdx, [rbp+120h+arg_0]
0x180012d56  mov     r10d, 1
0x180012d5c  mov     ebx, eax
0x180012d5e  mov     [rsp+220h+var_1E0], rdx
0x180012d63  lea     r11d, [r10+0Ah]
0x180012d67  test    ebx, ebx
0x180012d69  js      loc_180012C69
0x180012d6f  mov     r8d, [rdi+68h]
0x180012d73  bt      r8d, 0Eh
0x180012d78  jb      short loc_180012D97
0x180012d7a  lea     rcx, aPrintfaxPrinte_0; "PrintFax.Printer"
0x180012d81  test    r14, r14
0x180012d84  jz      short loc_180012DEC
0x180012d86  cmp     r12d, 8
0x180012d8a  jnz     short loc_180012DEC
0x180012d8c  mov     eax, [r14+0A8h]
0x180012d93  test    al, 40h
0x180012d95  jz      short loc_180012DA0
0x180012d97  lea     rcx, aPrintfaxFax; "PrintFax.FAX"
0x180012d9e  jmp     short loc_180012DEC
0x180012da0  test    al, al
0x180012da2  jns     short loc_180012DAD
0x180012da4  lea     rcx, aPrintfaxPrinte; "PrintFax.Printer.File"
0x180012dab  jmp     short loc_180012DEC
0x180012dad  bt      eax, 8
0x180012db1  jnb     short loc_180012DBC
0x180012db3  lea     rcx, aPrintfaxPrinte_1; "PrintFax.Printer.Virtual"
0x180012dba  jmp     short loc_180012DEC
0x180012dbc  bt      eax, 9
0x180012dc0  jnb     short loc_180012DCB
0x180012dc2  lea     rcx, aPrintfaxPrinte_4; "PrintFax.Printer.Service"
0x180012dc9  jmp     short loc_180012DEC
0x180012dcb  bt      eax, 0Ch
0x180012dcf  jnb     short loc_180012DDA
0x180012dd1  lea     rcx, aPrintfaxPrinte_3; "PrintFax.Printer.3D"
0x180012dd8  jmp     short loc_180012DEC
0x180012dda  bt      eax, 0Dh
0x180012dde  lea     rax, aPrintfaxPrinte_2; "PrintFax.Printer.Cloud"
0x180012de5  cmovnb  rax, rcx
0x180012de9  mov     rcx, rax
0x180012dec  test    dword ptr [rdi+7Ch], 0A0005Ah
0x180012df3  lea     rsi, [rdi+8]
0x180012df7  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data1
0x180012dfe  mov     eax, cs:DEVPKEY_Device_FriendlyName.pid
0x180012e04  mov     r9d, 11h
0x180012e0a  mov     [rbp+120h+var_160], eax
0x180012e0d  mov     rax, [rsi]
0x180012e10  mov     [rbp+120h+var_158], rax
0x180012e14  mov     eax, cs:DEVPKEY_Device_FriendlyNameAttributes.pid
0x180012e1a  lea     r15d, [r9-7]
0x180012e1e  movaps  [rbp+120h+var_170], xmm0
0x180012e22  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyNameAttributes.fmtid.Data1
0x180012e29  mov     [rbp+120h+var_140], eax
0x180012e2c  lea     eax, [r9-11h]
0x180012e30  setnz   al
0x180012e33  mov     [rbp+120h+var_15C], 12h
0x180012e3a  movaps  [rbp+120h+var_150], xmm0
0x180012e3e  movups  xmm0, xmmword ptr cs:PKEY_DeviceDisplay_IsNotWorkingProperly.fmtid.Data1
0x180012e45  mov     [rbp+120h+var_118], eax
0x180012e48  mov     eax, r8d
0x180012e4b  shr     eax, 3
0x180012e4e  movdqu  [rbp+120h+var_130], xmm0
0x180012e53  and     eax, r10d
0x180012e56  shr     r8d, 4
0x180012e5a  movups  xmm0, xmmword ptr cs:PKEY_DeviceDisplay_IsSharedDevice.fmtid.Data1
0x180012e61  mov     [rbp+120h+var_F8], eax
0x180012e64  and     r8d, r10d
0x180012e67  mov     eax, cs:DEVPKEY_DeviceContainer_IsNetworkDevice.pid
0x180012e6d  test    rdx, rdx
0x180012e70  movdqu  [rbp+120h+var_110], xmm0
0x180012e75  mov     [rbp+120h+var_E0], eax
0x180012e78  cmovnz  r15d, r11d
0x180012e7c  mov     eax, cs:DEVPKEY_DeviceContainer_Category.pid
0x180012e82  mov     [rbp+120h+var_80], eax
0x180012e88  mov     eax, cs:DEVPKEY_DeviceContainer_IsShowInDisconnectedState.pid
0x180012e8e  mov     [rbp+120h+var_60], eax
0x180012e94  mov     eax, cs:DEVPKEY_Device_NoConnectSound.pid
0x180012e9a  mov     [rbp+120h+var_13C], 7
0x180012ea1  mov     [rbp+120h+var_138], 2
0x180012ea8  mov     [rbp+120h+var_11C], r9d
0x180012eac  mov     [rbp+120h+var_120], 53h ; 'S'
0x180012eb3  mov     [rbp+120h+var_FC], r9d
0x180012eb7  mov     [rbp+120h+var_100], 54h ; 'T'
0x180012ebe  mov     [rbp+120h+var_DC], r9d
0x180012ec2  mov     [rbp+120h+var_D8], r8d
0x180012ec6  mov     [rbp+120h+var_BC], r9d
0x180012eca  mov     [rbp+120h+var_C0], 56h ; 'V'
0x180012ed1  mov     [rbp+120h+var_B8], 0
0x180012ed8  mov     [rbp+120h+var_9C], r9d
0x180012edf  mov     [rbp+120h+var_A0], r10d
0x180012ee6  mov     [rbp+120h+var_98], r10d
0x180012eed  mov     [rbp+120h+var_7C], 2012h
0x180012ef7  mov     [rbp+120h+var_78], rcx
0x180012efe  mov     [rbp+120h+var_5C], r9d
0x180012f05  mov     [rbp+120h+var_58], r10d
0x180012f0c  mov     [rbp+120h+var_40], eax
0x180012f12  mov     [rbp+120h+var_3C], r9d
0x180012f19  mov     [rbp+120h+var_38], r10d
0x180012f20  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_IsNetworkDevice.fmtid.Data1
0x180012f27  movaps  [rbp+120h+var_F0], xmm0
0x180012f2b  movups  xmm0, xmmword ptr cs:PKEY_DeviceDisplay_IsDefaultDevice.fmtid.Data1
0x180012f32  movdqu  [rbp+120h+var_D0], xmm0
0x180012f37  movups  xmm0, cs:xmmword_18001BF10
0x180012f3e  movdqu  [rbp+120h+var_B0], xmm0
0x180012f43  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_Category.fmtid.Data1
0x180012f4a  movaps  [rbp+120h+var_90], xmm0
0x180012f51  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_IsShowInDisconnectedState.fmtid.Data1
0x180012f58  movaps  [rbp+120h+var_70], xmm0
0x180012f5f  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_NoConnectSound.fmtid.Data1
0x180012f66  movaps  [rbp+120h+var_50], xmm0
0x180012f6d  test    r14, r14
0x180012f70  jz      short loc_180012F9D
0x180012f72  cmp     r12d, r10d
0x180012f75  jnz     short loc_180012F7D
0x180012f77  cmp     qword ptr [r14], 0
0x180012f7b  jmp     short loc_180012F98
0x180012f7d  cmp     r12d, 6
0x180012f81  jb      short loc_180012F9D
0x180012f83  cmp     qword ptr [r14+8], 0
0x180012f88  jz      short loc_180012F90
0x180012f8a  add     r15d, 2
0x180012f8e  jmp     short loc_180012F93
0x180012f90  add     r15d, r10d
0x180012f93  cmp     qword ptr [r14+68h], 0
0x180012f98  jz      short loc_180012F9D
0x180012f9a  add     r15d, r10d
0x180012f9d  lea     ecx, [r15+r15*2]
0x180012fa1  shl     ecx, 4
0x180012fa4  call    DllAllocSplMem
0x180012fa9  xor     edi, edi
0x180012fab  mov     r13, rax
0x180012fae  test    rax, rax
0x180012fb1  jnz     short loc_180012FF8
0x180012fb3  mov     ebx, 8007000Eh
0x180012fb8  xor     r12d, r12d
0x180012fbb  mov     edx, r15d; unsigned int
0x180012fbe  mov     rcx, r13; struct _DEVPROPERTY *
0x180012fc1  call    ?FreeDevPropertyList@@YAXPEAU_DEVPROPERTY@@K@Z; FreeDevPropertyList(_DEVPROPERTY *,ulong)
0x180012fc6  mov     edx, edi; unsigned int
0x180012fc8  mov     rcx, r12; struct _DEVPROPERTY *
0x180012fcb  call    ?FreeDevPropertyList@@YAXPEAU_DEVPROPERTY@@K@Z; FreeDevPropertyList(_DEVPROPERTY *,ulong)
0x180012fd0  mov     rcx, [rsp+220h+var_1E0]
0x180012fd5  call    DllFreeSplMem
0x180012fda  mov     eax, ebx
0x180012fdc  mov     rbx, [rsp+220h+arg_8]
0x180012fe4  add     rsp, 1F0h
0x180012feb  pop     r15
0x180012fed  pop     r14
0x180012fef  pop     r13
0x180012ff1  pop     r12
0x180012ff3  pop     rdi
0x180012ff4  pop     rsi
0x180012ff5  pop     rbp
0x180012ff6  retn
0x180012ff8  cmp     edi, 0Ah
0x180012ffb  jnb     short loc_180013022
0x180012ffd  mov     eax, edi
0x180012fff  lea     rdx, [rdi+rdi*2]
0x180013003  shl     rdx, 4
0x180013007  lea     rcx, [rbp+120h+var_170]
0x18001300b  shl     rax, 5
0x18001300f  add     rdx, r13; struct _DEVPROPERTY *
0x180013012  add     rcx, rax; struct _PrintQueueProperty *
0x180013015  call    ?ConvertPrintQueuePropertyToDevProperty@@YAJAEAU_PrintQueueProperty@@AEAU_DEVPROPERTY@@@Z; ConvertPrintQueuePropertyToDevProperty(_PrintQueueProperty &,_DEVPROPERTY &)
0x18001301a  inc     edi
0x18001301c  mov     ebx, eax
0x18001301e  test    eax, eax
0x180013020  jns     short loc_180012FF8
0x180013022  test    ebx, ebx
0x180013024  js      loc_180012C73
0x18001302a  mov     rcx, [rsp+220h+var_1E0]
0x18001302f  test    rcx, rcx
0x180013032  jz      short loc_180013070
0x180013034  movups  xmm0, cs:DEVPKEY_Device_RestrictedSD
0x18001303b  mov     eax, cs:dword_18001C018
0x180013041  lea     rdx, [rdi+rdi*2]
0x180013045  shl     rdx, 4
0x180013049  mov     [rsp+220h+var_1E8], rcx
0x18001304e  add     rdx, r13; struct _DEVPROPERTY *
0x180013051  lea     rcx, [rsp+220h+var_208+8]; struct _PrintQueueProperty *
0x180013056  mov     dword ptr [rsp+220h+var_1F0], eax
0x18001305a  movups  [rsp+220h+var_208+8], xmm0
0x18001305f  mov     dword ptr [rsp+220h+var_1F0+4], 13h
0x180013067  call    ?ConvertPrintQueuePropertyToDevProperty@@YAJAEAU_PrintQueueProperty@@AEAU_DEVPROPERTY@@@Z; ConvertPrintQueuePropertyToDevProperty(_PrintQueueProperty &,_DEVPROPERTY &)
0x18001306c  mov     ebx, eax
0x18001306e  inc     edi
0x180013070  test    ebx, ebx
0x180013072  js      loc_180012C73
0x180013078  test    r14, r14
0x18001307b  jz      loc_180012C73
0x180013081  cmp     r12d, 1
0x180013085  jnz     short loc_1800130D2
0x180013087  mov     rcx, [r14]
0x18001308a  test    rcx, rcx
0x18001308d  jz      loc_180012C73
0x180013093  mov     eax, cs:DEVPKEY_DrvPkg_Model.pid
0x180013099  lea     rdx, [rdi+rdi*2]
0x18001309d  movups  xmm0, xmmword ptr cs:DEVPKEY_DrvPkg_Model.fmtid.Data1
0x1800130a4  mov     dword ptr [rsp+220h+var_1F0], eax
0x1800130a8  shl     rdx, 4
0x1800130ac  mov     [rsp+220h+var_1E8], rcx
0x1800130b1  add     rdx, r13; struct _DEVPROPERTY *
0x1800130b4  lea     rcx, [rsp+220h+var_208+8]; struct _PrintQueueProperty *
0x1800130b9  mov     dword ptr [rsp+220h+var_1F0+4], 12h
0x1800130c1  movups  [rsp+220h+var_208+8], xmm0
0x1800130c6  call    ?ConvertPrintQueuePropertyToDevProperty@@YAJAEAU_PrintQueueProperty@@AEAU_DEVPROPERTY@@@Z; ConvertPrintQueuePropertyToDevProperty(_PrintQueueProperty &,_DEVPROPERTY &)
  ... truncated ...
```
