# CInternetTime::SetAssertiveLiveRegion(HWND__ *)

- ea: `0x180014dd4`
- end: `0x180014eb5`
- name: `?SetAssertiveLiveRegion@CInternetTime@@CAXPEAUHWND__@@@Z`
- size: `225`
- prototype: `void __fastcall(HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180015ed4`

## callees

- `0x180014dd4`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180014e36`
- `OLEAUT32!__imp_VariantInit` at `0x180014e36`
- `OLEAUT32!__imp_VariantClear` at `0x180014e9a`
- `OLEAUT32!__imp_VariantClear` at `0x180014e9a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014e1b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014e1b`

## pseudocode

```c
void __fastcall CInternetTime::SetAssertiveLiveRegion(HWND a1)
{
  struct IAccPropServicesVtbl *lpVtbl; // rax
  HRESULT (__stdcall *SetHwndProp)(IAccPropServices *, HWND, DWORD, DWORD, MSAAPROPID, VARIANT); // rax
  GUID v4; // [rsp+48h] [rbp+7h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp+17h] BYREF
  __int128 v6; // [rsp+78h] [rbp+37h] BYREF
  IRecordInfo *pRecInfo; // [rsp+88h] [rbp+47h]

  if ( g_pAccPropServices
    || CoCreateInstance(
         &CLSID_AccPropServices,
         0,
         3u,
         &GUID_6e26e776_04f0_495d_80e4_3330352e3169,
         (LPVOID *)&g_pAccPropServices) >= 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    pvarg.vt = 3;
    pvarg.lVal = 1;
    lpVtbl = g_pAccPropServices->lpVtbl;
    v6 = *(_OWORD *)&pvarg.vt;
    SetHwndProp = lpVtbl->SetHwndProp;
    pRecInfo = pvarg.pRecInfo;
    v4 = LiveSetting_Property_GUID;
    ((void (__fastcall *)(struct IAccPropServices *, HWND, __int64, _QWORD, GUID *, __int128 *))SetHwndProp)(
      g_pAccPropServices,
      a1,
      4294967292LL,
      0,
      &v4,
      &v6);
    VariantClear(&pvarg);
  }
}

```

## disassembly

```asm
0x180014dd4  mov     r11, rsp
0x180014dd7  mov     [r11+8], rbx
0x180014ddb  mov     [r11+10h], rdi
0x180014ddf  push    rbp
0x180014de0  lea     rbp, [r11-5Fh]
0x180014de4  sub     rsp, 90h
0x180014deb  cmp     cs:?g_pAccPropServices@@3PEAUIAccPropServices@@EA, 0; IAccPropServices * g_pAccPropServices
0x180014df3  mov     rbx, rcx
0x180014df6  mov     edi, 3
0x180014dfb  jnz     short loc_180014E25
0x180014dfd  lea     rax, ?g_pAccPropServices@@3PEAUIAccPropServices@@EA; IAccPropServices * g_pAccPropServices
0x180014e04  mov     r8d, edi; dwClsContext
0x180014e07  lea     r9, _GUID_6e26e776_04f0_495d_80e4_3330352e3169; riid
0x180014e0e  mov     [r11-78h], rax
0x180014e12  xor     edx, edx; pUnkOuter
0x180014e14  lea     rcx, CLSID_AccPropServices; rclsid
0x180014e1b  call    cs:__imp_CoCreateInstance
0x180014e21  test    eax, eax
0x180014e23  js      short loc_180014EA0
0x180014e25  xorps   xmm0, xmm0
0x180014e28  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180014e2c  xor     eax, eax
0x180014e2e  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180014e32  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180014e36  call    cs:__imp_VariantInit
0x180014e3c  mov     rcx, cs:?g_pAccPropServices@@3PEAUIAccPropServices@@EA; IAccPropServices * g_pAccPropServices
0x180014e43  lea     rdx, [rbp+57h+var_20]
0x180014e47  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180014e4c  xor     r9d, r9d
0x180014e4f  mov     [rsp+90h+var_68], rdx
0x180014e54  mov     r8d, 0FFFFFFFCh
0x180014e5a  mov     word ptr [rbp+57h+pvarg], di
0x180014e5e  lea     rdx, [rbp+57h+var_50]
0x180014e62  mov     dword ptr [rbp+57h+pvarg+8], 1
0x180014e69  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180014e6d  mov     rax, [rcx]
0x180014e70  mov     [rsp+90h+var_70], rdx
0x180014e75  mov     rdx, rbx
0x180014e78  movaps  [rbp+57h+var_20], xmm0
0x180014e7c  movups  xmm0, xmmword ptr cs:LiveSetting_Property_GUID.Data1
0x180014e83  mov     rax, [rax+30h]
0x180014e87  movsd   [rbp+57h+var_10], xmm1
0x180014e8c  movdqu  [rbp+57h+var_50], xmm0
0x180014e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e96  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180014e9a  call    cs:__imp_VariantClear
0x180014ea0  lea     r11, [rsp+90h+var_s0]
0x180014ea8  mov     rbx, [r11+10h]
0x180014eac  mov     rdi, [r11+18h]
0x180014eb0  mov     rsp, r11
0x180014eb3  pop     rbp
0x180014eb4  retn
```
