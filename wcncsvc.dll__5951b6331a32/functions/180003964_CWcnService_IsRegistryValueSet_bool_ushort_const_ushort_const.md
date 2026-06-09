# CWcnService::IsRegistryValueSet(bool,ushort const *,ushort const *)

- ea: `0x180003964`
- end: `0x180003ac9`
- name: `?IsRegistryValueSet@CWcnService@@SA_N_NPEBG1@Z`
- size: `357`
- prototype: `bool __fastcall(char, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a3a8`
- `0x180045bc0`

## callees

- `0x180003964`
- `0x180004fb8`
- `0x180005014`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800039ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800039ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003a55`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003a55`

## pseudocode

```c
bool __fastcall CWcnService::IsRegistryValueSet(char a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  const char *Indent; // rax
  __int64 v5; // r10
  bool v6; // bl
  _BYTE *v7; // r10
  unsigned int v8; // eax
  __int64 v9; // r10
  char v10; // r11
  const char *v11; // rax
  __int64 v12; // r10
  DWORD cbData; // [rsp+50h] [rbp+8h] BYREF
  const unsigned __int16 *Data; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  Data = a3;
  LOBYTE(cbData) = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v5 + 16), 62, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, Indent);
  }
  hKey = 0;
  LODWORD(Data) = 1;
  cbData = 4;
  v6 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\WCN", 0, 1u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, a2, 0, 0, (LPBYTE)&Data, &cbData) && cbData == 4 )
      v6 = (_DWORD)Data != 0;
    goto LABEL_11;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v8 = (unsigned int)GetIndent(0);
    WPP_SF_sd(*(_QWORD *)(v9 + 16), 63, (unsigned int)WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v8, v10);
LABEL_11:
    v7 = WPP_GLOBAL_Control;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (_BYTE *)&WPP_GLOBAL_Control && v7[25] >= 6u )
  {
    v11 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v12 + 16), 64, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids, v11);
  }
  return v6;
}

```

## disassembly

```asm
0x180003964  mov     [rsp+arg_8], rbx
0x180003969  mov     [rsp+Data], r8
0x18000396e  mov     byte ptr [rsp+cbData], cl
0x180003972  push    rbp
0x180003973  push    rsi
0x180003974  push    rdi
0x180003975  sub     rsp, 30h
0x180003979  mov     rdi, rdx
0x18000397c  mov     r10, cs:WPP_GLOBAL_Control
0x180003983  lea     rbp, WPP_GLOBAL_Control
0x18000398a  mov     esi, 1
0x18000398f  cmp     r10, rbp
0x180003992  jz      short loc_1800039B8
0x180003994  cmp     byte ptr [r10+19h], 6
0x180003999  jb      short loc_1800039B8
0x18000399b  mov     ecx, esi; int
0x18000399d  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800039a2  mov     rcx, [r10+10h]
0x1800039a6  lea     edx, [rsi+3Dh]
0x1800039a9  mov     r9, rax
0x1800039ac  lea     r8, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids
0x1800039b3  call    WPP_SF_s
0x1800039b8  lea     rax, [rsp+48h+hKey]
0x1800039bd  mov     [rsp+48h+hKey], 0
0x1800039c6  mov     r9d, esi; samDesired
0x1800039c9  mov     [rsp+48h+phkResult], rax; phkResult
0x1800039ce  xor     r8d, r8d; ulOptions
0x1800039d1  mov     dword ptr [rsp+48h+Data], esi
0x1800039d5  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800039dc  mov     [rsp+48h+cbData], 4
0x1800039e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800039eb  xor     bl, bl
0x1800039ed  call    cs:__imp_RegOpenKeyExW
0x1800039f3  mov     r11d, eax
0x1800039f6  test    eax, eax
0x1800039f8  jz      short loc_180003A33
0x1800039fa  mov     r10, cs:WPP_GLOBAL_Control
0x180003a01  cmp     r10, rbp
0x180003a04  jz      short loc_180003A77
0x180003a06  cmp     byte ptr [r10+19h], 5
0x180003a0b  jb      short loc_180003A77
0x180003a0d  xor     ecx, ecx; int
0x180003a0f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180003a14  mov     rcx, [r10+10h]
0x180003a18  lea     r8, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids
0x180003a1f  mov     edx, 3Fh ; '?'
0x180003a24  mov     dword ptr [rsp+48h+phkResult], r11d
0x180003a29  mov     r9, rax
0x180003a2c  call    WPP_SF_sd
0x180003a31  jmp     short loc_180003A70
0x180003a33  mov     rcx, [rsp+48h+hKey]; hKey
0x180003a38  lea     rax, [rsp+48h+cbData]
0x180003a3d  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180003a42  xor     r9d, r9d; lpType
0x180003a45  lea     rax, [rsp+48h+Data]
0x180003a4a  xor     r8d, r8d; lpReserved
0x180003a4d  mov     rdx, rdi; lpValueName
0x180003a50  mov     [rsp+48h+phkResult], rax; lpData
0x180003a55  call    cs:__imp_RegQueryValueExW
0x180003a5b  test    eax, eax
0x180003a5d  jnz     short loc_180003A70
0x180003a5f  cmp     [rsp+48h+cbData], 4
0x180003a64  jnz     short loc_180003A70
0x180003a66  cmp     dword ptr [rsp+48h+Data], eax
0x180003a6a  movzx   ebx, bl
0x180003a6d  cmovnz  ebx, esi
0x180003a70  mov     r10, cs:WPP_GLOBAL_Control
0x180003a77  mov     rcx, [rsp+48h+hKey]; hKey
0x180003a7c  test    rcx, rcx
0x180003a7f  jz      short loc_180003A8E
0x180003a81  call    cs:__imp_RegCloseKey
0x180003a87  mov     r10, cs:WPP_GLOBAL_Control
0x180003a8e  cmp     r10, rbp
0x180003a91  jz      short loc_180003ABA
0x180003a93  cmp     byte ptr [r10+19h], 6
0x180003a98  jb      short loc_180003ABA
0x180003a9a  or      ecx, 0FFFFFFFFh; int
0x180003a9d  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180003aa2  mov     rcx, [r10+10h]
0x180003aa6  lea     r8, WPP_ac811424b605344d9cc8b73f32b92b60_Traceguids
0x180003aad  mov     edx, 40h ; '@'
0x180003ab2  mov     r9, rax
0x180003ab5  call    WPP_SF_s
0x180003aba  mov     al, bl
0x180003abc  mov     rbx, [rsp+48h+arg_8]
0x180003ac1  add     rsp, 30h
0x180003ac5  pop     rdi
0x180003ac6  pop     rsi
0x180003ac7  pop     rbp
0x180003ac8  retn
```
