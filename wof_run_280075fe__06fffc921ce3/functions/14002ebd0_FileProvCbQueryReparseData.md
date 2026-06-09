# FileProvCbQueryReparseData

- ea: `0x14002ebd0`
- end: `0x14002ec83`
- name: `FileProvCbQueryReparseData`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path`

## callees

- `0x1400115b0`
- `0x1400230a8`
- `0x140023198`
- `0x14002ebd0`

## pseudocode

```c
__int64 __fastcall FileProvCbQueryReparseData(__int64 a1, __int64 a2, int *a3, _DWORD *a4, char a5)
{
  size_t v10; // r8
  int *v11; // rcx
  int v12; // eax

  if ( *a4 >= 8u )
  {
    v10 = *a4 < 0xCu ? 8 : 12;
    *a4 = v10;
    if ( a5 )
    {
      RtlSetUserMemory(a3);
      RtlWriteULongToUser(a3, 1);
    }
    else
    {
      RtlSetVolatileMemory(a3, 0, v10);
      *a3 = 1;
    }
    v11 = a3 + 1;
    v12 = *(_DWORD *)(a2 + 4);
    if ( a5 )
      RtlWriteULongToUser(v11, v12);
    else
      *v11 = v12;
    if ( *a4 >= 0xCu )
    {
      if ( a5 )
        RtlWriteULongToUser(a3 + 2, 0);
      else
        a3[2] = 0;
    }
    return 0;
  }
  else
  {
    *a4 = 8;
    return 3221225507LL;
  }
}

```

## disassembly

```asm
0x14002ebd0  mov     [rsp+arg_0], rbx
0x14002ebd5  mov     [rsp+arg_8], rbp
0x14002ebda  push    rdi
0x14002ebdb  sub     rsp, 20h
0x14002ebdf  mov     eax, [r9]
0x14002ebe2  mov     rdi, r9
0x14002ebe5  mov     rbx, r8
0x14002ebe8  mov     rbp, rdx
0x14002ebeb  cmp     eax, 8
0x14002ebee  jnb     short loc_14002EBFE
0x14002ebf0  mov     dword ptr [r9], 8
0x14002ebf7  mov     eax, 0C0000023h
0x14002ebfc  jmp     short loc_14002EC72
0x14002ebfe  cmp     eax, 0Ch
0x14002ec01  mov     rcx, rbx; void *
0x14002ec04  sbb     eax, eax
0x14002ec06  xor     edx, edx; Val
0x14002ec08  and     eax, 0FFFFFFFCh
0x14002ec0b  lea     r8d, [rax+0Ch]; Size
0x14002ec0f  mov     [r9], r8d
0x14002ec12  cmp     [rsp+28h+arg_20], dl
0x14002ec16  jz      short loc_14002EC2C
0x14002ec18  call    RtlSetUserMemory
0x14002ec1d  mov     edx, 1
0x14002ec22  mov     rcx, rbx
0x14002ec25  call    RtlWriteULongToUser
0x14002ec2a  jmp     short loc_14002EC37
0x14002ec2c  call    RtlSetVolatileMemory
0x14002ec31  mov     dword ptr [rbx], 1
0x14002ec37  cmp     [rsp+28h+arg_20], 0
0x14002ec3c  lea     rcx, [rbx+4]
0x14002ec40  mov     eax, [rbp+4]
0x14002ec43  jz      short loc_14002EC4E
0x14002ec45  mov     edx, eax
0x14002ec47  call    RtlWriteULongToUser
0x14002ec4c  jmp     short loc_14002EC50
0x14002ec4e  mov     [rcx], eax
0x14002ec50  cmp     dword ptr [rdi], 0Ch
0x14002ec53  jb      short loc_14002EC70
0x14002ec55  cmp     [rsp+28h+arg_20], 0
0x14002ec5a  jz      short loc_14002EC69
0x14002ec5c  xor     edx, edx
0x14002ec5e  lea     rcx, [rbx+8]
0x14002ec62  call    RtlWriteULongToUser
0x14002ec67  jmp     short loc_14002EC70
0x14002ec69  mov     dword ptr [rbx+8], 0
0x14002ec70  xor     eax, eax
0x14002ec72  mov     rbx, [rsp+28h+arg_0]
0x14002ec77  mov     rbp, [rsp+28h+arg_8]
0x14002ec7c  add     rsp, 20h
0x14002ec80  pop     rdi
0x14002ec81  retn
```
