# ItSpStoreRuntimeOverrides(_IT_IDLE_RUNTIME_PARAMETERS *)

- ea: `0x180073a3c`
- end: `0x180073b22`
- name: `?ItSpStoreRuntimeOverrides@@YAKPEAU_IT_IDLE_RUNTIME_PARAMETERS@@@Z`
- size: `230`
- prototype: `unsigned int __fastcall(struct _IT_IDLE_RUNTIME_PARAMETERS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180074770`

## callees

- `0x180073a00`
- `0x180073a3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073ae1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073ae1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073a8f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073a8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073b0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073b0f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180073af2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180073af2`

## string_xrefs

- `0x180073a58`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\IdleService`

## pseudocode

```c
__int64 __fastcall ItSpStoreRuntimeOverrides(struct _IT_IDLE_RUNTIME_PARAMETERS *a1)
{
  unsigned int v2; // ebx
  const BYTE *v3; // rdx
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\IdleService",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         0);
  if ( !v2 )
  {
    v2 = ItSpStoreOverrideValue(hKey, L"SkipNotification", *(_BYTE *)a1);
    if ( !v2 )
    {
      if ( *((_DWORD *)a1 + 1) && (v3 = (const BYTE *)*((_QWORD *)a1 + 1)) != 0 )
      {
        v2 = RegSetValueExW(hKey, L"ExemptRegistrationList", 0, 7u, v3, *((_DWORD *)a1 + 1));
      }
      else
      {
        v2 = RegDeleteValueW(hKey, L"ExemptRegistrationList");
        if ( v2 - 2 <= 1 )
          v2 = 0;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180073a3c  mov     r11, rsp
0x180073a3f  mov     [r11+8], rbx
0x180073a43  push    rdi
0x180073a44  sub     rsp, 50h
0x180073a48  mov     qword ptr [r11-18h], 0
0x180073a50  lea     rax, [r11+10h]
0x180073a54  mov     [r11-20h], rax
0x180073a58  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180073a5f  mov     qword ptr [r11-28h], 0
0x180073a67  mov     rdi, rcx
0x180073a6a  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180073a72  xor     r9d, r9d; lpClass
0x180073a75  xor     r8d, r8d; Reserved
0x180073a78  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180073a80  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180073a87  mov     qword ptr [r11+10h], 0
0x180073a8f  call    cs:__imp_RegCreateKeyExW
0x180073a95  mov     ebx, eax
0x180073a97  test    eax, eax
0x180073a99  jnz     short loc_180073B05
0x180073a9b  mov     r8b, [rdi]; unsigned __int8
0x180073a9e  lea     rdx, aSkipnotificati; "SkipNotification"
0x180073aa5  mov     rcx, [rsp+58h+hKey]; HKEY
0x180073aaa  call    ?ItSpStoreOverrideValue@@YAKPEAUHKEY__@@PEBGE@Z; ItSpStoreOverrideValue(HKEY__ *,ushort const *,uchar)
0x180073aaf  mov     ebx, eax
0x180073ab1  test    eax, eax
0x180073ab3  jnz     short loc_180073B05
0x180073ab5  mov     eax, [rdi+4]
0x180073ab8  mov     rcx, [rsp+58h+hKey]; hKey
0x180073abd  test    eax, eax
0x180073abf  jz      short loc_180073AEB
0x180073ac1  mov     rdx, [rdi+8]
0x180073ac5  test    rdx, rdx
0x180073ac8  jz      short loc_180073AEB
0x180073aca  mov     [rsp+58h+samDesired], eax; cbData
0x180073ace  lea     r9d, [rbx+7]; dwType
0x180073ad2  mov     qword ptr [rsp+58h+dwOptions], rdx; lpData
0x180073ad7  xor     r8d, r8d; Reserved
0x180073ada  lea     rdx, aExemptregistra; "ExemptRegistrationList"
0x180073ae1  call    cs:__imp_RegSetValueExW
0x180073ae7  mov     ebx, eax
0x180073ae9  jmp     short loc_180073B05
0x180073aeb  lea     rdx, aExemptregistra; "ExemptRegistrationList"
0x180073af2  call    cs:__imp_RegDeleteValueW
0x180073af8  mov     ebx, eax
0x180073afa  lea     ecx, [rax-2]
0x180073afd  xor     eax, eax
0x180073aff  cmp     ecx, 1
0x180073b02  cmovbe  ebx, eax
0x180073b05  mov     rcx, [rsp+58h+hKey]; hKey
0x180073b0a  test    rcx, rcx
0x180073b0d  jz      short loc_180073B15
0x180073b0f  call    cs:__imp_RegCloseKey
0x180073b15  mov     eax, ebx
0x180073b17  mov     rbx, [rsp+58h+arg_0]
0x180073b1c  add     rsp, 50h
0x180073b20  pop     rdi
0x180073b21  retn
```
