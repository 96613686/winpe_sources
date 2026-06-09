# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180004e90`
- end: `0x180004ec0`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(void **)`
- caller_count: `54`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001bd19`
- `0x18001bd2b`
- `0x18001bd41`
- `0x18001bef0`
- `0x18001bf2d`
- `0x18001bf3f`
- `0x18001bf55`
- `0x18001bf6b`
- `0x18001bf7d`
- `0x18001bf93`
- `0x18001bfa9`
- `0x18001bfd8`
- `0x18001bff1`
- `0x18001c020`
- `0x18001c195`
- `0x18001c1d2`
- `0x18001c1e4`
- `0x18001c1fa`
- `0x18001c229`
- `0x18001d1f4`
- `0x18001d206`
- `0x18001d21c`
- `0x18001d24b`
- `0x18001d288`
- `0x18001d29a`
- `0x18001d2b0`
- `0x18001d2d8`
- `0x18001db6e`
- `0x18001db80`
- `0x18001db96`
- `0x18001dbc5`
- `0x18001dbf0`
- `0x18001dc02`
- `0x18001dc14`
- `0x18001dc26`
- `0x18001dc38`
- `0x18001dc5c`
- `0x18001dc6e`
- `0x18001dc80`
- `0x18001dcb6`
- `0x18001dcec`
- `0x18001df30`
- `0x18001e0d4`
- `0x18001e0f8`
- `0x18001e946`
- `0x18001e958`
- `0x18001eb17`
- `0x18001eb6a`
- `0x18001ebbd`
- `0x18001ec14`

## callees

- `0x180004e90`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004ea3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004ea3`

## pseudocode

```c
void __fastcall std::wstring::~wstring(void **a1)
{
  if ( (unsigned __int64)a1[3] >= 8 )
    operator delete(*a1);
  a1[3] = (void *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
}

```

## disassembly

```asm
0x180004e90  push    rbx
0x180004e92  sub     rsp, 20h
0x180004e96  cmp     qword ptr [rcx+18h], 8
0x180004e9b  mov     rbx, rcx
0x180004e9e  jb      short loc_180004EA9
0x180004ea0  mov     rcx, [rcx]
0x180004ea3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004ea9  xor     eax, eax
0x180004eab  mov     qword ptr [rbx+18h], 7
0x180004eb3  mov     [rbx+10h], rax
0x180004eb7  mov     [rbx], ax
0x180004eba  add     rsp, 20h
0x180004ebe  pop     rbx
0x180004ebf  retn
```
