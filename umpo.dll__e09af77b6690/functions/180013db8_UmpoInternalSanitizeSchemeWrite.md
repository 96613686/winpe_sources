# UmpoInternalSanitizeSchemeWrite

- ea: `0x180013db8`
- end: `0x180013df1`
- name: `UmpoInternalSanitizeSchemeWrite`
- size: `57`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180013984`

## callees

- `0x180013db8`
- `0x1800188b0`

## string_xrefs

- `0x180013dd4`: `@%SystemRoot%\system32\powrprof.dll,`

## pseudocode

```c
__int64 __fastcall UmpoInternalSanitizeSchemeWrite(const wchar_t *a1, unsigned int a2)
{
  unsigned int v2; // ebx

  v2 = 0;
  if ( a2 >= 2 && *a1 == 64 && (a2 < 0x4A || wcsncmp_0(a1, L"@%SystemRoot%\\system32\\powrprof.dll,", 0x24u)) )
    return 5;
  return v2;
}

```

## disassembly

```asm
0x180013db8  push    rbx
0x180013dba  sub     rsp, 20h
0x180013dbe  xor     ebx, ebx
0x180013dc0  cmp     edx, 2
0x180013dc3  jb      short loc_180013DE9
0x180013dc5  cmp     word ptr [rcx], 40h ; '@'
0x180013dc9  jnz     short loc_180013DE9
0x180013dcb  cmp     edx, 4Ah ; 'J'
0x180013dce  jb      short loc_180013DE4
0x180013dd0  lea     r8d, [rbx+24h]; MaxCount
0x180013dd4  lea     rdx, aSystemrootSyst; "@%SystemRoot%\\system32\\powrprof.dll,"
0x180013ddb  call    wcsncmp_0
0x180013de0  test    eax, eax
0x180013de2  jz      short loc_180013DE9
0x180013de4  mov     ebx, 5
0x180013de9  mov     eax, ebx
0x180013deb  add     rsp, 20h
0x180013def  pop     rbx
0x180013df0  retn
```
