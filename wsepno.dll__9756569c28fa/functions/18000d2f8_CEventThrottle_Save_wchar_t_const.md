# CEventThrottle::Save(wchar_t const *)

- ea: `0x18000d2f8`
- end: `0x18000d3ab`
- name: `?Save@CEventThrottle@@QEAA_NPEB_W@Z`
- size: `179`
- prototype: `bool __fastcall(BYTE *lpData, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d3b4`

## callees

- `0x180001770`
- `0x180003714`
- `0x18000cd50`
- `0x18000d2f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d37b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d37b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d38b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d38b`

## pseudocode

```c
bool __fastcall CEventThrottle::Save(BYTE *lpData, const wchar_t *a2)
{
  bool v3; // bl
  const wchar_t *v4; // rcx
  __int64 v5; // r8
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  WCHAR ValueName[16]; // [rsp+38h] [rbp-30h] BYREF

  v3 = 0;
  if ( (int)StringCchPrintfW(ValueName, 0x10u, L"%08x", *((unsigned int *)lpData + 5)) >= 0 )
  {
    hKey = 0;
    if ( !WSearchRegOpenKey(
            v4,
            (wchar_t *)L"Software\\Microsoft\\Windows Search\\Tracing\\EventThrottleState",
            v5,
            2u,
            &hKey) )
    {
      v3 = RegSetValueExW(hKey, ValueName, 0, 3u, lpData, 0x14u) == 0;
      RegCloseKey(hKey);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000d2f8  mov     [rsp+arg_8], rbx
0x18000d2fd  push    rdi
0x18000d2fe  sub     rsp, 60h
0x18000d302  mov     rax, cs:__security_cookie
0x18000d309  xor     rax, rsp
0x18000d30c  mov     [rsp+68h+var_10], rax
0x18000d311  mov     r9d, [rcx+14h]
0x18000d315  lea     r8, a08x; "%08x"
0x18000d31c  mov     rdi, rcx
0x18000d31f  mov     edx, 10h; unsigned __int64
0x18000d324  lea     rcx, [rsp+68h+ValueName]; wchar_t *
0x18000d329  xor     bl, bl
0x18000d32b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000d330  test    eax, eax
0x18000d332  js      short loc_18000D391
0x18000d334  lea     rax, [rsp+68h+hKey]
0x18000d339  mov     [rsp+68h+hKey], 0
0x18000d342  mov     r9d, 2; unsigned int
0x18000d348  mov     [rsp+68h+lpData], rax; HKEY *
0x18000d34d  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows Search\\Tr"...
0x18000d354  call    ?WSearchRegOpenKey@@YAJPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; WSearchRegOpenKey(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x18000d359  test    eax, eax
0x18000d35b  jnz     short loc_18000D391
0x18000d35d  mov     rcx, [rsp+68h+hKey]; hKey
0x18000d362  lea     r9d, [rax+3]; dwType
0x18000d366  mov     [rsp+68h+cbData], 14h; cbData
0x18000d36e  lea     rdx, [rsp+68h+ValueName]; lpValueName
0x18000d373  xor     r8d, r8d; Reserved
0x18000d376  mov     [rsp+68h+lpData], rdi; lpData
0x18000d37b  call    cs:__imp_RegSetValueExW
0x18000d381  mov     rcx, [rsp+68h+hKey]; hKey
0x18000d386  test    eax, eax
0x18000d388  setz    bl
0x18000d38b  call    cs:__imp_RegCloseKey
0x18000d391  mov     al, bl
0x18000d393  mov     rcx, [rsp+68h+var_10]
0x18000d398  xor     rcx, rsp; StackCookie
0x18000d39b  call    __security_check_cookie
0x18000d3a0  mov     rbx, [rsp+68h+arg_8]
0x18000d3a5  add     rsp, 60h
0x18000d3a9  pop     rdi
0x18000d3aa  retn
```
