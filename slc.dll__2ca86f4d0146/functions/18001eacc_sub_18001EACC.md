# sub_18001EACC

- ea: `0x18001eacc`
- end: `0x18001eb08`
- name: `sub_18001EACC`
- size: `60`
- prototype: `__int64 __fastcall(int, __int64, _DWORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d5e8`
- `0x18001d6b8`
- `0x18001d788`
- `0x18001d858`
- `0x18001ef38`

## callees

- `0x18001d9c8`
- `0x18001e540`
- `0x18001eacc`

## pseudocode

```c
__int64 __fastcall sub_18001EACC(int a1, __int64 a2, _DWORD *a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( a1 )
  {
    if ( (unsigned int)(2 * a1) >> 1 == a1 )
    {
      *a3 = 2 * a1;
    }
    else
    {
      v3 = -2147024362;
      sub_18001D9C8(-2147024362);
    }
  }
  else
  {
    *a3 = 0;
  }
  sub_18001E540(v3);
  return v3;
}

```

## disassembly

```asm
0x18001eacc  push    rbx
0x18001eace  sub     rsp, 20h
0x18001ead2  xor     ebx, ebx
0x18001ead4  test    ecx, ecx
0x18001ead6  jz      short loc_18001EAF6
0x18001ead8  lea     edx, [rcx+rcx]
0x18001eadb  mov     eax, edx
0x18001eadd  shr     eax, 1
0x18001eadf  cmp     eax, ecx
0x18001eae1  jz      short loc_18001EAF1
0x18001eae3  mov     ebx, 80070216h
0x18001eae8  mov     ecx, ebx
0x18001eaea  call    sub_18001D9C8
0x18001eaef  jmp     short loc_18001EAF9
0x18001eaf1  mov     [r8], edx
0x18001eaf4  jmp     short loc_18001EAF9
0x18001eaf6  mov     [r8], ebx
0x18001eaf9  mov     ecx, ebx
0x18001eafb  call    sub_18001E540
0x18001eb00  mov     eax, ebx
0x18001eb02  add     rsp, 20h
0x18001eb06  pop     rbx
0x18001eb07  retn
```
