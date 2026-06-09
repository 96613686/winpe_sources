# set_writer_options

- ea: `0x1400060d4`
- end: `0x1400061d4`
- name: `set_writer_options`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400061dc`
- `0x1400063bc`
- `0x140006650`

## callees

- `0x1400060d4`
- `0x1400071a4`
- `0x1400076d1`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006181`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006181`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140006151`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140006151`
- `api-ms-win-crt-private-l1-1-0!_o_getenv` at `0x1400060ec`
- `api-ms-win-crt-private-l1-1-0!_o_getenv` at `0x1400060ec`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000610f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000610f`
- `archiveint!archive_clear_error` at `0x14000615f`
- `archiveint!archive_clear_error` at `0x14000615f`
- `archiveint!archive_write_set_options` at `0x140006146`
- `archiveint!archive_write_set_options` at `0x14000616c`
- `archiveint!archive_write_set_options` at `0x140006146`
- `archiveint!archive_write_set_options` at `0x14000616c`
- `archiveint!archive_error_string` at `0x14000619b`
- `archiveint!archive_error_string` at `0x1400061b9`
- `archiveint!archive_error_string` at `0x14000619b`
- `archiveint!archive_error_string` at `0x1400061b9`

## string_xrefs

- `0x1400060e5`: `TAR_WRITER_OPTIONS`

## pseudocode

```c
__int64 __fastcall set_writer_options(__int64 a1, __int64 a2)
{
  char *v4; // rax
  char *v5; // rbx
  __int64 v6; // rdx
  size_t v7; // rbp
  void *v8; // rax
  void *v9; // rsi
  int v10; // ebx
  __int64 result; // rax

  v4 = getenv("TAR_WRITER_OPTIONS");
  v5 = v4;
  if ( v4 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v4[v6] );
    v7 = v6 + 1;
    v8 = malloc(v6 + 30);
    v9 = v8;
    if ( !v8 )
    {
      _o__errno();
      lafe_errc(1);
    }
    qmemcpy(v8, "__ignore_wrong_module_name__,", 29);
    memcpy_0(v8, v5, v7);
    v10 = archive_write_set_options(a2, v9);
    free(v9);
    if ( v10 < -20 )
    {
      archive_error_string(a2);
      lafe_errc(1);
    }
    archive_clear_error(a2);
  }
  result = archive_write_set_options(a2, *(_QWORD *)(a1 + 96));
  if ( (_DWORD)result )
  {
    archive_error_string(a2);
    lafe_errc(1);
  }
  return result;
}

```

## disassembly

```asm
0x1400060d4  push    rbx
0x1400060d6  push    rbp
0x1400060d7  push    rsi
0x1400060d8  push    rdi
0x1400060d9  push    r14
0x1400060db  sub     rsp, 20h
0x1400060df  mov     r14, rcx
0x1400060e2  mov     rdi, rdx
0x1400060e5  lea     rcx, aTarWriterOptio; "TAR_WRITER_OPTIONS"
0x1400060ec  call    cs:__imp_getenv
0x1400060f2  mov     rbx, rax
0x1400060f5  test    rax, rax
0x1400060f8  jz      short loc_140006165
0x1400060fa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400060fe  inc     rdx
0x140006101  cmp     byte ptr [rax+rdx], 0
0x140006105  jnz     short loc_1400060FE
0x140006107  lea     rbp, [rdx+1]
0x14000610b  lea     rcx, [rbp+1Dh]; Size
0x14000610f  call    cs:__imp_malloc
0x140006115  mov     rsi, rax
0x140006118  test    rax, rax
0x14000611b  jz      short loc_140006181
0x14000611d  movups  xmm0, xmmword ptr cs:aIgnoreWrongMod; "__ignore_wrong_module_name__,"
0x140006124  mov     r8, rbp; Size
0x140006127  mov     rdx, rbx; Src
0x14000612a  mov     rcx, rax; void *
0x14000612d  movups  xmmword ptr [rax], xmm0
0x140006130  movups  xmm1, xmmword ptr cs:aIgnoreWrongMod+0Dh; "g_module_name__,"
0x140006137  movups  xmmword ptr [rax+0Dh], xmm1
0x14000613b  call    memcpy_0
0x140006140  mov     rdx, rsi
0x140006143  mov     rcx, rdi
0x140006146  call    cs:__imp_archive_write_set_options
0x14000614c  mov     rcx, rsi; Block
0x14000614f  mov     ebx, eax
0x140006151  call    cs:__imp_free
0x140006157  mov     rcx, rdi
0x14000615a  cmp     ebx, 0FFFFFFECh
0x14000615d  jl      short loc_14000619B
0x14000615f  call    cs:__imp_archive_clear_error
0x140006165  mov     rdx, [r14+60h]
0x140006169  mov     rcx, rdi
0x14000616c  call    cs:__imp_archive_write_set_options
0x140006172  test    eax, eax
0x140006174  jnz     short loc_1400061B6
0x140006176  add     rsp, 20h
0x14000617a  pop     r14
0x14000617c  pop     rdi
0x14000617d  pop     rsi
0x14000617e  pop     rbp
0x14000617f  pop     rbx
0x140006180  retn
0x140006181  call    cs:__imp__o__errno
0x140006187  lea     r8, aOutOfMemory; "Out of memory"
0x14000618e  mov     ecx, 1; Code
0x140006193  mov     edx, [rax]
0x140006195  call    lafe_errc
0x14000619b  call    cs:__imp_archive_error_string
0x1400061a1  xor     edx, edx
0x1400061a3  lea     r8, aS_5; "%s"
0x1400061aa  mov     r9, rax
0x1400061ad  lea     ecx, [rdx+1]; Code
0x1400061b0  call    lafe_errc
0x1400061b6  mov     rcx, rdi
0x1400061b9  call    cs:__imp_archive_error_string
0x1400061bf  xor     edx, edx
0x1400061c1  lea     r8, aS_5; "%s"
0x1400061c8  mov     r9, rax
0x1400061cb  lea     ecx, [rdx+1]; Code
0x1400061ce  call    lafe_errc
```
