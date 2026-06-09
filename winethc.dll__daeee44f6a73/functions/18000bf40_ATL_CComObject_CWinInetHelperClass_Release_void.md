# ATL::CComObject<CWinInetHelperClass>::Release(void)

- ea: `0x18000bf40`
- end: `0x18000bfc5`
- name: `?Release@?$CComObject@VCWinInetHelperClass@@@ATL@@UEAAKXZ`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bfd0`
- `0x18000bfe0`

## callees

- `0x18000bf40`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWinInetHelperClass>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 16);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 16, i - 1, i);
        i = *((_DWORD *)a1 + 16) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 168LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x18000bf40  mov     [rsp+arg_0], rbx
0x18000bf45  push    rdi
0x18000bf46  sub     rsp, 20h
0x18000bf4a  mov     r8d, [rcx+40h]
0x18000bf4e  mov     rbx, rcx
0x18000bf51  mov     ecx, 7FFFFFFFh
0x18000bf56  jmp     short loc_18000BF6A
0x18000bf58  lea     edx, [r8-1]
0x18000bf5c  mov     eax, r8d
0x18000bf5f  lock cmpxchg [rbx+40h], edx
0x18000bf64  jz      short loc_18000BF6F
0x18000bf66  mov     r8d, [rbx+40h]
0x18000bf6a  cmp     r8d, ecx
0x18000bf6d  jnz     short loc_18000BF58
0x18000bf6f  lea     edi, [r8-1]
0x18000bf73  test    edi, edi
0x18000bf75  jnz     short loc_18000BFB7
0x18000bf77  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000bf7e  mov     rax, [rcx]
0x18000bf81  mov     rax, [rax+8]
0x18000bf85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf8a  test    rbx, rbx
0x18000bf8d  jz      short loc_18000BFA4
0x18000bf8f  mov     rax, [rbx]
0x18000bf92  lea     edx, [rdi+1]
0x18000bf95  mov     rcx, rbx
0x18000bf98  mov     rax, [rax+0A8h]
0x18000bf9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfa4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000bfab  mov     rdx, [rcx]
0x18000bfae  mov     rax, [rdx+10h]
0x18000bfb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfb7  mov     rbx, [rsp+28h+arg_0]
0x18000bfbc  mov     eax, edi
0x18000bfbe  add     rsp, 20h
0x18000bfc2  pop     rdi
0x18000bfc3  retn
```
