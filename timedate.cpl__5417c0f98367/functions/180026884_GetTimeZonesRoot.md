# GetTimeZonesRoot

- ea: `0x180026884`
- end: `0x1800268df`
- name: `GetTimeZonesRoot`
- size: `91`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024984`
- `0x180024bb8`
- `0x180024e1c`
- `0x180024f30`
- `0x1800251f8`
- `0x180025658`
- `0x1800257cc`
- `0x180026010`
- `0x180026360`

## callees

- `0x180026884`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800268bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800268bc`

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
0x180026884  push    rbx
0x180026886  sub     rsp, 30h
0x18002688a  mov     rax, cs:_tzapi_globals
0x180026891  mov     rbx, rcx
0x180026894  test    rax, rax
0x180026897  jnz     short loc_1800268D4
0x180026899  lea     rax, _tzapi_globals
0x1800268a0  mov     r9d, 20019h; samDesired
0x1800268a6  xor     r8d, r8d; ulOptions
0x1800268a9  mov     [rsp+38h+phkResult], rax; phkResult
0x1800268ae  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800268b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800268bc  call    cs:__imp_RegOpenKeyExW
0x1800268c2  test    eax, eax
0x1800268c4  jz      short loc_1800268CD
0x1800268c6  mov     eax, 80040203h
0x1800268cb  jmp     short loc_1800268D9
0x1800268cd  mov     rax, cs:_tzapi_globals
0x1800268d4  mov     [rbx], rax
0x1800268d7  xor     eax, eax
0x1800268d9  add     rsp, 30h
0x1800268dd  pop     rbx
0x1800268de  retn
```
