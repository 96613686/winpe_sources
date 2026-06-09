# CWcnPageTemplate<CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,903,972,0>::FormatPageTitleWithSsid(_DOT11_SSID *,uint,uint)

- ea: `0x18000f4f8`
- end: `0x18000f599`
- name: `?FormatPageTitleWithSsid@?$CWcnPageTemplate@VCWcnPageTransfer@@$1?CLSID_WcnPageTransfer@@3U_GUID@@B$0DIH@$0DMM@$0A@@@QEAAJPEAU_DOT11_SSID@@II@Z`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f5a0`

## callees

- `0x180001820`
- `0x180002294`
- `0x18000f438`
- `0x18000f4f8`

## import_xrefs

- `wlanapi!WlanUtf8SsidToDisplayName` at `0x18000f550`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x18000f550`

## pseudocode

```c
__int64 __fastcall CWcnPageTemplate<CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,903,972,0>::FormatPageTitleWithSsid(
        __int64 a1,
        __int64 a2)
{
  int v5[4]; // [rsp+20h] [rbp-B8h] BYREF
  __int16 v6; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v7[142]; // [rsp+32h] [rbp-A6h] BYREF

  v6 = 0;
  memset_0(v7, 0, 0x80u);
  v5[0] = 65;
  if ( (unsigned int)WlanUtf8SsidToDisplayName(a2, 1, &v6, v5) )
    return CWcnPageTemplate<CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,903,972,0>::FormatPageTitle(a1, 10810);
  else
    return CWcnPageTemplate<CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,903,972,0>::FormatPageTitle(a1, 972);
}

```

## disassembly

```asm
0x18000f4f8  mov     [rsp+arg_10], rbx
0x18000f4fd  push    rdi
0x18000f4fe  sub     rsp, 0D0h
0x18000f505  mov     rax, cs:__security_cookie
0x18000f50c  xor     rax, rsp
0x18000f50f  mov     [rsp+0D8h+var_18], rax
0x18000f517  mov     rbx, rdx
0x18000f51a  mov     rdi, rcx
0x18000f51d  xor     eax, eax
0x18000f51f  lea     rcx, [rsp+0D8h+var_A6]; void *
0x18000f524  xor     edx, edx; Val
0x18000f526  mov     [rsp+0D8h+var_A8], ax
0x18000f52b  mov     r8d, 80h; Size
0x18000f531  call    memset_0
0x18000f536  lea     r9, [rsp+0D8h+var_B8]
0x18000f53b  mov     [rsp+0D8h+var_B8], 41h ; 'A'
0x18000f543  lea     r8, [rsp+0D8h+var_A8]
0x18000f548  mov     edx, 1
0x18000f54d  mov     rcx, rbx
0x18000f550  call    cs:__imp_WlanUtf8SsidToDisplayName
0x18000f556  mov     rcx, rdi
0x18000f559  test    eax, eax
0x18000f55b  jnz     short loc_18000F56E
0x18000f55d  lea     r8, [rsp+0D8h+var_A8]
0x18000f562  mov     edx, 3CCh
0x18000f567  call    ?FormatPageTitle@?$CWcnPageTemplate@VCWcnPageTransfer@@$1?CLSID_WcnPageTransfer@@3U_GUID@@B$0DIH@$0DMM@$0A@@@QEAAJIZZ; CWcnPageTemplate<CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,903,972,0>::FormatPageTitle(uint,...)
0x18000f56c  jmp     short loc_18000F578
0x18000f56e  mov     edx, 2A3Ah
0x18000f573  call    ?FormatPageTitle@?$CWcnPageTemplate@VCWcnPageTransfer@@$1?CLSID_WcnPageTransfer@@3U_GUID@@B$0DIH@$0DMM@$0A@@@QEAAJIZZ; CWcnPageTemplate<CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,903,972,0>::FormatPageTitle(uint,...)
0x18000f578  mov     rcx, [rsp+0D8h+var_18]
0x18000f580  xor     rcx, rsp; StackCookie
0x18000f583  call    __security_check_cookie
0x18000f588  mov     rbx, [rsp+0D8h+arg_10]
0x18000f590  add     rsp, 0D0h
0x18000f597  pop     rdi
0x18000f598  retn
```
