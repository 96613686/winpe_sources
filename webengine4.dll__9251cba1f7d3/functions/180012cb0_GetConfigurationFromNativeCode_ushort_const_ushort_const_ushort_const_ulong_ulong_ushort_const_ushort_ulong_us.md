# GetConfigurationFromNativeCode(ushort const *,ushort const *,ushort const * *,ulong *,ulong,ushort const * *,ushort * *,ulong,ushort *,ulong)

- ea: `0x180012cb0`
- end: `0x180013319`
- name: `?GetConfigurationFromNativeCode@@YAHPEBG0PEAPEBGPEAKK1PEAPEAGKPEAGK@Z`
- size: `1641`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 **@<r8>, unsigned int *@<r9>, unsigned int, const unsigned __int16 **, unsigned __int16 **, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x180020f58`

## callees

- `0x180002584`
- `0x180012b90`
- `0x180012cb0`
- `0x18001331c`
- `0x1800134a0`
- `0x18004d030`
- `0x18004d298`
- `0x18004d350`
- `0x18004d3c4`
- `0x18004d474`
- `0x18004d6c8`
- `0x18004d754`
- `0x1800653b4`
- `0x1800653e6`

## import_xrefs

- `KERNEL32!ReadFile` at `0x180012e03`
- `KERNEL32!ReadFile` at `0x180012e03`
- `KERNEL32!CloseHandle` at `0x180012f21`
- `KERNEL32!CloseHandle` at `0x180012f21`
- `KERNEL32!lstrlenW` at `0x180012f90`
- `KERNEL32!lstrlenW` at `0x180012f90`
- `KERNEL32!CreateFileW` at `0x180012da4`
- `KERNEL32!CreateFileW` at `0x180012da4`
- `KERNEL32!GetFileSize` at `0x180012dc9`
- `KERNEL32!GetFileSize` at `0x180012dc9`
- `KERNEL32!MultiByteToWideChar` at `0x180012eb7`
- `KERNEL32!MultiByteToWideChar` at `0x180012f06`
- `KERNEL32!MultiByteToWideChar` at `0x180012eb7`
- `KERNEL32!MultiByteToWideChar` at `0x180012f06`
- `ucrtbase_clr0400!_wcsicmp` at `0x180013021`
- `ucrtbase_clr0400!_wcsicmp` at `0x180013040`
- `ucrtbase_clr0400!_wcsicmp` at `0x180013059`
- `ucrtbase_clr0400!_wcsicmp` at `0x1800131b7`
- `ucrtbase_clr0400!_wcsicmp` at `0x180013236`
- `ucrtbase_clr0400!_wcsicmp` at `0x18001324e`
- `ucrtbase_clr0400!_wcsicmp` at `0x18001327c`
- `ucrtbase_clr0400!_wcsicmp` at `0x180013021`
- `ucrtbase_clr0400!_wcsicmp` at `0x180013040`
- `ucrtbase_clr0400!_wcsicmp` at `0x180013059`
- `ucrtbase_clr0400!_wcsicmp` at `0x1800131b7`
- `ucrtbase_clr0400!_wcsicmp` at `0x180013236`
- `ucrtbase_clr0400!_wcsicmp` at `0x18001324e`
- `ucrtbase_clr0400!_wcsicmp` at `0x18001327c`
- `ucrtbase_clr0400!wcstoul` at `0x1800130b2`
- `ucrtbase_clr0400!wcstoul` at `0x1800130b2`

## pseudocode

```c
__int64 __fastcall GetConfigurationFromNativeCode(
        LPCWSTR lpFileName,
        wchar_t *a2,
        const unsigned __int16 **a3,
        unsigned int *a4,
        unsigned int a5,
        const unsigned __int16 **a6,
        unsigned __int16 **a7,
        unsigned int a8,
        unsigned __int16 *a9,
        unsigned int a10)
{
  int v11; // esi
  unsigned int v12; // r14d
  unsigned __int16 *v13; // rdi
  DWORD v14; // r13d
  HANDLE FileW; // r15
  DWORD FileSize; // ebx
  unsigned __int16 *v17; // rax
  unsigned int i; // r9d
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rcx
  unsigned __int16 *v22; // r12
  unsigned int v23; // ebx
  UINT v24; // esi
  __int64 v25; // rax
  int v26; // r14d
  const CHAR *v27; // r15
  int v28; // ebx
  WCHAR *v29; // rax
  int v31; // ebx
  wchar_t *v32; // rax
  int v33; // ecx
  unsigned int ColonSeparatedTimeInSeconds; // eax
  unsigned int v35; // ecx
  const unsigned __int16 **v36; // r10
  const unsigned __int16 *v37; // rax
  int v38; // edx
  int v39; // r8d
  int v40; // r14d
  int v41; // ebx
  const wchar_t **v42; // rsi
  int v43; // ecx
  int v44; // [rsp+40h] [rbp-C0h]
  int v45; // [rsp+44h] [rbp-BCh]
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-B8h] BYREF
  int v47; // [rsp+4Ch] [rbp-B4h]
  int v48; // [rsp+50h] [rbp-B0h]
  int v49; // [rsp+54h] [rbp-ACh]
  BOOL v50; // [rsp+58h] [rbp-A8h]
  unsigned int NextWord; // [rsp+5Ch] [rbp-A4h]
  unsigned int *v52; // [rsp+60h] [rbp-A0h]
  unsigned __int16 **v53; // [rsp+68h] [rbp-98h]
  const unsigned __int16 **v54; // [rsp+70h] [rbp-90h]
  const unsigned __int16 **v55; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v56; // [rsp+80h] [rbp-80h]
  wchar_t *String2; // [rsp+88h] [rbp-78h]
  HANDLE hObject; // [rsp+90h] [rbp-70h]
  WCHAR String; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v60[103]; // [rsp+A2h] [rbp-5Eh] BYREF

  v55 = a6;
  v53 = a7;
  v56 = a9;
  v52 = a4;
  v54 = a3;
  String2 = a2;
  if ( !lpFileName || !a4 || !a3 || !a2 || !a5 )
    return 0;
  v47 = 0;
  v44 = -1;
  v11 = -1;
  v45 = -1;
  v12 = 0;
  NumberOfBytesRead = 0;
  v13 = 0;
  v50 = 0;
  v49 = 0;
  v14 = 0;
  v48 = 0;
  CReadWriteSpinLock::AcquireWriterLock((CReadWriteSpinLock *)&g_GetConfigurationFromNativeCodeLock);
  FileW = CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  hObject = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    FileSize = GetFileSize(FileW, 0);
    if ( FileSize - 1 > 0xFFFFFFFD )
      goto LABEL_30;
    v17 = (unsigned __int16 *)MemAllocClear(FileSize + 2);
    v13 = v17;
    if ( !v17 )
      goto LABEL_31;
    if ( !ReadFile(FileW, v17, FileSize, &NumberOfBytesRead, 0) )
    {
LABEL_30:
      GetLastWin32Error();
      goto LABEL_31;
    }
    if ( NumberOfBytesRead < 3 )
      goto LABEL_31;
    if ( *(_BYTE *)v13 == 0xFF )
    {
      if ( *((_BYTE *)v13 + 1) != 0xFE )
        goto LABEL_23;
LABEL_19:
      v22 = v13 + 1;
      v23 = (FileSize - 2) >> 1;
LABEL_36:
      NumberOfBytesRead = v23;
      if ( !v23 )
        goto LABEL_31;
      while ( 1 )
      {
        NextWord = GetNextWord(&String, 0x68u, &v22[v14], v23 - v14);
        v31 = lstrlenW(&String);
        if ( v31 < 1 )
          goto LABEL_31;
        if ( wcsstr_0(&String, L"<!--") != &String )
          break;
        v32 = wcsstr_0(&v22[v14], L"-->");
        if ( !v32 )
          goto LABEL_31;
        v14 += (((unsigned int)v32 - 2 * v14 - (unsigned int)v22) >> 1) + 3;
LABEL_96:
        v23 = NumberOfBytesRead;
        if ( v14 >= NumberOfBytesRead )
          goto LABEL_31;
        v11 = v45;
        v12 = v47;
      }
      if ( !v49 )
      {
LABEL_87:
        if ( !v50 || _wcsicmp(&String, String2) )
        {
          v43 = String - 60;
          if ( String == 60 )
            v43 = v60[0];
          v50 = v43 == 0;
        }
        else
        {
          v49 = 1;
        }
        v14 += NextWord;
        goto LABEL_96;
      }
      if ( !v48 )
      {
        if ( String != 61 || v60[0] )
        {
          v35 = 0;
          v48 = 0;
          v36 = v54;
          while ( 1 )
          {
            v37 = *v36;
            do
            {
              v38 = *(const unsigned __int16 *)((char *)v37 + (char *)&String - (char *)*v36);
              v39 = *v37 - v38;
              if ( v39 )
                break;
              ++v37;
            }
            while ( v38 );
            if ( !v39 )
              break;
            ++v35;
            ++v36;
            if ( v35 >= a5 )
            {
              v40 = v44;
              goto LABEL_70;
            }
          }
          v40 = v35;
          v44 = v35;
LABEL_70:
          v41 = 0;
          if ( a8 )
          {
            v42 = v55;
            while ( _wcsicmp(*v42, &String) )
            {
              ++v41;
              ++v42;
              if ( v41 >= a8 )
                goto LABEL_74;
            }
            v45 = v41;
          }
          else
          {
LABEL_74:
            v41 = v45;
          }
          if ( v40 < 0 && v41 < 0 && v56 && !*v56 && a10 > 1 && (String != 47 || v60[0] != 62 || v60[1]) )
            StringCchCopyW(v56, a10, &String);
        }
        else
        {
          v48 = 1;
        }
        goto LABEL_84;
      }
      v48 = 0;
      if ( v44 < 0 )
      {
        v47 = v12;
        v45 = v11;
        if ( v11 >= 0 )
        {
          GetQuotedString(v53[v11], 0x64u, &v22[v14], NumberOfBytesRead - v14);
          v47 = v12;
          v44 = -1;
          v45 = -1;
        }
        goto LABEL_84;
      }
      if ( _wcsicmp(&String, L"\"true\"") )
      {
        if ( _wcsicmp(&String, L"\"false\"") )
        {
          if ( _wcsicmp(&String, L"\"infinite\"") )
          {
            if ( wcschr_0(&String, 0x3Au) )
            {
              ColonSeparatedTimeInSeconds = GetColonSeparatedTimeInSeconds(&String);
            }
            else
            {
              if ( (unsigned int)(v31 - 3) > 0xB )
              {
LABEL_57:
                v44 = -1;
                v45 = -1;
LABEL_84:
                if ( !_wcsicmp(&String, L"/>") || !_wcsicmp(&String, L"</") )
                {
                  v48 = 0;
                  v49 = 0;
                  v44 = -1;
                  v45 = -1;
                }
                goto LABEL_87;
              }
              if ( (unsigned __int64)(2LL * (v31 - 1)) >= 0xD0 )
                _report_rangecheckfailure();
              *(&String + v31 - 1) = 0;
              ColonSeparatedTimeInSeconds = wcstoul(v60, 0, 0);
            }
            v33 = ColonSeparatedTimeInSeconds;
          }
          else
          {
            v33 = -1;
          }
        }
        else
        {
          v33 = 0;
        }
      }
      else
      {
        v33 = 1;
      }
      v47 = 1;
      v52[v44] = v33;
      goto LABEL_57;
    }
    if ( *(_BYTE *)v13 == 0xFE )
    {
      if ( *((_BYTE *)v13 + 1) == 0xFF )
      {
        for ( i = 2; i < FileSize - 1; *((_BYTE *)v13 + v19) = v20 )
        {
          v19 = i;
          v20 = i + 1;
          v21 = v20;
          i += 2;
          LOBYTE(v20) = *((_BYTE *)v13 + v20);
          *((_BYTE *)v13 + v21) = *((_BYTE *)v13 + v19);
        }
        goto LABEL_19;
      }
    }
    else if ( *(_BYTE *)v13 == 0xEF && *((_BYTE *)v13 + 1) == 0xBB )
    {
      v24 = 65001;
      if ( *((_BYTE *)v13 + 2) == 0xBF )
      {
LABEL_24:
        v25 = 0;
        if ( v24 == 65001 )
          v25 = 3;
        v26 = v25;
        v27 = (char *)v13 + v25;
        v28 = MultiByteToWideChar(v24, 0, (LPCCH)v13 + v25, NumberOfBytesRead - v25, 0, 0);
        if ( v28 <= 0 )
          goto LABEL_30;
        v23 = v28 + 1;
        v29 = (WCHAR *)MemAllocClear(saturated_mul((int)(v23 + 1), 2u));
        v22 = v29;
        if ( v29 )
        {
          if ( !MultiByteToWideChar(v24, 0, v27, NumberOfBytesRead - v26, v29, v23) )
          {
            MemFree(v22);
            goto LABEL_30;
          }
          MemFree(v13);
          v11 = -1;
          v13 = v22;
          v12 = 0;
          goto LABEL_36;
        }
LABEL_31:
        CloseHandle(hObject);
        v12 = v47;
        goto LABEL_32;
      }
    }
LABEL_23:
    v24 = 0;
    goto LABEL_24;
  }
  GetLastWin32Error();
LABEL_32:
  CReadWriteSpinLock::ReleaseWriterLock((CReadWriteSpinLock *)&g_GetConfigurationFromNativeCodeLock);
  if ( v13 )
    MemFree(v13);
  return v12;
}

```

## disassembly

```asm
0x180012cb0  mov     [rsp-8+arg_10], rbx
0x180012cb5  push    rbp
0x180012cb6  push    rsi
0x180012cb7  push    rdi
0x180012cb8  push    r12
0x180012cba  push    r13
0x180012cbc  push    r14
0x180012cbe  push    r15
0x180012cc0  lea     rbp, [rsp-80h]
0x180012cc5  sub     rsp, 180h
0x180012ccc  mov     rax, cs:__security_cookie
0x180012cd3  xor     rax, rsp
0x180012cd6  mov     [rbp+0B0h+var_40], rax
0x180012cda  mov     rax, [rbp+0B0h+arg_28]
0x180012ce1  xor     r12d, r12d
0x180012ce4  mov     [rsp+1B0h+var_138], rax
0x180012ce9  mov     rbx, rcx
0x180012cec  mov     rax, [rbp+0B0h+arg_30]
0x180012cf3  mov     [rsp+1B0h+var_148], rax
0x180012cf8  mov     rax, [rbp+0B0h+arg_40]
0x180012cff  mov     [rbp+0B0h+var_130], rax
0x180012d03  mov     [rsp+1B0h+var_150], r9
0x180012d08  mov     [rsp+1B0h+var_140], r8
0x180012d0d  mov     [rbp+0B0h+String2], rdx
0x180012d11  test    rcx, rcx
0x180012d14  jz      loc_1800132EA
0x180012d1a  test    r9, r9
0x180012d1d  jz      loc_1800132EA
0x180012d23  test    r8, r8
0x180012d26  jz      loc_1800132EA
0x180012d2c  test    rdx, rdx
0x180012d2f  jz      loc_1800132EA
0x180012d35  cmp     [rbp+0B0h+arg_20], r12d
0x180012d3c  jz      loc_1800132EA
0x180012d42  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180012d46  mov     [rsp+1B0h+var_164], r12d
0x180012d4b  mov     [rsp+1B0h+var_170], ecx
0x180012d4f  mov     esi, ecx
0x180012d51  mov     [rsp+1B0h+var_16C], ecx
0x180012d55  mov     r14d, r12d
0x180012d58  lea     rcx, ?g_GetConfigurationFromNativeCodeLock@@3VCReadWriteSpinLock@@A; this
0x180012d5f  mov     [rsp+1B0h+NumberOfBytesRead], r12d
0x180012d64  mov     edi, r12d
0x180012d67  mov     [rsp+1B0h+var_158], r12d
0x180012d6c  mov     [rsp+1B0h+var_15C], r12d
0x180012d71  mov     r13d, r12d
0x180012d74  mov     [rsp+1B0h+var_160], r12d
0x180012d79  call    ?AcquireWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::AcquireWriterLock(void)
0x180012d7e  lea     eax, [r12+3]
0x180012d83  mov     [rsp+1B0h+hTemplateFile], r12; hTemplateFile
0x180012d88  mov     [rsp+1B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180012d90  lea     r8d, [r12+7]; dwShareMode
0x180012d95  xor     r9d, r9d; lpSecurityAttributes
0x180012d98  mov     [rsp+1B0h+dwCreationDisposition], eax; dwCreationDisposition
0x180012d9c  mov     edx, 80000000h; dwDesiredAccess
0x180012da1  mov     rcx, rbx; lpFileName
0x180012da4  call    cs:__imp_CreateFileW
0x180012daa  mov     r15, rax
0x180012dad  mov     [rbp+0B0h+hObject], rax
0x180012db1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012db5  cmp     r15, rax
0x180012db8  jnz     short loc_180012DC4
0x180012dba  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180012dbf  jmp     loc_180012F2C
0x180012dc4  xor     edx, edx; lpFileSizeHigh
0x180012dc6  mov     rcx, r15; hFile
0x180012dc9  call    cs:__imp_GetFileSize
0x180012dcf  mov     ebx, eax
0x180012dd1  dec     eax
0x180012dd3  cmp     eax, 0FFFFFFFDh
0x180012dd6  ja      loc_180012F18
0x180012ddc  lea     ecx, [rbx+2]; unsigned __int64
0x180012ddf  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180012de4  mov     rdi, rax
0x180012de7  test    rax, rax
0x180012dea  jz      loc_180012F1D
0x180012df0  lea     r9, [rsp+1B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180012df5  mov     qword ptr [rsp+1B0h+dwCreationDisposition], r12; lpOverlapped
0x180012dfa  mov     r8d, ebx; nNumberOfBytesToRead
0x180012dfd  mov     rdx, rax; lpBuffer
0x180012e00  mov     rcx, r15; hFile
0x180012e03  call    cs:__imp_ReadFile
0x180012e09  test    eax, eax
0x180012e0b  jz      loc_180012F18
0x180012e11  mov     r9d, [rsp+1B0h+NumberOfBytesRead]
0x180012e16  mov     ecx, 3
0x180012e1b  cmp     r9d, ecx
0x180012e1e  jb      loc_180012F1D
0x180012e24  cmp     byte ptr [rdi], 0FFh
0x180012e27  mov     edx, 0FDE9h
0x180012e2c  jnz     short loc_180012E36
0x180012e2e  cmp     byte ptr [rdi+1], 0FEh
0x180012e32  jz      short loc_180012E70
0x180012e34  jmp     short loc_180012E91
0x180012e36  cmp     byte ptr [rdi], 0FEh
0x180012e39  jnz     short loc_180012E7E
0x180012e3b  cmp     byte ptr [rdi+1], 0FFh
0x180012e3f  jnz     short loc_180012E91
0x180012e41  lea     r10d, [rbx-1]
0x180012e45  mov     r9d, 2
0x180012e4b  cmp     r10d, r9d
0x180012e4e  jbe     short loc_180012E70
0x180012e50  mov     r8d, r9d
0x180012e53  lea     eax, [r9+1]
0x180012e57  mov     ecx, eax
0x180012e59  add     r9d, 2
0x180012e5d  mov     al, [rax+rdi]
0x180012e60  mov     dl, [r8+rdi]
0x180012e64  mov     [rcx+rdi], dl
0x180012e67  mov     [r8+rdi], al
0x180012e6b  cmp     r9d, r10d
0x180012e6e  jb      short loc_180012E50
0x180012e70  add     ebx, 0FFFFFFFEh
0x180012e73  lea     r12, [rdi+2]
0x180012e77  shr     ebx, 1
0x180012e79  jmp     loc_180012F5F
0x180012e7e  cmp     byte ptr [rdi], 0EFh
0x180012e81  jnz     short loc_180012E91
0x180012e83  cmp     byte ptr [rdi+1], 0BBh
0x180012e87  jnz     short loc_180012E91
0x180012e89  cmp     byte ptr [rdi+2], 0BFh
0x180012e8d  mov     esi, edx
0x180012e8f  jz      short loc_180012E94
0x180012e91  mov     esi, r12d
0x180012e94  cmp     esi, edx
0x180012e96  mov     [rsp+1B0h+dwFlagsAndAttributes], r12d; cchWideChar
0x180012e9b  mov     eax, r12d
0x180012e9e  mov     qword ptr [rsp+1B0h+dwCreationDisposition], r12; lpWideCharStr
0x180012ea3  cmovz   eax, ecx
0x180012ea6  xor     edx, edx; dwFlags
0x180012ea8  sub     r9d, eax; cbMultiByte
0x180012eab  mov     r14d, eax
0x180012eae  mov     ecx, esi; CodePage
0x180012eb0  lea     r15, [rax+rdi]
0x180012eb4  mov     r8, r15; lpMultiByteStr
0x180012eb7  call    cs:__imp_MultiByteToWideChar
0x180012ebd  mov     ebx, eax
0x180012ebf  test    eax, eax
0x180012ec1  jle     short loc_180012F18
0x180012ec3  inc     ebx
0x180012ec5  lea     eax, [rbx+1]
0x180012ec8  movsxd  rcx, eax
0x180012ecb  mov     eax, 2
0x180012ed0  mul     rcx
0x180012ed3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012eda  cmovo   rax, rcx
0x180012ede  mov     rcx, rax; unsigned __int64
0x180012ee1  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180012ee6  mov     r12, rax
0x180012ee9  test    rax, rax
0x180012eec  jz      short loc_180012F1D
0x180012eee  mov     r9d, [rsp+1B0h+NumberOfBytesRead]
0x180012ef3  mov     r8, r15; lpMultiByteStr
0x180012ef6  sub     r9d, r14d; cbMultiByte
0x180012ef9  mov     [rsp+1B0h+dwFlagsAndAttributes], ebx; cchWideChar
0x180012efd  xor     edx, edx; dwFlags
0x180012eff  mov     qword ptr [rsp+1B0h+dwCreationDisposition], rax; lpWideCharStr
0x180012f04  mov     ecx, esi; CodePage
0x180012f06  call    cs:__imp_MultiByteToWideChar
0x180012f0c  test    eax, eax
0x180012f0e  jnz     short loc_180012F4D
0x180012f10  mov     rcx, r12; lpMem
0x180012f13  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180012f18  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180012f1d  mov     rcx, [rbp+0B0h+hObject]; hObject
0x180012f21  call    cs:__imp_CloseHandle
0x180012f27  mov     r14d, [rsp+1B0h+var_164]
0x180012f2c  lea     rcx, ?g_GetConfigurationFromNativeCodeLock@@3VCReadWriteSpinLock@@A; this
0x180012f33  call    ?ReleaseWriterLock@CReadWriteSpinLock@@QEAAXXZ; CReadWriteSpinLock::ReleaseWriterLock(void)
0x180012f38  test    rdi, rdi
0x180012f3b  jz      short loc_180012F45
0x180012f3d  mov     rcx, rdi; lpMem
0x180012f40  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180012f45  mov     eax, r14d
0x180012f48  jmp     loc_1800132EC
0x180012f4d  mov     rcx, rdi; lpMem
0x180012f50  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180012f55  mov     esi, [rsp+1B0h+var_16C]
0x180012f59  mov     rdi, r12
0x180012f5c  mov     r14d, r13d
0x180012f5f  mov     [rsp+1B0h+NumberOfBytesRead], ebx
0x180012f63  test    ebx, ebx
0x180012f65  jz      short loc_180012F1D
0x180012f67  mov     eax, r13d
0x180012f6a  lea     rcx, [rbp+0B0h+String]; unsigned __int16 *
0x180012f6e  mov     r15d, r14d
0x180012f71  sub     ebx, r13d
0x180012f74  mov     r9d, ebx; unsigned int
0x180012f77  mov     edx, 68h ; 'h'; unsigned __int64
0x180012f7c  lea     r14, [r12+rax*2]
0x180012f80  mov     r8, r14; unsigned __int16 *
0x180012f83  call    ?GetNextWord@@YAKPEAG_K0K@Z; GetNextWord(ushort *,unsigned __int64,ushort *,ulong)
0x180012f88  lea     rcx, [rbp+0B0h+String]; lpString
0x180012f8c  mov     [rsp+1B0h+var_154], eax
0x180012f90  call    cs:__imp_lstrlenW
0x180012f96  mov     ebx, eax
0x180012f98  cmp     eax, 1
0x180012f9b  jl      short loc_180012F1D
0x180012f9d  lea     rdx, SubStr; "<!--"
0x180012fa4  lea     rcx, [rbp+0B0h+String]; Str
0x180012fa8  call    wcsstr_0
0x180012fad  lea     rcx, [rbp+0B0h+String]
0x180012fb1  cmp     rax, rcx
0x180012fb4  jnz     short loc_180012FEC
0x180012fb6  lea     rdx, asc_18006BA08; "-->"
0x180012fbd  mov     rcx, r14; Str
0x180012fc0  call    wcsstr_0
0x180012fc5  mov     rcx, rax
0x180012fc8  test    rax, rax
0x180012fcb  jz      loc_180012F1D
0x180012fd1  lea     eax, ds:0[r13*2]
0x180012fd9  add     r13d, 3
0x180012fdd  sub     ecx, eax
0x180012fdf  sub     ecx, r12d
0x180012fe2  shr     ecx, 1
0x180012fe4  add     r13d, ecx
0x180012fe7  jmp     loc_1800132CF
0x180012fec  xor     r8d, r8d
0x180012fef  cmp     [rsp+1B0h+var_15C], r8d
0x180012ff4  jz      loc_18001326D
0x180012ffa  cmp     [rsp+1B0h+var_160], r8d
0x180012fff  jz      loc_18001312C
0x180013005  mov     eax, [rsp+1B0h+var_170]
0x180013009  mov     [rsp+1B0h+var_160], r8d
0x18001300e  test    eax, eax
0x180013010  js      loc_1800130E0
0x180013016  lea     rdx, aTrue_0; "\"true\""
0x18001301d  lea     rcx, [rbp+0B0h+String]; String1
0x180013021  call    cs:__imp__wcsicmp
0x180013027  xor     esi, esi
0x180013029  test    eax, eax
0x18001302b  jnz     short loc_180013035
0x18001302d  lea     ecx, [rsi+1]
0x180013030  jmp     loc_1800130BA
0x180013035  lea     rdx, aFalse_0; "\"false\""
0x18001303c  lea     rcx, [rbp+0B0h+String]; String1
0x180013040  call    cs:__imp__wcsicmp
0x180013046  test    eax, eax
0x180013048  jnz     short loc_18001304E
0x18001304a  mov     ecx, esi
0x18001304c  jmp     short loc_1800130BA
0x18001304e  lea     rdx, aInfinite; "\"infinite\""
0x180013055  lea     rcx, [rbp+0B0h+String]; String1
0x180013059  call    cs:__imp__wcsicmp
0x18001305f  test    eax, eax
0x180013061  jnz     short loc_180013068
0x180013063  or      ecx, 0FFFFFFFFh
0x180013066  jmp     short loc_1800130BA
0x180013068  mov     edx, 3Ah ; ':'; Ch
0x18001306d  lea     rcx, [rbp+0B0h+String]; Str
0x180013071  call    wcschr_0
0x180013076  test    rax, rax
0x180013079  jz      short loc_180013086
0x18001307b  lea     rcx, [rbp+0B0h+String]; Str
0x18001307f  call    ?GetColonSeparatedTimeInSeconds@@YAKPEAG@Z; GetColonSeparatedTimeInSeconds(ushort *)
0x180013084  jmp     short loc_1800130B8
0x180013086  lea     eax, [rbx-3]
0x180013089  cmp     eax, 0Bh
0x18001308c  ja      short loc_1800130CF
0x18001308e  lea     eax, [rbx-1]
0x180013091  movsxd  rcx, eax
0x180013094  add     rcx, rcx
0x180013097  cmp     rcx, 0D0h
0x18001309e  jnb     loc_180013313
0x1800130a4  mov     [rbp+rcx+0B0h+String], si
0x1800130a9  xor     r8d, r8d; Radix
0x1800130ac  lea     rcx, [rbp+0B0h+var_10E]; String
0x1800130b0  xor     edx, edx; EndPtr
0x1800130b2  call    cs:__imp_wcstoul
0x1800130b8  mov     ecx, eax
0x1800130ba  movsxd  rax, [rsp+1B0h+var_170]
0x1800130bf  mov     rdx, [rsp+1B0h+var_150]
0x1800130c4  mov     [rsp+1B0h+var_164], 1
0x1800130cc  mov     [rdx+rax*4], ecx
0x1800130cf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800130d3  mov     [rsp+1B0h+var_170], esi
0x1800130d7  mov     [rsp+1B0h+var_16C], esi
0x1800130db  jmp     loc_18001322B
0x1800130e0  mov     [rsp+1B0h+var_164], r15d
0x1800130e5  mov     [rsp+1B0h+var_170], eax
0x1800130e9  mov     [rsp+1B0h+var_16C], esi
0x1800130ed  test    esi, esi
0x1800130ef  js      loc_180013227
0x1800130f5  mov     rax, [rsp+1B0h+var_148]
0x1800130fa  mov     r8, r14; unsigned __int16 *
0x1800130fd  mov     r9d, [rsp+1B0h+NumberOfBytesRead]
0x180013102  mov     edx, 64h ; 'd'; unsigned int
0x180013107  movsxd  rcx, esi
0x18001310a  sub     r9d, r13d; unsigned int
0x18001310d  mov     rcx, [rax+rcx*8]; unsigned __int16 *
0x180013111  call    ?GetQuotedString@@YAXPEAGK0K@Z; GetQuotedString(ushort *,ulong,ushort *,ulong)
0x180013116  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001311a  mov     [rsp+1B0h+var_164], r15d
0x18001311f  mov     [rsp+1B0h+var_170], esi
0x180013123  mov     [rsp+1B0h+var_16C], esi
0x180013127  jmp     loc_18001322B
0x18001312c  cmp     [rbp+0B0h+String], 3Dh ; '='
0x180013131  jnz     short loc_180013147
0x180013133  cmp     [rbp+0B0h+var_10E], r8w
0x180013138  jnz     short loc_180013147
  ... truncated ...
```
