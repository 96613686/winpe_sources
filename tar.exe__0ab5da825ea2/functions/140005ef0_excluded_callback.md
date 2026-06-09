# excluded_callback

- ea: `0x140005ef0`
- end: `0x140005f53`
- name: `excluded_callback`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140005680`
- `0x140005ef0`

## import_xrefs

- `archiveint!archive_entry_pathname` at `0x140005f21`
- `archiveint!archive_entry_pathname` at `0x140005f21`
- `archiveint!archive_read_disk_descend` at `0x140005f3d`
- `archiveint!archive_read_disk_descend` at `0x140005f3d`
- `archiveint!archive_read_disk_can_descend` at `0x140005f0e`
- `archiveint!archive_read_disk_can_descend` at `0x140005f0e`

## pseudocode

```c
void __fastcall excluded_callback(__int64 a1, __int64 a2, __int64 a3)
{
  const char *v6; // rax

  if ( *(char *)(a2 + 36) >= 0 )
  {
    if ( (unsigned int)archive_read_disk_can_descend() )
    {
      if ( (*(_BYTE *)(a2 + 36) & 0x20) == 0
        || (v6 = (const char *)archive_entry_pathname(a3), (unsigned int)yes("add '%s'", v6)) )
      {
        archive_read_disk_descend(a1);
      }
    }
  }
}

```

## disassembly

```asm
0x140005ef0  mov     [rsp+arg_0], rbx
0x140005ef5  mov     [rsp+arg_8], rsi
0x140005efa  push    rdi
0x140005efb  sub     rsp, 20h
0x140005eff  test    byte ptr [rdx+24h], 80h
0x140005f03  mov     rsi, r8
0x140005f06  mov     rdi, rdx
0x140005f09  mov     rbx, rcx
0x140005f0c  jnz     short loc_140005F43
0x140005f0e  call    cs:__imp_archive_read_disk_can_descend
0x140005f14  test    eax, eax
0x140005f16  jz      short loc_140005F43
0x140005f18  test    byte ptr [rdi+24h], 20h
0x140005f1c  jz      short loc_140005F3A
0x140005f1e  mov     rcx, rsi
0x140005f21  call    cs:__imp_archive_entry_pathname
0x140005f27  mov     rdx, rax
0x140005f2a  lea     rcx, aAddS; "add '%s'"
0x140005f31  call    yes
0x140005f36  test    eax, eax
0x140005f38  jz      short loc_140005F43
0x140005f3a  mov     rcx, rbx
0x140005f3d  call    cs:__imp_archive_read_disk_descend
0x140005f43  mov     rbx, [rsp+28h+arg_0]
0x140005f48  mov     rsi, [rsp+28h+arg_8]
0x140005f4d  add     rsp, 20h
0x140005f51  pop     rdi
0x140005f52  retn
```
