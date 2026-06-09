# SlbNatFindInstance

- ea: `0x1400344f8`
- end: `0x140034547`
- name: `SlbNatFindInstance`
- size: `79`
- prototype: `__int64 __fastcall(wchar_t *Str2)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140007bb0`
- `0x140014220`
- `0x14001448c`
- `0x1400300c4`
- `0x1400308ac`
- `0x140032314`
- `0x1400323e8`
- `0x1400324b8`
- `0x140032600`
- `0x140032770`
- `0x140032838`
- `0x140032948`

## callees

- `0x1400344f8`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x14003451f`
- `ntoskrnl!_wcsicmp` at `0x14003451f`

## pseudocode

```c
const wchar_t *__fastcall SlbNatFindInstance(wchar_t *Str2)
{
  const wchar_t *i; // rbx

  for ( i = (const wchar_t *)qword_140026338; i != (const wchar_t *)&qword_140026338; i = *(const wchar_t **)i )
  {
    if ( !_wcsicmp(i + 40, Str2) )
      return i;
  }
  return 0;
}

```

## disassembly

```asm
0x1400344f8  mov     [rsp+arg_0], rbx
0x1400344fd  push    rdi
0x1400344fe  sub     rsp, 20h
0x140034502  mov     rbx, cs:qword_140026338
0x140034509  mov     rdi, rcx
0x14003450c  lea     rax, qword_140026338
0x140034513  cmp     rbx, rax
0x140034516  jz      short loc_140034539
0x140034518  lea     rcx, [rbx+50h]; Str1
0x14003451c  mov     rdx, rdi; Str2
0x14003451f  call    cs:__imp__wcsicmp
0x140034526  nop     dword ptr [rax+rax+00h]
0x14003452b  test    eax, eax
0x14003452d  jz      short loc_140034534
0x14003452f  mov     rbx, [rbx]
0x140034532  jmp     short loc_14003450C
0x140034534  mov     rax, rbx
0x140034537  jmp     short loc_14003453B
0x140034539  xor     eax, eax
0x14003453b  mov     rbx, [rsp+28h+arg_0]
0x140034540  add     rsp, 20h
0x140034544  pop     rdi
0x140034545  retn
```
