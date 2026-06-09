# ReadRegistryDword

- ea: `0x14000b854`
- end: `0x14000b8ff`
- name: `ReadRegistryDword`
- size: `171`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000a284`
- `0x14000b734`
- `0x14000c4a4`

## callees

- `0x140001118`
- `0x140001168`
- `0x1400011b0`
- `0x14000164c`
- `0x14000b854`
- `0x14000b908`

## string_xrefs

- `0x14000b872`: `UevFilter.ReadRegistryDword: Entry\n`
- `0x14000b8c7`: `UevFilter.ReadRegistryDword: Invalid parameter specified\n`
- `0x14000b8db`: `UevFilter.ReadRegistryDword: Exit, status = 0x%X\n`

## pseudocode

```c
__int64 __fastcall ReadRegistryDword(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2, _DWORD *a3)
{
  __int64 v6; // r8
  int v7; // ebx
  PVOID v8; // rcx
  PVOID P; // [rsp+30h] [rbp+8h] BYREF

  P = 0;
  DbgTrace(2, "UevFilter.ReadRegistryDword: Entry\n");
  if ( a1 && a2 && a3 )
  {
    *a3 = 0;
    v7 = ReadRegistryValue(a1, a2, v6, &P);
    if ( v7 >= 0 )
    {
      v8 = P;
      *a3 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      FreeGenericBuffer(v8);
    }
  }
  else
  {
    DbgTraceErr("UevFilter.ReadRegistryDword: Invalid parameter specified\n");
    v7 = -1073741811;
  }
  DbgTraceFrmt(2, "UevFilter.ReadRegistryDword: Exit, status = 0x%X\n", v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000b854  mov     [rsp+arg_8], rbx
0x14000b859  mov     [rsp+arg_10], rsi
0x14000b85e  push    rdi
0x14000b85f  sub     rsp, 20h
0x14000b863  mov     rbx, rdx
0x14000b866  mov     [rsp+28h+P], 0
0x14000b86f  mov     rsi, rcx
0x14000b872  lea     rdx, aUevfilterReadr_0; "UevFilter.ReadRegistryDword: Entry\n"
0x14000b879  mov     ecx, 2
0x14000b87e  mov     rdi, r8
0x14000b881  call    DbgTrace
0x14000b886  test    rsi, rsi
0x14000b889  jz      short loc_14000B8C7
0x14000b88b  test    rbx, rbx
0x14000b88e  jz      short loc_14000B8C7
0x14000b890  test    rdi, rdi
0x14000b893  jz      short loc_14000B8C7
0x14000b895  lea     r9, [rsp+28h+P]
0x14000b89a  mov     dword ptr [rdi], 0
0x14000b8a0  mov     rdx, rbx
0x14000b8a3  mov     rcx, rsi
0x14000b8a6  call    ReadRegistryValue
0x14000b8ab  mov     ebx, eax
0x14000b8ad  test    eax, eax
0x14000b8af  js      short loc_14000B8D8
0x14000b8b1  mov     rcx, [rsp+28h+P]; P
0x14000b8b6  mov     edx, [rcx+8]
0x14000b8b9  mov     r8d, [rdx+rcx]
0x14000b8bd  mov     [rdi], r8d
0x14000b8c0  call    FreeGenericBuffer
0x14000b8c5  jmp     short loc_14000B8D8
0x14000b8c7  lea     rcx, aUevfilterReadr_3; "UevFilter.ReadRegistryDword: Invalid pa"...
0x14000b8ce  call    DbgTraceErr
0x14000b8d3  mov     ebx, 0C000000Dh
0x14000b8d8  mov     r8d, ebx
0x14000b8db  lea     rdx, aUevfilterReadr_2; "UevFilter.ReadRegistryDword: Exit, stat"...
0x14000b8e2  mov     ecx, 2
0x14000b8e7  call    DbgTraceFrmt
0x14000b8ec  mov     rsi, [rsp+28h+arg_10]
0x14000b8f1  mov     eax, ebx
0x14000b8f3  mov     rbx, [rsp+28h+arg_8]
0x14000b8f8  add     rsp, 20h
0x14000b8fc  pop     rdi
0x14000b8fd  retn
```
