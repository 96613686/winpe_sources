# InitializePrivateHpAllocator(void)

- ea: `0x18002e4a0`
- end: `0x18002e56c`
- name: `?InitializePrivateHpAllocator@@YAKXZ`
- size: `204`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002e68c`

## callees

- `0x18002e4a0`
- `0x18002e5bc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002e4e9`
- `KERNEL32!GetLastError` at `0x18002e52a`
- `KERNEL32!GetLastError` at `0x18002e4e9`
- `KERNEL32!GetLastError` at `0x18002e52a`
- `KERNEL32!HeapSetInformation` at `0x18002e51a`
- `KERNEL32!HeapSetInformation` at `0x18002e51a`
- `KERNEL32!HeapCreate` at `0x18002e4d1`
- `KERNEL32!HeapCreate` at `0x18002e4d1`

## pseudocode

```c
__int64 InitializePrivateHpAllocator(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // edi
  HANDLE v2; // rax
  DWORD v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // eax

  v0 = 0;
  if ( !dword_180049D98 )
  {
    dword_180049D98 = 1;
    v1 = 0;
    v2 = HeapCreate(0, 0, 0);
    hHeap = v2;
    if ( v2 )
    {
      if ( !HeapSetInformation(v2, HeapEnableTerminationOnCorruption, 0, 0) )
      {
        LastError = GetLastError();
        v11 = ElValidateWin32_27(LastError, v9, v10, 175);
        if ( !v11 )
          v11 = 31;
        v1 = v11;
      }
    }
    else
    {
      v3 = GetLastError();
      v1 = ElValidateWin32_27(v3, v4, v5, 162);
      if ( !v1 )
        v1 = 31;
    }
    ElValidateWin32_27(v1, v6, v7, 130);
    return v1;
  }
  return v0;
}

```

## disassembly

```asm
0x18002e4a0  mov     [rsp+arg_0], rbx
0x18002e4a5  push    rdi
0x18002e4a6  sub     rsp, 20h
0x18002e4aa  mov     eax, cs:dword_180049D98
0x18002e4b0  xor     ebx, ebx
0x18002e4b2  test    eax, eax
0x18002e4b4  jnz     loc_18002E55E
0x18002e4ba  mov     eax, cs:dword_180049D98
0x18002e4c0  xor     r8d, r8d; dwMaximumSize
0x18002e4c3  inc     eax
0x18002e4c5  xor     edx, edx; dwInitialSize
0x18002e4c7  xor     ecx, ecx; flOptions
0x18002e4c9  mov     cs:dword_180049D98, eax
0x18002e4cf  mov     edi, ebx
0x18002e4d1  call    cs:__imp_HeapCreate
0x18002e4d8  nop     dword ptr [rax+rax+00h]
0x18002e4dd  mov     cs:hHeap, rax
0x18002e4e4  test    rax, rax
0x18002e4e7  jnz     short loc_18002E50D
0x18002e4e9  call    cs:__imp_GetLastError
0x18002e4f0  nop     dword ptr [rax+rax+00h]
0x18002e4f5  mov     ecx, eax
0x18002e4f7  mov     r9d, 0A2h
0x18002e4fd  call    ElValidateWin32_27
0x18002e502  mov     edi, eax
0x18002e504  test    eax, eax
0x18002e506  jnz     short loc_18002E54F
0x18002e508  lea     edi, [rbx+1Fh]
0x18002e50b  jmp     short loc_18002E54F
0x18002e50d  xor     r9d, r9d; HeapInformationLength
0x18002e510  xor     r8d, r8d; HeapInformation
0x18002e513  mov     rcx, rax; HeapHandle
0x18002e516  lea     edx, [r9+1]; HeapInformationClass
0x18002e51a  call    cs:__imp_HeapSetInformation
0x18002e521  nop     dword ptr [rax+rax+00h]
0x18002e526  test    eax, eax
0x18002e528  jnz     short loc_18002E54F
0x18002e52a  call    cs:__imp_GetLastError
0x18002e531  nop     dword ptr [rax+rax+00h]
0x18002e536  mov     ecx, eax
0x18002e538  mov     r9d, 0AFh
0x18002e53e  call    ElValidateWin32_27
0x18002e543  mov     edi, 1Fh
0x18002e548  test    eax, eax
0x18002e54a  cmovz   eax, edi
0x18002e54d  mov     edi, eax
0x18002e54f  mov     r9d, 82h
0x18002e555  mov     ecx, edi
0x18002e557  call    ElValidateWin32_27
0x18002e55c  mov     ebx, edi
0x18002e55e  mov     eax, ebx
0x18002e560  mov     rbx, [rsp+28h+arg_0]
0x18002e565  add     rsp, 20h
0x18002e569  pop     rdi
0x18002e56a  retn
```
