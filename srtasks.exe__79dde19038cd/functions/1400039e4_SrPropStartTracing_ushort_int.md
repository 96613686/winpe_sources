# SrPropStartTracing(ushort * *,int)

- ea: `0x1400039e4`
- end: `0x140003dbc`
- name: `?SrPropStartTracing@@YAJPEAPEAGH@Z`
- size: `984`
- prototype: `__int64 __fastcall(LPVOID *, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140002f30`
- `0x14000312c`

## callees

- `0x140003320`
- `0x1400039e4`
- `0x14000595c`
- `0x14000e324`
- `0x14000e41c`
- `0x14000ed4c`
- `0x14000f0b0`
- `0x14000f188`
- `0x14000f7a0`
- `0x14000fa1c`
- `0x14000fd0c`
- `0x140010574`
- `0x140010744`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140003a8c`
- `ADVAPI32!RegOpenKeyExW` at `0x140003a8c`
- `ADVAPI32!RegCloseKey` at `0x140003d90`
- `ADVAPI32!RegCloseKey` at `0x140003d90`
- `ole32!CoTaskMemFree` at `0x140003d70`
- `ole32!CoTaskMemFree` at `0x140003d70`

## string_xrefs

- `0x140003b90`: `SrTasks`

## pseudocode

```c
__int64 __fastcall SrPropStartTracing(LPVOID *a1, int a2)
{
  unsigned int v4; // ebx
  __int16 v5; // ax
  int v6; // eax
  bool v7; // sf
  int v8; // ecx
  __int16 v9; // ax
  const unsigned __int16 *v10; // rcx
  const unsigned __int16 *v11; // r9
  unsigned int v12; // edx
  const unsigned __int16 *v13; // rcx
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  const unsigned __int16 *phkResult; // [rsp+20h] [rbp-99h]
  const unsigned __int16 *v18; // [rsp+28h] [rbp-91h]
  const unsigned __int16 *v19; // [rsp+30h] [rbp-89h]
  const unsigned __int16 *v20; // [rsp+38h] [rbp-81h]
  const unsigned __int16 *v21; // [rsp+40h] [rbp-79h]
  const unsigned __int16 *v22; // [rsp+48h] [rbp-71h]
  const unsigned __int16 *v23; // [rsp+50h] [rbp-69h]
  int started; // [rsp+60h] [rbp-59h] BYREF
  __int16 v25; // [rsp+64h] [rbp-55h]
  __int16 v26; // [rsp+66h] [rbp-53h]
  GUID ProviderId; // [rsp+A0h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-9h] BYREF
  unsigned __int16 *v29; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v30; // [rsp+C0h] [rbp+7h]
  int v31; // [rsp+C8h] [rbp+Fh] BYREF
  __int16 v32; // [rsp+CCh] [rbp+13h]
  __int16 v33; // [rsp+CEh] [rbp+15h]
  unsigned int v34; // [rsp+120h] [rbp+67h] BYREF
  TRACEHANDLE TraceHandle; // [rsp+130h] [rbp+77h] BYREF
  LPVOID pv; // [rsp+138h] [rbp+7Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&started, "SrPropStartTracing", 0x43Eu, 1u);
  hKey = 0;
  v29 = (unsigned __int16 *)qword_140013960;
  v4 = 503316717;
  v30 = 0;
  v5 = 1096;
  TraceHandle = -1;
  v34 = 503316717;
  pv = 0;
  if ( !a1 )
  {
    started = -2147024809;
    goto LABEL_33;
  }
  v25 = 1096;
  *a1 = 0;
  started = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SystemRestore",
         0,
         0x20019u,
         &hKey);
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  started = v6;
  v7 = v6 < 0;
  v5 = 1098;
  if ( v7 )
    goto LABEL_33;
  v25 = 1098;
  v8 = SxCheckWBDiagSession();
  started = v8;
  v5 = 1103;
  if ( v8 < 0 )
    goto LABEL_33;
  v25 = 1103;
  if ( v8 == 1 )
  {
    started = 1;
    v9 = 1106;
LABEL_8:
    v25 = v9;
    goto LABEL_34;
  }
  if ( (unsigned int)SxRegReadDWORD(hKey, L"SystemRestoreTracingFlags", &v34, 0) )
  {
    if ( a2 )
    {
      started = 0;
      v9 = 1125;
      goto LABEL_8;
    }
  }
  else
  {
    v4 = v34;
    if ( !v34 )
    {
      started = 0;
      v9 = 1119;
      goto LABEL_8;
    }
  }
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v31, "SrPropStopTracing", 0x4B2u, 1u);
  v31 = SxStopTracing(v10);
  if ( v31 >= 0 )
    v32 = 1204;
  else
    v33 = 1204;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v31);
  started = GetAndEnsureTracingDirectory((struct CBsString *)&v29);
  v5 = 1134;
  if ( started < 0 )
    goto LABEL_33;
  v25 = 1134;
  if ( !(_DWORD)v30 )
  {
    started = -2147020579;
LABEL_21:
    v5 = 1136;
    goto LABEL_33;
  }
  started = CBsString::_CombinePathImpl((CBsString *)&v29, L"SrTasks", 0, v11, phkResult, v18, v19, v20, v21, v22, v23);
  if ( started < 0 )
    goto LABEL_21;
  v25 = 1136;
  started = SxRotateLogs(v29, v12);
  v5 = 1138;
  if ( started >= 0 )
  {
    v25 = 1138;
    started = SxStartTracing(v13, v29, v14, &TraceHandle, (unsigned __int16 **)&pv);
    v5 = 1144;
    if ( started >= 0 )
    {
      v25 = 1144;
      ProviderId = c_guidGuiTracingControlGuid;
      started = SxEnableTraceDefault(TraceHandle, &ProviderId, v4);
      v5 = 1146;
      if ( started >= 0 )
      {
        v25 = 1146;
        ProviderId = c_guidSppTracingControlGuid;
        started = SxEnableTraceDefault(TraceHandle, &ProviderId, v4);
        v5 = 1147;
        if ( started >= 0 )
        {
          v25 = 1147;
          ProviderId = c_guidSrClientTracingControlGuid;
          started = SxEnableTraceDefault(TraceHandle, &ProviderId, v4);
          v5 = 1148;
          if ( started >= 0 )
          {
            v25 = 1148;
            ProviderId = c_guidSrClientTracingControlGuid;
            started = SxEnableTraceDefault(TraceHandle, &ProviderId, v4);
            v5 = 1149;
            if ( started >= 0 )
            {
              v25 = 1149;
              ProviderId = c_guidSrPropTracingControlGuid;
              started = SxEnableTraceDefault(TraceHandle, &ProviderId, v4);
              v5 = 1150;
              if ( started >= 0 )
              {
                v25 = 1150;
                ProviderId = c_guidAsrTracingControlGuid;
                started = SxEnableTraceCustom(TraceHandle, &ProviderId, 0xFFu, 0xFFu);
                v5 = 1155;
                if ( started >= 0 )
                {
                  v25 = 1155;
                  ProviderId = c_guidUdfdTracingControlGuid;
                  started = SxEnableTraceCustom(TraceHandle, &ProviderId, 0xFFu, 0xFFu);
                  v5 = 1160;
                  if ( started >= 0 )
                  {
                    v25 = 1160;
                    *a1 = pv;
                    pv = 0;
                    goto LABEL_34;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_33:
  v26 = v5;
LABEL_34:
  CoTaskMemFree(pv);
  v15 = started;
  CBsString::_Release((CBsString *)&v29);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&started);
  return v15;
}

```

## disassembly

```asm
0x1400039e4  mov     [rsp-8+arg_8], rbx
0x1400039e9  push    rbp
0x1400039ea  push    rsi
0x1400039eb  push    rdi
0x1400039ec  lea     rbp, [rsp-47h]
0x1400039f1  sub     rsp, 100h
0x1400039f8  mov     edi, edx
0x1400039fa  mov     rsi, rcx
0x1400039fd  lea     rdx, aSrpropstarttra; "SrPropStartTracing"
0x140003a04  mov     r9d, 1; unsigned __int16
0x140003a0a  lea     rcx, [rbp+57h+var_B0]; this
0x140003a0e  mov     r8d, 43Eh; unsigned __int16
0x140003a14  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140003a19  mov     [rbp+57h+hKey], 0
0x140003a21  lea     rax, qword_140013960
0x140003a28  mov     [rbp+57h+var_58], rax
0x140003a2c  mov     ebx, 1E0000EDh
0x140003a31  mov     [rbp+57h+var_50], 0
0x140003a39  mov     eax, 448h
0x140003a3e  mov     [rbp+57h+TraceHandle], 0FFFFFFFFFFFFFFFFh
0x140003a46  mov     [rbp+57h+arg_0], ebx
0x140003a49  mov     [rbp+57h+pv], 0
0x140003a51  test    rsi, rsi
0x140003a54  jz      loc_140003D61
0x140003a5a  mov     [rbp+57h+var_AC], ax
0x140003a5e  lea     rdx, s_cszSRRegKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x140003a65  lea     rax, [rbp+57h+hKey]
0x140003a69  mov     qword ptr [rsi], 0
0x140003a70  mov     r9d, 20019h; samDesired
0x140003a76  mov     [rsp+110h+phkResult], rax; unsigned __int16 *
0x140003a7b  xor     r8d, r8d; ulOptions
0x140003a7e  mov     [rbp+57h+var_B0], 0
0x140003a85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140003a8c  call    cs:__imp_RegOpenKeyExW
0x140003a92  test    eax, eax
0x140003a94  jle     short loc_140003A9E
0x140003a96  movzx   eax, ax
0x140003a99  or      eax, 80070000h
0x140003a9e  mov     [rbp+57h+var_B0], eax
0x140003aa1  test    eax, eax
0x140003aa3  mov     eax, 44Ah
0x140003aa8  js      loc_140003D68
0x140003aae  mov     [rbp+57h+var_AC], ax
0x140003ab2  call    ?SxCheckWBDiagSession@@YAJXZ; SxCheckWBDiagSession(void)
0x140003ab7  mov     ecx, eax
0x140003ab9  mov     [rbp+57h+var_B0], eax
0x140003abc  test    eax, eax
0x140003abe  mov     eax, 44Fh
0x140003ac3  js      loc_140003D68
0x140003ac9  mov     [rbp+57h+var_AC], ax
0x140003acd  cmp     ecx, 1
0x140003ad0  jnz     short loc_140003AE3
0x140003ad2  mov     [rbp+57h+var_B0], ecx
0x140003ad5  mov     eax, 452h
0x140003ada  mov     [rbp+57h+var_AC], ax
0x140003ade  jmp     loc_140003D6C
0x140003ae3  mov     rcx, [rbp+57h+hKey]; hKey
0x140003ae7  lea     r8, [rbp+57h+arg_0]; unsigned int *
0x140003aeb  xor     r9d, r9d; int
0x140003aee  lea     rdx, s_cszSRTracingFlags; "SystemRestoreTracingFlags"
0x140003af5  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x140003afa  test    eax, eax
0x140003afc  jnz     short loc_140003B0F
0x140003afe  mov     ebx, [rbp+57h+arg_0]
0x140003b01  test    ebx, ebx
0x140003b03  jnz     short loc_140003B21
0x140003b05  mov     [rbp+57h+var_B0], ebx
0x140003b08  mov     eax, 45Fh
0x140003b0d  jmp     short loc_140003ADA
0x140003b0f  test    edi, edi
0x140003b11  jz      short loc_140003B21
0x140003b13  mov     [rbp+57h+var_B0], 0
0x140003b1a  mov     eax, 465h
0x140003b1f  jmp     short loc_140003ADA
0x140003b21  mov     r9d, 1; unsigned __int16
0x140003b27  lea     rdx, aSrpropstoptrac; "SrPropStopTracing"
0x140003b2e  mov     r8d, 4B2h; unsigned __int16
0x140003b34  lea     rcx, [rbp+57h+var_48]; this
0x140003b38  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140003b3d  call    ?SxStopTracing@@YAJPEBG@Z; SxStopTracing(ushort const *)
0x140003b42  mov     [rbp+57h+var_48], eax
0x140003b45  test    eax, eax
0x140003b47  mov     eax, 4B4h
0x140003b4c  jns     short loc_140003B54
0x140003b4e  mov     [rbp+57h+var_42], ax
0x140003b52  jmp     short loc_140003B58
0x140003b54  mov     [rbp+57h+var_44], ax
0x140003b58  lea     rcx, [rbp+57h+var_48]; this
0x140003b5c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140003b61  lea     rcx, [rbp+57h+var_58]; struct CBsString *
0x140003b65  call    ?GetAndEnsureTracingDirectory@@YAJPEAVCBsString@@@Z; Creates fixed %SystemRoot%\Logs\SystemRestore with BA/SY-only SDDL; StandardUser cannot create/replace parent/path in default ACL state.
0x140003b6a  mov     [rbp+57h+var_B0], eax
0x140003b6d  test    eax, eax
0x140003b6f  mov     eax, 46Eh
0x140003b74  js      loc_140003D68
0x140003b7a  cmp     dword ptr [rbp+57h+var_50], 0
0x140003b7e  mov     [rbp+57h+var_AC], ax
0x140003b82  jnz     short loc_140003B8D
0x140003b84  mov     [rbp+57h+var_B0], 800710DDh
0x140003b8b  jmp     short loc_140003BA7
0x140003b8d  xor     r8d, r8d; unsigned __int16 *
0x140003b90  lea     rdx, aSrtasks; "SrTasks"
0x140003b97  lea     rcx, [rbp+57h+var_58]; this
0x140003b9b  call    ?_CombinePathImpl@CBsString@@AEAAJPEBG000000000@Z; CBsString::_CombinePathImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x140003ba0  mov     [rbp+57h+var_B0], eax
0x140003ba3  test    eax, eax
0x140003ba5  jns     short loc_140003BB1
0x140003ba7  mov     eax, 470h
0x140003bac  jmp     loc_140003D68
0x140003bb1  mov     rcx, [rbp+57h+var_58]; unsigned __int16 *
0x140003bb5  mov     eax, 470h
0x140003bba  mov     [rbp+57h+var_AC], ax
0x140003bbe  call    ?SxRotateLogs@@YAJPEBGK@Z; Trace log rotation is fixed to protected SystemRestore trace dir; no low-priv writable path source found.
0x140003bc3  mov     [rbp+57h+var_B0], eax
0x140003bc6  test    eax, eax
0x140003bc8  mov     eax, 472h
0x140003bcd  js      loc_140003D68
0x140003bd3  mov     rdx, [rbp+57h+var_58]; unsigned __int16 *
0x140003bd7  lea     r9, [rbp+57h+TraceHandle]; unsigned __int64 *
0x140003bdb  mov     [rbp+57h+var_AC], ax
0x140003bdf  lea     rax, [rbp+57h+pv]
0x140003be3  mov     [rsp+110h+phkResult], rax; unsigned __int16 **
0x140003be8  call    ?SxStartTracing@@YAJPEBG0KPEA_KPEAPEAG@Z; SxStartTracing(ushort const *,ushort const *,ulong,unsigned __int64 *,ushort * *)
0x140003bed  mov     [rbp+57h+var_B0], eax
0x140003bf0  test    eax, eax
0x140003bf2  mov     eax, 478h
0x140003bf7  js      loc_140003D68
0x140003bfd  movups  xmm0, xmmword ptr cs:?c_guidGuiTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidGuiTracingControlGuid ...
0x140003c04  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x140003c08  lea     rdx, [rbp+57h+ProviderId]; struct _GUID
0x140003c0c  mov     r8d, ebx; unsigned int
0x140003c0f  mov     [rbp+57h+var_AC], ax
0x140003c13  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x140003c18  call    ?SxEnableTraceDefault@@YAJ_KU_GUID@@K@Z; SxEnableTraceDefault(unsigned __int64,_GUID,ulong)
0x140003c1d  mov     [rbp+57h+var_B0], eax
0x140003c20  test    eax, eax
0x140003c22  mov     eax, 47Ah
0x140003c27  js      loc_140003D68
0x140003c2d  movups  xmm0, xmmword ptr cs:?c_guidSppTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidSppTracingControlGuid ...
0x140003c34  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x140003c38  lea     rdx, [rbp+57h+ProviderId]; struct _GUID
0x140003c3c  mov     r8d, ebx; unsigned int
0x140003c3f  mov     [rbp+57h+var_AC], ax
0x140003c43  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x140003c48  call    ?SxEnableTraceDefault@@YAJ_KU_GUID@@K@Z; SxEnableTraceDefault(unsigned __int64,_GUID,ulong)
0x140003c4d  mov     [rbp+57h+var_B0], eax
0x140003c50  test    eax, eax
0x140003c52  mov     eax, 47Bh
0x140003c57  js      loc_140003D68
0x140003c5d  movups  xmm0, xmmword ptr cs:?c_guidSrClientTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidSrClientTracingControlGuid ...
0x140003c64  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x140003c68  lea     rdx, [rbp+57h+ProviderId]; struct _GUID
0x140003c6c  mov     r8d, ebx; unsigned int
0x140003c6f  mov     [rbp+57h+var_AC], ax
0x140003c73  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x140003c78  call    ?SxEnableTraceDefault@@YAJ_KU_GUID@@K@Z; SxEnableTraceDefault(unsigned __int64,_GUID,ulong)
0x140003c7d  mov     [rbp+57h+var_B0], eax
0x140003c80  test    eax, eax
0x140003c82  mov     eax, 47Ch
0x140003c87  js      loc_140003D68
0x140003c8d  movups  xmm0, xmmword ptr cs:?c_guidSrClientTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidSrClientTracingControlGuid ...
0x140003c94  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x140003c98  lea     rdx, [rbp+57h+ProviderId]; struct _GUID
0x140003c9c  mov     r8d, ebx; unsigned int
0x140003c9f  mov     [rbp+57h+var_AC], ax
0x140003ca3  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x140003ca8  call    ?SxEnableTraceDefault@@YAJ_KU_GUID@@K@Z; SxEnableTraceDefault(unsigned __int64,_GUID,ulong)
0x140003cad  mov     [rbp+57h+var_B0], eax
0x140003cb0  test    eax, eax
0x140003cb2  mov     eax, 47Dh
0x140003cb7  js      loc_140003D68
0x140003cbd  movups  xmm0, xmmword ptr cs:?c_guidSrPropTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidSrPropTracingControlGuid ...
0x140003cc4  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x140003cc8  lea     rdx, [rbp+57h+ProviderId]; struct _GUID
0x140003ccc  mov     r8d, ebx; unsigned int
0x140003ccf  mov     [rbp+57h+var_AC], ax
0x140003cd3  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x140003cd8  call    ?SxEnableTraceDefault@@YAJ_KU_GUID@@K@Z; SxEnableTraceDefault(unsigned __int64,_GUID,ulong)
0x140003cdd  mov     [rbp+57h+var_B0], eax
0x140003ce0  test    eax, eax
0x140003ce2  mov     eax, 47Eh
0x140003ce7  js      short loc_140003D68
0x140003ce9  movups  xmm0, xmmword ptr cs:?c_guidAsrTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidAsrTracingControlGuid ...
0x140003cf0  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x140003cf4  lea     rdx, [rbp+57h+ProviderId]; ProviderId
0x140003cf8  mov     ebx, 0FFh
0x140003cfd  mov     [rbp+57h+var_AC], ax
0x140003d01  mov     r9d, ebx; unsigned int
0x140003d04  mov     r8d, ebx; MatchAnyKeyword
0x140003d07  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x140003d0c  call    ?SxEnableTraceCustom@@YAJ_KU_GUID@@KK@Z; SxEnableTraceCustom(unsigned __int64,_GUID,ulong,ulong)
0x140003d11  mov     [rbp+57h+var_B0], eax
0x140003d14  test    eax, eax
0x140003d16  mov     eax, 483h
0x140003d1b  js      short loc_140003D68
0x140003d1d  movups  xmm0, xmmword ptr cs:?c_guidUdfdTracingControlGuid@@3U_GUID@@B.Data1; _GUID const c_guidUdfdTracingControlGuid ...
0x140003d24  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x140003d28  lea     rdx, [rbp+57h+ProviderId]; ProviderId
0x140003d2c  mov     r9d, ebx; unsigned int
0x140003d2f  mov     [rbp+57h+var_AC], ax
0x140003d33  mov     r8d, ebx; MatchAnyKeyword
0x140003d36  movdqu  xmmword ptr [rbp+57h+ProviderId.Data1], xmm0
0x140003d3b  call    ?SxEnableTraceCustom@@YAJ_KU_GUID@@KK@Z; SxEnableTraceCustom(unsigned __int64,_GUID,ulong,ulong)
0x140003d40  mov     [rbp+57h+var_B0], eax
0x140003d43  test    eax, eax
0x140003d45  mov     eax, 488h
0x140003d4a  js      short loc_140003D68
0x140003d4c  mov     [rbp+57h+var_AC], ax
0x140003d50  mov     rax, [rbp+57h+pv]
0x140003d54  mov     [rsi], rax
0x140003d57  mov     [rbp+57h+pv], 0
0x140003d5f  jmp     short loc_140003D6C
0x140003d61  mov     [rbp+57h+var_B0], 80070057h
0x140003d68  mov     [rbp+57h+var_AA], ax
0x140003d6c  mov     rcx, [rbp+57h+pv]; pv
0x140003d70  call    cs:__imp_CoTaskMemFree
0x140003d76  mov     ebx, [rbp+57h+var_B0]
0x140003d79  lea     rcx, [rbp+57h+var_58]; this
0x140003d7d  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x140003d82  mov     rcx, [rbp+57h+hKey]; hKey
0x140003d86  lea     rdx, [rcx-1]
0x140003d8a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140003d8e  ja      short loc_140003D9E
0x140003d90  call    cs:__imp_RegCloseKey
0x140003d96  mov     [rbp+57h+hKey], 0
0x140003d9e  lea     rcx, [rbp+57h+var_B0]; this
0x140003da2  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140003da7  mov     eax, ebx
0x140003da9  mov     rbx, [rsp+110h+arg_8]
0x140003db1  add     rsp, 100h
0x140003db8  pop     rdi
0x140003db9  pop     rsi
0x140003dba  pop     rbp
0x140003dbb  retn
```
