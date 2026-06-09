# CNtSecurityDescriptor::operator=(CNtSecurityDescriptor &)

- ea: `0x180025e00`
- end: `0x180025e85`
- name: `??4CNtSecurityDescriptor@@QEAAAEAV0@AEAV0@@Z`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003aa90`
- `0x18003d310`

## callees

- `0x18000a290`
- `0x18000ab30`
- `0x180025e00`
- `0x18002ee96`
- `0x1800442d3`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180025e37`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180025e37`

## pseudocode

```c
__int64 __fastcall CNtSecurityDescriptor::operator=(__int64 a1, __int64 a2)
{
  void *v4; // rcx
  ULONG v5; // esi
  void *v6; // rax

  v4 = *(void **)a1;
  if ( v4 )
  {
    CMUILocale::_Free(v4);
    *(_QWORD *)a1 = 0;
  }
  *(_DWORD *)(a1 + 8) = *(_DWORD *)(a2 + 8);
  if ( *(_QWORD *)a2 )
  {
    v5 = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)a2);
    v6 = CWin32DefaultArena::WbemMemAlloc(v5);
    *(_QWORD *)a1 = v6;
    if ( v6 )
    {
      memset_0(v6, 0, v5);
      memcpy_0(*(void **)a1, *(const void **)a2, v5);
    }
    else
    {
      *(_DWORD *)(a1 + 8) = 2;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180025e00  mov     [rsp+arg_0], rbx
0x180025e05  mov     [rsp+arg_8], rsi
0x180025e0a  push    rdi
0x180025e0b  sub     rsp, 20h
0x180025e0f  mov     rbx, rcx
0x180025e12  mov     rdi, rdx
0x180025e15  mov     rcx, [rcx]; void *
0x180025e18  test    rcx, rcx
0x180025e1b  jz      short loc_180025E29
0x180025e1d  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x180025e22  mov     qword ptr [rbx], 0
0x180025e29  mov     eax, [rdi+8]
0x180025e2c  mov     [rbx+8], eax
0x180025e2f  mov     rcx, [rdi]; SecurityDescriptor
0x180025e32  test    rcx, rcx
0x180025e35  jz      short loc_180025E69
0x180025e37  call    cs:__imp_RtlLengthSecurityDescriptor
0x180025e3d  mov     ecx, eax; unsigned __int64
0x180025e3f  mov     esi, eax
0x180025e41  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180025e46  mov     [rbx], rax
0x180025e49  test    rax, rax
0x180025e4c  jz      short loc_180025E7C
0x180025e4e  mov     r8d, esi; Size
0x180025e51  xor     edx, edx; Val
0x180025e53  mov     rcx, rax; void *
0x180025e56  call    memset_0
0x180025e5b  mov     rdx, [rdi]; Src
0x180025e5e  mov     r8d, esi; Size
0x180025e61  mov     rcx, [rbx]; void *
0x180025e64  call    memcpy_0
0x180025e69  mov     rsi, [rsp+28h+arg_8]
0x180025e6e  mov     rax, rbx
0x180025e71  mov     rbx, [rsp+28h+arg_0]
0x180025e76  add     rsp, 20h
0x180025e7a  pop     rdi
0x180025e7b  retn
0x180025e7c  mov     dword ptr [rbx+8], 2
0x180025e83  jmp     short loc_180025E69
```
