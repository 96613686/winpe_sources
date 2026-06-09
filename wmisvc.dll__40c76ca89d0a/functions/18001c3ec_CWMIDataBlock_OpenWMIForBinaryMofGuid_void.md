# CWMIDataBlock::OpenWMIForBinaryMofGuid(void)

- ea: `0x18001c3ec`
- end: `0x18001c44a`
- name: `?OpenWMIForBinaryMofGuid@CWMIDataBlock@@QEAAJXZ`
- size: `94`
- prototype: `__int64 __fastcall(CWMIDataBlock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001f6c`

## callees

- `0x18001ae4c`
- `0x18001c3ec`

## import_xrefs

- `WMICLNT!WmiOpenBlock` at `0x18001c425`
- `WMICLNT!WmiOpenBlock` at `0x18001c425`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CWMIDataBlock::OpenWMIForBinaryMofGuid(CWMIDataBlock *this)
{
  unsigned int Guid; // ebx

  *((_DWORD *)this + 8) = 1;
  try
  {
    Guid = CWMIProcessClass::GetGuid(*((CWMIProcessClass **)this + 2));
    if ( !Guid )
    {
      WmiOpenBlock(*((_QWORD *)this + 2) + 56LL, *((unsigned int *)this + 293), (char *)this + 24);
      Guid = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)-2147217379;
  }
  return Guid;
}

```

## disassembly

```asm
0x18001c3ec  mov     [rsp+arg_0], rbx
0x18001c3f1  push    rdi
0x18001c3f2  sub     rsp, 30h
0x18001c3f6  mov     rdi, rcx
0x18001c3f9  mov     dword ptr [rcx+20h], 1
0x18001c400  mov     rcx, [rcx+10h]; this
0x18001c404  call    ?GetGuid@CWMIProcessClass@@QEAAJXZ; CWMIProcessClass::GetGuid(void)
0x18001c409  mov     ebx, eax
0x18001c40b  mov     [rsp+38h+var_18], eax
0x18001c40f  test    eax, eax
0x18001c411  jnz     short loc_18001C437
0x18001c413  lea     r8, [rdi+18h]
0x18001c417  mov     rcx, [rdi+10h]
0x18001c41b  add     rcx, 38h ; '8'
0x18001c41f  mov     edx, [rdi+494h]
0x18001c425  call    cs:__imp_WmiOpenBlock
0x18001c42b  neg     eax
0x18001c42d  sbb     ecx, ecx
0x18001c42f  and     ecx, ebx
0x18001c431  mov     ebx, ecx
0x18001c433  mov     [rsp+38h+var_18], ecx
0x18001c437  jmp     short loc_18001C43D
0x18001c439  mov     ebx, [rsp+38h+var_18]
0x18001c43d  mov     eax, ebx
0x18001c43f  mov     rbx, [rsp+38h+arg_0]
0x18001c444  add     rsp, 30h
0x18001c448  pop     rdi
0x18001c449  retn
```
