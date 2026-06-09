# IsCallerWiFiNetworkManager(int *)

- ea: `0x18003de40`
- end: `0x18003dfe9`
- name: `?IsCallerWiFiNetworkManager@@YAKPEAH@Z`
- size: `425`
- prototype: `unsigned int __fastcall(PBOOL IsMember)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003c850`
- `0x1800a53c0`
- `0x1800f53a0`
- `0x180127590`
- `0x18012a8c0`
- `0x18012ae50`
- `0x1801306e0`
- `0x180130ba0`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18003de40`
- `0x18003e4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ded9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ded9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003dec3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003dec3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dee9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dee9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003deaa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003deaa`

## pseudocode

```c
__int64 __fastcall IsCallerWiFiNetworkManager(PBOOL IsMember)
{
  PVOID *v2; // rcx
  RPC_STATUS v3; // eax
  HANDLE v4; // rdi
  DWORD LastError; // ebx
  PVOID *v6; // rcx
  PSID Sid; // [rsp+40h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 51, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  TokenHandle = 0;
  Sid = 0;
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 105) >= 4u && (*((_BYTE *)v2 + 108) & 1) != 0 )
    WPP_SF_(v2[12], 47, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
  *IsMember = 0;
  v3 = LocalQueryRpcClientToken(&TokenHandle);
  v4 = TokenHandle;
  LastError = v3;
  if ( !v3
    && (ConvertStringSidToSidW(L"S-1-5-80-1428027539-3309602793-2678353003-1498846795-3763184142", &Sid)
     || (LastError = GetLastError()) == 0)
    && !CheckTokenMembership(v4, Sid, IsMember) )
  {
    LastError = GetLastError();
  }
  if ( v4 )
    CloseHandle(v4);
  if ( Sid )
    LocalFree(Sid);
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 48, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, LastError);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 105) >= 4u && (*((_BYTE *)v6 + 108) & 1) != 0 )
      WPP_SF_d(v6[12], 52, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18003de40  mov     [rsp+arg_10], rbx
0x18003de45  push    rbp
0x18003de46  push    rsi
0x18003de47  push    rdi
0x18003de48  sub     rsp, 20h
0x18003de4c  mov     rsi, rcx
0x18003de4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003de56  lea     rbp, WPP_GLOBAL_Control
0x18003de5d  cmp     rcx, rbp
0x18003de60  jz      short loc_18003DE6C
0x18003de62  cmp     byte ptr [rcx+69h], 4
0x18003de66  jnb     loc_18003DF23
0x18003de6c  xor     ebx, ebx
0x18003de6e  mov     [rsp+38h+TokenHandle], rbx
0x18003de73  mov     [rsp+38h+Sid], rbx
0x18003de78  cmp     rcx, rbp
0x18003de7b  jz      short loc_18003DE87
0x18003de7d  cmp     byte ptr [rcx+69h], 4
0x18003de81  jnb     loc_18003DF4E
0x18003de87  lea     rcx, [rsp+38h+TokenHandle]; void **
0x18003de8c  mov     [rsi], ebx
0x18003de8e  call    ?LocalQueryRpcClientToken@@YAKPEAPEAX@Z; LocalQueryRpcClientToken(void * *)
0x18003de93  mov     rdi, [rsp+38h+TokenHandle]
0x18003de98  mov     ebx, eax
0x18003de9a  test    eax, eax
0x18003de9c  jnz     short loc_18003DED1
0x18003de9e  lea     rdx, [rsp+38h+Sid]; Sid
0x18003dea3  lea     rcx, aS1580142802753; "S-1-5-80-1428027539-3309602793-26783530"...
0x18003deaa  call    cs:__imp_ConvertStringSidToSidW
0x18003deb0  test    eax, eax
0x18003deb2  jz      loc_18003DF72
0x18003deb8  mov     rdx, [rsp+38h+Sid]; SidToCheck
0x18003debd  mov     r8, rsi; IsMember
0x18003dec0  mov     rcx, rdi; TokenHandle
0x18003dec3  call    cs:__imp_CheckTokenMembership
0x18003dec9  test    eax, eax
0x18003decb  jz      loc_18003DF87
0x18003ded1  test    rdi, rdi
0x18003ded4  jz      short loc_18003DEDF
0x18003ded6  mov     rcx, rdi; hObject
0x18003ded9  call    cs:__imp_CloseHandle
0x18003dedf  mov     rcx, [rsp+38h+Sid]; hMem
0x18003dee4  test    rcx, rcx
0x18003dee7  jz      short loc_18003DEEF
0x18003dee9  call    cs:__imp_LocalFree
0x18003deef  mov     rcx, cs:WPP_GLOBAL_Control
0x18003def6  cmp     rcx, rbp
0x18003def9  jz      short loc_18003DF14
0x18003defb  cmp     byte ptr [rcx+69h], 4
0x18003deff  jnb     loc_18003DF94
0x18003df05  cmp     rcx, rbp
0x18003df08  jz      short loc_18003DF14
0x18003df0a  cmp     byte ptr [rcx+69h], 4
0x18003df0e  jnb     loc_18003DFC2
0x18003df14  mov     eax, ebx
0x18003df16  mov     rbx, [rsp+38h+arg_10]
0x18003df1b  add     rsp, 20h
0x18003df1f  pop     rdi
0x18003df20  pop     rsi
0x18003df21  pop     rbp
0x18003df22  retn
0x18003df23  test    byte ptr [rcx+6Ch], 1
0x18003df27  jz      loc_18003DE6C
0x18003df2d  mov     rcx, [rcx+60h]
0x18003df31  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003df38  mov     edx, 33h ; '3'
0x18003df3d  call    WPP_SF_
0x18003df42  mov     rcx, cs:WPP_GLOBAL_Control
0x18003df49  jmp     loc_18003DE6C
0x18003df4e  test    byte ptr [rcx+6Ch], 1
0x18003df52  jz      loc_18003DE87
0x18003df58  mov     rcx, [rcx+60h]
0x18003df5c  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003df63  mov     edx, 2Fh ; '/'
0x18003df68  call    WPP_SF_
0x18003df6d  jmp     loc_18003DE87
0x18003df72  call    cs:__imp_GetLastError
0x18003df78  mov     ebx, eax
0x18003df7a  test    eax, eax
0x18003df7c  jnz     loc_18003DED1
0x18003df82  jmp     loc_18003DEB8
0x18003df87  call    cs:__imp_GetLastError
0x18003df8d  mov     ebx, eax
0x18003df8f  jmp     loc_18003DED1
0x18003df94  test    byte ptr [rcx+6Ch], 1
0x18003df98  jz      loc_18003DF05
0x18003df9e  mov     rcx, [rcx+60h]
0x18003dfa2  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003dfa9  mov     edx, 30h ; '0'
0x18003dfae  mov     r9d, ebx
0x18003dfb1  call    WPP_SF_d
0x18003dfb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dfbd  jmp     loc_18003DF05
0x18003dfc2  test    byte ptr [rcx+6Ch], 1
0x18003dfc6  jz      loc_18003DF14
0x18003dfcc  mov     rcx, [rcx+60h]
0x18003dfd0  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18003dfd7  mov     edx, 34h ; '4'
0x18003dfdc  mov     r9d, ebx
0x18003dfdf  call    WPP_SF_d
0x18003dfe4  jmp     loc_18003DF14
```
