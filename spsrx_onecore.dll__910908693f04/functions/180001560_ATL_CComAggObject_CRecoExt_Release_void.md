# ATL::CComAggObject<CRecoExt>::Release(void)

- ea: `0x180001560`
- end: `0x1800015db`
- name: `?Release@?$CComAggObject@VCRecoExt@@@ATL@@UEAAKXZ`
- size: `123`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001560`
- `0x1800015f0`
- `0x180002f08`
- `0x180010010`

## pseudocode

```c
unsigned int __fastcall ATL::CComAggObject<CRecoExt>::Release(int *a1)
{
  unsigned int result; // eax
  unsigned int v3; // edi
  char *(__fastcall *v4)(char *, char); // rax

  result = ATL::CComMultiThreadModel::SafeDecrementReference(a1 + 2);
  v3 = result;
  if ( !result )
  {
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
    {
      v4 = *(char *(__fastcall **)(char *, char))(*(_QWORD *)a1 + 24LL);
      if ( v4 == ATL::CComAggObject<CRecoExt>::`scalar deleting destructor' )
        ATL::CComAggObject<CRecoExt>::`scalar deleting destructor'((char *)a1, 1);
      else
        v4((char *)a1, 1);
    }
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180001560  mov     [rsp+arg_0], rbx
0x180001565  push    rdi
0x180001566  sub     rsp, 20h
0x18000156a  mov     rbx, rcx
0x18000156d  add     rcx, 8; int *
0x180001571  call    ?SafeDecrementReference@CComMultiThreadModel@ATL@@SAKPEAJ@Z; ATL::CComMultiThreadModel::SafeDecrementReference(long *)
0x180001576  mov     edi, eax
0x180001578  test    eax, eax
0x18000157a  jnz     short loc_1800015D0
0x18000157c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180001583  mov     rdx, [rcx]
0x180001586  mov     rax, [rdx+8]
0x18000158a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000158f  test    rbx, rbx
0x180001592  jz      short loc_1800015BB
0x180001594  mov     rcx, [rbx]
0x180001597  mov     edx, 1
0x18000159c  mov     rax, [rcx+18h]
0x1800015a0  lea     rcx, ??_G?$CComAggObject@VCRecoExt@@@ATL@@UEAAPEAXI@Z; ATL::CComAggObject<CRecoExt>::`scalar deleting destructor'(uint)
0x1800015a7  cmp     rax, rcx
0x1800015aa  mov     rcx, rbx; void *
0x1800015ad  jnz     short loc_1800015B6
0x1800015af  call    ??_G?$CComAggObject@VCRecoExt@@@ATL@@UEAAPEAXI@Z; ATL::CComAggObject<CRecoExt>::`scalar deleting destructor'(uint)
0x1800015b4  jmp     short loc_1800015BB
0x1800015b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015bb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800015c2  mov     rax, [rcx]
0x1800015c5  mov     rax, [rax+10h]
0x1800015c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015ce  mov     eax, edi
0x1800015d0  mov     rbx, [rsp+28h+arg_0]
0x1800015d5  add     rsp, 20h
0x1800015d9  pop     rdi
0x1800015da  retn
```
