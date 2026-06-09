# CFileStream::CreateInstance(ushort const *,ulong,IStream * *)

- ea: `0x18005b9f8`
- end: `0x18005bb13`
- name: `?CreateInstance@CFileStream@@SAJPEBGKPEAPEAUIStream@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct IStream **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18005b288`

## callees

- `0x180004110`
- `0x18000c150`
- `0x18000d610`
- `0x18002ff5c`
- `0x18005b9f8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005ba5f`
- `KERNEL32!GetLastError` at `0x18005ba5f`
- `KERNEL32!CloseHandle` at `0x18005bad1`
- `KERNEL32!CloseHandle` at `0x18005bad1`
- `KERNEL32!CreateFileW` at `0x18005ba50`
- `KERNEL32!CreateFileW` at `0x18005ba50`

## pseudocode

```c
__int64 __fastcall CFileStream::CreateInstance(const unsigned __int16 *a1, __int64 a2, struct IStream **a3)
{
  unsigned int v5; // ebx
  const struct std::nothrow_t *v6; // rdx
  HANDLE FileW; // rbp
  signed int LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  void *v11; // rdi
  __int64 v12; // r8

  if ( !a1 )
  {
    v5 = -2147024809;
    goto LABEL_13;
  }
  if ( !a3 )
  {
    v5 = -2147467261;
    goto LABEL_13;
  }
  *a3 = 0;
  FileW = CreateFileW(a1, 0xC0000000, 0, 0, 2u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    v11 = operator new(0x228u, v6);
    if ( v11 )
    {
      *((_DWORD *)v11 + 2) = 1;
      *(_QWORD *)v11 = &CFileStream::`vftable';
      *((_QWORD *)v11 + 2) = FileW;
      *((_DWORD *)v11 + 6) = -1073741824;
      DllAddRef(v10, v9, v12);
      StringCchCopyW((unsigned __int16 *)v11 + 14, 0x104u, a1);
      v5 = 0;
      *a3 = (struct IStream *)v11;
      return v5;
    }
    v5 = -2147024882;
    CloseHandle(FileW);
    goto LABEL_13;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
  {
LABEL_13:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_758d0e18d61c3b3cc13520c88bbdf2ff_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18005b9f8  push    rbx
0x18005b9fa  push    rbp
0x18005b9fb  push    rsi
0x18005b9fc  push    rdi
0x18005b9fd  sub     rsp, 48h
0x18005ba01  mov     rsi, r8
0x18005ba04  mov     rbx, rcx
0x18005ba07  test    rcx, rcx
0x18005ba0a  jnz     short loc_18005BA16
0x18005ba0c  mov     ebx, 80070057h
0x18005ba11  jmp     loc_18005BAD7
0x18005ba16  test    rsi, rsi
0x18005ba19  jnz     short loc_18005BA25
0x18005ba1b  mov     ebx, 80004003h
0x18005ba20  jmp     loc_18005BAD7
0x18005ba25  mov     qword ptr [r8], 0
0x18005ba2c  xor     r9d, r9d; lpSecurityAttributes
0x18005ba2f  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18005ba38  xor     r8d, r8d; dwShareMode
0x18005ba3b  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18005ba43  mov     edx, 0C0000000h; dwDesiredAccess
0x18005ba48  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x18005ba50  call    cs:__imp_CreateFileW
0x18005ba56  mov     rbp, rax
0x18005ba59  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005ba5d  jnz     short loc_18005BA7E
0x18005ba5f  call    cs:__imp_GetLastError
0x18005ba65  mov     ebx, eax
0x18005ba67  test    eax, eax
0x18005ba69  jle     short loc_18005BA74
0x18005ba6b  movzx   ebx, ax
0x18005ba6e  or      ebx, 80070000h
0x18005ba74  test    ebx, ebx
0x18005ba76  jns     loc_18005BB08
0x18005ba7c  jmp     short loc_18005BAD7
0x18005ba7e  mov     ecx, 228h; unsigned __int64
0x18005ba83  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005ba88  mov     rdi, rax
0x18005ba8b  test    rax, rax
0x18005ba8e  jz      short loc_18005BAC9
0x18005ba90  lea     rax, ??_7CFileStream@@6B@; const CFileStream::`vftable'
0x18005ba97  mov     dword ptr [rdi+8], 1
0x18005ba9e  mov     [rdi], rax
0x18005baa1  mov     [rdi+10h], rbp
0x18005baa5  mov     dword ptr [rdi+18h], 0C0000000h
0x18005baac  call    DllAddRef
0x18005bab1  lea     rcx, [rdi+1Ch]; unsigned __int16 *
0x18005bab5  mov     r8, rbx; unsigned __int16 *
0x18005bab8  mov     edx, 104h; unsigned __int64
0x18005babd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005bac2  xor     ebx, ebx
0x18005bac4  mov     [rsi], rdi
0x18005bac7  jmp     short loc_18005BB08
0x18005bac9  mov     ebx, 8007000Eh
0x18005bace  mov     rcx, rbp; hObject
0x18005bad1  call    cs:__imp_CloseHandle
0x18005bad7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bade  lea     rax, WPP_GLOBAL_Control
0x18005bae5  cmp     rcx, rax
0x18005bae8  jz      short loc_18005BB08
0x18005baea  test    byte ptr [rcx+1Ch], 2
0x18005baee  jz      short loc_18005BB08
0x18005baf0  mov     rcx, [rcx+10h]
0x18005baf4  lea     r8, WPP_758d0e18d61c3b3cc13520c88bbdf2ff_Traceguids
0x18005bafb  mov     edx, 0Ah
0x18005bb00  mov     r9d, ebx
0x18005bb03  call    WPP_SF_d
0x18005bb08  mov     eax, ebx
0x18005bb0a  add     rsp, 48h
0x18005bb0e  pop     rdi
0x18005bb0f  pop     rsi
0x18005bb10  pop     rbp
0x18005bb11  pop     rbx
0x18005bb12  retn
```
