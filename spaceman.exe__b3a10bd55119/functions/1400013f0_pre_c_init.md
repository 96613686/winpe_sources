# pre_c_init

- ea: `0x1400013f0`
- end: `0x1400014c7`
- name: `pre_c_init`
- size: `215`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400013f0`
- `0x1400017c4`
- `0x140001820`

## import_xrefs

- `msvcrt!_commode` at `0x140001496`
- `msvcrt!_fmode` at `0x14000148d`
- `msvcrt!__setusermatherr` at `0x1400014ba`
- `msvcrt!__setusermatherr` at `0x1400014ba`
- `msvcrt!__set_app_type` at `0x14000146f`
- `msvcrt!__set_app_type` at `0x14000146f`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 pre_c_init()
{
  int v0; // eax
  bool v1; // zf
  _crt_app_type image_app_type; // eax

  if ( _ImageBase != 23117 || *(_DWORD *)((char *)&_ImageBase + (int)off_14000003C) != 17744 )
    goto LABEL_2;
  if ( *(__int16 *)((char *)&word_140000018 + (int)off_14000003C) != 267 )
  {
    if ( *(__int16 *)((char *)&word_140000018 + (int)off_14000003C) == 523 )
    {
      v0 = 0;
      if ( *(_DWORD *)&byte_140000040[(int)off_14000003C + 68] <= 0xEu )
        goto LABEL_11;
      v1 = *(int *)((char *)&dword_1400000F8 + (int)off_14000003C) == 0;
      goto LABEL_10;
    }
LABEL_2:
    v0 = 0;
    goto LABEL_11;
  }
  v0 = 0;
  if ( *(_DWORD *)&byte_140000040[(int)off_14000003C + 52] <= 0xEu )
    goto LABEL_11;
  v1 = *(_DWORD *)&byte_140000040[(int)off_14000003C + 168] == 0;
LABEL_10:
  LOBYTE(v0) = !v1;
LABEL_11:
  dword_1400143A0 = v0;
  image_app_type = (unsigned int)get_image_app_type(1);
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
0x1400013f0  sub     rsp, 28h
0x1400013f4  mov     eax, 5A4Dh
0x1400013f9  cmp     cs:__ImageBase, ax
0x140001400  jz      short loc_140001406
0x140001402  xor     eax, eax
0x140001404  jmp     short loc_14000145D
0x140001406  movsxd  rcx, cs:off_14000003C
0x14000140d  lea     rdx, __ImageBase
0x140001414  cmp     dword ptr [rcx+rdx], 4550h
0x14000141b  jnz     short loc_140001402
0x14000141d  mov     eax, 10Bh
0x140001422  cmp     [rcx+rdx+18h], ax
0x140001427  jz      short loc_14000144A
0x140001429  mov     eax, 20Bh
0x14000142e  cmp     [rcx+rdx+18h], ax
0x140001433  jnz     short loc_140001402
0x140001435  xor     eax, eax
0x140001437  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x14000143f  jbe     short loc_14000145D
0x140001441  cmp     [rcx+rdx+0F8h], eax
0x140001448  jmp     short loc_14000145A
0x14000144a  xor     eax, eax
0x14000144c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001451  jbe     short loc_14000145D
0x140001453  cmp     [rcx+rdx+0E8h], eax
0x14000145a  setnz   al
0x14000145d  mov     ecx, 1
0x140001462  mov     cs:dword_1400143A0, eax
0x140001468  call    _get_image_app_type
0x14000146d  mov     ecx, eax; Type
0x14000146f  call    cs:__imp___set_app_type
0x140001475  mov     ecx, cs:_fmode
0x14000147b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000147f  mov     cs:__onexitend, rax
0x140001486  mov     cs:__onexitbegin, rax
0x14000148d  mov     rax, cs:__imp__fmode
0x140001494  mov     [rax], ecx
0x140001496  mov     rcx, cs:__imp__commode; Except
0x14000149d  mov     eax, cs:_commode
0x1400014a3  mov     [rcx], eax
0x1400014a5  call    _matherr
0x1400014aa  cmp     cs:__defaultmatherr, 0
0x1400014b1  jnz     short loc_1400014C0
0x1400014b3  lea     rcx, _matherr; UserMathErrorFunction
0x1400014ba  call    cs:__imp___setusermatherr
0x1400014c0  xor     eax, eax
0x1400014c2  add     rsp, 28h
0x1400014c6  retn
```
