# ComputeService::Net::SetDefaultRoute(ulong,uint,ushort const *)

- ea: `0x1400b23e0`
- end: `0x1400b2501`
- name: `?SetDefaultRoute@Net@ComputeService@@YAXKIPEBG@Z`
- size: `289`
- prototype: `void(ComputeService::Net *__hidden this, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400ad3a0`

## callees

- `0x140005360`
- `0x140006098`
- `0x1400341ac`
- `0x1400b23e0`
- `0x1400b26a8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400b2495`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400b2495`
- `IPHLPAPI!InitializeIpForwardEntry` at `0x1400b243b`
- `IPHLPAPI!InitializeIpForwardEntry` at `0x1400b243b`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1400b2470`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1400b24a6`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1400b2470`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1400b24a6`
- `IPHLPAPI!CreateIpForwardEntry2` at `0x1400b2481`
- `IPHLPAPI!CreateIpForwardEntry2` at `0x1400b2481`

## string_xrefs

- `0x1400b24d3`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400b24ec`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`

## pseudocode

```c
void __fastcall ComputeService::Net::SetDefaultRoute(
        ComputeService::Net *this,
        NET_IF_COMPARTMENT_ID a2,
        const WCHAR *a3,
        const unsigned __int16 *a4)
{
  NET_IFINDEX v6; // edi
  const unsigned __int16 *v7; // rdx
  struct sockaddr_storage *v8; // r9
  unsigned int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // edi
  unsigned int v12; // ecx
  _MIB_IPFORWARD_ROW2 Row; // [rsp+20h] [rbp-E0h] BYREF
  int v14[4]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v6 = (unsigned int)this;
  memset_0(v14, 0, 0x80u);
  Vml::VmStringToIpAddress(a3, v7, (int)v14, v8);
  memset_0(&Row, 0, sizeof(Row));
  InitializeIpForwardEntry(&Row);
  Row.InterfaceIndex = v6;
  memset(&Row.DestinationPrefix, 0, sizeof(Row.DestinationPrefix));
  Row.Protocol = RouteProtocolNetMgmt;
  Row.NextHop.Ipv4 = *(SOCKADDR_IN *)v14;
  Row.DestinationPrefix.Prefix.Ipv4.sin_family = 2;
  v9 = SetCurrentThreadCompartmentId(a2);
  if ( v9 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2D1,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
      (const char *)v9,
      Row.InterfaceLuid.Value);
  v10 = 0;
  do
  {
    v11 = CreateIpForwardEntry2(&Row);
    if ( v11 != 1168 )
      break;
    Sleep(0xFu);
    v12 = v10++;
  }
  while ( v12 < 0x3C );
  SetCurrentThreadCompartmentId(0);
  if ( v11 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2DE,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
      (const char *)v11,
      Row.InterfaceLuid.Value);
}

```

## disassembly

```asm
0x1400b23e0  mov     [rsp-8+arg_18], rbx
0x1400b23e5  push    rbp
0x1400b23e6  push    rsi
0x1400b23e7  push    rdi
0x1400b23e8  lea     rbp, [rsp-20h]
0x1400b23ed  sub     rsp, 120h
0x1400b23f4  mov     rax, cs:__security_cookie
0x1400b23fb  xor     rax, rsp
0x1400b23fe  mov     [rbp+30h+var_20], rax
0x1400b2402  mov     rbx, r8
0x1400b2405  mov     esi, edx
0x1400b2407  mov     edi, ecx
0x1400b2409  xor     edx, edx; Val
0x1400b240b  mov     r8d, 80h; Size
0x1400b2411  lea     rcx, [rbp+30h+var_A0]; void *
0x1400b2415  call    memset_0
0x1400b241a  lea     r8, [rbp+30h+var_A0]; int
0x1400b241e  mov     rcx, rbx; S
0x1400b2421  call    ?VmStringToIpAddress@Vml@@YAHPEBGHAEAUsockaddr_storage@@@Z; Vml::VmStringToIpAddress(ushort const *,int,sockaddr_storage &)
0x1400b2426  xor     edx, edx; Val
0x1400b2428  lea     rcx, [rsp+130h+Row]; void *
0x1400b242d  lea     r8d, [rdx+68h]; Size
0x1400b2431  call    memset_0
0x1400b2436  lea     rcx, [rsp+130h+Row]; Row
0x1400b243b  call    cs:__imp_InitializeIpForwardEntry
0x1400b2441  xorps   xmm0, xmm0
0x1400b2444  mov     [rsp+130h+Row.InterfaceIndex], edi
0x1400b2448  movups  xmmword ptr [rsp+130h+Row.DestinationPrefix.Prefix], xmm0
0x1400b244d  mov     eax, 2
0x1400b2452  mov     ecx, esi; CompartmentId
0x1400b2454  movups  xmmword ptr [rsp+130h+Row.DestinationPrefix.Prefix+10h], xmm0
0x1400b2459  mov     [rsp+130h+Row.Protocol], 3
0x1400b2461  movaps  xmm0, xmmword ptr [rbp+30h+var_A0]
0x1400b2465  movdqu  xmmword ptr [rsp+130h+Row.NextHop], xmm0
0x1400b246b  mov     word ptr [rsp+130h+Row.DestinationPrefix.Prefix], ax
0x1400b2470  call    cs:__imp_SetCurrentThreadCompartmentId
0x1400b2476  test    eax, eax
0x1400b2478  jnz     short loc_1400B24CF
0x1400b247a  xor     ebx, ebx
0x1400b247c  lea     rcx, [rsp+130h+Row]; Row
0x1400b2481  call    cs:__imp_CreateIpForwardEntry2
0x1400b2487  mov     edi, eax
0x1400b2489  cmp     eax, 490h
0x1400b248e  jnz     short loc_1400B24A4
0x1400b2490  mov     ecx, 0Fh; dwMilliseconds
0x1400b2495  call    cs:__imp_Sleep
0x1400b249b  mov     ecx, ebx
0x1400b249d  inc     ebx
0x1400b249f  cmp     ecx, 3Ch ; '<'
0x1400b24a2  jb      short loc_1400B247C
0x1400b24a4  xor     ecx, ecx; CompartmentId
0x1400b24a6  call    cs:__imp_SetCurrentThreadCompartmentId
0x1400b24ac  test    edi, edi
0x1400b24ae  jnz     short loc_1400B24E8
0x1400b24b0  mov     rcx, [rbp+30h+var_20]
0x1400b24b4  xor     rcx, rsp; StackCookie
0x1400b24b7  call    __security_check_cookie
0x1400b24bc  mov     rbx, [rsp+130h+arg_18]
0x1400b24c4  add     rsp, 120h
0x1400b24cb  pop     rdi
0x1400b24cc  pop     rsi
0x1400b24cd  pop     rbp
0x1400b24ce  retn
0x1400b24cf  mov     rcx, [rbp+38h]; this
0x1400b24d3  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400b24da  mov     r9d, eax; char *
0x1400b24dd  mov     edx, 2D1h; void *
0x1400b24e2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b24e8  mov     rcx, [rbp+38h]; this
0x1400b24ec  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400b24f3  mov     r9d, edi; char *
0x1400b24f6  mov     edx, 2DEh; void *
0x1400b24fb  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
