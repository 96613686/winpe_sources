# CleanPath(ushort const *,ushort const *)

- ea: `0x180014e10`
- end: `0x180015244`
- name: `?CleanPath@@YAJPEBG0@Z`
- size: `1076`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180047730`

## callees

- `0x180008200`
- `0x180014e10`
- `0x1800217ec`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180099764`
- `0x180099c84`
- `0x18009a24c`
- `0x18009a354`
- `0x18009a378`
- `0x18009a3ac`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180015076`
- `KERNEL32!CreateFileW` at `0x180015076`
- `KERNEL32!GetLastError` at `0x1800150ba`
- `KERNEL32!GetLastError` at `0x18001512a`
- `KERNEL32!GetLastError` at `0x180015142`
- `KERNEL32!GetLastError` at `0x1800150ba`
- `KERNEL32!GetLastError` at `0x18001512a`
- `KERNEL32!GetLastError` at `0x180015142`
- `KERNEL32!CloseHandle` at `0x18001508c`
- `KERNEL32!CloseHandle` at `0x180015136`
- `KERNEL32!CloseHandle` at `0x1800151e2`
- `KERNEL32!CloseHandle` at `0x18001508c`
- `KERNEL32!CloseHandle` at `0x180015136`
- `KERNEL32!CloseHandle` at `0x1800151e2`
- `KERNEL32!FindFirstFileW` at `0x180014fcd`
- `KERNEL32!FindFirstFileW` at `0x180014fcd`
- `KERNEL32!Sleep` at `0x1800150e1`
- `KERNEL32!Sleep` at `0x1800150e1`
- `KERNEL32!SetFileInformationByHandle` at `0x180015120`
- `KERNEL32!SetFileInformationByHandle` at `0x180015120`
- `KERNEL32!FindNextFileW` at `0x180015158`
- `KERNEL32!FindNextFileW` at `0x180015158`
- `KERNEL32!FindClose` at `0x1800151f5`
- `KERNEL32!FindClose` at `0x1800151f5`

## string_xrefs

- `0x180014e50`: `CleanPath`

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
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[1] = 0;
  v24 = (LPCWSTR)qword_1800E8530;
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
0x180014e10  mov     [rsp-8+arg_10], rbx
0x180014e15  push    rbp
0x180014e16  push    rsi
0x180014e17  push    rdi
0x180014e18  push    r12
0x180014e1a  push    r13
0x180014e1c  push    r14
0x180014e1e  push    r15
0x180014e20  lea     rbp, [rsp-240h]
0x180014e28  sub     rsp, 340h
0x180014e2f  mov     rax, cs:__security_cookie
0x180014e36  xor     rax, rsp
0x180014e39  mov     [rbp+270h+var_40], rax
0x180014e40  mov     r14, rdx
0x180014e43  mov     r12, rcx
0x180014e46  mov     r9d, 1; unsigned __int16
0x180014e4c  lea     r8d, [r9+60h]; unsigned __int16
0x180014e50  lea     rdx, aCleanpath; "CleanPath"
0x180014e57  lea     rcx, [rsp+370h+var_300]; this
0x180014e5c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180014e61  lea     rax, qword_1800E8530
0x180014e68  mov     [rbp+270h+lpFileName], rax
0x180014e6c  xor     r13d, r13d
0x180014e6f  mov     [rbp+270h+var_2C0], r13
0x180014e73  mov     [rsp+370h+var_310], rax
0x180014e78  mov     qword ptr [rsp+370h+var_308], r13
0x180014e7d  xor     edx, edx; Val
0x180014e7f  mov     r8d, 250h; Size
0x180014e85  lea     rcx, [rbp+270h+FindFileData]; void *
0x180014e89  call    memset_0
0x180014e8e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014e92  mov     rdi, rax
0x180014e95  mov     rbx, rax
0x180014e98  mov     r15d, r13d
0x180014e9b  mov     dword ptr [rbp+270h+FileInformation], r13d
0x180014e9f  xorps   xmm0, xmm0
0x180014ea2  xor     eax, eax
0x180014ea4  movups  [rbp+270h+FileInformation+4], xmm0
0x180014ea8  movups  [rbp+270h+var_2A4], xmm0
0x180014eac  mov     [rbp+270h+var_294], eax
0x180014eaf  lea     eax, [rbx+6Fh]
0x180014eb2  test    r12, r12
0x180014eb5  jnz     short loc_180014EC5
0x180014eb7  mov     esi, 80070057h
0x180014ebc  mov     [rsp+370h+var_300], esi
0x180014ec0  jmp     loc_180015194
0x180014ec5  mov     [rsp+370h+var_2FC], ax
0x180014eca  mov     eax, 6Fh ; 'o'
0x180014ecf  test    r14, r14
0x180014ed2  jz      short loc_180014EB7
0x180014ed4  mov     [rsp+370h+var_300], r13d
0x180014ed9  mov     [rsp+370h+var_2FC], ax
0x180014ede  mov     edx, 208h; unsigned int
0x180014ee3  lea     rcx, [rbp+270h+lpFileName]; this
0x180014ee7  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180014eec  mov     esi, eax
0x180014eee  mov     [rsp+370h+var_300], eax
0x180014ef2  test    eax, eax
0x180014ef4  mov     eax, 74h ; 't'
0x180014ef9  js      loc_180015194
0x180014eff  mov     [rsp+370h+var_2FC], ax
0x180014f04  mov     edx, 208h; unsigned int
0x180014f09  lea     rcx, [rsp+370h+var_310]; this
0x180014f0e  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180014f13  mov     esi, eax
0x180014f15  mov     [rsp+370h+var_300], eax
0x180014f19  test    eax, eax
0x180014f1b  mov     eax, 75h ; 'u'
0x180014f20  js      loc_180015194
0x180014f26  mov     [rsp+370h+var_2FC], ax
0x180014f2b  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x180014f30  mov     qword ptr [rsp+370h+dwCreationDisposition], r13; unsigned __int16 *
0x180014f35  xor     r9d, r9d; unsigned __int16 *
0x180014f38  mov     r8, r14; unsigned __int16 *
0x180014f3b  mov     rdx, r12; unsigned __int16 *
0x180014f3e  lea     rcx, [rbp+270h+lpFileName]; this
0x180014f42  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180014f47  mov     esi, eax
0x180014f49  mov     [rsp+370h+var_300], eax
0x180014f4d  test    eax, eax
0x180014f4f  mov     eax, 77h ; 'w'
0x180014f54  js      loc_180015194
0x180014f5a  mov     [rsp+370h+var_2FC], ax
0x180014f5f  mov     rdx, r12; unsigned __int16 *
0x180014f62  lea     rcx, [rsp+370h+var_310]; this
0x180014f67  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180014f6c  mov     esi, eax
0x180014f6e  mov     [rsp+370h+var_300], eax
0x180014f72  test    eax, eax
0x180014f74  mov     eax, 79h ; 'y'
0x180014f79  js      loc_180015194
0x180014f7f  mov     [rsp+370h+var_2FC], ax
0x180014f84  lea     edx, [rax-1Dh]; unsigned __int16
0x180014f87  lea     rcx, [rsp+370h+var_310]; this
0x180014f8c  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x180014f91  mov     esi, eax
0x180014f93  mov     [rsp+370h+var_300], eax
0x180014f97  test    eax, eax
0x180014f99  mov     eax, 7Ah ; 'z'
0x180014f9e  js      loc_180015194
0x180014fa4  mov     [rsp+370h+var_2FC], ax
0x180014fa9  mov     r13d, [rsp+370h+var_308]
0x180014fae  mov     qword ptr [rbp+270h+var_2A4+4], r15
0x180014fb2  xorps   xmm0, xmm0
0x180014fb5  movdqu  [rbp+270h+FileInformation], xmm0
0x180014fba  mov     [rbp-38h], r15
0x180014fbe  mov     dword ptr [rbp+270h+var_2A4+0Ch], 80h
0x180014fc5  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x180014fc9  mov     rcx, [rbp+270h+lpFileName]; lpFileName
0x180014fcd  call    cs:__imp_FindFirstFileW
0x180014fd3  mov     rdi, rax
0x180014fd6  xor     eax, eax
0x180014fd8  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180014fdc  setnz   al
0x180014fdf  mov     r14d, 8Fh
0x180014fe5  mov     r9d, 8Eh
0x180014feb  test    eax, eax
0x180014fed  jz      loc_180015173
0x180014ff3  test    byte ptr [rbp+270h+FindFileData.dwFileAttributes], 10h
0x180014ff7  jnz     loc_180015151
0x180014ffd  mov     edx, r13d; unsigned int
0x180015000  lea     rcx, [rsp+370h+var_310]; this
0x180015005  call    ?SetLength@CBsString@@QEAAJK@Z; CBsString::SetLength(ulong)
0x18001500a  mov     esi, eax
0x18001500c  mov     [rsp+370h+var_300], eax
0x180015010  test    eax, eax
0x180015012  js      loc_18001516B
0x180015018  mov     [rsp+370h+var_2FC], r9w
0x18001501e  lea     rdx, [rbp+270h+FindFileData.cFileName]; unsigned __int16 *
0x180015022  lea     rcx, [rsp+370h+var_310]; this
0x180015027  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18001502c  mov     esi, eax
0x18001502e  mov     [rsp+370h+var_300], eax
0x180015032  test    eax, eax
0x180015034  js      loc_180015163
0x18001503a  mov     [rsp+370h+var_2FC], r14w
0x180015040  mov     r12d, 190h
0x180015046  mov     r14d, 5
0x18001504c  mov     [rsp+370h+hTemplateFile], 0; hTemplateFile
0x180015055  mov     [rsp+370h+dwFlagsAndAttributes], 6000000h; dwFlagsAndAttributes
0x18001505d  mov     [rsp+370h+dwCreationDisposition], 3; dwCreationDisposition
0x180015065  xor     r9d, r9d; lpSecurityAttributes
0x180015068  mov     edx, 10180h; dwDesiredAccess
0x18001506d  lea     r8d, [r9+7]; dwShareMode
0x180015071  mov     rcx, [rsp+370h+var_310]; lpFileName
0x180015076  call    cs:__imp_CreateFileW
0x18001507c  mov     rsi, rax
0x18001507f  lea     rax, [rbx-1]
0x180015083  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180015087  ja      short loc_180015092
0x180015089  mov     rcx, rbx; hObject
0x18001508c  call    cs:__imp_CloseHandle
0x180015092  mov     rbx, rsi
0x180015095  lea     rax, [rsi+1]
0x180015099  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001509f  jnz     short loc_1800150F8
0x1800150a1  mov     rax, cs:WPP_GLOBAL_Control
0x1800150a8  lea     rcx, WPP_GLOBAL_Control
0x1800150af  cmp     rax, rcx
0x1800150b2  jz      short loc_1800150DE
0x1800150b4  test    byte ptr [rax+1Ch], 20h
0x1800150b8  jz      short loc_1800150DE
0x1800150ba  call    cs:__imp_GetLastError
0x1800150c0  mov     [rsp+370h+dwFlagsAndAttributes], r14d
0x1800150c5  mov     [rsp+370h+dwCreationDisposition], eax
0x1800150c9  mov     r9, [rsp+370h+var_310]
0x1800150ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150d5  mov     rcx, [rcx+10h]
0x1800150d9  call    WPP_SF_SDd
0x1800150de  mov     ecx, r12d; dwMilliseconds
0x1800150e1  call    cs:__imp_Sleep
0x1800150e7  mov     eax, r12d
0x1800150ea  shr     eax, 1
0x1800150ec  add     r12d, eax
0x1800150ef  dec     r14d
0x1800150f2  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800150f6  jz      short loc_1800150FD
0x1800150f8  test    rsi, rsi
0x1800150fb  jnz     short loc_180015111
0x1800150fd  test    r14d, r14d
0x180015100  jnz     loc_18001504C
0x180015106  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001510a  jz      short loc_180015142
0x18001510c  test    rsi, rsi
0x18001510f  jz      short loc_180015142
0x180015111  mov     r9d, 28h ; '('; dwBufferSize
0x180015117  lea     r8, [rbp+270h+FileInformation]; lpFileInformation
0x18001511b  xor     edx, edx; FileInformationClass
0x18001511d  mov     rcx, rsi; hFile
0x180015120  call    cs:__imp_SetFileInformationByHandle
0x180015126  test    eax, eax
0x180015128  jnz     short loc_180015133
0x18001512a  call    cs:__imp_GetLastError
0x180015130  mov     r15d, eax
0x180015133  mov     rcx, rsi; hObject
0x180015136  call    cs:__imp_CloseHandle
0x18001513c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015140  jmp     short loc_18001514B
0x180015142  call    cs:__imp_GetLastError
0x180015148  mov     r15d, eax
0x18001514b  mov     r14d, 8Fh
0x180015151  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x180015155  mov     rcx, rdi; hFindFile
0x180015158  call    cs:__imp_FindNextFileW
0x18001515e  jmp     loc_180014FE5
0x180015163  mov     [rsp+370h+var_2FA], r14w
0x180015169  jmp     short loc_180015199
0x18001516b  mov     [rsp+370h+var_2FA], r9w
0x180015171  jmp     short loc_180015199
0x180015173  test    r15d, r15d
0x180015176  jg      short loc_18001517D
0x180015178  mov     esi, r15d
0x18001517b  jmp     short loc_180015187
0x18001517d  movzx   esi, r15w
0x180015181  or      esi, 80070000h
0x180015187  mov     [rsp+370h+var_300], esi
0x18001518b  mov     eax, 0CDh
0x180015190  test    esi, esi
0x180015192  jns     short loc_1800151D0
0x180015194  mov     [rsp+370h+var_2FA], ax
0x180015199  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151a0  lea     rax, WPP_GLOBAL_Control
0x1800151a7  cmp     rcx, rax
0x1800151aa  jz      short loc_1800151D5
0x1800151ac  test    byte ptr [rcx+1Ch], 40h
0x1800151b0  jz      short loc_1800151D5
0x1800151b2  mov     edx, 0Bh
0x1800151b7  mov     r9d, r15d
0x1800151ba  lea     r8, WPP_20bb8c270ac93ab6d641335ef0919b68_Traceguids
0x1800151c1  mov     rcx, [rcx+10h]
0x1800151c5  call    WPP_SF_d
0x1800151ca  mov     esi, [rsp+370h+var_300]
0x1800151ce  jmp     short loc_1800151D5
0x1800151d0  mov     [rsp+370h+var_2FC], ax
0x1800151d5  lea     rax, [rbx-1]
0x1800151d9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800151dd  ja      short loc_1800151E8
0x1800151df  mov     rcx, rbx; hObject
0x1800151e2  call    cs:__imp_CloseHandle
0x1800151e8  lea     rcx, [rdi-1]
0x1800151ec  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800151f0  ja      short loc_1800151FB
0x1800151f2  mov     rcx, rdi; hFindFile
0x1800151f5  call    cs:__imp_FindClose
0x1800151fb  lea     rcx, [rsp+370h+var_310]; this
0x180015200  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180015205  lea     rcx, [rbp+270h+lpFileName]; this
0x180015209  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001520e  lea     rcx, [rsp+370h+var_300]; this
0x180015213  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180015218  mov     eax, esi
0x18001521a  mov     rcx, [rbp+270h+var_40]
0x180015221  xor     rcx, rsp; StackCookie
0x180015224  call    __security_check_cookie
0x180015229  mov     rbx, [rsp+370h+arg_10]
0x180015231  add     rsp, 340h
0x180015238  pop     r15
0x18001523a  pop     r14
0x18001523c  pop     r13
0x18001523e  pop     r12
0x180015240  pop     rdi
0x180015241  pop     rsi
0x180015242  pop     rbp
0x180015243  retn
```
