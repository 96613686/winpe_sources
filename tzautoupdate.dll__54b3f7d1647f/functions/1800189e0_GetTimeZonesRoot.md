# GetTimeZonesRoot

- ea: `0x1800189e0`
- end: `0x180018a3b`
- name: `GetTimeZonesRoot`
- size: `91`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017848`
- `0x1800179f4`
- `0x180017dd0`
- `0x18001831c`
- `0x18001859c`

## callees

- `0x1800189e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018a18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018a18`

## pseudocode

```c
__int64 __fastcall GetTimeZonesRoot(HKEY *a1)
{
  HKEY v1; // rax

  v1 = tzapi_globals;
  if ( !tzapi_globals )
  {
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Time Zones",
           0,
           0x20019u,
           &tzapi_globals) )
    {
      return 2147746307LL;
    }
    v1 = tzapi_globals;
  }
  *a1 = v1;
  return 0;
}

```

## disassembly

```asm
0x1800189e0  push    rbx
0x1800189e2  sub     rsp, 30h
0x1800189e6  mov     rax, cs:_tzapi_globals
0x1800189ed  mov     rbx, rcx
0x1800189f0  test    rax, rax
0x1800189f3  jnz     short loc_180018A30
0x1800189f5  lea     rax, _tzapi_globals
0x1800189fc  mov     r9d, 20019h; samDesired
0x180018a02  xor     r8d, r8d; ulOptions
0x180018a05  mov     [rsp+38h+phkResult], rax; phkResult
0x180018a0a  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180018a11  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018a18  call    cs:__imp_RegOpenKeyExW
0x180018a1e  test    eax, eax
0x180018a20  jz      short loc_180018A29
0x180018a22  mov     eax, 80040203h
0x180018a27  jmp     short loc_180018A35
0x180018a29  mov     rax, cs:_tzapi_globals
0x180018a30  mov     [rbx], rax
0x180018a33  xor     eax, eax
0x180018a35  add     rsp, 30h
0x180018a39  pop     rbx
0x180018a3a  retn
```
