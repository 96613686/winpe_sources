# PUT_VERB_HANDLER::OnReadData(IAsyncBuffer *)

- ea: `0x18000fa00`
- end: `0x18000faee`
- name: `?OnReadData@PUT_VERB_HANDLER@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIAsyncBuffer@@@Z`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x180003634`
- `0x18000f3ec`
- `0x18000fa00`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa7c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000fa59`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000fa59`

## pseudocode

```c
__int64 __fastcall PUT_VERB_HANDLER::OnReadData(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  DWORD v5; // ebx
  const void *v6; // rax
  signed int LastError; // eax
  unsigned int v9; // edi
  __int64 v10; // rbx
  __int64 v11; // rax
  int lpOverlapped; // [rsp+20h] [rbp-38h]
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  v2 = *a2;
  NumberOfBytesWritten = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *))(v2 + 24))(a2);
  v6 = (const void *)(*(__int64 (__fastcall **)(__int64 *))(*a2 + 8))(a2);
  if ( WriteFile(*(HANDLE *)(a1 - 296 + 384), v6, v5, &NumberOfBytesWritten, 0) )
  {
    *(_QWORD *)(a1 + 96) += (*(unsigned int (__fastcall **)(__int64 *))(*a2 + 24))(a2);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v10 = *(_QWORD *)(a1 + 120);
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 - 288) + 272LL))(*(_QWORD *)(a1 - 288));
    LOBYTE(lpOverlapped) = 3;
    (*(void (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, int))(*(_QWORD *)v11 + 32LL))(
      v11,
      L"Error Writing File",
      v10,
      v9,
      lpOverlapped);
    PUT_VERB_HANDLER::Cleanup((PUT_VERB_HANDLER *)(a1 - 296), 0);
    DAV_BASE_HANDLER::MapAndHandleError((DAV_BASE_HANDLER *)(a1 - 296), v9);
    return 2;
  }
}

```

## disassembly

```asm
0x18000fa00  push    rbx
0x18000fa02  push    rbp
0x18000fa03  push    rsi
0x18000fa04  push    rdi
0x18000fa05  sub     rsp, 38h
0x18000fa09  mov     rax, [rdx]
0x18000fa0c  mov     rsi, rcx
0x18000fa0f  mov     rcx, rdx
0x18000fa12  mov     [rsp+58h+NumberOfBytesWritten], 0
0x18000fa1a  mov     rdi, rdx
0x18000fa1d  mov     rax, [rax+18h]
0x18000fa21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa26  mov     r8, [rdi]
0x18000fa29  mov     ebx, eax
0x18000fa2b  mov     rcx, rdi
0x18000fa2e  mov     rax, [r8+8]
0x18000fa32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa37  lea     rbp, [rsi-128h]
0x18000fa3e  mov     qword ptr [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18000fa47  mov     rcx, [rbp+180h]; hFile
0x18000fa4e  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000fa53  mov     r8d, ebx; nNumberOfBytesToWrite
0x18000fa56  mov     rdx, rax; lpBuffer
0x18000fa59  call    cs:__imp_WriteFile
0x18000fa5f  test    eax, eax
0x18000fa61  jz      short loc_18000FA7C
0x18000fa63  mov     rax, [rdi]
0x18000fa66  mov     rcx, rdi
0x18000fa69  mov     rax, [rax+18h]
0x18000fa6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa72  mov     eax, eax
0x18000fa74  add     [rsi+60h], rax
0x18000fa78  xor     eax, eax
0x18000fa7a  jmp     short loc_18000FAE5
0x18000fa7c  call    cs:__imp_GetLastError
0x18000fa82  mov     edi, eax
0x18000fa84  test    eax, eax
0x18000fa86  jle     short loc_18000FA91
0x18000fa88  movzx   edi, ax
0x18000fa8b  or      edi, 80070000h
0x18000fa91  mov     rcx, [rsi-120h]
0x18000fa98  mov     rbx, [rsi+78h]
0x18000fa9c  mov     rax, [rcx]
0x18000fa9f  mov     rax, [rax+110h]
0x18000faa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faab  mov     rcx, rax
0x18000faae  mov     byte ptr [rsp+58h+lpOverlapped], 3
0x18000fab3  mov     r8, rbx
0x18000fab6  lea     rdx, aErrorWritingFi; "Error Writing File"
0x18000fabd  mov     r9, [rax]
0x18000fac0  mov     rax, [r9+20h]
0x18000fac4  mov     r9d, edi
0x18000fac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000facc  xor     edx, edx; int
0x18000face  mov     rcx, rbp; this
0x18000fad1  call    ?Cleanup@PUT_VERB_HANDLER@@AEAAJH@Z; PUT_VERB_HANDLER::Cleanup(int)
0x18000fad6  mov     edx, edi; int
0x18000fad8  mov     rcx, rbp; this
0x18000fadb  call    ?MapAndHandleError@DAV_BASE_HANDLER@@QEAAXJ@Z; DAV_BASE_HANDLER::MapAndHandleError(long)
0x18000fae0  mov     eax, 2
0x18000fae5  add     rsp, 38h
0x18000fae9  pop     rdi
0x18000faea  pop     rsi
0x18000faeb  pop     rbp
0x18000faec  pop     rbx
0x18000faed  retn
```
