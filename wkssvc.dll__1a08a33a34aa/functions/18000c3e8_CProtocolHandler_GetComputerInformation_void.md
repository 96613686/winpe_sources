# CProtocolHandler::GetComputerInformation(void)

- ea: `0x18000c3e8`
- end: `0x18000c488`
- name: `?GetComputerInformation@CProtocolHandler@@QEAAKXZ`
- size: `160`
- prototype: `unsigned int __fastcall(CProtocolHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ce14`

## callees

- `0x18000c1b4`
- `0x18000c3e8`
- `0x18000ea98`
- `0x180011c64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c42e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c42e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000c41e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000c41e`

## pseudocode

```c
__int64 __fastcall CProtocolHandler::GetComputerInformation(CProtocolHandler *this)
{
  DWORD v1; // eax
  WCHAR *v3; // rax
  WCHAR *v4; // rdi
  DWORD LastError; // ebx
  __int64 v6; // r8
  DWORD nSize; // [rsp+58h] [rbp+10h] BYREF

  v1 = 260;
  for ( nSize = 260; ; v1 = nSize )
  {
    v3 = (WCHAR *)MemoryAlloc(2LL * v1);
    v4 = v3;
    if ( !v3 )
      return 1450;
    if ( GetComputerNameExW(ComputerNameDnsFullyQualified, v3, &nSize) )
      break;
    LastError = GetLastError();
    if ( LastError != 234 )
      return LastError;
    MemoryFree(v4);
  }
  LastError = 0;
  v6 = -1;
  do
    ++v6;
  while ( v4[v6] );
  std::wstring::_Assign<unsigned short>((char *)this + 96, v4);
  MemoryFree(v4);
  return LastError;
}

```

## disassembly

```asm
0x18000c3e8  push    rbx
0x18000c3ea  push    rbp
0x18000c3eb  push    rsi
0x18000c3ec  push    rdi
0x18000c3ed  sub     rsp, 28h
0x18000c3f1  mov     eax, 104h
0x18000c3f6  mov     rsi, rcx
0x18000c3f9  mov     [rsp+48h+nSize], eax
0x18000c3fd  xor     ebp, ebp
0x18000c3ff  mov     ecx, eax
0x18000c401  add     rcx, rcx; unsigned __int64
0x18000c404  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x18000c409  mov     rdi, rax
0x18000c40c  test    rax, rax
0x18000c40f  jz      short loc_18000C477
0x18000c411  lea     r8, [rsp+48h+nSize]; nSize
0x18000c416  mov     rdx, rax; lpBuffer
0x18000c419  mov     ecx, 3; NameType
0x18000c41e  call    cs:__imp_GetComputerNameExW
0x18000c425  nop     dword ptr [rax+rax+00h]
0x18000c42a  test    eax, eax
0x18000c42c  jnz     short loc_18000C451
0x18000c42e  call    cs:__imp_GetLastError
0x18000c435  nop     dword ptr [rax+rax+00h]
0x18000c43a  mov     ebx, eax
0x18000c43c  cmp     eax, 0EAh
0x18000c441  jnz     short loc_18000C47C
0x18000c443  mov     rcx, rdi; void *
0x18000c446  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18000c44b  mov     eax, [rsp+48h+nSize]
0x18000c44f  jmp     short loc_18000C3FF
0x18000c451  mov     ebx, ebp
0x18000c453  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c457  inc     r8
0x18000c45a  cmp     [rdi+r8*2], bp
0x18000c45f  jnz     short loc_18000C457
0x18000c461  lea     rcx, [rsi+60h]
0x18000c465  mov     rdx, rdi
0x18000c468  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000c46d  mov     rcx, rdi; void *
0x18000c470  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18000c475  jmp     short loc_18000C47C
0x18000c477  mov     ebx, 5AAh
0x18000c47c  mov     eax, ebx
0x18000c47e  add     rsp, 28h
0x18000c482  pop     rdi
0x18000c483  pop     rsi
0x18000c484  pop     rbp
0x18000c485  pop     rbx
0x18000c486  retn
```
