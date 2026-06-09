# Rootcause::BuildReportXml(Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *,IXMLDOMDocument2 * *)

- ea: `0x180018a9c`
- end: `0x1800192a4`
- name: `?BuildReportXml@Rootcause@@AEAAJPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@PEAPEAUIXMLDOMDocument2@@@Z`
- size: `2056`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, SAFEARRAY **, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18001b9c8`

## callees

- `0x1800012a4`
- `0x180002280`
- `0x18000571c`
- `0x180005ad0`
- `0x180005ffc`
- `0x180018a9c`
- `0x18001b070`
- `0x18001cb90`
- `0x18001cc2c`
- `0x180026fa0`
- `0x180027aa0`
- `0x180027ea4`
- `0x1800280f8`
- `0x18002827c`
- `0x1800291e0`
- `0x18002a010`

## string_xrefs

- `0x18001902f`: `<?xml version="1.0" encoding="utf-8"?><DetailedInformation/>`
- `0x1800191a9`: `<?xml version="1.0" encoding="utf-8"?><DetailedInformation/>`
- `0x180018b02`: `Rootcause::BuildReportXml`
- `0x180018b54`: `Rootcause::BuildReportXml`
- `0x180018ba5`: `Rootcause::BuildReportXml`
- `0x180018c4e`: `Rootcause::BuildReportXml`
- `0x180018d50`: `Rootcause::BuildReportXml`
- `0x180018db6`: `Rootcause::BuildReportXml`
- `0x180019145`: `Rootcause::BuildReportXml`
- `0x1800191be`: `Rootcause::BuildReportXml`
- `0x180018b8a`: `<?xml version="1.0" encoding="utf-8"?><RootCause/>`

## pseudocode

```c
__int64 __fastcall Rootcause::BuildReportXml(
        const unsigned __int16 **this,
        SAFEARRAY **a2,
        struct IXMLDOMDocument2 **a3)
{
  struct IXMLDOMDocument2 *v5; // rsi
  struct IXMLDOMElement *v6; // rdi
  unsigned __int16 *v7; // r15
  void *v8; // r13
  unsigned int v9; // ebx
  int v10; // r8d
  int v11; // r9d
  const unsigned __int16 *v12; // rdx
  int v13; // eax
  int v14; // r8d
  int updated; // eax
  int v16; // r8d
  int v17; // r9d
  struct IXMLDOMDocument2 *v18; // rcx
  const unsigned __int16 *v19; // rdx
  int v20; // eax
  int v21; // r8d
  const unsigned __int16 *v22; // rdx
  int v23; // eax
  int v24; // r8d
  int v25; // r9d
  int v26; // eax
  int v27; // r8d
  __int64 v28; // rcx
  __int64 v29; // rdx
  const unsigned __int16 *v30; // r9
  __int64 v31; // rbx
  const unsigned __int16 *v32; // r12
  SAFEARRAY *v33; // rax
  __int64 v34; // rbx
  struct IXMLDOMDocument2 *v35; // rcx
  struct IXMLDOMDocument2 v36; // rax
  int ReportXml; // eax
  int v38; // eax
  unsigned __int16 *v40; // [rsp+30h] [rbp-40h] BYREF
  struct IXMLDOMDocument2 *v41; // [rsp+38h] [rbp-38h] BYREF
  struct IXMLDOMElement *v42; // [rsp+40h] [rbp-30h] BYREF
  struct IXMLDOMDocument2 *v43; // [rsp+48h] [rbp-28h] BYREF
  struct IXMLDOMDocument2 *v44; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int16 *v45; // [rsp+58h] [rbp-18h] BYREF
  const unsigned __int16 *v46; // [rsp+60h] [rbp-10h] BYREF
  void *Block; // [rsp+C8h] [rbp+58h] BYREF

  v44 = 0;
  v5 = 0;
  v41 = 0;
  v6 = 0;
  v43 = 0;
  v7 = 0;
  v42 = 0;
  v8 = 0;
  v40 = 0;
  Block = 0;
  v45 = 0;
  v46 = 0;
  if ( !a3 )
  {
    v9 = -2147024809;
    v10 = 1827;
    v11 = -2147024809;
LABEL_3:
    SdpDebugTrace(1u, L"Rootcause::BuildReportXml", v10, v11);
    return v9;
  }
  if ( !a2 )
  {
    v13 = SdpStrCpy(&v45, this[5]);
    v9 = v13;
    if ( v13 < 0 )
    {
      v14 = 1841;
      goto LABEL_9;
    }
LABEL_12:
    updated = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><RootCause/>", &v41);
    v9 = updated;
    if ( updated < 0 )
    {
      v16 = 1845;
      goto LABEL_14;
    }
    updated = SdpXmlSetAttribute(v41, 0, L"id", v45);
    v9 = updated;
    if ( updated < 0 )
    {
      v16 = 1848;
      goto LABEL_14;
    }
    v19 = this[7];
    if ( !v19 )
    {
      v17 = -2147467261;
      v16 = 1850;
      v9 = -2147467261;
LABEL_15:
      SdpDebugTrace(1u, L"Rootcause::BuildReportXml", v16, v17);
LABEL_16:
      v18 = v41;
LABEL_117:
      if ( v18 )
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v18->lpVtbl->Release)(v18);
      if ( v6 )
        ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
      if ( v5 )
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v5->lpVtbl->Release)(v5);
      if ( v44 )
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v44->lpVtbl->Release)(v44);
      if ( v7 )
        operator delete(v7);
      if ( v8 )
        operator delete(v8);
      goto LABEL_129;
    }
    if ( a2 && *((_DWORD *)a2 + 6) )
    {
      updated = SdpUpdateParamSet(a2[4], a2[5], (struct _SDIAG_PARAMSET *)(this + 9));
      v9 = updated;
      if ( updated < 0 )
      {
        v16 = 1856;
        goto LABEL_14;
      }
      v20 = SdpSubstituteParamSet((unsigned __int16 **)&Block, this[7], (struct _SDIAG_PARAMSET *)(this + 9));
      v9 = v20;
      if ( v20 < 0 )
      {
        v21 = 1861;
LABEL_27:
        SdpDebugTrace(1u, L"Rootcause::BuildReportXml", v21, v20);
        v8 = Block;
        goto LABEL_16;
      }
    }
    else
    {
      v20 = SdpStrCpy((unsigned __int16 **)&Block, v19);
      v9 = v20;
      if ( v20 < 0 )
      {
        v21 = 1865;
        goto LABEL_27;
      }
    }
    v8 = Block;
    updated = SdpXmlSetAttribute(v41, 0, L"name", (const unsigned __int16 *)Block);
    v9 = updated;
    if ( updated < 0 )
    {
      v16 = 1872;
      goto LABEL_14;
    }
    if ( v8 )
    {
      operator delete(v8);
      v8 = 0;
      Block = 0;
    }
    v22 = this[8];
    if ( !v22 )
    {
      v17 = -2147467261;
      v16 = 1884;
      v9 = -2147467261;
      goto LABEL_15;
    }
    if ( a2 && *((_DWORD *)a2 + 6) )
    {
      v20 = SdpSubstituteParamSet((unsigned __int16 **)&Block, v22, (struct _SDIAG_PARAMSET *)(this + 9));
      v9 = v20;
      if ( v20 < 0 )
      {
        v21 = 1890;
        goto LABEL_27;
      }
    }
    else
    {
      v20 = SdpStrCpy((unsigned __int16 **)&Block, v22);
      v9 = v20;
      if ( v20 < 0 )
      {
        v21 = 1894;
        goto LABEL_27;
      }
    }
    v8 = Block;
    v23 = SdpXmlCreateNode(v41, 0, L"Data", (const unsigned __int16 *)Block, &v42);
    v9 = v23;
    if ( v23 < 0 )
    {
      v24 = 1902;
      goto LABEL_44;
    }
    v6 = v42;
    updated = SdpXmlSetAttribute(0, v42, L"id", L"Description");
    v9 = updated;
    if ( updated < 0 )
    {
      v16 = 1908;
      goto LABEL_14;
    }
    v26 = SdpLoadString(0, 0x76u, &v40);
    v9 = v26;
    if ( v26 >= 0 )
    {
      v7 = v40;
      updated = SdpXmlSetAttribute(0, v6, L"name", v40);
      v9 = updated;
      if ( updated < 0 )
      {
        v16 = 1914;
        goto LABEL_14;
      }
      if ( v6 )
      {
        ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
        v6 = 0;
        v42 = 0;
      }
      if ( v7 )
      {
        operator delete(v7);
        v7 = 0;
        v40 = 0;
      }
      if ( a2 && (v29 = *((unsigned int *)a2 + 6), (_DWORD)v29) )
      {
        updated = Rootcause::StatusToString(v28, v29, &v46);
        v9 = updated;
        if ( updated < 0 )
        {
          v16 = 1925;
          goto LABEL_14;
        }
        v30 = v46;
      }
      else
      {
        v30 = L"Not Checked";
      }
      v23 = SdpXmlCreateNode(v41, 0, L"Data", v30, &v42);
      v9 = v23;
      if ( v23 < 0 )
      {
        v24 = 1936;
        goto LABEL_44;
      }
      v6 = v42;
      updated = SdpXmlSetAttribute(0, v42, L"id", L"Status");
      v9 = updated;
      if ( updated < 0 )
      {
        v16 = 1942;
        goto LABEL_14;
      }
      v26 = SdpLoadString(0, 0x93u, &v40);
      v9 = v26;
      if ( v26 >= 0 )
      {
        v7 = v40;
        updated = SdpXmlSetAttribute(0, v6, L"name", v40);
        v9 = updated;
        if ( updated < 0 )
        {
          v16 = 1948;
          goto LABEL_14;
        }
        if ( v6 )
        {
          ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
          v42 = 0;
        }
        if ( v7 )
        {
          operator delete(v7);
          v7 = 0;
        }
        v23 = SdpXmlCreateNode(v41, 0, L"ResolutionInformation", 0, &v42);
        v9 = v23;
        if ( v23 >= 0 )
        {
          v6 = v42;
          v31 = 0;
          LODWORD(v40) = 0;
          LODWORD(Block) = 0;
          if ( *((_DWORD *)this + 8) )
          {
            v46 = (const unsigned __int16 *)(this + 2);
            v32 = (const unsigned __int16 *)(this + 2);
            do
            {
              if ( v5 )
              {
                ((void (__fastcall *)(struct IXMLDOMDocument2 *))v5->lpVtbl->Release)(v5);
                v32 = v46;
                v5 = 0;
                v43 = 0;
              }
              if ( v44 )
              {
                ((void (__fastcall *)(struct IXMLDOMDocument2 *))v44->lpVtbl->Release)(v44);
                v32 = v46;
                v44 = 0;
              }
              if ( a2 )
              {
                if ( *((_DWORD *)a2 + 6) )
                {
                  updated = Resolver::RecordParameters((Resolver *)(*(_QWORD *)v32 + 80 * v31), a2[4], a2[5]);
                  v9 = updated;
                  if ( updated < 0 )
                  {
                    v16 = 1972;
                    goto LABEL_14;
                  }
                  v31 = (unsigned int)Block;
                  v32 = (const unsigned __int16 *)(this + 2);
                }
                v33 = a2[7];
                if ( !v33 )
                {
                  v17 = -2147467261;
                  v16 = 1975;
                  v9 = -2147467261;
                  goto LABEL_15;
                }
                v34 = 2 * v31;
                v35 = (struct IXMLDOMDocument2 *)*((_QWORD *)&v33->cLocks + v34);
                if ( !v35 )
                {
                  v17 = -2147467261;
                  v16 = 1976;
                  v9 = -2147467261;
                  goto LABEL_15;
                }
                v36.lpVtbl = v35->lpVtbl;
                v44 = v35;
                ((void (*)(void))v36.lpVtbl->AddRef)();
                LODWORD(v40) = *((_DWORD *)&a2[7]->cDims + 2 * v34);
              }
              else
              {
                updated = SdpXmlCreate(
                            (OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><DetailedInformation/>",
                            &v44);
                v9 = updated;
                if ( updated < 0 )
                {
                  v16 = 1985;
                  goto LABEL_14;
                }
              }
              ReportXml = Resolver::get_ReportXml(
                            (Resolver *)(*(_QWORD *)v32 + 80LL * (unsigned int)Block),
                            v44,
                            (unsigned int)v40,
                            &v43);
              v9 = ReportXml;
              if ( ReportXml < 0 )
              {
                SdpDebugTrace(1u, L"Rootcause::BuildReportXml", 1989, ReportXml);
                v5 = v43;
                goto LABEL_16;
              }
              v5 = v43;
              updated = SdpXmlAppend(0, v6, v43);
              v9 = updated;
              if ( updated < 0 )
              {
                v16 = 1992;
                goto LABEL_14;
              }
              v31 = (unsigned int)((_DWORD)Block + 1);
              LODWORD(Block) = v31;
            }
            while ( (unsigned int)v31 < *((_DWORD *)this + 8) );
          }
          if ( v6 )
          {
            ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
            v42 = 0;
          }
          if ( v5 )
          {
            ((void (__fastcall *)(struct IXMLDOMDocument2 *))v5->lpVtbl->Release)(v5);
            v5 = 0;
            v43 = 0;
          }
          v23 = SdpXmlCreateNode(v41, 0, L"DetectionInformation", 0, &v42);
          v9 = v23;
          if ( v23 >= 0 )
          {
            if ( a2 )
            {
              if ( !a2[6] )
              {
                v25 = -2147467261;
                v24 = 2009;
                v9 = -2147467261;
                goto LABEL_45;
              }
              v5 = (struct IXMLDOMDocument2 *)a2[6];
              ((void (__fastcall *)(struct IXMLDOMDocument2 *))v5->lpVtbl->AddRef)(v5);
            }
            else
            {
              v38 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><DetailedInformation/>", &v43);
              v9 = v38;
              if ( v38 < 0 )
              {
                SdpDebugTrace(1u, L"Rootcause::BuildReportXml", 2016, v38);
                v5 = v43;
                goto LABEL_46;
              }
              v5 = v43;
            }
            v6 = v42;
            updated = SdpXmlAppend(0, v42, v5);
            v9 = updated;
            if ( updated >= 0 )
            {
              *a3 = v41;
              v18 = 0;
              goto LABEL_117;
            }
            v16 = 2020;
LABEL_14:
            v17 = updated;
            goto LABEL_15;
          }
          v24 = 2006;
        }
        else
        {
          v24 = 1962;
        }
LABEL_44:
        v25 = v23;
LABEL_45:
        SdpDebugTrace(1u, L"Rootcause::BuildReportXml", v24, v25);
LABEL_46:
        v6 = v42;
        goto LABEL_16;
      }
      v27 = 1945;
    }
    else
    {
      v27 = 1911;
    }
    SdpDebugTrace(1u, L"Rootcause::BuildReportXml", v27, v26);
    v7 = v40;
    goto LABEL_16;
  }
  v12 = (const unsigned __int16 *)a2[2];
  if ( !v12 )
  {
    v11 = -2147467261;
    v10 = 1834;
    v9 = -2147467261;
    goto LABEL_3;
  }
  v13 = SdpCatId(this[5], v12, &v45);
  v9 = v13;
  if ( v13 >= 0 )
    goto LABEL_12;
  v14 = 1837;
LABEL_9:
  SdpDebugTrace(1u, L"Rootcause::BuildReportXml", v14, v13);
LABEL_129:
  if ( v45 )
    operator delete(v45);
  return v9;
}

```

## disassembly

```asm
0x180018a9c  mov     [rsp-38h+arg_8], rbx
0x180018aa1  mov     [rsp-38h+arg_10], r8
0x180018aa6  mov     [rsp-38h+arg_0], rcx
0x180018aab  push    rbp
0x180018aac  push    rsi
0x180018aad  push    rdi
0x180018aae  push    r12
0x180018ab0  push    r13
0x180018ab2  push    r14
0x180018ab4  push    r15
0x180018ab6  mov     rbp, rsp
0x180018ab9  sub     rsp, 70h
0x180018abd  mov     r12, rcx
0x180018ac0  mov     r14, rdx
0x180018ac3  xor     ecx, ecx
0x180018ac5  mov     [rbp+var_20], rcx
0x180018ac9  mov     esi, ecx
0x180018acb  mov     [rbp+var_38], rcx
0x180018acf  mov     edi, ecx
0x180018ad1  mov     [rbp+var_28], rcx
0x180018ad5  mov     r15d, ecx
0x180018ad8  mov     [rbp+var_30], rcx
0x180018adc  mov     r13d, ecx
0x180018adf  mov     [rbp+var_40], rcx
0x180018ae3  mov     [rbp+Block], rcx
0x180018ae7  mov     [rbp+var_18], rcx
0x180018aeb  mov     [rbp+var_10], rcx
0x180018aef  test    r8, r8
0x180018af2  jnz     short loc_180018B18
0x180018af4  mov     ebx, 80070057h
0x180018af9  mov     r8d, 723h; int
0x180018aff  mov     r9d, ebx; int
0x180018b02  lea     rdx, aRootcauseBuild; "Rootcause::BuildReportXml"
0x180018b09  mov     ecx, 1; Level
0x180018b0e  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180018b13  jmp     loc_18001928A
0x180018b18  test    r14, r14
0x180018b1b  jz      short loc_180018B6A
0x180018b1d  mov     rdx, [rdx+10h]; unsigned __int16 *
0x180018b21  test    rdx, rdx
0x180018b24  jnz     short loc_180018B37
0x180018b26  mov     r9d, 80004003h
0x180018b2c  mov     r8d, 72Ah
0x180018b32  mov     ebx, r9d
0x180018b35  jmp     short loc_180018B02
0x180018b37  mov     rcx, [r12+28h]; unsigned __int16 *
0x180018b3c  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180018b40  call    ?SdpCatId@@YAJPEBG0PEAPEAG@Z; SdpCatId(ushort const *,ushort const *,ushort * *)
0x180018b45  mov     ebx, eax
0x180018b47  test    eax, eax
0x180018b49  jns     short loc_180018B86
0x180018b4b  mov     r8d, 72Dh; int
0x180018b51  mov     r9d, eax; int
0x180018b54  lea     rdx, aRootcauseBuild; "Rootcause::BuildReportXml"
0x180018b5b  mov     ecx, 1; Level
0x180018b60  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180018b65  jmp     loc_180019279
0x180018b6a  mov     rdx, [r12+28h]; unsigned __int16 *
0x180018b6f  lea     rcx, [rbp+var_18]; unsigned __int16 **
0x180018b73  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x180018b78  mov     ebx, eax
0x180018b7a  test    eax, eax
0x180018b7c  jns     short loc_180018B86
0x180018b7e  mov     r8d, 731h
0x180018b84  jmp     short loc_180018B51
0x180018b86  lea     rdx, [rbp+var_38]; struct IXMLDOMDocument2 **
0x180018b8a  lea     rcx, aXmlVersion10En_10; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180018b91  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180018b96  mov     ebx, eax
0x180018b98  test    eax, eax
0x180018b9a  jns     short loc_180018BBF
0x180018b9c  mov     r8d, 735h; int
0x180018ba2  mov     r9d, eax; int
0x180018ba5  lea     rdx, aRootcauseBuild; "Rootcause::BuildReportXml"
0x180018bac  mov     ecx, 1; Level
0x180018bb1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180018bb6  mov     rcx, [rbp+var_38]
0x180018bba  jmp     loc_180019211
0x180018bbf  mov     r9, [rbp+var_18]; unsigned __int16 *
0x180018bc3  lea     r8, aId_0; "id"
0x180018bca  mov     rcx, [rbp+var_38]; struct IXMLDOMDocument2 *
0x180018bce  xor     edx, edx; struct IXMLDOMElement *
0x180018bd0  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180018bd5  mov     ebx, eax
0x180018bd7  test    eax, eax
0x180018bd9  jns     short loc_180018BE3
0x180018bdb  mov     r8d, 738h
0x180018be1  jmp     short loc_180018BA2
0x180018be3  mov     rdx, [r12+38h]; unsigned __int16 *
0x180018be8  test    rdx, rdx
0x180018beb  jnz     short loc_180018BFE
0x180018bed  mov     r9d, 80004003h
0x180018bf3  mov     r8d, 73Ah
0x180018bf9  mov     ebx, r9d
0x180018bfc  jmp     short loc_180018BA5
0x180018bfe  test    r14, r14
0x180018c01  jz      short loc_180018C68
0x180018c03  cmp     [r14+18h], esi
0x180018c07  jz      short loc_180018C68
0x180018c09  mov     rdx, [r14+28h]; SAFEARRAY *
0x180018c0d  lea     r8, [r12+48h]; struct _SDIAG_PARAMSET *
0x180018c12  mov     rcx, [r14+20h]; psa
0x180018c16  call    ?SdpUpdateParamSet@@YAJPEAUtagSAFEARRAY@@0PEAU_SDIAG_PARAMSET@@@Z; SdpUpdateParamSet(tagSAFEARRAY *,tagSAFEARRAY *,_SDIAG_PARAMSET *)
0x180018c1b  mov     ebx, eax
0x180018c1d  test    eax, eax
0x180018c1f  jns     short loc_180018C2C
0x180018c21  mov     r8d, 740h
0x180018c27  jmp     loc_180018BA2
0x180018c2c  mov     rdx, [r12+38h]; unsigned __int16 *
0x180018c31  lea     r8, [r12+48h]; struct _SDIAG_PARAMSET *
0x180018c36  lea     rcx, [rbp+Block]; unsigned __int16 **
0x180018c3a  call    ?SdpSubstituteParamSet@@YAJPEAPEAGPEBGPEAU_SDIAG_PARAMSET@@@Z; SdpSubstituteParamSet(ushort * *,ushort const *,_SDIAG_PARAMSET *)
0x180018c3f  mov     ebx, eax
0x180018c41  test    eax, eax
0x180018c43  jns     short loc_180018C7F
0x180018c45  mov     r8d, 745h; int
0x180018c4b  mov     r9d, eax; int
0x180018c4e  lea     rdx, aRootcauseBuild; "Rootcause::BuildReportXml"
0x180018c55  mov     ecx, 1; Level
0x180018c5a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180018c5f  mov     r13, [rbp+Block]
0x180018c63  jmp     loc_180018BB6
0x180018c68  lea     rcx, [rbp+Block]; unsigned __int16 **
0x180018c6c  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x180018c71  mov     ebx, eax
0x180018c73  test    eax, eax
0x180018c75  jns     short loc_180018C7F
0x180018c77  mov     r8d, 749h
0x180018c7d  jmp     short loc_180018C4B
0x180018c7f  mov     r13, [rbp+Block]
0x180018c83  lea     r8, aName_0; "name"
0x180018c8a  mov     rcx, [rbp+var_38]; struct IXMLDOMDocument2 *
0x180018c8e  mov     r9, r13; unsigned __int16 *
0x180018c91  xor     edx, edx; struct IXMLDOMElement *
0x180018c93  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180018c98  mov     ebx, eax
0x180018c9a  test    eax, eax
0x180018c9c  jns     short loc_180018CA9
0x180018c9e  mov     r8d, 750h
0x180018ca4  jmp     loc_180018BA2
0x180018ca9  test    r13, r13
0x180018cac  jz      short loc_180018CBD
0x180018cae  mov     rcx, r13; Block
0x180018cb1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018cb6  xor     r13d, r13d
0x180018cb9  mov     [rbp+Block], r13
0x180018cbd  mov     rdx, [r12+40h]; unsigned __int16 *
0x180018cc2  test    rdx, rdx
0x180018cc5  jnz     short loc_180018CDB
0x180018cc7  mov     r9d, 80004003h
0x180018ccd  mov     r8d, 75Ch
0x180018cd3  mov     ebx, r9d
0x180018cd6  jmp     loc_180018BA5
0x180018cdb  test    r14, r14
0x180018cde  jz      short loc_180018D05
0x180018ce0  cmp     [r14+18h], esi
0x180018ce4  jz      short loc_180018D05
0x180018ce6  lea     r8, [r12+48h]; struct _SDIAG_PARAMSET *
0x180018ceb  lea     rcx, [rbp+Block]; unsigned __int16 **
0x180018cef  call    ?SdpSubstituteParamSet@@YAJPEAPEAGPEBGPEAU_SDIAG_PARAMSET@@@Z; SdpSubstituteParamSet(ushort * *,ushort const *,_SDIAG_PARAMSET *)
0x180018cf4  mov     ebx, eax
0x180018cf6  test    eax, eax
0x180018cf8  jns     short loc_180018D1F
0x180018cfa  mov     r8d, 762h
0x180018d00  jmp     loc_180018C4B
0x180018d05  lea     rcx, [rbp+Block]; unsigned __int16 **
0x180018d09  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x180018d0e  mov     ebx, eax
0x180018d10  test    eax, eax
0x180018d12  jns     short loc_180018D1F
0x180018d14  mov     r8d, 766h
0x180018d1a  jmp     loc_180018C4B
0x180018d1f  mov     r13, [rbp+Block]
0x180018d23  lea     rax, [rbp+var_30]
0x180018d27  mov     rcx, [rbp+var_38]; struct IXMLDOMDocument2 *
0x180018d2b  lea     r8, aData; "Data"
0x180018d32  mov     r9, r13; unsigned __int16 *
0x180018d35  mov     [rsp+70h+var_50], rax; struct IXMLDOMElement **
0x180018d3a  xor     edx, edx; struct IXMLDOMElement *
0x180018d3c  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180018d41  mov     ebx, eax
0x180018d43  test    eax, eax
0x180018d45  jns     short loc_180018D6A
0x180018d47  mov     r8d, 76Eh; int
0x180018d4d  mov     r9d, eax; int
0x180018d50  lea     rdx, aRootcauseBuild; "Rootcause::BuildReportXml"
0x180018d57  mov     ecx, 1; Level
0x180018d5c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180018d61  mov     rdi, [rbp+var_30]
0x180018d65  jmp     loc_180018BB6
0x180018d6a  mov     rdi, [rbp+var_30]
0x180018d6e  lea     r9, aDescription; "Description"
0x180018d75  mov     rdx, rdi; struct IXMLDOMElement *
0x180018d78  lea     r8, aId_0; "id"
0x180018d7f  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180018d81  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180018d86  mov     ebx, eax
0x180018d88  test    eax, eax
0x180018d8a  jns     short loc_180018D97
0x180018d8c  mov     r8d, 774h
0x180018d92  jmp     loc_180018BA2
0x180018d97  lea     r8, [rbp+var_40]; unsigned __int16 **
0x180018d9b  mov     edx, 76h ; 'v'; unsigned int
0x180018da0  xor     ecx, ecx; unsigned __int16 *
0x180018da2  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x180018da7  mov     ebx, eax
0x180018da9  test    eax, eax
0x180018dab  jns     short loc_180018DD0
0x180018dad  mov     r8d, 777h; int
0x180018db3  mov     r9d, eax; int
0x180018db6  lea     rdx, aRootcauseBuild; "Rootcause::BuildReportXml"
0x180018dbd  mov     ecx, 1; Level
0x180018dc2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180018dc7  mov     r15, [rbp+var_40]
0x180018dcb  jmp     loc_180018BB6
0x180018dd0  mov     r15, [rbp+var_40]
0x180018dd4  lea     r8, aName_0; "name"
0x180018ddb  mov     r9, r15; unsigned __int16 *
0x180018dde  mov     rdx, rdi; struct IXMLDOMElement *
0x180018de1  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180018de3  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180018de8  mov     ebx, eax
0x180018dea  test    eax, eax
0x180018dec  jns     short loc_180018DF9
0x180018dee  mov     r8d, 77Ah
0x180018df4  jmp     loc_180018BA2
0x180018df9  test    rdi, rdi
0x180018dfc  jz      short loc_180018E13
0x180018dfe  mov     rax, [rdi]
0x180018e01  mov     rcx, rdi
0x180018e04  mov     rax, [rax+10h]
0x180018e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e0d  xor     edi, edi
0x180018e0f  mov     [rbp+var_30], rdi
0x180018e13  test    r15, r15
0x180018e16  jz      short loc_180018E27
0x180018e18  mov     rcx, r15; Block
0x180018e1b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018e20  xor     r15d, r15d
0x180018e23  mov     [rbp+var_40], r15
0x180018e27  test    r14, r14
0x180018e2a  jz      short loc_180018E54
0x180018e2c  mov     edx, [r14+18h]
0x180018e30  test    edx, edx
0x180018e32  jz      short loc_180018E54
0x180018e34  lea     r8, [rbp+var_10]
0x180018e38  call    ?StatusToString@Rootcause@@AEAAJW4SDIAG_ROOTCAUSE_STATUS@1@PEAPEAG@Z; Rootcause::StatusToString(Rootcause::SDIAG_ROOTCAUSE_STATUS,ushort * *)
0x180018e3d  mov     ebx, eax
0x180018e3f  test    eax, eax
0x180018e41  jns     short loc_180018E4E
0x180018e43  mov     r8d, 785h
0x180018e49  jmp     loc_180018BA2
0x180018e4e  mov     r9, [rbp+var_10]
0x180018e52  jmp     short loc_180018E5B
0x180018e54  lea     r9, aNotChecked; "Not Checked"
0x180018e5b  mov     rcx, [rbp+var_38]; struct IXMLDOMDocument2 *
0x180018e5f  lea     rax, [rbp+var_30]
0x180018e63  lea     r8, aData; "Data"
0x180018e6a  mov     [rsp+70h+var_50], rax; struct IXMLDOMElement **
0x180018e6f  xor     edx, edx; struct IXMLDOMElement *
0x180018e71  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180018e76  mov     ebx, eax
0x180018e78  test    eax, eax
0x180018e7a  jns     short loc_180018E87
0x180018e7c  mov     r8d, 790h
0x180018e82  jmp     loc_180018D4D
0x180018e87  mov     rdi, [rbp+var_30]
0x180018e8b  lea     r9, aStatus; "Status"
0x180018e92  mov     rdx, rdi; struct IXMLDOMElement *
0x180018e95  lea     r8, aId_0; "id"
0x180018e9c  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180018e9e  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180018ea3  mov     ebx, eax
0x180018ea5  test    eax, eax
0x180018ea7  jns     short loc_180018EB4
0x180018ea9  mov     r8d, 796h
0x180018eaf  jmp     loc_180018BA2
0x180018eb4  lea     r8, [rbp+var_40]; unsigned __int16 **
0x180018eb8  mov     edx, 93h; unsigned int
0x180018ebd  xor     ecx, ecx; unsigned __int16 *
0x180018ebf  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x180018ec4  mov     ebx, eax
0x180018ec6  test    eax, eax
0x180018ec8  jns     short loc_180018ED5
0x180018eca  mov     r8d, 799h
0x180018ed0  jmp     loc_180018DB3
0x180018ed5  mov     r15, [rbp+var_40]
0x180018ed9  lea     r8, aName_0; "name"
0x180018ee0  mov     r9, r15; unsigned __int16 *
0x180018ee3  mov     rdx, rdi; struct IXMLDOMElement *
0x180018ee6  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180018ee8  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180018eed  mov     ebx, eax
0x180018eef  test    eax, eax
0x180018ef1  jns     short loc_180018EFE
0x180018ef3  mov     r8d, 79Ch
0x180018ef9  jmp     loc_180018BA2
0x180018efe  test    rdi, rdi
0x180018f01  jz      short loc_180018F16
0x180018f03  mov     rax, [rdi]
  ... truncated ...
```
