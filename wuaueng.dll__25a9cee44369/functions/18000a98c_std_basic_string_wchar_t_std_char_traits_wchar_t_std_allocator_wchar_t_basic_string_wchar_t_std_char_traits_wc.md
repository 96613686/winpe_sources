# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x18000a98c`
- end: `0x18000a9ff`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ`
- size: `115`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `14`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005524`
- `0x180007ae8`
- `0x180007ca4`
- `0x180007d10`
- `0x180008148`
- `0x1800082c0`
- `0x180008388`
- `0x1800084c8`
- `0x180008848`
- `0x180009a60`
- `0x18000a430`
- `0x18000a980`
- `0x1800167e5`
- `0x180016809`

## callees

- `0x18000a98c`
- `0x180010084`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000a9f8`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000a9f8`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(__int64 a1)
{
  unsigned __int64 v1; // rdx
  _QWORD *v3; // rcx
  const struct std::nothrow_t *v4; // rdx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 24);
  if ( v1 > 7 )
  {
    v3 = *(_QWORD **)a1;
    v4 = (const struct std::nothrow_t *)(2 * v1 + 2);
    if ( (unsigned __int64)v4 >= 0x1000 )
    {
      v4 = (const struct std::nothrow_t *)((char *)v4 + 39);
      if ( (unsigned __int64)v3 - *(v3 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v3 = (_QWORD *)*(v3 - 1);
    }
    operator delete(v3, v4);
  }
  result = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18000a98c  push    rbx
0x18000a98e  sub     rsp, 30h
0x18000a992  mov     rdx, [rcx+18h]
0x18000a996  mov     rbx, rcx
0x18000a999  cmp     rdx, 7
0x18000a99d  jbe     short loc_18000A9D0
0x18000a99f  mov     rcx, [rcx]
0x18000a9a2  lea     rdx, ds:2[rdx*2]
0x18000a9aa  cmp     rdx, 1000h
0x18000a9b1  jb      short loc_18000A9CB
0x18000a9b3  mov     rax, [rcx-8]
0x18000a9b7  add     rdx, 27h ; '''; struct std::nothrow_t *
0x18000a9bb  sub     rcx, rax
0x18000a9be  sub     rcx, 8
0x18000a9c2  cmp     rcx, 1Fh
0x18000a9c6  ja      short loc_18000A9E7
0x18000a9c8  mov     rcx, rax; void *
0x18000a9cb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a9d0  xor     eax, eax
0x18000a9d2  mov     qword ptr [rbx+18h], 7
0x18000a9da  mov     [rbx+10h], rax
0x18000a9de  mov     [rbx], ax
0x18000a9e1  add     rsp, 30h
0x18000a9e5  pop     rbx
0x18000a9e6  retn
0x18000a9e7  xor     eax, eax
0x18000a9e9  xor     r9d, r9d; LineNo
0x18000a9ec  xor     r8d, r8d; FileName
0x18000a9ef  mov     [rsp+38h+Reserved], rax; Reserved
0x18000a9f4  xor     edx, edx; FunctionName
0x18000a9f6  xor     ecx, ecx; Expression
0x18000a9f8  call    cs:__imp__invoke_watson
```
