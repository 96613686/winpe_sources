# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180003450`
- end: `0x180003498`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `72`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003384`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000347e`
- `KERNEL32!LeaveCriticalSection` at `0x18000347e`
- `KERNEL32!EnterCriticalSection` at `0x180003464`
- `KERNEL32!EnterCriticalSection` at `0x180003464`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ClearReplacements(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  ATL::CRegObject *v2; // rbx
  unsigned int v3; // edx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v2 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  LODWORD(v2) = ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)v2 + 8), v3);
  LeaveCriticalSection(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003450  mov     [rsp+arg_0], rbx
0x180003455  push    rdi
0x180003456  sub     rsp, 20h
0x18000345a  lea     rdi, [rcx+20h]
0x18000345e  mov     rbx, rcx
0x180003461  mov     rcx, rdi; lpCriticalSection
0x180003464  call    cs:__imp_EnterCriticalSection
0x18000346b  nop     dword ptr [rax+rax+00h]
0x180003470  lea     rcx, [rbx+8]; this
0x180003474  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180003479  mov     rcx, rdi; lpCriticalSection
0x18000347c  mov     ebx, eax
0x18000347e  call    cs:__imp_LeaveCriticalSection
0x180003485  nop     dword ptr [rax+rax+00h]
0x18000348a  mov     eax, ebx
0x18000348c  mov     rbx, [rsp+28h+arg_0]
0x180003491  add     rsp, 20h
0x180003495  pop     rdi
0x180003496  retn
```
