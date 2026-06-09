# SubscribeToNetworkNotification(_OVERLAPPED &)

- ea: `0x180047764`
- end: `0x180047894`
- name: `?SubscribeToNetworkNotification@@YAJAEAU_OVERLAPPED@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(LPOVERLAPPED overlapped)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800475d4`
- `0x1800e5ff0`

## callees

- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180047764`

## import_xrefs

- `WS2_32!WSACreateEvent` at `0x1800477d0`
- `WS2_32!WSACreateEvent` at `0x1800477d0`
- `WS2_32!WSACloseEvent` at `0x1800477bb`
- `WS2_32!WSACloseEvent` at `0x180047861`
- `WS2_32!WSACloseEvent` at `0x1800477bb`
- `WS2_32!WSACloseEvent` at `0x180047861`
- `WS2_32!__imp_WSAGetLastError` at `0x1800477df`
- `WS2_32!__imp_WSAGetLastError` at `0x180047811`
- `WS2_32!__imp_WSAGetLastError` at `0x18004781e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800477df`
- `WS2_32!__imp_WSAGetLastError` at `0x180047811`
- `WS2_32!__imp_WSAGetLastError` at `0x18004781e`
- `IPHLPAPI!NotifyAddrChange` at `0x180047807`
- `IPHLPAPI!NotifyAddrChange` at `0x180047807`

## string_xrefs

- `0x18004778a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\liveconnector.cpp`
- `0x1800477f1`: `Failed to WSACreateEvent: 0x%X`

## pseudocode

```c
__int64 __fastcall SubscribeToNetworkNotification(LPOVERLAPPED overlapped)
{
  HANDLE hEvent; // rcx
  HANDLE v3; // rax
  int Error; // eax
  const unsigned __int16 *v5; // r9
  unsigned int v6; // r8d
  unsigned int v7; // edi
  HANDLE v8; // rcx
  const unsigned __int16 *v10; // [rsp+20h] [rbp-30h]
  __int64 v11; // [rsp+20h] [rbp-30h]
  _QWORD v12[4]; // [rsp+30h] [rbp-20h] BYREF
  int v13; // [rsp+70h] [rbp+20h] BYREF
  void *Handle; // [rsp+78h] [rbp+28h] BYREF

  v13 = 0;
  v12[0] = "SubscribeToNetworkNotification";
  v12[1] = &v13;
  v12[2] = 0;
  v12[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\liveconnector.cpp",
    "SubscribeToNetworkNotification",
    (const char *)0xD7,
    0,
    v10);
  hEvent = overlapped->hEvent;
  Handle = 0;
  if ( hEvent )
  {
    WSACloseEvent(hEvent);
    overlapped->Internal = 0;
    overlapped->InternalHigh = 0;
    overlapped->Pointer = 0;
    overlapped->hEvent = 0;
  }
  v3 = WSACreateEvent();
  overlapped->hEvent = v3;
  if ( !v3 )
  {
    Error = WSAGetLastError();
    if ( Error > 0 )
      Error = (unsigned __int16)Error | 0x80070000;
    v5 = L"Failed to WSACreateEvent: 0x%X";
    v6 = 233;
LABEL_12:
    LODWORD(v11) = Error;
    v13 = Error;
    TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\liveconnector.cpp", v6, v5, v11);
    goto LABEL_13;
  }
  if ( NotifyAddrChange(&Handle, overlapped) && WSAGetLastError() != 997 )
  {
    Error = WSAGetLastError();
    if ( Error > 0 )
      Error = (unsigned __int16)Error | 0x80070000;
    v5 = L"Failed to subscribe to network change notification: 0x%X";
    v6 = 244;
    goto LABEL_12;
  }
LABEL_13:
  v7 = v13;
  if ( v13 < 0 )
  {
    v8 = overlapped->hEvent;
    if ( v8 )
    {
      WSACloseEvent(v8);
      v7 = v13;
    }
    overlapped->Internal = 0;
    overlapped->InternalHigh = 0;
    overlapped->Pointer = 0;
    overlapped->hEvent = 0;
  }
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v12);
  return v7;
}

```

## disassembly

```asm
0x180047764  mov     [rsp-18h+arg_10], rbx
0x180047769  push    rbp
0x18004776a  push    rsi
0x18004776b  push    rdi
0x18004776c  mov     rbp, rsp
0x18004776f  sub     rsp, 50h
0x180047773  xor     esi, esi
0x180047775  lea     rdx, aSubscribetonet; "SubscribeToNetworkNotification"
0x18004777c  mov     rbx, rcx
0x18004777f  mov     [rbp+arg_0], esi
0x180047782  lea     rax, [rbp+arg_0]
0x180047786  mov     [rbp+var_20], rdx
0x18004778a  lea     rdi, aOnecoreuapDsEx_31; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180047791  mov     [rbp+var_18], rax
0x180047795  mov     rcx, rdi; this
0x180047798  mov     [rbp+var_10], rsi
0x18004779c  xor     r9d, r9d; unsigned int
0x18004779f  mov     [rbp+var_8], rsi
0x1800477a3  mov     r8d, 0D7h; char *
0x1800477a9  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800477ae  mov     rcx, [rbx+18h]; hEvent
0x1800477b2  mov     [rbp+Handle], rsi
0x1800477b6  test    rcx, rcx
0x1800477b9  jz      short loc_1800477D0
0x1800477bb  call    cs:__imp_WSACloseEvent
0x1800477c1  mov     [rbx], rsi
0x1800477c4  mov     [rbx+8], rsi
0x1800477c8  mov     [rbx+10h], rsi
0x1800477cc  mov     [rbx+18h], rsi
0x1800477d0  call    cs:__imp_WSACreateEvent
0x1800477d6  mov     [rbx+18h], rax
0x1800477da  test    rax, rax
0x1800477dd  jnz     short loc_180047800
0x1800477df  call    cs:__imp_WSAGetLastError
0x1800477e5  test    eax, eax
0x1800477e7  jle     short loc_1800477F1
0x1800477e9  movzx   eax, ax
0x1800477ec  or      eax, 80070000h
0x1800477f1  lea     r9, aFailedToWsacre; "Failed to WSACreateEvent: 0x%X"
0x1800477f8  mov     r8d, 0E9h
0x1800477fe  jmp     short loc_18004783D
0x180047800  mov     rdx, rbx; overlapped
0x180047803  lea     rcx, [rbp+Handle]; Handle
0x180047807  call    cs:__imp_NotifyAddrChange
0x18004780d  test    eax, eax
0x18004780f  jz      short loc_180047851
0x180047811  call    cs:__imp_WSAGetLastError
0x180047817  cmp     eax, 3E5h
0x18004781c  jz      short loc_180047851
0x18004781e  call    cs:__imp_WSAGetLastError
0x180047824  test    eax, eax
0x180047826  jle     short loc_180047830
0x180047828  movzx   eax, ax
0x18004782b  or      eax, 80070000h
0x180047830  lea     r9, aFailedToSubscr; "Failed to subscribe to network change n"...
0x180047837  mov     r8d, 0F4h; unsigned int
0x18004783d  mov     rdx, rdi; char *
0x180047840  mov     [rsp+50h+var_30], eax
0x180047844  mov     ecx, 2; unsigned __int8
0x180047849  mov     [rbp+arg_0], eax
0x18004784c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180047851  mov     edi, [rbp+arg_0]
0x180047854  test    edi, edi
0x180047856  jns     short loc_180047879
0x180047858  mov     rcx, [rbx+18h]; hEvent
0x18004785c  test    rcx, rcx
0x18004785f  jz      short loc_18004786A
0x180047861  call    cs:__imp_WSACloseEvent
0x180047867  mov     edi, [rbp+arg_0]
0x18004786a  mov     [rbx], rsi
0x18004786d  mov     [rbx+8], rsi
0x180047871  mov     [rbx+10h], rsi
0x180047875  mov     [rbx+18h], rsi
0x180047879  lea     rcx, [rbp+var_20]
0x18004787d  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180047882  mov     rbx, [rsp+50h+arg_10]
0x18004788a  mov     eax, edi
0x18004788c  add     rsp, 50h
0x180047890  pop     rdi
0x180047891  pop     rsi
0x180047892  pop     rbp
0x180047893  retn
```
