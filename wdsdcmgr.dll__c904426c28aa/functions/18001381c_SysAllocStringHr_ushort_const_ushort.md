# SysAllocStringHr(ushort const *,ushort * *)

- ea: `0x18001381c`
- end: `0x18001384e`
- name: `?SysAllocStringHr@@YAJPEBGPEAPEAG@Z`
- size: `50`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180003acc`
- `0x18000563c`
- `0x180005818`
- `0x18000600c`
- `0x1800063b4`
- `0x18000eb50`
- `0x18000fae0`
- `0x180010790`
- `0x1800119b0`
- `0x180011ab0`
- `0x180011c40`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180013833`
- `OLEAUT32!__imp_SysAllocString` at `0x180013833`

## pseudocode

```c
__int64 __fastcall SysAllocStringHr(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v3; // rax

  if ( !a1 )
    a1 = &word_18001870C;
  v3 = SysAllocString(a1);
  *a2 = v3;
  return v3 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18001381c  push    rbx
0x18001381e  sub     rsp, 20h
0x180013822  test    rcx, rcx
0x180013825  lea     rax, word_18001870C
0x18001382c  mov     rbx, rdx
0x18001382f  cmovz   rcx, rax; psz
0x180013833  call    cs:__imp_SysAllocString
0x180013839  mov     [rbx], rax
0x18001383c  neg     rax
0x18001383f  sbb     eax, eax
0x180013841  not     eax
0x180013843  and     eax, 8007000Eh
0x180013848  add     rsp, 20h
0x18001384c  pop     rbx
0x18001384d  retn
```
