# CSsdpRundownSupport::RemoveRundownItem(void *)

- ea: `0x18001aeb4`
- end: `0x18001af71`
- name: `?RemoveRundownItem@CSsdpRundownSupport@@QEAAXPEAX@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, void *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180018128`
- `0x18001a988`
- `0x1800218ac`
- `0x180031468`

## callees

- `0x18000b5e4`
- `0x18001aeb4`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001af27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001af27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aece`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aece`

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
        CUList<void *>::Iterator::HrErase(&v8);
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
0x18001aeb4  mov     [rsp+arg_8], rbx
0x18001aeb9  mov     [rsp+arg_10], rbp
0x18001aebe  push    rsi
0x18001aebf  push    rdi
0x18001aec0  push    r14
0x18001aec2  sub     rsp, 20h
0x18001aec6  mov     r14, rdx
0x18001aec9  mov     rbp, rcx
0x18001aecc  xor     edi, edi
0x18001aece  call    cs:__imp_EnterCriticalSection
0x18001aed5  nop     dword ptr [rax+rax+00h]
0x18001aeda  lea     rbx, [rbp+28h]
0x18001aede  mov     [rsp+38h+arg_0], rbx
0x18001aee3  cmp     [rbx], rdi
0x18001aee6  jz      short loc_18001AF24
0x18001aee8  mov     rax, rbx
0x18001aeeb  test    rax, rax
0x18001aeee  jz      short loc_18001AF24
0x18001aef0  mov     rsi, [rbx]
0x18001aef3  test    rsi, rsi
0x18001aef6  jz      short loc_18001AF24
0x18001aef8  mov     rcx, [rsi+8]
0x18001aefc  mov     rdx, r14
0x18001aeff  mov     rax, [rcx]
0x18001af02  mov     rax, [rax+10h]
0x18001af06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af0b  test    eax, eax
0x18001af0d  jnz     short loc_18001AF4C
0x18001af0f  mov     rbx, [rbx]
0x18001af12  test    rbx, rbx
0x18001af15  jz      short loc_18001AF24
0x18001af17  mov     rax, rbx
0x18001af1a  mov     [rsp+38h+arg_0], rbx
0x18001af1f  cmp     [rbx], rdi
0x18001af22  jnz     short loc_18001AEEB
0x18001af24  mov     rcx, rbp; lpCriticalSection
0x18001af27  call    cs:__imp_LeaveCriticalSection
0x18001af2e  nop     dword ptr [rax+rax+00h]
0x18001af33  test    rdi, rdi
0x18001af36  jnz     short loc_18001AF5C
0x18001af38  mov     rbx, [rsp+38h+arg_8]
0x18001af3d  mov     rbp, [rsp+38h+arg_10]
0x18001af42  add     rsp, 20h
0x18001af46  pop     r14
0x18001af48  pop     rdi
0x18001af49  pop     rsi
0x18001af4a  retn
0x18001af4c  mov     rdi, [rsi+8]
0x18001af50  lea     rcx, [rsp+38h+arg_0]
0x18001af55  call    ?HrErase@Iterator@?$CUList@PEAX@@QEAAJXZ; CUList<void *>::Iterator::HrErase(void)
0x18001af5a  jmp     short loc_18001AF24
0x18001af5c  mov     rax, [rdi]
0x18001af5f  mov     edx, 1
0x18001af64  mov     rcx, rdi
0x18001af67  mov     rax, [rax]
0x18001af6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af6f  jmp     short loc_18001AF38
```
