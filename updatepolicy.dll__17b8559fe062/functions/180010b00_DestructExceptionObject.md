# __DestructExceptionObject

- ea: `0x180010b00`
- end: `0x180010b73`
- name: `__DestructExceptionObject`
- size: `115`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180010d04`
- `0x180011b5c`
- `0x18001205c`
- `0x1800134f0`
- `0x1800136f0`

## callees

- `0x18000ed18`
- `0x180010b00`
- `0x180010b7c`
- `0x180011058`
- `0x180015430`

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
0x180010b00  test    rcx, rcx
0x180010b03  jz      short locret_180010B72
0x180010b05  mov     [rsp+arg_8], dl
0x180010b09  sub     rsp, 48h
0x180010b0d  cmp     dword ptr [rcx], 0E06D7363h
0x180010b13  jnz     short loc_180010B6E
0x180010b15  cmp     dword ptr [rcx+18h], 4
0x180010b19  jnz     short loc_180010B6E
0x180010b1b  mov     eax, [rcx+20h]
0x180010b1e  cmp     eax, 19930520h
0x180010b23  jz      short loc_180010B2F
0x180010b25  add     eax, 0E66CFADFh
0x180010b2a  cmp     eax, 1
0x180010b2d  ja      short loc_180010B6E
0x180010b2f  mov     rax, [rcx+30h]
0x180010b33  test    rax, rax
0x180010b36  jz      short loc_180010B6E
0x180010b38  movsxd  rdx, dword ptr [rax+4]
0x180010b3c  test    edx, edx
0x180010b3e  jz      short loc_180010B51
0x180010b40  add     rdx, [rcx+38h]; void *
0x180010b44  mov     rcx, [rcx+28h]; void *
0x180010b48  call    ?_CallMemberFunction0@@YAXQEAX0@Z; _CallMemberFunction0(void * const,void * const)
0x180010b4d  jmp     short loc_180010B6E
0x180010b4f  jmp     short loc_180010B6E
0x180010b51  test    byte ptr [rax], 10h
0x180010b54  jz      short loc_180010B6E
0x180010b56  mov     rax, [rcx+28h]
0x180010b5a  mov     rcx, [rax]
0x180010b5d  test    rcx, rcx
0x180010b60  jz      short loc_180010B6E
0x180010b62  mov     rax, [rcx]
0x180010b65  mov     rax, [rax+10h]
0x180010b69  call    _guard_dispatch_icall
0x180010b6e  add     rsp, 48h
0x180010b72  retn
0x18001682b  push    rbx
0x18001682d  push    rbp
0x18001682e  sub     rsp, 28h
0x180016832  mov     rbp, rdx
0x180016835  mov     [rbp+30h], rcx
0x180016839  cmp     byte ptr [rbp+58h], 0
0x18001683d  jz      short loc_1800168AB
0x18001683f  mov     rax, [rbp+30h]
0x180016843  mov     rcx, [rax]
0x180016846  mov     [rbp+28h], rcx
0x18001684a  mov     rax, [rbp+28h]
0x18001684e  cmp     dword ptr [rax], 0E06D7363h
0x180016854  jnz     short loc_1800168AB
0x180016856  mov     rax, [rbp+28h]
0x18001685a  cmp     dword ptr [rax+18h], 4
0x18001685e  jnz     short loc_1800168AB
0x180016860  mov     rax, [rbp+28h]
0x180016864  cmp     dword ptr [rax+20h], 19930520h
0x18001686b  jz      short loc_180016887
0x18001686d  mov     rax, [rbp+28h]
0x180016871  cmp     dword ptr [rax+20h], 19930521h
0x180016878  jz      short loc_180016887
0x18001687a  mov     rax, [rbp+28h]
0x18001687e  cmp     dword ptr [rax+20h], 19930522h
0x180016885  jnz     short loc_1800168AB
0x180016887  call    __vcrt_getptd
0x18001688c  mov     rcx, [rbp+28h]
0x180016890  mov     [rax+20h], rcx
0x180016894  mov     rax, [rbp+30h]
0x180016898  mov     rbx, [rax+8]
0x18001689c  call    __vcrt_getptd
0x1800168a1  mov     [rax+28h], rbx
0x1800168a5  call    _o_terminate_0
0x1800168aa  nop
0x1800168ab  mov     dword ptr [rbp+20h], 0
0x1800168b2  mov     eax, [rbp+20h]
0x1800168b5  add     rsp, 28h
0x1800168b9  pop     rbp
0x1800168ba  pop     rbx
0x1800168bb  retn
```
