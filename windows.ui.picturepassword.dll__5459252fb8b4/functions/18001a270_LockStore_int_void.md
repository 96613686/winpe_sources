# _LockStore(int,void * *)

- ea: `0x18001a270`
- end: `0x18001a33c`
- name: `?_LockStore@@YAJHPEAPEAX@Z`
- size: `204`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019e3c`

## callees

- `0x18001a154`
- `0x18001a270`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a329`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a329`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a2ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a2ad`

## string_xrefs

- `0x18001a2ec`: `RegOpenKeyEx`
- `0x18001a2e5`: `onecore\ds\security\eas\policyengine\common.cpp`

## pseudocode

```c
__int64 __fastcall _LockStore(__int64 a1, void **a2)
{
  int v3; // ebx
  bool v4; // zf
  HKEY v5; // rcx
  __int64 v7; // [rsp+20h] [rbp-28h]
  HKEY v8; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  v8 = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\EAS\\Policies", 0, 0x20019u, &v8);
  if ( (unsigned int)(v3 - 2) > 1 )
  {
    v4 = v3 == 0;
    if ( v3 <= 0 )
      goto LABEL_6;
    v3 = (unsigned __int16)v3 | 0xC0070000;
  }
  else
  {
    v3 = 0;
  }
  v4 = v3 == 0;
LABEL_6:
  if ( v4 )
  {
    v5 = 0;
    *a2 = v8;
    v3 = 0;
    v8 = 0;
  }
  else
  {
    LODWORD(v7) = 42;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      (unsigned int)v3,
      L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
      v7,
      L"RegOpenKeyEx",
      &pszPassword);
    v5 = v8;
  }
  if ( v5 )
    RegCloseKey(v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001a270  mov     r11, rsp
0x18001a273  mov     [r11+8], rbx
0x18001a277  push    rdi
0x18001a278  sub     rsp, 40h
0x18001a27c  mov     rdi, rdx
0x18001a27f  mov     qword ptr [rdx], 0
0x18001a286  lea     rax, [r11+10h]
0x18001a28a  mov     qword ptr [r11+10h], 0
0x18001a292  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\EAS"...
0x18001a299  mov     [r11-28h], rax
0x18001a29d  mov     r9d, 20019h; samDesired
0x18001a2a3  xor     r8d, r8d; ulOptions
0x18001a2a6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a2ad  call    cs:__imp_RegOpenKeyExW
0x18001a2b3  mov     ebx, eax
0x18001a2b5  mov     ecx, 1; unsigned int
0x18001a2ba  add     eax, 0FFFFFFFEh
0x18001a2bd  cmp     eax, ecx
0x18001a2bf  ja      short loc_18001A2C5
0x18001a2c1  xor     ebx, ebx
0x18001a2c3  jmp     short loc_18001A2D2
0x18001a2c5  test    ebx, ebx
0x18001a2c7  jle     short loc_18001A2D4
0x18001a2c9  movzx   ebx, bx
0x18001a2cc  or      ebx, 0C0070000h
0x18001a2d2  test    ebx, ebx
0x18001a2d4  jz      short loc_18001A313
0x18001a2d6  lea     rax, pszPassword
0x18001a2dd  mov     r8d, ebx
0x18001a2e0  mov     [rsp+48h+var_18], rax
0x18001a2e5  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\eas\\policyengin"...
0x18001a2ec  lea     rax, aRegopenkeyex; "RegOpenKeyEx"
0x18001a2f3  mov     [rsp+48h+var_20], rax
0x18001a2f8  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18001a2ff  mov     dword ptr [rsp+48h+var_28], 2Ah ; '*'
0x18001a307  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18001a30c  mov     rcx, [rsp+48h+arg_8]
0x18001a311  jmp     short loc_18001A324
0x18001a313  mov     rax, [rsp+48h+arg_8]
0x18001a318  xor     ecx, ecx; hKey
0x18001a31a  mov     [rdi], rax
0x18001a31d  xor     ebx, ebx
0x18001a31f  mov     [rsp+48h+arg_8], rcx
0x18001a324  test    rcx, rcx
0x18001a327  jz      short loc_18001A32F
0x18001a329  call    cs:__imp_RegCloseKey
0x18001a32f  mov     eax, ebx
0x18001a331  mov     rbx, [rsp+48h+arg_0]
0x18001a336  add     rsp, 40h
0x18001a33a  pop     rdi
0x18001a33b  retn
```
