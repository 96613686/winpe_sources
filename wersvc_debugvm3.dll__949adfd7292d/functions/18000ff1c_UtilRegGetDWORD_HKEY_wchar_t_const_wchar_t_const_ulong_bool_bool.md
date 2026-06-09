# UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)

- ea: `0x18000ff1c`
- end: `0x18000ffe7`
- name: `?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z`
- size: `203`
- prototype: `unsigned int __usercall@<eax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, unsigned int@<r9d>, bool *, bool)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002ab58`
- `0x18002d084`
- `0x18002f04c`

## callees

- `0x180007cc8`
- `0x18000ff1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ff66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ff66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ffd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ffd2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ffa0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ffa0`

## pseudocode

```c
__int64 __fastcall UtilRegGetDWORD(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValue,
        unsigned int a4,
        bool *a5,
        unsigned int pvData)
{
  unsigned int v7; // esi
  HKEY *phkResult; // rax
  LSTATUS v11; // eax
  bool v12; // sf
  bool v13; // cc
  LSTATUS ValueW; // eax
  HKEY hkey; // [rsp+60h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+20h] BYREF

  pvData = a4;
  pcbData = 4;
  v7 = a4;
  hkey = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  v11 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x101u, phkResult);
  v12 = v11 < 0;
  v13 = v11 <= 0;
  if ( !v11 )
  {
    ValueW = RegGetValueW(hkey, 0, lpValue, 0x10u, 0, &pvData, &pcbData);
    v12 = ValueW < 0;
    v13 = ValueW <= 0;
    if ( !ValueW )
      goto LABEL_7;
  }
  if ( !v13 )
    v12 = 1;
  if ( v12 )
    pvData = v7;
  else
LABEL_7:
    v7 = pvData;
  if ( hkey )
    RegCloseKey(hkey);
  return v7;
}

```

## disassembly

```asm
0x18000ff1c  mov     rax, rsp
0x18000ff1f  mov     [rax+10h], rbx
0x18000ff23  push    rbp
0x18000ff24  push    rsi
0x18000ff25  push    rdi
0x18000ff26  sub     rsp, 40h
0x18000ff2a  mov     rdi, rcx
0x18000ff2d  mov     [rax+30h], r9d
0x18000ff31  lea     rcx, [rax+8]
0x18000ff35  mov     dword ptr [rax+20h], 4
0x18000ff3c  mov     esi, r9d
0x18000ff3f  mov     qword ptr [rax+8], 0
0x18000ff47  mov     rbp, r8
0x18000ff4a  mov     rbx, rdx
0x18000ff4d  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000ff52  mov     r9d, 101h; samDesired
0x18000ff58  mov     [rsp+58h+phkResult], rax; phkResult
0x18000ff5d  xor     r8d, r8d; ulOptions
0x18000ff60  mov     rdx, rbx; lpSubKey
0x18000ff63  mov     rcx, rdi; hKey
0x18000ff66  call    cs:__imp_RegOpenKeyExW
0x18000ff6c  test    eax, eax
0x18000ff6e  jnz     short loc_18000FFAA
0x18000ff70  mov     rcx, [rsp+58h+hkey]; hkey
0x18000ff75  lea     rax, [rsp+58h+arg_18]
0x18000ff7a  mov     [rsp+58h+pcbData], rax; pcbData
0x18000ff7f  mov     r9d, 10h; dwFlags
0x18000ff85  lea     rax, [rsp+58h+arg_28]
0x18000ff8d  mov     r8, rbp; lpValue
0x18000ff90  mov     [rsp+58h+pvData], rax; pvData
0x18000ff95  xor     edx, edx; lpSubKey
0x18000ff97  mov     [rsp+58h+phkResult], 0; pdwType
0x18000ffa0  call    cs:__imp_RegGetValueW
0x18000ffa6  test    eax, eax
0x18000ffa8  jz      short loc_18000FFC1
0x18000ffaa  jle     short loc_18000FFB6
0x18000ffac  movzx   eax, ax
0x18000ffaf  or      eax, 80070000h
0x18000ffb4  test    eax, eax
0x18000ffb6  jns     short loc_18000FFC1
0x18000ffb8  mov     [rsp+58h+arg_28], esi
0x18000ffbf  jmp     short loc_18000FFC8
0x18000ffc1  mov     esi, [rsp+58h+arg_28]
0x18000ffc8  mov     rcx, [rsp+58h+hkey]; hKey
0x18000ffcd  test    rcx, rcx
0x18000ffd0  jz      short loc_18000FFD8
0x18000ffd2  call    cs:__imp_RegCloseKey
0x18000ffd8  mov     rbx, [rsp+58h+arg_8]
0x18000ffdd  mov     eax, esi
0x18000ffdf  add     rsp, 40h
0x18000ffe3  pop     rdi
0x18000ffe4  pop     rsi
0x18000ffe5  pop     rbp
0x18000ffe6  retn
```
