# SdpUpdateReportData(Settings *,IXMLDOMDocument2 *,ushort *,ushort *,ushort *,ushort *,ushort *)

- ea: `0x180004d58`
- end: `0x180005333`
- name: `?SdpUpdateReportData@@YAJPEAVSettings@@PEAUIXMLDOMDocument2@@PEAG2222@Z`
- size: `1499`
- prototype: `__int64 __fastcall(struct Settings *, struct IXMLDOMDocument2 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *String1)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180014544`
- `0x180018718`
- `0x18001d470`

## callees

- `0x1800012a4`
- `0x180004d58`
- `0x180005ffc`
- `0x180026fa0`
- `0x180027ea4`
- `0x1800280f8`
- `0x18002827c`
- `0x1800291e0`
- `0x1800298c0`
- `0x18002a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180004ee0`
- `msvcrt!_wcsicmp` at `0x180004f5b`
- `msvcrt!_wcsicmp` at `0x180004fd6`
- `msvcrt!_wcsicmp` at `0x180005051`
- `msvcrt!_wcsicmp` at `0x180004ee0`
- `msvcrt!_wcsicmp` at `0x180004f5b`
- `msvcrt!_wcsicmp` at `0x180004fd6`
- `msvcrt!_wcsicmp` at `0x180005051`

## string_xrefs

- `0x180004ddb`: `SdpUpdateReportData`
- `0x180004e4f`: `SdpUpdateReportData`
- `0x180004e98`: `SdpUpdateReportData`
- `0x180005115`: `SdpUpdateReportData`
- `0x180005178`: `SdpUpdateReportData`
- `0x180005233`: `SdpUpdateReportData`
- `0x1800052ad`: `SdpUpdateReportData`
- `0x180004e3a`: `<?xml version="1.0" encoding="utf-8"?><Detail/>`

## pseudocode

```c
__int64 __fastcall SdpUpdateReportData(
        struct Settings *a1,
        struct IXMLDOMDocument2 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *String1)
{
  struct IXMLDOMDocument2 *v7; // rsi
  struct IXMLDOMElement *v8; // rdi
  void *v9; // r13
  unsigned int v11; // r8d
  unsigned int v12; // ebx
  int v13; // eax
  struct IXMLDOMDocument2 *v14; // r15
  const unsigned __int16 *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  int v18; // r9d
  const wchar_t *v19; // rbx
  __int64 v20; // rax
  unsigned __int16 *v21; // r8
  __int64 v22; // rdx
  unsigned __int16 *v23; // rcx
  const wchar_t *v24; // rbx
  __int64 v25; // rax
  unsigned __int16 *v26; // r8
  __int64 v27; // rdx
  unsigned __int16 *v28; // rcx
  const wchar_t *v29; // rbx
  __int64 v30; // rax
  unsigned __int16 *v31; // r8
  __int64 v32; // rdx
  unsigned __int16 *v33; // rcx
  const wchar_t *v34; // rbx
  __int64 v35; // rax
  unsigned __int16 *v36; // r8
  __int64 v37; // rdx
  unsigned __int16 *v38; // rcx
  int v39; // eax
  unsigned int v40; // r8d
  int String; // eax
  int v42; // eax
  int v43; // eax
  int v44; // r9d
  unsigned int v45; // r8d
  int v46; // eax
  struct IXMLDOMElement *v48; // [rsp+30h] [rbp-D0h] BYREF
  struct IXMLDOMDocument2 *v49; // [rsp+38h] [rbp-C8h] BYREF
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  struct IXMLDOMDocument2 *v51; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v52; // [rsp+50h] [rbp-B0h]
  OLECHAR *psz; // [rsp+58h] [rbp-A8h]
  struct IXMLDOMDocument2 *v54; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v55[1024]; // [rsp+70h] [rbp-90h] BYREF

  v7 = 0;
  v8 = 0;
  v9 = 0;
  psz = a3;
  v54 = a2;
  v52 = a6;
  v51 = 0;
  v49 = 0;
  v48 = 0;
  Block = 0;
  if ( !a1 )
  {
    v11 = 1516;
LABEL_3:
    v12 = -2147024809;
    SdpDebugTrace(1u, L"SdpUpdateReportData", v11, -2147024809);
    return v12;
  }
  if ( !a4 )
  {
    v11 = 1517;
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v11 = 1518;
    goto LABEL_3;
  }
  if ( !a6 )
  {
    v11 = 1519;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v11 = 1520;
    goto LABEL_3;
  }
  if ( !String1 )
  {
    v11 = 1521;
    goto LABEL_3;
  }
  v13 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Detail/>", &v49);
  v12 = v13;
  if ( v13 >= 0 )
  {
    v15 = a4;
    v14 = v49;
    v16 = SdpXmlSetAttribute(v49, 0, L"id", v15);
    v12 = v16;
    if ( v16 < 0 )
    {
      v17 = 1534;
LABEL_18:
      v18 = v16;
LABEL_19:
      SdpDebugTrace(1u, L"SdpUpdateReportData", v17, v18);
      goto LABEL_85;
    }
    v16 = SdpXmlSetAttribute(v14, 0, L"name", a5);
    v12 = v16;
    if ( v16 < 0 )
    {
      v17 = 1537;
      goto LABEL_18;
    }
    v19 = L"Warning";
    if ( _wcsicmp(String1, L"Warning") )
    {
      v24 = L"Error";
      if ( _wcsicmp(String1, L"Error") )
      {
        v29 = L"Debug";
        if ( _wcsicmp(String1, L"Debug") )
        {
          v34 = L"Informational";
          if ( _wcsicmp(String1, L"Informational") )
          {
            v44 = -2147024809;
            v45 = 1557;
            v12 = -2147024809;
            goto LABEL_82;
          }
          v35 = 2147483646;
          v36 = v55;
          v37 = 1024;
          do
          {
            if ( !v35 )
              break;
            if ( !*v34 )
              break;
            *v36++ = *v34++;
            --v35;
            --v37;
          }
          while ( v37 );
          v38 = v36 - 1;
          v12 = v37 == 0 ? 0x8007007A : 0;
          if ( v37 )
            v38 = v36;
          *v38 = 0;
          if ( !v37 )
          {
            v18 = -2147024774;
            v17 = 1554;
            goto LABEL_19;
          }
        }
        else
        {
          v30 = 2147483646;
          v31 = v55;
          v32 = 1024;
          do
          {
            if ( !v30 )
              break;
            if ( !*v29 )
              break;
            *v31++ = *v29++;
            --v30;
            --v32;
          }
          while ( v32 );
          v33 = v31 - 1;
          v12 = v32 == 0 ? 0x8007007A : 0;
          if ( v32 )
            v33 = v31;
          *v33 = 0;
          if ( !v32 )
          {
            v18 = -2147024774;
            v17 = 1551;
            goto LABEL_19;
          }
        }
      }
      else
      {
        v25 = 2147483646;
        v26 = v55;
        v27 = 1024;
        do
        {
          if ( !v25 )
            break;
          if ( !*v24 )
            break;
          *v26++ = *v24++;
          --v25;
          --v27;
        }
        while ( v27 );
        v28 = v26 - 1;
        v12 = v27 == 0 ? 0x8007007A : 0;
        if ( v27 )
          v28 = v26;
        *v28 = 0;
        if ( !v27 )
        {
          v18 = -2147024774;
          v17 = 1548;
          goto LABEL_19;
        }
      }
    }
    else
    {
      v20 = 2147483646;
      v21 = v55;
      v22 = 1024;
      do
      {
        if ( !v20 )
          break;
        if ( !*v19 )
          break;
        *v21++ = *v19++;
        --v20;
        --v22;
      }
      while ( v22 );
      v23 = v21 - 1;
      v12 = v22 == 0 ? 0x8007007A : 0;
      if ( v22 )
        v23 = v21;
      *v23 = 0;
      if ( !v22 )
      {
        v18 = -2147024774;
        v17 = 1545;
        goto LABEL_19;
      }
    }
    v16 = SdpXmlSetAttribute(v14, 0, L"verbosity", v55);
    v12 = v16;
    if ( v16 < 0 )
    {
      v17 = 1564;
      goto LABEL_18;
    }
    v39 = SdpXmlCreateNode(v14, 0, L"Data", v52, &v48);
    v12 = v39;
    if ( v39 < 0 )
    {
      v40 = 1575;
LABEL_62:
      SdpDebugTrace(1u, L"SdpUpdateReportData", v40, v39);
      v8 = v48;
      goto LABEL_85;
    }
    v8 = v48;
    v16 = SdpXmlSetAttribute(0, v48, L"id", L"Description");
    v12 = v16;
    if ( v16 < 0 )
    {
      v17 = 1581;
      goto LABEL_18;
    }
    String = SdpLoadString(0, 0x76u, (unsigned __int16 **)&Block);
    v12 = String;
    if ( String < 0 )
    {
      SdpDebugTrace(1u, L"SdpUpdateReportData", 0x630u, String);
      v9 = Block;
      goto LABEL_85;
    }
    v9 = Block;
    v16 = SdpXmlSetAttribute(0, v8, L"name", (const unsigned __int16 *)Block);
    v12 = v16;
    if ( v16 < 0 )
    {
      v17 = 1587;
      goto LABEL_18;
    }
    if ( v8 )
    {
      ((void (__fastcall *)(struct IXMLDOMElement *))v8->lpVtbl->Release)(v8);
      v48 = 0;
    }
    if ( v9 )
    {
      operator delete(v9);
      v9 = 0;
    }
    v39 = SdpXmlCreateNode(v14, 0, L"Contents", 0, &v48);
    v12 = v39;
    if ( v39 < 0 )
    {
      v40 = 1601;
      goto LABEL_62;
    }
    v42 = SdpXmlCreate(psz, &v51);
    v12 = v42;
    if ( v42 < 0 )
    {
      SdpDebugTrace(1u, L"SdpUpdateReportData", 0x648u, v42);
      v7 = v51;
      v8 = v48;
      goto LABEL_83;
    }
    v7 = v51;
    v8 = v48;
    v43 = SdpXmlAppend(0, v48, v51);
    v12 = v43;
    if ( v43 >= 0 )
    {
      v46 = SdpXmlAppend(v54, 0, v14);
      v12 = v46;
      if ( v46 >= 0 )
        goto LABEL_83;
      v44 = v46;
      v45 = 1618;
    }
    else
    {
      v44 = v43;
      v45 = 1611;
    }
LABEL_82:
    SdpDebugTrace(1u, L"SdpUpdateReportData", v45, v44);
LABEL_83:
    if ( v7 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
    goto LABEL_85;
  }
  SdpDebugTrace(1u, L"SdpUpdateReportData", 0x5F8u, v13);
  v14 = v49;
LABEL_85:
  if ( v14 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v14->lpVtbl->Release)(v14);
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v8->lpVtbl->Release)(v8);
  if ( v9 )
    operator delete(v9);
  return v12;
}

```

## disassembly

```asm
0x180004d58  mov     [rsp-8+arg_0], rbx
0x180004d5d  push    rbp
0x180004d5e  push    rsi
0x180004d5f  push    rdi
0x180004d60  push    r12
0x180004d62  push    r13
0x180004d64  push    r14
0x180004d66  push    r15
0x180004d68  lea     rbp, [rsp-780h]
0x180004d70  sub     rsp, 880h
0x180004d77  mov     rax, cs:__security_cookie
0x180004d7e  xor     rax, rsp
0x180004d81  mov     [rbp+7B0h+var_40], rax
0x180004d88  mov     rax, [rbp+7B0h+arg_28]
0x180004d8f  xor     esi, esi
0x180004d91  mov     r12, [rbp+7B0h+arg_20]
0x180004d98  xor     edi, edi
0x180004d9a  mov     r14, [rbp+7B0h+String1]
0x180004da1  xor     r13d, r13d
0x180004da4  mov     [rsp+8B0h+psz], r8
0x180004da9  mov     r15, r9
0x180004dac  mov     [rsp+8B0h+var_850], rdx
0x180004db1  mov     [rsp+8B0h+var_860], rax
0x180004db6  mov     [rsp+8B0h+var_868], rsi
0x180004dbb  mov     [rsp+8B0h+var_878], rsi
0x180004dc0  mov     [rsp+8B0h+var_880], rdi
0x180004dc5  mov     [rsp+8B0h+Block], r13
0x180004dca  test    rcx, rcx
0x180004dcd  jnz     short loc_180004DF4
0x180004dcf  mov     r8d, 5ECh; int
0x180004dd5  mov     r9d, 80070057h; int
0x180004ddb  lea     rdx, aSdpupdaterepor; "SdpUpdateReportData"
0x180004de2  mov     ecx, 1; Level
0x180004de7  mov     ebx, r9d
0x180004dea  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180004def  jmp     loc_180005307
0x180004df4  test    r15, r15
0x180004df7  jnz     short loc_180004E01
0x180004df9  mov     r8d, 5EDh
0x180004dff  jmp     short loc_180004DD5
0x180004e01  test    r12, r12
0x180004e04  jnz     short loc_180004E0E
0x180004e06  mov     r8d, 5EEh
0x180004e0c  jmp     short loc_180004DD5
0x180004e0e  test    rax, rax
0x180004e11  jnz     short loc_180004E1B
0x180004e13  mov     r8d, 5EFh
0x180004e19  jmp     short loc_180004DD5
0x180004e1b  test    r8, r8
0x180004e1e  jnz     short loc_180004E28
0x180004e20  mov     r8d, 5F0h
0x180004e26  jmp     short loc_180004DD5
0x180004e28  test    r14, r14
0x180004e2b  jnz     short loc_180004E35
0x180004e2d  mov     r8d, 5F1h
0x180004e33  jmp     short loc_180004DD5
0x180004e35  lea     rdx, [rsp+8B0h+var_878]; struct IXMLDOMDocument2 **
0x180004e3a  lea     rcx, aXmlVersion10En_1; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180004e41  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180004e46  mov     ebx, eax
0x180004e48  test    eax, eax
0x180004e4a  jns     short loc_180004E70
0x180004e4c  mov     r9d, eax; int
0x180004e4f  lea     rdx, aSdpupdaterepor; "SdpUpdateReportData"
0x180004e56  mov     r8d, 5F8h; int
0x180004e5c  mov     ecx, 1; Level
0x180004e61  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180004e66  mov     r15, [rsp+8B0h+var_878]
0x180004e6b  jmp     loc_1800052D2
0x180004e70  mov     r9, r15; unsigned __int16 *
0x180004e73  lea     r8, aId_0; "id"
0x180004e7a  mov     r15, [rsp+8B0h+var_878]
0x180004e7f  xor     edx, edx; struct IXMLDOMElement *
0x180004e81  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180004e84  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180004e89  mov     ebx, eax
0x180004e8b  test    eax, eax
0x180004e8d  jns     short loc_180004EAE
0x180004e8f  mov     r8d, 5FEh; int
0x180004e95  mov     r9d, eax; int
0x180004e98  lea     rdx, aSdpupdaterepor; "SdpUpdateReportData"
0x180004e9f  mov     ecx, 1; Level
0x180004ea4  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180004ea9  jmp     loc_1800052D2
0x180004eae  mov     r9, r12; unsigned __int16 *
0x180004eb1  lea     r8, aName_0; "name"
0x180004eb8  xor     edx, edx; struct IXMLDOMElement *
0x180004eba  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180004ebd  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x180004ec2  xor     r12d, r12d
0x180004ec5  mov     ebx, eax
0x180004ec7  test    eax, eax
0x180004ec9  jns     short loc_180004ED3
0x180004ecb  mov     r8d, 601h
0x180004ed1  jmp     short loc_180004E95
0x180004ed3  lea     rbx, aWarning; "Warning"
0x180004eda  mov     rcx, r14; String1
0x180004edd  mov     rdx, rbx; String2
0x180004ee0  call    cs:__imp__wcsicmp
0x180004ee6  test    eax, eax
0x180004ee8  jnz     short loc_180004F4E
0x180004eea  mov     eax, 7FFFFFFEh
0x180004eef  lea     r8, [rsp+8B0h+var_840]
0x180004ef4  mov     edx, 400h
0x180004ef9  test    rax, rax
0x180004efc  jz      short loc_180004F1B
0x180004efe  movzx   ecx, word ptr [rbx]
0x180004f01  test    cx, cx
0x180004f04  jz      short loc_180004F1B
0x180004f06  mov     [r8], cx
0x180004f0a  add     rbx, 2
0x180004f0e  add     r8, 2
0x180004f12  dec     rax
0x180004f15  sub     rdx, 1
0x180004f19  jnz     short loc_180004EF9
0x180004f1b  mov     rax, rdx
0x180004f1e  lea     rcx, [r8-2]
0x180004f22  neg     rax
0x180004f25  sbb     ebx, ebx
0x180004f27  not     ebx
0x180004f29  and     ebx, 8007007Ah
0x180004f2f  test    rdx, rdx
0x180004f32  cmovnz  rcx, r8
0x180004f36  mov     [rcx], r12w
0x180004f3a  jnz     loc_1800050BF
0x180004f40  mov     r9d, ebx
0x180004f43  mov     r8d, 609h
0x180004f49  jmp     loc_180004E98
0x180004f4e  lea     rbx, aError; "Error"
0x180004f55  mov     rcx, r14; String1
0x180004f58  mov     rdx, rbx; String2
0x180004f5b  call    cs:__imp__wcsicmp
0x180004f61  test    eax, eax
0x180004f63  jnz     short loc_180004FC9
0x180004f65  mov     eax, 7FFFFFFEh
0x180004f6a  lea     r8, [rsp+8B0h+var_840]
0x180004f6f  mov     edx, 400h
0x180004f74  test    rax, rax
0x180004f77  jz      short loc_180004F96
0x180004f79  movzx   ecx, word ptr [rbx]
0x180004f7c  test    cx, cx
0x180004f7f  jz      short loc_180004F96
0x180004f81  mov     [r8], cx
0x180004f85  add     rbx, 2
0x180004f89  add     r8, 2
0x180004f8d  dec     rax
0x180004f90  sub     rdx, 1
0x180004f94  jnz     short loc_180004F74
0x180004f96  mov     rax, rdx
0x180004f99  lea     rcx, [r8-2]
0x180004f9d  neg     rax
0x180004fa0  sbb     ebx, ebx
0x180004fa2  not     ebx
0x180004fa4  and     ebx, 8007007Ah
0x180004faa  test    rdx, rdx
0x180004fad  cmovnz  rcx, r8
0x180004fb1  mov     [rcx], r12w
0x180004fb5  jnz     loc_1800050BF
0x180004fbb  mov     r9d, ebx
0x180004fbe  mov     r8d, 60Ch
0x180004fc4  jmp     loc_180004E98
0x180004fc9  lea     rbx, aDebug; "Debug"
0x180004fd0  mov     rcx, r14; String1
0x180004fd3  mov     rdx, rbx; String2
0x180004fd6  call    cs:__imp__wcsicmp
0x180004fdc  test    eax, eax
0x180004fde  jnz     short loc_180005044
0x180004fe0  mov     eax, 7FFFFFFEh
0x180004fe5  lea     r8, [rsp+8B0h+var_840]
0x180004fea  mov     edx, 400h
0x180004fef  test    rax, rax
0x180004ff2  jz      short loc_180005011
0x180004ff4  movzx   ecx, word ptr [rbx]
0x180004ff7  test    cx, cx
0x180004ffa  jz      short loc_180005011
0x180004ffc  mov     [r8], cx
0x180005000  add     rbx, 2
0x180005004  add     r8, 2
0x180005008  dec     rax
0x18000500b  sub     rdx, 1
0x18000500f  jnz     short loc_180004FEF
0x180005011  mov     rax, rdx
0x180005014  lea     rcx, [r8-2]
0x180005018  neg     rax
0x18000501b  sbb     ebx, ebx
0x18000501d  not     ebx
0x18000501f  and     ebx, 8007007Ah
0x180005025  test    rdx, rdx
0x180005028  cmovnz  rcx, r8
0x18000502c  mov     [rcx], r12w
0x180005030  jnz     loc_1800050BF
0x180005036  mov     r9d, ebx
0x180005039  mov     r8d, 60Fh
0x18000503f  jmp     loc_180004E98
0x180005044  lea     rbx, aInformational; "Informational"
0x18000504b  mov     rcx, r14; String1
0x18000504e  mov     rdx, rbx; String2
0x180005051  call    cs:__imp__wcsicmp
0x180005057  test    eax, eax
0x180005059  jnz     loc_18000529E
0x18000505f  mov     eax, 7FFFFFFEh
0x180005064  lea     r8, [rsp+8B0h+var_840]
0x180005069  mov     edx, 400h
0x18000506e  test    rax, rax
0x180005071  jz      short loc_180005090
0x180005073  movzx   ecx, word ptr [rbx]
0x180005076  test    cx, cx
0x180005079  jz      short loc_180005090
0x18000507b  mov     [r8], cx
0x18000507f  add     rbx, 2
0x180005083  add     r8, 2
0x180005087  dec     rax
0x18000508a  sub     rdx, 1
0x18000508e  jnz     short loc_18000506E
0x180005090  mov     rax, rdx
0x180005093  lea     rcx, [r8-2]
0x180005097  neg     rax
0x18000509a  sbb     ebx, ebx
0x18000509c  not     ebx
0x18000509e  and     ebx, 8007007Ah
0x1800050a4  test    rdx, rdx
0x1800050a7  cmovnz  rcx, r8
0x1800050ab  mov     [rcx], r12w
0x1800050af  jnz     short loc_1800050BF
0x1800050b1  mov     r9d, ebx
0x1800050b4  mov     r8d, 612h
0x1800050ba  jmp     loc_180004E98
0x1800050bf  lea     r9, [rsp+8B0h+var_840]; unsigned __int16 *
0x1800050c4  xor     edx, edx; struct IXMLDOMElement *
0x1800050c6  lea     r8, aVerbosity; "verbosity"
0x1800050cd  mov     rcx, r15; struct IXMLDOMDocument2 *
0x1800050d0  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x1800050d5  mov     ebx, eax
0x1800050d7  test    eax, eax
0x1800050d9  jns     short loc_1800050E6
0x1800050db  mov     r8d, 61Ch
0x1800050e1  jmp     loc_180004E95
0x1800050e6  mov     r9, [rsp+8B0h+var_860]; unsigned __int16 *
0x1800050eb  lea     rax, [rsp+8B0h+var_880]
0x1800050f0  lea     r8, aData; "Data"
0x1800050f7  mov     [rsp+8B0h+var_890], rax; struct IXMLDOMElement **
0x1800050fc  xor     edx, edx; struct IXMLDOMElement *
0x1800050fe  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180005101  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180005106  mov     ebx, eax
0x180005108  test    eax, eax
0x18000510a  jns     short loc_180005130
0x18000510c  mov     r8d, 627h; int
0x180005112  mov     r9d, eax; int
0x180005115  lea     rdx, aSdpupdaterepor; "SdpUpdateReportData"
0x18000511c  mov     ecx, 1; Level
0x180005121  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180005126  mov     rdi, [rsp+8B0h+var_880]
0x18000512b  jmp     loc_1800052D2
0x180005130  mov     rdi, [rsp+8B0h+var_880]
0x180005135  lea     r9, aDescription; "Description"
0x18000513c  mov     rdx, rdi; struct IXMLDOMElement *
0x18000513f  lea     r8, aId_0; "id"
0x180005146  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180005148  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x18000514d  mov     ebx, eax
0x18000514f  test    eax, eax
0x180005151  jns     short loc_18000515E
0x180005153  mov     r8d, 62Dh
0x180005159  jmp     loc_180004E95
0x18000515e  lea     r8, [rsp+8B0h+Block]; unsigned __int16 **
0x180005163  mov     edx, 76h ; 'v'; unsigned int
0x180005168  xor     ecx, ecx; unsigned __int16 *
0x18000516a  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x18000516f  mov     ebx, eax
0x180005171  test    eax, eax
0x180005173  jns     short loc_180005199
0x180005175  mov     r9d, eax; int
0x180005178  lea     rdx, aSdpupdaterepor; "SdpUpdateReportData"
0x18000517f  mov     r8d, 630h; int
0x180005185  mov     ecx, 1; Level
0x18000518a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000518f  mov     r13, [rsp+8B0h+Block]
0x180005194  jmp     loc_1800052D2
0x180005199  mov     r13, [rsp+8B0h+Block]
0x18000519e  lea     r8, aName_0; "name"
0x1800051a5  mov     r9, r13; unsigned __int16 *
0x1800051a8  mov     rdx, rdi; struct IXMLDOMElement *
0x1800051ab  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x1800051ad  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x1800051b2  mov     ebx, eax
0x1800051b4  test    eax, eax
0x1800051b6  jns     short loc_1800051C3
0x1800051b8  mov     r8d, 633h
0x1800051be  jmp     loc_180004E95
0x1800051c3  test    rdi, rdi
0x1800051c6  jz      short loc_1800051DC
0x1800051c8  mov     rax, [rdi]
0x1800051cb  mov     rcx, rdi
0x1800051ce  mov     rax, [rax+10h]
0x1800051d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051d7  mov     [rsp+8B0h+var_880], r12
0x1800051dc  test    r13, r13
0x1800051df  jz      short loc_1800051EC
0x1800051e1  mov     rcx, r13; Block
  ... truncated ...
```
