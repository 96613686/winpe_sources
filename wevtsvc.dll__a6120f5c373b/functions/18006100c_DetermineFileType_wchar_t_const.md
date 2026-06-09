# DetermineFileType(wchar_t const *)

- ea: `0x18006100c`
- end: `0x1800613d1`
- name: `?DetermineFileType@@YA?AW4FileType@@PEB_W@Z`
- size: `965`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800762f8`

## callees

- `0x18003420c`
- `0x18006100c`
- `0x1800613d8`
- `0x180092008`
- `0x18009aee0`
- `0x18009bb88`
- `0x1800d334c`
- `0x1800d3364`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006122d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006134f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006122d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006134f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061184`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061184`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180061149`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180061149`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061102`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061102`
- `RPCRT4!RpcImpersonateClient` at `0x18006103f`
- `RPCRT4!RpcImpersonateClient` at `0x18006103f`
- `RPCRT4!RpcRevertToSelf` at `0x18006118b`
- `RPCRT4!RpcRevertToSelf` at `0x18006133f`
- `RPCRT4!RpcRevertToSelf` at `0x18006118b`
- `RPCRT4!RpcRevertToSelf` at `0x18006133f`

## pseudocode

```c
__int64 __fastcall DetermineFileType(const wchar_t *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // ebx
  HANDLE FileW; // rdi
  DWORD LastError; // ebx
  DWORD v8; // ebx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  __int128 pExceptionObject; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v11; // [rsp+58h] [rbp-A8h]
  int v12; // [rsp+60h] [rbp-A0h]
  __int64 v13; // [rsp+64h] [rbp-9Ch]
  char v14; // [rsp+6Ch] [rbp-94h]
  char v15; // [rsp+71h] [rbp-8Fh]
  HANDLE v16; // [rsp+78h] [rbp-88h] BYREF
  unsigned int Buffer; // [rsp+80h] [rbp-80h] BYREF
  _BYTE Buf1[44]; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v19; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v20; // [rsp+B6h] [rbp-4Ah]
  int v21; // [rsp+C8h] [rbp-38h]

  v2 = RpcImpersonateClient(0);
  v3 = v2;
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2fa61b8b88573da6696e81491dd53375_Traceguids, v2);
    }
    *(_QWORD *)&pExceptionObject = &byte_1800EC961;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v11 = 0;
    v12 = v3;
    v13 = -1;
    v14 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v4 = 1;
  v15 = 1;
  if ( !FileExists(a1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_2fa61b8b88573da6696e81491dd53375_Traceguids, 2);
    }
    pExceptionObject = 0;
    v11 = 0;
    v12 = 2;
    v13 = 0x77FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  FileW = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x10000000u, 0);
  v16 = FileW;
  if ( (unsigned __int64)FileW + 1 <= 1 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2fa61b8b88573da6696e81491dd53375_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v11 = 0;
    v12 = LastError;
    v13 = 0x85FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  NumberOfBytesRead = 0;
  memset_0(&Buffer, 0, 0x180u);
  if ( !ReadFile(FileW, &Buffer, 0x180u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 384 )
  {
    v8 = GetLastError();
    if ( !v8 )
      v8 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_2fa61b8b88573da6696e81491dd53375_Traceguids, v8);
    }
    pExceptionObject = 0;
    v11 = 0;
    v12 = v8;
    v13 = 0x93FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !strcmp((const char *)&Buffer, "ElfFile") )
  {
    CloseHandle(FileW);
LABEL_13:
    RpcRevertToSelf();
    return v4;
  }
  if ( !memcmp_0(&Buffer, byte_1800F2188, 4u) && !memcmp_0(Buf1, &dword_1800F218C, 4u) )
  {
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v16);
    v4 = 0;
    goto LABEL_13;
  }
  if ( ((v21 + 1073676286) & 0xFFFEFFFF) == 0 && v19 <= Buffer && v20 <= 8u )
  {
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v16);
    v4 = 2;
    goto LABEL_13;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v16);
  RpcRevertToSelf();
  return 3;
}

```

## disassembly

```asm
0x18006100c  mov     [rsp-8+arg_8], rbx
0x180061011  mov     [rsp-8+arg_10], rsi
0x180061016  push    rbp
0x180061017  push    rdi
0x180061018  push    r14
0x18006101a  lea     rbp, [rsp-110h]
0x180061022  sub     rsp, 210h
0x180061029  mov     rax, cs:__security_cookie
0x180061030  xor     rax, rsp
0x180061033  mov     [rbp+120h+var_20], rax
0x18006103a  mov     rdi, rcx
0x18006103d  xor     ecx, ecx; BindingHandle
0x18006103f  call    cs:__imp_RpcImpersonateClient
0x180061045  mov     ebx, eax
0x180061047  xor     esi, esi
0x180061049  test    eax, eax
0x18006104b  jz      short loc_1800610C5
0x18006104d  lea     rcx, WPP_GLOBAL_Control
0x180061054  mov     r10, cs:WPP_GLOBAL_Control
0x18006105b  cmp     r10, rcx
0x18006105e  jz      short loc_180061071
0x180061060  test    dword ptr [r10+1Ch], 200h
0x180061068  jz      short loc_180061071
0x18006106a  cmp     byte ptr [r10+19h], 2
0x18006106f  jnb     short loc_1800610AB
0x180061071  lea     rax, byte_1800EC961
0x180061078  mov     qword ptr [rsp+220h+pExceptionObject], rax
0x18006107d  mov     qword ptr [rsp+220h+pExceptionObject+8], rsi
0x180061082  mov     [rsp+220h+var_1C8], rsi
0x180061087  mov     [rsp+220h+var_1C0], ebx
0x18006108b  mov     [rsp+220h+var_1BC], 0FFFFFFFFFFFFFFFFh
0x180061094  mov     [rsp+220h+var_1B4], sil
0x180061099  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800610a0  lea     rcx, [rsp+220h+pExceptionObject]; pExceptionObject
0x1800610a5  call    _CxxThrowException_0
0x1800610ab  mov     edx, 0Ah
0x1800610b0  mov     r9d, ebx
0x1800610b3  lea     r8, WPP_2fa61b8b88573da6696e81491dd53375_Traceguids
0x1800610ba  mov     rcx, [r10+10h]
0x1800610be  call    WPP_SF_d
0x1800610c3  jmp     short loc_180061071
0x1800610c5  mov     ebx, 1
0x1800610ca  mov     [rsp+220h+var_1AF], bl
0x1800610ce  mov     rcx, rdi; wchar_t *
0x1800610d1  call    ?FileExists@@YA_NPEB_W@Z; FileExists(wchar_t const *)
0x1800610d6  test    al, al
0x1800610d8  jz      loc_1800611BA
0x1800610de  mov     [rsp+220h+hTemplateFile], rsi; hTemplateFile
0x1800610e3  mov     [rsp+220h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x1800610eb  mov     [rsp+220h+dwCreationDisposition], 3; dwCreationDisposition
0x1800610f3  xor     r9d, r9d; lpSecurityAttributes
0x1800610f6  mov     edx, 80000000h; dwDesiredAccess
0x1800610fb  lea     r8d, [rbx+6]; dwShareMode
0x1800610ff  mov     rcx, rdi; lpFileName
0x180061102  call    cs:__imp_CreateFileW
0x180061108  mov     rdi, rax
0x18006110b  mov     [rsp+220h+var_1A8], rax
0x180061110  lea     rcx, [rax+1]
0x180061114  cmp     rcx, rbx
0x180061117  jbe     loc_18006122D
0x18006111d  mov     [rsp+220h+NumberOfBytesRead], esi
0x180061121  mov     r14d, 180h
0x180061127  mov     r8d, r14d; Size
0x18006112a  xor     edx, edx; Val
0x18006112c  lea     rcx, [rbp+120h+Buffer]; void *
0x180061130  call    memset_0
0x180061135  mov     qword ptr [rsp+220h+dwCreationDisposition], rsi; lpOverlapped
0x18006113a  lea     r9, [rsp+220h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18006113f  mov     r8d, r14d; nNumberOfBytesToRead
0x180061142  lea     rdx, [rbp+120h+Buffer]; lpBuffer
0x180061146  mov     rcx, rdi; hFile
0x180061149  call    cs:__imp_ReadFile
0x18006114f  test    eax, eax
0x180061151  jz      loc_18006134F
0x180061157  cmp     [rsp+220h+NumberOfBytesRead], r14d
0x18006115c  jnz     loc_18006134F
0x180061162  lea     r14d, [rbx+7]
0x180061166  mov     r8d, r14d; Size
0x180061169  lea     rdx, aElffile; "ElfFile"
0x180061170  lea     rcx, [rbp+120h+Buffer]; Buf1
0x180061174  call    memcmp_0
0x180061179  test    eax, eax
0x18006117b  jnz     loc_1800612AF
0x180061181  mov     rcx, rdi; hObject
0x180061184  call    cs:__imp_CloseHandle
0x18006118a  nop
0x18006118b  call    cs:__imp_RpcRevertToSelf
0x180061191  mov     eax, ebx
0x180061193  mov     rcx, [rbp+120h+var_20]
0x18006119a  xor     rcx, rsp; StackCookie
0x18006119d  call    __security_check_cookie
0x1800611a2  lea     r11, [rsp+220h+var_10]
0x1800611aa  mov     rbx, [r11+28h]
0x1800611ae  mov     rsi, [r11+30h]
0x1800611b2  mov     rsp, r11
0x1800611b5  pop     r14
0x1800611b7  pop     rdi
0x1800611b8  pop     rbp
0x1800611b9  retn
0x1800611ba  lea     rcx, WPP_GLOBAL_Control
0x1800611c1  mov     rax, cs:WPP_GLOBAL_Control
0x1800611c8  cmp     rax, rcx
0x1800611cb  jz      short loc_1800611F5
0x1800611cd  test    dword ptr [rax+1Ch], 200h
0x1800611d4  jz      short loc_1800611F5
0x1800611d6  cmp     byte ptr [rax+19h], 2
0x1800611da  jb      short loc_1800611F5
0x1800611dc  mov     edx, 0Bh
0x1800611e1  lea     r9d, [rdx-9]
0x1800611e5  lea     r8, WPP_2fa61b8b88573da6696e81491dd53375_Traceguids
0x1800611ec  mov     rcx, [rax+10h]
0x1800611f0  call    WPP_SF_d
0x1800611f5  xorps   xmm0, xmm0
0x1800611f8  movdqu  [rsp+220h+pExceptionObject], xmm0
0x1800611fe  mov     [rsp+220h+var_1C8], rsi
0x180061203  mov     [rsp+220h+var_1C0], 2
0x18006120b  mov     dword ptr [rsp+220h+var_1BC], 0FFFFFFFFh
0x180061213  mov     dword ptr [rsp+220h+var_1BC+4], 77h ; 'w'
0x18006121b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180061222  lea     rcx, [rsp+220h+pExceptionObject]; pExceptionObject
0x180061227  call    _CxxThrowException_0
0x18006122d  call    cs:__imp_GetLastError
0x180061233  mov     ebx, eax
0x180061235  mov     eax, 507h
0x18006123a  test    ebx, ebx
0x18006123c  cmovz   ebx, eax
0x18006123f  lea     rcx, WPP_GLOBAL_Control
0x180061246  mov     r10, cs:WPP_GLOBAL_Control
0x18006124d  cmp     r10, rcx
0x180061250  jz      short loc_18006127B
0x180061252  test    dword ptr [r10+1Ch], 200h
0x18006125a  jz      short loc_18006127B
0x18006125c  cmp     byte ptr [r10+19h], 2
0x180061261  jb      short loc_18006127B
0x180061263  mov     edx, 0Ch
0x180061268  mov     r9d, ebx
0x18006126b  lea     r8, WPP_2fa61b8b88573da6696e81491dd53375_Traceguids
0x180061272  mov     rcx, [r10+10h]
0x180061276  call    WPP_SF_d
0x18006127b  xorps   xmm0, xmm0
0x18006127e  movdqu  [rsp+220h+pExceptionObject], xmm0
0x180061284  mov     [rsp+220h+var_1C8], rsi
0x180061289  mov     [rsp+220h+var_1C0], ebx
0x18006128d  mov     dword ptr [rsp+220h+var_1BC], 0FFFFFFFFh
0x180061295  mov     dword ptr [rsp+220h+var_1BC+4], 85h
0x18006129d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800612a4  lea     rcx, [rsp+220h+pExceptionObject]; pExceptionObject
0x1800612a9  call    _CxxThrowException_0
0x1800612af  mov     ebx, 4
0x1800612b4  mov     r8d, ebx; Size
0x1800612b7  lea     rdx, byte_1800F2188; Buf2
0x1800612be  lea     rcx, [rbp+120h+Buffer]; Buf1
0x1800612c2  call    memcmp_0
0x1800612c7  test    eax, eax
0x1800612c9  jnz     short loc_1800612F3
0x1800612cb  mov     r8d, ebx; Size
0x1800612ce  lea     rdx, dword_1800F218C; Buf2
0x1800612d5  lea     rcx, [rbp+120h+Buf1]; Buf1
0x1800612d9  call    memcmp_0
0x1800612de  test    eax, eax
0x1800612e0  jnz     short loc_1800612F3
0x1800612e2  lea     rcx, [rsp+220h+var_1A8]
0x1800612e7  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800612ec  mov     ebx, esi
0x1800612ee  jmp     loc_18006118B
0x1800612f3  mov     eax, [rbp+120h+var_158]
0x1800612f6  add     eax, 3FFEFFFEh
0x1800612fb  test    eax, 0FFFEFFFFh
0x180061300  setz    cl
0x180061303  mov     eax, [rbp+120h+Buffer]
0x180061306  cmp     [rbp+120h+var_170], eax
0x180061309  setbe   dl
0x18006130c  cmp     [rbp+120h+var_16A], r14w
0x180061311  setbe   al
0x180061314  test    cl, cl
0x180061316  jz      short loc_180061334
0x180061318  test    dl, dl
0x18006131a  jz      short loc_180061334
0x18006131c  test    al, al
0x18006131e  jz      short loc_180061334
0x180061320  lea     rcx, [rsp+220h+var_1A8]
0x180061325  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18006132a  mov     ebx, 2
0x18006132f  jmp     loc_18006118B
0x180061334  lea     rcx, [rsp+220h+var_1A8]
0x180061339  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18006133e  nop
0x18006133f  call    cs:__imp_RpcRevertToSelf
0x180061345  mov     eax, 3
0x18006134a  jmp     loc_180061193
0x18006134f  call    cs:__imp_GetLastError
0x180061355  mov     ebx, eax
0x180061357  mov     eax, 507h
0x18006135c  test    ebx, ebx
0x18006135e  cmovz   ebx, eax
0x180061361  lea     rcx, WPP_GLOBAL_Control
0x180061368  mov     r10, cs:WPP_GLOBAL_Control
0x18006136f  cmp     r10, rcx
0x180061372  jz      short loc_18006139D
0x180061374  test    dword ptr [r10+1Ch], 200h
0x18006137c  jz      short loc_18006139D
0x18006137e  cmp     byte ptr [r10+19h], 2
0x180061383  jb      short loc_18006139D
0x180061385  mov     edx, 0Dh
0x18006138a  mov     r9d, ebx
0x18006138d  lea     r8, WPP_2fa61b8b88573da6696e81491dd53375_Traceguids
0x180061394  mov     rcx, [r10+10h]
0x180061398  call    WPP_SF_d
0x18006139d  xorps   xmm0, xmm0
0x1800613a0  movdqu  [rsp+220h+pExceptionObject], xmm0
0x1800613a6  mov     [rsp+220h+var_1C8], rsi
0x1800613ab  mov     [rsp+220h+var_1C0], ebx
0x1800613af  mov     dword ptr [rsp+220h+var_1BC], 0FFFFFFFFh
0x1800613b7  mov     dword ptr [rsp+220h+var_1BC+4], 93h
0x1800613bf  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800613c6  lea     rcx, [rsp+220h+pExceptionObject]; pExceptionObject
0x1800613cb  call    _CxxThrowException_0
```
