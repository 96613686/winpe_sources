# IncrementReadyBootTrainingCount

- ea: `0x180096654`
- end: `0x180096753`
- name: `IncrementReadyBootTrainingCount`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180096a00`

## callees

- `0x180096654`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180096740`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180096740`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009672f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009672f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800966b5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800966b5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800966ed`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800966ed`

## string_xrefs

- `0x180096673`: `System\CurrentControlSet\Services\RdyBoost\Diagnostics`
- `0x1800966dd`: `ReadyBootTrainingCountSinceLastServicing`
- `0x180096709`: `ReadyBootTrainingCountSinceLastServicing`

## pseudocode

```c
__int64 IncrementReadyBootTrainingCount()
{
  unsigned int v0; // ebx
  LSTATUS ValueW; // eax
  int v2; // eax
  int pvData; // [rsp+60h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+70h] [rbp+20h] BYREF

  pvData = 0;
  hkey = 0;
  pcbData = 4;
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\RdyBoost\\Diagnostics",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hkey,
         0);
  if ( !v0 )
  {
    ValueW = RegGetValueW(hkey, 0, L"ReadyBootTrainingCountSinceLastServicing", 0x18u, 0, &pvData, &pcbData);
    v0 = ValueW;
    if ( ValueW == 2 )
    {
      v2 = 0;
    }
    else
    {
      if ( ValueW )
        goto LABEL_7;
      v2 = pvData;
    }
    pvData = v2 + 1;
    v0 = RegSetValueExW(hkey, L"ReadyBootTrainingCountSinceLastServicing", 0, 4u, (const BYTE *)&pvData, 4u);
  }
LABEL_7:
  if ( hkey )
    RegCloseKey(hkey);
  return v0;
}

```

## disassembly

```asm
0x180096654  mov     r11, rsp
0x180096657  mov     [r11+20h], rbx
0x18009665b  push    rbp
0x18009665c  mov     rbp, rsp
0x18009665f  sub     rsp, 50h
0x180096663  mov     qword ptr [r11-18h], 0
0x18009666b  lea     rax, [rbp+hkey]
0x18009666f  mov     [r11-20h], rax
0x180096673  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Rd"...
0x18009667a  mov     qword ptr [r11-28h], 0
0x180096682  xor     r9d, r9d; lpClass
0x180096685  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x18009668d  xor     r8d, r8d; Reserved
0x180096690  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180096697  mov     [rsp+50h+dwOptions], 0; dwOptions
0x18009669f  mov     [rbp+pvData], 0
0x1800966a6  mov     [rbp+hkey], 0
0x1800966ae  mov     [rbp+arg_8], 4
0x1800966b5  call    cs:__imp_RegCreateKeyExW
0x1800966bb  mov     ebx, eax
0x1800966bd  test    eax, eax
0x1800966bf  jnz     short loc_180096737
0x1800966c1  mov     rcx, [rbp+hkey]; hkey
0x1800966c5  lea     rax, [rbp+arg_8]
0x1800966c9  mov     [rsp+50h+pcbData], rax; pcbData
0x1800966ce  lea     r9d, [rbx+18h]; dwFlags
0x1800966d2  lea     rax, [rbp+pvData]
0x1800966d6  xor     edx, edx; lpSubKey
0x1800966d8  mov     qword ptr [rsp+50h+samDesired], rax; pvData
0x1800966dd  lea     r8, aReadyboottrain; "ReadyBootTrainingCountSinceLastServicin"...
0x1800966e4  mov     qword ptr [rsp+50h+dwOptions], 0; pdwType
0x1800966ed  call    cs:__imp_RegGetValueW
0x1800966f3  mov     ebx, eax
0x1800966f5  cmp     eax, 2
0x1800966f8  jnz     short loc_1800966FE
0x1800966fa  xor     eax, eax
0x1800966fc  jmp     short loc_180096705
0x1800966fe  test    eax, eax
0x180096700  jnz     short loc_180096737
0x180096702  mov     eax, [rbp+pvData]
0x180096705  mov     rcx, [rbp+hkey]; hKey
0x180096709  lea     rdx, aReadyboottrain; "ReadyBootTrainingCountSinceLastServicin"...
0x180096710  inc     eax
0x180096712  mov     [rsp+50h+samDesired], 4; cbData
0x18009671a  mov     [rbp+pvData], eax
0x18009671d  mov     r9d, 4; dwType
0x180096723  lea     rax, [rbp+pvData]
0x180096727  xor     r8d, r8d; Reserved
0x18009672a  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x18009672f  call    cs:__imp_RegSetValueExW
0x180096735  mov     ebx, eax
0x180096737  mov     rcx, [rbp+hkey]; hKey
0x18009673b  test    rcx, rcx
0x18009673e  jz      short loc_180096746
0x180096740  call    cs:__imp_RegCloseKey
0x180096746  mov     eax, ebx
0x180096748  mov     rbx, [rsp+50h+arg_18]
0x18009674d  add     rsp, 50h
0x180096751  pop     rbp
0x180096752  retn
```
