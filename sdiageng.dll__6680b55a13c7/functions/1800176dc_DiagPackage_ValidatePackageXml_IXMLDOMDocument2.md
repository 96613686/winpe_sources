# DiagPackage::ValidatePackageXml(IXMLDOMDocument2 *)

- ea: `0x1800176dc`
- end: `0x180017905`
- name: `?ValidatePackageXml@DiagPackage@@AEAAJPEAUIXMLDOMDocument2@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(DiagPackage *this, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016080`

## callees

- `0x180003410`
- `0x1800130d0`
- `0x1800142cc`
- `0x1800176dc`
- `0x180026fa0`
- `0x180028b34`
- `0x1800293a0`
- `0x1800298c0`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800177f6`
- `OLEAUT32!__imp_SysAllocString` at `0x18001781c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800177f6`
- `OLEAUT32!__imp_SysAllocString` at `0x18001781c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800178a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800178b4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800178a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800178b4`

## string_xrefs

- `0x1800177d7`: `DiagPackage::ValidatePackageXml`
- `0x18001786e`: `DiagPackage::ValidatePackageXml`
- `0x1800177ef`: `http://www.microsoft.com/schemas/dcm/resource/2007`
- `0x180017815`: `http://www.microsoft.com/schemas/dcm/package/2007`

## pseudocode

```c
__int64 __fastcall DiagPackage::ValidatePackageXml(DiagPackage *this, struct IXMLDOMDocument2 *a2)
{
  struct IXMLDOMDocument2 *v2; // rdi
  _QWORD *v3; // rbx
  OLECHAR *v4; // r14
  OLECHAR *v6; // rsi
  __int64 v7; // r15
  __int64 v8; // rcx
  const unsigned __int16 *v9; // r8
  unsigned int v10; // ebx
  int v11; // r8d
  int v12; // r9d
  int v13; // eax
  int v14; // eax
  int v15; // r9d
  int v16; // r8d
  __int64 v17; // rcx
  __int64 v18; // r8
  struct IXMLDOMDocument2 *v20; // [rsp+30h] [rbp-39h] BYREF
  struct IXMLDOMDocument2 *v21; // [rsp+38h] [rbp-31h] BYREF
  _QWORD v22[4]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v23[16]; // [rsp+60h] [rbp-9h] BYREF

  v2 = 0;
  v3 = v22;
  v4 = 0;
  v20 = 0;
  v21 = 0;
  v6 = 0;
  v7 = 2;
  do
  {
    std::pair<unsigned short *,IXMLDOMDocument2 *>::pair<unsigned short *,IXMLDOMDocument2 *>(v3);
    v3 += 2;
    --v7;
  }
  while ( v7 );
  if ( (Microsoft_Windows_Diagnosis_ScriptedEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(v8, SCRIPTED_DIAGNOSTICS_EVENT_PERF_VALIDATE_START, v9, 1, v23);
  if ( a2 )
  {
    v13 = SdpCheckDocumentVersion(a2, L"SchemaVersion", v9);
    v10 = v13;
    if ( v13 >= 0 )
    {
      v13 = SdpXmlLoadResource(L"resource_schema.xsd", &v21, (const unsigned __int16 *)0xA);
      v10 = v13;
      if ( v13 >= 0 )
      {
        v14 = SdpXmlLoadResource(L"package_schema.xsd", &v20, (const unsigned __int16 *)0xA);
        v10 = v14;
        if ( v14 >= 0 )
        {
          v6 = SysAllocString(L"http://www.microsoft.com/schemas/dcm/resource/2007");
          if ( v6 )
          {
            v4 = SysAllocString(L"http://www.microsoft.com/schemas/dcm/package/2007");
            if ( v4 )
            {
              v2 = v20;
              v22[1] = v21;
              v22[3] = v20;
              v22[0] = v6;
              v22[2] = v4;
              v13 = SdpXmlValidate(a2, v22);
              v10 = v13;
              if ( v13 >= 0 )
                goto LABEL_22;
              v11 = 1039;
              goto LABEL_20;
            }
            v15 = -2147024882;
            v16 = 1024;
            v10 = -2147024882;
          }
          else
          {
            v15 = -2147024882;
            v16 = 1021;
            v10 = -2147024882;
          }
        }
        else
        {
          v15 = v14;
          v16 = 1018;
        }
        SdpDebugTrace(1u, L"DiagPackage::ValidatePackageXml", v16, v15);
        v2 = v20;
        goto LABEL_22;
      }
      v11 = 1015;
    }
    else
    {
      v11 = 1009;
    }
LABEL_20:
    v12 = v13;
    goto LABEL_21;
  }
  v10 = -2147024809;
  v11 = 1000;
  v12 = -2147024809;
LABEL_21:
  SdpDebugTrace(1u, L"DiagPackage::ValidatePackageXml", v11, v12);
LABEL_22:
  if ( (Microsoft_Windows_Diagnosis_ScriptedEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(v17, SCRIPTED_DIAGNOSTICS_EVENT_PERF_VALIDATE_STOP, v18, 1, v23);
  if ( v4 )
    SysFreeString(v4);
  if ( v6 )
    SysFreeString(v6);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v2->lpVtbl->Release)(v2);
  if ( v21 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v21->lpVtbl->Release)(v21);
  return v10;
}

```

## disassembly

```asm
0x1800176dc  push    rbp
0x1800176de  push    rbx
0x1800176df  push    rsi
0x1800176e0  push    rdi
0x1800176e1  push    r12
0x1800176e3  push    r13
0x1800176e5  push    r14
0x1800176e7  push    r15
0x1800176e9  lea     rbp, [rsp-1Fh]
0x1800176ee  sub     rsp, 88h
0x1800176f5  mov     rax, cs:__security_cookie
0x1800176fc  xor     rax, rsp
0x1800176ff  mov     [rbp+57h+var_50], rax
0x180017703  xor     edi, edi
0x180017705  lea     rbx, [rbp+57h+var_80]
0x180017709  xor     r14d, r14d
0x18001770c  mov     [rbp+57h+var_90], rdi
0x180017710  mov     r12, rdx
0x180017713  mov     [rbp+57h+var_88], rdi
0x180017717  xor     esi, esi
0x180017719  lea     r15d, [rdi+2]
0x18001771d  lea     r13d, [rdi+1]
0x180017721  mov     rcx, rbx
0x180017724  call    ??0?$pair@PEAGPEAUIXMLDOMDocument2@@@std@@QEAA@XZ; std::pair<ushort *,IXMLDOMDocument2 *>::pair<ushort *,IXMLDOMDocument2 *>(void)
0x180017729  add     rbx, 10h
0x18001772d  sub     r15, r13
0x180017730  jnz     short loc_180017721
0x180017732  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits, 10h
0x180017739  jz      short loc_180017753
0x18001773b  lea     rax, [rbp+57h+var_60]
0x18001773f  mov     r9d, r13d
0x180017742  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_PERF_VALIDATE_START
0x180017749  mov     [rsp+0C0h+var_A0], rax
0x18001774e  call    McGenEventWrite_EventWriteTransfer
0x180017753  test    r12, r12
0x180017756  jnz     short loc_18001776B
0x180017758  mov     ebx, 80070057h
0x18001775d  mov     r8d, 3E8h
0x180017763  mov     r9d, ebx
0x180017766  jmp     loc_18001786E
0x18001776b  lea     rdx, aSchemaversion; "SchemaVersion"
0x180017772  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180017775  call    ?SdpCheckDocumentVersion@@YAJPEAUIXMLDOMDocument2@@PEBG1@Z; SdpCheckDocumentVersion(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x18001777a  mov     ebx, eax
0x18001777c  test    eax, eax
0x18001777e  jns     short loc_18001778B
0x180017780  mov     r8d, 3F1h
0x180017786  jmp     loc_18001786B
0x18001778b  mov     r15d, 0Ah
0x180017791  lea     rdx, [rbp+57h+var_88]; struct IXMLDOMDocument2 **
0x180017795  mov     r8d, r15d; unsigned __int16 *
0x180017798  lea     rcx, Name; "resource_schema.xsd"
0x18001779f  call    ?SdpXmlLoadResource@@YAJPEBGPEAPEAUIXMLDOMDocument2@@0@Z; SdpXmlLoadResource(ushort const *,IXMLDOMDocument2 * *,ushort const *)
0x1800177a4  mov     ebx, eax
0x1800177a6  test    eax, eax
0x1800177a8  jns     short loc_1800177B5
0x1800177aa  mov     r8d, 3F7h
0x1800177b0  jmp     loc_18001786B
0x1800177b5  mov     r8, r15; unsigned __int16 *
0x1800177b8  lea     rdx, [rbp+57h+var_90]; struct IXMLDOMDocument2 **
0x1800177bc  lea     rcx, aPackageSchemaX; "package_schema.xsd"
0x1800177c3  call    ?SdpXmlLoadResource@@YAJPEBGPEAPEAUIXMLDOMDocument2@@0@Z; SdpXmlLoadResource(ushort const *,IXMLDOMDocument2 * *,ushort const *)
0x1800177c8  mov     ebx, eax
0x1800177ca  test    eax, eax
0x1800177cc  jns     short loc_1800177EF
0x1800177ce  mov     r9d, eax; int
0x1800177d1  mov     r8d, 3FAh; int
0x1800177d7  lea     rdx, aDiagpackageVal; "DiagPackage::ValidatePackageXml"
0x1800177de  mov     ecx, r13d; Level
0x1800177e1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800177e6  mov     rdi, [rbp+57h+var_90]
0x1800177ea  jmp     loc_18001787D
0x1800177ef  lea     rcx, aHttpWwwMicroso; "http://www.microsoft.com/schemas/dcm/re"...
0x1800177f6  call    cs:__imp_SysAllocString
0x1800177fc  mov     rsi, rax
0x1800177ff  test    rax, rax
0x180017802  jnz     short loc_180017815
0x180017804  mov     r9d, 8007000Eh
0x18001780a  mov     r8d, 3FDh
0x180017810  mov     ebx, r9d
0x180017813  jmp     short loc_1800177D7
0x180017815  lea     rcx, aHttpWwwMicroso_0; "http://www.microsoft.com/schemas/dcm/pa"...
0x18001781c  call    cs:__imp_SysAllocString
0x180017822  mov     r14, rax
0x180017825  test    rax, rax
0x180017828  jnz     short loc_18001783B
0x18001782a  mov     r9d, 8007000Eh
0x180017830  mov     r8d, 400h
0x180017836  mov     ebx, r9d
0x180017839  jmp     short loc_1800177D7
0x18001783b  mov     rax, [rbp+57h+var_88]
0x18001783f  lea     rdx, [rbp+57h+var_80]
0x180017843  mov     rdi, [rbp+57h+var_90]
0x180017847  mov     rcx, r12
0x18001784a  mov     [rbp+57h+var_78], rax
0x18001784e  mov     [rbp+57h+var_68], rdi
0x180017852  mov     [rbp+57h+var_80], rsi
0x180017856  mov     [rbp+57h+var_70], r14
0x18001785a  call    ?SdpXmlValidate@@YAJPEAUIXMLDOMDocument2@@PEAU?$pair@PEAGPEAUIXMLDOMDocument2@@@std@@K@Z; SdpXmlValidate(IXMLDOMDocument2 *,std::pair<ushort *,IXMLDOMDocument2 *> *,ulong)
0x18001785f  mov     ebx, eax
0x180017861  test    eax, eax
0x180017863  jns     short loc_18001787D
0x180017865  mov     r8d, 40Fh; int
0x18001786b  mov     r9d, eax; int
0x18001786e  lea     rdx, aDiagpackageVal; "DiagPackage::ValidatePackageXml"
0x180017875  mov     ecx, r13d; Level
0x180017878  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001787d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits, 10h
0x180017884  jz      short loc_18001789E
0x180017886  lea     rax, [rbp+57h+var_60]
0x18001788a  mov     r9d, r13d
0x18001788d  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_PERF_VALIDATE_STOP
0x180017894  mov     [rsp+0C0h+var_A0], rax
0x180017899  call    McGenEventWrite_EventWriteTransfer
0x18001789e  test    r14, r14
0x1800178a1  jz      short loc_1800178AC
0x1800178a3  mov     rcx, r14; bstrString
0x1800178a6  call    cs:__imp_SysFreeString
0x1800178ac  test    rsi, rsi
0x1800178af  jz      short loc_1800178BA
0x1800178b1  mov     rcx, rsi; bstrString
0x1800178b4  call    cs:__imp_SysFreeString
0x1800178ba  test    rdi, rdi
0x1800178bd  jz      short loc_1800178CE
0x1800178bf  mov     rax, [rdi]
0x1800178c2  mov     rcx, rdi
0x1800178c5  mov     rax, [rax+10h]
0x1800178c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178ce  mov     rcx, [rbp+57h+var_88]
0x1800178d2  test    rcx, rcx
0x1800178d5  jz      short loc_1800178E3
0x1800178d7  mov     rax, [rcx]
0x1800178da  mov     rax, [rax+10h]
0x1800178de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178e3  mov     eax, ebx
0x1800178e5  mov     rcx, [rbp+57h+var_50]
0x1800178e9  xor     rcx, rsp; StackCookie
0x1800178ec  call    __security_check_cookie
0x1800178f1  add     rsp, 88h
0x1800178f8  pop     r15
0x1800178fa  pop     r14
0x1800178fc  pop     r13
0x1800178fe  pop     r12
0x180017900  pop     rdi
0x180017901  pop     rsi
0x180017902  pop     rbx
0x180017903  pop     rbp
0x180017904  retn
```
