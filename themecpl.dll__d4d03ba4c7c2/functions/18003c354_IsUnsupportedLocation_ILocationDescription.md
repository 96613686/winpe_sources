# IsUnsupportedLocation(ILocationDescription *)

- ea: `0x18003c354`
- end: `0x18003c523`
- name: `?IsUnsupportedLocation@@YAHPEAUILocationDescription@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(struct ILocationDescription *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b224`

## callees

- `0x180002280`
- `0x18003c354`
- `0x180057010`

## import_xrefs

- `PROPSYS!PropVariantToBooleanWithDefault` at `0x18003c4c7`
- `PROPSYS!PropVariantToBooleanWithDefault` at `0x18003c4c7`
- `SHLWAPI!SHRegGetValueW` at `0x18003c416`
- `SHLWAPI!SHRegGetValueW` at `0x18003c416`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18003c38b`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18003c38b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c435`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c435`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c3d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c3d1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c4da`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003c4da`

## pseudocode

```c
_BOOL8 __fastcall IsUnsupportedLocation(struct ILocationDescription *a1, const CHAR *a2)
{
  BOOL v3; // ebx
  int v4; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v8; // [rsp+50h] [rbp-B0h] BYREF
  PROPVARIANT propvarIn[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v10; // [rsp+68h] [rbp-98h]
  _BYTE pvData[528]; // [rsp+70h] [rbp-90h] BYREF

  v3 = 0;
  if ( !SHWindowsPolicy(&POLID_DisableIndexedLibraryExperience, a2) )
  {
    v4 = g_tbSearchComponent;
    if ( !g_tbSearchComponent )
    {
      hkey = 0;
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows Search", 0, 1u, &hkey) )
      {
        v4 = 1;
        g_tbSearchComponent = 1;
      }
      else
      {
        pcbData = 520;
        g_tbSearchComponent = (SHRegGetValueW(hkey, 0, L"CurrentVersion", 0xFFFF, 0, pvData, &pcbData) != 0) + 1;
        RegCloseKey(hkey);
        v4 = g_tbSearchComponent;
      }
    }
    LOBYTE(v3) = v4 == 1;
  }
  v8 = 0;
  if ( v3
    && (*(int (__fastcall **)(struct ILocationDescription *, GUID *, __int64 *))(*(_QWORD *)a1 + 176LL))(
         a1,
         &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
         &v8) >= 0 )
  {
    v10 = 0;
    *(_OWORD *)propvarIn = 0;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v8 + 40LL))(
           v8,
           &PKEY_IsLocationSupported,
           propvarIn) >= 0 )
    {
      v3 = PropVariantToBooleanWithDefault(propvarIn, 1);
      PropVariantClear(propvarIn);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return !v3;
}

```

## disassembly

```asm
0x18003c354  mov     [rsp-8+arg_8], rbx
0x18003c359  mov     [rsp-8+arg_10], rdi
0x18003c35e  push    rbp
0x18003c35f  lea     rbp, [rsp-190h]
0x18003c367  sub     rsp, 290h
0x18003c36e  mov     rax, cs:__security_cookie
0x18003c375  xor     rax, rsp
0x18003c378  mov     [rbp+190h+var_10], rax
0x18003c37f  mov     rdi, rcx
0x18003c382  xor     ebx, ebx
0x18003c384  lea     rcx, POLID_DisableIndexedLibraryExperience; pszPath
0x18003c38b  call    cs:__imp_SHWindowsPolicy
0x18003c392  nop     dword ptr [rax+rax+00h]
0x18003c397  test    eax, eax
0x18003c399  jnz     loc_18003C45A
0x18003c39f  mov     eax, cs:?g_tbSearchComponent@@3W4TRIBIT@@A; TRIBIT g_tbSearchComponent
0x18003c3a5  test    eax, eax
0x18003c3a7  jnz     loc_18003C454
0x18003c3ad  lea     rax, [rsp+290h+hkey]
0x18003c3b2  mov     [rsp+290h+hkey], rbx
0x18003c3b7  lea     r9d, [rbx+1]; samDesired
0x18003c3bb  mov     [rsp+290h+phkResult], rax; phkResult
0x18003c3c0  xor     r8d, r8d; ulOptions
0x18003c3c3  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows Search"
0x18003c3ca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c3d1  call    cs:__imp_RegOpenKeyExW
0x18003c3d8  nop     dword ptr [rax+rax+00h]
0x18003c3dd  test    eax, eax
0x18003c3df  jnz     short loc_18003C449
0x18003c3e1  mov     rcx, [rsp+290h+hkey]; hkey
0x18003c3e6  lea     rax, [rsp+290h+var_250]
0x18003c3eb  mov     [rsp+290h+pcbData], rax; pcbData
0x18003c3f0  lea     r8, aCurrentversion; "CurrentVersion"
0x18003c3f7  lea     rax, [rsp+290h+var_220]
0x18003c3fc  mov     [rsp+290h+var_250], 208h
0x18003c404  mov     [rsp+290h+pvData], rax; pvData
0x18003c409  mov     r9d, 0FFFFh; srrfFlags
0x18003c40f  xor     edx, edx; pszSubKey
0x18003c411  mov     [rsp+290h+phkResult], rbx; pdwType
0x18003c416  call    cs:__imp_SHRegGetValueW
0x18003c41d  nop     dword ptr [rax+rax+00h]
0x18003c422  neg     eax
0x18003c424  sbb     ecx, ecx
0x18003c426  neg     ecx
0x18003c428  inc     ecx
0x18003c42a  mov     cs:?g_tbSearchComponent@@3W4TRIBIT@@A, ecx; TRIBIT g_tbSearchComponent
0x18003c430  mov     rcx, [rsp+290h+hkey]; hKey
0x18003c435  call    cs:__imp_RegCloseKey
0x18003c43c  nop     dword ptr [rax+rax+00h]
0x18003c441  mov     eax, cs:?g_tbSearchComponent@@3W4TRIBIT@@A; TRIBIT g_tbSearchComponent
0x18003c447  jmp     short loc_18003C454
0x18003c449  mov     eax, 1
0x18003c44e  mov     cs:?g_tbSearchComponent@@3W4TRIBIT@@A, eax; TRIBIT g_tbSearchComponent
0x18003c454  cmp     eax, 1
0x18003c457  setz    bl
0x18003c45a  mov     [rsp+290h+var_240], 0
0x18003c463  test    ebx, ebx
0x18003c465  jz      loc_18003C4F7
0x18003c46b  mov     rax, [rdi]
0x18003c46e  lea     r8, [rsp+290h+var_240]
0x18003c473  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18003c47a  mov     rcx, rdi
0x18003c47d  mov     rax, [rax+0B0h]
0x18003c484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c489  test    eax, eax
0x18003c48b  js      short loc_18003C4F7
0x18003c48d  mov     rcx, [rsp+290h+var_240]
0x18003c492  lea     r8, [rsp+290h+propvarIn]
0x18003c497  xor     eax, eax
0x18003c499  lea     rdx, PKEY_IsLocationSupported
0x18003c4a0  mov     [rsp+290h+var_228], rax
0x18003c4a5  xorps   xmm0, xmm0
0x18003c4a8  movups  xmmword ptr [rsp+290h+propvarIn], xmm0
0x18003c4ad  mov     rax, [rcx]
0x18003c4b0  mov     rax, [rax+28h]
0x18003c4b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4b9  test    eax, eax
0x18003c4bb  js      short loc_18003C4E6
0x18003c4bd  mov     edx, 1; fDefault
0x18003c4c2  lea     rcx, [rsp+290h+propvarIn]; propvarIn
0x18003c4c7  call    cs:__imp_PropVariantToBooleanWithDefault
0x18003c4ce  nop     dword ptr [rax+rax+00h]
0x18003c4d3  lea     rcx, [rsp+290h+propvarIn]; pvar
0x18003c4d8  mov     ebx, eax
0x18003c4da  call    cs:__imp_PropVariantClear
0x18003c4e1  nop     dword ptr [rax+rax+00h]
0x18003c4e6  mov     rcx, [rsp+290h+var_240]
0x18003c4eb  mov     rdx, [rcx]
0x18003c4ee  mov     rax, [rdx+10h]
0x18003c4f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4f7  xor     eax, eax
0x18003c4f9  test    ebx, ebx
0x18003c4fb  setz    al
0x18003c4fe  mov     rcx, [rbp+190h+var_10]
0x18003c505  xor     rcx, rsp; StackCookie
0x18003c508  call    __security_check_cookie
0x18003c50d  lea     r11, [rsp+290h+var_s0]
0x18003c515  mov     rbx, [r11+18h]
0x18003c519  mov     rdi, [r11+20h]
0x18003c51d  mov     rsp, r11
0x18003c520  pop     rbp
0x18003c521  retn
```
