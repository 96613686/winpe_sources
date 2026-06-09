# SetSelectiveBindingBuffer(ulong,void *)

- ea: `0x1800c78fc`
- end: `0x1800c79a3`
- name: `?SetSelectiveBindingBuffer@@YAKKPEAX@Z`
- size: `167`
- prototype: `unsigned int __fastcall(DWORD cbData, BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800c6b10`

## callees

- `0x1800c78fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7990`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c7990`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c795d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800c795d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c7983`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800c7983`

## string_xrefs

- `0x1800c793a`: `System\CurrentControlSet\Services\Rpc\Linkage`

## pseudocode

```c
LSTATUS __fastcall SetSelectiveBindingBuffer(DWORD cbData, BYTE *lpData)
{
  LSTATUS result; // eax
  LSTATUS v5; // ebx
  DWORD v6; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  v6 = 0;
  result = RegCreateKeyExA(
             HKEY_LOCAL_MACHINE,
             "System\\CurrentControlSet\\Services\\Rpc\\Linkage",
             0,
             (LPSTR)Class,
             0,
             0x20006u,
             0,
             &hKey,
             &v6);
  if ( !result )
  {
    v5 = RegSetValueExA(hKey, "Bind", 0, 3u, lpData, cbData);
    RegCloseKey(hKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800c78fc  mov     r11, rsp
0x1800c78ff  mov     [r11+8], rbx
0x1800c7903  push    rdi
0x1800c7904  sub     rsp, 50h
0x1800c7908  lea     rax, [r11+18h]
0x1800c790c  mov     qword ptr [r11+20h], 0
0x1800c7914  mov     [r11-18h], rax
0x1800c7918  lea     r9, Class; lpClass
0x1800c791f  lea     rax, [r11+20h]
0x1800c7923  mov     [rsp+58h+arg_10], 0
0x1800c792b  mov     [r11-20h], rax
0x1800c792f  mov     rbx, rdx
0x1800c7932  mov     qword ptr [r11-28h], 0
0x1800c793a  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Rp"...
0x1800c7941  mov     edi, ecx
0x1800c7943  mov     [rsp+58h+samDesired], 20006h; samDesired
0x1800c794b  xor     r8d, r8d; Reserved
0x1800c794e  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800c7956  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c795d  call    cs:__imp_RegCreateKeyExA
0x1800c7963  test    eax, eax
0x1800c7965  jnz     short loc_1800C7998
0x1800c7967  mov     rcx, [rsp+58h+hKey]; hKey
0x1800c796c  lea     r9d, [rax+3]; dwType
0x1800c7970  mov     [rsp+58h+samDesired], edi; cbData
0x1800c7974  lea     rdx, aBind; "Bind"
0x1800c797b  xor     r8d, r8d; Reserved
0x1800c797e  mov     qword ptr [rsp+58h+dwOptions], rbx; lpData
0x1800c7983  call    cs:__imp_RegSetValueExA
0x1800c7989  mov     rcx, [rsp+58h+hKey]; hKey
0x1800c798e  mov     ebx, eax
0x1800c7990  call    cs:__imp_RegCloseKey
0x1800c7996  mov     eax, ebx
0x1800c7998  mov     rbx, [rsp+58h+arg_0]
0x1800c799d  add     rsp, 50h
0x1800c79a1  pop     rdi
0x1800c79a2  retn
```
