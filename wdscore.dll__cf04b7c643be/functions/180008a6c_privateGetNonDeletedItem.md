# privateGetNonDeletedItem

- ea: `0x180008a6c`
- end: `0x180008ab5`
- name: `privateGetNonDeletedItem`
- size: `73`
- prototype: ``
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x180001f24`
- `0x1800022bc`
- `0x180002344`
- `0x180002364`
- `0x1800026fc`
- `0x180002f5c`
- `0x180003108`
- `0x180003804`
- `0x180003958`
- `0x1800039dc`
- `0x180003d18`
- `0x180004830`
- `0x180004e6c`
- `0x180005950`
- `0x180005d54`
- `0x1800060f0`
- `0x180006c44`
- `0x180006cb4`
- `0x180007184`
- `0x1800072f4`
- `0x180007330`
- `0x180007904`
- `0x180007f40`
- `0x1800087e0`
- `0x180008bc8`
- `0x18000a658`

## callees

- `0x180008a6c`
- `0x180008abc`

## pseudocode

```c
__int64 __fastcall privateGetNonDeletedItem(__int64 a1, int a2)
{
  __int64 v3; // rbx

  if ( a1 )
  {
    do
    {
      if ( !*(_DWORD *)(a1 + 32) )
        break;
      v3 = *(_QWORD *)((-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + a1 + 16);
      DeleteListItem(*(_QWORD *)a1, a1);
      a1 = v3;
    }
    while ( v3 );
  }
  return a1;
}

```

## disassembly

```asm
0x180008a6c  mov     [rsp+arg_0], rbx
0x180008a71  push    rdi
0x180008a72  sub     rsp, 20h
0x180008a76  mov     edi, edx
0x180008a78  test    rcx, rcx
0x180008a7b  jz      short loc_180008AA6
0x180008a7d  cmp     dword ptr [rcx+20h], 0
0x180008a81  jz      short loc_180008AA6
0x180008a83  mov     eax, edi
0x180008a85  mov     rdx, rcx
0x180008a88  neg     eax
0x180008a8a  sbb     r8, r8
0x180008a8d  and     r8, 0FFFFFFFFFFFFFFF8h
0x180008a91  mov     rbx, [r8+rcx+10h]
0x180008a96  mov     rcx, [rcx]
0x180008a99  call    DeleteListItem
0x180008a9e  mov     rcx, rbx
0x180008aa1  test    rbx, rbx
0x180008aa4  jnz     short loc_180008A7D
0x180008aa6  mov     rbx, [rsp+28h+arg_0]
0x180008aab  mov     rax, rcx
0x180008aae  add     rsp, 20h
0x180008ab2  pop     rdi
0x180008ab3  retn
```
