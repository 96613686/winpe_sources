# SafeCreateFile(void * *,ulong,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x18000eba0`
- end: `0x18000ed7d`
- name: `?SafeCreateFile@@YAJPEAPEAXKPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `477`
- prototype: `int(void **, unsigned int, const wchar_t *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d158`
- `0x18000deec`

## callees

- `0x180003950`
- `0x18000956c`
- `0x18000e810`
- `0x18000e970`
- `0x18000eabc`
- `0x18000eb44`
- `0x18000eba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed5d`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18000ed28`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18000ed28`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000eca5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000eca5`

## string_xrefs

- `0x18000ece9`: `%ws (Access: %lu, Share: %lu)`
- `0x18000ecf5`: `SafeCreateFile`

## pseudocode

```c
__int64 __fastcall SafeCreateFile(
        void **a1,
        int a2,
        const wchar_t *a3,
        DWORD a4,
        DWORD dwShareMode,
        struct _SECURITY_ATTRIBUTES *a6,
        DWORD a7,
        unsigned int a8)
{
  __int64 v11; // rbx
  __int64 v12; // rdx
  signed int v13; // edi
  HANDLE FileW; // rax
  signed int LastError; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-88h]
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
              dwCreationDisposition = v13;
              WUTrace("SafeCreateFile", 470, 32, 3);
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
0x18000eba0  push    rbx
0x18000eba2  push    rbp
0x18000eba3  push    rsi
0x18000eba4  push    rdi
0x18000eba5  push    r12
0x18000eba7  push    r13
0x18000eba9  push    r14
0x18000ebab  push    r15
0x18000ebad  sub     rsp, 68h
0x18000ebb1  mov     r12d, [rsp+0A8h+dwShareMode]
0x18000ebb9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ebbd  mov     r13d, [rsp+0A8h+arg_30]
0x18000ebc5  mov     r15d, r9d
0x18000ebc8  mov     ebp, [rsp+0A8h+arg_38]
0x18000ebcf  mov     rsi, r8
0x18000ebd2  mov     edi, edx
0x18000ebd4  mov     r14, rcx
0x18000ebd7  mov     rbx, rax
0x18000ebda  test    r8, r8
0x18000ebdd  jnz     short loc_18000EBE6
0x18000ebdf  mov     edx, 1ABh
0x18000ebe4  jmp     short loc_18000EBFF
0x18000ebe6  test    r14, r14
0x18000ebe9  jnz     short loc_18000EBF2
0x18000ebeb  mov     edx, 1ACh
0x18000ebf0  jmp     short loc_18000EBFF
0x18000ebf2  test    edi, 0FFFFFFFCh
0x18000ebf8  jz      short loc_18000EC09
0x18000ebfa  mov     edx, 1ADh
0x18000ebff  mov     edi, 80070057h
0x18000ec04  jmp     loc_18000ED3D
0x18000ec09  mov     [rcx], rax
0x18000ec0c  xor     edx, edx
0x18000ec0e  mov     rcx, rsi
0x18000ec11  call    SkipPathDrivePart
0x18000ec16  test    eax, eax
0x18000ec18  jnz     short loc_18000EC29
0x18000ec1a  mov     edi, 80070003h
0x18000ec1f  mov     edx, 1B2h
0x18000ec24  jmp     loc_18000ED3D
0x18000ec29  mov     rcx, rsi
0x18000ec2c  call    DoesPathContainDotDot
0x18000ec31  test    eax, eax
0x18000ec33  jz      short loc_18000EC44
0x18000ec35  mov     edi, 800700A1h
0x18000ec3a  mov     edx, 1B5h
0x18000ec3f  jmp     loc_18000ED3D
0x18000ec44  mov     rcx, rsi
0x18000ec47  call    DoesPathContainStreamSyntax
0x18000ec4c  test    eax, eax
0x18000ec4e  jz      short loc_18000EC5F
0x18000ec50  mov     edi, 8007007Bh
0x18000ec55  mov     edx, 1B8h
0x18000ec5a  jmp     loc_18000ED3D
0x18000ec5f  mov     r8d, edi
0x18000ec62  mov     rcx, rsi; lpszFileName
0x18000ec65  and     edi, 1
0x18000ec68  and     r8d, 2
0x18000ec6c  mov     edx, edi
0x18000ec6e  call    CheckValidDriveType
0x18000ec73  mov     edi, eax
0x18000ec75  test    eax, eax
0x18000ec77  jns     short loc_18000EC83
0x18000ec79  mov     edx, 1BDh
0x18000ec7e  jmp     loc_18000ED3D
0x18000ec83  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x18000ec8c  bts     ebp, 14h
0x18000ec90  mov     [rsp+0A8h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x18000ec94  xor     r9d, r9d; lpSecurityAttributes
0x18000ec97  mov     r8d, r12d; dwShareMode
0x18000ec9a  mov     [rsp+0A8h+dwCreationDisposition], r13d; int
0x18000ec9f  mov     edx, r15d; dwDesiredAccess
0x18000eca2  mov     rcx, rsi; lpFileName
0x18000eca5  call    cs:__imp_CreateFileW
0x18000ecab  mov     rbx, rax
0x18000ecae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ecb2  jnz     short loc_18000ED25
0x18000ecb4  call    cs:__imp_GetLastError
0x18000ecba  movzx   edi, ax
0x18000ecbd  or      edi, 80070000h
0x18000ecc3  test    eax, eax
0x18000ecc5  cmovle  edi, eax
0x18000ecc8  test    edi, edi
0x18000ecca  js      short loc_18000ECD3
0x18000eccc  mov     edi, 8000FFFFh
0x18000ecd1  jmp     short loc_18000ED1E
0x18000ecd3  mov     eax, edi
0x18000ecd5  cmp     edi, 80070005h
0x18000ecdb  jz      short loc_18000ECE4
0x18000ecdd  cmp     eax, 80070020h
0x18000ece2  jnz     short loc_18000ED1E
0x18000ece4  mov     [rsp+0A8h+var_68], r12d
0x18000ece9  lea     rax, aWsAccessLuShar; "%ws (Access: %lu, Share: %lu)"
0x18000ecf0  mov     [rsp+0A8h+var_70], r15d
0x18000ecf5  lea     rcx, aSafecreatefile; "SafeCreateFile"
0x18000ecfc  mov     r9d, 3
0x18000ed02  mov     [rsp+0A8h+hTemplateFile], rsi
0x18000ed07  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rax
0x18000ed0c  mov     edx, 1D6h
0x18000ed11  mov     [rsp+0A8h+dwCreationDisposition], edi
0x18000ed15  lea     r8d, [r9+1Dh]
0x18000ed19  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18000ed1e  mov     edx, 1D9h
0x18000ed23  jmp     short loc_18000ED3D
0x18000ed25  mov     rcx, rbx; hFile
0x18000ed28  call    cs:__imp_GetFileType
0x18000ed2e  cmp     eax, 1
0x18000ed31  jz      short loc_18000ED65
0x18000ed33  mov     edi, 8007006Eh
0x18000ed38  mov     edx, 1DDh; void *
0x18000ed3d  mov     rcx, [rsp+0A8h]; this
0x18000ed45  lea     r8, aCW1SSrcClientL_8; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000ed4c  mov     r9d, edi; char *
0x18000ed4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ed54  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000ed58  jz      short loc_18000ED6A
0x18000ed5a  mov     rcx, rbx; hObject
0x18000ed5d  call    cs:__imp_CloseHandle
0x18000ed63  jmp     short loc_18000ED6A
0x18000ed65  mov     [r14], rbx
0x18000ed68  xor     edi, edi
0x18000ed6a  mov     eax, edi
0x18000ed6c  add     rsp, 68h
0x18000ed70  pop     r15
0x18000ed72  pop     r14
0x18000ed74  pop     r13
0x18000ed76  pop     r12
0x18000ed78  pop     rdi
0x18000ed79  pop     rsi
0x18000ed7a  pop     rbp
0x18000ed7b  pop     rbx
0x18000ed7c  retn
```
