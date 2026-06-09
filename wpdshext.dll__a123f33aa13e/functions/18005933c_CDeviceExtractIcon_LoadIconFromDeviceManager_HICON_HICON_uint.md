# CDeviceExtractIcon::_LoadIconFromDeviceManager(HICON__ * *,HICON__ * *,uint)

- ea: `0x18005933c`
- end: `0x180059496`
- name: `?_LoadIconFromDeviceManager@CDeviceExtractIcon@@AEAAJPEAPEAUHICON__@@0I@Z`
- size: `346`
- prototype: `int(CDeviceExtractIcon *__hidden this, HICON *, HICON *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180057250`

## callees

- `0x1800285c8`
- `0x18005933c`
- `0x180078010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18005937d`
- `ole32!CoCreateInstance` at `0x18005937d`
- `SHELL32!__imp_SHDefExtractIconW` at `0x180059447`
- `SHELL32!__imp_SHDefExtractIconW` at `0x180059476`
- `SHELL32!__imp_SHDefExtractIconW` at `0x180059447`
- `SHELL32!__imp_SHDefExtractIconW` at `0x180059476`

## string_xrefs

- `0x180059440`: `wpdshext.dll`
- `0x18005946f`: `wpdshext.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDeviceExtractIcon::_LoadIconFromDeviceManager(
        CDeviceExtractIcon *this,
        HICON *a2,
        HICON *a3,
        UINT a4)
{
  HRESULT Instance; // edi
  int v9; // ebx
  int v11; // [rsp+40h] [rbp-28h] BYREF
  int v12; // [rsp+44h] [rbp-24h] BYREF
  int v13; // [rsp+48h] [rbp-20h] BYREF
  LPVOID ppv[3]; // [rsp+50h] [rbp-18h] BYREF

  ppv[0] = 0;
  Instance = CoCreateInstance(&CLSID_PortableDeviceManager, 0, 1u, &GUID_a1567595_4c2f_4574_a6fa_ecef917b9a40, ppv);
  v11 = 0;
  v12 = 0;
  if ( Instance >= 0 )
  {
    v13 = 4;
    Instance = (*(__int64 (__fastcall **)(LPVOID, char *, const wchar_t *, int *, int *, int *))(*(_QWORD *)ppv[0] + 64LL))(
                 ppv[0],
                 (char *)this + 12,
                 L"PortableDeviceType",
                 &v11,
                 &v13,
                 &v12);
    if ( Instance >= 0 )
    {
      v9 = -701;
      if ( v12 == 4 )
      {
        switch ( v11 )
        {
          case 1:
            v9 = -702;
            break;
          case 2:
            v9 = -704;
            break;
          case 3:
            v9 = -703;
            break;
          case 4:
            v9 = -705;
            break;
          case 5:
            v9 = -706;
            break;
          case 6:
            v9 = -707;
            break;
        }
      }
      Instance = SHDefExtractIconW(L"wpdshext.dll", v9, 0, a2, a3, a4);
      if ( Instance < 0 && v9 != -701 )
        Instance = SHDefExtractIconW(L"wpdshext.dll", -701, 0, a2, a3, a4);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18005933c  push    rbp
0x18005933e  push    rbx
0x18005933f  push    rsi
0x180059340  push    rdi
0x180059341  push    r14
0x180059343  push    r15
0x180059345  mov     rbp, rsp
0x180059348  sub     rsp, 68h
0x18005934c  mov     esi, r9d
0x18005934f  mov     r14, r8
0x180059352  mov     r15, rdx
0x180059355  mov     rbx, rcx
0x180059358  mov     [rbp+var_18], 0
0x180059360  lea     rax, [rbp+var_18]
0x180059364  mov     [rsp+68h+ppv], rax; ppv
0x180059369  lea     r9, _GUID_a1567595_4c2f_4574_a6fa_ecef917b9a40; riid
0x180059370  xor     edx, edx; pUnkOuter
0x180059372  lea     r8d, [rdx+1]; dwClsContext
0x180059376  lea     rcx, CLSID_PortableDeviceManager; rclsid
0x18005937d  call    cs:__imp_CoCreateInstance
0x180059383  mov     edi, eax
0x180059385  xor     ecx, ecx
0x180059387  mov     [rbp+var_28], ecx
0x18005938a  xor     eax, eax
0x18005938c  mov     [rbp+var_24], eax
0x18005938f  test    edi, edi
0x180059391  js      loc_18005947E
0x180059397  mov     [rbp+var_20], 4
0x18005939e  mov     rcx, [rbp+var_18]
0x1800593a2  mov     rax, [rcx]
0x1800593a5  lea     rdx, [rbx+0Ch]
0x1800593a9  lea     r8, [rbp+var_24]
0x1800593ad  mov     qword ptr [rsp+68h+nIconSize], r8
0x1800593b2  lea     r8, [rbp+var_20]
0x1800593b6  mov     [rsp+68h+ppv], r8
0x1800593bb  lea     r9, [rbp+var_28]
0x1800593bf  lea     r8, aPortabledevice_1; "PortableDeviceType"
0x1800593c6  mov     rax, [rax+40h]
0x1800593ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800593cf  mov     edi, eax
0x1800593d1  mov     ecx, [rbp+var_28]
0x1800593d4  mov     eax, [rbp+var_24]
0x1800593d7  test    edi, edi
0x1800593d9  js      loc_18005947E
0x1800593df  mov     ebx, 0FFFFFD43h
0x1800593e4  cmp     eax, 4
0x1800593e7  jnz     short loc_18005942F
0x1800593e9  sub     ecx, 1
0x1800593ec  jz      short loc_18005942A
0x1800593ee  sub     ecx, 1
0x1800593f1  jz      short loc_180059423
0x1800593f3  sub     ecx, 1
0x1800593f6  jz      short loc_18005941C
0x1800593f8  sub     ecx, 1
0x1800593fb  jz      short loc_180059415
0x1800593fd  sub     ecx, 1
0x180059400  jz      short loc_18005940E
0x180059402  cmp     ecx, 1
0x180059405  jnz     short loc_18005942F
0x180059407  mov     ebx, 0FFFFFD3Dh
0x18005940c  jmp     short loc_18005942F
0x18005940e  mov     ebx, 0FFFFFD3Eh
0x180059413  jmp     short loc_18005942F
0x180059415  mov     ebx, 0FFFFFD3Fh
0x18005941a  jmp     short loc_18005942F
0x18005941c  mov     ebx, 0FFFFFD41h
0x180059421  jmp     short loc_18005942F
0x180059423  mov     ebx, 0FFFFFD40h
0x180059428  jmp     short loc_18005942F
0x18005942a  mov     ebx, 0FFFFFD42h
0x18005942f  mov     [rsp+68h+nIconSize], esi; nIconSize
0x180059433  mov     [rsp+68h+ppv], r14; phiconSmall
0x180059438  mov     r9, r15; phiconLarge
0x18005943b  xor     r8d, r8d; uFlags
0x18005943e  mov     edx, ebx; iIndex
0x180059440  lea     rcx, szFile; "wpdshext.dll"
0x180059447  call    cs:__imp_SHDefExtractIconW
0x18005944d  mov     edi, eax
0x18005944f  test    eax, eax
0x180059451  jns     short loc_18005947E
0x180059453  cmp     ebx, 0FFFFFD43h
0x180059459  jz      short loc_18005947E
0x18005945b  mov     [rsp+68h+nIconSize], esi; nIconSize
0x18005945f  mov     [rsp+68h+ppv], r14; phiconSmall
0x180059464  mov     r9, r15; phiconLarge
0x180059467  xor     r8d, r8d; uFlags
0x18005946a  mov     edx, 0FFFFFD43h; iIndex
0x18005946f  lea     rcx, szFile; "wpdshext.dll"
0x180059476  call    cs:__imp_SHDefExtractIconW
0x18005947c  mov     edi, eax
0x18005947e  lea     rcx, [rbp+var_18]
0x180059482  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180059487  mov     eax, edi
0x180059489  add     rsp, 68h
0x18005948d  pop     r15
0x18005948f  pop     r14
0x180059491  pop     rdi
0x180059492  pop     rsi
0x180059493  pop     rbx
0x180059494  pop     rbp
0x180059495  retn
```
