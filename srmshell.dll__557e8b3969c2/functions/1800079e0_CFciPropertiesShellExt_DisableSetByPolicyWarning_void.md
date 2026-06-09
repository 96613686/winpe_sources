# CFciPropertiesShellExt::DisableSetByPolicyWarning(void)

- ea: `0x1800079e0`
- end: `0x180007cba`
- name: `?DisableSetByPolicyWarning@CFciPropertiesShellExt@@CAXXZ`
- size: `730`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ace8`

## callees

- `0x1800054c0`
- `0x1800079e0`
- `0x1800161e8`
- `0x18001623c`
- `0x180016564`
- `0x180019b84`
- `0x18001a280`
- `0x18001a540`
- `0x18001ae30`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007bbe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007bbe`

## string_xrefs

- `0x180007b0c`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x180007b18`: `CSrmRegistryKey::SetValue`
- `0x180007c9e`: `RegSetValueExW(0x%08lx,%s,0,REG_DWORD,%ld)`

## pseudocode

```c
void CFciPropertiesShellExt::DisableSetByPolicyWarning(void)
{
  unsigned __int16 i; // cx
  int v1; // ebx
  int v2; // edi
  unsigned __int16 *Buffer; // rsi
  HKEY v4; // r14
  __int64 v5; // rax
  BYTE Data[8]; // [rsp+48h] [rbp-310h] BYREF
  __int64 v7; // [rsp+50h] [rbp-308h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-300h]
  __int64 v9; // [rsp+60h] [rbp-2F8h] BYREF
  int v10; // [rsp+68h] [rbp-2F0h] BYREF
  const unsigned __int16 **v11; // [rsp+70h] [rbp-2E8h]
  const unsigned __int16 *v12; // [rsp+78h] [rbp-2E0h] BYREF
  const wchar_t *v13; // [rsp+80h] [rbp-2D8h]
  const unsigned __int16 *v14; // [rsp+88h] [rbp-2D0h]
  int v15; // [rsp+90h] [rbp-2C8h]
  int v16; // [rsp+94h] [rbp-2C4h]
  int v17; // [rsp+98h] [rbp-2C0h]
  _QWORD v18[12]; // [rsp+A0h] [rbp-2B8h] BYREF
  int v19; // [rsp+100h] [rbp-258h]
  _com_error *v20; // [rsp+108h] [rbp-250h] BYREF
  const exception *v21; // [rsp+110h] [rbp-248h] BYREF
  _BYTE v22[152]; // [rsp+118h] [rbp-240h] BYREF
  _QWORD v23[5]; // [rsp+1B0h] [rbp-1A8h] BYREF
  unsigned int v24; // [rsp+1DCh] [rbp-17Ch]
  _QWORD v25[22]; // [rsp+260h] [rbp-F8h] BYREF

  *(_QWORD *)Data = &v12;
  v12 = L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp";
  v13 = L"CFciPropertiesShellExt::DisableSetByPolicyWarning";
  v14 = L"FCIPROPC";
  v15 = 248;
  v16 = 17;
  v17 = 255;
  v19 = 0x1000000;
  memset_0(v18, 0, sizeof(v18));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v23, (const struct CSrmDebugInfo *)&v12, 0);
  try
  {
    v9 = 0;
    hKey = 0;
    v7 = 131334;
    if ( !CSrmRegistryKey::Open(
            (CSrmRegistryKey *)&v7,
            HKEY_CURRENT_USER,
            L"%s",
            L"Software\\Microsoft\\Windows\\CurrentVersion\\FCI") )
      CSrmRegistryKey::Create(
        (CSrmRegistryKey *)&v7,
        HKEY_CURRENT_USER,
        L"%s",
        L"Software\\Microsoft\\Windows\\CurrentVersion\\FCI");
    *(_DWORD *)Data = 0;
    v11 = &v12;
    v12 = L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp";
    v13 = L"CSrmRegistryKey::SetValue";
    v14 = L"SRMREGSC";
    v15 = 302;
    v16 = 17;
    v17 = 255;
    v19 = 0x1000000;
    for ( i = 0; i < 0xCu; ++i )
      v18[i] = 0;
    CSrmFunctionTracer::CSrmFunctionTracer((__int64)v25, (const struct CSrmDebugInfo *)&v12, 0);
    v1 = RegSetValueExW(hKey, L"SetByPolicyWarningEnable", 0, 4u, Data, 4u);
    if ( v1 )
    {
      v2 = *(_DWORD *)Data;
      Buffer = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)&v9);
      v4 = hKey;
      if ( v1 > 0 )
        v1 = (unsigned __int16)v1 | 0x80070000;
      v11 = (const unsigned __int16 **)v22;
      v5 = CSrmDebugInfo::CSrmDebugInfo(
             (__int64)v22,
             (__int64)L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
             (__int64)L"SRMREGSC",
             (__int64)L"CSrmRegistryKey::SetValue",
             319,
             17);
      CSrmFunctionTracer::TranslateGenericError(
        v25,
        v5,
        (unsigned int)v1,
        L"RegSetValueExW(0x%08lx,%s,0,REG_DWORD,%ld)",
        v4,
        Buffer,
        v2);
    }
    v25[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v25);
    CSrmRegistryKey::~CSrmRegistryKey((LPVOID *)&v7);
  }
  catch ( long v10 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)v23,
      v10,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp",
      L"FCIPROPC",
      L"CFciPropertiesShellExt::DisableSetByPolicyWarning",
      0x106u,
      v24);
  }
  catch ( _com_error *v20 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)v23,
      v20,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp",
      L"FCIPROPC",
      L"CFciPropertiesShellExt::DisableSetByPolicyWarning",
      0x106u,
      v24);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)v23,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp",
      L"FCIPROPC",
      L"CFciPropertiesShellExt::DisableSetByPolicyWarning",
      0x106u,
      v24);
  }
  catch ( const exception *v21 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)v23,
      v21,
      L"base\\fs\\fsrm\\clients\\srmshell\\fciprops.cpp",
      L"FCIPROPC",
      L"CFciPropertiesShellExt::DisableSetByPolicyWarning",
      0x106u,
      v24);
  }
  v9 = 0;
  hKey = 0;
}

```

## disassembly

```asm
0x1800079e0  push    rbx
0x1800079e2  push    rsi
0x1800079e3  push    rdi
0x1800079e4  push    r12
0x1800079e6  push    r13
0x1800079e8  push    r14
0x1800079ea  sub     rsp, 328h
0x1800079f1  mov     rax, cs:__security_cookie
0x1800079f8  xor     rax, rsp
0x1800079fb  mov     [rsp+358h+var_48], rax
0x180007a03  lea     rax, [rsp+358h+var_2E0]
0x180007a08  mov     qword ptr [rsp+358h+Data], rax
0x180007a0d  lea     rax, aBaseFsFsrmClie_1; "base\\fs\\fsrm\\clients\\srmshell\\fcip"...
0x180007a14  mov     [rsp+358h+var_2E0], rax
0x180007a19  lea     rax, aCfciproperties_2; "CFciPropertiesShellExt::DisableSetByPol"...
0x180007a20  mov     [rsp+358h+var_2D8], rax
0x180007a28  lea     rax, aFcipropc; "FCIPROPC"
0x180007a2f  mov     [rsp+358h+var_2D0], rax
0x180007a37  mov     [rsp+358h+var_2C8], 0F8h
0x180007a42  mov     esi, 11h
0x180007a47  mov     [rsp+358h+var_2C4], esi
0x180007a4e  mov     edi, 0FFh
0x180007a53  mov     [rsp+358h+var_2C0], edi
0x180007a5a  mov     [rsp+358h+var_258], 1000000h
0x180007a65  xor     edx, edx; Val
0x180007a67  lea     r8d, [rsi+4Fh]; Size
0x180007a6b  lea     rcx, [rsp+358h+var_2B8]; void *
0x180007a73  call    memset_0
0x180007a78  nop
0x180007a79  xor     r8d, r8d
0x180007a7c  lea     rdx, [rsp+358h+var_2E0]
0x180007a81  lea     rcx, [rsp+358h+var_1A8]
0x180007a89  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180007a8e  nop
0x180007a8f  mov     [rsp+358h+var_2F8], 0
0x180007a98  mov     [rsp+358h+hKey], 0
0x180007aa1  mov     [rsp+358h+var_304], 0
0x180007aa9  mov     [rsp+358h+var_308], 20006h
0x180007ab1  mov     [rsp+358h+var_308], 20106h
0x180007ab9  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180007ac0  lea     r8, aS_0; "%s"
0x180007ac7  mov     rbx, 0FFFFFFFF80000001h
0x180007ace  mov     rdx, rbx; hKey
0x180007ad1  lea     rcx, [rsp+358h+var_308]; this
0x180007ad6  call    ?Open@CSrmRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CSrmRegistryKey::Open(HKEY__ *,ushort const *,...)
0x180007adb  test    al, al
0x180007add  jnz     short loc_180007AFA
0x180007adf  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180007ae6  lea     r8, aS_0; "%s"
0x180007aed  mov     rdx, rbx; hKey
0x180007af0  lea     rcx, [rsp+358h+var_308]; this
0x180007af5  call    ?Create@CSrmRegistryKey@@QEAAXPEAUHKEY__@@PEBGZZ; CSrmRegistryKey::Create(HKEY__ *,ushort const *,...)
0x180007afa  mov     dword ptr [rsp+358h+Data], 0
0x180007b02  lea     rdx, [rsp+358h+var_2E0]
0x180007b07  mov     [rsp+358h+var_2E8], rdx
0x180007b0c  lea     r12, aBaseFsFsrmUtil_3; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x180007b13  mov     [rsp+358h+var_2E0], r12
0x180007b18  lea     r13, aCsrmregistryke_2; "CSrmRegistryKey::SetValue"
0x180007b1f  mov     [rsp+358h+var_2D8], r13
0x180007b27  lea     rax, aSrmregsc; "SRMREGSC"
0x180007b2e  mov     [rsp+358h+var_2D0], rax
0x180007b36  mov     [rsp+358h+var_2C8], 12Eh
0x180007b41  mov     [rsp+358h+var_2C4], esi
0x180007b48  mov     [rsp+358h+var_2C0], edi
0x180007b4f  xor     eax, eax
0x180007b51  mov     word ptr [rsp+358h+var_258], ax
0x180007b59  mov     byte ptr [rsp+358h+var_258+2], al
0x180007b60  mov     byte ptr [rsp+358h+var_258+3], 1
0x180007b68  xor     ecx, ecx
0x180007b6a  mov     [rsp+358h+var_318], cx
0x180007b6f  cmp     cx, 0Ch
0x180007b73  jnb     short loc_180007B89
0x180007b75  movzx   eax, cx
0x180007b78  mov     [rsp+rax*8+358h+var_2B8], 0
0x180007b84  inc     cx
0x180007b87  jmp     short loc_180007B6A
0x180007b89  xor     r8d, r8d
0x180007b8c  lea     rcx, [rsp+358h+var_F8]
0x180007b94  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180007b99  nop
0x180007b9a  mov     r9d, 4; dwType
0x180007ba0  mov     [rsp+358h+cbData], r9d; cbData
0x180007ba5  lea     rax, [rsp+358h+Data]
0x180007baa  mov     [rsp+358h+lpData], rax; lpData
0x180007baf  xor     r8d, r8d; Reserved
0x180007bb2  lea     rdx, ValueName; "SetByPolicyWarningEnable"
0x180007bb9  mov     rcx, [rsp+358h+hKey]; hKey
0x180007bbe  call    cs:__imp_RegSetValueExW
0x180007bc4  mov     ebx, eax
0x180007bc6  test    eax, eax
0x180007bc8  jnz     short loc_180007C35
0x180007bca  lea     rbx, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180007bd1  mov     [rsp+358h+var_F8], rbx
0x180007bd9  lea     rcx, [rsp+358h+var_F8]; this
0x180007be1  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180007be6  nop
0x180007be7  lea     rcx, [rsp+358h+var_308]; this
0x180007bec  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x180007bf1  nop
0x180007bf2  jmp     short loc_180007BFB
0x180007bf4  lea     rbx, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180007bfb  mov     [rsp+358h+var_1A8], rbx
0x180007c03  lea     rcx, [rsp+358h+var_1A8]; this
0x180007c0b  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180007c10  mov     rcx, [rsp+358h+var_48]
0x180007c18  xor     rcx, rsp; StackCookie
0x180007c1b  call    __security_check_cookie
0x180007c20  add     rsp, 328h
0x180007c27  pop     r14
0x180007c29  pop     r13
0x180007c2b  pop     r12
0x180007c2d  pop     rdi
0x180007c2e  pop     rsi
0x180007c2f  pop     rbx
0x180007c30  retn
0x180007c31  jmp     short loc_180007BF4
0x180007c33  jmp     short loc_180007BF4
0x180007c35  mov     edi, dword ptr [rsp+358h+Data]
0x180007c39  lea     rcx, [rsp+358h+var_2F8]; this
0x180007c3e  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x180007c43  mov     rsi, rax
0x180007c46  mov     r14, [rsp+358h+hKey]
0x180007c4b  test    ebx, ebx
0x180007c4d  jle     short loc_180007C58
0x180007c4f  movzx   ebx, bx
0x180007c52  or      ebx, 80070000h
0x180007c58  lea     rax, [rsp+358h+var_240]
0x180007c60  mov     [rsp+358h+var_2E8], rax
0x180007c65  mov     [rsp+358h+cbData], 11h
0x180007c6d  mov     dword ptr [rsp+358h+lpData], 13Fh
0x180007c75  mov     r9, r13
0x180007c78  lea     r8, aSrmregsc; "SRMREGSC"
0x180007c7f  mov     rdx, r12
0x180007c82  lea     rcx, [rsp+358h+var_240]
0x180007c8a  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180007c8f  nop
0x180007c90  mov     [rsp+358h+var_328], edi
0x180007c94  mov     qword ptr [rsp+358h+cbData], rsi
0x180007c99  mov     [rsp+358h+lpData], r14
0x180007c9e  lea     r9, aRegsetvalueexw; "RegSetValueExW(0x%08lx,%s,0,REG_DWORD,%"...
0x180007ca5  mov     r8d, ebx
0x180007ca8  mov     rdx, rax
0x180007cab  lea     rcx, [rsp+358h+var_F8]
0x180007cb3  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
```
