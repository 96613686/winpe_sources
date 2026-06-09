# ParseSource

- ea: `0x18004f43c`
- end: `0x18004f5ce`
- name: `ParseSource`
- size: `402`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18004f8fc`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180029a50`
- `0x18002a340`
- `0x18004f43c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004f5b3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18006a274`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004f5b3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18006a274`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18004f514`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18004f514`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004f465`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004f53a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004f465`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004f53a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004f4d7`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004f4d7`

## string_xrefs

- `0x18004f4c7`: `Failed at StringCbCopyW to initialize an empty string.\n`
- `0x18004f58f`: `Failed at StringCbCopyNW to copy substring to the allocated memory.\n`

## pseudocode

```c
void __fastcall ParseSource(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rbx
  wchar_t *v6; // rax
  __int64 v7; // rbx
  unsigned __int64 v8; // rdi
  unsigned __int16 *v9; // rax

  *a2 = 0;
  if ( !a1 )
  {
    v4 = (unsigned __int16 *)malloc(2u);
    v5 = v4;
    if ( !v4 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(0) )
        FileLogAdd(L"Failed to allocate memory with one WCHAR.\n");
      goto LABEL_23;
    }
    if ( (int)StringCbCopyW(v4, 2u, &qword_180071478) < 0 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(0) )
        FileLogAdd(L"Failed at StringCbCopyW to initialize an empty string.\n");
      goto LABEL_23;
    }
LABEL_22:
    *a2 = v5;
    v5 = 0;
    goto LABEL_23;
  }
  v6 = wcsstr(a1, L"(");
  if ( v6 )
  {
    v7 = v6 - a1;
  }
  else
  {
    v7 = -1;
    do
      ++v7;
    while ( a1[v7] );
  }
  while ( 1 )
  {
    v8 = 2 * v7;
    if ( !v7 || !(unsigned int)_o_iswspace(a1[v8 / 2 - 1]) )
      break;
    --v7;
  }
  v9 = (unsigned __int16 *)malloc(v8 + 2);
  v5 = v9;
  if ( v9 )
  {
    if ( (int)StringCbCopyNW(v9, v8 + 2, a1, v8) >= 0 )
    {
      v5[v8 / 2] = 0;
      goto LABEL_22;
    }
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"Failed at StringCbCopyNW to copy substring to the allocated memory.\n");
  }
  else if ( (unsigned __int8)FileLogAllowEntry(0) )
  {
    FileLogAdd(L"Failed to allocate memory with size: %d char.\n", (unsigned int)(v8 + 2));
  }
LABEL_23:
  if ( v5 )
    free(v5);
}

```

## disassembly

```asm
0x18004f43c  push    rbx
0x18004f43e  push    rsi
0x18004f43f  push    rdi
0x18004f440  push    r12
0x18004f442  push    r14
0x18004f444  push    r15
0x18004f446  sub     rsp, 38h
0x18004f44a  mov     r15, rdx
0x18004f44d  mov     rsi, rcx
0x18004f450  xor     r12d, r12d
0x18004f453  mov     [rsp+68h+var_48], r12
0x18004f458  mov     [rdx], r12
0x18004f45b  test    rcx, rcx
0x18004f45e  jnz     short loc_18004F4D0
0x18004f460  lea     edi, [rcx+2]
0x18004f463  mov     ecx, edi; Size
0x18004f465  call    cs:__imp_malloc
0x18004f46c  nop     dword ptr [rax+rax+00h]
0x18004f471  mov     rbx, rax
0x18004f474  mov     [rsp+68h+var_48], rax
0x18004f479  test    rax, rax
0x18004f47c  jnz     short loc_18004F49E
0x18004f47e  xor     ecx, ecx
0x18004f480  call    FileLogAllowEntry
0x18004f485  test    al, al
0x18004f487  jz      loc_18004F5AB
0x18004f48d  lea     rcx, aFailedToAlloca_0; "Failed to allocate memory with one WCHA"...
0x18004f494  call    FileLogAdd
0x18004f499  jmp     loc_18004F5AB
0x18004f49e  lea     r8, qword_180071478; unsigned __int16 *
0x18004f4a5  mov     rdx, rdi; unsigned __int64
0x18004f4a8  mov     rcx, rax; unsigned __int16 *
0x18004f4ab  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18004f4b0  test    eax, eax
0x18004f4b2  jns     loc_18004F5A0
0x18004f4b8  xor     ecx, ecx
0x18004f4ba  call    FileLogAllowEntry
0x18004f4bf  test    al, al
0x18004f4c1  jz      loc_18004F5AB
0x18004f4c7  lea     rcx, aFailedAtString_2; "Failed at StringCbCopyW to initialize a"...
0x18004f4ce  jmp     short loc_18004F494
0x18004f4d0  lea     rdx, SubStr; "("
0x18004f4d7  call    cs:__imp_wcsstr
0x18004f4de  nop     dword ptr [rax+rax+00h]
0x18004f4e3  mov     rbx, rax
0x18004f4e6  test    rax, rax
0x18004f4e9  jz      short loc_18004F4F3
0x18004f4eb  sub     rbx, rsi
0x18004f4ee  sar     rbx, 1
0x18004f4f1  jmp     short loc_18004F501
0x18004f4f3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004f4f7  inc     rbx
0x18004f4fa  cmp     [rsi+rbx*2], r12w
0x18004f4ff  jnz     short loc_18004F4F7
0x18004f501  mov     [rsp+68h+var_40], rbx
0x18004f506  lea     rdi, [rbx+rbx]
0x18004f50a  test    rbx, rbx
0x18004f50d  jz      short loc_18004F52E
0x18004f50f  movzx   ecx, word ptr [rdi+rsi-2]
0x18004f514  call    cs:__imp__o_iswspace
0x18004f51b  nop     dword ptr [rax+rax+00h]
0x18004f520  test    eax, eax
0x18004f522  jz      short loc_18004F52E
0x18004f524  dec     rbx
0x18004f527  mov     [rsp+68h+var_40], rbx
0x18004f52c  jmp     short loc_18004F506
0x18004f52e  lea     r14, [rdi+2]
0x18004f532  mov     [rsp+68h+arg_8], r14
0x18004f537  mov     rcx, r14; Size
0x18004f53a  call    cs:__imp_malloc
0x18004f541  nop     dword ptr [rax+rax+00h]
0x18004f546  mov     rbx, rax
0x18004f549  mov     [rsp+68h+var_48], rax
0x18004f54e  test    rax, rax
0x18004f551  jnz     short loc_18004F56F
0x18004f553  xor     ecx, ecx
0x18004f555  call    FileLogAllowEntry
0x18004f55a  test    al, al
0x18004f55c  jz      short loc_18004F5AB
0x18004f55e  mov     edx, r14d
0x18004f561  lea     rcx, aFailedToAlloca; "Failed to allocate memory with size: %d"...
0x18004f568  call    FileLogAdd
0x18004f56d  jmp     short loc_18004F5AB
0x18004f56f  mov     r9, rdi; unsigned __int64
0x18004f572  mov     r8, rsi; unsigned __int16 *
0x18004f575  mov     rdx, r14; unsigned __int64
0x18004f578  mov     rcx, rbx; unsigned __int16 *
0x18004f57b  call    ?StringCbCopyNW@@YAJPEAG_KPEBG1@Z; StringCbCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18004f580  test    eax, eax
0x18004f582  jns     short loc_18004F59B
0x18004f584  xor     ecx, ecx
0x18004f586  call    FileLogAllowEntry
0x18004f58b  test    al, al
0x18004f58d  jz      short loc_18004F5AB
0x18004f58f  lea     rcx, aFailedAtString; "Failed at StringCbCopyNW to copy substr"...
0x18004f596  jmp     loc_18004F494
0x18004f59b  mov     [rdi+rbx], r12w
0x18004f5a0  mov     [r15], rbx
0x18004f5a3  mov     rbx, r12
0x18004f5a6  mov     [rsp+68h+var_48], rbx
0x18004f5ab  test    rbx, rbx
0x18004f5ae  jz      short loc_18004F5BF
0x18004f5b0  mov     rcx, rbx; Block
0x18004f5b3  call    cs:__imp_free
0x18004f5ba  nop     dword ptr [rax+rax+00h]
0x18004f5bf  add     rsp, 38h
0x18004f5c3  pop     r15
0x18004f5c5  pop     r14
0x18004f5c7  pop     r12
0x18004f5c9  pop     rdi
0x18004f5ca  pop     rsi
0x18004f5cb  pop     rbx
0x18004f5cc  retn
0x18006a262  push    rbp
0x18006a264  sub     rsp, 20h
0x18006a268  mov     rbp, rdx
0x18006a26b  mov     rcx, [rbp+20h]; Block
0x18006a26f  test    rcx, rcx
0x18006a272  jz      short loc_18006A281
0x18006a274  call    cs:__imp_free
0x18006a27b  nop     dword ptr [rax+rax+00h]
0x18006a280  nop
0x18006a281  add     rsp, 20h
0x18006a285  pop     rbp
0x18006a286  retn
```
