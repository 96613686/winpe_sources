# WdsGetVolumeNameFromPath

- ea: `0x18003cdcc`
- end: `0x18003d1bc`
- name: `WdsGetVolumeNameFromPath`
- size: `1008`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x18003d1c4`

## callees

- `0x1800020b6`
- `0x1800324a4`
- `0x180035c20`
- `0x180039424`
- `0x18003cdcc`
- `0x18007ec9a`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18003cefa`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18003d0df`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18003d107`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18003cefa`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18003d0df`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18003d107`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d0f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d189`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d0f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d189`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18003d123`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18003d123`

## pseudocode

```c
__int64 __fastcall WdsGetVolumeNameFromPath(WCHAR *a1, wchar_t *a2, __int64 a3, wchar_t *a4)
{
  unsigned int v7; // esi
  WCHAR *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  WCHAR *v11; // rcx
  __int64 v12; // rbx
  WCHAR *v13; // r8
  __int64 v14; // rcx
  wchar_t *v15; // rax
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  __int64 v18; // rcx
  unsigned __int16 *v19; // r8
  __int64 v20; // rdx
  wchar_t *v21; // rax
  wchar_t *v22; // rcx
  wchar_t *v23; // rax
  wchar_t *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  signed int v27; // eax
  __int64 v28; // rcx
  wchar_t *v29; // r8
  unsigned __int16 *v30; // rax
  unsigned __int16 *v31; // rcx
  WCHAR szVolumeName[56]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Str[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR szFileName[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wchar_t pszDest[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+6D0h] [rbp+5D0h] BYREF
  wchar_t pszSrc[264]; // [rsp+8E0h] [rbp+7E0h] BYREF
  unsigned __int16 v39[264]; // [rsp+AF0h] [rbp+9F0h] BYREF

  v7 = 0;
  memset_0(szVolumePathName, 0, 0x208u);
  memset_0(szVolumeName, 0, 0x64u);
  memset_0(Str, 0, 0x208u);
  memset_0(pszSrc, 0, 0x208u);
  memset_0(szFileName, 0, 0x208u);
  memset_0(v39, 0, 0x208u);
  if ( a1 && a2 )
  {
    v8 = szFileName;
    v9 = 260;
    v10 = 2147483646;
    do
    {
      if ( !v10 )
        break;
      if ( !*a1 )
        break;
      *v8++ = *a1++;
      --v10;
      --v9;
    }
    while ( v9 );
    v11 = v8 - 1;
    if ( v9 )
      v11 = v8;
    *v11 = 0;
    if ( v9 )
    {
      memset_0(pszDest, 0, 0x208u);
      if ( GetVolumePathNameW(szFileName, szVolumePathName, 0x104u) )
      {
        v12 = -1;
        while ( 1 )
        {
          v13 = szFileName;
          v14 = 2147483646;
          v15 = Str;
          v16 = 260;
          do
          {
            if ( !v14 )
              break;
            if ( !*v13 )
              break;
            *v15++ = *v13++;
            --v14;
            --v16;
          }
          while ( v16 );
          v17 = v15 - 1;
          if ( v16 )
            v17 = v15;
          *v17 = 0;
          if ( !v16 )
            break;
          v18 = 2147483646;
          v19 = v39;
          v20 = 260;
          v21 = pszSrc;
          do
          {
            if ( !v18 )
              break;
            if ( !*v19 )
              break;
            *v21++ = *v19++;
            --v18;
            --v20;
          }
          while ( v20 );
          v22 = v21 - 1;
          if ( v20 )
            v22 = v21;
          *v22 = 0;
          if ( !v20 )
            break;
          v23 = wcsrchr_0(Str, 0x5Cu);
          if ( !v23 )
            goto LABEL_44;
          if ( StringCchCopyNW(szFileName, 0x104u, Str, v23 - Str) < 0 )
            goto LABEL_45;
          v24 = wcsrchr_0(Str, 0x5Cu);
          if ( !v24 )
          {
LABEL_44:
            SetLastError(0x57u);
LABEL_45:
            if ( GetVolumePathNameW(Str, szVolumePathName, 0x104u)
              && GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x32u)
              && (!a4 || StringCchCopyW(a4, 0x104u, pszSrc) >= 0)
              && StringCchCopyW(a2, 0x104u, szVolumeName) >= 0 )
            {
              do
                ++v12;
              while ( a2[v12] );
              if ( v12 && a2[v12 - 1] == 92 )
                a2[v12 - 1] = 0;
              return 1;
            }
            return v7;
          }
          if ( StringCchCopyW(pszDest, 0x104u, v24 + 1) >= 0 )
          {
            v25 = -1;
            do
              ++v25;
            while ( pszSrc[v25] );
            v26 = 260;
            if ( v25 )
            {
              v27 = StringCchPrintfW(v39, 0x104u, L"%s\\%s", pszDest, pszSrc);
            }
            else
            {
              v28 = 2147483646;
              v29 = pszDest;
              v30 = v39;
              do
              {
                if ( !v28 )
                  break;
                if ( !*v29 )
                  break;
                *v30++ = *v29++;
                --v28;
                --v26;
              }
              while ( v26 );
              v31 = v30 - 1;
              if ( v26 )
                v31 = v30;
              v27 = v26 == 0 ? 0x8007007A : 0;
              *v31 = 0;
            }
            if ( v27 < 0 )
              return v7;
            memset_0(pszDest, 0, 0x208u);
            if ( GetVolumePathNameW(szFileName, szVolumePathName, 0x104u) )
              continue;
          }
          goto LABEL_45;
        }
      }
    }
  }
  else
  {
    SetLastError(0x57u);
  }
  return v7;
}

```

## disassembly

```asm
0x18003cdcc  mov     [rsp-8+arg_0], rbx
0x18003cdd1  mov     [rsp-8+arg_10], rsi
0x18003cdd6  push    rbp
0x18003cdd7  push    rdi
0x18003cdd8  push    r12
0x18003cdda  push    r14
0x18003cddc  push    r15
0x18003cdde  lea     rbp, [rsp-0C10h]
0x18003cde6  sub     rsp, 0D10h
0x18003cded  mov     rax, cs:__security_cookie
0x18003cdf4  xor     rax, rsp
0x18003cdf7  mov     [rbp+0C30h+var_30], rax
0x18003cdfe  mov     rdi, rdx
0x18003ce01  mov     rbx, rcx
0x18003ce04  mov     r12d, 208h
0x18003ce0a  lea     rcx, [rbp+0C30h+szVolumePathName]; void *
0x18003ce11  xor     r15d, r15d
0x18003ce14  mov     r8d, r12d; Size
0x18003ce17  xor     edx, edx; Val
0x18003ce19  mov     r14, r9
0x18003ce1c  mov     esi, r15d
0x18003ce1f  call    memset_0
0x18003ce24  xor     edx, edx; Val
0x18003ce26  lea     r8d, [r15+64h]; Size
0x18003ce2a  lea     rcx, [rsp+0D30h+szVolumeName]; void *
0x18003ce2f  call    memset_0
0x18003ce34  mov     r8d, r12d; Size
0x18003ce37  lea     rcx, [rbp+0C30h+Str]; void *
0x18003ce3b  xor     edx, edx; Val
0x18003ce3d  call    memset_0
0x18003ce42  mov     r8d, r12d; Size
0x18003ce45  lea     rcx, [rbp+0C30h+pszSrc]; void *
0x18003ce4c  xor     edx, edx; Val
0x18003ce4e  call    memset_0
0x18003ce53  mov     r8d, r12d; Size
0x18003ce56  lea     rcx, [rbp+0C30h+szFileName]; void *
0x18003ce5d  xor     edx, edx; Val
0x18003ce5f  call    memset_0
0x18003ce64  mov     r8d, r12d; Size
0x18003ce67  lea     rcx, [rbp+0C30h+var_240]; void *
0x18003ce6e  xor     edx, edx; Val
0x18003ce70  call    memset_0
0x18003ce75  test    rbx, rbx
0x18003ce78  jz      loc_18003D184
0x18003ce7e  test    rdi, rdi
0x18003ce81  jz      loc_18003D184
0x18003ce87  mov     r12d, 104h
0x18003ce8d  lea     rax, [rbp+0C30h+szFileName]
0x18003ce94  mov     edx, r12d
0x18003ce97  mov     ecx, 7FFFFFFEh
0x18003ce9c  test    rcx, rcx
0x18003ce9f  jz      short loc_18003CEC0
0x18003cea1  movzx   r8d, word ptr [rbx]
0x18003cea5  test    r8w, r8w
0x18003cea9  jz      short loc_18003CEC0
0x18003ceab  mov     [rax], r8w
0x18003ceaf  add     rbx, 2
0x18003ceb3  add     rax, 2
0x18003ceb7  dec     rcx
0x18003ceba  sub     rdx, 1
0x18003cebe  jnz     short loc_18003CE9C
0x18003cec0  test    rdx, rdx
0x18003cec3  lea     rcx, [rax-2]
0x18003cec7  cmovnz  rcx, rax
0x18003cecb  mov     [rcx], r15w
0x18003cecf  jz      loc_18003D18F
0x18003ced5  xor     edx, edx; Val
0x18003ced7  lea     rcx, [rbp+0C30h+pszDest]; void *
0x18003cede  mov     r8d, 208h; Size
0x18003cee4  call    memset_0
0x18003cee9  mov     r8d, r12d; cchBufferLength
0x18003ceec  lea     rdx, [rbp+0C30h+szVolumePathName]; lpszVolumePathName
0x18003cef3  lea     rcx, [rbp+0C30h+szFileName]; lpszFileName
0x18003cefa  call    cs:__imp_GetVolumePathNameW
0x18003cf00  test    eax, eax
0x18003cf02  jz      loc_18003D18F
0x18003cf08  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003cf0c  mov     r10d, 5Ch ; '\'
0x18003cf12  lea     r8, [rbp+0C30h+szFileName]
0x18003cf19  mov     ecx, 7FFFFFFEh
0x18003cf1e  lea     rax, [rbp+0C30h+Str]
0x18003cf22  mov     rdx, r12
0x18003cf25  test    rcx, rcx
0x18003cf28  jz      short loc_18003CF49
0x18003cf2a  movzx   r9d, word ptr [r8]
0x18003cf2e  test    r9w, r9w
0x18003cf32  jz      short loc_18003CF49
0x18003cf34  mov     [rax], r9w
0x18003cf38  add     r8, 2
0x18003cf3c  add     rax, 2
0x18003cf40  dec     rcx
0x18003cf43  sub     rdx, 1
0x18003cf47  jnz     short loc_18003CF25
0x18003cf49  test    rdx, rdx
0x18003cf4c  lea     rcx, [rax-2]
0x18003cf50  cmovnz  rcx, rax
0x18003cf54  mov     [rcx], r15w
0x18003cf58  jz      loc_18003D18F
0x18003cf5e  mov     ecx, 7FFFFFFEh
0x18003cf63  lea     r8, [rbp+0C30h+var_240]
0x18003cf6a  mov     rdx, r12
0x18003cf6d  lea     rax, [rbp+0C30h+pszSrc]
0x18003cf74  test    rcx, rcx
0x18003cf77  jz      short loc_18003CF98
0x18003cf79  movzx   r9d, word ptr [r8]
0x18003cf7d  test    r9w, r9w
0x18003cf81  jz      short loc_18003CF98
0x18003cf83  mov     [rax], r9w
0x18003cf87  add     r8, 2
0x18003cf8b  add     rax, 2
0x18003cf8f  dec     rcx
0x18003cf92  sub     rdx, 1
0x18003cf96  jnz     short loc_18003CF74
0x18003cf98  test    rdx, rdx
0x18003cf9b  lea     rcx, [rax-2]
0x18003cf9f  cmovnz  rcx, rax
0x18003cfa3  mov     [rcx], r15w
0x18003cfa7  jz      loc_18003D18F
0x18003cfad  mov     edx, r10d; Ch
0x18003cfb0  lea     rcx, [rbp+0C30h+Str]; Str
0x18003cfb4  call    wcsrchr_0
0x18003cfb9  test    rax, rax
0x18003cfbc  jz      loc_18003D0EE
0x18003cfc2  lea     rcx, [rbp+0C30h+Str]
0x18003cfc6  mov     rdx, r12; cchDest
0x18003cfc9  sub     rax, rcx
0x18003cfcc  lea     r8, [rbp+0C30h+Str]; pszSrc
0x18003cfd0  sar     rax, 1
0x18003cfd3  lea     rcx, [rbp+0C30h+szFileName]; pszDest
0x18003cfda  mov     r9, rax; cchToCopy
0x18003cfdd  call    StringCchCopyNW
0x18003cfe2  test    eax, eax
0x18003cfe4  js      loc_18003D0F9
0x18003cfea  mov     edx, 5Ch ; '\'; Ch
0x18003cfef  lea     rcx, [rbp+0C30h+Str]; Str
0x18003cff3  call    wcsrchr_0
0x18003cff8  test    rax, rax
0x18003cffb  jz      loc_18003D0EE
0x18003d001  lea     r8, [rax+2]; pszSrc
0x18003d005  mov     rdx, r12; cchDest
0x18003d008  lea     rcx, [rbp+0C30h+pszDest]; pszDest
0x18003d00f  call    StringCchCopyW
0x18003d014  test    eax, eax
0x18003d016  js      loc_18003D0F9
0x18003d01c  lea     rcx, [rbp+0C30h+pszSrc]
0x18003d023  mov     rax, rbx
0x18003d026  inc     rax
0x18003d029  cmp     [rcx+rax*2], r15w
0x18003d02e  jnz     short loc_18003D026
0x18003d030  mov     rdx, r12; unsigned __int64
0x18003d033  test    rax, rax
0x18003d036  jz      short loc_18003D060
0x18003d038  lea     rax, [rbp+0C30h+pszSrc]
0x18003d03f  lea     r9, [rbp+0C30h+pszDest]
0x18003d046  mov     [rsp+0D30h+var_D10], rax
0x18003d04b  lea     r8, aSS; "%s\\%s"
0x18003d052  lea     rcx, [rbp+0C30h+var_240]; unsigned __int16 *
0x18003d059  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d05e  jmp     short loc_18003D0B2
0x18003d060  mov     ecx, 7FFFFFFEh
0x18003d065  lea     r8, [rbp+0C30h+pszDest]
0x18003d06c  lea     rax, [rbp+0C30h+var_240]
0x18003d073  test    rcx, rcx
0x18003d076  jz      short loc_18003D097
0x18003d078  movzx   r9d, word ptr [r8]
0x18003d07c  test    r9w, r9w
0x18003d080  jz      short loc_18003D097
0x18003d082  mov     [rax], r9w
0x18003d086  add     r8, 2
0x18003d08a  add     rax, 2
0x18003d08e  dec     rcx
0x18003d091  sub     rdx, 1
0x18003d095  jnz     short loc_18003D073
0x18003d097  lea     rcx, [rax-2]
0x18003d09b  test    rdx, rdx
0x18003d09e  cmovnz  rcx, rax
0x18003d0a2  neg     rdx
0x18003d0a5  sbb     eax, eax
0x18003d0a7  not     eax
0x18003d0a9  and     eax, 8007007Ah
0x18003d0ae  mov     [rcx], r15w
0x18003d0b2  test    eax, eax
0x18003d0b4  js      loc_18003D18F
0x18003d0ba  xor     edx, edx; Val
0x18003d0bc  lea     rcx, [rbp+0C30h+pszDest]; void *
0x18003d0c3  mov     r8d, 208h; Size
0x18003d0c9  call    memset_0
0x18003d0ce  mov     r8d, r12d; cchBufferLength
0x18003d0d1  lea     rdx, [rbp+0C30h+szVolumePathName]; lpszVolumePathName
0x18003d0d8  lea     rcx, [rbp+0C30h+szFileName]; lpszFileName
0x18003d0df  call    cs:__imp_GetVolumePathNameW
0x18003d0e5  test    eax, eax
0x18003d0e7  jz      short loc_18003D0F9
0x18003d0e9  jmp     loc_18003CF0C
0x18003d0ee  mov     ecx, 57h ; 'W'; dwErrCode
0x18003d0f3  call    cs:__imp_SetLastError
0x18003d0f9  mov     r8d, r12d; cchBufferLength
0x18003d0fc  lea     rdx, [rbp+0C30h+szVolumePathName]; lpszVolumePathName
0x18003d103  lea     rcx, [rbp+0C30h+Str]; lpszFileName
0x18003d107  call    cs:__imp_GetVolumePathNameW
0x18003d10d  test    eax, eax
0x18003d10f  jz      short loc_18003D18F
0x18003d111  mov     r8d, 32h ; '2'; cchBufferLength
0x18003d117  lea     rdx, [rsp+0D30h+szVolumeName]; lpszVolumeName
0x18003d11c  lea     rcx, [rbp+0C30h+szVolumePathName]; lpszVolumeMountPoint
0x18003d123  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18003d129  test    eax, eax
0x18003d12b  jz      short loc_18003D18F
0x18003d12d  test    r14, r14
0x18003d130  jz      short loc_18003D148
0x18003d132  lea     r8, [rbp+0C30h+pszSrc]; pszSrc
0x18003d139  mov     rdx, r12; cchDest
0x18003d13c  mov     rcx, r14; pszDest
0x18003d13f  call    StringCchCopyW
0x18003d144  test    eax, eax
0x18003d146  js      short loc_18003D18F
0x18003d148  lea     r8, [rsp+0D30h+szVolumeName]; pszSrc
0x18003d14d  mov     rdx, r12; cchDest
0x18003d150  mov     rcx, rdi; pszDest
0x18003d153  call    StringCchCopyW
0x18003d158  test    eax, eax
0x18003d15a  js      short loc_18003D18F
0x18003d15c  inc     rbx
0x18003d15f  cmp     [rdi+rbx*2], r15w
0x18003d164  jnz     short loc_18003D15C
0x18003d166  test    rbx, rbx
0x18003d169  jz      short loc_18003D17D
0x18003d16b  mov     eax, 5Ch ; '\'
0x18003d170  cmp     [rdi+rbx*2-2], ax
0x18003d175  jnz     short loc_18003D17D
0x18003d177  mov     [rdi+rbx*2-2], r15w
0x18003d17d  mov     esi, 1
0x18003d182  jmp     short loc_18003D18F
0x18003d184  mov     ecx, 57h ; 'W'; dwErrCode
0x18003d189  call    cs:__imp_SetLastError
0x18003d18f  mov     eax, esi
0x18003d191  mov     rcx, [rbp+0C30h+var_30]
0x18003d198  xor     rcx, rsp; StackCookie
0x18003d19b  call    __security_check_cookie
0x18003d1a0  lea     r11, [rsp+0D30h+var_20]
0x18003d1a8  mov     rbx, [r11+30h]
0x18003d1ac  mov     rsi, [r11+40h]
0x18003d1b0  mov     rsp, r11
0x18003d1b3  pop     r15
0x18003d1b5  pop     r14
0x18003d1b7  pop     r12
0x18003d1b9  pop     rdi
0x18003d1ba  pop     rbp
0x18003d1bb  retn
```
