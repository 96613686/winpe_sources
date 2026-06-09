# ArgParseCommandLine(int,ushort * *,ARGUMENT *,TYPED_ARGUMENT<ushort *> *)

- ea: `0x14003b990`
- end: `0x14003bbb2`
- name: `?ArgParseCommandLine@@YAJHPEAPEAGPEAVARGUMENT@@PEAV?$TYPED_ARGUMENT@PEAG@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14002ec00`

## callees

- `0x14002e7a0`
- `0x14003b990`
- `0x14003bbb8`
- `0x14003bc48`
- `0x14003be08`
- `0x14003c1ac`
- `0x14003c54c`
- `0x14003c780`
- `0x14003cb00`
- `0x14003e334`
- `0x14003eeac`
- `0x14003f0cc`
- `0x140040130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ba19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ba19`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x14003b9d0`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x14003b9d0`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x14003b9db`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x14003b9db`
- `api-ms-win-core-console-l2-1-0!GetConsoleScreenBufferInfo` at `0x14003ba0f`
- `api-ms-win-core-console-l2-1-0!GetConsoleScreenBufferInfo` at `0x14003ba0f`

## pseudocode

```c
__int64 __fastcall ArgParseCommandLine(int a1, unsigned __int16 **a2)
{
  char *StdHandle; // rax
  void *v5; // rbx
  signed int LastError; // eax
  bool v7; // sf
  __int64 result; // rax
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // eax
  struct ARGUMENT *v12; // rcx
  struct ARGUMENT *v13; // rax
  const unsigned __int16 *v14; // rsi
  int v15; // edi
  int v16; // eax
  int v17; // eax
  struct _ARGUMENT_INPUT *v18; // [rsp+20h] [rbp-58h] BYREF
  _CONSOLE_SCREEN_BUFFER_INFO ConsoleScreenBufferInfo; // [rsp+28h] [rbp-50h] BYREF

  v18 = 0;
  memset(&ConsoleScreenBufferInfo, 0, sizeof(ConsoleScreenBufferInfo));
  SetThreadPreferredUILanguages(0x100u, 0, 0);
  StdHandle = (char *)GetStdHandle(0xFFFFFFF5);
  v5 = StdHandle;
  if ( (unsigned __int64)(StdHandle - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return 2147942487LL;
  g_Width = 0;
  if ( (unsigned int)ArgIsConsole(StdHandle) )
  {
    if ( GetConsoleScreenBufferInfo(v5, &ConsoleScreenBufferInfo) )
      goto LABEL_8;
    LastError = GetLastError();
    v7 = LastError < 0;
    if ( LastError )
    {
      if ( LastError > 0 )
        v7 = 1;
      if ( !v7 )
LABEL_8:
        g_Width = ConsoleScreenBufferInfo.srWindow.Right - ConsoleScreenBufferInfo.srWindow.Left;
    }
  }
  ArgRegister(0);
  if ( dword_140060D14 )
  {
    dword_140060D14 = 0;
    qword_140083420 = (__int64)GuidHead.Data4;
    *(_QWORD *)GuidHead.Data4 = GuidHead.Data4;
  }
  result = ArgpLoadArguments();
  if ( (int)result >= 0 )
  {
    result = ArgpCmdInitialize(a1, a2, &v18);
    if ( (int)result >= 0 )
    {
      v9 = 0;
      v10 = ArgpParseFromInput(v18, 1);
      if ( v10 < 0 )
        v9 = v10;
      if ( dword_140060E84 && FileName )
      {
        result = ArgpFileInitialize(FileName, &v18);
        if ( (int)result < 0 )
          return result;
        v11 = ArgpParseFromInput(v18, 2);
        if ( v11 < 0 )
          v9 = v11;
      }
      if ( g_Debug )
        ArgpPrintDebugInfo();
      if ( !dword_140060E04 )
      {
        v17 = ArgApplyRules(0);
        result = ArgpFindBadArguments(v17);
LABEL_36:
        if ( (int)result >= 0 && (_DWORD)result != 1 )
          return v9;
        return result;
      }
      v12 = g_ArgsHead;
      v13 = g_ArgsHead;
      dword_140060DCC |= 0x200u;
      v14 = *a2;
      if ( g_ArgsHead == (struct ARGUMENT *)&g_ArgsHead )
      {
LABEL_27:
        v15 = 0;
        while ( v12 != (struct ARGUMENT *)&g_ArgsHead )
        {
          if ( (*((_DWORD *)v12 + 11) & 0x10) == 0 )
            *((_DWORD *)v12 + 21) = 1;
          v12 = *(struct ARGUMENT **)v12;
        }
      }
      else
      {
        while ( !*((_DWORD *)v13 + 25) || (*((_DWORD *)v13 + 11) & 0x200) != 0 )
        {
          v13 = *(struct ARGUMENT **)v13;
          if ( v13 == (struct ARGUMENT *)&g_ArgsHead )
            goto LABEL_27;
        }
        v15 = 1;
      }
      v16 = ArgApplyRules(1);
      result = ArgpFindBadArguments(v16);
      if ( (int)result >= 0 )
      {
        ArgpPrintUsage(v14);
        ArgpPrintArguments(v15);
        result = 1;
        goto LABEL_36;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003b990  push    rbx
0x14003b992  push    rsi
0x14003b993  push    rdi
0x14003b994  push    r14
0x14003b996  sub     rsp, 58h
0x14003b99a  mov     rax, cs:__security_cookie
0x14003b9a1  xor     rax, rsp
0x14003b9a4  mov     [rsp+78h+var_38], rax
0x14003b9a9  xorps   xmm0, xmm0
0x14003b9ac  mov     [rsp+78h+var_58], 0
0x14003b9b5  mov     rdi, rdx
0x14003b9b8  mov     esi, ecx
0x14003b9ba  xor     eax, eax
0x14003b9bc  xor     r8d, r8d; pulNumLanguages
0x14003b9bf  movups  xmmword ptr [rsp+78h+ConsoleScreenBufferInfo.dwSize.X], xmm0
0x14003b9c4  xor     edx, edx; pwszLanguagesBuffer
0x14003b9c6  mov     qword ptr [rsp+78h+ConsoleScreenBufferInfo.srWindow.Right], rax
0x14003b9cb  mov     ecx, 100h; dwFlags
0x14003b9d0  call    cs:__imp_SetThreadPreferredUILanguages
0x14003b9d6  mov     ecx, 0FFFFFFF5h; nStdHandle
0x14003b9db  call    cs:__imp_GetStdHandle
0x14003b9e1  mov     rbx, rax
0x14003b9e4  lea     rcx, [rax-1]
0x14003b9e8  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14003b9ec  ja      loc_14003BB96
0x14003b9f2  xor     ecx, ecx
0x14003b9f4  mov     cs:?g_Width@@3GA, cx; ushort g_Width
0x14003b9fb  mov     rcx, rax; hConsoleHandle
0x14003b9fe  call    ?ArgIsConsole@@YAHPEAX@Z; ArgIsConsole(void *)
0x14003ba03  test    eax, eax
0x14003ba05  jz      short loc_14003BA42
0x14003ba07  lea     rdx, [rsp+78h+ConsoleScreenBufferInfo]; lpConsoleScreenBufferInfo
0x14003ba0c  mov     rcx, rbx; hConsoleOutput
0x14003ba0f  call    cs:__imp_GetConsoleScreenBufferInfo
0x14003ba15  test    eax, eax
0x14003ba17  jnz     short loc_14003BA31
0x14003ba19  call    cs:__imp_GetLastError
0x14003ba1f  test    eax, eax
0x14003ba21  jz      short loc_14003BA42
0x14003ba23  jle     short loc_14003BA2F
0x14003ba25  movzx   eax, ax
0x14003ba28  or      eax, 80070000h
0x14003ba2d  test    eax, eax
0x14003ba2f  js      short loc_14003BA42
0x14003ba31  movzx   eax, [rsp+78h+ConsoleScreenBufferInfo.srWindow.Right]
0x14003ba36  sub     ax, [rsp+78h+ConsoleScreenBufferInfo.srWindow.Left]
0x14003ba3b  mov     cs:?g_Width@@3GA, ax; ushort g_Width
0x14003ba42  xor     ecx, ecx; struct ARGUMENT *
0x14003ba44  call    ?ArgRegister@@YAXPEAVARGUMENT@@@Z; ArgRegister(ARGUMENT *)
0x14003ba49  cmp     cs:dword_140060D14, 0
0x14003ba50  jz      short loc_14003BA71
0x14003ba52  lea     rax, ?GuidHead@@3PEAUGUID_POST_PROCESS_DATA@@EA.Data4; GUID_POST_PROCESS_DATA * GuidHead ...
0x14003ba59  mov     cs:dword_140060D14, 0
0x14003ba63  mov     cs:qword_140083420, rax
0x14003ba6a  mov     qword ptr cs:?GuidHead@@3PEAUGUID_POST_PROCESS_DATA@@EA.Data4, rax; GUID_POST_PROCESS_DATA * GuidHead ...
0x14003ba71  call    ?ArgpLoadArguments@@YAJXZ; ArgpLoadArguments(void)
0x14003ba76  test    eax, eax
0x14003ba78  js      loc_14003BB9B
0x14003ba7e  lea     r8, [rsp+78h+var_58]; struct _ARGUMENT_INPUT **
0x14003ba83  mov     rdx, rdi; unsigned __int16 **
0x14003ba86  mov     ecx, esi; int
0x14003ba88  call    ?ArgpCmdInitialize@@YAJHPEAPEAGPEAPEAU_ARGUMENT_INPUT@@@Z; ArgpCmdInitialize(int,ushort * *,_ARGUMENT_INPUT * *)
0x14003ba8d  test    eax, eax
0x14003ba8f  js      loc_14003BB9B
0x14003ba95  mov     rcx, [rsp+78h+var_58]; struct _ARGUMENT_INPUT *
0x14003ba9a  xor     ebx, ebx
0x14003ba9c  lea     r14d, [rbx+1]
0x14003baa0  mov     edx, r14d; int
0x14003baa3  call    ?ArgpParseFromInput@@YAJPEAU_ARGUMENT_INPUT@@H@Z; ArgpParseFromInput(_ARGUMENT_INPUT *,int)
0x14003baa8  test    eax, eax
0x14003baaa  cmovs   ebx, eax
0x14003baad  cmp     cs:dword_140060E84, 0
0x14003bab4  jz      short loc_14003BAE7
0x14003bab6  mov     rcx, cs:FileName; FileName
0x14003babd  test    rcx, rcx
0x14003bac0  jz      short loc_14003BAE7
0x14003bac2  lea     rdx, [rsp+78h+var_58]; struct _ARGUMENT_INPUT **
0x14003bac7  call    ?ArgpFileInitialize@@YAJPEBGPEAPEAU_ARGUMENT_INPUT@@@Z; ArgpFileInitialize(ushort const *,_ARGUMENT_INPUT * *)
0x14003bacc  test    eax, eax
0x14003bace  js      loc_14003BB9B
0x14003bad4  mov     rcx, [rsp+78h+var_58]; struct _ARGUMENT_INPUT *
0x14003bad9  lea     edx, [r14+1]; int
0x14003badd  call    ?ArgpParseFromInput@@YAJPEAU_ARGUMENT_INPUT@@H@Z; ArgpParseFromInput(_ARGUMENT_INPUT *,int)
0x14003bae2  test    eax, eax
0x14003bae4  cmovs   ebx, eax
0x14003bae7  cmp     cs:?g_Debug@@3HA, 0; int g_Debug
0x14003baee  jz      short loc_14003BAF5
0x14003baf0  call    ?ArgpPrintDebugInfo@@YAXXZ; ArgpPrintDebugInfo(void)
0x14003baf5  cmp     cs:dword_140060E04, 0
0x14003bafc  jz      short loc_14003BB7B
0x14003bafe  mov     rcx, cs:?g_ArgsHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ArgsHead
0x14003bb05  lea     rdx, ?g_ArgsHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ArgsHead
0x14003bb0c  mov     r8d, 200h
0x14003bb12  mov     rax, rcx
0x14003bb15  or      cs:dword_140060DCC, r8d
0x14003bb1c  mov     rsi, [rdi]
0x14003bb1f  cmp     rcx, rdx
0x14003bb22  jz      short loc_14003BB38
0x14003bb24  cmp     dword ptr [rax+64h], 0
0x14003bb28  jz      short loc_14003BB30
0x14003bb2a  test    [rax+2Ch], r8d
0x14003bb2e  jz      short loc_14003BB3C
0x14003bb30  mov     rax, [rax]
0x14003bb33  cmp     rax, rdx
0x14003bb36  jnz     short loc_14003BB24
0x14003bb38  xor     edi, edi
0x14003bb3a  jmp     short loc_14003BB4F
0x14003bb3c  mov     edi, r14d
0x14003bb3f  jmp     short loc_14003BB54
0x14003bb41  mov     eax, [rcx+2Ch]
0x14003bb44  test    al, 10h
0x14003bb46  jnz     short loc_14003BB4C
0x14003bb48  mov     [rcx+54h], r14d
0x14003bb4c  mov     rcx, [rcx]
0x14003bb4f  cmp     rcx, rdx
0x14003bb52  jnz     short loc_14003BB41
0x14003bb54  mov     ecx, r14d; int
0x14003bb57  call    ?ArgApplyRules@@YAJH@Z; ArgApplyRules(int)
0x14003bb5c  mov     ecx, eax; int
0x14003bb5e  call    ?ArgpFindBadArguments@@YAJJ@Z; ArgpFindBadArguments(long)
0x14003bb63  test    eax, eax
0x14003bb65  js      short loc_14003BB9B
0x14003bb67  mov     rcx, rsi; unsigned __int16 *
0x14003bb6a  call    ?ArgpPrintUsage@@YAXPEBG@Z; ArgpPrintUsage(ushort const *)
0x14003bb6f  mov     ecx, edi; int
0x14003bb71  call    ?ArgpPrintArguments@@YAXH@Z; ArgpPrintArguments(int)
0x14003bb76  mov     eax, r14d
0x14003bb79  jmp     short loc_14003BB89
0x14003bb7b  xor     ecx, ecx; int
0x14003bb7d  call    ?ArgApplyRules@@YAJH@Z; ArgApplyRules(int)
0x14003bb82  mov     ecx, eax; int
0x14003bb84  call    ?ArgpFindBadArguments@@YAJJ@Z; ArgpFindBadArguments(long)
0x14003bb89  test    eax, eax
0x14003bb8b  js      short loc_14003BB9B
0x14003bb8d  cmp     eax, r14d
0x14003bb90  jz      short loc_14003BB9B
0x14003bb92  mov     eax, ebx
0x14003bb94  jmp     short loc_14003BB9B
0x14003bb96  mov     eax, 80070057h
0x14003bb9b  mov     rcx, [rsp+78h+var_38]
0x14003bba0  xor     rcx, rsp; StackCookie
0x14003bba3  call    __security_check_cookie
0x14003bba8  add     rsp, 58h
0x14003bbac  pop     r14
0x14003bbae  pop     rdi
0x14003bbaf  pop     rsi
0x14003bbb0  pop     rbx
0x14003bbb1  retn
```
