# PKCV_DefaultConversion(_tagpropertykey const &,tagPROPVARIANT const &,tagPROPVARIANT *)

- ea: `0x180052714`
- end: `0x180052aaf`
- name: `?PKCV_DefaultConversion@@YAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@PEAU2@@Z`
- size: `923`
- prototype: `__int64 __fastcall(const struct _tagpropertykey *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180053490`

## callees

- `0x18001a5b0`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x18003a650`
- `0x180052714`
- `0x1800533dc`

## import_xrefs

- `KERNEL32!FileTimeToSystemTime` at `0x180052a19`
- `KERNEL32!FileTimeToSystemTime` at `0x180052a19`
- `ole32!CoTaskMemAlloc` at `0x180052856`
- `ole32!CoTaskMemAlloc` at `0x180052856`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180052a2d`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180052a2d`

## pseudocode

```c
__int64 __fastcall PKCV_DefaultConversion(
        const struct _tagpropertykey *a1,
        const struct tagPROPVARIANT *a2,
        struct tagPROPVARIANT *a3)
{
  unsigned int ulVal; // r15d
  SIZE_T v6; // rsi
  unsigned int i; // r14d
  BYTE *v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  SIZE_T v14; // r14
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rsi
  unsigned int v17; // r15d
  BYTE *pData; // rcx
  __int64 v19; // r10
  struct _SYSTEMTIME SystemTime; // [rsp+20h] [rbp-48h] BYREF

  if ( !a2->vt || a2->vt == 10 || !a3 || a3->vt )
  {
    v10 = -2147024809;
    goto LABEL_60;
  }
  if ( a2->vt != 4127 )
  {
    if ( a2->vt == 8223 )
    {
      v10 = -2147467259;
      goto LABEL_60;
    }
    if ( a2->vt == 64 )
    {
      v10 = 0;
      SystemTime = 0;
      FileTimeToSystemTime(&a2->filetime, &SystemTime);
      a3->vt = 7;
      SystemTimeToVariantTime(&SystemTime, &a3->dblVal);
      return v10;
    }
    if ( (a2->vt & 0x3000) == 0 )
      return 1;
    v10 = -2147467259;
    goto LABEL_57;
  }
  ulVal = a2->ulVal;
  v6 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= ulVal )
    {
      v14 = v6 + 4LL * ulVal;
      if ( v14 < v6 )
      {
        v11 = (PVOID *)WPP_GLOBAL_Control;
        v10 = -2147024362;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v10;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_61;
        v12 = 160;
      }
      else
      {
        if ( v14 - 1 <= 0x3FE )
        {
          v15 = (unsigned __int16 *)CoTaskMemAlloc(v14);
          v16 = v15;
          if ( !v15 )
          {
            v10 = -2147024882;
            goto LABEL_60;
          }
          memset_0(v15, 0, v14);
          v17 = 0;
          v10 = 0;
          while ( v17 < a2->lVal )
          {
            pData = a2->bstrblobVal.pData;
            *(_QWORD *)&SystemTime.wYear = 0;
            v9 = StringCchLengthW(
                   *(const unsigned __int16 **)&pData[8 * v17],
                   0x104u,
                   (unsigned __int64 *)&SystemTime.wYear);
            v10 = v9;
            if ( v9 < 0 )
            {
              v11 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                return v10;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v12 = 161;
                goto LABEL_19;
              }
              goto LABEL_61;
            }
            if ( *(_QWORD *)&SystemTime.wYear )
            {
              v9 = StringCbCatW(v16, v14, *(const unsigned __int16 **)&a2->bstrblobVal.pData[8 * v19]);
              v10 = v9;
              if ( v9 < 0 )
              {
                v11 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                  return v10;
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v12 = 162;
                  goto LABEL_19;
                }
                goto LABEL_61;
              }
              if ( v17 < a2->lVal - 1 )
              {
                v9 = StringCbCatW(v16, v14, L"; ");
                v10 = v9;
                if ( v9 < 0 )
                {
                  v11 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                    return v10;
                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    v12 = 163;
                    goto LABEL_19;
                  }
                  goto LABEL_61;
                }
              }
            }
            ++v17;
          }
          if ( (v10 & 0x80000000) != 0 )
            goto LABEL_44;
          a3->vt = 31;
          a3->hVal.QuadPart = (LONGLONG)v16;
LABEL_57:
          if ( (v10 & 0x80000000) == 0 )
            return v10;
LABEL_60:
          v11 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_61;
        }
        v10 = -2147467259;
LABEL_44:
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v10;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_61;
        v12 = 164;
      }
LABEL_14:
      v13 = v10;
      goto LABEL_15;
    }
    v8 = a2->bstrblobVal.pData;
    *(_QWORD *)&SystemTime.wYear = 0;
    v9 = StringCbLengthW(*(const unsigned __int16 **)&v8[8 * i], 0x208u, (unsigned __int64 *)&SystemTime.wYear);
    v10 = v9;
    if ( v9 < 0 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v10;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_61;
      v12 = 158;
LABEL_19:
      v13 = (unsigned int)v9;
LABEL_15:
      WPP_SF_d(v11[2], v12, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, v13);
      goto LABEL_60;
    }
    if ( v6 + *(_QWORD *)&SystemTime.wYear < v6 )
      break;
    v6 += *(_QWORD *)&SystemTime.wYear;
  }
  v10 = -2147024362;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v12 = 159;
    goto LABEL_14;
  }
LABEL_61:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 )
    WPP_SF_d(v11[2], 165, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180052714  mov     [rsp+arg_0], rbx
0x180052719  mov     [rsp+arg_18], rbp
0x18005271e  push    rsi
0x18005271f  push    rdi
0x180052720  push    r12
0x180052722  push    r14
0x180052724  push    r15
0x180052726  sub     rsp, 40h
0x18005272a  mov     rax, cs:__security_cookie
0x180052731  xor     rax, rsp
0x180052734  mov     [rsp+68h+var_38], rax
0x180052739  xor     r12d, r12d
0x18005273c  mov     rdi, r8
0x18005273f  mov     rbp, rdx
0x180052742  cmp     [rdx], r12w
0x180052746  jz      loc_180052A51
0x18005274c  cmp     word ptr [rdx], 0Ah
0x180052750  jz      loc_180052A51
0x180052756  test    r8, r8
0x180052759  jz      loc_180052A51
0x18005275f  cmp     [r8], r12w
0x180052763  jnz     loc_180052A51
0x180052769  mov     eax, 101Fh
0x18005276e  cmp     [rdx], ax
0x180052771  jnz     loc_1800529EE
0x180052777  mov     r15d, [rdx+8]
0x18005277b  mov     esi, r12d
0x18005277e  mov     r14d, r12d
0x180052781  cmp     r14d, r15d
0x180052784  jnb     loc_180052832
0x18005278a  mov     rcx, [rbp+10h]
0x18005278e  lea     r8, [rsp+68h+SystemTime]; unsigned __int64 *
0x180052793  mov     eax, r14d
0x180052796  mov     edx, 208h; unsigned __int64
0x18005279b  mov     qword ptr [rsp+68h+SystemTime.wYear], r12
0x1800527a0  mov     rcx, [rcx+rax*8]; unsigned __int16 *
0x1800527a4  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800527a9  mov     ebx, eax
0x1800527ab  test    eax, eax
0x1800527ad  js      short loc_180052807
0x1800527af  mov     rcx, qword ptr [rsp+68h+SystemTime.wYear]
0x1800527b4  add     rcx, rsi
0x1800527b7  cmp     rcx, rsi
0x1800527ba  jb      short loc_1800527C4
0x1800527bc  mov     rsi, rcx
0x1800527bf  inc     r14d
0x1800527c2  jmp     short loc_180052781
0x1800527c4  mov     ebx, 80070216h
0x1800527c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800527d0  lea     rdi, WPP_GLOBAL_Control
0x1800527d7  cmp     rcx, rdi
0x1800527da  jz      loc_180052A87
0x1800527e0  test    byte ptr [rcx+1Ch], 2
0x1800527e4  jz      loc_180052A64
0x1800527ea  mov     edx, 9Fh
0x1800527ef  mov     r9d, ebx
0x1800527f2  mov     rcx, [rcx+10h]
0x1800527f6  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x1800527fd  call    WPP_SF_d
0x180052802  jmp     loc_180052A5D
0x180052807  mov     rcx, cs:WPP_GLOBAL_Control
0x18005280e  lea     rdi, WPP_GLOBAL_Control
0x180052815  cmp     rcx, rdi
0x180052818  jz      loc_180052A87
0x18005281e  test    byte ptr [rcx+1Ch], 2
0x180052822  jz      loc_180052A64
0x180052828  mov     edx, 9Eh
0x18005282d  mov     r9d, eax
0x180052830  jmp     short loc_1800527F2
0x180052832  lea     eax, [r15+r15]
0x180052836  lea     r14, [rsi+rax*2]
0x18005283a  cmp     r14, rsi
0x18005283d  jb      loc_1800529BE
0x180052843  lea     rax, [r14-1]
0x180052847  cmp     rax, 3FEh
0x18005284d  ja      loc_18005298E
0x180052853  mov     rcx, r14; cb
0x180052856  call    cs:__imp_CoTaskMemAlloc
0x18005285c  mov     rsi, rax
0x18005285f  test    rax, rax
0x180052862  jnz     short loc_18005286E
0x180052864  mov     ebx, 8007000Eh
0x180052869  jmp     loc_180052A56
0x18005286e  mov     r8, r14; Size
0x180052871  xor     edx, edx; Val
0x180052873  mov     rcx, rsi; void *
0x180052876  call    memset_0
0x18005287b  mov     r15d, r12d
0x18005287e  mov     ebx, r12d
0x180052881  cmp     r15d, [rbp+8]
0x180052885  jnb     loc_18005297C
0x18005288b  mov     rcx, [rbp+10h]
0x18005288f  lea     r8, [rsp+68h+SystemTime]; unsigned __int64 *
0x180052894  mov     r10d, r15d
0x180052897  mov     edx, 104h; unsigned __int64
0x18005289c  mov     qword ptr [rsp+68h+SystemTime.wYear], r12
0x1800528a1  mov     rcx, [rcx+r10*8]; unsigned __int16 *
0x1800528a5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800528aa  mov     ebx, eax
0x1800528ac  test    eax, eax
0x1800528ae  js      loc_180052951
0x1800528b4  cmp     qword ptr [rsp+68h+SystemTime.wYear], r12
0x1800528b9  jz      short loc_1800528F6
0x1800528bb  mov     r8, [rbp+10h]
0x1800528bf  mov     rdx, r14; unsigned __int64
0x1800528c2  mov     rcx, rsi; unsigned __int16 *
0x1800528c5  mov     r8, [r8+r10*8]; unsigned __int16 *
0x1800528c9  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800528ce  mov     ebx, eax
0x1800528d0  test    eax, eax
0x1800528d2  js      short loc_180052926
0x1800528d4  mov     eax, [rbp+8]
0x1800528d7  dec     eax
0x1800528d9  cmp     r15d, eax
0x1800528dc  jnb     short loc_1800528F6
0x1800528de  lea     r8, asc_1800824C0; "; "
0x1800528e5  mov     rdx, r14; unsigned __int64
0x1800528e8  mov     rcx, rsi; unsigned __int16 *
0x1800528eb  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800528f0  mov     ebx, eax
0x1800528f2  test    eax, eax
0x1800528f4  js      short loc_1800528FB
0x1800528f6  inc     r15d
0x1800528f9  jmp     short loc_180052881
0x1800528fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180052902  lea     rdi, WPP_GLOBAL_Control
0x180052909  cmp     rcx, rdi
0x18005290c  jz      loc_180052A87
0x180052912  test    byte ptr [rcx+1Ch], 2
0x180052916  jz      loc_180052A64
0x18005291c  mov     edx, 0A3h
0x180052921  jmp     loc_18005282D
0x180052926  mov     rcx, cs:WPP_GLOBAL_Control
0x18005292d  lea     rdi, WPP_GLOBAL_Control
0x180052934  cmp     rcx, rdi
0x180052937  jz      loc_180052A87
0x18005293d  test    byte ptr [rcx+1Ch], 2
0x180052941  jz      loc_180052A64
0x180052947  mov     edx, 0A2h
0x18005294c  jmp     loc_18005282D
0x180052951  mov     rcx, cs:WPP_GLOBAL_Control
0x180052958  lea     rdi, WPP_GLOBAL_Control
0x18005295f  cmp     rcx, rdi
0x180052962  jz      loc_180052A87
0x180052968  test    byte ptr [rcx+1Ch], 2
0x18005296c  jz      loc_180052A64
0x180052972  mov     edx, 0A1h
0x180052977  jmp     loc_18005282D
0x18005297c  test    ebx, ebx
0x18005297e  js      short loc_180052993
0x180052980  mov     word ptr [rdi], 1Fh
0x180052985  mov     [rdi+8], rsi
0x180052989  jmp     loc_180052A4B
0x18005298e  mov     ebx, 80004005h
0x180052993  mov     rcx, cs:WPP_GLOBAL_Control
0x18005299a  lea     rdi, WPP_GLOBAL_Control
0x1800529a1  cmp     rcx, rdi
0x1800529a4  jz      loc_180052A87
0x1800529aa  test    byte ptr [rcx+1Ch], 2
0x1800529ae  jz      loc_180052A64
0x1800529b4  mov     edx, 0A4h
0x1800529b9  jmp     loc_1800527EF
0x1800529be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800529c5  lea     rdi, WPP_GLOBAL_Control
0x1800529cc  mov     ebx, 80070216h
0x1800529d1  cmp     rcx, rdi
0x1800529d4  jz      loc_180052A87
0x1800529da  test    byte ptr [rcx+1Ch], 2
0x1800529de  jz      loc_180052A64
0x1800529e4  mov     edx, 0A0h
0x1800529e9  jmp     loc_1800527EF
0x1800529ee  mov     eax, 201Fh
0x1800529f3  cmp     [rdx], ax
0x1800529f6  jnz     short loc_1800529FF
0x1800529f8  mov     ebx, 80004005h
0x1800529fd  jmp     short loc_180052A56
0x1800529ff  cmp     word ptr [rdx], 40h ; '@'
0x180052a03  jnz     short loc_180052A35
0x180052a05  xorps   xmm0, xmm0
0x180052a08  lea     rcx, [rdx+8]; lpFileTime
0x180052a0c  lea     rdx, [rsp+68h+SystemTime]; lpSystemTime
0x180052a11  mov     ebx, r12d
0x180052a14  movups  xmmword ptr [rsp+68h+SystemTime.wYear], xmm0
0x180052a19  call    cs:__imp_FileTimeToSystemTime
0x180052a1f  lea     rdx, [rdi+8]; pvtime
0x180052a23  mov     word ptr [rdi], 7
0x180052a28  lea     rcx, [rsp+68h+SystemTime]; lpSystemTime
0x180052a2d  call    cs:__imp_SystemTimeToVariantTime
0x180052a33  jmp     short loc_180052A87
0x180052a35  mov     eax, 3000h
0x180052a3a  test    [rdx], ax
0x180052a3d  jnz     short loc_180052A46
0x180052a3f  mov     ebx, 1
0x180052a44  jmp     short loc_180052A87
0x180052a46  mov     ebx, 80004005h
0x180052a4b  test    ebx, ebx
0x180052a4d  jns     short loc_180052A87
0x180052a4f  jmp     short loc_180052A56
0x180052a51  mov     ebx, 80070057h
0x180052a56  lea     rdi, WPP_GLOBAL_Control
0x180052a5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180052a64  cmp     rcx, rdi
0x180052a67  jz      short loc_180052A87
0x180052a69  test    byte ptr [rcx+1Ch], 2
0x180052a6d  jz      short loc_180052A87
0x180052a6f  mov     rcx, [rcx+10h]
0x180052a73  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180052a7a  mov     edx, 0A5h
0x180052a7f  mov     r9d, ebx
0x180052a82  call    WPP_SF_d
0x180052a87  mov     eax, ebx
0x180052a89  mov     rcx, [rsp+68h+var_38]
0x180052a8e  xor     rcx, rsp; StackCookie
0x180052a91  call    __security_check_cookie
0x180052a96  lea     r11, [rsp+68h+var_28]
0x180052a9b  mov     rbx, [r11+30h]
0x180052a9f  mov     rbp, [r11+48h]
0x180052aa3  mov     rsp, r11
0x180052aa6  pop     r15
0x180052aa8  pop     r14
0x180052aaa  pop     r12
0x180052aac  pop     rdi
0x180052aad  pop     rsi
0x180052aae  retn
```
