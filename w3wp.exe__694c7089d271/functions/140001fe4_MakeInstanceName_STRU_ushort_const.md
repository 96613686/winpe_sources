# MakeInstanceName(STRU *,ushort const *)

- ea: `0x140001fe4`
- end: `0x1400020ba`
- name: `?MakeInstanceName@@YAJPEAVSTRU@@PEBG@Z`
- size: `214`
- prototype: `__int64 __fastcall(struct STRU *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1400022c4`

## callees

- `0x140001fe4`
- `0x140003cc0`

## import_xrefs

- `msvcrt!_ultow` at `0x14000207c`
- `msvcrt!_ultow` at `0x14000207c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002063`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002063`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x140002043`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x140002095`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x140002043`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x140002095`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x140002020`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x140002020`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x14000202e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x14000202e`

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
0x140001fe4  mov     [rsp+arg_10], rbx
0x140001fe9  push    rdi
0x140001fea  sub     rsp, 40h
0x140001fee  mov     rax, cs:__security_cookie
0x140001ff5  xor     rax, rsp
0x140001ff8  mov     [rsp+48h+var_10], rax
0x140001ffd  xor     edi, edi
0x140001fff  mov     rbx, rcx
0x140002002  test    rdx, rdx
0x140002005  jz      short loc_14000203C
0x140002007  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000200b  inc     rax
0x14000200e  cmp     [rdx+rax*2], di
0x140002012  jnz     short loc_14000200B
0x140002014  cmp     rax, 7Fh
0x140002018  jbe     short loc_14000202E
0x14000201a  mov     r8d, 7Fh
0x140002020  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x140002027  nop     dword ptr [rax+rax+00h]
0x14000202c  jmp     short loc_1400020A1
0x14000202e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x140002035  nop     dword ptr [rax+rax+00h]
0x14000203a  jmp     short loc_1400020A1
0x14000203c  lea     rdx, aHwc; "HWC-"
0x140002043  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x14000204a  nop     dword ptr [rax+rax+00h]
0x14000204f  test    eax, eax
0x140002051  js      short loc_1400020A1
0x140002053  xor     eax, eax
0x140002055  mov     qword ptr [rsp+48h+Buffer], rax
0x14000205a  mov     [rsp+48h+var_20], ax
0x14000205f  mov     [rsp+48h+var_1E], al
0x140002063  call    cs:__imp_GetCurrentProcessId
0x14000206a  nop     dword ptr [rax+rax+00h]
0x14000206f  mov     r8d, 0Ah; Radix
0x140002075  lea     rdx, [rsp+48h+Buffer]; Buffer
0x14000207a  mov     ecx, eax; Value
0x14000207c  call    cs:__imp__ultow
0x140002083  nop     dword ptr [rax+rax+00h]
0x140002088  lea     rdx, [rsp+48h+Buffer]
0x14000208d  mov     [rsp+48h+var_14], di
0x140002092  mov     rcx, rbx
0x140002095  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x14000209c  nop     dword ptr [rax+rax+00h]
0x1400020a1  mov     rcx, [rsp+48h+var_10]
0x1400020a6  xor     rcx, rsp; StackCookie
0x1400020a9  call    __security_check_cookie
0x1400020ae  mov     rbx, [rsp+48h+arg_10]
0x1400020b3  add     rsp, 40h
0x1400020b7  pop     rdi
0x1400020b8  retn
```
