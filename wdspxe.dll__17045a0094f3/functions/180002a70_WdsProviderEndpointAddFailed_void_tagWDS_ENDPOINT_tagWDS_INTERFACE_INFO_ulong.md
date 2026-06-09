# WdsProviderEndpointAddFailed(void *,tagWDS_ENDPOINT *,tagWDS_INTERFACE_INFO *,ulong)

- ea: `0x180002a70`
- end: `0x180002b35`
- name: `?WdsProviderEndpointAddFailed@@YAXPEAXPEAUtagWDS_ENDPOINT@@PEAUtagWDS_INTERFACE_INFO@@K@Z`
- size: `197`
- prototype: `void(void *, struct tagWDS_ENDPOINT *, struct tagWDS_INTERFACE_INFO *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002988`
- `0x180002a30`
- `0x180011a90`

## import_xrefs

- `WdsCommonLib!?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAGK@Z` at `0x180002adc`
- `WdsCommonLib!?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAGK@Z` at `0x180002adc`

## string_xrefs

- `0x180002b02`: `Failed to listen on interface %s:%u for incoming client requests (rc=%u)`

## pseudocode

```c
void __fastcall WdsProviderEndpointAddFailed(
        void *a1,
        struct tagWDS_ENDPOINT *a2,
        struct tagWDS_INTERFACE_INFO *a3,
        int a4)
{
  unsigned int v4; // ebx
  size_t v6; // r8
  bool v8; // zf
  const wchar_t *v9; // r8
  __int128 v10; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+40h] [rbp-C0h]
  __int128 v12; // [rsp+50h] [rbp-B0h] BYREF
  int v13; // [rsp+60h] [rbp-A0h]
  BOOL v14; // [rsp+70h] [rbp-90h]
  _BYTE v15[140]; // [rsp+74h] [rbp-8Ch] BYREF

  v4 = *((unsigned __int16 *)a2 + 6);
  v12 = 0u;
  v6 = *((unsigned int *)a3 + 4);
  v13 = v6;
  memcpy_0(&v12, a3, v6);
  v11 = v13;
  v10 = v12;
  v8 = (unsigned int)CNetworkAddress::IpAddressToString(&v10, v15, 64) == 0;
  v9 = (const wchar_t *)v15;
  v14 = !v8;
  if ( !v8 )
    v9 = L"<<Failed>>";
  Trace(0x100000u, L"Failed to listen on interface %s:%u for incoming client requests (rc=%u)", v9, v4, a4);
}

```

## disassembly

```asm
0x180002a70  push    rbp
0x180002a72  push    rbx
0x180002a73  push    rdi
0x180002a74  lea     rbp, [rsp-10h]
0x180002a79  sub     rsp, 110h
0x180002a80  mov     rax, cs:__security_cookie
0x180002a87  xor     rax, rsp
0x180002a8a  mov     [rbp+20h+var_20], rax
0x180002a8e  movzx   ebx, word ptr [rdx+0Ch]
0x180002a92  lea     rcx, [rsp+120h+var_D0]; void *
0x180002a97  and     qword ptr [rsp+120h+var_D0], 0
0x180002a9d  mov     rax, r8
0x180002aa0  mov     r8d, [r8+10h]; Size
0x180002aa4  mov     rdx, rax; Src
0x180002aa7  and     qword ptr [rsp+120h+var_D0+8], 0
0x180002aad  mov     edi, r9d
0x180002ab0  mov     [rsp+120h+var_C0], r8d
0x180002ab5  call    memcpy_0
0x180002aba  movups  xmm0, [rsp+120h+var_D0]
0x180002abf  mov     eax, [rsp+120h+var_C0]
0x180002ac3  lea     rdx, [rsp+120h+var_AC]
0x180002ac8  mov     r8d, 40h ; '@'
0x180002ace  mov     [rsp+120h+var_E0], eax
0x180002ad2  lea     rcx, [rsp+120h+var_F0]
0x180002ad7  movaps  [rsp+120h+var_F0], xmm0
0x180002adc  call    cs:__imp_?IpAddressToString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAGK@Z; CNetworkAddress::IpAddressToString(tagWDS_IP_ADDRESS6,ushort *,ulong)
0x180002ae3  nop     dword ptr [rax+rax+00h]
0x180002ae8  xor     ecx, ecx
0x180002aea  mov     [rsp+120h+var_100], edi
0x180002aee  test    eax, eax
0x180002af0  lea     r8, [rsp+120h+var_AC]
0x180002af5  lea     rax, aFailed; "<<Failed>>"
0x180002afc  mov     r9d, ebx
0x180002aff  setnz   cl
0x180002b02  lea     rdx, aFailedToListen; "Failed to listen on interface %s:%u for"...
0x180002b09  test    ecx, ecx
0x180002b0b  mov     [rsp+120h+var_B0], ecx
0x180002b0f  mov     ecx, 100000h; unsigned int
0x180002b14  cmovnz  r8, rax
0x180002b18  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x180002b1d  mov     rcx, [rbp+20h+var_20]
0x180002b21  xor     rcx, rsp; StackCookie
0x180002b24  call    __security_check_cookie
0x180002b29  add     rsp, 110h
0x180002b30  pop     rdi
0x180002b31  pop     rbx
0x180002b32  pop     rbp
0x180002b33  retn
```
