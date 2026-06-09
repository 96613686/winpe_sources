# GetSelectiveBindingBuffer(ulong *,void * *)

- ea: `0x18009d2a0`
- end: `0x18009d3b7`
- name: `?GetSelectiveBindingBuffer@@YAKPEAKPEAPEAX@Z`
- size: `279`
- prototype: `unsigned int __fastcall(LPDWORD pcbData, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18009d010`

## callees

- `0x180021e70`
- `0x180022870`
- `0x18009d2a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18009d2ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18009d2ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009d39f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009d39f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18009d33b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18009d386`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18009d33b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18009d386`

## string_xrefs

- `0x18009d2cf`: `System\CurrentControlSet\Services\Rpc\Linkage`

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
0x18009d2a0  mov     r11, rsp
0x18009d2a3  mov     [r11+10h], rbx
0x18009d2a7  mov     [r11+18h], rsi
0x18009d2ab  push    rdi
0x18009d2ac  sub     rsp, 40h
0x18009d2b0  mov     rsi, rdx
0x18009d2b3  mov     qword ptr [rdx], 0
0x18009d2ba  mov     rdi, rcx
0x18009d2bd  mov     dword ptr [rcx], 0
0x18009d2c3  lea     rax, [r11+8]
0x18009d2c7  mov     qword ptr [r11+8], 0
0x18009d2cf  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Rp"...
0x18009d2d6  mov     [r11-28h], rax
0x18009d2da  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009d2e1  mov     r9d, 20019h; samDesired
0x18009d2e7  xor     r8d, r8d; ulOptions
0x18009d2ea  call    cs:__imp_RegOpenKeyExA
0x18009d2f0  test    eax, eax
0x18009d2f2  jz      short loc_18009D310
0x18009d2f4  cmp     eax, 2
0x18009d2f7  jnz     short loc_18009D300
0x18009d2f9  xor     eax, eax
0x18009d2fb  jmp     loc_18009D3A7
0x18009d300  cmp     eax, 13h
0x18009d303  mov     ebx, 0Eh
0x18009d308  cmovz   eax, ebx
0x18009d30b  jmp     loc_18009D3A7
0x18009d310  mov     rcx, [rsp+48h+hkey]; hkey
0x18009d315  lea     r8, aBind; "Bind"
0x18009d31c  mov     [rsp+48h+pcbData], rdi; pcbData
0x18009d321  mov     r9d, 8; dwFlags
0x18009d327  mov     [rsp+48h+pvData], 0; pvData
0x18009d330  xor     edx, edx; lpSubKey
0x18009d332  mov     [rsp+48h+pdwType], 0; pdwType
0x18009d33b  call    cs:__imp_RegGetValueA
0x18009d341  mov     ebx, eax
0x18009d343  test    eax, eax
0x18009d345  jnz     short loc_18009D39A
0x18009d347  cmp     [rdi], eax
0x18009d349  jz      short loc_18009D39A
0x18009d34b  mov     ecx, [rdi]; dwBytes
0x18009d34d  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18009d352  mov     [rsi], rax
0x18009d355  test    rax, rax
0x18009d358  jnz     short loc_18009D35F
0x18009d35a  lea     ebx, [rax+0Eh]
0x18009d35d  jmp     short loc_18009D39A
0x18009d35f  mov     rcx, [rsp+48h+hkey]; hkey
0x18009d364  lea     r8, aBind; "Bind"
0x18009d36b  mov     [rsp+48h+pcbData], rdi; pcbData
0x18009d370  mov     r9d, 8; dwFlags
0x18009d376  mov     [rsp+48h+pvData], rax; pvData
0x18009d37b  xor     edx, edx; lpSubKey
0x18009d37d  mov     [rsp+48h+pdwType], 0; pdwType
0x18009d386  call    cs:__imp_RegGetValueA
0x18009d38c  mov     ebx, eax
0x18009d38e  test    eax, eax
0x18009d390  jz      short loc_18009D39A
0x18009d392  mov     rcx, [rsi]; lpMem
0x18009d395  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009d39a  mov     rcx, [rsp+48h+hkey]; hKey
0x18009d39f  call    cs:__imp_RegCloseKey
0x18009d3a5  mov     eax, ebx
0x18009d3a7  mov     rbx, [rsp+48h+arg_8]
0x18009d3ac  mov     rsi, [rsp+48h+arg_10]
0x18009d3b1  add     rsp, 40h
0x18009d3b5  pop     rdi
0x18009d3b6  retn
```
