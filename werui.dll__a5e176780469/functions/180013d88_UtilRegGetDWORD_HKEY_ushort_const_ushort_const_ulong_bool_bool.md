# UtilRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong,bool *,bool)

- ea: `0x180013d88`
- end: `0x180013e36`
- name: `?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEBG1KPEA_N_N@Z`
- size: `174`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, bool *, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013ce8`

## callees

- `0x1800098f8`
- `0x180009a78`
- `0x180013d88`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180013e02`
- `ADVAPI32!RegGetValueW` at `0x180013e02`
- `ADVAPI32!RegOpenKeyExW` at `0x180013dcd`
- `ADVAPI32!RegOpenKeyExW` at `0x180013dcd`

## pseudocode

```c
__int64 __fastcall UtilRegGetDWORD(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        bool *a5,
        unsigned int pvData)
{
  unsigned int v6; // ebx
  HKEY *phkResult; // rax
  LSTATUS v8; // eax
  bool v9; // sf
  bool v10; // cc
  LSTATUS ValueW; // eax
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+20h] BYREF

  v6 = 0;
  pcbData = 4;
  pvData = 0;
  hkey = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  v8 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SilentProcessExit",
         0,
         0x101u,
         phkResult);
  v9 = v8 < 0;
  v10 = v8 <= 0;
  if ( !v8 )
  {
    ValueW = RegGetValueW(hkey, 0, L"IsTest", 0x10u, 0, &pvData, &pcbData);
    v9 = ValueW < 0;
    v10 = ValueW <= 0;
    if ( !ValueW )
      goto LABEL_7;
  }
  if ( !v10 )
    v9 = 1;
  if ( v9 )
    pvData = 0;
  else
LABEL_7:
    v6 = pvData;
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  return v6;
}

```

## disassembly

```asm
0x180013d88  mov     rax, rsp
0x180013d8b  mov     [rax+20h], r9d
0x180013d8f  mov     [rax+18h], r8
0x180013d93  push    rbx
0x180013d94  sub     rsp, 40h
0x180013d98  xor     ebx, ebx
0x180013d9a  mov     dword ptr [rax+20h], 4
0x180013da1  lea     rcx, [rax+18h]
0x180013da5  mov     [rax+30h], ebx
0x180013da8  mov     [rax+18h], rbx
0x180013dac  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180013db1  mov     r9d, 101h; samDesired
0x180013db7  mov     [rsp+48h+phkResult], rax; phkResult
0x180013dbc  xor     r8d, r8d; ulOptions
0x180013dbf  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180013dc6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180013dcd  call    cs:__imp_RegOpenKeyExW
0x180013dd3  test    eax, eax
0x180013dd5  jnz     short loc_180013E0C
0x180013dd7  mov     rcx, [rsp+48h+hkey]; hkey
0x180013ddc  lea     rax, [rsp+48h+arg_18]
0x180013de1  mov     [rsp+48h+pcbData], rax; pcbData
0x180013de6  lea     r9d, [rbx+10h]; dwFlags
0x180013dea  lea     rax, [rsp+48h+arg_28]
0x180013def  xor     edx, edx; lpSubKey
0x180013df1  mov     [rsp+48h+pvData], rax; pvData
0x180013df6  lea     r8, aIstest; "IsTest"
0x180013dfd  mov     [rsp+48h+phkResult], rbx; pdwType
0x180013e02  call    cs:__imp_RegGetValueW
0x180013e08  test    eax, eax
0x180013e0a  jz      short loc_180013E20
0x180013e0c  jle     short loc_180013E18
0x180013e0e  movzx   eax, ax
0x180013e11  or      eax, 80070000h
0x180013e16  test    eax, eax
0x180013e18  jns     short loc_180013E20
0x180013e1a  mov     [rsp+48h+arg_28], ebx
0x180013e1e  jmp     short loc_180013E24
0x180013e20  mov     ebx, [rsp+48h+arg_28]
0x180013e24  lea     rcx, [rsp+48h+hkey]
0x180013e29  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180013e2e  mov     eax, ebx
0x180013e30  add     rsp, 40h
0x180013e34  pop     rbx
0x180013e35  retn
```
