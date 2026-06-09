# CWsmLogConfig::~CWsmLogConfig(void)

- ea: `0x140009298`
- end: `0x1400092fa`
- name: `??1CWsmLogConfig@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(CWsmLogConfig *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000a4b0`
- `0x14000a680`
- `0x14000b4b0`
- `0x14000bb50`

## callees

- `0x140008f60`
- `0x140009298`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400092be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400092e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400092be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400092e2`

## pseudocode

```c
void __fastcall CWsmLogConfig::~CWsmLogConfig(CWsmLogConfig *this)
{
  void *v1; // rdi
  void *v3; // rcx

  v1 = (void *)*((_QWORD *)this + 5);
  if ( v1 )
  {
    CWsmLogConfig::CLogConfig::~CLogConfig(*((CWsmLogConfig::CLogConfig **)this + 5));
    ExFreePoolWithTag(v1, 0x6E6D7377u);
  }
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 != (void *)-1LL )
  {
    *((_QWORD *)this + 3) = v3;
    if ( v3 )
      ExFreePoolWithTag(v3, 0x6E6D7377u);
  }
}

```

## disassembly

```asm
0x140009298  mov     [rsp+arg_0], rbx
0x14000929d  push    rdi
0x14000929e  sub     rsp, 20h
0x1400092a2  mov     rdi, [rcx+28h]
0x1400092a6  mov     rbx, rcx
0x1400092a9  test    rdi, rdi
0x1400092ac  jz      short loc_1400092CA
0x1400092ae  mov     rcx, rdi; this
0x1400092b1  call    ??1CLogConfig@CWsmLogConfig@@QEAA@XZ; CWsmLogConfig::CLogConfig::~CLogConfig(void)
0x1400092b6  mov     edx, 6E6D7377h; Tag
0x1400092bb  mov     rcx, rdi; P
0x1400092be  call    cs:__imp_ExFreePoolWithTag
0x1400092c5  nop     dword ptr [rax+rax+00h]
0x1400092ca  mov     rcx, [rbx+10h]; P
0x1400092ce  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400092d2  jz      short loc_1400092EE
0x1400092d4  mov     [rbx+18h], rcx
0x1400092d8  test    rcx, rcx
0x1400092db  jz      short loc_1400092EE
0x1400092dd  mov     edx, 6E6D7377h; Tag
0x1400092e2  call    cs:__imp_ExFreePoolWithTag
0x1400092e9  nop     dword ptr [rax+rax+00h]
0x1400092ee  mov     rbx, [rsp+28h+arg_0]
0x1400092f3  add     rsp, 20h
0x1400092f7  pop     rdi
0x1400092f8  retn
```
