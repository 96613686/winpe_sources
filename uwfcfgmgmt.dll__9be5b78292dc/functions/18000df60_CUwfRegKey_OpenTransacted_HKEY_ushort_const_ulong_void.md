# CUwfRegKey::OpenTransacted(HKEY__ *,ushort const *,ulong,void *)

- ea: `0x18000df60`
- end: `0x18000dfcc`
- name: `?OpenTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGKPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, HANDLE)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008170`
- `0x180008300`
- `0x18000866c`
- `0x180008900`
- `0x180008924`
- `0x180008b3c`
- `0x180008c30`
- `0x18000dc40`

## callees

- `0x18000d5f0`
- `0x18000df60`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18000dfa6`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18000dfa6`

## pseudocode

```c
__int64 __fastcall CUwfRegKey::OpenTransacted(
        PHKEY phkResult,
        HKEY hKey,
        LPCWSTR lpSubKey,
        REGSAM samDesired,
        HANDLE hTransaction)
{
  unsigned int v5; // ebx
  LSTATUS v10; // eax

  v5 = 0;
  if ( *phkResult )
    CUwfRegKey::Close(phkResult);
  v10 = RegOpenKeyTransactedW(hKey, lpSubKey, 0, samDesired, phkResult, hTransaction, 0);
  if ( v10 )
  {
    if ( v10 > 0 )
      return (unsigned __int16)v10 | 0x80070000;
    else
      return (unsigned int)v10;
  }
  return v5;
}

```

## disassembly

```asm
0x18000df60  push    rbx
0x18000df62  push    rbp
0x18000df63  push    rsi
0x18000df64  push    rdi
0x18000df65  push    r14
0x18000df67  sub     rsp, 40h
0x18000df6b  xor     ebx, ebx
0x18000df6d  mov     esi, r9d
0x18000df70  mov     rbp, r8
0x18000df73  mov     r14, rdx
0x18000df76  mov     rdi, rcx
0x18000df79  cmp     [rcx], rbx
0x18000df7c  jz      short loc_18000DF83
0x18000df7e  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000df83  mov     rax, [rsp+68h+arg_20]
0x18000df8b  mov     r9d, esi; samDesired
0x18000df8e  mov     [rsp+68h+pExtendedParemeter], rbx; pExtendedParemeter
0x18000df93  xor     r8d, r8d; ulOptions
0x18000df96  mov     [rsp+68h+hTransaction], rax; hTransaction
0x18000df9b  mov     rdx, rbp; lpSubKey
0x18000df9e  mov     rcx, r14; hKey
0x18000dfa1  mov     [rsp+68h+phkResult], rdi; phkResult
0x18000dfa6  call    cs:__imp_RegOpenKeyTransactedW
0x18000dfac  test    eax, eax
0x18000dfae  jz      short loc_18000DFBF
0x18000dfb0  jg      short loc_18000DFB6
0x18000dfb2  mov     ebx, eax
0x18000dfb4  jmp     short loc_18000DFBF
0x18000dfb6  movzx   ebx, ax
0x18000dfb9  or      ebx, 80070000h
0x18000dfbf  mov     eax, ebx
0x18000dfc1  add     rsp, 40h
0x18000dfc5  pop     r14
0x18000dfc7  pop     rdi
0x18000dfc8  pop     rsi
0x18000dfc9  pop     rbp
0x18000dfca  pop     rbx
0x18000dfcb  retn
```
