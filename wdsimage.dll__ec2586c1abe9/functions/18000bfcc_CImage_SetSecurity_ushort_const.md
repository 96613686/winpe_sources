# CImage::SetSecurity(ushort const *)

- ea: `0x18000bfcc`
- end: `0x18000c142`
- name: `?SetSecurity@CImage@@QEAAJPEBG@Z`
- size: `374`
- prototype: `int(CImage *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005f40`

## callees

- `0x18000bfcc`
- `0x18000d5b0`
- `0x18000d6b0`
- `0x18000dfdc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000c07c`
- `KERNEL32!CloseHandle` at `0x18000c126`
- `KERNEL32!CloseHandle` at `0x18000c07c`
- `KERNEL32!CloseHandle` at `0x18000c126`
- `KERNEL32!CreateFileW` at `0x18000c02d`
- `KERNEL32!CreateFileW` at `0x18000c02d`
- `KERNEL32!GetFileAttributesW` at `0x18000bff3`
- `KERNEL32!GetFileAttributesW` at `0x18000bff3`
- `KERNEL32!GetProcessHeap` at `0x18000c0c6`
- `KERNEL32!GetProcessHeap` at `0x18000c0fd`
- `KERNEL32!GetProcessHeap` at `0x18000c0c6`
- `KERNEL32!GetProcessHeap` at `0x18000c0fd`
- `KERNEL32!HeapFree` at `0x18000c0da`
- `KERNEL32!HeapFree` at `0x18000c111`
- `KERNEL32!HeapFree` at `0x18000c0da`
- `KERNEL32!HeapFree` at `0x18000c111`
- `KERNEL32!GetLastError` at `0x18000c03f`
- `KERNEL32!GetLastError` at `0x18000c03f`

## pseudocode

```c
__int64 __fastcall CImage::SetSecurity(CImage *this, const unsigned __int16 *a2)
{
  const WCHAR *v3; // rcx
  __int64 v4; // rsi
  HANDLE FileW; // rax
  DWORD LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  unsigned int v11; // ebx
  WCHAR *v12; // rcx
  __int64 v13; // rdx
  void *v14; // rbp
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v16; // rdi
  HANDLE v17; // rax
  unsigned __int16 *v19; // [rsp+70h] [rbp+18h] BYREF

  v19 = 0;
  v3 = (const WCHAR *)*((_QWORD *)this + 14);
  v4 = 0;
  if ( v3 && GetFileAttributesW(v3) == -1 )
  {
    FileW = CreateFileW(*((LPCWSTR *)this + 14), 0x40000000u, 3u, 0, 1u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v10 = ElValidateWin32_4(LastError, v8, v9, 1303);
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      if ( (v11 & 0x80000000) == 0 )
        return (unsigned int)-2147467259;
      return v11;
    }
    CloseHandle(FileW);
    v12 = (WCHAR *)*((_QWORD *)this + 14);
    v4 = -1;
  }
  else
  {
    v12 = (WCHAR *)*((_QWORD *)this + 11);
  }
  v11 = pWdsImgSetSecurity(v12, a2, &v19);
  if ( (int)ElValidateHr_5(v11, v13, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 1321) < 0 )
  {
    v16 = v19;
  }
  else
  {
    v14 = (void *)*((_QWORD *)this + 15);
    if ( v14 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
    }
    *((_QWORD *)this + 15) = v19;
    v16 = 0;
  }
  if ( v16 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v16);
  }
  if ( v4 != -1 )
    CloseHandle((HANDLE)v4);
  return v11;
}

```

## disassembly

```asm
0x18000bfcc  mov     [rsp+arg_8], rbx
0x18000bfd1  push    rbp
0x18000bfd2  push    rsi
0x18000bfd3  push    rdi
0x18000bfd4  sub     rsp, 40h
0x18000bfd8  and     [rsp+58h+arg_10], 0
0x18000bfde  mov     rdi, rcx
0x18000bfe1  mov     rcx, [rcx+70h]; lpFileName
0x18000bfe5  xor     esi, esi
0x18000bfe7  mov     rbx, rdx
0x18000bfea  test    rcx, rcx
0x18000bfed  jz      loc_18000C092
0x18000bff3  call    cs:__imp_GetFileAttributesW
0x18000bffa  nop     dword ptr [rax+rax+00h]
0x18000bfff  cmp     eax, 0FFFFFFFFh
0x18000c002  jnz     loc_18000C092
0x18000c008  and     [rsp+58h+var_28], rsi
0x18000c00d  lea     r8d, [rsi+3]; dwShareMode
0x18000c011  mov     rcx, [rdi+70h]; lpFileName
0x18000c015  xor     r9d, r9d; lpSecurityAttributes
0x18000c018  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000c020  mov     edx, 40000000h; dwDesiredAccess
0x18000c025  mov     [rsp+58h+dwCreationDisposition], 1; dwCreationDisposition
0x18000c02d  call    cs:__imp_CreateFileW
0x18000c034  nop     dword ptr [rax+rax+00h]
0x18000c039  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c03d  jnz     short loc_18000C079
0x18000c03f  call    cs:__imp_GetLastError
0x18000c046  nop     dword ptr [rax+rax+00h]
0x18000c04b  mov     ecx, eax
0x18000c04d  mov     r9d, 517h
0x18000c053  call    ElValidateWin32_4
0x18000c058  mov     ebx, eax
0x18000c05a  test    eax, eax
0x18000c05c  jle     short loc_18000C067
0x18000c05e  movzx   ebx, ax
0x18000c061  or      ebx, 80070000h
0x18000c067  test    ebx, ebx
0x18000c069  js      loc_18000C132
0x18000c06f  mov     ebx, 80004005h
0x18000c074  jmp     loc_18000C132
0x18000c079  mov     rcx, rax; hObject
0x18000c07c  call    cs:__imp_CloseHandle
0x18000c083  nop     dword ptr [rax+rax+00h]
0x18000c088  mov     rcx, [rdi+70h]
0x18000c08c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000c090  jmp     short loc_18000C096
0x18000c092  mov     rcx, [rdi+58h]; lpFileName
0x18000c096  lea     r8, [rsp+58h+arg_10]; unsigned __int16 **
0x18000c09b  mov     rdx, rbx; StringSecurityDescriptor
0x18000c09e  call    ?pWdsImgSetSecurity@@YAJPEAG0PEAPEAG@Z; pWdsImgSetSecurity(ushort *,ushort *,ushort * *)
0x18000c0a3  mov     r9d, 529h
0x18000c0a9  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000c0b0  mov     ecx, eax
0x18000c0b2  mov     ebx, eax
0x18000c0b4  call    ElValidateHr_5
0x18000c0b9  test    eax, eax
0x18000c0bb  js      short loc_18000C0F3
0x18000c0bd  mov     rbp, [rdi+78h]
0x18000c0c1  test    rbp, rbp
0x18000c0c4  jz      short loc_18000C0E6
0x18000c0c6  call    cs:__imp_GetProcessHeap
0x18000c0cd  nop     dword ptr [rax+rax+00h]
0x18000c0d2  mov     r8, rbp; lpMem
0x18000c0d5  xor     edx, edx; dwFlags
0x18000c0d7  mov     rcx, rax; hHeap
0x18000c0da  call    cs:__imp_HeapFree
0x18000c0e1  nop     dword ptr [rax+rax+00h]
0x18000c0e6  mov     rax, [rsp+58h+arg_10]
0x18000c0eb  mov     [rdi+78h], rax
0x18000c0ef  xor     edi, edi
0x18000c0f1  jmp     short loc_18000C0F8
0x18000c0f3  mov     rdi, [rsp+58h+arg_10]
0x18000c0f8  test    rdi, rdi
0x18000c0fb  jz      short loc_18000C11D
0x18000c0fd  call    cs:__imp_GetProcessHeap
0x18000c104  nop     dword ptr [rax+rax+00h]
0x18000c109  mov     r8, rdi; lpMem
0x18000c10c  xor     edx, edx; dwFlags
0x18000c10e  mov     rcx, rax; hHeap
0x18000c111  call    cs:__imp_HeapFree
0x18000c118  nop     dword ptr [rax+rax+00h]
0x18000c11d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000c121  jz      short loc_18000C132
0x18000c123  mov     rcx, rsi; hObject
0x18000c126  call    cs:__imp_CloseHandle
0x18000c12d  nop     dword ptr [rax+rax+00h]
0x18000c132  mov     eax, ebx
0x18000c134  mov     rbx, [rsp+58h+arg_8]
0x18000c139  add     rsp, 40h
0x18000c13d  pop     rdi
0x18000c13e  pop     rsi
0x18000c13f  pop     rbp
0x18000c140  retn
```
