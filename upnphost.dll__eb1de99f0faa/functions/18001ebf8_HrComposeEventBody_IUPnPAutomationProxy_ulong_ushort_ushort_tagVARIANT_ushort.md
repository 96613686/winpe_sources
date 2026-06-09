# HrComposeEventBody(IUPnPAutomationProxy *,ulong,ushort * *,ushort * *,tagVARIANT *,ushort * *)

- ea: `0x18001ebf8`
- end: `0x18001ef27`
- name: `?HrComposeEventBody@@YAJPEAUIUPnPAutomationProxy@@KPEAPEAG1PEAUtagVARIANT@@1@Z`
- size: `815`
- prototype: `__int64 __fastcall(struct IUPnPAutomationProxy *, unsigned int, unsigned __int16 **, unsigned __int16 **, struct tagVARIANT *, BSTR pbstr)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180034030`
- `0x180045570`

## callees

- `0x18000db4c`
- `0x18001ebf8`
- `0x18001ef30`
- `0x18001ef4c`
- `0x18001f094`
- `0x18001f1a0`
- `0x18001f3f0`
- `0x180038324`
- `0x180039388`
- `0x180043124`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001edc8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001eea8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001edc8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001eea8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ecef`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ee4d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ecef`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ee4d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ec4d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ec4d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001ecde`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001ecde`
- `OLEAUT32!__imp_SysFreeString` at `0x18001eeb9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001eeb9`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ee3f`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ee3f`

## string_xrefs

- `0x18001eef1`: `HrComposeEventBody`

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
0x18001ebf8  mov     r11, rsp
0x18001ebfb  mov     [r11+10h], rbx
0x18001ebff  mov     [r11+20h], r9
0x18001ec03  mov     [r11+18h], r8
0x18001ec07  mov     [r11+8], rcx
0x18001ec0b  push    rbp
0x18001ec0c  push    rsi
0x18001ec0d  push    rdi
0x18001ec0e  push    r12
0x18001ec10  push    r13
0x18001ec12  push    r14
0x18001ec14  push    r15
0x18001ec16  mov     rbp, rsp
0x18001ec19  sub     rsp, 60h
0x18001ec1d  mov     r14, [rbp+pbstr]
0x18001ec21  lea     rax, [rbp+arg_0]
0x18001ec25  xor     r15d, r15d
0x18001ec28  mov     [r11-78h], rax
0x18001ec2c  mov     rdi, r8
0x18001ec2f  mov     [rbp+arg_0], r15
0x18001ec33  mov     r13d, edx
0x18001ec36  lea     r9, IID_IXMLDOMDocument; riid
0x18001ec3d  xor     edx, edx; pUnkOuter
0x18001ec3f  mov     [r14], r15
0x18001ec42  lea     r8d, [r15+1]; dwClsContext
0x18001ec46  lea     rcx, CLSID_DOMDocument60; rclsid
0x18001ec4d  call    cs:__imp_CoCreateInstance
0x18001ec53  mov     ebx, eax
0x18001ec55  lea     rax, WPP_GLOBAL_Control
0x18001ec5c  test    ebx, ebx
0x18001ec5e  js      loc_18001EED9
0x18001ec64  mov     rcx, [rbp+arg_0]; struct IXMLDOMDocument *
0x18001ec68  mov     [rbp+var_30], r15
0x18001ec6c  call    ?HrAppendProcessingInstruction@@YAJPEAUIXMLDOMDocument@@PEBG1@Z; HrAppendProcessingInstruction(IXMLDOMDocument *,ushort const *,ushort const *)
0x18001ec71  mov     ebx, eax
0x18001ec73  test    eax, eax
0x18001ec75  js      loc_18001EEC7
0x18001ec7b  mov     rcx, [rbp+arg_0]; struct IXMLDOMDocument *
0x18001ec7f  lea     r8, [rbp+var_30]; struct IXMLDOMNode **
0x18001ec83  lea     rdx, aEPropertyset; "e:propertyset"
0x18001ec8a  call    ?HrCreateElement@@YAJPEAUIXMLDOMDocument@@PEBGPEAPEAUIXMLDOMNode@@@Z; HrCreateElement(IXMLDOMDocument *,ushort const *,IXMLDOMNode * *)
0x18001ec8f  mov     ebx, eax
0x18001ec91  test    eax, eax
0x18001ec93  js      loc_18001EEC7
0x18001ec99  mov     r12, [rbp+var_30]
0x18001ec9d  mov     esi, r15d
0x18001eca0  test    r13d, r13d
0x18001eca3  jz      loc_18001EDF3
0x18001eca9  test    ebx, ebx
0x18001ecab  js      loc_18001EEBF
0x18001ecb1  mov     rcx, [rbp+arg_0]; struct IXMLDOMDocument *
0x18001ecb5  lea     r8, [rbp+var_28]; struct IXMLDOMNode **
0x18001ecb9  lea     rdx, aEProperty; "e:property"
0x18001ecc0  mov     [rbp+var_28], r15
0x18001ecc4  call    ?HrCreateElement@@YAJPEAUIXMLDOMDocument@@PEBGPEAPEAUIXMLDOMNode@@@Z; HrCreateElement(IXMLDOMDocument *,ushort const *,IXMLDOMNode * *)
0x18001ecc9  mov     ebx, eax
0x18001eccb  test    eax, eax
0x18001eccd  js      loc_18001EDDC
0x18001ecd3  mov     r14d, esi
0x18001ecd6  mov     [rbp+var_30], r15
0x18001ecda  mov     rcx, [rdi+r14*8]; lpString
0x18001ecde  call    cs:__imp_lstrlenW
0x18001ece4  movsxd  rbx, eax
0x18001ece7  lea     rcx, ds:2[rbx*2]; Size
0x18001ecef  call    cs:__imp_malloc
0x18001ecf5  mov     rdi, rax
0x18001ecf8  test    rax, rax
0x18001ecfb  jz      loc_18001EDD3
0x18001ed01  lea     rdx, [rbx+1]; cchDest
0x18001ed05  call    StringValidateDestW
0x18001ed0a  mov     r15, [rbp+var_28]
0x18001ed0e  mov     ebx, eax
0x18001ed10  test    eax, eax
0x18001ed12  js      loc_18001EDB3
0x18001ed18  mov     r9, [rbp+arg_10]
0x18001ed1c  mov     rcx, rdi; pszDest
0x18001ed1f  mov     r9, [r9+r14*8]; pszSrc
0x18001ed23  call    StringCopyWorkerW
0x18001ed28  mov     ebx, eax
0x18001ed2a  test    eax, eax
0x18001ed2c  js      loc_18001EDBD
0x18001ed32  mov     rcx, [rbp+arg_20]
0x18001ed36  lea     rax, [r14+r14*2]
0x18001ed3a  lea     r9, [rbp+var_20]; struct tagVARIANT
0x18001ed3e  mov     rdx, rdi; unsigned __int16 *
0x18001ed41  movups  xmm0, xmmword ptr [rcx+rax*8]
0x18001ed45  movsd   xmm1, qword ptr [rcx+rax*8+10h]
0x18001ed4b  lea     rax, [rbp+var_30]
0x18001ed4f  mov     rcx, [rbp+arg_0]; struct IXMLDOMDocument *
0x18001ed53  mov     [rsp+60h+var_40], rax; struct IXMLDOMElement **
0x18001ed58  mov     rax, [rbp+arg_18]
0x18001ed5c  movaps  xmmword ptr [rbp+var_20], xmm0
0x18001ed60  movsd   qword ptr [rbp+var_20+10h], xmm1
0x18001ed65  mov     r8, [rax+r14*8]; unsigned __int16 *
0x18001ed69  call    ?HrCreateElementWithType@@YAJPEAUIXMLDOMDocument@@PEBG1UtagVARIANT@@PEAPEAUIXMLDOMElement@@@Z; HrCreateElementWithType(IXMLDOMDocument *,ushort const *,ushort const *,tagVARIANT,IXMLDOMElement * *)
0x18001ed6e  mov     ebx, eax
0x18001ed70  test    eax, eax
0x18001ed72  js      short loc_18001EDBD
0x18001ed74  mov     rax, [r12]
0x18001ed78  xor     r8d, r8d
0x18001ed7b  mov     rdx, r15
0x18001ed7e  mov     rcx, r12
0x18001ed81  mov     rax, [rax+0A8h]
0x18001ed88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed8d  mov     rax, [r15]
0x18001ed90  xor     r8d, r8d
0x18001ed93  mov     rdx, [rbp+var_30]
0x18001ed97  mov     rcx, r15
0x18001ed9a  mov     rax, [rax+0A8h]
0x18001eda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eda6  mov     rcx, [rbp+var_30]; struct IUnknown *
0x18001edaa  mov     ebx, eax
0x18001edac  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18001edb1  jmp     short loc_18001EDBD
0x18001edb3  test    rdx, rdx
0x18001edb6  jz      short loc_18001EDBD
0x18001edb8  xor     eax, eax
0x18001edba  mov     [rdi], ax
0x18001edbd  mov     rcx, r15; struct IUnknown *
0x18001edc0  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18001edc5  mov     rcx, rdi; Block
0x18001edc8  call    cs:__imp_free
0x18001edce  xor     r15d, r15d
0x18001edd1  jmp     short loc_18001EDD8
0x18001edd3  mov     ebx, 8007000Eh
0x18001edd8  mov     rdi, [rbp+arg_10]
0x18001eddc  inc     esi
0x18001edde  cmp     esi, r13d
0x18001ede1  jb      loc_18001ECA9
0x18001ede7  test    ebx, ebx
0x18001ede9  js      loc_18001EEBF
0x18001edef  mov     r14, [rbp+pbstr]
0x18001edf3  mov     rcx, [rbp+arg_0]
0x18001edf7  xor     r8d, r8d
0x18001edfa  mov     rdx, r12
0x18001edfd  mov     rax, [rcx]
0x18001ee00  mov     rax, [rax+0A8h]
0x18001ee07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee0c  mov     ebx, eax
0x18001ee0e  test    eax, eax
0x18001ee10  js      loc_18001EEBF
0x18001ee16  mov     rcx, [rbp+arg_0]
0x18001ee1a  lea     rdx, [rbp+pbstr]
0x18001ee1e  mov     [rbp+pbstr], r15
0x18001ee22  mov     rax, [rcx]
0x18001ee25  mov     rax, [rax+110h]
0x18001ee2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee31  mov     ebx, eax
0x18001ee33  test    eax, eax
0x18001ee35  js      loc_18001EEBF
0x18001ee3b  mov     rcx, [rbp+pbstr]; pbstr
0x18001ee3f  call    cs:__imp_SysStringLen
0x18001ee45  inc     eax
0x18001ee47  mov     ebx, eax
0x18001ee49  lea     rcx, [rax+rax]; Size
0x18001ee4d  call    cs:__imp_malloc
0x18001ee53  mov     rdi, rax
0x18001ee56  test    rax, rax
0x18001ee59  jz      short loc_18001EEB0
0x18001ee5b  mov     r8, [rbp+pbstr]; unsigned __int16 *
0x18001ee5f  mov     edx, ebx; unsigned __int64
0x18001ee61  mov     rcx, rax; unsigned __int16 *
0x18001ee64  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ee69  mov     ebx, eax
0x18001ee6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee72  lea     rax, WPP_GLOBAL_Control
0x18001ee79  cmp     rcx, rax
0x18001ee7c  jz      short loc_18001EE9C
0x18001ee7e  test    byte ptr [rcx+1Ch], 40h
0x18001ee82  jz      short loc_18001EE9C
0x18001ee84  mov     rcx, [rcx+10h]
0x18001ee88  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x18001ee8f  mov     edx, 1Bh
0x18001ee94  mov     r9, rdi
0x18001ee97  call    WPP_SF_S
0x18001ee9c  test    ebx, ebx
0x18001ee9e  js      short loc_18001EEA5
0x18001eea0  mov     [r14], rdi
0x18001eea3  jmp     short loc_18001EEB5
0x18001eea5  mov     rcx, rdi; Block
0x18001eea8  call    cs:__imp_free
0x18001eeae  jmp     short loc_18001EEB5
0x18001eeb0  mov     ebx, 8007000Eh
0x18001eeb5  mov     rcx, [rbp+pbstr]; bstrString
0x18001eeb9  call    cs:__imp_SysFreeString
0x18001eebf  mov     rcx, r12; struct IUnknown *
0x18001eec2  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18001eec7  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x18001eecb  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18001eed0  lea     rax, WPP_GLOBAL_Control
0x18001eed7  test    ebx, ebx
0x18001eed9  jz      short loc_18001EF0D
0x18001eedb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eee2  cmp     rcx, rax
0x18001eee5  jz      short loc_18001EF0D
0x18001eee7  test    byte ptr [rcx+1Ch], 1
0x18001eeeb  jz      short loc_18001EF0D
0x18001eeed  mov     rcx, [rcx+10h]
0x18001eef1  lea     r9, aHrcomposeevent; "HrComposeEventBody"
0x18001eef8  mov     edx, 1Ch
0x18001eefd  mov     dword ptr [rsp+60h+var_40], ebx
0x18001ef01  lea     r8, WPP_26899187c1a539900c7f96418485818e_Traceguids
0x18001ef08  call    WPP_SF_sd
0x18001ef0d  mov     eax, ebx
0x18001ef0f  mov     rbx, [rsp+60h+arg_8]
0x18001ef17  add     rsp, 60h
0x18001ef1b  pop     r15
0x18001ef1d  pop     r14
0x18001ef1f  pop     r13
0x18001ef21  pop     r12
0x18001ef23  pop     rdi
0x18001ef24  pop     rsi
0x18001ef25  pop     rbp
0x18001ef26  retn
```
