# write_hierarchy

- ea: `0x140006ea4`
- end: `0x14000719b`
- name: `write_hierarchy`
- size: `759`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140005bbc`
- `0x1400069a8`

## callees

- `0x140001b96`
- `0x140001d10`
- `0x140004bd4`
- `0x140004d0c`
- `0x1400050fc`
- `0x140006db0`
- `0x140006ea4`
- `0x140007298`

## import_xrefs

- `archiveint!archive_entry_set_uname` at `0x140006fa0`
- `archiveint!archive_entry_set_uname` at `0x140006fec`
- `archiveint!archive_entry_set_uname` at `0x140006fa0`
- `archiveint!archive_entry_set_uname` at `0x140006fec`
- `archiveint!archive_entry_set_gid` at `0x140006fb4`
- `archiveint!archive_entry_set_gid` at `0x140006fb4`
- `archiveint!archive_errno` at `0x140006ef3`
- `archiveint!archive_errno` at `0x140006f3b`
- `archiveint!archive_errno` at `0x140006ef3`
- `archiveint!archive_errno` at `0x140006f3b`
- `archiveint!archive_entry_set_uid` at `0x140006f7b`
- `archiveint!archive_entry_set_uid` at `0x140006f7b`
- `archiveint!archive_entry_set_gname` at `0x140006fd9`
- `archiveint!archive_entry_set_gname` at `0x140006fff`
- `archiveint!archive_entry_set_gname` at `0x140006fd9`
- `archiveint!archive_entry_set_gname` at `0x140006fff`
- `archiveint!archive_entry_pathname` at `0x14000708b`
- `archiveint!archive_entry_pathname` at `0x14000708b`
- `archiveint!archive_read_close` at `0x140007184`
- `archiveint!archive_read_close` at `0x140007184`
- `archiveint!archive_entry_mtime` at `0x140007025`
- `archiveint!archive_entry_mtime` at `0x140007025`
- `archiveint!archive_entry_filetype` at `0x1400070b4`
- `archiveint!archive_entry_filetype` at `0x1400070b4`
- `archiveint!archive_entry_set_mtime` at `0x140007041`
- `archiveint!archive_entry_set_mtime` at `0x140007041`
- `archiveint!archive_read_disk_gname` at `0x140006fcc`
- `archiveint!archive_read_disk_gname` at `0x140006fcc`
- `archiveint!archive_entry_free` at `0x140007107`
- `archiveint!archive_entry_free` at `0x140007144`
- `archiveint!archive_entry_free` at `0x14000717b`
- `archiveint!archive_entry_free` at `0x140007107`
- `archiveint!archive_entry_free` at `0x140007144`
- `archiveint!archive_entry_free` at `0x14000717b`
- `archiveint!archive_entry_linkify` at `0x1400070df`
- `archiveint!archive_entry_linkify` at `0x1400070df`
- `archiveint!archive_read_next_header2` at `0x14000715a`
- `archiveint!archive_read_next_header2` at `0x14000715a`
- `archiveint!archive_entry_set_size` at `0x1400070ca`
- `archiveint!archive_entry_set_size` at `0x1400070ca`
- `archiveint!archive_read_disk_open` at `0x140006eda`
- `archiveint!archive_read_disk_open` at `0x140006eda`
- `archiveint!archive_entry_new` at `0x14000714a`
- `archiveint!archive_entry_new` at `0x14000714a`
- `archiveint!archive_read_disk_uname` at `0x140006f93`
- `archiveint!archive_read_disk_uname` at `0x140006f93`
- `archiveint!archive_error_string` at `0x140006ee7`
- `archiveint!archive_error_string` at `0x140006f2f`
- `archiveint!archive_error_string` at `0x140006ee7`
- `archiveint!archive_error_string` at `0x140006f2f`

## pseudocode

```c
__int64 __fastcall write_hierarchy(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r14
  const char *v6; // rbx
  unsigned int v7; // eax
  __int64 result; // rax
  const char *v9; // rbx
  unsigned int v10; // eax
  __int64 disk_uname; // rax
  __int64 disk_gname; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 v16; // rax
  FILE *v17; // rax
  FILE *v18; // rax
  FILE *v19; // rax
  __int64 v20; // rcx
  FILE *v21; // rax
  int next_header2; // esi
  __int64 v23; // [rsp+50h] [rbp+30h] BYREF
  __int64 v24; // [rsp+68h] [rbp+48h] BYREF

  v3 = *(_QWORD *)(a1 + 200);
  v23 = 0;
  v24 = 0;
  if ( (unsigned int)archive_read_disk_open(v3, a3) )
  {
    v6 = (const char *)archive_error_string(v3);
    v7 = archive_errno(v3);
    result = lafe_warnc(v7, "%s", v6);
    *(_DWORD *)(a1 + 188) = 1;
  }
  else
  {
    *(_DWORD *)(a1 + 248) = -1;
LABEL_36:
    v20 = v23;
    while ( 1 )
    {
      archive_entry_free(v20);
      v23 = archive_entry_new();
      next_header2 = archive_read_next_header2(v3, v23);
      if ( next_header2 == 1 )
        break;
      if ( next_header2 )
      {
        v9 = (const char *)archive_error_string(v3);
        v10 = archive_errno(v3);
        lafe_warnc(v10, "%s", v9);
        if ( next_header2 == -30 || next_header2 == -25 )
        {
          *(_DWORD *)(a1 + 188) = 1;
          break;
        }
        if ( next_header2 < -20 )
          goto LABEL_36;
      }
      if ( *(int *)(a1 + 64) >= 0 )
      {
        archive_entry_set_uid(v23, *(int *)(a1 + 64));
        if ( !*(_QWORD *)(a1 + 72) )
        {
          disk_uname = archive_read_disk_uname(*(_QWORD *)(a1 + 200), *(int *)(a1 + 64));
          archive_entry_set_uname(v23, disk_uname);
        }
      }
      if ( *(int *)(a1 + 52) >= 0 )
      {
        archive_entry_set_gid(v23, *(int *)(a1 + 52));
        if ( !*(_QWORD *)(a1 + 56) )
        {
          disk_gname = archive_read_disk_gname(*(_QWORD *)(a1 + 200), *(int *)(a1 + 52));
          archive_entry_set_gname(v23, disk_gname);
        }
      }
      v13 = *(_QWORD *)(a1 + 72);
      if ( v13 )
        archive_entry_set_uname(v23, v13);
      v14 = *(_QWORD *)(a1 + 56);
      if ( v14 )
        archive_entry_set_gname(v23, v14);
      if ( (unsigned int)edit_pathname(a1, v23) )
        goto LABEL_36;
      if ( *(_BYTE *)(a1 + 105) )
      {
        v15 = v23;
        v16 = archive_entry_mtime(v23);
        if ( !*(_BYTE *)(a1 + 106) || v16 > *(_QWORD *)(a1 + 112) )
          archive_entry_set_mtime(v15, *(_QWORD *)(a1 + 112), 0);
      }
      if ( *(int *)(a1 + 32) <= 1 )
      {
        if ( *(int *)(a1 + 32) > 0 )
        {
          archive_entry_pathname(v23);
          v19 = o___acrt_iob_func_0(2u);
          safe_fprintf(v19, "a %s");
        }
      }
      else
      {
        v17 = o___acrt_iob_func_0(2u);
        safe_fprintf(v17, "a ");
        v18 = o___acrt_iob_func_0(2u);
        list_item_verbose(a1, v18, v23);
      }
      if ( (unsigned __int16)archive_entry_filetype(v23) != 0x8000 )
        archive_entry_set_size(v23, 0);
      archive_entry_linkify(*(_QWORD *)(a1 + 208), &v23, &v24);
      v20 = v23;
      while ( v20 )
      {
        write_file(a1, a2, v20);
        v20 = v24;
        if ( v23 != v24 )
        {
          archive_entry_free(v23);
          v20 = v24;
        }
        v23 = v20;
        v24 = 0;
      }
      if ( *(_DWORD *)(a1 + 32) )
      {
        v21 = o___acrt_iob_func_0(2u);
        fprintf(v21, "\n");
        goto LABEL_36;
      }
    }
    archive_entry_free(v23);
    return archive_read_close(v3);
  }
  return result;
}

```

## disassembly

```asm
0x140006ea4  mov     [rsp-28h+arg_8], rbx
0x140006ea9  push    rbp
0x140006eaa  push    rsi
0x140006eab  push    rdi
0x140006eac  push    r14
0x140006eae  push    r15
0x140006eb0  mov     rbp, rsp
0x140006eb3  sub     rsp, 20h
0x140006eb7  mov     r14, [rcx+0C8h]
0x140006ebe  mov     r15, rdx
0x140006ec1  mov     rdi, rcx
0x140006ec4  mov     [rbp+arg_0], 0
0x140006ecc  mov     rcx, r14
0x140006ecf  mov     [rbp+arg_18], 0
0x140006ed7  mov     rdx, r8
0x140006eda  call    cs:__imp_archive_read_disk_open
0x140006ee0  test    eax, eax
0x140006ee2  jz      short loc_140006F19
0x140006ee4  mov     rcx, r14
0x140006ee7  call    cs:__imp_archive_error_string
0x140006eed  mov     rcx, r14
0x140006ef0  mov     rbx, rax
0x140006ef3  call    cs:__imp_archive_errno
0x140006ef9  mov     r8, rbx
0x140006efc  lea     rdx, aS_5; "%s"
0x140006f03  mov     ecx, eax
0x140006f05  call    lafe_warnc
0x140006f0a  mov     dword ptr [rdi+0BCh], 1
0x140006f14  jmp     loc_14000718A
0x140006f19  mov     dword ptr [rdi+0F8h], 0FFFFFFFFh
0x140006f23  jmp     loc_140007140
0x140006f28  test    esi, esi
0x140006f2a  jz      short loc_140006F6D
0x140006f2c  mov     rcx, r14
0x140006f2f  call    cs:__imp_archive_error_string
0x140006f35  mov     rcx, r14
0x140006f38  mov     rbx, rax
0x140006f3b  call    cs:__imp_archive_errno
0x140006f41  mov     r8, rbx
0x140006f44  lea     rdx, aS_5; "%s"
0x140006f4b  mov     ecx, eax
0x140006f4d  call    lafe_warnc
0x140006f52  cmp     esi, 0FFFFFFE2h
0x140006f55  jz      loc_14000716D
0x140006f5b  cmp     esi, 0FFFFFFE7h
0x140006f5e  jz      loc_14000716D
0x140006f64  cmp     esi, 0FFFFFFECh
0x140006f67  jl      loc_140007140
0x140006f6d  cmp     dword ptr [rdi+40h], 0
0x140006f71  jl      short loc_140006FA6
0x140006f73  movsxd  rdx, dword ptr [rdi+40h]
0x140006f77  mov     rcx, [rbp+arg_0]
0x140006f7b  call    cs:__imp_archive_entry_set_uid
0x140006f81  cmp     qword ptr [rdi+48h], 0
0x140006f86  jnz     short loc_140006FA6
0x140006f88  movsxd  rdx, dword ptr [rdi+40h]
0x140006f8c  mov     rcx, [rdi+0C8h]
0x140006f93  call    cs:__imp_archive_read_disk_uname
0x140006f99  mov     rcx, [rbp+arg_0]
0x140006f9d  mov     rdx, rax
0x140006fa0  call    cs:__imp_archive_entry_set_uname
0x140006fa6  cmp     dword ptr [rdi+34h], 0
0x140006faa  jl      short loc_140006FDF
0x140006fac  movsxd  rdx, dword ptr [rdi+34h]
0x140006fb0  mov     rcx, [rbp+arg_0]
0x140006fb4  call    cs:__imp_archive_entry_set_gid
0x140006fba  cmp     qword ptr [rdi+38h], 0
0x140006fbf  jnz     short loc_140006FDF
0x140006fc1  movsxd  rdx, dword ptr [rdi+34h]
0x140006fc5  mov     rcx, [rdi+0C8h]
0x140006fcc  call    cs:__imp_archive_read_disk_gname
0x140006fd2  mov     rcx, [rbp+arg_0]
0x140006fd6  mov     rdx, rax
0x140006fd9  call    cs:__imp_archive_entry_set_gname
0x140006fdf  mov     rdx, [rdi+48h]
0x140006fe3  test    rdx, rdx
0x140006fe6  jz      short loc_140006FF2
0x140006fe8  mov     rcx, [rbp+arg_0]
0x140006fec  call    cs:__imp_archive_entry_set_uname
0x140006ff2  mov     rdx, [rdi+38h]
0x140006ff6  test    rdx, rdx
0x140006ff9  jz      short loc_140007005
0x140006ffb  mov     rcx, [rbp+arg_0]
0x140006fff  call    cs:__imp_archive_entry_set_gname
0x140007005  mov     rdx, [rbp+arg_0]
0x140007009  mov     rcx, rdi
0x14000700c  call    edit_pathname
0x140007011  test    eax, eax
0x140007013  jnz     loc_140007140
0x140007019  cmp     [rdi+69h], al
0x14000701c  jz      short loc_140007047
0x14000701e  mov     rbx, [rbp+arg_0]
0x140007022  mov     rcx, rbx
0x140007025  call    cs:__imp_archive_entry_mtime
0x14000702b  cmp     byte ptr [rdi+6Ah], 0
0x14000702f  jz      short loc_140007037
0x140007031  cmp     rax, [rdi+70h]
0x140007035  jle     short loc_140007047
0x140007037  mov     rdx, [rdi+70h]
0x14000703b  xor     r8d, r8d
0x14000703e  mov     rcx, rbx
0x140007041  call    cs:__imp_archive_entry_set_mtime
0x140007047  cmp     dword ptr [rdi+20h], 1
0x14000704b  jle     short loc_140007081
0x14000704d  mov     ecx, 2; Ix
0x140007052  call    _o___acrt_iob_func_0
0x140007057  mov     rcx, rax; Stream
0x14000705a  lea     rdx, aA_0; "a "
0x140007061  call    safe_fprintf
0x140007066  mov     ecx, 2; Ix
0x14000706b  call    _o___acrt_iob_func_0
0x140007070  mov     r8, [rbp+arg_0]
0x140007074  mov     rdx, rax
0x140007077  mov     rcx, rdi
0x14000707a  call    list_item_verbose
0x14000707f  jmp     short loc_1400070B0
0x140007081  cmp     dword ptr [rdi+20h], 0
0x140007085  jle     short loc_1400070B0
0x140007087  mov     rcx, [rbp+arg_0]
0x14000708b  call    cs:__imp_archive_entry_pathname
0x140007091  mov     ecx, 2; Ix
0x140007096  mov     rbx, rax
0x140007099  call    _o___acrt_iob_func_0
0x14000709e  mov     rcx, rax; Stream
0x1400070a1  lea     rdx, aAS; "a %s"
0x1400070a8  mov     r8, rbx
0x1400070ab  call    safe_fprintf
0x1400070b0  mov     rcx, [rbp+arg_0]
0x1400070b4  call    cs:__imp_archive_entry_filetype
0x1400070ba  mov     ecx, 8000h
0x1400070bf  cmp     ax, cx
0x1400070c2  jz      short loc_1400070D0
0x1400070c4  mov     rcx, [rbp+arg_0]
0x1400070c8  xor     edx, edx
0x1400070ca  call    cs:__imp_archive_entry_set_size
0x1400070d0  mov     rcx, [rdi+0D0h]
0x1400070d7  lea     r8, [rbp+arg_18]
0x1400070db  lea     rdx, [rbp+arg_0]
0x1400070df  call    cs:__imp_archive_entry_linkify
0x1400070e5  mov     rcx, [rbp+arg_0]
0x1400070e9  jmp     short loc_14000711D
0x1400070eb  mov     r8, rcx
0x1400070ee  mov     rdx, r15
0x1400070f1  mov     rcx, rdi
0x1400070f4  call    write_file
0x1400070f9  mov     rcx, [rbp+arg_18]
0x1400070fd  cmp     [rbp+arg_0], rcx
0x140007101  jz      short loc_140007111
0x140007103  mov     rcx, [rbp+arg_0]
0x140007107  call    cs:__imp_archive_entry_free
0x14000710d  mov     rcx, [rbp+arg_18]
0x140007111  mov     [rbp+arg_0], rcx
0x140007115  mov     [rbp+arg_18], 0
0x14000711d  test    rcx, rcx
0x140007120  jnz     short loc_1400070EB
0x140007122  cmp     [rdi+20h], ecx
0x140007125  jz      short loc_140007144
0x140007127  mov     ecx, 2; Ix
0x14000712c  call    _o___acrt_iob_func_0
0x140007131  mov     rcx, rax; Stream
0x140007134  lea     rdx, asc_14000B8DC; "\n"
0x14000713b  call    fprintf
0x140007140  mov     rcx, [rbp+arg_0]
0x140007144  call    cs:__imp_archive_entry_free
0x14000714a  call    cs:__imp_archive_entry_new
0x140007150  mov     rdx, rax
0x140007153  mov     [rbp+arg_0], rax
0x140007157  mov     rcx, r14
0x14000715a  call    cs:__imp_archive_read_next_header2
0x140007160  mov     esi, eax
0x140007162  cmp     eax, 1
0x140007165  jnz     loc_140006F28
0x14000716b  jmp     short loc_140007177
0x14000716d  mov     dword ptr [rdi+0BCh], 1
0x140007177  mov     rcx, [rbp+arg_0]
0x14000717b  call    cs:__imp_archive_entry_free
0x140007181  mov     rcx, r14
0x140007184  call    cs:__imp_archive_read_close
0x14000718a  mov     rbx, [rsp+20h+arg_8]
0x14000718f  add     rsp, 20h
0x140007193  pop     r15
0x140007195  pop     r14
0x140007197  pop     rdi
0x140007198  pop     rsi
0x140007199  pop     rbp
0x14000719a  retn
```
