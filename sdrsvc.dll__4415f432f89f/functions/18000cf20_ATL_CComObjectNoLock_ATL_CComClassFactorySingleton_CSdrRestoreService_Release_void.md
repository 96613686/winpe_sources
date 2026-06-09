# ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CSdrRestoreService>>::Release(void)

- ea: `0x18000cf20`
- end: `0x18000cfb1`
- name: `?Release@?$CComObjectNoLock@V?$CComClassFactorySingleton@VCSdrRestoreService@@@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(char *Block, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001554`
- `0x18000cf20`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cf96`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cf96`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CSdrRestoreService>>::Release(
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
    *(_QWORD *)Block = &ATL::CComClassFactorySingleton<CSdrRestoreService>::`vftable';
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
0x18000cf20  mov     [rsp+arg_0], rbx
0x18000cf25  push    rdi
0x18000cf26  sub     rsp, 20h
0x18000cf2a  mov     rbx, rcx
0x18000cf2d  mov     r8d, 7FFFFFFFh
0x18000cf33  mov     ecx, [rcx+8]
0x18000cf36  jmp     short loc_18000CF47
0x18000cf38  lea     edx, [rcx-1]
0x18000cf3b  mov     eax, ecx
0x18000cf3d  lock cmpxchg [rbx+8], edx
0x18000cf42  jz      short loc_18000CF4C
0x18000cf44  mov     ecx, [rbx+8]
0x18000cf47  cmp     ecx, r8d
0x18000cf4a  jnz     short loc_18000CF38
0x18000cf4c  lea     edi, [rcx-1]
0x18000cf4f  test    edi, edi
0x18000cf51  jnz     short loc_18000CFA4
0x18000cf53  test    rbx, rbx
0x18000cf56  jz      short loc_18000CFA4
0x18000cf58  lea     rax, ??_7?$CComClassFactorySingleton@VCSdrRestoreService@@@ATL@@6B@; const ATL::CComClassFactorySingleton<CSdrRestoreService>::`vftable'
0x18000cf5f  mov     dword ptr [rbx+8], 0C0000001h
0x18000cf66  mov     [rbx], rax
0x18000cf69  mov     rcx, [rbx+50h]
0x18000cf6d  test    rcx, rcx
0x18000cf70  jz      short loc_18000CF7E
0x18000cf72  mov     rax, [rcx]
0x18000cf75  mov     rax, [rax+10h]
0x18000cf79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf7e  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000cf85  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000cf89  mov     [rbx], rax
0x18000cf8c  cmp     byte ptr [rcx+28h], 0
0x18000cf90  jz      short loc_18000CF9C
0x18000cf92  mov     byte ptr [rcx+28h], 0
0x18000cf96  call    cs:__imp_DeleteCriticalSection
0x18000cf9c  mov     rcx, rbx; Block
0x18000cf9f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cfa4  mov     rbx, [rsp+28h+arg_0]
0x18000cfa9  mov     eax, edi
0x18000cfab  add     rsp, 20h
0x18000cfaf  pop     rdi
0x18000cfb0  retn
```
