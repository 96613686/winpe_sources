# WamRegMetabaseConfig::MDGetDWORD(ushort const *,ulong,ulong *)

- ea: `0x180005a50`
- end: `0x180005b89`
- name: `?MDGetDWORD@WamRegMetabaseConfig@@QEAAJPEBGKPEAK@Z`
- size: `313`
- prototype: `__int64 __fastcall(WamRegMetabaseConfig *__hidden this, const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001ed0`
- `0x180002110`
- `0x180002460`
- `0x1800029e0`
- `0x1800030b0`
- `0x180003d80`
- `0x180004acc`
- `0x180004fd4`
- `0x180005584`

## callees

- `0x180005a50`
- `0x180007010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180005b57`
- `iisutil!PuDbgPrint` at `0x180005b57`

## string_xrefs

- `0x180005b31`: `inetsrv\iis\svcs\wam\wamreg\mdconfig.cpp`
- `0x180005b40`: `Get MD_APP_ISOLATED failed on MD path %S, id %d, error = %08x\n`
- `0x180005b26`: `WamRegMetabaseConfig::MDGetDWORD`

## pseudocode

```c
__int64 __fastcall WamRegMetabaseConfig::MDGetDWORD(
        WamRegMetabaseConfig *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned int *a4)
{
  LPVOID v4; // rdi
  int v7; // ebx
  int v8; // eax
  __int128 v10; // [rsp+40h] [rbp-30h] BYREF
  __int128 v11; // [rsp+50h] [rbp-20h]
  __int64 v12; // [rsp+60h] [rbp-10h]
  int v13; // [rsp+90h] [rbp+20h] BYREF
  int v14; // [rsp+94h] [rbp+24h]
  unsigned int v15; // [rsp+A0h] [rbp+30h] BYREF

  v14 = HIDWORD(this);
  v4 = WamRegMetabaseConfig::m_pMetabase;
  v12 = 0;
  v13 = 0;
  v15 = 0;
  v10 = 0;
  v11 = 0;
  v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *, __int64, int, unsigned int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 136LL))(
         WamRegMetabaseConfig::m_pMetabase,
         0,
         a2,
         1,
         30000,
         &v15);
  if ( v7 >= 0 )
  {
    *(_QWORD *)&v10 = 2104;
    *((_QWORD *)&v10 + 1) = 0x100000064LL;
    LODWORD(v11) = 4;
    *((_QWORD *)&v11 + 1) = a4;
    v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int128 *, int *))(*(_QWORD *)v4 + 80LL))(
           v4,
           v15,
           0,
           &v10,
           &v13);
    v7 = v8;
    if ( v8 < 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconfig.cpp",
        672,
        "WamRegMetabaseConfig::MDGetDWORD",
        "Get MD_APP_ISOLATED failed on MD path %S, id %d, error = %08x\n",
        a2,
        2104,
        v8);
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v4 + 144LL))(v4, v15);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180005a50  mov     r11, rsp
0x180005a53  mov     [r11+10h], rbx
0x180005a57  mov     [r11+20h], rsi
0x180005a5b  mov     [r11+18h], r8d
0x180005a5f  mov     [r11+8], rcx
0x180005a63  push    rbp
0x180005a64  push    rdi
0x180005a65  push    r14
0x180005a67  mov     rbp, rsp
0x180005a6a  sub     rsp, 70h
0x180005a6e  mov     rdi, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180005a75  lea     rcx, [rbp+arg_10]
0x180005a79  xor     eax, eax
0x180005a7b  mov     [r11-60h], rcx
0x180005a7f  xorps   xmm0, xmm0
0x180005a82  mov     [rbp+var_10], rax
0x180005a86  mov     [rbp+arg_0], eax
0x180005a89  mov     r14, r9
0x180005a8c  mov     [rbp+arg_10], 0
0x180005a93  mov     rsi, rdx
0x180005a96  movups  [rbp+var_30], xmm0
0x180005a9a  mov     r8, rdx
0x180005a9d  mov     r9d, 1
0x180005aa3  movups  [rbp+var_20], xmm0
0x180005aa7  mov     rax, [rdi]
0x180005aaa  xor     edx, edx
0x180005aac  mov     rcx, rdi
0x180005aaf  mov     dword ptr [rsp+70h+var_50], 7530h
0x180005ab7  mov     rax, [rax+88h]
0x180005abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ac3  mov     ebx, eax
0x180005ac5  test    eax, eax
0x180005ac7  js      loc_180005B72
0x180005acd  mov     edx, [rbp+arg_10]
0x180005ad0  lea     rcx, [rbp+arg_0]
0x180005ad4  mov     qword ptr [rbp+var_30], 838h
0x180005adc  lea     r9, [rbp+var_30]
0x180005ae0  mov     dword ptr [rbp+var_30+8], 64h ; 'd'
0x180005ae7  xor     r8d, r8d
0x180005aea  mov     dword ptr [rbp+var_30+0Ch], 1
0x180005af1  mov     dword ptr [rbp+var_20], 4
0x180005af8  mov     qword ptr [rbp+var_20+8], r14
0x180005afc  mov     rax, [rdi]
0x180005aff  mov     [rsp+70h+var_50], rcx
0x180005b04  mov     rcx, rdi
0x180005b07  mov     rax, [rax+50h]
0x180005b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b10  mov     ebx, eax
0x180005b12  test    eax, eax
0x180005b14  jns     short loc_180005B5D
0x180005b16  test    byte ptr cs:g_dwDebugFlags, 3
0x180005b1d  jz      short loc_180005B5D
0x180005b1f  mov     rcx, cs:g_pDebug
0x180005b26  lea     r9, aWamregmetabase_2; "WamRegMetabaseConfig::MDGetDWORD"
0x180005b2d  mov     [rsp+70h+var_38], eax
0x180005b31  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconf"...
0x180005b38  mov     [rsp+70h+var_40], 838h
0x180005b40  lea     rax, aGetMdAppIsolat; "Get MD_APP_ISOLATED failed on MD path %"...
0x180005b47  mov     [rsp+70h+var_48], rsi
0x180005b4c  mov     r8d, 2A0h
0x180005b52  mov     [rsp+70h+var_50], rax
0x180005b57  call    cs:__imp_PuDbgPrint
0x180005b5d  mov     rax, [rdi]
0x180005b60  mov     rcx, rdi
0x180005b63  mov     edx, [rbp+arg_10]
0x180005b66  mov     rax, [rax+90h]
0x180005b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b72  lea     r11, [rsp+70h+var_s0]
0x180005b77  mov     eax, ebx
0x180005b79  mov     rbx, [r11+28h]
0x180005b7d  mov     rsi, [r11+38h]
0x180005b81  mov     rsp, r11
0x180005b84  pop     r14
0x180005b86  pop     rdi
0x180005b87  pop     rbp
0x180005b88  retn
```
