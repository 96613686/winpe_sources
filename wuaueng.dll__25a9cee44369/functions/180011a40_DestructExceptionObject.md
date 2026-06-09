# __DestructExceptionObject

- ea: `0x180011a40`
- end: `0x180011ab3`
- name: `__DestructExceptionObject`
- size: `115`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180011c44`
- `0x180012a9c`
- `0x180012f9c`
- `0x180014430`
- `0x180014630`

## callees

- `0x18000fc64`
- `0x180011a40`
- `0x180011abc`
- `0x180011f98`
- `0x1800159b0`

## pseudocode

```c
void __fastcall _DestructExceptionObject(__int64 a1)
{
  int v1; // eax
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx

  if ( a1 )
  {
    if ( *(_DWORD *)a1 == -529697949 && *(_DWORD *)(a1 + 24) == 4 )
    {
      v1 = *(_DWORD *)(a1 + 32);
      if ( v1 == 429065504 || (unsigned int)(v1 - 429065505) <= 1 )
      {
        v2 = *(_QWORD *)(a1 + 48);
        if ( v2 )
        {
          v3 = *(int *)(v2 + 4);
          if ( (_DWORD)v3 )
          {
            ((void (__fastcall *)(_QWORD))(*(_QWORD *)(a1 + 56) + v3))(*(_QWORD *)(a1 + 40));
          }
          else if ( (*(_BYTE *)v2 & 0x10) != 0 )
          {
            v4 = **(_QWORD **)(a1 + 40);
            if ( v4 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180011a40  test    rcx, rcx
0x180011a43  jz      short locret_180011AB2
0x180011a45  mov     [rsp+arg_8], dl
0x180011a49  sub     rsp, 48h
0x180011a4d  cmp     dword ptr [rcx], 0E06D7363h
0x180011a53  jnz     short loc_180011AAE
0x180011a55  cmp     dword ptr [rcx+18h], 4
0x180011a59  jnz     short loc_180011AAE
0x180011a5b  mov     eax, [rcx+20h]
0x180011a5e  cmp     eax, 19930520h
0x180011a63  jz      short loc_180011A6F
0x180011a65  add     eax, 0E66CFADFh
0x180011a6a  cmp     eax, 1
0x180011a6d  ja      short loc_180011AAE
0x180011a6f  mov     rax, [rcx+30h]
0x180011a73  test    rax, rax
0x180011a76  jz      short loc_180011AAE
0x180011a78  movsxd  rdx, dword ptr [rax+4]
0x180011a7c  test    edx, edx
0x180011a7e  jz      short loc_180011A91
0x180011a80  add     rdx, [rcx+38h]; void *
0x180011a84  mov     rcx, [rcx+28h]; void *
0x180011a88  call    ?_CallMemberFunction0@@YAXQEAX0@Z; _CallMemberFunction0(void * const,void * const)
0x180011a8d  jmp     short loc_180011AAE
0x180011a8f  jmp     short loc_180011AAE
0x180011a91  test    byte ptr [rax], 10h
0x180011a94  jz      short loc_180011AAE
0x180011a96  mov     rax, [rcx+28h]
0x180011a9a  mov     rcx, [rax]
0x180011a9d  test    rcx, rcx
0x180011aa0  jz      short loc_180011AAE
0x180011aa2  mov     rax, [rcx]
0x180011aa5  mov     rax, [rax+10h]
0x180011aa9  call    _guard_dispatch_icall
0x180011aae  add     rsp, 48h
0x180011ab2  retn
0x180016df3  push    rbx
0x180016df5  push    rbp
0x180016df6  sub     rsp, 28h
0x180016dfa  mov     rbp, rdx
0x180016dfd  mov     [rbp+30h], rcx
0x180016e01  cmp     byte ptr [rbp+58h], 0
0x180016e05  jz      short loc_180016E73
0x180016e07  mov     rax, [rbp+30h]
0x180016e0b  mov     rcx, [rax]
0x180016e0e  mov     [rbp+28h], rcx
0x180016e12  mov     rax, [rbp+28h]
0x180016e16  cmp     dword ptr [rax], 0E06D7363h
0x180016e1c  jnz     short loc_180016E73
0x180016e1e  mov     rax, [rbp+28h]
0x180016e22  cmp     dword ptr [rax+18h], 4
0x180016e26  jnz     short loc_180016E73
0x180016e28  mov     rax, [rbp+28h]
0x180016e2c  cmp     dword ptr [rax+20h], 19930520h
0x180016e33  jz      short loc_180016E4F
0x180016e35  mov     rax, [rbp+28h]
0x180016e39  cmp     dword ptr [rax+20h], 19930521h
0x180016e40  jz      short loc_180016E4F
0x180016e42  mov     rax, [rbp+28h]
0x180016e46  cmp     dword ptr [rax+20h], 19930522h
0x180016e4d  jnz     short loc_180016E73
0x180016e4f  call    __vcrt_getptd
0x180016e54  mov     rcx, [rbp+28h]
0x180016e58  mov     [rax+20h], rcx
0x180016e5c  mov     rax, [rbp+30h]
0x180016e60  mov     rbx, [rax+8]
0x180016e64  call    __vcrt_getptd
0x180016e69  mov     [rax+28h], rbx
0x180016e6d  call    _o_terminate_0
0x180016e72  nop
0x180016e73  mov     dword ptr [rbp+20h], 0
0x180016e7a  mov     eax, [rbp+20h]
0x180016e7d  add     rsp, 28h
0x180016e81  pop     rbp
0x180016e82  pop     rbx
0x180016e83  retn
```
