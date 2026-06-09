# std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)

- ea: `0x18000bf8c`
- end: `0x18000bfc6`
- name: `?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ`
- size: `58`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `55`
- callee_count: `2`
- tags: ``

## callers

- `0x1800068fc`
- `0x180007bcc`
- `0x1800093c8`
- `0x180009834`
- `0x18000a81c`
- `0x18000acb4`
- `0x18000f6a0`
- `0x18001001c`
- `0x180010298`
- `0x1800105b4`
- `0x180010b0c`
- `0x180010cdc`
- `0x180010e90`
- `0x1800110c0`
- `0x1800116a0`
- `0x1800121dc`
- `0x180012990`
- `0x180012e58`
- `0x180013434`
- `0x1800135d4`
- `0x1800146b8`
- `0x180014954`
- `0x1800162ec`
- `0x180016954`
- `0x1800190ac`
- `0x180019cb4`
- `0x1800203fc`
- `0x180020cf0`
- `0x180021f84`
- `0x1800225a0`
- `0x180022ad8`
- `0x180023078`
- `0x180023e54`
- `0x180024378`
- `0x180024aac`
- `0x180025b5c`
- `0x1800274ac`
- `0x18002b840`
- `0x18002bb98`
- `0x18002c014`
- `0x18002c684`
- `0x18002ccc8`
- `0x18002cd7c`
- `0x18002cfc8`
- `0x18002d1f4`
- `0x18002d588`
- `0x18002db00`
- `0x18002dbb4`
- `0x18002dfc4`
- `0x18002e600`

## callees

- `0x18000bf8c`
- `0x18000bfe4`

## pseudocode

```c
__int64 __fastcall std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
  {
    result = wil::secure_allocator<unsigned char>::deallocate(a1, *a1, a1[2] - *a1);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000bf8c  push    rbx
0x18000bf8e  sub     rsp, 20h
0x18000bf92  mov     rdx, [rcx]
0x18000bf95  mov     rbx, rcx
0x18000bf98  test    rdx, rdx
0x18000bf9b  jz      short loc_18000BFC0
0x18000bf9d  mov     r8, [rcx+10h]
0x18000bfa1  sub     r8, rdx
0x18000bfa4  call    ?deallocate@?$secure_allocator@E@wil@@QEAAXPEAE_K@Z; wil::secure_allocator<uchar>::deallocate(uchar *,unsigned __int64)
0x18000bfa9  mov     qword ptr [rbx], 0
0x18000bfb0  mov     qword ptr [rbx+8], 0
0x18000bfb8  mov     qword ptr [rbx+10h], 0
0x18000bfc0  add     rsp, 20h
0x18000bfc4  pop     rbx
0x18000bfc5  retn
```
