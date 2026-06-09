# unregister_0

- ea: `0x18000edd0`
- end: `0x18000ee43`
- name: `unregister_0`
- size: `115`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e8b8`
- `0x18000ebac`
- `0x18000ecec`

## callees

- `0x18000e5b4`
- `0x18000edd0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18000ee06`
- `ADVAPI32!RegOpenKeyExA` at `0x18000ee06`
- `ADVAPI32!RegCloseKey` at `0x18000ee2b`
- `ADVAPI32!RegCloseKey` at `0x18000ee2b`

## string_xrefs

- `0x18000edff`: `CLSID`

## pseudocode

```c
__int64 __fastcall unregister_0(char *a1)
{
  unsigned int v3; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0xF003Fu, &hKey) )
    return 2147549183LL;
  v3 = DeleteKeyAndSubKeys(hKey, a1);
  if ( RegCloseKey(hKey) )
    return (unsigned int)-2147418113;
  return v3;
}

```

## disassembly

```asm
0x18000edd0  mov     r11, rsp
0x18000edd3  mov     [r11+10h], rdx
0x18000edd7  push    rbx
0x18000edd8  sub     rsp, 30h
0x18000eddc  mov     rbx, rcx
0x18000eddf  mov     qword ptr [r11+10h], 0
0x18000ede7  lea     rax, [r11+10h]
0x18000edeb  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000edf2  mov     r9d, 0F003Fh; samDesired
0x18000edf8  mov     [r11-18h], rax
0x18000edfc  xor     r8d, r8d; ulOptions
0x18000edff  lea     rdx, aClsid; "CLSID"
0x18000ee06  call    cs:__imp_RegOpenKeyExA
0x18000ee0c  test    eax, eax
0x18000ee0e  jz      short loc_18000EE17
0x18000ee10  mov     eax, 8000FFFFh
0x18000ee15  jmp     short loc_18000EE3D
0x18000ee17  mov     rcx, [rsp+38h+hKey]; HKEY
0x18000ee1c  mov     rdx, rbx; char *
0x18000ee1f  call    ?DeleteKeyAndSubKeys@@YAJPEAUHKEY__@@PEBD@Z; DeleteKeyAndSubKeys(HKEY__ *,char const *)
0x18000ee24  mov     rcx, [rsp+38h+hKey]; hKey
0x18000ee29  mov     ebx, eax
0x18000ee2b  call    cs:__imp_RegCloseKey
0x18000ee31  test    eax, eax
0x18000ee33  mov     ecx, 8000FFFFh
0x18000ee38  cmovnz  ebx, ecx
0x18000ee3b  mov     eax, ebx
0x18000ee3d  add     rsp, 30h
0x18000ee41  pop     rbx
0x18000ee42  retn
```
