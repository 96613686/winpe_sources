# UnloadOfflineRegistryKey

- ea: `0x1800070f0`
- end: `0x180007171`
- name: `UnloadOfflineRegistryKey`
- size: `129`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180002a50`
- `0x1800056a0`

## callees

- `0x180001de0`
- `0x1800070f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180007139`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180007139`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007112`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007112`

## pseudocode

```c
__int64 __fastcall UnloadOfflineRegistryKey(__int64 a1)
{
  HKEY v3; // rcx
  unsigned int v4; // edi

  if ( !a1 )
    return 2147942487LL;
  v3 = *(HKEY *)(a1 + 16);
  if ( v3 && !RegCloseKey(v3) )
    *(_QWORD *)(a1 + 16) = 0;
  if ( !*(_DWORD *)(a1 + 8) )
    goto LABEL_9;
  v4 = -2147467259;
  if ( RegUnLoadKeyW(HKEY_LOCAL_MACHINE, *(LPCWSTR *)a1) >= 0 )
  {
    *(_DWORD *)(a1 + 8) = 0;
LABEL_9:
    if ( *(_QWORD *)a1 )
    {
      operator delete((void *)(*(_QWORD *)a1 - 8LL));
      *(_QWORD *)a1 = 0;
    }
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1800070f0  mov     [rsp+arg_0], rbx
0x1800070f5  push    rdi
0x1800070f6  sub     rsp, 20h
0x1800070fa  mov     rbx, rcx
0x1800070fd  test    rcx, rcx
0x180007100  jnz     short loc_180007109
0x180007102  mov     eax, 80070057h
0x180007107  jmp     short loc_180007166
0x180007109  mov     rcx, [rcx+10h]; hKey
0x18000710d  test    rcx, rcx
0x180007110  jz      short loc_180007124
0x180007112  call    cs:__imp_RegCloseKey
0x180007118  test    eax, eax
0x18000711a  jnz     short loc_180007124
0x18000711c  mov     qword ptr [rbx+10h], 0
0x180007124  cmp     dword ptr [rbx+8], 0
0x180007128  jz      short loc_18000714A
0x18000712a  mov     rdx, [rbx]; lpSubKey
0x18000712d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007134  mov     edi, 80004005h
0x180007139  call    cs:__imp_RegUnLoadKeyW
0x18000713f  test    eax, eax
0x180007141  js      short loc_180007164
0x180007143  mov     dword ptr [rbx+8], 0
0x18000714a  mov     rcx, [rbx]
0x18000714d  test    rcx, rcx
0x180007150  jz      short loc_180007162
0x180007152  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180007156  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000715b  mov     qword ptr [rbx], 0
0x180007162  xor     edi, edi
0x180007164  mov     eax, edi
0x180007166  mov     rbx, [rsp+28h+arg_0]
0x18000716b  add     rsp, 20h
0x18000716f  pop     rdi
0x180007170  retn
```
