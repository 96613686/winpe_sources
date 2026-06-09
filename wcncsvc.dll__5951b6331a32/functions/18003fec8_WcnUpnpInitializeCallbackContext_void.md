# WcnUpnpInitializeCallbackContext(void)

- ea: `0x18003fec8`
- end: `0x18003ff4f`
- name: `?WcnUpnpInitializeCallbackContext@@YAJXZ`
- size: `135`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003dfb0`
- `0x18003f2c0`

## callees

- `0x180004f78`
- `0x18003fec8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003fefa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003fefa`

## pseudocode

```c
__int64 WcnUpnpInitializeCallbackContext(void)
{
  HRESULT Instance; // ebx

  Instance = 0;
  if ( g_WcnUpnpCallbackContextRefCnt
    || (Instance = CoCreateInstance(
                     &CLSID_ContextSwitcher,
                     0,
                     1u,
                     &GUID_000001da_0000_0000_c000_000000000046,
                     &g_pWcnUpnpCallbackContext),
        Instance >= 0) )
  {
    ++g_WcnUpnpCallbackContextRefCnt;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids,
      (unsigned int)Instance);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003fec8  push    rbx
0x18003feca  sub     rsp, 30h
0x18003fece  mov     eax, cs:?g_WcnUpnpCallbackContextRefCnt@@3JC; long volatile g_WcnUpnpCallbackContextRefCnt
0x18003fed4  xor     ebx, ebx
0x18003fed6  test    eax, eax
0x18003fed8  jnz     short loc_18003FF39
0x18003feda  lea     rax, ?g_pWcnUpnpCallbackContext@@3PEAUIContextCallback@@EA; IContextCallback * g_pWcnUpnpCallbackContext
0x18003fee1  xor     edx, edx; pUnkOuter
0x18003fee3  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x18003feea  mov     [rsp+38h+ppv], rax; ppv
0x18003feef  lea     r8d, [rbx+1]; dwClsContext
0x18003fef3  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18003fefa  call    cs:__imp_CoCreateInstance
0x18003ff00  mov     ebx, eax
0x18003ff02  test    eax, eax
0x18003ff04  jns     short loc_18003FF39
0x18003ff06  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ff0d  lea     rax, WPP_GLOBAL_Control
0x18003ff14  cmp     rcx, rax
0x18003ff17  jz      short loc_18003FF47
0x18003ff19  cmp     byte ptr [rcx+19h], 2
0x18003ff1d  jb      short loc_18003FF47
0x18003ff1f  mov     rcx, [rcx+10h]
0x18003ff23  lea     r8, WPP_0871ecebbedb34bb0cd06cc596f98bf3_Traceguids
0x18003ff2a  mov     edx, 25h ; '%'
0x18003ff2f  mov     r9d, ebx
0x18003ff32  call    WPP_SF_d
0x18003ff37  jmp     short loc_18003FF47
0x18003ff39  mov     eax, cs:?g_WcnUpnpCallbackContextRefCnt@@3JC; long volatile g_WcnUpnpCallbackContextRefCnt
0x18003ff3f  inc     eax
0x18003ff41  mov     cs:?g_WcnUpnpCallbackContextRefCnt@@3JC, eax; long volatile g_WcnUpnpCallbackContextRefCnt
0x18003ff47  mov     eax, ebx
0x18003ff49  add     rsp, 30h
0x18003ff4d  pop     rbx
0x18003ff4e  retn
```
