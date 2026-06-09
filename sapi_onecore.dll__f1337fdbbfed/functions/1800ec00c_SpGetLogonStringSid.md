# SpGetLogonStringSid

- ea: `0x1800ec00c`
- end: `0x1800ec13c`
- name: `SpGetLogonStringSid`
- size: `304`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, SPPIPEINFO *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ebfac`

## callees

- `0x18000a590`
- `0x18000cdb0`
- `0x180045938`
- `0x1800ec00c`
- `0x1800fc2fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800ec093`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800ec093`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ec0be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ec0d5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ec11d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ec0be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ec0d5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ec11d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ec10b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ec10b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ec0e7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ec0e7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ec083`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ec083`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800ec0b1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800ec0b1`

## pseudocode

```c
__int64 __fastcall SpGetLogonStringSid(HANDLE TokenHandle, SPPIPEINFO *this)
{
  enum _TOKEN_INFORMATION_CLASS v4; // edx
  int TokenInformation; // eax
  PSID *v6; // rsi
  unsigned int v7; // ecx
  int Win32Error; // ebx
  __int64 v9; // rbp
  DWORD LengthSid; // r14d
  void *v11; // rax
  void *v12; // rdi
  LPWSTR StringSid; // [rsp+60h] [rbp+18h] BYREF
  void *Block; // [rsp+68h] [rbp+20h] BYREF

  StringSid = 0;
  SPPIPEINFO::~SPPIPEINFO(this);
  Block = 0;
  TokenInformation = SpGetTokenInformation(TokenHandle, v4, &Block);
  v6 = (PSID *)Block;
  v7 = 0;
  Win32Error = TokenInformation;
  if ( TokenInformation >= 0 )
  {
    while ( v7 < *(_DWORD *)Block )
    {
      v9 = 2LL * v7;
      if ( (*((_DWORD *)Block + 4 * v7 + 4) & 0xC0000000) == 0xC0000000 )
      {
        LengthSid = GetLengthSid(*((PSID *)Block + 2 * v7 + 1));
        v11 = calloc(1u, LengthSid);
        v12 = v11;
        if ( !v11 )
        {
          Win32Error = -2147024882;
          goto LABEL_10;
        }
        if ( !CopySid(LengthSid, v11, v6[v9 + 1]) )
          free(v12);
        goto LABEL_11;
      }
      ++v7;
    }
  }
  Win32Error = -2147418113;
LABEL_10:
  v12 = 0;
LABEL_11:
  if ( v6 )
    free(v6);
  if ( Win32Error >= 0 )
  {
    if ( ConvertSidToStringSidW(v12, &StringSid) )
    {
      CSpDynamicString::operator=(this, StringSid);
      if ( !*(_QWORD *)this )
        Win32Error = -2147024882;
      LocalFree(StringSid);
    }
    else
    {
      Win32Error = SpHrFromLastWin32Error();
    }
    free(v12);
  }
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x1800ec00c  mov     [rsp+arg_0], rbx
0x1800ec011  mov     [rsp+arg_8], rbp
0x1800ec016  push    rsi
0x1800ec017  push    rdi
0x1800ec018  push    r13
0x1800ec01a  push    r14
0x1800ec01c  push    r15
0x1800ec01e  sub     rsp, 20h
0x1800ec022  mov     rbx, rcx
0x1800ec025  mov     [rsp+48h+StringSid], 0
0x1800ec02e  mov     rcx, rdx; this
0x1800ec031  mov     r15, rdx
0x1800ec034  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800ec039  lea     r8, [rsp+48h+Block]; void **
0x1800ec03e  mov     [rsp+48h+Block], 0
0x1800ec047  mov     rcx, rbx; TokenHandle
0x1800ec04a  call    ?SpGetTokenInformation@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z; SpGetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void * *)
0x1800ec04f  mov     rsi, [rsp+48h+Block]
0x1800ec054  xor     ecx, ecx
0x1800ec056  mov     ebx, eax
0x1800ec058  mov     r13d, 8007000Eh
0x1800ec05e  test    eax, eax
0x1800ec060  js      short loc_1800EC0C6
0x1800ec062  mov     edx, 0C0000000h
0x1800ec067  cmp     ecx, [rsi]
0x1800ec069  jnb     short loc_1800EC0C6
0x1800ec06b  mov     ebp, ecx
0x1800ec06d  add     rbp, rbp
0x1800ec070  mov     eax, [rsi+rbp*8+10h]
0x1800ec074  and     eax, edx
0x1800ec076  cmp     eax, edx
0x1800ec078  jz      short loc_1800EC07E
0x1800ec07a  inc     ecx
0x1800ec07c  jmp     short loc_1800EC067
0x1800ec07e  mov     rcx, [rsi+rbp*8+8]; pSid
0x1800ec083  call    cs:__imp_GetLengthSid
0x1800ec089  mov     edx, eax; Size
0x1800ec08b  mov     ecx, 1; Count
0x1800ec090  mov     r14d, eax
0x1800ec093  call    cs:__imp_calloc
0x1800ec099  mov     rdi, rax
0x1800ec09c  test    rax, rax
0x1800ec09f  jnz     short loc_1800EC0A6
0x1800ec0a1  mov     ebx, r13d
0x1800ec0a4  jmp     short loc_1800EC0CB
0x1800ec0a6  mov     r8, [rsi+rbp*8+8]; pSourceSid
0x1800ec0ab  mov     rdx, rdi; pDestinationSid
0x1800ec0ae  mov     ecx, r14d; nDestinationSidLength
0x1800ec0b1  call    cs:__imp_CopySid
0x1800ec0b7  test    eax, eax
0x1800ec0b9  jnz     short loc_1800EC0CD
0x1800ec0bb  mov     rcx, rdi; Block
0x1800ec0be  call    cs:__imp_free
0x1800ec0c4  jmp     short loc_1800EC0CD
0x1800ec0c6  mov     ebx, 8000FFFFh
0x1800ec0cb  xor     edi, edi
0x1800ec0cd  test    rsi, rsi
0x1800ec0d0  jz      short loc_1800EC0DB
0x1800ec0d2  mov     rcx, rsi; Block
0x1800ec0d5  call    cs:__imp_free
0x1800ec0db  test    ebx, ebx
0x1800ec0dd  js      short loc_1800EC123
0x1800ec0df  lea     rdx, [rsp+48h+StringSid]; StringSid
0x1800ec0e4  mov     rcx, rdi; Sid
0x1800ec0e7  call    cs:__imp_ConvertSidToStringSidW
0x1800ec0ed  test    eax, eax
0x1800ec0ef  jz      short loc_1800EC113
0x1800ec0f1  mov     rdx, [rsp+48h+StringSid]
0x1800ec0f6  mov     rcx, r15
0x1800ec0f9  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x1800ec0fe  cmp     qword ptr [r15], 0
0x1800ec102  mov     rcx, [rsp+48h+StringSid]; hMem
0x1800ec107  cmovz   ebx, r13d
0x1800ec10b  call    cs:__imp_LocalFree
0x1800ec111  jmp     short loc_1800EC11A
0x1800ec113  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800ec118  mov     ebx, eax
0x1800ec11a  mov     rcx, rdi; Block
0x1800ec11d  call    cs:__imp_free
0x1800ec123  mov     rbp, [rsp+48h+arg_8]
0x1800ec128  mov     eax, ebx
0x1800ec12a  mov     rbx, [rsp+48h+arg_0]
0x1800ec12f  add     rsp, 20h
0x1800ec133  pop     r15
0x1800ec135  pop     r14
0x1800ec137  pop     r13
0x1800ec139  pop     rdi
0x1800ec13a  pop     rsi
0x1800ec13b  retn
```
