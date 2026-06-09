# GetSidString(void *,ushort * *)

- ea: `0x180004fe0`
- end: `0x1800051ea`
- name: `?GetSidString@@YAJPEAXPEAPEAG@Z`
- size: `522`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000246c`
- `0x18000429c`

## callees

- `0x180004fc0`
- `0x180004fe0`
- `0x1800051f0`
- `0x1800053f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800050b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005102`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800050b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005102`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180005163`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180005163`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005014`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005076`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005014`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005076`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005000`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005065`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000514f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005000`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005065`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000514f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005042`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800051b8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005042`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800051b8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005059`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005059`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180005092`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180005092`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800050db`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800050db`

## pseudocode

```c
__int64 __fastcall GetSidString(HANDLE TokenHandle, unsigned __int16 **a2)
{
  HANDLE ProcessHeap; // rax
  PSID *v5; // rdi
  void *v6; // rsi
  int Error; // ebx
  DWORD LengthSid; // ebx
  HANDLE v9; // rax
  void *v10; // rax
  void *v11; // rbp
  HANDLE v12; // rax
  HANDLE v13; // rax
  DWORD v15; // ebx
  HANDLE v16; // rax
  PSID *v17; // rax
  BOOL TokenInformation; // eax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+20h] BYREF

  TokenInformationLength = 200;
  ProcessHeap = GetProcessHeap();
  v5 = (PSID *)HeapAlloc(ProcessHeap, 8u, 0xC8u);
  if ( !v5 )
    return (unsigned int)-2147024882;
  v6 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      v15 = TokenInformationLength;
      v16 = GetProcessHeap();
      v17 = (PSID *)HeapReAlloc(v16, 8u, v5, v15);
      if ( v17 )
      {
        v5 = v17;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
          goto LABEL_10;
      }
      TokenInformation = GetTokenInformation(
                           TokenHandle,
                           TokenUser,
                           v5,
                           TokenInformationLength,
                           &TokenInformationLength);
      Error = ResultFromWin32Bool(TokenInformation);
    }
  }
  if ( Error >= 0 )
  {
    LengthSid = GetLengthSid(*v5);
    TokenInformationLength = LengthSid;
    v9 = GetProcessHeap();
    v10 = HeapAlloc(v9, 8u, LengthSid);
    v11 = v10;
    if ( v10 )
    {
      if ( CopySid(TokenInformationLength, v10, *v5) )
      {
        Error = 0;
LABEL_8:
        v6 = v11;
        goto LABEL_9;
      }
      Error = ResultFromKnownLastError();
      if ( Error >= 0 )
        goto LABEL_8;
      ResultFromHeapFree(v11);
    }
    else
    {
      Error = -2147024882;
    }
LABEL_9:
    if ( !v5 )
      goto LABEL_12;
  }
LABEL_10:
  v12 = GetProcessHeap();
  if ( !HeapFree(v12, 0, v5) )
    ResultFromKnownLastError();
LABEL_12:
  if ( Error < 0 )
    return (unsigned int)Error;
  StringSid = 0;
  if ( ConvertSidToStringSidW(v6, &StringSid) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_16;
  }
  *a2 = StringSid;
LABEL_16:
  if ( v6 )
  {
    v13 = GetProcessHeap();
    if ( !HeapFree(v13, 0, v6) )
      ResultFromKnownLastError();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180004fe0  mov     [rsp+arg_0], rbx
0x180004fe5  mov     [rsp+arg_8], rbp
0x180004fea  push    rsi
0x180004feb  push    rdi
0x180004fec  push    r14
0x180004fee  sub     rsp, 30h
0x180004ff2  mov     r14, rdx
0x180004ff5  mov     [rsp+48h+TokenInformationLength], 0C8h
0x180004ffd  mov     rbp, rcx
0x180005000  call    cs:__imp_GetProcessHeap
0x180005006  mov     edx, 8; dwFlags
0x18000500b  mov     r8d, 0C8h; dwBytes
0x180005011  mov     rcx, rax; hHeap
0x180005014  call    cs:__imp_HeapAlloc
0x18000501a  mov     rdi, rax
0x18000501d  test    rax, rax
0x180005020  jz      loc_180005125
0x180005026  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000502b  lea     rax, [rsp+48h+TokenInformationLength]
0x180005030  mov     r8, rdi; TokenInformation
0x180005033  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180005038  mov     edx, 1; TokenInformationClass
0x18000503d  mov     rcx, rbp; TokenHandle
0x180005040  xor     esi, esi
0x180005042  call    cs:__imp_GetTokenInformation
0x180005048  test    eax, eax
0x18000504a  jz      loc_180005139
0x180005050  xor     ebx, ebx
0x180005052  test    ebx, ebx
0x180005054  js      short loc_1800050AA
0x180005056  mov     rcx, [rdi]; pSid
0x180005059  call    cs:__imp_GetLengthSid
0x18000505f  mov     ebx, eax
0x180005061  mov     [rsp+48h+TokenInformationLength], ebx
0x180005065  call    cs:__imp_GetProcessHeap
0x18000506b  mov     r8d, ebx; dwBytes
0x18000506e  mov     edx, 8; dwFlags
0x180005073  mov     rcx, rax; hHeap
0x180005076  call    cs:__imp_HeapAlloc
0x18000507c  mov     rbp, rax
0x18000507f  test    rax, rax
0x180005082  jz      loc_1800051CC
0x180005088  mov     r8, [rdi]; pSourceSid
0x18000508b  mov     rdx, rax; pDestinationSid
0x18000508e  mov     ecx, [rsp+48h+TokenInformationLength]; nDestinationSidLength
0x180005092  call    cs:__imp_CopySid
0x180005098  test    eax, eax
0x18000509a  jz      loc_180005173
0x1800050a0  xor     ebx, ebx
0x1800050a2  mov     rsi, rbp
0x1800050a5  test    rdi, rdi
0x1800050a8  jz      short loc_1800050C6
0x1800050aa  call    cs:__imp_GetProcessHeap
0x1800050b0  mov     r8, rdi; lpMem
0x1800050b3  xor     edx, edx; dwFlags
0x1800050b5  mov     rcx, rax; hHeap
0x1800050b8  call    cs:__imp_HeapFree
0x1800050be  test    eax, eax
0x1800050c0  jz      loc_1800051D6
0x1800050c6  test    ebx, ebx
0x1800050c8  js      short loc_180005110
0x1800050ca  lea     rdx, [rsp+48h+StringSid]; StringSid
0x1800050cf  mov     [rsp+48h+StringSid], 0
0x1800050d8  mov     rcx, rsi; Sid
0x1800050db  call    cs:__imp_ConvertSidToStringSidW
0x1800050e1  test    eax, eax
0x1800050e3  jz      short loc_18000512C
0x1800050e5  xor     ebx, ebx
0x1800050e7  mov     rax, [rsp+48h+StringSid]
0x1800050ec  mov     [r14], rax
0x1800050ef  test    rsi, rsi
0x1800050f2  jz      short loc_180005110
0x1800050f4  call    cs:__imp_GetProcessHeap
0x1800050fa  mov     r8, rsi; lpMem
0x1800050fd  xor     edx, edx; dwFlags
0x1800050ff  mov     rcx, rax; hHeap
0x180005102  call    cs:__imp_HeapFree
0x180005108  test    eax, eax
0x18000510a  jz      loc_1800051E0
0x180005110  mov     rbp, [rsp+48h+arg_8]
0x180005115  mov     eax, ebx
0x180005117  mov     rbx, [rsp+48h+arg_0]
0x18000511c  add     rsp, 30h
0x180005120  pop     r14
0x180005122  pop     rdi
0x180005123  pop     rsi
0x180005124  retn
0x180005125  mov     ebx, 8007000Eh
0x18000512a  jmp     short loc_180005110
0x18000512c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005131  mov     ebx, eax
0x180005133  test    eax, eax
0x180005135  jns     short loc_1800050E7
0x180005137  jmp     short loc_1800050EF
0x180005139  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000513e  mov     ebx, eax
0x180005140  cmp     eax, 8007007Ah
0x180005145  jnz     loc_180005052
0x18000514b  mov     ebx, [rsp+48h+TokenInformationLength]
0x18000514f  call    cs:__imp_GetProcessHeap
0x180005155  mov     r9d, ebx; dwBytes
0x180005158  mov     r8, rdi; lpMem
0x18000515b  mov     rcx, rax; hHeap
0x18000515e  mov     edx, 8; dwFlags
0x180005163  call    cs:__imp_HeapReAlloc
0x180005169  test    rax, rax
0x18000516c  jz      short loc_18000518F
0x18000516e  mov     rdi, rax
0x180005171  jmp     short loc_18000519E
0x180005173  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005178  mov     ebx, eax
0x18000517a  test    eax, eax
0x18000517c  jns     loc_1800050A2
0x180005182  mov     rcx, rbp; lpMem
0x180005185  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18000518a  jmp     loc_1800050A5
0x18000518f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005194  mov     ebx, eax
0x180005196  test    eax, eax
0x180005198  js      loc_1800050AA
0x18000519e  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1800051a3  lea     rax, [rsp+48h+TokenInformationLength]
0x1800051a8  mov     r8, rdi; TokenInformation
0x1800051ab  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800051b0  mov     edx, 1; TokenInformationClass
0x1800051b5  mov     rcx, rbp; TokenHandle
0x1800051b8  call    cs:__imp_GetTokenInformation
0x1800051be  mov     ecx, eax; int
0x1800051c0  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800051c5  mov     ebx, eax
0x1800051c7  jmp     loc_180005052
0x1800051cc  mov     ebx, 8007000Eh
0x1800051d1  jmp     loc_1800050A5
0x1800051d6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800051db  jmp     loc_1800050C6
0x1800051e0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800051e5  jmp     loc_180005110
```
