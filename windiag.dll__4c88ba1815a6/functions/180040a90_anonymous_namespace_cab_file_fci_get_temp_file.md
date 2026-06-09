# _anonymous_namespace_::cab_file::fci_get_temp_file

- ea: `0x180040a90`
- end: `0x180040b46`
- name: `_anonymous_namespace_::cab_file::fci_get_temp_file`
- size: `182`
- prototype: `BOOL __cdecl(char *pszTempName, int cbTempName, void *pv)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180040a90`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!_tempnam` at `0x180040ab5`
- `api-ms-win-crt-stdio-l1-1-0!_tempnam` at `0x180040ab5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040b29`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180040b29`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::cab_file::fci_get_temp_file(char *pszTempName, int cbTempName, void *pv)
{
  unsigned __int64 v3; // rsi
  unsigned int v5; // ebx
  char *v6; // r9
  unsigned __int64 v7; // r8
  signed int v8; // ebx
  __int64 v9; // rax
  char *v10; // rcx
  char *v11; // rax

  v3 = cbTempName;
  v5 = 0;
  v6 = _tempnam(DirectoryName, "windiag.fci");
  if ( v6 )
  {
    v7 = v3;
    if ( (_DWORD)v3 )
    {
      if ( v3 <= 0x7FFFFFFF )
      {
        v9 = 2147483646;
        v10 = v6;
        do
        {
          if ( !v9 )
            break;
          if ( !*v10 )
            break;
          *pszTempName++ = *v10++;
          --v9;
          --v7;
        }
        while ( v7 );
        v11 = pszTempName - 1;
        if ( v7 )
          v11 = pszTempName;
        *v11 = 0;
        v8 = v7 == 0 ? 0x8007007A : 0;
      }
      else
      {
        v8 = -2147024809;
        *pszTempName = 0;
      }
    }
    else
    {
      v8 = -2147024809;
    }
    free(v6);
    return v8 >= 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180040a90  mov     [rsp+arg_0], rbx
0x180040a95  mov     [rsp+arg_8], rsi
0x180040a9a  push    rdi
0x180040a9b  sub     rsp, 20h
0x180040a9f  movsxd  rsi, edx
0x180040aa2  mov     rdi, rcx
0x180040aa5  lea     rdx, FilePrefix; "windiag.fci"
0x180040aac  xor     ebx, ebx
0x180040aae  lea     rcx, DirectoryName; DirectoryName
0x180040ab5  call    cs:__imp__tempnam
0x180040abb  mov     r9, rax
0x180040abe  test    rax, rax
0x180040ac1  jz      short loc_180040B34
0x180040ac3  mov     r8, rsi
0x180040ac6  test    esi, esi
0x180040ac8  jz      short loc_180040B1A
0x180040aca  cmp     rsi, 7FFFFFFFh
0x180040ad1  jbe     short loc_180040ADA
0x180040ad3  mov     ebx, 80070057h
0x180040ad8  jmp     short loc_180040B23
0x180040ada  mov     eax, 7FFFFFFEh
0x180040adf  mov     rcx, r9
0x180040ae2  test    rax, rax
0x180040ae5  jz      short loc_180040AFE
0x180040ae7  mov     dl, [rcx]
0x180040ae9  test    dl, dl
0x180040aeb  jz      short loc_180040AFE
0x180040aed  mov     [rdi], dl
0x180040aef  inc     rcx
0x180040af2  inc     rdi
0x180040af5  dec     rax
0x180040af8  sub     r8, 1
0x180040afc  jnz     short loc_180040AE2
0x180040afe  test    r8, r8
0x180040b01  lea     rax, [rdi-1]
0x180040b05  cmovnz  rax, rdi
0x180040b09  neg     r8
0x180040b0c  mov     [rax], bl
0x180040b0e  sbb     ebx, ebx
0x180040b10  not     ebx
0x180040b12  and     ebx, 8007007Ah
0x180040b18  jmp     short loc_180040B26
0x180040b1a  mov     ebx, 80070057h
0x180040b1f  test    esi, esi
0x180040b21  jz      short loc_180040B26
0x180040b23  mov     byte ptr [rdi], 0
0x180040b26  mov     rcx, r9; Block
0x180040b29  call    cs:__imp_free
0x180040b2f  not     ebx
0x180040b31  shr     ebx, 1Fh
0x180040b34  mov     rsi, [rsp+28h+arg_8]
0x180040b39  mov     eax, ebx
0x180040b3b  mov     rbx, [rsp+28h+arg_0]
0x180040b40  add     rsp, 20h
0x180040b44  pop     rdi
0x180040b45  retn
```
