# WdcDataCollectorSetFolder::WdcDataCollectorSetFolder(ushort const *,WdcDataCollectorSetRoot *,ulong,ushort const *,int)

- ea: `0x180052b80`
- end: `0x180052e3d`
- name: `??0WdcDataCollectorSetFolder@@QEAA@PEBGPEAVWdcDataCollectorSetRoot@@K0H@Z`
- size: `701`
- prototype: `WdcDataCollectorSetFolder *__fastcall(WdcDataCollectorSetFolder *this, const unsigned __int16 *, struct WdcDataCollectorSetRoot *, UINT, OLECHAR *psz, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180053cd0`

## callees

- `0x1800044ac`
- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18001cb20`
- `0x180032ba0`
- `0x180040730`
- `0x180052b80`
- `0x180066e18`
- `0x180084e04`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180052c6e`
- `OLEAUT32!__imp_SysAllocString` at `0x180052cac`
- `OLEAUT32!__imp_SysAllocString` at `0x180052d94`
- `OLEAUT32!__imp_SysAllocString` at `0x180052c6e`
- `OLEAUT32!__imp_SysAllocString` at `0x180052cac`
- `OLEAUT32!__imp_SysAllocString` at `0x180052d94`
- `OLEAUT32!__imp_SysFreeString` at `0x180052c5a`
- `OLEAUT32!__imp_SysFreeString` at `0x180052c90`
- `OLEAUT32!__imp_SysFreeString` at `0x180052d80`
- `OLEAUT32!__imp_SysFreeString` at `0x180052c5a`
- `OLEAUT32!__imp_SysFreeString` at `0x180052c90`
- `OLEAUT32!__imp_SysFreeString` at `0x180052d80`
- `ole32!CoCreateInstance` at `0x180052dee`
- `ole32!CoCreateInstance` at `0x180052dee`

## string_xrefs

- `0x180052cca`: `service`

## pseudocode

```c
WdcDataCollectorSetFolder *__fastcall WdcDataCollectorSetFolder::WdcDataCollectorSetFolder(
        WdcDataCollectorSetFolder *this,
        const unsigned __int16 *a2,
        struct WdcDataCollectorSetRoot *a3,
        UINT a4,
        OLECHAR *psz,
        int a6)
{
  const char *v9; // rdx
  int v10; // r8d
  WCHAR *v11; // rsi
  HRESULT String; // eax
  OLECHAR *v13; // rcx
  BSTR v14; // rax
  OLECHAR *v15; // rcx
  const wchar_t *v16; // rax
  const wchar_t *v17; // rbx
  OLECHAR *v18; // rcx
  BSTR v19; // rax
  const char *v20; // rdx
  int v21; // r8d
  LPVOID *ppv; // [rsp+20h] [rbp-48h]

  WdcBaseNode::WdcBaseNode(this, a2);
  *((_QWORD *)this + 58) = 0;
  *(_QWORD *)this = &WdcDataCollectorSetFolder::`vftable';
  *((_DWORD *)this + 120) = a6;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 55) = a3;
  *((_DWORD *)this + 121) = 0;
  v11 = (WCHAR *)WdcAlloc(0x208u, v9, v10);
  if ( v11 )
  {
    *v11 = 0;
    String = WdcLoadString(a4, v11, 0x104u);
    if ( String >= 0 )
    {
      v13 = (OLECHAR *)*((_QWORD *)this + 58);
      if ( v13 )
      {
        SysFreeString(v13);
        *((_QWORD *)this + 58) = 0;
      }
      v14 = SysAllocString(v11);
      if ( !v14 )
        goto LABEL_24;
      *((_QWORD *)this + 58) = v14;
      v15 = (OLECHAR *)*((_QWORD *)this + 56);
      if ( v15 )
      {
        SysFreeString(v15);
        *((_QWORD *)this + 56) = 0;
      }
      v16 = SysAllocString(psz);
      v17 = v16;
      if ( psz )
      {
        if ( !v16 )
          goto LABEL_24;
      }
      *((_QWORD *)this + 56) = v16;
      if ( !wcscmp_0(v16, L"service") )
      {
        *((_DWORD *)this + 108) = 4;
      }
      else if ( !wcscmp_0(v17, L"system") )
      {
        *((_DWORD *)this + 108) = 5;
      }
      else
      {
        *((_DWORD *)this + 108) = !wcscmp_0(v17, L"session") || !wcscmp_0(v17, L"autosession") ? 6 : -1;
      }
      String = StringCchCopyW(v11, 0x104u, psz);
      if ( String >= 0 )
      {
        String = StringCchCatW(v11, 0x104u, L"\\*");
        if ( String >= 0 )
        {
          v18 = (OLECHAR *)*((_QWORD *)this + 57);
          if ( v18 )
          {
            SysFreeString(v18);
            *((_QWORD *)this + 57) = 0;
          }
          v19 = SysAllocString(v11);
          if ( !v19 )
          {
LABEL_24:
            WdcDebugMessage(
              "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
              "WdcAssignString",
              0,
              L"FAILURE: 0x%08x",
              -2147024882);
            LODWORD(ppv) = -2147024882;
LABEL_28:
            WdcDebugMessage(
              "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetfolder.cpp",
              "WdcDataCollectorSetFolder::WdcDataCollectorSetFolder",
              0,
              L"FAILURE: 0x%08x",
              ppv);
LABEL_29:
            WdcFree(v11, v20, v21);
            return this;
          }
          *((_QWORD *)this + 57) = v19;
          String = CoCreateInstance(
                     &CLSID_DataCollectorSetCollection,
                     0,
                     0x15u,
                     &IID_IDataCollectorSetCollection,
                     (LPVOID *)this + 59);
          if ( String >= 0 )
          {
            String = WdcCoSetSecurity(*((struct IUnknown **)this + 59));
            if ( String >= 0 )
              goto LABEL_29;
          }
        }
      }
    }
    LODWORD(ppv) = String;
    goto LABEL_28;
  }
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetfolder.cpp",
    "WdcDataCollectorSetFolder::WdcDataCollectorSetFolder",
    0,
    L"FAILURE: 0x%08x",
    -2147024882);
  return this;
}

```

## disassembly

```asm
0x180052b80  push    rbx
0x180052b82  push    rbp
0x180052b83  push    rsi
0x180052b84  push    rdi
0x180052b85  push    r12
0x180052b87  push    r14
0x180052b89  sub     rsp, 38h
0x180052b8d  mov     ebp, r9d
0x180052b90  mov     rbx, r8
0x180052b93  mov     rdi, rcx
0x180052b96  call    ??0WdcBaseNode@@QEAA@PEBG@Z; WdcBaseNode::WdcBaseNode(ushort const *)
0x180052b9b  lea     rax, ??_7WdcDataCollectorSetFolder@@6B@; const WdcDataCollectorSetFolder::`vftable'
0x180052ba2  mov     qword ptr [rdi+1D0h], 0
0x180052bad  mov     [rdi], rax
0x180052bb0  lea     r14, [rdi+1D8h]
0x180052bb7  mov     eax, [rsp+68h+arg_28]
0x180052bbe  mov     ecx, 208h; dwBytes
0x180052bc3  mov     [rdi+1E0h], eax
0x180052bc9  mov     qword ptr [r14], 0
0x180052bd0  mov     qword ptr [rdi+1C0h], 0
0x180052bdb  mov     qword ptr [rdi+1C8h], 0
0x180052be6  mov     [rdi+1B8h], rbx
0x180052bed  mov     dword ptr [rdi+1E4h], 0
0x180052bf7  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180052bfc  mov     rsi, rax
0x180052bff  test    rax, rax
0x180052c02  jnz     short loc_180052C2E
0x180052c04  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180052c0b  mov     dword ptr [rsp+68h+ppv], 8007000Eh
0x180052c13  xor     r8d, r8d; int
0x180052c16  lea     rdx, aWdcdatacollect_126; "WdcDataCollectorSetFolder::WdcDataColle"...
0x180052c1d  lea     rcx, aBaseDiagnosisP_1; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x180052c24  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180052c29  jmp     loc_180052E2D
0x180052c2e  xor     eax, eax
0x180052c30  mov     r12d, 104h
0x180052c36  mov     r8d, r12d; cchBufferMax
0x180052c39  mov     [rsi], ax
0x180052c3c  mov     rdx, rsi; lpBuffer
0x180052c3f  mov     ecx, ebp; uID
0x180052c41  call    ?WdcLoadString@@YAJKPEAG_K@Z; WdcLoadString(ulong,ushort *,unsigned __int64)
0x180052c46  test    eax, eax
0x180052c48  js      loc_180052E04
0x180052c4e  mov     rcx, [rdi+1D0h]; bstrString
0x180052c55  test    rcx, rcx
0x180052c58  jz      short loc_180052C6B
0x180052c5a  call    cs:__imp_SysFreeString
0x180052c60  mov     qword ptr [rdi+1D0h], 0
0x180052c6b  mov     rcx, rsi; psz
0x180052c6e  call    cs:__imp_SysAllocString
0x180052c74  test    rax, rax
0x180052c77  jz      loc_180052D9F
0x180052c7d  mov     [rdi+1D0h], rax
0x180052c84  mov     rcx, [rdi+1C0h]; bstrString
0x180052c8b  test    rcx, rcx
0x180052c8e  jz      short loc_180052CA1
0x180052c90  call    cs:__imp_SysFreeString
0x180052c96  mov     qword ptr [rdi+1C0h], 0
0x180052ca1  mov     rbp, [rsp+68h+psz]
0x180052ca9  mov     rcx, rbp; psz
0x180052cac  call    cs:__imp_SysAllocString
0x180052cb2  mov     rbx, rax
0x180052cb5  test    rbp, rbp
0x180052cb8  jz      short loc_180052CC3
0x180052cba  test    rax, rax
0x180052cbd  jz      loc_180052D9F
0x180052cc3  mov     [rdi+1C0h], rbx
0x180052cca  lea     rdx, aService; "service"
0x180052cd1  mov     rcx, rbx; String1
0x180052cd4  call    wcscmp_0
0x180052cd9  test    eax, eax
0x180052cdb  jnz     short loc_180052CE9
0x180052cdd  mov     dword ptr [rdi+1B0h], 4
0x180052ce7  jmp     short loc_180052D44
0x180052ce9  lea     rdx, aSystem_0; "system"
0x180052cf0  mov     rcx, rbx; String1
0x180052cf3  call    wcscmp_0
0x180052cf8  test    eax, eax
0x180052cfa  jnz     short loc_180052D08
0x180052cfc  mov     dword ptr [rdi+1B0h], 5
0x180052d06  jmp     short loc_180052D44
0x180052d08  lea     rdx, aSession; "session"
0x180052d0f  mov     rcx, rbx; String1
0x180052d12  call    wcscmp_0
0x180052d17  test    eax, eax
0x180052d19  jz      short loc_180052D3A
0x180052d1b  lea     rdx, aAutosession; "autosession"
0x180052d22  mov     rcx, rbx; String1
0x180052d25  call    wcscmp_0
0x180052d2a  test    eax, eax
0x180052d2c  jz      short loc_180052D3A
0x180052d2e  mov     dword ptr [rdi+1B0h], 0FFFFFFFFh
0x180052d38  jmp     short loc_180052D44
0x180052d3a  mov     dword ptr [rdi+1B0h], 6
0x180052d44  mov     r8, rbp; unsigned __int16 *
0x180052d47  mov     rdx, r12; unsigned __int64
0x180052d4a  mov     rcx, rsi; unsigned __int16 *
0x180052d4d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180052d52  test    eax, eax
0x180052d54  js      loc_180052E04
0x180052d5a  lea     r8, asc_180091E94; "\\*"
0x180052d61  mov     rdx, r12; unsigned __int64
0x180052d64  mov     rcx, rsi; unsigned __int16 *
0x180052d67  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180052d6c  test    eax, eax
0x180052d6e  js      loc_180052E04
0x180052d74  mov     rcx, [rdi+1C8h]; bstrString
0x180052d7b  test    rcx, rcx
0x180052d7e  jz      short loc_180052D91
0x180052d80  call    cs:__imp_SysFreeString
0x180052d86  mov     qword ptr [rdi+1C8h], 0
0x180052d91  mov     rcx, rsi; psz
0x180052d94  call    cs:__imp_SysAllocString
0x180052d9a  test    rax, rax
0x180052d9d  jnz     short loc_180052DCE
0x180052d9f  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180052da6  mov     dword ptr [rsp+68h+ppv], 8007000Eh
0x180052dae  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180052db5  xor     r8d, r8d; int
0x180052db8  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180052dbf  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180052dc4  mov     dword ptr [rsp+68h+ppv], 8007000Eh
0x180052dcc  jmp     short loc_180052E08
0x180052dce  mov     [rdi+1C8h], rax
0x180052dd5  xor     edx, edx; pUnkOuter
0x180052dd7  mov     [rsp+68h+ppv], r14; ppv
0x180052ddc  lea     r9, IID_IDataCollectorSetCollection; riid
0x180052de3  lea     rcx, CLSID_DataCollectorSetCollection; rclsid
0x180052dea  lea     r8d, [rdx+15h]; dwClsContext
0x180052dee  call    cs:__imp_CoCreateInstance
0x180052df4  test    eax, eax
0x180052df6  js      short loc_180052E04
0x180052df8  mov     rcx, [r14]; struct IUnknown *
0x180052dfb  call    ?WdcCoSetSecurity@@YAJPEAUIUnknown@@@Z; WdcCoSetSecurity(IUnknown *)
0x180052e00  test    eax, eax
0x180052e02  jns     short loc_180052E25
0x180052e04  mov     dword ptr [rsp+68h+ppv], eax
0x180052e08  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180052e0f  xor     r8d, r8d; int
0x180052e12  lea     rdx, aWdcdatacollect_126; "WdcDataCollectorSetFolder::WdcDataColle"...
0x180052e19  lea     rcx, aBaseDiagnosisP_1; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x180052e20  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180052e25  mov     rcx, rsi; void *
0x180052e28  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180052e2d  mov     rax, rdi
0x180052e30  add     rsp, 38h
0x180052e34  pop     r14
0x180052e36  pop     r12
0x180052e38  pop     rdi
0x180052e39  pop     rsi
0x180052e3a  pop     rbp
0x180052e3b  pop     rbx
0x180052e3c  retn
```
