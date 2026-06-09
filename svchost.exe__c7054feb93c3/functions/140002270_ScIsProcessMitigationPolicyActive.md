# ScIsProcessMitigationPolicyActive

- ea: `0x140002270`
- end: `0x140002349`
- name: `ScIsProcessMitigationPolicyActive`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140006568`

## callees

- `0x140002270`
- `0x140005746`
- `0x140005752`
- `0x14000575e`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140002299`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140002299`

## string_xrefs

- `0x1400022c9`: `System\CurrentControlSet\Control\SCMConfig`

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
0x140002270  mov     rax, rsp
0x140002273  mov     [rax+8], rbx
0x140002277  push    rdi
0x140002278  sub     rsp, 40h
0x14000227c  xor     edi, edi
0x14000227e  lea     rdx, [rax+10h]
0x140002282  mov     ebx, ecx
0x140002284  mov     [rax-18h], edi
0x140002287  xor     ecx, ecx
0x140002289  mov     [rax+18h], edi
0x14000228c  xor     r8d, r8d
0x14000228f  mov     [rax+20h], edi
0x140002292  mov     [rax+10h], edi
0x140002295  mov     [rax-10h], rdi
0x140002299  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x14000229f  mov     eax, [rsp+48h+arg_8]
0x1400022a3  cmp     eax, 0Dh
0x1400022a6  ja      loc_140002330
0x1400022ac  mov     ecx, 2208h
0x1400022b1  bt      ecx, eax
0x1400022b4  jnb     short loc_140002330
0x1400022b6  lea     rax, [rsp+48h+hKey]
0x1400022bb  mov     r9d, 20019h; samDesired
0x1400022c1  xor     r8d, r8d; ulOptions
0x1400022c4  mov     [rsp+48h+phkResult], rax; phkResult
0x1400022c9  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\SCM"...
0x1400022d0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400022d7  call    RegOpenKeyExW_0
0x1400022dc  test    eax, eax
0x1400022de  jnz     short loc_140002323
0x1400022e0  mov     rcx, [rsp+48h+hKey]; hKey
0x1400022e5  lea     rax, [rsp+48h+cbData]
0x1400022ea  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1400022ef  lea     r9, [rsp+48h+Type]; lpType
0x1400022f4  lea     rax, [rsp+48h+Data]
0x1400022f9  mov     [rsp+48h+cbData], 4
0x140002301  xor     r8d, r8d; lpReserved
0x140002304  mov     [rsp+48h+phkResult], rax; lpData
0x140002309  lea     rdx, ValueName; "EnableSvchostMitigationPolicy"
0x140002310  call    RegQueryValueExW_0
0x140002315  test    eax, eax
0x140002317  jz      short loc_140002337
0x140002319  mov     rcx, [rsp+48h+hKey]; hKey
0x14000231e  call    RegCloseKey_0
0x140002323  mov     eax, ebx
0x140002325  mov     rbx, [rsp+48h+arg_0]
0x14000232a  add     rsp, 40h
0x14000232e  pop     rdi
0x14000232f  retn
0x140002330  mov     eax, 1
0x140002335  jmp     short loc_140002325
0x140002337  cmp     [rsp+48h+Type], 4
0x14000233c  jnz     short loc_140002319
0x14000233e  mov     ebx, edi
0x140002340  cmp     dword ptr [rsp+48h+Data], ebx
0x140002344  setnz   bl
0x140002347  jmp     short loc_140002319
```
