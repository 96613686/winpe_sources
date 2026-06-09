# UserClientShutdownWorker

- ea: `0x18000a500`
- end: `0x18000a58b`
- name: `UserClientShutdownWorker`
- size: `139`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a1c0`

## callees

- `0x180009688`
- `0x18000a500`

## import_xrefs

- `ntdll!RtlRegisterThreadWithCsrss` at `0x18000a50d`
- `ntdll!RtlRegisterThreadWithCsrss` at `0x18000a50d`
- `ntdll!NtSetEvent` at `0x18000a55c`
- `ntdll!NtSetEvent` at `0x18000a55c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a571`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a571`

## pseudocode

```c
__int64 __fastcall UserClientShutdownWorker(char *hMem)
{
  _DWORD *v2; // rbx

  RtlRegisterThreadWithCsrss();
  v2 = (_DWORD *)*((_QWORD *)hMem + 2);
  *v2 = UserClientShutdown(
          *((_QWORD **)hMem + 4),
          *((_DWORD *)hMem + 10),
          hMem[44] & 1,
          *((_DWORD *)hMem + 12),
          *(union _LARGE_INTEGER *)(hMem + 24));
  if ( *((_QWORD *)hMem + 1) && _InterlockedExchangeAdd(*(volatile signed __int32 **)hMem, 0xFFFFFFFF) == 1 )
    NtSetEvent(*((HANDLE *)hMem + 1), 0);
  if ( (hMem[44] & 2) != 0 )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x18000a500  mov     [rsp+arg_0], rbx
0x18000a505  push    rdi
0x18000a506  sub     rsp, 30h
0x18000a50a  mov     rdi, rcx
0x18000a50d  call    cs:__imp_RtlRegisterThreadWithCsrss
0x18000a514  nop     dword ptr [rax+rax+00h]
0x18000a519  mov     r8b, [rdi+2Ch]
0x18000a51d  mov     rax, [rdi+18h]
0x18000a521  and     r8b, 1
0x18000a525  mov     r9d, [rdi+30h]
0x18000a529  mov     edx, [rdi+28h]
0x18000a52c  mov     rcx, [rdi+20h]
0x18000a530  mov     rbx, [rdi+10h]
0x18000a534  mov     [rsp+38h+var_18], rax
0x18000a539  call    UserClientShutdown
0x18000a53e  mov     [rbx], eax
0x18000a540  cmp     qword ptr [rdi+8], 0
0x18000a545  jz      short loc_18000A568
0x18000a547  mov     rcx, [rdi]
0x18000a54a  or      eax, 0FFFFFFFFh
0x18000a54d  lock xadd [rcx], eax
0x18000a551  cmp     eax, 1
0x18000a554  jnz     short loc_18000A568
0x18000a556  mov     rcx, [rdi+8]; EventHandle
0x18000a55a  xor     edx, edx; PreviousState
0x18000a55c  call    cs:__imp_NtSetEvent
0x18000a563  nop     dword ptr [rax+rax+00h]
0x18000a568  test    byte ptr [rdi+2Ch], 2
0x18000a56c  jz      short loc_18000A57D
0x18000a56e  mov     rcx, rdi; hMem
0x18000a571  call    cs:__imp_LocalFree
0x18000a578  nop     dword ptr [rax+rax+00h]
0x18000a57d  mov     rbx, [rsp+38h+arg_0]
0x18000a582  xor     eax, eax
0x18000a584  add     rsp, 30h
0x18000a588  pop     rdi
0x18000a589  retn
```
