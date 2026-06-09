# StSetPlapKey(int,ushort const *)

- ea: `0x1800d2e84`
- end: `0x1800d30e1`
- name: `?StSetPlapKey@@YAKHPEBG@Z`
- size: `605`
- prototype: `unsigned int(int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800415c0`
- `0x1801ffc98`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180073fc8`
- `0x1800d2e84`
- `0x180106340`
- `0x180107330`
- `0x180108234`
- `0x1801ff59c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800d2f7c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800d2f7c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d304e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d304e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d3091`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d3091`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d2fd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d30b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d2fd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d30b7`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x1800d2f5f`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x1800d2f5f`

## pseudocode

```c
__int64 __fastcall StSetPlapKey(int a1, const unsigned __int16 *a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  HKEY v8; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  memset_0(SubKey, 0, 0x208u);
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 52, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 105) >= 4u && (*((_BYTE *)v4 + 108) & 1) != 0 )
      WPP_SF_dS(
        (unsigned int)v4[12],
        53,
        (unsigned int)&WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids,
        a1,
        (__int64)a2);
  }
  if ( !IsGetCustomWfdSettingsRegPathPresent()
    || (int)GetCustomRegRootPath(SubKey, 260, L"Software\\Microsoft\\Wlansvc") < 0 )
  {
    v5 = _o_wcscpy_s(SubKey, 260, L"Software\\Microsoft\\Wlansvc");
    v6 = v5;
    if ( v5 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_17;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v5);
LABEL_16:
      v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_17:
      v8 = hKey;
      goto LABEL_18;
    }
  }
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, &hKey);
  if ( v6 )
    goto LABEL_16;
  if ( a1 )
    *(_DWORD *)Data = 1;
  v6 = RegSetValueExW(hKey, L"L2NAWLANMode", 0, 4u, Data, 4u);
  if ( v6 )
    goto LABEL_16;
  v8 = hKey;
  if ( !hKey )
    goto LABEL_20;
  if ( a1 == 1 )
  {
    RegCloseKey(hKey);
    hKey = 0;
    v6 = AddToListOfPlapProfiles(a2);
    goto LABEL_16;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_18:
  if ( v8 )
  {
    RegCloseKey(v8);
LABEL_20:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 105) >= 4u && (*((_BYTE *)v7 + 108) & 1) != 0 )
    WPP_SF_d(v7[12], 54, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1800d2e84  mov     [rsp-8+arg_10], rbx
0x1800d2e89  mov     [rsp-8+arg_18], rsi
0x1800d2e8e  push    rbp
0x1800d2e8f  push    rdi
0x1800d2e90  push    r13
0x1800d2e92  lea     rbp, [rsp-160h]
0x1800d2e9a  sub     rsp, 260h
0x1800d2ea1  mov     rax, cs:__security_cookie
0x1800d2ea8  xor     rax, rsp
0x1800d2eab  mov     [rbp+170h+var_20], rax
0x1800d2eb2  mov     rsi, rdx
0x1800d2eb5  mov     [rsp+270h+hKey], 0
0x1800d2ebe  mov     edi, ecx
0x1800d2ec0  mov     dword ptr [rsp+270h+Data], 0
0x1800d2ec8  xor     edx, edx; Val
0x1800d2eca  lea     rcx, [rsp+270h+SubKey]; void *
0x1800d2ecf  mov     r8d, 208h; Size
0x1800d2ed5  call    memset_0
0x1800d2eda  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2ee1  lea     r13, WPP_GLOBAL_Control
0x1800d2ee8  cmp     rcx, r13
0x1800d2eeb  jz      short loc_1800D2F43
0x1800d2eed  cmp     byte ptr [rcx+69h], 4
0x1800d2ef1  jb      short loc_1800D2F15
0x1800d2ef3  test    byte ptr [rcx+6Ch], 1
0x1800d2ef7  jz      short loc_1800D2F15
0x1800d2ef9  mov     rcx, [rcx+60h]
0x1800d2efd  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x1800d2f04  mov     edx, 34h ; '4'
0x1800d2f09  call    WPP_SF_
0x1800d2f0e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2f15  cmp     rcx, r13
0x1800d2f18  jz      short loc_1800D2F43
0x1800d2f1a  cmp     byte ptr [rcx+69h], 4
0x1800d2f1e  jb      short loc_1800D2F43
0x1800d2f20  test    byte ptr [rcx+6Ch], 1
0x1800d2f24  jz      short loc_1800D2F43
0x1800d2f26  mov     rcx, [rcx+60h]
0x1800d2f2a  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x1800d2f31  mov     edx, 35h ; '5'
0x1800d2f36  mov     [rsp+270h+phkResult], rsi
0x1800d2f3b  mov     r9d, edi
0x1800d2f3e  call    WPP_SF_dS
0x1800d2f43  call    IsGetCustomWfdSettingsRegPathPresent
0x1800d2f48  mov     ebx, 104h
0x1800d2f4d  test    al, al
0x1800d2f4f  jz      short loc_1800D2F6D
0x1800d2f51  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Wlansvc"
0x1800d2f58  mov     edx, ebx
0x1800d2f5a  lea     rcx, [rsp+270h+SubKey]
0x1800d2f5f  call    cs:__imp_GetCustomRegRootPath
0x1800d2f65  test    eax, eax
0x1800d2f67  jns     loc_1800D302F
0x1800d2f6d  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Wlansvc"
0x1800d2f74  mov     rdx, rbx
0x1800d2f77  lea     rcx, [rsp+270h+SubKey]
0x1800d2f7c  call    cs:__imp__o_wcscpy_s
0x1800d2f82  mov     ebx, eax
0x1800d2f84  test    eax, eax
0x1800d2f86  jz      loc_1800D302F
0x1800d2f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2f93  cmp     rcx, r13
0x1800d2f96  jz      short loc_1800D2FC3
0x1800d2f98  cmp     byte ptr [rcx+69h], 1
0x1800d2f9c  jb      short loc_1800D2FC3
0x1800d2f9e  test    byte ptr [rcx+6Ch], 1
0x1800d2fa2  jz      short loc_1800D2FC3
0x1800d2fa4  mov     rcx, [rcx+60h]
0x1800d2fa8  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x1800d2faf  mov     edx, 0Ah
0x1800d2fb4  mov     r9d, eax
0x1800d2fb7  call    WPP_SF_d
0x1800d2fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2fc3  mov     rax, [rsp+270h+hKey]
0x1800d2fc8  test    rax, rax
0x1800d2fcb  jz      short loc_1800D2FDD
0x1800d2fcd  mov     rcx, rax; hKey
0x1800d2fd0  call    cs:__imp_RegCloseKey
0x1800d2fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2fdd  cmp     rcx, r13
0x1800d2fe0  jz      short loc_1800D3006
0x1800d2fe2  cmp     byte ptr [rcx+69h], 4
0x1800d2fe6  jb      short loc_1800D3006
0x1800d2fe8  test    byte ptr [rcx+6Ch], 1
0x1800d2fec  jz      short loc_1800D3006
0x1800d2fee  mov     rcx, [rcx+60h]
0x1800d2ff2  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x1800d2ff9  mov     edx, 36h ; '6'
0x1800d2ffe  mov     r9d, ebx
0x1800d3001  call    WPP_SF_d
0x1800d3006  mov     eax, ebx
0x1800d3008  mov     rcx, [rbp+170h+var_20]
0x1800d300f  xor     rcx, rsp; StackCookie
0x1800d3012  call    __security_check_cookie
0x1800d3017  lea     r11, [rsp+270h+var_10]
0x1800d301f  mov     rbx, [r11+30h]
0x1800d3023  mov     rsi, [r11+38h]
0x1800d3027  mov     rsp, r11
0x1800d302a  pop     r13
0x1800d302c  pop     rdi
0x1800d302d  pop     rbp
0x1800d302e  retn
0x1800d302f  lea     rax, [rsp+270h+hKey]
0x1800d3034  mov     r9d, 20006h; samDesired
0x1800d303a  xor     r8d, r8d; ulOptions
0x1800d303d  mov     [rsp+270h+phkResult], rax; phkResult
0x1800d3042  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x1800d3047  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d304e  call    cs:__imp_RegOpenKeyExW
0x1800d3054  mov     ebx, eax
0x1800d3056  test    eax, eax
0x1800d3058  jnz     loc_1800D2FBC
0x1800d305e  test    edi, edi
0x1800d3060  jz      short loc_1800D306A
0x1800d3062  mov     dword ptr [rsp+270h+Data], 1
0x1800d306a  mov     rcx, [rsp+270h+hKey]; hKey
0x1800d306f  lea     rax, [rsp+270h+Data]
0x1800d3074  mov     [rsp+270h+cbData], 4; cbData
0x1800d307c  lea     rdx, aL2nawlanmode; "L2NAWLANMode"
0x1800d3083  mov     r9d, 4; dwType
0x1800d3089  mov     [rsp+270h+phkResult], rax; lpData
0x1800d308e  xor     r8d, r8d; Reserved
0x1800d3091  call    cs:__imp_RegSetValueExW
0x1800d3097  mov     ebx, eax
0x1800d3099  test    eax, eax
0x1800d309b  jnz     loc_1800D2FBC
0x1800d30a1  mov     rax, [rsp+270h+hKey]
0x1800d30a6  test    rax, rax
0x1800d30a9  jz      loc_1800D2FD6
0x1800d30af  cmp     edi, 1
0x1800d30b2  jnz     short loc_1800D30D5
0x1800d30b4  mov     rcx, rax; hKey
0x1800d30b7  call    cs:__imp_RegCloseKey
0x1800d30bd  mov     rcx, rsi; unsigned __int16 *
0x1800d30c0  mov     [rsp+270h+hKey], 0
0x1800d30c9  call    ?AddToListOfPlapProfiles@@YAKPEBG@Z; AddToListOfPlapProfiles(ushort const *)
0x1800d30ce  mov     ebx, eax
0x1800d30d0  jmp     loc_1800D2FBC
0x1800d30d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d30dc  jmp     loc_1800D2FC8
```
