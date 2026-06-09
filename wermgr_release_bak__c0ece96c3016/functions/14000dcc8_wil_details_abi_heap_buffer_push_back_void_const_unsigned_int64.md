# wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)

- ea: `0x14000dcc8`
- end: `0x14000dd82`
- name: `?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z`
- size: `186`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140008fe8`
- `0x14000a768`
- `0x1400121e8`
- `0x140013f84`

## callees

- `0x140002f0e`
- `0x140002fbc`
- `0x14000dcc8`
- `0x14000e154`
- `0x14001c9a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000dd29`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000dd62`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000dd29`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000dd62`

## pseudocode

```c
bool __fastcall wil::details_abi::heap_buffer::push_back(
        wil::details_abi::heap_buffer *this,
        const void *Src,
        size_t Size)
{
  size_t v6; // rcx
  unsigned __int64 v7; // rdx
  bool result; // al
  void *v9; // rcx
  __int64 v10; // rax
  unsigned __int64 v11; // rsi

  v6 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( Size + *((_QWORD *)this + 1) - *(_QWORD *)this < v6 )
    goto LABEL_5;
  v7 = Size;
  if ( Size < 2 * v6 )
    v7 = 2 * v6;
  result = wil::details_abi::heap_buffer::reserve(this, v7);
  if ( result )
  {
LABEL_5:
    v9 = (void *)*((_QWORD *)this + 1);
    v10 = *((_QWORD *)this + 2) - (_QWORD)v9;
    v11 = v10 & -(__int64)((unsigned __int64)v9 < *((_QWORD *)this + 2));
    if ( Size )
    {
      if ( !v9 )
      {
LABEL_7:
        *(_DWORD *)_o__errno() = 22;
LABEL_14:
        invalid_parameter_noinfo();
        goto LABEL_15;
      }
      if ( Src && v11 >= Size )
      {
        memcpy_0(v9, Src, Size);
      }
      else
      {
        memset_0(v9, 0, v10 & -(__int64)((unsigned __int64)v9 < *((_QWORD *)this + 2)));
        if ( !Src )
          goto LABEL_7;
        if ( v11 < Size )
        {
          *(_DWORD *)_o__errno() = 34;
          goto LABEL_14;
        }
      }
    }
LABEL_15:
    *((_QWORD *)this + 1) += Size;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x14000dcc8  push    rbx
0x14000dcca  push    rbp
0x14000dccb  push    rsi
0x14000dccc  push    rdi
0x14000dccd  sub     rsp, 28h
0x14000dcd1  mov     rdi, rcx
0x14000dcd4  mov     rbx, r8
0x14000dcd7  mov     rcx, [rcx+10h]
0x14000dcdb  mov     rbp, rdx
0x14000dcde  mov     rax, [rdi+8]
0x14000dce2  sub     rax, [rdi]
0x14000dce5  sub     rcx, [rdi]
0x14000dce8  add     rax, r8
0x14000dceb  cmp     rax, rcx
0x14000dcee  jb      short loc_14000DD0A
0x14000dcf0  lea     rax, [rcx+rcx]
0x14000dcf4  mov     rdx, rbx
0x14000dcf7  cmp     rbx, rax
0x14000dcfa  mov     rcx, rdi; this
0x14000dcfd  cmovb   rdx, rax; unsigned __int64
0x14000dd01  call    ?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::reserve(unsigned __int64)
0x14000dd06  test    al, al
0x14000dd08  jz      short loc_14000DD79
0x14000dd0a  mov     rcx, [rdi+8]; void *
0x14000dd0e  mov     rax, [rdi+10h]
0x14000dd12  sub     rax, rcx
0x14000dd15  cmp     rcx, [rdi+10h]
0x14000dd19  sbb     rsi, rsi
0x14000dd1c  and     rsi, rax
0x14000dd1f  test    rbx, rbx
0x14000dd22  jz      short loc_14000DD73
0x14000dd24  test    rcx, rcx
0x14000dd27  jnz     short loc_14000DD37
0x14000dd29  call    cs:__imp__o__errno
0x14000dd2f  mov     dword ptr [rax], 16h
0x14000dd35  jmp     short loc_14000DD6E
0x14000dd37  test    rbp, rbp
0x14000dd3a  jz      short loc_14000DD4E
0x14000dd3c  cmp     rsi, rbx
0x14000dd3f  jb      short loc_14000DD4E
0x14000dd41  mov     r8, rbx; Size
0x14000dd44  mov     rdx, rbp; Src
0x14000dd47  call    memcpy_0
0x14000dd4c  jmp     short loc_14000DD73
0x14000dd4e  mov     r8, rsi; Size
0x14000dd51  xor     edx, edx; Val
0x14000dd53  call    memset_0
0x14000dd58  test    rbp, rbp
0x14000dd5b  jz      short loc_14000DD29
0x14000dd5d  cmp     rsi, rbx
0x14000dd60  jnb     short loc_14000DD73
0x14000dd62  call    cs:__imp__o__errno
0x14000dd68  mov     dword ptr [rax], 22h ; '"'
0x14000dd6e  call    _invalid_parameter_noinfo
0x14000dd73  add     [rdi+8], rbx
0x14000dd77  mov     al, 1
0x14000dd79  add     rsp, 28h
0x14000dd7d  pop     rdi
0x14000dd7e  pop     rsi
0x14000dd7f  pop     rbp
0x14000dd80  pop     rbx
0x14000dd81  retn
```
