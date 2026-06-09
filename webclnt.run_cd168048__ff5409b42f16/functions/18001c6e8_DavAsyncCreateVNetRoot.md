# DavAsyncCreateVNetRoot

- ea: `0x18001c6e8`
- end: `0x18001ca61`
- name: `DavAsyncCreateVNetRoot`
- size: `889`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d9e4`

## callees

- `0x18000b4f0`
- `0x18000b7b4`
- `0x18000b7dc`
- `0x1800134d8`
- `0x18001c6e8`
- `0x1800206bc`
- `0x180028440`
- `0x18002cf62`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c940`
- `KERNEL32!LocalFree` at `0x18001ca1f`
- `KERNEL32!LocalFree` at `0x18001ca2d`
- `KERNEL32!LocalFree` at `0x18001ca1f`
- `KERNEL32!LocalFree` at `0x18001ca2d`
- `KERNEL32!LocalAlloc` at `0x18001c7a9`
- `KERNEL32!LocalAlloc` at `0x18001c8e4`
- `KERNEL32!LocalAlloc` at `0x18001c7a9`
- `KERNEL32!LocalAlloc` at `0x18001c8e4`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001c806`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001c936`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001c806`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001c936`

## pseudocode

```c
__int64 __fastcall DavAsyncCreateVNetRoot(__int64 a1)
{
  void *v2; // r13
  unsigned int v3; // eax
  __int64 v4; // r8
  unsigned int v5; // ebx
  wchar_t *v6; // r15
  WCHAR *v7; // r12
  DWORD LastError; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  wchar_t *v12; // rax
  int v13; // ecx
  DWORD dwBufferLength[4]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD hMem[14]; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+B0h] [rbp-50h]
  _BYTE Buffer[208]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(hMem, 0, 0xA0u);
  v2 = *(void **)(a1 + 520);
  dwBufferLength[0] = 0;
  v3 = DavQueryAndParseResponseEx(v2, 0);
  v5 = v3;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_d606ec14d11b32b0b0ec681c2fe61536_Traceguids, v3);
    return v5;
  }
  v6 = 0;
  v7 = 0;
  if ( *(_DWORD *)&AcceptOfficeAndTahoeServers )
  {
LABEL_37:
    *(_DWORD *)(a1 + 2320) = 1;
    v5 = DavParseXmlResponse(v2, hMem, v4);
    if ( !v5 )
    {
      v13 = v17;
      *(_DWORD *)(a1 + 2324) = v17;
      *(_DWORD *)(*(_QWORD *)(a1 + 504) + 60LL) = v13;
      DavFinalizeFileAttributesList((char *)hMem, 0);
    }
    if ( !v6 )
      goto LABEL_41;
    goto LABEL_40;
  }
  v6 = (wchar_t *)LocalAlloc(0x40u, 0x32u);
  if ( !v6 )
    return 8;
  memset_0(Buffer, 0, 0xC8u);
  StringCbCopyW(v6, 0x32u, L"MicrosoftOfficeWebServer");
  dwBufferLength[0] = 200;
  if ( WinHttpQueryHeaders(v2, 0xFFFFu, v6, Buffer, dwBufferLength, 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_d606ec14d11b32b0b0ec681c2fe61536_Traceguids);
    v11 = 1;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 12150 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_40;
      v10 = 56;
      goto LABEL_13;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_d606ec14d11b32b0b0ec681c2fe61536_Traceguids);
    v11 = 0;
  }
  *(_DWORD *)(a1 + 2312) = v11;
  memset_0(Buffer, 0, 0xC8u);
  v12 = (wchar_t *)LocalAlloc(0x40u, 0x2Au);
  v7 = v12;
  if ( !v12 )
  {
    v5 = 8;
    goto LABEL_40;
  }
  StringCbCopyW(v12, 0x2Au, L"MicrosoftTahoeServer");
  dwBufferLength[0] = 200;
  if ( WinHttpQueryHeaders(v2, 0xFFFFu, v7, Buffer, dwBufferLength, 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_d606ec14d11b32b0b0ec681c2fe61536_Traceguids);
    *(_DWORD *)(a1 + 2316) = 1;
    goto LABEL_37;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError == 12150 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_d606ec14d11b32b0b0ec681c2fe61536_Traceguids);
    *(_DWORD *)(a1 + 2316) = 0;
    goto LABEL_37;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_40;
  v10 = 59;
LABEL_13:
  WPP_SF_d(v9[2], v10, WPP_d606ec14d11b32b0b0ec681c2fe61536_Traceguids, LastError);
LABEL_40:
  LocalFree(v6);
LABEL_41:
  if ( v7 )
    LocalFree(v7);
  return v5;
}

```

## disassembly

```asm
0x18001c6e8  mov     [rsp-8+arg_8], rbx
0x18001c6ed  mov     [rsp-8+arg_10], rdi
0x18001c6f2  push    rbp
0x18001c6f3  push    r12
0x18001c6f5  push    r13
0x18001c6f7  push    r14
0x18001c6f9  push    r15
0x18001c6fb  lea     rbp, [rsp-0C0h]
0x18001c703  sub     rsp, 1C0h
0x18001c70a  mov     rax, cs:__security_cookie
0x18001c711  xor     rax, rsp
0x18001c714  mov     [rbp+0E0h+var_30], rax
0x18001c71b  mov     r14, rcx
0x18001c71e  xor     edx, edx; Val
0x18001c720  lea     rcx, [rsp+1E0h+hMem]; void *
0x18001c725  mov     r8d, 0A0h; Size
0x18001c72b  call    memset_0
0x18001c730  mov     r13, [r14+208h]
0x18001c737  xor     edx, edx
0x18001c739  mov     rcx, r13
0x18001c73c  mov     [rsp+1E0h+dwBufferLength], 0
0x18001c744  call    DavQueryAndParseResponseEx
0x18001c749  mov     ebx, eax
0x18001c74b  test    eax, eax
0x18001c74d  jz      short loc_18001C78D
0x18001c74f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c756  lea     rdi, WPP_GLOBAL_Control
0x18001c75d  cmp     rcx, rdi
0x18001c760  jz      loc_18001CA33
0x18001c766  test    byte ptr [rcx+1Ch], 1
0x18001c76a  jz      loc_18001CA33
0x18001c770  mov     rcx, [rcx+10h]
0x18001c774  lea     r8, WPP_d606ec14d11b32b0b0ec681c2fe61536_Traceguids
0x18001c77b  mov     edx, 37h ; '7'
0x18001c780  mov     r9d, eax
0x18001c783  call    WPP_SF_d
0x18001c788  jmp     loc_18001CA33
0x18001c78d  xor     r15d, r15d
0x18001c790  xor     r12d, r12d
0x18001c793  cmp     cs:AcceptOfficeAndTahoeServers, r12d
0x18001c79a  jnz     loc_18001C9D9
0x18001c7a0  lea     ebx, [r15+32h]
0x18001c7a4  mov     edx, ebx; uBytes
0x18001c7a6  lea     ecx, [rbx+0Eh]; uFlags
0x18001c7a9  call    cs:__imp_LocalAlloc
0x18001c7af  mov     r15, rax
0x18001c7b2  test    rax, rax
0x18001c7b5  jnz     short loc_18001C7BF
0x18001c7b7  lea     ebx, [rax+8]
0x18001c7ba  jmp     loc_18001CA33
0x18001c7bf  mov     edi, 0C8h
0x18001c7c4  lea     rcx, [rbp+0E0h+Buffer]; void *
0x18001c7c8  mov     r8d, edi; Size
0x18001c7cb  xor     edx, edx; Val
0x18001c7cd  call    memset_0
0x18001c7d2  lea     r8, aMicrosoftoffic; "MicrosoftOfficeWebServer"
0x18001c7d9  mov     rdx, rbx; cbDest
0x18001c7dc  mov     rcx, r15; pszDest
0x18001c7df  call    StringCbCopyW
0x18001c7e4  lea     rax, [rsp+1E0h+dwBufferLength]
0x18001c7e9  mov     [rsp+1E0h+lpdwIndex], r12; lpdwIndex
0x18001c7ee  lea     r9, [rbp+0E0h+Buffer]; lpBuffer
0x18001c7f2  mov     [rsp+1E0h+lpdwBufferLength], rax; lpdwBufferLength
0x18001c7f7  mov     r8, r15; pwszName
0x18001c7fa  mov     [rsp+1E0h+dwBufferLength], edi
0x18001c7fe  mov     edx, 0FFFFh; dwInfoLevel
0x18001c803  mov     rcx, r13; hRequest
0x18001c806  call    cs:__imp_WinHttpQueryHeaders
0x18001c80c  test    eax, eax
0x18001c80e  jnz     short loc_18001C88F
0x18001c810  call    cs:__imp_GetLastError
0x18001c816  mov     ebx, eax
0x18001c818  cmp     eax, 2F76h
0x18001c81d  jz      short loc_18001C85D
0x18001c81f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c826  lea     rdi, WPP_GLOBAL_Control
0x18001c82d  cmp     rcx, rdi
0x18001c830  jz      loc_18001CA1C
0x18001c836  test    byte ptr [rcx+1Ch], 1
0x18001c83a  jz      loc_18001CA1C
0x18001c840  mov     edx, 38h ; '8'
0x18001c845  mov     rcx, [rcx+10h]
0x18001c849  lea     r8, WPP_d606ec14d11b32b0b0ec681c2fe61536_Traceguids
0x18001c850  mov     r9d, eax
0x18001c853  call    WPP_SF_d
0x18001c858  jmp     loc_18001CA1C
0x18001c85d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c864  lea     rdi, WPP_GLOBAL_Control
0x18001c86b  cmp     rcx, rdi
0x18001c86e  jz      short loc_18001C88B
0x18001c870  test    byte ptr [rcx+1Ch], 2
0x18001c874  jz      short loc_18001C88B
0x18001c876  mov     rcx, [rcx+10h]
0x18001c87a  lea     r8, WPP_d606ec14d11b32b0b0ec681c2fe61536_Traceguids
0x18001c881  mov     edx, 39h ; '9'
0x18001c886  call    WPP_SF_
0x18001c88b  xor     eax, eax
0x18001c88d  jmp     short loc_18001C8C2
0x18001c88f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c896  lea     rdi, WPP_GLOBAL_Control
0x18001c89d  cmp     rcx, rdi
0x18001c8a0  jz      short loc_18001C8BD
0x18001c8a2  test    byte ptr [rcx+1Ch], 2
0x18001c8a6  jz      short loc_18001C8BD
0x18001c8a8  mov     rcx, [rcx+10h]
0x18001c8ac  lea     r8, WPP_d606ec14d11b32b0b0ec681c2fe61536_Traceguids
0x18001c8b3  mov     edx, 3Ah ; ':'
0x18001c8b8  call    WPP_SF_
0x18001c8bd  mov     eax, 1
0x18001c8c2  xor     edx, edx; Val
0x18001c8c4  mov     [r14+908h], eax
0x18001c8cb  mov     r8d, 0C8h; Size
0x18001c8d1  lea     rcx, [rbp+0E0h+Buffer]; void *
0x18001c8d5  call    memset_0
0x18001c8da  mov     ebx, 2Ah ; '*'
0x18001c8df  mov     edx, ebx; uBytes
0x18001c8e1  lea     ecx, [rbx+16h]; uFlags
0x18001c8e4  call    cs:__imp_LocalAlloc
0x18001c8ea  mov     r12, rax
0x18001c8ed  test    rax, rax
0x18001c8f0  jnz     short loc_18001C8FA
0x18001c8f2  lea     ebx, [rax+8]
0x18001c8f5  jmp     loc_18001CA1C
0x18001c8fa  lea     r8, aMicrosofttahoe; "MicrosoftTahoeServer"
0x18001c901  mov     rdx, rbx; cbDest
0x18001c904  mov     rcx, r12; pszDest
0x18001c907  call    StringCbCopyW
0x18001c90c  lea     rax, [rsp+1E0h+dwBufferLength]
0x18001c911  mov     [rsp+1E0h+lpdwIndex], 0; lpdwIndex
0x18001c91a  lea     r9, [rbp+0E0h+Buffer]; lpBuffer
0x18001c91e  mov     [rsp+1E0h+lpdwBufferLength], rax; lpdwBufferLength
0x18001c923  mov     r8, r12; pwszName
0x18001c926  mov     [rsp+1E0h+dwBufferLength], 0C8h
0x18001c92e  mov     edx, 0FFFFh; dwInfoLevel
0x18001c933  mov     rcx, r13; hRequest
0x18001c936  call    cs:__imp_WinHttpQueryHeaders
0x18001c93c  test    eax, eax
0x18001c93e  jnz     short loc_18001C9A7
0x18001c940  call    cs:__imp_GetLastError
0x18001c946  mov     ebx, eax
0x18001c948  cmp     eax, 2F76h
0x18001c94d  jz      short loc_18001C973
0x18001c94f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c956  cmp     rcx, rdi
0x18001c959  jz      loc_18001CA1C
0x18001c95f  test    byte ptr [rcx+1Ch], 1
0x18001c963  jz      loc_18001CA1C
0x18001c969  mov     edx, 3Bh ; ';'
0x18001c96e  jmp     loc_18001C845
0x18001c973  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c97a  cmp     rcx, rdi
0x18001c97d  jz      short loc_18001C99A
0x18001c97f  test    byte ptr [rcx+1Ch], 2
0x18001c983  jz      short loc_18001C99A
0x18001c985  mov     rcx, [rcx+10h]
0x18001c989  lea     r8, WPP_d606ec14d11b32b0b0ec681c2fe61536_Traceguids
0x18001c990  mov     edx, 3Ch ; '<'
0x18001c995  call    WPP_SF_
0x18001c99a  mov     dword ptr [r14+90Ch], 0
0x18001c9a5  jmp     short loc_18001C9D9
0x18001c9a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c9ae  cmp     rcx, rdi
0x18001c9b1  jz      short loc_18001C9CE
0x18001c9b3  test    byte ptr [rcx+1Ch], 2
0x18001c9b7  jz      short loc_18001C9CE
0x18001c9b9  mov     rcx, [rcx+10h]
0x18001c9bd  lea     r8, WPP_d606ec14d11b32b0b0ec681c2fe61536_Traceguids
0x18001c9c4  mov     edx, 3Dh ; '='
0x18001c9c9  call    WPP_SF_
0x18001c9ce  mov     dword ptr [r14+90Ch], 1
0x18001c9d9  lea     rdx, [rsp+1E0h+hMem]; hMem
0x18001c9de  mov     dword ptr [r14+910h], 1
0x18001c9e9  mov     rcx, r13; hRequest
0x18001c9ec  call    DavParseXmlResponse
0x18001c9f1  mov     ebx, eax
0x18001c9f3  test    eax, eax
0x18001c9f5  jnz     short loc_18001CA17
0x18001c9f7  mov     ecx, [rbp+0E0h+var_130]
0x18001c9fa  xor     edx, edx
0x18001c9fc  mov     [r14+914h], ecx
0x18001ca03  mov     rax, [r14+1F8h]
0x18001ca0a  mov     [rax+3Ch], ecx
0x18001ca0d  lea     rcx, [rsp+1E0h+hMem]; hMem
0x18001ca12  call    DavFinalizeFileAttributesList
0x18001ca17  test    r15, r15
0x18001ca1a  jz      short loc_18001CA25
0x18001ca1c  mov     rcx, r15; hMem
0x18001ca1f  call    cs:__imp_LocalFree
0x18001ca25  test    r12, r12
0x18001ca28  jz      short loc_18001CA33
0x18001ca2a  mov     rcx, r12; hMem
0x18001ca2d  call    cs:__imp_LocalFree
0x18001ca33  mov     eax, ebx
0x18001ca35  mov     rcx, [rbp+0E0h+var_30]
0x18001ca3c  xor     rcx, rsp; StackCookie
0x18001ca3f  call    __security_check_cookie
0x18001ca44  lea     r11, [rsp+1E0h+var_20]
0x18001ca4c  mov     rbx, [r11+38h]
0x18001ca50  mov     rdi, [r11+40h]
0x18001ca54  mov     rsp, r11
0x18001ca57  pop     r15
0x18001ca59  pop     r14
0x18001ca5b  pop     r13
0x18001ca5d  pop     r12
0x18001ca5f  pop     rbp
0x18001ca60  retn
```
