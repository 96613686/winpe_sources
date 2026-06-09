# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180007fd0`
- end: `0x180008078`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180007120`
- `0x180008080`

## callees

- `0x1800012e0`
- `0x180007fd0`

## import_xrefs

- `msvcrt!free` at `0x180008025`
- `msvcrt!free` at `0x18000803b`
- `msvcrt!free` at `0x180008025`
- `msvcrt!free` at `0x18000803b`
- `KERNEL32!RaiseException` at `0x180008071`
- `KERNEL32!RaiseException` at `0x180008071`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this)
{
  int v1; // eax
  int i; // edi
  void *v4; // rcx
  __int64 result; // rax

  v1 = *((_DWORD *)this + 4);
  if ( v1 > 0 )
  {
    for ( i = 0; i < v1; ++i )
    {
      if ( i < 0 || i >= v1 || (operator delete[](*(void **)(*(_QWORD *)this + 8LL * i)), i >= *((_DWORD *)this + 4)) )
      {
        RaiseException(0xC000008C, 1u, 0, 0);
        JUMPOUT(0x180008077LL);
      }
      operator delete[](*(void **)(*((_QWORD *)this + 1) + 8LL * i));
      v1 = *((_DWORD *)this + 4);
    }
  }
  if ( *(_QWORD *)this )
  {
    free(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 1) = 0;
  }
  result = 0;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x180007fd0  mov     [rsp+arg_0], rbx
0x180007fd5  mov     [rsp+arg_8], rsi
0x180007fda  push    rdi
0x180007fdb  sub     rsp, 20h
0x180007fdf  mov     eax, [rcx+10h]
0x180007fe2  mov     rbx, rcx
0x180007fe5  test    eax, eax
0x180007fe7  jle     short loc_18000801D
0x180007fe9  xor     edi, edi
0x180007feb  test    edi, edi
0x180007fed  js      short loc_180008062
0x180007fef  cmp     edi, eax
0x180007ff1  jge     short loc_180008062
0x180007ff3  mov     rcx, [rbx]
0x180007ff6  movsxd  rsi, edi
0x180007ff9  mov     rcx, [rcx+rsi*8]; Block
0x180007ffd  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180008002  cmp     edi, [rbx+10h]
0x180008005  jge     short loc_180008062
0x180008007  mov     rcx, [rbx+8]
0x18000800b  mov     rcx, [rcx+rsi*8]; Block
0x18000800f  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180008014  mov     eax, [rbx+10h]
0x180008017  inc     edi
0x180008019  cmp     edi, eax
0x18000801b  jl      short loc_180007FEB
0x18000801d  mov     rcx, [rbx]; Block
0x180008020  test    rcx, rcx
0x180008023  jz      short loc_180008032
0x180008025  call    cs:__imp_free
0x18000802b  mov     qword ptr [rbx], 0
0x180008032  mov     rcx, [rbx+8]; Block
0x180008036  test    rcx, rcx
0x180008039  jz      short loc_180008049
0x18000803b  call    cs:__imp_free
0x180008041  mov     qword ptr [rbx+8], 0
0x180008049  mov     rsi, [rsp+28h+arg_8]
0x18000804e  xor     eax, eax
0x180008050  mov     dword ptr [rbx+10h], 0
0x180008057  mov     rbx, [rsp+28h+arg_0]
0x18000805c  add     rsp, 20h
0x180008060  pop     rdi
0x180008061  retn
0x180008062  xor     r9d, r9d; lpArguments
0x180008065  xor     r8d, r8d; nNumberOfArguments
0x180008068  mov     ecx, 0C000008Ch; dwExceptionCode
0x18000806d  lea     edx, [r9+1]; dwExceptionFlags
0x180008071  call    cs:__imp_RaiseException
```
