# CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::FormatPageTitleWithSsid(_DOT11_SSID *,uint,uint)

- ea: `0x1800184dc`
- end: `0x18001857d`
- name: `?FormatPageTitleWithSsid@?$CWcnPageTemplate@VCWcnPageFinished@@$1?CLSID_WcnPageFinished@@3U_GUID@@B$0CAA@$0NAL@$0A@@@QEAAJPEAU_DOT11_SSID@@II@Z`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800187c0`

## callees

- `0x180001820`
- `0x180002294`
- `0x18000f438`
- `0x1800184dc`

## import_xrefs

- `wlanapi!WlanUtf8SsidToDisplayName` at `0x180018534`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x180018534`

## pseudocode

```c
__int64 __fastcall CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::FormatPageTitleWithSsid(
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
    return CWcnPageTemplate<CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,903,972,0>::FormatPageTitle(a1, 10811);
  else
    return CWcnPageTemplate<CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,903,972,0>::FormatPageTitle(a1, 3339);
}

```

## disassembly

```asm
0x1800184dc  mov     [rsp+arg_10], rbx
0x1800184e1  push    rdi
0x1800184e2  sub     rsp, 0D0h
0x1800184e9  mov     rax, cs:__security_cookie
0x1800184f0  xor     rax, rsp
0x1800184f3  mov     [rsp+0D8h+var_18], rax
0x1800184fb  mov     rbx, rdx
0x1800184fe  mov     rdi, rcx
0x180018501  xor     eax, eax
0x180018503  lea     rcx, [rsp+0D8h+var_A6]; void *
0x180018508  xor     edx, edx; Val
0x18001850a  mov     [rsp+0D8h+var_A8], ax
0x18001850f  mov     r8d, 80h; Size
0x180018515  call    memset_0
0x18001851a  lea     r9, [rsp+0D8h+var_B8]
0x18001851f  mov     [rsp+0D8h+var_B8], 41h ; 'A'
0x180018527  lea     r8, [rsp+0D8h+var_A8]
0x18001852c  mov     edx, 1
0x180018531  mov     rcx, rbx
0x180018534  call    cs:__imp_WlanUtf8SsidToDisplayName
0x18001853a  mov     rcx, rdi
0x18001853d  test    eax, eax
0x18001853f  jnz     short loc_180018552
0x180018541  lea     r8, [rsp+0D8h+var_A8]
0x180018546  mov     edx, 0D0Bh
0x18001854b  call    ?FormatPageTitle@?$CWcnPageTemplate@VCWcnPageTransfer@@$1?CLSID_WcnPageTransfer@@3U_GUID@@B$0DIH@$0DMM@$0A@@@QEAAJIZZ; CWcnPageTemplate<CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,903,972,0>::FormatPageTitle(uint,...)
0x180018550  jmp     short loc_18001855C
0x180018552  mov     edx, 2A3Bh
0x180018557  call    ?FormatPageTitle@?$CWcnPageTemplate@VCWcnPageTransfer@@$1?CLSID_WcnPageTransfer@@3U_GUID@@B$0DIH@$0DMM@$0A@@@QEAAJIZZ; CWcnPageTemplate<CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,903,972,0>::FormatPageTitle(uint,...)
0x18001855c  mov     rcx, [rsp+0D8h+var_18]
0x180018564  xor     rcx, rsp; StackCookie
0x180018567  call    __security_check_cookie
0x18001856c  mov     rbx, [rsp+0D8h+arg_10]
0x180018574  add     rsp, 0D0h
0x18001857b  pop     rdi
0x18001857c  retn
```
