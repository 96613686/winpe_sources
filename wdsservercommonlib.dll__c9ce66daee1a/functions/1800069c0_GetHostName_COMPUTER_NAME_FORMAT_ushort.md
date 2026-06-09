# GetHostName(_COMPUTER_NAME_FORMAT,ushort * *)

- ea: `0x1800069c0`
- end: `0x180006a78`
- name: `?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z`
- size: `184`
- prototype: `unsigned int __fastcall(COMPUTER_NAME_FORMAT NameType, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ec80`
- `0x18000ee60`
- `0x18001a440`

## callees

- `0x18000179c`
- `0x1800069c0`
- `0x18002e468`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800069eb`
- `KERNEL32!GetLastError` at `0x180006a54`
- `KERNEL32!GetLastError` at `0x1800069eb`
- `KERNEL32!GetLastError` at `0x180006a54`
- `KERNEL32!GetComputerNameExW` at `0x1800069df`
- `KERNEL32!GetComputerNameExW` at `0x180006a3c`
- `KERNEL32!GetComputerNameExW` at `0x1800069df`
- `KERNEL32!GetComputerNameExW` at `0x180006a3c`

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
0x1800069c0  mov     rax, rsp
0x1800069c3  mov     [rax+8], rbx
0x1800069c7  mov     [rax+10h], rsi
0x1800069cb  push    rdi
0x1800069cc  sub     rsp, 20h
0x1800069d0  and     dword ptr [rax+18h], 0
0x1800069d4  lea     r8, [rax+18h]; nSize
0x1800069d8  mov     rsi, rdx
0x1800069db  mov     edi, ecx
0x1800069dd  xor     edx, edx; lpBuffer
0x1800069df  call    cs:__imp_GetComputerNameExW
0x1800069e6  nop     dword ptr [rax+rax+00h]
0x1800069eb  call    cs:__imp_GetLastError
0x1800069f2  nop     dword ptr [rax+rax+00h]
0x1800069f7  cmp     eax, 0EAh
0x1800069fc  jnz     short loc_180006A67
0x1800069fe  mov     r8d, [rsp+28h+nSize]
0x180006a03  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006a0a  mov     eax, 2
0x180006a0f  mul     r8
0x180006a12  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006a19  cmovo   rax, rcx
0x180006a1d  mov     rcx, rax; unsigned __int64
0x180006a20  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006a25  mov     rbx, rax
0x180006a28  test    rax, rax
0x180006a2b  jnz     short loc_180006A32
0x180006a2d  lea     eax, [rbx+8]
0x180006a30  jmp     short loc_180006A67
0x180006a32  lea     r8, [rsp+28h+nSize]; nSize
0x180006a37  mov     rdx, rbx; lpBuffer
0x180006a3a  mov     ecx, edi; NameType
0x180006a3c  call    cs:__imp_GetComputerNameExW
0x180006a43  nop     dword ptr [rax+rax+00h]
0x180006a48  test    eax, eax
0x180006a4a  jnz     short loc_180006A62
0x180006a4c  mov     rcx, rbx; lpMem
0x180006a4f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006a54  call    cs:__imp_GetLastError
0x180006a5b  nop     dword ptr [rax+rax+00h]
0x180006a60  jmp     short loc_180006A67
0x180006a62  mov     [rsi], rbx
0x180006a65  xor     eax, eax
0x180006a67  mov     rbx, [rsp+28h+arg_0]
0x180006a6c  mov     rsi, [rsp+28h+arg_8]
0x180006a71  add     rsp, 20h
0x180006a75  pop     rdi
0x180006a76  retn
```
