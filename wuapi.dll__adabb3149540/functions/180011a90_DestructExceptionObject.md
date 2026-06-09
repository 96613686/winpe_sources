# __DestructExceptionObject

- ea: `0x180011a90`
- end: `0x180011b03`
- name: `__DestructExceptionObject`
- size: `115`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180011c94`
- `0x180012aec`
- `0x180012fec`
- `0x180014480`
- `0x180014680`

## callees

- `0x18000fcb4`
- `0x180011a90`
- `0x180011b0c`
- `0x180011fe8`
- `0x180015a00`

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
0x180011a90  test    rcx, rcx
0x180011a93  jz      short locret_180011B02
0x180011a95  mov     [rsp+arg_8], dl
0x180011a99  sub     rsp, 48h
0x180011a9d  cmp     dword ptr [rcx], 0E06D7363h
0x180011aa3  jnz     short loc_180011AFE
0x180011aa5  cmp     dword ptr [rcx+18h], 4
0x180011aa9  jnz     short loc_180011AFE
0x180011aab  mov     eax, [rcx+20h]
0x180011aae  cmp     eax, 19930520h
0x180011ab3  jz      short loc_180011ABF
0x180011ab5  add     eax, 0E66CFADFh
0x180011aba  cmp     eax, 1
0x180011abd  ja      short loc_180011AFE
0x180011abf  mov     rax, [rcx+30h]
0x180011ac3  test    rax, rax
0x180011ac6  jz      short loc_180011AFE
0x180011ac8  movsxd  rdx, dword ptr [rax+4]
0x180011acc  test    edx, edx
0x180011ace  jz      short loc_180011AE1
0x180011ad0  add     rdx, [rcx+38h]; void *
0x180011ad4  mov     rcx, [rcx+28h]; void *
0x180011ad8  call    ?_CallMemberFunction0@@YAXQEAX0@Z; _CallMemberFunction0(void * const,void * const)
0x180011add  jmp     short loc_180011AFE
0x180011adf  jmp     short loc_180011AFE
0x180011ae1  test    byte ptr [rax], 10h
0x180011ae4  jz      short loc_180011AFE
0x180011ae6  mov     rax, [rcx+28h]
0x180011aea  mov     rcx, [rax]
0x180011aed  test    rcx, rcx
0x180011af0  jz      short loc_180011AFE
0x180011af2  mov     rax, [rcx]
0x180011af5  mov     rax, [rax+10h]
0x180011af9  call    _guard_dispatch_icall
0x180011afe  add     rsp, 48h
0x180011b02  retn
0x180016e43  push    rbx
0x180016e45  push    rbp
0x180016e46  sub     rsp, 28h
0x180016e4a  mov     rbp, rdx
0x180016e4d  mov     [rbp+30h], rcx
0x180016e51  cmp     byte ptr [rbp+58h], 0
0x180016e55  jz      short loc_180016EC3
0x180016e57  mov     rax, [rbp+30h]
0x180016e5b  mov     rcx, [rax]
0x180016e5e  mov     [rbp+28h], rcx
0x180016e62  mov     rax, [rbp+28h]
0x180016e66  cmp     dword ptr [rax], 0E06D7363h
0x180016e6c  jnz     short loc_180016EC3
0x180016e6e  mov     rax, [rbp+28h]
0x180016e72  cmp     dword ptr [rax+18h], 4
0x180016e76  jnz     short loc_180016EC3
0x180016e78  mov     rax, [rbp+28h]
0x180016e7c  cmp     dword ptr [rax+20h], 19930520h
0x180016e83  jz      short loc_180016E9F
0x180016e85  mov     rax, [rbp+28h]
0x180016e89  cmp     dword ptr [rax+20h], 19930521h
0x180016e90  jz      short loc_180016E9F
0x180016e92  mov     rax, [rbp+28h]
0x180016e96  cmp     dword ptr [rax+20h], 19930522h
0x180016e9d  jnz     short loc_180016EC3
0x180016e9f  call    __vcrt_getptd
0x180016ea4  mov     rcx, [rbp+28h]
0x180016ea8  mov     [rax+20h], rcx
0x180016eac  mov     rax, [rbp+30h]
0x180016eb0  mov     rbx, [rax+8]
0x180016eb4  call    __vcrt_getptd
0x180016eb9  mov     [rax+28h], rbx
0x180016ebd  call    _o_terminate_0
0x180016ec2  nop
0x180016ec3  mov     dword ptr [rbp+20h], 0
0x180016eca  mov     eax, [rbp+20h]
0x180016ecd  add     rsp, 28h
0x180016ed1  pop     rbp
0x180016ed2  pop     rbx
0x180016ed3  retn
```
