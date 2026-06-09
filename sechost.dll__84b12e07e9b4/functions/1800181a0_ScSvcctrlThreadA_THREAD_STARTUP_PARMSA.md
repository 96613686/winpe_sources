# ScSvcctrlThreadA(_THREAD_STARTUP_PARMSA *)

- ea: `0x1800181a0`
- end: `0x1800181e4`
- name: `?ScSvcctrlThreadA@@YAKPEAU_THREAD_STARTUP_PARMSA@@@Z`
- size: `68`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180051010`

## import_xrefs

- `ntdll!RtlSetThreadSubProcessTag` at `0x1800181ac`
- `ntdll!RtlSetThreadSubProcessTag` at `0x1800181c3`
- `ntdll!RtlSetThreadSubProcessTag` at `0x1800181ac`
- `ntdll!RtlSetThreadSubProcessTag` at `0x1800181c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800181cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800181d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800181cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800181d6`

## pseudocode

```c
__int64 __fastcall ScSvcctrlThreadA(unsigned int *Parameter)
{
  RtlSetThreadSubProcessTag(Parameter[1]);
  (*((void (__fastcall **)(_QWORD, char *))Parameter + 1))(*Parameter, (char *)Parameter + 24);
  RtlSetThreadSubProcessTag(0);
  LocalFree(*((HLOCAL *)Parameter + 2));
  LocalFree(Parameter);
  return 0;
}

```

## disassembly

```asm
0x1800181a0  push    rbx
0x1800181a2  sub     rsp, 20h
0x1800181a6  mov     rbx, rcx
0x1800181a9  mov     ecx, [rcx+4]
0x1800181ac  call    cs:__imp_RtlSetThreadSubProcessTag
0x1800181b2  mov     ecx, [rbx]
0x1800181b4  lea     rdx, [rbx+18h]
0x1800181b8  mov     rax, [rbx+8]
0x1800181bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181c1  xor     ecx, ecx
0x1800181c3  call    cs:__imp_RtlSetThreadSubProcessTag
0x1800181c9  mov     rcx, [rbx+10h]; hMem
0x1800181cd  call    cs:__imp_LocalFree
0x1800181d3  mov     rcx, rbx; hMem
0x1800181d6  call    cs:__imp_LocalFree
0x1800181dc  xor     eax, eax
0x1800181de  add     rsp, 20h
0x1800181e2  pop     rbx
0x1800181e3  retn
```
