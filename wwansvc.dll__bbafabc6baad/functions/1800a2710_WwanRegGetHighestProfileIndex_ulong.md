# WwanRegGetHighestProfileIndex(ulong *)

- ea: `0x1800a2710`
- end: `0x1800a2a39`
- name: `?WwanRegGetHighestProfileIndex@@YAKPEAK@Z`
- size: `809`
- prototype: `unsigned int __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18009e098`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x180012300`
- `0x180074758`
- `0x180074cec`
- `0x1800a2710`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a2837`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a28b9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a2837`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a28b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2935`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a29c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2a02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2935`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a29c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a2a02`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a27d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a2862`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a28e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a27d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a2862`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a28e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a2923`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a2923`

## string_xrefs

- `0x1800a27e1`: `RegOpenKeyEx open profile root key failed, result %u.`
- `0x1800a2871`: `RegOpenKeyEx open profile root key failed, result %u.`
- `0x1800a298b`: `RegOpenKeyEx open profile index key failed, result %u.`

## pseudocode

```c
__int64 __fastcall WwanRegGetHighestProfileIndex(unsigned int *a1)
{
  unsigned int v2; // ebx
  unsigned int v3; // eax
  unsigned int v4; // edi
  DWORD i; // r14d
  unsigned int v6; // eax
  unsigned int v7; // eax
  bool v8; // zf
  DWORD j; // esi
  unsigned int v10; // eax
  unsigned int v11; // eax
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v15; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v20; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[40]; // [rsp+C0h] [rbp-40h] BYREF

  hKey = 0;
  phkResult = 0;
  v20 = 0;
  memset_0(Name, 0, 0x4Eu);
  cchName = 39;
  memset_0(SubKey, 0, 0x4Eu);
  v15 = 39;
  *(_DWORD *)Data = 0;
  cbData = 4;
  Type = 0;
  WwanLog::Enter("WwanRegGetHighestProfileIndex");
  if ( a1 )
  {
    *a1 = 0;
    v3 = RegOpenKeyExW(::phkResult, L"Profiles", 0, 9u, &hKey);
    v2 = v3;
    if ( v3 )
    {
      WwanLog::Error("WwanRegGetHighestProfileIndex", 0, L"RegOpenKeyEx open profile root key failed, result %u.", v3);
      if ( v2 == 2 )
        v2 = 0;
    }
    else
    {
      v4 = 0;
      for ( i = 0; ; ++i )
      {
        cchName = 39;
        v6 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
        v2 = v6;
        if ( v6 )
          break;
        v7 = RegOpenKeyExW(hKey, Name, 0, 9u, &phkResult);
        v2 = v7;
        if ( v7 )
        {
          WwanLog::Error(
            "WwanRegGetHighestProfileIndex",
            0,
            L"RegOpenKeyEx open profile root key failed, result %u.",
            v7);
          v8 = v2 == 2;
        }
        else
        {
          for ( j = 0; ; ++j )
          {
            v15 = 39;
            v10 = RegEnumKeyExW(phkResult, j, SubKey, &v15, 0, 0, 0, 0);
            v2 = v10;
            if ( v10 )
              break;
            v11 = RegOpenKeyExW(phkResult, SubKey, 0, 1u, &v20);
            v2 = v11;
            if ( v11 )
            {
              WwanLog::Error(
                "WwanRegGetHighestProfileIndex",
                0,
                L"RegOpenKeyEx open profile index key failed, result %u.",
                v11);
              goto LABEL_26;
            }
            cbData = 4;
            v2 = RegQueryValueExW(v20, L"ProfileIndex", 0, &Type, Data, &cbData);
            if ( v20 )
              RegCloseKey(v20);
            if ( v2 )
            {
              WwanLog::Error(
                "WwanRegGetHighestProfileIndex",
                0,
                L"RegQueryValueEx query profile index failed, result %u.",
                v2);
              if ( v2 != 2 )
                goto LABEL_26;
            }
            else if ( Type == 4 )
            {
              if ( *(_DWORD *)Data > v4 )
                v4 = *(_DWORD *)Data;
            }
            else
            {
              WwanLog::Error("WwanRegGetHighestProfileIndex", 0, L"RegQueryValueEx get invalid type %d, skip this.");
            }
          }
          WwanLog::Error("WwanRegGetHighestProfileIndex", 0, L"RegEnumKeyEx enum profile failed, result %u.", v10);
          if ( v2 == 259 )
            v2 = 0;
LABEL_26:
          if ( phkResult )
            RegCloseKey(phkResult);
          v8 = v2 == 0;
        }
        if ( !v8 )
          goto LABEL_34;
      }
      if ( v6 == 259 )
        v2 = 0;
      else
        WwanLog::Error("WwanRegGetHighestProfileIndex", 0, L"RegEnumKeyEx enum sim key failed, result %u.", v6);
LABEL_34:
      if ( hKey )
        RegCloseKey(hKey);
      if ( !v2 )
        *a1 = v4;
    }
  }
  else
  {
    v2 = 87;
  }
  WwanLog::Exit("WwanRegGetHighestProfileIndex");
  return v2;
}

```

## disassembly

```asm
0x1800a2710  push    rbp
0x1800a2712  push    rbx
0x1800a2713  push    rsi
0x1800a2714  push    rdi
0x1800a2715  push    r12
0x1800a2717  push    r13
0x1800a2719  push    r14
0x1800a271b  push    r15
0x1800a271d  lea     rbp, [rsp-28h]
0x1800a2722  sub     rsp, 128h
0x1800a2729  mov     rax, cs:__security_cookie
0x1800a2730  xor     rax, rsp
0x1800a2733  mov     [rbp+60h+var_50], rax
0x1800a2737  xor     r12d, r12d
0x1800a273a  mov     r15, rcx
0x1800a273d  xor     edx, edx; Val
0x1800a273f  mov     [rsp+160h+hKey], r12
0x1800a2744  lea     rcx, [rsp+160h+Name]; void *
0x1800a2749  mov     [rsp+160h+var_108], r12
0x1800a274e  mov     [rsp+160h+var_F8], r12
0x1800a2753  lea     ebx, [r12+4Eh]
0x1800a2758  mov     r8d, ebx; Size
0x1800a275b  call    memset_0
0x1800a2760  mov     r8d, ebx; Size
0x1800a2763  mov     [rsp+160h+cchName], 27h ; '''
0x1800a276b  xor     edx, edx; Val
0x1800a276d  lea     rcx, [rbp+60h+SubKey]; void *
0x1800a2771  call    memset_0
0x1800a2776  lea     r13, aWwanreggethigh; "WwanRegGetHighestProfileIndex"
0x1800a277d  mov     [rsp+160h+var_118], 27h ; '''
0x1800a2785  mov     rcx, r13; char *
0x1800a2788  mov     dword ptr [rsp+160h+Data], r12d
0x1800a278d  mov     [rsp+160h+cbData], 4
0x1800a2795  mov     [rsp+160h+Type], r12d
0x1800a279a  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800a279f  test    r15, r15
0x1800a27a2  jnz     short loc_1800A27AE
0x1800a27a4  lea     ebx, [r12+57h]
0x1800a27a9  jmp     loc_1800A2A0F
0x1800a27ae  mov     [r15], r12d
0x1800a27b1  lea     rax, [rsp+160h+hKey]
0x1800a27b6  mov     rcx, cs:phkResult; hKey
0x1800a27bd  lea     rdx, aProfiles; "Profiles"
0x1800a27c4  mov     r9d, 9; samDesired
0x1800a27ca  mov     [rsp+160h+phkResult], rax; phkResult
0x1800a27cf  xor     r8d, r8d; ulOptions
0x1800a27d2  call    cs:__imp_RegOpenKeyExW
0x1800a27d8  mov     ebx, eax
0x1800a27da  test    eax, eax
0x1800a27dc  jz      short loc_1800A2803
0x1800a27de  mov     r9d, eax
0x1800a27e1  lea     r8, aRegopenkeyexOp_0; "RegOpenKeyEx open profile root key fail"...
0x1800a27e8  xor     edx, edx; struct _GUID *
0x1800a27ea  mov     rcx, r13; char *
0x1800a27ed  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a27f2  cmp     ebx, 2
0x1800a27f5  jnz     loc_1800A2A0F
0x1800a27fb  mov     ebx, r12d
0x1800a27fe  jmp     loc_1800A2A0F
0x1800a2803  mov     edi, r12d
0x1800a2806  mov     r14d, r12d
0x1800a2809  mov     rcx, [rsp+160h+hKey]; hKey
0x1800a280e  lea     r9, [rsp+160h+cchName]; lpcchName
0x1800a2813  mov     [rsp+160h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800a2818  lea     r8, [rsp+160h+Name]; lpName
0x1800a281d  mov     [rsp+160h+lpcchClass], r12; lpcchClass
0x1800a2822  mov     edx, r14d; dwIndex
0x1800a2825  mov     [rsp+160h+lpClass], r12; lpClass
0x1800a282a  mov     [rsp+160h+phkResult], r12; lpReserved
0x1800a282f  mov     [rsp+160h+cchName], 27h ; '''
0x1800a2837  call    cs:__imp_RegEnumKeyExW
0x1800a283d  mov     ebx, eax
0x1800a283f  test    eax, eax
0x1800a2841  jnz     loc_1800A29D8
0x1800a2847  mov     rcx, [rsp+160h+hKey]; hKey
0x1800a284c  lea     rax, [rsp+160h+var_108]
0x1800a2851  lea     r9d, [rbx+9]; samDesired
0x1800a2855  mov     [rsp+160h+phkResult], rax; phkResult
0x1800a285a  xor     r8d, r8d; ulOptions
0x1800a285d  lea     rdx, [rsp+160h+Name]; lpSubKey
0x1800a2862  call    cs:__imp_RegOpenKeyExW
0x1800a2868  mov     ebx, eax
0x1800a286a  test    eax, eax
0x1800a286c  jz      short loc_1800A288A
0x1800a286e  mov     r9d, eax
0x1800a2871  lea     r8, aRegopenkeyexOp_0; "RegOpenKeyEx open profile root key fail"...
0x1800a2878  xor     edx, edx; struct _GUID *
0x1800a287a  mov     rcx, r13; char *
0x1800a287d  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a2882  cmp     ebx, 2
0x1800a2885  jmp     loc_1800A29CE
0x1800a288a  mov     esi, r12d
0x1800a288d  mov     rcx, [rsp+160h+var_108]; hKey
0x1800a2892  lea     r9, [rsp+160h+var_118]; lpcchName
0x1800a2897  mov     [rsp+160h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800a289c  lea     r8, [rbp+60h+SubKey]; lpName
0x1800a28a0  mov     [rsp+160h+lpcchClass], r12; lpcchClass
0x1800a28a5  mov     edx, esi; dwIndex
0x1800a28a7  mov     [rsp+160h+lpClass], r12; lpClass
0x1800a28ac  mov     [rsp+160h+phkResult], r12; lpReserved
0x1800a28b1  mov     [rsp+160h+var_118], 27h ; '''
0x1800a28b9  call    cs:__imp_RegEnumKeyExW
0x1800a28bf  mov     ebx, eax
0x1800a28c1  test    eax, eax
0x1800a28c3  jnz     loc_1800A299E
0x1800a28c9  mov     rcx, [rsp+160h+var_108]; hKey
0x1800a28ce  lea     rax, [rsp+160h+var_F8]
0x1800a28d3  lea     r9d, [rbx+1]; samDesired
0x1800a28d7  mov     [rsp+160h+phkResult], rax; phkResult
0x1800a28dc  xor     r8d, r8d; ulOptions
0x1800a28df  lea     rdx, [rbp+60h+SubKey]; lpSubKey
0x1800a28e3  call    cs:__imp_RegOpenKeyExW
0x1800a28e9  mov     ebx, eax
0x1800a28eb  test    eax, eax
0x1800a28ed  jnz     loc_1800A2988
0x1800a28f3  mov     rcx, [rsp+160h+var_F8]; hKey
0x1800a28f8  lea     rax, [rsp+160h+cbData]
0x1800a28fd  mov     [rsp+160h+lpClass], rax; lpcbData
0x1800a2902  lea     r9, [rsp+160h+Type]; lpType
0x1800a2907  lea     rax, [rsp+160h+Data]
0x1800a290c  mov     [rsp+160h+cbData], 4
0x1800a2914  xor     r8d, r8d; lpReserved
0x1800a2917  mov     [rsp+160h+phkResult], rax; lpData
0x1800a291c  lea     rdx, aProfileindex; "ProfileIndex"
0x1800a2923  call    cs:__imp_RegQueryValueExW
0x1800a2929  mov     rcx, [rsp+160h+var_F8]; hKey
0x1800a292e  mov     ebx, eax
0x1800a2930  test    rcx, rcx
0x1800a2933  jz      short loc_1800A293B
0x1800a2935  call    cs:__imp_RegCloseKey
0x1800a293b  test    ebx, ebx
0x1800a293d  jz      short loc_1800A295A
0x1800a293f  mov     r9d, ebx
0x1800a2942  lea     r8, aRegqueryvaluee_8; "RegQueryValueEx query profile index fai"...
0x1800a2949  xor     edx, edx; struct _GUID *
0x1800a294b  mov     rcx, r13; char *
0x1800a294e  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a2953  cmp     ebx, 2
0x1800a2956  jnz     short loc_1800A29BC
0x1800a2958  jmp     short loc_1800A2981
0x1800a295a  mov     r9d, [rsp+160h+Type]
0x1800a295f  cmp     r9d, 4
0x1800a2963  jz      short loc_1800A2978
0x1800a2965  lea     r8, aRegqueryvaluee_10; "RegQueryValueEx get invalid type %d, sk"...
0x1800a296c  xor     edx, edx; struct _GUID *
0x1800a296e  mov     rcx, r13; char *
0x1800a2971  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a2976  jmp     short loc_1800A2981
0x1800a2978  cmp     dword ptr [rsp+160h+Data], edi
0x1800a297c  cmova   edi, dword ptr [rsp+160h+Data]
0x1800a2981  inc     esi
0x1800a2983  jmp     loc_1800A288D
0x1800a2988  mov     r9d, eax
0x1800a298b  lea     r8, aRegopenkeyexOp; "RegOpenKeyEx open profile index key fai"...
0x1800a2992  xor     edx, edx; struct _GUID *
0x1800a2994  mov     rcx, r13; char *
0x1800a2997  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a299c  jmp     short loc_1800A29BC
0x1800a299e  mov     r9d, ebx
0x1800a29a1  lea     r8, aRegenumkeyexEn_0; "RegEnumKeyEx enum profile failed, resul"...
0x1800a29a8  xor     edx, edx; struct _GUID *
0x1800a29aa  mov     rcx, r13; char *
0x1800a29ad  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a29b2  cmp     ebx, 103h
0x1800a29b8  cmovz   ebx, r12d
0x1800a29bc  mov     rcx, [rsp+160h+var_108]; hKey
0x1800a29c1  test    rcx, rcx
0x1800a29c4  jz      short loc_1800A29CC
0x1800a29c6  call    cs:__imp_RegCloseKey
0x1800a29cc  test    ebx, ebx
0x1800a29ce  jnz     short loc_1800A29F8
0x1800a29d0  inc     r14d
0x1800a29d3  jmp     loc_1800A2809
0x1800a29d8  cmp     eax, 103h
0x1800a29dd  jnz     short loc_1800A29E4
0x1800a29df  mov     ebx, r12d
0x1800a29e2  jmp     short loc_1800A29F8
0x1800a29e4  mov     r9d, eax
0x1800a29e7  lea     r8, aRegenumkeyexEn; "RegEnumKeyEx enum sim key failed, resul"...
0x1800a29ee  xor     edx, edx; struct _GUID *
0x1800a29f0  mov     rcx, r13; char *
0x1800a29f3  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a29f8  mov     rcx, [rsp+160h+hKey]; hKey
0x1800a29fd  test    rcx, rcx
0x1800a2a00  jz      short loc_1800A2A08
0x1800a2a02  call    cs:__imp_RegCloseKey
0x1800a2a08  test    ebx, ebx
0x1800a2a0a  jnz     short loc_1800A2A0F
0x1800a2a0c  mov     [r15], edi
0x1800a2a0f  mov     rcx, r13; char *
0x1800a2a12  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x1800a2a17  mov     eax, ebx
0x1800a2a19  mov     rcx, [rbp+60h+var_50]
0x1800a2a1d  xor     rcx, rsp; StackCookie
0x1800a2a20  call    __security_check_cookie
0x1800a2a25  add     rsp, 128h
0x1800a2a2c  pop     r15
0x1800a2a2e  pop     r14
0x1800a2a30  pop     r13
0x1800a2a32  pop     r12
0x1800a2a34  pop     rdi
0x1800a2a35  pop     rsi
0x1800a2a36  pop     rbx
0x1800a2a37  pop     rbp
0x1800a2a38  retn
```
