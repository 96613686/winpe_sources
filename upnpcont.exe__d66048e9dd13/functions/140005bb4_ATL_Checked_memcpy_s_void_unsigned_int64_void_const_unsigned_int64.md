# ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)

- ea: `0x140005bb4`
- end: `0x140005c39`
- name: `?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z`
- size: `133`
- prototype: `void __fastcall(ATL::Checked *this, void *, const void *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400021e4`
- `0x14000295c`

## callees

- `0x140001d8a`
- `0x140001e30`
- `0x140003298`
- `0x140005bb4`
- `0x140006694`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005bd6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005c1d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005bd6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005c1d`

## pseudocode

```c
void __fastcall ATL::Checked::memcpy_s(ATL::Checked *this, void *a2, const void *a3, void *a4)
{
  if ( a4 )
  {
    if ( !this )
      goto LABEL_3;
    if ( !a3 || a2 < a4 )
    {
      memset_0(this, 0, (size_t)a2);
      if ( a3 )
      {
        if ( a2 >= a4 )
          goto LABEL_12;
        *(_DWORD *)_o__errno() = 34;
LABEL_11:
        invalid_parameter_noinfo();
LABEL_12:
        ATL::AtlThrowImpl(-2147024809);
      }
LABEL_3:
      *(_DWORD *)_o__errno() = 22;
      goto LABEL_11;
    }
    memcpy_0(this, a3, (size_t)a4);
  }
}

```

## disassembly

```asm
0x140005bb4  test    r9, r9
0x140005bb7  jz      short locret_140005C08
0x140005bb9  mov     [rsp+arg_0], rbx
0x140005bbe  mov     [rsp+arg_8], rsi
0x140005bc3  push    rdi
0x140005bc4  sub     rsp, 20h
0x140005bc8  mov     rbx, r9
0x140005bcb  mov     rsi, r8
0x140005bce  mov     rdi, rdx
0x140005bd1  test    rcx, rcx
0x140005bd4  jnz     short loc_140005BE4
0x140005bd6  call    cs:__imp__o__errno
0x140005bdc  mov     dword ptr [rax], 16h
0x140005be2  jmp     short loc_140005C29
0x140005be4  test    rsi, rsi
0x140005be7  jz      short loc_140005C09
0x140005be9  cmp     rdi, rbx
0x140005bec  jb      short loc_140005C09
0x140005bee  mov     r8, rbx; Size
0x140005bf1  mov     rdx, rsi; Src
0x140005bf4  call    memcpy_0
0x140005bf9  mov     rbx, [rsp+28h+arg_0]
0x140005bfe  mov     rsi, [rsp+28h+arg_8]
0x140005c03  add     rsp, 20h
0x140005c07  pop     rdi
0x140005c08  retn
0x140005c09  mov     r8, rdi; Size
0x140005c0c  xor     edx, edx; Val
0x140005c0e  call    memset_0
0x140005c13  test    rsi, rsi
0x140005c16  jz      short loc_140005BD6
0x140005c18  cmp     rdi, rbx
0x140005c1b  jnb     short loc_140005C2E
0x140005c1d  call    cs:__imp__o__errno
0x140005c23  mov     dword ptr [rax], 22h ; '"'
0x140005c29  call    _invalid_parameter_noinfo
0x140005c2e  mov     ecx, 80070057h; int
0x140005c33  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
