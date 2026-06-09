# WldpDisableDeveloperMode

- ea: `0x180028670`
- end: `0x180028730`
- name: `WldpDisableDeveloperMode`
- size: `192`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x18001f038`
- `0x1800203ec`
- `0x180027fd0`
- `0x180028670`
- `0x1800291e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180028708`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180028708`

## string_xrefs

- `0x1800286dd`: `onecore\base\ngscb\wldp\dll\wldp.cpp`

## pseudocode

```c
__int64 WldpDisableDeveloperMode()
{
  LPCWSTR v0; // rbx
  LSTATUS IsDeviceLockedDown; // eax
  unsigned int v2; // edi
  __int64 v3; // rdx
  LPCWSTR v5[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  unsigned __int8 v7; // [rsp+50h] [rbp+20h] BYREF
  int v8; // [rsp+58h] [rbp+28h] BYREF
  LPCWSTR lpSubKey; // [rsp+60h] [rbp+30h] BYREF

  v8 = 0;
  lpSubKey = 0;
  v7 = 0;
  v0 = 0;
  v5[0] = 0;
  IsDeviceLockedDown = WldpIsDeviceLockedDown(&v8);
  v2 = IsDeviceLockedDown;
  if ( IsDeviceLockedDown >= 0 )
  {
    if ( v8 )
    {
      IsDeviceLockedDown = WldpGetSepRegistryLocation(
                             L"CIDeveloper",
                             L"SYSTEM\\CurrentControlSet\\Control\\CI\\Developer\\DeveloperUnlock",
                             &v7,
                             (unsigned __int16 **)&lpSubKey);
      v2 = IsDeviceLockedDown;
      if ( IsDeviceLockedDown < 0 )
      {
        v3 = 1977;
        goto LABEL_6;
      }
      if ( v7 )
        v0 = lpSubKey;
      v5[0] = v0;
      IsDeviceLockedDown = RegDeleteKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0);
      v2 = IsDeviceLockedDown;
      if ( IsDeviceLockedDown < 0 )
      {
        v3 = 1988;
        goto LABEL_6;
      }
    }
    v2 = 0;
    goto LABEL_12;
  }
  v3 = 1967;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\wldp.cpp",
    (const char *)(unsigned int)IsDeviceLockedDown,
    (int)v5[0]);
LABEL_12:
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(v5);
  return v2;
}

```

## disassembly

```asm
0x180028670  push    rbp
0x180028672  push    rbx
0x180028673  push    rdi
0x180028674  mov     rbp, rsp
0x180028677  sub     rsp, 30h
0x18002867b  mov     [rbp+arg_8], 0
0x180028682  mov     [rbp+lpSubKey], 0
0x18002868a  mov     [rbp+arg_0], 0
0x18002868e  xor     ebx, ebx
0x180028690  mov     [rbp+var_10], rbx
0x180028694  lea     rcx, [rbp+arg_8]
0x180028698  call    WldpIsDeviceLockedDown
0x18002869d  mov     edi, eax
0x18002869f  test    eax, eax
0x1800286a1  jns     short loc_1800286AA
0x1800286a3  mov     edx, 7AFh
0x1800286a8  jmp     short loc_1800286D6
0x1800286aa  cmp     [rbp+arg_8], 0
0x1800286ae  jz      short loc_18002871B
0x1800286b0  lea     r9, [rbp+lpSubKey]; unsigned __int16 **
0x1800286b4  lea     r8, [rbp+arg_0]; unsigned __int8 *
0x1800286b8  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\CI"...
0x1800286bf  lea     rcx, aCideveloper; "CIDeveloper"
0x1800286c6  call    ?WldpGetSepRegistryLocation@@YAJPEBGPEAGPEAEPEAPEAG@Z; WldpGetSepRegistryLocation(ushort const *,ushort *,uchar *,ushort * *)
0x1800286cb  mov     edi, eax
0x1800286cd  test    eax, eax
0x1800286cf  jns     short loc_1800286EB
0x1800286d1  mov     edx, 7B9h; void *
0x1800286d6  mov     rcx, [rbp+18h]; this
0x1800286da  mov     r9d, eax; char *
0x1800286dd  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\wldp\\dll\\wldp.c"...
0x1800286e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800286e9  jmp     short loc_18002871D
0x1800286eb  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800286ef  cmp     [rbp+arg_0], 0
0x1800286f3  cmovnz  rbx, rdx
0x1800286f7  mov     [rbp+var_10], rbx
0x1800286fb  xor     r9d, r9d; Reserved
0x1800286fe  xor     r8d, r8d; samDesired
0x180028701  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028708  call    cs:__imp_RegDeleteKeyExW
0x18002870e  mov     edi, eax
0x180028710  test    eax, eax
0x180028712  jns     short loc_18002871B
0x180028714  mov     edx, 7C4h
0x180028719  jmp     short loc_1800286D6
0x18002871b  xor     edi, edi
0x18002871d  lea     rcx, [rbp+var_10]
0x180028721  call    ??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)
0x180028726  mov     eax, edi
0x180028728  add     rsp, 30h
0x18002872c  pop     rdi
0x18002872d  pop     rbx
0x18002872e  pop     rbp
0x18002872f  retn
```
