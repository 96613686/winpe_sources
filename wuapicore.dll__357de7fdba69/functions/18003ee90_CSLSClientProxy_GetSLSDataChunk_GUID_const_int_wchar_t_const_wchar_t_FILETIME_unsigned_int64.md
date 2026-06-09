# CSLSClientProxy::GetSLSDataChunk(_GUID const &,int,wchar_t const *,wchar_t * *,_FILETIME *,unsigned __int64 *)

- ea: `0x18003ee90`
- end: `0x18003f2fd`
- name: `?GetSLSDataChunk@CSLSClientProxy@@UEAAJAEBU_GUID@@HPEB_WPEAPEA_WPEAU_FILETIME@@PEA_K@Z`
- size: `1133`
- prototype: `int(CSLSClientProxy *__hidden this, const struct _GUID *, int, const wchar_t *, wchar_t **, struct _FILETIME *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180006ac4`
- `0x1800220b0`
- `0x18002de68`
- `0x18003eb78`
- `0x18003ee90`
- `0x180081b3c`
- `0x18009b050`
- `0x1800a1960`
- `0x1800a19e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18003efc4`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18003efc4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f00f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f00f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f2b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f2c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f2b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f2c1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18003ef77`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18003ef77`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003f20a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003f20a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f0df`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f177`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f223`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f2ce`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f0df`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f177`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f223`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f2ce`
- `OLEAUT32!__imp_SysStringLen` at `0x18003f19d`
- `OLEAUT32!__imp_SysStringLen` at `0x18003f19d`

## string_xrefs

- `0x18003ef5b`: `C:\__w\1\s\src\Client\comapi\SLSClientProxy.cpp`
- `0x18003f1f6`: `C:\__w\1\s\src\Client\comapi\SLSClientProxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=81
__int64 __fastcall CSLSClientProxy::GetSLSDataChunk(
        CSLSClientProxy *this,
        const struct _GUID *a2,
        int a3,
        const wchar_t *a4,
        wchar_t **a5,
        struct _FILETIME *a6,
        unsigned __int64 *a7)
{
  __int64 v8; // r8
  OLECHAR *v9; // r14
  wchar_t *v10; // rbx
  __int64 v11; // rdx
  HRESULT SLSData; // edi
  SIZE_T v13; // rdi
  HGLOBAL v14; // rax
  void *v15; // rsi
  __int64 v16; // rdx
  __int64 v17; // rdi
  unsigned int (__fastcall *v18)(__int64, OLECHAR *, __int64 *); // r15
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, BSTR *); // r15
  UINT v21; // eax
  bool v22; // zf
  UINT v23; // eax
  unsigned __int64 v24; // r15
  wchar_t *v25; // rax
  void **ppv; // [rsp+20h] [rbp-61h]
  OLECHAR *v28; // [rsp+40h] [rbp-41h] BYREF
  LPVOID v29; // [rsp+48h] [rbp-39h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-31h] BYREF
  int v31; // [rsp+58h] [rbp-29h] BYREF
  __int64 v32; // [rsp+60h] [rbp-21h] BYREF
  __int64 v33; // [rsp+68h] [rbp-19h] BYREF
  __int64 v34; // [rsp+70h] [rbp-11h] BYREF
  LPSTREAM ppstm; // [rsp+78h] [rbp-9h] BYREF
  void *Src; // [rsp+80h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]

  v8 = (unsigned int)(a3 != 0) + 2;
  v9 = 0;
  v28 = 0;
  v31 = 0;
  Src = 0;
  v10 = 0;
  ppstm = 0;
  v29 = 0;
  v34 = 0;
  v33 = 0;
  v32 = 0;
  bstrString = 0;
  if ( !a4 )
  {
    v11 = 120;
LABEL_7:
    SLSData = -2147467261;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SLSClientProxy.cpp",
      (const char *)(unsigned int)SLSData,
      (int)ppv);
    goto LABEL_49;
  }
  if ( !a5 )
  {
    v11 = 121;
    goto LABEL_7;
  }
  if ( !a6 )
  {
    v11 = 122;
    goto LABEL_7;
  }
  *a5 = 0;
  ppv = &Src;
  SLSData = CSLSClientProxy::GetSLSData(a7, a2, v8, &v31);
  if ( SLSData < 0 )
  {
    v11 = 131;
    goto LABEL_10;
  }
  v13 = (unsigned int)(v31 - 1);
  v14 = GlobalAlloc(0, v13);
  v15 = v14;
  if ( v14 )
  {
    memmove(v14, Src, v13);
    if ( ppstm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    SLSData = CreateStreamOnHGlobal(v15, 1, &ppstm);
    if ( SLSData >= 0 )
    {
      v15 = 0;
      if ( v29 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
      SLSData = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60, &v29);
      if ( SLSData >= 0 )
      {
        (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v29 + 576LL))(v29, 0xFFFFFFFFLL);
        if ( v34 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        SLSData = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v29)(
                    v29,
                    &GUID_00000109_0000_0000_c000_000000000046,
                    &v34);
        if ( SLSData >= 0 )
        {
          SLSData = (*(__int64 (__fastcall **)(__int64, LPSTREAM))(*(_QWORD *)v34 + 40LL))(v34, ppstm);
          if ( SLSData >= 0 )
          {
            if ( v33 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
            SLSData = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v29)(
                        v29,
                        &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
                        &v33);
            if ( SLSData >= 0 )
            {
              SysFreeString(0);
              SLSData = CSusBSTR::Append((CSusBSTR *)&v28, a4);
              if ( SLSData >= 0 )
              {
                v17 = v33;
                v18 = *(unsigned int (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v33 + 296LL);
                if ( v32 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                v9 = v28;
                if ( v18(v17, v28, &v32) )
                {
                  SLSData = -2147023728;
                  v16 = 163;
                }
                else
                {
                  v19 = v32;
                  if ( v32 )
                  {
                    v20 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v32 + 208LL);
                    SysFreeString(bstrString);
                    SLSData = v20(v19, &bstrString);
                    if ( SLSData >= 0 )
                    {
                      v21 = SysStringLen(bstrString);
                      v22 = v21 == -1;
                      v23 = v21 + 1;
                      v24 = v23;
                      if ( v22
                        || (v10 = (wchar_t *)SafeSusComAllocArray(v23, 2u), SLSData = v10 == 0 ? 0x8007000E : 0, v10) )
                      {
                        SLSData = StringCchCopyW(v10, v24, bstrString);
                        if ( SLSData >= 0 )
                        {
                          v25 = v10;
                          v10 = 0;
                          *a5 = v25;
                          SLSData = 0;
                          goto LABEL_49;
                        }
                        v16 = 171;
                      }
                      else
                      {
                        v16 = 170;
                      }
                    }
                    else
                    {
                      v16 = 166;
                    }
                  }
                  else
                  {
                    SLSData = -2147023728;
                    v16 = 165;
                  }
                }
              }
              else
              {
                v16 = 159;
                v9 = v28;
              }
            }
            else
            {
              v16 = 158;
            }
          }
          else
          {
            v16 = 157;
          }
        }
        else
        {
          v16 = 156;
        }
      }
      else
      {
        v16 = 152;
      }
    }
    else
    {
      v16 = 145;
    }
  }
  else
  {
    SLSData = -2147024882;
    v16 = 140;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SLSClientProxy.cpp",
    (const char *)(unsigned int)SLSData,
    (int)ppv);
  if ( v15 )
    GlobalFree(v15);
LABEL_49:
  SysFreeString(bstrString);
  bstrString = 0;
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
  }
  if ( v10 )
    CoTaskMemFree(v10);
  if ( Src )
  {
    CoTaskMemFree(Src);
    Src = 0;
  }
  SysFreeString(v9);
  return (unsigned int)SLSData;
}

```

## disassembly

```asm
0x18003ee90  mov     [rsp-8+arg_0], rbx
0x18003ee95  push    rbp
0x18003ee96  push    rsi
0x18003ee97  push    rdi
0x18003ee98  push    r12
0x18003ee9a  push    r13
0x18003ee9c  push    r14
0x18003ee9e  push    r15
0x18003eea0  lea     rbp, [rsp-0Fh]
0x18003eea5  sub     rsp, 90h
0x18003eeac  mov     rax, cs:__security_cookie
0x18003eeb3  xor     rax, rsp
0x18003eeb6  mov     [rbp+3Fh+var_38], rax
0x18003eeba  mov     r15, r9
0x18003eebd  mov     r12, [rbp+3Fh+arg_20]
0x18003eec1  mov     rax, [rbp+3Fh+arg_28]
0x18003eec5  mov     rcx, [rbp+3Fh+arg_30]
0x18003eec9  neg     r8d
0x18003eecc  sbb     r8d, r8d
0x18003eecf  neg     r8d
0x18003eed2  add     r8d, 2
0x18003eed6  xor     r13d, r13d
0x18003eed9  mov     r14d, r13d
0x18003eedc  mov     [rbp+3Fh+var_80], r13
0x18003eee0  mov     [rbp+3Fh+var_68], r13d
0x18003eee4  mov     [rbp+3Fh+Src], r13
0x18003eee8  mov     ebx, r13d
0x18003eeeb  mov     [rbp+3Fh+ppstm], r13
0x18003eeef  mov     [rbp+3Fh+var_78], r13
0x18003eef3  mov     [rbp+3Fh+var_50], r13
0x18003eef7  mov     [rbp+3Fh+var_58], r13
0x18003eefb  mov     [rbp+3Fh+var_60], r13
0x18003eeff  mov     [rbp+3Fh+bstrString], r13
0x18003ef03  test    r9, r9
0x18003ef06  jnz     short loc_18003EF0E
0x18003ef08  lea     edx, [r9+78h]
0x18003ef0c  jmp     short loc_18003EF22
0x18003ef0e  test    r12, r12
0x18003ef11  jnz     short loc_18003EF1A
0x18003ef13  lea     edx, [r12+79h]
0x18003ef18  jmp     short loc_18003EF22
0x18003ef1a  test    rax, rax
0x18003ef1d  jnz     short loc_18003EF29
0x18003ef1f  lea     edx, [rax+7Ah]
0x18003ef22  mov     edi, 80004003h
0x18003ef27  jmp     short loc_18003EF54
0x18003ef29  mov     [r12], r13
0x18003ef2d  mov     [rsp+0C0h+var_90], rcx
0x18003ef32  mov     [rsp+0C0h+var_98], rax
0x18003ef37  lea     rax, [rbp+3Fh+Src]
0x18003ef3b  mov     [rsp+0C0h+ppv], rax; int
0x18003ef40  lea     r9, [rbp+3Fh+var_68]
0x18003ef44  call    ?GetSLSData@CSLSClientProxy@@AEAAJAEBU_GUID@@W4tagSlsFlags@@PEAKPEAPEADPEAU_FILETIME@@PEA_K@Z; CSLSClientProxy::GetSLSData(_GUID const &,tagSlsFlags,ulong *,char * *,_FILETIME *,unsigned __int64 *)
0x18003ef49  mov     edi, eax
0x18003ef4b  test    eax, eax
0x18003ef4d  jns     short loc_18003EF6C
0x18003ef4f  mov     edx, 83h; void *
0x18003ef54  mov     rcx, [rbp+47h]; this
0x18003ef58  mov     r9d, edi; char *
0x18003ef5b  lea     r8, aCW1SSrcClientC_36; "C:\\__w\\1\\s\\src\\Client\\comapi\\SLS"...
0x18003ef62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ef67  jmp     loc_18003F21F
0x18003ef6c  mov     eax, [rbp+3Fh+var_68]
0x18003ef6f  dec     eax
0x18003ef71  mov     edi, eax
0x18003ef73  mov     edx, eax; dwBytes
0x18003ef75  xor     ecx, ecx; uFlags
0x18003ef77  call    cs:__imp_GlobalAlloc
0x18003ef7d  mov     rsi, rax
0x18003ef80  test    rax, rax
0x18003ef83  jnz     short loc_18003EF94
0x18003ef85  mov     edi, 8007000Eh
0x18003ef8a  mov     edx, 8Ch
0x18003ef8f  jmp     loc_18003F1EF
0x18003ef94  mov     r8, rdi; Size
0x18003ef97  mov     rdx, [rbp+3Fh+Src]; Src
0x18003ef9b  mov     rcx, rsi; void *
0x18003ef9e  call    memmove
0x18003efa3  mov     rcx, [rbp+3Fh+ppstm]
0x18003efa7  test    rcx, rcx
0x18003efaa  jz      short loc_18003EFB8
0x18003efac  mov     rax, [rcx]
0x18003efaf  mov     rax, [rax+10h]
0x18003efb3  call    _guard_dispatch_icall
0x18003efb8  lea     r8, [rbp+3Fh+ppstm]; ppstm
0x18003efbc  mov     edx, 1; fDeleteOnRelease
0x18003efc1  mov     rcx, rsi; hGlobal
0x18003efc4  call    cs:__imp_CreateStreamOnHGlobal
0x18003efca  mov     edi, eax
0x18003efcc  test    eax, eax
0x18003efce  jns     short loc_18003EFDA
0x18003efd0  mov     edx, 91h
0x18003efd5  jmp     loc_18003F1EF
0x18003efda  mov     rsi, r13
0x18003efdd  mov     rcx, [rbp+3Fh+var_78]
0x18003efe1  test    rcx, rcx
0x18003efe4  jz      short loc_18003EFF2
0x18003efe6  mov     rax, [rcx]
0x18003efe9  mov     rax, [rax+10h]
0x18003efed  call    _guard_dispatch_icall
0x18003eff2  lea     rax, [rbp+3Fh+var_78]
0x18003eff6  mov     [rsp+0C0h+ppv], rax; int
0x18003effb  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x18003f002  xor     edx, edx; pUnkOuter
0x18003f004  lea     r8d, [rdx+1]; dwClsContext
0x18003f008  lea     rcx, CLSID_DOMDocument60; rclsid
0x18003f00f  call    cs:__imp_CoCreateInstance
0x18003f015  mov     edi, eax
0x18003f017  test    eax, eax
0x18003f019  jns     short loc_18003F025
0x18003f01b  mov     edx, 98h
0x18003f020  jmp     loc_18003F1EF
0x18003f025  or      edx, 0FFFFFFFFh
0x18003f028  mov     rcx, [rbp+3Fh+var_78]
0x18003f02c  mov     rax, [rcx]
0x18003f02f  mov     rax, [rax+240h]
0x18003f036  call    _guard_dispatch_icall
0x18003f03b  mov     rcx, [rbp+3Fh+var_50]
0x18003f03f  test    rcx, rcx
0x18003f042  jz      short loc_18003F050
0x18003f044  mov     rax, [rcx]
0x18003f047  mov     rax, [rax+10h]
0x18003f04b  call    _guard_dispatch_icall
0x18003f050  mov     rcx, [rbp+3Fh+var_78]
0x18003f054  mov     rax, [rcx]
0x18003f057  lea     r8, [rbp+3Fh+var_50]
0x18003f05b  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18003f062  mov     rax, [rax]
0x18003f065  call    _guard_dispatch_icall
0x18003f06a  mov     edi, eax
0x18003f06c  test    eax, eax
0x18003f06e  jns     short loc_18003F07A
0x18003f070  mov     edx, 9Ch
0x18003f075  jmp     loc_18003F1EF
0x18003f07a  mov     rcx, [rbp+3Fh+var_50]
0x18003f07e  mov     rax, [rcx]
0x18003f081  mov     rdx, [rbp+3Fh+ppstm]
0x18003f085  mov     rax, [rax+28h]
0x18003f089  call    _guard_dispatch_icall
0x18003f08e  mov     edi, eax
0x18003f090  test    eax, eax
0x18003f092  jns     short loc_18003F09E
0x18003f094  mov     edx, 9Dh
0x18003f099  jmp     loc_18003F1EF
0x18003f09e  mov     rcx, [rbp+3Fh+var_58]
0x18003f0a2  test    rcx, rcx
0x18003f0a5  jz      short loc_18003F0B3
0x18003f0a7  mov     rax, [rcx]
0x18003f0aa  mov     rax, [rax+10h]
0x18003f0ae  call    _guard_dispatch_icall
0x18003f0b3  mov     rcx, [rbp+3Fh+var_78]
0x18003f0b7  mov     rax, [rcx]
0x18003f0ba  lea     r8, [rbp+3Fh+var_58]
0x18003f0be  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x18003f0c5  mov     rax, [rax]
0x18003f0c8  call    _guard_dispatch_icall
0x18003f0cd  mov     edi, eax
0x18003f0cf  test    eax, eax
0x18003f0d1  jns     short loc_18003F0DD
0x18003f0d3  mov     edx, 9Eh
0x18003f0d8  jmp     loc_18003F1EF
0x18003f0dd  xor     ecx, ecx; bstrString
0x18003f0df  call    cs:__imp_SysFreeString
0x18003f0e5  mov     rdx, r15; wchar_t *
0x18003f0e8  lea     rcx, [rbp+3Fh+var_80]; this
0x18003f0ec  call    ?Append@CSusBSTR@@QEAAJPEB_W@Z; CSusBSTR::Append(wchar_t const *)
0x18003f0f1  mov     edi, eax
0x18003f0f3  test    eax, eax
0x18003f0f5  jns     short loc_18003F105
0x18003f0f7  mov     edx, 9Fh
0x18003f0fc  mov     r14, [rbp+3Fh+var_80]
0x18003f100  jmp     loc_18003F1EF
0x18003f105  mov     rdi, [rbp+3Fh+var_58]
0x18003f109  mov     rax, [rdi]
0x18003f10c  mov     r15, [rax+128h]
0x18003f113  mov     rcx, [rbp+3Fh+var_60]
0x18003f117  test    rcx, rcx
0x18003f11a  jz      short loc_18003F128
0x18003f11c  mov     rdx, [rcx]
0x18003f11f  mov     rax, [rdx+10h]
0x18003f123  call    _guard_dispatch_icall
0x18003f128  lea     r8, [rbp+3Fh+var_60]
0x18003f12c  mov     r14, [rbp+3Fh+var_80]
0x18003f130  mov     rdx, r14
0x18003f133  mov     rcx, rdi
0x18003f136  mov     rax, r15
0x18003f139  call    _guard_dispatch_icall
0x18003f13e  test    eax, eax
0x18003f140  jz      short loc_18003F151
0x18003f142  mov     edi, 80070490h
0x18003f147  mov     edx, 0A3h
0x18003f14c  jmp     loc_18003F1EF
0x18003f151  mov     rdi, [rbp+3Fh+var_60]
0x18003f155  test    rdi, rdi
0x18003f158  jnz     short loc_18003F169
0x18003f15a  mov     edi, 80070490h
0x18003f15f  mov     edx, 0A5h
0x18003f164  jmp     loc_18003F1EF
0x18003f169  mov     rax, [rdi]
0x18003f16c  mov     r15, [rax+0D0h]
0x18003f173  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x18003f177  call    cs:__imp_SysFreeString
0x18003f17d  lea     rdx, [rbp+3Fh+bstrString]
0x18003f181  mov     rcx, rdi
0x18003f184  mov     rax, r15
0x18003f187  call    _guard_dispatch_icall
0x18003f18c  mov     edi, eax
0x18003f18e  test    eax, eax
0x18003f190  jns     short loc_18003F199
0x18003f192  mov     edx, 0A6h
0x18003f197  jmp     short loc_18003F1EF
0x18003f199  mov     rcx, [rbp+3Fh+bstrString]; pbstr
0x18003f19d  call    cs:__imp_SysStringLen
0x18003f1a3  add     eax, 1
0x18003f1a6  mov     r15d, eax
0x18003f1a9  jz      short loc_18003F1D5
0x18003f1ab  mov     edx, 2; unsigned __int64
0x18003f1b0  mov     ecx, r15d; unsigned __int64
0x18003f1b3  call    ?SafeSusComAllocArray@@YAPEAX_K0@Z; SafeSusComAllocArray(unsigned __int64,unsigned __int64)
0x18003f1b8  mov     rbx, rax
0x18003f1bb  neg     rax
0x18003f1be  sbb     ecx, ecx
0x18003f1c0  not     ecx
0x18003f1c2  mov     edi, 8007000Eh
0x18003f1c7  and     edi, ecx
0x18003f1c9  test    rbx, rbx
0x18003f1cc  jnz     short loc_18003F1D5
0x18003f1ce  mov     edx, 0AAh
0x18003f1d3  jmp     short loc_18003F1EF
0x18003f1d5  mov     r8, [rbp+3Fh+bstrString]; wchar_t *
0x18003f1d9  mov     rdx, r15; unsigned __int64
0x18003f1dc  mov     rcx, rbx; wchar_t *
0x18003f1df  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003f1e4  mov     edi, eax
0x18003f1e6  test    eax, eax
0x18003f1e8  jns     short loc_18003F212
0x18003f1ea  mov     edx, 0ABh; void *
0x18003f1ef  mov     rcx, [rbp+47h]; this
0x18003f1f3  mov     r9d, edi; char *
0x18003f1f6  lea     r8, aCW1SSrcClientC_36; "C:\\__w\\1\\s\\src\\Client\\comapi\\SLS"...
0x18003f1fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f202  test    rsi, rsi
0x18003f205  jz      short loc_18003F21F
0x18003f207  mov     rcx, rsi; hMem
0x18003f20a  call    cs:__imp_GlobalFree
0x18003f210  jmp     short loc_18003F21F
0x18003f212  mov     rax, rbx
0x18003f215  mov     rbx, r13
0x18003f218  mov     [r12], rax
0x18003f21c  mov     edi, r13d
0x18003f21f  mov     rcx, [rbp+3Fh+bstrString]; bstrString
0x18003f223  call    cs:__imp_SysFreeString
0x18003f229  mov     [rbp+3Fh+bstrString], r13
0x18003f22d  mov     rcx, [rbp+3Fh+var_60]
0x18003f231  test    rcx, rcx
0x18003f234  jz      short loc_18003F246
0x18003f236  mov     rax, [rcx]
0x18003f239  mov     rax, [rax+10h]
0x18003f23d  call    _guard_dispatch_icall
0x18003f242  mov     [rbp+3Fh+var_60], r13
0x18003f246  mov     rcx, [rbp+3Fh+var_58]
0x18003f24a  test    rcx, rcx
0x18003f24d  jz      short loc_18003F25F
0x18003f24f  mov     rax, [rcx]
0x18003f252  mov     rax, [rax+10h]
0x18003f256  call    _guard_dispatch_icall
0x18003f25b  mov     [rbp+3Fh+var_58], r13
0x18003f25f  mov     rcx, [rbp+3Fh+var_50]
0x18003f263  test    rcx, rcx
0x18003f266  jz      short loc_18003F278
0x18003f268  mov     rax, [rcx]
0x18003f26b  mov     rax, [rax+10h]
0x18003f26f  call    _guard_dispatch_icall
0x18003f274  mov     [rbp+3Fh+var_50], r13
0x18003f278  mov     rcx, [rbp+3Fh+var_78]
0x18003f27c  test    rcx, rcx
0x18003f27f  jz      short loc_18003F291
0x18003f281  mov     rax, [rcx]
0x18003f284  mov     rax, [rax+10h]
0x18003f288  call    _guard_dispatch_icall
0x18003f28d  mov     [rbp+3Fh+var_78], r13
0x18003f291  mov     rcx, [rbp+3Fh+ppstm]
0x18003f295  test    rcx, rcx
0x18003f298  jz      short loc_18003F2AA
0x18003f29a  mov     rax, [rcx]
0x18003f29d  mov     rax, [rax+10h]
0x18003f2a1  call    _guard_dispatch_icall
0x18003f2a6  mov     [rbp+3Fh+ppstm], r13
0x18003f2aa  test    rbx, rbx
0x18003f2ad  jz      short loc_18003F2B8
0x18003f2af  mov     rcx, rbx; pv
0x18003f2b2  call    cs:__imp_CoTaskMemFree
0x18003f2b8  mov     rcx, [rbp+3Fh+Src]; pv
0x18003f2bc  test    rcx, rcx
0x18003f2bf  jz      short loc_18003F2CB
0x18003f2c1  call    cs:__imp_CoTaskMemFree
0x18003f2c7  mov     [rbp+3Fh+Src], r13
0x18003f2cb  mov     rcx, r14; bstrString
0x18003f2ce  call    cs:__imp_SysFreeString
0x18003f2d4  mov     eax, edi
  ... truncated ...
```
