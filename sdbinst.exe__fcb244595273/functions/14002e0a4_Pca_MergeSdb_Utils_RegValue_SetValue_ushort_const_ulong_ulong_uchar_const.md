# Pca::MergeSdb::Utils::RegValue::SetValue(ushort const *,ulong,ulong,uchar const *)

- ea: `0x14002e0a4`
- end: `0x14002e12d`
- name: `?SetValue@RegValue@Utils@MergeSdb@Pca@@QEAAKPEBGKKPEBE@Z`
- size: `137`
- prototype: `__int64 __fastcall(void **this, unsigned __int16 *, int, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14002a494`
- `0x14002d418`

## callees

- `0x14001008c`
- `0x14002dce4`
- `0x14002e0a4`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x14002e10a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002e10a`

## string_xrefs

- `0x14002e0d9`: `Failed to create buffer for reg value (%d)`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegValue::SetValue(
        void **this,
        unsigned __int16 *a2,
        int a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  int Buffer; // eax
  unsigned int v7; // ebx
  void *v8; // rcx

  Buffer = Pca::MergeSdb::Utils::RegValue::RegValueCreateBuffer(this, (_DWORD *)this + 2, a2, a3, a4, a5);
  v7 = Buffer;
  if ( !Buffer )
    return 0;
  AslLogCallPrintf(
    1,
    "Pca::MergeSdb::Utils::RegValue::SetValue",
    2609,
    "Failed to create buffer for reg value (%d)",
    Buffer);
  v8 = *this;
  *this = 0;
  if ( v8 )
    operator delete[](v8);
  *((_DWORD *)this + 2) = 0;
  return v7;
}

```

## disassembly

```asm
0x14002e0a4  mov     r11, rsp
0x14002e0a7  mov     [r11+8], rbx
0x14002e0ab  mov     [r11+10h], rsi
0x14002e0af  push    rdi
0x14002e0b0  sub     rsp, 30h
0x14002e0b4  mov     rax, [rsp+38h+arg_20]
0x14002e0b9  mov     rdi, rcx
0x14002e0bc  mov     [r11-10h], rax
0x14002e0c0  mov     [r11-18h], r9d
0x14002e0c4  mov     r9d, r8d
0x14002e0c7  mov     r8, rdx
0x14002e0ca  lea     rdx, [rcx+8]
0x14002e0ce  call    ?RegValueCreateBuffer@RegValue@Utils@MergeSdb@Pca@@CAKAEAV?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@AEAKPEBGKKPEBE@Z; Pca::MergeSdb::Utils::RegValue::RegValueCreateBuffer(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &,ulong &,ushort const *,ulong,ulong,uchar const *)
0x14002e0d3  mov     ebx, eax
0x14002e0d5  test    eax, eax
0x14002e0d7  jz      short loc_14002E11B
0x14002e0d9  lea     r9, aFailedToCreate_0; "Failed to create buffer for reg value ("...
0x14002e0e0  mov     [rsp+38h+var_18], eax
0x14002e0e4  mov     r8d, 0A31h
0x14002e0ea  lea     rdx, aPcaMergesdbUti_2; "Pca::MergeSdb::Utils::RegValue::SetValu"...
0x14002e0f1  mov     ecx, 1
0x14002e0f6  call    AslLogCallPrintf
0x14002e0fb  mov     rcx, [rdi]
0x14002e0fe  mov     qword ptr [rdi], 0
0x14002e105  test    rcx, rcx
0x14002e108  jz      short loc_14002E110
0x14002e10a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14002e110  mov     dword ptr [rdi+8], 0
0x14002e117  mov     eax, ebx
0x14002e119  jmp     short loc_14002E11D
0x14002e11b  xor     eax, eax
0x14002e11d  mov     rbx, [rsp+38h+arg_0]
0x14002e122  mov     rsi, [rsp+38h+arg_8]
0x14002e127  add     rsp, 30h
0x14002e12b  pop     rdi
0x14002e12c  retn
```
