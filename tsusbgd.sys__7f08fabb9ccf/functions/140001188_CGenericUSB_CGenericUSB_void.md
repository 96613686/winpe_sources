# CGenericUSB::~CGenericUSB(void)

- ea: `0x140001188`
- end: `0x140001269`
- name: `??1CGenericUSB@@QEAA@XZ`
- size: `225`
- prototype: `void __fastcall(CGenericUSB *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001270`
- `0x14000c2e0`

## callees

- `0x140001188`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140001249`
- `ntoskrnl!ObfDereferenceObject` at `0x140001249`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400011a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400011ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400011e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400011f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000121b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000122c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400011a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400011ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400011e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400011f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000121b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000122c`

## pseudocode

```c
void __fastcall CGenericUSB::~CGenericUSB(CGenericUSB *this)
{
  _QWORD *v1; // rdi
  void *v3; // rcx
  _QWORD *v4; // rdi
  void *v5; // rcx
  _QWORD *v6; // rdi
  void *v7; // rcx
  void *v8; // rcx

  v1 = (_QWORD *)*((_QWORD *)this + 5);
  if ( v1 )
  {
    v3 = (void *)v1[1];
    if ( v3 )
      ExFreePoolWithTag(v3, 0);
    ExFreePoolWithTag(v1, 0);
  }
  v4 = (_QWORD *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 5) = 0;
  if ( v4 )
  {
    v5 = (void *)v4[1];
    if ( v5 )
      ExFreePoolWithTag(v5, 0);
    ExFreePoolWithTag(v4, 0);
  }
  v6 = (_QWORD *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 6) = 0;
  if ( v6 )
  {
    v7 = (void *)v6[1];
    if ( v7 )
      ExFreePoolWithTag(v7, 0);
    ExFreePoolWithTag(v6, 0);
  }
  v8 = (void *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 7) = 0;
  if ( v8 )
  {
    ObfDereferenceObject(v8);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x140001188  mov     [rsp+arg_0], rbx
0x14000118d  push    rdi
0x14000118e  sub     rsp, 20h
0x140001192  mov     rdi, [rcx+28h]
0x140001196  mov     rbx, rcx
0x140001199  test    rdi, rdi
0x14000119c  jz      short loc_1400011C6
0x14000119e  mov     rcx, [rdi+8]; P
0x1400011a2  test    rcx, rcx
0x1400011a5  jz      short loc_1400011B5
0x1400011a7  xor     edx, edx; Tag
0x1400011a9  call    cs:__imp_ExFreePoolWithTag
0x1400011b0  nop     dword ptr [rax+rax+00h]
0x1400011b5  xor     edx, edx; Tag
0x1400011b7  mov     rcx, rdi; P
0x1400011ba  call    cs:__imp_ExFreePoolWithTag
0x1400011c1  nop     dword ptr [rax+rax+00h]
0x1400011c6  mov     rdi, [rbx+30h]
0x1400011ca  mov     qword ptr [rbx+28h], 0
0x1400011d2  test    rdi, rdi
0x1400011d5  jz      short loc_1400011FF
0x1400011d7  mov     rcx, [rdi+8]; P
0x1400011db  test    rcx, rcx
0x1400011de  jz      short loc_1400011EE
0x1400011e0  xor     edx, edx; Tag
0x1400011e2  call    cs:__imp_ExFreePoolWithTag
0x1400011e9  nop     dword ptr [rax+rax+00h]
0x1400011ee  xor     edx, edx; Tag
0x1400011f0  mov     rcx, rdi; P
0x1400011f3  call    cs:__imp_ExFreePoolWithTag
0x1400011fa  nop     dword ptr [rax+rax+00h]
0x1400011ff  mov     rdi, [rbx+38h]
0x140001203  mov     qword ptr [rbx+30h], 0
0x14000120b  test    rdi, rdi
0x14000120e  jz      short loc_140001238
0x140001210  mov     rcx, [rdi+8]; P
0x140001214  test    rcx, rcx
0x140001217  jz      short loc_140001227
0x140001219  xor     edx, edx; Tag
0x14000121b  call    cs:__imp_ExFreePoolWithTag
0x140001222  nop     dword ptr [rax+rax+00h]
0x140001227  xor     edx, edx; Tag
0x140001229  mov     rcx, rdi; P
0x14000122c  call    cs:__imp_ExFreePoolWithTag
0x140001233  nop     dword ptr [rax+rax+00h]
0x140001238  mov     rcx, [rbx+18h]; Object
0x14000123c  mov     qword ptr [rbx+38h], 0
0x140001244  test    rcx, rcx
0x140001247  jz      short loc_14000125D
0x140001249  call    cs:__imp_ObfDereferenceObject
0x140001250  nop     dword ptr [rax+rax+00h]
0x140001255  mov     qword ptr [rbx+18h], 0
0x14000125d  mov     rbx, [rsp+28h+arg_0]
0x140001262  add     rsp, 20h
0x140001266  pop     rdi
0x140001267  retn
```
