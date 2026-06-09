# CXWizard::HrParseXMLFile(ushort * const,ulong,IXMLDOMParseError * *)

- ea: `0x180016dd4`
- end: `0x1800172ef`
- name: `?HrParseXMLFile@CXWizard@@AEAAJQEAGKPEAPEAUIXMLDOMParseError@@@Z`
- size: `1307`
- prototype: `int(CXWizard *__hidden this, unsigned __int16 *const, unsigned int, struct IXMLDOMParseError **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017350`

## callees

- `0x180004370`
- `0x1800085a8`
- `0x180008634`
- `0x18000ae04`
- `0x18000ae90`
- `0x1800124c0`
- `0x180014f08`
- `0x180016dd4`
- `0x180032a02`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016edd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016edd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016f74`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016f74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017297`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017297`
- `OLEAUT32!__imp_SysAllocString` at `0x180016e11`
- `OLEAUT32!__imp_SysAllocString` at `0x180016fdc`
- `OLEAUT32!__imp_SysAllocString` at `0x180017030`
- `OLEAUT32!__imp_SysAllocString` at `0x180016e11`
- `OLEAUT32!__imp_SysAllocString` at `0x180016fdc`
- `OLEAUT32!__imp_SysAllocString` at `0x180017030`
- `OLEAUT32!__imp_SysFreeString` at `0x180017023`
- `OLEAUT32!__imp_SysFreeString` at `0x18001707a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800172a0`
- `OLEAUT32!__imp_SysFreeString` at `0x180017023`
- `OLEAUT32!__imp_SysFreeString` at `0x18001707a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800172a0`
- `OLEAUT32!__imp_VariantInit` at `0x180016f38`
- `OLEAUT32!__imp_VariantInit` at `0x180016fc5`
- `OLEAUT32!__imp_VariantInit` at `0x180016f38`
- `OLEAUT32!__imp_VariantInit` at `0x180016fc5`

## pseudocode

```c
__int64 __fastcall CXWizard::HrParseXMLFile(
        CXWizard *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IXMLDOMParseError **a4)
{
  OLECHAR *v6; // r15
  HANDLE v8; // r13
  unsigned int v9; // r11d
  char LastErrorHRESULT; // al
  HRESULT v11; // eax
  unsigned int v12; // ebx
  OLECHAR *v13; // rbx
  __int64 v14; // rdx
  OLECHAR *v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  const struct IXMLDOMParseError *v21; // r8
  __int16 v22; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  struct IXMLDOMParseError *v24; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v25; // [rsp+58h] [rbp-A8h]
  __int64 *v26; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v27; // [rsp+68h] [rbp-98h] BYREF
  struct IXWizard *v28; // [rsp+80h] [rbp-80h]
  VARIANTARG v29; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR FileName; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v32[526]; // [rsp+D2h] [rbp-2Eh] BYREF

  v28 = this;
  v25 = a3;
  v6 = SysAllocString(a2);
  if ( v6 )
  {
    v8 = 0;
    if ( (v25 & 0x10000) != 0 )
    {
      memset_0(v32, 0, 0x208u);
      FileName = 0;
      StringCchCopyW(&FileName, 0x105u, a2);
      StringCchCatW(&FileName, v9, L".man");
      v8 = CreateFileW(&FileName, 0xC0000000, 0, 0, 2u, 0x80u, 0);
      if ( v8 == (HANDLE)-1LL
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        LastErrorHRESULT = GetLastErrorHRESULT();
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)WPP_f05614902d2b35c2540f8a05e236bf04_Traceguids,
          (unsigned int)&FileName,
          LastErrorHRESULT);
      }
    }
    memset(&pvarg, 0, sizeof(pvarg));
    v22 = 0;
    VariantInit(&pvarg);
    pvarg.llVal = (LONGLONG)v6;
    pvarg.vt = 8;
    ppv = 0;
    v11 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x401u, &IID_IXMLDOMDocument, &ppv);
    v12 = v11;
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_f05614902d2b35c2540f8a05e236bf04_Traceguids,
          (_DWORD)v6,
          v11);
    }
    else
    {
      v26 = 0;
      if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 **))ppv)(ppv, &IID_IXMLDOMDocument, &v26) >= 0 )
      {
        memset(&v27, 0, sizeof(v27));
        VariantInit(&v27);
        v27.vt = 11;
        v13 = SysAllocString(L"ProhibitDTD");
        if ( v13 )
        {
          v29.pRecInfo = v27.pRecInfo;
          v27.iVal = 0;
          v14 = *v26;
          *(_OWORD *)&v29.vt = *(_OWORD *)&v27.vt;
          (*(void (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *))(v14 + 640))(v26, v13, &v29);
          SysFreeString(v13);
        }
        v15 = SysAllocString(L"ResolveExternals");
        if ( v15 )
        {
          v27.iVal = 1;
          v16 = *v26;
          v29 = v27;
          (*(void (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *))(v16 + 640))(v26, v15, &v29);
          SysFreeString(v15);
        }
        (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
      }
      v17 = *(_QWORD *)ppv;
      v29 = pvarg;
      v12 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v17 + 464))(ppv, &v29, &v22);
      if ( v12 || v22 != -1 )
      {
        if ( a4 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              18,
              (unsigned int)WPP_f05614902d2b35c2540f8a05e236bf04_Traceguids,
              (_DWORD)v6,
              v12);
          if ( v12 == 1 )
            v12 = -2147467259;
          v20 = (*(__int64 (__fastcall **)(LPVOID, struct IXMLDOMParseError **))(*(_QWORD *)ppv + 480LL))(ppv, a4);
          if ( v20 >= 0 && (v21 = *a4) != 0 )
          {
            v24 = 0;
            CXMLDOMParseError::HrCreateInstance(v28, (const struct IXMLDOMDocument *)ppv, v21, &v24);
            ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
            *a4 = v24;
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              WPP_f05614902d2b35c2540f8a05e236bf04_Traceguids,
              (unsigned int)v20);
          }
        }
      }
      else
      {
        v24 = 0;
        v18 = (*(__int64 (__fastcall **)(LPVOID, struct IXMLDOMParseError **))(*(_QWORD *)ppv + 360LL))(ppv, &v24);
        v12 = v18;
        if ( v18 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              (unsigned int)WPP_f05614902d2b35c2540f8a05e236bf04_Traceguids,
              (_DWORD)v6,
              v18);
        }
        else
        {
          v19 = HrProcessXML((struct IXMLDOMElement *)v24, v25, v8, v28);
          v12 = v19;
          if ( v19 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)WPP_f05614902d2b35c2540f8a05e236bf04_Traceguids,
              (_DWORD)v6,
              v19);
          ((void (__fastcall *)(struct IXMLDOMParseError *))v24->lpVtbl->Release)(v24);
        }
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v8 )
      CloseHandle(v8);
    SysFreeString(v6);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_f05614902d2b35c2540f8a05e236bf04_Traceguids, v12);
    return v12;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_f05614902d2b35c2540f8a05e236bf04_Traceguids, 2147942414LL);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180016dd4  push    rbp
0x180016dd6  push    rbx
0x180016dd7  push    rsi
0x180016dd8  push    rdi
0x180016dd9  push    r12
0x180016ddb  push    r13
0x180016ddd  push    r15
0x180016ddf  lea     rbp, [rsp-1F0h]
0x180016de7  sub     rsp, 2F0h
0x180016dee  mov     rax, cs:__security_cookie
0x180016df5  xor     rax, rsp
0x180016df8  mov     [rbp+220h+var_40], rax
0x180016dff  mov     [rbp+220h+var_2A0], rcx
0x180016e03  mov     r12, r9
0x180016e06  mov     rcx, rdx; psz
0x180016e09  mov     [rsp+320h+var_2C8], r8d
0x180016e0e  mov     rbx, rdx
0x180016e11  call    cs:__imp_SysAllocString
0x180016e17  mov     r15, rax
0x180016e1a  test    rax, rax
0x180016e1d  jnz     short loc_180016E5B
0x180016e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e26  lea     rdi, WPP_GLOBAL_Control
0x180016e2d  cmp     rcx, rdi
0x180016e30  jz      short loc_180016E51
0x180016e32  test    byte ptr [rcx+1Ch], 4
0x180016e36  jz      short loc_180016E51
0x180016e38  mov     rcx, [rcx+10h]
0x180016e3c  lea     edx, [rax+0Eh]
0x180016e3f  mov     r9d, 8007000Eh
0x180016e45  lea     r8, WPP_f05614902d2b35c2540f8a05e236bf04_Traceguids
0x180016e4c  call    WPP_SF_d
0x180016e51  mov     eax, 8007000Eh
0x180016e56  jmp     loc_1800172CE
0x180016e5b  xor     r13d, r13d
0x180016e5e  lea     rsi, WPP_f05614902d2b35c2540f8a05e236bf04_Traceguids
0x180016e65  test    [rsp+320h+var_2C8], 10000h
0x180016e6d  lea     rdi, WPP_GLOBAL_Control
0x180016e74  jz      loc_180016F22
0x180016e7a  xor     edx, edx; Val
0x180016e7c  lea     rcx, [rbp+220h+var_24E]; void *
0x180016e80  mov     r8d, 208h; Size
0x180016e86  call    memset_0
0x180016e8b  xor     eax, eax
0x180016e8d  lea     rcx, [rbp+220h+FileName]; unsigned __int16 *
0x180016e91  mov     r11d, 105h
0x180016e97  mov     [rbp+220h+FileName], ax
0x180016e9b  mov     edx, r11d; unsigned __int64
0x180016e9e  mov     r8, rbx; unsigned __int16 *
0x180016ea1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016ea6  lea     r8, aMan; ".man"
0x180016ead  mov     edx, r11d; unsigned __int64
0x180016eb0  lea     rcx, [rbp+220h+FileName]; unsigned __int16 *
0x180016eb4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016eb9  mov     [rsp+320h+hTemplateFile], r13; hTemplateFile
0x180016ebe  lea     rcx, [rbp+220h+FileName]; lpFileName
0x180016ec2  mov     [rsp+320h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180016eca  xor     r9d, r9d; lpSecurityAttributes
0x180016ecd  xor     r8d, r8d; dwShareMode
0x180016ed0  mov     [rsp+320h+dwCreationDisposition], 2; dwCreationDisposition
0x180016ed8  mov     edx, 0C0000000h; dwDesiredAccess
0x180016edd  call    cs:__imp_CreateFileW
0x180016ee3  mov     r13, rax
0x180016ee6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016eea  jnz     short loc_180016F22
0x180016eec  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ef3  cmp     rcx, rdi
0x180016ef6  jz      short loc_180016F22
0x180016ef8  test    byte ptr [rcx+1Ch], 4
0x180016efc  jz      short loc_180016F22
0x180016efe  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180016f03  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f0a  lea     edx, [r13+10h]
0x180016f0e  lea     r9, [rbp+220h+FileName]
0x180016f12  mov     [rsp+320h+dwCreationDisposition], eax
0x180016f16  mov     r8, rsi
0x180016f19  mov     rcx, [rcx+10h]
0x180016f1d  call    WPP_SF_SD
0x180016f22  xor     eax, eax
0x180016f24  lea     rcx, [rbp+220h+pvarg]; pvarg
0x180016f28  xorps   xmm0, xmm0
0x180016f2b  mov     qword ptr [rbp+220h+pvarg+10h], rax
0x180016f2f  movups  xmmword ptr [rbp+220h+pvarg], xmm0
0x180016f33  mov     [rsp+320h+var_2E0], ax
0x180016f38  call    cs:__imp_VariantInit
0x180016f3e  mov     eax, 8
0x180016f43  mov     qword ptr [rbp+220h+pvarg+8], r15
0x180016f47  mov     word ptr [rbp+220h+pvarg], ax
0x180016f4b  lea     r9, IID_IXMLDOMDocument; riid
0x180016f52  lea     rax, [rsp+320h+ppv]
0x180016f57  mov     [rsp+320h+ppv], 0
0x180016f60  xor     edx, edx; pUnkOuter
0x180016f62  mov     qword ptr [rsp+320h+dwCreationDisposition], rax; ppv
0x180016f67  mov     r8d, 401h; dwClsContext
0x180016f6d  lea     rcx, CLSID_DOMDocument60; rclsid
0x180016f74  call    cs:__imp_CoCreateInstance
0x180016f7a  mov     ebx, eax
0x180016f7c  test    eax, eax
0x180016f7e  js      loc_180017265
0x180016f84  mov     rcx, [rsp+320h+ppv]
0x180016f89  lea     r8, [rsp+320h+var_2C0]
0x180016f8e  mov     [rsp+320h+var_2C0], 0
0x180016f97  lea     rdx, IID_IXMLDOMDocument
0x180016f9e  mov     rax, [rcx]
0x180016fa1  mov     rax, [rax]
0x180016fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fa9  test    eax, eax
0x180016fab  js      loc_180017091
0x180016fb1  xorps   xmm0, xmm0
0x180016fb4  lea     rcx, [rsp+320h+var_2B8]; pvarg
0x180016fb9  xor     eax, eax
0x180016fbb  movups  xmmword ptr [rsp+320h+var_2B8], xmm0
0x180016fc0  mov     qword ptr [rsp+320h+var_2B8+10h], rax
0x180016fc5  call    cs:__imp_VariantInit
0x180016fcb  mov     eax, 0Bh
0x180016fd0  lea     rcx, psz; "ProhibitDTD"
0x180016fd7  mov     word ptr [rsp+320h+var_2B8], ax
0x180016fdc  call    cs:__imp_SysAllocString
0x180016fe2  mov     rbx, rax
0x180016fe5  test    rax, rax
0x180016fe8  jz      short loc_180017029
0x180016fea  movsd   xmm1, qword ptr [rsp+320h+var_2B8+10h]
0x180016ff0  lea     r8, [rbp+220h+var_290]
0x180016ff4  xor     ecx, ecx
0x180016ff6  movsd   [rbp+220h+var_280], xmm1
0x180016ffb  mov     word ptr [rsp+320h+var_2B8+8], cx
0x180017000  mov     rcx, [rsp+320h+var_2C0]
0x180017005  movups  xmm0, xmmword ptr [rsp+320h+var_2B8]
0x18001700a  mov     rdx, [rcx]
0x18001700d  movaps  [rbp+220h+var_290], xmm0
0x180017011  mov     rax, [rdx+280h]
0x180017018  mov     rdx, rbx
0x18001701b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017020  mov     rcx, rbx; bstrString
0x180017023  call    cs:__imp_SysFreeString
0x180017029  lea     rcx, aResolveexterna; "ResolveExternals"
0x180017030  call    cs:__imp_SysAllocString
0x180017036  mov     rbx, rax
0x180017039  test    rax, rax
0x18001703c  jz      short loc_180017080
0x18001703e  mov     rcx, [rsp+320h+var_2C0]
0x180017043  lea     r8, [rbp+220h+var_290]
0x180017047  movsd   xmm1, qword ptr [rsp+320h+var_2B8+10h]
0x18001704d  mov     eax, 1
0x180017052  mov     word ptr [rsp+320h+var_2B8+8], ax
0x180017057  movups  xmm0, xmmword ptr [rsp+320h+var_2B8]
0x18001705c  mov     rdx, [rcx]
0x18001705f  movsd   [rbp+220h+var_280], xmm1
0x180017064  movaps  [rbp+220h+var_290], xmm0
0x180017068  mov     rax, [rdx+280h]
0x18001706f  mov     rdx, rbx
0x180017072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017077  mov     rcx, rbx; bstrString
0x18001707a  call    cs:__imp_SysFreeString
0x180017080  mov     rcx, [rsp+320h+var_2C0]
0x180017085  mov     rax, [rcx]
0x180017088  mov     rax, [rax+10h]
0x18001708c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017091  mov     rcx, [rsp+320h+ppv]
0x180017096  lea     r8, [rsp+320h+var_2E0]
0x18001709b  movups  xmm0, xmmword ptr [rbp+220h+pvarg]
0x18001709f  lea     rdx, [rbp+220h+var_290]
0x1800170a3  movsd   xmm1, qword ptr [rbp+220h+pvarg+10h]
0x1800170a8  mov     rax, [rcx]
0x1800170ab  movaps  [rbp+220h+var_290], xmm0
0x1800170af  movsd   [rbp+220h+var_280], xmm1
0x1800170b4  mov     rax, [rax+1D0h]
0x1800170bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170c0  mov     ebx, eax
0x1800170c2  test    eax, eax
0x1800170c4  jnz     loc_180017193
0x1800170ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800170ce  cmp     ax, [rsp+320h+var_2E0]
0x1800170d3  jnz     loc_180017193
0x1800170d9  mov     rcx, [rsp+320h+ppv]
0x1800170de  lea     rdx, [rsp+320h+var_2D0]
0x1800170e3  mov     [rsp+320h+var_2D0], 0
0x1800170ec  mov     rax, [rcx]
0x1800170ef  mov     rax, [rax+168h]
0x1800170f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170fb  mov     ebx, eax
0x1800170fd  test    eax, eax
0x1800170ff  js      short loc_18001715C
0x180017101  mov     r9, [rbp+220h+var_2A0]; struct IXWizard *
0x180017105  mov     r8, r13; void *
0x180017108  mov     edx, [rsp+320h+var_2C8]; unsigned int
0x18001710c  mov     rcx, [rsp+320h+var_2D0]; struct IXMLDOMElement *
0x180017111  call    ?HrProcessXML@@YAJPEAUIXMLDOMElement@@KPEAXPEAUIXWizard@@@Z; HrProcessXML(IXMLDOMElement *,ulong,void *,IXWizard *)
0x180017116  mov     ebx, eax
0x180017118  test    eax, eax
0x18001711a  jns     short loc_180017146
0x18001711c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017123  cmp     rcx, rdi
0x180017126  jz      short loc_180017146
0x180017128  test    byte ptr [rcx+1Ch], 4
0x18001712c  jz      short loc_180017146
0x18001712e  mov     rcx, [rcx+10h]
0x180017132  mov     edx, 10h
0x180017137  mov     r9, r15
0x18001713a  mov     [rsp+320h+dwCreationDisposition], eax
0x18001713e  mov     r8, rsi
0x180017141  call    WPP_SF_SD
0x180017146  mov     rcx, [rsp+320h+var_2D0]
0x18001714b  mov     rax, [rcx]
0x18001714e  mov     rax, [rax+10h]
0x180017152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017157  jmp     loc_180017252
0x18001715c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017163  cmp     rcx, rdi
0x180017166  jz      loc_180017252
0x18001716c  test    byte ptr [rcx+1Ch], 4
0x180017170  jz      loc_180017252
0x180017176  mov     rcx, [rcx+10h]
0x18001717a  mov     edx, 11h
0x18001717f  mov     r9, r15
0x180017182  mov     [rsp+320h+dwCreationDisposition], eax
0x180017186  mov     r8, rsi
0x180017189  call    WPP_SF_SD
0x18001718e  jmp     loc_180017252
0x180017193  test    r12, r12
0x180017196  jz      loc_180017252
0x18001719c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171a3  cmp     rcx, rdi
0x1800171a6  jz      short loc_1800171C6
0x1800171a8  test    byte ptr [rcx+1Ch], 8
0x1800171ac  jz      short loc_1800171C6
0x1800171ae  mov     rcx, [rcx+10h]
0x1800171b2  mov     edx, 12h
0x1800171b7  mov     r9, r15
0x1800171ba  mov     [rsp+320h+dwCreationDisposition], ebx
0x1800171be  mov     r8, rsi
0x1800171c1  call    WPP_SF_SD
0x1800171c6  mov     rcx, [rsp+320h+ppv]
0x1800171cb  mov     eax, 80004005h
0x1800171d0  cmp     ebx, 1
0x1800171d3  mov     rdx, r12
0x1800171d6  cmovz   ebx, eax
0x1800171d9  mov     rax, [rcx]
0x1800171dc  mov     rax, [rax+1E0h]
0x1800171e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171e8  test    eax, eax
0x1800171ea  js      short loc_18001722C
0x1800171ec  mov     r8, [r12]; struct IXMLDOMParseError *
0x1800171f0  test    r8, r8
0x1800171f3  jz      short loc_18001722C
0x1800171f5  mov     rdx, [rsp+320h+ppv]; struct IXMLDOMDocument *
0x1800171fa  lea     r9, [rsp+320h+var_2D0]; struct IXMLDOMParseError **
0x1800171ff  mov     rcx, [rbp+220h+var_2A0]; struct IXWizard *
0x180017203  mov     [rsp+320h+var_2D0], 0
0x18001720c  call    ?HrCreateInstance@CXMLDOMParseError@@SAJPEBUIXWizard@@PEBUIXMLDOMDocument@@PEBUIXMLDOMParseError@@PEAPEAU4@@Z; CXMLDOMParseError::HrCreateInstance(IXWizard const *,IXMLDOMDocument const *,IXMLDOMParseError const *,IXMLDOMParseError * *)
0x180017211  mov     rcx, [r12]
0x180017215  mov     rax, [rcx]
0x180017218  mov     rax, [rax+10h]
0x18001721c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017221  mov     rax, [rsp+320h+var_2D0]
0x180017226  mov     [r12], rax
0x18001722a  jmp     short loc_180017252
0x18001722c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017233  cmp     rcx, rdi
0x180017236  jz      short loc_180017252
0x180017238  test    byte ptr [rcx+1Ch], 4
0x18001723c  jz      short loc_180017252
0x18001723e  mov     rcx, [rcx+10h]
0x180017242  mov     edx, 13h
0x180017247  mov     r9d, eax
0x18001724a  mov     r8, rsi
0x18001724d  call    WPP_SF_d
0x180017252  mov     rcx, [rsp+320h+ppv]
0x180017257  mov     rax, [rcx]
0x18001725a  mov     rax, [rax+10h]
0x18001725e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017263  jmp     short loc_18001728F
0x180017265  mov     rcx, cs:WPP_GLOBAL_Control
0x18001726c  cmp     rcx, rdi
0x18001726f  jz      short loc_18001728F
0x180017271  test    byte ptr [rcx+1Ch], 4
0x180017275  jz      short loc_18001728F
0x180017277  mov     rcx, [rcx+10h]
0x18001727b  mov     edx, 14h
0x180017280  mov     r9, r15
0x180017283  mov     [rsp+320h+dwCreationDisposition], eax
0x180017287  mov     r8, rsi
0x18001728a  call    WPP_SF_SD
0x18001728f  test    r13, r13
0x180017292  jz      short loc_18001729D
0x180017294  mov     rcx, r13; hObject
0x180017297  call    cs:__imp_CloseHandle
0x18001729d  mov     rcx, r15; bstrString
0x1800172a0  call    cs:__imp_SysFreeString
0x1800172a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800172ad  cmp     rcx, rdi
0x1800172b0  jz      short loc_1800172CC
0x1800172b2  test    byte ptr [rcx+1Ch], 10h
0x1800172b6  jz      short loc_1800172CC
0x1800172b8  mov     rcx, [rcx+10h]
0x1800172bc  mov     edx, 15h
0x1800172c1  mov     r9d, ebx
0x1800172c4  mov     r8, rsi
0x1800172c7  call    WPP_SF_d
0x1800172cc  mov     eax, ebx
  ... truncated ...
```
