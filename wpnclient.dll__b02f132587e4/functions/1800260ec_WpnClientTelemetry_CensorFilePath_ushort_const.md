# WpnClientTelemetry::CensorFilePath(ushort const *)

- ea: `0x1800260ec`
- end: `0x18002611c`
- name: `?CensorFilePath@WpnClientTelemetry@@QEAAPEBGPEBG@Z`
- size: `48`
- prototype: `const unsigned __int16 *(WpnClientTelemetry *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180026610`
- `0x1800266e8`

## callees

- `0x1800260ec`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1800260fd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1800260fd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18002610a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18002610a`

## pseudocode

```c
const unsigned __int16 *__fastcall WpnClientTelemetry::CensorFilePath(
        WpnClientTelemetry *this,
        const unsigned __int16 *a2)
{
  const WCHAR *v2; // rbx

  v2 = a2;
  if ( a2 && !PathIsFileSpecW(a2) )
    return PathFindFileNameW(v2);
  return v2;
}

```

## disassembly

```asm
0x1800260ec  push    rbx
0x1800260ee  sub     rsp, 20h
0x1800260f2  mov     rbx, rdx
0x1800260f5  test    rdx, rdx
0x1800260f8  jz      short loc_180026113
0x1800260fa  mov     rcx, rdx; pszPath
0x1800260fd  call    cs:__imp_PathIsFileSpecW
0x180026103  test    eax, eax
0x180026105  jnz     short loc_180026113
0x180026107  mov     rcx, rbx; pszPath
0x18002610a  call    cs:__imp_PathFindFileNameW
0x180026110  mov     rbx, rax
0x180026113  mov     rax, rbx
0x180026116  add     rsp, 20h
0x18002611a  pop     rbx
0x18002611b  retn
```
