# CWMIDataBlock::GetDataBlockReady(ulong,int)

- ea: `0x18001c1f8`
- end: `0x18001c24f`
- name: `?GetDataBlockReady@CWMIDataBlock@@IEAAHKH@Z`
- size: `87`
- prototype: `__int64 __fastcall(CWMIDataBlock *this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c258`
- `0x18001c304`

## callees

- `0x180006a38`
- `0x18001c1f8`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001c21b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001c21b`

## pseudocode

```c
__int64 __fastcall CWMIDataBlock::GetDataBlockReady(CWMIDataBlock *this, unsigned int a2)
{
  void *v4; // rax
  __int64 result; // rax

  CWMIDataBlock::ResetDataBuffer(this);
  *((_DWORD *)this + 34) = a2;
  if ( a2 + 2 >= a2 && (v4 = CWin32DefaultArena::WbemMemAlloc(a2 + 2), (*((_QWORD *)this + 5) = v4) != 0) )
  {
    *((_QWORD *)this + 7) = v4;
    *((_QWORD *)this + 6) = v4;
    result = 1;
    *((_DWORD *)this + 16) = a2;
  }
  else
  {
    result = 0;
    *((_DWORD *)this + 34) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001c1f8  mov     [rsp+arg_0], rbx
0x18001c1fd  push    rdi
0x18001c1fe  sub     rsp, 20h
0x18001c202  mov     edi, edx
0x18001c204  mov     rbx, rcx
0x18001c207  call    ?ResetDataBuffer@CWMIDataBlock@@QEAAXXZ; CWMIDataBlock::ResetDataBuffer(void)
0x18001c20c  lea     eax, [rdi+2]
0x18001c20f  mov     [rbx+88h], edi
0x18001c215  cmp     eax, edi
0x18001c217  jb      short loc_18001C23C
0x18001c219  mov     ecx, eax
0x18001c21b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001c221  mov     [rbx+28h], rax
0x18001c225  test    rax, rax
0x18001c228  jz      short loc_18001C23C
0x18001c22a  mov     [rbx+38h], rax
0x18001c22e  mov     [rbx+30h], rax
0x18001c232  mov     eax, 1
0x18001c237  mov     [rbx+40h], edi
0x18001c23a  jmp     short loc_18001C244
0x18001c23c  xor     eax, eax
0x18001c23e  mov     [rbx+88h], eax
0x18001c244  mov     rbx, [rsp+28h+arg_0]
0x18001c249  add     rsp, 20h
0x18001c24d  pop     rdi
0x18001c24e  retn
```
