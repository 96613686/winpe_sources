# TSetPermissibleMasks

- ea: `0x180035280`
- end: `0x1800353a3`
- name: `TSetPermissibleMasks`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180028100`

## callees

- `0x18001c7c0`
- `0x180034540`
- `0x180035280`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18003531a`
- `KERNEL32!GetCurrentThreadId` at `0x180035352`
- `KERNEL32!GetCurrentThreadId` at `0x18003531a`
- `KERNEL32!GetCurrentThreadId` at `0x180035352`
- `KERNEL32!LeaveCriticalSection` at `0x1800352d8`
- `KERNEL32!LeaveCriticalSection` at `0x180035378`
- `KERNEL32!LeaveCriticalSection` at `0x1800352d8`
- `KERNEL32!LeaveCriticalSection` at `0x180035378`
- `KERNEL32!EnterCriticalSection` at `0x1800352b4`
- `KERNEL32!EnterCriticalSection` at `0x18003530a`
- `KERNEL32!EnterCriticalSection` at `0x1800352b4`
- `KERNEL32!EnterCriticalSection` at `0x18003530a`

## pseudocode

```c
_DWORD *__fastcall TSetPermissibleMasks(unsigned __int64 a1, int *a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  unsigned __int64 v6; // rdi
  int v8; // ebx
  int v9; // eax
  unsigned __int64 v10; // rbx
  size_t v11; // rdx
  size_t v12; // rdx
  __int64 v13; // rcx
  _DWORD *result; // rax

  v6 = a1 >> 4;
  EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((a1 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
  v8 = *(_DWORD *)(a1 + 216);
  LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v6 & gdwPointerToLockTableIndexBits));
  if ( (dword_180051900 & 2) == 0 || (v8 & 1) != 0 )
  {
    v10 = (unsigned int)a2[2] + ((unsigned __int64)(unsigned int)a2[3] << 32);
    EnterCriticalSection(&CriticalSection);
    dword_1800519E0 = 1282;
    dword_1800519E4 = GetCurrentThreadId();
    StringCbCopyA(pszDest, v11, "\\server\\event.c");
    dword_1800519F8 = 1284;
    qword_1800519A0 = v10 & 0xFFFFFFFF7FFFFFFFuLL;
    dword_1800519FC = GetCurrentThreadId();
    StringCbCopyA(byte_1800519E8, v12, "\\server\\event.c");
    LeaveCriticalSection(&CriticalSection);
    v9 = SetGlobalEventMasks(v13, v10);
  }
  else
  {
    v9 = -19;
  }
  *a2 = v9;
  result = a5;
  *a5 = 16;
  return result;
}

```

## disassembly

```asm
0x180035280  mov     [rsp+arg_0], rbx
0x180035285  mov     [rsp+arg_8], rsi
0x18003528a  push    rdi
0x18003528b  sub     rsp, 20h
0x18003528f  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180035295  mov     rdi, rcx
0x180035298  mov     rbx, rcx
0x18003529b  shr     rdi, 4
0x18003529f  and     rax, rdi
0x1800352a2  mov     rsi, rdx
0x1800352a5  lea     r8, [rax+rax*4]
0x1800352a9  mov     rax, cs:gLockTable
0x1800352b0  lea     rcx, [rax+r8*8]; lpCriticalSection
0x1800352b4  call    cs:__imp_EnterCriticalSection
0x1800352ba  mov     eax, cs:gdwPointerToLockTableIndexBits
0x1800352c0  mov     ebx, [rbx+0D8h]
0x1800352c6  and     rax, rdi
0x1800352c9  lea     rcx, [rax+rax*4]
0x1800352cd  mov     rax, cs:gLockTable
0x1800352d4  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800352d8  call    cs:__imp_LeaveCriticalSection
0x1800352de  test    byte ptr cs:dword_180051900, 2
0x1800352e5  jz      short loc_1800352F6
0x1800352e7  test    bl, 1
0x1800352ea  jnz     short loc_1800352F6
0x1800352ec  mov     eax, 0FFFFFFEDh
0x1800352f1  jmp     loc_180035386
0x1800352f6  mov     ebx, [rsi+0Ch]
0x1800352f9  lea     rcx, CriticalSection; lpCriticalSection
0x180035300  mov     eax, [rsi+8]
0x180035303  shl     rbx, 20h
0x180035307  add     rbx, rax
0x18003530a  call    cs:__imp_EnterCriticalSection
0x180035310  mov     cs:dword_1800519E0, 502h
0x18003531a  call    cs:__imp_GetCurrentThreadId
0x180035320  lea     r8, aPrintscanTapiS+0Eh; pszSrc
0x180035327  mov     cs:dword_1800519E4, eax
0x18003532d  lea     rcx, pszDest; pszDest
0x180035334  call    StringCbCopyA
0x180035339  mov     r10, rbx
0x18003533c  mov     cs:dword_1800519F8, 504h
0x180035346  btr     r10d, 1Fh
0x18003534b  mov     cs:qword_1800519A0, r10
0x180035352  call    cs:__imp_GetCurrentThreadId
0x180035358  lea     r8, aPrintscanTapiS+0Eh; pszSrc
0x18003535f  mov     cs:dword_1800519FC, eax
0x180035365  lea     rcx, byte_1800519E8; pszDest
0x18003536c  call    StringCbCopyA
0x180035371  lea     rcx, CriticalSection; lpCriticalSection
0x180035378  call    cs:__imp_LeaveCriticalSection
0x18003537e  mov     rdx, rbx
0x180035381  call    SetGlobalEventMasks
0x180035386  mov     [rsi], eax
0x180035388  mov     rax, [rsp+28h+arg_20]
0x18003538d  mov     rbx, [rsp+28h+arg_0]
0x180035392  mov     rsi, [rsp+28h+arg_8]
0x180035397  mov     dword ptr [rax], 10h
0x18003539d  add     rsp, 20h
0x1800353a1  pop     rdi
0x1800353a2  retn
```
