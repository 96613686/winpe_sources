# DiagPackage::BuildReportComputerXml(_OSVERSIONINFOEXW,_SYSTEM_INFO,IXMLDOMDocument2 * *)

- ea: `0x18001483c`
- end: `0x180014f76`
- name: `?BuildReportComputerXml@DiagPackage@@AEAAJU_OSVERSIONINFOEXW@@U_SYSTEM_INFO@@PEAPEAUIXMLDOMDocument2@@@Z`
- size: `1850`
- prototype: `__int64 __fastcall(DiagPackage *__hidden this, struct _OSVERSIONINFOEXW *__struct_ptr, struct _SYSTEM_INFO *__struct_ptr, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180015730`

## callees

- `0x1800012a4`
- `0x180002978`
- `0x180005ffc`
- `0x18001483c`
- `0x180026fa0`
- `0x1800280f8`
- `0x18002827c`
- `0x1800291e0`
- `0x1800298c0`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x18001490c`
- `KERNEL32!GetComputerNameExW` at `0x18001490c`
- `KERNEL32!GetLastError` at `0x180014916`
- `KERNEL32!GetLastError` at `0x180014916`

## string_xrefs

- `0x18001489b`: `DiagPackage::BuildReportComputerXml`
- `0x1800148d9`: `DiagPackage::BuildReportComputerXml`
- `0x18001496a`: `DiagPackage::BuildReportComputerXml`
- `0x1800149d7`: `DiagPackage::BuildReportComputerXml`
- `0x180014a46`: `DiagPackage::BuildReportComputerXml`
- `0x180014a8c`: `DiagPackage::BuildReportComputerXml`
- `0x180014bf3`: `DiagPackage::BuildReportComputerXml`
- `0x1800148be`: `<?xml version="1.0" encoding="utf-8"?><ComputerInformation/>`

## pseudocode

```c
__int64 __fastcall DiagPackage::BuildReportComputerXml(
        DiagPackage *this,
        struct _OSVERSIONINFOEXW *a2,
        struct _SYSTEM_INFO *a3,
        struct IXMLDOMDocument2 **a4)
{
  struct IXMLDOMElement *v6; // rsi
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // r9d
  int v10; // r8d
  struct IXMLDOMDocument2 *v11; // r12
  __int64 v12; // rdi
  signed int LastError; // eax
  int v14; // eax
  int v15; // r8d
  int v16; // eax
  int String; // eax
  int v18; // r8d
  void *v19; // r14
  int v20; // eax
  int v21; // r8d
  int v22; // r9d
  int wProductType; // ecx
  __int64 v24; // r15
  int v25; // ecx
  __int64 v26; // rax
  const wchar_t *v27; // rcx
  __int64 v28; // rdx
  WCHAR *v29; // r8
  WCHAR *v30; // rcx
  __int64 v31; // rax
  const wchar_t *v32; // rcx
  __int64 v33; // rdx
  WCHAR *v34; // r8
  WCHAR *v35; // rcx
  int v36; // eax
  int v37; // r8d
  __int64 v38; // rdx
  const wchar_t *v39; // rax
  WCHAR *v40; // rdx
  WCHAR *v41; // rcx
  const wchar_t *v42; // rax
  WCHAR *v43; // rdx
  WCHAR *v44; // rcx
  const wchar_t *v45; // rax
  WCHAR *v46; // rdx
  WCHAR *v47; // rcx
  const wchar_t *v48; // rax
  WCHAR *v49; // rdx
  WCHAR *v50; // rcx
  struct IXMLDOMElement *v52; // [rsp+30h] [rbp-D0h] BYREF
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  struct IXMLDOMDocument2 *v55; // [rsp+48h] [rbp-B8h] BYREF
  struct IXMLDOMDocument2 **v56; // [rsp+50h] [rbp-B0h]
  WCHAR Buffer[1024]; // [rsp+60h] [rbp-A0h] BYREF

  v56 = a4;
  v55 = 0;
  v52 = 0;
  Block = 0;
  v6 = 0;
  nSize = 0;
  if ( !a4 )
  {
    v7 = -2147024809;
    SdpDebugTrace(1u, L"DiagPackage::BuildReportComputerXml", 1817, -2147024809);
    return v7;
  }
  v8 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><ComputerInformation/>", &v55);
  v7 = v8;
  if ( v8 >= 0 )
  {
    v12 = 1024;
    nSize = 1024;
    if ( !GetComputerNameExW(ComputerNamePhysicalNetBIOS, Buffer, &nSize) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v10 = 1833;
      if ( (v7 & 0x80000000) == 0 )
        v7 = -2147467259;
      v9 = v7;
      goto LABEL_5;
    }
    v11 = v55;
    v14 = SdpXmlSetAttribute(v55, 0, L"name", Buffer);
    v7 = v14;
    if ( v14 < 0 )
    {
      v15 = 1839;
LABEL_14:
      SdpDebugTrace(1u, L"DiagPackage::BuildReportComputerXml", v15, v14);
      goto LABEL_110;
    }
    v14 = StringCchPrintfW(Buffer, 0x400u, L"%u.%u", a2->dwMajorVersion, a2->dwMinorVersion);
    v7 = v14;
    if ( v14 < 0 )
    {
      v15 = 1853;
      goto LABEL_14;
    }
    v16 = SdpXmlCreateNode(v11, 0, L"Data", Buffer, &v52);
    v7 = v16;
    if ( v16 < 0 )
    {
      SdpDebugTrace(1u, L"DiagPackage::BuildReportComputerXml", 1860, v16);
      v6 = v52;
      goto LABEL_110;
    }
    v6 = v52;
    v14 = SdpXmlSetAttribute(0, v52, L"id", L"Version");
    v7 = v14;
    if ( v14 < 0 )
    {
      v15 = 1866;
      goto LABEL_14;
    }
    String = SdpLoadString(0, 0x6Fu, (unsigned __int16 **)&Block);
    v7 = String;
    if ( String < 0 )
    {
      v18 = 1869;
LABEL_23:
      SdpDebugTrace(1u, L"DiagPackage::BuildReportComputerXml", v18, String);
      v19 = Block;
      goto LABEL_108;
    }
    v19 = Block;
    v20 = SdpXmlSetAttribute(0, v6, L"name", (const unsigned __int16 *)Block);
    v7 = v20;
    if ( v20 < 0 )
    {
      v21 = 1872;
LABEL_26:
      v22 = v20;
LABEL_27:
      SdpDebugTrace(1u, L"DiagPackage::BuildReportComputerXml", v21, v22);
      goto LABEL_108;
    }
    if ( v19 )
    {
      operator delete(v19);
      v19 = 0;
      Block = 0;
    }
    if ( v6 )
    {
      ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
      v6 = 0;
      v52 = 0;
    }
    wProductType = a2->wProductType;
    v24 = 2147483646;
    v25 = wProductType - 1;
    if ( v25 )
    {
      if ( (unsigned int)(v25 - 1) <= 1 )
      {
        v26 = 2147483646;
        v27 = L"Server";
        v28 = 1024;
        v29 = Buffer;
        do
        {
          if ( !v26 )
            break;
          if ( !*v27 )
            break;
          *v29++ = *v27++;
          --v26;
          --v28;
        }
        while ( v28 );
        v30 = v29 - 1;
        v7 = v28 == 0 ? 0x8007007A : 0;
        if ( v28 )
          v30 = v29;
        *v30 = 0;
        if ( !v28 )
        {
          v22 = -2147024774;
          v21 = 1885;
          goto LABEL_27;
        }
      }
    }
    else
    {
      v31 = 2147483646;
      v32 = L"Client";
      v33 = 1024;
      v34 = Buffer;
      do
      {
        if ( !v31 )
          break;
        if ( !*v32 )
          break;
        *v34++ = *v32++;
        --v31;
        --v33;
      }
      while ( v33 );
      v35 = v34 - 1;
      v7 = v33 == 0 ? 0x8007007A : 0;
      if ( v33 )
        v35 = v34;
      *v35 = 0;
      if ( !v33 )
      {
        v22 = -2147024774;
        v21 = 1889;
        goto LABEL_27;
      }
    }
    v36 = SdpXmlCreateNode(v11, 0, L"Data", Buffer, &v52);
    v7 = v36;
    if ( v36 >= 0 )
    {
      v6 = v52;
      v20 = SdpXmlSetAttribute(0, v52, L"id", L"SKU");
      v7 = v20;
      if ( v20 < 0 )
      {
        v21 = 1906;
        goto LABEL_26;
      }
      String = SdpLoadString(0, 0x70u, (unsigned __int16 **)&Block);
      v7 = String;
      if ( String < 0 )
      {
        v18 = 1909;
        goto LABEL_23;
      }
      v19 = Block;
      v20 = SdpXmlSetAttribute(0, v6, L"name", (const unsigned __int16 *)Block);
      v7 = v20;
      if ( v20 < 0 )
      {
        v21 = 1912;
        goto LABEL_26;
      }
      if ( v19 )
      {
        operator delete(v19);
        v19 = 0;
        Block = 0;
      }
      if ( v6 )
      {
        ((void (__fastcall *)(struct IXMLDOMElement *, __int64, _QWORD))v6->lpVtbl->Release)(v6, v38, 0);
        v6 = 0;
        v52 = 0;
      }
      if ( a3->wProcessorArchitecture )
      {
        switch ( a3->wProcessorArchitecture )
        {
          case 5u:
            v45 = L"arm";
            v46 = Buffer;
            do
            {
              if ( !v24 )
                break;
              if ( !*v45 )
                break;
              *v46++ = *v45++;
              --v24;
              --v12;
            }
            while ( v12 );
            v47 = v46 - 1;
            v7 = v12 == 0 ? 0x8007007A : 0;
            if ( v12 )
              v47 = v46;
            *v47 = 0;
            if ( !v12 )
            {
              v22 = -2147024774;
              v21 = 1932;
              goto LABEL_27;
            }
            break;
          case 6u:
            v42 = L"ia64";
            v43 = Buffer;
            do
            {
              if ( !v24 )
                break;
              if ( !*v42 )
                break;
              *v43++ = *v42++;
              --v24;
              --v12;
            }
            while ( v12 );
            v44 = v43 - 1;
            v7 = v12 == 0 ? 0x8007007A : 0;
            if ( v12 )
              v44 = v43;
            *v44 = 0;
            if ( !v12 )
            {
              v22 = -2147024774;
              v21 = 1936;
              goto LABEL_27;
            }
            break;
          case 9u:
            v39 = L"x64";
            v40 = Buffer;
            do
            {
              if ( !v24 )
                break;
              if ( !*v39 )
                break;
              *v40++ = *v39++;
              --v24;
              --v12;
            }
            while ( v12 );
            v41 = v40 - 1;
            v7 = v12 == 0 ? 0x8007007A : 0;
            if ( v12 )
              v41 = v40;
            *v41 = 0;
            if ( !v12 )
            {
              v22 = -2147024774;
              v21 = 1928;
              goto LABEL_27;
            }
            break;
        }
      }
      else
      {
        v48 = L"x86";
        v49 = Buffer;
        do
        {
          if ( !v24 )
            break;
          if ( !*v48 )
            break;
          *v49++ = *v48++;
          --v24;
          --v12;
        }
        while ( v12 );
        v50 = v49 - 1;
        v7 = v12 == 0 ? 0x8007007A : 0;
        if ( v12 )
          v50 = v49;
        *v50 = 0;
        if ( !v12 )
        {
          v22 = -2147024774;
          v21 = 1924;
          goto LABEL_27;
        }
      }
      v36 = SdpXmlCreateNode(v11, 0, L"Data", Buffer, &v52);
      v7 = v36;
      if ( v36 >= 0 )
      {
        v6 = v52;
        v20 = SdpXmlSetAttribute(0, v52, L"id", L"Architecture");
        v7 = v20;
        if ( v20 < 0 )
        {
          v21 = 1953;
          goto LABEL_26;
        }
        String = SdpLoadString(0, 0x71u, (unsigned __int16 **)&Block);
        v7 = String;
        if ( String < 0 )
        {
          v18 = 1956;
          goto LABEL_23;
        }
        v19 = Block;
        v20 = SdpXmlSetAttribute(0, v6, L"name", (const unsigned __int16 *)Block);
        v7 = v20;
        if ( v20 < 0 )
        {
          v21 = 1959;
          goto LABEL_26;
        }
        *v56 = v11;
        v11 = 0;
LABEL_108:
        if ( v19 )
          operator delete(v19);
        goto LABEL_110;
      }
      v37 = 1947;
    }
    else
    {
      v37 = 1900;
    }
    SdpDebugTrace(1u, L"DiagPackage::BuildReportComputerXml", v37, v36);
    v6 = v52;
    goto LABEL_108;
  }
  v9 = v8;
  v10 = 1824;
LABEL_5:
  SdpDebugTrace(1u, L"DiagPackage::BuildReportComputerXml", v10, v9);
  v11 = v55;
LABEL_110:
  if ( v11 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v11->lpVtbl->Release)(v11);
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
  return v7;
}

```

## disassembly

```asm
0x18001483c  mov     [rsp-8+arg_0], rbx
0x180014841  push    rbp
0x180014842  push    rsi
0x180014843  push    rdi
0x180014844  push    r12
0x180014846  push    r13
0x180014848  push    r14
0x18001484a  push    r15
0x18001484c  lea     rbp, [rsp-770h]
0x180014854  sub     rsp, 870h
0x18001485b  mov     rax, cs:__security_cookie
0x180014862  xor     rax, rsp
0x180014865  mov     [rbp+7A0h+var_40], rax
0x18001486c  xor     r14d, r14d
0x18001486f  mov     [rsp+8A0h+var_850], r9
0x180014874  mov     [rsp+8A0h+var_858], r14
0x180014879  mov     r13, r8
0x18001487c  mov     [rsp+8A0h+var_870], r14
0x180014881  mov     r15, rdx
0x180014884  mov     [rsp+8A0h+Block], r14
0x180014889  mov     esi, r14d
0x18001488c  mov     [rsp+8A0h+nSize], r14d
0x180014891  test    r9, r9
0x180014894  jnz     short loc_1800148B9
0x180014896  mov     ebx, 80070057h
0x18001489b  lea     rdx, aDiagpackageBui; "DiagPackage::BuildReportComputerXml"
0x1800148a2  mov     r9d, ebx; int
0x1800148a5  lea     ecx, [r14+1]; Level
0x1800148a9  mov     r8d, 719h; int
0x1800148af  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800148b4  jmp     loc_180014F4A
0x1800148b9  lea     rdx, [rsp+8A0h+var_858]; struct IXMLDOMDocument2 **
0x1800148be  lea     rcx, aXmlVersion10En_8; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x1800148c5  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x1800148ca  mov     ebx, eax
0x1800148cc  test    eax, eax
0x1800148ce  jns     short loc_1800148F4
0x1800148d0  mov     r9d, eax; int
0x1800148d3  mov     r8d, 720h; int
0x1800148d9  lea     rdx, aDiagpackageBui; "DiagPackage::BuildReportComputerXml"
0x1800148e0  mov     ecx, 1; Level
0x1800148e5  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800148ea  mov     r12, [rsp+8A0h+var_858]
0x1800148ef  jmp     loc_180014F21
0x1800148f4  mov     edi, 400h
0x1800148f9  lea     r8, [rsp+8A0h+nSize]; nSize
0x1800148fe  lea     rdx, [rsp+8A0h+Buffer]; lpBuffer
0x180014903  mov     [rsp+8A0h+nSize], edi
0x180014907  mov     ecx, 4; NameType
0x18001490c  call    cs:__imp_GetComputerNameExW
0x180014912  test    eax, eax
0x180014914  jnz     short loc_180014940
0x180014916  call    cs:__imp_GetLastError
0x18001491c  mov     ebx, eax
0x18001491e  test    eax, eax
0x180014920  jle     short loc_18001492B
0x180014922  movzx   ebx, ax
0x180014925  or      ebx, 80070000h
0x18001492b  test    ebx, ebx
0x18001492d  mov     eax, 80004005h
0x180014932  mov     r8d, 729h
0x180014938  cmovns  ebx, eax
0x18001493b  mov     r9d, ebx
0x18001493e  jmp     short loc_1800148D9
0x180014940  mov     r12, [rsp+8A0h+var_858]
0x180014945  lea     r9, [rsp+8A0h+Buffer]; unsigned __int16 *
0x18001494a  mov     rcx, r12; struct IXMLDOMDocument2 *
0x18001494d  lea     r8, aName_0; "name"
0x180014954  xor     edx, edx; struct IXMLDOMElement *
0x180014956  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001495b  mov     ebx, eax
0x18001495d  test    eax, eax
0x18001495f  jns     short loc_180014980
0x180014961  mov     r8d, 72Fh; int
0x180014967  mov     r9d, eax; int
0x18001496a  lea     rdx, aDiagpackageBui; "DiagPackage::BuildReportComputerXml"
0x180014971  mov     ecx, 1; Level
0x180014976  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001497b  jmp     loc_180014F21
0x180014980  mov     eax, [r15+8]
0x180014984  lea     r8, aUU; "%u.%u"
0x18001498b  mov     r9d, [r15+4]
0x18001498f  lea     rcx, [rsp+8A0h+Buffer]; unsigned __int16 *
0x180014994  mov     rdx, rdi; unsigned __int64
0x180014997  mov     dword ptr [rsp+8A0h+var_880], eax
0x18001499b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800149a0  mov     ebx, eax
0x1800149a2  test    eax, eax
0x1800149a4  jns     short loc_1800149AE
0x1800149a6  mov     r8d, 73Dh
0x1800149ac  jmp     short loc_180014967
0x1800149ae  lea     rax, [rsp+8A0h+var_870]
0x1800149b3  xor     edx, edx; struct IXMLDOMElement *
0x1800149b5  lea     r9, [rsp+8A0h+Buffer]; unsigned __int16 *
0x1800149ba  mov     [rsp+8A0h+var_880], rax; struct IXMLDOMElement **
0x1800149bf  lea     r8, aData; "Data"
0x1800149c6  mov     rcx, r12; struct IXMLDOMDocument2 *
0x1800149c9  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800149ce  mov     ebx, eax
0x1800149d0  test    eax, eax
0x1800149d2  jns     short loc_1800149F8
0x1800149d4  mov     r9d, eax; int
0x1800149d7  lea     rdx, aDiagpackageBui; "DiagPackage::BuildReportComputerXml"
0x1800149de  mov     r8d, 744h; int
0x1800149e4  mov     ecx, 1; Level
0x1800149e9  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800149ee  mov     rsi, [rsp+8A0h+var_870]
0x1800149f3  jmp     loc_180014F21
0x1800149f8  mov     rsi, [rsp+8A0h+var_870]
0x1800149fd  lea     r9, aVersion; "Version"
0x180014a04  mov     rdx, rsi; struct IXMLDOMElement *
0x180014a07  lea     r8, aId_0; "id"
0x180014a0e  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180014a10  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180014a15  mov     ebx, eax
0x180014a17  test    eax, eax
0x180014a19  jns     short loc_180014A26
0x180014a1b  mov     r8d, 74Ah
0x180014a21  jmp     loc_180014967
0x180014a26  lea     r8, [rsp+8A0h+Block]; unsigned __int16 **
0x180014a2b  mov     edx, 6Fh ; 'o'; unsigned int
0x180014a30  xor     ecx, ecx; unsigned __int16 *
0x180014a32  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x180014a37  mov     ebx, eax
0x180014a39  test    eax, eax
0x180014a3b  jns     short loc_180014A61
0x180014a3d  mov     r8d, 74Dh; int
0x180014a43  mov     r9d, eax; int
0x180014a46  lea     rdx, aDiagpackageBui; "DiagPackage::BuildReportComputerXml"
0x180014a4d  mov     ecx, 1; Level
0x180014a52  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180014a57  mov     r14, [rsp+8A0h+Block]
0x180014a5c  jmp     loc_180014F14
0x180014a61  mov     r14, [rsp+8A0h+Block]
0x180014a66  lea     r8, aName_0; "name"
0x180014a6d  mov     r9, r14; unsigned __int16 *
0x180014a70  mov     rdx, rsi; struct IXMLDOMElement *
0x180014a73  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180014a75  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180014a7a  xor     r10d, r10d
0x180014a7d  mov     ebx, eax
0x180014a7f  test    eax, eax
0x180014a81  jns     short loc_180014AA2
0x180014a83  mov     r8d, 750h; int
0x180014a89  mov     r9d, eax; int
0x180014a8c  lea     rdx, aDiagpackageBui; "DiagPackage::BuildReportComputerXml"
0x180014a93  mov     ecx, 1; Level
0x180014a98  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180014a9d  jmp     loc_180014F14
0x180014aa2  test    r14, r14
0x180014aa5  jz      short loc_180014ABA
0x180014aa7  mov     rcx, r14; Block
0x180014aaa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014aaf  xor     r10d, r10d
0x180014ab2  mov     r14d, r10d
0x180014ab5  mov     [rsp+8A0h+Block], r10
0x180014aba  test    rsi, rsi
0x180014abd  jz      short loc_180014AD9
0x180014abf  mov     rax, [rsi]
0x180014ac2  mov     rcx, rsi
0x180014ac5  mov     rax, [rax+10h]
0x180014ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ace  xor     r10d, r10d
0x180014ad1  mov     esi, r10d
0x180014ad4  mov     [rsp+8A0h+var_870], r10
0x180014ad9  movzx   ecx, byte ptr [r15+11Ah]
0x180014ae1  mov     r11d, 8007007Ah
0x180014ae7  mov     r15d, 7FFFFFFEh
0x180014aed  sub     ecx, 1
0x180014af0  jz      short loc_180014B62
0x180014af2  sub     ecx, 1
0x180014af5  jz      short loc_180014B00
0x180014af7  cmp     ecx, 1
0x180014afa  jnz     loc_180014BC4
0x180014b00  mov     rax, r15
0x180014b03  lea     rcx, aServer; "Server"
0x180014b0a  mov     rdx, rdi
0x180014b0d  lea     r8, [rsp+8A0h+Buffer]
0x180014b12  test    rax, rax
0x180014b15  jz      short loc_180014B36
0x180014b17  movzx   r9d, word ptr [rcx]
0x180014b1b  test    r9w, r9w
0x180014b1f  jz      short loc_180014B36
0x180014b21  mov     [r8], r9w
0x180014b25  add     rcx, 2
0x180014b29  add     r8, 2
0x180014b2d  dec     rax
0x180014b30  sub     rdx, 1
0x180014b34  jnz     short loc_180014B12
0x180014b36  mov     rax, rdx
0x180014b39  lea     rcx, [r8-2]
0x180014b3d  neg     rax
0x180014b40  sbb     ebx, ebx
0x180014b42  not     ebx
0x180014b44  and     ebx, r11d
0x180014b47  test    rdx, rdx
0x180014b4a  cmovnz  rcx, r8
0x180014b4e  mov     [rcx], r10w
0x180014b52  jnz     short loc_180014BC4
0x180014b54  mov     r9d, ebx
0x180014b57  mov     r8d, 75Dh
0x180014b5d  jmp     loc_180014A8C
0x180014b62  mov     rax, r15
0x180014b65  lea     rcx, aClient; "Client"
0x180014b6c  mov     rdx, rdi
0x180014b6f  lea     r8, [rsp+8A0h+Buffer]
0x180014b74  test    rax, rax
0x180014b77  jz      short loc_180014B98
0x180014b79  movzx   r9d, word ptr [rcx]
0x180014b7d  test    r9w, r9w
0x180014b81  jz      short loc_180014B98
0x180014b83  mov     [r8], r9w
0x180014b87  add     rcx, 2
0x180014b8b  add     r8, 2
0x180014b8f  dec     rax
0x180014b92  sub     rdx, 1
0x180014b96  jnz     short loc_180014B74
0x180014b98  mov     rax, rdx
0x180014b9b  lea     rcx, [r8-2]
0x180014b9f  neg     rax
0x180014ba2  sbb     ebx, ebx
0x180014ba4  not     ebx
0x180014ba6  and     ebx, r11d
0x180014ba9  test    rdx, rdx
0x180014bac  cmovnz  rcx, r8
0x180014bb0  mov     [rcx], r10w
0x180014bb4  jnz     short loc_180014BC4
0x180014bb6  mov     r9d, ebx
0x180014bb9  mov     r8d, 761h
0x180014bbf  jmp     loc_180014A8C
0x180014bc4  lea     rax, [rsp+8A0h+var_870]
0x180014bc9  xor     edx, edx; struct IXMLDOMElement *
0x180014bcb  lea     r9, [rsp+8A0h+Buffer]; unsigned __int16 *
0x180014bd0  mov     [rsp+8A0h+var_880], rax; struct IXMLDOMElement **
0x180014bd5  lea     r8, aData; "Data"
0x180014bdc  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180014bdf  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180014be4  mov     ebx, eax
0x180014be6  test    eax, eax
0x180014be8  jns     short loc_180014C0E
0x180014bea  mov     r8d, 76Ch; int
0x180014bf0  mov     r9d, eax; int
0x180014bf3  lea     rdx, aDiagpackageBui; "DiagPackage::BuildReportComputerXml"
0x180014bfa  mov     ecx, 1; Level
0x180014bff  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180014c04  mov     rsi, [rsp+8A0h+var_870]
0x180014c09  jmp     loc_180014F14
0x180014c0e  mov     rsi, [rsp+8A0h+var_870]
0x180014c13  lea     r9, aSku; "SKU"
0x180014c1a  mov     rdx, rsi; struct IXMLDOMElement *
0x180014c1d  lea     r8, aId_0; "id"
0x180014c24  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180014c26  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180014c2b  mov     ebx, eax
0x180014c2d  test    eax, eax
0x180014c2f  jns     short loc_180014C3C
0x180014c31  mov     r8d, 772h
0x180014c37  jmp     loc_180014A89
0x180014c3c  lea     r8, [rsp+8A0h+Block]; unsigned __int16 **
0x180014c41  mov     edx, 70h ; 'p'; unsigned int
0x180014c46  xor     ecx, ecx; unsigned __int16 *
0x180014c48  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x180014c4d  mov     ebx, eax
0x180014c4f  test    eax, eax
0x180014c51  jns     short loc_180014C5E
0x180014c53  mov     r8d, 775h
0x180014c59  jmp     loc_180014A43
0x180014c5e  mov     r14, [rsp+8A0h+Block]
0x180014c63  lea     r8, aName_0; "name"
0x180014c6a  mov     r9, r14; unsigned __int16 *
0x180014c6d  mov     rdx, rsi; struct IXMLDOMElement *
0x180014c70  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180014c72  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180014c77  xor     r8d, r8d
0x180014c7a  mov     ebx, eax
0x180014c7c  test    eax, eax
0x180014c7e  jns     short loc_180014C8B
0x180014c80  mov     r8d, 778h
0x180014c86  jmp     loc_180014A89
0x180014c8b  test    r14, r14
0x180014c8e  jz      short loc_180014CA3
0x180014c90  mov     rcx, r14; Block
0x180014c93  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014c98  xor     r8d, r8d
0x180014c9b  mov     r14d, r8d
0x180014c9e  mov     [rsp+8A0h+Block], r8
0x180014ca3  test    rsi, rsi
0x180014ca6  jz      short loc_180014CC2
0x180014ca8  mov     rax, [rsi]
0x180014cab  mov     rcx, rsi
0x180014cae  mov     rax, [rax+10h]
0x180014cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cb7  xor     r8d, r8d
0x180014cba  mov     esi, r8d
0x180014cbd  mov     [rsp+8A0h+var_870], r8
0x180014cc2  movzx   ecx, word ptr [r13+0]
0x180014cc7  test    ecx, ecx
0x180014cc9  jz      loc_180014E02
0x180014ccf  sub     ecx, 5
0x180014cd2  jz      loc_180014DA6
  ... truncated ...
```
