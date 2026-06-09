# UserServerDllInitializationWin1

- ea: `0x180001bc0`
- end: `0x180001c42`
- name: `UserServerDllInitializationWin1`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## callers

- `0x180001060`

## import_xrefs

- `ntdll!RtlCreateTagHeap` at `0x180001be6`
- `ntdll!RtlCreateTagHeap` at `0x180001be6`

## pseudocode

```c
__int64 __fastcall UserServerDllInitializationWin1(__int64 a1)
{
  __int64 result; // rax

  MinSrvDllTag = RtlCreateTagHeap(NtCurrentPeb()->ProcessHeap, 0, (PWSTR)L"MINSRV!", (PWSTR)L"TMP");
  *(_QWORD *)(a1 + 88) = UserHardError;
  *(_QWORD *)(a1 + 40) = &MinUserServerApiDispatchTable;
  *(_QWORD *)(a1 + 48) = &MinUserServerApiServerValidTable;
  *(_QWORD *)(a1 + 112) = UserClientShutdown;
  result = 0;
  *(_DWORD *)(a1 + 32) = 1024;
  *(_DWORD *)(a1 + 36) = 1026;
  *(_DWORD *)(a1 + 64) = 8;
  return result;
}

```

## disassembly

```asm
0x180001bc0  push    rbx
0x180001bc2  sub     rsp, 20h
0x180001bc6  mov     rbx, rcx
0x180001bc9  lea     r9, TagSubName; "TMP"
0x180001bd0  mov     rcx, gs:60h
0x180001bd9  lea     r8, TagName; "MINSRV!"
0x180001be0  xor     edx, edx; Flags
0x180001be2  mov     rcx, [rcx+30h]; HeapHandle
0x180001be6  call    cs:__imp_RtlCreateTagHeap
0x180001bed  nop     dword ptr [rax+rax+00h]
0x180001bf2  mov     cs:MinSrvDllTag, eax
0x180001bf8  lea     rax, UserHardError
0x180001bff  mov     [rbx+58h], rax
0x180001c03  lea     rax, MinUserServerApiDispatchTable
0x180001c0a  mov     [rbx+28h], rax
0x180001c0e  lea     rax, MinUserServerApiServerValidTable
0x180001c15  mov     [rbx+30h], rax
0x180001c19  lea     rax, UserClientShutdown
0x180001c20  mov     [rbx+70h], rax
0x180001c24  xor     eax, eax
0x180001c26  mov     dword ptr [rbx+20h], 400h
0x180001c2d  mov     dword ptr [rbx+24h], 402h
0x180001c34  mov     dword ptr [rbx+40h], 8
0x180001c3b  add     rsp, 20h
0x180001c3f  pop     rbx
0x180001c40  retn
```
