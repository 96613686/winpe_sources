# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x180007ee8`
- end: `0x180007f5a`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `114`
- prototype: `void __fastcall(__int64)`
- caller_count: `11`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006a98`
- `0x180006e34`
- `0x1800077f8`
- `0x180007ca4`
- `0x180007d10`
- `0x1800168b0`
- `0x1800168c2`
- `0x1800168e6`
- `0x180016912`
- `0x18001693e`
- `0x1800169de`

## callees

- `0x180007ee8`
- `0x180010084`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180007f53`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180007f53`

## pseudocode

```c
void __fastcall std::string::~string(__int64 a1)
{
  unsigned __int64 v1; // rdx
  _QWORD *v3; // rcx
  const struct std::nothrow_t *v4; // rdx

  v1 = *(_QWORD *)(a1 + 24);
  if ( v1 > 0xF )
  {
    v3 = *(_QWORD **)a1;
    v4 = (const struct std::nothrow_t *)(v1 + 1);
    if ( (unsigned __int64)v4 >= 0x1000 )
    {
      v4 = (const struct std::nothrow_t *)((char *)v4 + 39);
      if ( (unsigned __int64)v3 - *(v3 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v3 = (_QWORD *)*(v3 - 1);
    }
    operator delete(v3, v4);
  }
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 15;
  *(_BYTE *)a1 = 0;
}

```

## disassembly

```asm
0x180007ee8  push    rbx
0x180007eea  sub     rsp, 30h
0x180007eee  mov     rdx, [rcx+18h]
0x180007ef2  mov     rbx, rcx
0x180007ef5  cmp     rdx, 0Fh
0x180007ef9  jbe     short loc_180007F27
0x180007efb  mov     rcx, [rcx]
0x180007efe  inc     rdx
0x180007f01  cmp     rdx, 1000h
0x180007f08  jb      short loc_180007F22
0x180007f0a  mov     rax, [rcx-8]
0x180007f0e  add     rdx, 27h ; '''; struct std::nothrow_t *
0x180007f12  sub     rcx, rax
0x180007f15  sub     rcx, 8
0x180007f19  cmp     rcx, 1Fh
0x180007f1d  ja      short loc_180007F40
0x180007f1f  mov     rcx, rax; void *
0x180007f22  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007f27  mov     qword ptr [rbx+10h], 0
0x180007f2f  mov     qword ptr [rbx+18h], 0Fh
0x180007f37  mov     byte ptr [rbx], 0
0x180007f3a  add     rsp, 30h
0x180007f3e  pop     rbx
0x180007f3f  retn
0x180007f40  xor     r9d, r9d; LineNo
0x180007f43  mov     [rsp+38h+Reserved], 0; Reserved
0x180007f4c  xor     r8d, r8d; FileName
0x180007f4f  xor     edx, edx; FunctionName
0x180007f51  xor     ecx, ecx; Expression
0x180007f53  call    cs:__imp__invoke_watson
```
