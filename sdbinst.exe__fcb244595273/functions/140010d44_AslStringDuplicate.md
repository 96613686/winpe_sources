# AslStringDuplicate

- ea: `0x140010d44`
- end: `0x140010f77`
- name: `AslStringDuplicate`
- size: `563`
- prototype: `__int64 __fastcall(_QWORD *, _WORD *)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000f644`
- `0x14001031c`
- `0x140010678`
- `0x14001687c`
- `0x14001a24c`
- `0x14001c290`
- `0x14002b138`

## callees

- `0x14001008c`
- `0x140010d44`
- `0x140011d6c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140010e9a`
- `ntdll!RtlAllocateHeap` at `0x140010e9a`
- `ntdll!RtlFreeHeap` at `0x140010f5a`
- `ntdll!RtlFreeHeap` at `0x140010f5a`

## string_xrefs

- `0x140010ef0`: `RtlStringCchCopyW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslStringDuplicate(_QWORD *a1, _WORD *a2)
{
  void *v4; // rsi
  int v5; // ebx
  __int64 v6; // rax
  _WORD *i; // rcx
  const char *v8; // r9
  __int64 v9; // r8
  __int64 v10; // r14
  unsigned __int64 v11; // rdx
  SIZE_T v12; // rax
  PVOID Heap; // rax
  int v14; // eax
  unsigned __int64 v16; // [rsp+90h] [rbp+18h]

  v4 = 0;
  *a1 = 0;
  v5 = 0;
  if ( a2 )
  {
    v6 = 0x7FFFFFFF;
    for ( i = a2; v6 && *i; ++i )
      --v6;
    if ( !v6 )
      v5 = -1073741811;
    if ( v5 < 0 )
      v16 = 0;
    else
      v16 = 0x7FFFFFFF - v6;
    if ( v5 < 0 )
    {
      v8 = "RtlStringCchLengthW failed [%x]";
      v9 = 590;
LABEL_13:
      AslLogCallPrintf(1, "AslStringDuplicate", v9, v8, v5);
      goto LABEL_29;
    }
    v10 = v16 + 1;
    if ( v16 + 1 < v16 )
    {
      v10 = -1;
      v5 = -1073741675;
      v11 = -1;
    }
    else
    {
      v5 = 0;
      v11 = v16 + 1;
    }
    if ( v5 < 0 )
    {
      v8 = "SIZE_T arithmetic failed [%x]";
      v9 = 602;
      goto LABEL_13;
    }
    v12 = 2 * v11;
    if ( is_mul_ok(v11, 2u) )
    {
      v5 = 0;
    }
    else
    {
      v12 = -1;
      v5 = -1073741675;
    }
    if ( v5 < 0 )
    {
      v8 = "SIZE_T arithmetic failed [%x]";
      v9 = 608;
      goto LABEL_13;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v12);
    v4 = Heap;
    if ( Heap )
    {
      v14 = RtlStringCchCopyW(Heap, v10, a2);
      v5 = v14;
      if ( v14 >= 0 )
      {
        *a1 = v4;
        v4 = 0;
        v5 = 0;
      }
      else
      {
        AslLogCallPrintf(1, "AslStringDuplicate", 632, "RtlStringCchCopyW failed [%x]", v14);
      }
    }
    else
    {
      v5 = -1073741801;
      AslLogCallPrintf(1, "AslStringDuplicate", 615, "Out of memory");
    }
  }
LABEL_29:
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140010d44  mov     rax, rsp
0x140010d47  mov     [rax+8], rbx
0x140010d4b  push    rsi
0x140010d4c  push    rdi
0x140010d4d  push    r12
0x140010d4f  push    r14
0x140010d51  push    r15
0x140010d53  sub     rsp, 50h
0x140010d57  mov     r15, rdx
0x140010d5a  mov     r12, rcx
0x140010d5d  xor     edi, edi
0x140010d5f  mov     [rax+18h], rdi
0x140010d63  mov     esi, edi
0x140010d65  mov     [rax-40h], rdi
0x140010d69  mov     [rcx], rdi
0x140010d6c  mov     ebx, edi
0x140010d6e  test    rdx, rdx
0x140010d71  jz      loc_140010F10
0x140010d77  lea     r8, [rax+18h]
0x140010d7b  mov     edx, 7FFFFFFFh
0x140010d80  mov     eax, edx
0x140010d82  mov     [rsp+78h+var_30], rdx
0x140010d87  mov     rcx, r15
0x140010d8a  mov     [rsp+78h+var_38], rcx
0x140010d8f  test    rax, rax
0x140010d92  jz      short loc_140010DAC
0x140010d94  cmp     [rcx], di
0x140010d97  jz      short loc_140010DAC
0x140010d99  add     rcx, 2
0x140010d9d  mov     [rsp+78h+var_38], rcx
0x140010da2  dec     rax
0x140010da5  mov     [rsp+78h+var_30], rax
0x140010daa  jmp     short loc_140010D8F
0x140010dac  mov     ecx, 0C000000Dh
0x140010db1  test    rax, rax
0x140010db4  cmovz   ebx, ecx
0x140010db7  test    ebx, ebx
0x140010db9  js      short loc_140010DC3
0x140010dbb  sub     rdx, rax
0x140010dbe  mov     [r8], rdx
0x140010dc1  jmp     short loc_140010DC6
0x140010dc3  mov     [r8], rdi
0x140010dc6  test    ebx, ebx
0x140010dc8  jns     short loc_140010DCD
0x140010dca  mov     [r8], rdi
0x140010dcd  mov     [rsp+78h+var_48], ebx
0x140010dd1  test    ebx, ebx
0x140010dd3  jns     short loc_140010DFC
0x140010dd5  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x140010ddc  mov     r8d, 24Eh
0x140010de2  mov     [rsp+78h+var_58], ebx
0x140010de6  lea     rdx, aAslstringdupli_0; "AslStringDuplicate"
0x140010ded  mov     ecx, 1
0x140010df2  call    AslLogCallPrintf
0x140010df7  jmp     loc_140010F14
0x140010dfc  mov     rax, [rsp+78h+arg_10]
0x140010e04  lea     r14, [rax+1]
0x140010e08  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140010e0c  cmp     r14, rax
0x140010e0f  jb      short loc_140010E20
0x140010e11  mov     [rsp+78h+arg_10], r14
0x140010e19  mov     ebx, edi
0x140010e1b  mov     rdx, r14
0x140010e1e  jmp     short loc_140010E33
0x140010e20  mov     r14, rcx
0x140010e23  mov     [rsp+78h+arg_10], rcx
0x140010e2b  mov     ebx, 0C0000095h
0x140010e30  mov     rdx, rcx
0x140010e33  mov     [rsp+78h+var_48], ebx
0x140010e37  test    ebx, ebx
0x140010e39  jns     short loc_140010E4A
0x140010e3b  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x140010e42  mov     r8d, 25Ah
0x140010e48  jmp     short loc_140010DE2
0x140010e4a  mov     [rsp+78h+arg_18], rdi
0x140010e52  mov     eax, 2
0x140010e57  mul     rdx
0x140010e5a  test    rdx, rdx
0x140010e5d  jnz     short loc_140010E63
0x140010e5f  mov     ebx, edi
0x140010e61  jmp     short loc_140010E6B
0x140010e63  mov     rax, rcx
0x140010e66  mov     ebx, 0C0000095h
0x140010e6b  mov     [rsp+78h+var_48], ebx
0x140010e6f  test    ebx, ebx
0x140010e71  jns     short loc_140010E85
0x140010e73  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x140010e7a  mov     r8d, 260h
0x140010e80  jmp     loc_140010DE2
0x140010e85  mov     rcx, gs:60h
0x140010e8e  mov     r8, rax; Size
0x140010e91  mov     edx, 8; Flags
0x140010e96  mov     rcx, [rcx+30h]; HeapHandle
0x140010e9a  call    cs:__imp_RtlAllocateHeap
0x140010ea0  mov     rsi, rax
0x140010ea3  mov     [rsp+78h+var_40], rax
0x140010ea8  test    rax, rax
0x140010eab  jnz     short loc_140010ED4
0x140010ead  mov     ebx, 0C0000017h
0x140010eb2  mov     [rsp+78h+var_48], ebx
0x140010eb6  lea     r9, aOutOfMemory; "Out of memory"
0x140010ebd  mov     r8d, 267h
0x140010ec3  lea     rdx, aAslstringdupli_0; "AslStringDuplicate"
0x140010eca  lea     ecx, [rax+1]
0x140010ecd  call    AslLogCallPrintf
0x140010ed2  jmp     short loc_140010F14
0x140010ed4  mov     r8, r15
0x140010ed7  mov     rdx, r14
0x140010eda  mov     rcx, rsi
0x140010edd  call    RtlStringCchCopyW
0x140010ee2  mov     ebx, eax
0x140010ee4  mov     [rsp+78h+var_48], eax
0x140010ee8  test    eax, eax
0x140010eea  jns     short loc_140010F02
0x140010eec  mov     [rsp+78h+var_58], eax
0x140010ef0  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140010ef7  mov     r8d, 278h
0x140010efd  jmp     loc_140010DE6
0x140010f02  mov     [r12], rsi
0x140010f06  mov     rsi, rdi
0x140010f09  mov     [rsp+78h+var_40], rdi
0x140010f0e  mov     ebx, edi
0x140010f10  mov     [rsp+78h+var_48], ebx
0x140010f14  jmp     short loc_140010F43
0x140010f16  mov     ebx, eax
0x140010f18  mov     [rsp+78h+var_48], eax
0x140010f1c  mov     [rsp+78h+var_58], eax
0x140010f20  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x140010f27  mov     r8d, 289h
0x140010f2d  lea     rdx, aAslstringdupli_0; "AslStringDuplicate"
0x140010f34  mov     ecx, 1
0x140010f39  call    AslLogCallPrintf
0x140010f3e  mov     rsi, [rsp+78h+var_40]
0x140010f43  test    rsi, rsi
0x140010f46  jz      short loc_140010F60
0x140010f48  mov     rcx, gs:60h
0x140010f51  mov     r8, rsi; P
0x140010f54  xor     edx, edx; Flags
0x140010f56  mov     rcx, [rcx+30h]; HeapHandle
0x140010f5a  call    cs:__imp_RtlFreeHeap
0x140010f60  mov     eax, ebx
0x140010f62  mov     rbx, [rsp+78h+arg_0]
0x140010f6a  add     rsp, 50h
0x140010f6e  pop     r15
0x140010f70  pop     r14
0x140010f72  pop     r12
0x140010f74  pop     rdi
0x140010f75  pop     rsi
0x140010f76  retn
0x14002e711  push    rbp
0x14002e713  sub     rsp, 30h
0x14002e717  mov     rbp, rdx
0x14002e71a  mov     rax, [rcx]
0x14002e71d  xor     ecx, ecx
0x14002e71f  cmp     dword ptr [rax], 0C00000FDh
0x14002e725  setnz   cl
0x14002e728  mov     [rbp+34h], ecx
0x14002e72b  mov     eax, [rbp+34h]
0x14002e72e  add     rsp, 30h
0x14002e732  pop     rbp
0x14002e733  retn
```
