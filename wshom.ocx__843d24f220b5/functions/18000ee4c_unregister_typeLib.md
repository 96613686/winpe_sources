# unregister_typeLib

- ea: `0x18000ee4c`
- end: `0x18000eee9`
- name: `unregister_typeLib`
- size: `157`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ecec`

## callees

- `0x18000e5b4`
- `0x18000e81c`
- `0x18000ee4c`
- `0x180010250`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18000ee94`
- `ADVAPI32!RegOpenKeyExA` at `0x18000ee94`
- `ADVAPI32!RegCloseKey` at `0x18000eec8`
- `ADVAPI32!RegCloseKey` at `0x18000eec8`

## pseudocode

```c
__int64 __fastcall unregister_typeLib(struct _GUID *a1)
{
  int v2; // r8d
  unsigned int v4; // ebx
  HKEY hKey; // [rsp+30h] [rbp-98h] BYREF
  char v6[112]; // [rsp+40h] [rbp-88h] BYREF

  hKey = 0;
  if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, "TypeLib", 0, 0xF003Fu, &hKey) )
    return 2147549183LL;
  StringFromGUID2A(a1, v6, v2);
  v4 = DeleteKeyAndSubKeys(hKey, v6);
  RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x18000ee4c  push    rbx
0x18000ee4e  sub     rsp, 0C0h
0x18000ee55  mov     rax, cs:__security_cookie
0x18000ee5c  xor     rax, rsp
0x18000ee5f  mov     [rsp+0C8h+var_18], rax
0x18000ee67  mov     rbx, rcx
0x18000ee6a  mov     [rsp+0C8h+hKey], 0
0x18000ee73  lea     rax, [rsp+0C8h+hKey]
0x18000ee78  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000ee7f  mov     r9d, 0F003Fh; samDesired
0x18000ee85  mov     [rsp+0C8h+phkResult], rax; phkResult
0x18000ee8a  xor     r8d, r8d; ulOptions
0x18000ee8d  lea     rdx, aTypelib; "TypeLib"
0x18000ee94  call    cs:__imp_RegOpenKeyExA
0x18000ee9a  test    eax, eax
0x18000ee9c  jz      short loc_18000EEA5
0x18000ee9e  mov     eax, 8000FFFFh
0x18000eea3  jmp     short loc_18000EED0
0x18000eea5  lea     rdx, [rsp+0C8h+var_88]; char *
0x18000eeaa  mov     rcx, rbx; struct _GUID *
0x18000eead  call    ?StringFromGUID2A@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2A(_GUID const &,char *,int)
0x18000eeb2  mov     rcx, [rsp+0C8h+hKey]; HKEY
0x18000eeb7  lea     rdx, [rsp+0C8h+var_88]; char *
0x18000eebc  call    ?DeleteKeyAndSubKeys@@YAJPEAUHKEY__@@PEBD@Z; DeleteKeyAndSubKeys(HKEY__ *,char const *)
0x18000eec1  mov     rcx, [rsp+0C8h+hKey]; hKey
0x18000eec6  mov     ebx, eax
0x18000eec8  call    cs:__imp_RegCloseKey
0x18000eece  mov     eax, ebx
0x18000eed0  mov     rcx, [rsp+0C8h+var_18]
0x18000eed8  xor     rcx, rsp; StackCookie
0x18000eedb  call    __security_check_cookie
0x18000eee0  add     rsp, 0C0h
0x18000eee7  pop     rbx
0x18000eee8  retn
```
