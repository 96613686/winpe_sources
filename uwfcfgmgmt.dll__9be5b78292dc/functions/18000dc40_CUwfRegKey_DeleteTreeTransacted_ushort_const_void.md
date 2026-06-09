# CUwfRegKey::DeleteTreeTransacted(ushort const *,void *)

- ea: `0x18000dc40`
- end: `0x18000dd77`
- name: `?DeleteTreeTransacted@CUwfRegKey@@QEAAJPEBGPEAX@Z`
- size: `311`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, void *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006c80`
- `0x180007360`
- `0x180007390`
- `0x18000d690`
- `0x18000dc40`

## callees

- `0x18000d5f0`
- `0x18000dc40`
- `0x18000df60`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x18000dd33`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyTransactedW` at `0x18000dd33`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000dcf0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000dcf0`

## pseudocode

```c
__int64 __fastcall CUwfRegKey::DeleteTreeTransacted(HKEY *this, const unsigned __int16 *a2, void *a3)
{
  LSTATUS v5; // eax
  signed int v6; // ebx
  HKEY v7; // rcx
  bool v8; // cc
  DWORD cchName; // [rsp+40h] [rbp-238h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-230h] BYREF
  WCHAR Name[256]; // [rsp+50h] [rbp-228h] BYREF

  phkResult = 0;
  if ( a2 )
  {
    v5 = CUwfRegKey::OpenTransacted(&phkResult, *this, a2, 0xF003Fu, a3);
    v6 = v5;
    if ( v5 )
    {
      if ( v5 > 0 )
LABEL_13:
        v6 = (unsigned __int16)v5 | 0x80070000;
    }
    else
    {
      v5 = CUwfRegKey::DeleteTreeTransacted((CUwfRegKey *)&phkResult, 0, a3);
LABEL_6:
      v6 = v5;
    }
  }
  else
  {
    v6 = 0;
    while ( 1 )
    {
      v7 = *this;
      cchName = 256;
      v5 = RegEnumKeyExW(v7, 0, Name, &cchName, 0, 0, 0, 0);
      if ( v5 == 259 )
        break;
      v8 = v5 <= 0;
      if ( !v5 )
      {
        v6 = CUwfRegKey::DeleteTreeTransacted((CUwfRegKey *)this, Name, a3);
        if ( v6 < 0 )
          break;
        v5 = RegDeleteKeyTransactedW(*this, Name, 0, 0, a3, 0);
        v8 = v5 <= 0;
        if ( !v5 )
          continue;
      }
      if ( v8 )
        goto LABEL_6;
      goto LABEL_13;
    }
  }
  CUwfRegKey::Close(&phkResult);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000dc40  push    rbx
0x18000dc42  push    rsi
0x18000dc43  push    rdi
0x18000dc44  sub     rsp, 260h
0x18000dc4b  mov     rax, cs:__security_cookie
0x18000dc52  xor     rax, rsp
0x18000dc55  mov     [rsp+278h+var_28], rax
0x18000dc5d  mov     [rsp+278h+phkResult], 0
0x18000dc66  mov     rdi, r8
0x18000dc69  mov     rsi, rcx
0x18000dc6c  test    rdx, rdx
0x18000dc6f  jz      short loc_18000DCB3
0x18000dc71  mov     [rsp+278h+lpReserved], r8; HANDLE
0x18000dc76  mov     r9d, 0F003Fh; samDesired
0x18000dc7c  mov     r8, rdx; lpSubKey
0x18000dc7f  mov     rdx, [rcx]; hKey
0x18000dc82  lea     rcx, [rsp+278h+phkResult]; phkResult
0x18000dc87  call    ?OpenTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGKPEAX@Z; CUwfRegKey::OpenTransacted(HKEY__ *,ushort const *,ulong,void *)
0x18000dc8c  mov     ebx, eax
0x18000dc8e  test    eax, eax
0x18000dc90  jz      short loc_18000DC9D
0x18000dc92  jle     loc_18000DD50
0x18000dc98  jmp     loc_18000DD47
0x18000dc9d  mov     r8, rdi; void *
0x18000dca0  lea     rcx, [rsp+278h+phkResult]; this
0x18000dca5  xor     edx, edx; unsigned __int16 *
0x18000dca7  call    ?DeleteTreeTransacted@CUwfRegKey@@QEAAJPEBGPEAX@Z; CUwfRegKey::DeleteTreeTransacted(ushort const *,void *)
0x18000dcac  mov     ebx, eax
0x18000dcae  jmp     loc_18000DD50
0x18000dcb3  xor     ebx, ebx
0x18000dcb5  mov     rcx, [rsi]; hKey
0x18000dcb8  lea     r9, [rsp+278h+cchName]; lpcchName
0x18000dcbd  mov     [rsp+278h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000dcc6  lea     r8, [rsp+278h+Name]; lpName
0x18000dccb  mov     [rsp+278h+lpcchClass], 0; lpcchClass
0x18000dcd4  xor     edx, edx; dwIndex
0x18000dcd6  mov     [rsp+278h+lpClass], 0; lpClass
0x18000dcdf  mov     [rsp+278h+lpReserved], 0; lpReserved
0x18000dce8  mov     [rsp+278h+cchName], 100h
0x18000dcf0  call    cs:__imp_RegEnumKeyExW
0x18000dcf6  cmp     eax, 103h
0x18000dcfb  jz      short loc_18000DD50
0x18000dcfd  test    eax, eax
0x18000dcff  jnz     short loc_18000DD41
0x18000dd01  mov     r8, rdi; void *
0x18000dd04  lea     rdx, [rsp+278h+Name]; unsigned __int16 *
0x18000dd09  mov     rcx, rsi; this
0x18000dd0c  call    ?DeleteTreeTransacted@CUwfRegKey@@QEAAJPEBGPEAX@Z; CUwfRegKey::DeleteTreeTransacted(ushort const *,void *)
0x18000dd11  mov     ebx, eax
0x18000dd13  test    eax, eax
0x18000dd15  js      short loc_18000DD50
0x18000dd17  mov     rcx, [rsi]; hKey
0x18000dd1a  lea     rdx, [rsp+278h+Name]; lpSubKey
0x18000dd1f  mov     [rsp+278h+lpClass], 0; pExtendedParameter
0x18000dd28  xor     r9d, r9d; Reserved
0x18000dd2b  xor     r8d, r8d; samDesired
0x18000dd2e  mov     [rsp+278h+lpReserved], rdi; hTransaction
0x18000dd33  call    cs:__imp_RegDeleteKeyTransactedW
0x18000dd39  test    eax, eax
0x18000dd3b  jz      loc_18000DCB5
0x18000dd41  jle     loc_18000DCAC
0x18000dd47  movzx   ebx, ax
0x18000dd4a  or      ebx, 80070000h
0x18000dd50  lea     rcx, [rsp+278h+phkResult]; this
0x18000dd55  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000dd5a  mov     eax, ebx
0x18000dd5c  mov     rcx, [rsp+278h+var_28]
0x18000dd64  xor     rcx, rsp; StackCookie
0x18000dd67  call    __security_check_cookie
0x18000dd6c  add     rsp, 260h
0x18000dd73  pop     rdi
0x18000dd74  pop     rsi
0x18000dd75  pop     rbx
0x18000dd76  retn
```
