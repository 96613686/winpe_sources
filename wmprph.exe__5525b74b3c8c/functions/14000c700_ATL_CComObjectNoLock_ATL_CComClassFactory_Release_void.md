# ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(void)

- ea: `0x14000c700`
- end: `0x14000c76b`
- name: `?Release@?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `107`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001008`
- `0x14000c700`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000c74d`
- `KERNEL32!DeleteCriticalSection` at `0x14000c74d`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(char *a1)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 && a1 )
  {
    *((_DWORD *)a1 + 2) = 1;
    *(_QWORD *)a1 = &ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable';
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    operator delete(a1, v3 + 64);
  }
  return v3;
}

```

## disassembly

```asm
0x14000c700  mov     [rsp+arg_0], rbx
0x14000c705  push    rdi
0x14000c706  sub     rsp, 20h
0x14000c70a  mov     rbx, rcx
0x14000c70d  mov     r8d, 7FFFFFFFh
0x14000c713  mov     ecx, [rcx+8]
0x14000c716  jmp     short loc_14000C727
0x14000c718  lea     edx, [rcx-1]
0x14000c71b  mov     eax, ecx
0x14000c71d  lock cmpxchg [rbx+8], edx
0x14000c722  jz      short loc_14000C72C
0x14000c724  mov     ecx, [rbx+8]
0x14000c727  cmp     ecx, r8d
0x14000c72a  jnz     short loc_14000C718
0x14000c72c  lea     edi, [rcx-1]
0x14000c72f  test    edi, edi
0x14000c731  jnz     short loc_14000C75E
0x14000c733  test    rbx, rbx
0x14000c736  jz      short loc_14000C75E
0x14000c738  lea     rax, ??_7?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable'
0x14000c73f  mov     dword ptr [rbx+8], 1
0x14000c746  lea     rcx, [rbx+10h]; lpCriticalSection
0x14000c74a  mov     [rbx], rax
0x14000c74d  call    cs:__imp_DeleteCriticalSection
0x14000c753  lea     edx, [rdi+40h]; unsigned __int64
0x14000c756  mov     rcx, rbx; void *
0x14000c759  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c75e  mov     rbx, [rsp+28h+arg_0]
0x14000c763  mov     eax, edi
0x14000c765  add     rsp, 20h
0x14000c769  pop     rdi
0x14000c76a  retn
```
