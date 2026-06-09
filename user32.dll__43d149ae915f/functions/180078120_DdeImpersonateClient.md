# DdeImpersonateClient

- ea: `0x180078120`
- end: `0x18007819b`
- name: `DdeImpersonateClient`
- size: `123`
- prototype: `BOOL __stdcall(HCONV hConv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800482c4`
- `0x1800483d4`
- `0x18004888c`
- `0x180078120`

## import_xrefs

- `win32u!NtUserImpersonateDdeClientWindow` at `0x180078174`
- `win32u!NtUserImpersonateDdeClientWindow` at `0x180078174`
- `ntdll!RtlEnterCriticalSection` at `0x18007813b`
- `ntdll!RtlEnterCriticalSection` at `0x18007813b`
- `ntdll!RtlLeaveCriticalSection` at `0x180078183`
- `ntdll!RtlLeaveCriticalSection` at `0x180078183`

## pseudocode

```c
BOOL __stdcall DdeImpersonateClient(HCONV hConv)
{
  int v2; // edi
  unsigned int v3; // ecx
  unsigned __int64 v4; // rbx

  v2 = 0;
  RtlEnterCriticalSection(&gcsDDEML);
  v4 = ValidateCHandle(hConv, 2u, 0xFFFFFFFF);
  if ( v4 && PciiFromHandle(hConv) )
    v2 = NtUserImpersonateDdeClientWindow(*(_QWORD *)(v4 + 40), *(_QWORD *)(v4 + 48));
  else
    BestSetLastDDEMLError(v3);
  RtlLeaveCriticalSection(&gcsDDEML);
  return v2;
}

```

## disassembly

```asm
0x180078120  mov     [rsp+arg_0], rbx
0x180078125  mov     [rsp+arg_8], rsi
0x18007812a  push    rdi
0x18007812b  sub     rsp, 20h
0x18007812f  mov     rsi, rcx
0x180078132  xor     edi, edi
0x180078134  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18007813b  call    cs:__imp_RtlEnterCriticalSection
0x180078141  or      r8d, 0FFFFFFFFh; unsigned int
0x180078145  lea     edx, [rdi+2]; unsigned int
0x180078148  mov     rcx, rsi; void *
0x18007814b  call    ?ValidateCHandle@@YA_KPEAXKK@Z; ValidateCHandle(void *,ulong,ulong)
0x180078150  mov     rbx, rax
0x180078153  test    rax, rax
0x180078156  jnz     short loc_18007815F
0x180078158  call    ?BestSetLastDDEMLError@@YAXK@Z; BestSetLastDDEMLError(ulong)
0x18007815d  jmp     short loc_18007817C
0x18007815f  mov     rcx, rsi; void *
0x180078162  call    ?PciiFromHandle@@YAPEAUtagCL_INSTANCE_INFO@@PEAX@Z; PciiFromHandle(void *)
0x180078167  test    rax, rax
0x18007816a  jz      short loc_180078158
0x18007816c  mov     rdx, [rbx+30h]
0x180078170  mov     rcx, [rbx+28h]
0x180078174  call    cs:__imp_NtUserImpersonateDdeClientWindow
0x18007817a  mov     edi, eax
0x18007817c  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180078183  call    cs:__imp_RtlLeaveCriticalSection
0x180078189  mov     rbx, [rsp+28h+arg_0]
0x18007818e  mov     eax, edi
0x180078190  mov     rsi, [rsp+28h+arg_8]
0x180078195  add     rsp, 20h
0x180078199  pop     rdi
0x18007819a  retn
```
