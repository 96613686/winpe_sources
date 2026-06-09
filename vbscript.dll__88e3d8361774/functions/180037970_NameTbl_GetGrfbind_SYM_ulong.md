# NameTbl::GetGrfbind(SYM *,ulong *)

- ea: `0x180037970`
- end: `0x1800379d7`
- name: `?GetGrfbind@NameTbl@@UEAAJPEAUSYM@@PEAK@Z`
- size: `103`
- prototype: `__int64 __fastcall(NameTbl *__hidden this, struct SYM *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180037970`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180037985`
- `KERNEL32!GetCurrentThreadId` at `0x180037985`

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
0x180037970  push    rbx
0x180037972  push    rbp
0x180037973  push    rsi
0x180037974  push    rdi
0x180037975  sub     rsp, 38h
0x180037979  mov     ebx, [rcx+20h]
0x18003797c  mov     rsi, r8
0x18003797f  mov     rbp, rdx
0x180037982  mov     rdi, rcx
0x180037985  call    cs:__imp_GetCurrentThreadId
0x18003798b  cmp     eax, ebx
0x18003798d  jnz     short loc_1800379C2
0x18003798f  mov     rax, [rdi]
0x180037992  lea     r8, [rsp+58h+arg_0]
0x180037997  xor     r9d, r9d
0x18003799a  mov     [rsp+58h+arg_0], 0
0x1800379a3  mov     rdx, rbp
0x1800379a6  mov     rcx, rdi
0x1800379a9  mov     rax, [rax+100h]
0x1800379b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379b5  test    eax, eax
0x1800379b7  jz      short loc_1800379C9
0x1800379b9  add     rsp, 38h
0x1800379bd  pop     rdi
0x1800379be  pop     rsi
0x1800379bf  pop     rbp
0x1800379c0  pop     rbx
0x1800379c1  retn
0x1800379c2  mov     eax, 8000FFFFh
0x1800379c7  jmp     short loc_1800379B9
0x1800379c9  mov     rax, [rsp+58h+arg_0]
0x1800379ce  mov     ecx, [rax+18h]
0x1800379d1  xor     eax, eax
0x1800379d3  mov     [rsi], ecx
0x1800379d5  jmp     short loc_1800379B9
```
