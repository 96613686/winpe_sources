# SdpHandleReportFile(Settings *,ushort *,IXMLDOMDocument2 * *)

- ea: `0x1800034c4`
- end: `0x18000380c`
- name: `?SdpHandleReportFile@@YAJPEAVSettings@@PEAGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `840`
- prototype: `__int64 __fastcall(struct Settings *, unsigned __int16 *, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000a000`

## callees

- `0x1800012a4`
- `0x1800020f8`
- `0x1800034c4`
- `0x180005ffc`
- `0x18001e95c`
- `0x180026fa0`
- `0x18002708c`
- `0x1800280f8`
- `0x1800288b8`
- `0x1800291e0`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003627`
- `KERNEL32!GetLastError` at `0x180003627`
- `KERNEL32!CopyFileW` at `0x18000361d`
- `KERNEL32!CopyFileW` at `0x18000361d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800035b9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800035b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800037b4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800037b4`

## string_xrefs

- `0x18000364f`: `<?xml version="1.0" encoding="utf-8"?><Data/>`

## pseudocode

```c
__int64 __fastcall SdpHandleReportFile(struct Settings *a1, unsigned __int16 *a2, struct IXMLDOMDocument2 **a3)
{
  WCHAR *v3; // rsi
  unsigned __int16 *v4; // r15
  WCHAR *v5; // r12
  struct IXMLDOMElement *v6; // r14
  int v8; // r8d
  unsigned int v9; // ebx
  int ResultPath; // eax
  int FullPath; // eax
  int v12; // r9d
  int v13; // r8d
  const unsigned __int16 *v14; // rax
  OLECHAR *v15; // r13
  int v16; // eax
  int v17; // r9d
  int v18; // r8d
  signed int LastError; // eax
  int v20; // eax
  struct IXMLDOMDocument2 *v21; // rdi
  int v22; // eax
  int v23; // r8d
  int v24; // eax
  int RootNode; // eax
  struct IXMLDOMDocument2 *v27; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int16 *v28; // [rsp+28h] [rbp-28h] BYREF
  struct IXMLDOMElement *v29; // [rsp+30h] [rbp-20h] BYREF
  void *Block; // [rsp+38h] [rbp-18h] BYREF
  OLECHAR *psz; // [rsp+40h] [rbp-10h] BYREF
  LPCWSTR lpNewFileName; // [rsp+48h] [rbp-8h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+A8h] [rbp+58h] BYREF

  v3 = 0;
  v4 = 0;
  v5 = 0;
  v28 = 0;
  v6 = 0;
  Block = 0;
  lpNewFileName = 0;
  lpExistingFileName = 0;
  psz = 0;
  v27 = 0;
  v29 = 0;
  if ( !a3 )
  {
    v8 = 1396;
LABEL_3:
    v9 = -2147024809;
    SdpDebugTrace(1u, L"SdpHandleReportFile", v8, -2147024809);
    return v9;
  }
  if ( !a2 )
  {
    v8 = 1397;
    goto LABEL_3;
  }
  if ( !a1 )
  {
    v8 = 1398;
    goto LABEL_3;
  }
  ResultPath = Settings::get_ResultPath(a1, (unsigned __int16 **)&Block);
  v9 = ResultPath;
  if ( ResultPath >= 0 )
  {
    FullPath = SdpGetFullPath(a2, (unsigned __int16 **)&lpExistingFileName, &psz);
    v9 = FullPath;
    if ( FullPath < 0 )
    {
      v12 = FullPath;
      v13 = 1412;
LABEL_12:
      SdpDebugTrace(1u, L"SdpHandleReportFile", v13, v12);
      v3 = (WCHAR *)lpExistingFileName;
      goto LABEL_43;
    }
    v14 = SysAllocString(psz);
    v15 = (OLECHAR *)v14;
    if ( !v14 )
    {
      v9 = -2147024882;
      v13 = 1419;
      v12 = -2147024882;
      goto LABEL_12;
    }
    v16 = SdpBuildPath((const unsigned __int16 *)Block, v14, (unsigned __int16 **)&lpNewFileName);
    v5 = (WCHAR *)lpNewFileName;
    v9 = v16;
    v3 = (WCHAR *)lpExistingFileName;
    if ( v16 < 0 )
    {
      v17 = v16;
      v18 = 1422;
LABEL_17:
      SdpDebugTrace(1u, L"SdpHandleReportFile", v18, v17);
LABEL_41:
      SysFreeString(v15);
      if ( v4 )
        operator delete(v4);
      goto LABEL_43;
    }
    if ( !CopyFileW(lpExistingFileName, lpNewFileName, 0) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( (v9 & 0x80000000) != 0 )
      {
        v17 = v9;
        v18 = 1429;
        goto LABEL_17;
      }
    }
    v20 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Data/>", &v27);
    v9 = v20;
    if ( v20 >= 0 )
    {
      v21 = v27;
      v22 = SdpXmlSetAttribute(v27, 0, L"id", L"FileName");
      v9 = v22;
      if ( v22 >= 0 )
      {
        v24 = SdpLoadString(0, 0x78u, &v28);
        v9 = v24;
        if ( v24 < 0 )
        {
          SdpDebugTrace(1u, L"SdpHandleReportFile", 1445, v24);
          v4 = v28;
          goto LABEL_37;
        }
        v4 = v28;
        v22 = SdpXmlSetAttribute(v21, 0, L"name", v28);
        v9 = v22;
        if ( v22 >= 0 )
        {
          RootNode = SdpXmlGetRootNode(v21, &v29);
          v9 = RootNode;
          if ( RootNode < 0 )
          {
            SdpDebugTrace(1u, L"SdpHandleReportFile", 1451, RootNode);
            v6 = v29;
            goto LABEL_37;
          }
          v6 = v29;
          v22 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, OLECHAR *))v29->lpVtbl->put_text)(v29, v15);
          v9 = v22;
          if ( v22 >= 0 )
          {
            *a3 = v21;
            v21 = 0;
            goto LABEL_37;
          }
          v23 = 1454;
        }
        else
        {
          v23 = 1448;
        }
      }
      else
      {
        v23 = 1442;
      }
      SdpDebugTrace(1u, L"SdpHandleReportFile", v23, v22);
    }
    else
    {
      SdpDebugTrace(1u, L"SdpHandleReportFile", 1436, v20);
      v21 = v27;
    }
LABEL_37:
    if ( v21 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v21->lpVtbl->Release)(v21);
    if ( v6 )
      ((void (__fastcall *)(struct IXMLDOMElement *))v6->lpVtbl->Release)(v6);
    goto LABEL_41;
  }
  SdpDebugTrace(1u, L"SdpHandleReportFile", 1405, ResultPath);
LABEL_43:
  if ( Block )
    operator delete(Block);
  if ( v5 )
    operator delete(v5);
  if ( v3 )
    operator delete(v3);
  return v9;
}

```

## disassembly

```asm
0x1800034c4  mov     [rsp-38h+arg_0], rbx
0x1800034c9  mov     [rsp-38h+arg_10], r8
0x1800034ce  push    rbp
0x1800034cf  push    rsi
0x1800034d0  push    rdi
0x1800034d1  push    r12
0x1800034d3  push    r13
0x1800034d5  push    r14
0x1800034d7  push    r15
0x1800034d9  mov     rbp, rsp
0x1800034dc  sub     rsp, 50h
0x1800034e0  xor     esi, esi
0x1800034e2  xor     r15d, r15d
0x1800034e5  xor     r12d, r12d
0x1800034e8  mov     [rbp+var_28], r15
0x1800034ec  xor     r14d, r14d
0x1800034ef  mov     [rbp+Block], r15
0x1800034f3  mov     [rbp+lpNewFileName], r12
0x1800034f7  mov     rdi, rdx
0x1800034fa  mov     [rbp+lpExistingFileName], rsi
0x1800034fe  mov     [rbp+psz], rsi
0x180003502  mov     [rbp+var_30], rsi
0x180003506  mov     [rbp+var_20], r14
0x18000350a  test    r8, r8
0x18000350d  jnz     short loc_180003534
0x18000350f  mov     r8d, 574h; int
0x180003515  mov     r9d, 80070057h; int
0x18000351b  lea     rdx, aSdphandlerepor; "SdpHandleReportFile"
0x180003522  mov     ecx, 1; Level
0x180003527  mov     ebx, r9d
0x18000352a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000352f  jmp     loc_1800037F2
0x180003534  test    rdi, rdi
0x180003537  jnz     short loc_180003541
0x180003539  mov     r8d, 575h
0x18000353f  jmp     short loc_180003515
0x180003541  test    rcx, rcx
0x180003544  jnz     short loc_18000354E
0x180003546  mov     r8d, 576h
0x18000354c  jmp     short loc_180003515
0x18000354e  lea     rdx, [rbp+Block]; unsigned __int16 **
0x180003552  call    ?get_ResultPath@Settings@@QEAAJPEAPEAG@Z; Settings::get_ResultPath(ushort * *)
0x180003557  mov     ebx, eax
0x180003559  test    eax, eax
0x18000355b  jns     short loc_18000357C
0x18000355d  mov     r9d, eax; int
0x180003560  lea     rdx, aSdphandlerepor; "SdpHandleReportFile"
0x180003567  mov     r8d, 57Dh; int
0x18000356d  mov     ecx, 1; Level
0x180003572  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180003577  jmp     loc_1800037C7
0x18000357c  lea     r8, [rbp+psz]; unsigned __int16 **
0x180003580  mov     rcx, rdi; unsigned __int16 *
0x180003583  lea     rdx, [rbp+lpExistingFileName]; unsigned __int16 **
0x180003587  call    ?SdpGetFullPath@@YAJPEBGPEAPEAG1@Z; SdpGetFullPath(ushort const *,ushort * *,ushort * *)
0x18000358c  mov     ebx, eax
0x18000358e  test    eax, eax
0x180003590  jns     short loc_1800035B5
0x180003592  mov     r9d, eax; int
0x180003595  mov     r8d, 584h; int
0x18000359b  lea     rdx, aSdphandlerepor; "SdpHandleReportFile"
0x1800035a2  mov     ecx, 1; Level
0x1800035a7  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800035ac  mov     rsi, [rbp+lpExistingFileName]
0x1800035b0  jmp     loc_1800037C7
0x1800035b5  mov     rcx, [rbp+psz]; psz
0x1800035b9  call    cs:__imp_SysAllocString
0x1800035bf  mov     r13, rax
0x1800035c2  test    rax, rax
0x1800035c5  jnz     short loc_1800035D7
0x1800035c7  mov     ebx, 8007000Eh
0x1800035cc  mov     r8d, 58Bh
0x1800035d2  mov     r9d, ebx
0x1800035d5  jmp     short loc_18000359B
0x1800035d7  mov     rcx, [rbp+Block]; unsigned __int16 *
0x1800035db  lea     r8, [rbp+lpNewFileName]; unsigned __int16 **
0x1800035df  mov     rdx, r13; unsigned __int16 *
0x1800035e2  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x1800035e7  mov     r12, [rbp+lpNewFileName]
0x1800035eb  mov     ebx, eax
0x1800035ed  mov     rsi, [rbp+lpExistingFileName]
0x1800035f1  test    eax, eax
0x1800035f3  jns     short loc_180003614
0x1800035f5  mov     r9d, eax; int
0x1800035f8  mov     r8d, 58Eh; int
0x1800035fe  lea     rdx, aSdphandlerepor; "SdpHandleReportFile"
0x180003605  mov     ecx, 1; Level
0x18000360a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000360f  jmp     loc_1800037B1
0x180003614  xor     r8d, r8d; bFailIfExists
0x180003617  mov     rdx, r12; lpNewFileName
0x18000361a  mov     rcx, rsi; lpExistingFileName
0x18000361d  call    cs:__imp_CopyFileW
0x180003623  test    eax, eax
0x180003625  jnz     short loc_18000364B
0x180003627  call    cs:__imp_GetLastError
0x18000362d  mov     ebx, eax
0x18000362f  test    eax, eax
0x180003631  jle     short loc_18000363C
0x180003633  movzx   ebx, ax
0x180003636  or      ebx, 80070000h
0x18000363c  test    ebx, ebx
0x18000363e  jns     short loc_18000364B
0x180003640  mov     r9d, ebx
0x180003643  mov     r8d, 595h
0x180003649  jmp     short loc_1800035FE
0x18000364b  lea     rdx, [rbp+var_30]; struct IXMLDOMDocument2 **
0x18000364f  lea     rcx, aXmlVersion10En_24; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180003656  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x18000365b  mov     ebx, eax
0x18000365d  test    eax, eax
0x18000365f  jns     short loc_180003684
0x180003661  mov     r9d, eax; int
0x180003664  lea     rdx, aSdphandlerepor; "SdpHandleReportFile"
0x18000366b  mov     r8d, 59Ch; int
0x180003671  mov     ecx, 1; Level
0x180003676  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000367b  mov     rdi, [rbp+var_30]
0x18000367f  jmp     loc_180003789
0x180003684  mov     rdi, [rbp+var_30]
0x180003688  lea     r9, aFilename_0; "FileName"
0x18000368f  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x180003692  lea     r8, aId_0; "id"
0x180003699  xor     edx, edx; struct IXMLDOMElement *
0x18000369b  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x1800036a0  mov     ebx, eax
0x1800036a2  test    eax, eax
0x1800036a4  jns     short loc_1800036C5
0x1800036a6  mov     r8d, 5A2h; int
0x1800036ac  mov     r9d, eax; int
0x1800036af  lea     rdx, aSdphandlerepor; "SdpHandleReportFile"
0x1800036b6  mov     ecx, 1; Level
0x1800036bb  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800036c0  jmp     loc_180003789
0x1800036c5  lea     r8, [rbp+var_28]; unsigned __int16 **
0x1800036c9  mov     edx, 78h ; 'x'; unsigned int
0x1800036ce  xor     ecx, ecx; unsigned __int16 *
0x1800036d0  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x1800036d5  mov     ebx, eax
0x1800036d7  test    eax, eax
0x1800036d9  jns     short loc_1800036FE
0x1800036db  mov     r9d, eax; int
0x1800036de  lea     rdx, aSdphandlerepor; "SdpHandleReportFile"
0x1800036e5  mov     r8d, 5A5h; int
0x1800036eb  mov     ecx, 1; Level
0x1800036f0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800036f5  mov     r15, [rbp+var_28]
0x1800036f9  jmp     loc_180003789
0x1800036fe  mov     r15, [rbp+var_28]
0x180003702  lea     r8, aName_0; "name"
0x180003709  mov     r9, r15; unsigned __int16 *
0x18000370c  xor     edx, edx; struct IXMLDOMElement *
0x18000370e  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x180003711  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180003716  mov     ebx, eax
0x180003718  test    eax, eax
0x18000371a  jns     short loc_180003724
0x18000371c  mov     r8d, 5A8h
0x180003722  jmp     short loc_1800036AC
0x180003724  lea     rdx, [rbp+var_20]; struct IXMLDOMElement **
0x180003728  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18000372b  call    ?SdpXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; SdpXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x180003730  mov     ebx, eax
0x180003732  test    eax, eax
0x180003734  jns     short loc_180003756
0x180003736  mov     r9d, eax; int
0x180003739  lea     rdx, aSdphandlerepor; "SdpHandleReportFile"
0x180003740  mov     r8d, 5ABh; int
0x180003746  mov     ecx, 1; Level
0x18000374b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180003750  mov     r14, [rbp+var_20]
0x180003754  jmp     short loc_180003789
0x180003756  mov     r14, [rbp+var_20]
0x18000375a  mov     rdx, r13
0x18000375d  mov     rcx, r14
0x180003760  mov     rax, [r14]
0x180003763  mov     rax, [rax+0D8h]
0x18000376a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000376f  mov     ebx, eax
0x180003771  test    eax, eax
0x180003773  jns     short loc_180003780
0x180003775  mov     r8d, 5AEh
0x18000377b  jmp     loc_1800036AC
0x180003780  mov     rax, [rbp+arg_10]
0x180003784  mov     [rax], rdi
0x180003787  xor     edi, edi
0x180003789  test    rdi, rdi
0x18000378c  jz      short loc_18000379D
0x18000378e  mov     rax, [rdi]
0x180003791  mov     rcx, rdi
0x180003794  mov     rax, [rax+10h]
0x180003798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000379d  test    r14, r14
0x1800037a0  jz      short loc_1800037B1
0x1800037a2  mov     rax, [r14]
0x1800037a5  mov     rcx, r14
0x1800037a8  mov     rax, [rax+10h]
0x1800037ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b1  mov     rcx, r13; bstrString
0x1800037b4  call    cs:__imp_SysFreeString
0x1800037ba  test    r15, r15
0x1800037bd  jz      short loc_1800037C7
0x1800037bf  mov     rcx, r15; Block
0x1800037c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800037c7  mov     rax, [rbp+Block]
0x1800037cb  test    rax, rax
0x1800037ce  jz      short loc_1800037D8
0x1800037d0  mov     rcx, rax; Block
0x1800037d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800037d8  test    r12, r12
0x1800037db  jz      short loc_1800037E5
0x1800037dd  mov     rcx, r12; Block
0x1800037e0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800037e5  test    rsi, rsi
0x1800037e8  jz      short loc_1800037F2
0x1800037ea  mov     rcx, rsi; Block
0x1800037ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800037f2  mov     eax, ebx
0x1800037f4  mov     rbx, [rsp+50h+arg_0]
0x1800037fc  add     rsp, 50h
0x180003800  pop     r15
0x180003802  pop     r14
0x180003804  pop     r13
0x180003806  pop     r12
0x180003808  pop     rdi
0x180003809  pop     rsi
0x18000380a  pop     rbp
0x18000380b  retn
```
