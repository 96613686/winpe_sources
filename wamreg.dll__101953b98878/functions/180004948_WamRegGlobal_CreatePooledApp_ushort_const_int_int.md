# WamRegGlobal::CreatePooledApp(ushort const *,int,int)

- ea: `0x180004948`
- end: `0x180004ac4`
- name: `?CreatePooledApp@WamRegGlobal@@QEAAJPEBGHH@Z`
- size: `380`
- prototype: `__int64 __fastcall(WamRegGlobal *this, const unsigned __int16 *, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180001ed0`
- `0x180004fd4`

## callees

- `0x180004948`
- `0x180006408`
- `0x180006850`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180004a9b`
- `iisutil!PuDbgPrint` at `0x180004a9b`

## string_xrefs

- `0x180004a84`: `Failed to create in proc application. path = %S, error = %08x\n`
- `0x180004a72`: `WamRegGlobal::CreatePooledApp`

## pseudocode

```c
__int64 __fastcall WamRegGlobal::CreatePooledApp(WamRegGlobal *this, const unsigned __int16 *a2, int a3, int a4)
{
  int updated; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-E0h]
  _QWORD v9[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v10; // [rsp+50h] [rbp-B0h]
  __int128 v11; // [rsp+60h] [rbp-A0h]
  __int128 v12; // [rsp+70h] [rbp-90h]
  __int128 v13; // [rsp+80h] [rbp-80h]
  __int128 v14; // [rsp+90h] [rbp-70h]
  __int128 v15; // [rsp+A0h] [rbp-60h]
  __int128 v16; // [rsp+B0h] [rbp-50h]
  __int128 v17; // [rsp+C0h] [rbp-40h]
  __int128 v18; // [rsp+D0h] [rbp-30h]
  __int128 v19; // [rsp+E0h] [rbp-20h]
  __int128 v20; // [rsp+F0h] [rbp-10h]
  __int128 v21; // [rsp+100h] [rbp+0h]
  __int128 v22; // [rsp+110h] [rbp+10h]
  __int128 v23; // [rsp+120h] [rbp+20h]

  v9[0] = WamRegMetabaseConfig::m_rgMDPropTemplate;
  v11 = xmmword_180009770;
  v9[1] = a2;
  DWORD2(v11) = 1;
  LODWORD(v11) = a3 == 0 ? 2 : 0;
  v10 = xmmword_180009760;
  LODWORD(v10) = 1;
  v13 = xmmword_180009790;
  v12 = xmmword_180009780;
  v15 = xmmword_1800097B0;
  v14 = xmmword_1800097A0;
  v17 = xmmword_1800097D0;
  v16 = xmmword_1800097C0;
  v19 = xmmword_1800097F0;
  v18 = xmmword_1800097E0;
  v21 = xmmword_180009810;
  v20 = xmmword_180009800;
  v23 = xmmword_180009830;
  v22 = xmmword_180009820;
  if ( !a4 )
  {
    LODWORD(v19) = 1;
    *((_QWORD *)&v18 + 1) = &qword_180009278;
  }
  updated = WamRegMetabaseConfig::UpdateMD((WamRegMetabaseConfig *)1, (struct MDPropItem *)v9, 1u, a2, v8);
  v6 = updated;
  if ( updated < 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfunc.cpp",
      1088,
      "WamRegGlobal::CreatePooledApp",
      "Failed to create in proc application. path = %S, error = %08x\n",
      a2,
      updated);
  return v6;
}

```

## disassembly

```asm
0x180004948  mov     [rsp-8+arg_0], rbx
0x18000494d  mov     [rsp-8+arg_10], rdi
0x180004952  push    rbp
0x180004953  lea     rbp, [rsp-40h]
0x180004958  sub     rsp, 140h
0x18000495f  mov     rax, cs:__security_cookie
0x180004966  xor     rax, rsp
0x180004969  mov     [rbp+40h+var_10], rax
0x18000496d  movaps  xmm0, cs:?m_rgMDPropTemplate@WamRegMetabaseConfig@@0QBUMDPropItem@@B; MDPropItem const near * const WamRegMetabaseConfig::m_rgMDPropTemplate
0x180004974  neg     r8d
0x180004977  movaps  xmm1, cs:xmmword_180009760
0x18000497e  mov     ecx, 1; this
0x180004983  movups  [rsp+140h+var_100], xmm0
0x180004988  sbb     eax, eax
0x18000498a  mov     rdi, rdx
0x18000498d  movaps  xmm0, cs:xmmword_180009770
0x180004994  not     eax
0x180004996  movups  [rsp+140h+var_E0], xmm0
0x18000499b  and     eax, 2
0x18000499e  mov     qword ptr [rsp+140h+var_100+8], rdx
0x1800049a3  movaps  xmm0, cs:xmmword_180009790
0x1800049aa  mov     dword ptr [rsp+140h+var_E0+8], ecx
0x1800049ae  mov     dword ptr [rsp+140h+var_E0], eax
0x1800049b2  movups  [rsp+140h+var_F0], xmm1
0x1800049b7  mov     dword ptr [rsp+140h+var_F0], ecx
0x1800049bb  movaps  xmm1, cs:xmmword_180009780
0x1800049c2  movups  [rbp+40h+var_C0], xmm0
0x1800049c6  movaps  xmm0, cs:xmmword_1800097B0
0x1800049cd  movups  [rsp+140h+var_D0], xmm1
0x1800049d2  movaps  xmm1, cs:xmmword_1800097A0
0x1800049d9  movups  [rbp+40h+var_A0], xmm0
0x1800049dd  movaps  xmm0, cs:xmmword_1800097D0
0x1800049e4  movups  [rbp+40h+var_B0], xmm1
0x1800049e8  movaps  xmm1, cs:xmmword_1800097C0
0x1800049ef  movups  [rbp+40h+var_80], xmm0
0x1800049f3  movaps  xmm0, cs:xmmword_1800097F0
0x1800049fa  movups  [rbp+40h+var_90], xmm1
0x1800049fe  movaps  xmm1, cs:xmmword_1800097E0
0x180004a05  movups  [rbp+40h+var_60], xmm0
0x180004a09  movaps  xmm0, cs:xmmword_180009810
0x180004a10  movups  [rbp+40h+var_70], xmm1
0x180004a14  movaps  xmm1, cs:xmmword_180009800
0x180004a1b  movups  [rbp+40h+var_40], xmm0
0x180004a1f  movaps  xmm0, cs:xmmword_180009830
0x180004a26  movups  [rbp+40h+var_50], xmm1
0x180004a2a  movaps  xmm1, cs:xmmword_180009820
0x180004a31  movups  [rbp+40h+var_20], xmm0
0x180004a35  movups  [rbp+40h+var_30], xmm1
0x180004a39  test    r9d, r9d
0x180004a3c  jnz     short loc_180004A4C
0x180004a3e  lea     rax, qword_180009278
0x180004a45  mov     dword ptr [rbp+40h+var_60], ecx
0x180004a48  mov     qword ptr [rbp+40h+var_70+8], rax
0x180004a4c  mov     r9, rdi; unsigned __int16 *
0x180004a4f  lea     rdx, [rsp+140h+var_100]; struct MDPropItem *
0x180004a54  mov     r8d, ecx; unsigned int
0x180004a57  call    ?UpdateMD@WamRegMetabaseConfig@@QEAAJPEAUMDPropItem@@KPEBGH@Z; WamRegMetabaseConfig::UpdateMD(MDPropItem *,ulong,ushort const *,int)
0x180004a5c  mov     ebx, eax
0x180004a5e  test    eax, eax
0x180004a60  jns     short loc_180004AA1
0x180004a62  test    byte ptr cs:g_dwDebugFlags, 3
0x180004a69  jz      short loc_180004AA1
0x180004a6b  mov     rcx, cs:g_pDebug
0x180004a72  lea     r9, aWamregglobalCr; "WamRegGlobal::CreatePooledApp"
0x180004a79  mov     [rsp+140h+var_110], eax
0x180004a7d  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfun"...
0x180004a84  lea     rax, aFailedToCreate_2; "Failed to create in proc application. p"...
0x180004a8b  mov     [rsp+140h+var_118], rdi
0x180004a90  mov     r8d, 440h
0x180004a96  mov     [rsp+140h+var_120], rax
0x180004a9b  call    cs:__imp_PuDbgPrint
0x180004aa1  mov     eax, ebx
0x180004aa3  mov     rcx, [rbp+40h+var_10]
0x180004aa7  xor     rcx, rsp; StackCookie
0x180004aaa  call    __security_check_cookie
0x180004aaf  lea     r11, [rsp+140h+var_s0]
0x180004ab7  mov     rbx, [r11+10h]
0x180004abb  mov     rdi, [r11+20h]
0x180004abf  mov     rsp, r11
0x180004ac2  pop     rbp
0x180004ac3  retn
```
