# CVssRegistryKey::SetBinaryValue(ushort const *,uchar *,ulong)

- ea: `0x140008cd0`
- end: `0x140008f76`
- name: `?SetBinaryValue@CVssRegistryKey@@QEAAXPEBGPEAEK@Z`
- size: `678`
- prototype: `void(CVssRegistryKey *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140008094`

## callees

- `0x140008cd0`
- `0x1400137c0`
- `0x140013cb0`
- `0x140049ec4`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140008e31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140008e31`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008d70`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140008d70`
- `VssTrace!__imp_VssTraceMessage` at `0x140008f6b`
- `VssTrace!__imp_VssTraceMessage` at `0x140008f6b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140008e75`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140008e75`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140008db4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140008db4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008e5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008e5f`

## string_xrefs

- `0x140008cfe`: `CVssRegistryKey::SetBinaryValue`
- `0x140008ebc`: `CVssRegistryKey::SetBinaryValue`
- `0x140008f14`: `RegSetValueExW(0x%08lx,%s,0,REG_BINARY,%p.%lu)`
- `0x140008cf3`: `base\stor\vss\modules\registry\registry.cxx`
- `0x140008eb1`: `base\stor\vss\modules\registry\registry.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssRegistryKey::SetBinaryValue(HKEY *this, const unsigned __int16 *a2, unsigned __int8 *a3)
{
  __int64 v6; // rcx
  int v7; // ebx
  __int64 i; // rbx
  void *v9; // rcx
  LSTATUS v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  HKEY v13; // rsi
  HKEY v14; // rdi
  __int64 v15; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v18; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v19; // [rsp+68h] [rbp-98h]
  unsigned int v20; // [rsp+70h] [rbp-90h]
  int v21; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v22; // [rsp+78h] [rbp-88h]
  unsigned int v23; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  int v25; // [rsp+88h] [rbp-78h]
  __int128 v26; // [rsp+90h] [rbp-70h]
  __int128 v27; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v29; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v30; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v31; // [rsp+D0h] [rbp-30h]
  int v32; // [rsp+D8h] [rbp-28h]
  int v33; // [rsp+DCh] [rbp-24h]
  int v34; // [rsp+E0h] [rbp-20h]
  LPVOID pv[15]; // [rsp+E8h] [rbp-18h] BYREF
  int v36; // [rsp+160h] [rbp+60h]
  __int64 v37; // [rsp+190h] [rbp+90h] BYREF

  v29 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v30 = L"CVssRegistryKey::SetBinaryValue";
  v31 = L"REGREGSC";
  v32 = 362;
  v33 = 11;
  v34 = 255;
  v36 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v17 = 0;
  v22 = L"CVssRegistryKey::SetBinaryValue";
  v18 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v19 = L"REGREGSC";
  v20 = 362;
  v21 = 11;
  TickCount = GetTickCount();
  v25 = 255;
  v16 = 0xFFFFFFFF00000000uLL;
  v28 = 0;
  v26 = 0;
  v27 = 0;
  v37 = 0;
  if ( (int)VssGetTracingContextPerThread(&v37) >= 0 )
  {
    v12 = VssSetTracingContextPerThread(&v16);
    v6 = v28;
    if ( v12 >= 0 )
      v6 = v37;
    v28 = v6;
  }
  else
  {
    v6 = v28;
  }
  if ( v6 )
    v23 = *(_DWORD *)(v6 + 48) + 1;
  else
    v23 = 0;
  v7 = 160;
  if ( v25 != 255 )
    v7 = v25;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v16) )
    VssTraceMessage(v18, v19, v20, v23, v21, v22, L"ENTER", v7, 0);
  if ( HIBYTE(v36) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v9 = pv[i];
      if ( v9 )
      {
        CoTaskMemFree(v9);
        pv[i] = 0;
      }
    }
  }
  v10 = RegSetValueExW(this[1], a2, 0, 3u, a3, 0x48u);
  v11 = v10;
  if ( v10 )
  {
    v13 = this[3];
    v14 = this[1];
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    v29 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v30 = L"CVssRegistryKey::SetBinaryValue";
    v31 = L"REGREGSC";
    v32 = 381;
    v33 = 11;
    v34 = 255;
    v36 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    LODWORD(v15) = 72;
    CVssFunctionTracer::TranslateGenericError(
      &v16,
      &v29,
      v11,
      L"RegSetValueExW(0x%08lx,%s,0,REG_BINARY,%p.%lu)",
      v14,
      v13,
      a3,
      v15);
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v16);
}

```

## disassembly

```asm
0x140008cd0  mov     [rsp-8+arg_8], rbx
0x140008cd5  mov     [rsp-8+arg_10], rsi
0x140008cda  push    rbp
0x140008cdb  push    rdi
0x140008cdc  push    r14
0x140008cde  lea     rbp, [rsp-70h]
0x140008ce3  sub     rsp, 170h
0x140008cea  mov     r14, r8
0x140008ced  mov     rsi, rdx
0x140008cf0  mov     rdi, rcx
0x140008cf3  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x140008cfa  mov     [rbp+80h+var_C0], rax
0x140008cfe  lea     rax, aCvssregistryke_3; "CVssRegistryKey::SetBinaryValue"
0x140008d05  mov     [rbp+80h+var_B8], rax
0x140008d09  lea     rax, aRegregsc; "REGREGSC"
0x140008d10  mov     [rbp+80h+var_B0], rax
0x140008d14  mov     [rbp+80h+var_A8], 16Ah
0x140008d1b  mov     [rbp+80h+var_A4], 0Bh
0x140008d22  mov     [rbp+80h+var_A0], 0FFh
0x140008d29  mov     [rbp+80h+var_20], 1000000h
0x140008d30  xor     edx, edx; Val
0x140008d32  lea     r8d, [rdx+78h]; Size
0x140008d36  lea     rcx, [rbp+80h+pv]; void *
0x140008d3a  call    memset_0
0x140008d3f  mov     [rsp+180h+var_128], 0
0x140008d47  mov     rax, [rbp+80h+var_B8]
0x140008d4b  mov     [rsp+180h+var_108], rax
0x140008d50  mov     rax, [rbp+80h+var_C0]
0x140008d54  mov     [rsp+180h+var_120], rax
0x140008d59  mov     rax, [rbp+80h+var_B0]
0x140008d5d  mov     [rsp+180h+var_118], rax
0x140008d62  mov     eax, [rbp+80h+var_A8]
0x140008d65  mov     [rsp+180h+var_110], eax
0x140008d69  mov     eax, [rbp+80h+var_A4]
0x140008d6c  mov     [rsp+180h+var_10C], eax
0x140008d70  call    cs:__imp_GetTickCount
0x140008d76  mov     [rbp+80h+var_FC], eax
0x140008d79  mov     [rsp+180h+var_12C], 0FFFFFFFFh
0x140008d81  mov     eax, [rbp+80h+var_A0]
0x140008d84  mov     [rbp+80h+var_F8], eax
0x140008d87  mov     [rsp+180h+var_130], 0
0x140008d8f  mov     [rbp+80h+var_D0], 0
0x140008d97  xorps   xmm0, xmm0
0x140008d9a  movups  [rbp+80h+var_F0], xmm0
0x140008d9e  movups  [rbp+80h+var_E0], xmm0
0x140008da2  mov     [rbp+80h+arg_0], 0
0x140008dad  lea     rcx, [rbp+80h+arg_0]
0x140008db4  call    cs:__imp_VssGetTracingContextPerThread
0x140008dba  test    eax, eax
0x140008dbc  jns     loc_140008E70
0x140008dc2  mov     rcx, [rbp+80h+var_D0]
0x140008dc6  test    rcx, rcx
0x140008dc9  jz      loc_140008E92
0x140008dcf  mov     eax, [rcx+30h]
0x140008dd2  inc     eax
0x140008dd4  mov     [rbp+80h+var_100], eax
0x140008dd7  mov     ebx, 0A0h
0x140008ddc  cmp     [rbp+80h+var_F8], 0FFh
0x140008de3  cmovnz  ebx, [rbp+80h+var_F8]
0x140008de7  lea     rcx, [rsp+180h+var_130]; this
0x140008dec  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140008df1  test    eax, eax
0x140008df3  jnz     loc_140008F2D
0x140008df9  cmp     byte ptr [rbp+80h+var_20+3], 0
0x140008dfd  jz      short loc_140008E14
0x140008dff  xor     ebx, ebx
0x140008e01  mov     rcx, [rbp+rbx*8+80h+pv]; pv
0x140008e06  test    rcx, rcx
0x140008e09  jnz     short loc_140008E5F
0x140008e0b  inc     rbx
0x140008e0e  cmp     rbx, 0Fh
0x140008e12  jnz     short loc_140008E01
0x140008e14  mov     [rsp+180h+cbData], 48h ; 'H'; cbData
0x140008e1c  mov     [rsp+180h+lpData], r14; lpData
0x140008e21  mov     r9d, 3; dwType
0x140008e27  xor     r8d, r8d; Reserved
0x140008e2a  mov     rdx, rsi; lpValueName
0x140008e2d  mov     rcx, [rdi+8]; hKey
0x140008e31  call    cs:__imp_RegSetValueExW
0x140008e37  mov     ebx, eax
0x140008e39  test    eax, eax
0x140008e3b  jnz     short loc_140008E9E
0x140008e3d  lea     rcx, [rsp+180h+var_130]; this
0x140008e42  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140008e47  lea     r11, [rsp+180h+var_10]
0x140008e4f  mov     rbx, [r11+28h]
0x140008e53  mov     rsi, [r11+30h]
0x140008e57  mov     rsp, r11
0x140008e5a  pop     r14
0x140008e5c  pop     rdi
0x140008e5d  pop     rbp
0x140008e5e  retn
0x140008e5f  call    cs:__imp_CoTaskMemFree
0x140008e65  mov     [rbp+rbx*8+80h+pv], 0
0x140008e6e  jmp     short loc_140008E0B
0x140008e70  lea     rcx, [rsp+180h+var_130]
0x140008e75  call    cs:__imp_VssSetTracingContextPerThread
0x140008e7b  mov     rcx, [rbp+80h+var_D0]
0x140008e7f  test    eax, eax
0x140008e81  cmovns  rcx, [rbp+80h+arg_0]
0x140008e89  mov     [rbp+80h+var_D0], rcx
0x140008e8d  jmp     loc_140008DC6
0x140008e92  mov     [rbp+80h+var_100], 0
0x140008e99  jmp     loc_140008DD7
0x140008e9e  mov     rsi, [rdi+18h]
0x140008ea2  mov     rdi, [rdi+8]
0x140008ea6  jle     short loc_140008EB1
0x140008ea8  movzx   ebx, ax
0x140008eab  or      ebx, 80070000h
0x140008eb1  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x140008eb8  mov     [rbp+80h+var_C0], rax
0x140008ebc  lea     rax, aCvssregistryke_3; "CVssRegistryKey::SetBinaryValue"
0x140008ec3  mov     [rbp+80h+var_B8], rax
0x140008ec7  lea     rax, aRegregsc; "REGREGSC"
0x140008ece  mov     [rbp+80h+var_B0], rax
0x140008ed2  mov     [rbp+80h+var_A8], 17Dh
0x140008ed9  mov     [rbp+80h+var_A4], 0Bh
0x140008ee0  mov     [rbp+80h+var_A0], 0FFh
0x140008ee7  mov     [rbp+80h+var_20], 1000000h
0x140008eee  xor     edx, edx; Val
0x140008ef0  lea     r8d, [rdx+78h]; Size
0x140008ef4  lea     rcx, [rbp+80h+pv]; void *
0x140008ef8  call    memset_0
0x140008efd  mov     dword ptr [rsp+180h+var_148], 48h ; 'H'
0x140008f05  mov     [rsp+180h+var_150], r14
0x140008f0a  mov     qword ptr [rsp+180h+cbData], rsi
0x140008f0f  mov     [rsp+180h+lpData], rdi
0x140008f14  lea     r9, aRegsetvalueexw_0; "RegSetValueExW(0x%08lx,%s,0,REG_BINARY,"...
0x140008f1b  mov     r8d, ebx
0x140008f1e  lea     rdx, [rbp+80h+var_C0]
0x140008f22  lea     rcx, [rsp+180h+var_130]
0x140008f27  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x140008f2d  mov     [rsp+180h+var_140], 0
0x140008f36  mov     dword ptr [rsp+180h+var_148], ebx
0x140008f3a  lea     rax, aEnter; "ENTER"
0x140008f41  mov     [rsp+180h+var_150], rax
0x140008f46  mov     rax, [rsp+180h+var_108]
0x140008f4b  mov     qword ptr [rsp+180h+cbData], rax
0x140008f50  mov     eax, [rsp+180h+var_10C]
0x140008f54  mov     dword ptr [rsp+180h+lpData], eax
0x140008f58  mov     r9d, [rbp+80h+var_100]
0x140008f5c  mov     r8d, [rsp+180h+var_110]
0x140008f61  mov     rdx, [rsp+180h+var_118]
0x140008f66  mov     rcx, [rsp+180h+var_120]
0x140008f6b  call    cs:__imp_VssTraceMessage
0x140008f71  jmp     loc_140008DF9
```
