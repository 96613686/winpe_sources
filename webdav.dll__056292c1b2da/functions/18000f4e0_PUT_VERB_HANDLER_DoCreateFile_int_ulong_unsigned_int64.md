# PUT_VERB_HANDLER::DoCreateFile(int *,ulong,unsigned __int64 *)

- ea: `0x18000f4e0`
- end: `0x18000f631`
- name: `?DoCreateFile@PUT_VERB_HANDLER@@AEAAJPEAHKPEA_K@Z`
- size: `337`
- prototype: `__int64 __fastcall(PUT_VERB_HANDLER *this, int *, int, LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18000f640`

## callees

- `0x18000f4e0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f54d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f54d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f610`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000f5e8`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000f5e8`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000f5d7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000f606`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000f5d7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000f606`

## pseudocode

```c
__int64 __fastcall PUT_VERB_HANDLER::DoCreateFile(PUT_VERB_HANDLER *this, int *a2, int a3, LARGE_INTEGER *a4)
{
  __int64 v5; // rcx
  void *v8; // rax
  signed int LastError; // eax
  unsigned int v10; // edi
  __int64 v11; // rbx
  __int64 v12; // rax
  unsigned int v14; // ebx
  LARGE_INTEGER v15; // rdx
  signed int v16; // eax
  int v17; // [rsp+20h] [rbp-58h]
  union _LARGE_INTEGER NewFilePointer; // [rsp+80h] [rbp+8h] BYREF

  v5 = *((_QWORD *)this + 30);
  *a2 = 0;
  v8 = (void *)(*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _QWORD, int, unsigned int, _QWORD))(*(_QWORD *)v5 + 72LL))(
                 v5,
                 *((_QWORD *)this + 52),
                 1179926,
                 0,
                 0,
                 2,
                 a3 | 0x80u,
                 0);
  *((_QWORD *)this + 48) = v8;
  if ( v8 == (void *)-1LL )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    v11 = *((_QWORD *)this + 52);
    v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 272LL))(*((_QWORD *)this + 1));
    LOBYTE(v17) = 3;
    (*(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, int))(*(_QWORD *)v12 + 32LL))(
      v12,
      L"Error Creating File",
      v11,
      v10,
      v17);
    return v10;
  }
  else
  {
    v14 = 0;
    if ( a4 )
    {
      v15 = *a4;
      NewFilePointer.QuadPart = 0;
      if ( !v15.QuadPart )
      {
        *a2 = 1;
        return 0;
      }
      if ( !SetFilePointerEx(v8, v15, &NewFilePointer, 0)
        || !SetEndOfFile(*((HANDLE *)this + 48))
        || !SetFilePointerEx(*((HANDLE *)this + 48), 0, &NewFilePointer, 0) )
      {
        v16 = GetLastError();
        v14 = v16;
        if ( v16 > 0 )
          return (unsigned __int16)v16 | 0x80070000;
      }
    }
    return v14;
  }
}

```

## disassembly

```asm
0x18000f4e0  push    rbx
0x18000f4e2  push    rsi
0x18000f4e3  push    rdi
0x18000f4e4  push    r14
0x18000f4e6  sub     rsp, 58h
0x18000f4ea  mov     rsi, rcx
0x18000f4ed  mov     [rsp+78h+var_40], 0
0x18000f4f6  mov     rcx, [rcx+0F0h]
0x18000f4fd  bts     r8d, 7
0x18000f502  mov     [rsp+78h+var_48], r8d
0x18000f507  mov     rdi, r9
0x18000f50a  mov     r14, rdx
0x18000f50d  mov     dword ptr [rdx], 0
0x18000f513  mov     rdx, [rsi+1A0h]
0x18000f51a  xor     r9d, r9d
0x18000f51d  mov     rax, [rcx]
0x18000f520  mov     r8d, 120116h
0x18000f526  mov     [rsp+78h+var_50], 2
0x18000f52e  mov     [rsp+78h+var_58], 0
0x18000f537  mov     rax, [rax+48h]
0x18000f53b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f540  mov     [rsi+180h], rax
0x18000f547  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f54b  jnz     short loc_18000F5A7
0x18000f54d  call    cs:__imp_GetLastError
0x18000f553  mov     edi, eax
0x18000f555  test    eax, eax
0x18000f557  jle     short loc_18000F562
0x18000f559  movzx   edi, ax
0x18000f55c  or      edi, 80070000h
0x18000f562  mov     rcx, [rsi+8]
0x18000f566  mov     rbx, [rsi+1A0h]
0x18000f56d  mov     rax, [rcx]
0x18000f570  mov     rax, [rax+110h]
0x18000f577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f57c  mov     r10, rax
0x18000f57f  mov     byte ptr [rsp+78h+var_58], 3
0x18000f584  mov     r9d, edi
0x18000f587  lea     rdx, aErrorCreatingF; "Error Creating File"
0x18000f58e  mov     r8, rbx
0x18000f591  mov     rcx, [rax]
0x18000f594  mov     rax, [rcx+20h]
0x18000f598  mov     rcx, r10
0x18000f59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5a0  mov     eax, edi
0x18000f5a2  jmp     loc_18000F627
0x18000f5a7  xor     ebx, ebx
0x18000f5a9  test    rdi, rdi
0x18000f5ac  jz      short loc_18000F625
0x18000f5ae  mov     rdx, [rdi]; liDistanceToMove
0x18000f5b1  mov     qword ptr [rsp+78h+NewFilePointer], rbx
0x18000f5b9  test    rdx, rdx
0x18000f5bc  jnz     short loc_18000F5C9
0x18000f5be  mov     dword ptr [r14], 1
0x18000f5c5  xor     eax, eax
0x18000f5c7  jmp     short loc_18000F627
0x18000f5c9  xor     r9d, r9d; dwMoveMethod
0x18000f5cc  lea     r8, [rsp+78h+NewFilePointer]; lpNewFilePointer
0x18000f5d4  mov     rcx, rax; hFile
0x18000f5d7  call    cs:__imp_SetFilePointerEx
0x18000f5dd  test    eax, eax
0x18000f5df  jz      short loc_18000F610
0x18000f5e1  mov     rcx, [rsi+180h]; hFile
0x18000f5e8  call    cs:__imp_SetEndOfFile
0x18000f5ee  test    eax, eax
0x18000f5f0  jz      short loc_18000F610
0x18000f5f2  mov     rcx, [rsi+180h]; hFile
0x18000f5f9  lea     r8, [rsp+78h+NewFilePointer]; lpNewFilePointer
0x18000f601  xor     edx, edx; liDistanceToMove
0x18000f603  xor     r9d, r9d; dwMoveMethod
0x18000f606  call    cs:__imp_SetFilePointerEx
0x18000f60c  test    eax, eax
0x18000f60e  jnz     short loc_18000F625
0x18000f610  call    cs:__imp_GetLastError
0x18000f616  mov     ebx, eax
0x18000f618  test    eax, eax
0x18000f61a  jle     short loc_18000F625
0x18000f61c  movzx   ebx, ax
0x18000f61f  or      ebx, 80070000h
0x18000f625  mov     eax, ebx
0x18000f627  add     rsp, 58h
0x18000f62b  pop     r14
0x18000f62d  pop     rdi
0x18000f62e  pop     rsi
0x18000f62f  pop     rbx
0x18000f630  retn
```
