# InitializeWPInstanceCounters(void)

- ea: `0x140001e74`
- end: `0x140001fdd`
- name: `?InitializeWPInstanceCounters@@YAJXZ`
- size: `361`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002a40`

## callees

- `0x140001e74`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x140001f11`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x140001f24`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x140001f11`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x140001f24`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProvider` at `0x140001e8a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProvider` at `0x140001ed2`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProvider` at `0x140001e8a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProvider` at `0x140001ed2`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x140001eb0`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x140001ef8`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x140001eb0`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x140001ef8`
- `iisutil!PuDbgPrintError` at `0x140001f77`
- `iisutil!PuDbgPrintError` at `0x140001f77`

## string_xrefs

- `0x140001f70`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wp\w3wp.cxx`

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
0x140001e74  push    rbx
0x140001e76  sub     rsp, 30h
0x140001e7a  lea     r8, hDataSource_WPInstanceCounters_1; phProvider
0x140001e81  xor     edx, edx; ControlCallback
0x140001e83  lea     rcx, ProviderGuid_WPInstanceCounters_1; ProviderGuid
0x140001e8a  call    cs:__imp_PerfStartProvider
0x140001e91  nop     dword ptr [rax+rax+00h]
0x140001e96  mov     ebx, eax
0x140001e98  test    eax, eax
0x140001e9a  jnz     short loc_140001F0A
0x140001e9c  mov     rcx, cs:hDataSource_WPInstanceCounters_1; ProviderHandle
0x140001ea3  lea     rdx, CtrSet_WPInstanceCounters_1_1; Template
0x140001eaa  mov     r8d, 128h; TemplateSize
0x140001eb0  call    cs:__imp_PerfSetCounterSetInfo
0x140001eb7  nop     dword ptr [rax+rax+00h]
0x140001ebc  mov     ebx, eax
0x140001ebe  test    eax, eax
0x140001ec0  jnz     short loc_140001F0A
0x140001ec2  lea     r8, hDataSource_WPInstanceCounters_2; phProvider
0x140001ec9  xor     edx, edx; ControlCallback
0x140001ecb  lea     rcx, ProviderGuid_WPInstanceCounters_2; ProviderGuid
0x140001ed2  call    cs:__imp_PerfStartProvider
0x140001ed9  nop     dword ptr [rax+rax+00h]
0x140001ede  mov     ebx, eax
0x140001ee0  test    eax, eax
0x140001ee2  jnz     short loc_140001F0A
0x140001ee4  mov     rcx, cs:hDataSource_WPInstanceCounters_2; ProviderHandle
0x140001eeb  lea     rdx, CtrSet_WPInstanceCounters_2_1; Template
0x140001ef2  mov     r8d, 688h; TemplateSize
0x140001ef8  call    cs:__imp_PerfSetCounterSetInfo
0x140001eff  nop     dword ptr [rax+rax+00h]
0x140001f04  mov     ebx, eax
0x140001f06  test    eax, eax
0x140001f08  jz      short loc_140001F85
0x140001f0a  mov     rcx, cs:hDataSource_WPInstanceCounters_1; ProviderHandle
0x140001f11  call    cs:__imp_PerfStopProvider
0x140001f18  nop     dword ptr [rax+rax+00h]
0x140001f1d  mov     rcx, cs:hDataSource_WPInstanceCounters_2; ProviderHandle
0x140001f24  call    cs:__imp_PerfStopProvider
0x140001f2b  nop     dword ptr [rax+rax+00h]
0x140001f30  test    ebx, ebx
0x140001f32  jz      short loc_140001F85
0x140001f34  jle     short loc_140001F3F
0x140001f36  movzx   ebx, bx
0x140001f39  or      ebx, 80070000h
0x140001f3f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x140001f46  jz      loc_140001FD4
0x140001f4c  mov     rcx, cs:g_pDebug
0x140001f53  lea     rax, aPerfautoinitia; "PerfAutoInitialize failed.\n"
0x140001f5a  mov     [rsp+38h+var_10], rax
0x140001f5f  lea     r9, aInitializewpin; "InitializeWPInstanceCounters"
0x140001f66  mov     r8d, 0D3h
0x140001f6c  mov     [rsp+38h+var_18], ebx
0x140001f70  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x140001f77  call    cs:__imp_PuDbgPrintError
0x140001f7e  nop     dword ptr [rax+rax+00h]
0x140001f83  jmp     short loc_140001FD4
0x140001f85  mov     rcx, cs:hDataSource_WPInstanceCounters_1
0x140001f8c  lea     rax, CtrSetGuid_WPInstanceCounters_1_1
0x140001f93  xor     ebx, ebx
0x140001f95  mov     cs:?g_WPCountersManagerInfo@@3UWP_COUNTERS_MANAGER_INFO@@A, rcx; WP_COUNTERS_MANAGER_INFO g_WPCountersManagerInfo
0x140001f9c  mov     rcx, cs:hDataSource_WPInstanceCounters_2
0x140001fa3  mov     cs:qword_140008E98, rcx
0x140001faa  mov     cs:qword_140008EA8, rax
0x140001fb1  lea     rax, CtrSetGuid_WPInstanceCounters_2_1
0x140001fb8  lea     ecx, [rbx+1]
0x140001fbb  mov     cs:dword_140008EA0, ebx
0x140001fc1  mov     cs:dword_140008EB8, ecx
0x140001fc7  mov     cs:dword_140008ED0, ecx
0x140001fcd  mov     cs:qword_140008EC0, rax
0x140001fd4  mov     eax, ebx
0x140001fd6  add     rsp, 30h
0x140001fda  pop     rbx
0x140001fdb  retn
```
