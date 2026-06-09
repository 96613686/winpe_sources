# SsServerFsControlGetInfoCommonEx

- ea: `0x180008ca0`
- end: `0x180008dd7`
- name: `SsServerFsControlGetInfoCommonEx`
- size: `311`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, ULONG FsControlCode@<edx>, HLOCAL hMem@<r8>, SIZE_T uBytes)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011be0`
- `0x1800218b4`
- `0x180021c60`
- `0x180028ed0`
- `0x18002bd40`
- `0x18002bfe0`
- `0x18002f8b8`

## callees

- `0x180008ca0`
- `0x180008de0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008d15`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008d15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008d97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008dcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008d97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008dcc`

## pseudocode

```c
__int64 __fastcall SsServerFsControlGetInfoCommonEx(
        HANDLE FileHandle,
        ULONG FsControlCode,
        unsigned __int16 *hMem,
        HLOCAL *a4,
        SIZE_T uBytes)
{
  unsigned int v5; // esi
  ULONG v10; // ebp
  unsigned int i; // r14d
  HLOCAL v12; // rax
  unsigned int v13; // eax
  int v15; // [rsp+70h] [rbp+18h]

  v5 = 0;
  v15 = *((_DWORD *)hMem + 23);
  if ( (hMem[36] & 1) != 0 )
  {
    v10 = 1024;
    if ( (unsigned int)uBytes <= 0x400 )
      v10 = uBytes;
  }
  else
  {
    v10 = uBytes;
    if ( (unsigned int)uBytes > 0x2000 )
      v10 = 0x2000;
  }
  *a4 = 0;
  for ( i = 0; i < 5; ++i )
  {
    if ( *a4 )
      LocalFree(*a4);
    v12 = LocalAlloc(0x40u, v10);
    *a4 = v12;
    if ( !v12 )
    {
      v5 = 8;
      break;
    }
    *((_DWORD *)hMem + 23) = v15;
    v13 = SsServerFsControlCommon(FileHandle, FsControlCode, hMem, *a4, v10);
    v5 = v13;
    if ( v13 != 2123 && v13 != 234 || v10 >= (unsigned int)uBytes )
      break;
    v10 = uBytes;
    if ( *((_DWORD *)hMem + 22) + 1024 < (unsigned int)uBytes )
      v10 = *((_DWORD *)hMem + 22) + 1024;
  }
  if ( *a4 && !*((_DWORD *)hMem + 20) )
  {
    LocalFree(*a4);
    *a4 = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180008ca0  push    rbx
0x180008ca2  push    rsi
0x180008ca3  push    rdi
0x180008ca4  sub     rsp, 40h
0x180008ca8  mov     eax, [r8+5Ch]
0x180008cac  xor     esi, esi
0x180008cae  test    byte ptr [r8+48h], 1
0x180008cb3  mov     rbx, r9
0x180008cb6  mov     [rsp+58h+arg_0], rbp
0x180008cbb  mov     rdi, r8
0x180008cbe  mov     [rsp+58h+arg_8], r12
0x180008cc3  mov     r12d, edx
0x180008cc6  mov     [rsp+58h+arg_18], r13
0x180008ccb  mov     r13, rcx
0x180008cce  mov     [rsp+58h+var_20], r14
0x180008cd3  mov     [rsp+58h+var_28], r15
0x180008cd8  mov     r15d, dword ptr [rsp+58h+uBytes]
0x180008ce0  mov     [rsp+58h+arg_10], eax
0x180008ce4  jz      loc_180008D84
0x180008cea  mov     ebp, 400h
0x180008cef  cmp     r15d, ebp
0x180008cf2  cmovbe  ebp, r15d
0x180008cf6  mov     [r9], rsi
0x180008cf9  xor     r14d, r14d
0x180008cfc  cmp     r14d, 5
0x180008d00  jnb     short loc_180008D53
0x180008d02  mov     rcx, [rbx]; hMem
0x180008d05  test    rcx, rcx
0x180008d08  jnz     loc_180008DCC
0x180008d0e  mov     edx, ebp; uBytes
0x180008d10  mov     ecx, 40h ; '@'; uFlags
0x180008d15  call    cs:__imp_LocalAlloc
0x180008d1b  mov     [rbx], rax
0x180008d1e  test    rax, rax
0x180008d21  jz      loc_180008DC5
0x180008d27  mov     eax, [rsp+58h+arg_10]
0x180008d2b  mov     r8, rdi; hMem
0x180008d2e  mov     [rdi+5Ch], eax
0x180008d31  mov     edx, r12d; FsControlCode
0x180008d34  mov     r9, [rbx]; OutputBuffer
0x180008d37  mov     rcx, r13; FileHandle
0x180008d3a  mov     [rsp+58h+var_38], ebp; ULONG
0x180008d3e  call    SsServerFsControlCommon
0x180008d43  mov     esi, eax
0x180008d45  cmp     eax, 84Bh
0x180008d4a  jz      short loc_180008DA6
0x180008d4c  cmp     eax, 0EAh
0x180008d51  jz      short loc_180008DA6
0x180008d53  mov     rcx, [rbx]; hMem
0x180008d56  mov     r15, [rsp+58h+var_28]
0x180008d5b  mov     r14, [rsp+58h+var_20]
0x180008d60  mov     r13, [rsp+58h+arg_18]
0x180008d65  mov     r12, [rsp+58h+arg_8]
0x180008d6a  mov     rbp, [rsp+58h+arg_0]
0x180008d6f  test    rcx, rcx
0x180008d72  jz      short loc_180008D7A
0x180008d74  cmp     dword ptr [rdi+50h], 0
0x180008d78  jz      short loc_180008D97
0x180008d7a  mov     eax, esi
0x180008d7c  add     rsp, 40h
0x180008d80  pop     rdi
0x180008d81  pop     rsi
0x180008d82  pop     rbx
0x180008d83  retn
0x180008d84  mov     eax, 2000h
0x180008d89  mov     ebp, r15d
0x180008d8c  cmp     r15d, eax
0x180008d8f  cmova   ebp, eax
0x180008d92  jmp     loc_180008CF6
0x180008d97  call    cs:__imp_LocalFree
0x180008d9d  mov     qword ptr [rbx], 0
0x180008da4  jmp     short loc_180008D7A
0x180008da6  cmp     ebp, r15d
0x180008da9  jnb     short loc_180008D53
0x180008dab  mov     ecx, [rdi+58h]
0x180008dae  mov     ebp, r15d
0x180008db1  add     ecx, 400h
0x180008db7  cmp     ecx, r15d
0x180008dba  cmovb   ebp, ecx
0x180008dbd  inc     r14d
0x180008dc0  jmp     loc_180008CFC
0x180008dc5  mov     esi, 8
0x180008dca  jmp     short loc_180008D53
0x180008dcc  call    cs:__imp_LocalFree
0x180008dd2  jmp     loc_180008D0E
```
