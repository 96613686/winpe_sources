# ATL::CComObject<CUWFCspNextSessionNode>::Release(void)

- ea: `0x18000acb0`
- end: `0x18000ad34`
- name: `?Release@?$CComObject@VCUWFCspNextSessionNode@@@ATL@@UEAAKXZ`
- size: `132`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ad40`

## callees

- `0x18000acb0`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CUWFCspNextSessionNode>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 18);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 18, i - 1, i);
        i = *((_DWORD *)a1 + 18) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 128LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x18000acb0  mov     [rsp+arg_0], rbx
0x18000acb5  push    rdi
0x18000acb6  sub     rsp, 20h
0x18000acba  mov     r8d, [rcx+48h]
0x18000acbe  mov     rbx, rcx
0x18000acc1  mov     ecx, 7FFFFFFFh
0x18000acc6  jmp     short loc_18000ACDA
0x18000acc8  lea     edx, [r8-1]
0x18000accc  mov     eax, r8d
0x18000accf  lock cmpxchg [rbx+48h], edx
0x18000acd4  jz      short loc_18000ACDF
0x18000acd6  mov     r8d, [rbx+48h]
0x18000acda  cmp     r8d, ecx
0x18000acdd  jnz     short loc_18000ACC8
0x18000acdf  lea     edi, [r8-1]
0x18000ace3  test    edi, edi
0x18000ace5  jnz     short loc_18000AD27
0x18000ace7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000acee  mov     rax, [rcx]
0x18000acf1  mov     rax, [rax+8]
0x18000acf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acfa  test    rbx, rbx
0x18000acfd  jz      short loc_18000AD14
0x18000acff  mov     rax, [rbx]
0x18000ad02  lea     edx, [rdi+1]
0x18000ad05  mov     rcx, rbx
0x18000ad08  mov     rax, [rax+80h]
0x18000ad0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad14  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ad1b  mov     rdx, [rcx]
0x18000ad1e  mov     rax, [rdx+10h]
0x18000ad22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad27  mov     rbx, [rsp+28h+arg_0]
0x18000ad2c  mov     eax, edi
0x18000ad2e  add     rsp, 20h
0x18000ad32  pop     rdi
0x18000ad33  retn
```
