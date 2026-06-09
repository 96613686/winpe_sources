# ComputeGrfscr(ushort const *)

- ea: `0x1800131b8`
- end: `0x180013236`
- name: `?ComputeGrfscr@@YAKPEBG@Z`
- size: `126`
- prototype: `unsigned int __fastcall(wchar_t *String2)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012c58`
- `0x18004b2b4`
- `0x18004b470`
- `0x18004d010`
- `0x1800566b4`

## callees

- `0x1800131b8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800131ee`
- `msvcrt!_wcsicmp` at `0x18001320d`
- `msvcrt!_wcsicmp` at `0x1800131ee`
- `msvcrt!_wcsicmp` at `0x18001320d`

## string_xrefs

- `0x180013206`: `STRIP EMBEDDED HTML COMMENTS`

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
0x1800131b8  mov     [rsp+arg_0], rbx
0x1800131bd  mov     [rsp+arg_8], rsi
0x1800131c2  push    rdi
0x1800131c3  sub     rsp, 20h
0x1800131c7  xor     esi, esi
0x1800131c9  mov     rdi, rcx
0x1800131cc  mov     ebx, esi
0x1800131ce  test    rcx, rcx
0x1800131d1  jz      short loc_180013223
0x1800131d3  cmp     word ptr [rcx], 22h ; '"'
0x1800131d7  jnz     short loc_1800131E4
0x1800131d9  cmp     [rcx+2], si
0x1800131dd  jnz     short loc_1800131E4
0x1800131df  lea     ebx, [rsi+10h]
0x1800131e2  jmp     short loc_180013223
0x1800131e4  mov     rdx, rdi; String2
0x1800131e7  lea     rcx, aScript; "</script>"
0x1800131ee  call    cs:__imp__wcsicmp
0x1800131f5  nop     dword ptr [rax+rax+00h]
0x1800131fa  test    eax, eax
0x1800131fc  jnz     short loc_180013203
0x1800131fe  lea     ebx, [rax+1]
0x180013201  jmp     short loc_180013223
0x180013203  mov     rdx, rdi; String2
0x180013206  lea     rcx, aStripEmbeddedH; "STRIP EMBEDDED HTML COMMENTS"
0x18001320d  call    cs:__imp__wcsicmp
0x180013214  nop     dword ptr [rax+rax+00h]
0x180013219  test    eax, eax
0x18001321b  mov     ecx, 201h
0x180013220  cmovz   ebx, ecx
0x180013223  mov     rsi, [rsp+28h+arg_8]
0x180013228  mov     eax, ebx
0x18001322a  mov     rbx, [rsp+28h+arg_0]
0x18001322f  add     rsp, 20h
0x180013233  pop     rdi
0x180013234  retn
```
