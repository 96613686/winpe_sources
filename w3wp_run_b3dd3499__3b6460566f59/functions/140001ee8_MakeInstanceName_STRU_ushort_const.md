# MakeInstanceName(STRU *,ushort const *)

- ea: `0x140001ee8`
- end: `0x140001f99`
- name: `?MakeInstanceName@@YAJPEAVSTRU@@PEBG@Z`
- size: `177`
- prototype: `__int64 __fastcall(struct STRU *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callers

- `0x14000215c`

## callees

- `0x140001ee8`
- `0x1400038e0`

## import_xrefs

- `msvcrt!_ultow` at `0x140001f68`
- `msvcrt!_ultow` at `0x140001f68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001f55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001f55`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x140001f3b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x140001f7b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x140001f3b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x140001f7b`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x140001f24`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x140001f24`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x140001f2c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x140001f2c`

## pseudocode

```c
int __fastcall MakeInstanceName(struct STRU *a1, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rax
  int result; // eax
  DWORD CurrentProcessId; // eax
  wchar_t Buffer[4]; // [rsp+20h] [rbp-28h] BYREF
  __int16 v7; // [rsp+28h] [rbp-20h]
  char v8; // [rsp+2Ah] [rbp-1Eh]
  __int16 v9; // [rsp+34h] [rbp-14h]

  if ( a2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a2[v3] );
    if ( v3 <= 0x7F )
      return STRU::Copy(a1, a2);
    else
      return STRU::Copy(a1, a2, 0x7Fu);
  }
  else
  {
    result = STRU::Append(a1, L"HWC-");
    if ( result >= 0 )
    {
      *(_QWORD *)Buffer = 0;
      v7 = 0;
      v8 = 0;
      CurrentProcessId = GetCurrentProcessId();
      _ultow(CurrentProcessId, Buffer, 10);
      v9 = 0;
      return STRU::Append(a1, Buffer);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140001ee8  mov     [rsp+arg_10], rbx
0x140001eed  push    rdi
0x140001eee  sub     rsp, 40h
0x140001ef2  mov     rax, cs:__security_cookie
0x140001ef9  xor     rax, rsp
0x140001efc  mov     [rsp+48h+var_10], rax
0x140001f01  xor     edi, edi
0x140001f03  mov     rbx, rcx
0x140001f06  test    rdx, rdx
0x140001f09  jz      short loc_140001F34
0x140001f0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001f0f  inc     rax
0x140001f12  cmp     [rdx+rax*2], di
0x140001f16  jnz     short loc_140001F0F
0x140001f18  cmp     rax, 7Fh
0x140001f1c  jbe     short loc_140001F2C
0x140001f1e  mov     r8d, 7Fh
0x140001f24  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x140001f2a  jmp     short loc_140001F81
0x140001f2c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x140001f32  jmp     short loc_140001F81
0x140001f34  lea     rdx, aHwc; "HWC-"
0x140001f3b  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x140001f41  test    eax, eax
0x140001f43  js      short loc_140001F81
0x140001f45  xor     eax, eax
0x140001f47  mov     qword ptr [rsp+48h+Buffer], rax
0x140001f4c  mov     [rsp+48h+var_20], ax
0x140001f51  mov     [rsp+48h+var_1E], al
0x140001f55  call    cs:__imp_GetCurrentProcessId
0x140001f5b  mov     r8d, 0Ah; Radix
0x140001f61  lea     rdx, [rsp+48h+Buffer]; Buffer
0x140001f66  mov     ecx, eax; Value
0x140001f68  call    cs:__imp__ultow
0x140001f6e  lea     rdx, [rsp+48h+Buffer]
0x140001f73  mov     [rsp+48h+var_14], di
0x140001f78  mov     rcx, rbx
0x140001f7b  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x140001f81  mov     rcx, [rsp+48h+var_10]
0x140001f86  xor     rcx, rsp; StackCookie
0x140001f89  call    __security_check_cookie
0x140001f8e  mov     rbx, [rsp+48h+arg_10]
0x140001f93  add     rsp, 40h
0x140001f97  pop     rdi
0x140001f98  retn
```
