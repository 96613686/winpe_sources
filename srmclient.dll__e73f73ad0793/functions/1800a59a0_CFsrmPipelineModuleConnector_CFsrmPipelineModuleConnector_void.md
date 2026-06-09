# CFsrmPipelineModuleConnector::~CFsrmPipelineModuleConnector(void)

- ea: `0x1800a59a0`
- end: `0x1800a5a1d`
- name: `??1CFsrmPipelineModuleConnector@@QEAA@XZ`
- size: `125`
- prototype: `void __fastcall(CFsrmPipelineModuleConnector *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800a5a30`
- `0x1800d0583`
- `0x1800d0595`

## callees

- `0x1800a59a0`
- `0x1800d5010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800a59ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a59ca`
- `KERNEL32!DeleteCriticalSection` at `0x1800a59bc`
- `KERNEL32!DeleteCriticalSection` at `0x1800a5a0b`
- `KERNEL32!DeleteCriticalSection` at `0x1800a59bc`
- `KERNEL32!DeleteCriticalSection` at `0x1800a5a0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CFsrmPipelineModuleConnector::~CFsrmPipelineModuleConnector(CFsrmPipelineModuleConnector *this)
{
  __int64 v2; // rcx

  if ( *((_BYTE *)this + 120) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
    *((_BYTE *)this + 120) = 0;
  }
  SysFreeString(*((BSTR *)this + 9));
  v2 = *((_QWORD *)this + 8);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x1800a59a0  mov     [rsp+arg_10], rbx
0x1800a59a5  mov     [rsp+arg_0], rcx
0x1800a59aa  push    rdi
0x1800a59ab  sub     rsp, 20h
0x1800a59af  mov     rbx, rcx
0x1800a59b2  cmp     byte ptr [rcx+78h], 0
0x1800a59b6  jz      short loc_1800A59C6
0x1800a59b8  add     rcx, 50h ; 'P'; lpCriticalSection
0x1800a59bc  call    cs:__imp_DeleteCriticalSection
0x1800a59c2  mov     byte ptr [rbx+78h], 0
0x1800a59c6  mov     rcx, [rbx+48h]; bstrString
0x1800a59ca  call    cs:__imp_SysFreeString
0x1800a59d0  nop
0x1800a59d1  lea     rax, [rbx+40h]
0x1800a59d5  mov     [rsp+28h+arg_8], rax
0x1800a59da  mov     rcx, [rax]
0x1800a59dd  test    rcx, rcx
0x1800a59e0  jz      short loc_1800A59EF
0x1800a59e2  mov     rax, [rcx]
0x1800a59e5  mov     rax, [rax+10h]
0x1800a59e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a59ee  nop
0x1800a59ef  lea     rax, [rbx+8]
0x1800a59f3  mov     [rsp+28h+arg_0], rax
0x1800a59f8  lea     rcx, [rax+8]; lpCriticalSection
0x1800a59fc  mov     [rsp+28h+arg_8], rcx
0x1800a5a01  cmp     byte ptr [rcx+28h], 0
0x1800a5a05  jz      short loc_1800A5A12
0x1800a5a07  mov     byte ptr [rcx+28h], 0
0x1800a5a0b  call    cs:__imp_DeleteCriticalSection
0x1800a5a11  nop
0x1800a5a12  mov     rbx, [rsp+28h+arg_10]
0x1800a5a17  add     rsp, 20h
0x1800a5a1b  pop     rdi
0x1800a5a1c  retn
```
