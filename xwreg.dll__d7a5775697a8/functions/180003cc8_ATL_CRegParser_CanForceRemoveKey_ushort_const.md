# ATL::CRegParser::CanForceRemoveKey(ushort const *)

- ea: `0x180003cc8`
- end: `0x180003d0f`
- name: `?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z`
- size: `71`
- prototype: `int(ATL::CRegParser *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800055a0`

## callees

- `0x180003cc8`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003ced`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003ced`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CanForceRemoveKey(ATL::CRegParser *this, const unsigned __int16 *a2)
{
  int i; // ebx

  for ( i = 0; i < 12; ++i )
  {
    if ( !lstrcmpiW(a2, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[i]) )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180003cc8  mov     [rsp+arg_0], rbx
0x180003ccd  push    rdi
0x180003cce  sub     rsp, 20h
0x180003cd2  mov     rdi, rdx
0x180003cd5  xor     ebx, ebx
0x180003cd7  cmp     ebx, 0Ch
0x180003cda  jge     short loc_180003CFF
0x180003cdc  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180003ce3  movsxd  rdx, ebx
0x180003ce6  mov     rcx, rdi; lpString1
0x180003ce9  mov     rdx, [rax+rdx*8]; lpString2
0x180003ced  call    cs:__imp_lstrcmpiW
0x180003cf3  test    eax, eax
0x180003cf5  jz      short loc_180003CFB
0x180003cf7  inc     ebx
0x180003cf9  jmp     short loc_180003CD7
0x180003cfb  xor     eax, eax
0x180003cfd  jmp     short loc_180003D04
0x180003cff  mov     eax, 1
0x180003d04  mov     rbx, [rsp+28h+arg_0]
0x180003d09  add     rsp, 20h
0x180003d0d  pop     rdi
0x180003d0e  retn
```
