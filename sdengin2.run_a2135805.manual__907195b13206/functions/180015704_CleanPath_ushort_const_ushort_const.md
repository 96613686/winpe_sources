# CleanPath(ushort const *,ushort const *)

- ea: `0x180015704`
- end: `0x180015b81`
- name: `?CleanPath@@YAJPEBG0@Z`
- size: `1149`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x1800492f0`

## callees

- `0x1800083a0`
- `0x180015704`
- `0x18002241c`
- `0x180072e08`
- `0x180072f14`
- `0x18009dd7c`
- `0x18009e2e8`
- `0x18009e904`
- `0x18009ea0c`
- `0x18009ea34`
- `0x18009ea6c`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180015970`
- `KERNEL32!CreateFileW` at `0x180015970`
- `KERNEL32!GetLastError` at `0x1800159c0`
- `KERNEL32!GetLastError` at `0x180015a42`
- `KERNEL32!GetLastError` at `0x180015a66`
- `KERNEL32!GetLastError` at `0x1800159c0`
- `KERNEL32!GetLastError` at `0x180015a42`
- `KERNEL32!GetLastError` at `0x180015a66`
- `KERNEL32!CloseHandle` at `0x18001598c`
- `KERNEL32!CloseHandle` at `0x180015a54`
- `KERNEL32!CloseHandle` at `0x180015b12`
- `KERNEL32!CloseHandle` at `0x18001598c`
- `KERNEL32!CloseHandle` at `0x180015a54`
- `KERNEL32!CloseHandle` at `0x180015b12`
- `KERNEL32!FindFirstFileW` at `0x1800158c1`
- `KERNEL32!FindFirstFileW` at `0x1800158c1`
- `KERNEL32!Sleep` at `0x1800159ed`
- `KERNEL32!Sleep` at `0x1800159ed`
- `KERNEL32!SetFileInformationByHandle` at `0x180015a32`
- `KERNEL32!SetFileInformationByHandle` at `0x180015a32`
- `KERNEL32!FindNextFileW` at `0x180015a82`
- `KERNEL32!FindNextFileW` at `0x180015a82`
- `KERNEL32!FindClose` at `0x180015b2b`
- `KERNEL32!FindClose` at `0x180015b2b`

## string_xrefs

- `0x180015744`: `CleanPath`

## pseudocode

```c
__int64 __fastcall CleanPath(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  __int64 FirstFileW; // rdi
  __int64 v5; // rbx
  signed int v6; // r15d
  __int16 v7; // ax
  signed int v8; // esi
  unsigned int v9; // r13d
  BOOL i; // eax
  __int16 v11; // r9
  DWORD v12; // r12d
  int v13; // r14d
  HANDLE FileW; // rsi
  char LastError; // al
  int v16; // edx
  int v17; // r8d
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v20; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v21; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v22; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v23; // [rsp+50h] [rbp-B0h]
  LPCWSTR v24; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v25[2]; // [rsp+68h] [rbp-98h]
  int v26; // [rsp+70h] [rbp-90h] BYREF
  __int16 v27; // [rsp+74h] [rbp-8Ch]
  __int16 v28; // [rsp+76h] [rbp-8Ah]
  LPCWSTR lpFileName[2]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE FileInformation[36]; // [rsp+B8h] [rbp-48h] BYREF
  int v31; // [rsp+DCh] [rbp-24h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-20h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v26, "CleanPath", 0x61u, 1u);
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  lpFileName[1] = 0;
  v24 = (LPCWSTR)qword_1800EE510;
  *(_QWORD *)v25 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = -1;
  v5 = -1;
  v6 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v31 = 0;
  v7 = 110;
  if ( a1 && (v27 = 110, v7 = 111, a2) )
  {
    v26 = 0;
    v27 = 111;
    v8 = CBsString::ExtendBuffer((CBsString *)lpFileName, 0x208u);
    v26 = v8;
    v7 = 116;
    if ( v8 >= 0 )
    {
      v27 = 116;
      v8 = CBsString::ExtendBuffer((CBsString *)&v24, 0x208u);
      v26 = v8;
      v7 = 117;
      if ( v8 >= 0 )
      {
        v27 = 117;
        v8 = CBsString::SetPath((CBsString *)lpFileName, a1, a2, 0, 0, 0, hTemplateFile, v20, v21, v22, v23);
        v26 = v8;
        v7 = 119;
        if ( v8 >= 0 )
        {
          v27 = 119;
          v8 = CBsString::Set((CBsString *)&v24, a1);
          v26 = v8;
          v7 = 121;
          if ( v8 >= 0 )
          {
            v27 = 121;
            v8 = CBsString::Trailing((CBsString *)&v24, 0x5Cu);
            v26 = v8;
            v7 = 122;
            if ( v8 >= 0 )
            {
              v27 = 122;
              v9 = v25[0];
              memset(FileInformation, 0, 32);
              *(_DWORD *)&FileInformation[32] = 128;
              FirstFileW = (__int64)FindFirstFileW(lpFileName[0], &FindFileData);
              for ( i = FirstFileW != -1; i; i = FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
              {
                if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
                {
                  v8 = CBsString::SetLength((CBsString *)&v24, v9);
                  v26 = v8;
                  if ( v8 < 0 )
                  {
                    v28 = v11;
                    goto LABEL_36;
                  }
                  v27 = v11;
                  v8 = CBsString::Append((CBsString *)&v24, FindFileData.cFileName);
                  v26 = v8;
                  if ( v8 < 0 )
                  {
                    v28 = 143;
                    goto LABEL_36;
                  }
                  v27 = 143;
                  v12 = 400;
                  v13 = 5;
                  while ( 1 )
                  {
                    FileW = CreateFileW(v24, 0x10180u, 7u, 0, 3u, 0x6000000u, 0);
                    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                      CloseHandle((HANDLE)v5);
                    v5 = (__int64)FileW;
                    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
                      goto LABEL_22;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
                    {
                      LastError = GetLastError();
                      WPP_SF_SDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v17, (_DWORD)v24, LastError, v13);
                    }
                    Sleep(v12);
                    v12 += v12 >> 1;
                    --v13;
                    if ( FileW != (HANDLE)-1LL )
                    {
LABEL_22:
                      if ( FileW )
                        break;
                    }
                    if ( !v13 )
                    {
                      v6 = GetLastError();
                      goto LABEL_28;
                    }
                  }
                  if ( !SetFileInformationByHandle(FileW, FileBasicInfo, FileInformation, 0x28u) )
                    v6 = GetLastError();
                  CloseHandle(FileW);
                  v5 = -1;
                }
LABEL_28:
                ;
              }
              v8 = v6 > 0 ? (unsigned __int16)v6 | 0x80070000 : v6;
              v26 = v8;
              v7 = 205;
              if ( v8 >= 0 )
              {
                v27 = 205;
                goto LABEL_40;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v8 = -2147024809;
    v26 = -2147024809;
  }
  v28 = v7;
LABEL_36:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_20bb8c270ac93ab6d641335ef0919b68_Traceguids,
      (unsigned int)v6);
    v8 = v26;
  }
LABEL_40:
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v5);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose((HANDLE)FirstFileW);
  CBsString::_Release((CBsString *)&v24);
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v26);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015704  mov     [rsp-8+arg_10], rbx
0x180015709  push    rbp
0x18001570a  push    rsi
0x18001570b  push    rdi
0x18001570c  push    r12
0x18001570e  push    r13
0x180015710  push    r14
0x180015712  push    r15
0x180015714  lea     rbp, [rsp-240h]
0x18001571c  sub     rsp, 340h
0x180015723  mov     rax, cs:__security_cookie
0x18001572a  xor     rax, rsp
0x18001572d  mov     [rbp+270h+var_40], rax
0x180015734  mov     r14, rdx
0x180015737  mov     r12, rcx
0x18001573a  mov     r9d, 1; unsigned __int16
0x180015740  lea     r8d, [r9+60h]; unsigned __int16
0x180015744  lea     rdx, aCleanpath; "CleanPath"
0x18001574b  lea     rcx, [rsp+370h+var_300]; this
0x180015750  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180015755  lea     rax, qword_1800EE510
0x18001575c  mov     [rbp+270h+lpFileName], rax
0x180015760  xor     r13d, r13d
0x180015763  mov     [rbp+270h+var_2C0], r13
0x180015767  mov     [rsp+370h+var_310], rax
0x18001576c  mov     qword ptr [rsp+370h+var_308], r13
0x180015771  xor     edx, edx; Val
0x180015773  mov     r8d, 250h; Size
0x180015779  lea     rcx, [rbp+270h+FindFileData]; void *
0x18001577d  call    memset_0
0x180015782  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015786  mov     rdi, rax
0x180015789  mov     rbx, rax
0x18001578c  mov     r15d, r13d
0x18001578f  mov     dword ptr [rbp+270h+FileInformation], r13d
0x180015793  xorps   xmm0, xmm0
0x180015796  xor     eax, eax
0x180015798  movups  [rbp+270h+FileInformation+4], xmm0
0x18001579c  movups  [rbp+270h+var_2A4], xmm0
0x1800157a0  mov     [rbp+270h+var_294], eax
0x1800157a3  lea     eax, [rbx+6Fh]
0x1800157a6  test    r12, r12
0x1800157a9  jnz     short loc_1800157B9
0x1800157ab  mov     esi, 80070057h
0x1800157b0  mov     [rsp+370h+var_300], esi
0x1800157b4  jmp     loc_180015AC4
0x1800157b9  mov     [rsp+370h+var_2FC], ax
0x1800157be  mov     eax, 6Fh ; 'o'
0x1800157c3  test    r14, r14
0x1800157c6  jz      short loc_1800157AB
0x1800157c8  mov     [rsp+370h+var_300], r13d
0x1800157cd  mov     [rsp+370h+var_2FC], ax
0x1800157d2  mov     edx, 208h; unsigned int
0x1800157d7  lea     rcx, [rbp+270h+lpFileName]; this
0x1800157db  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x1800157e0  mov     esi, eax
0x1800157e2  mov     [rsp+370h+var_300], eax
0x1800157e6  test    eax, eax
0x1800157e8  mov     eax, 74h ; 't'
0x1800157ed  js      loc_180015AC4
0x1800157f3  mov     [rsp+370h+var_2FC], ax
0x1800157f8  mov     edx, 208h; unsigned int
0x1800157fd  lea     rcx, [rsp+370h+var_310]; this
0x180015802  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180015807  mov     esi, eax
0x180015809  mov     [rsp+370h+var_300], eax
0x18001580d  test    eax, eax
0x18001580f  mov     eax, 75h ; 'u'
0x180015814  js      loc_180015AC4
0x18001581a  mov     [rsp+370h+var_2FC], ax
0x18001581f  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x180015824  mov     qword ptr [rsp+370h+dwCreationDisposition], r13; unsigned __int16 *
0x180015829  xor     r9d, r9d; unsigned __int16 *
0x18001582c  mov     r8, r14; unsigned __int16 *
0x18001582f  mov     rdx, r12; unsigned __int16 *
0x180015832  lea     rcx, [rbp+270h+lpFileName]; this
0x180015836  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001583b  mov     esi, eax
0x18001583d  mov     [rsp+370h+var_300], eax
0x180015841  test    eax, eax
0x180015843  mov     eax, 77h ; 'w'
0x180015848  js      loc_180015AC4
0x18001584e  mov     [rsp+370h+var_2FC], ax
0x180015853  mov     rdx, r12; unsigned __int16 *
0x180015856  lea     rcx, [rsp+370h+var_310]; this
0x18001585b  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180015860  mov     esi, eax
0x180015862  mov     [rsp+370h+var_300], eax
0x180015866  test    eax, eax
0x180015868  mov     eax, 79h ; 'y'
0x18001586d  js      loc_180015AC4
0x180015873  mov     [rsp+370h+var_2FC], ax
0x180015878  lea     edx, [rax-1Dh]; unsigned __int16
0x18001587b  lea     rcx, [rsp+370h+var_310]; this
0x180015880  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x180015885  mov     esi, eax
0x180015887  mov     [rsp+370h+var_300], eax
0x18001588b  test    eax, eax
0x18001588d  mov     eax, 7Ah ; 'z'
0x180015892  js      loc_180015AC4
0x180015898  mov     [rsp+370h+var_2FC], ax
0x18001589d  mov     r13d, [rsp+370h+var_308]
0x1800158a2  mov     qword ptr [rbp+270h+var_2A4+4], r15
0x1800158a6  xorps   xmm0, xmm0
0x1800158a9  movdqu  [rbp+270h+FileInformation], xmm0
0x1800158ae  mov     [rbp-38h], r15
0x1800158b2  mov     dword ptr [rbp+270h+var_2A4+0Ch], 80h
0x1800158b9  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x1800158bd  mov     rcx, [rbp+270h+lpFileName]; lpFileName
0x1800158c1  call    cs:__imp_FindFirstFileW
0x1800158c8  nop     dword ptr [rax+rax+00h]
0x1800158cd  mov     rdi, rax
0x1800158d0  xor     eax, eax
0x1800158d2  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800158d6  setnz   al
0x1800158d9  mov     r14d, 8Fh
0x1800158df  mov     r9d, 8Eh
0x1800158e5  test    eax, eax
0x1800158e7  jz      loc_180015AA3
0x1800158ed  test    byte ptr [rbp+270h+FindFileData.dwFileAttributes], 10h
0x1800158f1  jnz     loc_180015A7B
0x1800158f7  mov     edx, r13d; unsigned int
0x1800158fa  lea     rcx, [rsp+370h+var_310]; this
0x1800158ff  call    ?SetLength@CBsString@@QEAAJK@Z; CBsString::SetLength(ulong)
0x180015904  mov     esi, eax
0x180015906  mov     [rsp+370h+var_300], eax
0x18001590a  test    eax, eax
0x18001590c  js      loc_180015A9B
0x180015912  mov     [rsp+370h+var_2FC], r9w
0x180015918  lea     rdx, [rbp+270h+FindFileData.cFileName]; unsigned __int16 *
0x18001591c  lea     rcx, [rsp+370h+var_310]; this
0x180015921  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180015926  mov     esi, eax
0x180015928  mov     [rsp+370h+var_300], eax
0x18001592c  test    eax, eax
0x18001592e  js      loc_180015A93
0x180015934  mov     [rsp+370h+var_2FC], r14w
0x18001593a  mov     r12d, 190h
0x180015940  mov     r14d, 5
0x180015946  mov     [rsp+370h+hTemplateFile], 0; hTemplateFile
0x18001594f  mov     [rsp+370h+dwFlagsAndAttributes], 6000000h; dwFlagsAndAttributes
0x180015957  mov     [rsp+370h+dwCreationDisposition], 3; dwCreationDisposition
0x18001595f  xor     r9d, r9d; lpSecurityAttributes
0x180015962  mov     edx, 10180h; dwDesiredAccess
0x180015967  lea     r8d, [r9+7]; dwShareMode
0x18001596b  mov     rcx, [rsp+370h+var_310]; lpFileName
0x180015970  call    cs:__imp_CreateFileW
0x180015977  nop     dword ptr [rax+rax+00h]
0x18001597c  mov     rsi, rax
0x18001597f  lea     rax, [rbx-1]
0x180015983  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180015987  ja      short loc_180015998
0x180015989  mov     rcx, rbx; hObject
0x18001598c  call    cs:__imp_CloseHandle
0x180015993  nop     dword ptr [rax+rax+00h]
0x180015998  mov     rbx, rsi
0x18001599b  lea     rax, [rsi+1]
0x18001599f  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800159a5  jnz     short loc_180015A0A
0x1800159a7  mov     rax, cs:WPP_GLOBAL_Control
0x1800159ae  lea     rcx, WPP_GLOBAL_Control
0x1800159b5  cmp     rax, rcx
0x1800159b8  jz      short loc_1800159EA
0x1800159ba  test    byte ptr [rax+1Ch], 20h
0x1800159be  jz      short loc_1800159EA
0x1800159c0  call    cs:__imp_GetLastError
0x1800159c7  nop     dword ptr [rax+rax+00h]
0x1800159cc  mov     [rsp+370h+dwFlagsAndAttributes], r14d
0x1800159d1  mov     [rsp+370h+dwCreationDisposition], eax
0x1800159d5  mov     r9, [rsp+370h+var_310]
0x1800159da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800159e1  mov     rcx, [rcx+10h]
0x1800159e5  call    WPP_SF_SDd
0x1800159ea  mov     ecx, r12d; dwMilliseconds
0x1800159ed  call    cs:__imp_Sleep
0x1800159f4  nop     dword ptr [rax+rax+00h]
0x1800159f9  mov     eax, r12d
0x1800159fc  shr     eax, 1
0x1800159fe  add     r12d, eax
0x180015a01  dec     r14d
0x180015a04  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180015a08  jz      short loc_180015A0F
0x180015a0a  test    rsi, rsi
0x180015a0d  jnz     short loc_180015A23
0x180015a0f  test    r14d, r14d
0x180015a12  jnz     loc_180015946
0x180015a18  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180015a1c  jz      short loc_180015A66
0x180015a1e  test    rsi, rsi
0x180015a21  jz      short loc_180015A66
0x180015a23  mov     r9d, 28h ; '('; dwBufferSize
0x180015a29  lea     r8, [rbp+270h+FileInformation]; lpFileInformation
0x180015a2d  xor     edx, edx; FileInformationClass
0x180015a2f  mov     rcx, rsi; hFile
0x180015a32  call    cs:__imp_SetFileInformationByHandle
0x180015a39  nop     dword ptr [rax+rax+00h]
0x180015a3e  test    eax, eax
0x180015a40  jnz     short loc_180015A51
0x180015a42  call    cs:__imp_GetLastError
0x180015a49  nop     dword ptr [rax+rax+00h]
0x180015a4e  mov     r15d, eax
0x180015a51  mov     rcx, rsi; hObject
0x180015a54  call    cs:__imp_CloseHandle
0x180015a5b  nop     dword ptr [rax+rax+00h]
0x180015a60  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015a64  jmp     short loc_180015A75
0x180015a66  call    cs:__imp_GetLastError
0x180015a6d  nop     dword ptr [rax+rax+00h]
0x180015a72  mov     r15d, eax
0x180015a75  mov     r14d, 8Fh
0x180015a7b  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x180015a7f  mov     rcx, rdi; hFindFile
0x180015a82  call    cs:__imp_FindNextFileW
0x180015a89  nop     dword ptr [rax+rax+00h]
0x180015a8e  jmp     loc_1800158DF
0x180015a93  mov     [rsp+370h+var_2FA], r14w
0x180015a99  jmp     short loc_180015AC9
0x180015a9b  mov     [rsp+370h+var_2FA], r9w
0x180015aa1  jmp     short loc_180015AC9
0x180015aa3  test    r15d, r15d
0x180015aa6  jg      short loc_180015AAD
0x180015aa8  mov     esi, r15d
0x180015aab  jmp     short loc_180015AB7
0x180015aad  movzx   esi, r15w
0x180015ab1  or      esi, 80070000h
0x180015ab7  mov     [rsp+370h+var_300], esi
0x180015abb  mov     eax, 0CDh
0x180015ac0  test    esi, esi
0x180015ac2  jns     short loc_180015B00
0x180015ac4  mov     [rsp+370h+var_2FA], ax
0x180015ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ad0  lea     rax, WPP_GLOBAL_Control
0x180015ad7  cmp     rcx, rax
0x180015ada  jz      short loc_180015B05
0x180015adc  test    byte ptr [rcx+1Ch], 40h
0x180015ae0  jz      short loc_180015B05
0x180015ae2  mov     edx, 0Bh
0x180015ae7  mov     r9d, r15d
0x180015aea  lea     r8, WPP_20bb8c270ac93ab6d641335ef0919b68_Traceguids
0x180015af1  mov     rcx, [rcx+10h]
0x180015af5  call    WPP_SF_d
0x180015afa  mov     esi, [rsp+370h+var_300]
0x180015afe  jmp     short loc_180015B05
0x180015b00  mov     [rsp+370h+var_2FC], ax
0x180015b05  lea     rax, [rbx-1]
0x180015b09  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180015b0d  ja      short loc_180015B1E
0x180015b0f  mov     rcx, rbx; hObject
0x180015b12  call    cs:__imp_CloseHandle
0x180015b19  nop     dword ptr [rax+rax+00h]
0x180015b1e  lea     rcx, [rdi-1]
0x180015b22  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180015b26  ja      short loc_180015B37
0x180015b28  mov     rcx, rdi; hFindFile
0x180015b2b  call    cs:__imp_FindClose
0x180015b32  nop     dword ptr [rax+rax+00h]
0x180015b37  lea     rcx, [rsp+370h+var_310]; this
0x180015b3c  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180015b41  lea     rcx, [rbp+270h+lpFileName]; this
0x180015b45  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180015b4a  lea     rcx, [rsp+370h+var_300]; this
0x180015b4f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180015b54  mov     eax, esi
0x180015b56  mov     rcx, [rbp+270h+var_40]
0x180015b5d  xor     rcx, rsp; StackCookie
0x180015b60  call    __security_check_cookie
0x180015b65  mov     rbx, [rsp+370h+arg_10]
0x180015b6d  add     rsp, 340h
0x180015b74  pop     r15
0x180015b76  pop     r14
0x180015b78  pop     r13
0x180015b7a  pop     r12
0x180015b7c  pop     rdi
0x180015b7d  pop     rsi
0x180015b7e  pop     rbp
0x180015b7f  retn
```
