# CWcnNetworkProfileLoaderElevated::LoadStringResource(int,ulong,ushort *)

- ea: `0x18002d788`
- end: `0x18002d9f6`
- name: `?LoadStringResource@CWcnNetworkProfileLoaderElevated@@AEAAJHKPEAG@Z`
- size: `622`
- prototype: `int(CWcnNetworkProfileLoaderElevated *__hidden this, int, unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002cb30`
- `0x18002cdc0`

## callees

- `0x180001820`
- `0x18000d368`
- `0x18000d630`
- `0x18000e1dc`
- `0x18001bc88`
- `0x18002d788`
- `0x18002de1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002d885`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002d885`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d995`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d995`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d92d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d92d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d80e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d8b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d8bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d8c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d94b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d80e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d8b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d8bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d8c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d94b`
- `KERNEL32!GetSystemDirectoryW` at `0x18002d804`
- `KERNEL32!GetSystemDirectoryW` at `0x18002d804`

## string_xrefs

- `0x18002d876`: `\wcnapi.dll`

## pseudocode

```c
__int64 __fastcall CWcnNetworkProfileLoaderElevated::LoadStringResource(
        CWcnNetworkProfileLoaderElevated *this,
        UINT a2,
        int a3,
        unsigned __int16 *a4)
{
  const char *Indent; // rax
  __int64 v8; // r10
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  _BYTE *v11; // r10
  unsigned int v12; // eax
  __int64 v13; // r10
  HINSTANCE Library; // rax
  HMODULE v16; // rdi
  unsigned int LastError; // ebx
  unsigned int v18; // eax
  __int64 v19; // r10
  unsigned int v20; // ebx
  unsigned int v21; // eax
  __int64 v22; // r10
  unsigned int v23; // eax
  __int64 v24; // r10
  WCHAR Buffer[264]; // [rsp+30h] [rbp-258h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 38, WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids, Indent);
  }
  *a4 = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    if ( (unsigned int)_o_wcscat_s(Buffer, 260, L"\\wcnapi.dll") )
      return 2147549183LL;
    Library = (HINSTANCE)IsolationAwareLoadLibraryExW(Buffer);
    v16 = Library;
    if ( Library )
    {
      v10 = 0;
      if ( !LoadStringW(Library, a2, a4, a3) )
      {
        v20 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0x80070000 : GetLastError();
        v10 = v20 | 0x80000000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = (unsigned int)GetIndent(0);
          WPP_SF_sd(*(_QWORD *)(v22 + 16), 41, (unsigned int)WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids, v21, v10);
        }
      }
      FreeLibrary(v16);
    }
    else
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v10 = LastError | 0x80000000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v10;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_29;
      v18 = (unsigned int)GetIndent(0);
      WPP_SF_sSd(
        *(_QWORD *)(v19 + 16),
        40,
        (unsigned int)WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids,
        v18,
        (__int64)Buffer,
        v10);
    }
    goto LABEL_28;
  }
  if ( (int)GetLastError() > 0 )
    v9 = (unsigned __int16)GetLastError() | 0x80070000;
  else
    v9 = GetLastError();
  v10 = v9 | 0x80000000;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v10;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = (unsigned int)GetIndent(0);
    WPP_SF_sd(*(_QWORD *)(v13 + 16), 39, (unsigned int)WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids, v12, v10);
LABEL_28:
    v11 = WPP_GLOBAL_Control;
  }
LABEL_29:
  if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && ((v10 & 0x80000000) != 0 || v11[25] >= 6u) )
  {
    v23 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v24 + 16), 42, (unsigned int)WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids, v23, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x18002d788  push    rbx
0x18002d78a  push    rbp
0x18002d78b  push    rsi
0x18002d78c  push    rdi
0x18002d78d  push    r12
0x18002d78f  push    r14
0x18002d791  push    r15
0x18002d793  sub     rsp, 250h
0x18002d79a  mov     rax, cs:__security_cookie
0x18002d7a1  xor     rax, rsp
0x18002d7a4  mov     [rsp+288h+var_48], rax
0x18002d7ac  mov     rsi, r9
0x18002d7af  mov     r14d, r8d
0x18002d7b2  mov     ebp, edx
0x18002d7b4  mov     r10, cs:WPP_GLOBAL_Control
0x18002d7bb  lea     r15, WPP_GLOBAL_Control
0x18002d7c2  lea     r12, WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids
0x18002d7c9  cmp     r10, r15
0x18002d7cc  jz      short loc_18002D7F3
0x18002d7ce  cmp     byte ptr [r10+19h], 6
0x18002d7d3  jb      short loc_18002D7F3
0x18002d7d5  mov     ecx, 1; int
0x18002d7da  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002d7df  mov     rcx, [r10+10h]
0x18002d7e3  mov     edx, 26h ; '&'
0x18002d7e8  mov     r9, rax
0x18002d7eb  mov     r8, r12
0x18002d7ee  call    WPP_SF_s
0x18002d7f3  xor     eax, eax
0x18002d7f5  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x18002d7fa  mov     ebx, 104h
0x18002d7ff  mov     [rsi], ax
0x18002d802  mov     edx, ebx; uSize
0x18002d804  call    cs:__imp_GetSystemDirectoryW
0x18002d80a  test    eax, eax
0x18002d80c  jnz     short loc_18002D876
0x18002d80e  call    cs:__imp_GetLastError
0x18002d814  test    eax, eax
0x18002d816  jg      short loc_18002D822
0x18002d818  call    cs:__imp_GetLastError
0x18002d81e  mov     ebx, eax
0x18002d820  jmp     short loc_18002D831
0x18002d822  call    cs:__imp_GetLastError
0x18002d828  movzx   ebx, ax
0x18002d82b  or      ebx, 80070000h
0x18002d831  or      ebx, 80000000h
0x18002d837  mov     r10, cs:WPP_GLOBAL_Control
0x18002d83e  cmp     r10, r15
0x18002d841  jz      loc_18002D9D2
0x18002d847  cmp     byte ptr [r10+19h], 2
0x18002d84c  jb      loc_18002D9A2
0x18002d852  xor     ecx, ecx; int
0x18002d854  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002d859  mov     rcx, [r10+10h]
0x18002d85d  mov     edx, 27h ; '''
0x18002d862  mov     r9, rax
0x18002d865  mov     dword ptr [rsp+288h+var_268], ebx
0x18002d869  mov     r8, r12
0x18002d86c  call    WPP_SF_sd
0x18002d871  jmp     loc_18002D99B
0x18002d876  lea     r8, aWcnapiDll; "\\wcnapi.dll"
0x18002d87d  mov     rdx, rbx
0x18002d880  lea     rcx, [rsp+288h+Buffer]
0x18002d885  call    cs:__imp__o_wcscat_s
0x18002d88b  test    eax, eax
0x18002d88d  jz      short loc_18002D899
0x18002d88f  mov     eax, 8000FFFFh
0x18002d894  jmp     loc_18002D9D4
0x18002d899  mov     r8d, 60h ; '`'
0x18002d89f  lea     rcx, [rsp+288h+Buffer]; lpLibFileName
0x18002d8a4  call    IsolationAwareLoadLibraryExW
0x18002d8a9  mov     rdi, rax
0x18002d8ac  test    rax, rax
0x18002d8af  jnz     short loc_18002D920
0x18002d8b1  call    cs:__imp_GetLastError
0x18002d8b7  test    eax, eax
0x18002d8b9  jg      short loc_18002D8C5
0x18002d8bb  call    cs:__imp_GetLastError
0x18002d8c1  mov     ebx, eax
0x18002d8c3  jmp     short loc_18002D8D4
0x18002d8c5  call    cs:__imp_GetLastError
0x18002d8cb  movzx   ebx, ax
0x18002d8ce  or      ebx, 80070000h
0x18002d8d4  or      ebx, 80000000h
0x18002d8da  mov     r10, cs:WPP_GLOBAL_Control
0x18002d8e1  cmp     r10, r15
0x18002d8e4  jz      loc_18002D9D2
0x18002d8ea  cmp     byte ptr [r10+19h], 2
0x18002d8ef  jb      loc_18002D9A2
0x18002d8f5  xor     ecx, ecx; int
0x18002d8f7  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002d8fc  lea     rcx, [rsp+288h+Buffer]
0x18002d901  mov     [rsp+288h+var_260], ebx
0x18002d905  mov     [rsp+288h+var_268], rcx
0x18002d90a  mov     edx, 28h ; '('
0x18002d90f  mov     rcx, [r10+10h]
0x18002d913  mov     r9, rax
0x18002d916  mov     r8, r12
0x18002d919  call    WPP_SF_sSd
0x18002d91e  jmp     short loc_18002D99B
0x18002d920  mov     r9d, r14d; cchBufferMax
0x18002d923  mov     r8, rsi; lpBuffer
0x18002d926  mov     edx, ebp; uID
0x18002d928  mov     rcx, rdi; hInstance
0x18002d92b  xor     ebx, ebx
0x18002d92d  call    cs:__imp_LoadStringW
0x18002d933  test    eax, eax
0x18002d935  jnz     short loc_18002D992
0x18002d937  call    cs:__imp_GetLastError
0x18002d93d  test    eax, eax
0x18002d93f  jg      short loc_18002D94B
0x18002d941  call    cs:__imp_GetLastError
0x18002d947  mov     ebx, eax
0x18002d949  jmp     short loc_18002D95A
0x18002d94b  call    cs:__imp_GetLastError
0x18002d951  movzx   ebx, ax
0x18002d954  or      ebx, 80070000h
0x18002d95a  or      ebx, 80000000h
0x18002d960  mov     r10, cs:WPP_GLOBAL_Control
0x18002d967  cmp     r10, r15
0x18002d96a  jz      short loc_18002D992
0x18002d96c  cmp     byte ptr [r10+19h], 2
0x18002d971  jb      short loc_18002D992
0x18002d973  xor     ecx, ecx; int
0x18002d975  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002d97a  mov     rcx, [r10+10h]
0x18002d97e  mov     edx, 29h ; ')'
0x18002d983  mov     r9, rax
0x18002d986  mov     dword ptr [rsp+288h+var_268], ebx
0x18002d98a  mov     r8, r12
0x18002d98d  call    WPP_SF_sd
0x18002d992  mov     rcx, rdi; hLibModule
0x18002d995  call    cs:__imp_FreeLibrary
0x18002d99b  mov     r10, cs:WPP_GLOBAL_Control
0x18002d9a2  cmp     r10, r15
0x18002d9a5  jz      short loc_18002D9D2
0x18002d9a7  test    ebx, ebx
0x18002d9a9  js      short loc_18002D9B2
0x18002d9ab  cmp     byte ptr [r10+19h], 6
0x18002d9b0  jb      short loc_18002D9D2
0x18002d9b2  or      ecx, 0FFFFFFFFh; int
0x18002d9b5  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002d9ba  mov     rcx, [r10+10h]
0x18002d9be  mov     edx, 2Ah ; '*'
0x18002d9c3  mov     r9, rax
0x18002d9c6  mov     dword ptr [rsp+288h+var_268], ebx
0x18002d9ca  mov     r8, r12
0x18002d9cd  call    WPP_SF_sd
0x18002d9d2  mov     eax, ebx
0x18002d9d4  mov     rcx, [rsp+288h+var_48]
0x18002d9dc  xor     rcx, rsp; StackCookie
0x18002d9df  call    __security_check_cookie
0x18002d9e4  add     rsp, 250h
0x18002d9eb  pop     r15
0x18002d9ed  pop     r14
0x18002d9ef  pop     r12
0x18002d9f1  pop     rdi
0x18002d9f2  pop     rsi
0x18002d9f3  pop     rbp
0x18002d9f4  pop     rbx
0x18002d9f5  retn
```
