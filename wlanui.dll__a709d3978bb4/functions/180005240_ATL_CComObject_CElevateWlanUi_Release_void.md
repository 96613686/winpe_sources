# ATL::CComObject<CElevateWlanUi>::Release(void)

- ea: `0x180005240`
- end: `0x1800052c1`
- name: `?Release@?$CComObject@VCElevateWlanUi@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005240`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CElevateWlanUi>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 48LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180005240  mov     [rsp+arg_0], rbx
0x180005245  push    rdi
0x180005246  sub     rsp, 20h
0x18000524a  mov     r8d, [rcx+8]
0x18000524e  mov     rbx, rcx
0x180005251  mov     ecx, 7FFFFFFFh
0x180005256  jmp     short loc_18000526A
0x180005258  lea     edx, [r8-1]
0x18000525c  mov     eax, r8d
0x18000525f  lock cmpxchg [rbx+8], edx
0x180005264  jz      short loc_18000526F
0x180005266  mov     r8d, [rbx+8]
0x18000526a  cmp     r8d, ecx
0x18000526d  jnz     short loc_180005258
0x18000526f  lea     edi, [r8-1]
0x180005273  test    edi, edi
0x180005275  jnz     short loc_1800052B4
0x180005277  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000527e  mov     rax, [rcx]
0x180005281  mov     rax, [rax+8]
0x180005285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000528a  test    rbx, rbx
0x18000528d  jz      short loc_1800052A1
0x18000528f  mov     rax, [rbx]
0x180005292  lea     edx, [rdi+1]
0x180005295  mov     rcx, rbx
0x180005298  mov     rax, [rax+30h]
0x18000529c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052a1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800052a8  mov     rdx, [rcx]
0x1800052ab  mov     rax, [rdx+10h]
0x1800052af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052b4  mov     rbx, [rsp+28h+arg_0]
0x1800052b9  mov     eax, edi
0x1800052bb  add     rsp, 20h
0x1800052bf  pop     rdi
0x1800052c0  retn
```
