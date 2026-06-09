# CConsistentMapping::AcquireFullAccess(int)

- ea: `0x18000f690`
- end: `0x18000f734`
- name: `?AcquireFullAccess@CConsistentMapping@@IEAAHH@Z`
- size: `164`
- prototype: `__int64 __fastcall(CConsistentMapping *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180013880`
- `0x1800139c0`

## callees

- `0x18000f690`
- `0x18000f9b8`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall CConsistentMapping::AcquireFullAccess(CConsistentMapping *this)
{
  __int64 v2; // rbx

  if ( *(_DWORD *)(*((_QWORD *)this + 1) + 8LL) == -1
    && (v2 = *((_QWORD *)this + 1),
        *(_DWORD *)(v2 + 16) == (*(unsigned int (__fastcall **)(struct IKernel32Interface *))(*(_QWORD *)g_Kernel32
                                                                                            + 624LL))(g_Kernel32)) )
  {
    if ( !*(_DWORD *)(*((_QWORD *)this + 1) + 12LL) )
      return 0;
    ++*(_DWORD *)(*((_QWORD *)this + 1) + 12LL);
  }
  else
  {
    AcquireWriteAccess((volatile int *)(*((_QWORD *)this + 1) + 8LL));
    *(_DWORD *)(*((_QWORD *)this + 1) + 16LL) = (*(__int64 (__fastcall **)(struct IKernel32Interface *))(*(_QWORD *)g_Kernel32 + 624LL))(g_Kernel32);
    *(_DWORD *)(*((_QWORD *)this + 1) + 12LL) = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x18000f690  mov     [rsp+arg_0], rbx
0x18000f695  push    rdi
0x18000f696  sub     rsp, 20h
0x18000f69a  mov     rax, [rcx+8]
0x18000f69e  mov     rdi, rcx
0x18000f6a1  mov     edx, [rax+8]
0x18000f6a4  cmp     edx, 0FFFFFFFFh
0x18000f6a7  jnz     short loc_18000F6EE
0x18000f6a9  mov     rax, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000f6b0  mov     rbx, [rcx+8]
0x18000f6b4  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000f6bb  mov     rdx, [rax]
0x18000f6be  mov     rax, [rdx+270h]
0x18000f6c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6ca  mov     ecx, [rbx+10h]
0x18000f6cd  cmp     ecx, eax
0x18000f6cf  jnz     short loc_18000F6EE
0x18000f6d1  mov     rax, [rdi+8]
0x18000f6d5  mov     ecx, [rax+0Ch]
0x18000f6d8  test    ecx, ecx
0x18000f6da  jnz     short loc_18000F6E0
0x18000f6dc  xor     eax, eax
0x18000f6de  jmp     short loc_18000F728
0x18000f6e0  mov     rdx, [rdi+8]
0x18000f6e4  mov     ecx, [rdx+0Ch]
0x18000f6e7  inc     ecx
0x18000f6e9  mov     [rdx+0Ch], ecx
0x18000f6ec  jmp     short loc_18000F723
0x18000f6ee  mov     rcx, [rdi+8]
0x18000f6f2  add     rcx, 8; volatile int *
0x18000f6f6  call    ?AcquireWriteAccess@@YAXPECJ@Z; AcquireWriteAccess(long volatile *)
0x18000f6fb  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000f702  mov     rax, [rcx]
0x18000f705  mov     rax, [rax+270h]
0x18000f70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f711  mov     rcx, [rdi+8]
0x18000f715  mov     [rcx+10h], eax
0x18000f718  mov     rax, [rdi+8]
0x18000f71c  mov     dword ptr [rax+0Ch], 1
0x18000f723  mov     eax, 1
0x18000f728  mov     rbx, [rsp+28h+arg_0]
0x18000f72d  add     rsp, 20h
0x18000f731  pop     rdi
0x18000f732  retn
```
