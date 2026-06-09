# CRegBlob::~CRegBlob(void)

- ea: `0x18004c590`
- end: `0x18004c6c7`
- name: `??1CRegBlob@@QEAA@XZ`
- size: `311`
- prototype: `void __fastcall(CRegBlob *this, __int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18004b358`
- `0x18004b7a8`
- `0x18004c2c0`
- `0x1800aaa7c`

## callees

- `0x18004c590`
- `0x1800d1dd8`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c5f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c5f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c5da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c5da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18004c63f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18004c696`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18004c63f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18004c696`

## pseudocode

```c
void __fastcall CRegBlob::~CRegBlob(CRegBlob *this, __int64 a2, __int64 a3)
{
  unsigned int v4; // eax
  const BYTE **v5; // rsi
  BYTE *v6; // r8
  const BYTE *v7; // rcx
  BYTE *lpData; // [rsp+20h] [rbp-48h]

  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    LODWORD(lpData) = *((_DWORD *)this + 2);
    WPP_SF_qlll(this, a2, a3, this);
  }
  if ( *((_DWORD *)this + 3)
    && *((_DWORD *)this + 2)
    && (v7 = (const BYTE *)*((_QWORD *)this + 3), v5 = (const BYTE **)((char *)this + 24), v7)
    && *((_QWORD *)this + 4) )
  {
    if ( !*((_DWORD *)this + 11)
      || (v4 = RegSetValueExA(*(HKEY *)this, "SavedLegacySettings", 0, 3u, v7, *((_DWORD *)this + 4))) == 0 )
    {
      v4 = RegSetValueExA(*(HKEY *)this, *((LPCSTR *)this + 4), 0, 3u, *v5, *((_DWORD *)this + 4));
      if ( !v4 )
        *((_DWORD *)this + 3) = 0;
    }
  }
  else
  {
    v4 = 87;
    v5 = (const BYTE **)((char *)this + 24);
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 15, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, v4, lpData);
  if ( *(_QWORD *)this && *((_DWORD *)this + 10) )
    RegCloseKey(*(HKEY *)this);
  v6 = (BYTE *)*v5;
  *(_QWORD *)this = 0;
  if ( v6 )
  {
    HeapFree(g_hWxProcessHeap, 0, v6);
    *v5 = 0;
  }
}

```

## disassembly

```asm
0x18004c590  push    rbx
0x18004c592  push    rbp
0x18004c593  push    rsi
0x18004c594  push    rdi
0x18004c595  push    r14
0x18004c597  sub     rsp, 40h
0x18004c59b  mov     rbx, rcx
0x18004c59e  test    byte ptr cs:xmmword_180107A60, 20h
0x18004c5a5  jnz     loc_18004C655
0x18004c5ab  xor     ebp, ebp
0x18004c5ad  cmp     [rbx+0Ch], ebp
0x18004c5b0  jz      short loc_18004C5B7
0x18004c5b2  cmp     [rbx+8], ebp
0x18004c5b5  jnz     short loc_18004C608
0x18004c5b7  mov     eax, 57h ; 'W'
0x18004c5bc  lea     rsi, [rbx+18h]
0x18004c5c0  test    byte ptr cs:xmmword_180107A60, 20h
0x18004c5c7  jnz     loc_18004C6A9
0x18004c5cd  mov     rcx, [rbx]; hKey
0x18004c5d0  test    rcx, rcx
0x18004c5d3  jz      short loc_18004C5E0
0x18004c5d5  cmp     [rbx+28h], ebp
0x18004c5d8  jz      short loc_18004C5E0
0x18004c5da  call    cs:__imp_RegCloseKey
0x18004c5e0  mov     r8, [rsi]; lpMem
0x18004c5e3  mov     [rbx], rbp
0x18004c5e6  test    r8, r8
0x18004c5e9  jz      short loc_18004C5FD
0x18004c5eb  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18004c5f2  xor     edx, edx; dwFlags
0x18004c5f4  call    cs:__imp_HeapFree
0x18004c5fa  mov     [rsi], rbp
0x18004c5fd  add     rsp, 40h
0x18004c601  pop     r14
0x18004c603  pop     rdi
0x18004c604  pop     rsi
0x18004c605  pop     rbp
0x18004c606  pop     rbx
0x18004c607  retn
0x18004c608  mov     rcx, [rbx+18h]
0x18004c60c  lea     rsi, [rbx+18h]
0x18004c610  test    rcx, rcx
0x18004c613  jz      short loc_18004C5B7
0x18004c615  cmp     [rbx+20h], rbp
0x18004c619  jz      short loc_18004C5B7
0x18004c61b  cmp     [rbx+2Ch], ebp
0x18004c61e  jnz     short loc_18004C677
0x18004c620  mov     eax, [rbx+10h]
0x18004c623  mov     r9d, 3; dwType
0x18004c629  mov     rdx, [rbx+20h]; lpValueName
0x18004c62d  xor     r8d, r8d; Reserved
0x18004c630  mov     rcx, [rbx]; hKey
0x18004c633  mov     [rsp+68h+cbData], eax; cbData
0x18004c637  mov     rax, [rsi]
0x18004c63a  mov     [rsp+68h+lpData], rax; lpData
0x18004c63f  call    cs:__imp_RegSetValueExA
0x18004c645  test    eax, eax
0x18004c647  jnz     loc_18004C5C0
0x18004c64d  mov     [rbx+0Ch], ebp
0x18004c650  jmp     loc_18004C5C0
0x18004c655  mov     eax, [rcx+0Ch]
0x18004c658  mov     r9, rbx
0x18004c65b  mov     [rsp+68h+var_38], eax
0x18004c65f  mov     eax, [rcx+2Ch]
0x18004c662  mov     [rsp+68h+cbData], eax
0x18004c666  mov     eax, [rcx+8]
0x18004c669  mov     dword ptr [rsp+68h+lpData], eax
0x18004c66d  call    WPP_SF_qlll
0x18004c672  jmp     loc_18004C5AB
0x18004c677  mov     eax, [rbx+10h]
0x18004c67a  lea     rdx, aSavedlegacyset; "SavedLegacySettings"
0x18004c681  mov     [rsp+68h+cbData], eax; cbData
0x18004c685  mov     r9d, 3; dwType
0x18004c68b  mov     [rsp+68h+lpData], rcx; lpData
0x18004c690  xor     r8d, r8d; Reserved
0x18004c693  mov     rcx, [rbx]; hKey
0x18004c696  call    cs:__imp_RegSetValueExA
0x18004c69c  test    eax, eax
0x18004c69e  jnz     loc_18004C5C0
0x18004c6a4  jmp     loc_18004C620
0x18004c6a9  mov     edx, 0Fh
0x18004c6ae  lea     r8, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids
0x18004c6b5  mov     ecx, 405h
0x18004c6ba  mov     r9d, eax
0x18004c6bd  call    WPP_SF_d
0x18004c6c2  jmp     loc_18004C5CD
```
