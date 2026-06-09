# SiIsValidDiskDevice

- ea: `0x140032314`
- end: `0x1400323e1`
- name: `SiIsValidDiskDevice`
- size: `205`
- prototype: `__int64 __fastcall(wchar_t *Str1, wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x1400323e8`

## callees

- `0x140032314`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x140032330`
- `ntoskrnl!_wcsicmp` at `0x14003234c`
- `ntoskrnl!_wcsicmp` at `0x140032330`
- `ntoskrnl!_wcsicmp` at `0x14003234c`
- `ntoskrnl!_wcsnicmp` at `0x14003236c`
- `ntoskrnl!_wcsnicmp` at `0x14003236c`

## string_xrefs

- `0x140032326`: `Directory`
- `0x140032342`: `SymbolicLink`

## pseudocode

```c
char __fastcall SiIsValidDiskDevice(wchar_t *Str1, wchar_t *a2, int *a3)
{
  wchar_t *v6; // r8
  wchar_t v7; // dx
  int v8; // ecx
  __int16 v10; // r9

  if ( _wcsicmp(a2, L"Directory") && _wcsicmp(a2, L"SymbolicLink") )
    return 0;
  if ( _wcsnicmp(Str1, L"Harddisk", 8u) )
    return 0;
  v6 = Str1 + 8;
  v7 = Str1[8];
  if ( !v7 )
    return 0;
  v8 = 0;
  if ( v7 != 48 )
  {
    v10 = 0;
    while ( v7 )
    {
      if ( (unsigned __int16)(v7 - 48) > 9u )
        return 0;
      if ( (unsigned __int16)++v10 > 0xAu )
        return 0;
      ++v6;
      v8 = v7 + 2 * (5 * v8 - 24);
      v7 = *v6;
    }
    goto LABEL_7;
  }
  if ( Str1[9] )
    return 0;
LABEL_7:
  if ( a3 )
    *a3 = v8;
  return 1;
}

```

## disassembly

```asm
0x140032314  push    rbx
0x140032316  push    rbp
0x140032317  push    rsi
0x140032318  push    rdi
0x140032319  sub     rsp, 28h
0x14003231d  mov     rsi, rdx
0x140032320  mov     rbx, rcx
0x140032323  mov     rcx, rsi; Str1
0x140032326  lea     rdx, aDirectory; "Directory"
0x14003232d  mov     rdi, r8
0x140032330  call    cs:__imp__wcsicmp
0x140032337  nop     dword ptr [rax+rax+00h]
0x14003233c  xor     ebp, ebp
0x14003233e  test    eax, eax
0x140032340  jz      short loc_14003235C
0x140032342  lea     rdx, aSymboliclink; "SymbolicLink"
0x140032349  mov     rcx, rsi; Str1
0x14003234c  call    cs:__imp__wcsicmp
0x140032353  nop     dword ptr [rax+rax+00h]
0x140032358  test    eax, eax
0x14003235a  jnz     short loc_1400323D5
0x14003235c  mov     r8d, 8; MaxCount
0x140032362  lea     rdx, aHarddisk; "Harddisk"
0x140032369  mov     rcx, rbx; Str1
0x14003236c  call    cs:__imp__wcsnicmp
0x140032373  nop     dword ptr [rax+rax+00h]
0x140032378  test    eax, eax
0x14003237a  jnz     short loc_1400323D5
0x14003237c  lea     r8, [rbx+10h]
0x140032380  movzx   edx, word ptr [r8]
0x140032384  test    dx, dx
0x140032387  jz      short loc_1400323D5
0x140032389  mov     ecx, ebp
0x14003238b  cmp     dx, 30h ; '0'
0x14003238f  jnz     short loc_1400323A3
0x140032391  cmp     [r8+2], bp
0x140032396  jnz     short loc_1400323D5
0x140032398  test    rdi, rdi
0x14003239b  jz      short loc_14003239F
0x14003239d  mov     [rdi], ecx
0x14003239f  mov     al, 1
0x1400323a1  jmp     short loc_1400323D7
0x1400323a3  mov     r9d, ebp
0x1400323a6  test    dx, dx
0x1400323a9  jz      short loc_140032398
0x1400323ab  lea     eax, [rdx-30h]
0x1400323ae  cmp     ax, 9
0x1400323b2  ja      short loc_1400323D5
0x1400323b4  inc     r9w
0x1400323b8  cmp     r9w, 0Ah
0x1400323bd  ja      short loc_1400323D5
0x1400323bf  movzx   eax, dx
0x1400323c2  lea     ecx, [rcx+rcx*4]
0x1400323c5  add     r8, 2
0x1400323c9  lea     ecx, [rcx-18h]
0x1400323cc  lea     ecx, [rax+rcx*2]
0x1400323cf  movzx   edx, word ptr [r8]
0x1400323d3  jmp     short loc_1400323A6
0x1400323d5  xor     al, al
0x1400323d7  add     rsp, 28h
0x1400323db  pop     rdi
0x1400323dc  pop     rsi
0x1400323dd  pop     rbp
0x1400323de  pop     rbx
0x1400323df  retn
```
