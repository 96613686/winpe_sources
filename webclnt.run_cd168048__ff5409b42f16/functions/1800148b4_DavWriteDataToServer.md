# DavWriteDataToServer

- ea: `0x1800148b4`
- end: `0x180014cac`
- name: `DavWriteDataToServer`
- size: `1016`
- prototype: `__int64 __fastcall(PVOID pvCallbackContext)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000d9e4`

## callees

- `0x18000b7dc`
- `0x1800148b4`
- `0x1800297e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b5b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180014a38`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180014aa5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180014a38`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180014aa5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800149d3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800149d3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800149c2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014a7f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800149c2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014a7f`
- `KERNEL32!LocalFree` at `0x180014b02`
- `KERNEL32!LocalFree` at `0x180014b02`
- `KERNEL32!LocalAlloc` at `0x180014988`
- `KERNEL32!LocalAlloc` at `0x180014988`
- `ADVAPI32!ReadEncryptedFileRaw` at `0x180014c32`
- `ADVAPI32!ReadEncryptedFileRaw` at `0x180014c32`
- `WINHTTP!WinHttpWriteData` at `0x180014a77`
- `WINHTTP!WinHttpWriteData` at `0x180014a77`

## pseudocode

```c
__int64 __fastcall DavWriteDataToServer(_DWORD *pvCallbackContext)
{
  bool v1; // zf
  int v3; // eax
  __int64 v4; // r9
  void *v5; // r14
  void *v6; // r8
  void *v7; // r12
  DWORD v8; // edi
  __int64 v9; // r15
  HLOCAL v10; // r13
  DWORD EncryptedFileRaw; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  DWORD LastError; // eax
  unsigned int v15; // r15d
  DWORD v16; // eax
  BOOL v17; // ebx
  _BYTE *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  _BYTE *v21; // rax
  unsigned int v22; // eax
  DWORD v23; // eax
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+8h] BYREF
  DWORD dwNumberOfBytesWritten; // [rsp+78h] [rbp+10h] BYREF

  v1 = pvCallbackContext[12] == 3;
  NumberOfBytesRead = 0;
  dwNumberOfBytesWritten = 0;
  if ( v1 )
  {
    v3 = pvCallbackContext[142];
    v4 = (unsigned int)pvCallbackContext[130];
    v5 = (void *)*((_QWORD *)pvCallbackContext + 69);
    v6 = (void *)*((_QWORD *)pvCallbackContext + 70);
    v7 = (void *)*((_QWORD *)pvCallbackContext + 68);
  }
  else
  {
    if ( pvCallbackContext[12] != 13 )
    {
      v5 = 0;
      v7 = 0;
      v4 = 0;
      goto LABEL_7;
    }
    v3 = pvCallbackContext[138];
    v4 = (unsigned int)pvCallbackContext[128];
    v5 = (void *)*((_QWORD *)pvCallbackContext + 67);
    v6 = (void *)*((_QWORD *)pvCallbackContext + 68);
    v7 = (void *)*((_QWORD *)pvCallbackContext + 70);
  }
  if ( v3 == 1 )
  {
    EncryptedFileRaw = ReadEncryptedFileRaw(DavWriteDataToServerRawCallback, pvCallbackContext, v6);
    v8 = EncryptedFileRaw;
    if ( EncryptedFileRaw )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v8;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_54;
      v13 = 251;
      goto LABEL_52;
    }
LABEL_53:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_54;
  }
LABEL_7:
  v8 = 0;
  if ( !(_DWORD)v4 )
    goto LABEL_53;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 243, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v4);
  v9 = 4096;
  v10 = LocalAlloc(0x40u, 0x1000u);
  if ( v10 )
  {
    RevertToSelf();
    if ( SetFilePointer(v5, 0, 0, 0) == -1 )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 245, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, LastError);
    }
    else
    {
      v15 = 0;
      if ( ReadFile(v5, v10, 0x1000u, &NumberOfBytesRead, 0) )
      {
        while ( 1 )
        {
          v15 += NumberOfBytesRead;
          if ( !NumberOfBytesRead )
            break;
          v16 = UMReflectorImpersonate(pvCallbackContext, *((_QWORD *)pvCallbackContext + 9));
          v8 = v16;
          if ( v16 )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v19 = 248;
              goto LABEL_27;
            }
            goto LABEL_29;
          }
          v17 = WinHttpWriteData(v7, v10, NumberOfBytesRead, &dwNumberOfBytesWritten);
          RevertToSelf();
          if ( !v17 )
          {
            v23 = GetLastError();
            v8 = v23;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 249, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v23);
            goto LABEL_29;
          }
          if ( !ReadFile(v5, v10, 0x1000u, &NumberOfBytesRead, 0) )
            goto LABEL_24;
        }
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 247, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v15);
            v18 = WPP_GLOBAL_Control;
          }
          if ( v18 != (_BYTE *)&WPP_GLOBAL_Control && (v18[28] & 2) != 0 )
          {
            v19 = 250;
            v20 = v15;
            goto LABEL_28;
          }
        }
      }
      else
      {
LABEL_24:
        v16 = GetLastError();
        v8 = v16;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 246;
LABEL_27:
          v20 = v16;
LABEL_28:
          WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v20);
        }
      }
LABEL_29:
      v9 = 4096;
    }
    v21 = v10;
    do
    {
      *v21++ = 0;
      --v9;
    }
    while ( v9 );
    LocalFree(v10);
    v22 = UMReflectorImpersonate(pvCallbackContext, *((_QWORD *)pvCallbackContext + 9));
    if ( v22 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v8;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_54;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v22);
    }
    goto LABEL_53;
  }
  EncryptedFileRaw = GetLastError();
  v8 = EncryptedFileRaw;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 244;
LABEL_52:
    WPP_SF_d(v12[2], v13, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, EncryptedFileRaw);
    goto LABEL_53;
  }
LABEL_54:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
    WPP_SF_d(v12[2], 253, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x1800148b4  mov     [rsp+arg_10], rbx
0x1800148b9  push    rbp
0x1800148ba  push    rsi
0x1800148bb  push    rdi
0x1800148bc  push    r12
0x1800148be  push    r13
0x1800148c0  push    r14
0x1800148c2  push    r15
0x1800148c4  sub     rsp, 30h
0x1800148c8  cmp     dword ptr [rcx+30h], 3
0x1800148cc  lea     rbx, WPP_GLOBAL_Control
0x1800148d3  mov     rsi, rcx
0x1800148d6  mov     [rsp+68h+NumberOfBytesRead], 0
0x1800148de  mov     [rsp+68h+dwNumberOfBytesWritten], 0
0x1800148e6  jz      short loc_18001491D
0x1800148e8  cmp     dword ptr [rcx+30h], 0Dh
0x1800148ec  jnz     short loc_180014912
0x1800148ee  mov     eax, [rcx+228h]
0x1800148f4  mov     r9d, [rcx+200h]
0x1800148fb  mov     r14, [rcx+218h]
0x180014902  mov     r8, [rcx+220h]
0x180014909  mov     r12, [rcx+230h]
0x180014910  jmp     short loc_18001493F
0x180014912  xor     r14d, r14d
0x180014915  xor     r12d, r12d
0x180014918  xor     r9d, r9d
0x18001491b  jmp     short loc_180014948
0x18001491d  mov     eax, [rcx+238h]
0x180014923  mov     r9d, [rcx+208h]
0x18001492a  mov     r14, [rcx+228h]
0x180014931  mov     r8, [rcx+230h]; pvContext
0x180014938  mov     r12, [rcx+220h]
0x18001493f  cmp     eax, 1
0x180014942  jz      loc_180014C28
0x180014948  xor     edi, edi
0x18001494a  test    r9d, r9d
0x18001494d  jz      loc_180014C68
0x180014953  mov     rcx, cs:WPP_GLOBAL_Control
0x18001495a  cmp     rcx, rbx
0x18001495d  jz      short loc_18001497A
0x18001495f  test    byte ptr [rcx+1Ch], 2
0x180014963  jz      short loc_18001497A
0x180014965  mov     rcx, [rcx+10h]
0x180014969  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180014970  mov     edx, 0F3h
0x180014975  call    WPP_SF_d
0x18001497a  mov     r15d, 1000h
0x180014980  mov     ecx, 40h ; '@'; uFlags
0x180014985  mov     edx, r15d; uBytes
0x180014988  call    cs:__imp_LocalAlloc
0x18001498e  mov     r13, rax
0x180014991  test    rax, rax
0x180014994  jnz     short loc_1800149C2
0x180014996  call    cs:__imp_GetLastError
0x18001499c  mov     edi, eax
0x18001499e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149a5  cmp     rcx, rbx
0x1800149a8  jz      loc_180014C92
0x1800149ae  test    byte ptr [rcx+1Ch], 1
0x1800149b2  jz      loc_180014C6F
0x1800149b8  mov     edx, 0F4h
0x1800149bd  jmp     loc_180014C55
0x1800149c2  call    cs:__imp_RevertToSelf
0x1800149c8  xor     r9d, r9d; dwMoveMethod
0x1800149cb  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800149ce  xor     edx, edx; lDistanceToMove
0x1800149d0  mov     rcx, r14; hFile
0x1800149d3  call    cs:__imp_SetFilePointer
0x1800149d9  cmp     eax, 0FFFFFFFFh
0x1800149dc  jnz     short loc_180014A1F
0x1800149de  xor     ebp, ebp
0x1800149e0  call    cs:__imp_GetLastError
0x1800149e6  mov     edi, eax
0x1800149e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149ef  cmp     rcx, rbx
0x1800149f2  jz      loc_180014AF0
0x1800149f8  test    byte ptr [rcx+1Ch], 1
0x1800149fc  jz      loc_180014AF0
0x180014a02  mov     rcx, [rcx+10h]
0x180014a06  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180014a0d  mov     edx, 0F5h
0x180014a12  mov     r9d, eax
0x180014a15  call    WPP_SF_d
0x180014a1a  jmp     loc_180014AF0
0x180014a1f  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180014a24  mov     [rsp+68h+lpOverlapped], rdi; lpOverlapped
0x180014a29  mov     r8d, 1000h; nNumberOfBytesToRead
0x180014a2f  mov     rdx, r13; lpBuffer
0x180014a32  mov     rcx, r14; hFile
0x180014a35  xor     r15d, r15d
0x180014a38  call    cs:__imp_ReadFile
0x180014a3e  test    eax, eax
0x180014a40  jz      short loc_180014AB6
0x180014a42  mov     eax, [rsp+68h+NumberOfBytesRead]
0x180014a46  add     r15d, eax
0x180014a49  test    eax, eax
0x180014a4b  jz      loc_180014BCC
0x180014a51  mov     rdx, [rsi+48h]
0x180014a55  mov     rcx, rsi
0x180014a58  call    UMReflectorImpersonate
0x180014a5d  mov     edi, eax
0x180014a5f  test    eax, eax
0x180014a61  jnz     loc_180014BA1
0x180014a67  mov     r8d, [rsp+68h+NumberOfBytesRead]; dwNumberOfBytesToWrite
0x180014a6c  lea     r9, [rsp+68h+dwNumberOfBytesWritten]; lpdwNumberOfBytesWritten
0x180014a71  mov     rdx, r13; lpBuffer
0x180014a74  mov     rcx, r12; hRequest
0x180014a77  call    cs:__imp_WinHttpWriteData
0x180014a7d  mov     ebx, eax
0x180014a7f  call    cs:__imp_RevertToSelf
0x180014a85  xor     ebp, ebp
0x180014a87  test    ebx, ebx
0x180014a89  jz      loc_180014B5B
0x180014a8f  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180014a94  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x180014a99  mov     r8d, 1000h; nNumberOfBytesToRead
0x180014a9f  mov     rdx, r13; lpBuffer
0x180014aa2  mov     rcx, r14; hFile
0x180014aa5  call    cs:__imp_ReadFile
0x180014aab  test    eax, eax
0x180014aad  jnz     short loc_180014A42
0x180014aaf  lea     rbx, WPP_GLOBAL_Control
0x180014ab6  call    cs:__imp_GetLastError
0x180014abc  mov     edi, eax
0x180014abe  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ac5  cmp     rcx, rbx
0x180014ac8  jz      short loc_180014AE8
0x180014aca  test    byte ptr [rcx+1Ch], 1
0x180014ace  jz      short loc_180014AE8
0x180014ad0  mov     edx, 0F6h
0x180014ad5  mov     r9d, eax
0x180014ad8  mov     rcx, [rcx+10h]
0x180014adc  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180014ae3  call    WPP_SF_d
0x180014ae8  xor     ebp, ebp
0x180014aea  mov     r15d, 1000h
0x180014af0  mov     rax, r13
0x180014af3  mov     byte ptr [rax], 0
0x180014af6  inc     rax
0x180014af9  sub     r15, 1
0x180014afd  jnz     short loc_180014AF3
0x180014aff  mov     rcx, r13; hMem
0x180014b02  call    cs:__imp_LocalFree
0x180014b08  test    ebp, ebp
0x180014b0a  jnz     loc_180014C68
0x180014b10  mov     rdx, [rsi+48h]
0x180014b14  mov     rcx, rsi
0x180014b17  call    UMReflectorImpersonate
0x180014b1c  test    eax, eax
0x180014b1e  jz      loc_180014C68
0x180014b24  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b2b  cmp     rcx, rbx
0x180014b2e  jz      loc_180014C92
0x180014b34  test    byte ptr [rcx+1Ch], 1
0x180014b38  jz      loc_180014C6F
0x180014b3e  mov     rcx, [rcx+10h]
0x180014b42  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180014b49  mov     edx, 0FCh
0x180014b4e  mov     r9d, eax
0x180014b51  call    WPP_SF_d
0x180014b56  jmp     loc_180014C68
0x180014b5b  call    cs:__imp_GetLastError
0x180014b61  mov     edi, eax
0x180014b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b6a  lea     rbx, WPP_GLOBAL_Control
0x180014b71  cmp     rcx, rbx
0x180014b74  jz      loc_180014AEA
0x180014b7a  test    byte ptr [rcx+1Ch], 1
0x180014b7e  jz      loc_180014AEA
0x180014b84  mov     rcx, [rcx+10h]
0x180014b88  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180014b8f  mov     edx, 0F9h
0x180014b94  mov     r9d, eax
0x180014b97  call    WPP_SF_d
0x180014b9c  jmp     loc_180014AEA
0x180014ba1  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ba8  lea     rbx, WPP_GLOBAL_Control
0x180014baf  cmp     rcx, rbx
0x180014bb2  jz      loc_180014AE8
0x180014bb8  test    byte ptr [rcx+1Ch], 1
0x180014bbc  jz      loc_180014AE8
0x180014bc2  mov     edx, 0F8h
0x180014bc7  jmp     loc_180014AD5
0x180014bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bd3  lea     rbx, WPP_GLOBAL_Control
0x180014bda  cmp     rcx, rbx
0x180014bdd  jz      loc_180014AE8
0x180014be3  test    byte ptr [rcx+1Ch], 2
0x180014be7  jz      short loc_180014C08
0x180014be9  mov     rcx, [rcx+10h]
0x180014bed  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180014bf4  mov     edx, 0F7h
0x180014bf9  mov     r9d, r15d
0x180014bfc  call    WPP_SF_d
0x180014c01  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c08  cmp     rcx, rbx
0x180014c0b  jz      loc_180014AE8
0x180014c11  test    byte ptr [rcx+1Ch], 2
0x180014c15  jz      loc_180014AE8
0x180014c1b  mov     edx, 0FAh
0x180014c20  mov     r9d, r15d
0x180014c23  jmp     loc_180014AD8
0x180014c28  mov     rdx, rsi; pvCallbackContext
0x180014c2b  lea     rcx, DavWriteDataToServerRawCallback; pfExportCallback
0x180014c32  call    cs:__imp_ReadEncryptedFileRaw
0x180014c38  mov     edi, eax
0x180014c3a  test    eax, eax
0x180014c3c  jz      short loc_180014C68
0x180014c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c45  cmp     rcx, rbx
0x180014c48  jz      short loc_180014C92
0x180014c4a  test    byte ptr [rcx+1Ch], 1
0x180014c4e  jz      short loc_180014C6F
0x180014c50  mov     edx, 0FBh
0x180014c55  mov     rcx, [rcx+10h]
0x180014c59  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180014c60  mov     r9d, eax
0x180014c63  call    WPP_SF_d
0x180014c68  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c6f  cmp     rcx, rbx
0x180014c72  jz      short loc_180014C92
0x180014c74  test    byte ptr [rcx+1Ch], 2
0x180014c78  jz      short loc_180014C92
0x180014c7a  mov     rcx, [rcx+10h]
0x180014c7e  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180014c85  mov     edx, 0FDh
0x180014c8a  mov     r9d, edi
0x180014c8d  call    WPP_SF_d
0x180014c92  mov     rbx, [rsp+68h+arg_10]
0x180014c9a  mov     eax, edi
0x180014c9c  add     rsp, 30h
0x180014ca0  pop     r15
0x180014ca2  pop     r14
0x180014ca4  pop     r13
0x180014ca6  pop     r12
0x180014ca8  pop     rdi
0x180014ca9  pop     rsi
0x180014caa  pop     rbp
0x180014cab  retn
```
