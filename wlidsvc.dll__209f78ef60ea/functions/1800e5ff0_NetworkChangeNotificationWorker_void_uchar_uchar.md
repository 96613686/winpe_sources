# NetworkChangeNotificationWorker(void *,uchar,uchar)

- ea: `0x1800e5ff0`
- end: `0x1800e615b`
- name: `?NetworkChangeNotificationWorker@@YAXPEAXEE@Z`
- size: `363`
- prototype: `void __fastcall(void *, unsigned __int8, unsigned __int8)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18003c4d8`
- `0x180047764`
- `0x1800e5ff0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800e6135`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800e6135`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800e6056`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800e6056`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e609c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e609c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800e60fc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800e60fc`
- `WS2_32!WSACloseEvent` at `0x1800e6113`
- `WS2_32!WSACloseEvent` at `0x1800e6113`
- `WS2_32!__imp_WSACleanup` at `0x1800e612a`
- `WS2_32!__imp_WSACleanup` at `0x1800e612a`

## string_xrefs

- `0x1800e6031`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\liveconnector.cpp`
- `0x1800e60b1`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\liveconnector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall NetworkChangeNotificationWorker(void *a1, __int64 a2, char a3)
{
  int v4; // ebx
  HRESULT v5; // ecx
  HANDLE hEvent; // rcx
  const unsigned __int16 *v7; // [rsp+20h] [rbp-48h] BYREF
  const wil::ResultException *v8; // [rsp+28h] [rbp-40h] BYREF
  ATL::CAtlException *v9; // [rsp+30h] [rbp-38h] BYREF
  CPassportException *v10; // [rsp+38h] [rbp-30h] BYREF
  _QWORD v11[5]; // [rsp+40h] [rbp-28h] BYREF
  int v12; // [rsp+80h] [rbp+18h] BYREF
  __int64 v13; // [rsp+88h] [rbp+20h]

  v12 = 0;
  v11[0] = "NetworkChangeNotificationWorker";
  v11[1] = &v12;
  v11[2] = 0;
  v11[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\liveconnector.cpp",
    "NetworkChangeNotificationWorker",
    (const char *)0x65,
    0,
    v7);
  if ( !a3 )
  {
    v4 = 0;
    v13 = 0;
    v5 = CoInitializeEx(0, 0);
    if ( v5 < 0 )
    {
      HIDWORD(v13) = v5 == -2147417850;
    }
    else
    {
      v4 = 1;
      LODWORD(v13) = 1;
    }
    try
    {
      while ( 1 )
      {
        hEvent = g_overlap.hEvent;
        if ( !g_overlap.hEvent )
          break;
        if ( !g_fLCTaskInProgress )
          goto LABEL_14;
        if ( WaitForSingleObject(g_overlap.hEvent, 0xFFFFFFFF)
          || (TracePrintW(
                2u,
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\liveconnector.cpp",
                0x75u,
                L"Network notification event signaled"),
              !g_fLCTaskInProgress)
          || (RandomWait(), !g_fLCTaskInProgress)
          || (v12 = SubscribeToNetworkNotification(&g_overlap), v12 < 0)
          || !g_fLCTaskInProgress )
        {
          hEvent = g_overlap.hEvent;
LABEL_14:
          if ( hEvent )
          {
            WSACloseEvent(hEvent);
            *(_OWORD *)&g_overlap.Internal = 0;
            *(_OWORD *)&g_overlap.Offset = 0;
          }
          break;
        }
        Sleep(0xBB8u);
      }
      WSACleanup();
      if ( v4 )
        CoUninitialize();
    }
    catch ( CPassportException *v10 )
    {
      v12 = *((_DWORD *)v10 + 2);
      if ( v12 >= 0 )
        v12 = -2147418113;
    }
    catch ( ATL::CAtlException *v9 )
    {
      v12 = *(_DWORD *)v9;
      if ( v12 >= 0 )
        v12 = -2147418113;
    }
    catch ( std::bad_alloc )
    {
      v12 = -2147024882;
    }
    catch ( long v7 )
    {
      v12 = (int)v7;
      if ( (int)v7 >= 0 )
        v12 = -2147418113;
    }
    catch ( const wil::ResultException *v8 )
    {
      v12 = *((_DWORD *)v8 + 8);
      if ( v12 >= 0 )
        v12 = -2147418113;
    }
  }
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v11);
}

```

## disassembly

```asm
0x1800e5ff0  mov     r11, rsp
0x1800e5ff3  mov     [r11+8], rbx
0x1800e5ff7  push    rdi
0x1800e5ff8  sub     rsp, 60h
0x1800e5ffc  mov     bl, r8b
0x1800e5fff  mov     dword ptr [r11+18h], 0
0x1800e6007  lea     rdx, aNetworkchangen; "NetworkChangeNotificationWorker"
0x1800e600e  mov     [r11-28h], rdx
0x1800e6012  lea     rax, [r11+18h]
0x1800e6016  mov     [r11-20h], rax
0x1800e601a  mov     qword ptr [r11-18h], 0
0x1800e6022  mov     qword ptr [r11-10h], 0
0x1800e602a  xor     r9d, r9d; unsigned int
0x1800e602d  lea     r8d, [r9+65h]; char *
0x1800e6031  lea     rcx, aOnecoreuapDsEx_31; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800e6038  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800e603d  nop
0x1800e603e  test    bl, bl
0x1800e6040  jnz     loc_1800E6146
0x1800e6046  xor     ebx, ebx
0x1800e6048  mov     [rsp+68h+arg_18], rbx
0x1800e6050  xor     edi, edi
0x1800e6052  xor     edx, edx; dwCoInit
0x1800e6054  xor     ecx, ecx; pvReserved
0x1800e6056  call    cs:__imp_CoInitializeEx
0x1800e605c  mov     ecx, eax
0x1800e605e  test    eax, eax
0x1800e6060  lea     eax, [rbx+1]
0x1800e6063  js      short loc_1800E6070
0x1800e6065  mov     ebx, eax
0x1800e6067  mov     dword ptr [rsp+68h+arg_18], eax
0x1800e606e  jmp     short loc_1800E6080
0x1800e6070  cmp     ecx, 80010106h
0x1800e6076  cmovz   edi, eax
0x1800e6079  mov     dword ptr [rsp+68h+arg_18+4], edi
0x1800e6080  mov     rcx, cs:?g_overlap@@3U_OVERLAPPED@@A.hEvent; hHandle
0x1800e6087  test    rcx, rcx
0x1800e608a  jz      loc_1800E612A
0x1800e6090  cmp     cs:?g_fLCTaskInProgress@@3HA, 0; int g_fLCTaskInProgress
0x1800e6097  jz      short loc_1800E610E
0x1800e6099  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800e609c  call    cs:__imp_WaitForSingleObject
0x1800e60a2  test    eax, eax
0x1800e60a4  jnz     short loc_1800E6107
0x1800e60a6  lea     r9, aNetworkNotific; "Network notification event signaled"
0x1800e60ad  lea     r8d, [rax+75h]; unsigned int
0x1800e60b1  lea     rdx, aOnecoreuapDsEx_31; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800e60b8  lea     ecx, [rax+2]; unsigned __int8
0x1800e60bb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800e60c0  cmp     cs:?g_fLCTaskInProgress@@3HA, 0; int g_fLCTaskInProgress
0x1800e60c7  jz      short loc_1800E6107
0x1800e60c9  call    ?RandomWait@@YAXXZ; RandomWait(void)
0x1800e60ce  cmp     cs:?g_fLCTaskInProgress@@3HA, 0; int g_fLCTaskInProgress
0x1800e60d5  jz      short loc_1800E6107
0x1800e60d7  lea     rcx, ?g_overlap@@3U_OVERLAPPED@@A; overlapped
0x1800e60de  call    ?SubscribeToNetworkNotification@@YAJAEAU_OVERLAPPED@@@Z; SubscribeToNetworkNotification(_OVERLAPPED &)
0x1800e60e3  mov     [rsp+68h+arg_10], eax
0x1800e60ea  test    eax, eax
0x1800e60ec  js      short loc_1800E6107
0x1800e60ee  cmp     cs:?g_fLCTaskInProgress@@3HA, 0; int g_fLCTaskInProgress
0x1800e60f5  jz      short loc_1800E6107
0x1800e60f7  mov     ecx, 0BB8h; dwMilliseconds
0x1800e60fc  call    cs:__imp_Sleep
0x1800e6102  jmp     loc_1800E6080
0x1800e6107  mov     rcx, cs:?g_overlap@@3U_OVERLAPPED@@A.hEvent; hEvent
0x1800e610e  test    rcx, rcx
0x1800e6111  jz      short loc_1800E612A
0x1800e6113  call    cs:__imp_WSACloseEvent
0x1800e6119  xorps   xmm0, xmm0
0x1800e611c  movups  xmmword ptr cs:?g_overlap@@3U_OVERLAPPED@@A.Internal, xmm0; _OVERLAPPED g_overlap ...
0x1800e6123  movups  xmmword ptr cs:?g_overlap@@3U_OVERLAPPED@@A.10h, xmm0; _OVERLAPPED g_overlap ...
0x1800e612a  call    cs:__imp_WSACleanup
0x1800e6130  nop
0x1800e6131  test    ebx, ebx
0x1800e6133  jz      short loc_1800E613C
0x1800e6135  call    cs:__imp_CoUninitialize
0x1800e613b  nop
0x1800e613c  jmp     short loc_1800E6146
0x1800e613e  jmp     short loc_1800E6146
0x1800e6140  jmp     short loc_1800E6146
0x1800e6142  jmp     short loc_1800E6146
0x1800e6144  jmp     short $+2
0x1800e6146  lea     rcx, [rsp+68h+var_28]
0x1800e614b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800e6150  mov     rbx, [rsp+68h+arg_0]
0x1800e6155  add     rsp, 60h
0x1800e6159  pop     rdi
0x1800e615a  retn
```
