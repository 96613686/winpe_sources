# IsTetheringGPAllowedInternal(bool *)

- ea: `0x180029d00`
- end: `0x180029ec1`
- name: `?IsTetheringGPAllowedInternal@@YAJPEA_N@Z`
- size: `449`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001dc08`
- `0x18002d868`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x18000bfb4`
- `0x180029d00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029daf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029daf`
- `policymanager!PolicyManager_GetWiFiPolicy_AllowInternetSharing` at `0x180029e1c`
- `policymanager!PolicyManager_GetWiFiPolicy_AllowInternetSharing` at `0x180029e1c`

## string_xrefs

- `0x180029d81`: `NC_ShowSharedAccessUi`

## pseudocode

```c
__int64 __fastcall IsTetheringGPAllowedInternal(bool *a1)
{
  TetheringServiceTelemetry *v2; // rcx
  unsigned int v3; // ebx
  LSTATUS ValueW; // eax
  __int64 v5; // r9
  bool v6; // di
  int WiFiPolicy_AllowInternetSharing; // eax
  int v9; // [rsp+70h] [rbp+8h] BYREF
  int pvData; // [rsp+78h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+18h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v9 = 0;
  pvData = 0;
  pcbData = 4;
  if ( a1 )
  {
    *a1 = 0;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"Software\\Policies\\Microsoft\\Windows\\Network Connections",
               L"NC_ShowSharedAccessUi",
               0x10u,
               0,
               &pvData,
               &pcbData);
    v3 = ValueW;
    if ( ValueW > 0 )
      v3 = (unsigned __int16)ValueW | 0x80070000;
    v6 = 1;
    if ( (v3 & 0x80000000) != 0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, v3);
        v2 = WPP_GLOBAL_Control;
      }
      if ( v3 != -2147024894 )
        goto LABEL_25;
    }
    if ( v3 == -2147024894 || pvData )
    {
      v9 = 1;
      WiFiPolicy_AllowInternetSharing = PolicyManager_GetWiFiPolicy_AllowInternetSharing(&v9);
      v3 = WiFiPolicy_AllowInternetSharing;
      if ( WiFiPolicy_AllowInternetSharing < 0 )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
          return v3;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_25;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          152,
          &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids,
          (unsigned int)WiFiPolicy_AllowInternetSharing);
        goto LABEL_24;
      }
      if ( v9 )
      {
LABEL_23:
        *a1 = v6;
LABEL_24:
        v2 = WPP_GLOBAL_Control;
LABEL_25:
        if ( v2 == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
          return v3;
        if ( (*((_BYTE *)v2 + 28) & 8) != 0 )
        {
          LOBYTE(v5) = *a1;
          WPP_SF_c(*((_QWORD *)v2 + 2), 153, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, v5);
          v2 = WPP_GLOBAL_Control;
        }
        goto LABEL_28;
      }
    }
    else
    {
      v9 = 0;
    }
    v6 = 0;
    goto LABEL_23;
  }
  v3 = -2147024809;
LABEL_28:
  if ( v2 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v2 + 2), 154, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180029d00  push    rbx
0x180029d02  push    rsi
0x180029d03  push    rdi
0x180029d04  push    r14
0x180029d06  push    r15
0x180029d08  sub     rsp, 40h
0x180029d0c  mov     rsi, rcx
0x180029d0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d16  lea     r14, WPP_GLOBAL_Control
0x180029d1d  lea     r15, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x180029d24  cmp     rcx, r14
0x180029d27  jz      short loc_180029D47
0x180029d29  test    byte ptr [rcx+1Ch], 8
0x180029d2d  jz      short loc_180029D47
0x180029d2f  mov     rcx, [rcx+10h]
0x180029d33  mov     edx, 96h
0x180029d38  mov     r8, r15
0x180029d3b  call    WPP_SF_
0x180029d40  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d47  mov     [rsp+68h+arg_0], 0
0x180029d4f  mov     [rsp+68h+arg_8], 0
0x180029d57  mov     [rsp+68h+arg_10], 4
0x180029d62  test    rsi, rsi
0x180029d65  jnz     short loc_180029D71
0x180029d67  mov     ebx, 80070057h
0x180029d6c  jmp     loc_180029E94
0x180029d71  lea     rax, [rsp+68h+arg_10]
0x180029d79  mov     byte ptr [rsi], 0
0x180029d7c  mov     [rsp+68h+pcbData], rax; pcbData
0x180029d81  lea     r8, aNcShowsharedac; "NC_ShowSharedAccessUi"
0x180029d88  lea     rax, [rsp+68h+arg_8]
0x180029d8d  mov     r9d, 10h; dwFlags
0x180029d93  mov     [rsp+68h+pvData], rax; pvData
0x180029d98  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180029d9f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180029da6  mov     [rsp+68h+pdwType], 0; pdwType
0x180029daf  call    cs:__imp_RegGetValueW
0x180029db5  mov     ebx, eax
0x180029db7  test    eax, eax
0x180029db9  jle     short loc_180029DC4
0x180029dbb  movzx   ebx, ax
0x180029dbe  or      ebx, 80070000h
0x180029dc4  mov     edi, 1
0x180029dc9  test    ebx, ebx
0x180029dcb  jns     short loc_180029E02
0x180029dcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180029dd4  cmp     rcx, r14
0x180029dd7  jz      short loc_180029DFA
0x180029dd9  test    [rcx+1Ch], dil
0x180029ddd  jz      short loc_180029DFA
0x180029ddf  mov     rcx, [rcx+10h]
0x180029de3  mov     edx, 97h
0x180029de8  mov     r9d, ebx
0x180029deb  mov     r8, r15
0x180029dee  call    WPP_SF_d
0x180029df3  mov     rcx, cs:WPP_GLOBAL_Control
0x180029dfa  cmp     ebx, 80070002h
0x180029e00  jnz     short loc_180029E6E
0x180029e02  cmp     ebx, 80070002h
0x180029e08  jz      short loc_180029E11
0x180029e0a  cmp     [rsp+68h+arg_8], 0
0x180029e0f  jz      short loc_180029E59
0x180029e11  mov     eax, edi
0x180029e13  lea     rcx, [rsp+68h+arg_0]
0x180029e18  mov     [rsp+68h+arg_0], eax
0x180029e1c  call    cs:__imp_PolicyManager_GetWiFiPolicy_AllowInternetSharing
0x180029e22  mov     ebx, eax
0x180029e24  test    eax, eax
0x180029e26  jns     short loc_180029E50
0x180029e28  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e2f  cmp     rcx, r14
0x180029e32  jz      short loc_180029EB3
0x180029e34  test    [rcx+1Ch], dil
0x180029e38  jz      short loc_180029E6E
0x180029e3a  mov     rcx, [rcx+10h]
0x180029e3e  mov     edx, 98h
0x180029e43  mov     r9d, eax
0x180029e46  mov     r8, r15
0x180029e49  call    WPP_SF_d
0x180029e4e  jmp     short loc_180029E67
0x180029e50  cmp     [rsp+68h+arg_0], 0
0x180029e55  jz      short loc_180029E61
0x180029e57  jmp     short loc_180029E64
0x180029e59  mov     [rsp+68h+arg_0], 0
0x180029e61  xor     dil, dil
0x180029e64  mov     [rsi], dil
0x180029e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e6e  cmp     rcx, r14
0x180029e71  jz      short loc_180029EB3
0x180029e73  test    byte ptr [rcx+1Ch], 8
0x180029e77  jz      short loc_180029E94
0x180029e79  mov     r9b, [rsi]
0x180029e7c  mov     edx, 99h
0x180029e81  mov     rcx, [rcx+10h]
0x180029e85  mov     r8, r15
0x180029e88  call    WPP_SF_c
0x180029e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e94  cmp     rcx, r14
0x180029e97  jz      short loc_180029EB3
0x180029e99  test    byte ptr [rcx+1Ch], 8
0x180029e9d  jz      short loc_180029EB3
0x180029e9f  mov     rcx, [rcx+10h]
0x180029ea3  mov     edx, 9Ah
0x180029ea8  mov     r9d, ebx
0x180029eab  mov     r8, r15
0x180029eae  call    WPP_SF_d
0x180029eb3  mov     eax, ebx
0x180029eb5  add     rsp, 40h
0x180029eb9  pop     r15
0x180029ebb  pop     r14
0x180029ebd  pop     rdi
0x180029ebe  pop     rsi
0x180029ebf  pop     rbx
0x180029ec0  retn
```
