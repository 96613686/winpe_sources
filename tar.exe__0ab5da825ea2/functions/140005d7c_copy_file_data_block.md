# copy_file_data_block

- ea: `0x140005d7c`
- end: `0x140005edc`
- name: `copy_file_data_block`
- size: `352`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000583c`
- `0x140006db0`

## callees

- `0x140001cb6`
- `0x140005d7c`
- `0x140007298`

## import_xrefs

- `archiveint!archive_errno` at `0x140005e77`
- `archiveint!archive_errno` at `0x140005e77`
- `archiveint!archive_entry_pathname` at `0x140005e93`
- `archiveint!archive_entry_pathname` at `0x140005e93`
- `archiveint!archive_write_data` at `0x140005e00`
- `archiveint!archive_write_data` at `0x140005e2e`
- `archiveint!archive_write_data` at `0x140005e00`
- `archiveint!archive_write_data` at `0x140005e2e`
- `archiveint!archive_read_data_block` at `0x140005e55`
- `archiveint!archive_read_data_block` at `0x140005e55`
- `archiveint!archive_error_string` at `0x140005e6b`
- `archiveint!archive_error_string` at `0x140005ec0`
- `archiveint!archive_error_string` at `0x140005e6b`
- `archiveint!archive_error_string` at `0x140005ec0`

## string_xrefs

- `0x140005e99`: `%s: Truncated write; file may have grown while being archived.`

## pseudocode

```c
__int64 __fastcall copy_file_data_block(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rsi
  void *v6; // r15
  __int64 v7; // r14
  __int64 v10; // rbx
  unsigned __int64 v11; // r14
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // eax
  const char *v15; // rbx
  unsigned int v16; // eax
  const char *v17; // rax
  const char *v19; // rax
  unsigned __int64 v20; // [rsp+20h] [rbp-28h] BYREF
  __int64 v21; // [rsp+28h] [rbp-20h] BYREF
  _QWORD v22[3]; // [rsp+30h] [rbp-18h] BYREF

  v20 = 0;
  v5 = 0;
  v21 = 0;
  v6 = 0;
  v22[0] = 0;
  v7 = a3;
  while ( 1 )
  {
    v14 = archive_read_data_block(v7, v22, &v20, &v21);
    if ( v14 )
      break;
    if ( v21 > v5 )
    {
      v10 = v21 - v5;
      if ( !v6 )
      {
        v6 = *(void **)(a1 + 232);
        memset_0(v6, 0, *(_QWORD *)(a1 + 240));
      }
      if ( v10 > 0 )
      {
        while ( 1 )
        {
          v11 = v10;
          if ( v10 > *(_QWORD *)(a1 + 240) )
            v11 = *(_QWORD *)(a1 + 240);
          v12 = archive_write_data(a2, v6, v11);
          if ( v12 < 0 )
            break;
          if ( v12 < v11 )
            goto LABEL_18;
          v5 += v12;
          v10 -= v12;
          if ( v10 <= 0 )
          {
            v7 = a3;
            goto LABEL_12;
          }
        }
LABEL_20:
        v19 = (const char *)archive_error_string(a2);
        lafe_warnc(0, "%s", v19);
        return 0xFFFFFFFFLL;
      }
    }
LABEL_12:
    v13 = archive_write_data(a2, v22[0], v20);
    if ( v13 < 0 )
      goto LABEL_20;
    if ( v13 < v20 )
    {
LABEL_18:
      v17 = (const char *)archive_entry_pathname(a4);
      lafe_warnc(0, "%s: Truncated write; file may have grown while being archived.", v17);
      return 0;
    }
    v5 += v13;
  }
  if ( v14 >= -20 )
    return 0;
  v15 = (const char *)archive_error_string(a2);
  v16 = archive_errno(a2);
  lafe_warnc(v16, "%s", v15);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x140005d7c  mov     [rsp-40h+arg_10], r8
0x140005d81  push    rbp
0x140005d82  push    rbx
0x140005d83  push    rsi
0x140005d84  push    rdi
0x140005d85  push    r12
0x140005d87  push    r13
0x140005d89  push    r14
0x140005d8b  push    r15
0x140005d8d  mov     rbp, rsp
0x140005d90  sub     rsp, 48h
0x140005d94  xor     ebx, ebx
0x140005d96  mov     r12, r9
0x140005d99  mov     [rbp+var_28], rbx
0x140005d9d  mov     esi, ebx
0x140005d9f  mov     [rbp+var_20], rbx
0x140005da3  mov     r15d, ebx
0x140005da6  mov     [rbp+var_18], rbx
0x140005daa  mov     r14, r8
0x140005dad  mov     rdi, rdx
0x140005db0  mov     r13, rcx
0x140005db3  jmp     loc_140005E46
0x140005db8  mov     rbx, [rbp+var_20]
0x140005dbc  cmp     rbx, rsi
0x140005dbf  jle     short loc_140005E23
0x140005dc1  sub     rbx, rsi
0x140005dc4  test    r15, r15
0x140005dc7  jnz     short loc_140005DE1
0x140005dc9  mov     r15, [r13+0E8h]
0x140005dd0  xor     edx, edx; Val
0x140005dd2  mov     r8, [r13+0F0h]; Size
0x140005dd9  mov     rcx, r15; void *
0x140005ddc  call    memset_0
0x140005de1  test    rbx, rbx
0x140005de4  jle     short loc_140005E23
0x140005de6  mov     rax, [r13+0F0h]
0x140005ded  mov     r14, rbx
0x140005df0  cmp     rbx, rax
0x140005df3  mov     rdx, r15
0x140005df6  mov     rcx, rdi
0x140005df9  cmovg   r14, rax
0x140005dfd  mov     r8, r14
0x140005e00  call    cs:__imp_archive_write_data
0x140005e06  test    rax, rax
0x140005e09  js      loc_140005EBD
0x140005e0f  cmp     rax, r14
0x140005e12  jb      short loc_140005E90
0x140005e14  add     rsi, rax
0x140005e17  sub     rbx, rax
0x140005e1a  test    rbx, rbx
0x140005e1d  jg      short loc_140005DE6
0x140005e1f  mov     r14, [rbp+arg_10]
0x140005e23  mov     r8, [rbp+var_28]
0x140005e27  mov     rcx, rdi
0x140005e2a  mov     rdx, [rbp+var_18]
0x140005e2e  call    cs:__imp_archive_write_data
0x140005e34  test    rax, rax
0x140005e37  js      loc_140005EBD
0x140005e3d  cmp     rax, [rbp+var_28]
0x140005e41  jb      short loc_140005E90
0x140005e43  add     rsi, rax
0x140005e46  lea     r9, [rbp+var_20]
0x140005e4a  mov     rcx, r14
0x140005e4d  lea     r8, [rbp+var_28]
0x140005e51  lea     rdx, [rbp+var_18]
0x140005e55  call    cs:__imp_archive_read_data_block
0x140005e5b  test    eax, eax
0x140005e5d  jz      loc_140005DB8
0x140005e63  cmp     eax, 0FFFFFFECh
0x140005e66  jge     short loc_140005EAA
0x140005e68  mov     rcx, rdi
0x140005e6b  call    cs:__imp_archive_error_string
0x140005e71  mov     rcx, rdi
0x140005e74  mov     rbx, rax
0x140005e77  call    cs:__imp_archive_errno
0x140005e7d  mov     r8, rbx
0x140005e80  lea     rdx, aS_5; "%s"
0x140005e87  mov     ecx, eax
0x140005e89  call    lafe_warnc
0x140005e8e  jmp     short loc_140005ED7
0x140005e90  mov     rcx, r12
0x140005e93  call    cs:__imp_archive_entry_pathname
0x140005e99  lea     rdx, aSTruncatedWrit; "%s: Truncated write; file may have grow"...
0x140005ea0  xor     ecx, ecx
0x140005ea2  mov     r8, rax
0x140005ea5  call    lafe_warnc
0x140005eaa  xor     eax, eax
0x140005eac  add     rsp, 48h
0x140005eb0  pop     r15
0x140005eb2  pop     r14
0x140005eb4  pop     r13
0x140005eb6  pop     r12
0x140005eb8  pop     rdi
0x140005eb9  pop     rsi
0x140005eba  pop     rbx
0x140005ebb  pop     rbp
0x140005ebc  retn
0x140005ebd  mov     rcx, rdi
0x140005ec0  call    cs:__imp_archive_error_string
0x140005ec6  lea     rdx, aS_5; "%s"
0x140005ecd  xor     ecx, ecx
0x140005ecf  mov     r8, rax
0x140005ed2  call    lafe_warnc
0x140005ed7  or      eax, 0FFFFFFFFh
0x140005eda  jmp     short loc_140005EAC
```
