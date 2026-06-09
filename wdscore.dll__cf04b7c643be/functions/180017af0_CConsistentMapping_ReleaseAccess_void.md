# CConsistentMapping::ReleaseAccess(void)

- ea: `0x180017af0`
- end: `0x180017b73`
- name: `?ReleaseAccess@CConsistentMapping@@IEAAXXZ`
- size: `131`
- prototype: `void __fastcall(CConsistentMapping *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180013880`
- `0x1800139c0`
- `0x1800166d0`
- `0x180018650`
- `0x180018690`

## callees

- `0x180017ab4`
- `0x180017af0`
- `0x18002a010`

## pseudocode

```c
void __fastcall CConsistentMapping::ReleaseAccess(CConsistentMapping *this)
{
  __int64 v2; // rbx

  if ( *(_DWORD *)(*((_QWORD *)this + 1) + 8LL) != -1 )
    goto LABEL_6;
  v2 = *((_QWORD *)this + 1);
  if ( *(_DWORD *)(v2 + 16) != (*(unsigned int (__fastcall **)(struct IKernel32Interface *))(*(_QWORD *)g_Kernel32
                                                                                           + 624LL))(g_Kernel32) )
    goto LABEL_6;
  if ( *(_DWORD *)(*((_QWORD *)this + 1) + 12LL) )
  {
    if ( !--*(_DWORD *)(*((_QWORD *)this + 1) + 12LL) )
    {
      *(_DWORD *)(*((_QWORD *)this + 1) + 16LL) = 0;
LABEL_6:
      ReleaseAccess((volatile int *)(*((_QWORD *)this + 1) + 8LL));
    }
  }
}

```

## disassembly

```asm
0x180017af0  mov     [rsp+arg_0], rbx
0x180017af5  push    rdi
0x180017af6  sub     rsp, 20h
0x180017afa  mov     rax, [rcx+8]
0x180017afe  mov     rdi, rcx
0x180017b01  mov     edx, [rax+8]
0x180017b04  cmp     edx, 0FFFFFFFFh
0x180017b07  jnz     short loc_180017B5A
0x180017b09  mov     rax, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180017b10  mov     rbx, [rcx+8]
0x180017b14  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180017b1b  mov     rdx, [rax]
0x180017b1e  mov     rax, [rdx+270h]
0x180017b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b2a  mov     ecx, [rbx+10h]
0x180017b2d  cmp     ecx, eax
0x180017b2f  jnz     short loc_180017B5A
0x180017b31  mov     rax, [rdi+8]
0x180017b35  mov     ecx, [rax+0Ch]
0x180017b38  test    ecx, ecx
0x180017b3a  jz      short loc_180017B67
0x180017b3c  mov     rcx, [rdi+8]
0x180017b40  mov     eax, [rcx+0Ch]
0x180017b43  dec     eax
0x180017b45  mov     [rcx+0Ch], eax
0x180017b48  mov     rax, [rdi+8]
0x180017b4c  mov     ecx, [rax+0Ch]
0x180017b4f  test    ecx, ecx
0x180017b51  jnz     short loc_180017B67
0x180017b53  mov     rax, [rdi+8]
0x180017b57  mov     [rax+10h], ecx
0x180017b5a  mov     rcx, [rdi+8]
0x180017b5e  add     rcx, 8; volatile int *
0x180017b62  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x180017b67  mov     rbx, [rsp+28h+arg_0]
0x180017b6c  add     rsp, 20h
0x180017b70  pop     rdi
0x180017b71  retn
```
