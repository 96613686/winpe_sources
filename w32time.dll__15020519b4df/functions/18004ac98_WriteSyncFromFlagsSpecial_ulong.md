# WriteSyncFromFlagsSpecial(ulong)

- ea: `0x18004ac98`
- end: `0x18004add2`
- name: `?WriteSyncFromFlagsSpecial@@YAJK@Z`
- size: `314`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18004afd0`
- `0x18004b2f0`
- `0x18004b4b0`

## callees

- `0x18004ac98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ad1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ad88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ad1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ad88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004adba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004adba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ad4c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ad4c`

## string_xrefs

- `0x18004ad09`: `System\CurrentControlSet\Services\W32Time\Parameters`
- `0x18004ad7a`: `System\CurrentControlSet\Services\W32Time`

## pseudocode

```c
__int64 __fastcall WriteSyncFromFlagsSpecial(int a1)
{
  int v1; // ecx
  int v2; // ecx
  unsigned int v3; // ebx
  const wchar_t *v4; // rdi
  __int64 v5; // rax
  DWORD cbData; // esi
  LSTATUS v7; // eax
  const WCHAR *v8; // rdx
  bool v9; // cc
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  if ( a1 )
  {
    v1 = a1 - 1;
    if ( v1 )
    {
      v2 = v1 - 1;
      if ( v2 )
      {
        if ( v2 != 1 )
          return (unsigned int)-2147467263;
        v4 = (const wchar_t *)L"AllSync";
      }
      else
      {
        v4 = L"NT5DS";
      }
    }
    else
    {
      v4 = L"NTP";
    }
  }
  else
  {
    v4 = L"NoSync";
  }
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  cbData = 2 * v5 + 2;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\W32Time\\Parameters", 0, 3u, &hKey);
  v3 = v7;
  if ( !v7 )
  {
    v8 = L"Type";
    goto LABEL_14;
  }
  if ( v7 != 2 )
  {
    v9 = v7 <= 0;
LABEL_20:
    if ( !v9 )
      v3 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_22;
  }
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\W32Time", 0, 3u, &hKey);
  v3 = v7;
  v9 = v7 <= 0;
  if ( v7 )
    goto LABEL_20;
  v8 = L"SpecialType";
LABEL_14:
  v7 = RegSetValueExW(hKey, v8, 0, 1u, (const BYTE *)v4, cbData);
  v3 = v7;
  v9 = v7 <= 0;
  if ( v7 )
    goto LABEL_20;
  v3 = 0;
LABEL_22:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18004ac98  push    rbx
0x18004ac9a  push    rbp
0x18004ac9b  push    rsi
0x18004ac9c  push    rdi
0x18004ac9d  sub     rsp, 38h
0x18004aca1  xor     ebp, ebp
0x18004aca3  mov     [rsp+58h+hKey], rbp
0x18004aca8  test    ecx, ecx
0x18004acaa  jz      short loc_18004ACE0
0x18004acac  sub     ecx, 1
0x18004acaf  jz      short loc_18004ACD7
0x18004acb1  sub     ecx, 1
0x18004acb4  jz      short loc_18004ACCE
0x18004acb6  cmp     ecx, 1
0x18004acb9  jz      short loc_18004ACC5
0x18004acbb  mov     ebx, 80004001h
0x18004acc0  jmp     loc_18004ADC6
0x18004acc5  lea     rdi, aAllsync; "AllSync"
0x18004accc  jmp     short loc_18004ACE7
0x18004acce  lea     rdi, aNt5ds; "NT5DS"
0x18004acd5  jmp     short loc_18004ACE7
0x18004acd7  lea     rdi, aNtp; "NTP"
0x18004acde  jmp     short loc_18004ACE7
0x18004ace0  lea     rdi, aNosync; "NoSync"
0x18004ace7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004aceb  inc     rax
0x18004acee  cmp     [rdi+rax*2], bp
0x18004acf2  jnz     short loc_18004ACEB
0x18004acf4  lea     esi, ds:2[rax*2]
0x18004acfb  mov     r9d, 3; samDesired
0x18004ad01  lea     rax, [rsp+58h+hKey]
0x18004ad06  xor     r8d, r8d; ulOptions
0x18004ad09  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\W3"...
0x18004ad10  mov     [rsp+58h+phkResult], rax; phkResult
0x18004ad15  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004ad1c  call    cs:__imp_RegOpenKeyExW
0x18004ad23  nop     dword ptr [rax+rax+00h]
0x18004ad28  mov     ebx, eax
0x18004ad2a  test    eax, eax
0x18004ad2c  jnz     short loc_18004AD62
0x18004ad2e  lea     rdx, aType; "Type"
0x18004ad35  mov     rcx, [rsp+58h+hKey]; hKey
0x18004ad3a  mov     r9d, 1; dwType
0x18004ad40  mov     [rsp+58h+cbData], esi; cbData
0x18004ad44  xor     r8d, r8d; Reserved
0x18004ad47  mov     [rsp+58h+phkResult], rdi; lpData
0x18004ad4c  call    cs:__imp_RegSetValueExW
0x18004ad53  nop     dword ptr [rax+rax+00h]
0x18004ad58  mov     ebx, eax
0x18004ad5a  test    eax, eax
0x18004ad5c  jnz     short loc_18004ADA5
0x18004ad5e  mov     ebx, ebp
0x18004ad60  jmp     short loc_18004ADB0
0x18004ad62  cmp     eax, 2
0x18004ad65  jnz     short loc_18004ADA3
0x18004ad67  lea     rax, [rsp+58h+hKey]
0x18004ad6c  mov     r9d, 3; samDesired
0x18004ad72  xor     r8d, r8d; ulOptions
0x18004ad75  mov     [rsp+58h+phkResult], rax; phkResult
0x18004ad7a  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\W3"...
0x18004ad81  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004ad88  call    cs:__imp_RegOpenKeyExW
0x18004ad8f  nop     dword ptr [rax+rax+00h]
0x18004ad94  mov     ebx, eax
0x18004ad96  test    eax, eax
0x18004ad98  jnz     short loc_18004ADA5
0x18004ad9a  lea     rdx, aSpecialtype; "SpecialType"
0x18004ada1  jmp     short loc_18004AD35
0x18004ada3  test    eax, eax
0x18004ada5  jle     short loc_18004ADB0
0x18004ada7  movzx   ebx, ax
0x18004adaa  or      ebx, 80070000h
0x18004adb0  mov     rcx, [rsp+58h+hKey]; hKey
0x18004adb5  test    rcx, rcx
0x18004adb8  jz      short loc_18004ADC6
0x18004adba  call    cs:__imp_RegCloseKey
0x18004adc1  nop     dword ptr [rax+rax+00h]
0x18004adc6  mov     eax, ebx
0x18004adc8  add     rsp, 38h
0x18004adcc  pop     rdi
0x18004adcd  pop     rsi
0x18004adce  pop     rbp
0x18004adcf  pop     rbx
0x18004add0  retn
```
