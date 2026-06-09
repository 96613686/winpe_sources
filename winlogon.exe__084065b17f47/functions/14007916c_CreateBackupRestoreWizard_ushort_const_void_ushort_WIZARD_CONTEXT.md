# CreateBackupRestoreWizard(ushort const *,void *,ushort,_WIZARD_CONTEXT * *)

- ea: `0x14007916c`
- end: `0x1400794b0`
- name: `?CreateBackupRestoreWizard@@YAKPEBGPEAXGPEAPEAU_WIZARD_CONTEXT@@@Z`
- size: `836`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, void *, unsigned __int16, struct _WIZARD_CONTEXT **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400794b8`

## callees

- `0x1400057f4`
- `0x14000d4e0`
- `0x1400198e0`
- `0x14001a200`
- `0x140035f30`
- `0x14003de48`
- `0x140041c34`
- `0x140053720`
- `0x1400544e0`
- `0x14007916c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14007924b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14007924b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007925d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400793b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007925d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400793b6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1400793ac`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1400793ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400792b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400792b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007945d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140079477`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140079487`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009fc86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009fca0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009fcb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007945d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140079477`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140079487`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009fc86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009fca0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009fcb0`

## string_xrefs

- `0x1400792d9`: `%s %c "%s" /proceid=%u /usertoken=%I64u /stopevent=%I64u`

## pseudocode

```c
__int64 __fastcall CreateBackupRestoreWizard(
        const unsigned __int16 *a1,
        void *a2,
        unsigned __int16 a3,
        struct _WIZARD_CONTEXT **a4)
{
  int v5; // r12d
  _OWORD *v8; // rax
  __int64 v9; // r9
  _OWORD *v10; // rdi
  DWORD LastError; // ebx
  HANDLE EventW; // rbx
  CUser *v13; // rcx
  __int64 v14; // rdx
  void *v15; // rcx
  DWORD lpEnvironment; // [rsp+30h] [rbp-518h]
  void *v18; // [rsp+58h] [rbp-4F0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-4E8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-4C8h] BYREF
  WCHAR CommandLine[520]; // [rsp+F0h] [rbp-458h] BYREF

  v5 = a3;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(CommandLine, 0, sizeof(CommandLine));
  v8 = WLAlloc(0x10u);
  v10 = v8;
  v18 = v8;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids, v9);
    }
    LastError = 14;
    goto LABEL_29;
  }
  *v8 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)v10 + 1) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v14 = 11;
    goto LABEL_12;
  }
  lpEnvironment = GetCurrentProcessId();
  if ( (unsigned int)StringCchPrintfW(
                       CommandLine,
                       0x208u,
                       L"%s %c \"%s\" /proceid=%u /usertoken=%I64u /stopevent=%I64u",
                       L"credwiz.exe",
                       v5,
                       a1,
                       lpEnvironment,
                       a2,
                       EventW) )
  {
    LastError = 87;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v14 = 12;
    goto LABEL_12;
  }
  StartupInfo.cb = 104;
  StartupInfo.dwFlags = 257;
  StartupInfo.wShowWindow = 1;
  StartupInfo.lpDesktop = L"Winsta0\\Winlogon";
  if ( !CreateProcessW(0, CommandLine, 0, 0, 1, 4u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    LastError = GetLastError();
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v14 = 13;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids, LastError);
    goto LABEL_29;
  }
  LastError = StartProcessInJob(&ProcessInformation, 0, (struct _WINLOGON_JOB **)v10);
  if ( !LastError )
  {
    *a4 = (struct _WIZARD_CONTEXT *)v10;
    v10 = 0;
    v18 = 0;
    LastError = 0;
    goto LABEL_29;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 14;
    goto LABEL_12;
  }
LABEL_29:
  if ( LastError && v10 )
  {
    if ( *(_QWORD *)v10 )
      DeletepJob((struct _WINLOGON_JOB **)v10, 0);
    v15 = (void *)*((_QWORD *)v10 + 1);
    if ( v15 )
      CloseHandle(v15);
    UHHeapFree(&v18);
  }
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  return LastError;
}

```

## disassembly

```asm
0x14007916c  push    rbx
0x14007916e  push    rsi
0x14007916f  push    rdi
0x140079170  push    r12
0x140079172  push    r14
0x140079174  push    r15
0x140079176  sub     rsp, 518h
0x14007917d  mov     rax, cs:__security_cookie
0x140079184  xor     rax, rsp
0x140079187  mov     [rsp+548h+var_48], rax
0x14007918f  mov     r14, r9
0x140079192  movzx   r12d, r8w
0x140079196  mov     r15, rdx
0x140079199  mov     rsi, rcx
0x14007919c  mov     [rsp+548h+var_4F0], 0
0x1400791a5  mov     [rsp+548h+var_4F8], 0
0x1400791ad  xor     edx, edx; Val
0x1400791af  lea     r8d, [rdx+68h]; Size
0x1400791b3  lea     rcx, [rsp+548h+StartupInfo]; void *
0x1400791bb  call    memset_0
0x1400791c0  xorps   xmm0, xmm0
0x1400791c3  xor     eax, eax
0x1400791c5  movups  xmmword ptr [rsp+548h+ProcessInformation.hProcess], xmm0
0x1400791ca  mov     qword ptr [rsp+548h+ProcessInformation.dwProcessId], rax
0x1400791cf  xor     edx, edx; Val
0x1400791d1  mov     r8d, 410h; Size
0x1400791d7  lea     rcx, [rsp+548h+CommandLine]; void *
0x1400791df  call    memset_0
0x1400791e4  nop
0x1400791e5  mov     ecx, 10h; unsigned __int64
0x1400791ea  call    ?WLAlloc@@YAPEAX_K@Z; WLAlloc(unsigned __int64)
0x1400791ef  mov     rdi, rax
0x1400791f2  mov     [rsp+548h+var_4F0], rax
0x1400791f7  test    rax, rax
0x1400791fa  jnz     short loc_14007923B
0x1400791fc  lea     rax, WPP_GLOBAL_Control
0x140079203  mov     rcx, cs:WPP_GLOBAL_Control
0x14007920a  cmp     rcx, rax
0x14007920d  jz      short loc_140079231
0x14007920f  lea     esi, [rdi+1]
0x140079212  test    [rcx+1Ch], sil
0x140079216  jz      short loc_140079231
0x140079218  cmp     byte ptr [rcx+19h], 2
0x14007921c  jb      short loc_140079231
0x14007921e  lea     edx, [rdi+0Ah]
0x140079221  lea     r8, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids
0x140079228  mov     rcx, [rcx+10h]
0x14007922c  call    WPP_SF_
0x140079231  mov     ebx, 0Eh
0x140079236  jmp     loc_140079437
0x14007923b  xorps   xmm0, xmm0
0x14007923e  movups  xmmword ptr [rax], xmm0
0x140079241  xor     r9d, r9d; lpName
0x140079244  xor     r8d, r8d; bInitialState
0x140079247  xor     edx, edx; bManualReset
0x140079249  xor     ecx, ecx; lpEventAttributes
0x14007924b  call    cs:__imp_CreateEventW
0x140079251  mov     rbx, rax
0x140079254  mov     [rdi+8], rax
0x140079258  test    rax, rax
0x14007925b  jnz     short loc_1400792B4
0x14007925d  call    cs:__imp_GetLastError
0x140079263  mov     ebx, eax
0x140079265  mov     [rsp+548h+var_4F8], eax
0x140079269  lea     rax, WPP_GLOBAL_Control
0x140079270  mov     rcx, cs:WPP_GLOBAL_Control
0x140079277  cmp     rcx, rax
0x14007927a  jz      loc_14007943B
0x140079280  mov     esi, 1
0x140079285  test    [rcx+1Ch], sil
0x140079289  jz      loc_14007943B
0x14007928f  cmp     byte ptr [rcx+19h], 2
0x140079293  jb      loc_14007943B
0x140079299  lea     edx, [rsi+0Ah]
0x14007929c  mov     r9d, ebx
0x14007929f  lea     r8, WPP_e431f3cf7a823dcb3dd35d1d8ef9f9e1_Traceguids
0x1400792a6  mov     rcx, [rcx+10h]
0x1400792aa  call    WPP_SF_d
0x1400792af  jmp     loc_14007943B
0x1400792b4  call    cs:__imp_GetCurrentProcessId
0x1400792ba  mov     [rsp+548h+lpStartupInfo], rbx
0x1400792bf  mov     [rsp+548h+lpCurrentDirectory], r15
0x1400792c4  mov     dword ptr [rsp+548h+lpEnvironment], eax
0x1400792c8  mov     qword ptr [rsp+548h+dwCreationFlags], rsi
0x1400792cd  mov     [rsp+548h+bInheritHandles], r12d
0x1400792d2  lea     r9, aCredwizExe; "credwiz.exe"
0x1400792d9  lea     r8, aSCSProceidUUse; "%s %c \"%s\" /proceid=%u /usertoken=%I6"...
0x1400792e0  mov     edx, 208h; unsigned __int64
0x1400792e5  lea     rcx, [rsp+548h+CommandLine]; unsigned __int16 *
0x1400792ed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400792f2  test    eax, eax
0x1400792f4  jz      short loc_140079335
0x1400792f6  mov     ebx, 57h ; 'W'
0x1400792fb  mov     [rsp+548h+var_4F8], ebx
0x1400792ff  lea     rax, WPP_GLOBAL_Control
0x140079306  mov     rcx, cs:WPP_GLOBAL_Control
0x14007930d  cmp     rcx, rax
0x140079310  jz      loc_14007943B
0x140079316  lea     esi, [rbx-56h]
0x140079319  test    [rcx+1Ch], sil
0x14007931d  jz      loc_14007943B
0x140079323  cmp     byte ptr [rcx+19h], 2
0x140079327  jb      loc_14007943B
0x14007932d  lea     edx, [rbx-4Bh]
0x140079330  jmp     loc_14007929C
0x140079335  mov     [rsp+548h+StartupInfo.cb], 68h ; 'h'
0x140079340  mov     [rsp+548h+StartupInfo.dwFlags], 101h
0x14007934b  mov     esi, 1
0x140079350  mov     [rsp+548h+StartupInfo.wShowWindow], si
0x140079358  lea     rax, aWinsta0Winlogo; "Winsta0\\Winlogon"
0x14007935f  mov     [rsp+548h+StartupInfo.lpDesktop], rax
0x140079367  lea     rax, [rsp+548h+ProcessInformation]
0x14007936c  mov     [rsp+548h+lpProcessInformation], rax; lpProcessInformation
0x140079371  lea     rax, [rsp+548h+StartupInfo]
0x140079379  mov     [rsp+548h+lpStartupInfo], rax; lpStartupInfo
0x14007937e  mov     [rsp+548h+lpCurrentDirectory], 0; lpCurrentDirectory
0x140079387  mov     [rsp+548h+lpEnvironment], 0; lpEnvironment
0x140079390  mov     [rsp+548h+dwCreationFlags], 4; dwCreationFlags
0x140079398  mov     [rsp+548h+bInheritHandles], esi; bInheritHandles
0x14007939c  xor     r9d, r9d; lpThreadAttributes
0x14007939f  xor     r8d, r8d; lpProcessAttributes
0x1400793a2  lea     rdx, [rsp+548h+CommandLine]; lpCommandLine
0x1400793aa  xor     ecx, ecx; lpApplicationName
0x1400793ac  call    cs:__imp_CreateProcessW
0x1400793b2  test    eax, eax
0x1400793b4  jnz     short loc_1400793E9
0x1400793b6  call    cs:__imp_GetLastError
0x1400793bc  mov     ebx, eax
0x1400793be  mov     [rsp+548h+var_4F8], eax
0x1400793c2  lea     rax, WPP_GLOBAL_Control
0x1400793c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400793d0  cmp     rcx, rax
0x1400793d3  jz      short loc_14007943B
0x1400793d5  test    [rcx+1Ch], sil
0x1400793d9  jz      short loc_14007943B
0x1400793db  cmp     byte ptr [rcx+19h], 2
0x1400793df  jb      short loc_14007943B
0x1400793e1  lea     edx, [rsi+0Ch]
0x1400793e4  jmp     loc_14007929C
0x1400793e9  mov     r8, rdi; struct _WINLOGON_JOB **
0x1400793ec  xor     edx, edx; unsigned int
0x1400793ee  lea     rcx, [rsp+548h+ProcessInformation]; struct _PROCESS_INFORMATION *
0x1400793f3  call    ?StartProcessInJob@@YAKPEAU_PROCESS_INFORMATION@@KPEAPEAU_WINLOGON_JOB@@@Z; StartProcessInJob(_PROCESS_INFORMATION *,ulong,_WINLOGON_JOB * *)
0x1400793f8  mov     ebx, eax
0x1400793fa  mov     [rsp+548h+var_4F8], eax
0x1400793fe  test    eax, eax
0x140079400  jz      short loc_14007942B
0x140079402  lea     rax, WPP_GLOBAL_Control
0x140079409  mov     rcx, cs:WPP_GLOBAL_Control
0x140079410  cmp     rcx, rax
0x140079413  jz      short loc_14007943B
0x140079415  test    [rcx+1Ch], sil
0x140079419  jz      short loc_14007943B
0x14007941b  cmp     byte ptr [rcx+19h], 2
0x14007941f  jb      short loc_14007943B
0x140079421  mov     edx, 0Eh
0x140079426  jmp     loc_14007929C
0x14007942b  mov     [r14], rdi
0x14007942e  xor     edi, edi
0x140079430  mov     [rsp+548h+var_4F0], rdi
0x140079435  xor     ebx, ebx
0x140079437  mov     [rsp+548h+var_4F8], ebx
0x14007943b  test    ebx, ebx
0x14007943d  jz      short loc_14007946D
0x14007943f  test    rdi, rdi
0x140079442  jz      short loc_14007946D
0x140079444  cmp     qword ptr [rdi], 0
0x140079448  jz      short loc_140079454
0x14007944a  xor     edx, edx; int
0x14007944c  mov     rcx, rdi; struct _WINLOGON_JOB **
0x14007944f  call    ?DeletepJob@@YAXPEAPEAU_WINLOGON_JOB@@H@Z; DeletepJob(_WINLOGON_JOB * *,int)
0x140079454  mov     rcx, [rdi+8]; hObject
0x140079458  test    rcx, rcx
0x14007945b  jz      short loc_140079463
0x14007945d  call    cs:__imp_CloseHandle
0x140079463  lea     rcx, [rsp+548h+var_4F0]
0x140079468  call    UHHeapFree
0x14007946d  mov     rcx, [rsp+548h+ProcessInformation.hProcess]; hObject
0x140079472  test    rcx, rcx
0x140079475  jz      short loc_14007947D
0x140079477  call    cs:__imp_CloseHandle
0x14007947d  mov     rcx, [rsp+548h+ProcessInformation.hThread]; hObject
0x140079482  test    rcx, rcx
0x140079485  jz      short loc_14007948D
0x140079487  call    cs:__imp_CloseHandle
0x14007948d  mov     eax, ebx
0x14007948f  mov     rcx, [rsp+548h+var_48]
0x140079497  xor     rcx, rsp; StackCookie
0x14007949a  call    __security_check_cookie
0x14007949f  add     rsp, 518h
0x1400794a6  pop     r15
0x1400794a8  pop     r14
0x1400794aa  pop     r12
0x1400794ac  pop     rdi
0x1400794ad  pop     rsi
0x1400794ae  pop     rbx
0x1400794af  retn
0x14009fc51  push    rbx
0x14009fc53  push    rbp
0x14009fc54  sub     rsp, 58h
0x14009fc58  mov     rbp, rdx
0x14009fc5b  cmp     dword ptr [rbp+50h], 0
0x14009fc5f  jz      short loc_14009FC97
0x14009fc61  mov     rbx, [rbp+58h]
0x14009fc65  test    rbx, rbx
0x14009fc68  jz      short loc_14009FC97
0x14009fc6a  cmp     qword ptr [rbx], 0
0x14009fc6e  jz      short loc_14009FC7B
0x14009fc70  xor     edx, edx; int
0x14009fc72  mov     rcx, rbx; struct _WINLOGON_JOB **
0x14009fc75  call    ?DeletepJob@@YAXPEAPEAU_WINLOGON_JOB@@H@Z; DeletepJob(_WINLOGON_JOB * *,int)
0x14009fc7a  nop
0x14009fc7b  cmp     qword ptr [rbx+8], 0
0x14009fc80  jz      short loc_14009FC8D
0x14009fc82  mov     rcx, [rbx+8]; hObject
0x14009fc86  call    cs:__imp_CloseHandle
0x14009fc8c  nop
0x14009fc8d  lea     rcx, [rbp+58h]
0x14009fc91  call    UHHeapFree
0x14009fc96  nop
0x14009fc97  mov     rcx, [rbp+60h]; hObject
0x14009fc9b  test    rcx, rcx
0x14009fc9e  jz      short loc_14009FCA7
0x14009fca0  call    cs:__imp_CloseHandle
0x14009fca6  nop
0x14009fca7  mov     rcx, [rbp+68h]; hObject
0x14009fcab  test    rcx, rcx
0x14009fcae  jz      short loc_14009FCB7
0x14009fcb0  call    cs:__imp_CloseHandle
0x14009fcb6  nop
0x14009fcb7  add     rsp, 58h
0x14009fcbb  pop     rbp
0x14009fcbc  pop     rbx
0x14009fcbd  retn
```
