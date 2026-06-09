# WamRegMetabaseConfig::UpdateMD(MDPropItem *,ulong,ushort const *,int)

- ea: `0x180006408`
- end: `0x180006657`
- name: `?UpdateMD@WamRegMetabaseConfig@@QEAAJPEAUMDPropItem@@KPEBGH@Z`
- size: `591`
- prototype: `__int64 __fastcall(WamRegMetabaseConfig *this, struct MDPropItem *, int, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180004948`
- `0x180004acc`

## callees

- `0x180006408`
- `0x180007010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000653a`
- `iisutil!PuDbgPrint` at `0x1800065e4`
- `iisutil!PuDbgPrint` at `0x18000663e`
- `iisutil!PuDbgPrint` at `0x18000653a`
- `iisutil!PuDbgPrint` at `0x1800065e4`
- `iisutil!PuDbgPrint` at `0x18000663e`

## string_xrefs

- `0x180006521`: `WamRegMetabaseConfig::UpdateMD`
- `0x1800065b4`: `WamRegMetabaseConfig::UpdateMD`
- `0x180006615`: `WamRegMetabaseConfig::UpdateMD`
- `0x180006533`: `inetsrv\iis\svcs\wam\wamreg\mdconfig.cpp`
- `0x1800065bf`: `inetsrv\iis\svcs\wam\wamreg\mdconfig.cpp`
- `0x180006620`: `inetsrv\iis\svcs\wam\wamreg\mdconfig.cpp`
- `0x1800065d3`: `Metabase SetData failed. Path = %S, id = %08x, error = %08x\n`
- `0x180006627`: `Failed to open metabase path %S, error = %08x\n`

## pseudocode

```c
__int64 __fastcall WamRegMetabaseConfig::UpdateMD(
        WamRegMetabaseConfig *this,
        struct MDPropItem *a2,
        int a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  int v8; // eax
  unsigned int v9; // esi
  unsigned int v10; // r14d
  char *v11; // r15
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  __int128 v16; // [rsp+40h] [rbp-38h] BYREF
  __int128 v17; // [rsp+50h] [rbp-28h]
  __int64 v18; // [rsp+60h] [rbp-18h]

  a5 = 0;
  v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *, __int64, int, unsigned int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 136LL))(
         WamRegMetabaseConfig::m_pMetabase,
         0,
         a4,
         2,
         30000,
         &a5);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconfig.cpp",
        248,
        "WamRegMetabaseConfig::UpdateMD",
        "Failed to open metabase path %S, error = %08x\n",
        a4,
        v8);
  }
  else
  {
    v16 = 0;
    v18 = 0;
    v10 = 0;
    v17 = 0;
    while ( 1 )
    {
      v11 = (char *)a2 + 24 * v10;
      if ( *((_DWORD *)v11 + 4) == 1 )
      {
        if ( *((_DWORD *)v11 + 1) == 2 )
        {
          LODWORD(v16) = *((_DWORD *)a2 + 6 * v10);
          v12 = -1;
          DWORD2(v16) = v10 != 0 ? 100 : 2;
          v13 = *((_QWORD *)a2 + 3 * v10 + 1);
          DWORD1(v16) = a3;
          HIDWORD(v16) = 2;
          do
            ++v12;
          while ( *(_WORD *)(v13 + 2 * v12) );
          *((_QWORD *)&v17 + 1) = v13;
          LODWORD(v17) = 2 * v12 + 2;
        }
        else if ( *((_DWORD *)v11 + 1) == 1 )
        {
          LODWORD(v16) = *((_DWORD *)a2 + 6 * v10);
          DWORD1(v16) = a3;
          *((_QWORD *)&v17 + 1) = (char *)a2 + 24 * v10 + 8;
          DWORD2(v16) = v10 != 0 ? 100 : 2;
          HIDWORD(v16) = 1;
          LODWORD(v17) = 4;
        }
        else if ( (g_dwDebugFlags & 3) != 0 )
        {
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconfig.cpp",
            203,
            "WamRegMetabaseConfig::UpdateMD",
            "Unsupported data type by WAMREG.\n");
        }
        v14 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int128 *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase
                                                                            + 72LL))(
                WamRegMetabaseConfig::m_pMetabase,
                a5,
                0,
                &v16);
        *((_DWORD *)a2 + 6 * v10 + 5) = v14;
        v9 = v14;
        if ( v14 < 0 )
          break;
      }
      if ( *((_DWORD *)a2 + 6 * v10 + 4) == 2 )
        v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase
                                                                               + 88LL))(
               WamRegMetabaseConfig::m_pMetabase,
               a5,
               0,
               *((unsigned int *)a2 + 6 * v10),
               *((_DWORD *)v11 + 1));
      if ( (int)++v10 >= 10 )
        goto LABEL_19;
    }
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconfig.cpp",
        214,
        "WamRegMetabaseConfig::UpdateMD",
        "Metabase SetData failed. Path = %S, id = %08x, error = %08x\n",
        a4,
        *((_DWORD *)a2 + 6 * v10),
        v14);
LABEL_19:
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 144LL))(
      WamRegMetabaseConfig::m_pMetabase,
      a5);
  }
  return v9;
}

```

## disassembly

```asm
0x180006408  push    rbp
0x18000640a  push    rbx
0x18000640b  push    rsi
0x18000640c  push    rdi
0x18000640d  push    r12
0x18000640f  push    r13
0x180006411  push    r14
0x180006413  push    r15
0x180006415  mov     rbp, rsp
0x180006418  sub     rsp, 78h
0x18000641c  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180006423  mov     rdi, rdx
0x180006426  lea     rdx, [rbp+arg_20]
0x18000642a  mov     r12, r9
0x18000642d  mov     [rsp+78h+var_50], rdx
0x180006432  xor     ebx, ebx
0x180006434  mov     [rbp+arg_20], ebx
0x180006437  mov     r13d, r8d
0x18000643a  mov     rax, [rcx]
0x18000643d  mov     r8, r12
0x180006440  xor     edx, edx
0x180006442  mov     dword ptr [rsp+78h+var_58], 7530h
0x18000644a  lea     r9d, [rbx+2]
0x18000644e  mov     rax, [rax+88h]
0x180006455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000645a  mov     esi, eax
0x18000645c  test    eax, eax
0x18000645e  js      loc_180006605
0x180006464  xorps   xmm0, xmm0
0x180006467  xor     eax, eax
0x180006469  movups  [rbp+var_38], xmm0
0x18000646d  mov     [rbp+var_18], rax
0x180006471  mov     r14d, ebx
0x180006474  movups  [rbp+var_28], xmm0
0x180006478  mov     eax, r14d
0x18000647b  lea     rbx, [rax+rax*2]
0x18000647f  cmp     dword ptr [rdi+rbx*8+10h], 1
0x180006484  lea     r15, [rdi+rbx*8]
0x180006488  jnz     loc_180006567
0x18000648e  mov     eax, r14d
0x180006491  neg     eax
0x180006493  sbb     ecx, ecx
0x180006495  and     ecx, 62h
0x180006498  add     ecx, 2
0x18000649b  cmp     dword ptr [r15+4], 2
0x1800064a0  jnz     short loc_1800064DA
0x1800064a2  mov     eax, [rdi+rbx*8]
0x1800064a5  mov     dword ptr [rbp+var_38], eax
0x1800064a8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800064ac  mov     dword ptr [rbp+var_38+8], ecx
0x1800064af  xor     edx, edx
0x1800064b1  mov     rcx, [rdi+rbx*8+8]
0x1800064b6  mov     dword ptr [rbp+var_38+4], r13d
0x1800064ba  mov     dword ptr [rbp+var_38+0Ch], 2
0x1800064c1  inc     rax
0x1800064c4  cmp     [rcx+rax*2], dx
0x1800064c8  jnz     short loc_1800064C1
0x1800064ca  lea     eax, ds:2[rax*2]
0x1800064d1  mov     qword ptr [rbp+var_28+8], rcx
0x1800064d5  mov     dword ptr [rbp+var_28], eax
0x1800064d8  jmp     short loc_180006540
0x1800064da  cmp     dword ptr [r15+4], 1
0x1800064df  jnz     short loc_18000650A
0x1800064e1  mov     eax, [rdi+rbx*8]
0x1800064e4  mov     dword ptr [rbp+var_38], eax
0x1800064e7  lea     rax, [rdi+8]
0x1800064eb  lea     rax, [rax+rbx*8]
0x1800064ef  mov     dword ptr [rbp+var_38+4], r13d
0x1800064f3  mov     qword ptr [rbp+var_28+8], rax
0x1800064f7  mov     dword ptr [rbp+var_38+8], ecx
0x1800064fa  mov     dword ptr [rbp+var_38+0Ch], 1
0x180006501  mov     dword ptr [rbp+var_28], 4
0x180006508  jmp     short loc_180006540
0x18000650a  test    byte ptr cs:g_dwDebugFlags, 3
0x180006511  jz      short loc_180006540
0x180006513  mov     rcx, cs:g_pDebug
0x18000651a  lea     rax, aUnsupportedDat; "Unsupported data type by WAMREG.\n"
0x180006521  lea     r9, aWamregmetabase_0; "WamRegMetabaseConfig::UpdateMD"
0x180006528  mov     [rsp+78h+var_58], rax
0x18000652d  mov     r8d, 0CBh
0x180006533  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconf"...
0x18000653a  call    cs:__imp_PuDbgPrint
0x180006540  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180006547  lea     r9, [rbp+var_38]
0x18000654b  mov     edx, [rbp+arg_20]
0x18000654e  xor     r8d, r8d
0x180006551  mov     rax, [rcx]
0x180006554  mov     rax, [rax+48h]
0x180006558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000655d  mov     [rdi+rbx*8+14h], eax
0x180006561  mov     esi, eax
0x180006563  test    eax, eax
0x180006565  js      short loc_1800065A4
0x180006567  cmp     dword ptr [rdi+rbx*8+10h], 2
0x18000656c  jnz     short loc_180006595
0x18000656e  mov     edx, [r15+4]
0x180006572  xor     r8d, r8d
0x180006575  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x18000657c  mov     r9d, [rdi+rbx*8]
0x180006580  mov     dword ptr [rsp+78h+var_58], edx
0x180006584  mov     edx, [rbp+arg_20]
0x180006587  mov     rax, [rcx]
0x18000658a  mov     rax, [rax+58h]
0x18000658e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006593  mov     esi, eax
0x180006595  inc     r14d
0x180006598  cmp     r14d, 0Ah
0x18000659c  jl      loc_180006478
0x1800065a2  jmp     short loc_1800065EA
0x1800065a4  test    byte ptr cs:g_dwDebugFlags, 3
0x1800065ab  jz      short loc_1800065EA
0x1800065ad  mov     rcx, cs:g_pDebug
0x1800065b4  lea     r9, aWamregmetabase_0; "WamRegMetabaseConfig::UpdateMD"
0x1800065bb  mov     [rsp+78h+var_40], eax
0x1800065bf  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconf"...
0x1800065c6  mov     eax, [rdi+rbx*8]
0x1800065c9  mov     r8d, 0D6h
0x1800065cf  mov     [rsp+78h+var_48], eax
0x1800065d3  lea     rax, aMetabaseSetdat; "Metabase SetData failed. Path = %S, id "...
0x1800065da  mov     [rsp+78h+var_50], r12
0x1800065df  mov     [rsp+78h+var_58], rax
0x1800065e4  call    cs:__imp_PuDbgPrint
0x1800065ea  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x1800065f1  mov     edx, [rbp+arg_20]
0x1800065f4  mov     rax, [rcx]
0x1800065f7  mov     rax, [rax+90h]
0x1800065fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006603  jmp     short loc_180006644
0x180006605  test    byte ptr cs:g_dwDebugFlags, 3
0x18000660c  jz      short loc_180006644
0x18000660e  mov     rcx, cs:g_pDebug
0x180006615  lea     r9, aWamregmetabase_0; "WamRegMetabaseConfig::UpdateMD"
0x18000661c  mov     [rsp+78h+var_48], eax
0x180006620  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconf"...
0x180006627  lea     rax, aFailedToOpenMe; "Failed to open metabase path %S, error "...
0x18000662e  mov     [rsp+78h+var_50], r12
0x180006633  mov     r8d, 0F8h
0x180006639  mov     [rsp+78h+var_58], rax
0x18000663e  call    cs:__imp_PuDbgPrint
0x180006644  mov     eax, esi
0x180006646  add     rsp, 78h
0x18000664a  pop     r15
0x18000664c  pop     r14
0x18000664e  pop     r13
0x180006650  pop     r12
0x180006652  pop     rdi
0x180006653  pop     rsi
0x180006654  pop     rbx
0x180006655  pop     rbp
0x180006656  retn
```
