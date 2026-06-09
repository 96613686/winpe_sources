# NdrpDisableClientHarden(void)

- ea: `0x1800a51e4`
- end: `0x1800a52c4`
- name: `?NdrpDisableClientHarden@@YAHXZ`
- size: `224`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800050b0`
- `0x180005360`

## callees

- `0x18000cb10`
- `0x1800a51e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a5223`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a5223`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a5293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a5293`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a5278`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a5278`

## string_xrefs

- `0x1800a5215`: `Software\Microsoft\Rpc\SystemParameter001`

## pseudocode

```c
_BOOL8 NdrpDisableClientHarden(void)
{
  RPC_STATUS v0; // ebx
  struct _LIST_ENTRY *Flink; // r8
  LSTATUS ValueW; // eax
  HKEY v3; // rcx
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  int pvData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  v0 = dword_1800F9838;
  if ( dword_1800F9838 == -1 )
  {
    hkey = 0;
    v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Rpc\\SystemParameter001", 0, 0x20019u, &hkey);
    if ( v0 )
    {
      v3 = 0;
      hkey = 0;
    }
    else
    {
      Flink = NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[6].Flink;
      pcbData = 4;
      pvData = 0;
      ValueW = RegGetValueW(hkey, 0, (LPCWSTR)Flink, 0x18u, 0, &pvData, &pcbData);
      v3 = hkey;
      v0 = ValueW;
    }
    if ( v3 )
      RegCloseKey(v3);
    dword_1800F9838 = v0;
    if ( !v0 )
      return 1;
    if ( v0 != 2 )
      RpcRaiseException(v0);
  }
  return v0 == 0;
}

```

## disassembly

```asm
0x1800a51e4  push    rbx
0x1800a51e6  sub     rsp, 40h
0x1800a51ea  mov     ebx, cs:dword_1800F9838
0x1800a51f0  cmp     ebx, 0FFFFFFFFh
0x1800a51f3  jnz     loc_1800A52B7
0x1800a51f9  lea     rax, [rsp+48h+hkey]
0x1800a51fe  mov     [rsp+48h+hkey], 0
0x1800a5207  mov     r9d, 20019h; samDesired
0x1800a520d  mov     [rsp+48h+phkResult], rax; phkResult
0x1800a5212  xor     r8d, r8d; ulOptions
0x1800a5215  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Rpc\\SystemParamet"...
0x1800a521c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a5223  call    cs:__imp_RegOpenKeyExW
0x1800a5229  mov     ebx, eax
0x1800a522b  test    eax, eax
0x1800a522d  jnz     short loc_1800A5287
0x1800a522f  mov     rax, gs:60h
0x1800a5238  lea     r9d, [rbx+18h]; dwFlags
0x1800a523c  xor     edx, edx; lpSubKey
0x1800a523e  mov     rcx, [rax+18h]
0x1800a5242  mov     rax, [rcx+10h]
0x1800a5246  mov     rcx, [rsp+48h+hkey]; hkey
0x1800a524b  mov     r8, [rax+60h]; lpValue
0x1800a524f  lea     rax, [rsp+48h+arg_0]
0x1800a5254  mov     [rsp+48h+pcbData], rax; pcbData
0x1800a5259  lea     rax, [rsp+48h+arg_8]
0x1800a525e  mov     [rsp+48h+pvData], rax; pvData
0x1800a5263  mov     [rsp+48h+phkResult], 0; pdwType
0x1800a526c  mov     [rsp+48h+arg_0], 4
0x1800a5274  mov     [rsp+48h+arg_8], ebx
0x1800a5278  call    cs:__imp_RegGetValueW
0x1800a527e  mov     rcx, [rsp+48h+hkey]
0x1800a5283  mov     ebx, eax
0x1800a5285  jmp     short loc_1800A528E
0x1800a5287  xor     ecx, ecx; hKey
0x1800a5289  mov     [rsp+48h+hkey], rcx
0x1800a528e  test    rcx, rcx
0x1800a5291  jz      short loc_1800A5299
0x1800a5293  call    cs:__imp_RegCloseKey
0x1800a5299  mov     cs:dword_1800F9838, ebx
0x1800a529f  test    ebx, ebx
0x1800a52a1  jz      short loc_1800A52B0
0x1800a52a3  cmp     ebx, 2
0x1800a52a6  jz      short loc_1800A52B7
0x1800a52a8  mov     ecx, ebx; exception
0x1800a52aa  call    RpcRaiseException
0x1800a52b0  mov     eax, 1
0x1800a52b5  jmp     short loc_1800A52BE
0x1800a52b7  xor     eax, eax
0x1800a52b9  test    ebx, ebx
0x1800a52bb  setz    al
0x1800a52be  add     rsp, 40h
0x1800a52c2  pop     rbx
0x1800a52c3  retn
```
