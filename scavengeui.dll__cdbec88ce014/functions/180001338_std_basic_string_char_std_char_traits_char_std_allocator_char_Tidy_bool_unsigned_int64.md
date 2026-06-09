# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Tidy(bool,unsigned __int64)

- ea: `0x180001338`
- end: `0x180001390`
- name: `?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z`
- size: `88`
- prototype: `void __fastcall(void **, char, size_t)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003c64`

## callees

- `0x180001338`
- `0x180001e86`
- `0x180002026`

## pseudocode

```c
void __fastcall std::string::_Tidy(void **a1, char a2, size_t a3)
{
  void *v5; // rsi

  if ( a2 && (unsigned __int64)a1[3] >= 0x10 )
  {
    v5 = *a1;
    if ( a3 )
      memcpy_0(a1, *a1, a3);
    operator delete(v5);
  }
  a1[3] = (void *)15;
  a1[2] = (void *)a3;
  *((_BYTE *)a1 + a3) = 0;
}

```

## disassembly

```asm
0x180001338  mov     [rsp+arg_0], rbx
0x18000133d  mov     [rsp+arg_8], rsi
0x180001342  push    rdi
0x180001343  sub     rsp, 20h
0x180001347  mov     rdi, r8
0x18000134a  mov     rbx, rcx
0x18000134d  test    dl, dl
0x18000134f  jz      short loc_180001370
0x180001351  cmp     qword ptr [rcx+18h], 10h
0x180001356  jb      short loc_180001370
0x180001358  mov     rsi, [rcx]
0x18000135b  test    r8, r8
0x18000135e  jz      short loc_180001368
0x180001360  mov     rdx, rsi; Src
0x180001363  call    memcpy_0
0x180001368  mov     rcx, rsi; void *
0x18000136b  call    ??3@YAXPEAX@Z_0
0x180001370  mov     rsi, [rsp+28h+arg_8]
0x180001375  mov     qword ptr [rbx+18h], 0Fh
0x18000137d  mov     [rbx+10h], rdi
0x180001381  mov     byte ptr [rdi+rbx], 0
0x180001385  mov     rbx, [rsp+28h+arg_0]
0x18000138a  add     rsp, 20h
0x18000138e  pop     rdi
0x18000138f  retn
```
