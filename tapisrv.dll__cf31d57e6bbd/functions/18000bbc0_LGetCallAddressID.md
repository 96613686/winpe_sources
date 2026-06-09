# LGetCallAddressID

- ea: `0x18000bbc0`
- end: `0x18000bc6c`
- name: `LGetCallAddressID`
- size: `172`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180028100`

## callees

- `0x18000bbc0`
- `0x18001aecc`
- `0x18003dc84`
- `0x18003e15c`

## string_xrefs

- `0x18000bc50`: `lineGetCallAddressID: exit, result=x%x`

## pseudocode

```c
__int64 __fastcall LGetCallAddressID(__int64 a1, _DWORD *a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  unsigned int *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx

  if ( dword_180051918 )
  {
    v6 = a2 + 2;
    v7 = ReferenceCall((unsigned int)a2[2], a1);
    if ( v7 )
    {
      v8 = *(unsigned int *)(*(_QWORD *)(v7 + 24) + 52LL);
      a2[3] = v8;
      if ( *(_DWORD *)v7 != 1229734723 )
        *a2 = -2147483624;
      DereferenceObject(v8, *v6, 1);
      if ( !*a2 )
        *a5 = 16;
    }
    else
    {
      *a2 = -2147483624;
    }
  }
  else
  {
    *a2 = -2147483568;
  }
  return TRACELogPrint(524290, "lineGetCallAddressID: exit, result=x%x", *a2);
}

```

## disassembly

```asm
0x18000bbc0  mov     [rsp+arg_0], rbx
0x18000bbc5  mov     [rsp+arg_8], rdx
0x18000bbca  push    rdi
0x18000bbcb  sub     rsp, 30h
0x18000bbcf  mov     rbx, rdx
0x18000bbd2  cmp     cs:dword_180051918, 0
0x18000bbd9  jnz     short loc_18000BBE3
0x18000bbdb  mov     dword ptr [rdx], 80000050h
0x18000bbe1  jmp     short loc_18000BC4D
0x18000bbe3  lea     rdi, [rdx+8]
0x18000bbe7  mov     [rsp+38h+var_18], rdi
0x18000bbec  mov     rdx, rcx
0x18000bbef  mov     ecx, [rdi]
0x18000bbf1  call    ReferenceCall
0x18000bbf6  mov     rdx, rax
0x18000bbf9  test    rax, rax
0x18000bbfc  jnz     short loc_18000BC06
0x18000bbfe  mov     dword ptr [rbx], 80000018h
0x18000bc04  jmp     short loc_18000BC4D
0x18000bc06  mov     rax, [rax+18h]
0x18000bc0a  mov     ecx, [rax+34h]
0x18000bc0d  mov     [rbx+0Ch], ecx
0x18000bc10  cmp     dword ptr [rdx], 494C4343h
0x18000bc16  jz      short loc_18000BC1E
0x18000bc18  mov     dword ptr [rbx], 80000018h
0x18000bc1e  jmp     short loc_18000BC30
0x18000bc20  mov     rbx, [rsp+38h+arg_8]
0x18000bc25  mov     dword ptr [rbx], 80000018h
0x18000bc2b  mov     rdi, [rsp+38h+var_18]
0x18000bc30  mov     r8d, 1
0x18000bc36  mov     edx, [rdi]
0x18000bc38  call    DereferenceObject
0x18000bc3d  cmp     dword ptr [rbx], 0
0x18000bc40  jnz     short loc_18000BC4D
0x18000bc42  mov     rax, [rsp+38h+arg_20]
0x18000bc47  mov     dword ptr [rax], 10h
0x18000bc4d  mov     r8d, [rbx]
0x18000bc50  lea     rdx, aLinegetcalladd; "lineGetCallAddressID: exit, result=x%x"
0x18000bc57  mov     ecx, 80002h
0x18000bc5c  call    TRACELogPrint
0x18000bc61  mov     rbx, [rsp+38h+arg_0]
0x18000bc66  add     rsp, 30h
0x18000bc6a  pop     rdi
0x18000bc6b  retn
```
