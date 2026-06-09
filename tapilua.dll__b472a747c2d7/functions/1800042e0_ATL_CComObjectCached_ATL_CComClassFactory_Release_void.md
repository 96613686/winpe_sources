# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x1800042e0`
- end: `0x180004379`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `153`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001494`
- `0x1800042e0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180004337`
- `KERNEL32!DeleteCriticalSection` at `0x18000434b`
- `KERNEL32!DeleteCriticalSection` at `0x180004337`
- `KERNEL32!DeleteCriticalSection` at `0x18000434b`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(char *a1)
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
  if ( i == 1 )
  {
    if ( a1 )
    {
      *((_DWORD *)a1 + 2) = 1;
      *(_QWORD *)a1 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
      if ( a1[112] != (_BYTE)v3 )
      {
        a1[112] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
      }
      if ( a1[56] )
      {
        a1[56] = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
      }
      operator delete(a1);
    }
  }
  else if ( i == 2 )
  {
    _InterlockedDecrement(&dword_18000A288);
  }
  return v3;
}

```

## disassembly

```asm
0x1800042e0  mov     [rsp+arg_0], rbx
0x1800042e5  push    rdi
0x1800042e6  sub     rsp, 20h
0x1800042ea  mov     rbx, rcx
0x1800042ed  mov     r8d, 7FFFFFFFh
0x1800042f3  mov     ecx, [rcx+8]
0x1800042f6  jmp     short loc_180004307
0x1800042f8  lea     edx, [rcx-1]
0x1800042fb  mov     eax, ecx
0x1800042fd  lock cmpxchg [rbx+8], edx
0x180004302  jz      short loc_18000430C
0x180004304  mov     ecx, [rbx+8]
0x180004307  cmp     ecx, r8d
0x18000430a  jnz     short loc_1800042F8
0x18000430c  lea     edi, [rcx-1]
0x18000430f  test    edi, edi
0x180004311  jnz     short loc_180004360
0x180004313  test    rbx, rbx
0x180004316  jz      short loc_18000436C
0x180004318  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000431f  mov     dword ptr [rbx+8], 1
0x180004326  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000432a  mov     [rbx], rax
0x18000432d  cmp     [rcx+28h], dil
0x180004331  jz      short loc_18000433D
0x180004333  mov     [rcx+28h], dil
0x180004337  call    cs:__imp_DeleteCriticalSection
0x18000433d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004341  cmp     byte ptr [rcx+28h], 0
0x180004345  jz      short loc_180004351
0x180004347  mov     byte ptr [rcx+28h], 0
0x18000434b  call    cs:__imp_DeleteCriticalSection
0x180004351  mov     edx, 78h ; 'x'; unsigned __int64
0x180004356  mov     rcx, rbx; void *
0x180004359  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000435e  jmp     short loc_18000436C
0x180004360  cmp     edi, 1
0x180004363  jnz     short loc_18000436C
0x180004365  lock dec cs:dword_18000A288
0x18000436c  mov     rbx, [rsp+28h+arg_0]
0x180004371  mov     eax, edi
0x180004373  add     rsp, 20h
0x180004377  pop     rdi
0x180004378  retn
```
