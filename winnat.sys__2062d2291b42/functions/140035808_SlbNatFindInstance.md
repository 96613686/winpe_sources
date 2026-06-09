# SlbNatFindInstance

- ea: `0x140035808`
- end: `0x140035857`
- name: `SlbNatFindInstance`
- size: `79`
- prototype: `__int64 __fastcall(wchar_t *Str2)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140007bb0`
- `0x140014b60`
- `0x140014dcc`
- `0x1400311f4`
- `0x1400319dc`
- `0x140033444`
- `0x140033518`
- `0x1400335e8`
- `0x140033730`
- `0x1400338a0`
- `0x140033968`
- `0x140033a78`

## callees

- `0x140035808`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x14003582f`
- `ntoskrnl!_wcsicmp` at `0x14003582f`

## pseudocode

```c
const wchar_t *__fastcall SlbNatFindInstance(wchar_t *Str2)
{
  const wchar_t *i; // rbx

  for ( i = (const wchar_t *)qword_140027338; i != (const wchar_t *)&qword_140027338; i = *(const wchar_t **)i )
  {
    if ( !_wcsicmp(i + 40, Str2) )
      return i;
  }
  return 0;
}

```

## disassembly

```asm
0x140035808  mov     [rsp+arg_0], rbx
0x14003580d  push    rdi
0x14003580e  sub     rsp, 20h
0x140035812  mov     rbx, cs:qword_140027338
0x140035819  mov     rdi, rcx
0x14003581c  lea     rax, qword_140027338
0x140035823  cmp     rbx, rax
0x140035826  jz      short loc_140035849
0x140035828  lea     rcx, [rbx+50h]; Str1
0x14003582c  mov     rdx, rdi; Str2
0x14003582f  call    cs:__imp__wcsicmp
0x140035836  nop     dword ptr [rax+rax+00h]
0x14003583b  test    eax, eax
0x14003583d  jz      short loc_140035844
0x14003583f  mov     rbx, [rbx]
0x140035842  jmp     short loc_14003581C
0x140035844  mov     rax, rbx
0x140035847  jmp     short loc_14003584B
0x140035849  xor     eax, eax
0x14003584b  mov     rbx, [rsp+28h+arg_0]
0x140035850  add     rsp, 20h
0x140035854  pop     rdi
0x140035855  retn
```
