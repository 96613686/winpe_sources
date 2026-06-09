# RegHelper::Set(HKEY__ *,char const *,char const *)

- ea: `0x18000e748`
- end: `0x18000e793`
- name: `?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z`
- size: `75`
- prototype: `bool(RegHelper *__hidden this, HKEY, const char *, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000e8b8`
- `0x18000ebac`

## callees

- `0x18000e748`

## import_xrefs

- `ADVAPI32!RegSetValueExA` at `0x18000e783`
- `ADVAPI32!RegSetValueExA` at `0x18000e783`

## pseudocode

```c
bool __fastcall RegHelper::Set(RegHelper *this, HKEY a2, const BYTE *lpData, const char *a4)
{
  __int64 v4; // rax

  if ( lpData )
  {
    v4 = -1;
    do
      ++v4;
    while ( lpData[v4] );
  }
  else
  {
    LODWORD(v4) = 0;
  }
  return RegSetValueExA(a2, a4, 0, 1u, lpData, v4 + 1) == 0;
}

```

## disassembly

```asm
0x18000e748  sub     rsp, 38h
0x18000e74c  mov     r10, r9
0x18000e74f  mov     r11, rdx
0x18000e752  test    r8, r8
0x18000e755  jz      short loc_18000E767
0x18000e757  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e75b  inc     rax
0x18000e75e  cmp     byte ptr [r8+rax], 0
0x18000e763  jnz     short loc_18000E75B
0x18000e765  jmp     short loc_18000E769
0x18000e767  xor     eax, eax
0x18000e769  inc     eax
0x18000e76b  mov     r9d, 1; dwType
0x18000e771  mov     [rsp+38h+cbData], eax; cbData
0x18000e775  mov     rdx, r10; lpValueName
0x18000e778  mov     [rsp+38h+lpData], r8; lpData
0x18000e77d  mov     rcx, r11; hKey
0x18000e780  xor     r8d, r8d; Reserved
0x18000e783  call    cs:__imp_RegSetValueExA
0x18000e789  test    eax, eax
0x18000e78b  setz    al
0x18000e78e  add     rsp, 38h
0x18000e792  retn
```
