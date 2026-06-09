# OverrideServerSpecificDwordValues(void)

- ea: `0x18004a474`
- end: `0x18004a584`
- name: `?OverrideServerSpecificDwordValues@@YAJXZ`
- size: `272`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800498b8`

## callees

- `0x18004a474`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a4cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a4cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a541`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a567`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a073`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a541`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a567`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a073`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a517`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a517`

## pseudocode

```c
__int64 OverrideServerSpecificDwordValues(void)
{
  signed int v0; // ebx
  unsigned int i; // edi
  __int64 v2; // rsi
  LSTATUS v3; // eax
  int v4; // eax
  bool v5; // sf
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  v0 = 0;
  for ( i = 0; i < 6; ++i )
  {
    v2 = 4LL * i;
    Data = (int)off_18006E9F0[v2 + 2];
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, off_18006E9F0[v2], 0, 2u, &hKey);
    v0 = v3;
    if ( v3 > 0 )
      v0 = (unsigned __int16)v3 | 0x80070000;
    if ( v0 < 0 )
      break;
    v4 = RegSetValueExW(hKey, off_18006E9F0[v2 + 1], 0, 4u, (const BYTE *)&Data, 4u);
    v5 = v4 < 0;
    if ( v4 > 0 )
    {
      v4 = (unsigned __int16)v4 | 0x80070000;
      v5 = v4 < 0;
    }
    if ( v5 && !v0 )
      v0 = v4;
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18004a474  mov     [rsp+arg_10], rbx
0x18004a479  push    rsi
0x18004a47a  push    rdi
0x18004a47b  push    r15
0x18004a47d  sub     rsp, 40h
0x18004a481  mov     [rsp+58h+hKey], 0
0x18004a48a  xor     ebx, ebx
0x18004a48c  xor     edi, edi
0x18004a48e  lea     r15, off_18006E9F0; "System\\CurrentControlSet\\Services\\W3"...
0x18004a495  mov     [rsp+58h+var_24], edi
0x18004a499  cmp     edi, 6
0x18004a49c  jnb     loc_18004A55D
0x18004a4a2  mov     esi, edi
0x18004a4a4  shl     rsi, 5
0x18004a4a8  mov     eax, [rsi+r15+10h]
0x18004a4ad  mov     [rsp+58h+Data], eax
0x18004a4b1  lea     rax, [rsp+58h+hKey]
0x18004a4b6  mov     [rsp+58h+phkResult], rax; phkResult
0x18004a4bb  mov     r9d, 2; samDesired
0x18004a4c1  xor     r8d, r8d; ulOptions
0x18004a4c4  mov     rdx, [rsi+r15]; lpSubKey
0x18004a4c8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004a4cf  call    cs:__imp_RegOpenKeyExW
0x18004a4d6  nop     dword ptr [rax+rax+00h]
0x18004a4db  mov     ebx, eax
0x18004a4dd  test    eax, eax
0x18004a4df  jle     short loc_18004A4EA
0x18004a4e1  movzx   ebx, ax
0x18004a4e4  or      ebx, 80070000h
0x18004a4ea  mov     [rsp+58h+var_28], ebx
0x18004a4ee  test    ebx, ebx
0x18004a4f0  js      short loc_18004A55D
0x18004a4f2  mov     [rsp+58h+cbData], 4; cbData
0x18004a4fa  lea     rax, [rsp+58h+Data]
0x18004a4ff  mov     [rsp+58h+phkResult], rax; lpData
0x18004a504  mov     r9d, 4; dwType
0x18004a50a  xor     r8d, r8d; Reserved
0x18004a50d  mov     rdx, [rsi+r15+8]; lpValueName
0x18004a512  mov     rcx, [rsp+58h+hKey]; hKey
0x18004a517  call    cs:__imp_RegSetValueExW
0x18004a51e  nop     dword ptr [rax+rax+00h]
0x18004a523  test    eax, eax
0x18004a525  jle     short loc_18004A531
0x18004a527  movzx   eax, ax
0x18004a52a  or      eax, 80070000h
0x18004a52f  test    eax, eax
0x18004a531  jns     short loc_18004A53C
0x18004a533  test    ebx, ebx
0x18004a535  cmovz   ebx, eax
0x18004a538  mov     [rsp+58h+var_28], ebx
0x18004a53c  mov     rcx, [rsp+58h+hKey]; hKey
0x18004a541  call    cs:__imp_RegCloseKey
0x18004a548  nop     dword ptr [rax+rax+00h]
0x18004a54d  mov     [rsp+58h+hKey], 0
0x18004a556  inc     edi
0x18004a558  jmp     loc_18004A495
0x18004a55d  mov     rcx, [rsp+58h+hKey]; hKey
0x18004a562  test    rcx, rcx
0x18004a565  jz      short loc_18004A573
0x18004a567  call    cs:__imp_RegCloseKey
0x18004a56e  nop     dword ptr [rax+rax+00h]
0x18004a573  mov     eax, ebx
0x18004a575  mov     rbx, [rsp+58h+arg_10]
0x18004a57a  add     rsp, 40h
0x18004a57e  pop     r15
0x18004a580  pop     rdi
0x18004a581  pop     rsi
0x18004a582  retn
0x18006a061  push    rbp
0x18006a063  sub     rsp, 30h
0x18006a067  mov     rbp, rdx
0x18006a06a  mov     rcx, [rbp+68h]; hKey
0x18006a06e  test    rcx, rcx
0x18006a071  jz      short loc_18006A080
0x18006a073  call    cs:__imp_RegCloseKey
0x18006a07a  nop     dword ptr [rax+rax+00h]
0x18006a07f  nop
0x18006a080  add     rsp, 30h
0x18006a084  pop     rbp
0x18006a085  retn
```
