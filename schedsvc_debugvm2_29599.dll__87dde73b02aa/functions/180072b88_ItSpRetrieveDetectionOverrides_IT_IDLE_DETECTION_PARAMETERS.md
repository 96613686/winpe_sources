# ItSpRetrieveDetectionOverrides(_IT_IDLE_DETECTION_PARAMETERS *)

- ea: `0x180072b88`
- end: `0x180072cbb`
- name: `?ItSpRetrieveDetectionOverrides@@YAKPEAU_IT_IDLE_DETECTION_PARAMETERS@@@Z`
- size: `307`
- prototype: `unsigned int __fastcall(struct _IT_IDLE_DETECTION_PARAMETERS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180073c94`

## callees

- `0x180072b88`
- `0x180072cc4`
- `0x180072d28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072bbe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072bbe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072ca8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072ca8`

## string_xrefs

- `0x180072bb7`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\IdleService`

## pseudocode

```c
__int64 __fastcall ItSpRetrieveDetectionOverrides(struct _IT_IDLE_DETECTION_PARAMETERS *a1)
{
  LSTATUS v2; // eax
  unsigned int OverrideValue; // ebx
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
    OverrideValue = ItSpRetrieveOverrideValue(hKey, L"IdleCheckTimeout", (unsigned int *)a1 + 2);
    if ( !OverrideValue )
    {
      OverrideValue = ItSpRetrieveOverrideValue(hKey, L"IdleEndTimeout", (unsigned int *)a1 + 3);
      if ( !OverrideValue )
      {
        OverrideValue = ItSpRetrieveOverrideValue(hKey, L"UserInput", (unsigned __int8 *)a1);
        if ( !OverrideValue )
        {
          OverrideValue = ItSpRetrieveOverrideValue(hKey, L"SamplingInterval", (unsigned int *)a1 + 4);
          if ( !OverrideValue )
          {
            OverrideValue = ItSpRetrieveOverrideValue(hKey, L"SamplingNumber", (unsigned int *)a1 + 5);
            if ( !OverrideValue )
            {
              OverrideValue = ItSpRetrieveOverrideValue(hKey, L"CPUThreshold", (unsigned int *)a1 + 6);
              if ( !OverrideValue )
                OverrideValue = ItSpRetrieveOverrideValue(hKey, L"IOThreshold", (unsigned int *)a1 + 7);
            }
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return OverrideValue;
}

```

## disassembly

```asm
0x180072b88  mov     r11, rsp
0x180072b8b  mov     [r11+8], rbx
0x180072b8f  push    rdi
0x180072b90  sub     rsp, 30h
0x180072b94  mov     rdi, rcx
0x180072b97  mov     qword ptr [r11+10h], 0
0x180072b9f  lea     rax, [r11+10h]
0x180072ba3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180072baa  mov     r9d, 0F003Fh; samDesired
0x180072bb0  mov     [r11-18h], rax
0x180072bb4  xor     r8d, r8d; ulOptions
0x180072bb7  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180072bbe  call    cs:__imp_RegOpenKeyExW
0x180072bc4  mov     ebx, eax
0x180072bc6  lea     edx, [rax-2]
0x180072bc9  cmp     edx, 1
0x180072bcc  jbe     loc_180072C9C
0x180072bd2  test    eax, eax
0x180072bd4  jnz     loc_180072C9E
0x180072bda  mov     rcx, [rsp+38h+hKey]; HKEY
0x180072bdf  lea     r8, [rdi+8]; unsigned int *
0x180072be3  lea     rdx, aIdlechecktimeo; "IdleCheckTimeout"
0x180072bea  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAK@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,ulong *)
0x180072bef  mov     ebx, eax
0x180072bf1  test    eax, eax
0x180072bf3  jnz     loc_180072C9E
0x180072bf9  mov     rcx, [rsp+38h+hKey]; HKEY
0x180072bfe  lea     r8, [rdi+0Ch]; unsigned int *
0x180072c02  lea     rdx, aIdleendtimeout; "IdleEndTimeout"
0x180072c09  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAK@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,ulong *)
0x180072c0e  mov     ebx, eax
0x180072c10  test    eax, eax
0x180072c12  jnz     loc_180072C9E
0x180072c18  mov     rcx, [rsp+38h+hKey]; HKEY
0x180072c1d  lea     rdx, aUserinput; "UserInput"
0x180072c24  mov     r8, rdi; unsigned __int8 *
0x180072c27  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAE@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,uchar *)
0x180072c2c  mov     ebx, eax
0x180072c2e  test    eax, eax
0x180072c30  jnz     short loc_180072C9E
0x180072c32  mov     rcx, [rsp+38h+hKey]; HKEY
0x180072c37  lea     r8, [rdi+10h]; unsigned int *
0x180072c3b  lea     rdx, aSamplinginterv; "SamplingInterval"
0x180072c42  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAK@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,ulong *)
0x180072c47  mov     ebx, eax
0x180072c49  test    eax, eax
0x180072c4b  jnz     short loc_180072C9E
0x180072c4d  mov     rcx, [rsp+38h+hKey]; HKEY
0x180072c52  lea     r8, [rdi+14h]; unsigned int *
0x180072c56  lea     rdx, aSamplingnumber; "SamplingNumber"
0x180072c5d  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAK@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,ulong *)
0x180072c62  mov     ebx, eax
0x180072c64  test    eax, eax
0x180072c66  jnz     short loc_180072C9E
0x180072c68  mov     rcx, [rsp+38h+hKey]; HKEY
0x180072c6d  lea     r8, [rdi+18h]; unsigned int *
0x180072c71  lea     rdx, aCputhreshold; "CPUThreshold"
0x180072c78  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAK@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,ulong *)
0x180072c7d  mov     ebx, eax
0x180072c7f  test    eax, eax
0x180072c81  jnz     short loc_180072C9E
0x180072c83  mov     rcx, [rsp+38h+hKey]; HKEY
0x180072c88  lea     r8, [rdi+1Ch]; unsigned int *
0x180072c8c  lea     rdx, aIothreshold; "IOThreshold"
0x180072c93  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAK@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,ulong *)
0x180072c98  mov     ebx, eax
0x180072c9a  jmp     short loc_180072C9E
0x180072c9c  xor     ebx, ebx
0x180072c9e  mov     rcx, [rsp+38h+hKey]; hKey
0x180072ca3  test    rcx, rcx
0x180072ca6  jz      short loc_180072CAE
0x180072ca8  call    cs:__imp_RegCloseKey
0x180072cae  mov     eax, ebx
0x180072cb0  mov     rbx, [rsp+38h+arg_0]
0x180072cb5  add     rsp, 30h
0x180072cb9  pop     rdi
0x180072cba  retn
```
