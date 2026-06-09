# CSharedAccessFile::Open(ushort const *,int,int,int,int *)

- ea: `0x180023284`
- end: `0x180023348`
- name: `?Open@CSharedAccessFile@@QEAAHPEBGHHHPEAH@Z`
- size: `196`
- prototype: `int(CSharedAccessFile *__hidden this, const unsigned __int16 *, int, int, int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180023aa0`

## callees

- `0x180022bcc`
- `0x180022ca8`
- `0x180023284`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800232cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800232cc`

## pseudocode

```c
__int64 __fastcall CSharedAccessFile::Open(
        CSharedAccessFile *this,
        const unsigned __int16 *a2,
        __int64 a3,
        int a4,
        int a5,
        int *a6)
{
  HANDLE SharedFileW; // rax
  unsigned int v10; // ebx
  BOOL v11; // ecx
  DWORD v12; // r8d
  char *v13; // rax

  SharedFileW = CreateSharedFileW(a2, 0, 3u, 0x80u, g_DefaultACL);
  *(_QWORD *)this = SharedFileW;
  if ( SharedFileW == (HANDLE)-1LL )
  {
    v10 = 0;
    v11 = GetLastError() == 32;
  }
  else
  {
    CloseHandleWrapper(SharedFileW);
    v10 = 0;
    v11 = 0;
  }
  if ( a6 )
    *a6 = v11;
  if ( !a4 || (v12 = 2, v11) )
    v12 = 4;
  v13 = (char *)CreateSharedFileW(a2, 3u, v12, a5 != 0 ? -2147483520 : 128, g_DefaultACL);
  *(_QWORD *)this = v13;
  LOBYTE(v10) = v13 + 1 != 0;
  return v10;
}

```

## disassembly

```asm
0x180023284  push    rbx
0x180023286  push    rsi
0x180023287  push    rdi
0x180023288  push    r14
0x18002328a  sub     rsp, 38h
0x18002328e  mov     eax, cs:g_DefaultACL
0x180023294  mov     rsi, rdx
0x180023297  xor     edx, edx; dwShareMode
0x180023299  mov     [rsp+58h+var_38], eax; int
0x18002329d  mov     edi, r9d
0x1800232a0  mov     r14, rcx
0x1800232a3  mov     r9d, 80h; dwFlagsAndAttributes
0x1800232a9  mov     rcx, rsi; lpFileName
0x1800232ac  lea     r8d, [rdx+3]; dwCreationDisposition
0x1800232b0  call    CreateSharedFileW
0x1800232b5  mov     [r14], rax
0x1800232b8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800232bc  jz      short loc_1800232CC
0x1800232be  mov     rcx, rax
0x1800232c1  call    CloseHandleWrapper
0x1800232c6  xor     ebx, ebx
0x1800232c8  mov     ecx, ebx
0x1800232ca  jmp     short loc_1800232E2
0x1800232cc  call    cs:__imp_GetLastError
0x1800232d3  nop     dword ptr [rax+rax+00h]
0x1800232d8  xor     ebx, ebx
0x1800232da  cmp     eax, 20h ; ' '
0x1800232dd  mov     ecx, ebx
0x1800232df  setz    cl
0x1800232e2  mov     rax, [rsp+58h+arg_28]
0x1800232ea  test    rax, rax
0x1800232ed  jz      short loc_1800232F1
0x1800232ef  mov     [rax], ecx
0x1800232f1  neg     [rsp+58h+arg_20]
0x1800232f8  mov     eax, cs:g_DefaultACL
0x1800232fe  sbb     r9d, r9d
0x180023301  and     r9d, 80000000h
0x180023308  sub     r9d, 0FFFFFF80h; dwFlagsAndAttributes
0x18002330c  test    edi, edi
0x18002330e  jz      short loc_18002331A
0x180023310  mov     r8d, 2
0x180023316  test    ecx, ecx
0x180023318  jz      short loc_180023320
0x18002331a  mov     r8d, 4; dwCreationDisposition
0x180023320  mov     edx, 3; dwShareMode
0x180023325  mov     [rsp+58h+var_38], eax; int
0x180023329  mov     rcx, rsi; lpFileName
0x18002332c  call    CreateSharedFileW
0x180023331  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023335  mov     [r14], rax
0x180023338  setnz   bl
0x18002333b  mov     eax, ebx
0x18002333d  add     rsp, 38h
0x180023341  pop     r14
0x180023343  pop     rdi
0x180023344  pop     rsi
0x180023345  pop     rbx
0x180023346  retn
```
