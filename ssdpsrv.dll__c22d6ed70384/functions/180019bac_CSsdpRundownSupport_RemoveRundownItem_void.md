# CSsdpRundownSupport::RemoveRundownItem(void *)

- ea: `0x180019bac`
- end: `0x180019c5c`
- name: `?RemoveRundownItem@CSsdpRundownSupport@@QEAAXPEAX@Z`
- size: `176`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, void *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180015d9c`
- `0x180019734`
- `0x18002021c`
- `0x18002f1f8`

## callees

- `0x180019bac`
- `0x18001d754`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019c19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019c19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019bc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019bc6`

## pseudocode

```c
void __fastcall CSsdpRundownSupport::RemoveRundownItem(LPCRITICAL_SECTION lpCriticalSection, void *a2)
{
  struct _RTL_CRITICAL_SECTION *CriticalSection; // rdi
  LPCRITICAL_SECTION v5; // rbx
  LPCRITICAL_SECTION v6; // rax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rsi
  LPCRITICAL_SECTION v8; // [rsp+40h] [rbp+8h] BYREF

  CriticalSection = 0;
  EnterCriticalSection(lpCriticalSection);
  v5 = lpCriticalSection + 1;
  v8 = lpCriticalSection + 1;
  if ( lpCriticalSection[1].DebugInfo )
  {
    v6 = lpCriticalSection + 1;
    while ( v6 )
    {
      DebugInfo = v5->DebugInfo;
      if ( !v5->DebugInfo )
        break;
      if ( ((unsigned int (__fastcall *)(struct _RTL_CRITICAL_SECTION *, void *))DebugInfo->CriticalSection->DebugInfo->ProcessLocksList.Flink)(
             DebugInfo->CriticalSection,
             a2) )
      {
        CriticalSection = DebugInfo->CriticalSection;
        CUList<CRundownHelperBase *>::Iterator::HrErase(&v8);
        break;
      }
      v5 = (LPCRITICAL_SECTION)v5->DebugInfo;
      if ( v5 )
      {
        v6 = v5;
        v8 = v5;
        if ( v5->DebugInfo )
          continue;
      }
      break;
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( CriticalSection )
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))CriticalSection->DebugInfo->Type)(CriticalSection, 1);
}

```

## disassembly

```asm
0x180019bac  mov     [rsp+arg_8], rbx
0x180019bb1  mov     [rsp+arg_10], rbp
0x180019bb6  push    rsi
0x180019bb7  push    rdi
0x180019bb8  push    r14
0x180019bba  sub     rsp, 20h
0x180019bbe  mov     r14, rdx
0x180019bc1  mov     rbp, rcx
0x180019bc4  xor     edi, edi
0x180019bc6  call    cs:__imp_EnterCriticalSection
0x180019bcc  lea     rbx, [rbp+28h]
0x180019bd0  mov     [rsp+38h+arg_0], rbx
0x180019bd5  cmp     [rbx], rdi
0x180019bd8  jz      short loc_180019C16
0x180019bda  mov     rax, rbx
0x180019bdd  test    rax, rax
0x180019be0  jz      short loc_180019C16
0x180019be2  mov     rsi, [rbx]
0x180019be5  test    rsi, rsi
0x180019be8  jz      short loc_180019C16
0x180019bea  mov     rcx, [rsi+8]
0x180019bee  mov     rdx, r14
0x180019bf1  mov     rax, [rcx]
0x180019bf4  mov     rax, [rax+10h]
0x180019bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bfd  test    eax, eax
0x180019bff  jnz     short loc_180019C37
0x180019c01  mov     rbx, [rbx]
0x180019c04  test    rbx, rbx
0x180019c07  jz      short loc_180019C16
0x180019c09  mov     rax, rbx
0x180019c0c  mov     [rsp+38h+arg_0], rbx
0x180019c11  cmp     [rbx], rdi
0x180019c14  jnz     short loc_180019BDD
0x180019c16  mov     rcx, rbp; lpCriticalSection
0x180019c19  call    cs:__imp_LeaveCriticalSection
0x180019c1f  test    rdi, rdi
0x180019c22  jnz     short loc_180019C47
0x180019c24  mov     rbx, [rsp+38h+arg_8]
0x180019c29  mov     rbp, [rsp+38h+arg_10]
0x180019c2e  add     rsp, 20h
0x180019c32  pop     r14
0x180019c34  pop     rdi
0x180019c35  pop     rsi
0x180019c36  retn
0x180019c37  mov     rdi, [rsi+8]
0x180019c3b  lea     rcx, [rsp+38h+arg_0]
0x180019c40  call    ?HrErase@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJXZ; CUList<CRundownHelperBase *>::Iterator::HrErase(void)
0x180019c45  jmp     short loc_180019C16
0x180019c47  mov     rax, [rdi]
0x180019c4a  mov     edx, 1
0x180019c4f  mov     rcx, rdi
0x180019c52  mov     rax, [rax]
0x180019c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c5a  jmp     short loc_180019C24
```
