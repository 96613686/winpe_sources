# RegisterKey(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)

- ea: `0x180037414`
- end: `0x1800374e3`
- name: `?RegisterKey@@YAHPEAUHKEY__@@PEBG1KPEBXK@Z`
- size: `207`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800375d0`

## callees

- `0x180037414`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800374b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800374b7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037494`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037494`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800374c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800374c8`

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
0x180037414  mov     rax, rsp
0x180037417  push    rbx
0x180037418  push    rbp
0x180037419  push    rsi
0x18003741a  push    rdi
0x18003741b  sub     rsp, 68h
0x18003741f  mov     rdi, [rsp+88h+lpData]
0x180037427  mov     rbp, r8
0x18003742a  xor     r8d, r8d; Reserved
0x18003742d  mov     esi, r9d
0x180037430  mov     [rax-38h], r8
0x180037434  mov     [rax+20h], r8d
0x180037438  mov     eax, r9d
0x18003743b  sub     eax, 1
0x18003743e  jz      short loc_180037453
0x180037440  cmp     eax, 3
0x180037443  jnz     short loc_18003744A
0x180037445  lea     ebx, [rax+1]
0x180037448  jmp     short loc_180037468
0x18003744a  mov     ebx, [rsp+88h+arg_28]
0x180037451  jmp     short loc_180037468
0x180037453  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037457  inc     rax
0x18003745a  cmp     [rdi+rax*2], r8w
0x18003745f  jnz     short loc_180037457
0x180037461  lea     ebx, ds:2[rax*2]
0x180037468  lea     rax, [rsp+88h+dwDisposition]
0x180037470  xor     r9d, r9d; lpClass
0x180037473  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x180037478  lea     rax, [rsp+88h+hKey]
0x18003747d  mov     [rsp+88h+phkResult], rax; phkResult
0x180037482  mov     [rsp+88h+lpSecurityAttributes], r8; lpSecurityAttributes
0x180037487  mov     [rsp+88h+samDesired], 20006h; samDesired
0x18003748f  mov     [rsp+88h+dwOptions], r8d; dwOptions
0x180037494  call    cs:__imp_RegCreateKeyExW
0x18003749b  nop     dword ptr [rax+rax+00h]
0x1800374a0  mov     rcx, [rsp+88h+hKey]; hKey
0x1800374a5  mov     r9d, esi; dwType
0x1800374a8  xor     r8d, r8d; Reserved
0x1800374ab  mov     [rsp+88h+samDesired], ebx; cbData
0x1800374af  mov     rdx, rbp; lpValueName
0x1800374b2  mov     qword ptr [rsp+88h+dwOptions], rdi; lpData
0x1800374b7  call    cs:__imp_RegSetValueExW
0x1800374be  nop     dword ptr [rax+rax+00h]
0x1800374c3  mov     rcx, [rsp+88h+hKey]; hKey
0x1800374c8  call    cs:__imp_RegCloseKey
0x1800374cf  nop     dword ptr [rax+rax+00h]
0x1800374d4  mov     eax, 1
0x1800374d9  add     rsp, 68h
0x1800374dd  pop     rdi
0x1800374de  pop     rsi
0x1800374df  pop     rbp
0x1800374e0  pop     rbx
0x1800374e1  retn
```
