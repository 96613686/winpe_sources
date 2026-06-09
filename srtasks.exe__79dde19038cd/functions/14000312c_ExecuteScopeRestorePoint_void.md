# ExecuteScopeRestorePoint(void)

- ea: `0x14000312c`
- end: `0x140003318`
- name: `?ExecuteScopeRestorePoint@@YAJXZ`
- size: `492`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005718`

## callees

- `0x140002e1c`
- `0x140002e44`
- `0x14000312c`
- `0x140003584`
- `0x140003950`
- `0x1400039e4`
- `0x140003dc4`
- `0x140003e70`
- `0x1400050f0`
- `0x140007030`
- `0x14000e324`
- `0x14000e41c`

## import_xrefs

- `KERNEL32!HeapSetInformation` at `0x1400031a1`
- `KERNEL32!HeapSetInformation` at `0x1400031a1`
- `ole32!CoUninitialize` at `0x1400032cc`
- `ole32!CoUninitialize` at `0x1400032cc`
- `ole32!CoInitializeEx` at `0x1400031ab`
- `ole32!CoInitializeEx` at `0x1400031ab`
- `ole32!CoTaskMemFree` at `0x1400032eb`
- `ole32!CoTaskMemFree` at `0x1400032eb`

## pseudocode

```c
__int64 ExecuteScopeRestorePoint(void)
{
  HRESULT v0; // eax
  __int64 v1; // rdx
  __int64 v2; // r8
  HRESULT v3; // ebx
  int v4; // edi
  __int16 v5; // ax
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int RestorePointIndexToWaitFor; // eax
  int v9; // eax
  _QWORD *v10; // rcx
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-40h] BYREF
  __int16 v14; // [rsp+24h] [rbp-3Ch]
  __int16 v15; // [rsp+26h] [rbp-3Ah]
  unsigned __int8 v16; // [rsp+80h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+28h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "ExecuteScopeRestorePoint", 939, 1);
  pv = 0;
  v16 = 1;
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  v0 = CoInitializeEx(0, 0);
  v3 = v0;
  if ( v0 >= 0 )
  {
    v4 = 1;
  }
  else
  {
    v4 = 0;
    if ( v0 != -2147417850 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
          (unsigned int)v0);
      }
      v13 = v3;
      v15 = 959;
      goto LABEL_27;
    }
  }
  v13 = SxInitializeCOMSecurityForSPP();
  v5 = 966;
  if ( v13 < 0 )
    goto LABEL_12;
  v14 = 966;
  SrPropStartTracing(&pv, 1);
  LimitProcessResourceUsage(v7, v6, 4);
  RestorePointIndexToWaitFor = GetRestorePointIndexToWaitFor();
  if ( !RestorePointIndexToWaitFor )
    goto LABEL_23;
  v9 = WaitForRestorePointToAppear(RestorePointIndexToWaitFor, &v16);
  if ( v9 >= 0 )
    goto LABEL_18;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      58,
      &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids,
      (unsigned int)v9);
LABEL_18:
    v10 = WPP_GLOBAL_Control;
  }
  if ( !v16 )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x8000000) != 0 )
      WPP_SF_(v10[2], 59, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
    goto LABEL_25;
  }
LABEL_23:
  v13 = _ExecuteScopeRestorePoint();
  v5 = 987;
  if ( v13 < 0 )
  {
LABEL_12:
    v15 = v5;
    goto LABEL_25;
  }
  v14 = 987;
LABEL_25:
  if ( v4 )
    CoUninitialize();
LABEL_27:
  LOBYTE(v1) = v13 < 0;
  if ( pv )
  {
    SrPropStopTracing((LPCWSTR)pv, v1);
    CoTaskMemFree(pv);
    pv = 0;
  }
  v11 = v13;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13, v1, v2);
  return v11;
}

```

## disassembly

```asm
0x14000312c  mov     [rsp-18h+arg_10], rbx
0x140003131  push    rbp
0x140003132  push    rdi
0x140003133  push    r14
0x140003135  mov     rbp, rsp
0x140003138  sub     rsp, 60h
0x14000313c  mov     rcx, cs:WPP_GLOBAL_Control
0x140003143  lea     r14, WPP_GLOBAL_Control
0x14000314a  cmp     rcx, r14
0x14000314d  jz      short loc_14000316D
0x14000314f  test    dword ptr [rcx+1Ch], 20000000h
0x140003156  jz      short loc_14000316D
0x140003158  mov     rcx, [rcx+10h]
0x14000315c  lea     r8, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x140003163  mov     edx, 38h ; '8'
0x140003168  call    WPP_SF_
0x14000316d  mov     r9d, 1; unsigned __int16
0x140003173  lea     rdx, aExecutescopere_0; "ExecuteScopeRestorePoint"
0x14000317a  mov     r8d, 3ABh; unsigned __int16
0x140003180  lea     rcx, [rbp+var_40]; this
0x140003184  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140003189  xor     r9d, r9d; HeapInformationLength
0x14000318c  mov     [rbp+pv], 0
0x140003194  xor     r8d, r8d; HeapInformation
0x140003197  mov     [rbp+arg_0], 1
0x14000319b  xor     ecx, ecx; HeapHandle
0x14000319d  lea     edx, [r9+1]; HeapInformationClass
0x1400031a1  call    cs:__imp_HeapSetInformation
0x1400031a7  xor     edx, edx; dwCoInit
0x1400031a9  xor     ecx, ecx; pvReserved
0x1400031ab  call    cs:__imp_CoInitializeEx
0x1400031b1  mov     ebx, eax
0x1400031b3  test    eax, eax
0x1400031b5  jns     short loc_1400031FC
0x1400031b7  xor     edi, edi
0x1400031b9  cmp     eax, 80010106h
0x1400031be  jz      short loc_140003201
0x1400031c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400031c7  cmp     rcx, r14
0x1400031ca  jz      short loc_1400031EB
0x1400031cc  test    dword ptr [rcx+1Ch], 2000000h
0x1400031d3  jz      short loc_1400031EB
0x1400031d5  mov     rcx, [rcx+10h]
0x1400031d9  lea     edx, [rdi+39h]
0x1400031dc  mov     r9d, eax
0x1400031df  lea     r8, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x1400031e6  call    WPP_SF_d
0x1400031eb  mov     eax, 3BFh
0x1400031f0  mov     [rbp+var_40], ebx
0x1400031f3  mov     [rbp+var_3A], ax
0x1400031f7  jmp     loc_1400032D2
0x1400031fc  mov     edi, 1
0x140003201  call    ?SxInitializeCOMSecurityForSPP@@YAJXZ; SxInitializeCOMSecurityForSPP(void)
0x140003206  mov     [rbp+var_40], eax
0x140003209  test    eax, eax
0x14000320b  mov     eax, 3C6h
0x140003210  jns     short loc_14000321B
0x140003212  mov     [rbp+var_3A], ax
0x140003216  jmp     loc_1400032C8
0x14000321b  mov     edx, 1; int
0x140003220  mov     [rbp+var_3C], ax
0x140003224  lea     rcx, [rbp+pv]; unsigned __int16 **
0x140003228  call    ?SrPropStartTracing@@YAJPEAPEAGH@Z; SrPropStartTracing(ushort * *,int)
0x14000322d  mov     r8d, 4
0x140003233  call    LimitProcessResourceUsage
0x140003238  call    ?GetRestorePointIndexToWaitFor@@YAKXZ; GetRestorePointIndexToWaitFor(void)
0x14000323d  test    eax, eax
0x14000323f  jz      short loc_1400032AF
0x140003241  lea     rdx, [rbp+arg_0]; unsigned __int8 *
0x140003245  mov     ecx, eax; unsigned int
0x140003247  call    ?WaitForRestorePointToAppear@@YAJKPEAE@Z; WaitForRestorePointToAppear(ulong,uchar *)
0x14000324c  test    eax, eax
0x14000324e  jns     short loc_14000327D
0x140003250  mov     rcx, cs:WPP_GLOBAL_Control
0x140003257  cmp     rcx, r14
0x14000325a  jz      short loc_140003284
0x14000325c  test    dword ptr [rcx+1Ch], 4000000h
0x140003263  jz      short loc_140003284
0x140003265  mov     rcx, [rcx+10h]
0x140003269  lea     r8, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x140003270  mov     edx, 3Ah ; ':'
0x140003275  mov     r9d, eax
0x140003278  call    WPP_SF_d
0x14000327d  mov     rcx, cs:WPP_GLOBAL_Control
0x140003284  cmp     [rbp+arg_0], 0
0x140003288  jnz     short loc_1400032AF
0x14000328a  cmp     rcx, r14
0x14000328d  jz      short loc_1400032C8
0x14000328f  test    dword ptr [rcx+1Ch], 8000000h
0x140003296  jz      short loc_1400032C8
0x140003298  mov     rcx, [rcx+10h]
0x14000329c  lea     r8, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x1400032a3  mov     edx, 3Bh ; ';'
0x1400032a8  call    WPP_SF_
0x1400032ad  jmp     short loc_1400032C8
0x1400032af  call    ?_ExecuteScopeRestorePoint@@YAJXZ; _ExecuteScopeRestorePoint(void)
0x1400032b4  mov     [rbp+var_40], eax
0x1400032b7  test    eax, eax
0x1400032b9  mov     eax, 3DBh
0x1400032be  js      loc_140003212
0x1400032c4  mov     [rbp+var_3C], ax
0x1400032c8  test    edi, edi
0x1400032ca  jz      short loc_1400032D2
0x1400032cc  call    cs:__imp_CoUninitialize
0x1400032d2  cmp     [rbp+var_40], 0
0x1400032d6  mov     rcx, [rbp+pv]; lpFileName
0x1400032da  setl    dl; unsigned __int8
0x1400032dd  test    rcx, rcx
0x1400032e0  jz      short loc_1400032F9
0x1400032e2  call    ?SrPropStopTracing@@YAJPEBGE@Z; SrPropStopTracing(ushort const *,uchar)
0x1400032e7  mov     rcx, [rbp+pv]; pv
0x1400032eb  call    cs:__imp_CoTaskMemFree
0x1400032f1  mov     [rbp+pv], 0
0x1400032f9  mov     ebx, [rbp+var_40]
0x1400032fc  lea     rcx, [rbp+var_40]; this
0x140003300  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140003305  mov     eax, ebx
0x140003307  mov     rbx, [rsp+60h+arg_10]
0x14000330f  add     rsp, 60h
0x140003313  pop     r14
0x140003315  pop     rdi
0x140003316  pop     rbp
0x140003317  retn
```
