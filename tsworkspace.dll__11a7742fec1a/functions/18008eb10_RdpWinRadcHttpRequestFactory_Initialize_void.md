# RdpWinRadcHttpRequestFactory::Initialize(void)

- ea: `0x18008eb10`
- end: `0x18008eda0`
- name: `?Initialize@RdpWinRadcHttpRequestFactory@@QEAA?AW4_XResult32@@XZ`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18008f0a0`

## callees

- `0x18000b26c`
- `0x18000ec94`
- `0x18000ece0`
- `0x180019fb0`
- `0x18001a008`
- `0x180032c88`
- `0x18007e1a0`
- `0x18008eb10`
- `0x180094bc4`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008eb4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ebd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008eb4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ebd5`
- `WINHTTP!WinHttpOpen` at `0x18008eb3b`
- `WINHTTP!WinHttpOpen` at `0x18008eb3b`
- `WINHTTP!WinHttpSetTimeouts` at `0x18008ebcb`
- `WINHTTP!WinHttpSetTimeouts` at `0x18008ebcb`

## string_xrefs

- `0x18008ec67`: `Failed to create TaskQueue`
- `0x18008ed7c`: `RdpX_Threading_CreateCriticalSection failed`

## pseudocode

```c
__int64 __fastcall RdpWinRadcHttpRequestFactory::Initialize(__int64 a1)
{
  void *v2; // rax
  __int64 v3; // rcx
  signed int LastError; // ebx
  unsigned int ActivityIdPrefix; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int Object; // eax
  __int64 v9; // rcx
  int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rcx
  unsigned int CriticalSection; // ebx
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v23; // [rsp+28h] [rbp-10h]

  v2 = WinHttpOpen(L"TSWorkspace/3.0", 1u, 0, 0, 0);
  *(_QWORD *)(a1 + 16) = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(v3);
    v6 = 10;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      WPP_39fc8a4223bb3dce4123b7a5d92bc4ed_Traceguids,
      ActivityIdPrefix,
      LastError);
LABEL_7:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    return MapHRToXResult((unsigned int)LastError);
  }
  if ( !WinHttpSetTimeouts(v2, 0, 180000, 180000, 300000) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(v7);
    v6 = 11;
    goto LABEL_6;
  }
  Object = RdpX_CreateObject(0, 0, 4, 5, a1 + 40);
  LastError = MapXResultToHR(Object);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return MapHRToXResult((unsigned int)LastError);
    }
    v10 = RdpX_GetActivityIdPrefix(v9);
    v11 = 12;
    v12 = "Failed to create TaskQueue";
    goto LABEL_22;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 40) + 24LL))(*(_QWORD *)(a1 + 40));
  LastError = MapXResultToHR(v13);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return MapHRToXResult((unsigned int)LastError);
    }
    v10 = RdpX_GetActivityIdPrefix(v15);
    v11 = 13;
    v12 = "InitializeInstance failed!";
LABEL_22:
    LODWORD(v23) = LastError;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)WPP_39fc8a4223bb3dce4123b7a5d92bc4ed_Traceguids,
      v10,
      (__int64)v12,
      v23);
    return MapHRToXResult((unsigned int)LastError);
  }
  CriticalSection = RdpX_Win_CreateCriticalSection(v15, v14, v16, a1 + 72);
  if ( CriticalSection
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v19 = RdpX_GetActivityIdPrefix(v17);
    WPP_SF_DLD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_39fc8a4223bb3dce4123b7a5d92bc4ed_Traceguids,
      v19,
      CriticalSection,
      CriticalSection);
  }
  LastError = MapXResultToHR(CriticalSection);
  if ( LastError >= 0 )
  {
    LastError = 0;
    return MapHRToXResult((unsigned int)LastError);
  }
  if ( (PVOID *)v20 != &WPP_GLOBAL_Control && (*(_BYTE *)(v20 + 28) & 8) != 0 && *(_BYTE *)(v20 + 25) >= 2u )
  {
    v10 = RdpX_GetActivityIdPrefix(v21);
    v11 = 14;
    v12 = "RdpX_Threading_CreateCriticalSection failed";
    goto LABEL_22;
  }
  return MapHRToXResult((unsigned int)LastError);
}

```

## disassembly

```asm
0x18008eb10  mov     [rsp+arg_0], rbx
0x18008eb15  mov     [rsp+arg_8], rsi
0x18008eb1a  push    rdi
0x18008eb1b  sub     rsp, 30h
0x18008eb1f  xor     r9d, r9d; pszProxyBypassW
0x18008eb22  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18008eb2a  mov     rdi, rcx
0x18008eb2d  xor     r8d, r8d; pszProxyW
0x18008eb30  lea     rcx, aTsworkspace30; "TSWorkspace/3.0"
0x18008eb37  lea     edx, [r9+1]; dwAccessType
0x18008eb3b  call    cs:__imp_WinHttpOpen
0x18008eb41  mov     [rdi+10h], rax
0x18008eb45  test    rax, rax
0x18008eb48  jnz     short loc_18008EBB5
0x18008eb4a  call    cs:__imp_GetLastError
0x18008eb50  mov     ebx, eax
0x18008eb52  mov     rax, cs:WPP_GLOBAL_Control
0x18008eb59  lea     rdi, WPP_GLOBAL_Control
0x18008eb60  cmp     rax, rdi
0x18008eb63  jz      short loc_18008EB99
0x18008eb65  test    byte ptr [rax+1Ch], 8
0x18008eb69  jz      short loc_18008EB99
0x18008eb6b  cmp     byte ptr [rax+19h], 2
0x18008eb6f  jb      short loc_18008EB99
0x18008eb71  call    RdpX_GetActivityIdPrefix
0x18008eb76  mov     edx, 0Ah
0x18008eb7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008eb82  lea     r8, WPP_39fc8a4223bb3dce4123b7a5d92bc4ed_Traceguids
0x18008eb89  mov     r9d, eax
0x18008eb8c  mov     [rsp+38h+dwFlags], ebx
0x18008eb90  mov     rcx, [rcx+10h]
0x18008eb94  call    WPP_SF_Dd
0x18008eb99  test    ebx, ebx
0x18008eb9b  jle     short loc_18008EBA6
0x18008eb9d  movzx   ebx, bx
0x18008eba0  or      ebx, 80070000h
0x18008eba6  test    ebx, ebx
0x18008eba8  mov     eax, 80004005h
0x18008ebad  cmovns  ebx, eax
0x18008ebb0  jmp     loc_18008ED8A
0x18008ebb5  mov     r8d, 2BF20h; nConnectTimeout
0x18008ebbb  mov     [rsp+38h+dwFlags], 493E0h; nReceiveTimeout
0x18008ebc3  mov     r9d, r8d; nSendTimeout
0x18008ebc6  xor     edx, edx; nResolveTimeout
0x18008ebc8  mov     rcx, rax; hInternet
0x18008ebcb  call    cs:__imp_WinHttpSetTimeouts
0x18008ebd1  test    eax, eax
0x18008ebd3  jnz     short loc_18008EC0B
0x18008ebd5  call    cs:__imp_GetLastError
0x18008ebdb  mov     ebx, eax
0x18008ebdd  mov     rax, cs:WPP_GLOBAL_Control
0x18008ebe4  lea     rdi, WPP_GLOBAL_Control
0x18008ebeb  cmp     rax, rdi
0x18008ebee  jz      short loc_18008EB99
0x18008ebf0  test    byte ptr [rax+1Ch], 8
0x18008ebf4  jz      short loc_18008EB99
0x18008ebf6  cmp     byte ptr [rax+19h], 2
0x18008ebfa  jb      short loc_18008EB99
0x18008ebfc  call    RdpX_GetActivityIdPrefix
0x18008ec01  mov     edx, 0Bh
0x18008ec06  jmp     loc_18008EB7B
0x18008ec0b  xor     edx, edx
0x18008ec0d  lea     rsi, [rdi+28h]
0x18008ec11  xor     ecx, ecx
0x18008ec13  mov     qword ptr [rsp+38h+dwFlags], rsi
0x18008ec18  lea     r9d, [rdx+5]
0x18008ec1c  lea     r8d, [rdx+4]
0x18008ec20  call    ?RdpX_CreateObject@@YA?AW4_XResult32@@PEAURdpXInterface@@IW4_XObjectId32@@W4_XInterfaceId32@@PEAPEAX@Z; RdpX_CreateObject(RdpXInterface *,uint,_XObjectId32,_XInterfaceId32,void * *)
0x18008ec25  mov     ecx, eax
0x18008ec27  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x18008ec2c  mov     ebx, eax
0x18008ec2e  test    eax, eax
0x18008ec30  jns     short loc_18008EC96
0x18008ec32  mov     rax, cs:WPP_GLOBAL_Control
0x18008ec39  lea     rdi, WPP_GLOBAL_Control
0x18008ec40  cmp     rax, rdi
0x18008ec43  jz      loc_18008ED8A
0x18008ec49  test    byte ptr [rax+1Ch], 8
0x18008ec4d  jz      loc_18008ED8A
0x18008ec53  cmp     byte ptr [rax+19h], 2
0x18008ec57  jb      loc_18008ED8A
0x18008ec5d  call    RdpX_GetActivityIdPrefix
0x18008ec62  mov     edx, 0Ch
0x18008ec67  lea     rcx, aFailedToCreate_4; "Failed to create TaskQueue"
0x18008ec6e  mov     [rsp+38h+var_10], ebx
0x18008ec72  lea     r8, WPP_39fc8a4223bb3dce4123b7a5d92bc4ed_Traceguids
0x18008ec79  mov     qword ptr [rsp+38h+dwFlags], rcx
0x18008ec7e  mov     r9d, eax
0x18008ec81  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ec88  mov     rcx, [rcx+10h]
0x18008ec8c  call    WPP_SF_DsD
0x18008ec91  jmp     loc_18008ED8A
0x18008ec96  mov     rcx, [rsi]
0x18008ec99  mov     rax, [rcx]
0x18008ec9c  mov     rax, [rax+18h]
0x18008eca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eca5  mov     ecx, eax
0x18008eca7  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x18008ecac  mov     ebx, eax
0x18008ecae  test    eax, eax
0x18008ecb0  jns     short loc_18008ECF3
0x18008ecb2  mov     rax, cs:WPP_GLOBAL_Control
0x18008ecb9  lea     rdi, WPP_GLOBAL_Control
0x18008ecc0  cmp     rax, rdi
0x18008ecc3  jz      loc_18008ED8A
0x18008ecc9  test    byte ptr [rax+1Ch], 8
0x18008eccd  jz      loc_18008ED8A
0x18008ecd3  cmp     byte ptr [rax+19h], 2
0x18008ecd7  jb      loc_18008ED8A
0x18008ecdd  call    RdpX_GetActivityIdPrefix
0x18008ece2  mov     edx, 0Dh
0x18008ece7  lea     rcx, aInitializeinst_0; "InitializeInstance failed!"
0x18008ecee  jmp     loc_18008EC6E
0x18008ecf3  lea     r9, [rdi+48h]
0x18008ecf7  call    ?RdpX_Win_CreateCriticalSection@@YA?AW4_XResult32@@PEAURdpXInterface@@IW4_XInterfaceId32@@PEAPEAX@Z; RdpX_Win_CreateCriticalSection(RdpXInterface *,uint,_XInterfaceId32,void * *)
0x18008ecfc  lea     rdi, WPP_GLOBAL_Control
0x18008ed03  mov     ebx, eax
0x18008ed05  test    eax, eax
0x18008ed07  jz      short loc_18008ED4D
0x18008ed09  mov     rdx, cs:WPP_GLOBAL_Control
0x18008ed10  cmp     rdx, rdi
0x18008ed13  jz      short loc_18008ED54
0x18008ed15  test    byte ptr [rdx+1Ch], 1
0x18008ed19  jz      short loc_18008ED54
0x18008ed1b  cmp     byte ptr [rdx+19h], 2
0x18008ed1f  jb      short loc_18008ED54
0x18008ed21  call    RdpX_GetActivityIdPrefix
0x18008ed26  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ed2d  lea     r8, WPP_39fc8a4223bb3dce4123b7a5d92bc4ed_Traceguids
0x18008ed34  mov     edx, 16h
0x18008ed39  mov     [rsp+38h+var_10], ebx
0x18008ed3d  mov     r9d, eax
0x18008ed40  mov     [rsp+38h+dwFlags], ebx
0x18008ed44  mov     rcx, [rcx+10h]
0x18008ed48  call    WPP_SF_DLD
0x18008ed4d  mov     rdx, cs:WPP_GLOBAL_Control
0x18008ed54  mov     ecx, ebx
0x18008ed56  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x18008ed5b  mov     ebx, eax
0x18008ed5d  test    eax, eax
0x18008ed5f  jns     short loc_18008ED88
0x18008ed61  cmp     rdx, rdi
0x18008ed64  jz      short loc_18008ED8A
0x18008ed66  test    byte ptr [rdx+1Ch], 8
0x18008ed6a  jz      short loc_18008ED8A
0x18008ed6c  cmp     byte ptr [rdx+19h], 2
0x18008ed70  jb      short loc_18008ED8A
0x18008ed72  call    RdpX_GetActivityIdPrefix
0x18008ed77  mov     edx, 0Eh
0x18008ed7c  lea     rcx, aRdpxThreadingC; "RdpX_Threading_CreateCriticalSection fa"...
0x18008ed83  jmp     loc_18008EC6E
0x18008ed88  xor     ebx, ebx
0x18008ed8a  mov     ecx, ebx
0x18008ed8c  mov     rbx, [rsp+38h+arg_0]
0x18008ed91  mov     rsi, [rsp+38h+arg_8]
0x18008ed96  add     rsp, 30h
0x18008ed9a  pop     rdi
0x18008ed9b  jmp     ?MapHRToXResult@@YA?AW4_XResult32@@J@Z; MapHRToXResult(long)
```
