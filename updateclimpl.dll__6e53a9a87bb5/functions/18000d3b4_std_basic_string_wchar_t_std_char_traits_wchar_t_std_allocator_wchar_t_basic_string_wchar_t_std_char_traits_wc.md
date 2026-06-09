# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x18000d3b4`
- end: `0x18000d427`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ`
- size: `115`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800084bc`
- `0x18000892c`
- `0x180008b90`
- `0x180008cdc`
- `0x18000c1e4`
- `0x180015892`
- `0x180015991`
- `0x1800159f1`

## callees

- `0x18000d3b4`
- `0x180010334`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000d420`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000d420`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(__int64 a1)
{
  unsigned __int64 v1; // rdx
  _QWORD *v3; // rcx
  unsigned __int64 v4; // rdx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 24);
  if ( v1 > 7 )
  {
    v3 = *(_QWORD **)a1;
    v4 = 2 * v1 + 2;
    if ( v4 >= 0x1000 )
    {
      v4 += 39LL;
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
0x18000d3b4  push    rbx
0x18000d3b6  sub     rsp, 30h
0x18000d3ba  mov     rdx, [rcx+18h]
0x18000d3be  mov     rbx, rcx
0x18000d3c1  cmp     rdx, 7
0x18000d3c5  jbe     short loc_18000D3F8
0x18000d3c7  mov     rcx, [rcx]
0x18000d3ca  lea     rdx, ds:2[rdx*2]
0x18000d3d2  cmp     rdx, 1000h
0x18000d3d9  jb      short loc_18000D3F3
0x18000d3db  mov     rax, [rcx-8]
0x18000d3df  add     rdx, 27h ; '''; unsigned __int64
0x18000d3e3  sub     rcx, rax
0x18000d3e6  sub     rcx, 8
0x18000d3ea  cmp     rcx, 1Fh
0x18000d3ee  ja      short loc_18000D40F
0x18000d3f0  mov     rcx, rax; void *
0x18000d3f3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d3f8  xor     eax, eax
0x18000d3fa  mov     qword ptr [rbx+18h], 7
0x18000d402  mov     [rbx+10h], rax
0x18000d406  mov     [rbx], ax
0x18000d409  add     rsp, 30h
0x18000d40d  pop     rbx
0x18000d40e  retn
0x18000d40f  xor     eax, eax
0x18000d411  xor     r9d, r9d; LineNo
0x18000d414  xor     r8d, r8d; FileName
0x18000d417  mov     [rsp+38h+Reserved], rax; Reserved
0x18000d41c  xor     edx, edx; FunctionName
0x18000d41e  xor     ecx, ecx; Expression
0x18000d420  call    cs:__imp__invoke_watson
```
