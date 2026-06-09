# ItSpRetrieveRuntimeOverrides(_IT_IDLE_RUNTIME_PARAMETERS *)

- ea: `0x1800769b8`
- end: `0x180076a5e`
- name: `?ItSpRetrieveRuntimeOverrides@@YAKPEAU_IT_IDLE_RUNTIME_PARAMETERS@@@Z`
- size: `166`
- prototype: `unsigned int __fastcall(struct _IT_IDLE_RUNTIME_PARAMETERS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180077974`

## callees

- `0x180076778`
- `0x18007684c`
- `0x1800769b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800769ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800769ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076a44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076a44`

## string_xrefs

- `0x1800769e7`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\IdleService`

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
0x1800769b8  mov     r11, rsp
0x1800769bb  mov     [r11+8], rbx
0x1800769bf  push    rdi
0x1800769c0  sub     rsp, 30h
0x1800769c4  mov     rdi, rcx
0x1800769c7  mov     qword ptr [r11+10h], 0
0x1800769cf  lea     rax, [r11+10h]
0x1800769d3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800769da  mov     r9d, 0F003Fh; samDesired
0x1800769e0  mov     [r11-18h], rax
0x1800769e4  xor     r8d, r8d; ulOptions
0x1800769e7  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800769ee  call    cs:__imp_RegOpenKeyExW
0x1800769f5  nop     dword ptr [rax+rax+00h]
0x1800769fa  mov     ebx, eax
0x1800769fc  lea     edx, [rax-2]
0x1800769ff  cmp     edx, 1
0x180076a02  jbe     short loc_180076A38
0x180076a04  test    eax, eax
0x180076a06  jnz     short loc_180076A3A
0x180076a08  mov     rcx, [rsp+38h+hKey]; HKEY
0x180076a0d  lea     rdx, aSkipnotificati; "SkipNotification"
0x180076a14  mov     r8, rdi; unsigned __int8 *
0x180076a17  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAE@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,uchar *)
0x180076a1c  mov     ebx, eax
0x180076a1e  test    eax, eax
0x180076a20  jnz     short loc_180076A3A
0x180076a22  mov     rcx, [rsp+38h+hKey]; hKey
0x180076a27  lea     r9, [rdi+4]; unsigned int *
0x180076a2b  lea     r8, [rdi+8]; unsigned __int16 **
0x180076a2f  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAPEAGPEAK@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,ushort * *,ulong *)
0x180076a34  mov     ebx, eax
0x180076a36  jmp     short loc_180076A3A
0x180076a38  xor     ebx, ebx
0x180076a3a  mov     rcx, [rsp+38h+hKey]; hKey
0x180076a3f  test    rcx, rcx
0x180076a42  jz      short loc_180076A50
0x180076a44  call    cs:__imp_RegCloseKey
0x180076a4b  nop     dword ptr [rax+rax+00h]
0x180076a50  mov     eax, ebx
0x180076a52  mov     rbx, [rsp+38h+arg_0]
0x180076a57  add     rsp, 30h
0x180076a5b  pop     rdi
0x180076a5c  retn
```
