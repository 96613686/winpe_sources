# SdbpGetMappedTagData

- ea: `0x140013f74`
- end: `0x140013ff1`
- name: `SdbpGetMappedTagData`
- size: `125`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140013824`
- `0x140013898`
- `0x140013f04`
- `0x140015538`
- `0x140018cb4`
- `0x140018d48`
- `0x14001b2f0`
- `0x14001f90c`

## callees

- `0x14001008c`
- `0x140013f74`
- `0x14001415c`

## string_xrefs

- `0x140013f96`: `Trying to read mapped data past the end of the database offset 0x%x size 0x%x`

## pseudocode

```c
__int64 __fastcall SdbpGetMappedTagData(__int64 a1, int a2)
{
  __int64 v3; // rdx
  __int64 v4; // rbx

  v3 = (unsigned int)SdbpGetTagHeadSize() + a2;
  if ( (unsigned int)v3 >= *(_DWORD *)(a1 + 20) )
  {
    AslLogCallPrintf(
      1,
      "SdbpGetMappedData",
      915,
      "Trying to read mapped data past the end of the database offset 0x%x size 0x%x",
      v3,
      *(_DWORD *)(a1 + 20));
    v4 = 0;
LABEL_4:
    AslLogCallPrintf(1, "SdbpGetMappedTagData", 550, "Error getting ptr to tag data");
    return v4;
  }
  v4 = v3 + *(_QWORD *)(a1 + 8);
  if ( !v4 )
    goto LABEL_4;
  return v4;
}

```

## disassembly

```asm
0x140013f74  mov     [rsp+arg_0], rbx
0x140013f79  push    rdi
0x140013f7a  sub     rsp, 30h
0x140013f7e  mov     ebx, edx
0x140013f80  mov     rdi, rcx
0x140013f83  call    SdbpGetTagHeadSize
0x140013f88  lea     edx, [rax+rbx]
0x140013f8b  mov     eax, [rdi+14h]
0x140013f8e  cmp     edx, eax
0x140013f90  jb      short loc_140013FBC
0x140013f92  mov     [rsp+38h+var_10], eax
0x140013f96  lea     r9, aTryingToReadMa; "Trying to read mapped data past the end"...
0x140013f9d  mov     [rsp+38h+var_18], edx
0x140013fa1  mov     r8d, 393h
0x140013fa7  lea     rdx, aSdbpgetmappedd; "SdbpGetMappedData"
0x140013fae  mov     ecx, 1
0x140013fb3  call    AslLogCallPrintf
0x140013fb8  xor     ebx, ebx
0x140013fba  jmp     short loc_140013FC5
0x140013fbc  mov     rbx, [rdi+8]
0x140013fc0  add     rbx, rdx
0x140013fc3  jnz     short loc_140013FE3
0x140013fc5  lea     r9, aErrorGettingPt; "Error getting ptr to tag data"
0x140013fcc  mov     r8d, 226h
0x140013fd2  lea     rdx, aSdbpgetmappedt_0; "SdbpGetMappedTagData"
0x140013fd9  mov     ecx, 1
0x140013fde  call    AslLogCallPrintf
0x140013fe3  mov     rax, rbx
0x140013fe6  mov     rbx, [rsp+38h+arg_0]
0x140013feb  add     rsp, 30h
0x140013fef  pop     rdi
0x140013ff0  retn
```
