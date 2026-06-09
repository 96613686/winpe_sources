# P2pInitializeInternal(char *,HTTP_DISPATCH_TABLE * const,int,int)

- ea: `0x180041d5c`
- end: `0x180041ecb`
- name: `?P2pInitializeInternal@@YAKPEADQEAUHTTP_DISPATCH_TABLE@@HH@Z`
- size: `367`
- prototype: `unsigned int __fastcall(char *, struct HTTP_DISPATCH_TABLE *const, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180041ab0`

## callees

- `0x180041d5c`
- `0x180041ed4`
- `0x180042368`
- `0x180042730`
- `0x180042968`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e93`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041eba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041eba`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180041e36`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180041e36`

## string_xrefs

- `0x180041d7e`: `Software\Microsoft\Windows NT\CurrentVersion\PeerDist\Service`
- `0x180041d77`: `Software\Policies\Microsoft\PeerDist\Service`

## pseudocode

```c
__int64 __fastcall P2pInitializeInternal(char *a1, struct HTTP_DISPATCH_TABLE *const a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // rbx
  const WCHAR *v5; // rcx
  __int64 v7; // rbx
  const WCHAR *v8; // rcx
  unsigned int v9; // eax
  BOOL v10; // edi
  unsigned int *v11; // rdx
  P2P_PEER_DIST_API *v12; // rcx
  void **v13; // r8
  int PeerDist; // eax
  const char *v15; // rdx
  const char *v16; // rcx
  char ***v17; // r8
  LPCWSTR lpSubKey; // [rsp+20h] [rbp-18h]
  const wchar_t *v19; // [rsp+28h] [rbp-10h]
  unsigned int v20; // [rsp+78h] [rbp+40h] BYREF

  v20 = a4;
  v4 = 0;
  if ( !P2pEnabled )
  {
    lpSubKey = L"Software\\Policies\\Microsoft\\PeerDist\\Service";
    v19 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist\\Service";
    do
    {
      v5 = (&lpSubKey)[v4];
      v20 = 0;
      if ( ReadDWordValue(v5, L"Enable", &v20) != 2 )
        break;
      v4 = (unsigned int)(v4 + 1);
    }
    while ( (unsigned int)v4 < 2 );
    if ( v20 && (unsigned int)P2pCheckPlatform(v20 != 0) )
    {
      lpSubKey = L"Software\\Policies\\Microsoft\\PeerDist\\Service";
      v7 = 0;
      v19 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist\\Service";
      do
      {
        v8 = (&lpSubKey)[v7];
        v20 = 0;
        v9 = ReadDWordValue(v8, L"DisableSecondClientBenefit", &v20);
        v10 = v20 == 0;
        if ( v9 != 2 )
          break;
        v7 = (unsigned int)(v7 + 1);
      }
      while ( (unsigned int)v7 < 2 );
      qword_1800AE588 = (__int64)&g_P2pQueuedHashRequsts;
      g_P2pQueuedHashRequsts = (P2P_HASH_REQUEST *)&g_P2pQueuedHashRequsts;
      if ( InitializeCriticalSectionAndSpinCount(&P2pGlobalLock, 0xFA0u) )
      {
        PeerDist = P2P_PEER_DIST_API::LoadPeerDist(v12, v11, v13);
        if ( PeerDist )
        {
          if ( PeerDist == 126 )
            PeerDist = 50;
          LODWORD(v4) = PeerDist;
          DeleteCriticalSection(&P2pGlobalLock);
        }
        else
        {
          P2pEnabled = 1;
          P2pClientTag = "WebIO";
          P2pHttpDispatchTable = (struct HTTP_DISPATCH_TABLE *)&WaHttpExtensionDispatchTable;
          if ( P2pVersion <= 1 )
            v10 = 0;
          P2pEnableSecondClientBenefit = v10;
          P2PReadHeaderListToCopy(v16, v15, v17);
          LODWORD(v4) = 0;
        }
      }
      else
      {
        LODWORD(v4) = GetLastError();
      }
    }
    else
    {
      LODWORD(v4) = 50;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180041d5c  mov     [rsp-20h+arg_18], r9d
0x180041d61  push    rbp
0x180041d62  push    rbx
0x180041d63  push    rdi
0x180041d64  push    r15
0x180041d66  mov     rbp, rsp
0x180041d69  sub     rsp, 38h
0x180041d6d  xor     ebx, ebx
0x180041d6f  cmp     cs:?P2pEnabled@@3HA, ebx; int P2pEnabled
0x180041d75  jnz     short loc_180041DC5
0x180041d77  lea     rdi, aSoftwarePolici; "Software\\Policies\\Microsoft\\PeerDist"...
0x180041d7e  lea     r15, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x180041d85  mov     [rbp+lpSubKey], rdi
0x180041d89  mov     [rbp+var_10], r15
0x180041d8d  mov     rcx, [rbp+rbx*8+lpSubKey]; lpSubKey
0x180041d92  lea     r8, [rbp+arg_18]; unsigned int *
0x180041d96  lea     rdx, aEnable; "Enable"
0x180041d9d  mov     [rbp+arg_18], 0
0x180041da4  call    ?ReadDWordValue@@YAKPEBG0PEAK@Z; ReadDWordValue(ushort const *,ushort const *,ulong *)
0x180041da9  xor     ecx, ecx
0x180041dab  cmp     [rbp+arg_18], ecx
0x180041dae  setnz   cl; int
0x180041db1  cmp     eax, 2
0x180041db4  jnz     short loc_180041DBC
0x180041db6  inc     ebx
0x180041db8  cmp     ebx, eax
0x180041dba  jb      short loc_180041D8D
0x180041dbc  test    ecx, ecx
0x180041dbe  jnz     short loc_180041DD2
0x180041dc0  mov     ebx, 32h ; '2'
0x180041dc5  mov     eax, ebx
0x180041dc7  add     rsp, 38h
0x180041dcb  pop     r15
0x180041dcd  pop     rdi
0x180041dce  pop     rbx
0x180041dcf  pop     rbp
0x180041dd0  retn
0x180041dd2  call    ?P2pCheckPlatform@@YAHH@Z; P2pCheckPlatform(int)
0x180041dd7  test    eax, eax
0x180041dd9  jz      short loc_180041DC0
0x180041ddb  mov     [rbp+lpSubKey], rdi
0x180041ddf  xor     ebx, ebx
0x180041de1  mov     [rbp+var_10], r15
0x180041de5  mov     rcx, [rbp+rbx*8+lpSubKey]; lpSubKey
0x180041dea  lea     r8, [rbp+arg_18]; unsigned int *
0x180041dee  lea     rdx, aDisablesecondc; "DisableSecondClientBenefit"
0x180041df5  mov     [rbp+arg_18], 0
0x180041dfc  call    ?ReadDWordValue@@YAKPEBG0PEAK@Z; ReadDWordValue(ushort const *,ushort const *,ulong *)
0x180041e01  xor     edi, edi
0x180041e03  cmp     [rbp+arg_18], edi
0x180041e06  setz    dil
0x180041e0a  cmp     eax, 2
0x180041e0d  jnz     short loc_180041E15
0x180041e0f  inc     ebx
0x180041e11  cmp     ebx, eax
0x180041e13  jb      short loc_180041DE5
0x180041e15  lea     rax, ?g_P2pQueuedHashRequsts@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_P2pQueuedHashRequsts
0x180041e1c  mov     edx, 0FA0h; dwSpinCount
0x180041e21  lea     rcx, ?P2pGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180041e28  mov     cs:qword_1800AE588, rax
0x180041e2f  mov     cs:?g_P2pQueuedHashRequsts@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_P2pQueuedHashRequsts
0x180041e36  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180041e3d  nop     dword ptr [rax+rax+00h]
0x180041e42  test    eax, eax
0x180041e44  jz      short loc_180041E93
0x180041e46  call    ?LoadPeerDist@P2P_PEER_DIST_API@@QEAAKPEAKPEAPEAX@Z; P2P_PEER_DIST_API::LoadPeerDist(ulong *,void * *)
0x180041e4b  test    eax, eax
0x180041e4d  jnz     short loc_180041EA6
0x180041e4f  lea     rax, aWebio; "WebIO"
0x180041e56  mov     cs:?P2pEnabled@@3HA, 1; int P2pEnabled
0x180041e60  mov     cs:?P2pClientTag@@3PEADEA, rax; char * P2pClientTag
0x180041e67  lea     rax, WaHttpExtensionDispatchTable
0x180041e6e  mov     cs:?P2pHttpDispatchTable@@3PEAUHTTP_DISPATCH_TABLE@@EA, rax; HTTP_DISPATCH_TABLE * P2pHttpDispatchTable
0x180041e75  xor     eax, eax
0x180041e77  cmp     cs:?P2pVersion@@3KA, 1; ulong P2pVersion
0x180041e7e  cmovbe  edi, eax
0x180041e81  mov     cs:?P2pEnableSecondClientBenefit@@3HA, edi; int P2pEnableSecondClientBenefit
0x180041e87  call    ?P2PReadHeaderListToCopy@@YAXPEBD0AEAPEAPEAD@Z; P2PReadHeaderListToCopy(char const *,char const *,char * * &)
0x180041e8c  xor     ebx, ebx
0x180041e8e  jmp     loc_180041DC5
0x180041e93  call    cs:__imp_GetLastError
0x180041e9a  nop     dword ptr [rax+rax+00h]
0x180041e9f  mov     ebx, eax
0x180041ea1  jmp     loc_180041DC5
0x180041ea6  cmp     eax, 7Eh ; '~'
0x180041ea9  lea     rcx, ?P2pGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180041eb0  mov     ebx, 32h ; '2'
0x180041eb5  cmovz   eax, ebx
0x180041eb8  mov     ebx, eax
0x180041eba  call    cs:__imp_DeleteCriticalSection
0x180041ec1  nop     dword ptr [rax+rax+00h]
0x180041ec6  jmp     loc_180041DC5
```
