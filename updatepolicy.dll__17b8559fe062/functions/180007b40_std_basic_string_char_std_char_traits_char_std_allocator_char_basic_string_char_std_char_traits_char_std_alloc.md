# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x180007b40`
- end: `0x180007bb2`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `114`
- prototype: `void __fastcall(__int64)`
- caller_count: `11`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800015ac`
- `0x1800017f8`
- `0x180002358`
- `0x180002650`
- `0x1800026b4`
- `0x180015ee3`
- `0x180015ef5`
- `0x180015fc1`
- `0x180015fed`
- `0x18001603d`
- `0x180016228`

## callees

- `0x180007b40`
- `0x18000ed64`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180007bab`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180007bab`

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
0x180007b40  push    rbx
0x180007b42  sub     rsp, 30h
0x180007b46  mov     rdx, [rcx+18h]
0x180007b4a  mov     rbx, rcx
0x180007b4d  cmp     rdx, 0Fh
0x180007b51  jbe     short loc_180007B7F
0x180007b53  mov     rcx, [rcx]
0x180007b56  inc     rdx
0x180007b59  cmp     rdx, 1000h
0x180007b60  jb      short loc_180007B7A
0x180007b62  mov     rax, [rcx-8]
0x180007b66  add     rdx, 27h ; '''; struct std::nothrow_t *
0x180007b6a  sub     rcx, rax
0x180007b6d  sub     rcx, 8
0x180007b71  cmp     rcx, 1Fh
0x180007b75  ja      short loc_180007B98
0x180007b77  mov     rcx, rax; void *
0x180007b7a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007b7f  mov     qword ptr [rbx+10h], 0
0x180007b87  mov     qword ptr [rbx+18h], 0Fh
0x180007b8f  mov     byte ptr [rbx], 0
0x180007b92  add     rsp, 30h
0x180007b96  pop     rbx
0x180007b97  retn
0x180007b98  xor     r9d, r9d; LineNo
0x180007b9b  mov     [rsp+38h+Reserved], 0; Reserved
0x180007ba4  xor     r8d, r8d; FileName
0x180007ba7  xor     edx, edx; FunctionName
0x180007ba9  xor     ecx, ecx; Expression
0x180007bab  call    cs:__imp__invoke_watson
```
