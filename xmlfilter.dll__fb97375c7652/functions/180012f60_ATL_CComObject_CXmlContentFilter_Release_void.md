# ATL::CComObject<CXmlContentFilter>::Release(void)

- ea: `0x180012f60`
- end: `0x180012fe1`
- name: `?Release@?$CComObject@VCXmlContentFilter@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012ff0`
- `0x180013000`

## callees

- `0x180012f60`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CXmlContentFilter>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 6);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 6, i - 1, i);
        i = *((_DWORD *)a1 + 6) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 64LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180012f60  mov     [rsp+arg_0], rbx
0x180012f65  push    rdi
0x180012f66  sub     rsp, 20h
0x180012f6a  mov     r8d, [rcx+18h]
0x180012f6e  mov     rbx, rcx
0x180012f71  mov     ecx, 7FFFFFFFh
0x180012f76  jmp     short loc_180012F8A
0x180012f78  lea     edx, [r8-1]
0x180012f7c  mov     eax, r8d
0x180012f7f  lock cmpxchg [rbx+18h], edx
0x180012f84  jz      short loc_180012F8F
0x180012f86  mov     r8d, [rbx+18h]
0x180012f8a  cmp     r8d, ecx
0x180012f8d  jnz     short loc_180012F78
0x180012f8f  lea     edi, [r8-1]
0x180012f93  test    edi, edi
0x180012f95  jnz     short loc_180012FD4
0x180012f97  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012f9e  mov     rax, [rcx]
0x180012fa1  mov     rax, [rax+8]
0x180012fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012faa  test    rbx, rbx
0x180012fad  jz      short loc_180012FC1
0x180012faf  mov     rax, [rbx]
0x180012fb2  lea     edx, [rdi+1]
0x180012fb5  mov     rcx, rbx
0x180012fb8  mov     rax, [rax+40h]
0x180012fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fc1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012fc8  mov     rdx, [rcx]
0x180012fcb  mov     rax, [rdx+10h]
0x180012fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fd4  mov     rbx, [rsp+28h+arg_0]
0x180012fd9  mov     eax, edi
0x180012fdb  add     rsp, 20h
0x180012fdf  pop     rdi
0x180012fe0  retn
```
