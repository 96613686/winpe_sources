# CWin32SharedMem::Create_(ushort const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x18005f624`
- end: `0x18005f6b5`
- name: `?Create_@CWin32SharedMem@@AEAAJPEBGKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `145`
- prototype: `__int64 __fastcall(CWin32SharedMem *__hidden this, LPCWSTR lpName, DWORD dwMaximumSizeLow, LPSECURITY_ATTRIBUTES lpFileMappingAttributes)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000a90c`
- `0x18000aadc`
- `0x18000eb30`
- `0x180014f20`
- `0x180077d14`
- `0x180079dcc`

## callees

- `0x18005f624`
- `0x18005f6bc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005f689`
- `KERNEL32!GetLastError` at `0x18005f689`
- `KERNEL32!MapViewOfFile` at `0x18005f67a`
- `KERNEL32!MapViewOfFile` at `0x18005f67a`
- `KERNEL32!CreateFileMappingW` at `0x18005f658`
- `KERNEL32!CreateFileMappingW` at `0x18005f658`

## pseudocode

```c
__int64 __fastcall CWin32SharedMem::Create_(
        CWin32SharedMem *this,
        LPCWSTR lpName,
        DWORD dwMaximumSizeLow,
        LPSECURITY_ATTRIBUTES lpFileMappingAttributes)
{
  HANDLE FileMappingW; // rax
  signed int v9; // ebx
  LPVOID v10; // rax
  signed int LastError; // eax

  CWin32SharedMem::Free_(this);
  *((_DWORD *)this + 4) = dwMaximumSizeLow;
  FileMappingW = CreateFileMappingW(
                   (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                   lpFileMappingAttributes,
                   4u,
                   0,
                   dwMaximumSizeLow,
                   lpName);
  *((_QWORD *)this + 3) = FileMappingW;
  if ( !FileMappingW || (v9 = 0, v10 = MapViewOfFile(FileMappingW, 6u, 0, 0, 0), (*((_QWORD *)this + 1) = v10) == 0) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
      CWin32SharedMem::Free_(this);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005f624  push    rbx
0x18005f626  push    rbp
0x18005f627  push    rsi
0x18005f628  push    rdi
0x18005f629  sub     rsp, 38h
0x18005f62d  mov     rsi, r9
0x18005f630  mov     edi, r8d
0x18005f633  mov     rbx, rdx
0x18005f636  mov     rbp, rcx
0x18005f639  call    ?Free_@CWin32SharedMem@@AEAAXXZ; CWin32SharedMem::Free_(void)
0x18005f63e  xor     r9d, r9d; dwMaximumSizeHigh
0x18005f641  mov     [rsp+58h+lpName], rbx; lpName
0x18005f646  mov     rdx, rsi; lpFileMappingAttributes
0x18005f649  mov     [rbp+10h], edi
0x18005f64c  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18005f650  mov     [rsp+58h+dwMaximumSizeLow], edi; dwMaximumSizeLow
0x18005f654  lea     r8d, [r9+4]; flProtect
0x18005f658  call    cs:__imp_CreateFileMappingW
0x18005f65e  mov     [rbp+18h], rax
0x18005f662  test    rax, rax
0x18005f665  jz      short loc_18005F689
0x18005f667  xor     ebx, ebx
0x18005f669  xor     r9d, r9d; dwFileOffsetLow
0x18005f66c  xor     r8d, r8d; dwFileOffsetHigh
0x18005f66f  mov     qword ptr [rsp+58h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x18005f674  mov     rcx, rax; hFileMappingObject
0x18005f677  lea     edx, [rbx+6]; dwDesiredAccess
0x18005f67a  call    cs:__imp_MapViewOfFile
0x18005f680  mov     [rbp+8], rax
0x18005f684  test    rax, rax
0x18005f687  jnz     short loc_18005F6AA
0x18005f689  call    cs:__imp_GetLastError
0x18005f68f  mov     ebx, eax
0x18005f691  test    eax, eax
0x18005f693  jle     short loc_18005F69E
0x18005f695  movzx   ebx, ax
0x18005f698  or      ebx, 80070000h
0x18005f69e  test    ebx, ebx
0x18005f6a0  jns     short loc_18005F6AA
0x18005f6a2  mov     rcx, rbp; this
0x18005f6a5  call    ?Free_@CWin32SharedMem@@AEAAXXZ; CWin32SharedMem::Free_(void)
0x18005f6aa  mov     eax, ebx
0x18005f6ac  add     rsp, 38h
0x18005f6b0  pop     rdi
0x18005f6b1  pop     rsi
0x18005f6b2  pop     rbp
0x18005f6b3  pop     rbx
0x18005f6b4  retn
```
