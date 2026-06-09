# UmpoWnfEnergySaverOverrideCallback

- ea: `0x1800114f0`
- end: `0x18001154e`
- name: `UmpoWnfEnergySaverOverrideCallback`
- size: `94`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _DWORD *Data, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800114f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180011539`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180011539`

## pseudocode

```c
__int64 __fastcall UmpoWnfEnergySaverOverrideCallback(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _DWORD *Data,
        int a6)
{
  unsigned int v6; // ebx

  if ( Data && a6 == 4 )
  {
    LODWORD(Data) = *Data;
    v6 = 0;
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, &UmpoEcoModeRedirectedRegistryPath, L"EnergySaverState", 4u, &Data, 4u);
  }
  else
  {
    return 128;
  }
  return v6;
}

```

## disassembly

```asm
0x1800114f0  push    rbx
0x1800114f2  sub     rsp, 30h
0x1800114f6  mov     rax, [rsp+38h+Data]
0x1800114fb  test    rax, rax
0x1800114fe  jz      short loc_180011541
0x180011500  mov     r9d, 4; dwType
0x180011506  cmp     [rsp+38h+arg_28], r9d
0x18001150b  jnz     short loc_180011541
0x18001150d  mov     eax, [rax]
0x18001150f  lea     r8, aEnergysaversta; "EnergySaverState"
0x180011516  mov     dword ptr [rsp+38h+Data], eax
0x18001151a  lea     rdx, UmpoEcoModeRedirectedRegistryPath; lpSubKey
0x180011521  lea     rax, [rsp+38h+Data]
0x180011526  mov     [rsp+38h+cbData], r9d; cbData
0x18001152b  xor     ebx, ebx
0x18001152d  mov     [rsp+38h+lpData], rax; lpData
0x180011532  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011539  call    cs:__imp_RegSetKeyValueW
0x18001153f  jmp     short loc_180011546
0x180011541  mov     ebx, 80h
0x180011546  mov     eax, ebx
0x180011548  add     rsp, 30h
0x18001154c  pop     rbx
0x18001154d  retn
```
