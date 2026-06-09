# StringTypePriv::_ConvertStrToType<HKEY__ *>(HKEY__ *,HKEY__ * *,ushort const *,ushort const *,ushort const *)

- ea: `0x180051b4c`
- end: `0x180051bcc`
- name: `??$_ConvertStrToType@PEAUHKEY__@@@StringTypePriv@@CA_NPEAUHKEY__@@PEAPEAU1@PEBG22@Z`
- size: `128`
- prototype: `char __fastcall(__int64, _QWORD *, const WCHAR *, const WCHAR *, const WCHAR *lpString2)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180051bd4`

## callees

- `0x180051b4c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180051b81`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180051ba8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180051b81`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180051ba8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall StringTypePriv::_ConvertStrToType<HKEY__ *>(
        __int64 a1,
        _QWORD *a2,
        const WCHAR *a3,
        const WCHAR *a4,
        const WCHAR *lpString2)
{
  if ( (!a4 || CompareStringOrdinal(a3, -1, a4, -1, 1) != 2)
    && (!lpString2 || CompareStringOrdinal(a3, -1, lpString2, -1, 1) != 2) )
  {
    return 0;
  }
  *a2 = a1;
  return 1;
}

```

## disassembly

```asm
0x180051b4c  mov     [rsp+arg_0], rbx
0x180051b51  mov     [rsp+arg_8], rsi
0x180051b56  push    rdi
0x180051b57  sub     rsp, 30h
0x180051b5b  mov     rax, r9
0x180051b5e  mov     rsi, r8
0x180051b61  mov     rbx, rdx
0x180051b64  mov     rdi, rcx
0x180051b67  test    r9, r9
0x180051b6a  jz      short loc_180051B8C
0x180051b6c  or      r9d, 0FFFFFFFFh; cchCount2
0x180051b70  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180051b78  or      edx, r9d; cchCount1
0x180051b7b  mov     r8, rax; lpString2
0x180051b7e  mov     rcx, rsi; lpString1
0x180051b81  call    cs:__imp_CompareStringOrdinal
0x180051b87  cmp     eax, 2
0x180051b8a  jz      short loc_180051BB3
0x180051b8c  mov     r8, [rsp+38h+lpString2]; lpString2
0x180051b91  test    r8, r8
0x180051b94  jz      short loc_180051BBA
0x180051b96  or      r9d, 0FFFFFFFFh; cchCount2
0x180051b9a  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180051ba2  or      edx, r9d; cchCount1
0x180051ba5  mov     rcx, rsi; lpString1
0x180051ba8  call    cs:__imp_CompareStringOrdinal
0x180051bae  cmp     eax, 2
0x180051bb1  jnz     short loc_180051BBA
0x180051bb3  mov     [rbx], rdi
0x180051bb6  mov     al, 1
0x180051bb8  jmp     short loc_180051BBC
0x180051bba  xor     al, al
0x180051bbc  mov     rbx, [rsp+38h+arg_0]
0x180051bc1  mov     rsi, [rsp+38h+arg_8]
0x180051bc6  add     rsp, 30h
0x180051bca  pop     rdi
0x180051bcb  retn
```
