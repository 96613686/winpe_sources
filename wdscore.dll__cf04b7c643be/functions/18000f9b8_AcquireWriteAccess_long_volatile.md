# AcquireWriteAccess(long volatile *)

- ea: `0x18000f9b8`
- end: `0x18000fa69`
- name: `?AcquireWriteAccess@@YAXPECJ@Z`
- size: `177`
- prototype: `void __fastcall(volatile int *)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f690`
- `0x18000fcf0`
- `0x1800107c4`
- `0x180011064`
- `0x1800149c4`
- `0x1800179a4`
- `0x180017c2c`

## callees

- `0x18000f9b8`
- `0x18002a010`

## pseudocode

```c
void __fastcall AcquireWriteAccess(volatile int *a1)
{
  unsigned int v2; // edi
  signed __int32 v3; // esi
  int v4; // ebp
  signed __int32 v5; // edx

  v2 = 0;
  v3 = 0;
  v4 = (*(__int64 (__fastcall **)(struct IKernel32Interface *))(*(_QWORD *)g_Kernel32 + 344LL))(g_Kernel32);
  if ( _InterlockedCompareExchange(a1, -1, 0) )
  {
    do
    {
      if ( v2 > 0x3E8 )
      {
        v2 = 0;
        if ( (*(unsigned int (__fastcall **)(struct IKernel32Interface *))(*(_QWORD *)g_Kernel32 + 344LL))(g_Kernel32)
           - v4 > 0x3E8 )
        {
          while ( *(int *)a1 >= 0 )
          {
            v5 = *a1;
            if ( v5 == _InterlockedCompareExchange(a1, v5 | 0x80000000, v5) )
            {
              v3 = 0x80000000;
              break;
            }
          }
        }
        (*(void (__fastcall **)(struct IKernel32Interface *, __int64))(*(_QWORD *)g_Kernel32 + 496LL))(g_Kernel32, 1);
      }
      ++v2;
    }
    while ( v3 != _InterlockedCompareExchange(a1, -1, v3) );
  }
}

```

## disassembly

```asm
0x18000f9b8  push    rbx
0x18000f9ba  push    rbp
0x18000f9bb  push    rsi
0x18000f9bc  push    rdi
0x18000f9bd  push    r12
0x18000f9bf  sub     rsp, 20h
0x18000f9c3  mov     rbx, rcx
0x18000f9c6  xor     edi, edi
0x18000f9c8  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000f9cf  mov     rax, [rcx]
0x18000f9d2  mov     rax, [rax+158h]
0x18000f9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9de  xor     esi, esi
0x18000f9e0  or      r12d, 0FFFFFFFFh
0x18000f9e4  mov     ebp, eax
0x18000f9e6  xor     eax, eax
0x18000f9e8  lock cmpxchg [rbx], r12d
0x18000f9ed  jz      short loc_18000FA5D
0x18000f9ef  cmp     edi, 3E8h
0x18000f9f5  jbe     short loc_18000FA50
0x18000f9f7  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000f9fe  xor     edi, edi
0x18000fa00  mov     rax, [rcx]
0x18000fa03  mov     rax, [rax+158h]
0x18000fa0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa0f  sub     eax, ebp
0x18000fa11  cmp     eax, 3E8h
0x18000fa16  jbe     short loc_18000FA35
0x18000fa18  mov     edx, [rbx]
0x18000fa1a  test    edx, edx
0x18000fa1c  js      short loc_18000FA35
0x18000fa1e  mov     ecx, edx
0x18000fa20  mov     eax, edx
0x18000fa22  or      ecx, 80000000h
0x18000fa28  lock cmpxchg [rbx], ecx
0x18000fa2c  cmp     edx, eax
0x18000fa2e  jnz     short loc_18000FA18
0x18000fa30  mov     esi, 80000000h
0x18000fa35  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000fa3c  mov     edx, 1
0x18000fa41  mov     rax, [rcx]
0x18000fa44  mov     rax, [rax+1F0h]
0x18000fa4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa50  inc     edi
0x18000fa52  mov     eax, esi
0x18000fa54  lock cmpxchg [rbx], r12d
0x18000fa59  cmp     esi, eax
0x18000fa5b  jnz     short loc_18000F9EF
0x18000fa5d  add     rsp, 20h
0x18000fa61  pop     r12
0x18000fa63  pop     rdi
0x18000fa64  pop     rsi
0x18000fa65  pop     rbp
0x18000fa66  pop     rbx
0x18000fa67  retn
```
