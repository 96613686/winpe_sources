# UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180008568`
- end: `0x180008a10`
- name: `?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `1192`
- prototype: `__int64 __fastcall(wchar_t *, void **)`
- caller_count: `9`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008a48`
- `0x18001d128`
- `0x18003b590`
- `0x18003ef14`
- `0x18004d478`
- `0x1800757f8`
- `0x180075aac`
- `0x180076b00`
- `0x18008b42c`

## callees

- `0x18000716c`
- `0x1800072cc`
- `0x180007e10`
- `0x180007e34`
- `0x180008568`
- `0x180013730`
- `0x1800157c4`
- `0x180027884`
- `0x180039950`
- `0x18003db78`
- `0x180050db0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008939`
- `ntdll!NtCreateFile` at `0x180008871`
- `ntdll!NtCreateFile` at `0x180008871`
- `ntdll!RtlInitUnicodeString` at `0x1800087de`
- `ntdll!RtlInitUnicodeString` at `0x1800087de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089e5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008719`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008719`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800086a2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800086a2`
- `ext-ms-win-wer-xbox-l1-2-0!XerShouldWerManageRootDirectory` at `0x1800085bc`
- `ext-ms-win-wer-xbox-l1-2-0!XerShouldWerManageRootDirectory` at `0x1800085bc`

## string_xrefs

- `0x1800085e2`: `onecore\windows\feedback\core\common\lib\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilVerifyAndLockDirectory(wchar_t *a1, void **a2)
{
  unsigned int v4; // ebx
  void *v5; // rdi
  wchar_t *v6; // rcx
  int v7; // edx
  int i; // r14d
  HANDLE FileW; // rax
  DWORD LastError; // eax
  int AsString; // eax
  NTSTATUS v12; // ebx
  DWORD v13; // eax
  unsigned int v14; // eax
  DWORD v15; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  char dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  void *v20; // [rsp+68h] [rbp-98h] BYREF
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  HANDLE *p_hObject; // [rsp+78h] [rbp-88h]
  _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR SourceString[40]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v4 = 0;
  hObject = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  v5 = 0;
  v20 = 0;
  if ( (unsigned __int8)XerShouldWerManageRootDirectory() )
  {
    if ( !a1 )
    {
      v4 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16E4,
        (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
        (const char *)0x80070057LL,
        dwCreationDisposition);
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v20);
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hObject);
      return v4;
    }
    if ( a2 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, a1);
      for ( i = 0; i < 1000; ++i )
      {
        FileW = CreateFileW(a1, 0xC0000000, 1u, 0, 3u, 0x2000000u, 0);
        tlx::unique_any<tlx::file_handle_traits>::reset(&v20, FileW);
        v5 = v20;
        if ( (unsigned __int64)v20 + 1 > 1 )
          break;
        LastError = GetLastError();
        AsString = ERROR_HR_FROM_WIN32(LastError);
        v4 = AsString;
        if ( AsString != -2147024864 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v7 = 177;
LABEL_46:
            dwCreationDispositiona = AsString;
            goto LABEL_47;
          }
          goto LABEL_48;
        }
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            176,
            (unsigned int)WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
            (_DWORD)a1,
            i);
        Sleep(0x14u);
      }
      if ( (unsigned __int64)v5 + 1 <= 1 )
      {
        v15 = GetLastError();
        AsString = ERROR_HR_FROM_WIN32(v15);
        v4 = AsString;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v7 = 178;
          goto LABEL_46;
        }
      }
      else
      {
        AsString = UtilVerifyFilePath(a1, v5);
        v4 = AsString;
        if ( AsString >= 0 )
        {
          AsString = UtilUuidCreateAsString(SourceString);
          v4 = AsString;
          if ( AsString >= 0 )
          {
            RtlInitUnicodeString(&DestinationString, SourceString);
            ObjectAttributes.Length = 48;
            ObjectAttributes.RootDirectory = v5;
            ObjectAttributes.Attributes = 64;
            ObjectAttributes.ObjectName = &DestinationString;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            FileHandle = 0;
            p_hObject = &hObject;
            tlx::unique_any<tlx::file_handle_traits>::reset(&hObject, 0);
            v12 = NtCreateFile(
                    &FileHandle,
                    0xC0010000,
                    &ObjectAttributes,
                    &IoStatusBlock,
                    0,
                    0x80u,
                    0,
                    2u,
                    0x1000u,
                    0,
                    0);
            if ( FileHandle )
              tlx::unique_any<tlx::file_handle_traits>::reset(p_hObject, FileHandle);
            if ( hObject == (HANDLE)-1LL || (char *)hObject + 1 == HANDLE_FLAG_INHERIT )
            {
              v13 = GetLastError();
              v14 = ERROR_HR_FROM_WIN32(v13);
              v4 = v14;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  181,
                  (unsigned int)WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
                  (unsigned int)SourceString,
                  v14);
            }
            else if ( v12 >= 0 )
            {
              tlx::unique_any<tlx::file_handle_traits>::operator=(a2, &hObject);
              v4 = 0;
            }
            else
            {
              v4 = v12 | 0x10000000;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  182,
                  (unsigned int)WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
                  (unsigned int)SourceString,
                  v4);
              tlx::unique_any<tlx::file_handle_traits>::reset(&hObject, 0);
            }
          }
          else
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v7 = 180;
              goto LABEL_46;
            }
          }
        }
        else
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v7 = 179;
            goto LABEL_46;
          }
        }
      }
    }
    else
    {
      v4 = -2147024809;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v7 = 174;
        dwCreationDispositiona = 87;
LABEL_47:
        WPP_SF_Sd(
          *((_QWORD *)v6 + 2),
          v7,
          (unsigned int)WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
          (_DWORD)a1,
          dwCreationDispositiona);
      }
    }
  }
LABEL_48:
  if ( (unsigned __int64)v5 + 1 > 1 )
  {
    tlx::unique_any<tlx::file_handle_traits>::reset(&v20, 0);
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, a1);
    v5 = v20;
  }
  if ( (unsigned __int64)v5 + 1 > 1 )
    CloseHandle(v5);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return v4;
}

```

## disassembly

```asm
0x180008568  mov     [rsp-8+arg_10], rbx
0x18000856d  push    rbp
0x18000856e  push    rsi
0x18000856f  push    rdi
0x180008570  push    r14
0x180008572  push    r15
0x180008574  lea     rbp, [rsp-40h]
0x180008579  sub     rsp, 140h
0x180008580  mov     rax, cs:__security_cookie
0x180008587  xor     rax, rsp
0x18000858a  mov     [rbp+60h+var_30], rax
0x18000858e  mov     r15, rdx
0x180008591  mov     rsi, rcx
0x180008594  xor     ebx, ebx
0x180008596  mov     [rsp+160h+hObject], rbx
0x18000859b  xorps   xmm0, xmm0
0x18000859e  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm0
0x1800085a2  xorps   xmm1, xmm1
0x1800085a5  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm1
0x1800085a9  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm1
0x1800085ad  movups  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800085b1  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x1800085b5  xor     edi, edi
0x1800085b7  mov     [rsp+160h+var_F8], rdi
0x1800085bc  call    cs:__imp_XerShouldWerManageRootDirectory
0x1800085c2  lea     r14, WPP_GLOBAL_Control
0x1800085c9  test    al, al
0x1800085cb  jz      loc_18000897D
0x1800085d1  test    rsi, rsi
0x1800085d4  jnz     short loc_18000860E
0x1800085d6  mov     rcx, [rbp+68h]; this
0x1800085da  mov     ebx, 80070057h
0x1800085df  mov     r9d, ebx; char *
0x1800085e2  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x1800085e9  mov     edx, 16E4h; void *
0x1800085ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800085f3  nop
0x1800085f4  lea     rcx, [rsp+160h+var_F8]
0x1800085f9  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800085fe  nop
0x1800085ff  lea     rcx, [rsp+160h+hObject]
0x180008604  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180008609  jmp     loc_1800089EB
0x18000860e  test    r15, r15
0x180008611  jnz     short loc_180008640
0x180008613  mov     ebx, 80070057h
0x180008618  mov     rcx, cs:WPP_GLOBAL_Control
0x18000861f  cmp     rcx, r14
0x180008622  jz      loc_18000897D
0x180008628  test    byte ptr [rcx+1Ch], 1
0x18000862c  jz      loc_18000897D
0x180008632  mov     edx, 0AEh
0x180008637  mov     [rsp+160h+dwCreationDisposition], ebx
0x18000863b  jmp     loc_18000896A
0x180008640  mov     rcx, cs:WPP_GLOBAL_Control
0x180008647  cmp     rcx, r14
0x18000864a  jz      short loc_18000866A
0x18000864c  test    byte ptr [rcx+1Ch], 4
0x180008650  jz      short loc_18000866A
0x180008652  mov     edx, 0AFh
0x180008657  mov     r9, rsi
0x18000865a  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180008661  mov     rcx, [rcx+10h]
0x180008665  call    WPP_SF_S
0x18000866a  xor     r14d, r14d
0x18000866d  cmp     r14d, 3E8h
0x180008674  jge     loc_180008752
0x18000867a  mov     [rsp+160h+hTemplateFile], 0; hTemplateFile
0x180008683  mov     [rsp+160h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000868b  mov     [rsp+160h+dwCreationDisposition], 3; dwCreationDisposition
0x180008693  xor     r9d, r9d; lpSecurityAttributes
0x180008696  mov     edx, 0C0000000h; dwDesiredAccess
0x18000869b  lea     r8d, [r9+1]; dwShareMode
0x18000869f  mov     rcx, rsi; lpFileName
0x1800086a2  call    cs:__imp_CreateFileW
0x1800086a8  mov     rdx, rax
0x1800086ab  lea     rcx, [rsp+160h+var_F8]
0x1800086b0  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800086b5  mov     rdi, [rsp+160h+var_F8]
0x1800086ba  lea     rax, [rdi+1]
0x1800086be  cmp     rax, 1
0x1800086c2  ja      loc_180008752
0x1800086c8  call    cs:__imp_GetLastError
0x1800086ce  mov     ecx, eax; unsigned int
0x1800086d0  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800086d5  mov     ebx, eax
0x1800086d7  cmp     eax, 80070020h
0x1800086dc  jnz     short loc_180008727
0x1800086de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086e5  lea     rax, WPP_GLOBAL_Control
0x1800086ec  cmp     rcx, rax
0x1800086ef  jz      short loc_180008714
0x1800086f1  test    byte ptr [rcx+1Ch], 2
0x1800086f5  jz      short loc_180008714
0x1800086f7  mov     edx, 0B0h
0x1800086fc  mov     [rsp+160h+dwCreationDisposition], r14d
0x180008701  mov     r9, rsi
0x180008704  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18000870b  mov     rcx, [rcx+10h]
0x18000870f  call    WPP_SF_Sd
0x180008714  mov     ecx, 14h; dwMilliseconds
0x180008719  call    cs:__imp_Sleep
0x18000871f  inc     r14d
0x180008722  jmp     loc_18000866D
0x180008727  mov     rcx, cs:WPP_GLOBAL_Control
0x18000872e  lea     r14, WPP_GLOBAL_Control
0x180008735  cmp     rcx, r14
0x180008738  jz      loc_18000897D
0x18000873e  test    byte ptr [rcx+1Ch], 1
0x180008742  jz      loc_18000897D
0x180008748  mov     edx, 0B1h
0x18000874d  jmp     loc_180008966
0x180008752  lea     rax, [rdi+1]
0x180008756  cmp     rax, 1
0x18000875a  jbe     loc_180008939
0x180008760  mov     rdx, rdi; void *
0x180008763  mov     rcx, rsi; wchar_t *
0x180008766  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x18000876b  mov     ebx, eax
0x18000876d  test    eax, eax
0x18000876f  jns     short loc_18000879C
0x180008771  mov     rcx, cs:WPP_GLOBAL_Control
0x180008778  lea     r14, WPP_GLOBAL_Control
0x18000877f  cmp     rcx, r14
0x180008782  jz      loc_18000897D
0x180008788  test    byte ptr [rcx+1Ch], 1
0x18000878c  jz      loc_18000897D
0x180008792  mov     edx, 0B3h
0x180008797  jmp     loc_180008966
0x18000879c  lea     rcx, [rbp+60h+SourceString]; wchar_t *
0x1800087a0  call    ?UtilUuidCreateAsString@@YAJPEA_W@Z; UtilUuidCreateAsString(wchar_t *)
0x1800087a5  mov     ebx, eax
0x1800087a7  test    eax, eax
0x1800087a9  jns     short loc_1800087D6
0x1800087ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087b2  lea     r14, WPP_GLOBAL_Control
0x1800087b9  cmp     rcx, r14
0x1800087bc  jz      loc_18000897D
0x1800087c2  test    byte ptr [rcx+1Ch], 1
0x1800087c6  jz      loc_18000897D
0x1800087cc  mov     edx, 0B4h
0x1800087d1  jmp     loc_180008966
0x1800087d6  lea     rdx, [rbp+60h+SourceString]; SourceString
0x1800087da  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x1800087de  call    cs:__imp_RtlInitUnicodeString
0x1800087e4  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x1800087eb  mov     [rbp+60h+ObjectAttributes.RootDirectory], rdi
0x1800087ef  mov     [rbp+60h+ObjectAttributes.Attributes], 40h ; '@'
0x1800087f6  lea     rax, [rbp+60h+DestinationString]
0x1800087fa  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x1800087fe  xorps   xmm0, xmm0
0x180008801  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x180008806  mov     [rsp+160h+FileHandle], 0
0x18000880f  lea     rax, [rsp+160h+hObject]
0x180008814  mov     [rsp+160h+var_E8], rax
0x180008819  xor     edx, edx
0x18000881b  lea     rcx, [rsp+160h+hObject]
0x180008820  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180008825  mov     [rsp+160h+EaLength], 0; EaLength
0x18000882d  mov     [rsp+160h+EaBuffer], 0; EaBuffer
0x180008836  mov     [rsp+160h+CreateOptions], 1000h; CreateOptions
0x18000883e  mov     [rsp+160h+CreateDisposition], 2; CreateDisposition
0x180008846  mov     dword ptr [rsp+160h+hTemplateFile], 0; ShareAccess
0x18000884e  mov     [rsp+160h+dwFlagsAndAttributes], 80h; FileAttributes
0x180008856  mov     qword ptr [rsp+160h+dwCreationDisposition], 0; AllocationSize
0x18000885f  lea     r9, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x180008863  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x180008867  mov     edx, 0C0010000h; DesiredAccess
0x18000886c  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x180008871  call    cs:__imp_NtCreateFile
0x180008877  mov     ebx, eax
0x180008879  mov     rdx, [rsp+160h+FileHandle]
0x18000887e  test    rdx, rdx
0x180008881  jz      short loc_18000888D
0x180008883  mov     rcx, [rsp+160h+var_E8]
0x180008888  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18000888d  mov     rax, [rsp+160h+hObject]
0x180008892  inc     rax
0x180008895  cmp     rax, 1
0x180008899  jbe     short loc_180008902
0x18000889b  test    ebx, ebx
0x18000889d  jns     short loc_1800088EA
0x18000889f  bts     ebx, 1Ch
0x1800088a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088aa  lea     r14, WPP_GLOBAL_Control
0x1800088b1  cmp     rcx, r14
0x1800088b4  jz      short loc_1800088D9
0x1800088b6  test    byte ptr [rcx+1Ch], 1
0x1800088ba  jz      short loc_1800088D9
0x1800088bc  mov     edx, 0B6h
0x1800088c1  mov     [rsp+160h+dwCreationDisposition], ebx
0x1800088c5  lea     r9, [rbp+60h+SourceString]
0x1800088c9  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800088d0  mov     rcx, [rcx+10h]
0x1800088d4  call    WPP_SF_Sd
0x1800088d9  xor     edx, edx
0x1800088db  lea     rcx, [rsp+160h+hObject]
0x1800088e0  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800088e5  jmp     loc_18000897D
0x1800088ea  lea     rdx, [rsp+160h+hObject]
0x1800088ef  mov     rcx, r15
0x1800088f2  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x1800088f7  xor     ebx, ebx
0x1800088f9  lea     r14, WPP_GLOBAL_Control
0x180008900  jmp     short loc_18000897D
0x180008902  call    cs:__imp_GetLastError
0x180008908  mov     ecx, eax; unsigned int
0x18000890a  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18000890f  mov     ebx, eax
0x180008911  mov     rcx, cs:WPP_GLOBAL_Control
0x180008918  lea     r14, WPP_GLOBAL_Control
0x18000891f  cmp     rcx, r14
0x180008922  jz      short loc_18000897D
0x180008924  test    byte ptr [rcx+1Ch], 1
0x180008928  jz      short loc_18000897D
0x18000892a  mov     edx, 0B5h
0x18000892f  mov     [rsp+160h+dwCreationDisposition], eax
0x180008933  lea     r9, [rbp+60h+SourceString]
0x180008937  jmp     short loc_18000896D
0x180008939  call    cs:__imp_GetLastError
0x18000893f  mov     ecx, eax; unsigned int
0x180008941  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180008946  mov     ebx, eax
0x180008948  mov     rcx, cs:WPP_GLOBAL_Control
0x18000894f  lea     r14, WPP_GLOBAL_Control
0x180008956  cmp     rcx, r14
0x180008959  jz      short loc_18000897D
0x18000895b  test    byte ptr [rcx+1Ch], 1
0x18000895f  jz      short loc_18000897D
0x180008961  mov     edx, 0B2h
0x180008966  mov     [rsp+160h+dwCreationDisposition], eax
0x18000896a  mov     r9, rsi
0x18000896d  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180008974  mov     rcx, [rcx+10h]
0x180008978  call    WPP_SF_Sd
0x18000897d  lea     rax, [rdi+1]
0x180008981  cmp     rax, 1
0x180008985  jbe     short loc_1800089C2
0x180008987  xor     edx, edx
0x180008989  lea     rcx, [rsp+160h+var_F8]
0x18000898e  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180008993  mov     rcx, cs:WPP_GLOBAL_Control
0x18000899a  cmp     rcx, r14
0x18000899d  jz      short loc_1800089BD
0x18000899f  test    byte ptr [rcx+1Ch], 4
0x1800089a3  jz      short loc_1800089BD
0x1800089a5  mov     edx, 0B7h
0x1800089aa  mov     r9, rsi
0x1800089ad  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800089b4  mov     rcx, [rcx+10h]
0x1800089b8  call    WPP_SF_S
0x1800089bd  mov     rdi, [rsp+160h+var_F8]
0x1800089c2  lea     rax, [rdi+1]
0x1800089c6  cmp     rax, 1
0x1800089ca  jbe     short loc_1800089D6
0x1800089cc  mov     rcx, rdi; hObject
0x1800089cf  call    cs:__imp_CloseHandle
0x1800089d5  nop
0x1800089d6  mov     rcx, [rsp+160h+hObject]; hObject
0x1800089db  lea     rax, [rcx+1]
0x1800089df  cmp     rax, 1
0x1800089e3  jbe     short loc_1800089EB
0x1800089e5  call    cs:__imp_CloseHandle
0x1800089eb  mov     eax, ebx
0x1800089ed  mov     rcx, [rbp+60h+var_30]
0x1800089f1  xor     rcx, rsp; StackCookie
0x1800089f4  call    __security_check_cookie
0x1800089f9  mov     rbx, [rsp+160h+arg_10]
0x180008a01  add     rsp, 140h
0x180008a08  pop     r15
0x180008a0a  pop     r14
0x180008a0c  pop     rdi
0x180008a0d  pop     rsi
0x180008a0e  pop     rbp
0x180008a0f  retn
```
