# ComputeGrfscr(ushort const *)

- ea: `0x180018610`
- end: `0x180018681`
- name: `?ComputeGrfscr@@YAKPEBG@Z`
- size: `113`
- prototype: `unsigned int __fastcall(wchar_t *String2)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800180dc`
- `0x180049cb0`
- `0x180049e6c`
- `0x18004b9a0`
- `0x180054d74`

## callees

- `0x180018610`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180018646`
- `msvcrt!_wcsicmp` at `0x18001865f`
- `msvcrt!_wcsicmp` at `0x180018646`
- `msvcrt!_wcsicmp` at `0x18001865f`

## string_xrefs

- `0x180018658`: `STRIP EMBEDDED HTML COMMENTS`

## pseudocode

```c
__int64 __fastcall ComputeGrfscr(wchar_t *String2)
{
  unsigned int v2; // ebx

  v2 = 0;
  if ( String2 )
  {
    if ( *String2 != 34 || String2[1] )
    {
      if ( _wcsicmp(L"</script>", String2) )
      {
        if ( !_wcsicmp(L"STRIP EMBEDDED HTML COMMENTS", String2) )
          return 513;
      }
      else
      {
        return 1;
      }
    }
    else
    {
      return 16;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180018610  mov     [rsp+arg_0], rbx
0x180018615  mov     [rsp+arg_8], rsi
0x18001861a  push    rdi
0x18001861b  sub     rsp, 20h
0x18001861f  xor     esi, esi
0x180018621  mov     rdi, rcx
0x180018624  mov     ebx, esi
0x180018626  test    rcx, rcx
0x180018629  jz      short loc_18001866F
0x18001862b  cmp     word ptr [rcx], 22h ; '"'
0x18001862f  jnz     short loc_18001863C
0x180018631  cmp     [rcx+2], si
0x180018635  jnz     short loc_18001863C
0x180018637  lea     ebx, [rsi+10h]
0x18001863a  jmp     short loc_18001866F
0x18001863c  mov     rdx, rdi; String2
0x18001863f  lea     rcx, aScript; "</script>"
0x180018646  call    cs:__imp__wcsicmp
0x18001864c  test    eax, eax
0x18001864e  jnz     short loc_180018655
0x180018650  lea     ebx, [rax+1]
0x180018653  jmp     short loc_18001866F
0x180018655  mov     rdx, rdi; String2
0x180018658  lea     rcx, aStripEmbeddedH; "STRIP EMBEDDED HTML COMMENTS"
0x18001865f  call    cs:__imp__wcsicmp
0x180018665  test    eax, eax
0x180018667  mov     ecx, 201h
0x18001866c  cmovz   ebx, ecx
0x18001866f  mov     rsi, [rsp+28h+arg_8]
0x180018674  mov     eax, ebx
0x180018676  mov     rbx, [rsp+28h+arg_0]
0x18001867b  add     rsp, 20h
0x18001867f  pop     rdi
0x180018680  retn
```
