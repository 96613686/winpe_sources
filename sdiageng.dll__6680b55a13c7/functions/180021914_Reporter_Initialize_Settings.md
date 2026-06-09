# Reporter::Initialize(Settings *)

- ea: `0x180021914`
- end: `0x180021d2d`
- name: `?Initialize@Reporter@@QEAAJPEAVSettings@@@Z`
- size: `1049`
- prototype: `__int64 __fastcall(Reporter *__hidden this, struct Settings *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000cf00`

## callees

- `0x1800012a4`
- `0x1800020f8`
- `0x18001e95c`
- `0x1800217ac`
- `0x180021870`
- `0x180021914`
- `0x180021ec4`
- `0x180022174`
- `0x180026fa0`
- `0x1800280f8`
- `0x1800291e0`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180021a16`
- `OLEAUT32!__imp_SysAllocString` at `0x180021a9d`
- `OLEAUT32!__imp_SysAllocString` at `0x180021aee`
- `OLEAUT32!__imp_SysAllocString` at `0x180021a16`
- `OLEAUT32!__imp_SysAllocString` at `0x180021a9d`
- `OLEAUT32!__imp_SysAllocString` at `0x180021aee`
- `OLEAUT32!__imp_SysFreeString` at `0x180021cc5`
- `OLEAUT32!__imp_SysFreeString` at `0x180021cd7`
- `OLEAUT32!__imp_SysFreeString` at `0x180021ce5`
- `OLEAUT32!__imp_SysFreeString` at `0x180021cc5`
- `OLEAUT32!__imp_SysFreeString` at `0x180021cd7`
- `OLEAUT32!__imp_SysFreeString` at `0x180021ce5`

## string_xrefs

- `0x1800219d8`: `ResultReport.xml`
- `0x180021a64`: `DebugReport.xml`
- `0x180021b09`: `<?xml version="1.0" encoding="utf-8"?><ResultReport/>`
- `0x180021b71`: `<?xml version="1.0" encoding="utf-8"?><DebugReport/>`

## pseudocode

```c
__int64 __fastcall Reporter::Initialize(Reporter *this, struct Settings *a2)
{
  unsigned __int16 *v2; // rsi
  OLECHAR *v3; // rdi
  struct IXMLDOMDocument2 *v4; // r15
  struct IXMLDOMDocument2 *v5; // r14
  unsigned __int16 *v7; // r12
  unsigned int v8; // ebx
  Reporter *v9; // rcx
  OLECHAR *v10; // r13
  int ResultPath; // eax
  int v12; // eax
  int v13; // r8d
  int v14; // r9d
  int v15; // eax
  int v16; // r8d
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  Reporter *v23; // rcx
  int v24; // eax
  BSTR v25; // rcx
  __int64 v26; // xmm1_8
  __int64 v27; // xmm1_8
  __int128 v28; // xmm0
  Reporter *v29; // rcx
  unsigned __int16 *v31; // [rsp+20h] [rbp-50h] BYREF
  struct IXMLDOMDocument2 *v32; // [rsp+28h] [rbp-48h] BYREF
  struct IXMLDOMDocument2 *v33; // [rsp+30h] [rbp-40h] BYREF
  __int128 v34; // [rsp+38h] [rbp-38h] BYREF
  __int64 v35; // [rsp+48h] [rbp-28h]
  __int128 v36; // [rsp+50h] [rbp-20h] BYREF
  __int64 v37; // [rsp+60h] [rbp-10h]
  Reporter *v38; // [rsp+B8h] [rbp+48h]
  OLECHAR *psz; // [rsp+C0h] [rbp+50h] BYREF
  BSTR bstrString; // [rsp+C8h] [rbp+58h]

  v2 = 0;
  v3 = 0;
  v4 = 0;
  v31 = 0;
  v5 = 0;
  psz = 0;
  v32 = 0;
  v33 = 0;
  v7 = 0;
  bstrString = 0;
  v37 = 0;
  v35 = 0;
  v36 = 0;
  v34 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    SdpDebugTrace(1u, L"Reporter::Initialize", 85, -2147024809);
    v10 = 0;
    goto LABEL_40;
  }
  *((_QWORD *)this + 6) = a2;
  ResultPath = Settings::get_ResultPath(a2, &v31);
  v8 = ResultPath;
  if ( ResultPath < 0 )
  {
    SdpDebugTrace(1u, L"Reporter::Initialize", 95, ResultPath);
    v2 = v31;
    v10 = 0;
    goto LABEL_40;
  }
  v2 = v31;
  v12 = SdpBuildPath(v31, L"ResultReport.xml", &psz);
  v8 = v12;
  if ( v12 < 0 )
  {
    SdpDebugTrace(1u, L"Reporter::Initialize", 98, v12);
    v3 = psz;
    v10 = 0;
    goto LABEL_40;
  }
  v3 = psz;
  v38 = (Reporter *)SysAllocString(psz);
  if ( !v38 )
  {
    v13 = 101;
LABEL_9:
    v14 = -2147024882;
    v8 = -2147024882;
LABEL_10:
    SdpDebugTrace(1u, L"Reporter::Initialize", v13, v14);
LABEL_11:
    v10 = (OLECHAR *)v38;
    goto LABEL_40;
  }
  if ( v3 )
  {
    operator delete(v3);
    psz = 0;
  }
  v15 = SdpBuildPath(v2, L"DebugReport.xml", &psz);
  v8 = v15;
  if ( v15 < 0 )
  {
    v16 = 107;
LABEL_16:
    SdpDebugTrace(1u, L"Reporter::Initialize", v16, v15);
    v3 = psz;
    goto LABEL_11;
  }
  v3 = psz;
  bstrString = SysAllocString(psz);
  if ( !bstrString )
  {
    v13 = 110;
    goto LABEL_9;
  }
  if ( v3 )
  {
    operator delete(v3);
    psz = 0;
  }
  v15 = SdpBuildPath(v2, L"results.xsl", &psz);
  v8 = v15;
  if ( v15 < 0 )
  {
    v16 = 115;
    goto LABEL_16;
  }
  v3 = psz;
  v7 = SysAllocString(psz);
  if ( !v7 )
  {
    v13 = 118;
    goto LABEL_9;
  }
  v17 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><ResultReport/>", &v32);
  v8 = v17;
  if ( v17 < 0 )
  {
    SdpDebugTrace(1u, L"Reporter::Initialize", 125, v17);
    v4 = v32;
    goto LABEL_11;
  }
  v4 = v32;
  v18 = SdpXmlSetAttribute(v32, 0, L"SchemaVersion", L"1.0");
  v8 = v18;
  if ( v18 < 0 )
  {
    v14 = v18;
    v13 = 131;
    goto LABEL_10;
  }
  v19 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><DebugReport/>", &v33);
  v8 = v19;
  if ( v19 < 0 )
  {
    SdpDebugTrace(1u, L"Reporter::Initialize", 134, v19);
    v5 = v33;
    goto LABEL_11;
  }
  v5 = v33;
  v20 = SdpXmlSetAttribute(v33, 0, L"SchemaVersion", L"1.0");
  v8 = v20;
  if ( v20 < 0 )
  {
    v14 = v20;
    v13 = 140;
    goto LABEL_10;
  }
  v21 = Reporter::SetupDebugReport(this, v5, (struct Reporter::_REPORT *)&v34);
  v8 = v21;
  if ( v21 < 0 )
  {
    v14 = v21;
    v13 = 147;
    goto LABEL_10;
  }
  v22 = Reporter::SetupResultReport(this, v4, (struct Reporter::_REPORT *)&v36);
  v8 = v22;
  if ( v22 < 0 )
  {
    v14 = v22;
    v13 = 150;
    goto LABEL_10;
  }
  v24 = Reporter::AddXslToResults(v23, v7);
  v8 = v24;
  if ( v24 < 0 )
  {
    v14 = v24;
    v13 = 157;
    goto LABEL_10;
  }
  v25 = bstrString;
  v26 = v35;
  *(_OWORD *)this = v34;
  *((_QWORD *)this + 7) = v25;
  *((_QWORD *)this + 2) = v26;
  v27 = v37;
  v34 = 0;
  bstrString = 0;
  v28 = v36;
  v9 = v38;
  *((_QWORD *)this + 8) = v38;
  *(_OWORD *)((char *)this + 24) = v28;
  v35 = 0;
  *((_QWORD *)this + 5) = v27;
  v36 = 0;
  v37 = 0;
  v10 = 0;
LABEL_40:
  Reporter::FreeReport(v9, (struct Reporter::_REPORT *)&v34);
  Reporter::FreeReport(v29, (struct Reporter::_REPORT *)&v36);
  if ( v2 )
    operator delete(v2);
  if ( v3 )
    operator delete(v3);
  if ( v10 )
    SysFreeString(v10);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v7 )
    SysFreeString(v7);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v4->lpVtbl->Release)(v4);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v5->lpVtbl->Release)(v5);
  return v8;
}

```

## disassembly

```asm
0x180021914  mov     [rsp-38h+arg_0], rbx
0x180021919  push    rbp
0x18002191a  push    rsi
0x18002191b  push    rdi
0x18002191c  push    r12
0x18002191e  push    r13
0x180021920  push    r14
0x180021922  push    r15
0x180021924  mov     rbp, rsp
0x180021927  sub     rsp, 70h
0x18002192b  xor     esi, esi
0x18002192d  xor     edi, edi
0x18002192f  xor     r15d, r15d
0x180021932  mov     [rbp+var_50], rsi
0x180021936  xor     r14d, r14d
0x180021939  mov     [rbp+psz], rdi
0x18002193d  mov     r13, rcx
0x180021940  mov     [rbp+var_48], r15
0x180021944  xor     ecx, ecx
0x180021946  mov     [rbp+var_40], r14
0x18002194a  xor     r12d, r12d
0x18002194d  mov     [rbp+bstrString], rcx
0x180021951  mov     [rbp+var_10], rcx
0x180021955  xorps   xmm0, xmm0
0x180021958  mov     [rbp+var_28], rcx
0x18002195c  xorps   xmm1, xmm1
0x18002195f  mov     rax, rdx
0x180021962  movups  [rbp+var_20], xmm0
0x180021966  movups  [rbp+var_38], xmm1
0x18002196a  test    rdx, rdx
0x18002196d  jnz     short loc_180021992
0x18002196f  lea     r8d, [rdx+55h]; int
0x180021973  mov     ebx, 80070057h
0x180021978  mov     r9d, ebx; int
0x18002197b  lea     rdx, aReporterInitia; "Reporter::Initialize"
0x180021982  lea     ecx, [rax+1]; Level
0x180021985  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18002198a  mov     r13d, esi
0x18002198d  jmp     loc_180021C91
0x180021992  lea     rdx, [rbp+var_50]; unsigned __int16 **
0x180021996  mov     [r13+30h], rax
0x18002199a  mov     rcx, rax; this
0x18002199d  call    ?get_ResultPath@Settings@@QEAAJPEAPEAG@Z; Settings::get_ResultPath(ushort * *)
0x1800219a2  mov     ebx, eax
0x1800219a4  test    eax, eax
0x1800219a6  jns     short loc_1800219CD
0x1800219a8  mov     r8d, 5Fh ; '_'; int
0x1800219ae  lea     rdx, aReporterInitia; "Reporter::Initialize"
0x1800219b5  mov     r9d, eax; int
0x1800219b8  lea     ecx, [r8-5Eh]; Level
0x1800219bc  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800219c1  mov     rsi, [rbp+var_50]
0x1800219c5  mov     r13, rdi
0x1800219c8  jmp     loc_180021C91
0x1800219cd  mov     rsi, [rbp+var_50]
0x1800219d1  lea     r8, [rbp+psz]; unsigned __int16 **
0x1800219d5  mov     rcx, rsi; unsigned __int16 *
0x1800219d8  lea     rdx, aResultreportXm; "ResultReport.xml"
0x1800219df  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x1800219e4  mov     ebx, eax
0x1800219e6  test    eax, eax
0x1800219e8  jns     short loc_180021A0F
0x1800219ea  mov     r8d, 62h ; 'b'; int
0x1800219f0  lea     rdx, aReporterInitia; "Reporter::Initialize"
0x1800219f7  mov     r9d, eax; int
0x1800219fa  lea     ecx, [r8-61h]; Level
0x1800219fe  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180021a03  mov     rdi, [rbp+psz]
0x180021a07  mov     r13, r12
0x180021a0a  jmp     loc_180021C91
0x180021a0f  mov     rdi, [rbp+psz]
0x180021a13  mov     rcx, rdi; psz
0x180021a16  call    cs:__imp_SysAllocString
0x180021a1c  mov     [rbp+arg_8], rax
0x180021a20  test    rax, rax
0x180021a23  jnz     short loc_180021A4C
0x180021a25  lea     r8d, [rax+65h]; int
0x180021a29  mov     r9d, 8007000Eh; int
0x180021a2f  mov     ebx, r9d
0x180021a32  lea     rdx, aReporterInitia; "Reporter::Initialize"
0x180021a39  mov     ecx, 1; Level
0x180021a3e  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180021a43  mov     r13, [rbp+arg_8]
0x180021a47  jmp     loc_180021C91
0x180021a4c  test    rdi, rdi
0x180021a4f  jz      short loc_180021A5D
0x180021a51  mov     rcx, rdi; Block
0x180021a54  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021a59  mov     [rbp+psz], r12
0x180021a5d  lea     r8, [rbp+psz]; unsigned __int16 **
0x180021a61  mov     rcx, rsi; unsigned __int16 *
0x180021a64  lea     rdx, aDebugreportXml; "DebugReport.xml"
0x180021a6b  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x180021a70  mov     ebx, eax
0x180021a72  test    eax, eax
0x180021a74  jns     short loc_180021A96
0x180021a76  mov     r8d, 6Bh ; 'k'; int
0x180021a7c  mov     r9d, eax; int
0x180021a7f  lea     rdx, aReporterInitia; "Reporter::Initialize"
0x180021a86  mov     ecx, 1; Level
0x180021a8b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180021a90  mov     rdi, [rbp+psz]
0x180021a94  jmp     short loc_180021A43
0x180021a96  mov     rdi, [rbp+psz]
0x180021a9a  mov     rcx, rdi; psz
0x180021a9d  call    cs:__imp_SysAllocString
0x180021aa3  mov     [rbp+bstrString], rax
0x180021aa7  test    rax, rax
0x180021aaa  jnz     short loc_180021AB5
0x180021aac  lea     r8d, [rax+6Eh]
0x180021ab0  jmp     loc_180021A29
0x180021ab5  test    rdi, rdi
0x180021ab8  jz      short loc_180021AC6
0x180021aba  mov     rcx, rdi; Block
0x180021abd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021ac2  mov     [rbp+psz], r12
0x180021ac6  lea     r8, [rbp+psz]; unsigned __int16 **
0x180021aca  mov     rcx, rsi; unsigned __int16 *
0x180021acd  lea     rdx, aResultsXsl; "results.xsl"
0x180021ad4  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x180021ad9  mov     ebx, eax
0x180021adb  test    eax, eax
0x180021add  jns     short loc_180021AE7
0x180021adf  mov     r8d, 73h ; 's'
0x180021ae5  jmp     short loc_180021A7C
0x180021ae7  mov     rdi, [rbp+psz]
0x180021aeb  mov     rcx, rdi; psz
0x180021aee  call    cs:__imp_SysAllocString
0x180021af4  mov     r12, rax
0x180021af7  test    rax, rax
0x180021afa  jnz     short loc_180021B05
0x180021afc  lea     r8d, [rax+76h]
0x180021b00  jmp     loc_180021A29
0x180021b05  lea     rdx, [rbp+var_48]; struct IXMLDOMDocument2 **
0x180021b09  lea     rcx, aXmlVersion10En_16; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180021b10  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180021b15  mov     ebx, eax
0x180021b17  test    eax, eax
0x180021b19  jns     short loc_180021B3D
0x180021b1b  mov     r8d, 7Dh ; '}'; int
0x180021b21  lea     rdx, aReporterInitia; "Reporter::Initialize"
0x180021b28  mov     r9d, eax; int
0x180021b2b  lea     ecx, [r8-7Ch]; Level
0x180021b2f  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180021b34  mov     r15, [rbp+var_48]
0x180021b38  jmp     loc_180021A43
0x180021b3d  mov     r15, [rbp+var_48]
0x180021b41  lea     r9, a10; "1.0"
0x180021b48  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180021b4b  lea     r8, aSchemaversion; "SchemaVersion"
0x180021b52  xor     edx, edx; struct IXMLDOMElement *
0x180021b54  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180021b59  mov     ebx, eax
0x180021b5b  test    eax, eax
0x180021b5d  jns     short loc_180021B6D
0x180021b5f  mov     r9d, eax
0x180021b62  mov     r8d, 83h
0x180021b68  jmp     loc_180021A32
0x180021b6d  lea     rdx, [rbp+var_40]; struct IXMLDOMDocument2 **
0x180021b71  lea     rcx, aXmlVersion10En_7; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180021b78  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180021b7d  mov     ebx, eax
0x180021b7f  test    eax, eax
0x180021b81  jns     short loc_180021BA6
0x180021b83  mov     r9d, eax; int
0x180021b86  lea     rdx, aReporterInitia; "Reporter::Initialize"
0x180021b8d  mov     r8d, 86h; int
0x180021b93  mov     ecx, 1; Level
0x180021b98  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180021b9d  mov     r14, [rbp+var_40]
0x180021ba1  jmp     loc_180021A43
0x180021ba6  mov     r14, [rbp+var_40]
0x180021baa  lea     r9, a10; "1.0"
0x180021bb1  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180021bb4  lea     r8, aSchemaversion; "SchemaVersion"
0x180021bbb  xor     edx, edx; struct IXMLDOMElement *
0x180021bbd  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180021bc2  mov     ebx, eax
0x180021bc4  test    eax, eax
0x180021bc6  jns     short loc_180021BD6
0x180021bc8  mov     r9d, eax
0x180021bcb  mov     r8d, 8Ch
0x180021bd1  jmp     loc_180021A32
0x180021bd6  lea     r8, [rbp+var_38]; struct Reporter::_REPORT *
0x180021bda  mov     rdx, r14; struct IXMLDOMDocument2 *
0x180021bdd  mov     rcx, r13; this
0x180021be0  call    ?SetupDebugReport@Reporter@@AEAAJPEAUIXMLDOMDocument2@@PEAU_REPORT@1@@Z; Reporter::SetupDebugReport(IXMLDOMDocument2 *,Reporter::_REPORT *)
0x180021be5  mov     ebx, eax
0x180021be7  test    eax, eax
0x180021be9  jns     short loc_180021BF9
0x180021beb  mov     r9d, eax
0x180021bee  mov     r8d, 93h
0x180021bf4  jmp     loc_180021A32
0x180021bf9  lea     r8, [rbp+var_20]; struct Reporter::_REPORT *
0x180021bfd  mov     rdx, r15; struct IXMLDOMDocument2 *
0x180021c00  mov     rcx, r13; this
0x180021c03  call    ?SetupResultReport@Reporter@@AEAAJPEAUIXMLDOMDocument2@@PEAU_REPORT@1@@Z; Reporter::SetupResultReport(IXMLDOMDocument2 *,Reporter::_REPORT *)
0x180021c08  mov     ebx, eax
0x180021c0a  test    eax, eax
0x180021c0c  jns     short loc_180021C1C
0x180021c0e  mov     r9d, eax
0x180021c11  mov     r8d, 96h
0x180021c17  jmp     loc_180021A32
0x180021c1c  mov     rdx, r12; unsigned __int16 *
0x180021c1f  call    ?AddXslToResults@Reporter@@AEAAJPEAG@Z; Reporter::AddXslToResults(ushort *)
0x180021c24  mov     ebx, eax
0x180021c26  test    eax, eax
0x180021c28  jns     short loc_180021C38
0x180021c2a  mov     r9d, eax
0x180021c2d  mov     r8d, 9Dh
0x180021c33  jmp     loc_180021A32
0x180021c38  movups  xmm0, [rbp+var_38]
0x180021c3c  mov     rcx, [rbp+bstrString]
0x180021c40  xor     eax, eax
0x180021c42  movsd   xmm1, [rbp+var_28]
0x180021c47  movups  xmmword ptr [r13+0], xmm0
0x180021c4c  mov     [r13+38h], rcx
0x180021c50  xor     ecx, ecx
0x180021c52  xorps   xmm0, xmm0
0x180021c55  movsd   qword ptr [r13+10h], xmm1
0x180021c5b  movsd   xmm1, [rbp+var_10]
0x180021c60  movups  [rbp+var_38], xmm0
0x180021c64  mov     [rbp+bstrString], rcx
0x180021c68  movups  xmm0, [rbp+var_20]
0x180021c6c  mov     rcx, [rbp+arg_8]; this
0x180021c70  mov     [r13+40h], rcx
0x180021c74  movups  xmmword ptr [r13+18h], xmm0
0x180021c79  mov     [rbp+var_28], rax
0x180021c7d  xorps   xmm0, xmm0
0x180021c80  movsd   qword ptr [r13+28h], xmm1
0x180021c86  movups  [rbp+var_20], xmm0
0x180021c8a  mov     [rbp+var_10], rax
0x180021c8e  xor     r13d, r13d
0x180021c91  lea     rdx, [rbp+var_38]; struct Reporter::_REPORT *
0x180021c95  call    ?FreeReport@Reporter@@AEAAJPEAU_REPORT@1@@Z; Reporter::FreeReport(Reporter::_REPORT *)
0x180021c9a  lea     rdx, [rbp+var_20]; struct Reporter::_REPORT *
0x180021c9e  call    ?FreeReport@Reporter@@AEAAJPEAU_REPORT@1@@Z; Reporter::FreeReport(Reporter::_REPORT *)
0x180021ca3  test    rsi, rsi
0x180021ca6  jz      short loc_180021CB0
0x180021ca8  mov     rcx, rsi; Block
0x180021cab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021cb0  test    rdi, rdi
0x180021cb3  jz      short loc_180021CBD
0x180021cb5  mov     rcx, rdi; Block
0x180021cb8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021cbd  test    r13, r13
0x180021cc0  jz      short loc_180021CCB
0x180021cc2  mov     rcx, r13; bstrString
0x180021cc5  call    cs:__imp_SysFreeString
0x180021ccb  mov     rax, [rbp+bstrString]
0x180021ccf  test    rax, rax
0x180021cd2  jz      short loc_180021CDD
0x180021cd4  mov     rcx, rax; bstrString
0x180021cd7  call    cs:__imp_SysFreeString
0x180021cdd  test    r12, r12
0x180021ce0  jz      short loc_180021CEB
0x180021ce2  mov     rcx, r12; bstrString
0x180021ce5  call    cs:__imp_SysFreeString
0x180021ceb  test    r15, r15
0x180021cee  jz      short loc_180021CFF
0x180021cf0  mov     rax, [r15]
0x180021cf3  mov     rcx, r15
0x180021cf6  mov     rax, [rax+10h]
0x180021cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cff  test    r14, r14
0x180021d02  jz      short loc_180021D13
0x180021d04  mov     rax, [r14]
0x180021d07  mov     rcx, r14
0x180021d0a  mov     rax, [rax+10h]
0x180021d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d13  mov     eax, ebx
0x180021d15  mov     rbx, [rsp+70h+arg_0]
0x180021d1d  add     rsp, 70h
0x180021d21  pop     r15
0x180021d23  pop     r14
0x180021d25  pop     r13
0x180021d27  pop     r12
0x180021d29  pop     rdi
0x180021d2a  pop     rsi
0x180021d2b  pop     rbp
0x180021d2c  retn
```
