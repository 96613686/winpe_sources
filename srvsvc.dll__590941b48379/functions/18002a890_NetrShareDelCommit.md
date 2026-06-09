# NetrShareDelCommit

- ea: `0x18002a890`
- end: `0x18002ab51`
- name: `NetrShareDelCommit`
- size: `705`
- prototype: `__int64 __fastcall(_QWORD **)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002a340`
- `0x18002a860`
- `0x18002ab60`
- `0x18002ae40`

## callees

- `0x18000b9a0`
- `0x18001deb0`
- `0x180021140`
- `0x180021288`
- `0x180026150`
- `0x18002a890`
- `0x18002bb14`
- `0x18002bb88`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ab1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ab1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a986`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aa45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a986`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aa45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a8d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a8d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a917`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a917`
- `RPCRT4!RpcImpersonateClient` at `0x18002aa78`
- `RPCRT4!RpcImpersonateClient` at `0x18002aaa1`
- `RPCRT4!RpcImpersonateClient` at `0x18002aa78`
- `RPCRT4!RpcImpersonateClient` at `0x18002aaa1`
- `RPCRT4!RpcRevertToSelf` at `0x18002aac4`
- `RPCRT4!RpcRevertToSelf` at `0x18002aac4`

## string_xrefs

- `0x18002a99b`: `NetrShareDelCommit`
- `0x18002a9f6`: `NetrShareDelCommit`
- `0x18002aa5a`: `NetrShareDelCommit`

## pseudocode

```c
__int64 __fastcall NetrShareDelCommit(_QWORD **a1)
{
  _QWORD *v1; // rdi
  _QWORD *v2; // rbx
  _QWORD **v3; // rdx
  unsigned int v4; // esi
  __int64 v5; // rbx
  char CurrentThreadId; // al
  int v7; // r8d
  __int64 v8; // rcx
  __int128 v9; // xmm1
  unsigned int v10; // eax
  _QWORD *v11; // rbx
  __int64 v12; // rbx
  char v13; // al
  int v14; // r8d
  RPC_STATUS v15; // ebx
  unsigned int v16; // eax
  __int128 v18; // [rsp+30h] [rbp-F8h] BYREF
  __int128 v19; // [rsp+40h] [rbp-E8h] BYREF
  wchar_t pszDest[88]; // [rsp+50h] [rbp-D8h] BYREF

  if ( !a1 )
    return 87;
  v1 = *a1;
  if ( !*a1 )
    return 87;
  *a1 = 0;
  EnterCriticalSection(&ShareDelContextMutex);
  v2 = SrvShareDelContextHead;
  if ( SrvShareDelContextHead == v1 )
  {
    SrvShareDelContextHead = *(HLOCAL *)SrvShareDelContextHead;
    *v1 = 0;
  }
  else
  {
    do
    {
      if ( !v2 )
      {
        v2 = 0;
        goto LABEL_8;
      }
      v3 = (_QWORD **)v2;
      v2 = (_QWORD *)*v2;
    }
    while ( v2 != v1 );
    v2 = v3;
    *v3 = (_QWORD *)**v3;
    *v1 = 0;
  }
LABEL_8:
  LeaveCriticalSection(&ShareDelContextMutex);
  if ( !v2 || StringCbCopyNW(pszDest, 0xA2u, (STRSAFE_PCNZWCH)v1[2], *((unsigned __int16 *)v1 + 4)) < 0 )
    return 87;
  v4 = 0;
  if ( *((_DWORD *)v1 + 28) && !*((_DWORD *)v1 + 27) && !*((_DWORD *)v1 + 26) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_sdS(v5, 29, v7, (unsigned int)"NetrShareDelCommit", CurrentThreadId, (__int64)pszDest);
    }
    v8 = *((unsigned int *)v1 + 29);
    v9 = *(_OWORD *)(v1 + 1);
    v18 = *(_OWORD *)(v1 + 3);
    v19 = v9;
    v10 = DeleteClusterFileShare(v8, &v19, &v18);
    v4 = v10;
    if ( v10 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_23;
      }
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (unsigned int)WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids,
        (unsigned int)"NetrShareDelCommit",
        v10);
    }
  }
  v11 = WPP_GLOBAL_Control;
LABEL_23:
  if ( !*((_DWORD *)v1 + 28) || *((_DWORD *)v1 + 27) || *((_DWORD *)v1 + 26) || v4 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 && *((_BYTE *)v11 + 25) >= 2u )
    {
      v12 = v11[2];
      v13 = GetCurrentThreadId();
      WPP_SF_sdS(v12, 31, v14, (unsigned int)"NetrShareDelCommit", v13, (__int64)pszDest);
    }
    if ( v1[16] )
    {
      v15 = RpcImpersonateClient(0);
      v16 = (*(__int64 (__fastcall **)(_QWORD, wchar_t *))(v1[16] + 64LL))(v1[4], pszDest);
    }
    else
    {
      v15 = RpcImpersonateClient(0);
      v16 = ((__int64 (__fastcall *)(_QWORD, wchar_t *))qword_18005E500)(v1[4], pszDest);
    }
    v4 = v16;
    if ( !v15 )
      RpcRevertToSelf();
    if ( !v4 && !*((_DWORD *)v1 + 27) )
    {
      SsRemoveShareFromRegistry((PCWSTR)v1 + 68);
      if ( *((_DWORD *)v1 + 30) )
      {
        if ( dword_18005CCF8 != 1 && !*((_DWORD *)v1 + 27) && !*((_DWORD *)v1 + 31) )
          _InterlockedDecrement(&UserShareCount);
      }
    }
    if ( *((_DWORD *)v1 + 26) )
    {
      _InterlockedDecrement(&dword_18005D048);
      SsSetExportedServerType(0, 0, 1);
    }
  }
  LocalFree(v1);
  return v4;
}

```

## disassembly

```asm
0x18002a890  mov     [rsp+arg_8], rbx
0x18002a895  mov     [rsp+arg_10], rbp
0x18002a89a  push    rsi
0x18002a89b  push    rdi
0x18002a89c  push    r15
0x18002a89e  sub     rsp, 110h
0x18002a8a5  mov     rax, cs:__security_cookie
0x18002a8ac  xor     rax, rsp
0x18002a8af  mov     [rsp+128h+var_28], rax
0x18002a8b7  xor     ebp, ebp
0x18002a8b9  test    rcx, rcx
0x18002a8bc  jz      loc_18002AB24
0x18002a8c2  mov     rdi, [rcx]
0x18002a8c5  test    rdi, rdi
0x18002a8c8  jz      loc_18002AB24
0x18002a8ce  mov     [rcx], rbp
0x18002a8d1  lea     rcx, ShareDelContextMutex; lpCriticalSection
0x18002a8d8  call    cs:__imp_EnterCriticalSection
0x18002a8de  mov     rbx, cs:SrvShareDelContextHead
0x18002a8e5  cmp     rbx, rdi
0x18002a8e8  jnz     short loc_18002A908
0x18002a8ea  mov     rax, [rbx]
0x18002a8ed  mov     cs:SrvShareDelContextHead, rax
0x18002a8f4  mov     [rdi], rbp
0x18002a8f7  jmp     short loc_18002A910
0x18002a8f9  mov     rdx, rbx
0x18002a8fc  mov     rbx, [rbx]
0x18002a8ff  cmp     rbx, rdi
0x18002a902  jz      loc_18002AA8D
0x18002a908  test    rbx, rbx
0x18002a90b  jnz     short loc_18002A8F9
0x18002a90d  mov     rbx, rbp
0x18002a910  lea     rcx, ShareDelContextMutex; lpCriticalSection
0x18002a917  call    cs:__imp_LeaveCriticalSection
0x18002a91d  test    rbx, rbx
0x18002a920  jz      loc_18002AB24
0x18002a926  movzx   r9d, word ptr [rdi+8]; cbToCopy
0x18002a92b  lea     rcx, [rsp+128h+pszDest]; pszDest
0x18002a930  mov     r8, [rdi+10h]; pszSrc
0x18002a934  mov     edx, 0A2h; cbDest
0x18002a939  call    StringCbCopyNW
0x18002a93e  test    eax, eax
0x18002a940  js      loc_18002AB24
0x18002a946  lea     r15, WPP_GLOBAL_Control
0x18002a94d  mov     esi, ebp
0x18002a94f  cmp     [rdi+70h], ebp
0x18002a952  jz      loc_18002AA12
0x18002a958  cmp     [rdi+6Ch], ebp
0x18002a95b  jnz     loc_18002AA12
0x18002a961  cmp     [rdi+68h], ebp
0x18002a964  jnz     loc_18002AA12
0x18002a96a  mov     rbx, cs:WPP_GLOBAL_Control
0x18002a971  cmp     rbx, r15
0x18002a974  jz      short loc_18002A9AE
0x18002a976  test    byte ptr [rbx+1Ch], 4
0x18002a97a  jz      short loc_18002A9AE
0x18002a97c  cmp     byte ptr [rbx+19h], 2
0x18002a980  jb      short loc_18002A9AE
0x18002a982  mov     rbx, [rbx+10h]
0x18002a986  call    cs:__imp_GetCurrentThreadId
0x18002a98c  lea     rcx, [rsp+128h+pszDest]
0x18002a991  mov     edx, 1Dh
0x18002a996  mov     [rsp+128h+var_100], rcx
0x18002a99b  lea     r9, aNetrsharedelco; "NetrShareDelCommit"
0x18002a9a2  mov     rcx, rbx
0x18002a9a5  mov     [rsp+128h+var_108], eax
0x18002a9a9  call    WPP_SF_sdS
0x18002a9ae  movups  xmm0, xmmword ptr [rdi+18h]
0x18002a9b2  mov     ecx, [rdi+74h]
0x18002a9b5  lea     r8, [rsp+128h+var_F8]
0x18002a9ba  movups  xmm1, xmmword ptr [rdi+8]
0x18002a9be  lea     rdx, [rsp+128h+var_E8]
0x18002a9c3  movdqu  [rsp+128h+var_F8], xmm0
0x18002a9c9  movdqu  [rsp+128h+var_E8], xmm1
0x18002a9cf  call    DeleteClusterFileShare
0x18002a9d4  mov     esi, eax
0x18002a9d6  test    eax, eax
0x18002a9d8  jz      short loc_18002AA12
0x18002a9da  mov     rbx, cs:WPP_GLOBAL_Control
0x18002a9e1  cmp     rbx, r15
0x18002a9e4  jz      short loc_18002AA19
0x18002a9e6  test    byte ptr [rbx+1Ch], 4
0x18002a9ea  jz      short loc_18002AA19
0x18002a9ec  cmp     byte ptr [rbx+19h], 1
0x18002a9f0  jb      short loc_18002AA19
0x18002a9f2  mov     rcx, [rbx+10h]
0x18002a9f6  lea     r9, aNetrsharedelco; "NetrShareDelCommit"
0x18002a9fd  mov     edx, 1Eh
0x18002aa02  mov     [rsp+128h+var_108], eax
0x18002aa06  lea     r8, WPP_cee36e08cc873b175cea1cc8b33051d6_Traceguids
0x18002aa0d  call    WPP_SF_sd
0x18002aa12  mov     rbx, cs:WPP_GLOBAL_Control
0x18002aa19  cmp     [rdi+70h], ebp
0x18002aa1c  jz      short loc_18002AA30
0x18002aa1e  cmp     [rdi+6Ch], ebp
0x18002aa21  jnz     short loc_18002AA30
0x18002aa23  cmp     [rdi+68h], ebp
0x18002aa26  jnz     short loc_18002AA30
0x18002aa28  test    esi, esi
0x18002aa2a  jz      loc_18002AB17
0x18002aa30  cmp     rbx, r15
0x18002aa33  jz      short loc_18002AA6D
0x18002aa35  test    byte ptr [rbx+1Ch], 4
0x18002aa39  jz      short loc_18002AA6D
0x18002aa3b  cmp     byte ptr [rbx+19h], 2
0x18002aa3f  jb      short loc_18002AA6D
0x18002aa41  mov     rbx, [rbx+10h]
0x18002aa45  call    cs:__imp_GetCurrentThreadId
0x18002aa4b  lea     rcx, [rsp+128h+pszDest]
0x18002aa50  mov     edx, 1Fh
0x18002aa55  mov     [rsp+128h+var_100], rcx
0x18002aa5a  lea     r9, aNetrsharedelco; "NetrShareDelCommit"
0x18002aa61  mov     rcx, rbx
0x18002aa64  mov     [rsp+128h+var_108], eax
0x18002aa68  call    WPP_SF_sdS
0x18002aa6d  xor     ecx, ecx; BindingHandle
0x18002aa6f  cmp     [rdi+80h], rbp
0x18002aa76  jz      short loc_18002AAA1
0x18002aa78  call    cs:__imp_RpcImpersonateClient
0x18002aa7e  mov     rcx, [rdi+80h]
0x18002aa85  mov     ebx, eax
0x18002aa87  mov     rax, [rcx+40h]
0x18002aa8b  jmp     short loc_18002AAB0
0x18002aa8d  mov     rax, [rdx]
0x18002aa90  mov     rbx, rdx
0x18002aa93  mov     rcx, [rax]
0x18002aa96  mov     [rdx], rcx
0x18002aa99  mov     [rdi], rbp
0x18002aa9c  jmp     loc_18002A910
0x18002aaa1  call    cs:__imp_RpcImpersonateClient
0x18002aaa7  mov     ebx, eax
0x18002aaa9  mov     rax, cs:qword_18005E500
0x18002aab0  mov     rcx, [rdi+20h]
0x18002aab4  lea     rdx, [rsp+128h+pszDest]
0x18002aab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aabe  mov     esi, eax
0x18002aac0  test    ebx, ebx
0x18002aac2  jnz     short loc_18002AACA
0x18002aac4  call    cs:__imp_RpcRevertToSelf
0x18002aaca  test    esi, esi
0x18002aacc  jnz     short loc_18002AAFE
0x18002aace  cmp     [rdi+6Ch], ebp
0x18002aad1  jnz     short loc_18002AAFE
0x18002aad3  lea     rcx, [rdi+88h]; ValueName
0x18002aada  call    SsRemoveShareFromRegistry
0x18002aadf  cmp     [rdi+78h], ebp
0x18002aae2  jz      short loc_18002AAFE
0x18002aae4  cmp     cs:dword_18005CCF8, 1
0x18002aaeb  jz      short loc_18002AAFE
0x18002aaed  cmp     [rdi+6Ch], ebp
0x18002aaf0  jnz     short loc_18002AAFE
0x18002aaf2  cmp     [rdi+7Ch], ebp
0x18002aaf5  jnz     short loc_18002AAFE
0x18002aaf7  lock dec cs:UserShareCount
0x18002aafe  cmp     [rdi+68h], ebp
0x18002ab01  jz      short loc_18002AB17
0x18002ab03  lock dec cs:dword_18005D048
0x18002ab0a  xor     edx, edx
0x18002ab0c  xor     ecx, ecx
0x18002ab0e  lea     r8d, [rdx+1]
0x18002ab12  call    SsSetExportedServerType
0x18002ab17  mov     rcx, rdi; hMem
0x18002ab1a  call    cs:__imp_LocalFree
0x18002ab20  mov     eax, esi
0x18002ab22  jmp     short loc_18002AB29
0x18002ab24  mov     eax, 57h ; 'W'
0x18002ab29  mov     rcx, [rsp+128h+var_28]
0x18002ab31  xor     rcx, rsp; StackCookie
0x18002ab34  call    __security_check_cookie
0x18002ab39  lea     r11, [rsp+128h+var_18]
0x18002ab41  mov     rbx, [r11+28h]
0x18002ab45  mov     rbp, [r11+30h]
0x18002ab49  mov     rsp, r11
0x18002ab4c  pop     r15
0x18002ab4e  pop     rdi
0x18002ab4f  pop     rsi
0x18002ab50  retn
```
