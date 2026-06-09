# CWdsTptNamespaceStore::RemoveNamespace(ushort const *)

- ea: `0x18001b0ac`
- end: `0x18001b112`
- name: `?RemoveNamespace@CWdsTptNamespaceStore@@QEAAKPEBG@Z`
- size: `102`
- prototype: `unsigned int(CWdsTptNamespaceStore *__hidden this, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800031e4`
- `0x180005f18`
- `0x1800067f0`
- `0x180007a24`
- `0x18001acc8`

## callees

- `0x18001b0ac`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001b0fa`
- `KERNEL32!LeaveCriticalSection` at `0x18001b0fa`
- `KERNEL32!EnterCriticalSection` at `0x18001b0c5`
- `KERNEL32!EnterCriticalSection` at `0x18001b0c5`
- `ADVAPI32!RegDeleteKeyExW` at `0x18001b0e7`
- `ADVAPI32!RegDeleteKeyExW` at `0x18001b0e7`

## pseudocode

```c
__int64 __fastcall CWdsTptNamespaceStore::RemoveNamespace(CWdsTptNamespaceStore *this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( a2 && *a2 )
    v4 = RegDeleteKeyExW(*((HKEY *)this + 6), a2, 0x100u, 0);
  else
    v4 = 87;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return v4;
}

```

## disassembly

```asm
0x18001b0ac  mov     [rsp+arg_0], rbx
0x18001b0b1  mov     [rsp+arg_8], rsi
0x18001b0b6  push    rdi
0x18001b0b7  sub     rsp, 20h
0x18001b0bb  mov     rsi, rcx
0x18001b0be  mov     rbx, rdx
0x18001b0c1  add     rcx, 8; lpCriticalSection
0x18001b0c5  call    cs:__imp_EnterCriticalSection
0x18001b0cb  xor     eax, eax
0x18001b0cd  test    rbx, rbx
0x18001b0d0  jz      short loc_18001B0F1
0x18001b0d2  cmp     [rbx], ax
0x18001b0d5  jz      short loc_18001B0F1
0x18001b0d7  mov     rcx, [rsi+30h]; hKey
0x18001b0db  xor     r9d, r9d; Reserved
0x18001b0de  mov     r8d, 100h; samDesired
0x18001b0e4  mov     rdx, rbx; lpSubKey
0x18001b0e7  call    cs:__imp_RegDeleteKeyExW
0x18001b0ed  mov     ebx, eax
0x18001b0ef  jmp     short loc_18001B0F6
0x18001b0f1  mov     ebx, 57h ; 'W'
0x18001b0f6  lea     rcx, [rsi+8]; lpCriticalSection
0x18001b0fa  call    cs:__imp_LeaveCriticalSection
0x18001b100  mov     rsi, [rsp+28h+arg_8]
0x18001b105  mov     eax, ebx
0x18001b107  mov     rbx, [rsp+28h+arg_0]
0x18001b10c  add     rsp, 20h
0x18001b110  pop     rdi
0x18001b111  retn
```
