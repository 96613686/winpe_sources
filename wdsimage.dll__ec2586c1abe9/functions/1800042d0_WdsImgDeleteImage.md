# WdsImgDeleteImage

- ea: `0x1800042d0`
- end: `0x180004311`
- name: `WdsImgDeleteImage`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180003c68`
- `0x1800042d0`
- `0x1800096c0`

## pseudocode

```c
__int64 __fastcall WdsImgDeleteImage(CImage *a1)
{
  unsigned int v1; // ebx
  __int64 v2; // rdx
  __int64 v3; // r8

  if ( a1 )
  {
    if ( *((_DWORD *)a1 + 4) == 4 )
    {
      v1 = CImage::Delete(a1, 1);
      ElValidateHr_0(v1, v2, v3, 0x7A3u);
    }
    else
    {
      return (unsigned int)-1056833019;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v1;
}

```

## disassembly

```asm
0x1800042d0  push    rbx
0x1800042d2  sub     rsp, 20h
0x1800042d6  test    rcx, rcx
0x1800042d9  jnz     short loc_1800042E2
0x1800042db  mov     ebx, 80070057h
0x1800042e0  jmp     short loc_180004308
0x1800042e2  cmp     dword ptr [rcx+10h], 4
0x1800042e6  jz      short loc_1800042EF
0x1800042e8  mov     ebx, 0C1020205h
0x1800042ed  jmp     short loc_180004308
0x1800042ef  mov     edx, 1; int
0x1800042f4  call    ?Delete@CImage@@QEAAJH@Z; CImage::Delete(int)
0x1800042f9  mov     r9d, 7A3h
0x1800042ff  mov     ecx, eax
0x180004301  mov     ebx, eax
0x180004303  call    ElValidateHr_0
0x180004308  mov     eax, ebx
0x18000430a  add     rsp, 20h
0x18000430e  pop     rbx
0x18000430f  retn
```
