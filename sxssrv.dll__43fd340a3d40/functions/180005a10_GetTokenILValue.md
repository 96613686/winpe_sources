# GetTokenILValue

- ea: `0x180005a10`
- end: `0x180005a86`
- name: `GetTokenILValue`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003310`

## callees

- `0x180005a10`
- `0x180005a90`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180005a67`
- `ntdll!RtlFreeHeap` at `0x180005a67`
- `ntdll!RtlSubAuthoritySid` at `0x180005a45`
- `ntdll!RtlSubAuthoritySid` at `0x180005a45`

## pseudocode

```c
__int64 __fastcall GetTokenILValue(void *a1, ULONG *a2)
{
  __int64 result; // rax
  unsigned int v4; // ebx
  PVOID v5; // rdi
  PVOID P; // [rsp+40h] [rbp+18h] BYREF

  P = 0;
  result = GetTokenIntegrityLevel(a1, &P);
  v4 = result;
  if ( (int)result >= 0 )
  {
    v5 = P;
    *a2 = *RtlSubAuthoritySid(*(PSID *)P, 0);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180005a10  mov     [rsp+arg_8], rbx
0x180005a15  push    rsi
0x180005a16  sub     rsp, 20h
0x180005a1a  mov     rsi, rdx
0x180005a1d  mov     [rsp+28h+P], 0
0x180005a26  lea     rdx, [rsp+28h+P]
0x180005a2b  call    GetTokenIntegrityLevel
0x180005a30  mov     ebx, eax
0x180005a32  test    eax, eax
0x180005a34  js      short loc_180005A7A
0x180005a36  mov     [rsp+28h+arg_0], rdi
0x180005a3b  xor     edx, edx; SubAuthority
0x180005a3d  mov     rdi, [rsp+28h+P]
0x180005a42  mov     rcx, [rdi]; Sid
0x180005a45  call    cs:__imp_RtlSubAuthoritySid
0x180005a4c  nop     dword ptr [rax+rax+00h]
0x180005a51  mov     r8, rdi; P
0x180005a54  xor     edx, edx; Flags
0x180005a56  mov     ecx, [rax]
0x180005a58  mov     [rsi], ecx
0x180005a5a  mov     rcx, gs:60h
0x180005a63  mov     rcx, [rcx+30h]; HeapHandle
0x180005a67  call    cs:__imp_RtlFreeHeap
0x180005a6e  nop     dword ptr [rax+rax+00h]
0x180005a73  mov     rdi, [rsp+28h+arg_0]
0x180005a78  mov     eax, ebx
0x180005a7a  mov     rbx, [rsp+28h+arg_8]
0x180005a7f  add     rsp, 20h
0x180005a83  pop     rsi
0x180005a84  retn
```
