# ComputeService::Net::Details::AddOrRemoveIPAddress(ulong,uint,ushort const *,uchar,bool)

- ea: `0x1400b1bb8`
- end: `0x1400b1cf0`
- name: `?AddOrRemoveIPAddress@Details@Net@ComputeService@@YAXKIPEBGE_N@Z`
- size: `312`
- prototype: `void(ComputeService::Net::Details *__hidden this, unsigned int, unsigned int, const unsigned __int16 *, unsigned __int8, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400ad3a0`

## callees

- `0x140005360`
- `0x140006098`
- `0x1400341ac`
- `0x1400b1908`
- `0x1400b1bb8`
- `0x1400b26a8`
- `0x1400b2768`

## import_xrefs

- `IPHLPAPI!CreateUnicastIpAddressEntry` at `0x1400b1c98`
- `IPHLPAPI!CreateUnicastIpAddressEntry` at `0x1400b1c98`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x1400b1c16`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x1400b1c16`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1400b1c37`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1400b1c37`

## string_xrefs

- `0x1400b1c64`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400b1cde`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeService::Net::Details::AddOrRemoveIPAddress(
        ComputeService::Net::Details *this,
        NET_IF_COMPARTMENT_ID a2,
        const WCHAR *a3,
        const unsigned __int16 *a4)
{
  UINT8 v4; // si
  NET_IFINDEX v7; // edi
  const unsigned __int16 *v8; // rdx
  struct sockaddr_storage *v9; // r9
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12[2]; // [rsp+20h] [rbp-E0h] BYREF
  const char *v13; // [rsp+28h] [rbp-D8h]
  __int64 v14; // [rsp+30h] [rbp-D0h]
  __int16 v15; // [rsp+38h] [rbp-C8h]
  _OWORD v16[3]; // [rsp+40h] [rbp-C0h] BYREF
  _MIB_UNICASTIPADDRESS_ROW Row; // [rsp+70h] [rbp-90h] BYREF
  int v18[4]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v4 = (unsigned __int8)a4;
  v7 = (unsigned int)this;
  memset_0(&Row, 0, sizeof(Row));
  memset_0(v18, 0, 0x80u);
  Vml::VmStringToIpAddress(a3, v8, (int)v18, v9);
  InitializeUnicastIpAddressEntry(&Row);
  Row.InterfaceIndex = v7;
  Row.OnLinkPrefixLength = v4;
  Row.DadState = NldsPreferred;
  Row.Address.Ipv4 = *(SOCKADDR_IN *)v18;
  v10 = SetCurrentThreadCompartmentId(a2);
  if ( v10 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
      (const char *)v10,
      v12[0]);
  memset(v16, 0, sizeof(v16));
  *(_QWORD *)v12 = retaddr;
  v13 = "onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp";
  v14 = 0;
  v15 = 171;
  wil::scope_exit_log__lambda_c68909df8d60a9e460b50da927fd40f5___(v16, v12);
  v11 = CreateUnicastIpAddressEntry(&Row);
  if ( v11 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xB1,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
      (const char *)v11,
      v12[0]);
  wil::details::lambda_call_log__lambda_c68909df8d60a9e460b50da927fd40f5___::reset(v16);
}

```

## disassembly

```asm
0x1400b1bb8  push    rbp
0x1400b1bba  push    rbx
0x1400b1bbb  push    rsi
0x1400b1bbc  push    rdi
0x1400b1bbd  push    r14
0x1400b1bbf  lea     rbp, [rsp-50h]
0x1400b1bc4  sub     rsp, 150h
0x1400b1bcb  mov     rax, cs:__security_cookie
0x1400b1bd2  xor     rax, rsp
0x1400b1bd5  mov     [rbp+70h+var_30], rax
0x1400b1bd9  mov     sil, r9b
0x1400b1bdc  mov     rbx, r8
0x1400b1bdf  mov     r14d, edx
0x1400b1be2  mov     edi, ecx
0x1400b1be4  xor     edx, edx; Val
0x1400b1be6  lea     r8d, [rdx+50h]; Size
0x1400b1bea  lea     rcx, [rsp+170h+Row]; void *
0x1400b1bef  call    memset_0
0x1400b1bf4  xor     edx, edx; Val
0x1400b1bf6  mov     r8d, 80h; Size
0x1400b1bfc  lea     rcx, [rbp+70h+var_B0]; void *
0x1400b1c00  call    memset_0
0x1400b1c05  lea     r8, [rbp+70h+var_B0]; int
0x1400b1c09  mov     rcx, rbx; S
0x1400b1c0c  call    ?VmStringToIpAddress@Vml@@YAHPEBGHAEAUsockaddr_storage@@@Z; Vml::VmStringToIpAddress(ushort const *,int,sockaddr_storage &)
0x1400b1c11  lea     rcx, [rsp+170h+Row]; Row
0x1400b1c16  call    cs:__imp_InitializeUnicastIpAddressEntry
0x1400b1c1c  mov     [rbp+70h+Row.InterfaceIndex], edi
0x1400b1c1f  mov     [rbp+70h+Row.OnLinkPrefixLength], sil
0x1400b1c23  mov     [rbp+70h+Row.DadState], 4
0x1400b1c2a  movaps  xmm0, xmmword ptr [rbp+70h+var_B0]
0x1400b1c2e  movdqu  xmmword ptr [rsp+170h+Row.Address], xmm0
0x1400b1c34  mov     ecx, r14d; CompartmentId
0x1400b1c37  call    cs:__imp_SetCurrentThreadCompartmentId
0x1400b1c3d  mov     rcx, [rbp+78h]; this
0x1400b1c41  test    eax, eax
0x1400b1c43  jnz     loc_1400B1CDB
0x1400b1c49  xorps   xmm0, xmm0
0x1400b1c4c  movups  [rsp+170h+var_130], xmm0
0x1400b1c51  movups  [rsp+170h+var_120], xmm0
0x1400b1c56  movups  [rsp+170h+var_110], xmm0
0x1400b1c5b  mov     rax, [rbp+78h]
0x1400b1c5f  mov     qword ptr [rsp+170h+var_150], rax; unsigned int
0x1400b1c64  lea     rbx, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400b1c6b  mov     [rsp+170h+var_148], rbx
0x1400b1c70  mov     [rsp+170h+var_140], 0
0x1400b1c79  mov     eax, 0ABh
0x1400b1c7e  mov     [rsp+170h+var_138], ax
0x1400b1c83  lea     rdx, [rsp+170h+var_150]
0x1400b1c88  lea     rcx, [rsp+170h+var_130]
0x1400b1c8d  call    wil__scope_exit_log__lambda_c68909df8d60a9e460b50da927fd40f5___
0x1400b1c92  nop
0x1400b1c93  lea     rcx, [rsp+170h+Row]; Row
0x1400b1c98  call    cs:__imp_CreateUnicastIpAddressEntry
0x1400b1c9e  mov     rcx, [rbp+78h]; this
0x1400b1ca2  test    eax, eax
0x1400b1ca4  jnz     short loc_1400B1CCA
0x1400b1ca6  lea     rcx, [rsp+170h+var_130]
0x1400b1cab  call    wil__details__lambda_call_log__lambda_c68909df8d60a9e460b50da927fd40f5_____reset
0x1400b1cb0  mov     rcx, [rbp+70h+var_30]
0x1400b1cb4  xor     rcx, rsp; StackCookie
0x1400b1cb7  call    __security_check_cookie
0x1400b1cbc  add     rsp, 150h
0x1400b1cc3  pop     r14
0x1400b1cc5  pop     rdi
0x1400b1cc6  pop     rsi
0x1400b1cc7  pop     rbx
0x1400b1cc8  pop     rbp
0x1400b1cc9  retn
0x1400b1cca  mov     r9d, eax; char *
0x1400b1ccd  mov     r8, rbx; unsigned int
0x1400b1cd0  mov     edx, 0B1h; void *
0x1400b1cd5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b1cdb  mov     r9d, eax; char *
0x1400b1cde  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400b1ce5  mov     edx, 0AAh; void *
0x1400b1cea  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
