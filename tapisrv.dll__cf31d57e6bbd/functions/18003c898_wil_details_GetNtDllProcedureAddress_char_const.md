# wil_details_GetNtDllProcedureAddress(char const *)

- ea: `0x18003c898`
- end: `0x18003c8b8`
- name: `?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z`
- size: `32`
- prototype: `FARPROC __fastcall(const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800362f0`
- `0x18003ad50`
- `0x18003ad90`
- `0x18003d880`
- `0x18003d8f8`
- `0x18003dad0`

## callees

- `0x18003c868`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003c8b1`

## pseudocode

```c
FARPROC __fastcall wil_details_GetNtDllProcedureAddress(const char *a1)
{
  HMODULE NtDllModuleHandle; // rax

  NtDllModuleHandle = wil_details_GetNtDllModuleHandle();
  return GetProcAddress(NtDllModuleHandle, a1);
}

```

## disassembly

```asm
0x18003c898  push    rbx
0x18003c89a  sub     rsp, 20h
0x18003c89e  mov     rbx, rcx
0x18003c8a1  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x18003c8a6  mov     rcx, rax
0x18003c8a9  mov     rdx, rbx
0x18003c8ac  add     rsp, 20h
0x18003c8b0  pop     rbx
0x18003c8b1  jmp     cs:__imp_GetProcAddress
```
