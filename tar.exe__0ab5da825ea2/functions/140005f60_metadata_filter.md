# metadata_filter

- ea: `0x140005f60`
- end: `0x140005fbe`
- name: `metadata_filter`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140005680`
- `0x140005f60`

## import_xrefs

- `archiveint!archive_entry_pathname` at `0x140005f79`
- `archiveint!archive_entry_pathname` at `0x140005f79`
- `archiveint!archive_read_disk_descend` at `0x140005fa8`
- `archiveint!archive_read_disk_descend` at `0x140005fa8`
- `archiveint!archive_read_disk_can_descend` at `0x140005f9b`
- `archiveint!archive_read_disk_can_descend` at `0x140005f9b`

## pseudocode

```c
__int64 __fastcall metadata_filter(__int64 a1, __int64 a2, __int64 a3)
{
  const char *v5; // rax
  __int64 result; // rax

  if ( (*(_BYTE *)(a2 + 36) & 0x20) == 0
    || (v5 = (const char *)archive_entry_pathname(a3), result = yes("add '%s'", v5), (_DWORD)result) )
  {
    if ( *(char *)(a2 + 36) >= 0 )
    {
      if ( (unsigned int)archive_read_disk_can_descend(a1) )
        archive_read_disk_descend(a1);
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x140005f60  mov     [rsp+arg_0], rbx
0x140005f65  push    rdi
0x140005f66  sub     rsp, 20h
0x140005f6a  test    byte ptr [rdx+24h], 20h
0x140005f6e  mov     rdi, rdx
0x140005f71  mov     rbx, rcx
0x140005f74  jz      short loc_140005F92
0x140005f76  mov     rcx, r8
0x140005f79  call    cs:__imp_archive_entry_pathname
0x140005f7f  mov     rdx, rax
0x140005f82  lea     rcx, aAddS; "add '%s'"
0x140005f89  call    yes
0x140005f8e  test    eax, eax
0x140005f90  jz      short loc_140005FB3
0x140005f92  test    byte ptr [rdi+24h], 80h
0x140005f96  jnz     short loc_140005FAE
0x140005f98  mov     rcx, rbx
0x140005f9b  call    cs:__imp_archive_read_disk_can_descend
0x140005fa1  test    eax, eax
0x140005fa3  jz      short loc_140005FAE
0x140005fa5  mov     rcx, rbx
0x140005fa8  call    cs:__imp_archive_read_disk_descend
0x140005fae  mov     eax, 1
0x140005fb3  mov     rbx, [rsp+28h+arg_0]
0x140005fb8  add     rsp, 20h
0x140005fbc  pop     rdi
0x140005fbd  retn
```
