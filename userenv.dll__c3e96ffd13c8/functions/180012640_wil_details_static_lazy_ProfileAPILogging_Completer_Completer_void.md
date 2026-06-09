# wil::details::static_lazy<ProfileAPILogging>::Completer::~Completer(void)

- ea: `0x180012640`
- end: `0x18001269a`
- name: `??1Completer@?$static_lazy@VProfileAPILogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cc34`

## callees

- `0x180001c7c`
- `0x180012640`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180012693`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<ProfileAPILogging>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    *(_QWORD *)(v2 + 16) = *(_QWORD *)(*(_QWORD *)a1 + 32LL);
    *(_BYTE *)(v2 + 24) = 1;
    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation();
    v3 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v3 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180012640  mov     [rsp+arg_0], rbx
0x180012645  push    rdi
0x180012646  sub     rsp, 20h
0x18001264a  cmp     dword ptr [rcx+8], 0
0x18001264e  mov     rdi, rcx
0x180012651  jnz     short loc_18001267F
0x180012653  mov     rbx, [rcx]
0x180012656  mov     rcx, [rbx+20h]
0x18001265a  mov     [rbx+10h], rcx
0x18001265e  mov     byte ptr [rbx+18h], 1
0x180012662  call    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation
0x180012667  mov     rax, [rbx+8]
0x18001266b  lea     rcx, [rbx+8]
0x18001266f  mov     dword ptr [rbx+1Ch], 1
0x180012676  mov     rax, [rax+8]
0x18001267a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001267f  mov     rcx, [rdi]
0x180012682  mov     edx, [rdi+8]
0x180012685  lea     r8, [rcx+8]
0x180012689  mov     rbx, [rsp+28h+arg_0]
0x18001268e  add     rsp, 20h
0x180012692  pop     rdi
0x180012693  jmp     cs:__imp_InitOnceComplete
```
