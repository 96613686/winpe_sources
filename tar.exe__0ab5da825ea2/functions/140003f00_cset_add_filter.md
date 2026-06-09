# _cset_add_filter

- ea: `0x140003f00`
- end: `0x140003f78`
- name: `_cset_add_filter`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001f9c`
- `0x140003f80`

## callees

- `0x140003f00`
- `0x1400071a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strdup` at `0x140003f31`
- `api-ms-win-crt-private-l1-1-0!_o__strdup` at `0x140003f31`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140003f20`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140003f20`

## pseudocode

```c
__int64 __fastcall cset_add_filter(__int64 a1, int a2, __int64 a3)
{
  __int64 v6; // rdi
  __int64 result; // rax
  __int64 v8; // rcx

  v6 = _o_realloc(*(_QWORD *)(a1 + 8), 16 * (*(int *)(a1 + 16) + 1LL));
  if ( !v6 || (result = _o__strdup(a3)) == 0 )
    lafe_errc(1, 0, (__int64)"No memory");
  v8 = 2LL * *(int *)(a1 + 16);
  *(_QWORD *)(a1 + 8) = v6;
  *(_DWORD *)(v6 + 8 * v8) = a2;
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL * (int)(*(_DWORD *)(a1 + 16))++ + 8) = result;
  return result;
}

```

## disassembly

```asm
0x140003f00  push    rbx
0x140003f02  push    rbp
0x140003f03  push    rsi
0x140003f04  push    rdi
0x140003f05  sub     rsp, 28h
0x140003f09  mov     ebp, edx
0x140003f0b  mov     rbx, rcx
0x140003f0e  movsxd  rdx, dword ptr [rcx+10h]
0x140003f12  mov     rsi, r8
0x140003f15  mov     rcx, [rcx+8]
0x140003f19  inc     rdx
0x140003f1c  shl     rdx, 4
0x140003f20  call    cs:__imp__o_realloc
0x140003f26  mov     rdi, rax
0x140003f29  test    rax, rax
0x140003f2c  jz      short loc_140003F66
0x140003f2e  mov     rcx, rsi
0x140003f31  call    cs:__imp__o__strdup
0x140003f37  test    rax, rax
0x140003f3a  jz      short loc_140003F66
0x140003f3c  movsxd  rcx, dword ptr [rbx+10h]
0x140003f40  add     rcx, rcx
0x140003f43  mov     [rbx+8], rdi
0x140003f47  mov     [rdi+rcx*8], ebp
0x140003f4a  movsxd  rdx, dword ptr [rbx+10h]
0x140003f4e  mov     rcx, [rbx+8]
0x140003f52  add     rdx, rdx
0x140003f55  mov     [rcx+rdx*8+8], rax
0x140003f5a  inc     dword ptr [rbx+10h]
0x140003f5d  add     rsp, 28h
0x140003f61  pop     rdi
0x140003f62  pop     rsi
0x140003f63  pop     rbp
0x140003f64  pop     rbx
0x140003f65  retn
0x140003f66  xor     edx, edx
0x140003f68  lea     r8, aNoMemory; "No memory"
0x140003f6f  lea     ecx, [rdx+1]; Code
0x140003f72  call    lafe_errc
```
