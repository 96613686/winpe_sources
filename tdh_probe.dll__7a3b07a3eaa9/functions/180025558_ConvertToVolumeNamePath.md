# ConvertToVolumeNamePath

- ea: `0x180025558`
- end: `0x180025747`
- name: `ConvertToVolumeNamePath`
- size: `495`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180025ed8`

## callees

- `0x180012fd0`
- `0x1800207c0`
- `0x180020850`
- `0x180021490`
- `0x180025558`
- `0x180049fcc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180025680`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180025680`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180025654`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180025654`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800255bd`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x1800255bd`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x180025715`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x180025715`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x18002569e`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x18002569e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800255cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800256ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800256fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800255cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800256ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800256fd`

## pseudocode

```c
DWORD __fastcall ConvertToVolumeNamePath(__int64 a1, wchar_t *a2)
{
  __int64 v4; // rbx
  HANDLE FirstVolumeW; // rsi
  __int64 v7; // rdi
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rdi
  __int64 v10; // r8
  DWORD LastError; // ebx
  WCHAR szVolumeName[4]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR DeviceName[260]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR TargetPath[264]; // [rsp+240h] [rbp+140h] BYREF

  memset_0(szVolumeName, 0, 0x208u);
  memset_0(TargetPath, 0, 0x208u);
  v4 = -1;
  FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x104u);
  if ( FirstVolumeW == (HANDLE)-1LL )
    return GetLastError();
  while ( 1 )
  {
    v7 = -1;
    do
      ++v7;
    while ( szVolumeName[v7] );
    if ( wcsncmp_0(szVolumeName, L"\\\\?\\", 4u) || (v8 = v7 - 1, v8 <= 4) || (v9 = v8, szVolumeName[v9] != 92) )
    {
      LastError = 161;
      goto LABEL_21;
    }
    if ( v9 >= 260 )
      _report_rangecheckfailure();
    szVolumeName[v9] = 0;
    if ( !QueryDosDeviceW(DeviceName, TargetPath, 0x104u) )
    {
      LastError = GetLastError();
      goto LABEL_21;
    }
    v10 = -1;
    do
      ++v10;
    while ( TargetPath[v10] );
    if ( !(unsigned int)_o__wcsnicmp(a1, TargetPath, v10) )
      break;
    szVolumeName[v9] = 92;
    if ( !FindNextVolumeW(FirstVolumeW, szVolumeName, 0x104u) )
    {
      LastError = GetLastError();
      if ( LastError == 18 )
        LastError = 2;
      goto LABEL_21;
    }
  }
  do
    ++v4;
  while ( TargetPath[v4] );
  LastError = ((int)StringCchPrintfW(a2, 0x104u, L"%s%s", szVolumeName, a1 + 2LL * (unsigned int)v4) >> 31) & 0x57;
LABEL_21:
  FindVolumeClose(FirstVolumeW);
  return LastError;
}

```

## disassembly

```asm
0x180025558  mov     [rsp-8+arg_10], rbx
0x18002555d  push    rbp
0x18002555e  push    rsi
0x18002555f  push    rdi
0x180025560  push    r12
0x180025562  push    r13
0x180025564  push    r14
0x180025566  push    r15
0x180025568  lea     rbp, [rsp-360h]
0x180025570  sub     rsp, 460h
0x180025577  mov     rax, cs:__security_cookie
0x18002557e  xor     rax, rsp
0x180025581  mov     [rbp+390h+var_40], rax
0x180025588  mov     r15, rdx
0x18002558b  mov     r14, rcx
0x18002558e  mov     ebx, 208h
0x180025593  lea     rcx, [rsp+490h+szVolumeName]; void *
0x180025598  mov     r8d, ebx; Size
0x18002559b  xor     edx, edx; Val
0x18002559d  call    memset_0
0x1800255a2  mov     r8d, ebx; Size
0x1800255a5  lea     rcx, [rbp+390h+TargetPath]; void *
0x1800255ac  xor     edx, edx; Val
0x1800255ae  call    memset_0
0x1800255b3  mov     edx, 104h; cchBufferLength
0x1800255b8  lea     rcx, [rsp+490h+szVolumeName]; lpszVolumeName
0x1800255bd  call    cs:__imp_FindFirstVolumeW
0x1800255c3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800255c7  mov     rsi, rax
0x1800255ca  cmp     rax, rbx
0x1800255cd  jnz     short loc_1800255DA
0x1800255cf  call    cs:__imp_GetLastError
0x1800255d5  jmp     loc_18002571D
0x1800255da  xor     r12d, r12d
0x1800255dd  lea     r13d, [r12+5Ch]
0x1800255e2  lea     rax, [rsp+490h+szVolumeName]
0x1800255e7  mov     rdi, rbx
0x1800255ea  inc     rdi
0x1800255ed  cmp     [rax+rdi*2], r12w
0x1800255f2  jnz     short loc_1800255EA
0x1800255f4  mov     r8d, 4; MaxCount
0x1800255fa  lea     rdx, String2; "\\\\?\\"
0x180025601  lea     rcx, [rsp+490h+szVolumeName]; String1
0x180025606  call    wcsncmp_0
0x18002560b  test    eax, eax
0x18002560d  jnz     loc_18002570D
0x180025613  dec     rdi
0x180025616  cmp     rdi, 4
0x18002561a  jbe     loc_18002570D
0x180025620  add     rdi, rdi
0x180025623  cmp     [rsp+rdi+490h+szVolumeName], r13w
0x180025629  jnz     loc_18002570D
0x18002562f  cmp     rdi, 208h
0x180025636  jnb     loc_180025707
0x18002563c  mov     r8d, 104h; ucchMax
0x180025642  mov     [rsp+rdi+490h+szVolumeName], r12w
0x180025648  lea     rdx, [rbp+390h+TargetPath]; lpTargetPath
0x18002564f  lea     rcx, [rsp+490h+DeviceName]; lpDeviceName
0x180025654  call    cs:__imp_QueryDosDeviceW
0x18002565a  test    eax, eax
0x18002565c  jz      loc_1800256FD
0x180025662  lea     rax, [rbp+390h+TargetPath]
0x180025669  mov     r8, rbx
0x18002566c  inc     r8
0x18002566f  cmp     [rax+r8*2], r12w
0x180025674  jnz     short loc_18002566C
0x180025676  lea     rdx, [rbp+390h+TargetPath]
0x18002567d  mov     rcx, r14
0x180025680  call    cs:__imp__o__wcsnicmp
0x180025686  test    eax, eax
0x180025688  jz      short loc_1800256BE
0x18002568a  mov     r8d, 104h; cchBufferLength
0x180025690  mov     [rsp+rdi+490h+szVolumeName], r13w
0x180025696  lea     rdx, [rsp+490h+szVolumeName]; lpszVolumeName
0x18002569b  mov     rcx, rsi; hFindVolume
0x18002569e  call    cs:__imp_FindNextVolumeW
0x1800256a4  test    eax, eax
0x1800256a6  jnz     loc_1800255E2
0x1800256ac  call    cs:__imp_GetLastError
0x1800256b2  mov     ebx, eax
0x1800256b4  cmp     eax, 12h
0x1800256b7  jnz     short loc_180025712
0x1800256b9  lea     ebx, [rax-10h]
0x1800256bc  jmp     short loc_180025712
0x1800256be  lea     rax, [rbp+390h+TargetPath]
0x1800256c5  inc     rbx
0x1800256c8  cmp     [rax+rbx*2], r12w
0x1800256cd  jnz     short loc_1800256C5
0x1800256cf  mov     eax, ebx
0x1800256d1  lea     r9, [rsp+490h+szVolumeName]
0x1800256d6  mov     edx, 104h; unsigned __int64
0x1800256db  mov     rcx, r15; wchar_t *
0x1800256de  lea     r8, [r14+rax*2]
0x1800256e2  mov     [rsp+490h+var_470], r8
0x1800256e7  lea     r8, aSS; "%s%s"
0x1800256ee  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800256f3  mov     ebx, eax
0x1800256f5  sar     ebx, 1Fh
0x1800256f8  and     ebx, 57h
0x1800256fb  jmp     short loc_180025712
0x1800256fd  call    cs:__imp_GetLastError
0x180025703  mov     ebx, eax
0x180025705  jmp     short loc_180025712
0x180025707  call    __report_rangecheckfailure
0x18002570d  mov     ebx, 0A1h
0x180025712  mov     rcx, rsi; hFindVolume
0x180025715  call    cs:__imp_FindVolumeClose
0x18002571b  mov     eax, ebx
0x18002571d  mov     rcx, [rbp+390h+var_40]
0x180025724  xor     rcx, rsp; StackCookie
0x180025727  call    __security_check_cookie
0x18002572c  mov     rbx, [rsp+490h+arg_10]
0x180025734  add     rsp, 460h
0x18002573b  pop     r15
0x18002573d  pop     r14
0x18002573f  pop     r13
0x180025741  pop     r12
0x180025743  pop     rdi
0x180025744  pop     rsi
0x180025745  pop     rbp
0x180025746  retn
```
