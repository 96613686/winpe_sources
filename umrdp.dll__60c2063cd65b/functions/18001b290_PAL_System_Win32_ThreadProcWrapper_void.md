# PAL_System_Win32_ThreadProcWrapper(void *)

- ea: `0x18001b290`
- end: `0x18001b2dc`
- name: `?PAL_System_Win32_ThreadProcWrapper@@YAKPEAX@Z`
- size: `76`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001b290`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b2aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b2aa`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18001b2c5`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18001b2c5`

## pseudocode

```c
__int64 __fastcall PAL_System_Win32_ThreadProcWrapper(__int64 (__fastcall **Parameter)(__int64))
{
  __int64 (__fastcall *v1)(__int64); // rbx
  __int64 (__fastcall *v2)(__int64); // rdi
  HMODULE v3; // rsi
  __int64 result; // rax

  v1 = Parameter[1];
  v2 = *Parameter;
  v3 = (HMODULE)Parameter[2];
  LocalFree(Parameter);
  result = v2((__int64)v1);
  if ( v3 )
    FreeLibraryAndExitThread(v3, result);
  return result;
}

```

## disassembly

```asm
0x18001b290  mov     [rsp+arg_0], rbx
0x18001b295  mov     [rsp+arg_8], rsi
0x18001b29a  push    rdi
0x18001b29b  sub     rsp, 20h
0x18001b29f  mov     rbx, [rcx+8]
0x18001b2a3  mov     rdi, [rcx]
0x18001b2a6  mov     rsi, [rcx+10h]
0x18001b2aa  call    cs:__imp_LocalFree
0x18001b2b0  mov     rcx, rbx
0x18001b2b3  mov     rax, rdi
0x18001b2b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2bb  test    rsi, rsi
0x18001b2be  jz      short loc_18001B2CC
0x18001b2c0  mov     edx, eax; dwExitCode
0x18001b2c2  mov     rcx, rsi; hLibModule
0x18001b2c5  call    cs:__imp_FreeLibraryAndExitThread
0x18001b2cc  mov     rbx, [rsp+28h+arg_0]
0x18001b2d1  mov     rsi, [rsp+28h+arg_8]
0x18001b2d6  add     rsp, 20h
0x18001b2da  pop     rdi
0x18001b2db  retn
```
