# ATL::CRegObject::~CRegObject(void)

- ea: `0x180002eb8`
- end: `0x180002f73`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `187`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003510`
- `0x18000ce24`

## callees

- `0x180002eb8`
- `0x180004220`

## import_xrefs

- `msvcrt!free` at `0x180002f2b`
- `msvcrt!free` at `0x180002f47`
- `msvcrt!free` at `0x180002f2b`
- `msvcrt!free` at `0x180002f47`
- `KERNEL32!LeaveCriticalSection` at `0x180002ef6`
- `KERNEL32!LeaveCriticalSection` at `0x180002ef6`
- `KERNEL32!EnterCriticalSection` at `0x180002edb`
- `KERNEL32!EnterCriticalSection` at `0x180002edb`
- `KERNEL32!DeleteCriticalSection` at `0x180002f0f`
- `KERNEL32!DeleteCriticalSection` at `0x180002f0f`

## pseudocode

```c
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  void **v3; // rdi
  void *v4; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  *(_QWORD *)this = &ATL::CRegObject::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v3 = (void **)((char *)this + 8);
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  LeaveCriticalSection(v2);
  if ( LOBYTE(v2[1].DebugInfo) )
  {
    LOBYTE(v2[1].DebugInfo) = 0;
    DeleteCriticalSection(v2);
  }
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  if ( *v3 )
  {
    free(*v3);
    *v3 = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 2) = 0;
  }
  *((_DWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x180002eb8  mov     [rsp+arg_0], rbx
0x180002ebd  mov     [rsp+arg_8], rsi
0x180002ec2  push    rdi
0x180002ec3  sub     rsp, 20h
0x180002ec7  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180002ece  mov     rbx, rcx
0x180002ed1  lea     rsi, [rcx+20h]
0x180002ed5  mov     [rcx], rax
0x180002ed8  mov     rcx, rsi; lpCriticalSection
0x180002edb  call    cs:__imp_EnterCriticalSection
0x180002ee2  nop     dword ptr [rax+rax+00h]
0x180002ee7  lea     rdi, [rbx+8]
0x180002eeb  mov     rcx, rdi; this
0x180002eee  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002ef3  mov     rcx, rsi; lpCriticalSection
0x180002ef6  call    cs:__imp_LeaveCriticalSection
0x180002efd  nop     dword ptr [rax+rax+00h]
0x180002f02  cmp     byte ptr [rsi+28h], 0
0x180002f06  jz      short loc_180002F1B
0x180002f08  mov     rcx, rsi; lpCriticalSection
0x180002f0b  mov     byte ptr [rsi+28h], 0
0x180002f0f  call    cs:__imp_DeleteCriticalSection
0x180002f16  nop     dword ptr [rax+rax+00h]
0x180002f1b  mov     rcx, rdi; this
0x180002f1e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002f23  mov     rcx, [rdi]; Block
0x180002f26  test    rcx, rcx
0x180002f29  jz      short loc_180002F3E
0x180002f2b  call    cs:__imp_free
0x180002f32  nop     dword ptr [rax+rax+00h]
0x180002f37  mov     qword ptr [rdi], 0
0x180002f3e  mov     rcx, [rbx+10h]; Block
0x180002f42  test    rcx, rcx
0x180002f45  jz      short loc_180002F5B
0x180002f47  call    cs:__imp_free
0x180002f4e  nop     dword ptr [rax+rax+00h]
0x180002f53  mov     qword ptr [rbx+10h], 0
0x180002f5b  mov     rsi, [rsp+28h+arg_8]
0x180002f60  mov     dword ptr [rbx+18h], 0
0x180002f67  mov     rbx, [rsp+28h+arg_0]
0x180002f6c  add     rsp, 20h
0x180002f70  pop     rdi
0x180002f71  retn
```
