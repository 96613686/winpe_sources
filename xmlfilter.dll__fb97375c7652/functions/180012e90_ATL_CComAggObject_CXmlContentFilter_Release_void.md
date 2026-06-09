# ATL::CComAggObject<CXmlContentFilter>::Release(void)

- ea: `0x180012e90`
- end: `0x180012f11`
- name: `?Release@?$CComAggObject@VCXmlContentFilter@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012e90`
- `0x180017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComAggObject<CXmlContentFilter>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180012e90  mov     [rsp+arg_0], rbx
0x180012e95  push    rdi
0x180012e96  sub     rsp, 20h
0x180012e9a  mov     r8d, [rcx+8]
0x180012e9e  mov     rbx, rcx
0x180012ea1  mov     ecx, 7FFFFFFFh
0x180012ea6  jmp     short loc_180012EBA
0x180012ea8  lea     edx, [r8-1]
0x180012eac  mov     eax, r8d
0x180012eaf  lock cmpxchg [rbx+8], edx
0x180012eb4  jz      short loc_180012EBF
0x180012eb6  mov     r8d, [rbx+8]
0x180012eba  cmp     r8d, ecx
0x180012ebd  jnz     short loc_180012EA8
0x180012ebf  lea     edi, [r8-1]
0x180012ec3  test    edi, edi
0x180012ec5  jnz     short loc_180012F04
0x180012ec7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012ece  mov     rax, [rcx]
0x180012ed1  mov     rax, [rax+8]
0x180012ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012eda  test    rbx, rbx
0x180012edd  jz      short loc_180012EF1
0x180012edf  mov     rax, [rbx]
0x180012ee2  lea     edx, [rdi+1]
0x180012ee5  mov     rcx, rbx
0x180012ee8  mov     rax, [rax+18h]
0x180012eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ef1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012ef8  mov     rdx, [rcx]
0x180012efb  mov     rax, [rdx+10h]
0x180012eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f04  mov     rbx, [rsp+28h+arg_0]
0x180012f09  mov     eax, edi
0x180012f0b  add     rsp, 20h
0x180012f0f  pop     rdi
0x180012f10  retn
```
