# QueryOriginalBucket

- ea: `0x180002f60`
- end: `0x1800030a8`
- name: `QueryOriginalBucket`
- size: `328`
- prototype: `signed int __fastcall(HANDLE hProcess, __int64, _WORD *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001400`
- `0x180001cc6`
- `0x180002f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fe1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180002fd7`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180002fd7`

## pseudocode

```c
signed int __fastcall QueryOriginalBucket(HANDLE hProcess, __int64 a2, _WORD *a3, unsigned int a4)
{
  __int64 v5; // rbp
  signed int result; // eax
  __int64 v9; // rcx
  __int64 v10; // rdx
  char *v11; // rax
  _WORD *v12; // rcx
  unsigned int v13; // eax
  SIZE_T NumberOfBytesRead[2]; // [rsp+30h] [rbp-258h] BYREF
  int Buffer; // [rsp+40h] [rbp-248h] BYREF
  char v16; // [rsp+44h] [rbp-244h] BYREF

  v5 = a4;
  memset_0(&Buffer, 0, 0x204u);
  NumberOfBytesRead[0] = 0;
  if ( ReadProcessMemory(hProcess, (char *)&dword_18000D450 + a2 - 0x180000000LL, &Buffer, 0x204u, NumberOfBytesRead) )
  {
    if ( NumberOfBytesRead[0] == 516 )
    {
      if ( Buffer == 1096172337 )
      {
        v9 = 2147483646;
        v10 = v5;
        if ( (unsigned int)(v5 - 1) > 0x7FFFFFFE )
        {
          v13 = -1073741811;
          if ( (_DWORD)v5 )
            *a3 = 0;
        }
        else
        {
          v11 = &v16;
          do
          {
            if ( !v9 )
              break;
            if ( !*(_WORD *)v11 )
              break;
            *a3 = *(_WORD *)v11;
            v11 += 2;
            ++a3;
            --v9;
            --v10;
          }
          while ( v10 );
          v12 = a3 - 1;
          if ( v10 )
            v12 = a3;
          v13 = v10 == 0 ? 0x80000005 : 0;
          *v12 = 0;
        }
        return v13 | 0x10000000;
      }
      else
      {
        return -2147024883;
      }
    }
    else
    {
      return -2147024597;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180002f60  mov     [rsp+arg_18], rbx
0x180002f65  push    rbp
0x180002f66  push    rsi
0x180002f67  push    rdi
0x180002f68  push    r14
0x180002f6a  push    r15
0x180002f6c  sub     rsp, 260h
0x180002f73  mov     rax, cs:__security_cookie
0x180002f7a  xor     rax, rsp
0x180002f7d  mov     [rsp+288h+var_38], rax
0x180002f85  mov     rsi, r8
0x180002f88  mov     ebp, r9d
0x180002f8b  mov     rdi, rdx
0x180002f8e  mov     rbx, rcx
0x180002f91  mov     r15d, 204h
0x180002f97  lea     rcx, [rsp+288h+Buffer]; void *
0x180002f9c  mov     r8d, r15d; Size
0x180002f9f  xor     edx, edx; Val
0x180002fa1  call    memset_0
0x180002fa6  lea     rax, cs:180000000h
0x180002fad  xor     r14d, r14d
0x180002fb0  sub     rdi, rax
0x180002fb3  mov     [rsp+288h+NumberOfBytesRead], r14
0x180002fb8  lea     rax, [rsp+288h+NumberOfBytesRead]
0x180002fbd  mov     r9d, r15d; nSize
0x180002fc0  lea     rdx, dword_18000D450
0x180002fc7  mov     [rsp+288h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180002fcc  add     rdx, rdi; lpBaseAddress
0x180002fcf  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x180002fd4  mov     rcx, rbx; hProcess
0x180002fd7  call    cs:__imp_ReadProcessMemory
0x180002fdd  test    eax, eax
0x180002fdf  jnz     short loc_180002FFC
0x180002fe1  call    cs:__imp_GetLastError
0x180002fe7  test    eax, eax
0x180002fe9  jle     loc_180003081
0x180002fef  movzx   eax, ax
0x180002ff2  or      eax, 80070000h
0x180002ff7  jmp     loc_180003081
0x180002ffc  cmp     [rsp+288h+NumberOfBytesRead], r15
0x180003001  jz      short loc_18000300A
0x180003003  mov     eax, 8007012Bh
0x180003008  jmp     short loc_180003081
0x18000300a  cmp     [rsp+288h+Buffer], 41564331h
0x180003012  jz      short loc_18000301B
0x180003014  mov     eax, 8007000Dh
0x180003019  jmp     short loc_180003081
0x18000301b  lea     eax, [rbp-1]
0x18000301e  mov     ecx, 7FFFFFFEh
0x180003023  mov     rdx, rbp
0x180003026  cmp     eax, ecx
0x180003028  ja      short loc_180003070
0x18000302a  lea     rax, [rsp+288h+var_244]
0x18000302f  test    rcx, rcx
0x180003032  jz      short loc_180003053
0x180003034  movzx   r8d, word ptr [rax]
0x180003038  test    r8w, r8w
0x18000303c  jz      short loc_180003053
0x18000303e  mov     [rsi], r8w
0x180003042  add     rax, 2
0x180003046  add     rsi, 2
0x18000304a  dec     rcx
0x18000304d  sub     rdx, 1
0x180003051  jnz     short loc_18000302F
0x180003053  test    rdx, rdx
0x180003056  lea     rcx, [rsi-2]
0x18000305a  cmovnz  rcx, rsi
0x18000305e  neg     rdx
0x180003061  sbb     eax, eax
0x180003063  not     eax
0x180003065  and     eax, 80000005h
0x18000306a  mov     [rcx], r14w
0x18000306e  jmp     short loc_18000307D
0x180003070  mov     eax, 0C000000Dh
0x180003075  test    ebp, ebp
0x180003077  jz      short loc_18000307D
0x180003079  mov     [rsi], r14w
0x18000307d  bts     eax, 1Ch
0x180003081  mov     rcx, [rsp+288h+var_38]
0x180003089  xor     rcx, rsp; StackCookie
0x18000308c  call    __security_check_cookie
0x180003091  mov     rbx, [rsp+288h+arg_18]
0x180003099  add     rsp, 260h
0x1800030a0  pop     r15
0x1800030a2  pop     r14
0x1800030a4  pop     rdi
0x1800030a5  pop     rsi
0x1800030a6  pop     rbp
0x1800030a7  retn
```
