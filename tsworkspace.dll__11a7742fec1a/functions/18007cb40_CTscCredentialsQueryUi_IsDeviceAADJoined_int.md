# CTscCredentialsQueryUi::IsDeviceAADJoined(int *)

- ea: `0x18007cb40`
- end: `0x18007cd7a`
- name: `?IsDeviceAADJoined@CTscCredentialsQueryUi@@CAJPEAH@Z`
- size: `570`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18007d16c`

## callees

- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18007cb40`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007cd69`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007cd69`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007cc41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007cc54`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007cc41`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007cc54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cbce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cbce`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007cbc0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007cbc0`

## string_xrefs

- `0x18007cbb9`: `netapi32.dll`

## pseudocode

```c
__int64 __fastcall CTscCredentialsQueryUi::IsDeviceAADJoined(int *a1)
{
  void (*v1)(void); // rbp
  HMODULE v3; // rdi
  unsigned int v4; // eax
  signed int LastError; // ebx
  HMODULE LibraryW; // rax
  unsigned int v7; // eax
  FARPROC ProcAddress; // rbx
  FARPROC v9; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v11; // eax
  unsigned int v12; // eax
  _DWORD *v14; // [rsp+60h] [rbp+8h] BYREF

  v1 = 0;
  v14 = 0;
  if ( a1 )
  {
    LibraryW = LoadLibraryW(L"netapi32.dll");
    v3 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "NetGetAadJoinInformation");
      v9 = GetProcAddress(v3, "NetFreeAadJoinInformation");
      v1 = (void (*)(void))v9;
      if ( ProcAddress && v9 )
      {
        LastError = ((__int64 (__fastcall *)(_QWORD, _DWORD **))ProcAddress)(0, &v14);
        if ( LastError >= 0 )
        {
          if ( !v14 || (v11 = 1, *v14 != 1) )
            v11 = 0;
          *a1 = v11;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            62,
            (unsigned int)WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"NetGetAadJoinInformation failed",
            LastError);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v12 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids, v12);
        }
        LastError = -2147467263;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids,
          v7,
          LastError);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
    }
  }
  else
  {
    v3 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids,
        v4,
        (__int64)"pfAADJoined",
        -2147024809);
    }
    LastError = -2147024809;
  }
  if ( v14 && v1 )
    v1();
  if ( v3 )
    FreeLibrary(v3);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18007cb40  push    rbx
0x18007cb42  push    rbp
0x18007cb43  push    rsi
0x18007cb44  push    rdi
0x18007cb45  sub     rsp, 38h
0x18007cb49  xor     ebp, ebp
0x18007cb4b  mov     rsi, rcx
0x18007cb4e  mov     [rsp+58h+arg_0], rbp
0x18007cb53  test    rcx, rcx
0x18007cb56  jnz     short loc_18007CBB9
0x18007cb58  xor     edi, edi
0x18007cb5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cb61  lea     rax, WPP_GLOBAL_Control
0x18007cb68  cmp     rcx, rax
0x18007cb6b  jz      short loc_18007CBAF
0x18007cb6d  test    byte ptr [rcx+1Ch], 8
0x18007cb71  jz      short loc_18007CBAF
0x18007cb73  cmp     byte ptr [rcx+19h], 2
0x18007cb77  jb      short loc_18007CBAF
0x18007cb79  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007cb7e  lea     rcx, aPfaadjoined; "pfAADJoined"
0x18007cb85  mov     [rsp+58h+var_30], 80070057h
0x18007cb8d  mov     [rsp+58h+var_38], rcx
0x18007cb92  lea     edx, [rsi+3Bh]
0x18007cb95  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cb9c  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x18007cba3  mov     r9d, eax
0x18007cba6  mov     rcx, [rcx+10h]
0x18007cbaa  call    WPP_SF_DsD
0x18007cbaf  mov     ebx, 80070057h
0x18007cbb4  jmp     loc_18007CD4A
0x18007cbb9  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x18007cbc0  call    cs:__imp_LoadLibraryW
0x18007cbc6  mov     rdi, rax
0x18007cbc9  test    rax, rax
0x18007cbcc  jnz     short loc_18007CC37
0x18007cbce  call    cs:__imp_GetLastError
0x18007cbd4  mov     ebx, eax
0x18007cbd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cbdd  lea     rax, WPP_GLOBAL_Control
0x18007cbe4  cmp     rcx, rax
0x18007cbe7  jz      short loc_18007CC1B
0x18007cbe9  test    byte ptr [rcx+1Ch], 8
0x18007cbed  jz      short loc_18007CC1B
0x18007cbef  cmp     byte ptr [rcx+19h], 2
0x18007cbf3  jb      short loc_18007CC1B
0x18007cbf5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007cbfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cc01  lea     edx, [rdi+3Ch]
0x18007cc04  mov     r9d, eax
0x18007cc07  mov     dword ptr [rsp+58h+var_38], ebx
0x18007cc0b  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x18007cc12  mov     rcx, [rcx+10h]
0x18007cc16  call    WPP_SF_Dd
0x18007cc1b  test    ebx, ebx
0x18007cc1d  jle     short loc_18007CC28
0x18007cc1f  movzx   ebx, bx
0x18007cc22  or      ebx, 80070000h
0x18007cc28  test    ebx, ebx
0x18007cc2a  mov     eax, 80004005h
0x18007cc2f  cmovns  ebx, eax
0x18007cc32  jmp     loc_18007CD4A
0x18007cc37  lea     rdx, aNetgetaadjoini; "NetGetAadJoinInformation"
0x18007cc3e  mov     rcx, rdi; hModule
0x18007cc41  call    cs:__imp_GetProcAddress
0x18007cc47  lea     rdx, aNetfreeaadjoin; "NetFreeAadJoinInformation"
0x18007cc4e  mov     rcx, rdi; hModule
0x18007cc51  mov     rbx, rax
0x18007cc54  call    cs:__imp_GetProcAddress
0x18007cc5a  mov     rbp, rax
0x18007cc5d  test    rbx, rbx
0x18007cc60  jz      loc_18007CCFE
0x18007cc66  test    rax, rax
0x18007cc69  jz      loc_18007CCFE
0x18007cc6f  lea     rdx, [rsp+58h+arg_0]
0x18007cc74  xor     ecx, ecx
0x18007cc76  mov     rax, rbx
0x18007cc79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cc7e  mov     ebx, eax
0x18007cc80  test    eax, eax
0x18007cc82  jns     short loc_18007CCE5
0x18007cc84  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cc8b  lea     rax, WPP_GLOBAL_Control
0x18007cc92  cmp     rcx, rax
0x18007cc95  jz      loc_18007CD4A
0x18007cc9b  test    byte ptr [rcx+1Ch], 8
0x18007cc9f  jz      loc_18007CD4A
0x18007cca5  cmp     byte ptr [rcx+19h], 2
0x18007cca9  jb      loc_18007CD4A
0x18007ccaf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007ccb4  lea     rcx, aNetgetaadjoini_0; "NetGetAadJoinInformation failed"
0x18007ccbb  mov     [rsp+58h+var_30], ebx
0x18007ccbf  mov     [rsp+58h+var_38], rcx
0x18007ccc4  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x18007cccb  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ccd2  mov     edx, 3Eh ; '>'
0x18007ccd7  mov     r9d, eax
0x18007ccda  mov     rcx, [rcx+10h]
0x18007ccde  call    WPP_SF_DsD
0x18007cce3  jmp     short loc_18007CD4A
0x18007cce5  mov     rcx, [rsp+58h+arg_0]
0x18007ccea  test    rcx, rcx
0x18007cced  jz      short loc_18007CCF8
0x18007ccef  mov     eax, 1
0x18007ccf4  cmp     [rcx], eax
0x18007ccf6  jz      short loc_18007CCFA
0x18007ccf8  xor     eax, eax
0x18007ccfa  mov     [rsi], eax
0x18007ccfc  jmp     short loc_18007CD4A
0x18007ccfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cd05  lea     rax, WPP_GLOBAL_Control
0x18007cd0c  cmp     rcx, rax
0x18007cd0f  jz      short loc_18007CD45
0x18007cd11  mov     eax, 1
0x18007cd16  test    [rcx+1Ch], al
0x18007cd19  jz      short loc_18007CD45
0x18007cd1b  cmp     byte ptr [rcx+19h], 3
0x18007cd1f  jb      short loc_18007CD45
0x18007cd21  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007cd26  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cd2d  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x18007cd34  mov     edx, 3Dh ; '='
0x18007cd39  mov     r9d, eax
0x18007cd3c  mov     rcx, [rcx+10h]
0x18007cd40  call    WPP_SF_D
0x18007cd45  mov     ebx, 80004001h
0x18007cd4a  mov     rcx, [rsp+58h+arg_0]
0x18007cd4f  test    rcx, rcx
0x18007cd52  jz      short loc_18007CD61
0x18007cd54  test    rbp, rbp
0x18007cd57  jz      short loc_18007CD61
0x18007cd59  mov     rax, rbp
0x18007cd5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cd61  test    rdi, rdi
0x18007cd64  jz      short loc_18007CD6F
0x18007cd66  mov     rcx, rdi; hLibModule
0x18007cd69  call    cs:__imp_FreeLibrary
0x18007cd6f  mov     eax, ebx
0x18007cd71  add     rsp, 38h
0x18007cd75  pop     rdi
0x18007cd76  pop     rsi
0x18007cd77  pop     rbp
0x18007cd78  pop     rbx
0x18007cd79  retn
```
