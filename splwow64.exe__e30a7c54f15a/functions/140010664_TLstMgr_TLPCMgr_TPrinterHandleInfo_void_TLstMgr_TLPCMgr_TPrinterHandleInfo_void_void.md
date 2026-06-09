# TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::~TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>(void)

- ea: `0x140010664`
- end: `0x1400106e4`
- name: `??1?$TLstMgr@VTPrinterHandleInfo@TLPCMgr@@PEAX@@QEAA@XZ`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1400107a0`
- `0x1400108dc`

## callees

- `0x140001b90`
- `0x140010664`
- `0x140016010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400106dd`
- `KERNEL32!EnterCriticalSection` at `0x14001067d`
- `KERNEL32!EnterCriticalSection` at `0x14001067d`
- `KERNEL32!LeaveCriticalSection` at `0x1400106c5`
- `KERNEL32!LeaveCriticalSection` at `0x1400106c5`

## pseudocode

```c
void __fastcall TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::~TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  _QWORD *v3; // rdi

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  while ( 1 )
  {
    v3 = *(_QWORD **)(a1 + 32);
    if ( !v3 )
      break;
    *(_QWORD *)(a1 + 32) = v3[1];
    if ( *v3 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 16LL))(*v3);
    operator delete(v3);
  }
  *(_DWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
}

```

## disassembly

```asm
0x140010664  mov     [rsp+arg_0], rbx
0x140010669  mov     [rsp+arg_8], rsi
0x14001066e  push    rdi
0x14001066f  sub     rsp, 20h
0x140010673  lea     rsi, [rcx+38h]
0x140010677  mov     rbx, rcx
0x14001067a  mov     rcx, rsi; lpCriticalSection
0x14001067d  call    cs:__imp_EnterCriticalSection
0x140010683  jmp     short loc_1400106AE
0x140010685  mov     rax, [rdi+8]
0x140010689  mov     [rbx+20h], rax
0x14001068d  mov     rcx, [rdi]
0x140010690  test    rcx, rcx
0x140010693  jz      short loc_1400106A1
0x140010695  mov     rax, [rcx]
0x140010698  mov     rax, [rax+10h]
0x14001069c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400106a1  mov     edx, 18h
0x1400106a6  mov     rcx, rdi; Block
0x1400106a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400106ae  mov     rdi, [rbx+20h]
0x1400106b2  test    rdi, rdi
0x1400106b5  jnz     short loc_140010685
0x1400106b7  mov     rcx, rsi; lpCriticalSection
0x1400106ba  mov     [rbx+30h], edi
0x1400106bd  mov     [rbx+28h], rdi
0x1400106c1  mov     [rbx+20h], rdi
0x1400106c5  call    cs:__imp_LeaveCriticalSection
0x1400106cb  mov     rcx, rsi
0x1400106ce  mov     rbx, [rsp+28h+arg_0]
0x1400106d3  mov     rsi, [rsp+28h+arg_8]
0x1400106d8  add     rsp, 20h
0x1400106dc  pop     rdi
0x1400106dd  jmp     cs:__imp_DeleteCriticalSection
```
