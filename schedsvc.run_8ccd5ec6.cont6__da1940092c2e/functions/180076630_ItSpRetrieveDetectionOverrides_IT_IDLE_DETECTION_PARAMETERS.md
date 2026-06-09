# ItSpRetrieveDetectionOverrides(_IT_IDLE_DETECTION_PARAMETERS *)

- ea: `0x180076630`
- end: `0x180076770`
- name: `?ItSpRetrieveDetectionOverrides@@YAKPEAU_IT_IDLE_DETECTION_PARAMETERS@@@Z`
- size: `320`
- prototype: `unsigned int __fastcall(struct _IT_IDLE_DETECTION_PARAMETERS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180077974`

## callees

- `0x180076630`
- `0x180076778`
- `0x1800767e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076666`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076666`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076756`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076756`

## string_xrefs

- `0x18007665f`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\IdleService`

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
0x180076630  mov     r11, rsp
0x180076633  mov     [r11+8], rbx
0x180076637  push    rdi
0x180076638  sub     rsp, 30h
0x18007663c  mov     rdi, rcx
0x18007663f  mov     qword ptr [r11+10h], 0
0x180076647  lea     rax, [r11+10h]
0x18007664b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180076652  mov     r9d, 0F003Fh; samDesired
0x180076658  mov     [r11-18h], rax
0x18007665c  xor     r8d, r8d; ulOptions
0x18007665f  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180076666  call    cs:__imp_RegOpenKeyExW
0x18007666d  nop     dword ptr [rax+rax+00h]
0x180076672  mov     ebx, eax
0x180076674  lea     edx, [rax-2]
0x180076677  cmp     edx, 1
0x18007667a  jbe     loc_18007674A
0x180076680  test    eax, eax
0x180076682  jnz     loc_18007674C
0x180076688  mov     rcx, [rsp+38h+hKey]; HKEY
0x18007668d  lea     r8, [rdi+8]; unsigned int *
0x180076691  lea     rdx, aIdlechecktimeo; "IdleCheckTimeout"
0x180076698  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAK@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,ulong *)
0x18007669d  mov     ebx, eax
0x18007669f  test    eax, eax
0x1800766a1  jnz     loc_18007674C
0x1800766a7  mov     rcx, [rsp+38h+hKey]; HKEY
0x1800766ac  lea     r8, [rdi+0Ch]; unsigned int *
0x1800766b0  lea     rdx, aIdleendtimeout; "IdleEndTimeout"
0x1800766b7  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAK@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,ulong *)
0x1800766bc  mov     ebx, eax
0x1800766be  test    eax, eax
0x1800766c0  jnz     loc_18007674C
0x1800766c6  mov     rcx, [rsp+38h+hKey]; HKEY
0x1800766cb  lea     rdx, aUserinput; "UserInput"
0x1800766d2  mov     r8, rdi; unsigned __int8 *
0x1800766d5  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAE@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,uchar *)
0x1800766da  mov     ebx, eax
0x1800766dc  test    eax, eax
0x1800766de  jnz     short loc_18007674C
0x1800766e0  mov     rcx, [rsp+38h+hKey]; HKEY
0x1800766e5  lea     r8, [rdi+10h]; unsigned int *
0x1800766e9  lea     rdx, aSamplinginterv; "SamplingInterval"
0x1800766f0  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAK@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,ulong *)
0x1800766f5  mov     ebx, eax
0x1800766f7  test    eax, eax
0x1800766f9  jnz     short loc_18007674C
0x1800766fb  mov     rcx, [rsp+38h+hKey]; HKEY
0x180076700  lea     r8, [rdi+14h]; unsigned int *
0x180076704  lea     rdx, aSamplingnumber; "SamplingNumber"
0x18007670b  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAK@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,ulong *)
0x180076710  mov     ebx, eax
0x180076712  test    eax, eax
0x180076714  jnz     short loc_18007674C
0x180076716  mov     rcx, [rsp+38h+hKey]; HKEY
0x18007671b  lea     r8, [rdi+18h]; unsigned int *
0x18007671f  lea     rdx, aCputhreshold; "CPUThreshold"
0x180076726  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAK@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,ulong *)
0x18007672b  mov     ebx, eax
0x18007672d  test    eax, eax
0x18007672f  jnz     short loc_18007674C
0x180076731  mov     rcx, [rsp+38h+hKey]; HKEY
0x180076736  lea     r8, [rdi+1Ch]; unsigned int *
0x18007673a  lea     rdx, aIothreshold; "IOThreshold"
0x180076741  call    ?ItSpRetrieveOverrideValue@@YAKPEAUHKEY__@@PEBGPEAK@Z; ItSpRetrieveOverrideValue(HKEY__ *,ushort const *,ulong *)
0x180076746  mov     ebx, eax
0x180076748  jmp     short loc_18007674C
0x18007674a  xor     ebx, ebx
0x18007674c  mov     rcx, [rsp+38h+hKey]; hKey
0x180076751  test    rcx, rcx
0x180076754  jz      short loc_180076762
0x180076756  call    cs:__imp_RegCloseKey
0x18007675d  nop     dword ptr [rax+rax+00h]
0x180076762  mov     eax, ebx
0x180076764  mov     rbx, [rsp+38h+arg_0]
0x180076769  add     rsp, 30h
0x18007676d  pop     rdi
0x18007676e  retn
```
