# ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)

- ea: `0x180004a94`
- end: `0x180004b19`
- name: `?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z`
- size: `133`
- prototype: `void __fastcall(ATL::Checked *this, void *, const void *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000246c`
- `0x180002d2c`

## callees

- `0x1800020ca`
- `0x180002106`
- `0x180002f30`
- `0x180004a94`
- `0x180004ea0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004ab6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004afd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004ab6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004afd`

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
0x180004a94  test    r9, r9
0x180004a97  jz      short locret_180004AE8
0x180004a99  mov     [rsp+arg_0], rbx
0x180004a9e  mov     [rsp+arg_8], rsi
0x180004aa3  push    rdi
0x180004aa4  sub     rsp, 20h
0x180004aa8  mov     rbx, r9
0x180004aab  mov     rsi, r8
0x180004aae  mov     rdi, rdx
0x180004ab1  test    rcx, rcx
0x180004ab4  jnz     short loc_180004AC4
0x180004ab6  call    cs:__imp__o__errno
0x180004abc  mov     dword ptr [rax], 16h
0x180004ac2  jmp     short loc_180004B09
0x180004ac4  test    rsi, rsi
0x180004ac7  jz      short loc_180004AE9
0x180004ac9  cmp     rdi, rbx
0x180004acc  jb      short loc_180004AE9
0x180004ace  mov     r8, rbx; Size
0x180004ad1  mov     rdx, rsi; Src
0x180004ad4  call    memcpy_0
0x180004ad9  mov     rbx, [rsp+28h+arg_0]
0x180004ade  mov     rsi, [rsp+28h+arg_8]
0x180004ae3  add     rsp, 20h
0x180004ae7  pop     rdi
0x180004ae8  retn
0x180004ae9  mov     r8, rdi; Size
0x180004aec  xor     edx, edx; Val
0x180004aee  call    memset_0
0x180004af3  test    rsi, rsi
0x180004af6  jz      short loc_180004AB6
0x180004af8  cmp     rdi, rbx
0x180004afb  jnb     short loc_180004B0E
0x180004afd  call    cs:__imp__o__errno
0x180004b03  mov     dword ptr [rax], 22h ; '"'
0x180004b09  call    _invalid_parameter_noinfo
0x180004b0e  mov     ecx, 80070057h; int
0x180004b13  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
