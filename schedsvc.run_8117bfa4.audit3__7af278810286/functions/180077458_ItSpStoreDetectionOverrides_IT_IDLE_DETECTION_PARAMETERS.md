# ItSpStoreDetectionOverrides(_IT_IDLE_DETECTION_PARAMETERS *)

- ea: `0x180077458`
- end: `0x180077660`
- name: `?ItSpStoreDetectionOverrides@@YAKPEAU_IT_IDLE_DETECTION_PARAMETERS@@@Z`
- size: `520`
- prototype: `unsigned int __fastcall(struct _IT_IDLE_DETECTION_PARAMETERS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180078520`

## callees

- `0x180077458`
- `0x180077668`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800774f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007752b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077583`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800775be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800775f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007762c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800774f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007752b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077583`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800775be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800775f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007762c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800774b1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800774b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077643`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077643`

## string_xrefs

- `0x18007747a`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\IdleService`

## pseudocode

```c
__int64 __fastcall ItSpStoreDetectionOverrides(struct _IT_IDLE_DETECTION_PARAMETERS *a1)
{
  unsigned int v2; // ebx
  int Data; // [rsp+78h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF

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
    Data = *((_DWORD *)a1 + 2);
    v2 = RegSetValueExW(hKey, L"IdleCheckTimeout", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v2 )
    {
      Data = *((_DWORD *)a1 + 3);
      v2 = RegSetValueExW(hKey, L"IdleEndTimeout", 0, 4u, (const BYTE *)&Data, 4u);
      if ( !v2 )
      {
        v2 = ItSpStoreOverrideValue(hKey, L"UserInput", *(_BYTE *)a1);
        if ( !v2 )
        {
          Data = *((_DWORD *)a1 + 4);
          v2 = RegSetValueExW(hKey, L"SamplingInterval", 0, 4u, (const BYTE *)&Data, 4u);
          if ( !v2 )
          {
            Data = *((_DWORD *)a1 + 5);
            v2 = RegSetValueExW(hKey, L"SamplingNumber", 0, 4u, (const BYTE *)&Data, 4u);
            if ( !v2 )
            {
              Data = *((_DWORD *)a1 + 6);
              v2 = RegSetValueExW(hKey, L"CPUThreshold", 0, 4u, (const BYTE *)&Data, 4u);
              if ( !v2 )
              {
                Data = *((_DWORD *)a1 + 7);
                v2 = RegSetValueExW(hKey, L"IOThreshold", 0, 4u, (const BYTE *)&Data, 4u);
              }
            }
          }
        }
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
0x180077458  mov     r11, rsp
0x18007745b  mov     [r11+8], rbx
0x18007745f  push    rbp
0x180077460  push    rdi
0x180077461  push    r14
0x180077463  mov     rbp, rsp
0x180077466  sub     rsp, 50h
0x18007746a  mov     qword ptr [r11-28h], 0
0x180077472  lea     rax, [rbp+hKey]
0x180077476  mov     [r11-30h], rax
0x18007747a  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180077481  mov     qword ptr [r11-38h], 0
0x180077489  mov     rdi, rcx
0x18007748c  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x180077494  xor     r9d, r9d; lpClass
0x180077497  xor     r8d, r8d; Reserved
0x18007749a  mov     [rsp+50h+dwOptions], 0; dwOptions
0x1800774a2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800774a9  mov     [rbp+hKey], 0
0x1800774b1  call    cs:__imp_RegCreateKeyExW
0x1800774b8  nop     dword ptr [rax+rax+00h]
0x1800774bd  mov     ebx, eax
0x1800774bf  test    eax, eax
0x1800774c1  jnz     loc_18007763A
0x1800774c7  mov     eax, [rdi+8]
0x1800774ca  lea     r14d, [rbx+4]
0x1800774ce  mov     rcx, [rbp+hKey]; hKey
0x1800774d2  lea     rdx, aIdlechecktimeo; "IdleCheckTimeout"
0x1800774d9  mov     [rbp+Data], eax
0x1800774dc  mov     r9d, r14d; dwType
0x1800774df  lea     rax, [rbp+Data]
0x1800774e3  mov     [rsp+50h+samDesired], r14d; cbData
0x1800774e8  xor     r8d, r8d; Reserved
0x1800774eb  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800774f0  call    cs:__imp_RegSetValueExW
0x1800774f7  nop     dword ptr [rax+rax+00h]
0x1800774fc  mov     ebx, eax
0x1800774fe  test    eax, eax
0x180077500  jnz     loc_18007763A
0x180077506  mov     eax, [rdi+0Ch]
0x180077509  lea     rdx, aIdleendtimeout; "IdleEndTimeout"
0x180077510  mov     rcx, [rbp+hKey]; hKey
0x180077514  mov     r9d, r14d; dwType
0x180077517  mov     [rbp+Data], eax
0x18007751a  xor     r8d, r8d; Reserved
0x18007751d  lea     rax, [rbp+Data]
0x180077521  mov     [rsp+50h+samDesired], r14d; cbData
0x180077526  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x18007752b  call    cs:__imp_RegSetValueExW
0x180077532  nop     dword ptr [rax+rax+00h]
0x180077537  mov     ebx, eax
0x180077539  test    eax, eax
0x18007753b  jnz     loc_18007763A
0x180077541  mov     r8b, [rdi]; unsigned __int8
0x180077544  lea     rdx, aUserinput; "UserInput"
0x18007754b  mov     rcx, [rbp+hKey]; HKEY
0x18007754f  call    ?ItSpStoreOverrideValue@@YAKPEAUHKEY__@@PEBGE@Z; ItSpStoreOverrideValue(HKEY__ *,ushort const *,uchar)
0x180077554  mov     ebx, eax
0x180077556  test    eax, eax
0x180077558  jnz     loc_18007763A
0x18007755e  mov     eax, [rdi+10h]
0x180077561  lea     rdx, aSamplinginterv; "SamplingInterval"
0x180077568  mov     rcx, [rbp+hKey]; hKey
0x18007756c  mov     r9d, r14d; dwType
0x18007756f  mov     [rbp+Data], eax
0x180077572  xor     r8d, r8d; Reserved
0x180077575  lea     rax, [rbp+Data]
0x180077579  mov     [rsp+50h+samDesired], r14d; cbData
0x18007757e  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180077583  call    cs:__imp_RegSetValueExW
0x18007758a  nop     dword ptr [rax+rax+00h]
0x18007758f  mov     ebx, eax
0x180077591  test    eax, eax
0x180077593  jnz     loc_18007763A
0x180077599  mov     eax, [rdi+14h]
0x18007759c  lea     rdx, aSamplingnumber; "SamplingNumber"
0x1800775a3  mov     rcx, [rbp+hKey]; hKey
0x1800775a7  mov     r9d, r14d; dwType
0x1800775aa  mov     [rbp+Data], eax
0x1800775ad  xor     r8d, r8d; Reserved
0x1800775b0  lea     rax, [rbp+Data]
0x1800775b4  mov     [rsp+50h+samDesired], r14d; cbData
0x1800775b9  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800775be  call    cs:__imp_RegSetValueExW
0x1800775c5  nop     dword ptr [rax+rax+00h]
0x1800775ca  mov     ebx, eax
0x1800775cc  test    eax, eax
0x1800775ce  jnz     short loc_18007763A
0x1800775d0  mov     eax, [rdi+18h]
0x1800775d3  lea     rdx, aCputhreshold; "CPUThreshold"
0x1800775da  mov     rcx, [rbp+hKey]; hKey
0x1800775de  mov     r9d, r14d; dwType
0x1800775e1  mov     [rbp+Data], eax
0x1800775e4  xor     r8d, r8d; Reserved
0x1800775e7  lea     rax, [rbp+Data]
0x1800775eb  mov     [rsp+50h+samDesired], r14d; cbData
0x1800775f0  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800775f5  call    cs:__imp_RegSetValueExW
0x1800775fc  nop     dword ptr [rax+rax+00h]
0x180077601  mov     ebx, eax
0x180077603  test    eax, eax
0x180077605  jnz     short loc_18007763A
0x180077607  mov     eax, [rdi+1Ch]
0x18007760a  lea     rdx, aIothreshold; "IOThreshold"
0x180077611  mov     rcx, [rbp+hKey]; hKey
0x180077615  mov     r9d, r14d; dwType
0x180077618  mov     [rbp+Data], eax
0x18007761b  xor     r8d, r8d; Reserved
0x18007761e  lea     rax, [rbp+Data]
0x180077622  mov     [rsp+50h+samDesired], r14d; cbData
0x180077627  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x18007762c  call    cs:__imp_RegSetValueExW
0x180077633  nop     dword ptr [rax+rax+00h]
0x180077638  mov     ebx, eax
0x18007763a  mov     rcx, [rbp+hKey]; hKey
0x18007763e  test    rcx, rcx
0x180077641  jz      short loc_18007764F
0x180077643  call    cs:__imp_RegCloseKey
0x18007764a  nop     dword ptr [rax+rax+00h]
0x18007764f  mov     eax, ebx
0x180077651  mov     rbx, [rsp+50h+arg_0]
0x180077656  add     rsp, 50h
0x18007765a  pop     r14
0x18007765c  pop     rdi
0x18007765d  pop     rbp
0x18007765e  retn
```
