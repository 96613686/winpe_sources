# GetHostName(_COMPUTER_NAME_FORMAT,ushort * *)

- ea: `0x1800074d0`
- end: `0x18000758f`
- name: `?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z`
- size: `191`
- prototype: `unsigned int __fastcall(COMPUTER_NAME_FORMAT NameType, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f810`
- `0x18000fa00`
- `0x18001b280`

## callees

- `0x18000214c`
- `0x1800074d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000755f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000755f`
- `KERNEL32!GetLastError` at `0x1800074fb`
- `KERNEL32!GetLastError` at `0x18000756b`
- `KERNEL32!GetLastError` at `0x1800074fb`
- `KERNEL32!GetLastError` at `0x18000756b`
- `KERNEL32!GetComputerNameExW` at `0x1800074ef`
- `KERNEL32!GetComputerNameExW` at `0x18000754c`
- `KERNEL32!GetComputerNameExW` at `0x1800074ef`
- `KERNEL32!GetComputerNameExW` at `0x18000754c`

## pseudocode

```c
unsigned int __fastcall GetHostName(COMPUTER_NAME_FORMAT NameType, unsigned __int16 **a2)
{
  unsigned int result; // eax
  unsigned __int64 v5; // rax
  WCHAR *v6; // rax
  unsigned __int16 *v7; // rbx
  DWORD nSize; // [rsp+40h] [rbp+18h] BYREF

  nSize = 0;
  GetComputerNameExW(NameType, 0, &nSize);
  result = GetLastError();
  if ( result == 234 )
  {
    v5 = 2LL * nSize;
    if ( !is_mul_ok(nSize, 2u) )
      v5 = -1;
    v6 = (WCHAR *)operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    if ( v6 )
    {
      if ( GetComputerNameExW(NameType, v6, &nSize) )
      {
        *a2 = v7;
        return 0;
      }
      else
      {
        operator delete(v7);
        return GetLastError();
      }
    }
    else
    {
      return 8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800074d0  mov     rax, rsp
0x1800074d3  mov     [rax+8], rbx
0x1800074d7  mov     [rax+10h], rsi
0x1800074db  push    rdi
0x1800074dc  sub     rsp, 20h
0x1800074e0  and     dword ptr [rax+18h], 0
0x1800074e4  lea     r8, [rax+18h]; nSize
0x1800074e8  mov     rsi, rdx
0x1800074eb  mov     edi, ecx
0x1800074ed  xor     edx, edx; lpBuffer
0x1800074ef  call    cs:__imp_GetComputerNameExW
0x1800074f6  nop     dword ptr [rax+rax+00h]
0x1800074fb  call    cs:__imp_GetLastError
0x180007502  nop     dword ptr [rax+rax+00h]
0x180007507  cmp     eax, 0EAh
0x18000750c  jnz     short loc_18000757E
0x18000750e  mov     r8d, [rsp+28h+nSize]
0x180007513  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000751a  mov     eax, 2
0x18000751f  mul     r8
0x180007522  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007529  cmovo   rax, rcx
0x18000752d  mov     rcx, rax; unsigned __int64
0x180007530  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007535  mov     rbx, rax
0x180007538  test    rax, rax
0x18000753b  jnz     short loc_180007542
0x18000753d  lea     eax, [rbx+8]
0x180007540  jmp     short loc_18000757E
0x180007542  lea     r8, [rsp+28h+nSize]; nSize
0x180007547  mov     rdx, rbx; lpBuffer
0x18000754a  mov     ecx, edi; NameType
0x18000754c  call    cs:__imp_GetComputerNameExW
0x180007553  nop     dword ptr [rax+rax+00h]
0x180007558  test    eax, eax
0x18000755a  jnz     short loc_180007579
0x18000755c  mov     rcx, rbx
0x18000755f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007566  nop     dword ptr [rax+rax+00h]
0x18000756b  call    cs:__imp_GetLastError
0x180007572  nop     dword ptr [rax+rax+00h]
0x180007577  jmp     short loc_18000757E
0x180007579  mov     [rsi], rbx
0x18000757c  xor     eax, eax
0x18000757e  mov     rbx, [rsp+28h+arg_0]
0x180007583  mov     rsi, [rsp+28h+arg_8]
0x180007588  add     rsp, 20h
0x18000758c  pop     rdi
0x18000758d  retn
```
