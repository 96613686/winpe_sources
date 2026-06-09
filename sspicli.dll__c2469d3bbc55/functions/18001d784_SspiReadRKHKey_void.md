# SspiReadRKHKey(void)

- ea: `0x18001d784`
- end: `0x18001d876`
- name: `?SspiReadRKHKey@@YAEXZ`
- size: `242`
- prototype: `unsigned __int8(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001d880`

## callees

- `0x18001d784`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d83f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d83f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d808`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d808`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d7d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d7d8`

## pseudocode

```c
bool SspiReadRKHKey(void)
{
  unsigned int v0; // eax
  LSTATUS v1; // ecx
  LSTATUS v2; // ecx
  int v3; // eax
  DWORD Type; // [rsp+40h] [rbp+10h] BYREF
  int Data; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  v0 = DisableRKH;
  Type = 0;
  cbData = 4;
  Data = 0;
  hKey = 0;
  if ( !DisableRKH )
  {
    v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\MSV1_0", 0, 1u, &hKey);
    if ( v1 )
    {
      v0 = 2;
      if ( v1 == 2 )
      {
        DisableRKH = 1;
        return 1;
      }
      DisableRKH = 2;
    }
    else
    {
      v2 = RegQueryValueExW(hKey, L"DisableHostToTarget", 0, &Type, (LPBYTE)&Data, &cbData);
      v3 = 2;
      if ( v2 )
      {
        if ( v2 == 2 )
          v3 = 1;
      }
      else if ( Type == 4 )
      {
        v3 = (Data != 0) + 1;
      }
      DisableRKH = v3;
      RegCloseKey(hKey);
      v0 = DisableRKH;
    }
  }
  return v0 == 1;
}

```

## disassembly

```asm
0x18001d784  push    rbp
0x18001d786  mov     rbp, rsp
0x18001d789  sub     rsp, 30h
0x18001d78d  mov     eax, cs:?DisableRKH@@3KA; ulong DisableRKH
0x18001d793  mov     [rbp+Type], 0
0x18001d79a  mov     [rbp+cbData], 4
0x18001d7a1  mov     [rbp+Data], 0
0x18001d7a8  mov     [rbp+hKey], 0
0x18001d7b0  test    eax, eax
0x18001d7b2  jnz     loc_18001D86A
0x18001d7b8  lea     rax, [rbp+hKey]
0x18001d7bc  mov     r9d, 1; samDesired
0x18001d7c2  xor     r8d, r8d; ulOptions
0x18001d7c5  mov     [rsp+30h+phkResult], rax; phkResult
0x18001d7ca  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x18001d7d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d7d8  call    cs:__imp_RegOpenKeyExW
0x18001d7de  mov     ecx, eax
0x18001d7e0  test    eax, eax
0x18001d7e2  jnz     short loc_18001D84D
0x18001d7e4  mov     rcx, [rbp+hKey]; hKey
0x18001d7e8  lea     rax, [rbp+cbData]
0x18001d7ec  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001d7f1  lea     r9, [rbp+Type]; lpType
0x18001d7f5  lea     rax, [rbp+Data]
0x18001d7f9  xor     r8d, r8d; lpReserved
0x18001d7fc  lea     rdx, aDisablehosttot; "DisableHostToTarget"
0x18001d803  mov     [rsp+30h+phkResult], rax; lpData
0x18001d808  call    cs:__imp_RegQueryValueExW
0x18001d80e  mov     ecx, eax
0x18001d810  mov     eax, 2
0x18001d815  test    ecx, ecx
0x18001d817  jnz     short loc_18001D82C
0x18001d819  cmp     [rbp+Type], 4
0x18001d81d  jnz     short loc_18001D835
0x18001d81f  mov     eax, [rbp+Data]
0x18001d822  neg     eax
0x18001d824  sbb     eax, eax
0x18001d826  neg     eax
0x18001d828  inc     eax
0x18001d82a  jmp     short loc_18001D835
0x18001d82c  cmp     ecx, eax
0x18001d82e  jnz     short loc_18001D835
0x18001d830  mov     eax, 1
0x18001d835  mov     rcx, [rbp+hKey]; hKey
0x18001d839  mov     cs:?DisableRKH@@3KA, eax; ulong DisableRKH
0x18001d83f  call    cs:__imp_RegCloseKey
0x18001d845  mov     eax, cs:?DisableRKH@@3KA; ulong DisableRKH
0x18001d84b  jmp     short loc_18001D86A
0x18001d84d  mov     eax, 2
0x18001d852  cmp     ecx, eax
0x18001d854  jnz     short loc_18001D864
0x18001d856  mov     cs:?DisableRKH@@3KA, 1; ulong DisableRKH
0x18001d860  mov     al, 1
0x18001d862  jmp     short loc_18001D870
0x18001d864  mov     cs:?DisableRKH@@3KA, eax; ulong DisableRKH
0x18001d86a  cmp     eax, 1
0x18001d86d  setz    al
0x18001d870  add     rsp, 30h
0x18001d874  pop     rbp
0x18001d875  retn
```
