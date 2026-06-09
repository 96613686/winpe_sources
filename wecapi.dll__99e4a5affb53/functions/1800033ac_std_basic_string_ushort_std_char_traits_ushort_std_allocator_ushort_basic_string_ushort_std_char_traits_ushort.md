# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x1800033ac`
- end: `0x1800033db`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `47`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000bf0a`
- `0x18000c4a6`
- `0x18000c6d2`
- `0x18000c6f6`
- `0x18000c73e`
- `0x18000c750`

## callees

- `0x1800026c0`
- `0x1800033ac`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(__int64 a1)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 24) >= 8u )
    operator delete(*(void **)a1);
  result = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800033ac  push    rbx
0x1800033ae  sub     rsp, 20h
0x1800033b2  cmp     qword ptr [rcx+18h], 8
0x1800033b7  mov     rbx, rcx
0x1800033ba  jb      short loc_1800033C4
0x1800033bc  mov     rcx, [rcx]; void *
0x1800033bf  call    ??3@YAXPEAX@Z
0x1800033c4  xor     eax, eax
0x1800033c6  mov     qword ptr [rbx+18h], 7
0x1800033ce  mov     [rbx+10h], rax
0x1800033d2  mov     [rbx], ax
0x1800033d5  add     rsp, 20h
0x1800033d9  pop     rbx
0x1800033da  retn
```
