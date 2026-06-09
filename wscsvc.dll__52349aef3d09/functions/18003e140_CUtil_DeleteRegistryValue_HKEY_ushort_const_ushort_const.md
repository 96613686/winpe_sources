# CUtil::DeleteRegistryValue(HKEY__ *,ushort const *,ushort const *)

- ea: `0x18003e140`
- end: `0x18003e26e`
- name: `?DeleteRegistryValue@CUtil@@SAJPEAUHKEY__@@PEBG1@Z`
- size: `302`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003d100`

## callees

- `0x18003e140`
- `0x18003e5f4`
- `0x18003e7e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003e1b5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003e1b5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003e197`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003e197`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e1c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e1c5`

## string_xrefs

- `0x18003e160`: `SOFTWARE\Microsoft\Security Center\Svc\DSA`

## pseudocode

```c
__int64 __fastcall CUtil::DeleteRegistryValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned int v3; // eax
  int v4; // r8d
  int v5; // r9d
  HKEY v6; // rbx
  LSTATUS v7; // edi
  int v8; // r8d
  int v9; // r9d
  bool v10; // sf
  HKEY hKey; // [rsp+90h] [rbp+18h] BYREF

  hKey = 0;
  v3 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Security Center\\Svc\\DSA",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  v6 = (HKEY)v3;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        v4,
        v5,
        (__int64)L"SOFTWARE\\Microsoft\\Security Center\\Svc\\DSA",
        v3);
    }
    v10 = (int)v6 < 0;
    if ( (int)v6 <= 0 )
      goto LABEL_16;
    LODWORD(v6) = (unsigned __int16)v6;
    goto LABEL_14;
  }
  v7 = RegDeleteValueW(hKey, L"OemDefaultAntivirus");
  RegCloseKey(hKey);
  hKey = v6;
  if ( !v7 )
    return (unsigned int)v6;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_qSSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v6 + 16,
      v8,
      v9,
      (__int64)L"SOFTWARE\\Microsoft\\Security Center\\Svc\\DSA",
      (__int64)L"OemDefaultAntivirus",
      v7);
  if ( v7 > 0 )
  {
    LODWORD(v6) = (unsigned __int16)v7;
LABEL_14:
    LODWORD(v6) = (unsigned int)v6 | 0x80070000;
    goto LABEL_15;
  }
  LODWORD(v6) = v7;
LABEL_15:
  v10 = (int)v6 < 0;
LABEL_16:
  if ( !v10 )
    LODWORD(v6) = -2147467259;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003e140  mov     r11, rsp
0x18003e143  mov     [r11+18h], r8
0x18003e147  push    rbx
0x18003e148  push    rbp
0x18003e149  push    rdi
0x18003e14a  push    r14
0x18003e14c  sub     rsp, 58h
0x18003e150  mov     qword ptr [r11-38h], 0
0x18003e158  lea     rax, [r11+18h]
0x18003e15c  mov     [r11-40h], rax
0x18003e160  lea     rbp, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Security Center\\S"...
0x18003e167  mov     qword ptr [r11-48h], 0
0x18003e16f  xor     r9d, r9d; lpClass
0x18003e172  mov     [rsp+78h+samDesired], 20006h; samDesired
0x18003e17a  xor     r8d, r8d; Reserved
0x18003e17d  mov     rdx, rbp; lpSubKey
0x18003e180  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18003e188  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e18f  mov     qword ptr [r11+18h], 0
0x18003e197  call    cs:__imp_RegCreateKeyExW
0x18003e19d  mov     ebx, eax
0x18003e19f  test    eax, eax
0x18003e1a1  jnz     short loc_18003E21B
0x18003e1a3  mov     rcx, [rsp+78h+hKey]; hKey
0x18003e1ab  lea     r14, aOemdefaultanti; "OemDefaultAntivirus"
0x18003e1b2  mov     rdx, r14; lpValueName
0x18003e1b5  call    cs:__imp_RegDeleteValueW
0x18003e1bb  mov     rcx, [rsp+78h+hKey]; hKey
0x18003e1c3  mov     edi, eax
0x18003e1c5  call    cs:__imp_RegCloseKey
0x18003e1cb  mov     [rsp+78h+hKey], rbx
0x18003e1d3  test    edi, edi
0x18003e1d5  jz      loc_18003E262
0x18003e1db  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e1e2  lea     rax, WPP_GLOBAL_Control
0x18003e1e9  cmp     rcx, rax
0x18003e1ec  jz      short loc_18003E20E
0x18003e1ee  test    byte ptr [rcx+1Ch], 1
0x18003e1f2  jz      short loc_18003E20E
0x18003e1f4  mov     rcx, [rcx+10h]
0x18003e1f8  lea     edx, [rbx+10h]
0x18003e1fb  mov     [rsp+78h+var_48], edi
0x18003e1ff  mov     qword ptr [rsp+78h+samDesired], r14
0x18003e204  mov     qword ptr [rsp+78h+dwOptions], rbp
0x18003e209  call    WPP_SF_qSSd
0x18003e20e  test    edi, edi
0x18003e210  jg      short loc_18003E216
0x18003e212  mov     ebx, edi
0x18003e214  jmp     short loc_18003E258
0x18003e216  movzx   ebx, di
0x18003e219  jmp     short loc_18003E252
0x18003e21b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e222  lea     rax, WPP_GLOBAL_Control
0x18003e229  cmp     rcx, rax
0x18003e22c  jz      short loc_18003E24B
0x18003e22e  test    byte ptr [rcx+1Ch], 1
0x18003e232  jz      short loc_18003E24B
0x18003e234  mov     rcx, [rcx+10h]
0x18003e238  mov     edx, 11h
0x18003e23d  mov     [rsp+78h+samDesired], ebx
0x18003e241  mov     qword ptr [rsp+78h+dwOptions], rbp
0x18003e246  call    WPP_SF_qSd
0x18003e24b  test    ebx, ebx
0x18003e24d  jle     short loc_18003E25A
0x18003e24f  movzx   ebx, bx
0x18003e252  or      ebx, 80070000h
0x18003e258  test    ebx, ebx
0x18003e25a  mov     eax, 80004005h
0x18003e25f  cmovns  ebx, eax
0x18003e262  mov     eax, ebx
0x18003e264  add     rsp, 58h
0x18003e268  pop     r14
0x18003e26a  pop     rdi
0x18003e26b  pop     rbp
0x18003e26c  pop     rbx
0x18003e26d  retn
```
