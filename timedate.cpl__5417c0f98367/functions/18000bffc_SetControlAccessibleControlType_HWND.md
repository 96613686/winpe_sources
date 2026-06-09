# SetControlAccessibleControlType(HWND__ *)

- ea: `0x18000bffc`
- end: `0x18000c124`
- name: `?SetControlAccessibleControlType@@YAXPEAUHWND__@@@Z`
- size: `296`
- prototype: `void __fastcall(HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000c12c`

## callees

- `0x18000bffc`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000c062`
- `OLEAUT32!__imp_VariantInit` at `0x18000c062`
- `OLEAUT32!__imp_VariantClear` at `0x18000c109`
- `OLEAUT32!__imp_VariantClear` at `0x18000c109`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c043`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c043`

## pseudocode

```c
void __fastcall SetControlAccessibleControlType(HWND a1)
{
  struct IAccPropServicesVtbl *lpVtbl; // rax
  HRESULT (__stdcall *SetHwndProp)(IAccPropServices *, HWND, DWORD, DWORD, MSAAPROPID, VARIANT); // rax
  struct IAccPropServicesVtbl *v4; // rax
  GUID v5; // [rsp+48h] [rbp+7h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp+17h] BYREF
  __int128 v7; // [rsp+78h] [rbp+37h] BYREF
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
    pvarg.lVal = 50004;
    lpVtbl = g_pAccPropServices->lpVtbl;
    v7 = *(_OWORD *)&pvarg.vt;
    SetHwndProp = lpVtbl->SetHwndProp;
    pRecInfo = pvarg.pRecInfo;
    v5 = ControlType_Property_GUID;
    if ( ((int (__fastcall *)(struct IAccPropServices *, HWND, __int64, _QWORD, GUID *, __int128 *))SetHwndProp)(
           g_pAccPropServices,
           a1,
           4294967292LL,
           0,
           &v5,
           &v7) >= 0 )
    {
      v4 = g_pAccPropServices->lpVtbl;
      v5 = LocalizedControlType_Property_GUID;
      ((void (__fastcall *)(struct IAccPropServices *, HWND, __int64, _QWORD, GUID *, const wchar_t *))v4->SetHwndPropStr)(
        g_pAccPropServices,
        a1,
        4294967292LL,
        0,
        &v5,
        L"edit");
    }
    VariantClear(&pvarg);
  }
}

```

## disassembly

```asm
0x18000bffc  mov     r11, rsp
0x18000bfff  mov     [r11+8], rbx
0x18000c003  mov     [r11+10h], rdi
0x18000c007  push    rbp
0x18000c008  lea     rbp, [r11-5Fh]
0x18000c00c  sub     rsp, 90h
0x18000c013  cmp     cs:?g_pAccPropServices@@3PEAUIAccPropServices@@EA, 0; IAccPropServices * g_pAccPropServices
0x18000c01b  mov     rbx, rcx
0x18000c01e  mov     edi, 3
0x18000c023  jnz     short loc_18000C051
0x18000c025  lea     rax, ?g_pAccPropServices@@3PEAUIAccPropServices@@EA; IAccPropServices * g_pAccPropServices
0x18000c02c  mov     r8d, edi; dwClsContext
0x18000c02f  lea     r9, _GUID_6e26e776_04f0_495d_80e4_3330352e3169; riid
0x18000c036  mov     [r11-78h], rax
0x18000c03a  xor     edx, edx; pUnkOuter
0x18000c03c  lea     rcx, CLSID_AccPropServices; rclsid
0x18000c043  call    cs:__imp_CoCreateInstance
0x18000c049  test    eax, eax
0x18000c04b  js      loc_18000C10F
0x18000c051  xorps   xmm0, xmm0
0x18000c054  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000c058  xor     eax, eax
0x18000c05a  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18000c05e  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18000c062  call    cs:__imp_VariantInit
0x18000c068  mov     rcx, cs:?g_pAccPropServices@@3PEAUIAccPropServices@@EA; IAccPropServices * g_pAccPropServices
0x18000c06f  lea     rdx, [rbp+57h+var_20]
0x18000c073  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18000c078  xor     r9d, r9d
0x18000c07b  mov     word ptr [rbp+57h+pvarg], di
0x18000c07f  mov     edi, 0FFFFFFFCh
0x18000c084  mov     [rsp+90h+var_68], rdx
0x18000c089  mov     r8d, edi
0x18000c08c  mov     dword ptr [rbp+57h+pvarg+8], 0C354h
0x18000c093  lea     rdx, [rbp+57h+var_50]
0x18000c097  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18000c09b  mov     rax, [rcx]
0x18000c09e  mov     [rsp+90h+var_70], rdx
0x18000c0a3  mov     rdx, rbx
0x18000c0a6  movaps  [rbp+57h+var_20], xmm0
0x18000c0aa  movups  xmm0, xmmword ptr cs:ControlType_Property_GUID.Data1
0x18000c0b1  mov     rax, [rax+30h]
0x18000c0b5  movsd   [rbp+57h+var_10], xmm1
0x18000c0ba  movdqu  [rbp+57h+var_50], xmm0
0x18000c0bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0c4  test    eax, eax
0x18000c0c6  js      short loc_18000C105
0x18000c0c8  mov     rcx, cs:?g_pAccPropServices@@3PEAUIAccPropServices@@EA; IAccPropServices * g_pAccPropServices
0x18000c0cf  lea     rdx, aEdit_0; "edit"
0x18000c0d6  movups  xmm0, xmmword ptr cs:LocalizedControlType_Property_GUID.Data1
0x18000c0dd  mov     [rsp+90h+var_68], rdx
0x18000c0e2  xor     r9d, r9d
0x18000c0e5  lea     rdx, [rbp+57h+var_50]
0x18000c0e9  mov     r8d, edi
0x18000c0ec  mov     rax, [rcx]
0x18000c0ef  mov     [rsp+90h+var_70], rdx
0x18000c0f4  mov     rdx, rbx
0x18000c0f7  movdqu  [rbp+57h+var_50], xmm0
0x18000c0fc  mov     rax, [rax+38h]
0x18000c100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c105  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000c109  call    cs:__imp_VariantClear
0x18000c10f  lea     r11, [rsp+90h+var_s0]
0x18000c117  mov     rbx, [r11+10h]
0x18000c11b  mov     rdi, [r11+18h]
0x18000c11f  mov     rsp, r11
0x18000c122  pop     rbp
0x18000c123  retn
```
