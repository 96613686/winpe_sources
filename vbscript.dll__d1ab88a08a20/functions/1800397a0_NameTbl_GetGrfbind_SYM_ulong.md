# NameTbl::GetGrfbind(SYM *,ulong *)

- ea: `0x1800397a0`
- end: `0x18003980e`
- name: `?GetGrfbind@NameTbl@@UEAAJPEAUSYM@@PEAK@Z`
- size: `110`
- prototype: `__int64 __fastcall(NameTbl *__hidden this, struct SYM *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800397a0`
- `0x18007a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800397b5`
- `KERNEL32!GetCurrentThreadId` at `0x1800397b5`

## pseudocode

```c
__int64 __fastcall NameTbl::GetGrfbind(NameTbl *this, struct SYM *a2, unsigned int *a3)
{
  int v3; // ebx
  __int64 v7; // rax
  __int64 result; // rax
  __int64 v9; // [rsp+60h] [rbp+8h] BYREF

  v3 = *((_DWORD *)this + 8);
  if ( GetCurrentThreadId() != v3 )
    return 2147549183LL;
  v7 = *(_QWORD *)this;
  v9 = 0;
  result = (*(__int64 (__fastcall **)(NameTbl *, struct SYM *, __int64 *, _QWORD))(v7 + 256))(this, a2, &v9, 0);
  if ( !(_DWORD)result )
  {
    result = 0;
    *a3 = *(_DWORD *)(v9 + 24);
  }
  return result;
}

```

## disassembly

```asm
0x1800397a0  push    rbx
0x1800397a2  push    rbp
0x1800397a3  push    rsi
0x1800397a4  push    rdi
0x1800397a5  sub     rsp, 38h
0x1800397a9  mov     ebx, [rcx+20h]
0x1800397ac  mov     rsi, r8
0x1800397af  mov     rbp, rdx
0x1800397b2  mov     rdi, rcx
0x1800397b5  call    cs:__imp_GetCurrentThreadId
0x1800397bc  nop     dword ptr [rax+rax+00h]
0x1800397c1  cmp     eax, ebx
0x1800397c3  jnz     short loc_1800397F9
0x1800397c5  mov     rax, [rdi]
0x1800397c8  lea     r8, [rsp+58h+arg_0]
0x1800397cd  xor     r9d, r9d
0x1800397d0  mov     [rsp+58h+arg_0], 0
0x1800397d9  mov     rdx, rbp
0x1800397dc  mov     rcx, rdi
0x1800397df  mov     rax, [rax+100h]
0x1800397e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397eb  test    eax, eax
0x1800397ed  jz      short loc_180039800
0x1800397ef  add     rsp, 38h
0x1800397f3  pop     rdi
0x1800397f4  pop     rsi
0x1800397f5  pop     rbp
0x1800397f6  pop     rbx
0x1800397f7  retn
0x1800397f9  mov     eax, 8000FFFFh
0x1800397fe  jmp     short loc_1800397EF
0x180039800  mov     rax, [rsp+58h+arg_0]
0x180039805  mov     ecx, [rax+18h]
0x180039808  xor     eax, eax
0x18003980a  mov     [rsi], ecx
0x18003980c  jmp     short loc_1800397EF
```
