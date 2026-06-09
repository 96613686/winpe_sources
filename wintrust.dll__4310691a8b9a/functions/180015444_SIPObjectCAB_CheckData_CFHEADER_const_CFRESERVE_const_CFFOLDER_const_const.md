# SIPObjectCAB_::CheckData(CFHEADER const &,CFRESERVE const &,CFFOLDER const * const)

- ea: `0x180015444`
- end: `0x18001555d`
- name: `?CheckData@SIPObjectCAB_@@AEAAHAEBUCFHEADER@@AEBUCFRESERVE@@QEBUCFFOLDER@@@Z`
- size: `281`
- prototype: `_BOOL8 __fastcall(SIPObjectCAB_ *this, const struct CFHEADER *, const struct CFRESERVE *, const struct CFFOLDER *const)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800151a8`

## callees

- `0x180015444`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180015490`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800154c2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001553e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180015490`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800154c2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001553e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180015505`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180015505`

## pseudocode

```c
_BOOL8 __fastcall SIPObjectCAB_::CheckData(
        SIPObjectCAB_ *this,
        const struct CFHEADER *a2,
        const struct CFRESERVE *a3,
        const struct CFFOLDER *const a4)
{
  unsigned __int64 i; // rbx
  void *v9; // rcx
  DWORD v10; // ecx
  DWORD v12; // eax
  unsigned __int64 v13; // rbp
  unsigned __int64 j; // rdi
  __int64 Buffer; // [rsp+30h] [rbp-38h] BYREF
  DWORD NumberOfBytesRead; // [rsp+78h] [rbp+10h] BYREF

  NumberOfBytesRead = 0;
  Buffer = 0;
  for ( i = 0; ; ++i )
  {
    v9 = (void *)*((_QWORD *)this + 1);
    if ( i >= *((unsigned __int16 *)a2 + 13) )
      break;
    v12 = SetFilePointer(v9, 0, 0, 1u);
    if ( v12 == -1 || v12 != *((_DWORD *)a4 + 2 * i) )
      return 0;
    v13 = *((unsigned int *)a4 + 2 * i);
    for ( j = 0; j < *((unsigned __int16 *)a4 + 4 * i + 2); ++j )
    {
      if ( !ReadFile(*((HANDLE *)this + 1), &Buffer, 8u, &NumberOfBytesRead, 0) )
        return 0;
      if ( NumberOfBytesRead != 8 )
        return 0;
      v13 += WORD2(Buffer) + (unsigned int)*((unsigned __int8 *)a3 + 3);
      if ( v13 >= *((int *)a2 + 2)
        || SetFilePointer(*((HANDLE *)this + 1), WORD2(Buffer) + *((unsigned __int8 *)a3 + 3), 0, 1u) == -1 )
      {
        return 0;
      }
    }
  }
  v10 = SetFilePointer(v9, 0, 0, 1u);
  if ( v10 != -1 )
    return v10 == *((_DWORD *)a2 + 2);
  return 0;
}

```

## disassembly

```asm
0x180015444  mov     rax, rsp
0x180015447  mov     [rax+8], rbx
0x18001544b  mov     [rax+18h], rbp
0x18001544f  push    rsi
0x180015450  push    rdi
0x180015451  push    r12
0x180015453  push    r14
0x180015455  push    r15
0x180015457  sub     rsp, 40h
0x18001545b  mov     r15, r9
0x18001545e  mov     dword ptr [rax+10h], 0
0x180015465  mov     r12, r8
0x180015468  mov     qword ptr [rax-38h], 0
0x180015470  mov     rsi, rdx
0x180015473  mov     r14, rcx
0x180015476  xor     ebx, ebx
0x180015478  movzx   eax, word ptr [rsi+1Ah]
0x18001547c  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001547f  mov     rcx, [r14+8]; hFile
0x180015483  xor     edx, edx; lDistanceToMove
0x180015485  mov     r9d, 1; dwMoveMethod
0x18001548b  cmp     rbx, rax
0x18001548e  jb      short loc_1800154C2
0x180015490  call    cs:__imp_SetFilePointer
0x180015496  mov     ecx, eax
0x180015498  cmp     eax, 0FFFFFFFFh
0x18001549b  jz      loc_180015556
0x1800154a1  xor     eax, eax
0x1800154a3  cmp     ecx, [rsi+8]
0x1800154a6  setz    al
0x1800154a9  lea     r11, [rsp+68h+var_28]
0x1800154ae  mov     rbx, [r11+30h]
0x1800154b2  mov     rbp, [r11+40h]
0x1800154b6  mov     rsp, r11
0x1800154b9  pop     r15
0x1800154bb  pop     r14
0x1800154bd  pop     r12
0x1800154bf  pop     rdi
0x1800154c0  pop     rsi
0x1800154c1  retn
0x1800154c2  call    cs:__imp_SetFilePointer
0x1800154c8  cmp     eax, 0FFFFFFFFh
0x1800154cb  jz      loc_180015556
0x1800154d1  cmp     eax, [r15+rbx*8]
0x1800154d5  jnz     short loc_180015556
0x1800154d7  mov     ebp, [r15+rbx*8]
0x1800154db  xor     edi, edi
0x1800154dd  movzx   eax, word ptr [r15+rbx*8+4]
0x1800154e3  cmp     rdi, rax
0x1800154e6  jnb     short loc_18001554E
0x1800154e8  mov     rcx, [r14+8]; hFile
0x1800154ec  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800154f1  mov     r8d, 8; nNumberOfBytesToRead
0x1800154f7  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x180015500  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x180015505  call    cs:__imp_ReadFile
0x18001550b  test    eax, eax
0x18001550d  jz      short loc_180015556
0x18001550f  cmp     [rsp+68h+NumberOfBytesRead], 8
0x180015514  jnz     short loc_180015556
0x180015516  movzx   eax, [rsp+68h+var_34]
0x18001551b  movzx   edx, byte ptr [r12+3]
0x180015521  add     edx, eax; lDistanceToMove
0x180015523  mov     eax, edx
0x180015525  add     rbp, rax
0x180015528  movsxd  rax, dword ptr [rsi+8]
0x18001552c  cmp     rbp, rax
0x18001552f  jnb     short loc_180015556
0x180015531  mov     rcx, [r14+8]; hFile
0x180015535  mov     r9d, 1; dwMoveMethod
0x18001553b  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001553e  call    cs:__imp_SetFilePointer
0x180015544  cmp     eax, 0FFFFFFFFh
0x180015547  jz      short loc_180015556
0x180015549  inc     rdi
0x18001554c  jmp     short loc_1800154DD
0x18001554e  inc     rbx
0x180015551  jmp     loc_180015478
0x180015556  xor     eax, eax
0x180015558  jmp     loc_1800154A9
```
