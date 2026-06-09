# pre_c_init

- ea: `0x1400012b0`
- end: `0x140001387`
- name: `pre_c_init`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400012b0`
- `0x140001844`
- `0x140011810`

## import_xrefs

- `msvcrt!__set_app_type` at `0x14000132f`
- `msvcrt!__set_app_type` at `0x14000132f`
- `msvcrt!_commode` at `0x140001356`
- `msvcrt!_fmode` at `0x14000134d`
- `msvcrt!__setusermatherr` at `0x14000137a`
- `msvcrt!__setusermatherr` at `0x14000137a`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 pre_c_init()
{
  int v0; // eax
  bool v1; // zf
  _crt_app_type image_app_type; // eax

  if ( LOWORD(MEMORY[0x140000000].unused) != 23117 || *(_DWORD *)(MEMORY[0x14000003C] + 0x140000000LL) != 17744 )
    goto LABEL_2;
  if ( *(_WORD *)(MEMORY[0x14000003C] + 0x140000018LL) != 267 )
  {
    if ( *(_WORD *)(MEMORY[0x14000003C] + 0x140000018LL) == 523 )
    {
      v0 = 0;
      if ( *(_DWORD *)(MEMORY[0x14000003C] + 0x140000084LL) <= 0xEu )
        goto LABEL_11;
      v1 = *(_DWORD *)(MEMORY[0x14000003C] + 0x1400000F8LL) == 0;
      goto LABEL_10;
    }
LABEL_2:
    v0 = 0;
    goto LABEL_11;
  }
  v0 = 0;
  if ( *(_DWORD *)(MEMORY[0x14000003C] + 0x140000074LL) <= 0xEu )
    goto LABEL_11;
  v1 = *(_DWORD *)(MEMORY[0x14000003C] + 0x1400000E8LL) == 0;
LABEL_10:
  LOBYTE(v0) = !v1;
LABEL_11:
  dword_140020480 = v0;
  image_app_type = (unsigned int)get_image_app_type(2);
  __set_app_type(image_app_type);
  _onexitend = -1;
  _onexitbegin = -1;
  _fmode = fmode;
  _commode = commode;
  matherr(*(struct _exception **)&_commode);
  if ( !_defaultmatherr )
    __setusermatherr(matherr);
  return 0;
}

```

## disassembly

```asm
0x1400012b0  sub     rsp, 28h
0x1400012b4  mov     eax, 5A4Dh
0x1400012b9  cmp     cs:140000000h, ax
0x1400012c0  jz      short loc_1400012C6
0x1400012c2  xor     eax, eax
0x1400012c4  jmp     short loc_14000131D
0x1400012c6  movsxd  rcx, dword ptr cs:14000003Ch
0x1400012cd  lea     rdx, cs:140000000h
0x1400012d4  cmp     dword ptr [rcx+rdx], 4550h
0x1400012db  jnz     short loc_1400012C2
0x1400012dd  mov     eax, 10Bh
0x1400012e2  cmp     [rcx+rdx+18h], ax
0x1400012e7  jz      short loc_14000130A
0x1400012e9  mov     eax, 20Bh
0x1400012ee  cmp     [rcx+rdx+18h], ax
0x1400012f3  jnz     short loc_1400012C2
0x1400012f5  xor     eax, eax
0x1400012f7  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x1400012ff  jbe     short loc_14000131D
0x140001301  cmp     [rcx+rdx+0F8h], eax
0x140001308  jmp     short loc_14000131A
0x14000130a  xor     eax, eax
0x14000130c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001311  jbe     short loc_14000131D
0x140001313  cmp     [rcx+rdx+0E8h], eax
0x14000131a  setnz   al
0x14000131d  mov     ecx, 2
0x140001322  mov     cs:dword_140020480, eax
0x140001328  call    _get_image_app_type
0x14000132d  mov     ecx, eax; Type
0x14000132f  call    cs:__imp___set_app_type
0x140001335  mov     ecx, cs:_fmode
0x14000133b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000133f  mov     cs:__onexitend, rax
0x140001346  mov     cs:__onexitbegin, rax
0x14000134d  mov     rax, cs:__imp__fmode
0x140001354  mov     [rax], ecx
0x140001356  mov     rcx, cs:__imp__commode; Except
0x14000135d  mov     eax, cs:_commode
0x140001363  mov     [rcx], eax
0x140001365  call    _matherr
0x14000136a  cmp     cs:__defaultmatherr, 0
0x140001371  jnz     short loc_140001380
0x140001373  lea     rcx, _matherr; UserMathErrorFunction
0x14000137a  call    cs:__imp___setusermatherr
0x140001380  xor     eax, eax
0x140001382  add     rsp, 28h
0x140001386  retn
```
