# DavAsyncFsCtl

- ea: `0x180023cd4`
- end: `0x180023ff8`
- name: `DavAsyncFsCtl`
- size: `804`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d9e4`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b89c`
- `0x1800134d8`
- `0x180023cd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f80`
- `WINHTTP!WinHttpReadData` at `0x180023ee3`
- `WINHTTP!WinHttpReadData` at `0x180023ee3`
- `WINHTTP!WinHttpQueryHeaders` at `0x180023e0a`
- `WINHTTP!WinHttpQueryHeaders` at `0x180023e0a`

## pseudocode

```c
__int64 __fastcall DavAsyncFsCtl(__int64 a1, char a2)
{
  void *v2; // r12
  unsigned int v4; // r15d
  unsigned int v5; // ebx
  unsigned int v6; // r14d
  __int64 v7; // rsi
  DWORD v8; // r14d
  __int64 v9; // rdi
  DWORD LastError; // eax
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  DWORD v14; // r14d
  void *v15; // r13
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r9
  DWORD v19; // eax
  DWORD dwBufferLength; // [rsp+70h] [rbp+8h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+78h] [rbp+10h] BYREF

  LOBYTE(dwNumberOfBytesRead) = a2;
  v2 = *(void **)(a1 + 560);
  v4 = 0;
  dwNumberOfBytesRead = 0;
  v5 = DavQueryAndParseResponseEx(v2, &dwNumberOfBytesRead);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        WPP_d103a73541d83417b437566f644ce9ea_Traceguids,
        v5,
        dwNumberOfBytesRead);
    return v5;
  }
  if ( *(_DWORD *)(a1 + 664) != 67108984 )
  {
    if ( *(_DWORD *)(a1 + 664) == 67108991 )
    {
      *(_DWORD *)(a1 + 2312) = 0;
      return v5;
    }
    return 87;
  }
  v6 = *(_DWORD *)(a1 + 684);
  v7 = *(_QWORD *)(a1 + 688);
  dwNumberOfBytesRead = 0;
  *(_QWORD *)(v7 + 68) = 0;
  *(_QWORD *)(v7 + 80) = 0;
  *(_DWORD *)(v7 + 64) = 0;
  if ( v6 < 0x58 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_d103a73541d83417b437566f644ce9ea_Traceguids);
    return 87;
  }
  v8 = v6 - 88;
  if ( v8 < 2 )
    return 122;
  dwBufferLength = v8;
  v9 = v7 + 88;
  if ( !WinHttpQueryHeaders(v2, 0x15u, 0, (LPVOID)(v7 + 88), &dwBufferLength, 0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_d103a73541d83417b437566f644ce9ea_Traceguids, LastError);
    return v5;
  }
  v11 = dwBufferLength;
  if ( (unsigned __int64)dwBufferLength + 2 > v8 )
  {
    v5 = 122;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v5;
    v13 = 58;
LABEL_53:
    WPP_SF_(v12[2], v13, WPP_d103a73541d83417b437566f644ce9ea_Traceguids);
    return v5;
  }
  v14 = v8 - dwBufferLength;
  *(_DWORD *)(v7 + 84) = dwBufferLength;
  v15 = (void *)(v11 + v9);
  do
  {
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)(v9 + 2 * v16) );
    if ( (_DWORD)v16 )
      ++*(_DWORD *)(v7 + 72);
    v9 += 2LL * (unsigned int)(v16 + 1);
  }
  while ( (_DWORD)v16 );
  if ( v14 )
  {
    while ( WinHttpReadData(v2, v15, v14, &dwNumberOfBytesRead) )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          WPP_d103a73541d83417b437566f644ce9ea_Traceguids,
          dwNumberOfBytesRead);
        v12 = WPP_GLOBAL_Control;
      }
      v4 += dwNumberOfBytesRead;
      if ( v14 <= dwNumberOfBytesRead )
        v14 = 0;
      else
        v14 -= dwNumberOfBytesRead;
      if ( v4 > 0xFFFF )
      {
        v5 = 58;
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
        {
          v17 = 61;
          v18 = 0xFFFF;
LABEL_48:
          WPP_SF_d(v12[2], v17, WPP_d103a73541d83417b437566f644ce9ea_Traceguids, v18);
          return v5;
        }
        return v5;
      }
      if ( !dwNumberOfBytesRead )
      {
        *(_DWORD *)(v7 + 80) = v4;
        *(_DWORD *)(a1 + 2312) = v4 + dwBufferLength + 88;
        return v5;
      }
      if ( !v14 )
        goto LABEL_50;
    }
    v19 = GetLastError();
    v5 = v19;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 59;
      v18 = v19;
      goto LABEL_48;
    }
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
LABEL_50:
    v5 = 122;
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
    {
      v13 = 62;
      goto LABEL_53;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180023cd4  mov     rax, rsp
0x180023cd7  mov     [rax+18h], rbx
0x180023cdb  mov     [rax+10h], dl
0x180023cde  push    rbp
0x180023cdf  push    rsi
0x180023ce0  push    rdi
0x180023ce1  push    r12
0x180023ce3  push    r13
0x180023ce5  push    r14
0x180023ce7  push    r15
0x180023ce9  sub     rsp, 30h
0x180023ced  mov     r12, [rcx+230h]
0x180023cf4  lea     rdx, [rax+10h]
0x180023cf8  mov     rbp, rcx
0x180023cfb  xor     r15d, r15d
0x180023cfe  mov     rcx, r12
0x180023d01  mov     [rax+10h], r15d
0x180023d05  call    DavQueryAndParseResponseEx
0x180023d0a  mov     ebx, eax
0x180023d0c  test    eax, eax
0x180023d0e  jz      short loc_180023D55
0x180023d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d17  lea     rdi, WPP_GLOBAL_Control
0x180023d1e  cmp     rcx, rdi
0x180023d21  jz      loc_180023FDE
0x180023d27  test    byte ptr [rcx+1Ch], 1
0x180023d2b  jz      loc_180023FDE
0x180023d31  mov     eax, [rsp+68h+dwNumberOfBytesRead]
0x180023d35  lea     edx, [r15+37h]
0x180023d39  mov     rcx, [rcx+10h]
0x180023d3d  lea     r8, WPP_d103a73541d83417b437566f644ce9ea_Traceguids
0x180023d44  mov     r9d, ebx
0x180023d47  mov     dword ptr [rsp+68h+lpdwBufferLength], eax
0x180023d4b  call    WPP_SF_Dd
0x180023d50  jmp     loc_180023FDE
0x180023d55  mov     ecx, [rbp+298h]
0x180023d5b  sub     ecx, 4000078h
0x180023d61  jz      short loc_180023D74
0x180023d63  cmp     ecx, 7
0x180023d66  jnz     short loc_180023DC7
0x180023d68  mov     [rbp+908h], r15d
0x180023d6f  jmp     loc_180023FDE
0x180023d74  mov     r14d, [rbp+2ACh]
0x180023d7b  mov     rsi, [rbp+2B0h]
0x180023d82  mov     [rsp+68h+dwNumberOfBytesRead], r15d
0x180023d87  mov     [rsi+44h], r15
0x180023d8b  mov     [rsi+50h], r15
0x180023d8f  mov     [rsi+40h], r15d
0x180023d93  cmp     r14d, 58h ; 'X'
0x180023d97  jnb     short loc_180023DD1
0x180023d99  mov     rcx, cs:WPP_GLOBAL_Control
0x180023da0  lea     rdi, WPP_GLOBAL_Control
0x180023da7  cmp     rcx, rdi
0x180023daa  jz      short loc_180023DC7
0x180023dac  test    byte ptr [rcx+1Ch], 1
0x180023db0  jz      short loc_180023DC7
0x180023db2  mov     rcx, [rcx+10h]
0x180023db6  lea     r8, WPP_d103a73541d83417b437566f644ce9ea_Traceguids
0x180023dbd  mov     edx, 38h ; '8'
0x180023dc2  call    WPP_SF_
0x180023dc7  mov     ebx, 57h ; 'W'
0x180023dcc  jmp     loc_180023FDE
0x180023dd1  add     r14d, 0FFFFFFA8h
0x180023dd5  cmp     r14d, 2
0x180023dd9  jnb     short loc_180023DE5
0x180023ddb  mov     ebx, 7Ah ; 'z'
0x180023de0  jmp     loc_180023FDE
0x180023de5  xor     r8d, r8d; pwszName
0x180023de8  mov     [rsp+68h+lpdwIndex], r15; lpdwIndex
0x180023ded  lea     rax, [rsp+68h+dwBufferLength]
0x180023df2  mov     [rsp+68h+dwBufferLength], r14d
0x180023df7  lea     rdi, [rsi+58h]
0x180023dfb  mov     [rsp+68h+lpdwBufferLength], rax; lpdwBufferLength
0x180023e00  mov     r9, rdi; lpBuffer
0x180023e03  mov     rcx, r12; hRequest
0x180023e06  lea     edx, [r8+15h]; dwInfoLevel
0x180023e0a  call    cs:__imp_WinHttpQueryHeaders
0x180023e10  test    eax, eax
0x180023e12  jnz     short loc_180023E5A
0x180023e14  call    cs:__imp_GetLastError
0x180023e1a  mov     ebx, eax
0x180023e1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e23  lea     rdi, WPP_GLOBAL_Control
0x180023e2a  cmp     rcx, rdi
0x180023e2d  jz      loc_180023FDE
0x180023e33  test    byte ptr [rcx+1Ch], 1
0x180023e37  jz      loc_180023FDE
0x180023e3d  mov     rcx, [rcx+10h]
0x180023e41  lea     r8, WPP_d103a73541d83417b437566f644ce9ea_Traceguids
0x180023e48  mov     edx, 39h ; '9'
0x180023e4d  mov     r9d, eax
0x180023e50  call    WPP_SF_d
0x180023e55  jmp     loc_180023FDE
0x180023e5a  mov     edx, [rsp+68h+dwBufferLength]
0x180023e5e  mov     eax, r14d
0x180023e61  lea     rcx, [rdx+2]
0x180023e65  cmp     rcx, rax
0x180023e68  jbe     short loc_180023E98
0x180023e6a  mov     ebx, 7Ah ; 'z'
0x180023e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e76  lea     rdi, WPP_GLOBAL_Control
0x180023e7d  cmp     rcx, rdi
0x180023e80  jz      loc_180023FDE
0x180023e86  test    byte ptr [rcx+1Ch], 1
0x180023e8a  jz      loc_180023FDE
0x180023e90  lea     edx, [rbx-40h]
0x180023e93  jmp     loc_180023FCE
0x180023e98  sub     r14d, edx
0x180023e9b  mov     [rsi+54h], edx
0x180023e9e  xor     r8d, r8d
0x180023ea1  lea     r13, [rdx+rdi]
0x180023ea5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180023ea9  inc     rdx
0x180023eac  cmp     [rdi+rdx*2], r8w
0x180023eb1  jnz     short loc_180023EA9
0x180023eb3  test    edx, edx
0x180023eb5  jz      short loc_180023EBA
0x180023eb7  inc     dword ptr [rsi+48h]
0x180023eba  lea     eax, [rdx+1]
0x180023ebd  lea     rdi, [rdi+rax*2]
0x180023ec1  test    edx, edx
0x180023ec3  jnz     short loc_180023EA5
0x180023ec5  lea     rdi, WPP_GLOBAL_Control
0x180023ecc  test    r14d, r14d
0x180023ecf  jz      loc_180023FB4
0x180023ed5  lea     r9, [rsp+68h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x180023eda  mov     r8d, r14d; dwNumberOfBytesToRead
0x180023edd  mov     rdx, r13; lpBuffer
0x180023ee0  mov     rcx, r12; hRequest
0x180023ee3  call    cs:__imp_WinHttpReadData
0x180023ee9  xor     edx, edx
0x180023eeb  test    eax, eax
0x180023eed  jz      loc_180023F80
0x180023ef3  mov     rcx, cs:WPP_GLOBAL_Control
0x180023efa  cmp     rcx, rdi
0x180023efd  jz      short loc_180023F28
0x180023eff  test    byte ptr [rcx+1Ch], 2
0x180023f03  jz      short loc_180023F28
0x180023f05  mov     r9d, [rsp+68h+dwNumberOfBytesRead]
0x180023f0a  lea     r8, WPP_d103a73541d83417b437566f644ce9ea_Traceguids
0x180023f11  mov     rcx, [rcx+10h]
0x180023f15  mov     edx, 3Ch ; '<'
0x180023f1a  call    WPP_SF_d
0x180023f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f26  xor     edx, edx
0x180023f28  mov     eax, [rsp+68h+dwNumberOfBytesRead]
0x180023f2c  add     r15d, eax
0x180023f2f  cmp     r14d, eax
0x180023f32  jbe     short loc_180023F39
0x180023f34  sub     r14d, eax
0x180023f37  jmp     short loc_180023F3C
0x180023f39  mov     r14d, edx
0x180023f3c  mov     r8d, 0FFFFh
0x180023f42  cmp     r15d, r8d
0x180023f45  ja      short loc_180023F68
0x180023f47  test    eax, eax
0x180023f49  jz      short loc_180023F52
0x180023f4b  test    r14d, r14d
0x180023f4e  jnz     short loc_180023ED5
0x180023f50  jmp     short loc_180023FBB
0x180023f52  mov     [rsi+50h], r15d
0x180023f56  mov     ecx, [rsp+68h+dwBufferLength]
0x180023f5a  add     ecx, 58h ; 'X'
0x180023f5d  add     ecx, r15d
0x180023f60  mov     [rbp+908h], ecx
0x180023f66  jmp     short loc_180023FDE
0x180023f68  mov     ebx, 3Ah ; ':'
0x180023f6d  cmp     rcx, rdi
0x180023f70  jz      short loc_180023FDE
0x180023f72  test    byte ptr [rcx+1Ch], 1
0x180023f76  jz      short loc_180023FDE
0x180023f78  lea     edx, [rbx+3]
0x180023f7b  mov     r9d, r8d
0x180023f7e  jmp     short loc_180023FA2
0x180023f80  call    cs:__imp_GetLastError
0x180023f86  mov     ebx, eax
0x180023f88  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f8f  cmp     rcx, rdi
0x180023f92  jz      short loc_180023FDE
0x180023f94  test    byte ptr [rcx+1Ch], 1
0x180023f98  jz      short loc_180023FDE
0x180023f9a  mov     edx, 3Bh ; ';'
0x180023f9f  mov     r9d, eax
0x180023fa2  mov     rcx, [rcx+10h]
0x180023fa6  lea     r8, WPP_d103a73541d83417b437566f644ce9ea_Traceguids
0x180023fad  call    WPP_SF_d
0x180023fb2  jmp     short loc_180023FDE
0x180023fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180023fbb  mov     ebx, 7Ah ; 'z'
0x180023fc0  cmp     rcx, rdi
0x180023fc3  jz      short loc_180023FDE
0x180023fc5  test    byte ptr [rcx+1Ch], 1
0x180023fc9  jz      short loc_180023FDE
0x180023fcb  lea     edx, [rbx-3Ch]
0x180023fce  mov     rcx, [rcx+10h]
0x180023fd2  lea     r8, WPP_d103a73541d83417b437566f644ce9ea_Traceguids
0x180023fd9  call    WPP_SF_
0x180023fde  mov     eax, ebx
0x180023fe0  mov     rbx, [rsp+68h+arg_10]
0x180023fe8  add     rsp, 30h
0x180023fec  pop     r15
0x180023fee  pop     r14
0x180023ff0  pop     r13
0x180023ff2  pop     r12
0x180023ff4  pop     rdi
0x180023ff5  pop     rsi
0x180023ff6  pop     rbp
0x180023ff7  retn
```
