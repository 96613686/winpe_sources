# ExecuteScheduledSPPCreation(void)

- ea: `0x140002f30`
- end: `0x140003123`
- name: `?ExecuteScheduledSPPCreation@@YAJXZ`
- size: `499`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005718`

## callees

- `0x140002e1c`
- `0x140002e44`
- `0x140002f30`
- `0x14000372c`
- `0x140003950`
- `0x1400039e4`
- `0x140003dc4`
- `0x140004a70`
- `0x140007030`
- `0x14000e324`
- `0x14000e41c`

## import_xrefs

- `KERNEL32!HeapSetInformation` at `0x140002fa8`
- `KERNEL32!HeapSetInformation` at `0x140002fa8`
- `ole32!CoUninitialize` at `0x1400030d9`
- `ole32!CoUninitialize` at `0x1400030d9`
- `ole32!CoInitializeEx` at `0x140002fb2`
- `ole32!CoInitializeEx` at `0x140002fb2`
- `ole32!CoTaskMemFree` at `0x1400030f6`
- `ole32!CoTaskMemFree` at `0x1400030f6`

## string_xrefs

- `0x140002f76`: `ExecuteScheduledSPPCreation`

## pseudocode

```c
__int64 ExecuteScheduledSPPCreation(void)
{
  int v0; // edi
  HRESULT v1; // eax
  __int64 v2; // rdx
  __int64 v3; // r8
  int v4; // ebx
  __int16 v5; // ax
  int v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // ebx
  int v12; // [rsp+20h] [rbp-40h] BYREF
  __int16 v13; // [rsp+24h] [rbp-3Ch]
  __int16 v14; // [rsp+26h] [rbp-3Ah]
  int v15; // [rsp+80h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+28h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
  v0 = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "ExecuteScheduledSPPCreation", 590, 1);
  v15 = 0;
  pv = 0;
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  v1 = CoInitializeEx(0, 0);
  v4 = v1;
  if ( v1 < 0 )
  {
    v0 = 0;
    if ( v1 != -2147417850 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
          (unsigned int)v1);
      }
      v12 = v4;
      v14 = 608;
      goto LABEL_27;
    }
  }
  v12 = SxInitializeCOMSecurityForSPP();
  v5 = 615;
  if ( v12 < 0 )
    goto LABEL_11;
  v13 = 615;
  v6 = IsSafeDocsTaskRunning(&v15);
  v4 = v6;
  if ( v6 >= 0 )
  {
    v7 = WPP_GLOBAL_Control;
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
        (unsigned int)v6);
      v7 = WPP_GLOBAL_Control;
    }
    v4 = 0;
  }
  if ( v15 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x4000000) != 0 )
      WPP_SF_(v7[2], 42, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
    v12 = 0;
    v5 = 628;
  }
  else
  {
    SrPropStartTracing(&pv, 0);
    LimitProcessResourceUsage(v9, v8, 3);
    v12 = _ExecuteScheduledSPPCreation();
    v5 = 643;
    if ( v12 < 0 )
    {
LABEL_11:
      v14 = v5;
      goto LABEL_25;
    }
  }
  v13 = v5;
LABEL_25:
  if ( v0 )
    CoUninitialize();
LABEL_27:
  if ( pv )
  {
    SrPropStopTracing((LPCWSTR)pv, v4 < 0);
    CoTaskMemFree(pv);
    pv = 0;
  }
  v10 = v12;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12, v2, v3);
  return v10;
}

```

## disassembly

```asm
0x140002f30  mov     [rsp-18h+arg_10], rbx
0x140002f35  push    rbp
0x140002f36  push    rdi
0x140002f37  push    r14
0x140002f39  mov     rbp, rsp
0x140002f3c  sub     rsp, 60h
0x140002f40  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f47  lea     r14, WPP_GLOBAL_Control
0x140002f4e  cmp     rcx, r14
0x140002f51  jz      short loc_140002F71
0x140002f53  test    dword ptr [rcx+1Ch], 20000000h
0x140002f5a  jz      short loc_140002F71
0x140002f5c  mov     rcx, [rcx+10h]
0x140002f60  lea     r8, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x140002f67  mov     edx, 27h ; '''
0x140002f6c  call    WPP_SF_
0x140002f71  mov     edi, 1
0x140002f76  lea     rdx, aExecuteschedul; "ExecuteScheduledSPPCreation"
0x140002f7d  mov     r9d, edi; unsigned __int16
0x140002f80  lea     rcx, [rbp+var_40]; this
0x140002f84  mov     r8d, 24Eh; unsigned __int16
0x140002f8a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140002f8f  xor     r9d, r9d; HeapInformationLength
0x140002f92  mov     [rbp+arg_0], 0
0x140002f99  xor     r8d, r8d; HeapInformation
0x140002f9c  mov     [rbp+pv], 0
0x140002fa4  mov     edx, edi; HeapInformationClass
0x140002fa6  xor     ecx, ecx; HeapHandle
0x140002fa8  call    cs:__imp_HeapSetInformation
0x140002fae  xor     edx, edx; dwCoInit
0x140002fb0  xor     ecx, ecx; pvReserved
0x140002fb2  call    cs:__imp_CoInitializeEx
0x140002fb8  mov     ebx, eax
0x140002fba  test    eax, eax
0x140002fbc  jns     short loc_140003003
0x140002fbe  xor     edi, edi
0x140002fc0  cmp     eax, 80010106h
0x140002fc5  jz      short loc_140003003
0x140002fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140002fce  cmp     rcx, r14
0x140002fd1  jz      short loc_140002FF2
0x140002fd3  test    dword ptr [rcx+1Ch], 2000000h
0x140002fda  jz      short loc_140002FF2
0x140002fdc  mov     rcx, [rcx+10h]
0x140002fe0  lea     edx, [rdi+28h]
0x140002fe3  mov     r9d, eax
0x140002fe6  lea     r8, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x140002fed  call    WPP_SF_d
0x140002ff2  mov     eax, 260h
0x140002ff7  mov     [rbp+var_40], ebx
0x140002ffa  mov     [rbp+var_3A], ax
0x140002ffe  jmp     loc_1400030DF
0x140003003  call    ?SxInitializeCOMSecurityForSPP@@YAJXZ; SxInitializeCOMSecurityForSPP(void)
0x140003008  mov     [rbp+var_40], eax
0x14000300b  test    eax, eax
0x14000300d  mov     eax, 267h
0x140003012  jns     short loc_14000301D
0x140003014  mov     [rbp+var_3A], ax
0x140003018  jmp     loc_1400030D5
0x14000301d  lea     rcx, [rbp+arg_0]
0x140003021  mov     [rbp+var_3C], ax
0x140003025  call    IsSafeDocsTaskRunning
0x14000302a  mov     ebx, eax
0x14000302c  test    eax, eax
0x14000302e  jns     short loc_140003068
0x140003030  mov     rcx, cs:WPP_GLOBAL_Control
0x140003037  cmp     rcx, r14
0x14000303a  jz      short loc_140003064
0x14000303c  test    dword ptr [rcx+1Ch], 2000000h
0x140003043  jz      short loc_140003064
0x140003045  mov     rcx, [rcx+10h]
0x140003049  lea     r8, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x140003050  mov     edx, 29h ; ')'
0x140003055  mov     r9d, eax
0x140003058  call    WPP_SF_d
0x14000305d  mov     rcx, cs:WPP_GLOBAL_Control
0x140003064  xor     ebx, ebx
0x140003066  jmp     short loc_14000306F
0x140003068  mov     rcx, cs:WPP_GLOBAL_Control
0x14000306f  cmp     [rbp+arg_0], 0
0x140003073  jz      short loc_1400030A6
0x140003075  cmp     rcx, r14
0x140003078  jz      short loc_140003098
0x14000307a  test    dword ptr [rcx+1Ch], 4000000h
0x140003081  jz      short loc_140003098
0x140003083  mov     rcx, [rcx+10h]
0x140003087  lea     r8, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x14000308e  mov     edx, 2Ah ; '*'
0x140003093  call    WPP_SF_
0x140003098  mov     [rbp+var_40], 0
0x14000309f  mov     eax, 274h
0x1400030a4  jmp     short loc_1400030D1
0x1400030a6  xor     edx, edx; int
0x1400030a8  lea     rcx, [rbp+pv]; unsigned __int16 **
0x1400030ac  call    ?SrPropStartTracing@@YAJPEAPEAGH@Z; SrPropStartTracing(ushort * *,int)
0x1400030b1  mov     r8d, 3
0x1400030b7  call    LimitProcessResourceUsage
0x1400030bc  call    ?_ExecuteScheduledSPPCreation@@YAJXZ; Weak service/task/agent config-permissions audit 2026-06-06: SYSTEM SR task core; inputs are fixed HKLM SystemRestore values and protected trace dir, no low-priv-controlled execution path.
0x1400030c1  mov     [rbp+var_40], eax
0x1400030c4  test    eax, eax
0x1400030c6  mov     eax, 283h
0x1400030cb  js      loc_140003014
0x1400030d1  mov     [rbp+var_3C], ax
0x1400030d5  test    edi, edi
0x1400030d7  jz      short loc_1400030DF
0x1400030d9  call    cs:__imp_CoUninitialize
0x1400030df  mov     rcx, [rbp+pv]; lpFileName
0x1400030e3  test    rcx, rcx
0x1400030e6  jz      short loc_140003104
0x1400030e8  shr     ebx, 1Fh
0x1400030eb  mov     dl, bl; unsigned __int8
0x1400030ed  call    ?SrPropStopTracing@@YAJPEBGE@Z; SrPropStopTracing(ushort const *,uchar)
0x1400030f2  mov     rcx, [rbp+pv]; pv
0x1400030f6  call    cs:__imp_CoTaskMemFree
0x1400030fc  mov     [rbp+pv], 0
0x140003104  mov     ebx, [rbp+var_40]
0x140003107  lea     rcx, [rbp+var_40]; this
0x14000310b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140003110  mov     eax, ebx
0x140003112  mov     rbx, [rsp+60h+arg_10]
0x14000311a  add     rsp, 60h
0x14000311e  pop     r14
0x140003120  pop     rdi
0x140003121  pop     rbp
0x140003122  retn
```
