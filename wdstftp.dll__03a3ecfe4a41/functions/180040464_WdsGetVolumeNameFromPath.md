# WdsGetVolumeNameFromPath

- ea: `0x180040464`
- end: `0x18004073e`
- name: `WdsGetVolumeNameFromPath`
- size: `730`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x180040744`

## callees

- `0x18000fd58`
- `0x180011788`
- `0x18004037c`
- `0x1800403f4`
- `0x180040464`
- `0x1800607b0`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x180040557`
- `KERNEL32!GetVolumePathNameW` at `0x180040654`
- `KERNEL32!GetVolumePathNameW` at `0x180040679`
- `KERNEL32!GetVolumePathNameW` at `0x180040557`
- `KERNEL32!GetVolumePathNameW` at `0x180040654`
- `KERNEL32!GetVolumePathNameW` at `0x180040679`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004069f`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004069f`
- `KERNEL32!SetLastError` at `0x180040705`
- `KERNEL32!SetLastError` at `0x180040705`

## pseudocode

```c
__int64 __fastcall WdsGetVolumeNameFromPath(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rax
  WCHAR szVolumeName[56]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR szFileName[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v15[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR pszSrc[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+6D0h] [rbp+5D0h] BYREF
  unsigned __int16 v18[264]; // [rsp+8E0h] [rbp+7E0h] BYREF
  wchar_t Buffer[264]; // [rsp+AF0h] [rbp+9F0h] BYREF

  v7 = 0;
  memset_0(szVolumePathName, 0, 0x208u);
  memset_0(szVolumeName, 0, 0x64u);
  memset_0(pszSrc, 0, 0x208u);
  memset_0(v18, 0, 0x208u);
  memset_0(szFileName, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  if ( a1 && a2 )
  {
    if ( (int)StringCchCopyW(szFileName, 0x104u, a1) >= 0 )
    {
      memset_0(v15, 0, 0x208u);
      if ( GetVolumePathNameW(szFileName, szVolumePathName, 0x104u) )
      {
        v8 = -1;
        while ( (int)StringCchCopyW(pszSrc, 0x104u, szFileName) >= 0 && (int)StringCchCopyW(v18, 0x104u, Buffer) >= 0 )
        {
          if ( (unsigned int)WdsGetParentPath(pszSrc, szFileName) && (unsigned int)WdsGetFileName(pszSrc, v15, 260) )
          {
            v9 = -1;
            do
              ++v9;
            while ( v18[v9] );
            if ( v9 )
              v10 = StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v15, v18);
            else
              v10 = StringCchCopyW(Buffer, 0x104u, v15);
            if ( v10 < 0 )
              return v7;
            memset_0(v15, 0, 0x208u);
            if ( GetVolumePathNameW(szFileName, szVolumePathName, 0x104u) )
              continue;
          }
          if ( GetVolumePathNameW(pszSrc, szVolumePathName, 0x104u)
            && GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x32u)
            && (!a4 || (int)StringCchCopyW(a4, 0x104u, v18) >= 0)
            && (int)StringCchCopyW(a2, 0x104u, szVolumeName) >= 0 )
          {
            do
              ++v8;
            while ( a2[v8] );
            if ( (_DWORD)v8 )
            {
              v11 = (unsigned int)(v8 - 1);
              if ( a2[v11] == 92 )
                a2[v11] = 0;
            }
            return 1;
          }
          return v7;
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
0x180040464  mov     [rsp-8+arg_0], rbx
0x180040469  mov     [rsp-8+arg_10], rsi
0x18004046e  push    rbp
0x18004046f  push    rdi
0x180040470  push    r12
0x180040472  push    r14
0x180040474  push    r15
0x180040476  lea     rbp, [rsp-0C10h]
0x18004047e  sub     rsp, 0D10h
0x180040485  mov     rax, cs:__security_cookie
0x18004048c  xor     rax, rsp
0x18004048f  mov     [rbp+0C30h+var_30], rax
0x180040496  mov     rsi, rdx
0x180040499  mov     rdi, rcx
0x18004049c  mov     r12d, 208h
0x1800404a2  lea     rcx, [rbp+0C30h+szVolumePathName]; void *
0x1800404a9  mov     r8d, r12d; Size
0x1800404ac  xor     edx, edx; Val
0x1800404ae  mov     r14, r9
0x1800404b1  xor     ebx, ebx
0x1800404b3  call    memset_0
0x1800404b8  xor     edx, edx; Val
0x1800404ba  lea     r8d, [rbx+64h]; Size
0x1800404be  lea     rcx, [rsp+0D30h+szVolumeName]; void *
0x1800404c3  call    memset_0
0x1800404c8  mov     r8d, r12d; Size
0x1800404cb  lea     rcx, [rbp+0C30h+pszSrc]; void *
0x1800404d2  xor     edx, edx; Val
0x1800404d4  call    memset_0
0x1800404d9  mov     r8d, r12d; Size
0x1800404dc  lea     rcx, [rbp+0C30h+var_450]; void *
0x1800404e3  xor     edx, edx; Val
0x1800404e5  call    memset_0
0x1800404ea  mov     r8d, r12d; Size
0x1800404ed  lea     rcx, [rbp+0C30h+szFileName]; void *
0x1800404f1  xor     edx, edx; Val
0x1800404f3  call    memset_0
0x1800404f8  mov     r8d, r12d; Size
0x1800404fb  lea     rcx, [rbp+0C30h+Buffer]; void *
0x180040502  xor     edx, edx; Val
0x180040504  call    memset_0
0x180040509  test    rdi, rdi
0x18004050c  jz      loc_180040700
0x180040512  test    rsi, rsi
0x180040515  jz      loc_180040700
0x18004051b  mov     r15d, 104h
0x180040521  lea     rcx, [rbp+0C30h+szFileName]; unsigned __int16 *
0x180040525  mov     edx, r15d; unsigned __int64
0x180040528  mov     r8, rdi; unsigned __int16 *
0x18004052b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180040530  test    eax, eax
0x180040532  js      loc_180040711
0x180040538  mov     r8d, r12d; Size
0x18004053b  lea     rcx, [rbp+0C30h+var_A80]; void *
0x180040542  xor     edx, edx; Val
0x180040544  call    memset_0
0x180040549  mov     r8d, r15d; cchBufferLength
0x18004054c  lea     rdx, [rbp+0C30h+szVolumePathName]; lpszVolumePathName
0x180040553  lea     rcx, [rbp+0C30h+szFileName]; lpszFileName
0x180040557  call    cs:__imp_GetVolumePathNameW
0x18004055e  nop     dword ptr [rax+rax+00h]
0x180040563  test    eax, eax
0x180040565  jz      loc_180040711
0x18004056b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004056f  lea     r8, [rbp+0C30h+szFileName]; unsigned __int16 *
0x180040573  mov     rdx, r15; unsigned __int64
0x180040576  lea     rcx, [rbp+0C30h+pszSrc]; unsigned __int16 *
0x18004057d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180040582  test    eax, eax
0x180040584  js      loc_180040711
0x18004058a  lea     r8, [rbp+0C30h+Buffer]; unsigned __int16 *
0x180040591  mov     rdx, r15; unsigned __int64
0x180040594  lea     rcx, [rbp+0C30h+var_450]; unsigned __int16 *
0x18004059b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800405a0  test    eax, eax
0x1800405a2  js      loc_180040711
0x1800405a8  lea     rdx, [rbp+0C30h+szFileName]; pszDest
0x1800405ac  lea     rcx, [rbp+0C30h+pszSrc]; pszSrc
0x1800405b3  call    WdsGetParentPath
0x1800405b8  test    eax, eax
0x1800405ba  jz      loc_180040668
0x1800405c0  mov     r8d, r15d
0x1800405c3  lea     rdx, [rbp+0C30h+var_A80]
0x1800405ca  lea     rcx, [rbp+0C30h+pszSrc]
0x1800405d1  call    WdsGetFileName
0x1800405d6  test    eax, eax
0x1800405d8  jz      loc_180040668
0x1800405de  lea     rcx, [rbp+0C30h+var_450]
0x1800405e5  mov     rax, rdi
0x1800405e8  inc     rax
0x1800405eb  cmp     [rcx+rax*2], bx
0x1800405ef  jnz     short loc_1800405E8
0x1800405f1  lea     rcx, [rbp+0C30h+Buffer]; unsigned __int16 *
0x1800405f8  mov     rdx, r15; unsigned __int64
0x1800405fb  test    rax, rax
0x1800405fe  jz      short loc_180040621
0x180040600  lea     rax, [rbp+0C30h+var_450]
0x180040607  lea     r9, [rbp+0C30h+var_A80]
0x18004060e  mov     [rsp+0D30h+var_D10], rax
0x180040613  lea     r8, aSS_0; "%s\\%s"
0x18004061a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004061f  jmp     short loc_18004062D
0x180040621  lea     r8, [rbp+0C30h+var_A80]; unsigned __int16 *
0x180040628  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004062d  test    eax, eax
0x18004062f  js      loc_180040711
0x180040635  mov     r8, r12; Size
0x180040638  lea     rcx, [rbp+0C30h+var_A80]; void *
0x18004063f  xor     edx, edx; Val
0x180040641  call    memset_0
0x180040646  mov     r8d, r15d; cchBufferLength
0x180040649  lea     rdx, [rbp+0C30h+szVolumePathName]; lpszVolumePathName
0x180040650  lea     rcx, [rbp+0C30h+szFileName]; lpszFileName
0x180040654  call    cs:__imp_GetVolumePathNameW
0x18004065b  nop     dword ptr [rax+rax+00h]
0x180040660  test    eax, eax
0x180040662  jnz     loc_18004056F
0x180040668  mov     r8d, r15d; cchBufferLength
0x18004066b  lea     rdx, [rbp+0C30h+szVolumePathName]; lpszVolumePathName
0x180040672  lea     rcx, [rbp+0C30h+pszSrc]; lpszFileName
0x180040679  call    cs:__imp_GetVolumePathNameW
0x180040680  nop     dword ptr [rax+rax+00h]
0x180040685  test    eax, eax
0x180040687  jz      loc_180040711
0x18004068d  mov     r8d, 32h ; '2'; cchBufferLength
0x180040693  lea     rdx, [rsp+0D30h+szVolumeName]; lpszVolumeName
0x180040698  lea     rcx, [rbp+0C30h+szVolumePathName]; lpszVolumeMountPoint
0x18004069f  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800406a6  nop     dword ptr [rax+rax+00h]
0x1800406ab  test    eax, eax
0x1800406ad  jz      short loc_180040711
0x1800406af  test    r14, r14
0x1800406b2  jz      short loc_1800406CA
0x1800406b4  lea     r8, [rbp+0C30h+var_450]; unsigned __int16 *
0x1800406bb  mov     rdx, r15; unsigned __int64
0x1800406be  mov     rcx, r14; unsigned __int16 *
0x1800406c1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800406c6  test    eax, eax
0x1800406c8  js      short loc_180040711
0x1800406ca  lea     r8, [rsp+0D30h+szVolumeName]; unsigned __int16 *
0x1800406cf  mov     rdx, r15; unsigned __int64
0x1800406d2  mov     rcx, rsi; unsigned __int16 *
0x1800406d5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800406da  test    eax, eax
0x1800406dc  js      short loc_180040711
0x1800406de  inc     rdi
0x1800406e1  cmp     [rsi+rdi*2], bx
0x1800406e5  jnz     short loc_1800406DE
0x1800406e7  test    edi, edi
0x1800406e9  jz      short loc_1800406F9
0x1800406eb  lea     eax, [rdi-1]
0x1800406ee  cmp     word ptr [rsi+rax*2], 5Ch ; '\'
0x1800406f3  jnz     short loc_1800406F9
0x1800406f5  mov     [rsi+rax*2], bx
0x1800406f9  mov     ebx, 1
0x1800406fe  jmp     short loc_180040711
0x180040700  mov     ecx, 57h ; 'W'; dwErrCode
0x180040705  call    cs:__imp_SetLastError
0x18004070c  nop     dword ptr [rax+rax+00h]
0x180040711  mov     eax, ebx
0x180040713  mov     rcx, [rbp+0C30h+var_30]
0x18004071a  xor     rcx, rsp; StackCookie
0x18004071d  call    __security_check_cookie
0x180040722  lea     r11, [rsp+0D30h+var_20]
0x18004072a  mov     rbx, [r11+30h]
0x18004072e  mov     rsi, [r11+40h]
0x180040732  mov     rsp, r11
0x180040735  pop     r15
0x180040737  pop     r14
0x180040739  pop     r12
0x18004073b  pop     rdi
0x18004073c  pop     rbp
0x18004073d  retn
```
