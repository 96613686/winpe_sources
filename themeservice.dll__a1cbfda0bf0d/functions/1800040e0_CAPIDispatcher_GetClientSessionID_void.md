# CAPIDispatcher::GetClientSessionID(void)

- ea: `0x1800040e0`
- end: `0x180004125`
- name: `?GetClientSessionID@CAPIDispatcher@@QEBAKXZ`
- size: `69`
- prototype: `__int64 __fastcall(CAPIDispatcher *this)`
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## callers

- `0x180002270`
- `0x180003280`
- `0x180003790`
- `0x18000b180`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x18000410e`
- `ntdll!NtQueryInformationProcess` at `0x18000410e`

## pseudocode

```c
__int64 __fastcall CAPIDispatcher::GetClientSessionID(CAPIDispatcher *this)
{
  void *v1; // rcx
  NTSTATUS v2; // eax
  unsigned int v3; // ecx
  unsigned int ProcessInformation; // [rsp+40h] [rbp+8h] BYREF
  ULONG ReturnLength; // [rsp+48h] [rbp+10h] BYREF

  v1 = (void *)*((_QWORD *)this + 12);
  ReturnLength = 0;
  ProcessInformation = 0;
  v2 = NtQueryInformationProcess(v1, ProcessSessionInformation, &ProcessInformation, 4u, &ReturnLength);
  v3 = 0;
  if ( v2 >= 0 )
    return ProcessInformation;
  return v3;
}

```

## disassembly

```asm
0x1800040e0  push    rbx
0x1800040e2  sub     rsp, 30h
0x1800040e6  mov     rcx, [rcx+60h]; ProcessHandle
0x1800040ea  lea     rax, [rsp+38h+arg_8]
0x1800040ef  xor     ebx, ebx
0x1800040f1  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800040f6  mov     r9d, 4; ProcessInformationLength
0x1800040fc  mov     [rsp+38h+arg_8], ebx
0x180004100  lea     r8, [rsp+38h+ProcessInformation]; ProcessInformation
0x180004105  mov     [rsp+38h+ProcessInformation], ebx
0x180004109  mov     edx, 18h; ProcessInformationClass
0x18000410e  call    cs:__imp_NtQueryInformationProcess
0x180004114  test    eax, eax
0x180004116  mov     ecx, ebx
0x180004118  cmovns  ecx, [rsp+38h+ProcessInformation]
0x18000411d  mov     eax, ecx
0x18000411f  add     rsp, 30h
0x180004123  pop     rbx
0x180004124  retn
```
