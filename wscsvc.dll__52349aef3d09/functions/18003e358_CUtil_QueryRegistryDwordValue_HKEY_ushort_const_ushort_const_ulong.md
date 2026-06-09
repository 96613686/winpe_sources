# CUtil::QueryRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x18003e358`
- end: `0x18003e51c`
- name: `?QueryRegistryDwordValue@CUtil@@SAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `452`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180034b30`

## callees

- `0x1800202e8`
- `0x18003e358`
- `0x18003e524`
- `0x18003e5f4`
- `0x18003e7e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e3d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e3d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e4b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e4b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e419`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e419`

## pseudocode

```c
__int64 __fastcall CUtil::QueryRegistryDwordValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  int v8; // ebx
  int v9; // r8d
  int v10; // r9d
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  DWORD cbData; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  HKEY Type; // [rsp+70h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+88h] [rbp+38h] BYREF

  Type = a1;
  if ( a4 )
  {
    hKey = 0;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x11u, &hKey);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v9, v10, (__int64)a2, v8);
      }
      if ( v8 > 0 )
        return (unsigned __int16)v8 | 0x80070000;
    }
    else
    {
      Data = 0;
      cbData = 4;
      LODWORD(Type) = 4;
      v8 = RegQueryValueExW(hKey, a3, 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData);
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_qSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v12, v13, (__int64)a2, (__int64)a3, v8);
        }
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
      }
      else if ( (_DWORD)Type == 4 )
      {
        *a4 = Data;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, v13, (__int64)a2, (__int64)a3);
        }
        v8 = -2147023092;
      }
      RegCloseKey(hKey);
    }
    return (unsigned int)v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18003e358  mov     [rsp-18h+arg_8], rbx
0x18003e35d  mov     [rsp-18h+arg_10], rsi
0x18003e362  mov     [rsp-18h+Type], rcx
0x18003e367  push    rbp
0x18003e368  push    rdi
0x18003e369  push    r14
0x18003e36b  mov     rbp, rsp
0x18003e36e  sub     rsp, 50h
0x18003e372  mov     r14, r9
0x18003e375  mov     rsi, r8
0x18003e378  mov     rdi, rdx
0x18003e37b  test    r9, r9
0x18003e37e  jnz     short loc_18003E3B7
0x18003e380  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e387  lea     rax, WPP_GLOBAL_Control
0x18003e38e  cmp     rcx, rax
0x18003e391  jz      short loc_18003E3AD
0x18003e393  test    byte ptr [rcx+1Ch], 1
0x18003e397  jz      short loc_18003E3AD
0x18003e399  mov     rcx, [rcx+10h]
0x18003e39d  lea     edx, [r9+12h]
0x18003e3a1  lea     r8, WPP_bc50b57d3a7f3ca15f27abc6215da79e_Traceguids
0x18003e3a8  call    WPP_SF_
0x18003e3ad  mov     eax, 80070057h
0x18003e3b2  jmp     loc_18003E507
0x18003e3b7  lea     rax, [rbp+hKey]
0x18003e3bb  mov     [rbp+hKey], 0
0x18003e3c3  mov     r9d, 11h; samDesired
0x18003e3c9  mov     [rsp+50h+phkResult], rax; phkResult
0x18003e3ce  xor     r8d, r8d; ulOptions
0x18003e3d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e3d8  call    cs:__imp_RegOpenKeyExW
0x18003e3de  mov     ebx, eax
0x18003e3e0  test    eax, eax
0x18003e3e2  jnz     loc_18003E4BE
0x18003e3e8  mov     rcx, [rbp+hKey]; hKey
0x18003e3ec  lea     r9, [rbp+Type]; lpType
0x18003e3f0  mov     [rbp+Data], eax
0x18003e3f3  xor     r8d, r8d; lpReserved
0x18003e3f6  lea     rax, [rbp+cbData]
0x18003e3fa  mov     [rbp+cbData], 4
0x18003e401  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18003e406  mov     rdx, rsi; lpValueName
0x18003e409  lea     rax, [rbp+Data]
0x18003e40d  mov     dword ptr [rbp+Type], 4
0x18003e414  mov     [rsp+50h+phkResult], rax; lpData
0x18003e419  call    cs:__imp_RegQueryValueExW
0x18003e41f  mov     ebx, eax
0x18003e421  test    eax, eax
0x18003e423  jnz     short loc_18003E466
0x18003e425  cmp     dword ptr [rbp+Type], 4
0x18003e429  jnz     short loc_18003E433
0x18003e42b  mov     eax, [rbp+Data]
0x18003e42e  mov     [r14], eax
0x18003e431  jmp     short loc_18003E4B2
0x18003e433  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e43a  lea     rax, WPP_GLOBAL_Control
0x18003e441  cmp     rcx, rax
0x18003e444  jz      short loc_18003E45F
0x18003e446  test    byte ptr [rcx+1Ch], 1
0x18003e44a  jz      short loc_18003E45F
0x18003e44c  mov     rcx, [rcx+10h]
0x18003e450  mov     [rsp+50h+lpcbData], rsi
0x18003e455  mov     [rsp+50h+phkResult], rdi
0x18003e45a  call    WPP_SF_qSS
0x18003e45f  mov     ebx, 8007070Ch
0x18003e464  jmp     short loc_18003E4B2
0x18003e466  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e46d  lea     rax, WPP_GLOBAL_Control
0x18003e474  cmp     rcx, rax
0x18003e477  jz      short loc_18003E49B
0x18003e479  test    byte ptr [rcx+1Ch], 1
0x18003e47d  jz      short loc_18003E49B
0x18003e47f  mov     rcx, [rcx+10h]
0x18003e483  mov     edx, 14h
0x18003e488  mov     [rsp+50h+var_20], ebx
0x18003e48c  mov     [rsp+50h+lpcbData], rsi
0x18003e491  mov     [rsp+50h+phkResult], rdi
0x18003e496  call    WPP_SF_qSSd
0x18003e49b  test    ebx, ebx
0x18003e49d  jle     short loc_18003E4A8
0x18003e49f  movzx   ebx, bx
0x18003e4a2  or      ebx, 80070000h
0x18003e4a8  test    ebx, ebx
0x18003e4aa  mov     eax, 80004005h
0x18003e4af  cmovns  ebx, eax
0x18003e4b2  mov     rcx, [rbp+hKey]; hKey
0x18003e4b6  call    cs:__imp_RegCloseKey
0x18003e4bc  jmp     short loc_18003E505
0x18003e4be  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e4c5  lea     rax, WPP_GLOBAL_Control
0x18003e4cc  cmp     rcx, rax
0x18003e4cf  jz      short loc_18003E4EE
0x18003e4d1  test    byte ptr [rcx+1Ch], 1
0x18003e4d5  jz      short loc_18003E4EE
0x18003e4d7  mov     rcx, [rcx+10h]
0x18003e4db  mov     edx, 15h
0x18003e4e0  mov     dword ptr [rsp+50h+lpcbData], ebx
0x18003e4e4  mov     [rsp+50h+phkResult], rdi
0x18003e4e9  call    WPP_SF_qSd
0x18003e4ee  test    ebx, ebx
0x18003e4f0  jle     short loc_18003E4FB
0x18003e4f2  movzx   ebx, bx
0x18003e4f5  or      ebx, 80070000h
0x18003e4fb  test    ebx, ebx
0x18003e4fd  mov     eax, 80004005h
0x18003e502  cmovns  ebx, eax
0x18003e505  mov     eax, ebx
0x18003e507  lea     r11, [rsp+50h+var_s0]
0x18003e50c  mov     rbx, [r11+28h]
0x18003e510  mov     rsi, [r11+30h]
0x18003e514  mov     rsp, r11
0x18003e517  pop     r14
0x18003e519  pop     rdi
0x18003e51a  pop     rbp
0x18003e51b  retn
```
