# ItSpRetrieveRuntimeOverrides(_IT_IDLE_RUNTIME_PARAMETERS *)

- ea: `0x180072ec0`
- end: `0x180072f59`
- name: `?ItSpRetrieveRuntimeOverrides@@YAKPEAU_IT_IDLE_RUNTIME_PARAMETERS@@@Z`
- size: `153`
- prototype: `unsigned int __fastcall(struct _IT_IDLE_RUNTIME_PARAMETERS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180073c94`

## callees

- `0x180072cc4`
- `0x180072d88`
- `0x180072ec0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072ef6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072ef6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072f46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072f46`

## string_xrefs

- `0x180072eef`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\IdleService`

## pseudocode

```c
__int64 __fastcall ItSpRetrieveRuntimeOverrides(struct _IT_IDLE_RUNTIME_PARAMETERS *a1)
{
  LSTATUS v2; // eax
  unsigned int OverrideValue; // ebx
  const unsigned __int16 *v4; // rdx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\IdleService",
         0,
         0xF003Fu,
         &hKey);
  OverrideValue = v2;
  if ( (unsigned int)(v2 - 2) <= 1 )
  {
    OverrideValue = 0;
  }
  else if ( !v2 )
  {
    OverrideValue = ItSpRetrieveOverrideValue(hKey, L"SkipNotification", (unsigned __int8 *)a1);
    if ( !OverrideValue )
      OverrideValue = ItSpRetrieveOverrideValue(hKey, v4, (unsigned __int16 **)a1 + 1, (unsigned int *)a1 + 1);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return OverrideValue;
}

```

## disassembly

```asm
0x180072ec0  mov     r11, rsp
0x180072ec3  mov     [r11+8], rbx
0x180072ec7  push    rdi
0x180072ec8  sub     rsp, 30h
0x180072ecc  mov     rdi, rcx
0x180072ecf  mov     qword ptr [r11+10h], 0
0x180072ed7  lea     rax, [r11+10h]
0x180072edb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180072ee2  mov     r9d, 0F003Fh; samDesired
0x180072ee8  mov     [r11-18h], rax
0x180072eec  xor     r8d, r8d; ulOptions
0x180072eef  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180072ef6  call    cs:__imp_RegOpenKeyExW
0x180072efc  mov     ebx, eax
0x180072efe  lea     edx, [rax-2]
0x180072f01  cmp     edx, 1
0x180072f04  jbe     short loc_180072F3A
0x180072f06  test    eax, eax
0x180072f08  jnz     short loc_180072F3C
0x180072f0a  mov     rcx, [rsp+38h+hKey]; HKEY
0x180072f0f  lea     rdx, aSkipnotificati; "SkipNotification"
0x180072f16  mov     r8, rdi; unsigned __int8 *
0x180072f19  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAE@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,uchar *)
0x180072f1e  mov     ebx, eax
0x180072f20  test    eax, eax
0x180072f22  jnz     short loc_180072F3C
0x180072f24  mov     rcx, [rsp+38h+hKey]; hKey
0x180072f29  lea     r9, [rdi+4]; unsigned int *
0x180072f2d  lea     r8, [rdi+8]; unsigned __int16 **
0x180072f31  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAPEAGPEAK@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,ushort * *,ulong *)
0x180072f36  mov     ebx, eax
0x180072f38  jmp     short loc_180072F3C
0x180072f3a  xor     ebx, ebx
0x180072f3c  mov     rcx, [rsp+38h+hKey]; hKey
0x180072f41  test    rcx, rcx
0x180072f44  jz      short loc_180072F4C
0x180072f46  call    cs:__imp_RegCloseKey
0x180072f4c  mov     eax, ebx
0x180072f4e  mov     rbx, [rsp+38h+arg_0]
0x180072f53  add     rsp, 30h
0x180072f57  pop     rdi
0x180072f58  retn
```
