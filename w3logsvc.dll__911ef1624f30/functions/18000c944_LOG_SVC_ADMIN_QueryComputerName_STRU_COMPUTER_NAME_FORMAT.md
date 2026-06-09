# LOG_SVC_ADMIN::QueryComputerName(STRU *,_COMPUTER_NAME_FORMAT)

- ea: `0x18000c944`
- end: `0x18000ca1d`
- name: `?QueryComputerName@LOG_SVC_ADMIN@@AEAAJPEAVSTRU@@W4_COMPUTER_NAME_FORMAT@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(LOG_SVC_ADMIN *this, struct STRU *, COMPUTER_NAME_FORMAT)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000bc64`

## callees

- `0x180001008`
- `0x180001048`
- `0x18000c944`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c98f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c98f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000c985`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000c9db`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000c985`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000c9db`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000ca02`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000ca02`

## pseudocode

```c
__int64 __fastcall LOG_SVC_ADMIN::QueryComputerName(LOG_SVC_ADMIN *this, struct STRU *a2, COMPUTER_NAME_FORMAT a3)
{
  WCHAR *v5; // rax
  WCHAR *v6; // rdi
  unsigned int v7; // ebx
  signed int LastError; // eax
  WCHAR *v9; // rax
  DWORD nSize; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+54h] [rbp+Ch]

  v12 = HIDWORD(this);
  nSize = 15;
  v5 = (WCHAR *)operator new(0x1Eu);
  v6 = v5;
  if ( !v5 )
    return (unsigned int)-2147024882;
  if ( GetComputerNameExW(a3, v5, &nSize) )
    goto LABEL_10;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError != 234 )
    goto LABEL_8;
  ++nSize;
  operator delete(v6);
  v9 = (WCHAR *)operator new(saturated_mul(nSize, 2u));
  v6 = v9;
  if ( v9 )
  {
    if ( !GetComputerNameExW(a3, v9, &nSize) )
    {
      LastError = GetLastError();
      v7 = LastError;
LABEL_8:
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_11;
    }
LABEL_10:
    v7 = STRU::Copy(a2, v6);
LABEL_11:
    operator delete(v6);
    return v7;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x18000c944  mov     qword ptr [rsp+nSize], rcx
0x18000c949  push    rbx
0x18000c94a  push    rbp
0x18000c94b  push    rsi
0x18000c94c  push    rdi
0x18000c94d  sub     rsp, 28h
0x18000c951  mov     ecx, 1Eh; Size
0x18000c956  mov     [rsp+48h+nSize], 0Fh
0x18000c95e  mov     esi, r8d
0x18000c961  mov     rbp, rdx
0x18000c964  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c969  mov     rdi, rax
0x18000c96c  test    rax, rax
0x18000c96f  jnz     short loc_18000C97B
0x18000c971  mov     ebx, 8007000Eh
0x18000c976  jmp     loc_18000CA12
0x18000c97b  lea     r8, [rsp+48h+nSize]; nSize
0x18000c980  mov     rdx, rdi; lpBuffer
0x18000c983  mov     ecx, esi; NameType
0x18000c985  call    cs:__imp_GetComputerNameExW
0x18000c98b  test    eax, eax
0x18000c98d  jnz     short loc_18000C9FC
0x18000c98f  call    cs:__imp_GetLastError
0x18000c995  mov     ebx, eax
0x18000c997  cmp     eax, 0EAh
0x18000c99c  jnz     short loc_18000C9ED
0x18000c99e  inc     [rsp+48h+nSize]
0x18000c9a2  mov     rcx, rdi; Block
0x18000c9a5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c9aa  mov     ecx, [rsp+48h+nSize]
0x18000c9ae  mov     eax, 2
0x18000c9b3  mul     rcx
0x18000c9b6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c9bd  cmovb   rax, rcx
0x18000c9c1  mov     rcx, rax; Size
0x18000c9c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c9c9  mov     rdi, rax
0x18000c9cc  test    rax, rax
0x18000c9cf  jz      short loc_18000C971
0x18000c9d1  lea     r8, [rsp+48h+nSize]; nSize
0x18000c9d6  mov     rdx, rax; lpBuffer
0x18000c9d9  mov     ecx, esi; NameType
0x18000c9db  call    cs:__imp_GetComputerNameExW
0x18000c9e1  test    eax, eax
0x18000c9e3  jnz     short loc_18000C9FC
0x18000c9e5  call    cs:__imp_GetLastError
0x18000c9eb  mov     ebx, eax
0x18000c9ed  test    eax, eax
0x18000c9ef  jle     short loc_18000CA0A
0x18000c9f1  movzx   ebx, ax
0x18000c9f4  or      ebx, 80070000h
0x18000c9fa  jmp     short loc_18000CA0A
0x18000c9fc  mov     rdx, rdi
0x18000c9ff  mov     rcx, rbp
0x18000ca02  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000ca08  mov     ebx, eax
0x18000ca0a  mov     rcx, rdi; Block
0x18000ca0d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ca12  mov     eax, ebx
0x18000ca14  add     rsp, 28h
0x18000ca18  pop     rdi
0x18000ca19  pop     rsi
0x18000ca1a  pop     rbp
0x18000ca1b  pop     rbx
0x18000ca1c  retn
```
