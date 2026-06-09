# CConsistentMappingFactory::CreateObject(int)

- ea: `0x1800114e4`
- end: `0x180011570`
- name: `?CreateObject@CConsistentMappingFactory@@SAPEAVCConsistentMapping@@H@Z`
- size: `140`
- prototype: `struct CConsistentMapping *__fastcall(int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010ca4`
- `0x18001700c`

## callees

- `0x180001144`
- `0x18000f144`
- `0x1800114e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct CConsistentMapping *__fastcall CConsistentMappingFactory::CreateObject(int a1)
{
  _QWORD *v1; // rax
  _QWORD *v2; // rcx
  struct CConsistentMapping *result; // rax

  if ( a1 )
  {
    v1 = operator new(0x38u);
    v2 = v1;
    if ( !v1 )
      return 0;
    *v1 = &CConsistentMapping::`vftable';
    v1[1] = v1 + 4;
    *v1 = &CConsistentMemoryMapping::`vftable';
    v1[2] = 0;
    v1[3] = 0;
    *((_OWORD *)v1 + 2) = 0;
    v1[6] = 0;
    return (struct CConsistentMapping *)v2;
  }
  else
  {
    result = (struct CConsistentMapping *)operator new(0x70u);
    if ( result )
      return CConsistentFileMapping::CConsistentFileMapping(result);
  }
  return result;
}

```

## disassembly

```asm
0x1800114e4  sub     rsp, 38h
0x1800114e8  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800114f1  test    ecx, ecx
0x1800114f3  jz      short loc_18001154D
0x1800114f5  mov     ecx, 38h ; '8'; Size
0x1800114fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800114ff  mov     rcx, rax
0x180011502  mov     [rsp+38h+arg_8], rax
0x180011507  test    rax, rax
0x18001150a  jz      short loc_180011546
0x18001150c  lea     rax, ??_7CConsistentMapping@@6B@; const CConsistentMapping::`vftable'
0x180011513  mov     [rcx], rax
0x180011516  lea     rax, [rcx+20h]
0x18001151a  mov     [rcx+8], rax
0x18001151e  lea     rdx, ??_7CConsistentMemoryMapping@@6B@; const CConsistentMemoryMapping::`vftable'
0x180011525  mov     [rcx], rdx
0x180011528  mov     qword ptr [rcx+10h], 0
0x180011530  mov     qword ptr [rcx+18h], 0
0x180011538  xorps   xmm0, xmm0
0x18001153b  xor     edx, edx
0x18001153d  movups  xmmword ptr [rax], xmm0
0x180011540  mov     [rax+10h], rdx
0x180011544  jmp     short loc_180011548
0x180011546  xor     ecx, ecx
0x180011548  mov     rax, rcx
0x18001154b  jmp     short loc_18001156A
0x18001154d  mov     ecx, 70h ; 'p'; Size
0x180011552  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011557  mov     [rsp+38h+arg_8], rax
0x18001155c  test    rax, rax
0x18001155f  jz      short loc_18001156A
0x180011561  mov     rcx, rax; this
0x180011564  call    ??0CConsistentFileMapping@@QEAA@XZ; CConsistentFileMapping::CConsistentFileMapping(void)
0x180011569  nop
0x18001156a  add     rsp, 38h
0x18001156e  retn
```
