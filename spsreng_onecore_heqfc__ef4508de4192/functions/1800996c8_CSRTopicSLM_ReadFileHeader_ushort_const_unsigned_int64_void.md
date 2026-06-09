# CSRTopicSLM::ReadFileHeader(ushort const *,unsigned __int64,void *)

- ea: `0x1800996c8`
- end: `0x180099750`
- name: `?ReadFileHeader@CSRTopicSLM@@SAJPEBG_KPEAX@Z`
- size: `136`
- prototype: `__int64 __fastcall(wchar_t *FileName, size_t ElementCount, void *Buffer)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000b6a0`
- `0x1800999d8`

## callees

- `0x1800055cc`
- `0x1800996c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x1800996f4`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x1800996f4`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18009972a`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18009972a`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180099713`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180099713`

## pseudocode

```c
errno_t __fastcall CSRTopicSLM::ReadFileHeader(wchar_t *FileName, size_t ElementCount, void *Buffer)
{
  errno_t result; // eax
  bool v6; // cc
  int Win32Error; // ebx
  FILE *Stream; // [rsp+48h] [rbp+20h] BYREF

  Stream = 0;
  result = _wfopen_s(&Stream, FileName, L"rb");
  if ( Stream )
  {
    v6 = result <= 0;
    if ( !result )
    {
      Win32Error = 0;
      if ( fread(Buffer, 1u, ElementCount, Stream) != ElementCount )
        Win32Error = HrFromLastWin32Error();
      fclose(Stream);
      return Win32Error;
    }
  }
  else
  {
    v6 = result <= 0;
  }
  if ( !v6 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800996c8  mov     rax, rsp
0x1800996cb  mov     [rax+8], rbx
0x1800996cf  mov     [rax+10h], rsi
0x1800996d3  push    rdi
0x1800996d4  sub     rsp, 20h
0x1800996d8  mov     rdi, rdx
0x1800996db  mov     qword ptr [rax+20h], 0
0x1800996e3  mov     rdx, rcx; FileName
0x1800996e6  mov     rsi, r8
0x1800996e9  lea     rcx, [rax+20h]; Stream
0x1800996ed  lea     r8, aRb; "rb"
0x1800996f4  call    cs:__imp__wfopen_s
0x1800996fa  mov     r9, [rsp+28h+Stream]; Stream
0x1800996ff  test    r9, r9
0x180099702  jz      short loc_180099734
0x180099704  test    eax, eax
0x180099706  jnz     short loc_180099736
0x180099708  mov     r8, rdi; ElementCount
0x18009970b  lea     edx, [rax+1]; ElementSize
0x18009970e  mov     rcx, rsi; Buffer
0x180099711  xor     ebx, ebx
0x180099713  call    cs:__imp_fread
0x180099719  cmp     rax, rdi
0x18009971c  jz      short loc_180099725
0x18009971e  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180099723  mov     ebx, eax
0x180099725  mov     rcx, [rsp+28h+Stream]; Stream
0x18009972a  call    cs:__imp_fclose
0x180099730  mov     eax, ebx
0x180099732  jmp     short loc_180099740
0x180099734  test    eax, eax
0x180099736  jle     short loc_180099740
0x180099738  movzx   eax, ax
0x18009973b  or      eax, 80070000h
0x180099740  mov     rbx, [rsp+28h+arg_0]
0x180099745  mov     rsi, [rsp+28h+arg_8]
0x18009974a  add     rsp, 20h
0x18009974e  pop     rdi
0x18009974f  retn
```
