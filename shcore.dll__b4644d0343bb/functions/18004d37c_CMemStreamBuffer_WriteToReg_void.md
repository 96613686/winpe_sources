# CMemStreamBuffer::WriteToReg(void)

- ea: `0x18004d37c`
- end: `0x18004d41a`
- name: `?WriteToReg@CMemStreamBuffer@@AEAAHXZ`
- size: `158`
- prototype: `__int64 __fastcall(CMemStreamBuffer *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800203f0`
- `0x18002064c`
- `0x180020990`
- `0x180020e5c`
- `0x180020f00`

## callees

- `0x18004c200`
- `0x18004d37c`
- `0x180070350`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d3d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d3d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d38f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d38f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004d3c6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004d3c6`

## pseudocode

```c
_BOOL8 __fastcall CMemStreamBuffer::WriteToReg(CMemStreamBuffer *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  const WCHAR *v3; // rdx
  bool v4; // zf
  BOOL v5; // ebx
  LSTATUS v7; // eax
  _WORD *v8; // rcx
  LSTATUS v9; // esi

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_DWORD *)this + 5) )
  {
    v3 = (const WCHAR *)*((_QWORD *)this + 5);
    if ( !v3 || !*v3 )
      v3 = 0;
    v4 = RegSetValueExW(*((HKEY *)this + 4), v3, 0, 3u, *((const BYTE **)this + 1), *((_DWORD *)this + 5)) == 0;
  }
  else
  {
    v7 = SHDeleteValueW(*((HKEY *)this + 4), 0, *((LPCWSTR *)this + 5));
    v8 = (_WORD *)*((_QWORD *)this + 5);
    v9 = v7;
    if ( !v8 || !*v8 )
      SHDeleteEmptyKeyW(*((HKEY *)this + 4), 0);
    v4 = v9 == 0;
  }
  v5 = v4;
  LeaveCriticalSection(v1);
  return v5;
}

```

## disassembly

```asm
0x18004d37c  push    rbx
0x18004d37e  push    rbp
0x18004d37f  push    rsi
0x18004d380  push    rdi
0x18004d381  sub     rsp, 38h
0x18004d385  lea     rdi, [rcx+30h]
0x18004d389  mov     rbx, rcx
0x18004d38c  mov     rcx, rdi; lpCriticalSection
0x18004d38f  call    cs:__imp_EnterCriticalSection
0x18004d395  mov     eax, [rbx+14h]
0x18004d398  xor     ebp, ebp
0x18004d39a  test    eax, eax
0x18004d39c  jz      short loc_18004D3EC
0x18004d39e  mov     rdx, [rbx+28h]; lpValueName
0x18004d3a2  mov     rcx, [rbx+8]
0x18004d3a6  test    rdx, rdx
0x18004d3a9  jz      short loc_18004D3E7
0x18004d3ab  cmp     [rdx], bp
0x18004d3ae  jz      short loc_18004D3E7
0x18004d3b0  mov     [rsp+58h+cbData], eax; cbData
0x18004d3b4  mov     r9d, 3; dwType
0x18004d3ba  mov     [rsp+58h+lpData], rcx; lpData
0x18004d3bf  xor     r8d, r8d; Reserved
0x18004d3c2  mov     rcx, [rbx+20h]; hKey
0x18004d3c6  call    cs:__imp_RegSetValueExW
0x18004d3cc  test    eax, eax
0x18004d3ce  mov     ebx, ebp
0x18004d3d0  mov     rcx, rdi; lpCriticalSection
0x18004d3d3  setz    bl
0x18004d3d6  call    cs:__imp_LeaveCriticalSection
0x18004d3dc  mov     eax, ebx
0x18004d3de  add     rsp, 38h
0x18004d3e2  pop     rdi
0x18004d3e3  pop     rsi
0x18004d3e4  pop     rbp
0x18004d3e5  pop     rbx
0x18004d3e6  retn
0x18004d3e7  mov     rdx, rbp
0x18004d3ea  jmp     short loc_18004D3B0
0x18004d3ec  mov     r8, [rbx+28h]; pszValue
0x18004d3f0  xor     edx, edx; pszSubKey
0x18004d3f2  mov     rcx, [rbx+20h]; hkey
0x18004d3f6  call    SHDeleteValueW
0x18004d3fb  mov     rcx, [rbx+28h]
0x18004d3ff  mov     esi, eax
0x18004d401  test    rcx, rcx
0x18004d404  jz      short loc_18004D40B
0x18004d406  cmp     [rcx], bp
0x18004d409  jnz     short loc_18004D416
0x18004d40b  mov     rcx, [rbx+20h]; hkey
0x18004d40f  xor     edx, edx; pszSubKey
0x18004d411  call    SHDeleteEmptyKeyW
0x18004d416  test    esi, esi
0x18004d418  jmp     short loc_18004D3CE
```
