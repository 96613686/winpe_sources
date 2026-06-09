# DavAsyncReName

- ea: `0x18001dcb4`
- end: `0x18001dfba`
- name: `DavAsyncReName`
- size: `774`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000d9e4`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b89c`
- `0x1800134d8`
- `0x18001dcb4`
- `0x1800283fc`
- `0x180028440`
- `0x180028584`
- `0x180028680`
- `0x18002cf62`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001deac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001deac`
- `KERNEL32!LocalFree` at `0x18001de8b`
- `KERNEL32!LocalFree` at `0x18001de8b`
- `KERNEL32!LocalAlloc` at `0x18001dd6e`
- `KERNEL32!LocalAlloc` at `0x18001dd6e`
- `WINHTTP!WinHttpReadData` at `0x18001de36`
- `WINHTTP!WinHttpReadData` at `0x18001de36`

## pseudocode

```c
__int64 __fastcall DavAsyncReName(__int64 a1, char a2)
{
  void *v2; // r15
  HLOCAL v3; // rsi
  unsigned int v4; // eax
  DWORD v5; // ebx
  unsigned int v6; // edi
  DWORD LastError; // eax
  _BYTE *v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // ebx
  BOOL v11; // r14d
  __int64 v12; // rbx
  DWORD v13; // eax
  unsigned int v15; // eax
  _DWORD hMem[16]; // [rsp+30h] [rbp-79h] BYREF
  _QWORD v17[18]; // [rsp+70h] [rbp-39h] BYREF
  int v18; // [rsp+110h] [rbp+67h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+118h] [rbp+6Fh] BYREF
  __int64 v20; // [rsp+120h] [rbp+77h] BYREF
  __int64 v21; // [rsp+128h] [rbp+7Fh] BYREF

  LOBYTE(dwNumberOfBytesRead) = a2;
  v2 = *(void **)(a1 + 520);
  v3 = 0;
  dwNumberOfBytesRead = 0;
  v21 = 0;
  v20 = 0;
  v4 = DavQueryAndParseResponseEx(v2, &dwNumberOfBytesRead);
  v5 = dwNumberOfBytesRead;
  v6 = v4;
  if ( v4 )
  {
    v6 = 1176;
    if ( dwNumberOfBytesRead == 412 )
      v6 = 183;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids,
        v6,
        dwNumberOfBytesRead);
  }
  if ( v5 == 207 )
  {
    dwNumberOfBytesRead = 0;
    v18 = 0;
    memset_0(hMem, 0, 0xA0u);
    v3 = LocalAlloc(0x40u, 0x1000u);
    if ( v3 )
    {
      v10 = 0;
      while ( 1 )
      {
        if ( !WinHttpReadData(v2, v3, 0x1000u, &dwNumberOfBytesRead) )
        {
          LastError = GetLastError();
          v6 = LastError;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v9 = 41;
            goto LABEL_23;
          }
          goto LABEL_24;
        }
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids,
            dwNumberOfBytesRead);
          v8 = WPP_GLOBAL_Control;
        }
        v10 += dwNumberOfBytesRead;
        LastError = *(_DWORD *)&DavFileAttributesLimitInBytes;
        if ( v10 > *(_DWORD *)&DavFileAttributesLimitInBytes )
          break;
        v11 = dwNumberOfBytesRead == 0;
        LastError = DavPushData((_DWORD)v3, (unsigned int)&v21, (unsigned int)&v20, dwNumberOfBytesRead, v11);
        v6 = LastError;
        if ( LastError )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v9 = 44;
            goto LABEL_23;
          }
          goto LABEL_24;
        }
        if ( v11 )
        {
          v17[1] = v17;
          v17[0] = v17;
          v15 = DavParseData((__int64)hMem, v21, v20, &v18);
          v6 = v15;
          if ( v15 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids, v15);
          }
          else if ( hMem[0] )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids);
            v6 = 32;
          }
          DavFinalizeFileAttributesList(hMem);
          goto LABEL_24;
        }
      }
      v6 = 58;
      if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && (v8[28] & 1) != 0 )
      {
        v9 = 43;
        goto LABEL_23;
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 40;
LABEL_23:
        WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids, LastError);
      }
    }
  }
LABEL_24:
  DavCloseContext(v21, v20);
  if ( v3
    && !LocalFree(v3)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v13 = GetLastError();
    WPP_SF_d(v12, 48, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids, v13);
  }
  return v6;
}

```

## disassembly

```asm
0x18001dcb4  mov     byte ptr [rsp-8+dwNumberOfBytesRead], dl
0x18001dcb8  push    rbp
0x18001dcb9  push    rbx
0x18001dcba  push    rsi
0x18001dcbb  push    rdi
0x18001dcbc  push    r13
0x18001dcbe  push    r14
0x18001dcc0  push    r15
0x18001dcc2  lea     rbp, [rsp-27h]
0x18001dcc7  sub     rsp, 0D0h
0x18001dcce  mov     r15, [rcx+208h]
0x18001dcd5  lea     rdx, [rbp+57h+dwNumberOfBytesRead]
0x18001dcd9  xor     esi, esi
0x18001dcdb  mov     [rbp+57h+dwNumberOfBytesRead], 0
0x18001dce2  mov     rcx, r15
0x18001dce5  mov     [rbp+57h+arg_18], rsi
0x18001dce9  mov     [rbp+57h+arg_10], rsi
0x18001dced  call    DavQueryAndParseResponseEx
0x18001dcf2  mov     ebx, [rbp+57h+dwNumberOfBytesRead]
0x18001dcf5  mov     edi, eax
0x18001dcf7  lea     r13, WPP_GLOBAL_Control
0x18001dcfe  test    eax, eax
0x18001dd00  jz      short loc_18001DD41
0x18001dd02  cmp     ebx, 19Ch
0x18001dd08  mov     edi, 498h
0x18001dd0d  mov     eax, 0B7h
0x18001dd12  cmovz   edi, eax
0x18001dd15  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dd1c  cmp     rcx, r13
0x18001dd1f  jz      short loc_18001DD41
0x18001dd21  test    byte ptr [rcx+1Ch], 1
0x18001dd25  jz      short loc_18001DD41
0x18001dd27  mov     rcx, [rcx+10h]
0x18001dd2b  lea     edx, [rsi+27h]
0x18001dd2e  mov     r9d, edi
0x18001dd31  mov     [rsp+100h+var_E0], ebx
0x18001dd35  lea     r8, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids
0x18001dd3c  call    WPP_SF_Dd
0x18001dd41  cmp     ebx, 0CFh
0x18001dd47  jnz     loc_18001DE76
0x18001dd4d  xor     edx, edx; Val
0x18001dd4f  mov     [rbp+57h+dwNumberOfBytesRead], esi
0x18001dd52  lea     r8d, [rbx-2Fh]; Size
0x18001dd56  mov     [rbp+57h+arg_0], esi
0x18001dd59  lea     rcx, [rbp+57h+hMem]; void *
0x18001dd5d  call    memset_0
0x18001dd62  mov     edi, 1000h
0x18001dd67  mov     ecx, 40h ; '@'; uFlags
0x18001dd6c  mov     edx, edi; uBytes
0x18001dd6e  call    cs:__imp_LocalAlloc
0x18001dd74  mov     rsi, rax
0x18001dd77  test    rax, rax
0x18001dd7a  jnz     short loc_18001DDA6
0x18001dd7c  call    cs:__imp_GetLastError
0x18001dd82  mov     edi, eax
0x18001dd84  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dd8b  cmp     rcx, r13
0x18001dd8e  jz      loc_18001DE76
0x18001dd94  test    byte ptr [rcx+1Ch], 1
0x18001dd98  jz      loc_18001DE76
0x18001dd9e  lea     edx, [rsi+28h]
0x18001dda1  jmp     loc_18001DE63
0x18001dda6  xor     ebx, ebx
0x18001dda8  mov     r8d, edi
0x18001ddab  jmp     short loc_18001DE2C
0x18001ddad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ddb4  cmp     rcx, r13
0x18001ddb7  jz      short loc_18001DDDF
0x18001ddb9  test    byte ptr [rcx+1Ch], 2
0x18001ddbd  jz      short loc_18001DDDF
0x18001ddbf  mov     r9d, [rbp+57h+dwNumberOfBytesRead]
0x18001ddc3  lea     r8, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids
0x18001ddca  mov     rcx, [rcx+10h]
0x18001ddce  mov     edx, 2Ah ; '*'
0x18001ddd3  call    WPP_SF_d
0x18001ddd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dddf  mov     r9d, [rbp+57h+dwNumberOfBytesRead]
0x18001dde3  add     ebx, r9d
0x18001dde6  mov     eax, cs:DavFileAttributesLimitInBytes
0x18001ddec  cmp     ebx, eax
0x18001ddee  ja      loc_18001DF9A
0x18001ddf4  xor     r14d, r14d
0x18001ddf7  lea     r8, [rbp+57h+arg_10]
0x18001ddfb  test    r9d, r9d
0x18001ddfe  lea     rdx, [rbp+57h+arg_18]
0x18001de02  mov     rcx, rsi
0x18001de05  setz    r14b
0x18001de09  mov     [rsp+100h+var_E0], r14d
0x18001de0e  call    DavPushData
0x18001de13  mov     edi, eax
0x18001de15  test    eax, eax
0x18001de17  jnz     loc_18001DF76
0x18001de1d  test    r14d, r14d
0x18001de20  jnz     loc_18001DEDD
0x18001de26  mov     r8d, 1000h; dwNumberOfBytesToRead
0x18001de2c  lea     r9, [rbp+57h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18001de30  mov     rdx, rsi; lpBuffer
0x18001de33  mov     rcx, r15; hRequest
0x18001de36  call    cs:__imp_WinHttpReadData
0x18001de3c  test    eax, eax
0x18001de3e  jnz     loc_18001DDAD
0x18001de44  call    cs:__imp_GetLastError
0x18001de4a  mov     edi, eax
0x18001de4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de53  cmp     rcx, r13
0x18001de56  jz      short loc_18001DE76
0x18001de58  test    byte ptr [rcx+1Ch], 1
0x18001de5c  jz      short loc_18001DE76
0x18001de5e  mov     edx, 29h ; ')'
0x18001de63  mov     rcx, [rcx+10h]
0x18001de67  lea     r8, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids
0x18001de6e  mov     r9d, eax
0x18001de71  call    WPP_SF_d
0x18001de76  mov     rdx, [rbp+57h+arg_10]
0x18001de7a  mov     rcx, [rbp+57h+arg_18]
0x18001de7e  call    DavCloseContext
0x18001de83  test    rsi, rsi
0x18001de86  jz      short loc_18001DEC9
0x18001de88  mov     rcx, rsi; hMem
0x18001de8b  call    cs:__imp_LocalFree
0x18001de91  test    rax, rax
0x18001de94  jnz     short loc_18001DEC9
0x18001de96  mov     rbx, cs:WPP_GLOBAL_Control
0x18001de9d  cmp     rbx, r13
0x18001dea0  jz      short loc_18001DEC9
0x18001dea2  test    byte ptr [rbx+1Ch], 1
0x18001dea6  jz      short loc_18001DEC9
0x18001dea8  mov     rbx, [rbx+10h]
0x18001deac  call    cs:__imp_GetLastError
0x18001deb2  mov     edx, 30h ; '0'
0x18001deb7  lea     r8, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids
0x18001debe  mov     r9d, eax
0x18001dec1  mov     rcx, rbx
0x18001dec4  call    WPP_SF_d
0x18001dec9  mov     eax, edi
0x18001decb  add     rsp, 0D0h
0x18001ded2  pop     r15
0x18001ded4  pop     r14
0x18001ded6  pop     r13
0x18001ded8  pop     rdi
0x18001ded9  pop     rsi
0x18001deda  pop     rbx
0x18001dedb  pop     rbp
0x18001dedc  retn
0x18001dedd  mov     r8, [rbp+57h+arg_10]
0x18001dee1  lea     rax, [rbp+57h+var_90]
0x18001dee5  mov     rdx, [rbp+57h+arg_18]
0x18001dee9  lea     r9, [rbp+57h+arg_0]
0x18001deed  mov     [rbp+57h+var_88], rax
0x18001def1  lea     rcx, [rbp+57h+hMem]
0x18001def5  lea     rax, [rbp+57h+var_90]
0x18001def9  mov     [rbp+57h+var_90], rax
0x18001defd  call    DavParseData
0x18001df02  mov     edi, eax
0x18001df04  test    eax, eax
0x18001df06  jz      short loc_18001DF42
0x18001df08  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df0f  cmp     rcx, r13
0x18001df12  jz      short loc_18001DF32
0x18001df14  test    byte ptr [rcx+1Ch], 1
0x18001df18  jz      short loc_18001DF32
0x18001df1a  mov     rcx, [rcx+10h]
0x18001df1e  lea     r8, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids
0x18001df25  mov     edx, 2Dh ; '-'
0x18001df2a  mov     r9d, eax
0x18001df2d  call    WPP_SF_d
0x18001df32  xor     edx, edx
0x18001df34  lea     rcx, [rbp+57h+hMem]; hMem
0x18001df38  call    DavFinalizeFileAttributesList
0x18001df3d  jmp     loc_18001DE76
0x18001df42  cmp     [rbp+57h+hMem], 0
0x18001df46  jz      short loc_18001DF32
0x18001df48  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df4f  cmp     rcx, r13
0x18001df52  jz      short loc_18001DF6F
0x18001df54  test    byte ptr [rcx+1Ch], 1
0x18001df58  jz      short loc_18001DF6F
0x18001df5a  mov     rcx, [rcx+10h]
0x18001df5e  lea     r8, WPP_0457ef77d9993115458dc6abacb02a8f_Traceguids
0x18001df65  mov     edx, 2Eh ; '.'
0x18001df6a  call    WPP_SF_
0x18001df6f  mov     edi, 20h ; ' '
0x18001df74  jmp     short loc_18001DF32
0x18001df76  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df7d  cmp     rcx, r13
0x18001df80  jz      loc_18001DE76
0x18001df86  test    byte ptr [rcx+1Ch], 1
0x18001df8a  jz      loc_18001DE76
0x18001df90  mov     edx, 2Ch ; ','
0x18001df95  jmp     loc_18001DE63
0x18001df9a  mov     edi, 3Ah ; ':'
0x18001df9f  cmp     rcx, r13
0x18001dfa2  jz      loc_18001DE76
0x18001dfa8  test    byte ptr [rcx+1Ch], 1
0x18001dfac  jz      loc_18001DE76
0x18001dfb2  lea     edx, [rdi-0Fh]
0x18001dfb5  jmp     loc_18001DE63
```
