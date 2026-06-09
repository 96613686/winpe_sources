# std::vector<uchar *,std::allocator<uchar *>>::~vector<uchar *,std::allocator<uchar *>>(void)

- ea: `0x180004a04`
- end: `0x180004a38`
- name: `??1?$vector@PEAEV?$allocator@PEAE@std@@@std@@QEAA@XZ`
- size: `52`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000efb5`
- `0x18000f085`
- `0x18000f2d3`
- `0x18000f7d1`
- `0x18000f7e3`
- `0x18000f807`
- `0x18000f819`

## callees

- `0x180004a04`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004a15`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004a15`

## pseudocode

```c
void __fastcall std::vector<unsigned char *>::~vector<unsigned char *>(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180004a04  push    rbx
0x180004a06  sub     rsp, 20h
0x180004a0a  mov     rbx, rcx
0x180004a0d  mov     rcx, [rcx]
0x180004a10  test    rcx, rcx
0x180004a13  jz      short loc_180004A32
0x180004a15  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004a1b  mov     qword ptr [rbx], 0
0x180004a22  mov     qword ptr [rbx+8], 0
0x180004a2a  mov     qword ptr [rbx+10h], 0
0x180004a32  add     rsp, 20h
0x180004a36  pop     rbx
0x180004a37  retn
```
