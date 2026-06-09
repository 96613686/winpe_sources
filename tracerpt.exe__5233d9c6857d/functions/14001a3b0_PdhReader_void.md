# PdhReader(void *)

- ea: `0x14001a3b0`
- end: `0x14001a63e`
- name: `?PdhReader@@YAKPEAX@Z`
- size: `654`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14001a3b0`
- `0x14001a644`
- `0x14001a760`
- `0x14001ab78`
- `0x140040130`

## import_xrefs

- `pdh!PdhBindInputDataSourceW` at `0x14001a42e`
- `pdh!PdhBindInputDataSourceW` at `0x14001a42e`
- `pdh!PdhComputeCounterStatistics` at `0x14001a5e1`
- `pdh!PdhComputeCounterStatistics` at `0x14001a5e1`
- `pdh!PdhOpenQueryH` at `0x14001a44b`
- `pdh!PdhOpenQueryH` at `0x14001a44b`
- `pdh!PdhGetDataSourceTimeRangeH` at `0x14001a470`
- `pdh!PdhGetDataSourceTimeRangeH` at `0x14001a470`
- `pdh!PdhSetQueryTimeRange` at `0x14001a54b`
- `pdh!PdhSetQueryTimeRange` at `0x14001a54b`
- `pdh!PdhCloseLog` at `0x14001a605`
- `pdh!PdhCloseLog` at `0x14001a605`
- `pdh!PdhCloseQuery` at `0x14001a615`
- `pdh!PdhCloseQuery` at `0x14001a615`

## pseudocode

```c
__int64 __fastcall PdhReader(PVOID Parameter)
{
  char v1; // di
  struct _PDH_STATISTICS *v2; // rbx
  PDH_STATUS v3; // eax
  PDH_STATUS v4; // eax
  PDH_STATUS DataSourceTimeRangeH; // eax
  LONGLONG v6; // rax
  LONGLONG v7; // rcx
  LONGLONG StartTime; // rdx
  PDH_STATUS v10; // eax
  LONGLONG EndTime; // rax
  DWORD Log; // eax
  DWORD Data; // eax
  struct _PDH_STATISTICS *i; // rcx
  struct _PDH_STATISTICS *v15; // rdi
  PDH_STATUS v16; // eax
  PDH_HLOG hDataSource; // [rsp+30h] [rbp-58h] BYREF
  PDH_HQUERY phQuery; // [rsp+38h] [rbp-50h] BYREF
  DWORD pdwBufferSize; // [rsp+40h] [rbp-48h] BYREF
  DWORD pdwNumEntries; // [rsp+44h] [rbp-44h] BYREF
  struct _PDH_TIME_INFO v21; // [rsp+48h] [rbp-40h] BYREF
  _PDH_TIME_INFO pInfo; // [rsp+60h] [rbp-28h] BYREF

  hDataSource = 0;
  phQuery = 0;
  memset(&pInfo, 0, sizeof(pInfo));
  memset(&v21, 0, sizeof(v21));
  v1 = 1;
  pdwNumEntries = 1;
  pdwBufferSize = 24;
  v2 = (struct _PDH_STATISTICS *)*((_QWORD *)g_TraceContext + 1086);
  *(&v2->max.CStatus + 1) = 0;
  if ( v2->max.longValue )
  {
    v3 = PdhBindInputDataSourceW(&hDataSource, *(LPCWSTR *)&v2[1].dwFormat);
    *(&v2->max.CStatus + 1) = v3;
    if ( !v3 )
    {
      v4 = PdhOpenQueryH(hDataSource, 0, &phQuery);
      *(&v2->max.CStatus + 1) = v4;
      if ( !v4 )
      {
        DataSourceTimeRangeH = PdhGetDataSourceTimeRangeH(hDataSource, &pdwNumEntries, &pInfo, &pdwBufferSize);
        *(&v2->max.CStatus + 1) = DataSourceTimeRangeH;
        if ( !DataSourceTimeRangeH )
        {
          v2->max.CStatus = pInfo.SampleCount;
          if ( !*((_BYTE *)g_TraceContext + 8505) )
          {
            qword_1400820A0 = pInfo.StartTime;
            EndTime = pInfo.EndTime;
            goto LABEL_19;
          }
          v21.StartTime = TraceToPDHTime(qword_1400820B8);
          v6 = TraceToPDHTime(qword_1400820C0);
          v7 = v6;
          v21.EndTime = v6;
          v21.SampleCount = 0;
          StartTime = pInfo.StartTime;
          if ( pInfo.StartTime < v21.StartTime )
            StartTime = v21.StartTime;
          if ( pInfo.EndTime < v6 )
            v7 = pInfo.EndTime;
          if ( StartTime >= v7
            || (double)(LODWORD(pInfo.EndTime) - LODWORD(pInfo.StartTime)) * 0.02 > (double)((int)v7 - (int)StartTime) )
          {
            v1 = 0;
          }
          else
          {
            v21.StartTime = StartTime;
            v21.EndTime = v7;
            v21.SampleCount = 0;
          }
          if ( !v1 )
          {
            *(&v2->max.CStatus + 1) = -1073738760;
            return 3221228536LL;
          }
          v10 = PdhSetQueryTimeRange(phQuery, &v21);
          *(&v2->max.CStatus + 1) = v10;
          if ( !v10 )
          {
            qword_1400820A0 = v21.StartTime;
            EndTime = v21.EndTime;
LABEL_19:
            qword_1400820A8 = EndTime;
            Log = QueryLog(hDataSource, phQuery, (struct _LIST_ENTRY *)v2);
            *(&v2->max.CStatus + 1) = Log;
            if ( !Log )
            {
              Data = QueryData(phQuery, (struct _LIST_ENTRY *)v2);
              *(&v2->max.CStatus + 1) = Data;
              if ( !Data )
              {
                for ( i = *(struct _PDH_STATISTICS **)&v2->dwFormat; v2 != i; i = v15 )
                {
                  v15 = *(struct _PDH_STATISTICS **)&i->dwFormat;
                  v16 = PdhComputeCounterStatistics(
                          (PDH_HCOUNTER)i->min.largeValue,
                          0x8200u,
                          0,
                          i->mean.longValue,
                          (PPDH_RAW_COUNTER)i->max.largeValue,
                          i + 1);
                  if ( v16 )
                    goto LABEL_26;
                }
                v16 = 0;
LABEL_26:
                *(&v2->max.CStatus + 1) = v16;
              }
            }
          }
        }
      }
    }
  }
  if ( hDataSource )
    PdhCloseLog(hDataSource, 0);
  if ( phQuery )
    PdhCloseQuery(phQuery);
  return *(&v2->max.CStatus + 1);
}

```

## disassembly

```asm
0x14001a3b0  mov     r11, rsp
0x14001a3b3  mov     [r11+8], rbx
0x14001a3b7  push    rdi
0x14001a3b8  sub     rsp, 80h
0x14001a3bf  mov     rax, cs:__security_cookie
0x14001a3c6  xor     rax, rsp
0x14001a3c9  mov     [rsp+88h+var_10], rax
0x14001a3ce  mov     qword ptr [r11-58h], 0
0x14001a3d6  mov     qword ptr [r11-50h], 0
0x14001a3de  xorps   xmm0, xmm0
0x14001a3e1  xor     eax, eax
0x14001a3e3  movups  xmmword ptr [rsp+88h+pInfo.StartTime], xmm0
0x14001a3e8  mov     [r11-18h], rax
0x14001a3ec  xorps   xmm1, xmm1
0x14001a3ef  movups  xmmword ptr [rsp+88h+var_40.StartTime], xmm1
0x14001a3f4  mov     [r11-30h], rax
0x14001a3f8  lea     edi, [rax+1]
0x14001a3fb  mov     [rsp+88h+pdwNumEntries], edi
0x14001a3ff  mov     [rsp+88h+pdwBufferSize], 18h
0x14001a407  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x14001a40e  mov     rbx, [rax+21F0h]
0x14001a415  mov     dword ptr [rbx+1Ch], 0
0x14001a41c  cmp     dword ptr [rbx+20h], 0
0x14001a420  jbe     loc_14001A5F9
0x14001a426  mov     rdx, [rbx+38h]; LogFileNameList
0x14001a42a  lea     rcx, [r11-58h]; phDataSource
0x14001a42e  call    cs:__imp_PdhBindInputDataSourceW
0x14001a434  mov     [rbx+1Ch], eax
0x14001a437  test    eax, eax
0x14001a439  jnz     loc_14001A5F9
0x14001a43f  lea     r8, [rsp+88h+phQuery]; phQuery
0x14001a444  xor     edx, edx; dwUserData
0x14001a446  mov     rcx, [rsp+88h+hDataSource]; hDataSource
0x14001a44b  call    cs:__imp_PdhOpenQueryH
0x14001a451  mov     [rbx+1Ch], eax
0x14001a454  test    eax, eax
0x14001a456  jnz     loc_14001A5F9
0x14001a45c  lea     r9, [rsp+88h+pdwBufferSize]; pdwBufferSize
0x14001a461  lea     r8, [rsp+88h+pInfo]; pInfo
0x14001a466  lea     rdx, [rsp+88h+pdwNumEntries]; pdwNumEntries
0x14001a46b  mov     rcx, [rsp+88h+hDataSource]; hDataSource
0x14001a470  call    cs:__imp_PdhGetDataSourceTimeRangeH
0x14001a476  mov     [rbx+1Ch], eax
0x14001a479  test    eax, eax
0x14001a47b  jnz     loc_14001A5F9
0x14001a481  mov     eax, [rsp+88h+pInfo.SampleCount]
0x14001a485  mov     [rbx+18h], eax
0x14001a488  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x14001a48f  cmp     byte ptr [rax+2139h], 0
0x14001a496  jz      loc_14001A56F
0x14001a49c  mov     rcx, cs:qword_1400820B8; unsigned __int64
0x14001a4a3  call    ?TraceToPDHTime@@YA_K_K@Z; TraceToPDHTime(unsigned __int64)
0x14001a4a8  mov     [rsp+88h+var_40.StartTime], rax
0x14001a4ad  mov     rcx, cs:qword_1400820C0; unsigned __int64
0x14001a4b4  call    ?TraceToPDHTime@@YA_K_K@Z; TraceToPDHTime(unsigned __int64)
0x14001a4b9  mov     rcx, rax
0x14001a4bc  mov     [rsp+88h+var_40.EndTime], rax
0x14001a4c1  mov     [rsp+88h+var_40.SampleCount], 0
0x14001a4c9  mov     r9, [rsp+88h+pInfo.StartTime]
0x14001a4ce  mov     rdx, r9
0x14001a4d1  cmp     r9, [rsp+88h+var_40.StartTime]
0x14001a4d6  cmovl   rdx, [rsp+88h+var_40.StartTime]
0x14001a4dc  mov     r8, [rsp+88h+pInfo.EndTime]
0x14001a4e1  cmp     r8, rax
0x14001a4e4  cmovl   rcx, r8
0x14001a4e8  cmp     rdx, rcx
0x14001a4eb  jl      short loc_14001A4F2
0x14001a4ed  xor     dil, dil
0x14001a4f0  jmp     short loc_14001A52B
0x14001a4f2  mov     rax, rcx
0x14001a4f5  sub     rax, rdx
0x14001a4f8  xorps   xmm1, xmm1
0x14001a4fb  cvtsi2sd xmm1, rax
0x14001a500  sub     r8, r9
0x14001a503  xorps   xmm0, xmm0
0x14001a506  cvtsi2sd xmm0, r8
0x14001a50b  mulsd   xmm0, cs:__real@3f947ae147ae147b
0x14001a513  comisd  xmm0, xmm1
0x14001a517  ja      short loc_14001A4ED
0x14001a519  mov     [rsp+88h+var_40.StartTime], rdx
0x14001a51e  mov     [rsp+88h+var_40.EndTime], rcx
0x14001a523  mov     [rsp+88h+var_40.SampleCount], 0
0x14001a52b  test    dil, dil
0x14001a52e  jnz     short loc_14001A541
0x14001a530  mov     dword ptr [rbx+1Ch], 0C0000BF8h
0x14001a537  mov     eax, 0C0000BF8h
0x14001a53c  jmp     loc_14001A620
0x14001a541  lea     rdx, [rsp+88h+var_40]; pInfo
0x14001a546  mov     rcx, [rsp+88h+phQuery]; hQuery
0x14001a54b  call    cs:__imp_PdhSetQueryTimeRange
0x14001a551  mov     [rbx+1Ch], eax
0x14001a554  test    eax, eax
0x14001a556  jnz     loc_14001A5F9
0x14001a55c  mov     rax, [rsp+88h+var_40.StartTime]
0x14001a561  mov     cs:qword_1400820A0, rax
0x14001a568  mov     rax, [rsp+88h+var_40.EndTime]
0x14001a56d  jmp     short loc_14001A580
0x14001a56f  mov     rax, [rsp+88h+pInfo.StartTime]
0x14001a574  mov     cs:qword_1400820A0, rax
0x14001a57b  mov     rax, [rsp+88h+pInfo.EndTime]
0x14001a580  mov     cs:qword_1400820A8, rax
0x14001a587  mov     r8, rbx; struct _LIST_ENTRY *
0x14001a58a  mov     rdx, [rsp+88h+phQuery]; void *
0x14001a58f  mov     rcx, [rsp+88h+hDataSource]; void *
0x14001a594  call    ?QueryLog@@YAJPEAX0PEAU_LIST_ENTRY@@@Z; QueryLog(void *,void *,_LIST_ENTRY *)
0x14001a599  mov     [rbx+1Ch], eax
0x14001a59c  test    eax, eax
0x14001a59e  jnz     short loc_14001A5F9
0x14001a5a0  mov     rdx, rbx; struct _LIST_ENTRY *
0x14001a5a3  mov     rcx, [rsp+88h+phQuery]; hQuery
0x14001a5a8  call    ?QueryData@@YAJPEAXPEAU_LIST_ENTRY@@@Z; QueryData(void *,_LIST_ENTRY *)
0x14001a5ad  mov     [rbx+1Ch], eax
0x14001a5b0  test    eax, eax
0x14001a5b2  jnz     short loc_14001A5F9
0x14001a5b4  mov     rcx, [rbx]
0x14001a5b7  cmp     rbx, rcx
0x14001a5ba  jz      short loc_14001A5F0
0x14001a5bc  mov     rdi, [rcx]
0x14001a5bf  lea     rax, [rcx+38h]
0x14001a5c3  mov     [rsp+88h+data], rax; data
0x14001a5c8  mov     rax, [rcx+20h]
0x14001a5cc  mov     [rsp+88h+lpRawValueArray], rax; lpRawValueArray
0x14001a5d1  mov     r9d, [rcx+30h]; dwNumEntries
0x14001a5d5  xor     r8d, r8d; dwFirstEntry
0x14001a5d8  mov     edx, 8200h; dwFormat
0x14001a5dd  mov     rcx, [rcx+10h]; hCounter
0x14001a5e1  call    cs:__imp_PdhComputeCounterStatistics
0x14001a5e7  test    eax, eax
0x14001a5e9  jnz     short loc_14001A5F2
0x14001a5eb  mov     rcx, rdi
0x14001a5ee  jmp     short loc_14001A5B7
0x14001a5f0  xor     eax, eax
0x14001a5f2  mov     [rbx+1Ch], eax
0x14001a5f5  test    eax, eax
0x14001a5f7  jnz     short $+2
0x14001a5f9  mov     rcx, [rsp+88h+hDataSource]; hLog
0x14001a5fe  test    rcx, rcx
0x14001a601  jz      short loc_14001A60B
0x14001a603  xor     edx, edx; dwFlags
0x14001a605  call    cs:__imp_PdhCloseLog
0x14001a60b  mov     rcx, [rsp+88h+phQuery]; hQuery
0x14001a610  test    rcx, rcx
0x14001a613  jz      short loc_14001A61B
0x14001a615  call    cs:__imp_PdhCloseQuery
0x14001a61b  mov     eax, [rbx+1Ch]
0x14001a61e  jmp     short $+2
0x14001a620  mov     rcx, [rsp+88h+var_10]
0x14001a625  xor     rcx, rsp; StackCookie
0x14001a628  call    __security_check_cookie
0x14001a62d  mov     rbx, [rsp+88h+arg_0]
0x14001a635  add     rsp, 80h
0x14001a63c  pop     rdi
0x14001a63d  retn
```
