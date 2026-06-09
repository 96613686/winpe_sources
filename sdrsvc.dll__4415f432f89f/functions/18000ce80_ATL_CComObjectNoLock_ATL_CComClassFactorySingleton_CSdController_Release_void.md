# ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CSdController>>::Release(void)

- ea: `0x18000ce80`
- end: `0x18000cf11`
- name: `?Release@?$CComObjectNoLock@V?$CComClassFactorySingleton@VCSdController@@@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(char *Block, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001554`
- `0x18000ce80`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cef6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cef6`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CSdController>>::Release(
        char *Block,
        __int64 a2)
{
  signed __int32 i; // ecx
  unsigned __int32 v4; // edi
  __int64 v5; // rcx

  for ( i = *((_DWORD *)Block + 2); i != 0x7FFFFFFF; i = *((_DWORD *)Block + 2) )
  {
    a2 = (unsigned int)(i - 1);
    if ( i == _InterlockedCompareExchange((volatile signed __int32 *)Block + 2, a2, i) )
      break;
  }
  v4 = i - 1;
  if ( i == 1 && Block )
  {
    *((_DWORD *)Block + 2) = -1073741823;
    *(_QWORD *)Block = &ATL::CComClassFactorySingleton<CSdController>::`vftable';
    v5 = *((_QWORD *)Block + 10);
    if ( v5 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v5 + 16LL))(v5, a2, 0x7FFFFFFF);
    *(_QWORD *)Block = &ATL::CComClassFactory::`vftable';
    if ( Block[56] )
    {
      Block[56] = 0;
      DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
    }
    operator delete(Block);
  }
  return v4;
}

```

## disassembly

```asm
0x18000ce80  mov     [rsp+arg_0], rbx
0x18000ce85  push    rdi
0x18000ce86  sub     rsp, 20h
0x18000ce8a  mov     rbx, rcx
0x18000ce8d  mov     r8d, 7FFFFFFFh
0x18000ce93  mov     ecx, [rcx+8]
0x18000ce96  jmp     short loc_18000CEA7
0x18000ce98  lea     edx, [rcx-1]
0x18000ce9b  mov     eax, ecx
0x18000ce9d  lock cmpxchg [rbx+8], edx
0x18000cea2  jz      short loc_18000CEAC
0x18000cea4  mov     ecx, [rbx+8]
0x18000cea7  cmp     ecx, r8d
0x18000ceaa  jnz     short loc_18000CE98
0x18000ceac  lea     edi, [rcx-1]
0x18000ceaf  test    edi, edi
0x18000ceb1  jnz     short loc_18000CF04
0x18000ceb3  test    rbx, rbx
0x18000ceb6  jz      short loc_18000CF04
0x18000ceb8  lea     rax, ??_7?$CComClassFactorySingleton@VCSdController@@@ATL@@6B@; const ATL::CComClassFactorySingleton<CSdController>::`vftable'
0x18000cebf  mov     dword ptr [rbx+8], 0C0000001h
0x18000cec6  mov     [rbx], rax
0x18000cec9  mov     rcx, [rbx+50h]
0x18000cecd  test    rcx, rcx
0x18000ced0  jz      short loc_18000CEDE
0x18000ced2  mov     rax, [rcx]
0x18000ced5  mov     rax, [rax+10h]
0x18000ced9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cede  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000cee5  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000cee9  mov     [rbx], rax
0x18000ceec  cmp     byte ptr [rcx+28h], 0
0x18000cef0  jz      short loc_18000CEFC
0x18000cef2  mov     byte ptr [rcx+28h], 0
0x18000cef6  call    cs:__imp_DeleteCriticalSection
0x18000cefc  mov     rcx, rbx; Block
0x18000ceff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cf04  mov     rbx, [rsp+28h+arg_0]
0x18000cf09  mov     eax, edi
0x18000cf0b  add     rsp, 20h
0x18000cf0f  pop     rdi
0x18000cf10  retn
```
