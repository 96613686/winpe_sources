# ItSpStoreDetectionOverrides(_IT_IDLE_DETECTION_PARAMETERS *)

- ea: `0x180073820`
- end: `0x1800739f7`
- name: `?ItSpStoreDetectionOverrides@@YAKPEAU_IT_IDLE_DETECTION_PARAMETERS@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(struct _IT_IDLE_DETECTION_PARAMETERS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800746b0`

## callees

- `0x180073820`
- `0x180073a00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800738b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800738e7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073939`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007396e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007399f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800739d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800738b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800738e7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180073939`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007396e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007399f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800739d0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073879`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180073879`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800739e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800739e1`

## string_xrefs

- `0x180073842`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\IdleService`

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
0x180073820  mov     r11, rsp
0x180073823  mov     [r11+8], rbx
0x180073827  push    rbp
0x180073828  push    rdi
0x180073829  push    r14
0x18007382b  mov     rbp, rsp
0x18007382e  sub     rsp, 50h
0x180073832  mov     qword ptr [r11-28h], 0
0x18007383a  lea     rax, [rbp+hKey]
0x18007383e  mov     [r11-30h], rax
0x180073842  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180073849  mov     qword ptr [r11-38h], 0
0x180073851  mov     rdi, rcx
0x180073854  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x18007385c  xor     r9d, r9d; lpClass
0x18007385f  xor     r8d, r8d; Reserved
0x180073862  mov     [rsp+50h+dwOptions], 0; dwOptions
0x18007386a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180073871  mov     [rbp+hKey], 0
0x180073879  call    cs:__imp_RegCreateKeyExW
0x18007387f  mov     ebx, eax
0x180073881  test    eax, eax
0x180073883  jnz     loc_1800739D8
0x180073889  mov     eax, [rdi+8]
0x18007388c  lea     r14d, [rbx+4]
0x180073890  mov     rcx, [rbp+hKey]; hKey
0x180073894  lea     rdx, aIdlechecktimeo; "IdleCheckTimeout"
0x18007389b  mov     [rbp+Data], eax
0x18007389e  mov     r9d, r14d; dwType
0x1800738a1  lea     rax, [rbp+Data]
0x1800738a5  mov     [rsp+50h+samDesired], r14d; cbData
0x1800738aa  xor     r8d, r8d; Reserved
0x1800738ad  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800738b2  call    cs:__imp_RegSetValueExW
0x1800738b8  mov     ebx, eax
0x1800738ba  test    eax, eax
0x1800738bc  jnz     loc_1800739D8
0x1800738c2  mov     eax, [rdi+0Ch]
0x1800738c5  lea     rdx, aIdleendtimeout; "IdleEndTimeout"
0x1800738cc  mov     rcx, [rbp+hKey]; hKey
0x1800738d0  mov     r9d, r14d; dwType
0x1800738d3  mov     [rbp+Data], eax
0x1800738d6  xor     r8d, r8d; Reserved
0x1800738d9  lea     rax, [rbp+Data]
0x1800738dd  mov     [rsp+50h+samDesired], r14d; cbData
0x1800738e2  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800738e7  call    cs:__imp_RegSetValueExW
0x1800738ed  mov     ebx, eax
0x1800738ef  test    eax, eax
0x1800738f1  jnz     loc_1800739D8
0x1800738f7  mov     r8b, [rdi]; unsigned __int8
0x1800738fa  lea     rdx, aUserinput; "UserInput"
0x180073901  mov     rcx, [rbp+hKey]; HKEY
0x180073905  call    ?ItSpStoreOverrideValue@@YAKPEAUHKEY__@@PEBGE@Z; ItSpStoreOverrideValue(HKEY__ *,ushort const *,uchar)
0x18007390a  mov     ebx, eax
0x18007390c  test    eax, eax
0x18007390e  jnz     loc_1800739D8
0x180073914  mov     eax, [rdi+10h]
0x180073917  lea     rdx, aSamplinginterv; "SamplingInterval"
0x18007391e  mov     rcx, [rbp+hKey]; hKey
0x180073922  mov     r9d, r14d; dwType
0x180073925  mov     [rbp+Data], eax
0x180073928  xor     r8d, r8d; Reserved
0x18007392b  lea     rax, [rbp+Data]
0x18007392f  mov     [rsp+50h+samDesired], r14d; cbData
0x180073934  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180073939  call    cs:__imp_RegSetValueExW
0x18007393f  mov     ebx, eax
0x180073941  test    eax, eax
0x180073943  jnz     loc_1800739D8
0x180073949  mov     eax, [rdi+14h]
0x18007394c  lea     rdx, aSamplingnumber; "SamplingNumber"
0x180073953  mov     rcx, [rbp+hKey]; hKey
0x180073957  mov     r9d, r14d; dwType
0x18007395a  mov     [rbp+Data], eax
0x18007395d  xor     r8d, r8d; Reserved
0x180073960  lea     rax, [rbp+Data]
0x180073964  mov     [rsp+50h+samDesired], r14d; cbData
0x180073969  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x18007396e  call    cs:__imp_RegSetValueExW
0x180073974  mov     ebx, eax
0x180073976  test    eax, eax
0x180073978  jnz     short loc_1800739D8
0x18007397a  mov     eax, [rdi+18h]
0x18007397d  lea     rdx, aCputhreshold; "CPUThreshold"
0x180073984  mov     rcx, [rbp+hKey]; hKey
0x180073988  mov     r9d, r14d; dwType
0x18007398b  mov     [rbp+Data], eax
0x18007398e  xor     r8d, r8d; Reserved
0x180073991  lea     rax, [rbp+Data]
0x180073995  mov     [rsp+50h+samDesired], r14d; cbData
0x18007399a  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x18007399f  call    cs:__imp_RegSetValueExW
0x1800739a5  mov     ebx, eax
0x1800739a7  test    eax, eax
0x1800739a9  jnz     short loc_1800739D8
0x1800739ab  mov     eax, [rdi+1Ch]
0x1800739ae  lea     rdx, aIothreshold; "IOThreshold"
0x1800739b5  mov     rcx, [rbp+hKey]; hKey
0x1800739b9  mov     r9d, r14d; dwType
0x1800739bc  mov     [rbp+Data], eax
0x1800739bf  xor     r8d, r8d; Reserved
0x1800739c2  lea     rax, [rbp+Data]
0x1800739c6  mov     [rsp+50h+samDesired], r14d; cbData
0x1800739cb  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800739d0  call    cs:__imp_RegSetValueExW
0x1800739d6  mov     ebx, eax
0x1800739d8  mov     rcx, [rbp+hKey]; hKey
0x1800739dc  test    rcx, rcx
0x1800739df  jz      short loc_1800739E7
0x1800739e1  call    cs:__imp_RegCloseKey
0x1800739e7  mov     eax, ebx
0x1800739e9  mov     rbx, [rsp+50h+arg_0]
0x1800739ee  add     rsp, 50h
0x1800739f2  pop     r14
0x1800739f4  pop     rdi
0x1800739f5  pop     rbp
0x1800739f6  retn
```
