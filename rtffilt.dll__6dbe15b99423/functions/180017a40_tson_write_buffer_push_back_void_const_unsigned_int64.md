# tson::write_buffer::push_back(void const *,unsigned __int64)

- ea: `0x180017a40`
- end: `0x180017ae8`
- name: `?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z`
- size: `168`
- prototype: `bool(tson::write_buffer *__hidden this, const void *, unsigned __int64)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ecd0`
- `0x18000ef64`
- `0x180016768`
- `0x180017d40`
- `0x180018360`
- `0x180018f64`
- `0x180019178`

## callees

- `0x180002846`
- `0x1800028b4`
- `0x180017a40`
- `0x180017c40`
- `0x1800198b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017a82`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017ac5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017a82`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017ac5`

## pseudocode

```c
bool __fastcall tson::write_buffer::push_back(tson::write_buffer *this, const void *a2, size_t a3)
{
  bool result; // al
  void *v7; // rcx
  size_t v8; // rsi

  if ( *((_QWORD *)this + 260) - *((_QWORD *)this + 259) >= a3 || (result = tson::write_buffer::reserve(this, a3)) )
  {
    if ( a3 )
    {
      v7 = (void *)*((_QWORD *)this + 259);
      if ( !v7 )
      {
LABEL_5:
        *(_DWORD *)_o__errno(v7, a2, a3) = 22;
LABEL_12:
        invalid_parameter_noinfo();
        goto LABEL_13;
      }
      v8 = *((_QWORD *)this + 260) - (_QWORD)v7;
      if ( a2 && v8 >= a3 )
      {
        memcpy_0(v7, a2, a3);
      }
      else
      {
        memset_0(v7, 0, *((_QWORD *)this + 260) - (_QWORD)v7);
        if ( !a2 )
          goto LABEL_5;
        if ( v8 < a3 )
        {
          *(_DWORD *)_o__errno(v7, a2, a3) = 34;
          goto LABEL_12;
        }
      }
    }
LABEL_13:
    *((_QWORD *)this + 259) += a3;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180017a40  push    rbx
0x180017a42  push    rbp
0x180017a43  push    rsi
0x180017a44  push    rdi
0x180017a45  sub     rsp, 28h
0x180017a49  mov     rax, [rcx+820h]
0x180017a50  mov     rbx, r8
0x180017a53  sub     rax, [rcx+818h]
0x180017a5a  mov     rbp, rdx
0x180017a5d  mov     rdi, rcx
0x180017a60  cmp     rax, r8
0x180017a63  jnb     short loc_180017A71
0x180017a65  mov     rdx, rbx; unsigned __int64
0x180017a68  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180017a6d  test    al, al
0x180017a6f  jz      short loc_180017ADF
0x180017a71  test    rbx, rbx
0x180017a74  jz      short loc_180017AD6
0x180017a76  mov     rcx, [rdi+818h]; void *
0x180017a7d  test    rcx, rcx
0x180017a80  jnz     short loc_180017A90
0x180017a82  call    cs:__imp__o__errno
0x180017a88  mov     dword ptr [rax], 16h
0x180017a8e  jmp     short loc_180017AD1
0x180017a90  mov     rsi, [rdi+820h]
0x180017a97  sub     rsi, rcx
0x180017a9a  test    rbp, rbp
0x180017a9d  jz      short loc_180017AB1
0x180017a9f  cmp     rsi, rbx
0x180017aa2  jb      short loc_180017AB1
0x180017aa4  mov     r8, rbx; Size
0x180017aa7  mov     rdx, rbp; Src
0x180017aaa  call    memcpy_0
0x180017aaf  jmp     short loc_180017AD6
0x180017ab1  mov     r8, rsi; Size
0x180017ab4  xor     edx, edx; Val
0x180017ab6  call    memset_0
0x180017abb  test    rbp, rbp
0x180017abe  jz      short loc_180017A82
0x180017ac0  cmp     rsi, rbx
0x180017ac3  jnb     short loc_180017AD6
0x180017ac5  call    cs:__imp__o__errno
0x180017acb  mov     dword ptr [rax], 22h ; '"'
0x180017ad1  call    _invalid_parameter_noinfo
0x180017ad6  add     [rdi+818h], rbx
0x180017add  mov     al, 1
0x180017adf  add     rsp, 28h
0x180017ae3  pop     rdi
0x180017ae4  pop     rsi
0x180017ae5  pop     rbp
0x180017ae6  pop     rbx
0x180017ae7  retn
```
