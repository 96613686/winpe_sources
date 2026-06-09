# HrComposeEventBody(IUPnPAutomationProxy *,ulong,ushort * *,ushort * *,tagVARIANT *,ushort * *)

- ea: `0x180013cd0`
- end: `0x180014030`
- name: `?HrComposeEventBody@@YAJPEAUIUPnPAutomationProxy@@KPEAPEAG1PEAUtagVARIANT@@1@Z`
- size: `864`
- prototype: `__int64 __fastcall(struct IUPnPAutomationProxy *, unsigned int, unsigned __int16 **, unsigned __int16 **, struct tagVARIANT *, BSTR pbstr)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180035fd0`
- `0x180048170`

## callees

- `0x180013cd0`
- `0x180014038`
- `0x180014054`
- `0x1800141bc`
- `0x1800142e4`
- `0x180014550`
- `0x1800200f4`
- `0x18003a798`
- `0x18003b904`
- `0x180045b90`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013eb2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013fa4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013eb2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013fa4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180013dd3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180013f43`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180013dd3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180013f43`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013d25`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013d25`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180013dbc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180013dbc`
- `OLEAUT32!__imp_SysFreeString` at `0x180013fbb`
- `OLEAUT32!__imp_SysFreeString` at `0x180013fbb`
- `OLEAUT32!__imp_SysStringLen` at `0x180013f2f`
- `OLEAUT32!__imp_SysStringLen` at `0x180013f2f`

## string_xrefs

- `0x180013ff9`: `HrComposeEventBody`

## pseudocode

```c
__int64 __fastcall HrComposeEventBody(
        struct IUPnPAutomationProxy *a1,
        unsigned int a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        struct tagVARIANT *a5,
        BSTR pbstr)
{
  BSTR v6; // r14
  unsigned __int16 **v7; // rdi
  const unsigned __int16 *v9; // rdx
  HRESULT Instance; // ebx
  const unsigned __int16 *v11; // r8
  bool v12; // zf
  struct IUnknown *v13; // r12
  int v14; // esi
  __int64 v15; // rbx
  const wchar_t *v16; // rcx
  wchar_t *v17; // rdi
  size_t v18; // r8
  HRESULT v19; // eax
  size_t v20; // rdx
  size_t *v21; // r8
  struct IUnknown *v22; // r15
  IRecordInfo *pRecInfo; // xmm1_8
  __int64 v24; // rbx
  unsigned __int16 *v25; // rax
  unsigned __int16 *v26; // rdi
  struct IXMLDOMElement **v28; // [rsp+20h] [rbp-40h]
  struct IUnknown *v29; // [rsp+30h] [rbp-30h] BYREF
  struct IUnknown *v30; // [rsp+38h] [rbp-28h] BYREF
  struct tagVARIANT v31; // [rsp+40h] [rbp-20h] BYREF
  struct IUnknown *v32; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int16 **v33; // [rsp+B0h] [rbp+50h]
  unsigned __int16 **v34; // [rsp+B8h] [rbp+58h]

  v34 = a4;
  v33 = a3;
  v6 = pbstr;
  v7 = a3;
  v32 = 0;
  *(_QWORD *)pbstr = 0;
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, (LPVOID *)&v32);
  v12 = Instance == 0;
  if ( Instance >= 0 )
  {
    v29 = 0;
    Instance = HrAppendProcessingInstruction((struct IXMLDOMDocument *)v32, v9, v11);
    if ( Instance >= 0 )
    {
      Instance = HrCreateElement((struct IXMLDOMDocument *)v32, L"e:propertyset", (struct IXMLDOMNode **)&v29);
      if ( Instance >= 0 )
      {
        v13 = v29;
        v14 = 0;
        if ( a2 )
        {
          while ( Instance >= 0 )
          {
            v30 = 0;
            Instance = HrCreateElement((struct IXMLDOMDocument *)v32, L"e:property", (struct IXMLDOMNode **)&v30);
            if ( Instance >= 0 )
            {
              v29 = 0;
              v15 = lstrlenW(v7[v14]);
              v17 = (wchar_t *)malloc(2 * v15 + 2);
              if ( v17 )
              {
                v19 = StringValidateDestW(v16, v15 + 1, v18);
                v22 = v30;
                Instance = v19;
                if ( v19 < 0 )
                {
                  if ( v20 )
                    *v17 = 0;
                }
                else
                {
                  Instance = StringCopyWorkerW(v17, v20, v21, v33[v14], (size_t)v28);
                  if ( Instance >= 0 )
                  {
                    pRecInfo = a5[v14].pRecInfo;
                    *(_OWORD *)&v31.vt = *(_OWORD *)&a5[v14].vt;
                    v31.pRecInfo = pRecInfo;
                    Instance = HrCreateElementWithType(
                                 (struct IXMLDOMDocument *)v32,
                                 v17,
                                 v34[v14],
                                 &v31,
                                 (struct IXMLDOMElement **)&v29);
                    if ( Instance >= 0 )
                    {
                      ((void (__fastcall *)(struct IUnknown *, struct IUnknown *, _QWORD))v13->lpVtbl[7].QueryInterface)(
                        v13,
                        v22,
                        0);
                      Instance = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown *, _QWORD))v22->lpVtbl[7].QueryInterface)(
                                   v22,
                                   v29,
                                   0);
                      ReleaseObj(v29);
                    }
                  }
                }
                ReleaseObj(v22);
                free(v17);
              }
              else
              {
                Instance = -2147024882;
              }
              v7 = v33;
            }
            if ( ++v14 >= a2 )
            {
              if ( Instance < 0 )
                break;
              v6 = pbstr;
              goto LABEL_20;
            }
          }
        }
        else
        {
LABEL_20:
          Instance = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown *, _QWORD))v32->lpVtbl[7].QueryInterface)(
                       v32,
                       v13,
                       0);
          if ( Instance >= 0 )
          {
            pbstr = 0;
            Instance = ((__int64 (__fastcall *)(struct IUnknown *, BSTR *))v32->lpVtbl[11].AddRef)(v32, &pbstr);
            if ( Instance >= 0 )
            {
              v24 = SysStringLen(pbstr) + 1;
              v25 = (unsigned __int16 *)malloc(2 * v24);
              v26 = v25;
              if ( v25 )
              {
                Instance = StringCchCopyW(v25, (unsigned int)v24, pbstr);
                if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    27,
                    WPP_26899187c1a539900c7f96418485818e_Traceguids,
                    v26);
                if ( Instance < 0 )
                  free(v26);
                else
                  *(_QWORD *)v6 = v26;
              }
              else
              {
                Instance = -2147024882;
              }
              SysFreeString(pbstr);
            }
          }
        }
        ReleaseObj(v13);
      }
    }
    ReleaseObj(v32);
    v12 = Instance == 0;
  }
  if ( !v12 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      (unsigned int)WPP_26899187c1a539900c7f96418485818e_Traceguids,
      (unsigned int)"HrComposeEventBody",
      Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180013cd0  mov     r11, rsp
0x180013cd3  mov     [r11+10h], rbx
0x180013cd7  mov     [r11+20h], r9
0x180013cdb  mov     [r11+18h], r8
0x180013cdf  mov     [r11+8], rcx
0x180013ce3  push    rbp
0x180013ce4  push    rsi
0x180013ce5  push    rdi
0x180013ce6  push    r12
0x180013ce8  push    r13
0x180013cea  push    r14
0x180013cec  push    r15
0x180013cee  mov     rbp, rsp
0x180013cf1  sub     rsp, 60h
0x180013cf5  mov     r14, [rbp+pbstr]
0x180013cf9  lea     rax, [rbp+arg_0]
0x180013cfd  xor     r15d, r15d
0x180013d00  mov     [r11-78h], rax
0x180013d04  mov     rdi, r8
0x180013d07  mov     [rbp+arg_0], r15
0x180013d0b  mov     r13d, edx
0x180013d0e  lea     r9, IID_IXMLDOMDocument; riid
0x180013d15  xor     edx, edx; pUnkOuter
0x180013d17  mov     [r14], r15
0x180013d1a  lea     r8d, [r15+1]; dwClsContext
0x180013d1e  lea     rcx, CLSID_DOMDocument60; rclsid
0x180013d25  call    cs:__imp_CoCreateInstance
0x180013d2c  nop     dword ptr [rax+rax+00h]
0x180013d31  mov     ebx, eax
0x180013d33  lea     rax, WPP_GLOBAL_Control
0x180013d3a  test    ebx, ebx
0x180013d3c  js      loc_180013FE1
0x180013d42  mov     rcx, [rbp+arg_0]; struct IXMLDOMDocument *
0x180013d46  mov     [rbp+var_30], r15
0x180013d4a  call    ?HrAppendProcessingInstruction@@YAJPEAUIXMLDOMDocument@@PEBG1@Z; HrAppendProcessingInstruction(IXMLDOMDocument *,ushort const *,ushort const *)
0x180013d4f  mov     ebx, eax
0x180013d51  test    eax, eax
0x180013d53  js      loc_180013FCF
0x180013d59  mov     rcx, [rbp+arg_0]; struct IXMLDOMDocument *
0x180013d5d  lea     r8, [rbp+var_30]; struct IXMLDOMNode **
0x180013d61  lea     rdx, aEPropertyset; "e:propertyset"
0x180013d68  call    ?HrCreateElement@@YAJPEAUIXMLDOMDocument@@PEBGPEAPEAUIXMLDOMNode@@@Z; HrCreateElement(IXMLDOMDocument *,ushort const *,IXMLDOMNode * *)
0x180013d6d  mov     ebx, eax
0x180013d6f  test    eax, eax
0x180013d71  js      loc_180013FCF
0x180013d77  mov     r12, [rbp+var_30]
0x180013d7b  mov     esi, r15d
0x180013d7e  test    r13d, r13d
0x180013d81  jz      loc_180013EE3
0x180013d87  test    ebx, ebx
0x180013d89  js      loc_180013FC7
0x180013d8f  mov     rcx, [rbp+arg_0]; struct IXMLDOMDocument *
0x180013d93  lea     r8, [rbp+var_28]; struct IXMLDOMNode **
0x180013d97  lea     rdx, aEProperty; "e:property"
0x180013d9e  mov     [rbp+var_28], r15
0x180013da2  call    ?HrCreateElement@@YAJPEAUIXMLDOMDocument@@PEBGPEAPEAUIXMLDOMNode@@@Z; HrCreateElement(IXMLDOMDocument *,ushort const *,IXMLDOMNode * *)
0x180013da7  mov     ebx, eax
0x180013da9  test    eax, eax
0x180013dab  js      loc_180013ECC
0x180013db1  mov     r14d, esi
0x180013db4  mov     [rbp+var_30], r15
0x180013db8  mov     rcx, [rdi+r14*8]; lpString
0x180013dbc  call    cs:__imp_lstrlenW
0x180013dc3  nop     dword ptr [rax+rax+00h]
0x180013dc8  movsxd  rbx, eax
0x180013dcb  lea     rcx, ds:2[rbx*2]; Size
0x180013dd3  call    cs:__imp_malloc
0x180013dda  nop     dword ptr [rax+rax+00h]
0x180013ddf  mov     rdi, rax
0x180013de2  test    rax, rax
0x180013de5  jz      loc_180013EC3
0x180013deb  lea     rdx, [rbx+1]; cchDest
0x180013def  call    StringValidateDestW
0x180013df4  mov     r15, [rbp+var_28]
0x180013df8  mov     ebx, eax
0x180013dfa  test    eax, eax
0x180013dfc  js      loc_180013E9D
0x180013e02  mov     r9, [rbp+arg_10]
0x180013e06  mov     rcx, rdi; pszDest
0x180013e09  mov     r9, [r9+r14*8]; pszSrc
0x180013e0d  call    StringCopyWorkerW
0x180013e12  mov     ebx, eax
0x180013e14  test    eax, eax
0x180013e16  js      loc_180013EA7
0x180013e1c  mov     rcx, [rbp+arg_20]
0x180013e20  lea     rax, [r14+r14*2]
0x180013e24  lea     r9, [rbp+var_20]; struct tagVARIANT
0x180013e28  mov     rdx, rdi; unsigned __int16 *
0x180013e2b  movups  xmm0, xmmword ptr [rcx+rax*8]
0x180013e2f  movsd   xmm1, qword ptr [rcx+rax*8+10h]
0x180013e35  lea     rax, [rbp+var_30]
0x180013e39  mov     rcx, [rbp+arg_0]; struct IXMLDOMDocument *
0x180013e3d  mov     [rsp+60h+var_40], rax; struct IXMLDOMElement **
0x180013e42  mov     rax, [rbp+arg_18]
0x180013e46  movaps  xmmword ptr [rbp+var_20], xmm0
0x180013e4a  movsd   qword ptr [rbp+var_20+10h], xmm1
0x180013e4f  mov     r8, [rax+r14*8]; unsigned __int16 *
0x180013e53  call    ?HrCreateElementWithType@@YAJPEAUIXMLDOMDocument@@PEBG1UtagVARIANT@@PEAPEAUIXMLDOMElement@@@Z; HrCreateElementWithType(IXMLDOMDocument *,ushort const *,ushort const *,tagVARIANT,IXMLDOMElement * *)
0x180013e58  mov     ebx, eax
0x180013e5a  test    eax, eax
0x180013e5c  js      short loc_180013EA7
0x180013e5e  mov     rax, [r12]
0x180013e62  xor     r8d, r8d
0x180013e65  mov     rdx, r15
0x180013e68  mov     rcx, r12
0x180013e6b  mov     rax, [rax+0A8h]
0x180013e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e77  mov     rax, [r15]
0x180013e7a  xor     r8d, r8d
0x180013e7d  mov     rdx, [rbp+var_30]
0x180013e81  mov     rcx, r15
0x180013e84  mov     rax, [rax+0A8h]
0x180013e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e90  mov     rcx, [rbp+var_30]; struct IUnknown *
0x180013e94  mov     ebx, eax
0x180013e96  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180013e9b  jmp     short loc_180013EA7
0x180013e9d  test    rdx, rdx
0x180013ea0  jz      short loc_180013EA7
0x180013ea2  xor     eax, eax
0x180013ea4  mov     [rdi], ax
0x180013ea7  mov     rcx, r15; struct IUnknown *
0x180013eaa  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180013eaf  mov     rcx, rdi; Block
0x180013eb2  call    cs:__imp_free
0x180013eb9  nop     dword ptr [rax+rax+00h]
0x180013ebe  xor     r15d, r15d
0x180013ec1  jmp     short loc_180013EC8
0x180013ec3  mov     ebx, 8007000Eh
0x180013ec8  mov     rdi, [rbp+arg_10]
0x180013ecc  inc     esi
0x180013ece  cmp     esi, r13d
0x180013ed1  jb      loc_180013D87
0x180013ed7  test    ebx, ebx
0x180013ed9  js      loc_180013FC7
0x180013edf  mov     r14, [rbp+pbstr]
0x180013ee3  mov     rcx, [rbp+arg_0]
0x180013ee7  xor     r8d, r8d
0x180013eea  mov     rdx, r12
0x180013eed  mov     rax, [rcx]
0x180013ef0  mov     rax, [rax+0A8h]
0x180013ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013efc  mov     ebx, eax
0x180013efe  test    eax, eax
0x180013f00  js      loc_180013FC7
0x180013f06  mov     rcx, [rbp+arg_0]
0x180013f0a  lea     rdx, [rbp+pbstr]
0x180013f0e  mov     [rbp+pbstr], r15
0x180013f12  mov     rax, [rcx]
0x180013f15  mov     rax, [rax+110h]
0x180013f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f21  mov     ebx, eax
0x180013f23  test    eax, eax
0x180013f25  js      loc_180013FC7
0x180013f2b  mov     rcx, [rbp+pbstr]; pbstr
0x180013f2f  call    cs:__imp_SysStringLen
0x180013f36  nop     dword ptr [rax+rax+00h]
0x180013f3b  inc     eax
0x180013f3d  mov     ebx, eax
0x180013f3f  lea     rcx, [rax+rax]; Size
0x180013f43  call    cs:__imp_malloc
0x180013f4a  nop     dword ptr [rax+rax+00h]
0x180013f4f  mov     rdi, rax
0x180013f52  test    rax, rax
0x180013f55  jz      short loc_180013FB2
0x180013f57  mov     r8, [rbp+pbstr]; unsigned __int16 *
0x180013f5b  mov     edx, ebx; unsigned __int64
0x180013f5d  mov     rcx, rax; unsigned __int16 *
0x180013f60  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013f65  mov     ebx, eax
0x180013f67  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f6e  lea     rax, WPP_GLOBAL_Control
0x180013f75  cmp     rcx, rax
0x180013f78  jz      short loc_180013F98
0x180013f7a  test    byte ptr [rcx+1Ch], 40h
0x180013f7e  jz      short loc_180013F98
0x180013f80  mov     rcx, [rcx+10h]
0x180013f84  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x180013f8b  mov     edx, 1Bh
0x180013f90  mov     r9, rdi
0x180013f93  call    WPP_SF_S
0x180013f98  test    ebx, ebx
0x180013f9a  js      short loc_180013FA1
0x180013f9c  mov     [r14], rdi
0x180013f9f  jmp     short loc_180013FB7
0x180013fa1  mov     rcx, rdi; Block
0x180013fa4  call    cs:__imp_free
0x180013fab  nop     dword ptr [rax+rax+00h]
0x180013fb0  jmp     short loc_180013FB7
0x180013fb2  mov     ebx, 8007000Eh
0x180013fb7  mov     rcx, [rbp+pbstr]; bstrString
0x180013fbb  call    cs:__imp_SysFreeString
0x180013fc2  nop     dword ptr [rax+rax+00h]
0x180013fc7  mov     rcx, r12; struct IUnknown *
0x180013fca  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180013fcf  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x180013fd3  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180013fd8  lea     rax, WPP_GLOBAL_Control
0x180013fdf  test    ebx, ebx
0x180013fe1  jz      short loc_180014015
0x180013fe3  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fea  cmp     rcx, rax
0x180013fed  jz      short loc_180014015
0x180013fef  test    byte ptr [rcx+1Ch], 1
0x180013ff3  jz      short loc_180014015
0x180013ff5  mov     rcx, [rcx+10h]
0x180013ff9  lea     r9, aHrcomposeevent; "HrComposeEventBody"
0x180014000  mov     edx, 1Ch
0x180014005  mov     dword ptr [rsp+60h+var_40], ebx
0x180014009  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x180014010  call    WPP_SF_sd
0x180014015  mov     eax, ebx
0x180014017  mov     rbx, [rsp+60h+arg_8]
0x18001401f  add     rsp, 60h
0x180014023  pop     r15
0x180014025  pop     r14
0x180014027  pop     r13
0x180014029  pop     r12
0x18001402b  pop     rdi
0x18001402c  pop     rsi
0x18001402d  pop     rbp
0x18001402e  retn
```
