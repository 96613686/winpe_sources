# CBinDescriptorTable::Init(unsigned __int64,CMemoryManager *,CSpinLockFileMappingArray *,int)

- ea: `0x1800151c4`
- end: `0x180015245`
- name: `?Init@CBinDescriptorTable@@QEAAH_KPEAVCMemoryManager@@PEAVCSpinLockFileMappingArray@@H@Z`
- size: `129`
- prototype: `__int64 __usercall@<rax>(CBinDescriptorTable *__hidden this@<rcx>, unsigned __int64@<rdx>, struct CMemoryManager *@<r8>, struct CSpinLockFileMappingArray *@<r9>, int)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x1800104fc`
- `0x180010e44`
- `0x180011868`
- `0x180017888`
- `0x180017e48`

## callees

- `0x180012408`
- `0x180013480`
- `0x180013738`
- `0x1800150dc`
- `0x1800151c4`
- `0x1800274de`

## pseudocode

```c
__int64 __fastcall CBinDescriptorTable::Init(
        CBinDescriptorTable *this,
        unsigned __int64 a2,
        struct CMemoryManager *a3,
        struct CSpinLockFileMappingArray *a4,
        int a5)
{
  unsigned __int64 v8; // r8
  void *v9; // rax
  size_t Size[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( !(unsigned int)CBin::Init(this, a2, a3, 0) )
    return 0;
  *((_QWORD *)this + 48) = a4;
  if ( a5 )
  {
    if ( !(unsigned int)CBin::EnumReset(this, 0) )
      return 0;
    for ( Size[0] = 0; ; memset_0(v9, 0, Size[0]) )
    {
      v9 = CBin::EnumView(this, Size, v8);
      if ( !v9 )
        break;
    }
    CBin::EnumFinish(this);
  }
  return 1;
}

```

## disassembly

```asm
0x1800151c4  mov     [rsp+arg_0], rbx
0x1800151c9  push    rdi
0x1800151ca  sub     rsp, 30h
0x1800151ce  mov     rdi, r9
0x1800151d1  mov     rbx, rcx
0x1800151d4  xor     r9d, r9d; unsigned __int64
0x1800151d7  call    ?Init@CBin@@QEAAH_KPEAVCMemoryManager@@0@Z; CBin::Init(unsigned __int64,CMemoryManager *,unsigned __int64)
0x1800151dc  test    eax, eax
0x1800151de  jnz     short loc_1800151E4
0x1800151e0  xor     eax, eax
0x1800151e2  jmp     short loc_180015239
0x1800151e4  cmp     [rsp+38h+arg_20], 0
0x1800151e9  mov     [rbx+180h], rdi
0x1800151f0  jz      short loc_180015234
0x1800151f2  xor     edx, edx; unsigned __int64
0x1800151f4  mov     rcx, rbx; this
0x1800151f7  call    ?EnumReset@CBin@@QEAAH_K@Z; CBin::EnumReset(unsigned __int64)
0x1800151fc  test    eax, eax
0x1800151fe  jz      short loc_1800151E0
0x180015200  mov     [rsp+38h+Size], 0
0x180015209  jmp     short loc_18001521A
0x18001520b  mov     r8, [rsp+38h+Size]; Size
0x180015210  xor     edx, edx; Val
0x180015212  mov     rcx, rax; void *
0x180015215  call    memset_0
0x18001521a  lea     rdx, [rsp+38h+Size]; unsigned __int64 *
0x18001521f  mov     rcx, rbx; this
0x180015222  call    ?EnumView@CBin@@QEAAPEAXAEA_K_K@Z; CBin::EnumView(unsigned __int64 &,unsigned __int64)
0x180015227  test    rax, rax
0x18001522a  jnz     short loc_18001520B
0x18001522c  mov     rcx, rbx; this
0x18001522f  call    ?EnumFinish@CBin@@QEAAHXZ; CBin::EnumFinish(void)
0x180015234  mov     eax, 1
0x180015239  mov     rbx, [rsp+38h+arg_0]
0x18001523e  add     rsp, 30h
0x180015242  pop     rdi
0x180015243  retn
```
