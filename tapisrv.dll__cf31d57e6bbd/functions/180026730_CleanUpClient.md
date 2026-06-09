# CleanUpClient

- ea: `0x180026730`
- end: `0x180026c4d`
- name: `CleanUpClient`
- size: `1309`
- prototype: `__int64 __fastcall(unsigned __int64, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800283d0`
- `0x18002ba70`
- `0x18002e9b0`

## callees

- `0x180001600`
- `0x180004fcc`
- `0x18001c7c0`
- `0x180020db4`
- `0x180026730`
- `0x180028b00`
- `0x18002a804`
- `0x18002c8d4`
- `0x18003dc84`
- `0x180040010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180026abc`
- `RPCRT4!NdrClientCall3` at `0x180026abc`
- `KERNEL32!CloseHandle` at `0x180026b8a`
- `KERNEL32!CloseHandle` at `0x180026b9d`
- `KERNEL32!CloseHandle` at `0x180026b8a`
- `KERNEL32!CloseHandle` at `0x180026b9d`
- `KERNEL32!Sleep` at `0x18002681f`
- `KERNEL32!Sleep` at `0x18002681f`
- `KERNEL32!GetCurrentThreadId` at `0x180026956`
- `KERNEL32!GetCurrentThreadId` at `0x1800269ce`
- `KERNEL32!GetCurrentThreadId` at `0x180026956`
- `KERNEL32!GetCurrentThreadId` at `0x1800269ce`
- `KERNEL32!LeaveCriticalSection` at `0x180026814`
- `KERNEL32!LeaveCriticalSection` at `0x180026883`
- `KERNEL32!LeaveCriticalSection` at `0x1800268d1`
- `KERNEL32!LeaveCriticalSection` at `0x180026939`
- `KERNEL32!LeaveCriticalSection` at `0x1800269f4`
- `KERNEL32!LeaveCriticalSection` at `0x180026814`
- `KERNEL32!LeaveCriticalSection` at `0x180026883`
- `KERNEL32!LeaveCriticalSection` at `0x1800268d1`
- `KERNEL32!LeaveCriticalSection` at `0x180026939`
- `KERNEL32!LeaveCriticalSection` at `0x1800269f4`
- `KERNEL32!EnterCriticalSection` at `0x18002679d`
- `KERNEL32!EnterCriticalSection` at `0x1800268ba`
- `KERNEL32!EnterCriticalSection` at `0x180026916`
- `KERNEL32!EnterCriticalSection` at `0x180026946`
- `KERNEL32!EnterCriticalSection` at `0x18002679d`
- `KERNEL32!EnterCriticalSection` at `0x1800268ba`
- `KERNEL32!EnterCriticalSection` at `0x180026916`
- `KERNEL32!EnterCriticalSection` at `0x180026946`

## string_xrefs

- `0x180026a6f`: `CLIENT DLL had a problem: x%p`

## pseudocode

```c
__int64 __fastcall CleanUpClient(unsigned __int64 a1, int a2)
{
  unsigned __int64 v3; // rdi
  int v4; // ecx
  int v5; // edi
  _BYTE *v7; // r14
  HANDLE *v8; // rsi
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  __int64 v10; // rcx
  _QWORD *v11; // rax
  size_t v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  size_t v15; // rdx
  __int64 v16; // r8
  __int64 i; // rdi
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdi
  WCHAR *v21; // rcx
  unsigned int v22; // [rsp+34h] [rbp-94h]
  unsigned __int64 v24; // [rsp+50h] [rbp-78h]
  unsigned __int64 v25; // [rsp+58h] [rbp-70h] BYREF
  _OWORD v26[4]; // [rsp+60h] [rbp-68h] BYREF

  v22 = 0;
  v3 = a1 >> 4;
  v25 = a1 >> 4;
  v24 = a1 >> 4;
  while ( 1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v3 & gdwPointerToLockTableIndexBits));
    v4 = *(_DWORD *)a1;
    if ( !a2 )
      break;
    if ( v4 != 1129204803 )
    {
      if ( v4 == 1414417475 )
      {
        *(_DWORD *)a1 = 1280724553;
        v5 = 0;
        goto LABEL_13;
      }
      v5 = 1;
      if ( v4 == 1515080771 )
      {
        *(_DWORD *)a1 = 1280724553;
        v22 = 1;
        goto LABEL_13;
      }
      goto LABEL_12;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v3 & gdwPointerToLockTableIndexBits));
    Sleep(0x32u);
  }
  if ( v4 == 1414417475 )
  {
    v5 = 0;
    *(_DWORD *)a1 = 1129204803;
    goto LABEL_13;
  }
  v5 = 1;
LABEL_12:
  v22 = 0;
LABEL_13:
  LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)v24 & gdwPointerToLockTableIndexBits));
  if ( v5 )
    return v22;
  v7 = (_BYTE *)(a1 + 216);
  if ( (*(_BYTE *)(a1 + 216) & 4) != 0 )
  {
    EnterCriticalSection(&gMgmtCritSec);
    gbLockMMCWrite = 0;
    LeaveCriticalSection(&gMgmtCritSec);
  }
  v8 = (HANDLE *)(a1 + 8);
  if ( ((*(_QWORD *)(a1 + 8) & 0xFFFFFFFFFFFFFFFEuLL) == 0xFFFFFFFFFFFFFFFEuLL || *v8 == (HANDLE)-3LL)
    && *(_QWORD *)(a1 + 224) )
  {
    v9 = &gCnClientMsgPendingCritSec;
    if ( *v8 != (HANDLE)-1LL )
      v9 = &gDgClientMsgPendingCritSec;
    EnterCriticalSection(v9);
    v10 = *(_QWORD *)(a1 + 224);
    if ( v10 )
    {
      v11 = *(_QWORD **)(a1 + 232);
      *v11 = v10;
      *(_QWORD *)(v10 + 8) = v11;
    }
    LeaveCriticalSection(v9);
  }
  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 5982;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(pszDest, v12, "server\\server.c");
  v13 = *(_QWORD *)(a1 + 208);
  if ( v13 )
    *(_QWORD *)(v13 + 200) = *(_QWORD *)(a1 + 200);
  v14 = *(_QWORD *)(a1 + 200);
  if ( v14 )
    *(_QWORD *)(v14 + 208) = *(_QWORD *)(a1 + 208);
  else
    qword_180051908 = *(_QWORD *)(a1 + 208);
  dword_1800519F8 = 6005;
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v15, "server\\server.c");
  LeaveCriticalSection(&CriticalSection);
  if ( (dword_180051900 & 2) != 0 && (*v7 & 1) == 0 )
  {
    v25 = 0;
    (*((void (__fastcall **)(_QWORD))qword_180051988 + 5))(*(_QWORD *)(a1 + 72));
    if ( lpParameter )
    {
      for ( i = *((_QWORD *)lpParameter + 1); i; i = *(_QWORD *)(i + 248) )
      {
        if ( (unsigned int)GetTCClient(i, a1, v16, &v25) )
          (*(void (__fastcall **)(unsigned __int64))(i + 40))(v25);
      }
    }
  }
  if ( *v8 == (HANDLE)-1LL && a2 )
    NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, a1 + 56);
  while ( 1 )
  {
    v18 = *(_QWORD *)(a1 + 168);
    if ( !v18 )
      break;
    DestroytLineApp(*(unsigned int *)(v18 + 24), a1);
  }
  while ( 1 )
  {
    v19 = *(_QWORD *)(a1 + 176);
    if ( !v19 )
      break;
    DestroytPhoneApp(*(unsigned int *)(v19 + 4), a1);
  }
  v20 = *(_QWORD *)(a1 + 184);
  while ( v20 )
  {
    memset(v26, 0, 60);
    DWORD2(v26[0]) = *(_DWORD *)(v20 + 88);
    HIDWORD(v26[0]) = -2147483576;
    v20 = *(_QWORD *)(v20 + 80);
    FreeDialogInstance(a1, v26, 60);
  }
  if ( ((unsigned __int64)*v8 & 0xFFFFFFFFFFFFFFFEuLL) != 0xFFFFFFFFFFFFFFFEuLL && *v8 != (HANDLE)-3LL )
    CloseHandle(*v8);
  if ( *v8 != (HANDLE)-1LL )
    CloseHandle(*(HANDLE *)(a1 + 128));
  ServerFree(*(LPVOID *)(a1 + 144));
  ServerFree(*(LPVOID *)(a1 + 24));
  v21 = *(WCHAR **)(a1 + 40);
  if ( v21 != lpString )
    ServerFree(v21);
  ServerFree(*(LPVOID *)(a1 + 48));
  if ( (dword_180051900 & 2) != 0 && (*v7 & 1) == 0 )
  {
    ServerFree(*(LPVOID *)(a1 + 64));
    ServerFree(*(LPVOID *)(a1 + 80));
    ServerFree(*(LPVOID *)(a1 + 88));
    ServerFree(*(LPVOID *)(a1 + 104));
    ServerFree(*(LPVOID *)(a1 + 112));
  }
  if ( !a2 )
    *(_DWORD *)a1 = 1515080771;
  return 1;
}

```

## disassembly

```asm
0x180026730  mov     [rsp+arg_10], rbx
0x180026735  mov     [rsp+arg_8], edx
0x180026739  push    rsi
0x18002673a  push    rdi
0x18002673b  push    r14
0x18002673d  sub     rsp, 0B0h
0x180026744  mov     rax, cs:__security_cookie
0x18002674b  xor     rax, rsp
0x18002674e  mov     [rsp+0C8h+var_28], rax
0x180026756  mov     rbx, rcx
0x180026759  mov     [rsp+0C8h+var_80], rcx
0x18002675e  mov     [rsp+0C8h+var_90], rcx
0x180026763  mov     [rsp+0C8h+var_94], 0
0x18002676b  mov     rdi, rcx
0x18002676e  shr     rdi, 4
0x180026772  mov     [rsp+0C8h+var_70], rdi
0x180026777  mov     [rsp+0C8h+var_78], rdi
0x18002677c  nop
0x18002677d  mov     rsi, rdi
0x180026780  mov     [rsp+0C8h+var_88], rdi
0x180026785  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18002678b  and     rax, rdi
0x18002678e  lea     rcx, [rax+rax*4]
0x180026792  mov     rax, cs:gLockTable
0x180026799  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18002679d  call    cs:__imp_EnterCriticalSection
0x1800267a3  jmp     short loc_1800267B4
0x1800267a5  mov     rbx, [rsp+0C8h+var_90]
0x1800267aa  mov     rsi, [rsp+0C8h+var_88]
0x1800267af  mov     rdi, [rsp+0C8h+var_70]
0x1800267b4  mov     rax, [rsp+0C8h+var_80]
0x1800267b9  mov     ecx, [rax]
0x1800267bb  cmp     [rsp+0C8h+arg_8], 0
0x1800267c3  jz      short loc_18002682A
0x1800267c5  cmp     ecx, 434E4C43h
0x1800267cb  jz      short loc_1800267FC
0x1800267cd  cmp     ecx, 544E4C43h
0x1800267d3  jz      short loc_1800267F2
0x1800267d5  mov     edi, 1
0x1800267da  cmp     ecx, 5A4E4C43h
0x1800267e0  jnz     short loc_180026845
0x1800267e2  mov     dword ptr [rax], 4C564E49h
0x1800267e8  mov     [rsp+0C8h+var_98], edi
0x1800267ec  mov     [rsp+0C8h+var_94], edi
0x1800267f0  jmp     short loc_180026851
0x1800267f2  mov     dword ptr [rax], 4C564E49h
0x1800267f8  xor     edi, edi
0x1800267fa  jmp     short loc_18002684D
0x1800267fc  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180026802  and     rax, rsi
0x180026805  lea     rcx, [rax+rax*4]
0x180026809  mov     rax, cs:gLockTable
0x180026810  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180026814  call    cs:__imp_LeaveCriticalSection
0x18002681a  mov     ecx, 32h ; '2'; dwMilliseconds
0x18002681f  call    cs:__imp_Sleep
0x180026825  jmp     loc_18002677C
0x18002682a  cmp     ecx, 544E4C43h
0x180026830  jnz     short loc_180026840
0x180026832  xor     edi, edi
0x180026834  mov     [rsp+0C8h+var_98], edi
0x180026838  mov     dword ptr [rax], 434E4C43h
0x18002683e  jmp     short loc_180026851
0x180026840  mov     edi, 1
0x180026845  mov     [rsp+0C8h+var_94], 0
0x18002684d  mov     [rsp+0C8h+var_98], edi
0x180026851  jmp     short loc_180026869
0x180026853  mov     [rsp+0C8h+var_94], 0
0x18002685b  mov     edi, 1
0x180026860  mov     [rsp+0C8h+var_98], edi
0x180026864  mov     rbx, [rsp+0C8h+var_90]
0x180026869  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18002686f  and     rax, [rsp+0C8h+var_78]
0x180026874  lea     rcx, [rax+rax*4]
0x180026878  mov     rax, cs:gLockTable
0x18002687f  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180026883  call    cs:__imp_LeaveCriticalSection
0x180026889  jmp     short loc_180026894
0x18002688b  mov     edi, [rsp+0C8h+var_98]
0x18002688f  mov     rbx, [rsp+0C8h+var_90]
0x180026894  test    edi, edi
0x180026896  jz      short loc_1800268A1
0x180026898  mov     eax, [rsp+0C8h+var_94]
0x18002689c  jmp     loc_180026C29
0x1800268a1  lea     r14, [rbx+0D8h]
0x1800268a8  mov     [rsp+0C8h+var_78], r14
0x1800268ad  test    byte ptr [r14], 4
0x1800268b1  jz      short loc_1800268D7
0x1800268b3  lea     rcx, gMgmtCritSec; lpCriticalSection
0x1800268ba  call    cs:__imp_EnterCriticalSection
0x1800268c0  mov     cs:gbLockMMCWrite, 0
0x1800268ca  lea     rcx, gMgmtCritSec; lpCriticalSection
0x1800268d1  call    cs:__imp_LeaveCriticalSection
0x1800268d7  lea     rsi, [rbx+8]
0x1800268db  mov     [rsp+0C8h+var_88], rsi
0x1800268e0  mov     rax, [rsi]
0x1800268e3  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800268e7  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x1800268eb  jz      short loc_1800268F3
0x1800268ed  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFDh
0x1800268f1  jnz     short loc_18002693F
0x1800268f3  cmp     qword ptr [rbx+0E0h], 0
0x1800268fb  jz      short loc_18002693F
0x1800268fd  lea     rax, gDgClientMsgPendingCritSec
0x180026904  lea     rdi, gCnClientMsgPendingCritSec
0x18002690b  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18002690f  cmovnz  rdi, rax
0x180026913  mov     rcx, rdi; lpCriticalSection
0x180026916  call    cs:__imp_EnterCriticalSection
0x18002691c  mov     rcx, [rbx+0E0h]
0x180026923  test    rcx, rcx
0x180026926  jz      short loc_180026936
0x180026928  mov     rax, [rbx+0E8h]
0x18002692f  mov     [rax], rcx
0x180026932  mov     [rcx+8], rax
0x180026936  mov     rcx, rdi; lpCriticalSection
0x180026939  call    cs:__imp_LeaveCriticalSection
0x18002693f  lea     rcx, CriticalSection; lpCriticalSection
0x180026946  call    cs:__imp_EnterCriticalSection
0x18002694c  mov     cs:dword_1800519E0, 175Eh
0x180026956  call    cs:__imp_GetCurrentThreadId
0x18002695c  mov     cs:dword_1800519E4, eax
0x180026962  lea     r8, aPrintscanTapiS_3+0Fh; pszSrc
0x180026969  lea     rcx, pszDest; pszDest
0x180026970  call    StringCbCopyA
0x180026975  nop
0x180026976  mov     rcx, [rbx+0D0h]
0x18002697d  test    rcx, rcx
0x180026980  jz      short loc_180026990
0x180026982  mov     rax, [rbx+0C8h]
0x180026989  mov     [rcx+0C8h], rax
0x180026990  mov     rcx, [rbx+0C8h]
0x180026997  mov     rax, [rbx+0D0h]
0x18002699e  test    rcx, rcx
0x1800269a1  jz      short loc_1800269AC
0x1800269a3  mov     [rcx+0D0h], rax
0x1800269aa  jmp     short loc_1800269B3
0x1800269ac  mov     cs:qword_180051908, rax
0x1800269b3  jmp     short loc_1800269C4
0x1800269b5  mov     rbx, [rsp+0C8h+var_90]
0x1800269ba  mov     r14, [rsp+0C8h+var_78]
0x1800269bf  mov     rsi, [rsp+0C8h+var_88]
0x1800269c4  mov     cs:dword_1800519F8, 1775h
0x1800269ce  call    cs:__imp_GetCurrentThreadId
0x1800269d4  mov     cs:dword_1800519FC, eax
0x1800269da  lea     r8, aPrintscanTapiS_3+0Fh; pszSrc
0x1800269e1  lea     rcx, byte_1800519E8; pszDest
0x1800269e8  call    StringCbCopyA
0x1800269ed  lea     rcx, CriticalSection; lpCriticalSection
0x1800269f4  call    cs:__imp_LeaveCriticalSection
0x1800269fa  test    byte ptr cs:dword_180051900, 2
0x180026a01  jz      loc_180026A95
0x180026a07  test    byte ptr [r14], 1
0x180026a0b  jnz     loc_180026A95
0x180026a11  mov     [rsp+0C8h+var_70], 0
0x180026a1a  mov     rax, cs:qword_180051988
0x180026a21  mov     rcx, [rbx+48h]
0x180026a25  mov     rax, [rax+28h]
0x180026a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a2e  mov     rdi, cs:lpParameter
0x180026a35  test    rdi, rdi
0x180026a38  jz      short loc_180026A95
0x180026a3a  mov     rdi, [rdi+8]
0x180026a3e  test    rdi, rdi
0x180026a41  jz      short loc_180026A95
0x180026a43  lea     r9, [rsp+0C8h+var_70]
0x180026a48  mov     rdx, rbx
0x180026a4b  mov     rcx, rdi
0x180026a4e  call    GetTCClient
0x180026a53  test    eax, eax
0x180026a55  jz      short loc_180026A8C
0x180026a57  mov     rcx, [rsp+0C8h+var_70]
0x180026a5c  mov     rax, [rdi+28h]
0x180026a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a65  jmp     short loc_180026A8C
0x180026a67  mov     rbx, [rsp+0C8h+var_90]
0x180026a6c  mov     r8, rbx
0x180026a6f  lea     rdx, aClientDllHadAP; "CLIENT DLL had a problem: x%p"
0x180026a76  mov     ecx, 10002h
0x180026a7b  call    TRACELogPrint
0x180026a80  mov     r14, [rsp+0C8h+var_78]
0x180026a85  mov     rsi, [rsp+0C8h+var_88]
0x180026a8a  jmp     short loc_180026A95
0x180026a8c  mov     rdi, [rdi+0F8h]
0x180026a93  jmp     short loc_180026A3E
0x180026a95  mov     [rsp+0C8h+var_88], rsi
0x180026a9a  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180026a9e  jnz     short loc_180026AF4
0x180026aa0  cmp     [rsp+0C8h+arg_8], 0
0x180026aa8  jz      short loc_180026AF4
0x180026aaa  lea     r9, [rbx+38h]
0x180026aae  xor     r8d, r8d; pReturnValue
0x180026ab1  lea     edx, [r8+2]; nProcNum
0x180026ab5  lea     rcx, pProxyInfo; pProxyInfo
0x180026abc  call    cs:__imp_NdrClientCall3
0x180026ac2  jmp     short loc_180026AF4
0x180026ac4  mov     r8d, eax
0x180026ac7  lea     rdx, aRundownExcepti; "rundown: exception #%d detaching from r"...
0x180026ace  mov     ecx, 10002h
0x180026ad3  call    TRACELogPrint
0x180026ad8  mov     rbx, [rsp+0C8h+var_90]
0x180026add  mov     rsi, [rsp+0C8h+var_88]
0x180026ae2  mov     r14, [rsp+0C8h+var_78]
0x180026ae7  jmp     short loc_180026AF4
0x180026ae9  mov     rdx, rbx
0x180026aec  mov     ecx, [rax+18h]
0x180026aef  call    DestroytLineApp
0x180026af4  mov     rax, [rbx+0A8h]
0x180026afb  test    rax, rax
0x180026afe  jnz     short loc_180026AE9
0x180026b00  jmp     short loc_180026B0D
0x180026b02  mov     rdx, rbx
0x180026b05  mov     ecx, [rax+4]
0x180026b08  call    DestroytPhoneApp
0x180026b0d  mov     rax, [rbx+0B0h]
0x180026b14  test    rax, rax
0x180026b17  jnz     short loc_180026B02
0x180026b19  mov     rdi, [rbx+0B8h]
0x180026b20  jmp     short loc_180026B6F
0x180026b22  xorps   xmm0, xmm0
0x180026b25  movups  [rsp+0C8h+var_68], xmm0
0x180026b2a  movups  [rsp+0C8h+var_58], xmm0
0x180026b2f  movups  xmmword ptr [rsp+0C8h+var_48], xmm0
0x180026b37  movups  xmmword ptr [rsp+0C8h+var_48+0Ch], xmm0
0x180026b3f  mov     eax, [rdi+58h]
0x180026b42  mov     dword ptr [rsp+0C8h+var_68+8], eax
0x180026b46  mov     dword ptr [rsp+0C8h+var_68+0Ch], 80000048h
0x180026b4e  mov     rdi, [rdi+50h]
0x180026b52  mov     [rsp+0C8h+var_A8], 0
0x180026b5b  xor     r9d, r9d
0x180026b5e  lea     r8d, [r9+3Ch]
0x180026b62  lea     rdx, [rsp+0C8h+var_68]
0x180026b67  mov     rcx, rbx
0x180026b6a  call    FreeDialogInstance
0x180026b6f  test    rdi, rdi
0x180026b72  jnz     short loc_180026B22
0x180026b74  mov     rax, [rsi]
0x180026b77  and     rax, 0FFFFFFFFFFFFFFFEh
0x180026b7b  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x180026b7f  jz      short loc_180026B90
0x180026b81  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFDh
0x180026b85  jz      short loc_180026B90
0x180026b87  mov     rcx, [rsi]; hObject
0x180026b8a  call    cs:__imp_CloseHandle
0x180026b90  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180026b94  jz      short loc_180026BA3
0x180026b96  mov     rcx, [rbx+80h]; hObject
0x180026b9d  call    cs:__imp_CloseHandle
0x180026ba3  mov     rcx, [rbx+90h]; lpMem
0x180026baa  call    ServerFree
0x180026baf  mov     rcx, [rbx+18h]; lpMem
0x180026bb3  call    ServerFree
0x180026bb8  mov     rcx, [rbx+28h]; lpMem
0x180026bbc  cmp     rcx, cs:lpString
0x180026bc3  jz      short loc_180026BCA
0x180026bc5  call    ServerFree
0x180026bca  mov     rcx, [rbx+30h]; lpMem
0x180026bce  call    ServerFree
0x180026bd3  test    byte ptr cs:dword_180051900, 2
0x180026bda  jz      short loc_180026C0F
0x180026bdc  test    byte ptr [r14], 1
0x180026be0  jnz     short loc_180026C0F
0x180026be2  mov     rcx, [rbx+40h]; lpMem
0x180026be6  call    ServerFree
0x180026beb  mov     rcx, [rbx+50h]; lpMem
0x180026bef  call    ServerFree
0x180026bf4  mov     rcx, [rbx+58h]; lpMem
0x180026bf8  call    ServerFree
0x180026bfd  mov     rcx, [rbx+68h]; lpMem
0x180026c01  call    ServerFree
0x180026c06  mov     rcx, [rbx+70h]; lpMem
0x180026c0a  call    ServerFree
0x180026c0f  cmp     [rsp+0C8h+arg_8], 0
0x180026c17  jnz     short loc_180026C24
0x180026c19  mov     rcx, [rsp+0C8h+var_80]
0x180026c1e  mov     dword ptr [rcx], 5A4E4C43h
0x180026c24  mov     eax, 1
0x180026c29  mov     rcx, [rsp+0C8h+var_28]
0x180026c31  xor     rcx, rsp; StackCookie
0x180026c34  call    __security_check_cookie
0x180026c39  mov     rbx, [rsp+0C8h+arg_10]
0x180026c41  add     rsp, 0B0h
0x180026c48  pop     r14
0x180026c4a  pop     rdi
0x180026c4b  pop     rsi
0x180026c4c  retn
0x18003fca6  push    rbp
0x18003fca8  sub     rsp, 30h
0x18003fcac  mov     rbp, rdx
0x18003fcaf  mov     rcx, [rcx]
0x18003fcb2  mov     ecx, [rcx]; ExceptionCode
0x18003fcb4  call    cs:__imp_I_RpcExceptionFilter
0x18003fcba  nop
0x18003fcbb  add     rsp, 30h
0x18003fcbf  pop     rbp
0x18003fcc0  retn
```
