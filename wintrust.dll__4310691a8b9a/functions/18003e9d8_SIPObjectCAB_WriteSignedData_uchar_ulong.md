# SIPObjectCAB_::WriteSignedData(uchar *,ulong)

- ea: `0x18003e9d8`
- end: `0x18003ead7`
- name: `?WriteSignedData@SIPObjectCAB_@@AEAAHPEAEK@Z`
- size: `255`
- prototype: `__int64 __fastcall(SIPObjectCAB_ *__hidden this, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18003e430`

## callees

- `0x18003e8a4`
- `0x18003e9d8`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18003eaab`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18003eaab`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003ea5a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003ea5a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003ea85`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003ea85`

## pseudocode

```c
__int64 __fastcall SIPObjectCAB_::WriteSignedData(SIPObjectCAB_ *this, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  __int64 v6; // rdx
  void *v7; // rcx
  __int128 v9; // [rsp+30h] [rbp-18h]
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp+10h] BYREF

  if ( !lpBuffer )
    return 0;
  if ( !nNumberOfBytesToWrite )
    return 0;
  v6 = *((unsigned __int16 *)this + 74);
  LODWORD(v9) = *((_DWORD *)this + 22);
  *((_QWORD *)&v9 + 1) = 0;
  DWORD1(v9) = nNumberOfBytesToWrite;
  if ( *((unsigned __int16 *)this + 58) < (unsigned __int64)(v6 + 20) )
    return 0;
  *(_OWORD *)(*((_QWORD *)this + 16) + v6 + 4) = v9;
  if ( !SIPObjectCAB_::WriteHeader(this) )
    return 0;
  if ( SetFilePointer(*((HANDLE *)this + 1), *((_DWORD *)this + 22), 0, 0) == -1 )
    return 0;
  v7 = (void *)*((_QWORD *)this + 1);
  NumberOfBytesWritten = 0;
  if ( !WriteFile(v7, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0)
    || NumberOfBytesWritten != nNumberOfBytesToWrite )
  {
    return 0;
  }
  (*(void (__fastcall **)(SIPObjectCAB_ *))(*(_QWORD *)this + 152LL))(this);
  SetEndOfFile(*((HANDLE *)this + 1));
  return (*(__int64 (__fastcall **)(SIPObjectCAB_ *))(*(_QWORD *)this + 144LL))(this);
}

```

## disassembly

```asm
0x18003e9d8  mov     [rsp+arg_0], rbx
0x18003e9dd  mov     [rsp+arg_10], rsi
0x18003e9e2  push    rdi
0x18003e9e3  sub     rsp, 40h
0x18003e9e7  mov     edi, r8d
0x18003e9ea  mov     rsi, rdx
0x18003e9ed  mov     rbx, rcx
0x18003e9f0  test    rdx, rdx
0x18003e9f3  jz      loc_18003EAC5
0x18003e9f9  test    r8d, r8d
0x18003e9fc  jz      loc_18003EAC5
0x18003ea02  mov     eax, [rcx+58h]
0x18003ea05  movzx   edx, word ptr [rcx+94h]
0x18003ea0c  movzx   ecx, word ptr [rcx+74h]
0x18003ea10  mov     dword ptr [rsp+48h+var_18], eax
0x18003ea14  mov     qword ptr [rsp+48h+var_18+8], 0
0x18003ea1d  lea     rax, [rdx+14h]
0x18003ea21  mov     dword ptr [rsp+48h+var_18+4], r8d
0x18003ea26  cmp     rcx, rax
0x18003ea29  jb      loc_18003EAC5
0x18003ea2f  mov     rax, [rbx+80h]
0x18003ea36  mov     rcx, rbx; this
0x18003ea39  movups  xmm0, [rsp+48h+var_18]
0x18003ea3e  movdqu  xmmword ptr [rax+rdx+4], xmm0
0x18003ea44  call    ?WriteHeader@SIPObjectCAB_@@AEAAHXZ; SIPObjectCAB_::WriteHeader(void)
0x18003ea49  test    eax, eax
0x18003ea4b  jz      short loc_18003EAC5
0x18003ea4d  mov     edx, [rbx+58h]; lDistanceToMove
0x18003ea50  xor     r9d, r9d; dwMoveMethod
0x18003ea53  mov     rcx, [rbx+8]; hFile
0x18003ea57  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003ea5a  call    cs:__imp_SetFilePointer
0x18003ea60  cmp     eax, 0FFFFFFFFh
0x18003ea63  jz      short loc_18003EAC5
0x18003ea65  mov     rcx, [rbx+8]; hFile
0x18003ea69  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003ea6e  mov     r8d, edi; nNumberOfBytesToWrite
0x18003ea71  mov     [rsp+48h+NumberOfBytesWritten], 0
0x18003ea79  mov     rdx, rsi; lpBuffer
0x18003ea7c  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18003ea85  call    cs:__imp_WriteFile
0x18003ea8b  test    eax, eax
0x18003ea8d  jz      short loc_18003EAC5
0x18003ea8f  cmp     [rsp+48h+NumberOfBytesWritten], edi
0x18003ea93  jnz     short loc_18003EAC5
0x18003ea95  mov     rax, [rbx]
0x18003ea98  mov     rcx, rbx
0x18003ea9b  mov     rax, [rax+98h]
0x18003eaa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eaa7  mov     rcx, [rbx+8]; hFile
0x18003eaab  call    cs:__imp_SetEndOfFile
0x18003eab1  mov     rax, [rbx]
0x18003eab4  mov     rcx, rbx
0x18003eab7  mov     rax, [rax+90h]
0x18003eabe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eac3  jmp     short loc_18003EAC7
0x18003eac5  xor     eax, eax
0x18003eac7  mov     rbx, [rsp+48h+arg_0]
0x18003eacc  mov     rsi, [rsp+48h+arg_10]
0x18003ead1  add     rsp, 40h
0x18003ead5  pop     rdi
0x18003ead6  retn
```
