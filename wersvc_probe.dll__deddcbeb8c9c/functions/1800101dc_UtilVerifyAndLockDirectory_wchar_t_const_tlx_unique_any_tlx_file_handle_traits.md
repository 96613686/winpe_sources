# UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x1800101dc`
- end: `0x1800106ee`
- name: `?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `1298`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e0a0`
- `0x180018c5c`
- `0x180032c40`
- `0x180032e2c`
- `0x180033274`

## callees

- `0x1800029d0`
- `0x180006aa8`
- `0x180007c88`
- `0x18000cb10`
- `0x1800101dc`
- `0x1800106f4`
- `0x180012004`
- `0x180013494`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001032b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001032b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800103a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800105f1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800102fa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800102fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010317`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001053d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800105ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800105e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001066a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800106a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800106be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010317`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001053d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800105ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800105e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001066a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800106a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800106be`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001038e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001038e`
- `ntdll!RtlInitUnicodeString` at `0x180010495`
- `ntdll!RtlInitUnicodeString` at `0x180010495`
- `ntdll!NtCreateFile` at `0x180010518`
- `ntdll!NtCreateFile` at `0x180010518`
- `ext-ms-win-wer-xbox-l1-2-0!XerShouldWerManageRootDirectory` at `0x180010234`
- `ext-ms-win-wer-xbox-l1-2-0!XerShouldWerManageRootDirectory` at `0x180010234`

## string_xrefs

- `0x18001025a`: `onecore\windows\feedback\core\common\lib\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilVerifyAndLockDirectory(wchar_t *a1, void **a2)
{
  int v4; // ebx
  void *v5; // r14
  HANDLE *v6; // rcx
  int v7; // edx
  WCHAR *v8; // r9
  int v9; // esi
  int v10; // r8d
  int v11; // r9d
  HANDLE FileW; // r15
  void *v13; // rcx
  signed int v14; // eax
  signed int v15; // eax
  int AsString; // eax
  void **v17; // rax
  NTSTATUS v18; // ebx
  void *v19; // rcx
  HANDLE v20; // rdx
  void *v21; // rcx
  signed int LastError; // eax
  void *v23; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  char dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  HANDLE v30; // [rsp+A8h] [rbp-58h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  void *v32; // [rsp+C0h] [rbp-40h] BYREF
  void **v33; // [rsp+C8h] [rbp-38h]
  WCHAR SourceString[40]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v4 = 0;
  hObject = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  v5 = 0;
  if ( !(unsigned __int8)XerShouldWerManageRootDirectory() )
    goto LABEL_66;
  if ( !a1 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16E4,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    goto LABEL_75;
  }
  if ( !a2 )
  {
    v4 = -2147024809;
    v6 = (HANDLE *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_67;
    v7 = 174;
LABEL_8:
    dwCreationDispositiona = v4;
LABEL_9:
    LODWORD(v8) = (_DWORD)a1;
    goto LABEL_65;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, a1);
  v9 = 0;
  while ( 1 )
  {
    FileW = CreateFileW(a1, 0xC0000000, 1u, 0, 3u, 0x2000000u, 0);
    v13 = v5;
    v5 = FileW;
    v30 = FileW;
    if ( (unsigned __int64)v13 + 1 > 1 )
      CloseHandle(v13);
    if ( (unsigned __int64)FileW + 1 > 1 )
    {
      AsString = UtilVerifyFilePath(a1, FileW, v10, v11);
      v4 = AsString;
      if ( AsString >= 0 )
      {
        AsString = UtilUuidCreateAsString(SourceString);
        v4 = AsString;
        if ( AsString >= 0 )
        {
          RtlInitUnicodeString(&DestinationString, SourceString);
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = FileW;
          ObjectAttributes.Attributes = 64;
          ObjectAttributes.ObjectName = &DestinationString;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v17 = (void **)utl::out_ptr<void,tlx::unique_any<tlx::file_handle_traits>,>(&v32, &hObject);
          v18 = NtCreateFile(v17, 0xC0010000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 2u, 0x1000u, 0, 0);
          if ( v32 )
          {
            v19 = *v33;
            *v33 = v32;
            if ( (unsigned __int64)v19 + 1 > 1 )
              CloseHandle(v19);
          }
          v20 = hObject;
          if ( (unsigned __int64)hObject + 1 > 1 )
          {
            if ( v18 >= 0 )
            {
              hObject = 0;
              v21 = *a2;
              *a2 = v20;
              if ( (unsigned __int64)v21 + 1 > 1 )
                CloseHandle(v21);
              v4 = 0;
            }
            else
            {
              v4 = v18 | 0x10000000;
              v6 = (HANDLE *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  182,
                  (unsigned int)&WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
                  (unsigned int)SourceString,
                  v4);
                v20 = hObject;
                v6 = (HANDLE *)WPP_GLOBAL_Control;
              }
              hObject = 0;
              if ( (unsigned __int64)v20 + 1 <= 1 )
                goto LABEL_67;
              CloseHandle(v20);
            }
LABEL_66:
            v6 = (HANDLE *)WPP_GLOBAL_Control;
            goto LABEL_67;
          }
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          if ( v4 >= 0 )
            v4 = -2147467259;
          v6 = (HANDLE *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_67;
          v7 = 181;
          dwCreationDispositiona = v4;
          v8 = SourceString;
LABEL_65:
          WPP_SF_Sd(
            (unsigned int)v6[2],
            v7,
            (unsigned int)&WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
            (_DWORD)v8,
            dwCreationDispositiona);
          goto LABEL_66;
        }
        v6 = (HANDLE *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_67;
        v7 = 180;
      }
      else
      {
        v6 = (HANDLE *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_67;
        v7 = 179;
      }
      dwCreationDispositiona = AsString;
      goto LABEL_9;
    }
    v14 = GetLastError();
    v4 = v14;
    if ( v14 > 0 )
      v4 = (unsigned __int16)v14 | 0x80070000;
    if ( v4 >= 0 )
      break;
    if ( v4 != -2147024864 )
      goto LABEL_33;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        176,
        (unsigned int)&WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
        (_DWORD)a1,
        v9);
    Sleep(0x14u);
    if ( ++v9 >= 1000 )
    {
      v15 = GetLastError();
      v4 = v15;
      if ( v15 > 0 )
        v4 = (unsigned __int16)v15 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147467259;
      v6 = (HANDLE *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 178;
        goto LABEL_8;
      }
      goto LABEL_67;
    }
  }
  v4 = -2147467259;
LABEL_33:
  v6 = (HANDLE *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 177;
    goto LABEL_8;
  }
LABEL_67:
  if ( (unsigned __int64)v5 + 1 > 1 )
  {
    v23 = v5;
    v5 = 0;
    if ( (unsigned __int64)v23 + 1 > 1 )
    {
      CloseHandle(v23);
      v6 = (HANDLE *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
      WPP_SF_S(v6[2], 183, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, a1);
  }
  if ( (unsigned __int64)v5 + 1 > 1 )
    CloseHandle(v5);
LABEL_75:
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800101dc  mov     [rsp-8+arg_10], rbx
0x1800101e1  mov     [rsp-8+arg_18], rsi
0x1800101e6  push    rbp
0x1800101e7  push    rdi
0x1800101e8  push    r12
0x1800101ea  push    r14
0x1800101ec  push    r15
0x1800101ee  lea     rbp, [rsp-40h]
0x1800101f3  sub     rsp, 140h
0x1800101fa  mov     rax, cs:__security_cookie
0x180010201  xor     rax, rsp
0x180010204  mov     [rbp+60h+var_30], rax
0x180010208  mov     r12, rdx
0x18001020b  mov     rdi, rcx
0x18001020e  xor     ebx, ebx
0x180010210  mov     [rsp+160h+hObject], rbx
0x180010215  xorps   xmm0, xmm0
0x180010218  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm0
0x18001021c  xorps   xmm1, xmm1
0x18001021f  movups  xmmword ptr [rsp+160h+ObjectAttributes.Length], xmm1
0x180010224  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm1
0x180010228  movups  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm1
0x18001022c  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x180010231  xor     r14d, r14d
0x180010234  call    cs:__imp_XerShouldWerManageRootDirectory
0x18001023a  lea     r15, WPP_GLOBAL_Control
0x180010241  test    al, al
0x180010243  jz      loc_180010646
0x180010249  test    rdi, rdi
0x18001024c  jnz     short loc_180010271
0x18001024e  mov     rcx, [rbp+68h]; this
0x180010252  mov     ebx, 80070057h
0x180010257  mov     r9d, ebx; char *
0x18001025a  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\commo"...
0x180010261  mov     edx, 16E4h; void *
0x180010266  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001026b  nop
0x18001026c  jmp     loc_1800106AF
0x180010271  test    r12, r12
0x180010274  jnz     short loc_1800102A6
0x180010276  mov     ebx, 80070057h
0x18001027b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010282  cmp     rcx, r15
0x180010285  jz      loc_18001064D
0x18001028b  test    byte ptr [rcx+1Ch], 1
0x18001028f  jz      loc_18001064D
0x180010295  mov     edx, 0AEh
0x18001029a  mov     [rsp+160h+dwCreationDisposition], ebx
0x18001029e  mov     r9, rdi
0x1800102a1  jmp     loc_180010636
0x1800102a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102ad  cmp     rcx, r15
0x1800102b0  jz      short loc_1800102D0
0x1800102b2  test    byte ptr [rcx+1Ch], 4
0x1800102b6  jz      short loc_1800102D0
0x1800102b8  mov     edx, 0AFh
0x1800102bd  mov     r9, rdi
0x1800102c0  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800102c7  mov     rcx, [rcx+10h]
0x1800102cb  call    WPP_SF_S
0x1800102d0  xor     esi, esi
0x1800102d2  mov     [rsp+160h+hTemplateFile], 0; hTemplateFile
0x1800102db  mov     [rsp+160h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800102e3  mov     [rsp+160h+dwCreationDisposition], 3; dwCreationDisposition
0x1800102eb  xor     r9d, r9d; lpSecurityAttributes
0x1800102ee  mov     edx, 0C0000000h; dwDesiredAccess
0x1800102f3  lea     r8d, [r9+1]; dwShareMode
0x1800102f7  mov     rcx, rdi; lpFileName
0x1800102fa  call    cs:__imp_CreateFileW
0x180010300  mov     r15, rax
0x180010303  mov     rcx, r14; hObject
0x180010306  mov     r14, rax
0x180010309  mov     [rbp+60h+var_B8], rax
0x18001030d  lea     rax, [rcx+1]
0x180010311  cmp     rax, 1
0x180010315  jbe     short loc_18001031D
0x180010317  call    cs:__imp_CloseHandle
0x18001031d  lea     rax, [r15+1]
0x180010321  cmp     rax, 1
0x180010325  ja      loc_180010415
0x18001032b  call    cs:__imp_GetLastError
0x180010331  mov     ebx, eax
0x180010333  test    eax, eax
0x180010335  jle     short loc_180010340
0x180010337  movzx   ebx, ax
0x18001033a  or      ebx, 80070000h
0x180010340  test    ebx, ebx
0x180010342  jns     loc_1800103E5
0x180010348  cmp     ebx, 80070020h
0x18001034e  jnz     loc_1800103EA
0x180010354  mov     rcx, cs:WPP_GLOBAL_Control
0x18001035b  lea     r15, WPP_GLOBAL_Control
0x180010362  cmp     rcx, r15
0x180010365  jz      short loc_180010389
0x180010367  test    byte ptr [rcx+1Ch], 2
0x18001036b  jz      short loc_180010389
0x18001036d  mov     edx, 0B0h
0x180010372  mov     [rsp+160h+dwCreationDisposition], esi
0x180010376  mov     r9, rdi
0x180010379  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180010380  mov     rcx, [rcx+10h]
0x180010384  call    WPP_SF_Sd
0x180010389  mov     ecx, 14h; dwMilliseconds
0x18001038e  call    cs:__imp_Sleep
0x180010394  inc     esi
0x180010396  cmp     esi, 3E8h
0x18001039c  jl      loc_1800102D2
0x1800103a2  call    cs:__imp_GetLastError
0x1800103a8  mov     ebx, eax
0x1800103aa  test    eax, eax
0x1800103ac  jle     short loc_1800103B7
0x1800103ae  movzx   ebx, ax
0x1800103b1  or      ebx, 80070000h
0x1800103b7  mov     eax, 80004005h
0x1800103bc  test    ebx, ebx
0x1800103be  cmovns  ebx, eax
0x1800103c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103c8  cmp     rcx, r15
0x1800103cb  jz      loc_18001064D
0x1800103d1  test    byte ptr [rcx+1Ch], 1
0x1800103d5  jz      loc_18001064D
0x1800103db  mov     edx, 0B2h
0x1800103e0  jmp     loc_18001029A
0x1800103e5  mov     ebx, 80004005h
0x1800103ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103f1  lea     r15, WPP_GLOBAL_Control
0x1800103f8  cmp     rcx, r15
0x1800103fb  jz      loc_18001064D
0x180010401  test    byte ptr [rcx+1Ch], 1
0x180010405  jz      loc_18001064D
0x18001040b  mov     edx, 0B1h
0x180010410  jmp     loc_18001029A
0x180010415  mov     rdx, r15; void *
0x180010418  mov     rcx, rdi; wchar_t *
0x18001041b  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x180010420  mov     ebx, eax
0x180010422  test    eax, eax
0x180010424  jns     short loc_180010455
0x180010426  mov     rcx, cs:WPP_GLOBAL_Control
0x18001042d  lea     r15, WPP_GLOBAL_Control
0x180010434  cmp     rcx, r15
0x180010437  jz      loc_18001064D
0x18001043d  test    byte ptr [rcx+1Ch], 1
0x180010441  jz      loc_18001064D
0x180010447  mov     edx, 0B3h
0x18001044c  mov     [rsp+160h+dwCreationDisposition], eax
0x180010450  jmp     loc_18001029E
0x180010455  lea     rcx, [rbp+60h+SourceString]; wchar_t *
0x180010459  call    ?UtilUuidCreateAsString@@YAJPEA_W@Z; UtilUuidCreateAsString(wchar_t *)
0x18001045e  mov     ebx, eax
0x180010460  test    eax, eax
0x180010462  jns     short loc_18001048C
0x180010464  mov     rcx, cs:WPP_GLOBAL_Control
0x18001046b  lea     r15, WPP_GLOBAL_Control
0x180010472  cmp     rcx, r15
0x180010475  jz      loc_18001064D
0x18001047b  test    byte ptr [rcx+1Ch], 1
0x18001047f  jz      loc_18001064D
0x180010485  mov     edx, 0B4h
0x18001048a  jmp     short loc_18001044C
0x18001048c  lea     rdx, [rbp+60h+SourceString]; SourceString
0x180010490  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x180010495  call    cs:__imp_RtlInitUnicodeString
0x18001049b  mov     [rsp+160h+ObjectAttributes.Length], 30h ; '0'
0x1800104a3  mov     [rbp+60h+ObjectAttributes.RootDirectory], r15
0x1800104a7  mov     [rbp+60h+ObjectAttributes.Attributes], 40h ; '@'
0x1800104ae  lea     rax, [rsp+160h+DestinationString]
0x1800104b3  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x1800104b7  xorps   xmm0, xmm0
0x1800104ba  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800104bf  lea     rdx, [rsp+160h+hObject]
0x1800104c4  lea     rcx, [rbp+60h+var_A0]
0x1800104c8  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x1800104cd  mov     [rsp+160h+EaLength], 0; EaLength
0x1800104d5  mov     [rsp+160h+EaBuffer], 0; EaBuffer
0x1800104de  mov     [rsp+160h+CreateOptions], 1000h; CreateOptions
0x1800104e6  mov     [rsp+160h+CreateDisposition], 2; CreateDisposition
0x1800104ee  mov     dword ptr [rsp+160h+hTemplateFile], 0; ShareAccess
0x1800104f6  mov     [rsp+160h+dwFlagsAndAttributes], 80h; FileAttributes
0x1800104fe  mov     qword ptr [rsp+160h+dwCreationDisposition], 0; AllocationSize
0x180010507  lea     r9, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x18001050b  lea     r8, [rsp+160h+ObjectAttributes]; ObjectAttributes
0x180010510  mov     edx, 0C0010000h; DesiredAccess
0x180010515  mov     rcx, rax; FileHandle
0x180010518  call    cs:__imp_NtCreateFile
0x18001051e  mov     ebx, eax
0x180010520  mov     rdx, [rbp+60h+var_A0]
0x180010524  test    rdx, rdx
0x180010527  jz      short loc_180010543
0x180010529  mov     rax, [rbp+60h+var_98]
0x18001052d  mov     rcx, [rax]; hObject
0x180010530  mov     [rax], rdx
0x180010533  lea     rax, [rcx+1]
0x180010537  cmp     rax, 1
0x18001053b  jbe     short loc_180010543
0x18001053d  call    cs:__imp_CloseHandle
0x180010543  mov     rdx, [rsp+160h+hObject]
0x180010548  lea     rax, [rdx+1]
0x18001054c  cmp     rax, 1
0x180010550  jbe     loc_1800105F1
0x180010556  test    ebx, ebx
0x180010558  jns     short loc_1800105C5
0x18001055a  bts     ebx, 1Ch
0x18001055e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010565  lea     r15, WPP_GLOBAL_Control
0x18001056c  cmp     rcx, r15
0x18001056f  jz      short loc_1800105A0
0x180010571  test    byte ptr [rcx+1Ch], 1
0x180010575  jz      short loc_1800105A0
0x180010577  mov     edx, 0B6h
0x18001057c  mov     [rsp+160h+dwCreationDisposition], ebx
0x180010580  lea     r9, [rbp+60h+SourceString]
0x180010584  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18001058b  mov     rcx, [rcx+10h]
0x18001058f  call    WPP_SF_Sd
0x180010594  mov     rdx, [rsp+160h+hObject]
0x180010599  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105a0  mov     [rsp+160h+hObject], 0
0x1800105a9  lea     rax, [rdx+1]
0x1800105ad  cmp     rax, 1
0x1800105b1  jbe     loc_18001064D
0x1800105b7  mov     rcx, rdx; hObject
0x1800105ba  call    cs:__imp_CloseHandle
0x1800105c0  jmp     loc_180010646
0x1800105c5  mov     [rsp+160h+hObject], 0
0x1800105ce  mov     rcx, [r12]; hObject
0x1800105d2  mov     [r12], rdx
0x1800105d6  lea     rax, [rcx+1]
0x1800105da  cmp     rax, 1
0x1800105de  jbe     short loc_1800105E6
0x1800105e0  call    cs:__imp_CloseHandle
0x1800105e6  xor     ebx, ebx
0x1800105e8  lea     r15, WPP_GLOBAL_Control
0x1800105ef  jmp     short loc_180010646
0x1800105f1  call    cs:__imp_GetLastError
0x1800105f7  mov     ebx, eax
0x1800105f9  test    eax, eax
0x1800105fb  jle     short loc_180010606
0x1800105fd  movzx   ebx, ax
0x180010600  or      ebx, 80070000h
0x180010606  mov     eax, 80004005h
0x18001060b  test    ebx, ebx
0x18001060d  cmovns  ebx, eax
0x180010610  mov     rcx, cs:WPP_GLOBAL_Control
0x180010617  lea     r15, WPP_GLOBAL_Control
0x18001061e  cmp     rcx, r15
0x180010621  jz      short loc_18001064D
0x180010623  test    byte ptr [rcx+1Ch], 1
0x180010627  jz      short loc_18001064D
0x180010629  mov     edx, 0B5h
0x18001062e  mov     [rsp+160h+dwCreationDisposition], ebx
0x180010632  lea     r9, [rbp+60h+SourceString]
0x180010636  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18001063d  mov     rcx, [rcx+10h]
0x180010641  call    WPP_SF_Sd
0x180010646  mov     rcx, cs:WPP_GLOBAL_Control
0x18001064d  lea     rax, [r14+1]
0x180010651  cmp     rax, 1
0x180010655  jbe     short loc_18001069B
0x180010657  mov     rdx, r14
0x18001065a  xor     r14d, r14d
0x18001065d  lea     rax, [rdx+1]
0x180010661  cmp     rax, 1
0x180010665  jbe     short loc_180010677
0x180010667  mov     rcx, rdx; hObject
0x18001066a  call    cs:__imp_CloseHandle
0x180010670  mov     rcx, cs:WPP_GLOBAL_Control
0x180010677  cmp     rcx, r15
0x18001067a  jz      short loc_18001069B
0x18001067c  test    byte ptr [rcx+1Ch], 4
0x180010680  jz      short loc_18001069B
0x180010682  mov     edx, 0B7h
0x180010687  mov     r9, rdi
0x18001068a  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180010691  mov     rcx, [rcx+10h]
0x180010695  call    WPP_SF_S
0x18001069a  nop
0x18001069b  lea     rax, [r14+1]
0x18001069f  cmp     rax, 1
0x1800106a3  jbe     short loc_1800106AF
0x1800106a5  mov     rcx, r14; hObject
0x1800106a8  call    cs:__imp_CloseHandle
0x1800106ae  nop
0x1800106af  mov     rcx, [rsp+160h+hObject]; hObject
0x1800106b4  lea     rax, [rcx+1]
0x1800106b8  cmp     rax, 1
0x1800106bc  jbe     short loc_1800106C4
0x1800106be  call    cs:__imp_CloseHandle
0x1800106c4  mov     eax, ebx
0x1800106c6  mov     rcx, [rbp+60h+var_30]
0x1800106ca  xor     rcx, rsp; StackCookie
0x1800106cd  call    __security_check_cookie
0x1800106d2  lea     r11, [rsp+160h+var_20]
0x1800106da  mov     rbx, [r11+40h]
0x1800106de  mov     rsi, [r11+48h]
0x1800106e2  mov     rsp, r11
0x1800106e5  pop     r15
0x1800106e7  pop     r14
0x1800106e9  pop     r12
0x1800106eb  pop     rdi
  ... truncated ...
```
