# InitializeWPInstanceCounters(void)

- ea: `0x140001da4`
- end: `0x140001ee2`
- name: `?InitializeWPInstanceCounters@@YAJXZ`
- size: `318`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400027b0`

## callees

- `0x140001da4`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x140001e29`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x140001e36`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x140001e29`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x140001e36`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProvider` at `0x140001dba`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProvider` at `0x140001df6`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProvider` at `0x140001dba`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProvider` at `0x140001df6`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x140001dda`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x140001e16`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x140001dda`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x140001e16`
- `iisutil!PuDbgPrintError` at `0x140001e83`
- `iisutil!PuDbgPrintError` at `0x140001e83`

## string_xrefs

- `0x140001e7c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wp\w3wp.cxx`

## pseudocode

```c
__int64 InitializeWPInstanceCounters(void)
{
  signed int started; // ebx

  started = PerfStartProvider(&ProviderGuid_WPInstanceCounters_1, 0, &hDataSource_WPInstanceCounters_1);
  if ( (started
     || (started = PerfSetCounterSetInfo(hDataSource_WPInstanceCounters_1, &CtrSet_WPInstanceCounters_1_1, 0x128u)) != 0
     || (started = PerfStartProvider(&ProviderGuid_WPInstanceCounters_2, 0, &hDataSource_WPInstanceCounters_2)) != 0
     || (started = PerfSetCounterSetInfo(hDataSource_WPInstanceCounters_2, &CtrSet_WPInstanceCounters_2_1, 0x688u)) != 0)
    && (PerfStopProvider(hDataSource_WPInstanceCounters_1), PerfStopProvider(hDataSource_WPInstanceCounters_2), started) )
  {
    if ( started > 0 )
      started = (unsigned __int16)started | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wp\\w3wp.cxx",
        211,
        "InitializeWPInstanceCounters",
        started,
        "PerfAutoInitialize failed.\n");
  }
  else
  {
    started = 0;
    g_WPCountersManagerInfo = hDataSource_WPInstanceCounters_1;
    qword_140008E98 = (__int64)hDataSource_WPInstanceCounters_2;
    qword_140008EA8 = (__int64)CtrSetGuid_WPInstanceCounters_1_1;
    dword_140008EA0 = 0;
    dword_140008EB8 = 1;
    dword_140008ED0 = 1;
    qword_140008EC0 = (__int64)CtrSetGuid_WPInstanceCounters_2_1;
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x140001da4  push    rbx
0x140001da6  sub     rsp, 30h
0x140001daa  lea     r8, hDataSource_WPInstanceCounters_1; phProvider
0x140001db1  xor     edx, edx; ControlCallback
0x140001db3  lea     rcx, ProviderGuid_WPInstanceCounters_1; ProviderGuid
0x140001dba  call    cs:__imp_PerfStartProvider
0x140001dc0  mov     ebx, eax
0x140001dc2  test    eax, eax
0x140001dc4  jnz     short loc_140001E22
0x140001dc6  mov     rcx, cs:hDataSource_WPInstanceCounters_1; ProviderHandle
0x140001dcd  lea     rdx, CtrSet_WPInstanceCounters_1_1; Template
0x140001dd4  mov     r8d, 128h; TemplateSize
0x140001dda  call    cs:__imp_PerfSetCounterSetInfo
0x140001de0  mov     ebx, eax
0x140001de2  test    eax, eax
0x140001de4  jnz     short loc_140001E22
0x140001de6  lea     r8, hDataSource_WPInstanceCounters_2; phProvider
0x140001ded  xor     edx, edx; ControlCallback
0x140001def  lea     rcx, ProviderGuid_WPInstanceCounters_2; ProviderGuid
0x140001df6  call    cs:__imp_PerfStartProvider
0x140001dfc  mov     ebx, eax
0x140001dfe  test    eax, eax
0x140001e00  jnz     short loc_140001E22
0x140001e02  mov     rcx, cs:hDataSource_WPInstanceCounters_2; ProviderHandle
0x140001e09  lea     rdx, CtrSet_WPInstanceCounters_2_1; Template
0x140001e10  mov     r8d, 688h; TemplateSize
0x140001e16  call    cs:__imp_PerfSetCounterSetInfo
0x140001e1c  mov     ebx, eax
0x140001e1e  test    eax, eax
0x140001e20  jz      short loc_140001E8B
0x140001e22  mov     rcx, cs:hDataSource_WPInstanceCounters_1; ProviderHandle
0x140001e29  call    cs:__imp_PerfStopProvider
0x140001e2f  mov     rcx, cs:hDataSource_WPInstanceCounters_2; ProviderHandle
0x140001e36  call    cs:__imp_PerfStopProvider
0x140001e3c  test    ebx, ebx
0x140001e3e  jz      short loc_140001E8B
0x140001e40  jle     short loc_140001E4B
0x140001e42  movzx   ebx, bx
0x140001e45  or      ebx, 80070000h
0x140001e4b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x140001e52  jz      loc_140001EDA
0x140001e58  mov     rcx, cs:g_pDebug
0x140001e5f  lea     rax, aPerfautoinitia; "PerfAutoInitialize failed.\n"
0x140001e66  mov     [rsp+38h+var_10], rax
0x140001e6b  lea     r9, aInitializewpin; "InitializeWPInstanceCounters"
0x140001e72  mov     r8d, 0D3h
0x140001e78  mov     [rsp+38h+var_18], ebx
0x140001e7c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x140001e83  call    cs:__imp_PuDbgPrintError
0x140001e89  jmp     short loc_140001EDA
0x140001e8b  mov     rcx, cs:hDataSource_WPInstanceCounters_1
0x140001e92  lea     rax, CtrSetGuid_WPInstanceCounters_1_1
0x140001e99  xor     ebx, ebx
0x140001e9b  mov     cs:?g_WPCountersManagerInfo@@3UWP_COUNTERS_MANAGER_INFO@@A, rcx; WP_COUNTERS_MANAGER_INFO g_WPCountersManagerInfo
0x140001ea2  mov     rcx, cs:hDataSource_WPInstanceCounters_2
0x140001ea9  mov     cs:qword_140008E98, rcx
0x140001eb0  mov     cs:qword_140008EA8, rax
0x140001eb7  lea     rax, CtrSetGuid_WPInstanceCounters_2_1
0x140001ebe  lea     ecx, [rbx+1]
0x140001ec1  mov     cs:dword_140008EA0, ebx
0x140001ec7  mov     cs:dword_140008EB8, ecx
0x140001ecd  mov     cs:dword_140008ED0, ecx
0x140001ed3  mov     cs:qword_140008EC0, rax
0x140001eda  mov     eax, ebx
0x140001edc  add     rsp, 30h
0x140001ee0  pop     rbx
0x140001ee1  retn
```
