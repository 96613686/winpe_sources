# CSsdpSearchRequest::HrGetCacheResult(int,ulong *)

- ea: `0x180016950`
- end: `0x180016d82`
- name: `?HrGetCacheResult@CSsdpSearchRequest@@QEAAJHPEAK@Z`
- size: `1074`
- prototype: `__int64 __fastcall(CSsdpSearchRequest *__hidden this, int, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180014b40`
- `0x180015168`

## callees

- `0x18000683c`
- `0x180008190`
- `0x18000b630`
- `0x180016950`
- `0x180016d90`
- `0x180016e2c`
- `0x1800174b0`
- `0x1800271fc`
- `0x180029df0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016aba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016b53`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016b67`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016cb4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016aba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016b53`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016b67`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016cb4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800169f1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800169f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016b7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016b7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016acd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016acd`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800169d3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180016a48`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800169d3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180016a48`

## pseudocode

```c
__int64 __fastcall CSsdpSearchRequest::HrGetCacheResult(CSsdpSearchRequest *this, int a2, unsigned int *a3)
{
  const WCHAR *v3; // r8
  unsigned int v4; // ebp
  HashFn *v6; // r15
  __int64 v7; // rax
  int cbMultiByte; // edi
  CHAR *lpMultiByteStr; // rbx
  int v10; // esi
  LPCSTR v11; // rcx
  unsigned int v12; // r8d
  _QWORD *v13; // rdi
  int i; // esi
  int v15; // eax
  int j; // esi
  void *v17; // rcx
  unsigned int Win32Error; // eax
  struct _GUID v20; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v21; // [rsp+A0h] [rbp+8h]
  void *Block; // [rsp+B8h] [rbp+20h] BYREF

  v3 = (const WCHAR *)*((_QWORD *)this + 1);
  v4 = 0;
  v6 = 0;
  Block = 0;
  v21 = 0;
  if ( !v3 )
    goto LABEL_32;
  v7 = -1;
  do
    ++v7;
  while ( v3[v7] );
  if ( v7 )
    cbMultiByte = WideCharToMultiByte(0, 0x400u, v3, -1, 0, 0, 0, 0);
  else
LABEL_32:
    cbMultiByte = 1;
  lpMultiByteStr = (CHAR *)malloc(cbMultiByte);
  if ( !lpMultiByteStr )
  {
    v11 = WPP_GLOBAL_Control;
    v4 = -2147024882;
    goto LABEL_33;
  }
  v10 = 0;
  if ( !CUString::GetLength((CSsdpSearchRequest *)((char *)this + 8)) )
  {
    *lpMultiByteStr = 0;
    v11 = WPP_GLOBAL_Control;
LABEL_11:
    v6 = (HashFn *)lpMultiByteStr;
    if ( !v10 )
      goto LABEL_12;
    goto LABEL_33;
  }
  if ( !WideCharToMultiByte(0, 0x400u, *((LPCWCH *)this + 1), -1, lpMultiByteStr, cbMultiByte, 0, 0) )
  {
    Win32Error = HrFromLastWin32Error();
    v10 = Win32Error;
    if ( Win32Error )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_10;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids, Win32Error);
    }
  }
  v11 = WPP_GLOBAL_Control;
LABEL_10:
  v4 = v10;
  if ( v10 >= 0 )
    goto LABEL_11;
  free(lpMultiByteStr);
  v11 = WPP_GLOBAL_Control;
LABEL_33:
  if ( v11 != (LPCSTR)&WPP_GLOBAL_Control && (v11[28] & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v11 + 2), 15, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids, v4);
    v11 = WPP_GLOBAL_Control;
  }
LABEL_12:
  if ( (v4 & 0x80000000) == 0 )
  {
    v12 = *((_DWORD *)this + 69);
    v20 = *(struct _GUID *)((char *)this + 280);
    v4 = CSsdpCacheEntryManager::HrSearchListCache(
           &CSsdpCacheEntryManager::s_instance,
           v6,
           v12,
           &v20,
           (struct _MessageList **)&Block);
    free(v6);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    v13 = Block;
    if ( Block )
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids,
          *(unsigned int *)Block);
      for ( i = 0; i < *(_DWORD *)v13; ++i )
      {
        if ( !a2
          || !(unsigned int)CSsdpSearchRequest::FIsInResponseMessageList(
                              this,
                              *(const char **)(*(_QWORD *)(88LL * i + v13[1] + 80) + 64LL)) )
        {
          v15 = CSsdpSearchRequest::HrAddRequestToResponseMessageList(
                  this,
                  (const struct _SSDP_REQUEST *)(v13[1] + 88LL * i));
          v4 = v15;
          if ( v15 )
          {
            if ( v15 == -2147467260 )
            {
              if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids);
              v4 = 0;
            }
            break;
          }
          ++v21;
        }
      }
      for ( j = 0; j < *(_DWORD *)v13; ++j )
        FreeSsdpRequest((struct _SSDP_REQUEST *)(v13[1] + 88LL * j));
      v17 = (void *)v13[1];
      if ( v17 )
        free(v17);
      if ( v13 )
        free(v13);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
    v11 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    *a3 = v21;
    v11 = WPP_GLOBAL_Control;
  }
  if ( v4 && v11 != (LPCSTR)&WPP_GLOBAL_Control && (v11[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v11 + 2), 16, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180016950  mov     rax, rsp
0x180016953  mov     [rax+18h], r8
0x180016957  mov     [rax+10h], edx
0x18001695a  push    rbp
0x18001695b  sub     rsp, 90h
0x180016962  mov     r8, [rcx+8]; lpWideCharStr
0x180016966  xor     ebp, ebp
0x180016968  mov     [rax-10h], rbx
0x18001696c  mov     [rax-20h], rdi
0x180016970  mov     [rax-30h], r13
0x180016974  mov     r13, rcx
0x180016977  mov     [rax-38h], r14
0x18001697b  mov     [rax-40h], r15
0x18001697f  mov     r15d, ebp
0x180016982  mov     [rax+20h], rbp
0x180016986  mov     [rsp+98h+arg_0], ebp
0x18001698d  test    r8, r8
0x180016990  jz      loc_180016BDB
0x180016996  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001699d  nop     dword ptr [rax]
0x1800169a0  inc     rax
0x1800169a3  cmp     [r8+rax*2], bp
0x1800169a8  jnz     short loc_1800169A0
0x1800169aa  test    rax, rax
0x1800169ad  jz      loc_180016BDB
0x1800169b3  mov     [rsp+98h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x1800169b8  mov     edx, 400h; dwFlags
0x1800169bd  mov     [rsp+98h+lpDefaultChar], rbp; lpDefaultChar
0x1800169c2  xor     ecx, ecx; CodePage
0x1800169c4  mov     [rsp+98h+cbMultiByte], ebp; cbMultiByte
0x1800169c8  mov     r9d, 0FFFFFFFFh; cchWideChar
0x1800169ce  mov     [rsp+98h+lpMultiByteStr], rbp; lpMultiByteStr
0x1800169d3  call    cs:__imp_WideCharToMultiByte
0x1800169da  nop     dword ptr [rax+rax+00h]
0x1800169df  mov     edi, eax
0x1800169e1  mov     [rsp+98h+var_18], rsi
0x1800169e9  movsxd  rcx, edi; Size
0x1800169ec  mov     [rsp+98h+var_28], r12
0x1800169f1  call    cs:__imp_malloc
0x1800169f8  nop     dword ptr [rax+rax+00h]
0x1800169fd  mov     rbx, rax
0x180016a00  test    rax, rax
0x180016a03  jz      loc_180016C99
0x180016a09  lea     rcx, [r13+8]; this
0x180016a0d  mov     esi, ebp
0x180016a0f  call    ?GetLength@CUString@@QEBA_KXZ; CUString::GetLength(void)
0x180016a14  lea     r12, WPP_GLOBAL_Control
0x180016a1b  test    rax, rax
0x180016a1e  jz      loc_180016C1C
0x180016a24  mov     r8, [r13+8]; lpWideCharStr
0x180016a28  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180016a2e  mov     [rsp+98h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x180016a33  mov     edx, 400h; dwFlags
0x180016a38  mov     [rsp+98h+lpDefaultChar], rbp; lpDefaultChar
0x180016a3d  xor     ecx, ecx; CodePage
0x180016a3f  mov     [rsp+98h+cbMultiByte], edi; cbMultiByte
0x180016a43  mov     [rsp+98h+lpMultiByteStr], rbx; lpMultiByteStr
0x180016a48  call    cs:__imp_WideCharToMultiByte
0x180016a4f  nop     dword ptr [rax+rax+00h]
0x180016a54  test    eax, eax
0x180016a56  jz      loc_180016C53
0x180016a5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a63  mov     ebp, esi
0x180016a65  test    esi, esi
0x180016a67  js      loc_180016CB1
0x180016a6d  mov     r15, rbx
0x180016a70  test    esi, esi
0x180016a72  jnz     loc_180016BE5
0x180016a78  test    ebp, ebp
0x180016a7a  js      loc_180016B8D
0x180016a80  movups  xmm0, xmmword ptr [r13+118h]
0x180016a88  mov     r8d, [r13+114h]; unsigned int
0x180016a8f  lea     rax, [rsp+98h+Block]
0x180016a97  lea     r9, [rsp+98h+var_58]; struct _GUID
0x180016a9c  mov     [rsp+98h+lpMultiByteStr], rax; struct _MessageList **
0x180016aa1  mov     rdx, r15; char *
0x180016aa4  movaps  xmmword ptr [rsp+98h+var_58.Data1], xmm0
0x180016aa9  lea     rcx, ?s_instance@CSsdpCacheEntryManager@@0V1@A; this
0x180016ab0  call    ?HrSearchListCache@CSsdpCacheEntryManager@@QEAAJPEADKU_GUID@@PEAPEAU_MessageList@@@Z; CSsdpCacheEntryManager::HrSearchListCache(char *,ulong,_GUID,_MessageList * *)
0x180016ab5  mov     rcx, r15; Block
0x180016ab8  mov     ebp, eax
0x180016aba  call    cs:__imp_free
0x180016ac1  nop     dword ptr [rax+rax+00h]
0x180016ac6  lea     rcx, [r13+98h]; lpCriticalSection
0x180016acd  call    cs:__imp_EnterCriticalSection
0x180016ad4  nop     dword ptr [rax+rax+00h]
0x180016ad9  mov     rdi, [rsp+98h+Block]
0x180016ae1  test    rdi, rdi
0x180016ae4  jz      loc_180016B73
0x180016aea  mov     rcx, cs:WPP_GLOBAL_Control
0x180016af1  cmp     rcx, r12
0x180016af4  jz      short loc_180016B00
0x180016af6  test    byte ptr [rcx+1Ch], 8
0x180016afa  jnz     loc_180016CCC
0x180016b00  mov     r15d, [rsp+98h+arg_8]
0x180016b08  xor     esi, esi
0x180016b0a  cmp     esi, [rdi]
0x180016b0c  jge     short loc_180016B40
0x180016b0e  movsxd  r14, esi
0x180016b11  test    r15d, r15d
0x180016b14  jnz     loc_180016C2B
0x180016b1a  imul    rdx, r14, 58h ; 'X'
0x180016b1e  mov     rcx, r13; this
0x180016b21  add     rdx, [rdi+8]; struct _SSDP_REQUEST *
0x180016b25  call    ?HrAddRequestToResponseMessageList@CSsdpSearchRequest@@QEAAJPEBU_SSDP_REQUEST@@@Z; CSsdpSearchRequest::HrAddRequestToResponseMessageList(_SSDP_REQUEST const *)
0x180016b2a  mov     ebp, eax
0x180016b2c  test    eax, eax
0x180016b2e  jnz     loc_180016CE9
0x180016b34  inc     [rsp+98h+arg_0]
0x180016b3b  jmp     loc_180016C4C
0x180016b40  xor     esi, esi
0x180016b42  cmp     [rdi], esi
0x180016b44  jg      loc_180016D22
0x180016b4a  mov     rcx, [rdi+8]; Block
0x180016b4e  test    rcx, rcx
0x180016b51  jz      short loc_180016B5F
0x180016b53  call    cs:__imp_free
0x180016b5a  nop     dword ptr [rax+rax+00h]
0x180016b5f  test    rdi, rdi
0x180016b62  jz      short loc_180016B73
0x180016b64  mov     rcx, rdi; Block
0x180016b67  call    cs:__imp_free
0x180016b6e  nop     dword ptr [rax+rax+00h]
0x180016b73  lea     rcx, [r13+98h]; lpCriticalSection
0x180016b7a  call    cs:__imp_LeaveCriticalSection
0x180016b81  nop     dword ptr [rax+rax+00h]
0x180016b86  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b8d  mov     rax, [rsp+98h+arg_10]
0x180016b95  mov     r15, [rsp+98h+var_40]
0x180016b9a  mov     r14, [rsp+98h+var_38]
0x180016b9f  mov     r13, [rsp+98h+var_30]
0x180016ba4  mov     rdi, [rsp+98h+var_20]
0x180016ba9  mov     rsi, [rsp+98h+var_18]
0x180016bb1  mov     rbx, [rsp+98h+var_10]
0x180016bb9  test    rax, rax
0x180016bbc  jnz     loc_180016D3D
0x180016bc2  test    ebp, ebp
0x180016bc4  jnz     loc_180016D52
0x180016bca  mov     r12, [rsp+98h+var_28]
0x180016bcf  mov     eax, ebp
0x180016bd1  add     rsp, 90h
0x180016bd8  pop     rbp
0x180016bd9  retn
0x180016bdb  mov     edi, 1
0x180016be0  jmp     loc_1800169E1
0x180016be5  cmp     rcx, r12
0x180016be8  jz      loc_180016A78
0x180016bee  test    byte ptr [rcx+1Ch], 1
0x180016bf2  jz      loc_180016A78
0x180016bf8  mov     rcx, [rcx+10h]
0x180016bfc  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x180016c03  mov     edx, 0Fh
0x180016c08  mov     r9d, ebp
0x180016c0b  call    WPP_SF_d
0x180016c10  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c17  jmp     loc_180016A78
0x180016c1c  mov     [rbx], sil
0x180016c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c26  jmp     loc_180016A6D
0x180016c2b  mov     rax, [rdi+8]
0x180016c2f  mov     rcx, r13; this
0x180016c32  imul    rdx, r14, 58h ; 'X'
0x180016c36  mov     rdx, [rdx+rax+50h]
0x180016c3b  mov     rdx, [rdx+40h]; char *
0x180016c3f  call    ?FIsInResponseMessageList@CSsdpSearchRequest@@QEAAHPEBD@Z; CSsdpSearchRequest::FIsInResponseMessageList(char const *)
0x180016c44  test    eax, eax
0x180016c46  jz      loc_180016B1A
0x180016c4c  inc     esi
0x180016c4e  jmp     loc_180016B0A
0x180016c53  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180016c58  mov     esi, eax
0x180016c5a  test    eax, eax
0x180016c5c  jz      loc_180016A5C
0x180016c62  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c69  cmp     rcx, r12
0x180016c6c  jz      loc_180016A63
0x180016c72  test    byte ptr [rcx+1Ch], 1
0x180016c76  jz      loc_180016A63
0x180016c7c  mov     rcx, [rcx+10h]
0x180016c80  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x180016c87  mov     edx, 0Eh
0x180016c8c  mov     r9d, eax
0x180016c8f  call    WPP_SF_d
0x180016c94  jmp     loc_180016A5C
0x180016c99  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ca0  lea     r12, WPP_GLOBAL_Control
0x180016ca7  mov     ebp, 8007000Eh
0x180016cac  jmp     loc_180016BE5
0x180016cb1  mov     rcx, rbx; Block
0x180016cb4  call    cs:__imp_free
0x180016cbb  nop     dword ptr [rax+rax+00h]
0x180016cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cc7  jmp     loc_180016BE5
0x180016ccc  mov     r9d, [rdi]
0x180016ccf  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x180016cd6  mov     rcx, [rcx+10h]
0x180016cda  mov     edx, 0Eh
0x180016cdf  call    WPP_SF_d
0x180016ce4  jmp     loc_180016B00
0x180016ce9  cmp     eax, 80004004h
0x180016cee  jnz     loc_180016B40
0x180016cf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cfb  cmp     rcx, r12
0x180016cfe  jz      short loc_180016D1B
0x180016d00  test    byte ptr [rcx+1Ch], 8
0x180016d04  jz      short loc_180016D1B
0x180016d06  mov     rcx, [rcx+10h]
0x180016d0a  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x180016d11  mov     edx, 0Fh
0x180016d16  call    WPP_SF_
0x180016d1b  xor     ebp, ebp
0x180016d1d  jmp     loc_180016B40
0x180016d22  movsxd  rax, esi
0x180016d25  imul    rcx, rax, 58h ; 'X'
0x180016d29  add     rcx, [rdi+8]; struct _SSDP_REQUEST *
0x180016d2d  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x180016d32  inc     esi
0x180016d34  cmp     esi, [rdi]
0x180016d36  jl      short loc_180016D22
0x180016d38  jmp     loc_180016B4A
0x180016d3d  mov     ecx, [rsp+98h+arg_0]
0x180016d44  mov     [rax], ecx
0x180016d46  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d4d  jmp     loc_180016BC2
0x180016d52  cmp     rcx, r12
0x180016d55  jz      loc_180016BCA
0x180016d5b  test    byte ptr [rcx+1Ch], 1
0x180016d5f  jz      loc_180016BCA
0x180016d65  mov     rcx, [rcx+10h]
0x180016d69  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x180016d70  mov     edx, 10h
0x180016d75  mov     r9d, ebp
0x180016d78  call    WPP_SF_d
0x180016d7d  jmp     loc_180016BCA
```
