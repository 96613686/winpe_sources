# UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180009684`
- end: `0x180009b4a`
- name: `?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `1222`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `9`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009b78`
- `0x18001d718`
- `0x18003d4f0`
- `0x180040f04`
- `0x18004f8b8`
- `0x180078ca8`
- `0x180078f5c`
- `0x18007a000`
- `0x18008f2ec`

## callees

- `0x180007fd8`
- `0x180008004`
- `0x180009464`
- `0x180009684`
- `0x1800170b0`
- `0x180019138`
- `0x18001c368`
- `0x180028760`
- `0x18002a758`
- `0x18003bb8c`
- `0x18003fb94`
- `0x180053300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a82`
- `ntdll!NtCreateFile` at `0x1800099ab`
- `ntdll!NtCreateFile` at `0x1800099ab`
- `ntdll!RtlInitUnicodeString` at `0x180009912`
- `ntdll!RtlInitUnicodeString` at `0x180009912`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180009847`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180009847`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800097c4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800097c4`
- `ext-ms-win-wer-xbox-l1-2-0!XerShouldWerManageRootDirectory` at `0x1800096d8`
- `ext-ms-win-wer-xbox-l1-2-0!XerShouldWerManageRootDirectory` at `0x1800096d8`

## string_xrefs

- `0x180009704`: `onecore\windows\feedback\core\common\lib\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilVerifyAndLockDirectory(wchar_t *a1, __int64 a2)
{
  unsigned int v4; // edi
  void *v5; // rbx
  wchar_t *v6; // rcx
  int v7; // edx
  int i; // r14d
  HANDLE FileW; // rax
  DWORD LastError; // eax
  int AsString; // eax
  NTSTATUS v12; // edi
  DWORD v13; // eax
  unsigned int v14; // eax
  DWORD v15; // eax
  __int64 v16; // rcx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  char dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  void *v21; // [rsp+68h] [rbp-98h] BYREF
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v23; // [rsp+78h] [rbp-88h]
  _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR SourceString[40]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v4 = 0;
  v20 = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  v5 = 0;
  v21 = 0;
  if ( (unsigned __int8)XerShouldWerManageRootDirectory() )
  {
    if ( !a1 )
    {
      v4 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16F8,
        (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
        (const char *)0x80070057LL,
        dwCreationDisposition);
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v21);
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v20);
      return v4;
    }
    if ( a2 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, a1);
      for ( i = 0; i < 1000; ++i )
      {
        FileW = CreateFileW(a1, 0xC0000000, 1u, 0, 3u, 0x2000000u, 0);
        tlx::unique_any<tlx::file_handle_traits>::reset(&v21, FileW);
        v5 = v21;
        if ( (unsigned __int64)v21 + 1 > 1 )
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
            (unsigned int)WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
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
            v23 = &v20;
            tlx::unique_any<tlx::file_handle_traits>::reset(&v20, 0);
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
              tlx::unique_any<tlx::file_handle_traits>::reset(v23, FileHandle);
            if ( v20 == -1 || v20 == 0 )
            {
              v13 = GetLastError();
              v14 = ERROR_HR_FROM_WIN32(v13);
              v4 = v14;
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  181,
                  (unsigned int)WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
                  (unsigned int)SourceString,
                  v14);
            }
            else if ( v12 >= 0 )
            {
              tlx::unique_any<tlx::file_handle_traits>::operator=(a2, &v20);
              v4 = 0;
            }
            else
            {
              v4 = v12 | 0x10000000;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  182,
                  (unsigned int)WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
                  (unsigned int)SourceString,
                  v4);
              tlx::unique_any<tlx::file_handle_traits>::reset(&v20, 0);
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
          (unsigned int)WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
          (_DWORD)a1,
          dwCreationDispositiona);
      }
    }
  }
LABEL_48:
  if ( (unsigned __int64)v5 + 1 > 1 )
  {
    tlx::unique_any<tlx::file_handle_traits>::reset(&v21, 0);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, a1);
    v5 = v21;
  }
  tlx::file_handle_traits::operator()(v6, v5);
  tlx::file_handle_traits::operator()(v16, v20);
  return v4;
}

```

## disassembly

```asm
0x180009684  mov     [rsp-8+arg_10], rbx
0x180009689  push    rbp
0x18000968a  push    rsi
0x18000968b  push    rdi
0x18000968c  push    r14
0x18000968e  push    r15
0x180009690  lea     rbp, [rsp-40h]
0x180009695  sub     rsp, 140h
0x18000969c  mov     rax, cs:__security_cookie
0x1800096a3  xor     rax, rsp
0x1800096a6  mov     [rbp+60h+var_30], rax
0x1800096aa  mov     r15, rdx
0x1800096ad  mov     rsi, rcx
0x1800096b0  xor     edi, edi
0x1800096b2  mov     [rsp+160h+var_100], rdi
0x1800096b7  xorps   xmm0, xmm0
0x1800096ba  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm0
0x1800096be  xorps   xmm1, xmm1
0x1800096c1  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm1
0x1800096c5  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm1
0x1800096c9  movups  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800096cd  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x1800096d1  xor     ebx, ebx
0x1800096d3  mov     [rsp+160h+var_F8], rbx
0x1800096d8  call    cs:__imp_XerShouldWerManageRootDirectory
0x1800096df  nop     dword ptr [rax+rax+00h]
0x1800096e4  lea     r14, WPP_GLOBAL_Control
0x1800096eb  test    al, al
0x1800096ed  jz      loc_180009ACC
0x1800096f3  test    rsi, rsi
0x1800096f6  jnz     short loc_180009730
0x1800096f8  mov     rcx, [rbp+68h]; this
0x1800096fc  mov     edi, 80070057h
0x180009701  mov     r9d, edi; char *
0x180009704  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x18000970b  mov     edx, 16F8h; void *
0x180009710  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009715  nop
0x180009716  lea     rcx, [rsp+160h+var_F8]
0x18000971b  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180009720  nop
0x180009721  lea     rcx, [rsp+160h+var_100]
0x180009726  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18000972b  jmp     loc_180009B24
0x180009730  test    r15, r15
0x180009733  jnz     short loc_180009762
0x180009735  mov     edi, 80070057h
0x18000973a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009741  cmp     rcx, r14
0x180009744  jz      loc_180009ACC
0x18000974a  test    byte ptr [rcx+1Ch], 1
0x18000974e  jz      loc_180009ACC
0x180009754  mov     edx, 0AEh
0x180009759  mov     [rsp+160h+dwCreationDisposition], edi
0x18000975d  jmp     loc_180009AB9
0x180009762  mov     rcx, cs:WPP_GLOBAL_Control
0x180009769  cmp     rcx, r14
0x18000976c  jz      short loc_18000978C
0x18000976e  test    byte ptr [rcx+1Ch], 4
0x180009772  jz      short loc_18000978C
0x180009774  mov     edx, 0AFh
0x180009779  mov     r9, rsi
0x18000977c  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x180009783  mov     rcx, [rcx+10h]
0x180009787  call    WPP_SF_S
0x18000978c  xor     r14d, r14d
0x18000978f  cmp     r14d, 3E8h
0x180009796  jge     loc_180009886
0x18000979c  mov     [rsp+160h+hTemplateFile], 0; hTemplateFile
0x1800097a5  mov     [rsp+160h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800097ad  mov     [rsp+160h+dwCreationDisposition], 3; dwCreationDisposition
0x1800097b5  xor     r9d, r9d; lpSecurityAttributes
0x1800097b8  mov     edx, 0C0000000h; dwDesiredAccess
0x1800097bd  lea     r8d, [r9+1]; dwShareMode
0x1800097c1  mov     rcx, rsi; lpFileName
0x1800097c4  call    cs:__imp_CreateFileW
0x1800097cb  nop     dword ptr [rax+rax+00h]
0x1800097d0  mov     rdx, rax
0x1800097d3  lea     rcx, [rsp+160h+var_F8]
0x1800097d8  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800097dd  mov     rbx, [rsp+160h+var_F8]
0x1800097e2  lea     rax, [rbx+1]
0x1800097e6  cmp     rax, 1
0x1800097ea  ja      loc_180009886
0x1800097f0  call    cs:__imp_GetLastError
0x1800097f7  nop     dword ptr [rax+rax+00h]
0x1800097fc  mov     ecx, eax; unsigned int
0x1800097fe  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180009803  mov     edi, eax
0x180009805  cmp     eax, 80070020h
0x18000980a  jnz     short loc_18000985B
0x18000980c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009813  lea     rax, WPP_GLOBAL_Control
0x18000981a  cmp     rcx, rax
0x18000981d  jz      short loc_180009842
0x18000981f  test    byte ptr [rcx+1Ch], 2
0x180009823  jz      short loc_180009842
0x180009825  mov     edx, 0B0h
0x18000982a  mov     [rsp+160h+dwCreationDisposition], r14d
0x18000982f  mov     r9, rsi
0x180009832  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x180009839  mov     rcx, [rcx+10h]
0x18000983d  call    WPP_SF_Sd
0x180009842  mov     ecx, 14h; dwMilliseconds
0x180009847  call    cs:__imp_Sleep
0x18000984e  nop     dword ptr [rax+rax+00h]
0x180009853  inc     r14d
0x180009856  jmp     loc_18000978F
0x18000985b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009862  lea     r14, WPP_GLOBAL_Control
0x180009869  cmp     rcx, r14
0x18000986c  jz      loc_180009ACC
0x180009872  test    byte ptr [rcx+1Ch], 1
0x180009876  jz      loc_180009ACC
0x18000987c  mov     edx, 0B1h
0x180009881  jmp     loc_180009AB5
0x180009886  lea     rax, [rbx+1]
0x18000988a  cmp     rax, 1
0x18000988e  jbe     loc_180009A82
0x180009894  mov     rdx, rbx; void *
0x180009897  mov     rcx, rsi; wchar_t *
0x18000989a  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x18000989f  mov     edi, eax
0x1800098a1  test    eax, eax
0x1800098a3  jns     short loc_1800098D0
0x1800098a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098ac  lea     r14, WPP_GLOBAL_Control
0x1800098b3  cmp     rcx, r14
0x1800098b6  jz      loc_180009ACC
0x1800098bc  test    byte ptr [rcx+1Ch], 1
0x1800098c0  jz      loc_180009ACC
0x1800098c6  mov     edx, 0B3h
0x1800098cb  jmp     loc_180009AB5
0x1800098d0  lea     rcx, [rbp+60h+SourceString]; wchar_t *
0x1800098d4  call    ?UtilUuidCreateAsString@@YAJPEA_W@Z; UtilUuidCreateAsString(wchar_t *)
0x1800098d9  mov     edi, eax
0x1800098db  test    eax, eax
0x1800098dd  jns     short loc_18000990A
0x1800098df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098e6  lea     r14, WPP_GLOBAL_Control
0x1800098ed  cmp     rcx, r14
0x1800098f0  jz      loc_180009ACC
0x1800098f6  test    byte ptr [rcx+1Ch], 1
0x1800098fa  jz      loc_180009ACC
0x180009900  mov     edx, 0B4h
0x180009905  jmp     loc_180009AB5
0x18000990a  lea     rdx, [rbp+60h+SourceString]; SourceString
0x18000990e  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x180009912  call    cs:__imp_RtlInitUnicodeString
0x180009919  nop     dword ptr [rax+rax+00h]
0x18000991e  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x180009925  mov     [rbp+60h+ObjectAttributes.RootDirectory], rbx
0x180009929  mov     [rbp+60h+ObjectAttributes.Attributes], 40h ; '@'
0x180009930  lea     rax, [rbp+60h+DestinationString]
0x180009934  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x180009938  xorps   xmm0, xmm0
0x18000993b  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x180009940  mov     [rsp+160h+FileHandle], 0
0x180009949  lea     rax, [rsp+160h+var_100]
0x18000994e  mov     [rsp+160h+var_E8], rax
0x180009953  xor     edx, edx
0x180009955  lea     rcx, [rsp+160h+var_100]
0x18000995a  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18000995f  mov     [rsp+160h+EaLength], 0; EaLength
0x180009967  mov     [rsp+160h+EaBuffer], 0; EaBuffer
0x180009970  mov     [rsp+160h+CreateOptions], 1000h; CreateOptions
0x180009978  mov     [rsp+160h+CreateDisposition], 2; CreateDisposition
0x180009980  mov     dword ptr [rsp+160h+hTemplateFile], 0; ShareAccess
0x180009988  mov     [rsp+160h+dwFlagsAndAttributes], 80h; FileAttributes
0x180009990  mov     qword ptr [rsp+160h+dwCreationDisposition], 0; AllocationSize
0x180009999  lea     r9, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x18000999d  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x1800099a1  mov     edx, 0C0010000h; DesiredAccess
0x1800099a6  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x1800099ab  call    cs:__imp_NtCreateFile
0x1800099b2  nop     dword ptr [rax+rax+00h]
0x1800099b7  mov     edi, eax
0x1800099b9  mov     rdx, [rsp+160h+FileHandle]
0x1800099be  test    rdx, rdx
0x1800099c1  jz      short loc_1800099CD
0x1800099c3  mov     rcx, [rsp+160h+var_E8]
0x1800099c8  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800099cd  mov     rax, [rsp+160h+var_100]
0x1800099d2  inc     rax
0x1800099d5  cmp     rax, 1
0x1800099d9  jbe     short loc_180009A45
0x1800099db  test    edi, edi
0x1800099dd  jns     short loc_180009A2A
0x1800099df  bts     edi, 1Ch
0x1800099e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099ea  lea     r14, WPP_GLOBAL_Control
0x1800099f1  cmp     rcx, r14
0x1800099f4  jz      short loc_180009A19
0x1800099f6  test    byte ptr [rcx+1Ch], 1
0x1800099fa  jz      short loc_180009A19
0x1800099fc  mov     edx, 0B6h
0x180009a01  mov     [rsp+160h+dwCreationDisposition], edi
0x180009a05  lea     r9, [rbp+60h+SourceString]
0x180009a09  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x180009a10  mov     rcx, [rcx+10h]
0x180009a14  call    WPP_SF_Sd
0x180009a19  xor     edx, edx
0x180009a1b  lea     rcx, [rsp+160h+var_100]
0x180009a20  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180009a25  jmp     loc_180009ACC
0x180009a2a  lea     rdx, [rsp+160h+var_100]
0x180009a2f  mov     rcx, r15
0x180009a32  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x180009a37  xor     edi, edi
0x180009a39  lea     r14, WPP_GLOBAL_Control
0x180009a40  jmp     loc_180009ACC
0x180009a45  call    cs:__imp_GetLastError
0x180009a4c  nop     dword ptr [rax+rax+00h]
0x180009a51  mov     ecx, eax; unsigned int
0x180009a53  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180009a58  mov     edi, eax
0x180009a5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a61  lea     r14, WPP_GLOBAL_Control
0x180009a68  cmp     rcx, r14
0x180009a6b  jz      short loc_180009ACC
0x180009a6d  test    byte ptr [rcx+1Ch], 1
0x180009a71  jz      short loc_180009ACC
0x180009a73  mov     edx, 0B5h
0x180009a78  mov     [rsp+160h+dwCreationDisposition], eax
0x180009a7c  lea     r9, [rbp+60h+SourceString]
0x180009a80  jmp     short loc_180009ABC
0x180009a82  call    cs:__imp_GetLastError
0x180009a89  nop     dword ptr [rax+rax+00h]
0x180009a8e  mov     ecx, eax; unsigned int
0x180009a90  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180009a95  mov     edi, eax
0x180009a97  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a9e  lea     r14, WPP_GLOBAL_Control
0x180009aa5  cmp     rcx, r14
0x180009aa8  jz      short loc_180009ACC
0x180009aaa  test    byte ptr [rcx+1Ch], 1
0x180009aae  jz      short loc_180009ACC
0x180009ab0  mov     edx, 0B2h
0x180009ab5  mov     [rsp+160h+dwCreationDisposition], eax
0x180009ab9  mov     r9, rsi
0x180009abc  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x180009ac3  mov     rcx, [rcx+10h]
0x180009ac7  call    WPP_SF_Sd
0x180009acc  lea     rax, [rbx+1]
0x180009ad0  cmp     rax, 1
0x180009ad4  jbe     short loc_180009B11
0x180009ad6  xor     edx, edx
0x180009ad8  lea     rcx, [rsp+160h+var_F8]
0x180009add  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180009ae2  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ae9  cmp     rcx, r14
0x180009aec  jz      short loc_180009B0C
0x180009aee  test    byte ptr [rcx+1Ch], 4
0x180009af2  jz      short loc_180009B0C
0x180009af4  mov     edx, 0B7h
0x180009af9  mov     r9, rsi
0x180009afc  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x180009b03  mov     rcx, [rcx+10h]
0x180009b07  call    WPP_SF_S
0x180009b0c  mov     rbx, [rsp+160h+var_F8]
0x180009b11  mov     rdx, rbx
0x180009b14  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x180009b19  nop
0x180009b1a  mov     rdx, [rsp+160h+var_100]
0x180009b1f  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x180009b24  mov     eax, edi
0x180009b26  mov     rcx, [rbp+60h+var_30]
0x180009b2a  xor     rcx, rsp; StackCookie
0x180009b2d  call    __security_check_cookie
0x180009b32  mov     rbx, [rsp+160h+arg_10]
0x180009b3a  add     rsp, 140h
0x180009b41  pop     r15
0x180009b43  pop     r14
0x180009b45  pop     rdi
0x180009b46  pop     rsi
0x180009b47  pop     rbp
0x180009b48  retn
```
