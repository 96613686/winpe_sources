# CUwfRegKey::CreateTransacted(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *,void *)

- ea: `0x18000db50`
- end: `0x18000dbec`
- name: `?CreateTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAKPEAX@Z`
- size: `156`
- prototype: `__int64 __fastcall(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, LPWSTR lpClass, DWORD, REGSAM, LPSECURITY_ATTRIBUTES, LPDWORD, HANDLE)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006b20`
- `0x18000d690`

## callees

- `0x18000d5f0`
- `0x18000db50`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18000dbc6`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18000dbc6`

## pseudocode

```c
__int64 __fastcall CUwfRegKey::CreateTransacted(
        PHKEY phkResult,
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPWSTR lpClass,
        DWORD dwOptions,
        REGSAM samDesired,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        LPDWORD lpdwDisposition,
        HANDLE hTransaction)
{
  unsigned int v9; // ebx
  LSTATUS KeyTransactedW; // eax

  v9 = 0;
  if ( *phkResult )
    CUwfRegKey::Close(phkResult);
  KeyTransactedW = RegCreateKeyTransactedW(
                     hKey,
                     lpSubKey,
                     0,
                     lpClass,
                     dwOptions,
                     samDesired,
                     lpSecurityAttributes,
                     phkResult,
                     lpdwDisposition,
                     hTransaction,
                     0);
  if ( KeyTransactedW )
  {
    if ( KeyTransactedW > 0 )
      return (unsigned __int16)KeyTransactedW | 0x80070000;
    else
      return (unsigned int)KeyTransactedW;
  }
  return v9;
}

```

## disassembly

```asm
0x18000db50  push    rbx
0x18000db52  push    rbp
0x18000db53  push    rsi
0x18000db54  push    rdi
0x18000db55  push    r14
0x18000db57  sub     rsp, 60h
0x18000db5b  xor     ebx, ebx
0x18000db5d  mov     rsi, r9
0x18000db60  mov     rbp, r8
0x18000db63  mov     r14, rdx
0x18000db66  mov     rdi, rcx
0x18000db69  cmp     [rcx], rbx
0x18000db6c  jz      short loc_18000DB73
0x18000db6e  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000db73  mov     rax, [rsp+88h+arg_40]
0x18000db7b  mov     r9, rsi; lpClass
0x18000db7e  mov     [rsp+88h+pExtendedParemeter], rbx; pExtendedParemeter
0x18000db83  xor     r8d, r8d; Reserved
0x18000db86  mov     [rsp+88h+hTransaction], rax; hTransaction
0x18000db8b  mov     rdx, rbp; lpSubKey
0x18000db8e  mov     rax, [rsp+88h+arg_38]
0x18000db96  mov     rcx, r14; hKey
0x18000db99  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x18000db9e  mov     rax, [rsp+88h+arg_30]
0x18000dba6  mov     [rsp+88h+phkResult], rdi; phkResult
0x18000dbab  mov     [rsp+88h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18000dbb0  mov     eax, [rsp+88h+arg_28]
0x18000dbb7  mov     [rsp+88h+samDesired], eax; samDesired
0x18000dbbb  mov     eax, [rsp+88h+arg_20]
0x18000dbc2  mov     [rsp+88h+dwOptions], eax; dwOptions
0x18000dbc6  call    cs:__imp_RegCreateKeyTransactedW
0x18000dbcc  test    eax, eax
0x18000dbce  jz      short loc_18000DBDF
0x18000dbd0  jg      short loc_18000DBD6
0x18000dbd2  mov     ebx, eax
0x18000dbd4  jmp     short loc_18000DBDF
0x18000dbd6  movzx   ebx, ax
0x18000dbd9  or      ebx, 80070000h
0x18000dbdf  mov     eax, ebx
0x18000dbe1  add     rsp, 60h
0x18000dbe5  pop     r14
0x18000dbe7  pop     rdi
0x18000dbe8  pop     rsi
0x18000dbe9  pop     rbp
0x18000dbea  pop     rbx
0x18000dbeb  retn
```
