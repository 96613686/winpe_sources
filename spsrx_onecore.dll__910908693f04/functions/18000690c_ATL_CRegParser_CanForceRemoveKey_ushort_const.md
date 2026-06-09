# ATL::CRegParser::CanForceRemoveKey(ushort const *)

- ea: `0x18000690c`
- end: `0x18000694e`
- name: `?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z`
- size: `66`
- prototype: `int(ATL::CRegParser *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800078ec`

## callees

- `0x18000690c`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006929`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006929`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CanForceRemoveKey(ATL::CRegParser *this, const unsigned __int16 *a2)
{
  __int64 v3; // rbx

  v3 = 0;
  while ( lstrcmpiW(a2, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[v3]) )
  {
    v3 = (unsigned int)(v3 + 1);
    if ( (int)v3 >= 12 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000690c  mov     [rsp+arg_0], rbx
0x180006911  push    rdi
0x180006912  sub     rsp, 20h
0x180006916  mov     rdi, rdx
0x180006919  xor     ebx, ebx
0x18000691b  lea     rcx, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180006922  mov     rdx, [rcx+rbx*8]; lpString2
0x180006926  mov     rcx, rdi; lpString1
0x180006929  call    cs:__imp_lstrcmpiW
0x18000692f  test    eax, eax
0x180006931  jz      short loc_180006941
0x180006933  inc     ebx
0x180006935  cmp     ebx, 0Ch
0x180006938  jl      short loc_18000691B
0x18000693a  mov     eax, 1
0x18000693f  jmp     short loc_180006943
0x180006941  xor     eax, eax
0x180006943  mov     rbx, [rsp+28h+arg_0]
0x180006948  add     rsp, 20h
0x18000694c  pop     rdi
0x18000694d  retn
```
