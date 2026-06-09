# AslRegistryGetStringExpand

- ea: `0x140010844`
- end: `0x140010a61`
- name: `AslRegistryGetStringExpand`
- size: `541`
- prototype: `__int64 __fastcall(wchar_t **, void *, const WCHAR *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14000d8e8`

## callees

- `0x14000ee5c`
- `0x14000f074`
- `0x14001008c`
- `0x140010678`
- `0x140010844`

## import_xrefs

- `msvcrt!wcschr` at `0x14001088e`
- `msvcrt!wcschr` at `0x14001088e`
- `ntdll!RtlAllocateHeap` at `0x1400108fe`
- `ntdll!RtlAllocateHeap` at `0x14001099f`
- `ntdll!RtlAllocateHeap` at `0x1400108fe`
- `ntdll!RtlAllocateHeap` at `0x14001099f`
- `ntdll!RtlFreeHeap` at `0x14001097f`
- `ntdll!RtlFreeHeap` at `0x140010a2b`
- `ntdll!RtlFreeHeap` at `0x140010a48`
- `ntdll!RtlFreeHeap` at `0x14001097f`
- `ntdll!RtlFreeHeap` at `0x140010a2b`
- `ntdll!RtlFreeHeap` at `0x140010a48`

## string_xrefs

- `0x1400108c7`: `AslRegistryGetStringExpand`
- `0x14001091e`: `AslRegistryGetStringExpand`
- `0x1400109fa`: `AslRegistryGetStringExpand`

## pseudocode

```c
__int64 __fastcall AslRegistryGetStringExpand(wchar_t **a1, void *a2, const WCHAR *a3, int a4)
{
  PVOID Heap; // rdi
  int String; // eax
  wchar_t *v8; // rsi
  int v9; // ebx
  int ProcessWowInfo; // eax
  __int64 v11; // r8
  __int16 v12; // r15
  __int16 v13; // r12
  int v14; // ebx
  __int64 v16; // [rsp+28h] [rbp-30h]
  __int16 v17[2]; // [rsp+40h] [rbp-18h] BYREF
  __int16 v18; // [rsp+44h] [rbp-14h] BYREF
  wchar_t *Str[2]; // [rsp+48h] [rbp-10h] BYREF

  Heap = 0;
  v17[0] = -1;
  Str[0] = 0;
  v18 = -1;
  String = AslRegistryGetString(Str, a2, a3);
  v8 = Str[0];
  v9 = String;
  if ( String < 0 )
    goto LABEL_16;
  if ( !wcschr(Str[0], 0x25u) )
  {
    *a1 = v8;
    return 0;
  }
  ProcessWowInfo = AslEnvGetProcessWowInfo(&v18, v17);
  v9 = ProcessWowInfo;
  if ( ProcessWowInfo >= 0 )
  {
    Str[0] = (wchar_t *)260;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
    if ( !Heap )
    {
      v11 = 1476;
LABEL_8:
      AslLogCallPrintf(1, "AslRegistryGetStringExpand", v11, "Out of memory");
      v9 = -1073741801;
      goto LABEL_16;
    }
    v12 = v17[0];
    v13 = v18;
    v9 = AslEnvExpandStrings2(a4, (_DWORD)v8, (_DWORD)Heap, 260, (__int64)Str, v18, v17[0]);
    if ( v9 == -1073741789 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      v14 = (int)Str[0];
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * (__int64)Str[0]);
      if ( !Heap )
      {
        v11 = 1494;
        goto LABEL_8;
      }
      v9 = AslEnvExpandStrings2(a4, (_DWORD)v8, (_DWORD)Heap, v14, (__int64)Str, v13, v12);
    }
    if ( v9 >= 0 )
    {
      *a1 = (wchar_t *)Heap;
      Heap = 0;
      v9 = 0;
    }
    else
    {
      LODWORD(v16) = v9;
      AslLogCallPrintf(
        1,
        "AslRegistryGetStringExpand",
        1509,
        "AslEnvExpandStrings2 failed to expand strings for %ws [%x]",
        v8,
        v16);
    }
    goto LABEL_16;
  }
  AslLogCallPrintf(1, "AslRegistryGetStringExpand", 1464, "AslEnvGetProcessWowInfo failed [%x]", ProcessWowInfo);
LABEL_16:
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140010844  push    rbp
0x140010846  push    rbx
0x140010847  push    rsi
0x140010848  push    rdi
0x140010849  push    r12
0x14001084b  push    r13
0x14001084d  push    r14
0x14001084f  push    r15
0x140010851  mov     rbp, rsp
0x140010854  sub     rsp, 58h
0x140010858  mov     eax, 0FFFFh
0x14001085d  mov     r14, rcx
0x140010860  xor     edi, edi
0x140010862  mov     [rbp+var_18], ax
0x140010866  lea     rcx, [rbp+Str]
0x14001086a  mov     [rbp+Str], rdi
0x14001086e  mov     [rbp+var_14], ax
0x140010872  mov     r13, r9
0x140010875  call    AslRegistryGetString
0x14001087a  mov     rsi, [rbp+Str]
0x14001087e  mov     ebx, eax
0x140010880  test    eax, eax
0x140010882  js      loc_140010A14
0x140010888  lea     edx, [rdi+25h]; Ch
0x14001088b  mov     rcx, rsi; Str
0x14001088e  call    cs:__imp_wcschr
0x140010894  test    rax, rax
0x140010897  jnz     short loc_1400108A3
0x140010899  mov     [r14], rsi
0x14001089c  xor     ebx, ebx
0x14001089e  jmp     loc_140010A4E
0x1400108a3  lea     rdx, [rbp+var_18]
0x1400108a7  lea     rcx, [rbp+var_14]
0x1400108ab  call    AslEnvGetProcessWowInfo
0x1400108b0  mov     ebx, eax
0x1400108b2  test    eax, eax
0x1400108b4  jns     short loc_1400108DD
0x1400108b6  lea     r9, aAslenvgetproce_1; "AslEnvGetProcessWowInfo failed [%x]"
0x1400108bd  mov     dword ptr [rsp+58h+var_38], eax
0x1400108c1  mov     r8d, 5B8h
0x1400108c7  lea     rdx, aAslregistryget_5; "AslRegistryGetStringExpand"
0x1400108ce  mov     ecx, 1
0x1400108d3  call    AslLogCallPrintf
0x1400108d8  jmp     loc_140010A14
0x1400108dd  mov     rcx, gs:60h
0x1400108e6  mov     ebx, 104h
0x1400108eb  mov     edx, 8; Flags
0x1400108f0  mov     [rbp+Str], rbx
0x1400108f4  mov     r8d, 208h; Size
0x1400108fa  mov     rcx, [rcx+30h]; HeapHandle
0x1400108fe  call    cs:__imp_RtlAllocateHeap
0x140010904  mov     rdi, rax
0x140010907  test    rax, rax
0x14001090a  jnz     short loc_140010934
0x14001090c  mov     r8d, 5C4h
0x140010912  lea     r9, aOutOfMemory; "Out of memory"
0x140010919  mov     ecx, 1
0x14001091e  lea     rdx, aAslregistryget_5; "AslRegistryGetStringExpand"
0x140010925  call    AslLogCallPrintf
0x14001092a  mov     ebx, 0C0000017h
0x14001092f  jmp     loc_140010A14
0x140010934  movzx   r15d, [rbp+var_18]
0x140010939  lea     rax, [rbp+Str]
0x14001093d  movzx   r12d, [rbp+var_14]
0x140010942  mov     r9, rbx
0x140010945  mov     [rsp+58h+var_28], r15w
0x14001094b  mov     r8, rdi
0x14001094e  mov     word ptr [rsp+58h+var_30], r12w
0x140010954  mov     rdx, rsi
0x140010957  mov     rcx, r13
0x14001095a  mov     [rsp+58h+var_38], rax
0x14001095f  call    AslEnvExpandStrings2
0x140010964  mov     ebx, eax
0x140010966  cmp     eax, 0C0000023h
0x14001096b  jnz     short loc_1400109E0
0x14001096d  mov     rcx, gs:60h
0x140010976  mov     r8, rdi; P
0x140010979  xor     edx, edx; Flags
0x14001097b  mov     rcx, [rcx+30h]; HeapHandle
0x14001097f  call    cs:__imp_RtlFreeHeap
0x140010985  mov     rcx, gs:60h
0x14001098e  mov     edx, 8; Flags
0x140010993  mov     rbx, [rbp+Str]
0x140010997  mov     rcx, [rcx+30h]; HeapHandle
0x14001099b  lea     r8, [rbx+rbx]; Size
0x14001099f  call    cs:__imp_RtlAllocateHeap
0x1400109a5  mov     rdi, rax
0x1400109a8  test    rax, rax
0x1400109ab  jnz     short loc_1400109B8
0x1400109ad  mov     r8d, 5D6h
0x1400109b3  jmp     loc_140010912
0x1400109b8  mov     [rsp+58h+var_28], r15w
0x1400109be  lea     rax, [rbp+Str]
0x1400109c2  mov     word ptr [rsp+58h+var_30], r12w
0x1400109c8  mov     r9, rbx
0x1400109cb  mov     r8, rdi
0x1400109ce  mov     [rsp+58h+var_38], rax
0x1400109d3  mov     rdx, rsi
0x1400109d6  mov     rcx, r13
0x1400109d9  call    AslEnvExpandStrings2
0x1400109de  mov     ebx, eax
0x1400109e0  test    ebx, ebx
0x1400109e2  jns     short loc_140010A0D
0x1400109e4  mov     dword ptr [rsp+58h+var_30], ebx
0x1400109e8  lea     r9, aAslenvexpandst_0; "AslEnvExpandStrings2 failed to expand s"...
0x1400109ef  mov     r8d, 5E5h
0x1400109f5  mov     [rsp+58h+var_38], rsi
0x1400109fa  lea     rdx, aAslregistryget_5; "AslRegistryGetStringExpand"
0x140010a01  mov     ecx, 1
0x140010a06  call    AslLogCallPrintf
0x140010a0b  jmp     short loc_140010A14
0x140010a0d  mov     [r14], rdi
0x140010a10  xor     edi, edi
0x140010a12  xor     ebx, ebx
0x140010a14  test    rsi, rsi
0x140010a17  jz      short loc_140010A31
0x140010a19  mov     rcx, gs:60h
0x140010a22  mov     r8, rsi; P
0x140010a25  xor     edx, edx; Flags
0x140010a27  mov     rcx, [rcx+30h]; HeapHandle
0x140010a2b  call    cs:__imp_RtlFreeHeap
0x140010a31  test    rdi, rdi
0x140010a34  jz      short loc_140010A4E
0x140010a36  mov     rcx, gs:60h
0x140010a3f  mov     r8, rdi; P
0x140010a42  xor     edx, edx; Flags
0x140010a44  mov     rcx, [rcx+30h]; HeapHandle
0x140010a48  call    cs:__imp_RtlFreeHeap
0x140010a4e  mov     eax, ebx
0x140010a50  add     rsp, 58h
0x140010a54  pop     r15
0x140010a56  pop     r14
0x140010a58  pop     r13
0x140010a5a  pop     r12
0x140010a5c  pop     rdi
0x140010a5d  pop     rsi
0x140010a5e  pop     rbx
0x140010a5f  pop     rbp
0x140010a60  retn
```
