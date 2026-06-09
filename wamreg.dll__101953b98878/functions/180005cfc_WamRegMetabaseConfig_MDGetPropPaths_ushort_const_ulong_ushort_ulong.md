# WamRegMetabaseConfig::MDGetPropPaths(ushort const *,ulong,ushort * *,ulong *)

- ea: `0x180005cfc`
- end: `0x180005f6e`
- name: `?MDGetPropPaths@WamRegMetabaseConfig@@QEAAJPEBGKPEAPEAGPEAK@Z`
- size: `626`
- prototype: `__int64 __fastcall(WamRegMetabaseConfig *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800021d0`
- `0x180002460`
- `0x1800029e0`
- `0x1800030b0`
- `0x1800034b0`
- `0x180003720`
- `0x180003d80`

## callees

- `0x180001044`
- `0x180005cfc`
- `0x180007010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180005dae`
- `iisutil!PuDbgPrint` at `0x180005e81`
- `iisutil!PuDbgPrint` at `0x180005f30`
- `iisutil!PuDbgPrint` at `0x180005dae`
- `iisutil!PuDbgPrint` at `0x180005e81`
- `iisutil!PuDbgPrint` at `0x180005f30`

## string_xrefs

- `0x180005d90`: `inetsrv\iis\svcs\wam\wamreg\mdconfig.cpp`
- `0x180005e7a`: `inetsrv\iis\svcs\wam\wamreg\mdconfig.cpp`
- `0x180005f24`: `inetsrv\iis\svcs\wam\wamreg\mdconfig.cpp`
- `0x180005d85`: `WamRegMetabaseConfig::MDGetPropPaths`
- `0x180005e68`: `WamRegMetabaseConfig::MDGetPropPaths`
- `0x180005f18`: `WamRegMetabaseConfig::MDGetPropPaths`
- `0x180005f0c`: `GetDataPaths failed with identitifier %d, path %S, hr = %08x\n`
- `0x180005d97`: `Failed to open metabase path %S, hr = %08x\n`

## pseudocode

```c
__int64 __fastcall WamRegMetabaseConfig::MDGetPropPaths(
        WamRegMetabaseConfig *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 **a4,
        unsigned int *a5)
{
  __int64 v6; // rdx
  int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  unsigned __int16 *v12; // rsi
  unsigned int v13; // r15d
  int v14; // eax
  unsigned int *v15; // rax
  unsigned int v17[4]; // [rsp+50h] [rbp-10h] BYREF
  WamRegMetabaseConfig *v18; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v19; // [rsp+98h] [rbp+38h] BYREF

  v18 = this;
  v6 = 0;
  LOWORD(v18) = 0;
  v17[0] = 0;
  v19 = 0;
  if ( a2 )
  {
    v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *, __int64, int, unsigned int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 136LL))(
           WamRegMetabaseConfig::m_pMetabase,
           0,
           a2,
           1,
           30000,
           v17);
    v10 = v9;
    if ( v9 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconfig.cpp",
          1457,
          "WamRegMetabaseConfig::MDGetPropPaths",
          "Failed to open metabase path %S, hr = %08x\n",
          a2,
          v9);
      return v10;
    }
    v6 = v17[0];
  }
  v11 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD, _DWORD, _DWORD, WamRegMetabaseConfig **, unsigned int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 128LL))(
          WamRegMetabaseConfig::m_pMetabase,
          v6,
          0,
          a3,
          0,
          0,
          &v18,
          &v19);
  v10 = v11;
  if ( (v11 & 0x1FFF0000) == 0x70000 )
    v11 = (unsigned __int16)v11;
  if ( v11 == 122 )
  {
    if ( v19 )
    {
      v12 = (unsigned __int16 *)operator new(saturated_mul(v19, 2u));
      if ( v12 )
      {
        v13 = v19;
        v14 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD, unsigned int, unsigned __int16 *, unsigned int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 128LL))(
                WamRegMetabaseConfig::m_pMetabase,
                v17[0],
                0,
                a3,
                0,
                v19,
                v12,
                &v19);
        v10 = v14;
        if ( v14 >= 0 )
        {
          v15 = a5;
          *a4 = v12;
          *v15 = v13;
        }
        else if ( (g_dwDebugFlags & 3) != 0 )
        {
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconfig.cpp",
            1431,
            "WamRegMetabaseConfig::MDGetPropPaths",
            "GetDataPaths failed with identitifier %d, path %S, hr = %08x\n",
            a3,
            a2,
            v14);
        }
      }
      else
      {
        v10 = -2147024882;
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconfig.cpp",
            1414,
            "WamRegMetabaseConfig::MDGetPropPaths",
            "Out of memory. \n");
      }
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconfig.cpp",
      1446,
      "WamRegMetabaseConfig::MDGetPropPaths",
      "GetDataPaths failed with identitifier %d, path %S, hr = %08x\n",
      a3,
      a2,
      v10);
  }
  if ( v17[0] )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 144LL))(WamRegMetabaseConfig::m_pMetabase);
  return v10;
}

```

## disassembly

```asm
0x180005cfc  mov     r11, rsp
0x180005cff  mov     [r11+18h], rbx
0x180005d03  mov     [r11+20h], rsi
0x180005d07  mov     [r11+8], rcx
0x180005d0b  push    rbp
0x180005d0c  push    rdi
0x180005d0d  push    r12
0x180005d0f  push    r14
0x180005d11  push    r15
0x180005d13  mov     rbp, rsp
0x180005d16  sub     rsp, 60h
0x180005d1a  xor     eax, eax
0x180005d1c  mov     rdi, rdx
0x180005d1f  xor     edx, edx
0x180005d21  mov     word ptr [rbp+arg_0], ax
0x180005d25  mov     [rbp+var_10], edx
0x180005d28  mov     r12, r9
0x180005d2b  mov     [rbp+arg_8], eax
0x180005d2e  mov     r14d, r8d
0x180005d31  test    rdi, rdi
0x180005d34  jz      loc_180005DBC
0x180005d3a  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180005d41  lea     rdx, [rbp+var_10]
0x180005d45  mov     [r11-60h], rdx
0x180005d49  mov     r9d, 1
0x180005d4f  mov     r8, rdi
0x180005d52  mov     dword ptr [rsp+60h+var_40], 7530h
0x180005d5a  xor     edx, edx
0x180005d5c  mov     rax, [rcx]
0x180005d5f  mov     rax, [rax+88h]
0x180005d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d6b  mov     ebx, eax
0x180005d6d  test    eax, eax
0x180005d6f  jns     short loc_180005DB9
0x180005d71  test    byte ptr cs:g_dwDebugFlags, 3
0x180005d78  jz      loc_180005F53
0x180005d7e  mov     rcx, cs:g_pDebug
0x180005d85  lea     r9, aWamregmetabase_1; "WamRegMetabaseConfig::MDGetPropPaths"
0x180005d8c  mov     dword ptr [rsp+60h+var_30], eax
0x180005d90  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconf"...
0x180005d97  lea     rax, aFailedToOpenMe_0; "Failed to open metabase path %S, hr = %"...
0x180005d9e  mov     [rsp+60h+var_38], rdi
0x180005da3  mov     r8d, 5B1h
0x180005da9  mov     [rsp+60h+var_40], rax
0x180005dae  call    cs:__imp_PuDbgPrint
0x180005db4  jmp     loc_180005F53
0x180005db9  mov     edx, [rbp+var_10]
0x180005dbc  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180005dc3  lea     r8, [rbp+arg_8]
0x180005dc7  mov     [rsp+60h+var_28], r8
0x180005dcc  mov     r9d, r14d
0x180005dcf  lea     r8, [rbp+arg_0]
0x180005dd3  mov     [rsp+60h+var_30], r8
0x180005dd8  xor     r8d, r8d
0x180005ddb  mov     rax, [rcx]
0x180005dde  mov     dword ptr [rsp+60h+var_38], 0
0x180005de6  mov     dword ptr [rsp+60h+var_40], 0
0x180005dee  mov     rax, [rax+80h]
0x180005df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dfa  mov     ecx, eax
0x180005dfc  mov     ebx, eax
0x180005dfe  and     ecx, 1FFF0000h
0x180005e04  cmp     ecx, 70000h
0x180005e0a  jnz     short loc_180005E0F
0x180005e0c  movzx   eax, bx
0x180005e0f  cmp     eax, 7Ah ; 'z'
0x180005e12  jnz     loc_180005EF2
0x180005e18  mov     eax, [rbp+arg_8]
0x180005e1b  test    eax, eax
0x180005e1d  jz      loc_180005F36
0x180005e23  mov     ecx, eax
0x180005e25  mov     eax, 2
0x180005e2a  mul     rcx
0x180005e2d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005e34  cmovb   rax, rcx
0x180005e38  mov     rcx, rax; Size
0x180005e3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005e40  mov     rsi, rax
0x180005e43  test    rax, rax
0x180005e46  jnz     short loc_180005E8C
0x180005e48  test    byte ptr cs:g_dwDebugFlags, 3
0x180005e4f  mov     ebx, 8007000Eh
0x180005e54  jz      loc_180005F36
0x180005e5a  mov     rcx, cs:g_pDebug
0x180005e61  lea     rax, aOutOfMemory; "Out of memory. \n"
0x180005e68  lea     r9, aWamregmetabase_1; "WamRegMetabaseConfig::MDGetPropPaths"
0x180005e6f  mov     [rsp+60h+var_40], rax
0x180005e74  mov     r8d, 586h
0x180005e7a  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconf"...
0x180005e81  call    cs:__imp_PuDbgPrint
0x180005e87  jmp     loc_180005F36
0x180005e8c  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180005e93  lea     rdx, [rbp+arg_8]
0x180005e97  mov     r15d, [rbp+arg_8]
0x180005e9b  mov     r9d, r14d
0x180005e9e  mov     [rsp+60h+var_28], rdx
0x180005ea3  xor     r8d, r8d
0x180005ea6  mov     edx, [rbp+var_10]
0x180005ea9  mov     rax, [rcx]
0x180005eac  mov     [rsp+60h+var_30], rsi
0x180005eb1  mov     dword ptr [rsp+60h+var_38], r15d
0x180005eb6  mov     dword ptr [rsp+60h+var_40], 0
0x180005ebe  mov     rax, [rax+80h]
0x180005ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eca  mov     ebx, eax
0x180005ecc  test    eax, eax
0x180005ece  jns     short loc_180005EE5
0x180005ed0  test    byte ptr cs:g_dwDebugFlags, 3
0x180005ed7  jz      short loc_180005F36
0x180005ed9  mov     dword ptr [rsp+60h+var_28], eax
0x180005edd  mov     r8d, 597h
0x180005ee3  jmp     short loc_180005F05
0x180005ee5  mov     rax, [rbp+arg_20]
0x180005ee9  mov     [r12], rsi
0x180005eed  mov     [rax], r15d
0x180005ef0  jmp     short loc_180005F36
0x180005ef2  test    byte ptr cs:g_dwDebugFlags, 3
0x180005ef9  jz      short loc_180005F36
0x180005efb  mov     dword ptr [rsp+60h+var_28], ebx
0x180005eff  mov     r8d, 5A6h
0x180005f05  mov     rcx, cs:g_pDebug
0x180005f0c  lea     rax, aGetdatapathsFa; "GetDataPaths failed with identitifier %"...
0x180005f13  mov     [rsp+60h+var_30], rdi
0x180005f18  lea     r9, aWamregmetabase_1; "WamRegMetabaseConfig::MDGetPropPaths"
0x180005f1f  mov     dword ptr [rsp+60h+var_38], r14d
0x180005f24  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconf"...
0x180005f2b  mov     [rsp+60h+var_40], rax
0x180005f30  call    cs:__imp_PuDbgPrint
0x180005f36  mov     edx, [rbp+var_10]
0x180005f39  test    edx, edx
0x180005f3b  jz      short loc_180005F53
0x180005f3d  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180005f44  mov     rax, [rcx]
0x180005f47  mov     rax, [rax+90h]
0x180005f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f53  lea     r11, [rsp+60h+var_s0]
0x180005f58  mov     eax, ebx
0x180005f5a  mov     rbx, [r11+40h]
0x180005f5e  mov     rsi, [r11+48h]
0x180005f62  mov     rsp, r11
0x180005f65  pop     r15
0x180005f67  pop     r14
0x180005f69  pop     r12
0x180005f6b  pop     rdi
0x180005f6c  pop     rbp
0x180005f6d  retn
```
