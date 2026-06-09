# ATL::Checked::memmove_s(void *,unsigned __int64,void const *,unsigned __int64)

- ea: `0x18000e130`
- end: `0x18000e187`
- name: `?memmove_s@Checked@ATL@@YAXPEAX_KPEBX1@Z`
- size: `87`
- prototype: `void __fastcall(ATL::Checked *this, void *, const void *, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c618`
- `0x18000c6e0`

## callees

- `0x180002e1a`
- `0x18000c3b8`
- `0x18000e130`
- `0x18000feb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e143`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e161`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e143`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e161`

## pseudocode

```c
void __fastcall ATL::Checked::memmove_s(ATL::Checked *this, void *a2, const void *a3, void *a4)
{
  int *v4; // rax
  int v5; // ebx

  if ( !a4 )
    goto LABEL_9;
  if ( this && a3 )
  {
    if ( a2 < a4 )
    {
      v4 = (int *)((__int64 (*)(void))_o__errno)();
      v5 = 34;
      goto LABEL_4;
    }
    memmove_0(this, a3, (size_t)a4);
LABEL_9:
    v5 = 0;
    goto LABEL_10;
  }
  v4 = (int *)_o__errno(this, a2);
  v5 = 22;
LABEL_4:
  *v4 = v5;
  invalid_parameter_noinfo();
LABEL_10:
  ATL::AtlCrtErrorCheck(v5);
}

```

## disassembly

```asm
0x18000e130  push    rbx
0x18000e132  sub     rsp, 20h
0x18000e136  mov     rax, r8
0x18000e139  test    r9, r9
0x18000e13c  jz      short loc_18000E179
0x18000e13e  test    rcx, rcx
0x18000e141  jnz     short loc_18000E157
0x18000e143  call    cs:__imp__o__errno
0x18000e149  mov     ebx, 16h
0x18000e14e  mov     [rax], ebx
0x18000e150  call    _invalid_parameter_noinfo
0x18000e155  jmp     short loc_18000E17B
0x18000e157  test    rax, rax
0x18000e15a  jz      short loc_18000E143
0x18000e15c  cmp     rdx, r9
0x18000e15f  jnb     short loc_18000E16E
0x18000e161  call    cs:__imp__o__errno
0x18000e167  mov     ebx, 22h ; '"'
0x18000e16c  jmp     short loc_18000E14E
0x18000e16e  mov     r8, r9; Size
0x18000e171  mov     rdx, rax; Src
0x18000e174  call    memmove_0
0x18000e179  xor     ebx, ebx
0x18000e17b  mov     ecx, ebx; int
0x18000e17d  add     rsp, 20h
0x18000e181  pop     rbx
0x18000e182  jmp     ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
```
