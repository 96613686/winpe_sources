# CSilentProcessExitTestAutomation::Initialize(ushort const *)

- ea: `0x180013ce8`
- end: `0x180013d82`
- name: `?Initialize@CSilentProcessExitTestAutomation@@QEAAXPEBG@Z`
- size: `154`
- prototype: `void __fastcall(CSilentProcessExitTestAutomation *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010234`

## callees

- `0x180005c20`
- `0x180005c80`
- `0x180009580`
- `0x1800098f8`
- `0x180013ce8`
- `0x180013d88`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180013d64`
- `ADVAPI32!RegCreateKeyExW` at `0x180013d64`

## pseudocode

```c
void __fastcall CSilentProcessExitTestAutomation::Initialize(
        CSilentProcessExitTestAutomation *this,
        const unsigned __int16 *a2)
{
  const unsigned __int16 *v4; // rdx
  HKEY v5; // rcx
  const unsigned __int16 *v6; // r8
  unsigned int v7; // r9d
  HKEY *phkResult; // rax
  bool *dwOptions; // [rsp+20h] [rbp-58h]
  bool samDesired; // [rsp+28h] [rbp-50h]
  LPCWSTR lpSubKey[5]; // [rsp+50h] [rbp-28h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpSubKey);
  if ( UtilRegGetDWORD(v5, v4, v6, v7, dwOptions, samDesired)
    && (int)tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
              lpSubKey,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SilentProcessExit\\%ls",
              a2) >= 0 )
  {
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(this);
    RegCreateKeyExW(HKEY_CURRENT_USER, lpSubKey[0], 0, 0, 0, 0x20006u, 0, phkResult, 0);
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpSubKey);
}

```

## disassembly

```asm
0x180013ce8  mov     [rsp+arg_0], rbx
0x180013ced  push    rdi
0x180013cee  sub     rsp, 70h
0x180013cf2  mov     rdi, rcx
0x180013cf5  mov     rbx, rdx
0x180013cf8  lea     rcx, [rsp+78h+lpSubKey]; void *
0x180013cfd  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180013d02  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEBG1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong,bool *,bool)
0x180013d07  test    eax, eax
0x180013d09  jz      short loc_180013D6A
0x180013d0b  mov     r8, rbx
0x180013d0e  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180013d15  lea     rcx, [rsp+78h+lpSubKey]
0x180013d1a  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180013d1f  test    eax, eax
0x180013d21  js      short loc_180013D6A
0x180013d23  mov     rcx, rdi
0x180013d26  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180013d2b  mov     rdx, [rsp+78h+lpSubKey]; lpSubKey
0x180013d30  xor     r9d, r9d; lpClass
0x180013d33  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x180013d3c  xor     r8d, r8d; Reserved
0x180013d3f  mov     [rsp+78h+phkResult], rax; phkResult
0x180013d44  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180013d4b  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180013d54  mov     dword ptr [rsp+78h+samDesired], 20006h; samDesired
0x180013d5c  mov     dword ptr [rsp+78h+dwOptions], 0; dwOptions
0x180013d64  call    cs:__imp_RegCreateKeyExW
0x180013d6a  lea     rcx, [rsp+78h+lpSubKey]
0x180013d6f  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180013d74  mov     rbx, [rsp+78h+arg_0]
0x180013d7c  add     rsp, 70h
0x180013d80  pop     rdi
0x180013d81  retn
```
