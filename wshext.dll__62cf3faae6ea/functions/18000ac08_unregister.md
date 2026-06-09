# unregister

- ea: `0x18000ac08`
- end: `0x18000ac7b`
- name: `unregister`
- size: `115`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a270`
- `0x18000aacc`

## callees

- `0x18000a848`
- `0x18000ac08`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18000ac3e`
- `ADVAPI32!RegOpenKeyExA` at `0x18000ac3e`
- `ADVAPI32!RegCloseKey` at `0x18000ac63`
- `ADVAPI32!RegCloseKey` at `0x18000ac63`

## string_xrefs

- `0x18000ac37`: `CLSID`

## pseudocode

```c
__int64 __fastcall unregister(char *a1)
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
0x18000ac08  mov     r11, rsp
0x18000ac0b  mov     [r11+10h], rdx
0x18000ac0f  push    rbx
0x18000ac10  sub     rsp, 30h
0x18000ac14  mov     rbx, rcx
0x18000ac17  mov     qword ptr [r11+10h], 0
0x18000ac1f  lea     rax, [r11+10h]
0x18000ac23  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000ac2a  mov     r9d, 0F003Fh; samDesired
0x18000ac30  mov     [r11-18h], rax
0x18000ac34  xor     r8d, r8d; ulOptions
0x18000ac37  lea     rdx, aClsid; "CLSID"
0x18000ac3e  call    cs:__imp_RegOpenKeyExA
0x18000ac44  test    eax, eax
0x18000ac46  jz      short loc_18000AC4F
0x18000ac48  mov     eax, 8000FFFFh
0x18000ac4d  jmp     short loc_18000AC75
0x18000ac4f  mov     rcx, [rsp+38h+hKey]; HKEY
0x18000ac54  mov     rdx, rbx; char *
0x18000ac57  call    ?DeleteKeyAndSubKeys@@YAJPEAUHKEY__@@PEBD@Z; DeleteKeyAndSubKeys(HKEY__ *,char const *)
0x18000ac5c  mov     rcx, [rsp+38h+hKey]; hKey
0x18000ac61  mov     ebx, eax
0x18000ac63  call    cs:__imp_RegCloseKey
0x18000ac69  test    eax, eax
0x18000ac6b  mov     ecx, 8000FFFFh
0x18000ac70  cmovnz  ebx, ecx
0x18000ac73  mov     eax, ebx
0x18000ac75  add     rsp, 30h
0x18000ac79  pop     rbx
0x18000ac7a  retn
```
