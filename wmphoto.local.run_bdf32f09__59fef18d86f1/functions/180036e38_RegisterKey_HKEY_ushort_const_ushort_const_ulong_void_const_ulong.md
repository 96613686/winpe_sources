# RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)

- ea: `0x180036e38`
- end: `0x180036ef4`
- name: `?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z`
- size: `188`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180036fe0`

## callees

- `0x180036e38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036ed5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036ed5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036eb8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036eb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036ee0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036ee0`

## pseudocode

```c
__int64 __fastcall RegisterKey(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        BYTE *lpData,
        DWORD a6)
{
  const BYTE *v6; // rdi
  DWORD v9; // ebx
  __int64 v10; // rax
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+20h] BYREF

  v6 = lpData;
  hKey = 0;
  dwDisposition = 0;
  if ( a4 == 1 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&lpData[2 * v10] );
    v9 = 2 * v10 + 2;
  }
  else if ( a4 == 4 )
  {
    v9 = 4;
  }
  else
  {
    v9 = a6;
  }
  RegCreateKeyExW(a1, a2, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
  RegSetValueExW(hKey, a3, 0, a4, v6, v9);
  RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x180036e38  mov     rax, rsp
0x180036e3b  push    rbx
0x180036e3c  push    rbp
0x180036e3d  push    rsi
0x180036e3e  push    rdi
0x180036e3f  sub     rsp, 68h
0x180036e43  mov     rdi, [rsp+88h+lpData]
0x180036e4b  mov     rbp, r8
0x180036e4e  xor     r8d, r8d; Reserved
0x180036e51  mov     esi, r9d
0x180036e54  mov     [rax-38h], r8
0x180036e58  mov     [rax+20h], r8d
0x180036e5c  mov     eax, r9d
0x180036e5f  sub     eax, 1
0x180036e62  jz      short loc_180036E77
0x180036e64  cmp     eax, 3
0x180036e67  jnz     short loc_180036E6E
0x180036e69  lea     ebx, [rax+1]
0x180036e6c  jmp     short loc_180036E8C
0x180036e6e  mov     ebx, [rsp+88h+arg_28]
0x180036e75  jmp     short loc_180036E8C
0x180036e77  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036e7b  inc     rax
0x180036e7e  cmp     [rdi+rax*2], r8w
0x180036e83  jnz     short loc_180036E7B
0x180036e85  lea     ebx, ds:2[rax*2]
0x180036e8c  lea     rax, [rsp+88h+dwDisposition]
0x180036e94  xor     r9d, r9d; lpClass
0x180036e97  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x180036e9c  lea     rax, [rsp+88h+hKey]
0x180036ea1  mov     [rsp+88h+phkResult], rax; phkResult
0x180036ea6  mov     [rsp+88h+lpSecurityAttributes], r8; lpSecurityAttributes
0x180036eab  mov     [rsp+88h+samDesired], 20006h; samDesired
0x180036eb3  mov     [rsp+88h+dwOptions], r8d; dwOptions
0x180036eb8  call    cs:__imp_RegCreateKeyExW
0x180036ebe  mov     rcx, [rsp+88h+hKey]; hKey
0x180036ec3  mov     r9d, esi; dwType
0x180036ec6  xor     r8d, r8d; Reserved
0x180036ec9  mov     [rsp+88h+samDesired], ebx; cbData
0x180036ecd  mov     rdx, rbp; lpValueName
0x180036ed0  mov     qword ptr [rsp+88h+dwOptions], rdi; lpData
0x180036ed5  call    cs:__imp_RegSetValueExW
0x180036edb  mov     rcx, [rsp+88h+hKey]; hKey
0x180036ee0  call    cs:__imp_RegCloseKey
0x180036ee6  mov     eax, 1
0x180036eeb  add     rsp, 68h
0x180036eef  pop     rdi
0x180036ef0  pop     rsi
0x180036ef1  pop     rbp
0x180036ef2  pop     rbx
0x180036ef3  retn
```
