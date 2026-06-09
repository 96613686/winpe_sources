# PropVariantCompare(tagPROPVARIANT const &,tagPROPVARIANT const &,int *,ulong)

- ea: `0x18006d9ec`
- end: `0x18006dc70`
- name: `?PropVariantCompare@@YAJAEBUtagPROPVARIANT@@0PEAHK@Z`
- size: `644`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, int *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008710`
- `0x180033d04`
- `0x18004b92c`

## callees

- `0x18002e9f0`
- `0x18002ff5c`
- `0x180035590`
- `0x18006d9ec`
- `0x18007559c`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x18006db2f`
- `KERNEL32!CompareFileTime` at `0x18006db2f`
- `KERNEL32!SystemTimeToFileTime` at `0x18006db03`
- `KERNEL32!SystemTimeToFileTime` at `0x18006db19`
- `KERNEL32!SystemTimeToFileTime` at `0x18006db03`
- `KERNEL32!SystemTimeToFileTime` at `0x18006db19`
- `SHLWAPI!StrCmpLogicalW` at `0x18006dc2c`
- `SHLWAPI!StrCmpLogicalW` at `0x18006dc2c`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18006dabe`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18006dad5`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18006dabe`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18006dad5`

## pseudocode

```c
__int64 __fastcall PropVariantCompare(
        const struct tagPROPVARIANT *a1,
        const struct tagPROPVARIANT *a2,
        int *a3,
        char a4)
{
  unsigned int v7; // esi
  unsigned int vt; // eax
  unsigned __int16 uiVal; // ax
  bool v10; // cf
  bool v11; // cc
  LARGE_INTEGER v12; // xmm0_8
  const FILETIME *p_filetime; // rdx
  const FILETIME *v14; // rcx
  int v15; // eax
  double dblVal; // xmm0_8
  double v17; // xmm1_8
  float fltVal; // xmm0_4
  float v19; // xmm1_4
  unsigned int ulVal; // eax
  PVOID *v21; // rcx
  LARGE_INTEGER hVal; // rax
  FILETIME FileTime2; // [rsp+30h] [rbp-40h] BYREF
  struct _FILETIME FileTime; // [rsp+38h] [rbp-38h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-30h] BYREF
  SYSTEMTIME v27; // [rsp+50h] [rbp-20h] BYREF

  if ( !a3 )
  {
    v7 = -2147467261;
    goto LABEL_36;
  }
  *a3 = 0;
  vt = a1->vt;
  if ( (_WORD)vt != a2->vt )
  {
    v7 = -2147024809;
    goto LABEL_36;
  }
  v7 = 0;
  if ( vt > 0x13 )
  {
    if ( vt != 21 )
    {
      if ( vt == 31 )
      {
        v15 = StrCmpLogicalW(a1->bstrVal, a2->bstrVal);
        goto LABEL_23;
      }
      if ( vt != 64 )
      {
        if ( vt != 72 )
          goto LABEL_33;
        v15 = memcmp_0(a1->puuid, a2->puuid, 0x10u);
LABEL_23:
        *a3 = v15;
        return v7;
      }
      p_filetime = &a2->filetime;
      v14 = &a1->filetime;
LABEL_22:
      v15 = CompareFileTime(v14, p_filetime);
      goto LABEL_23;
    }
    hVal = a1->hVal;
    v10 = hVal.QuadPart < (unsigned __int64)a2->hVal.QuadPart;
    v11 = hVal.QuadPart <= (unsigned __int64)a2->hVal.QuadPart;
LABEL_44:
    if ( !v10 )
    {
LABEL_45:
      if ( !v11 )
        *a3 = 1;
      return v7;
    }
    goto LABEL_14;
  }
  switch ( vt )
  {
    case 0x13u:
      ulVal = a1->ulVal;
      v10 = ulVal < a2->lVal;
      v11 = ulVal <= a2->lVal;
      goto LABEL_44;
    case 4u:
      fltVal = a2->fltVal;
      v19 = a1->fltVal;
      if ( fltVal <= v19 )
      {
        v11 = v19 == fltVal;
        goto LABEL_45;
      }
LABEL_14:
      *a3 = -1;
      return v7;
    case 5u:
      dblVal = a2->dblVal;
      v17 = a1->dblVal;
      if ( dblVal <= v17 )
      {
        v11 = v17 == dblVal;
        goto LABEL_45;
      }
      goto LABEL_14;
  }
  if ( vt != 7 )
  {
    if ( vt == 11 )
    {
      if ( a1->iVal == a2->iVal )
        return v7;
      goto LABEL_14;
    }
    if ( vt == 18 )
    {
      uiVal = a1->uiVal;
      v10 = uiVal < (unsigned int)a2->iVal;
      v11 = uiVal <= (unsigned int)a2->iVal;
      goto LABEL_44;
    }
LABEL_33:
    v7 = -2147467259;
    v21 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_37;
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, vt);
LABEL_36:
    v21 = (PVOID *)WPP_GLOBAL_Control;
LABEL_37:
    if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 2) != 0 )
      WPP_SF_d(v21[2], 34, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, v7);
    return v7;
  }
  v12 = a1->hVal;
  SystemTime = 0;
  v27 = 0;
  if ( VariantTimeToSystemTime(*(DOUBLE *)&v12.QuadPart, &SystemTime) && VariantTimeToSystemTime(a2->dblVal, &v27) )
  {
    FileTime = 0;
    FileTime2 = 0;
    if ( (a4 & 1) != 0 )
    {
      *(_QWORD *)&SystemTime.wHour = 0;
      *(_QWORD *)&v27.wHour = 0;
    }
    if ( SystemTimeToFileTime(&SystemTime, &FileTime) && SystemTimeToFileTime(&v27, &FileTime2) )
    {
      p_filetime = &FileTime2;
      v14 = &FileTime;
      goto LABEL_22;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18006d9ec  mov     [rsp-28h+arg_18], rbx
0x18006d9f1  push    rbp
0x18006d9f2  push    rsi
0x18006d9f3  push    rdi
0x18006d9f4  push    r12
0x18006d9f6  push    r14
0x18006d9f8  mov     rbp, rsp
0x18006d9fb  sub     rsp, 70h
0x18006d9ff  mov     rax, cs:__security_cookie
0x18006da06  xor     rax, rsp
0x18006da09  mov     [rbp+var_10], rax
0x18006da0d  lea     r12, WPP_GLOBAL_Control
0x18006da14  mov     r14d, r9d
0x18006da17  mov     rbx, r8
0x18006da1a  mov     rdi, rdx
0x18006da1d  test    r8, r8
0x18006da20  jnz     short loc_18006DA2C
0x18006da22  mov     esi, 80004003h
0x18006da27  jmp     loc_18006DBD3
0x18006da2c  mov     dword ptr [r8], 0
0x18006da33  movzx   eax, word ptr [rcx]
0x18006da36  cmp     ax, [rdx]
0x18006da39  jz      short loc_18006DA45
0x18006da3b  mov     esi, 80070057h
0x18006da40  jmp     loc_18006DBD3
0x18006da45  xor     esi, esi
0x18006da47  mov     r9d, eax
0x18006da4a  cmp     eax, 13h
0x18006da4d  ja      loc_18006DB7F
0x18006da53  jz      loc_18006DB74
0x18006da59  mov     edx, eax
0x18006da5b  sub     edx, 4
0x18006da5e  jz      loc_18006DB59
0x18006da64  sub     edx, 1
0x18006da67  jz      loc_18006DB3C
0x18006da6d  sub     edx, 2
0x18006da70  jz      short loc_18006DAA7
0x18006da72  sub     edx, 4
0x18006da75  jz      short loc_18006DA8D
0x18006da77  cmp     edx, 7
0x18006da7a  jnz     loc_18006DB9F
0x18006da80  movzx   eax, word ptr [rcx+8]
0x18006da84  cmp     ax, [rdi+8]
0x18006da88  jmp     loc_18006DC3F
0x18006da8d  movzx   eax, word ptr [rdi+8]
0x18006da91  cmp     [rcx+8], ax
0x18006da95  jz      loc_18006DC4E
0x18006da9b  mov     dword ptr [r8], 0FFFFFFFFh
0x18006daa2  jmp     loc_18006DC4E
0x18006daa7  movsd   xmm0, qword ptr [rcx+8]; vtime
0x18006daac  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18006dab0  xorps   xmm1, xmm1
0x18006dab3  xorps   xmm2, xmm2
0x18006dab6  movups  xmmword ptr [rbp+SystemTime.wYear], xmm1
0x18006daba  movups  xmmword ptr [rbp+var_20.wYear], xmm2
0x18006dabe  call    cs:__imp_VariantTimeToSystemTime
0x18006dac4  test    eax, eax
0x18006dac6  jz      loc_18006DC4E
0x18006dacc  movsd   xmm0, qword ptr [rdi+8]; vtime
0x18006dad1  lea     rdx, [rbp+var_20]; lpSystemTime
0x18006dad5  call    cs:__imp_VariantTimeToSystemTime
0x18006dadb  test    eax, eax
0x18006dadd  jz      loc_18006DC4E
0x18006dae3  mov     qword ptr [rbp+FileTime.dwLowDateTime], rsi
0x18006dae7  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rsi
0x18006daeb  test    r14b, 1
0x18006daef  jz      short loc_18006DAFB
0x18006daf1  xor     eax, eax
0x18006daf3  mov     qword ptr [rbp+SystemTime.wHour], rax
0x18006daf7  mov     qword ptr [rbp+var_20.wHour], rax
0x18006dafb  lea     rdx, [rbp+FileTime]; lpFileTime
0x18006daff  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18006db03  call    cs:__imp_SystemTimeToFileTime
0x18006db09  test    eax, eax
0x18006db0b  jz      loc_18006DC4E
0x18006db11  lea     rdx, [rbp+FileTime2]; lpFileTime
0x18006db15  lea     rcx, [rbp+var_20]; lpSystemTime
0x18006db19  call    cs:__imp_SystemTimeToFileTime
0x18006db1f  test    eax, eax
0x18006db21  jz      loc_18006DC4E
0x18006db27  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18006db2b  lea     rcx, [rbp+FileTime]; lpFileTime1
0x18006db2f  call    cs:__imp_CompareFileTime
0x18006db35  mov     [rbx], eax
0x18006db37  jmp     loc_18006DC4E
0x18006db3c  movsd   xmm0, qword ptr [rdi+8]
0x18006db41  movsd   xmm1, qword ptr [rcx+8]
0x18006db46  comisd  xmm0, xmm1
0x18006db4a  ja      loc_18006DA9B
0x18006db50  comisd  xmm1, xmm0
0x18006db54  jmp     loc_18006DC45
0x18006db59  movss   xmm0, dword ptr [rdi+8]
0x18006db5e  movss   xmm1, dword ptr [rcx+8]
0x18006db63  comiss  xmm0, xmm1
0x18006db66  ja      loc_18006DA9B
0x18006db6c  comiss  xmm1, xmm0
0x18006db6f  jmp     loc_18006DC45
0x18006db74  mov     eax, [rcx+8]
0x18006db77  cmp     eax, [rdx+8]
0x18006db7a  jmp     loc_18006DC3F
0x18006db7f  cmp     r9d, 15h
0x18006db83  jz      loc_18006DC37
0x18006db89  cmp     r9d, 1Fh
0x18006db8d  jz      loc_18006DC24
0x18006db93  cmp     r9d, 40h ; '@'
0x18006db97  jz      short loc_18006DC17
0x18006db99  cmp     r9d, 48h ; 'H'
0x18006db9d  jz      short loc_18006DBFF
0x18006db9f  mov     esi, 80004005h
0x18006dba4  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dbab  cmp     rcx, r12
0x18006dbae  jz      loc_18006DC4E
0x18006dbb4  test    byte ptr [rcx+1Ch], 2
0x18006dbb8  jz      short loc_18006DBDA
0x18006dbba  mov     rcx, [rcx+10h]
0x18006dbbe  lea     r8, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x18006dbc5  mov     edx, 21h ; '!'
0x18006dbca  mov     [rsp+70h+var_50], esi
0x18006dbce  call    WPP_SF_dd
0x18006dbd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dbda  cmp     rcx, r12
0x18006dbdd  jz      short loc_18006DC4E
0x18006dbdf  test    byte ptr [rcx+1Ch], 2
0x18006dbe3  jz      short loc_18006DC4E
0x18006dbe5  mov     rcx, [rcx+10h]
0x18006dbe9  lea     r8, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x18006dbf0  mov     edx, 22h ; '"'
0x18006dbf5  mov     r9d, esi
0x18006dbf8  call    WPP_SF_d
0x18006dbfd  jmp     short loc_18006DC4E
0x18006dbff  mov     rdx, [rdx+8]; Buf2
0x18006dc03  mov     r8d, 10h; Size
0x18006dc09  mov     rcx, [rcx+8]; Buf1
0x18006dc0d  call    memcmp_0
0x18006dc12  jmp     loc_18006DB35
0x18006dc17  add     rdx, 8
0x18006dc1b  add     rcx, 8
0x18006dc1f  jmp     loc_18006DB2F
0x18006dc24  mov     rdx, [rdx+8]; psz2
0x18006dc28  mov     rcx, [rcx+8]; psz1
0x18006dc2c  call    cs:__imp_StrCmpLogicalW
0x18006dc32  jmp     loc_18006DB35
0x18006dc37  mov     rax, [rcx+8]
0x18006dc3b  cmp     rax, [rdx+8]
0x18006dc3f  jb      loc_18006DA9B
0x18006dc45  jbe     short loc_18006DC4E
0x18006dc47  mov     dword ptr [r8], 1
0x18006dc4e  mov     eax, esi
0x18006dc50  mov     rcx, [rbp+var_10]
0x18006dc54  xor     rcx, rsp; StackCookie
0x18006dc57  call    __security_check_cookie
0x18006dc5c  mov     rbx, [rsp+70h+arg_18]
0x18006dc64  add     rsp, 70h
0x18006dc68  pop     r14
0x18006dc6a  pop     r12
0x18006dc6c  pop     rdi
0x18006dc6d  pop     rsi
0x18006dc6e  pop     rbp
0x18006dc6f  retn
```
