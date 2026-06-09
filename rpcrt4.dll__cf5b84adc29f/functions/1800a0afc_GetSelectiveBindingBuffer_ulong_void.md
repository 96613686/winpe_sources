# GetSelectiveBindingBuffer(ulong *,void * *)

- ea: `0x1800a0afc`
- end: `0x1800a0c2c`
- name: `?GetSelectiveBindingBuffer@@YAKPEAKPEAPEAX@Z`
- size: `304`
- prototype: `unsigned int __fastcall(LPDWORD pcbData, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800a086c`

## callees

- `0x180023020`
- `0x180023a40`
- `0x1800a0afc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800a0b46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800a0b46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a0c0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a0c0d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800a0b9d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800a0bee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800a0b9d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800a0bee`

## string_xrefs

- `0x1800a0b2b`: `System\CurrentControlSet\Services\Rpc\Linkage`

## pseudocode

```c
LSTATUS __fastcall GetSelectiveBindingBuffer(LPDWORD pcbData, void **a2)
{
  LSTATUS result; // eax
  LSTATUS ValueA; // ebx
  void *pvData; // rax
  HKEY hkey; // [rsp+50h] [rbp+8h] BYREF

  *a2 = 0;
  *pcbData = 0;
  hkey = 0;
  result = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\Rpc\\Linkage", 0, 0x20019u, &hkey);
  if ( result )
  {
    if ( result == 2 )
    {
      return 0;
    }
    else if ( result == 19 )
    {
      return 14;
    }
  }
  else
  {
    ValueA = RegGetValueA(hkey, 0, "Bind", 8u, 0, 0, pcbData);
    if ( !ValueA && *pcbData )
    {
      pvData = AllocWrapper(*pcbData);
      *a2 = pvData;
      if ( pvData )
      {
        ValueA = RegGetValueA(hkey, 0, "Bind", 8u, 0, pvData, pcbData);
        if ( ValueA )
          FreeWrapper(*a2);
      }
      else
      {
        ValueA = 14;
      }
    }
    RegCloseKey(hkey);
    return ValueA;
  }
  return result;
}

```

## disassembly

```asm
0x1800a0afc  mov     r11, rsp
0x1800a0aff  mov     [r11+10h], rbx
0x1800a0b03  mov     [r11+18h], rsi
0x1800a0b07  push    rdi
0x1800a0b08  sub     rsp, 40h
0x1800a0b0c  mov     rsi, rdx
0x1800a0b0f  mov     qword ptr [rdx], 0
0x1800a0b16  mov     rdi, rcx
0x1800a0b19  mov     dword ptr [rcx], 0
0x1800a0b1f  lea     rax, [r11+8]
0x1800a0b23  mov     qword ptr [r11+8], 0
0x1800a0b2b  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Rp"...
0x1800a0b32  mov     [r11-28h], rax
0x1800a0b36  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a0b3d  mov     r9d, 20019h; samDesired
0x1800a0b43  xor     r8d, r8d; ulOptions
0x1800a0b46  call    cs:__imp_RegOpenKeyExA
0x1800a0b4d  nop     dword ptr [rax+rax+00h]
0x1800a0b52  test    eax, eax
0x1800a0b54  jz      short loc_1800A0B72
0x1800a0b56  cmp     eax, 2
0x1800a0b59  jnz     short loc_1800A0B62
0x1800a0b5b  xor     eax, eax
0x1800a0b5d  jmp     loc_1800A0C1B
0x1800a0b62  cmp     eax, 13h
0x1800a0b65  mov     ebx, 0Eh
0x1800a0b6a  cmovz   eax, ebx
0x1800a0b6d  jmp     loc_1800A0C1B
0x1800a0b72  mov     rcx, [rsp+48h+hkey]; hkey
0x1800a0b77  lea     r8, aBind; "Bind"
0x1800a0b7e  mov     [rsp+48h+pcbData], rdi; pcbData
0x1800a0b83  mov     r9d, 8; dwFlags
0x1800a0b89  mov     [rsp+48h+pvData], 0; pvData
0x1800a0b92  xor     edx, edx; lpSubKey
0x1800a0b94  mov     [rsp+48h+pdwType], 0; pdwType
0x1800a0b9d  call    cs:__imp_RegGetValueA
0x1800a0ba4  nop     dword ptr [rax+rax+00h]
0x1800a0ba9  mov     ebx, eax
0x1800a0bab  test    eax, eax
0x1800a0bad  jnz     short loc_1800A0C08
0x1800a0baf  cmp     [rdi], eax
0x1800a0bb1  jz      short loc_1800A0C08
0x1800a0bb3  mov     ecx, [rdi]; dwBytes
0x1800a0bb5  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800a0bba  mov     [rsi], rax
0x1800a0bbd  test    rax, rax
0x1800a0bc0  jnz     short loc_1800A0BC7
0x1800a0bc2  lea     ebx, [rax+0Eh]
0x1800a0bc5  jmp     short loc_1800A0C08
0x1800a0bc7  mov     rcx, [rsp+48h+hkey]; hkey
0x1800a0bcc  lea     r8, aBind; "Bind"
0x1800a0bd3  mov     [rsp+48h+pcbData], rdi; pcbData
0x1800a0bd8  mov     r9d, 8; dwFlags
0x1800a0bde  mov     [rsp+48h+pvData], rax; pvData
0x1800a0be3  xor     edx, edx; lpSubKey
0x1800a0be5  mov     [rsp+48h+pdwType], 0; pdwType
0x1800a0bee  call    cs:__imp_RegGetValueA
0x1800a0bf5  nop     dword ptr [rax+rax+00h]
0x1800a0bfa  mov     ebx, eax
0x1800a0bfc  test    eax, eax
0x1800a0bfe  jz      short loc_1800A0C08
0x1800a0c00  mov     rcx, [rsi]; lpMem
0x1800a0c03  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800a0c08  mov     rcx, [rsp+48h+hkey]; hKey
0x1800a0c0d  call    cs:__imp_RegCloseKey
0x1800a0c14  nop     dword ptr [rax+rax+00h]
0x1800a0c19  mov     eax, ebx
0x1800a0c1b  mov     rbx, [rsp+48h+arg_8]
0x1800a0c20  mov     rsi, [rsp+48h+arg_10]
0x1800a0c25  add     rsp, 40h
0x1800a0c29  pop     rdi
0x1800a0c2a  retn
```
