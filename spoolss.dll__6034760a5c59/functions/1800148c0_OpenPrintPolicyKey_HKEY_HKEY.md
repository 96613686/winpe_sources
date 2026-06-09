# OpenPrintPolicyKey(HKEY__ *,HKEY__ * *)

- ea: `0x1800148c0`
- end: `0x180014922`
- name: `?OpenPrintPolicyKey@@YAJPEAUHKEY__@@PEAPEAU1@@Z`
- size: `98`
- prototype: `__int64 __fastcall(HKEY, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014984`

## callees

- `0x1800148a8`
- `0x1800148c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014903`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014903`

## pseudocode

```c
__int64 __fastcall OpenPrintPolicyKey(HKEY a1, HKEY *a2)
{
  __int64 result; // rax
  unsigned int v4; // eax
  int v5; // edx
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  phkResult = 0;
  if ( !a2 )
    return 2147500035LL;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows NT\\Printers",
         0,
         0x20019u,
         &phkResult);
  result = NCoreLibrary::HResultFromWin32((NCoreLibrary *)v4, v5);
  if ( (int)result >= 0 )
    *a2 = phkResult;
  return result;
}

```

## disassembly

```asm
0x1800148c0  mov     [rsp+arg_0], rcx
0x1800148c5  push    rbx
0x1800148c6  sub     rsp, 30h
0x1800148ca  mov     [rsp+38h+arg_0], 0
0x1800148d3  mov     rbx, rdx
0x1800148d6  test    rdx, rdx
0x1800148d9  jnz     short loc_1800148E2
0x1800148db  mov     eax, 80004003h
0x1800148e0  jmp     short loc_18001491C
0x1800148e2  lea     rax, [rsp+38h+arg_0]
0x1800148e7  mov     r9d, 20019h; samDesired
0x1800148ed  xor     r8d, r8d; ulOptions
0x1800148f0  mov     [rsp+38h+phkResult], rax; phkResult
0x1800148f5  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows "...
0x1800148fc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014903  call    cs:__imp_RegOpenKeyExW
0x180014909  mov     ecx, eax; this
0x18001490b  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x180014910  test    eax, eax
0x180014912  js      short loc_18001491C
0x180014914  mov     rcx, [rsp+38h+arg_0]
0x180014919  mov     [rbx], rcx
0x18001491c  add     rsp, 30h
0x180014920  pop     rbx
0x180014921  retn
```
