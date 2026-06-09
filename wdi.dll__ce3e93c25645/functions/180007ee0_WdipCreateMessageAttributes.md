# WdipCreateMessageAttributes

- ea: `0x180007ee0`
- end: `0x180007f4a`
- name: `WdipCreateMessageAttributes`
- size: `106`
- prototype: `LPVOID __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000cec0`
- `0x18000d6cc`

## callees

- `0x180001340`
- `0x180003160`
- `0x180007ee0`

## import_xrefs

- `ntdll!AlpcInitializeMessageAttribute` at `0x180007eff`
- `ntdll!AlpcInitializeMessageAttribute` at `0x180007f26`
- `ntdll!AlpcInitializeMessageAttribute` at `0x180007eff`
- `ntdll!AlpcInitializeMessageAttribute` at `0x180007f26`

## pseudocode

```c
LPVOID __fastcall WdipCreateMessageAttributes(__int64 a1)
{
  unsigned int v1; // edi
  LPVOID result; // rax
  LPVOID v3; // rbx
  SIZE_T v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  v1 = a1;
  AlpcInitializeMessageAttribute(a1, 0, 0, &v4);
  result = WdipAlloc(v4);
  v3 = result;
  if ( result )
  {
    if ( (int)AlpcInitializeMessageAttribute(v1, result, v4, &v4) >= 0 )
    {
      return v3;
    }
    else
    {
      WdipFree(v3);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007ee0  mov     [rsp+arg_0], rbx
0x180007ee5  push    rdi
0x180007ee6  sub     rsp, 20h
0x180007eea  lea     r9, [rsp+28h+arg_8]
0x180007eef  mov     [rsp+28h+arg_8], 0
0x180007ef8  xor     r8d, r8d
0x180007efb  xor     edx, edx
0x180007efd  mov     edi, ecx
0x180007eff  call    cs:__imp_AlpcInitializeMessageAttribute
0x180007f05  mov     rcx, [rsp+28h+arg_8]
0x180007f0a  call    WdipAlloc
0x180007f0f  mov     rbx, rax
0x180007f12  test    rax, rax
0x180007f15  jz      short loc_180007F3F
0x180007f17  mov     r8, [rsp+28h+arg_8]
0x180007f1c  lea     r9, [rsp+28h+arg_8]
0x180007f21  mov     rdx, rax
0x180007f24  mov     ecx, edi
0x180007f26  call    cs:__imp_AlpcInitializeMessageAttribute
0x180007f2c  test    eax, eax
0x180007f2e  jns     short loc_180007F3C
0x180007f30  mov     rcx, rbx
0x180007f33  call    WdipFree
0x180007f38  xor     eax, eax
0x180007f3a  jmp     short loc_180007F3F
0x180007f3c  mov     rax, rbx
0x180007f3f  mov     rbx, [rsp+28h+arg_0]
0x180007f44  add     rsp, 20h
0x180007f48  pop     rdi
0x180007f49  retn
```
