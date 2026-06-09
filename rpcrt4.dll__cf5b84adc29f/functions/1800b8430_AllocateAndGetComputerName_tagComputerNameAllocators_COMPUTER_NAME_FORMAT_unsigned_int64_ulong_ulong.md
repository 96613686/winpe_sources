# AllocateAndGetComputerName(tagComputerNameAllocators,_COMPUTER_NAME_FORMAT,unsigned __int64,ulong,ulong *)

- ea: `0x1800b8430`
- end: `0x1800b84f3`
- name: `?AllocateAndGetComputerName@@YAPEAGW4tagComputerNameAllocators@@W4_COMPUTER_NAME_FORMAT@@_KKPEAK@Z`
- size: `195`
- prototype: `void *__fastcall(__int64, COMPUTER_NAME_FORMAT, __int64, unsigned int, _DWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800b83d0`
- `0x1800b8df8`
- `0x1800ca3a4`

## callees

- `0x180023020`
- `0x180023a40`
- `0x1800b8430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8467`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800b845b`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800b84ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800b845b`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800b84ab`

## pseudocode

```c
void *__fastcall AllocateAndGetComputerName(
        __int64 a1,
        COMPUTER_NAME_FORMAT a2,
        __int64 a3,
        unsigned int a4,
        _DWORD *a5)
{
  __int64 v6; // r14
  void *v8; // rbx
  char *v10; // rax
  char *v11; // rdi
  __int64 v12; // rcx
  DWORD nSize[18]; // [rsp+20h] [rbp-48h] BYREF

  v6 = a4;
  nSize[0] = 0;
  v8 = 0;
  GetComputerNameExW(a2, 0, nSize);
  if ( GetLastError() != 234 )
    return v8;
  if ( nSize[0] > 0x1388 )
    return 0;
  v10 = (char *)AllocWrapper(a3 + 2LL * nSize[0]);
  v8 = v10;
  if ( v10 )
  {
    v11 = &v10[v6];
    if ( GetComputerNameExW(a2, (LPWSTR)&v10[v6], nSize) )
    {
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)&v11[2 * v12] );
      *a5 = v12 + 1;
      return v8;
    }
    FreeWrapper(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x1800b8430  push    rbx
0x1800b8432  push    rbp
0x1800b8433  push    rsi
0x1800b8434  push    rdi
0x1800b8435  push    r14
0x1800b8437  push    r15
0x1800b8439  sub     rsp, 38h
0x1800b843d  mov     ebp, edx
0x1800b843f  mov     r14d, r9d
0x1800b8442  mov     rsi, r8
0x1800b8445  mov     edi, ecx
0x1800b8447  xor     r15d, r15d
0x1800b844a  lea     r8, [rsp+68h+nSize]; nSize
0x1800b844f  mov     ecx, ebp; NameType
0x1800b8451  mov     [rsp+68h+nSize], r15d
0x1800b8456  xor     edx, edx; lpBuffer
0x1800b8458  mov     ebx, r15d
0x1800b845b  call    cs:__imp_GetComputerNameExW
0x1800b8462  nop     dword ptr [rax+rax+00h]
0x1800b8467  call    cs:__imp_GetLastError
0x1800b846e  nop     dword ptr [rax+rax+00h]
0x1800b8473  cmp     eax, 0EAh
0x1800b8478  jnz     short loc_1800B84C6
0x1800b847a  mov     eax, [rsp+68h+nSize]
0x1800b847e  cmp     eax, 1388h
0x1800b8483  jbe     short loc_1800B8489
0x1800b8485  xor     eax, eax
0x1800b8487  jmp     short loc_1800B84C9
0x1800b8489  mov     rcx, rax
0x1800b848c  lea     rcx, [rsi+rax*2]; dwBytes
0x1800b8490  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800b8495  mov     rbx, rax
0x1800b8498  test    rax, rax
0x1800b849b  jz      short loc_1800B84C3
0x1800b849d  lea     rdi, [rax+r14]
0x1800b84a1  mov     ecx, ebp; NameType
0x1800b84a3  mov     rdx, rdi; lpBuffer
0x1800b84a6  lea     r8, [rsp+68h+nSize]; nSize
0x1800b84ab  call    cs:__imp_GetComputerNameExW
0x1800b84b2  nop     dword ptr [rax+rax+00h]
0x1800b84b7  test    eax, eax
0x1800b84b9  jnz     short loc_1800B84D7
0x1800b84bb  mov     rcx, rbx; lpMem
0x1800b84be  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800b84c3  mov     rbx, r15
0x1800b84c6  mov     rax, rbx
0x1800b84c9  add     rsp, 38h
0x1800b84cd  pop     r15
0x1800b84cf  pop     r14
0x1800b84d1  pop     rdi
0x1800b84d2  pop     rsi
0x1800b84d3  pop     rbp
0x1800b84d4  pop     rbx
0x1800b84d5  retn
0x1800b84d7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800b84db  inc     rcx
0x1800b84de  cmp     [rdi+rcx*2], r15w
0x1800b84e3  jnz     short loc_1800B84DB
0x1800b84e5  mov     rax, [rsp+68h+arg_20]
0x1800b84ed  inc     ecx
0x1800b84ef  mov     [rax], ecx
0x1800b84f1  jmp     short loc_1800B84C6
```
