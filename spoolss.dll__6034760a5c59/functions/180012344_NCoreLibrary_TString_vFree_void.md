# NCoreLibrary::TString::vFree(void *)

- ea: `0x180012344`
- end: `0x18001236d`
- name: `?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z`
- size: `41`
- prototype: `void(NCoreLibrary::TString *__hidden this, void *)`
- caller_count: `9`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800048b4`
- `0x1800111e0`
- `0x1800111f0`
- `0x180011c98`
- `0x180011df8`
- `0x180013180`
- `0x1800133ec`
- `0x1800138bc`
- `0x180013f00`

## callees

- `0x180004f18`
- `0x180012344`

## pseudocode

```c
void __fastcall NCoreLibrary::TString::vFree(NCoreLibrary::TString *this, __int16 *a2)
{
  if ( a2 != (__int16 *)&NCoreLibrary::TString::gszNullState && a2 != &word_18002174E )
    operator delete(a2);
}

```

## disassembly

```asm
0x180012344  sub     rsp, 28h
0x180012348  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x18001234f  cmp     rdx, rax
0x180012352  jz      short loc_180012368
0x180012354  lea     rax, word_18002174E
0x18001235b  cmp     rdx, rax
0x18001235e  jz      short loc_180012368
0x180012360  mov     rcx, rdx; void *
0x180012363  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012368  add     rsp, 28h
0x18001236c  retn
```
