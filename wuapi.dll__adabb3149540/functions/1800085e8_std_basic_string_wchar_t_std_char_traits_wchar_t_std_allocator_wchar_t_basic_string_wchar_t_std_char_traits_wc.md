# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x1800085e8`
- end: `0x18000865b`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ`
- size: `115`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `14`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000634c`
- `0x18000642c`
- `0x180006810`
- `0x180006874`
- `0x180006b3c`
- `0x180006bd4`
- `0x180006cd0`
- `0x180006d98`
- `0x180006f10`
- `0x180006f90`
- `0x180007158`
- `0x180007308`
- `0x180016a67`
- `0x180016a8b`

## callees

- `0x1800085e8`
- `0x1800100d4`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180008654`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180008654`

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
0x1800085e8  push    rbx
0x1800085ea  sub     rsp, 30h
0x1800085ee  mov     rdx, [rcx+18h]
0x1800085f2  mov     rbx, rcx
0x1800085f5  cmp     rdx, 7
0x1800085f9  jbe     short loc_18000862C
0x1800085fb  mov     rcx, [rcx]
0x1800085fe  lea     rdx, ds:2[rdx*2]
0x180008606  cmp     rdx, 1000h
0x18000860d  jb      short loc_180008627
0x18000860f  mov     rax, [rcx-8]
0x180008613  add     rdx, 27h ; '''; struct std::nothrow_t *
0x180008617  sub     rcx, rax
0x18000861a  sub     rcx, 8
0x18000861e  cmp     rcx, 1Fh
0x180008622  ja      short loc_180008643
0x180008624  mov     rcx, rax; void *
0x180008627  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000862c  xor     eax, eax
0x18000862e  mov     qword ptr [rbx+18h], 7
0x180008636  mov     [rbx+10h], rax
0x18000863a  mov     [rbx], ax
0x18000863d  add     rsp, 30h
0x180008641  pop     rbx
0x180008642  retn
0x180008643  xor     eax, eax
0x180008645  xor     r9d, r9d; LineNo
0x180008648  xor     r8d, r8d; FileName
0x18000864b  mov     [rsp+38h+Reserved], rax; Reserved
0x180008650  xor     edx, edx; FunctionName
0x180008652  xor     ecx, ecx; Expression
0x180008654  call    cs:__imp__invoke_watson
```
