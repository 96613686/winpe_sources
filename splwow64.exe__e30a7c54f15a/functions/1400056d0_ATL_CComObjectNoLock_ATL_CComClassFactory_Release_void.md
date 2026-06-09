# ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(void)

- ea: `0x1400056d0`
- end: `0x140005747`
- name: `?Release@?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `119`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001b90`
- `0x1400056d0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140005727`
- `KERNEL32!DeleteCriticalSection` at `0x140005727`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(char *Block)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)Block + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)Block + 2, i - 1, i);
        i = *((_DWORD *)Block + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 && Block )
  {
    *((_DWORD *)Block + 2) = -1073741823;
    *(_QWORD *)Block = &ATL::CComClassFactory::`vftable';
    if ( Block[56] != (_BYTE)v3 )
    {
      Block[56] = v3;
      DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
    }
    operator delete(Block);
  }
  return v3;
}

```

## disassembly

```asm
0x1400056d0  mov     [rsp+arg_0], rbx
0x1400056d5  push    rdi
0x1400056d6  sub     rsp, 20h
0x1400056da  mov     rbx, rcx
0x1400056dd  mov     r8d, 7FFFFFFFh
0x1400056e3  mov     ecx, [rcx+8]
0x1400056e6  jmp     short loc_1400056F7
0x1400056e8  lea     edx, [rcx-1]
0x1400056eb  mov     eax, ecx
0x1400056ed  lock cmpxchg [rbx+8], edx
0x1400056f2  jz      short loc_1400056FC
0x1400056f4  mov     ecx, [rbx+8]
0x1400056f7  cmp     ecx, r8d
0x1400056fa  jnz     short loc_1400056E8
0x1400056fc  lea     edi, [rcx-1]
0x1400056ff  test    edi, edi
0x140005701  jnz     short loc_14000573A
0x140005703  test    rbx, rbx
0x140005706  jz      short loc_14000573A
0x140005708  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x14000570f  mov     dword ptr [rbx+8], 0C0000001h
0x140005716  lea     rcx, [rbx+10h]; lpCriticalSection
0x14000571a  mov     [rbx], rax
0x14000571d  cmp     [rcx+28h], dil
0x140005721  jz      short loc_14000572D
0x140005723  mov     [rcx+28h], dil
0x140005727  call    cs:__imp_DeleteCriticalSection
0x14000572d  mov     edx, 48h ; 'H'
0x140005732  mov     rcx, rbx; Block
0x140005735  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000573a  mov     rbx, [rsp+28h+arg_0]
0x14000573f  mov     eax, edi
0x140005741  add     rsp, 20h
0x140005745  pop     rdi
0x140005746  retn
```
