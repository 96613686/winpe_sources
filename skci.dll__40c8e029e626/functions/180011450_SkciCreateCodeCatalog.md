# SkciCreateCodeCatalog

- ea: `0x180011450`
- end: `0x18001152e`
- name: `SkciCreateCodeCatalog`
- size: `222`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180011450`
- `0x18004421c`

## import_xrefs

- `securekernel!SkobCreateHandle` at `0x1800114e3`
- `securekernel!SkobCreateHandle` at `0x1800114e3`
- `securekernel!SkmmFreeSecureAllocation` at `0x1800114fb`
- `securekernel!SkmmFreeSecureAllocation` at `0x1800114fb`
- `securekernel!SkobCreateObject` at `0x180011497`
- `securekernel!SkobCreateObject` at `0x180011497`
- `securekernel!SkobDereferenceObject` at `0x18001150c`
- `securekernel!SkobDereferenceObject` at `0x18001150c`

## pseudocode

```c
__int64 __fastcall SkciCreateCodeCatalog(__int64 a1, unsigned __int64 a2, int a3, __int64 a4)
{
  int Handle; // ebx
  unsigned int v9; // r9d
  __int64 v10; // rdx
  __int64 v12; // [rsp+58h] [rbp+10h] BYREF

  v12 = 0;
  if ( a2 <= 0xFFFFFFFF )
  {
    Handle = SkobCreateObject(&SkciCatalogType, &v12);
    if ( Handle >= 0 )
    {
      v9 = (unsigned int)g_CiDeveloperMode >> 15;
      LOBYTE(v9) = (g_CiDeveloperMode & 0x8000) != 0;
      Handle = CiVerifyAndAddCatalogToLoadedListWithID(a3, a1, a2, v9, v12);
      if ( Handle >= 0 )
      {
        LOBYTE(v10) = 1;
        Handle = SkobCreateHandle(v12, v10, 0, a4);
        if ( Handle >= 0 )
          SkmmFreeSecureAllocation(a1, a2);
      }
      SkobDereferenceObject(v12);
    }
  }
  else
  {
    return (unsigned int)-1073741584;
  }
  return (unsigned int)Handle;
}

```

## disassembly

```asm
0x180011450  mov     [rsp+arg_0], rbx
0x180011455  mov     [rsp+arg_10], rbp
0x18001145a  push    rsi
0x18001145b  push    rdi
0x18001145c  push    r14
0x18001145e  sub     rsp, 30h
0x180011462  mov     eax, 0FFFFFFFFh
0x180011467  mov     [rsp+48h+arg_8], 0
0x180011470  mov     rbp, r9
0x180011473  mov     r14, r8
0x180011476  mov     rdi, rdx
0x180011479  mov     rsi, rcx
0x18001147c  cmp     rdx, rax
0x18001147f  jbe     short loc_18001148B
0x180011481  mov     ebx, 0C00000F0h
0x180011486  jmp     loc_180011518
0x18001148b  lea     rdx, [rsp+48h+arg_8]
0x180011490  lea     rcx, SkciCatalogType
0x180011497  call    cs:__imp_SkobCreateObject
0x18001149e  nop     dword ptr [rax+rax+00h]
0x1800114a3  mov     ebx, eax
0x1800114a5  test    eax, eax
0x1800114a7  js      short loc_180011518
0x1800114a9  mov     r9d, cs:g_CiDeveloperMode
0x1800114b0  mov     r8d, edi
0x1800114b3  mov     rax, [rsp+48h+arg_8]
0x1800114b8  mov     rdx, rsi
0x1800114bb  shr     r9d, 0Fh
0x1800114bf  mov     rcx, r14
0x1800114c2  and     r9b, 1
0x1800114c6  mov     [rsp+48h+var_28], rax
0x1800114cb  call    CiVerifyAndAddCatalogToLoadedListWithID
0x1800114d0  mov     ebx, eax
0x1800114d2  test    eax, eax
0x1800114d4  js      short loc_180011507
0x1800114d6  mov     rcx, [rsp+48h+arg_8]
0x1800114db  mov     r9, rbp
0x1800114de  xor     r8d, r8d
0x1800114e1  mov     dl, 1
0x1800114e3  call    cs:__imp_SkobCreateHandle
0x1800114ea  nop     dword ptr [rax+rax+00h]
0x1800114ef  mov     ebx, eax
0x1800114f1  test    eax, eax
0x1800114f3  js      short loc_180011507
0x1800114f5  mov     rdx, rdi
0x1800114f8  mov     rcx, rsi
0x1800114fb  call    cs:__imp_SkmmFreeSecureAllocation
0x180011502  nop     dword ptr [rax+rax+00h]
0x180011507  mov     rcx, [rsp+48h+arg_8]
0x18001150c  call    cs:__imp_SkobDereferenceObject
0x180011513  nop     dword ptr [rax+rax+00h]
0x180011518  mov     rbp, [rsp+48h+arg_10]
0x18001151d  mov     eax, ebx
0x18001151f  mov     rbx, [rsp+48h+arg_0]
0x180011524  add     rsp, 30h
0x180011528  pop     r14
0x18001152a  pop     rdi
0x18001152b  pop     rsi
0x18001152c  retn
```
