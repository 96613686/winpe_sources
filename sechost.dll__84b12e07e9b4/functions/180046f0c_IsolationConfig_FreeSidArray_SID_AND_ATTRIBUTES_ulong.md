# IsolationConfig::FreeSidArray(_SID_AND_ATTRIBUTES *,ulong)

- ea: `0x180046f0c`
- end: `0x180046f7e`
- name: `?FreeSidArray@IsolationConfig@@SAXPEAU_SID_AND_ATTRIBUTES@@K@Z`
- size: `114`
- prototype: `void __fastcall(struct _SID_AND_ATTRIBUTES *lpMem, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001a2a8`
- `0x180042c50`

## callees

- `0x180046f0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046f68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046f68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046f5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046f5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046f3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046f3a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180046f54`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180046f54`

## pseudocode

```c
void __fastcall IsolationConfig::FreeSidArray(struct _SID_AND_ATTRIBUTES *lpMem, int a2)
{
  unsigned int v2; // esi
  unsigned int v3; // edi
  PSID Sid; // rcx
  PSID v6; // rcx
  HANDLE ProcessHeap; // rax

  if ( lpMem )
  {
    v2 = a2 - 1;
    v3 = 0;
    if ( a2 != 1 )
    {
      do
      {
        Sid = lpMem[v3].Sid;
        if ( Sid )
          LocalFree(Sid);
        ++v3;
      }
      while ( v3 < v2 );
    }
    v6 = lpMem[v2].Sid;
    if ( v6 )
      FreeSid(v6);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x180046f0c  test    rcx, rcx
0x180046f0f  jz      short locret_180046F7D
0x180046f11  mov     [rsp+arg_0], rbx
0x180046f16  mov     [rsp+arg_8], rsi
0x180046f1b  push    rdi
0x180046f1c  sub     rsp, 20h
0x180046f20  lea     esi, [rdx-1]
0x180046f23  xor     edi, edi
0x180046f25  mov     rbx, rcx
0x180046f28  test    esi, esi
0x180046f2a  jz      short loc_180046F46
0x180046f2c  mov     eax, edi
0x180046f2e  add     rax, rax
0x180046f31  mov     rcx, [rbx+rax*8]; hMem
0x180046f35  test    rcx, rcx
0x180046f38  jz      short loc_180046F40
0x180046f3a  call    cs:__imp_LocalFree
0x180046f40  inc     edi
0x180046f42  cmp     edi, esi
0x180046f44  jb      short loc_180046F2C
0x180046f46  mov     eax, esi
0x180046f48  add     rax, rax
0x180046f4b  mov     rcx, [rbx+rax*8]; pSid
0x180046f4f  test    rcx, rcx
0x180046f52  jz      short loc_180046F5A
0x180046f54  call    cs:__imp_FreeSid
0x180046f5a  call    cs:__imp_GetProcessHeap
0x180046f60  mov     r8, rbx; lpMem
0x180046f63  xor     edx, edx; dwFlags
0x180046f65  mov     rcx, rax; hHeap
0x180046f68  call    cs:__imp_HeapFree
0x180046f6e  mov     rbx, [rsp+28h+arg_0]
0x180046f73  mov     rsi, [rsp+28h+arg_8]
0x180046f78  add     rsp, 20h
0x180046f7c  pop     rdi
0x180046f7d  retn
```
