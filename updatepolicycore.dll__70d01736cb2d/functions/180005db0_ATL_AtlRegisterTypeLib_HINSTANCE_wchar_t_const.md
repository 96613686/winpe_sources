# ATL::AtlRegisterTypeLib(HINSTANCE__ *,wchar_t const *)

- ea: `0x180005db0`
- end: `0x180005fbd`
- name: `?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEB_W@Z`
- size: `525`
- prototype: `__int64 __fastcall(HINSTANCE, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180004a70`

## callees

- `0x180005bec`
- `0x180005db0`
- `0x1800078c8`
- `0x18002ffa4`
- `0x18002ffd0`
- `0x18003017c`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005f18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005f18`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005eaa`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005eaa`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f43`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f66`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f43`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f66`
- `OLEAUT32!__imp_SysStringLen` at `0x180005e4a`
- `OLEAUT32!__imp_SysStringLen` at `0x180005e4a`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x180005f23`

## string_xrefs

- `0x180005efc`: `OLEAUT32.DLL`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterTypeLib(HINSTANCE a1, const wchar_t *a2)
{
  int v2; // ebx
  WCHAR *v3; // rbx
  UINT v4; // eax
  int v5; // eax
  WCHAR *v6; // rbx
  WCHAR *v7; // rdi
  LPWSTR v8; // rax
  __int64 v9; // rbx
  HMODULE ModuleHandleW; // rax
  __int64 (__fastcall *ProcAddress)(struct ITypeLib *, BSTR, WCHAR *); // rax
  BSTR bstrString; // [rsp+48h] [rbp-C0h] BYREF
  BSTR pbstr; // [rsp+50h] [rbp-B8h] BYREF
  struct ITypeLib *v15; // [rsp+58h] [rbp-B0h] BYREF
  WCHAR sz[264]; // [rsp+68h] [rbp-A0h] BYREF

  bstrString = 0;
  v15 = 0;
  v2 = ATL::AtlLoadTypeLib(a1, a2, &bstrString, &v15);
  if ( v2 >= 0 )
  {
    v3 = 0;
    pbstr = 0;
    if ( ((int (__fastcall *)(struct ITypeLib *, __int64, _QWORD, _QWORD, _QWORD, BSTR *))v15->lpVtbl->GetDocumentation)(
           v15,
           0xFFFFFFFFLL,
           0,
           0,
           0,
           &pbstr) >= 0
      && pbstr )
    {
      v4 = SysStringLen(pbstr);
      v5 = o_wcsncpy_s_0(sz, 260, pbstr, v4);
      if ( v5 )
      {
        if ( v5 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v5 == 22 || v5 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v5 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      sz[259] = 0;
      v6 = sz;
      v7 = sz;
      if ( sz[0] )
      {
        do
        {
          v8 = CharNextW(v7);
          if ( *v7 == 92 || *v7 == 47 || *v7 == 58 )
            v6 = v8;
          v7 = v8;
        }
        while ( *v8 );
      }
      v9 = v6 - sz;
      if ( 2 * (unsigned __int64)(unsigned int)v9 >= 0x208 )
        _report_rangecheckfailure();
      sz[(unsigned int)v9] = 0;
      v3 = sz;
    }
    if ( !ATL::_AtlRegisterPerUser
      || (ModuleHandleW = GetModuleHandleW(L"OLEAUT32.DLL")) == 0
      || (ProcAddress = (__int64 (__fastcall *)(struct ITypeLib *, BSTR, WCHAR *))GetProcAddress(
                                                                                    ModuleHandleW,
                                                                                    "RegisterTypeLibForUser")) == 0 )
    {
      ProcAddress = (__int64 (__fastcall *)(struct ITypeLib *, BSTR, WCHAR *))RegisterTypeLib;
    }
    v2 = ProcAddress(v15, bstrString, v3);
    SysFreeString(pbstr);
  }
  if ( v15 )
    ((void (__fastcall *)(struct ITypeLib *))v15->lpVtbl->Release)(v15);
  SysFreeString(bstrString);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180005db0  mov     rax, rsp
0x180005db3  mov     [rax+10h], rbx
0x180005db7  mov     [rax+18h], rsi
0x180005dbb  mov     [rax+20h], rdi
0x180005dbf  push    rbp
0x180005dc0  lea     rbp, [rax-188h]
0x180005dc7  sub     rsp, 280h
0x180005dce  mov     rax, cs:__security_cookie
0x180005dd5  xor     rax, rsp
0x180005dd8  mov     [rbp+180h+var_10], rax
0x180005ddf  xor     esi, esi
0x180005de1  mov     [rsp+280h+bstrString], rsi
0x180005de6  mov     [rsp+280h+var_230], rsi
0x180005deb  lea     r9, [rsp+280h+var_230]; struct ITypeLib **
0x180005df0  lea     r8, [rsp+280h+bstrString]; wchar_t **
0x180005df5  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEB_WPEAPEA_WPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,wchar_t const *,wchar_t * *,ITypeLib * *)
0x180005dfa  mov     ebx, eax
0x180005dfc  test    eax, eax
0x180005dfe  js      loc_180005F4A
0x180005e04  mov     ebx, esi
0x180005e06  mov     [rsp+280h+pbstr], rsi
0x180005e0b  mov     rcx, [rsp+280h+var_230]
0x180005e10  mov     rax, [rcx]
0x180005e13  lea     rdx, [rsp+280h+pbstr]
0x180005e18  mov     [rsp+280h+var_258], rdx
0x180005e1d  mov     [rsp+280h+var_260], rsi
0x180005e22  xor     r9d, r9d
0x180005e25  xor     r8d, r8d
0x180005e28  or      edx, 0FFFFFFFFh
0x180005e2b  mov     rax, [rax+48h]
0x180005e2f  call    _guard_dispatch_icall
0x180005e34  test    eax, eax
0x180005e36  js      loc_180005EF3
0x180005e3c  mov     rcx, [rsp+280h+pbstr]; pbstr
0x180005e41  test    rcx, rcx
0x180005e44  jz      loc_180005EF3
0x180005e4a  call    cs:__imp_SysStringLen
0x180005e50  mov     r9d, eax
0x180005e53  mov     r8, [rsp+280h+pbstr]
0x180005e58  mov     edx, 104h
0x180005e5d  lea     rcx, [rsp+280h+sz]
0x180005e62  call    _o_wcsncpy_s_0
0x180005e67  test    eax, eax
0x180005e69  jz      short loc_180005E8F
0x180005e6b  cmp     eax, 0Ch
0x180005e6e  jz      loc_180005F96
0x180005e74  cmp     eax, 16h
0x180005e77  jz      loc_180005FB2
0x180005e7d  cmp     eax, 22h ; '"'
0x180005e80  jz      loc_180005FB2
0x180005e86  cmp     eax, 50h ; 'P'
0x180005e89  jnz     loc_180005FA7
0x180005e8f  mov     [rbp+180h+var_1A], si
0x180005e96  lea     rbx, [rsp+280h+sz]
0x180005e9b  lea     rdi, [rsp+280h+sz]
0x180005ea0  cmp     [rsp+280h+sz], si
0x180005ea5  jz      short loc_180005ECD
0x180005ea7  mov     rcx, rdi; lpsz
0x180005eaa  call    cs:__imp_CharNextW
0x180005eb0  cmp     word ptr [rdi], 5Ch ; '\'
0x180005eb4  jz      short loc_180005EC2
0x180005eb6  cmp     word ptr [rdi], 2Fh ; '/'
0x180005eba  jz      short loc_180005EC2
0x180005ebc  cmp     word ptr [rdi], 3Ah ; ':'
0x180005ec0  jnz     short loc_180005EC5
0x180005ec2  mov     rbx, rax
0x180005ec5  mov     rdi, rax
0x180005ec8  cmp     [rax], si
0x180005ecb  jnz     short loc_180005EA7
0x180005ecd  lea     rax, [rsp+280h+sz]
0x180005ed2  sub     rbx, rax
0x180005ed5  sar     rbx, 1
0x180005ed8  mov     eax, ebx
0x180005eda  add     rax, rax
0x180005edd  cmp     rax, 208h
0x180005ee3  jnb     loc_180005FA1
0x180005ee9  mov     [rsp+rax+280h+sz], si
0x180005eee  lea     rbx, [rsp+280h+sz]
0x180005ef3  cmp     cs:?_AtlRegisterPerUser@ATL@@3_NA, 1; bool ATL::_AtlRegisterPerUser
0x180005efa  jnz     short loc_180005F23
0x180005efc  lea     rcx, ModuleName; "OLEAUT32.DLL"
0x180005f03  call    cs:__imp_GetModuleHandleW
0x180005f09  test    rax, rax
0x180005f0c  jz      short loc_180005F23
0x180005f0e  lea     rdx, aRegistertypeli; "RegisterTypeLibForUser"
0x180005f15  mov     rcx, rax; hModule
0x180005f18  call    cs:__imp_GetProcAddress
0x180005f1e  test    rax, rax
0x180005f21  jnz     short loc_180005F2A
0x180005f23  mov     rax, cs:__imp_RegisterTypeLib
0x180005f2a  mov     r8, rbx
0x180005f2d  mov     rdx, [rsp+280h+bstrString]
0x180005f32  mov     rcx, [rsp+280h+var_230]
0x180005f37  call    _guard_dispatch_icall
0x180005f3c  mov     ebx, eax
0x180005f3e  mov     rcx, [rsp+280h+pbstr]; bstrString
0x180005f43  call    cs:__imp_SysFreeString
0x180005f49  nop
0x180005f4a  mov     rcx, [rsp+280h+var_230]
0x180005f4f  test    rcx, rcx
0x180005f52  jz      short loc_180005F61
0x180005f54  mov     rax, [rcx]
0x180005f57  mov     rax, [rax+10h]
0x180005f5b  call    _guard_dispatch_icall
0x180005f60  nop
0x180005f61  mov     rcx, [rsp+280h+bstrString]; bstrString
0x180005f66  call    cs:__imp_SysFreeString
0x180005f6c  mov     eax, ebx
0x180005f6e  mov     rcx, [rbp+180h+var_10]
0x180005f75  xor     rcx, rsp; StackCookie
0x180005f78  call    __security_check_cookie
0x180005f7d  lea     r11, [rsp+280h+var_s0]
0x180005f85  mov     rbx, [r11+18h]
0x180005f89  mov     rsi, [r11+20h]
0x180005f8d  mov     rdi, [r11+28h]
0x180005f91  mov     rsp, r11
0x180005f94  pop     rbp
0x180005f95  retn
0x180005f96  mov     ecx, 8007000Eh; int
0x180005f9b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005fa1  call    __report_rangecheckfailure
0x180005fa7  mov     ecx, 80004005h; int
0x180005fac  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005fb2  mov     ecx, 80070057h; int
0x180005fb7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
