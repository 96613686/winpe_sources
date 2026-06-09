# ScIsProcessMitigationPolicyActive

- ea: `0x140002830`
- end: `0x140002910`
- name: `ScIsProcessMitigationPolicyActive`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140006a3c`

## callees

- `0x140002830`
- `0x140005b26`
- `0x140005b32`
- `0x140005b3e`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140002859`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140002859`

## string_xrefs

- `0x14000288f`: `System\CurrentControlSet\Control\SCMConfig`

## pseudocode

```c
__int64 __fastcall ScIsProcessMitigationPolicyActive(BOOL a1)
{
  int v2; // ecx
  BYTE Data[8]; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v6; // [rsp+58h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF

  *(_DWORD *)Data = 0;
  cbData = 0;
  Type = 0;
  v6 = 0;
  hKey = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v6, 0);
  if ( v6 > 0xD )
    return 1;
  v2 = 8712;
  if ( !_bittest(&v2, v6) )
    return 1;
  if ( !RegOpenKeyExW_0(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\SCMConfig", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW_0(hKey, L"EnableSvchostMitigationPolicy", 0, &Type, Data, &cbData) && Type == 4 )
      a1 = *(_DWORD *)Data != 0;
    RegCloseKey_0(hKey);
  }
  return a1;
}

```

## disassembly

```asm
0x140002830  mov     rax, rsp
0x140002833  mov     [rax+8], rbx
0x140002837  push    rdi
0x140002838  sub     rsp, 40h
0x14000283c  xor     edi, edi
0x14000283e  lea     rdx, [rax+10h]
0x140002842  mov     ebx, ecx
0x140002844  mov     [rax-18h], edi
0x140002847  xor     ecx, ecx
0x140002849  mov     [rax+18h], edi
0x14000284c  xor     r8d, r8d
0x14000284f  mov     [rax+20h], edi
0x140002852  mov     [rax+10h], edi
0x140002855  mov     [rax-10h], rdi
0x140002859  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x140002860  nop     dword ptr [rax+rax+00h]
0x140002865  mov     eax, [rsp+48h+arg_8]
0x140002869  cmp     eax, 0Dh
0x14000286c  ja      loc_1400028F7
0x140002872  mov     ecx, 2208h
0x140002877  bt      ecx, eax
0x14000287a  jnb     short loc_1400028F7
0x14000287c  lea     rax, [rsp+48h+hKey]
0x140002881  mov     r9d, 20019h; samDesired
0x140002887  xor     r8d, r8d; ulOptions
0x14000288a  mov     [rsp+48h+phkResult], rax; phkResult
0x14000288f  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\SCM"...
0x140002896  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000289d  call    RegOpenKeyExW_0
0x1400028a2  test    eax, eax
0x1400028a4  jnz     short loc_1400028E9
0x1400028a6  mov     rcx, [rsp+48h+hKey]; hKey
0x1400028ab  lea     rax, [rsp+48h+cbData]
0x1400028b0  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1400028b5  lea     r9, [rsp+48h+Type]; lpType
0x1400028ba  lea     rax, [rsp+48h+Data]
0x1400028bf  mov     [rsp+48h+cbData], 4
0x1400028c7  xor     r8d, r8d; lpReserved
0x1400028ca  mov     [rsp+48h+phkResult], rax; lpData
0x1400028cf  lea     rdx, ValueName; "EnableSvchostMitigationPolicy"
0x1400028d6  call    RegQueryValueExW_0
0x1400028db  test    eax, eax
0x1400028dd  jz      short loc_1400028FE
0x1400028df  mov     rcx, [rsp+48h+hKey]; hKey
0x1400028e4  call    RegCloseKey_0
0x1400028e9  mov     eax, ebx
0x1400028eb  mov     rbx, [rsp+48h+arg_0]
0x1400028f0  add     rsp, 40h
0x1400028f4  pop     rdi
0x1400028f5  retn
0x1400028f7  mov     eax, 1
0x1400028fc  jmp     short loc_1400028EB
0x1400028fe  cmp     [rsp+48h+Type], 4
0x140002903  jnz     short loc_1400028DF
0x140002905  mov     ebx, edi
0x140002907  cmp     dword ptr [rsp+48h+Data], ebx
0x14000290b  setnz   bl
0x14000290e  jmp     short loc_1400028DF
```
