# CUwfRegKey::CopyTree(HKEY__ *,ushort const *,bool)

- ea: `0x18000d630`
- end: `0x18000d683`
- name: `?CopyTree@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `83`
- prototype: `__int64 __fastcall(HKEY *this, HKEY, const unsigned __int16 *, char)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006ae0`
- `0x18000d620`
- `0x18000e780`

## callees

- `0x18000d630`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18000d65e`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18000d65e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000d64f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000d64f`

## pseudocode

```c
__int64 __fastcall CUwfRegKey::CopyTree(HKEY *this, HKEY a2, const unsigned __int16 *a3, char a4)
{
  unsigned int v4; // ebx
  LSTATUS v8; // eax

  v4 = 0;
  if ( a4 )
    RegDeleteTreeW(a2, 0);
  v8 = RegCopyTreeW(*this, a3, a2);
  if ( v8 )
  {
    if ( v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
    else
      return (unsigned int)v8;
  }
  return v4;
}

```

## disassembly

```asm
0x18000d630  push    rbx
0x18000d632  push    rsi
0x18000d633  push    rdi
0x18000d634  push    r14
0x18000d636  sub     rsp, 28h
0x18000d63a  xor     ebx, ebx
0x18000d63c  mov     rsi, r8
0x18000d63f  mov     rdi, rdx
0x18000d642  mov     r14, rcx
0x18000d645  test    r9b, r9b
0x18000d648  jz      short loc_18000D655
0x18000d64a  xor     edx, edx; lpSubKey
0x18000d64c  mov     rcx, rdi; hKey
0x18000d64f  call    cs:__imp_RegDeleteTreeW
0x18000d655  mov     rcx, [r14]; hKeySrc
0x18000d658  mov     r8, rdi; hKeyDest
0x18000d65b  mov     rdx, rsi; lpSubKey
0x18000d65e  call    cs:__imp_RegCopyTreeW
0x18000d664  test    eax, eax
0x18000d666  jz      short loc_18000D677
0x18000d668  jg      short loc_18000D66E
0x18000d66a  mov     ebx, eax
0x18000d66c  jmp     short loc_18000D677
0x18000d66e  movzx   ebx, ax
0x18000d671  or      ebx, 80070000h
0x18000d677  mov     eax, ebx
0x18000d679  add     rsp, 28h
0x18000d67d  pop     r14
0x18000d67f  pop     rdi
0x18000d680  pop     rsi
0x18000d681  pop     rbx
0x18000d682  retn
```
