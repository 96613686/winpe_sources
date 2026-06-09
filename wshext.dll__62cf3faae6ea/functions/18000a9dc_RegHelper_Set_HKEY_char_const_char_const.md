# RegHelper::Set(HKEY__ *,char const *,char const *)

- ea: `0x18000a9dc`
- end: `0x18000aa27`
- name: `?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z`
- size: `75`
- prototype: `bool(RegHelper *__hidden this, HKEY, const char *, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000aacc`

## callees

- `0x18000a9dc`

## import_xrefs

- `ADVAPI32!RegSetValueExA` at `0x18000aa17`
- `ADVAPI32!RegSetValueExA` at `0x18000aa17`

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
0x18000a9dc  sub     rsp, 38h
0x18000a9e0  mov     r10, r9
0x18000a9e3  mov     r11, rdx
0x18000a9e6  test    r8, r8
0x18000a9e9  jz      short loc_18000A9FB
0x18000a9eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a9ef  inc     rax
0x18000a9f2  cmp     byte ptr [r8+rax], 0
0x18000a9f7  jnz     short loc_18000A9EF
0x18000a9f9  jmp     short loc_18000A9FD
0x18000a9fb  xor     eax, eax
0x18000a9fd  inc     eax
0x18000a9ff  mov     r9d, 1; dwType
0x18000aa05  mov     [rsp+38h+cbData], eax; cbData
0x18000aa09  mov     rdx, r10; lpValueName
0x18000aa0c  mov     [rsp+38h+lpData], r8; lpData
0x18000aa11  mov     rcx, r11; hKey
0x18000aa14  xor     r8d, r8d; Reserved
0x18000aa17  call    cs:__imp_RegSetValueExA
0x18000aa1d  test    eax, eax
0x18000aa1f  setz    al
0x18000aa22  add     rsp, 38h
0x18000aa26  retn
```
