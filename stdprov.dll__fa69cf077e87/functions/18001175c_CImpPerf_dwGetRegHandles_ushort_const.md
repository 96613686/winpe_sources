# CImpPerf::dwGetRegHandles(ushort const *)

- ea: `0x18001175c`
- end: `0x1800118cb`
- name: `?dwGetRegHandles@CImpPerf@@QEAAKPEBG@Z`
- size: `367`
- prototype: `LSTATUS __fastcall(PCNZWCH *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010dc8`

## callees

- `0x180002e10`
- `0x18001175c`
- `0x180015680`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800117d2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180011845`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800117d2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180011845`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800117f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011806`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011883`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800117f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011806`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011883`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18001185b`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180011874`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18001185b`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180011874`

## pseudocode

```c
LSTATUS __fastcall CImpPerf::dwGetRegHandles(PCNZWCH *this, const unsigned __int16 *a2)
{
  LSTATUS result; // eax
  HKEY *v5; // rbx
  HKEY v6; // rcx
  HKEY *v7; // rdi
  LSTATUS v8; // esi
  WCHAR MachineName[256]; // [rsp+30h] [rbp-228h] BYREF

  if ( !a2 )
    return -2147217400;
  StringCchCopyW(MachineName, 0x100u, a2);
  v5 = (HKEY *)(this + 67);
  if ( CompareStringW(0x7Fu, 1u, this[68], -1, L"local", -1) == 2 )
  {
    v6 = *v5;
    if ( *v5 && v6 != HKEY_PERFORMANCE_DATA )
      RegCloseKey(v6);
    v7 = (HKEY *)(this + 65);
    if ( *v7 )
      RegCloseKey(*v7);
    *v7 = 0;
    *v5 = 0;
  }
  else
  {
    v7 = (HKEY *)(this + 65);
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"local", -1) == 2 )
  {
    *v7 = HKEY_LOCAL_MACHINE;
    *v5 = HKEY_PERFORMANCE_DATA;
  }
  else
  {
    result = RegConnectRegistryW(MachineName, HKEY_PERFORMANCE_DATA, v5);
    if ( result )
      return result;
    v8 = RegConnectRegistryW(MachineName, HKEY_LOCAL_MACHINE, v7);
    if ( v8 )
    {
      RegCloseKey(*v5);
      result = v8;
      *v7 = 0;
      *v5 = 0;
      return result;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001175c  mov     [rsp+arg_10], rbx
0x180011761  push    rsi
0x180011762  push    rdi
0x180011763  push    r14
0x180011765  sub     rsp, 240h
0x18001176c  mov     rax, cs:__security_cookie
0x180011773  xor     rax, rsp
0x180011776  mov     [rsp+258h+var_28], rax
0x18001177e  mov     rsi, rdx
0x180011781  mov     rdi, rcx
0x180011784  test    rdx, rdx
0x180011787  jnz     short loc_180011793
0x180011789  mov     eax, 80041008h
0x18001178e  jmp     loc_1800118A7
0x180011793  mov     r8, rsi; unsigned __int16 *
0x180011796  lea     rcx, [rsp+258h+MachineName]; unsigned __int16 *
0x18001179b  mov     edx, 100h; unsigned __int64
0x1800117a0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800117a5  mov     r8, [rdi+220h]; lpString1
0x1800117ac  lea     rax, aLocal_1; "local"
0x1800117b3  or      r9d, 0FFFFFFFFh; cchCount1
0x1800117b7  mov     [rsp+258h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800117bf  lea     rbx, [rdi+218h]
0x1800117c6  mov     [rsp+258h+lpString2], rax; lpString2
0x1800117cb  lea     edx, [r9+2]; dwCmpFlags
0x1800117cf  lea     ecx, [rdx+7Eh]; Locale
0x1800117d2  call    cs:__imp_CompareStringW
0x1800117d8  mov     r14, 0FFFFFFFF80000004h
0x1800117df  cmp     eax, 2
0x1800117e2  jnz     short loc_18001181C
0x1800117e4  mov     rcx, [rbx]; hKey
0x1800117e7  test    rcx, rcx
0x1800117ea  jz      short loc_1800117F7
0x1800117ec  cmp     rcx, r14
0x1800117ef  jz      short loc_1800117F7
0x1800117f1  call    cs:__imp_RegCloseKey
0x1800117f7  add     rdi, 208h
0x1800117fe  mov     rcx, [rdi]; hKey
0x180011801  test    rcx, rcx
0x180011804  jz      short loc_18001180C
0x180011806  call    cs:__imp_RegCloseKey
0x18001180c  mov     qword ptr [rdi], 0
0x180011813  mov     qword ptr [rbx], 0
0x18001181a  jmp     short loc_180011823
0x18001181c  add     rdi, 208h
0x180011823  or      r9d, 0FFFFFFFFh; cchCount1
0x180011827  mov     [rsp+258h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001182f  lea     rax, aLocal_1; "local"
0x180011836  mov     r8, rsi; lpString1
0x180011839  mov     [rsp+258h+lpString2], rax; lpString2
0x18001183e  lea     edx, [r9+2]; dwCmpFlags
0x180011842  lea     ecx, [rdx+7Eh]; Locale
0x180011845  call    cs:__imp_CompareStringW
0x18001184b  cmp     eax, 2
0x18001184e  jz      short loc_18001189B
0x180011850  mov     r8, rbx; phkResult
0x180011853  lea     rcx, [rsp+258h+MachineName]; lpMachineName
0x180011858  mov     rdx, r14; hKey
0x18001185b  call    cs:__imp_RegConnectRegistryW
0x180011861  test    eax, eax
0x180011863  jnz     short loc_1800118A7
0x180011865  mov     r8, rdi; phkResult
0x180011868  lea     rcx, [rsp+258h+MachineName]; lpMachineName
0x18001186d  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180011874  call    cs:__imp_RegConnectRegistryW
0x18001187a  mov     esi, eax
0x18001187c  test    eax, eax
0x18001187e  jz      short loc_1800118A5
0x180011880  mov     rcx, [rbx]; hKey
0x180011883  call    cs:__imp_RegCloseKey
0x180011889  mov     eax, esi
0x18001188b  mov     qword ptr [rdi], 0
0x180011892  mov     qword ptr [rbx], 0
0x180011899  jmp     short loc_1800118A7
0x18001189b  mov     qword ptr [rdi], 0FFFFFFFF80000002h
0x1800118a2  mov     [rbx], r14
0x1800118a5  xor     eax, eax
0x1800118a7  mov     rcx, [rsp+258h+var_28]
0x1800118af  xor     rcx, rsp; StackCookie
0x1800118b2  call    __security_check_cookie
0x1800118b7  mov     rbx, [rsp+258h+arg_10]
0x1800118bf  add     rsp, 240h
0x1800118c6  pop     r14
0x1800118c8  pop     rdi
0x1800118c9  pop     rsi
0x1800118ca  retn
```
