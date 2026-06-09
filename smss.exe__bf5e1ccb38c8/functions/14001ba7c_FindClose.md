# FindClose

- ea: `0x14001ba7c`
- end: `0x14001bb47`
- name: `FindClose`
- size: `203`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001ae48`

## callees

- `0x14001ba7c`
- `0x14001cabc`

## import_xrefs

- `ntdll!NtClose` at `0x14001bad9`
- `ntdll!NtClose` at `0x14001bad9`
- `ntdll!RtlFreeHeap` at `0x14001bafa`
- `ntdll!RtlFreeHeap` at `0x14001bb1b`
- `ntdll!RtlFreeHeap` at `0x14001bafa`
- `ntdll!RtlFreeHeap` at `0x14001bb1b`
- `ntdll!RtlSetLastWin32Error` at `0x14001ba9f`
- `ntdll!RtlSetLastWin32Error` at `0x14001ba9f`
- `ntdll!RtlEnterCriticalSection` at `0x14001bab1`
- `ntdll!RtlEnterCriticalSection` at `0x14001bab1`
- `ntdll!RtlLeaveCriticalSection` at `0x14001bad0`
- `ntdll!RtlLeaveCriticalSection` at `0x14001bad0`
- `ntdll!RtlDeleteCriticalSection` at `0x14001bb03`
- `ntdll!RtlDeleteCriticalSection` at `0x14001bb03`

## pseudocode

```c
__int64 __fastcall FindClose(struct _RTL_CRITICAL_SECTION *BaseAddress)
{
  struct _RTL_CRITICAL_SECTION *v3; // r14
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rbx
  void *v5; // rsi
  NTSTATUS v6; // eax

  if ( BaseAddress == (struct _RTL_CRITICAL_SECTION *)1 )
    return 1;
  if ( BaseAddress == (struct _RTL_CRITICAL_SECTION *)-1LL )
  {
    RtlSetLastWin32Error(6u);
    return 0;
  }
  else
  {
    v3 = BaseAddress + 1;
    RtlEnterCriticalSection(BaseAddress + 1);
    DebugInfo = BaseAddress->DebugInfo;
    v5 = *(void **)&BaseAddress->LockCount;
    BaseAddress->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)-1LL;
    *(_QWORD *)&BaseAddress->LockCount = 0;
    RtlLeaveCriticalSection(v3);
    v6 = NtClose(DebugInfo);
    if ( v6 < 0 )
    {
      BaseSetLastNTError((unsigned int)v6);
      return 0;
    }
    else
    {
      if ( v5 )
        RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v5);
      RtlDeleteCriticalSection(v3);
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, BaseAddress);
      return 1;
    }
  }
}

```

## disassembly

```asm
0x14001ba7c  push    rbx
0x14001ba7e  push    rsi
0x14001ba7f  push    rdi
0x14001ba80  push    r14
0x14001ba82  sub     rsp, 28h
0x14001ba86  mov     rdi, rcx
0x14001ba89  cmp     rcx, 1
0x14001ba8d  jnz     short loc_14001BA96
0x14001ba8f  mov     eax, ecx
0x14001ba91  jmp     loc_14001BB3D
0x14001ba96  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14001ba9a  jnz     short loc_14001BAAA
0x14001ba9c  lea     ecx, [rdi+7]; LastError
0x14001ba9f  call    cs:__imp_RtlSetLastWin32Error
0x14001baa5  jmp     loc_14001BB3B
0x14001baaa  lea     r14, [rcx+28h]
0x14001baae  mov     rcx, r14; CriticalSection
0x14001bab1  call    cs:__imp_RtlEnterCriticalSection
0x14001bab7  mov     rbx, [rdi]
0x14001baba  mov     rsi, [rdi+8]
0x14001babe  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x14001bac5  mov     qword ptr [rdi+8], 0
0x14001bacd  mov     rcx, r14; CriticalSection
0x14001bad0  call    cs:__imp_RtlLeaveCriticalSection
0x14001bad6  mov     rcx, rbx; Handle
0x14001bad9  call    cs:__imp_NtClose
0x14001badf  test    eax, eax
0x14001bae1  js      short loc_14001BB28
0x14001bae3  test    rsi, rsi
0x14001bae6  jz      short loc_14001BB00
0x14001bae8  mov     rcx, gs:60h
0x14001baf1  mov     r8, rsi; BaseAddress
0x14001baf4  xor     edx, edx; Flags
0x14001baf6  mov     rcx, [rcx+30h]; HeapHandle
0x14001bafa  call    cs:__imp_RtlFreeHeap
0x14001bb00  mov     rcx, r14; CriticalSection
0x14001bb03  call    cs:__imp_RtlDeleteCriticalSection
0x14001bb09  mov     rcx, gs:60h
0x14001bb12  mov     r8, rdi; BaseAddress
0x14001bb15  xor     edx, edx; Flags
0x14001bb17  mov     rcx, [rcx+30h]; HeapHandle
0x14001bb1b  call    cs:__imp_RtlFreeHeap
0x14001bb21  mov     eax, 1
0x14001bb26  jmp     short loc_14001BB3D
0x14001bb28  mov     ecx, eax
0x14001bb2a  call    BaseSetLastNTError
0x14001bb2f  xor     eax, eax
0x14001bb31  jmp     short loc_14001BB3D
0x14001bb33  mov     ecx, eax
0x14001bb35  call    BaseSetLastNTError
0x14001bb3a  nop
0x14001bb3b  xor     eax, eax
0x14001bb3d  add     rsp, 28h
0x14001bb41  pop     r14
0x14001bb43  pop     rdi
0x14001bb44  pop     rsi
0x14001bb45  pop     rbx
0x14001bb46  retn
0x14001d00d  push    rbp
0x14001d00f  sub     rsp, 20h
0x14001d013  mov     rbp, rdx
0x14001d016  mov     rax, [rcx]
0x14001d019  xor     ecx, ecx
0x14001d01b  cmp     dword ptr [rax], 0C00000FDh
0x14001d021  setnz   cl
0x14001d024  mov     eax, ecx
0x14001d026  add     rsp, 20h
0x14001d02a  pop     rbp
0x14001d02b  retn
```
