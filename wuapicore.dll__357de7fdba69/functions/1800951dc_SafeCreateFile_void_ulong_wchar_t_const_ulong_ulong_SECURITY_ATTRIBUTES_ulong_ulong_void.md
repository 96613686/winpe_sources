# SafeCreateFile(void * *,ulong,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x1800951dc`
- end: `0x1800953b9`
- name: `?SafeCreateFile@@YAJPEAPEAXKPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `477`
- prototype: `int(void **, unsigned int, const wchar_t *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180089950`
- `0x180089a84`

## callees

- `0x180006ac4`
- `0x180090bc8`
- `0x180094e4c`
- `0x180094fac`
- `0x1800950f8`
- `0x180095180`
- `0x1800951dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800952f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800952f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095399`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095399`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180095364`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180095364`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800952e1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800952e1`

## string_xrefs

- `0x180095331`: `SafeCreateFile`
- `0x180095325`: `%ws (Access: %lu, Share: %lu)`

## pseudocode

```c
__int64 __fastcall SafeCreateFile(
        void **a1,
        int a2,
        const wchar_t *a3,
        DWORD a4,
        unsigned int dwShareMode,
        struct _SECURITY_ATTRIBUTES *a6,
        DWORD a7,
        unsigned int a8)
{
  __int64 v11; // rbx
  __int64 v12; // rdx
  signed int v13; // edi
  HANDLE FileW; // rax
  signed int LastError; // eax
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-88h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v11 = -1;
  if ( !a3 )
  {
    v12 = 427;
LABEL_7:
    v13 = -2147024809;
    goto LABEL_27;
  }
  if ( !a1 )
  {
    v12 = 428;
    goto LABEL_7;
  }
  if ( (a2 & 0xFFFFFFFC) != 0 )
  {
    v12 = 429;
    goto LABEL_7;
  }
  *a1 = (void *)-1LL;
  if ( (unsigned int)SkipPathDrivePart(a3, 0) )
  {
    if ( (unsigned int)DoesPathContainDotDot(a3) )
    {
      v13 = -2147024735;
      v12 = 437;
    }
    else if ( (unsigned int)DoesPathContainStreamSyntax(a3) )
    {
      v13 = -2147024773;
      v12 = 440;
    }
    else
    {
      v13 = CheckValidDriveType(a3);
      if ( v13 >= 0 )
      {
        FileW = CreateFileW(a3, a4, dwShareMode, 0, a7, a8 | 0x100000, 0);
        v11 = (__int64)FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          v13 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v13 = LastError;
          if ( v13 < 0 )
          {
            if ( v13 == -2147024891 || v13 == -2147024864 )
            {
              LODWORD(dwCreationDisposition) = v13;
              WUTrace(
                "SafeCreateFile",
                470,
                32,
                3,
                dwCreationDisposition,
                L"%ws (Access: %lu, Share: %lu)",
                a3,
                a4,
                dwShareMode);
            }
          }
          else
          {
            v13 = -2147418113;
          }
          v12 = 473;
        }
        else
        {
          if ( GetFileType(FileW) == 1 )
          {
            *a1 = (void *)v11;
            return 0;
          }
          v13 = -2147024786;
          v12 = 477;
        }
      }
      else
      {
        v12 = 445;
      }
    }
  }
  else
  {
    v13 = -2147024893;
    v12 = 434;
  }
LABEL_27:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\SafeFile.cpp",
    (const char *)(unsigned int)v13,
    dwCreationDisposition);
  if ( v11 != -1 )
    CloseHandle((HANDLE)v11);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800951dc  push    rbx
0x1800951de  push    rbp
0x1800951df  push    rsi
0x1800951e0  push    rdi
0x1800951e1  push    r12
0x1800951e3  push    r13
0x1800951e5  push    r14
0x1800951e7  push    r15
0x1800951e9  sub     rsp, 68h
0x1800951ed  mov     r12d, [rsp+0A8h+dwShareMode]
0x1800951f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800951f9  mov     r13d, [rsp+0A8h+arg_30]
0x180095201  mov     r15d, r9d
0x180095204  mov     ebp, [rsp+0A8h+arg_38]
0x18009520b  mov     rsi, r8
0x18009520e  mov     edi, edx
0x180095210  mov     r14, rcx
0x180095213  mov     rbx, rax
0x180095216  test    r8, r8
0x180095219  jnz     short loc_180095222
0x18009521b  mov     edx, 1ABh
0x180095220  jmp     short loc_18009523B
0x180095222  test    r14, r14
0x180095225  jnz     short loc_18009522E
0x180095227  mov     edx, 1ACh
0x18009522c  jmp     short loc_18009523B
0x18009522e  test    edi, 0FFFFFFFCh
0x180095234  jz      short loc_180095245
0x180095236  mov     edx, 1ADh
0x18009523b  mov     edi, 80070057h
0x180095240  jmp     loc_180095379
0x180095245  mov     [rcx], rax
0x180095248  xor     edx, edx
0x18009524a  mov     rcx, rsi
0x18009524d  call    SkipPathDrivePart
0x180095252  test    eax, eax
0x180095254  jnz     short loc_180095265
0x180095256  mov     edi, 80070003h
0x18009525b  mov     edx, 1B2h
0x180095260  jmp     loc_180095379
0x180095265  mov     rcx, rsi
0x180095268  call    DoesPathContainDotDot
0x18009526d  test    eax, eax
0x18009526f  jz      short loc_180095280
0x180095271  mov     edi, 800700A1h
0x180095276  mov     edx, 1B5h
0x18009527b  jmp     loc_180095379
0x180095280  mov     rcx, rsi
0x180095283  call    DoesPathContainStreamSyntax
0x180095288  test    eax, eax
0x18009528a  jz      short loc_18009529B
0x18009528c  mov     edi, 8007007Bh
0x180095291  mov     edx, 1B8h
0x180095296  jmp     loc_180095379
0x18009529b  mov     r8d, edi
0x18009529e  mov     rcx, rsi; lpszFileName
0x1800952a1  and     edi, 1
0x1800952a4  and     r8d, 2
0x1800952a8  mov     edx, edi
0x1800952aa  call    CheckValidDriveType
0x1800952af  mov     edi, eax
0x1800952b1  test    eax, eax
0x1800952b3  jns     short loc_1800952BF
0x1800952b5  mov     edx, 1BDh
0x1800952ba  jmp     loc_180095379
0x1800952bf  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x1800952c8  bts     ebp, 14h
0x1800952cc  mov     [rsp+0A8h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x1800952d0  xor     r9d, r9d; lpSecurityAttributes
0x1800952d3  mov     r8d, r12d; dwShareMode
0x1800952d6  mov     dword ptr [rsp+0A8h+dwCreationDisposition], r13d; int
0x1800952db  mov     edx, r15d; dwDesiredAccess
0x1800952de  mov     rcx, rsi; lpFileName
0x1800952e1  call    cs:__imp_CreateFileW
0x1800952e7  mov     rbx, rax
0x1800952ea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800952ee  jnz     short loc_180095361
0x1800952f0  call    cs:__imp_GetLastError
0x1800952f6  movzx   edi, ax
0x1800952f9  or      edi, 80070000h
0x1800952ff  test    eax, eax
0x180095301  cmovle  edi, eax
0x180095304  test    edi, edi
0x180095306  js      short loc_18009530F
0x180095308  mov     edi, 8000FFFFh
0x18009530d  jmp     short loc_18009535A
0x18009530f  mov     eax, edi
0x180095311  cmp     edi, 80070005h
0x180095317  jz      short loc_180095320
0x180095319  cmp     eax, 80070020h
0x18009531e  jnz     short loc_18009535A
0x180095320  mov     [rsp+0A8h+var_68], r12d
0x180095325  lea     rax, aWsAccessLuShar; "%ws (Access: %lu, Share: %lu)"
0x18009532c  mov     [rsp+0A8h+var_70], r15d
0x180095331  lea     rcx, aSafecreatefile; "SafeCreateFile"
0x180095338  mov     r9d, 3
0x18009533e  mov     [rsp+0A8h+hTemplateFile], rsi
0x180095343  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rax
0x180095348  mov     edx, 1D6h
0x18009534d  mov     dword ptr [rsp+0A8h+dwCreationDisposition], edi
0x180095351  lea     r8d, [r9+1Dh]
0x180095355  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18009535a  mov     edx, 1D9h
0x18009535f  jmp     short loc_180095379
0x180095361  mov     rcx, rbx; hFile
0x180095364  call    cs:__imp_GetFileType
0x18009536a  cmp     eax, 1
0x18009536d  jz      short loc_1800953A1
0x18009536f  mov     edi, 8007006Eh
0x180095374  mov     edx, 1DDh; void *
0x180095379  mov     rcx, [rsp+0A8h]; this
0x180095381  lea     r8, aCW1SSrcClientL_8; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x180095388  mov     r9d, edi; char *
0x18009538b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095390  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180095394  jz      short loc_1800953A6
0x180095396  mov     rcx, rbx; hObject
0x180095399  call    cs:__imp_CloseHandle
0x18009539f  jmp     short loc_1800953A6
0x1800953a1  mov     [r14], rbx
0x1800953a4  xor     edi, edi
0x1800953a6  mov     eax, edi
0x1800953a8  add     rsp, 68h
0x1800953ac  pop     r15
0x1800953ae  pop     r14
0x1800953b0  pop     r13
0x1800953b2  pop     r12
0x1800953b4  pop     rdi
0x1800953b5  pop     rsi
0x1800953b6  pop     rbp
0x1800953b7  pop     rbx
0x1800953b8  retn
```
