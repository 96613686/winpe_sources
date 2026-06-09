# SmpPathCanBeTrustedIsNotARedirection

- ea: `0x14001598c`
- end: `0x140015adf`
- name: `SmpPathCanBeTrustedIsNotARedirection`
- size: `339`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1400130f4`
- `0x14001426c`
- `0x140015ae8`

## callees

- `0x14001598c`
- `0x140019a5c`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140015a10`
- `ntdll!RtlAllocateHeap` at `0x140015a10`
- `ntdll!RtlFreeHeap` at `0x140015aaf`
- `ntdll!RtlFreeHeap` at `0x140015aaf`
- `ntdll!RtlCompareUnicodeStrings` at `0x140015a8c`
- `ntdll!RtlCompareUnicodeStrings` at `0x140015a8c`

## pseudocode

```c
bool __fastcall SmpPathCanBeTrustedIsNotARedirection(HANDLE Handle, unsigned __int16 *a2, int a3)
{
  bool v3; // r14
  unsigned int FinalPathNameByHandleW; // eax
  unsigned int v8; // ebx
  unsigned int v9; // eax
  WCHAR *Heap; // rdi
  const WCHAR *v11; // r8
  __int64 v12; // rdx
  __int16 v13; // cx
  char v15; // [rsp+38h] [rbp-240h] BYREF

  v3 = 0;
  if ( *a2 >= 0xCu )
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(Handle);
    v8 = FinalPathNameByHandleW;
    if ( FinalPathNameByHandleW )
    {
      v9 = FinalPathNameByHandleW + 2;
      if ( v9 > 0x106 )
      {
        Heap = (WCHAR *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), SmBaseTag, 2LL * v9);
        if ( !Heap )
          return v3;
        v8 = GetFinalPathNameByHandleW(Handle);
        if ( !v8 )
        {
LABEL_15:
          RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Heap);
          return v3;
        }
        v11 = Heap + 4;
      }
      else
      {
        Heap = 0;
        v11 = (const WCHAR *)&v15;
      }
      if ( *a2 >= (unsigned __int64)(2LL * (int)v8) )
      {
        if ( a3 && v8 > 7 )
        {
          v12 = v8 - 4;
          v11[v8 - 3] = 0;
          ++v8;
          v13 = 92;
        }
        else
        {
          v12 = v8 - 4;
          v13 = 0;
        }
        v11[v12] = v13;
        v3 = RtlCompareUnicodeStrings((PCWCH)(*((_QWORD *)a2 + 1) + 8LL), v8 - 3, v11, v8 - 3, 1u) == 0;
      }
      if ( Heap )
        goto LABEL_15;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14001598c  mov     [rsp+arg_10], rbx
0x140015991  push    rbp
0x140015992  push    rsi
0x140015993  push    rdi
0x140015994  push    r14
0x140015996  push    r15
0x140015998  sub     rsp, 250h
0x14001599f  mov     rax, cs:__security_cookie
0x1400159a6  xor     rax, rsp
0x1400159a9  mov     [rsp+278h+var_38], rax
0x1400159b1  xor     r14b, r14b
0x1400159b4  mov     r15d, r8d
0x1400159b7  cmp     word ptr [rdx], 0Ch
0x1400159bb  mov     rbp, rdx
0x1400159be  mov     rsi, rcx
0x1400159c1  jb      loc_140015AB5
0x1400159c7  xor     r9d, r9d
0x1400159ca  lea     rdx, [rsp+278h+var_248]
0x1400159cf  mov     r8d, 104h
0x1400159d5  call    GetFinalPathNameByHandleW
0x1400159da  mov     ebx, eax
0x1400159dc  test    eax, eax
0x1400159de  jz      loc_140015AB5
0x1400159e4  add     eax, 2
0x1400159e7  cmp     eax, 106h
0x1400159ec  ja      short loc_1400159F7
0x1400159ee  xor     edi, edi
0x1400159f0  lea     r8, [rsp+278h+var_240]
0x1400159f5  jmp     short loc_140015A3D
0x1400159f7  mov     rcx, gs:60h
0x140015a00  mov     edx, cs:SmBaseTag; Flags
0x140015a06  mov     r8d, eax
0x140015a09  add     r8, r8; Size
0x140015a0c  mov     rcx, [rcx+30h]; HeapHandle
0x140015a10  call    cs:__imp_RtlAllocateHeap
0x140015a16  mov     rdi, rax
0x140015a19  test    rax, rax
0x140015a1c  jz      loc_140015AB5
0x140015a22  xor     r9d, r9d
0x140015a25  mov     r8d, ebx
0x140015a28  mov     rdx, rax
0x140015a2b  mov     rcx, rsi; Handle
0x140015a2e  call    GetFinalPathNameByHandleW
0x140015a33  mov     ebx, eax
0x140015a35  test    eax, eax
0x140015a37  jz      short loc_140015A9D
0x140015a39  lea     r8, [rdi+8]; String2
0x140015a3d  movzx   eax, word ptr [rbp+0]
0x140015a41  movsxd  rcx, ebx
0x140015a44  add     rcx, rcx
0x140015a47  cmp     rax, rcx
0x140015a4a  jb      short loc_140015A98
0x140015a4c  test    r15d, r15d
0x140015a4f  jz      short loc_140015A6A
0x140015a51  cmp     ebx, 7
0x140015a54  jbe     short loc_140015A6A
0x140015a56  xor     eax, eax
0x140015a58  lea     ecx, [rbx-3]
0x140015a5b  lea     edx, [rbx-4]
0x140015a5e  mov     [r8+rcx*2], ax
0x140015a63  inc     ebx
0x140015a65  lea     ecx, [rax+5Ch]
0x140015a68  jmp     short loc_140015A72
0x140015a6a  xor     eax, eax
0x140015a6c  lea     edx, [rbx-4]
0x140015a6f  movzx   ecx, ax
0x140015a72  mov     [r8+rdx*2], cx
0x140015a77  lea     eax, [rbx-3]
0x140015a7a  mov     rcx, [rbp+8]
0x140015a7e  add     rcx, 8; String1
0x140015a82  mov     edx, eax; String1Length
0x140015a84  mov     r9d, eax; String2Length
0x140015a87  mov     [rsp+278h+CaseInSensitive], 1; CaseInSensitive
0x140015a8c  call    cs:__imp_RtlCompareUnicodeStrings
0x140015a92  test    eax, eax
0x140015a94  setz    r14b
0x140015a98  test    rdi, rdi
0x140015a9b  jz      short loc_140015AB5
0x140015a9d  mov     rcx, gs:60h
0x140015aa6  mov     r8, rdi; BaseAddress
0x140015aa9  xor     edx, edx; Flags
0x140015aab  mov     rcx, [rcx+30h]; HeapHandle
0x140015aaf  call    cs:__imp_RtlFreeHeap
0x140015ab5  mov     al, r14b
0x140015ab8  mov     rcx, [rsp+278h+var_38]
0x140015ac0  xor     rcx, rsp; StackCookie
0x140015ac3  call    __security_check_cookie
0x140015ac8  mov     rbx, [rsp+278h+arg_10]
0x140015ad0  add     rsp, 250h
0x140015ad7  pop     r15
0x140015ad9  pop     r14
0x140015adb  pop     rdi
0x140015adc  pop     rsi
0x140015add  pop     rbp
0x140015ade  retn
```
