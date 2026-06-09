# GetTokenILValue

- ea: `0x180005920`
- end: `0x18000598e`
- name: `GetTokenILValue`
- size: `110`
- prototype: `__int64 __fastcall(void *, ULONG *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003170`

## callees

- `0x180005920`
- `0x1800059a0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180005974`
- `ntdll!RtlFreeHeap` at `0x180005974`
- `ntdll!RtlSubAuthoritySid` at `0x180005950`
- `ntdll!RtlSubAuthoritySid` at `0x180005950`

## pseudocode

```c
__int64 __fastcall GetTokenILValue(void *a1, ULONG *a2)
{
  __int64 result; // rax
  unsigned int v4; // ebx

  result = GetTokenIntegrityLevel(a1);
  v4 = result;
  if ( (int)result >= 0 )
  {
    *a2 = *RtlSubAuthoritySid(MEMORY[0], 0);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, 0);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180005920  mov     [rsp+arg_0], rbx
0x180005925  push    rdi
0x180005926  sub     rsp, 20h
0x18000592a  mov     rdi, rdx
0x18000592d  mov     [rsp+28h+P], 0
0x180005936  lea     rdx, [rsp+28h+P]
0x18000593b  call    GetTokenIntegrityLevel
0x180005940  mov     ebx, eax
0x180005942  test    eax, eax
0x180005944  js      short loc_180005982
0x180005946  mov     rcx, [rsp+28h+P]
0x18000594b  xor     edx, edx; SubAuthority
0x18000594d  mov     rcx, [rcx]; Sid
0x180005950  call    cs:__imp_RtlSubAuthoritySid
0x180005957  nop     dword ptr [rax+rax+00h]
0x18000595c  xor     edx, edx; Flags
0x18000595e  mov     ecx, [rax]
0x180005960  mov     [rdi], ecx
0x180005962  mov     rcx, gs:60h
0x18000596b  mov     r8, [rsp+28h+P]; P
0x180005970  mov     rcx, [rcx+30h]; HeapHandle
0x180005974  call    cs:__imp_RtlFreeHeap
0x18000597b  nop     dword ptr [rax+rax+00h]
0x180005980  mov     eax, ebx
0x180005982  mov     rbx, [rsp+28h+arg_0]
0x180005987  add     rsp, 20h
0x18000598b  pop     rdi
0x18000598c  retn
```
