# CProtocolHandler::GetComputerInformation(void)

- ea: `0x18000b97c`
- end: `0x18000ba0f`
- name: `?GetComputerInformation@CProtocolHandler@@QEAAKXZ`
- size: `147`
- prototype: `__int64 __fastcall(CProtocolHandler *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c308`

## callees

- `0x18000b76c`
- `0x18000b97c`
- `0x18000dd68`
- `0x180010d28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000b9b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000b9b2`

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
0x18000b97c  push    rbx
0x18000b97e  push    rbp
0x18000b97f  push    rsi
0x18000b980  push    rdi
0x18000b981  sub     rsp, 28h
0x18000b985  mov     eax, 104h
0x18000b98a  mov     rsi, rcx
0x18000b98d  mov     [rsp+48h+nSize], eax
0x18000b991  xor     ebp, ebp
0x18000b993  mov     ecx, eax
0x18000b995  add     rcx, rcx; unsigned __int64
0x18000b998  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x18000b99d  mov     rdi, rax
0x18000b9a0  test    rax, rax
0x18000b9a3  jz      short loc_18000B9FF
0x18000b9a5  lea     r8, [rsp+48h+nSize]; nSize
0x18000b9aa  mov     rdx, rax; lpBuffer
0x18000b9ad  mov     ecx, 3; NameType
0x18000b9b2  call    cs:__imp_GetComputerNameExW
0x18000b9b8  test    eax, eax
0x18000b9ba  jnz     short loc_18000B9D9
0x18000b9bc  call    cs:__imp_GetLastError
0x18000b9c2  mov     ebx, eax
0x18000b9c4  cmp     eax, 0EAh
0x18000b9c9  jnz     short loc_18000BA04
0x18000b9cb  mov     rcx, rdi; void *
0x18000b9ce  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18000b9d3  mov     eax, [rsp+48h+nSize]
0x18000b9d7  jmp     short loc_18000B993
0x18000b9d9  mov     ebx, ebp
0x18000b9db  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000b9df  inc     r8
0x18000b9e2  cmp     [rdi+r8*2], bp
0x18000b9e7  jnz     short loc_18000B9DF
0x18000b9e9  lea     rcx, [rsi+60h]
0x18000b9ed  mov     rdx, rdi
0x18000b9f0  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000b9f5  mov     rcx, rdi; void *
0x18000b9f8  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18000b9fd  jmp     short loc_18000BA04
0x18000b9ff  mov     ebx, 5AAh
0x18000ba04  mov     eax, ebx
0x18000ba06  add     rsp, 28h
0x18000ba0a  pop     rdi
0x18000ba0b  pop     rsi
0x18000ba0c  pop     rbp
0x18000ba0d  pop     rbx
0x18000ba0e  retn
```
