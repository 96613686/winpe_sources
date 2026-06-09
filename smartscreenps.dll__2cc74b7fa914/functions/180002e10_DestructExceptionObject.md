# __DestructExceptionObject

- ea: `0x180002e10`
- end: `0x180002e7c`
- name: `__DestructExceptionObject`
- size: `108`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180002fb0`
- `0x180003e48`
- `0x180004304`
- `0x180005670`
- `0x180005890`

## callees

- `0x180002e10`
- `0x180002e84`
- `0x1800033d8`
- `0x1800068ae`
- `0x18000e010`

## pseudocode

```c
void __fastcall _DestructExceptionObject(__int64 a1)
{
  __int64 v1; // rax
  __int64 v2; // rdx
  __int64 v3; // rcx

  if ( a1 )
  {
    if ( *(_DWORD *)a1 == -529697949
      && *(_DWORD *)(a1 + 24) == 4
      && (unsigned int)(*(_DWORD *)(a1 + 32) - 429065504) <= 2 )
    {
      v1 = *(_QWORD *)(a1 + 48);
      if ( v1 )
      {
        v2 = *(int *)(v1 + 4);
        if ( (_DWORD)v2 )
        {
          ((void (__fastcall *)(_QWORD))(*(_QWORD *)(a1 + 56) + v2))(*(_QWORD *)(a1 + 40));
        }
        else if ( (*(_BYTE *)v1 & 0x10) != 0 )
        {
          v3 = **(_QWORD **)(a1 + 40);
          if ( v3 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180002e10  test    rcx, rcx
0x180002e13  jz      short locret_180002E7B
0x180002e15  mov     [rsp+arg_8], dl
0x180002e19  sub     rsp, 48h
0x180002e1d  cmp     dword ptr [rcx], 0E06D7363h
0x180002e23  jnz     short loc_180002E77
0x180002e25  cmp     dword ptr [rcx+18h], 4
0x180002e29  jnz     short loc_180002E77
0x180002e2b  mov     eax, [rcx+20h]
0x180002e2e  sub     eax, 19930520h
0x180002e33  cmp     eax, 2
0x180002e36  ja      short loc_180002E77
0x180002e38  mov     rax, [rcx+30h]
0x180002e3c  test    rax, rax
0x180002e3f  jz      short loc_180002E77
0x180002e41  movsxd  rdx, dword ptr [rax+4]
0x180002e45  test    edx, edx
0x180002e47  jz      short loc_180002E5A
0x180002e49  add     rdx, [rcx+38h]; void *
0x180002e4d  mov     rcx, [rcx+28h]; void *
0x180002e51  call    ?_CallMemberFunction0@@YAXQEAX0@Z; _CallMemberFunction0(void * const,void * const)
0x180002e56  jmp     short loc_180002E77
0x180002e58  jmp     short loc_180002E77
0x180002e5a  test    byte ptr [rax], 10h
0x180002e5d  jz      short loc_180002E77
0x180002e5f  mov     rax, [rcx+28h]
0x180002e63  mov     rcx, [rax]
0x180002e66  test    rcx, rcx
0x180002e69  jz      short loc_180002E77
0x180002e6b  mov     rax, [rcx]
0x180002e6e  mov     rax, [rax+10h]
0x180002e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e77  add     rsp, 48h
0x180002e7b  retn
0x18000c933  push    rbx
0x18000c935  push    rbp
0x18000c936  sub     rsp, 28h
0x18000c93a  mov     rbp, rdx
0x18000c93d  mov     [rbp+30h], rcx
0x18000c941  cmp     byte ptr [rbp+58h], 0
0x18000c945  jz      short loc_18000C9B3
0x18000c947  mov     rax, [rbp+30h]
0x18000c94b  mov     rcx, [rax]
0x18000c94e  mov     [rbp+28h], rcx
0x18000c952  mov     rax, [rbp+28h]
0x18000c956  cmp     dword ptr [rax], 0E06D7363h
0x18000c95c  jnz     short loc_18000C9B3
0x18000c95e  mov     rax, [rbp+28h]
0x18000c962  cmp     dword ptr [rax+18h], 4
0x18000c966  jnz     short loc_18000C9B3
0x18000c968  mov     rax, [rbp+28h]
0x18000c96c  cmp     dword ptr [rax+20h], 19930520h
0x18000c973  jz      short loc_18000C98F
0x18000c975  mov     rax, [rbp+28h]
0x18000c979  cmp     dword ptr [rax+20h], 19930521h
0x18000c980  jz      short loc_18000C98F
0x18000c982  mov     rax, [rbp+28h]
0x18000c986  cmp     dword ptr [rax+20h], 19930522h
0x18000c98d  jnz     short loc_18000C9B3
0x18000c98f  call    __vcrt_getptd
0x18000c994  mov     rcx, [rbp+28h]
0x18000c998  mov     [rax+20h], rcx
0x18000c99c  mov     rax, [rbp+30h]
0x18000c9a0  mov     rbx, [rax+8]
0x18000c9a4  call    __vcrt_getptd
0x18000c9a9  mov     [rax+28h], rbx
0x18000c9ad  call    terminate_0
0x18000c9b3  mov     dword ptr [rbp+20h], 0
0x18000c9ba  mov     eax, [rbp+20h]
0x18000c9bd  add     rsp, 28h
0x18000c9c1  pop     rbp
0x18000c9c2  pop     rbx
0x18000c9c3  retn
```
