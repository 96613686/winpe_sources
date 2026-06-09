# WdcReportCabinet::WdcReportCabinet(ushort const *,ulong,ushort const *)

- ea: `0x18004cd28`
- end: `0x18004cf2e`
- name: `??0WdcReportCabinet@@QEAA@PEBGK0@Z`
- size: `518`
- prototype: `WdcReportCabinet *__fastcall(WdcReportCabinet *this, const unsigned __int16 *, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180050230`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18001cb20`
- `0x180032ba0`
- `0x180040730`
- `0x18004cd28`
- `0x180066e18`
- `0x180084e04`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004ce09`
- `OLEAUT32!__imp_SysAllocString` at `0x18004ced6`
- `OLEAUT32!__imp_SysAllocString` at `0x18004ce09`
- `OLEAUT32!__imp_SysAllocString` at `0x18004ced6`
- `OLEAUT32!__imp_SysFreeString` at `0x18004cdf5`
- `OLEAUT32!__imp_SysFreeString` at `0x18004cec2`
- `OLEAUT32!__imp_SysFreeString` at `0x18004cdf5`
- `OLEAUT32!__imp_SysFreeString` at `0x18004cec2`
- `ole32!CoCreateInstance` at `0x18004cd8c`
- `ole32!CoCreateInstance` at `0x18004cd8c`

## string_xrefs

- `0x18004ce27`: `service`

## pseudocode

```c
WdcReportCabinet *__fastcall WdcReportCabinet::WdcReportCabinet(
        WdcReportCabinet *this,
        const unsigned __int16 *a2,
        int a3,
        const unsigned __int16 *a4)
{
  HRESULT Instance; // eax
  const char *v8; // rdx
  int v9; // r8d
  unsigned __int16 *v10; // rbx
  OLECHAR *v11; // rcx
  const wchar_t *v12; // rax
  const wchar_t *v13; // rsi
  int v14; // eax
  unsigned __int64 v15; // r11
  const char *v16; // rdx
  int v17; // r8d
  OLECHAR *v18; // rcx
  BSTR v19; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-38h]

  WdcBaseNode::WdcBaseNode(this, a2);
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  *(_QWORD *)this = &WdcReportCabinet::`vftable';
  *((_QWORD *)this + 54) = 0;
  *((_DWORD *)this + 110) = a3;
  Instance = CoCreateInstance(
               &CLSID_DataCollectorSetCollection,
               0,
               0x15u,
               &IID_IDataCollectorSetCollection,
               (LPVOID *)this + 54);
  if ( Instance >= 0 )
  {
    Instance = WdcCoSetSecurity(*((struct IUnknown **)this + 54));
    if ( Instance >= 0 )
    {
      v10 = (unsigned __int16 *)WdcAlloc(0x208u, v8, v9);
      if ( !v10 )
      {
        LODWORD(ppv) = -2147024882;
        goto LABEL_3;
      }
      *v10 = 0;
      v11 = (OLECHAR *)*((_QWORD *)this + 56);
      if ( v11 )
      {
        SysFreeString(v11);
        *((_QWORD *)this + 56) = 0;
      }
      v12 = SysAllocString(a4);
      v13 = v12;
      if ( !a4 || v12 )
      {
        *((_QWORD *)this + 56) = v12;
        if ( !wcscmp_0(v12, L"service") )
          *((_DWORD *)this + 111) = 8;
        else
          *((_DWORD *)this + 111) = wcscmp_0(v13, L"system") != 0 ? -1 : 9;
        v14 = StringCchCopyW(v10, 0x104u, a4);
        if ( v14 < 0 || (v14 = StringCchCatW(v10, v15, L"\\*"), v14 < 0) )
        {
          LODWORD(ppv) = v14;
LABEL_16:
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mmc\\reportnode.cpp",
            "WdcReportCabinet::WdcReportCabinet",
            0,
            L"FAILURE: 0x%08x",
            ppv);
LABEL_23:
          WdcFree(v10, v16, v17);
          return this;
        }
        v18 = (OLECHAR *)*((_QWORD *)this + 57);
        if ( v18 )
        {
          SysFreeString(v18);
          *((_QWORD *)this + 57) = 0;
        }
        v19 = SysAllocString(v10);
        if ( v19 )
        {
          *((_QWORD *)this + 57) = v19;
          goto LABEL_23;
        }
      }
      LODWORD(ppv) = -2147024882;
      WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", ppv);
      LODWORD(ppv) = -2147024882;
      goto LABEL_16;
    }
  }
  LODWORD(ppv) = Instance;
LABEL_3:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\reportnode.cpp",
    "WdcReportCabinet::WdcReportCabinet",
    0,
    L"FAILURE: 0x%08x",
    ppv);
  return this;
}

```

## disassembly

```asm
0x18004cd28  push    rbx
0x18004cd2a  push    rbp
0x18004cd2b  push    rsi
0x18004cd2c  push    rdi
0x18004cd2d  sub     rsp, 38h
0x18004cd31  mov     rbp, r9
0x18004cd34  mov     ebx, r8d
0x18004cd37  mov     rdi, rcx
0x18004cd3a  call    ??0WdcBaseNode@@QEAA@PEBG@Z; WdcBaseNode::WdcBaseNode(ushort const *)
0x18004cd3f  xor     edx, edx; pUnkOuter
0x18004cd41  mov     qword ptr [rdi+1C0h], 0
0x18004cd4c  lea     rax, ??_7WdcReportCabinet@@6B@; const WdcReportCabinet::`vftable'
0x18004cd53  mov     qword ptr [rdi+1C8h], 0
0x18004cd5e  lea     rsi, [rdi+1B0h]
0x18004cd65  mov     [rdi], rax
0x18004cd68  lea     r9, IID_IDataCollectorSetCollection; riid
0x18004cd6f  mov     qword ptr [rsi], 0
0x18004cd76  lea     r8d, [rdx+15h]; dwClsContext
0x18004cd7a  mov     [rdi+1B8h], ebx
0x18004cd80  lea     rcx, CLSID_DataCollectorSetCollection; rclsid
0x18004cd87  mov     [rsp+58h+ppv], rsi; ppv
0x18004cd8c  call    cs:__imp_CoCreateInstance
0x18004cd92  test    eax, eax
0x18004cd94  jns     short loc_18004CDBC
0x18004cd96  mov     dword ptr [rsp+58h+ppv], eax
0x18004cd9a  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18004cda1  xor     r8d, r8d; int
0x18004cda4  lea     rdx, aWdcreportcabin_1; "WdcReportCabinet::WdcReportCabinet"
0x18004cdab  lea     rcx, aBaseDiagnosisP_40; "base\\diagnosis\\pdui\\perfmon\\mmc\\re"...
0x18004cdb2  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18004cdb7  jmp     loc_18004CF22
0x18004cdbc  mov     rcx, [rsi]; struct IUnknown *
0x18004cdbf  call    ?WdcCoSetSecurity@@YAJPEAUIUnknown@@@Z; WdcCoSetSecurity(IUnknown *)
0x18004cdc4  test    eax, eax
0x18004cdc6  js      short loc_18004CD96
0x18004cdc8  mov     ecx, 208h; dwBytes
0x18004cdcd  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18004cdd2  mov     rbx, rax
0x18004cdd5  test    rax, rax
0x18004cdd8  jnz     short loc_18004CDE4
0x18004cdda  mov     dword ptr [rsp+58h+ppv], 8007000Eh
0x18004cde2  jmp     short loc_18004CD9A
0x18004cde4  xor     eax, eax
0x18004cde6  mov     [rbx], ax
0x18004cde9  mov     rcx, [rdi+1C0h]; bstrString
0x18004cdf0  test    rcx, rcx
0x18004cdf3  jz      short loc_18004CE06
0x18004cdf5  call    cs:__imp_SysFreeString
0x18004cdfb  mov     qword ptr [rdi+1C0h], 0
0x18004ce06  mov     rcx, rbp; psz
0x18004ce09  call    cs:__imp_SysAllocString
0x18004ce0f  mov     rsi, rax
0x18004ce12  test    rbp, rbp
0x18004ce15  jz      short loc_18004CE20
0x18004ce17  test    rax, rax
0x18004ce1a  jz      loc_18004CEE1
0x18004ce20  mov     [rdi+1C0h], rsi
0x18004ce27  lea     rdx, aService; "service"
0x18004ce2e  mov     rcx, rsi; String1
0x18004ce31  call    wcscmp_0
0x18004ce36  test    eax, eax
0x18004ce38  jnz     short loc_18004CE46
0x18004ce3a  mov     dword ptr [rdi+1BCh], 8
0x18004ce44  jmp     short loc_18004CE65
0x18004ce46  lea     rdx, aSystem_0; "system"
0x18004ce4d  mov     rcx, rsi; String1
0x18004ce50  call    wcscmp_0
0x18004ce55  neg     eax
0x18004ce57  sbb     ecx, ecx
0x18004ce59  and     ecx, 0FFFFFFF6h
0x18004ce5c  add     ecx, 9
0x18004ce5f  mov     [rdi+1BCh], ecx
0x18004ce65  mov     r11d, 104h
0x18004ce6b  mov     r8, rbp; unsigned __int16 *
0x18004ce6e  mov     edx, r11d; unsigned __int64
0x18004ce71  mov     rcx, rbx; unsigned __int16 *
0x18004ce74  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004ce79  test    eax, eax
0x18004ce7b  jns     short loc_18004CEA0
0x18004ce7d  mov     dword ptr [rsp+58h+ppv], eax
0x18004ce81  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18004ce88  xor     r8d, r8d; int
0x18004ce8b  lea     rdx, aWdcreportcabin_1; "WdcReportCabinet::WdcReportCabinet"
0x18004ce92  lea     rcx, aBaseDiagnosisP_40; "base\\diagnosis\\pdui\\perfmon\\mmc\\re"...
0x18004ce99  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18004ce9e  jmp     short loc_18004CF1A
0x18004cea0  lea     r8, asc_180091E94; "\\*"
0x18004cea7  mov     rdx, r11; unsigned __int64
0x18004ceaa  mov     rcx, rbx; unsigned __int16 *
0x18004cead  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004ceb2  test    eax, eax
0x18004ceb4  js      short loc_18004CE7D
0x18004ceb6  mov     rcx, [rdi+1C8h]; bstrString
0x18004cebd  test    rcx, rcx
0x18004cec0  jz      short loc_18004CED3
0x18004cec2  call    cs:__imp_SysFreeString
0x18004cec8  mov     qword ptr [rdi+1C8h], 0
0x18004ced3  mov     rcx, rbx; psz
0x18004ced6  call    cs:__imp_SysAllocString
0x18004cedc  test    rax, rax
0x18004cedf  jnz     short loc_18004CF13
0x18004cee1  xor     r8d, r8d; int
0x18004cee4  mov     dword ptr [rsp+58h+ppv], 8007000Eh
0x18004ceec  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18004cef3  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18004cefa  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18004cf01  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18004cf06  mov     dword ptr [rsp+58h+ppv], 8007000Eh
0x18004cf0e  jmp     loc_18004CE81
0x18004cf13  mov     [rdi+1C8h], rax
0x18004cf1a  mov     rcx, rbx; void *
0x18004cf1d  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18004cf22  mov     rax, rdi
0x18004cf25  add     rsp, 38h
0x18004cf29  pop     rdi
0x18004cf2a  pop     rsi
0x18004cf2b  pop     rbp
0x18004cf2c  pop     rbx
0x18004cf2d  retn
```
