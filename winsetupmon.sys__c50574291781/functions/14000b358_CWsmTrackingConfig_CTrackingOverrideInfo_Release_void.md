# CWsmTrackingConfig::CTrackingOverrideInfo::Release(void)

- ea: `0x14000b358`
- end: `0x14000b40c`
- name: `?Release@CTrackingOverrideInfo@CWsmTrackingConfig@@IEAAXXZ`
- size: `180`
- prototype: `void __fastcall(CWsmTrackingConfig::CTrackingOverrideInfo *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140009120`
- `0x14000c9b0`

## callees

- `0x14000b358`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b38c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b3a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b3d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b3e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b38c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b3a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b3d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b3e7`

## pseudocode

```c
void __fastcall CWsmTrackingConfig::CTrackingOverrideInfo::Release(CWsmTrackingConfig::CTrackingOverrideInfo *this)
{
  void **v1; // rdi
  void *v3; // rcx
  void **v4; // rdi
  void *v5; // rcx

  v1 = (void **)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v1 )
  {
    v3 = *v1;
    if ( *v1 != v1 + 2 && v3 )
      ExFreePoolWithTag(v3, 0x6E6D7377u);
    ExFreePoolWithTag(v1, 0x6E6D7377u);
  }
  v4 = (void **)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v4 )
  {
    v5 = *v4;
    if ( *v4 != v4 + 2 && v5 )
      ExFreePoolWithTag(v5, 0x6E6D7377u);
    ExFreePoolWithTag(v4, 0x6E6D7377u);
  }
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
}

```

## disassembly

```asm
0x14000b358  mov     [rsp+arg_0], rbx
0x14000b35d  push    rdi
0x14000b35e  sub     rsp, 20h
0x14000b362  mov     rdi, [rcx+20h]
0x14000b366  mov     rbx, rcx
0x14000b369  mov     qword ptr [rcx+20h], 0
0x14000b371  test    rdi, rdi
0x14000b374  jz      short loc_14000B3AC
0x14000b376  mov     rcx, [rdi]; P
0x14000b379  lea     rax, [rdi+10h]
0x14000b37d  cmp     rcx, rax
0x14000b380  jz      short loc_14000B398
0x14000b382  test    rcx, rcx
0x14000b385  jz      short loc_14000B398
0x14000b387  mov     edx, 6E6D7377h; Tag
0x14000b38c  call    cs:__imp_ExFreePoolWithTag
0x14000b393  nop     dword ptr [rax+rax+00h]
0x14000b398  mov     edx, 6E6D7377h; Tag
0x14000b39d  mov     rcx, rdi; P
0x14000b3a0  call    cs:__imp_ExFreePoolWithTag
0x14000b3a7  nop     dword ptr [rax+rax+00h]
0x14000b3ac  mov     rdi, [rbx+10h]
0x14000b3b0  mov     qword ptr [rbx+10h], 0
0x14000b3b8  test    rdi, rdi
0x14000b3bb  jz      short loc_14000B3F3
0x14000b3bd  mov     rcx, [rdi]; P
0x14000b3c0  lea     rax, [rdi+10h]
0x14000b3c4  cmp     rcx, rax
0x14000b3c7  jz      short loc_14000B3DF
0x14000b3c9  test    rcx, rcx
0x14000b3cc  jz      short loc_14000B3DF
0x14000b3ce  mov     edx, 6E6D7377h; Tag
0x14000b3d3  call    cs:__imp_ExFreePoolWithTag
0x14000b3da  nop     dword ptr [rax+rax+00h]
0x14000b3df  mov     edx, 6E6D7377h; Tag
0x14000b3e4  mov     rcx, rdi; P
0x14000b3e7  call    cs:__imp_ExFreePoolWithTag
0x14000b3ee  nop     dword ptr [rax+rax+00h]
0x14000b3f3  xorps   xmm0, xmm0
0x14000b3f6  xor     eax, eax
0x14000b3f8  movups  xmmword ptr [rbx+28h], xmm0
0x14000b3fc  mov     [rbx+38h], rax
0x14000b400  mov     rbx, [rsp+28h+arg_0]
0x14000b405  add     rsp, 20h
0x14000b409  pop     rdi
0x14000b40a  retn
```
