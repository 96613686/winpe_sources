# GetFullFileName

- ea: `0x3839fabe0`
- end: `0x3839fae01`
- name: `GetFullFileName`
- size: `545`
- prototype: `__int64 __fastcall(wchar_t *Path, LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x3839fae10`
- `0x3839fb130`

## callees

- `0x38391aed0`
- `0x3839fabe0`

## import_xrefs

- `MSVCR100!_wfullpath` at `0x3839fac4d`
- `MSVCR100!_wfullpath` at `0x3839fac4d`
- `KERNEL32!GetLastError` at `0x3839facf2`
- `KERNEL32!GetLastError` at `0x3839facf2`
- `KERNEL32!CreateFileW` at `0x3839face2`
- `KERNEL32!CreateFileW` at `0x3839face2`
- `KERNEL32!CloseHandle` at `0x3839fadee`
- `KERNEL32!CloseHandle` at `0x3839fadee`

## pseudocode

```c
__int64 __fastcall GetFullFileName(wchar_t *Path, WCHAR *lpFileName, DWORD a3)
{
  HANDLE FileW; // rax
  DWORD LastError; // eax

  if ( !*Path )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_383B49128[0] )
        bidTraceW(off_383B43328[0], 2895913, off_383B49128[0], 2147680508LL);
    }
    return 2147680508LL;
  }
  if ( _wfullpath(lpFileName, Path, 0x104u) )
  {
    if ( a3 == 0x80000000 )
      FileW = CreateFileW(lpFileName, a3, 1u, 0, 3u, 0x100080u, 0);
    else
      FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 4u, 0x100080u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( LastError == 123 )
      {
        if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
          return 2147680508LL;
        bidTraceW(off_383B43328[0], 2940969, off_383B49128[0], 2147680508LL);
        return 2147680508LL;
      }
      else if ( LastError == 3 )
      {
        if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
          bidTraceW(off_383B43328[0], 2945065, off_383B49128[0], 2147680259LL);
        return 2147680259LL;
      }
      else
      {
        if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
          bidTraceW(off_383B43328[0], 2949161, off_383B49128[0], 2147680258LL);
        return 2147680258LL;
      }
    }
    else
    {
      CloseHandle(FileW);
      return 0;
    }
  }
  else
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B43328[0], 2901033, off_383B49128[0], 2147500037LL);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x3839fabe0  mov     [rsp+arg_0], rbx
0x3839fabe5  push    rdi
0x3839fabe6  sub     rsp, 40h
0x3839fabea  cmp     word ptr [rcx], 0
0x3839fabee  mov     edi, r8d
0x3839fabf1  mov     rbx, rdx
0x3839fabf4  jnz     short loc_3839FAC41
0x3839fabf6  test    byte ptr cs:_bidGblFlags, 2
0x3839fabfd  jz      short loc_3839FAC31
0x3839fabff  mov     rcx, cs:off_383B43328; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fac06  mov     rdx, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fac0d  test    rdx, rdx
0x3839fac10  jz      short loc_3839FAC31
0x3839fac12  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fac19  mov     r9d, 800300FCh
0x3839fac1f  mov     edx, 2C3029h
0x3839fac24  mov     [rsp+48h+dwCreationDisposition], 0B0Ch
0x3839fac2c  call    _bidTraceW
0x3839fac31  mov     eax, 800300FCh
0x3839fac36  mov     rbx, [rsp+48h+arg_0]
0x3839fac3b  add     rsp, 40h
0x3839fac3f  pop     rdi
0x3839fac40  retn
0x3839fac41  mov     rdx, rcx; Path
0x3839fac44  mov     r8d, 104h; BufferCount
0x3839fac4a  mov     rcx, rbx; Buffer
0x3839fac4d  call    cs:__imp__wfullpath
0x3839fac53  test    rax, rax
0x3839fac56  jnz     short loc_3839FACA3
0x3839fac58  test    byte ptr cs:_bidGblFlags, 2
0x3839fac5f  jz      short loc_3839FAC93
0x3839fac61  mov     rcx, cs:off_383B43328; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fac68  mov     rdx, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fac6f  test    rdx, rdx
0x3839fac72  jz      short loc_3839FAC93
0x3839fac74  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fac7b  mov     r9d, 80004005h
0x3839fac81  mov     edx, 2C4429h
0x3839fac86  mov     [rsp+48h+dwCreationDisposition], 0B11h
0x3839fac8e  call    _bidTraceW
0x3839fac93  mov     eax, 80004005h
0x3839fac98  mov     rbx, [rsp+48h+arg_0]
0x3839fac9d  add     rsp, 40h
0x3839faca1  pop     rdi
0x3839faca2  retn
0x3839faca3  xor     r9d, r9d; lpSecurityAttributes
0x3839faca6  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x3839facaf  mov     rcx, rbx; lpFileName
0x3839facb2  mov     [rsp+48h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x3839facba  cmp     edi, 80000000h
0x3839facc0  jnz     short loc_3839FACD2
0x3839facc2  mov     [rsp+48h+dwCreationDisposition], 3
0x3839facca  mov     edx, edi
0x3839faccc  lea     r8d, [r9+1]
0x3839facd0  jmp     short loc_3839FACE2
0x3839facd2  mov     [rsp+48h+dwCreationDisposition], 4; dwCreationDisposition
0x3839facda  xor     r8d, r8d; dwShareMode
0x3839facdd  mov     edx, 0C0000000h; dwDesiredAccess
0x3839face2  call    cs:__imp_CreateFileW
0x3839face8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x3839facec  jnz     loc_3839FADEB
0x3839facf2  call    cs:__imp_GetLastError
0x3839facf8  cmp     eax, 7Bh ; '{'
0x3839facfb  jnz     short loc_3839FAD50
0x3839facfd  test    byte ptr cs:_bidGblFlags, 2
0x3839fad04  jz      loc_3839FAC31
0x3839fad0a  mov     rcx, cs:off_383B43328; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fad11  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fad18  test    rax, rax
0x3839fad1b  jz      loc_3839FAC31
0x3839fad21  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fad28  mov     r9d, 800300FCh
0x3839fad2e  mov     edx, 2CE029h
0x3839fad33  mov     [rsp+48h+dwCreationDisposition], 0B38h
0x3839fad3b  call    _bidTraceW
0x3839fad40  mov     eax, 800300FCh
0x3839fad45  mov     rbx, [rsp+48h+arg_0]
0x3839fad4a  add     rsp, 40h
0x3839fad4e  pop     rdi
0x3839fad4f  retn
0x3839fad50  cmp     eax, 3
0x3839fad53  jnz     short loc_3839FADA0
0x3839fad55  test    byte ptr cs:_bidGblFlags, 2
0x3839fad5c  jz      short loc_3839FAD90
0x3839fad5e  mov     rcx, cs:off_383B43328; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fad65  mov     rdx, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fad6c  test    rdx, rdx
0x3839fad6f  jz      short loc_3839FAD90
0x3839fad71  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fad78  mov     r9d, 80030003h
0x3839fad7e  mov     edx, 2CF029h
0x3839fad83  mov     [rsp+48h+dwCreationDisposition], 0B3Ch
0x3839fad8b  call    _bidTraceW
0x3839fad90  mov     eax, 80030003h
0x3839fad95  mov     rbx, [rsp+48h+arg_0]
0x3839fad9a  add     rsp, 40h
0x3839fad9e  pop     rdi
0x3839fad9f  retn
0x3839fada0  test    byte ptr cs:_bidGblFlags, 2
0x3839fada7  jz      short loc_3839FADDB
0x3839fada9  mov     rcx, cs:off_383B43328; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839fadb0  mov     rdx, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fadb7  test    rdx, rdx
0x3839fadba  jz      short loc_3839FADDB
0x3839fadbc  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839fadc3  mov     r9d, 80030002h
0x3839fadc9  mov     edx, 2D0029h
0x3839fadce  mov     [rsp+48h+dwCreationDisposition], 0B40h
0x3839fadd6  call    _bidTraceW
0x3839faddb  mov     eax, 80030002h
0x3839fade0  mov     rbx, [rsp+48h+arg_0]
0x3839fade5  add     rsp, 40h
0x3839fade9  pop     rdi
0x3839fadea  retn
0x3839fadeb  mov     rcx, rax; hObject
0x3839fadee  call    cs:__imp_CloseHandle
0x3839fadf4  mov     rbx, [rsp+48h+arg_0]
0x3839fadf9  xor     eax, eax
0x3839fadfb  add     rsp, 40h
0x3839fadff  pop     rdi
0x3839fae00  retn
```
