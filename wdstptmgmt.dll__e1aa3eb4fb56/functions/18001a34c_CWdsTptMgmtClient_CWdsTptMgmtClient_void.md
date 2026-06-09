# CWdsTptMgmtClient::~CWdsTptMgmtClient(void)

- ea: `0x18001a34c`
- end: `0x18001a39b`
- name: `??1CWdsTptMgmtClient@@UEAA@XZ`
- size: `79`
- prototype: `void __fastcall(CWdsTptMgmtClient *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a3f0`

## callees

- `0x18001c08c`
- `0x18001c0b8`
- `0x18001c3e0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001a37e`
- `KERNEL32!DeleteCriticalSection` at `0x18001a37e`

## pseudocode

```c
void __fastcall CWdsTptMgmtClient::~CWdsTptMgmtClient(CWdsTptMgmtClient *this)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // r8

  *(_QWORD *)this = &CWdsTptMgmtClient::`vftable';
  v2 = CWdsTptMgmtClient::Shutdown(this);
  ElValidateWin32_14(v2, v3, v4, 84);
  CClientLibraryInitializer::Shutdown((CWdsTptMgmtClient *)((char *)this + 80));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &CRefCount::`vftable';
}

```

## disassembly

```asm
0x18001a34c  push    rbx
0x18001a34e  sub     rsp, 20h
0x18001a352  lea     rax, ??_7CWdsTptMgmtClient@@6B@; const CWdsTptMgmtClient::`vftable'
0x18001a359  mov     rbx, rcx
0x18001a35c  mov     [rcx], rax
0x18001a35f  call    ?Shutdown@CWdsTptMgmtClient@@AEAAKXZ; CWdsTptMgmtClient::Shutdown(void)
0x18001a364  mov     ecx, eax
0x18001a366  mov     r9d, 54h ; 'T'
0x18001a36c  call    ElValidateWin32_14
0x18001a371  lea     rcx, [rbx+50h]; this
0x18001a375  call    ?Shutdown@CClientLibraryInitializer@@QEAAXXZ; CClientLibraryInitializer::Shutdown(void)
0x18001a37a  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001a37e  call    cs:__imp_DeleteCriticalSection
0x18001a385  nop     dword ptr [rax+rax+00h]
0x18001a38a  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x18001a391  mov     [rbx], rax
0x18001a394  add     rsp, 20h
0x18001a398  pop     rbx
0x18001a399  retn
```
