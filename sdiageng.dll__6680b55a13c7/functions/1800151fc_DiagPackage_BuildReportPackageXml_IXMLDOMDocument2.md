# DiagPackage::BuildReportPackageXml(IXMLDOMDocument2 * *)

- ea: `0x1800151fc`
- end: `0x180015728`
- name: `?BuildReportPackageXml@DiagPackage@@AEAAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `1324`
- prototype: `__int64 __fastcall(DiagPackage *__hidden this, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180016630`

## callees

- `0x1800012a4`
- `0x180005ffc`
- `0x1800151fc`
- `0x18001e75c`
- `0x18001e8b0`
- `0x180026fa0`
- `0x1800280f8`
- `0x18002827c`
- `0x1800291e0`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800152ea`
- `OLEAUT32!__imp_SysAllocString` at `0x1800154b5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800152ea`
- `OLEAUT32!__imp_SysAllocString` at `0x1800154b5`
- `OLEAUT32!__imp_SysFreeString` at `0x180015373`
- `OLEAUT32!__imp_SysFreeString` at `0x1800155e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156ba`
- `OLEAUT32!__imp_SysFreeString` at `0x180015373`
- `OLEAUT32!__imp_SysFreeString` at `0x1800155e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156ba`

## string_xrefs

- `0x180015247`: `DiagPackage::BuildReportPackageXml`
- `0x180015289`: `DiagPackage::BuildReportPackageXml`
- `0x1800152bf`: `DiagPackage::BuildReportPackageXml`
- `0x1800152fe`: `DiagPackage::BuildReportPackageXml`
- `0x18001535a`: `DiagPackage::BuildReportPackageXml`
- `0x18001548e`: `DiagPackage::BuildReportPackageXml`
- `0x1800154c9`: `DiagPackage::BuildReportPackageXml`
- `0x18001551c`: `DiagPackage::BuildReportPackageXml`
- `0x180015582`: `DiagPackage::BuildReportPackageXml`
- `0x1800156a3`: `DiagPackage::BuildReportPackageXml`
- `0x180015274`: `<?xml version="1.0" encoding="utf-8"?><PackageInformation/>`

## pseudocode

```c
__int64 __fastcall DiagPackage::BuildReportPackageXml(DiagPackage *this, struct IXMLDOMDocument2 **a2)
{
  struct IXMLDOMElement *v3; // rdi
  void *v4; // rsi
  unsigned int v5; // ebx
  int v6; // r8d
  int v7; // eax
  struct IXMLDOMDocument2 *v8; // r15
  int PackageId; // eax
  OLECHAR *v10; // r14
  unsigned __int16 *v11; // r12
  int v12; // eax
  int v13; // r8d
  int String; // eax
  int v15; // r8d
  int PackagePublisher; // eax
  int v17; // eax
  int v18; // eax
  OLECHAR *psz; // [rsp+30h] [rbp-10h] BYREF
  struct IXMLDOMDocument2 *v21; // [rsp+38h] [rbp-8h] BYREF
  struct IXMLDOMElement *v23; // [rsp+90h] [rbp+50h] BYREF
  void *Block; // [rsp+98h] [rbp+58h] BYREF

  v21 = 0;
  v3 = 0;
  v23 = 0;
  v4 = 0;
  Block = 0;
  psz = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 2006;
LABEL_3:
    SdpDebugTrace(1u, L"DiagPackage::BuildReportPackageXml", v6, v5);
    return v5;
  }
  if ( !*((_QWORD *)this + 1) )
  {
    v5 = -2147467261;
    v6 = 2007;
    goto LABEL_3;
  }
  v7 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><PackageInformation/>", &v21);
  v5 = v7;
  if ( v7 >= 0 )
  {
    PackageId = Settings::get_PackageId(*((Settings **)this + 1), &psz);
    v5 = PackageId;
    if ( PackageId < 0 )
    {
      SdpDebugTrace(1u, L"DiagPackage::BuildReportPackageXml", 2021, PackageId);
      v8 = v21;
      v10 = psz;
      goto LABEL_62;
    }
    v10 = psz;
    v11 = SysAllocString(psz);
    if ( !v11 )
    {
      v5 = -2147024882;
      SdpDebugTrace(1u, L"DiagPackage::BuildReportPackageXml", 2024, -2147024882);
      v8 = v21;
LABEL_62:
      if ( v10 )
        operator delete(v10);
      goto LABEL_64;
    }
    if ( v10 )
    {
      operator delete(v10);
      v10 = 0;
      psz = 0;
    }
    v8 = v21;
    v12 = SdpXmlSetAttribute(v21, 0, L"id", v11);
    v5 = v12;
    if ( v12 < 0 )
    {
      v13 = 2031;
LABEL_16:
      SdpDebugTrace(1u, L"DiagPackage::BuildReportPackageXml", v13, v12);
LABEL_58:
      SysFreeString(v11);
      goto LABEL_60;
    }
    SysFreeString(v11);
    v11 = (unsigned __int16 *)*((_QWORD *)this + 6);
    String = SdpXmlSetAttribute(v8, 0, L"name", v11);
    v5 = String;
    if ( String >= 0 )
    {
      v11 = (unsigned __int16 *)*((_QWORD *)this + 11);
      String = SdpXmlCreateNode(v8, 0, L"Data", v11, &v23);
      v3 = v23;
      v5 = String;
      if ( String >= 0 )
      {
        String = SdpXmlSetAttribute(0, v23, L"id", L"Version");
        v5 = String;
        if ( String >= 0 )
        {
          String = SdpLoadString(0, 0x77u, (unsigned __int16 **)&Block);
          v4 = Block;
          v5 = String;
          if ( String >= 0 )
          {
            String = SdpXmlSetAttribute(0, v3, L"name", (const unsigned __int16 *)Block);
            v5 = String;
            if ( String >= 0 )
            {
              if ( v4 )
              {
                operator delete(v4);
                v4 = 0;
                Block = 0;
              }
              if ( v3 )
              {
                ((void (__fastcall *)(struct IXMLDOMElement *))v3->lpVtbl->Release)(v3);
                v3 = 0;
                v23 = 0;
              }
              PackagePublisher = Settings::get_PackagePublisher(*((Settings **)this + 1), &psz);
              v5 = PackagePublisher;
              if ( PackagePublisher < 0 )
              {
                SdpDebugTrace(1u, L"DiagPackage::BuildReportPackageXml", 2086, PackagePublisher);
                v10 = psz;
                goto LABEL_60;
              }
              v10 = psz;
              v11 = SysAllocString(psz);
              if ( !v11 )
              {
                v5 = -2147024882;
                SdpDebugTrace(1u, L"DiagPackage::BuildReportPackageXml", 2089, -2147024882);
                goto LABEL_60;
              }
              if ( v10 )
              {
                operator delete(v10);
                v10 = 0;
              }
              v17 = SdpXmlCreateNode(v8, 0, L"Data", v11, &v23);
              v5 = v17;
              if ( v17 < 0 )
              {
                SdpDebugTrace(1u, L"DiagPackage::BuildReportPackageXml", 2097, v17);
                v3 = v23;
                goto LABEL_58;
              }
              v3 = v23;
              v12 = SdpXmlSetAttribute(0, v23, L"id", L"Publisher");
              v5 = v12;
              if ( v12 < 0 )
              {
                v13 = 2103;
                goto LABEL_16;
              }
              v18 = SdpLoadString(0, 0x75u, (unsigned __int16 **)&Block);
              v5 = v18;
              if ( v18 < 0 )
              {
                SdpDebugTrace(1u, L"DiagPackage::BuildReportPackageXml", 2106, v18);
                v4 = Block;
                goto LABEL_58;
              }
              v4 = Block;
              v12 = SdpXmlSetAttribute(0, v3, L"name", (const unsigned __int16 *)Block);
              v5 = v12;
              if ( v12 < 0 )
              {
                v13 = 2109;
                goto LABEL_16;
              }
              if ( v4 )
              {
                operator delete(v4);
                v4 = 0;
                Block = 0;
              }
              SysFreeString(v11);
              if ( v3 )
              {
                ((void (__fastcall *)(struct IXMLDOMElement *))v3->lpVtbl->Release)(v3);
                v23 = 0;
              }
              v11 = (unsigned __int16 *)*((_QWORD *)this + 7);
              String = SdpXmlCreateNode(v8, 0, L"Data", v11, &v23);
              v3 = v23;
              v5 = String;
              if ( String >= 0 )
              {
                String = SdpXmlSetAttribute(0, v23, L"id", L"Description");
                v5 = String;
                if ( String >= 0 )
                {
                  String = SdpLoadString(0, 0x76u, (unsigned __int16 **)&Block);
                  v4 = Block;
                  v5 = String;
                  if ( String >= 0 )
                  {
                    String = SdpXmlSetAttribute(0, v3, L"name", (const unsigned __int16 *)Block);
                    v5 = String;
                    if ( String >= 0 )
                    {
                      *a2 = v8;
                      v8 = 0;
LABEL_60:
                      if ( v4 )
                        operator delete(v4);
                      goto LABEL_62;
                    }
                    v15 = 2138;
                  }
                  else
                  {
                    v15 = 2135;
                  }
                }
                else
                {
                  v15 = 2132;
                }
              }
              else
              {
                v15 = 2126;
              }
            }
            else
            {
              v15 = 2073;
            }
          }
          else
          {
            v15 = 2070;
          }
        }
        else
        {
          v15 = 2067;
        }
      }
      else
      {
        v15 = 2061;
      }
    }
    else
    {
      v15 = 2042;
    }
    SdpDebugTrace(1u, L"DiagPackage::BuildReportPackageXml", v15, String);
    if ( !v11 )
      goto LABEL_60;
    goto LABEL_58;
  }
  SdpDebugTrace(1u, L"DiagPackage::BuildReportPackageXml", 2014, v7);
  v8 = v21;
LABEL_64:
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v8->lpVtbl->Release)(v8);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v3->lpVtbl->Release)(v3);
  return v5;
}

```

## disassembly

```asm
0x1800151fc  mov     [rsp-38h+arg_0], rbx
0x180015201  mov     [rsp-38h+arg_8], rdx
0x180015206  push    rbp
0x180015207  push    rsi
0x180015208  push    rdi
0x180015209  push    r12
0x18001520b  push    r13
0x18001520d  push    r14
0x18001520f  push    r15
0x180015211  mov     rbp, rsp
0x180015214  sub     rsp, 40h
0x180015218  xor     r15d, r15d
0x18001521b  mov     r13, rcx
0x18001521e  mov     [rbp+var_8], r15
0x180015222  mov     edi, r15d
0x180015225  mov     [rbp+arg_10], r15
0x180015229  mov     esi, r15d
0x18001522c  mov     [rbp+Block], r15
0x180015230  mov     [rbp+psz], r15
0x180015234  test    rdx, rdx
0x180015237  jnz     short loc_18001525D
0x180015239  mov     ebx, 80070057h
0x18001523e  mov     r8d, 7D6h; int
0x180015244  mov     r9d, ebx; int
0x180015247  lea     rdx, aDiagpackageBui_0; "DiagPackage::BuildReportPackageXml"
0x18001524e  mov     ecx, 1; Level
0x180015253  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180015258  jmp     loc_18001570E
0x18001525d  cmp     [rcx+8], r15
0x180015261  jnz     short loc_180015270
0x180015263  mov     ebx, 80004003h
0x180015268  mov     r8d, 7D7h
0x18001526e  jmp     short loc_180015244
0x180015270  lea     rdx, [rbp+var_8]; struct IXMLDOMDocument2 **
0x180015274  lea     rcx, aXmlVersion10En_3; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18001527b  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180015280  mov     ebx, eax
0x180015282  test    eax, eax
0x180015284  jns     short loc_1800152A9
0x180015286  mov     r9d, eax; int
0x180015289  lea     rdx, aDiagpackageBui_0; "DiagPackage::BuildReportPackageXml"
0x180015290  mov     r8d, 7DEh; int
0x180015296  mov     ecx, 1; Level
0x18001529b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800152a0  mov     r15, [rbp+var_8]
0x1800152a4  jmp     loc_1800156E6
0x1800152a9  mov     rcx, [r13+8]; this
0x1800152ad  lea     rdx, [rbp+psz]; unsigned __int16 **
0x1800152b1  call    ?get_PackageId@Settings@@QEAAJPEAPEAG@Z; Settings::get_PackageId(ushort * *)
0x1800152b6  mov     ebx, eax
0x1800152b8  test    eax, eax
0x1800152ba  jns     short loc_1800152E3
0x1800152bc  mov     r9d, eax; int
0x1800152bf  lea     rdx, aDiagpackageBui_0; "DiagPackage::BuildReportPackageXml"
0x1800152c6  mov     r8d, 7E5h; int
0x1800152cc  mov     ecx, 1; Level
0x1800152d1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800152d6  mov     r15, [rbp+var_8]
0x1800152da  mov     r14, [rbp+psz]
0x1800152de  jmp     loc_1800156D9
0x1800152e3  mov     r14, [rbp+psz]
0x1800152e7  mov     rcx, r14; psz
0x1800152ea  call    cs:__imp_SysAllocString
0x1800152f0  mov     r12, rax
0x1800152f3  test    rax, rax
0x1800152f6  jnz     short loc_18001531F
0x1800152f8  mov     r9d, 8007000Eh; int
0x1800152fe  lea     rdx, aDiagpackageBui_0; "DiagPackage::BuildReportPackageXml"
0x180015305  mov     r8d, 7E8h; int
0x18001530b  lea     ecx, [rax+1]; Level
0x18001530e  mov     ebx, r9d
0x180015311  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180015316  mov     r15, [rbp+var_8]
0x18001531a  jmp     loc_1800156D9
0x18001531f  test    r14, r14
0x180015322  jz      short loc_180015333
0x180015324  mov     rcx, r14; Block
0x180015327  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001532c  mov     r14, r15
0x18001532f  mov     [rbp+psz], r15
0x180015333  mov     r15, [rbp+var_8]
0x180015337  lea     r8, aId_0; "id"
0x18001533e  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180015341  mov     r9, r12; unsigned __int16 *
0x180015344  xor     edx, edx; struct IXMLDOMElement *
0x180015346  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001534b  mov     ebx, eax
0x18001534d  test    eax, eax
0x18001534f  jns     short loc_180015370
0x180015351  mov     r8d, 7EFh; int
0x180015357  mov     r9d, eax; int
0x18001535a  lea     rdx, aDiagpackageBui_0; "DiagPackage::BuildReportPackageXml"
0x180015361  mov     ecx, 1; Level
0x180015366  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001536b  jmp     loc_1800156B7
0x180015370  mov     rcx, r12; bstrString
0x180015373  call    cs:__imp_SysFreeString
0x180015379  mov     r12, [r13+30h]
0x18001537d  lea     r8, aName_0; "name"
0x180015384  mov     r9, r12; unsigned __int16 *
0x180015387  xor     edx, edx; struct IXMLDOMElement *
0x180015389  mov     rcx, r15; struct IXMLDOMDocument2 *
0x18001538c  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180015391  mov     ebx, eax
0x180015393  test    eax, eax
0x180015395  jns     short loc_1800153A2
0x180015397  mov     r8d, 7FAh
0x18001539d  jmp     loc_18001569E
0x1800153a2  mov     r12, [r13+58h]
0x1800153a6  lea     rax, [rbp+arg_10]
0x1800153aa  mov     r9, r12; unsigned __int16 *
0x1800153ad  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x1800153b2  lea     r8, aData; "Data"
0x1800153b9  xor     edx, edx; struct IXMLDOMElement *
0x1800153bb  mov     rcx, r15; struct IXMLDOMDocument2 *
0x1800153be  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800153c3  mov     rdi, [rbp+arg_10]
0x1800153c7  mov     ebx, eax
0x1800153c9  test    eax, eax
0x1800153cb  jns     short loc_1800153D8
0x1800153cd  mov     r8d, 80Dh
0x1800153d3  jmp     loc_18001569E
0x1800153d8  lea     r9, aVersion; "Version"
0x1800153df  mov     rdx, rdi; struct IXMLDOMElement *
0x1800153e2  lea     r8, aId_0; "id"
0x1800153e9  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x1800153eb  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x1800153f0  mov     ebx, eax
0x1800153f2  test    eax, eax
0x1800153f4  jns     short loc_180015401
0x1800153f6  mov     r8d, 813h
0x1800153fc  jmp     loc_18001569E
0x180015401  lea     r8, [rbp+Block]; unsigned __int16 **
0x180015405  mov     edx, 77h ; 'w'; unsigned int
0x18001540a  xor     ecx, ecx; unsigned __int16 *
0x18001540c  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x180015411  mov     rsi, [rbp+Block]
0x180015415  mov     ebx, eax
0x180015417  test    eax, eax
0x180015419  jns     short loc_180015426
0x18001541b  mov     r8d, 816h
0x180015421  jmp     loc_18001569E
0x180015426  mov     r9, rsi; unsigned __int16 *
0x180015429  lea     r8, aName_0; "name"
0x180015430  mov     rdx, rdi; struct IXMLDOMElement *
0x180015433  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180015435  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001543a  mov     ebx, eax
0x18001543c  test    eax, eax
0x18001543e  jns     short loc_18001544B
0x180015440  mov     r8d, 819h
0x180015446  jmp     loc_18001569E
0x18001544b  test    rsi, rsi
0x18001544e  jz      short loc_18001545E
0x180015450  mov     rcx, rsi; Block
0x180015453  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015458  xor     esi, esi
0x18001545a  mov     [rbp+Block], rsi
0x18001545e  test    rdi, rdi
0x180015461  jz      short loc_180015478
0x180015463  mov     rax, [rdi]
0x180015466  mov     rcx, rdi
0x180015469  mov     rax, [rax+10h]
0x18001546d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015472  xor     edi, edi
0x180015474  mov     [rbp+arg_10], rdi
0x180015478  mov     rcx, [r13+8]; this
0x18001547c  lea     rdx, [rbp+psz]; unsigned __int16 **
0x180015480  call    ?get_PackagePublisher@Settings@@QEAAJPEAPEAG@Z; Settings::get_PackagePublisher(ushort * *)
0x180015485  mov     ebx, eax
0x180015487  test    eax, eax
0x180015489  jns     short loc_1800154AE
0x18001548b  mov     r9d, eax; int
0x18001548e  lea     rdx, aDiagpackageBui_0; "DiagPackage::BuildReportPackageXml"
0x180015495  mov     r8d, 826h; int
0x18001549b  mov     ecx, 1; Level
0x1800154a0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800154a5  mov     r14, [rbp+psz]
0x1800154a9  jmp     loc_1800156CC
0x1800154ae  mov     r14, [rbp+psz]
0x1800154b2  mov     rcx, r14; psz
0x1800154b5  call    cs:__imp_SysAllocString
0x1800154bb  mov     r12, rax
0x1800154be  test    rax, rax
0x1800154c1  jnz     short loc_1800154E6
0x1800154c3  mov     r9d, 8007000Eh; int
0x1800154c9  lea     rdx, aDiagpackageBui_0; "DiagPackage::BuildReportPackageXml"
0x1800154d0  mov     r8d, 829h; int
0x1800154d6  lea     ecx, [rax+1]; Level
0x1800154d9  mov     ebx, r9d
0x1800154dc  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800154e1  jmp     loc_1800156CC
0x1800154e6  test    r14, r14
0x1800154e9  jz      short loc_1800154F6
0x1800154eb  mov     rcx, r14; Block
0x1800154ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800154f3  xor     r14d, r14d
0x1800154f6  lea     rax, [rbp+arg_10]
0x1800154fa  mov     r9, r12; unsigned __int16 *
0x1800154fd  lea     r8, aData; "Data"
0x180015504  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x180015509  xor     edx, edx; struct IXMLDOMElement *
0x18001550b  mov     rcx, r15; struct IXMLDOMDocument2 *
0x18001550e  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180015513  mov     ebx, eax
0x180015515  test    eax, eax
0x180015517  jns     short loc_18001553C
0x180015519  mov     r9d, eax; int
0x18001551c  lea     rdx, aDiagpackageBui_0; "DiagPackage::BuildReportPackageXml"
0x180015523  mov     r8d, 831h; int
0x180015529  mov     ecx, 1; Level
0x18001552e  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180015533  mov     rdi, [rbp+arg_10]
0x180015537  jmp     loc_1800156B7
0x18001553c  mov     rdi, [rbp+arg_10]
0x180015540  lea     r9, aPublisher; "Publisher"
0x180015547  mov     rdx, rdi; struct IXMLDOMElement *
0x18001554a  lea     r8, aId_0; "id"
0x180015551  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180015553  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180015558  mov     ebx, eax
0x18001555a  test    eax, eax
0x18001555c  jns     short loc_180015569
0x18001555e  mov     r8d, 837h
0x180015564  jmp     loc_180015357
0x180015569  lea     r8, [rbp+Block]; unsigned __int16 **
0x18001556d  mov     edx, 75h ; 'u'; unsigned int
0x180015572  xor     ecx, ecx; unsigned __int16 *
0x180015574  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x180015579  mov     ebx, eax
0x18001557b  test    eax, eax
0x18001557d  jns     short loc_1800155A2
0x18001557f  mov     r9d, eax; int
0x180015582  lea     rdx, aDiagpackageBui_0; "DiagPackage::BuildReportPackageXml"
0x180015589  mov     r8d, 83Ah; int
0x18001558f  mov     ecx, 1; Level
0x180015594  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180015599  mov     rsi, [rbp+Block]
0x18001559d  jmp     loc_1800156B7
0x1800155a2  mov     rsi, [rbp+Block]
0x1800155a6  lea     r8, aName_0; "name"
0x1800155ad  mov     r9, rsi; unsigned __int16 *
0x1800155b0  mov     rdx, rdi; struct IXMLDOMElement *
0x1800155b3  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x1800155b5  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x1800155ba  mov     ebx, eax
0x1800155bc  test    eax, eax
0x1800155be  jns     short loc_1800155CB
0x1800155c0  mov     r8d, 83Dh
0x1800155c6  jmp     loc_180015357
0x1800155cb  test    rsi, rsi
0x1800155ce  jz      short loc_1800155DE
0x1800155d0  mov     rcx, rsi; Block
0x1800155d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800155d8  xor     esi, esi
0x1800155da  mov     [rbp+Block], rsi
0x1800155de  mov     rcx, r12; bstrString
0x1800155e1  call    cs:__imp_SysFreeString
0x1800155e7  test    rdi, rdi
0x1800155ea  jz      short loc_180015603
0x1800155ec  mov     rax, [rdi]
0x1800155ef  mov     rcx, rdi
0x1800155f2  mov     rax, [rax+10h]
0x1800155f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155fb  mov     [rbp+arg_10], 0
0x180015603  mov     r12, [r13+38h]
0x180015607  lea     rax, [rbp+arg_10]
0x18001560b  mov     r9, r12; unsigned __int16 *
0x18001560e  mov     [rsp+40h+var_20], rax; struct IXMLDOMElement **
0x180015613  lea     r8, aData; "Data"
0x18001561a  xor     edx, edx; struct IXMLDOMElement *
0x18001561c  mov     rcx, r15; struct IXMLDOMDocument2 *
0x18001561f  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180015624  mov     rdi, [rbp+arg_10]
0x180015628  mov     ebx, eax
0x18001562a  test    eax, eax
0x18001562c  jns     short loc_180015636
0x18001562e  mov     r8d, 84Eh
0x180015634  jmp     short loc_18001569E
0x180015636  lea     r9, aDescription; "Description"
0x18001563d  mov     rdx, rdi; struct IXMLDOMElement *
0x180015640  lea     r8, aId_0; "id"
0x180015647  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180015649  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001564e  mov     ebx, eax
0x180015650  test    eax, eax
0x180015652  jns     short loc_18001565C
0x180015654  mov     r8d, 854h
0x18001565a  jmp     short loc_18001569E
0x18001565c  lea     r8, [rbp+Block]; unsigned __int16 **
0x180015660  mov     edx, 76h ; 'v'; unsigned int
0x180015665  xor     ecx, ecx; unsigned __int16 *
0x180015667  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x18001566c  mov     rsi, [rbp+Block]
0x180015670  mov     ebx, eax
0x180015672  test    eax, eax
0x180015674  jns     short loc_18001567E
0x180015676  mov     r8d, 857h
0x18001567c  jmp     short loc_18001569E
0x18001567e  mov     r9, rsi; unsigned __int16 *
  ... truncated ...
```
