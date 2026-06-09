# CUserManager::DeleteAccount(ushort *,bool)

- ea: `0x18000aac4`
- end: `0x18000ad06`
- name: `?DeleteAccount@CUserManager@@QEAAJPEAG_N@Z`
- size: `578`
- prototype: `int(CUserManager *__hidden this, unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x18000ad0c`
- `0x18000ade0`

## callees

- `0x18000aac4`
- `0x180014c28`
- `0x180022610`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x18000abb1`
- `SHELL32!SHGetFolderPathEx` at `0x18000abb1`
- `SHLWAPI!__imp_StrCmpICW` at `0x18000ab3a`
- `SHLWAPI!__imp_StrCmpICW` at `0x18000ab3a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000abe5`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ac33`
- `OLEAUT32!__imp_SysAllocString` at `0x18000abe5`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ac33`
- `OLEAUT32!__imp_SysFreeString` at `0x18000acd8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000acd8`
- `OLEAUT32!__imp_VariantInit` at `0x18000ab81`
- `OLEAUT32!__imp_VariantInit` at `0x18000ac03`
- `OLEAUT32!__imp_VariantInit` at `0x18000ac24`
- `OLEAUT32!__imp_VariantInit` at `0x18000ac56`
- `OLEAUT32!__imp_VariantInit` at `0x18000ab81`
- `OLEAUT32!__imp_VariantInit` at `0x18000ac03`
- `OLEAUT32!__imp_VariantInit` at `0x18000ac24`
- `OLEAUT32!__imp_VariantInit` at `0x18000ac56`
- `OLEAUT32!__imp_VariantClear` at `0x18000acc2`
- `OLEAUT32!__imp_VariantClear` at `0x18000accd`
- `OLEAUT32!__imp_VariantClear` at `0x18000acc2`
- `OLEAUT32!__imp_VariantClear` at `0x18000accd`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000abcb`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000abcb`

## pseudocode

```c
__int64 __fastcall CUserManager::DeleteAccount(CUserManager *this, unsigned __int16 *a2, char a3)
{
  __int64 v3; // rax
  __int64 v7; // rax
  HRESULT v8; // ebx
  HWND ParentWindow; // rax
  LONGLONG llVal; // rax
  __int64 *v11; // rcx
  __int64 v12; // rax
  __int64 (__fastcall *v13)(__int64 *, __int128 *, __int128 *, __int16 *); // rax
  __int16 v15; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR pszStr2; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG v18; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v19; // [rsp+70h] [rbp-90h] BYREF
  IRecordInfo *pRecInfo; // [rsp+80h] [rbp-80h]
  __int128 v21; // [rsp+90h] [rbp-70h] BYREF
  IRecordInfo *v22; // [rsp+A0h] [rbp-60h]
  WCHAR pszPath[264]; // [rsp+B0h] [rbp-50h] BYREF

  v3 = *(_QWORD *)this;
  pszStr2 = 0;
  v7 = (*(__int64 (__fastcall **)(CUserManager *))(v3 + 152))(this);
  v8 = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v7 + 96LL))(v7, &pszStr2);
  if ( v8 >= 0 )
  {
    if ( StrCmpICW(a2, pszStr2) )
    {
      VariantInit(&pvarg);
      if ( !a3 )
        goto LABEL_14;
      v8 = SHGetFolderPathEx(&FOLDERID_Desktop, 0, 0, pszPath, 260);
      if ( v8 >= 0 )
      {
        v8 = PathCchAppend(pszPath, 0x104u, a2);
        if ( v8 >= 0 )
        {
          pvarg.vt = 8;
          llVal = (LONGLONG)SysAllocString(pszPath);
          pvarg.llVal = llVal;
          if ( llVal )
          {
            v8 = 0;
          }
          else
          {
            v8 = -2147024882;
            VariantInit(&pvarg);
            llVal = pvarg.llVal;
          }
          if ( v8 >= 0 && llVal )
          {
LABEL_14:
            VariantInit(&v18);
            v18.vt = 8;
            v18.llVal = (LONGLONG)SysAllocString(a2);
            if ( v18.llVal )
            {
              v11 = (__int64 *)*((_QWORD *)this + 8);
              v19 = *(_OWORD *)&pvarg.vt;
              v15 = 0;
              v12 = *v11;
              pRecInfo = pvarg.pRecInfo;
              v21 = *(_OWORD *)&v18.vt;
              v13 = *(__int64 (__fastcall **)(__int64 *, __int128 *, __int128 *, __int16 *))(v12 + 64);
              v22 = v18.pRecInfo;
              v8 = v13(v11, &v21, &v19, &v15);
            }
            else
            {
              v8 = a2 != 0 ? -2147024882 : -2147024809;
              VariantInit(&v18);
            }
            (*(void (__fastcall **)(CUserManager *))(*(_QWORD *)this + 40LL))(this);
            VariantClear(&v18);
          }
        }
      }
      VariantClear(&pvarg);
    }
    else
    {
      ParentWindow = (HWND)*((_QWORD *)this + 111);
      v8 = -2147024891;
      if ( !ParentWindow )
      {
        ParentWindow = CUserCplCore::GetParentWindow(*((CUserCplCore **)this + 110));
        *((_QWORD *)this + 111) = ParentWindow;
      }
      CUserCplCore::s_ThrowErrorBox(ParentWindow, 0x22u, 0);
    }
  }
  SysFreeString((BSTR)pszStr2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000aac4  mov     [rsp-8+arg_10], rbx
0x18000aac9  push    rbp
0x18000aaca  push    rsi
0x18000aacb  push    rdi
0x18000aacc  push    r14
0x18000aace  push    r15
0x18000aad0  lea     rbp, [rsp-1D0h]
0x18000aad8  sub     rsp, 2D0h
0x18000aadf  mov     rax, cs:__security_cookie
0x18000aae6  xor     rax, rsp
0x18000aae9  mov     [rbp+1F0h+var_30], rax
0x18000aaf0  mov     rax, [rcx]
0x18000aaf3  mov     r14b, r8b
0x18000aaf6  mov     rsi, rdx
0x18000aaf9  mov     [rsp+2F0h+pszStr2], 0
0x18000ab02  mov     rdi, rcx
0x18000ab05  mov     rax, [rax+98h]
0x18000ab0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab11  mov     r8, rax
0x18000ab14  lea     rdx, [rsp+2F0h+pszStr2]
0x18000ab19  mov     rcx, [rax]
0x18000ab1c  mov     rax, [rcx+60h]
0x18000ab20  mov     rcx, r8
0x18000ab23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab28  mov     ebx, eax
0x18000ab2a  test    eax, eax
0x18000ab2c  js      loc_18000ACD3
0x18000ab32  mov     rdx, [rsp+2F0h+pszStr2]; pszStr2
0x18000ab37  mov     rcx, rsi; pszStr1
0x18000ab3a  call    cs:__imp_StrCmpICW
0x18000ab40  test    eax, eax
0x18000ab42  jnz     short loc_18000AB7C
0x18000ab44  mov     rax, [rdi+378h]
0x18000ab4b  mov     ebx, 80070005h
0x18000ab50  test    rax, rax
0x18000ab53  jnz     short loc_18000AB68
0x18000ab55  mov     rcx, [rdi+370h]; this
0x18000ab5c  call    ?GetParentWindow@CUserCplCore@@QEAAPEAUHWND__@@XZ; CUserCplCore::GetParentWindow(void)
0x18000ab61  mov     [rdi+378h], rax
0x18000ab68  xor     r8d, r8d; unsigned int
0x18000ab6b  mov     rcx, rax; hWnd
0x18000ab6e  lea     edx, [r8+22h]; unsigned int
0x18000ab72  call    ?s_ThrowErrorBox@CUserCplCore@@SA_NPEAUHWND__@@II@Z; CUserCplCore::s_ThrowErrorBox(HWND__ *,uint,uint)
0x18000ab77  jmp     loc_18000ACD3
0x18000ab7c  lea     rcx, [rsp+2F0h+pvarg]; pvarg
0x18000ab81  call    cs:__imp_VariantInit
0x18000ab87  mov     r15d, 8
0x18000ab8d  test    r14b, r14b
0x18000ab90  jz      loc_18000AC1F
0x18000ab96  mov     r14d, 104h
0x18000ab9c  lea     r9, [rbp+1F0h+pszPath]
0x18000aba0  xor     r8d, r8d
0x18000aba3  mov     [rsp+2F0h+var_2D0], r14d
0x18000aba8  xor     edx, edx
0x18000abaa  lea     rcx, FOLDERID_Desktop
0x18000abb1  call    cs:__imp_SHGetFolderPathEx
0x18000abb7  mov     ebx, eax
0x18000abb9  test    eax, eax
0x18000abbb  js      loc_18000ACC8
0x18000abc1  mov     r8, rsi; pszMore
0x18000abc4  lea     rcx, [rbp+1F0h+pszPath]; pszPath
0x18000abc8  mov     edx, r14d; cchPath
0x18000abcb  call    cs:__imp_PathCchAppend
0x18000abd1  mov     ebx, eax
0x18000abd3  test    eax, eax
0x18000abd5  js      loc_18000ACC8
0x18000abdb  lea     rcx, [rbp+1F0h+pszPath]; psz
0x18000abdf  mov     word ptr [rsp+2F0h+pvarg], r15w
0x18000abe5  call    cs:__imp_SysAllocString
0x18000abeb  mov     qword ptr [rsp+2F0h+pvarg+8], rax
0x18000abf0  test    rax, rax
0x18000abf3  jz      short loc_18000ABF9
0x18000abf5  xor     ebx, ebx
0x18000abf7  jmp     short loc_18000AC0E
0x18000abf9  lea     rcx, [rsp+2F0h+pvarg]; pvarg
0x18000abfe  mov     ebx, 8007000Eh
0x18000ac03  call    cs:__imp_VariantInit
0x18000ac09  mov     rax, qword ptr [rsp+2F0h+pvarg+8]
0x18000ac0e  test    ebx, ebx
0x18000ac10  js      loc_18000ACC8
0x18000ac16  test    rax, rax
0x18000ac19  jz      loc_18000ACC8
0x18000ac1f  lea     rcx, [rsp+2F0h+var_298]; pvarg
0x18000ac24  call    cs:__imp_VariantInit
0x18000ac2a  mov     rcx, rsi; psz
0x18000ac2d  mov     word ptr [rsp+2F0h+var_298], r15w
0x18000ac33  call    cs:__imp_SysAllocString
0x18000ac39  mov     qword ptr [rsp+2F0h+var_298+8], rax
0x18000ac3e  test    rax, rax
0x18000ac41  jnz     short loc_18000AC5E
0x18000ac43  neg     rsi
0x18000ac46  lea     rcx, [rsp+2F0h+var_298]; pvarg
0x18000ac4b  sbb     ebx, ebx
0x18000ac4d  and     ebx, 0FFFFFFB7h
0x18000ac50  add     ebx, 80070057h
0x18000ac56  call    cs:__imp_VariantInit
0x18000ac5c  jmp     short loc_18000ACAE
0x18000ac5e  movups  xmm0, xmmword ptr [rsp+2F0h+pvarg]
0x18000ac63  lea     r9, [rsp+2F0h+var_2C0]
0x18000ac68  mov     rcx, [rdi+40h]
0x18000ac6c  movsd   xmm1, qword ptr [rsp+2F0h+pvarg+10h]
0x18000ac72  lea     r8, [rsp+2F0h+var_280]
0x18000ac77  xor     eax, eax
0x18000ac79  movaps  [rsp+2F0h+var_280], xmm0
0x18000ac7e  movups  xmm0, xmmword ptr [rsp+2F0h+var_298]
0x18000ac83  mov     [rsp+2F0h+var_2C0], ax
0x18000ac88  lea     rdx, [rbp+1F0h+var_260]
0x18000ac8c  mov     rax, [rcx]
0x18000ac8f  movsd   [rbp+1F0h+var_270], xmm1
0x18000ac94  movsd   xmm1, qword ptr [rsp+2F0h+var_298+10h]
0x18000ac9a  movaps  [rbp+1F0h+var_260], xmm0
0x18000ac9e  mov     rax, [rax+40h]
0x18000aca2  movsd   [rbp+1F0h+var_250], xmm1
0x18000aca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acac  mov     ebx, eax
0x18000acae  mov     rax, [rdi]
0x18000acb1  mov     rcx, rdi
0x18000acb4  mov     rax, [rax+28h]
0x18000acb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acbd  lea     rcx, [rsp+2F0h+var_298]; pvarg
0x18000acc2  call    cs:__imp_VariantClear
0x18000acc8  lea     rcx, [rsp+2F0h+pvarg]; pvarg
0x18000accd  call    cs:__imp_VariantClear
0x18000acd3  mov     rcx, [rsp+2F0h+pszStr2]; bstrString
0x18000acd8  call    cs:__imp_SysFreeString
0x18000acde  mov     eax, ebx
0x18000ace0  mov     rcx, [rbp+1F0h+var_30]
0x18000ace7  xor     rcx, rsp; StackCookie
0x18000acea  call    __security_check_cookie
0x18000acef  mov     rbx, [rsp+2F0h+arg_10]
0x18000acf7  add     rsp, 2D0h
0x18000acfe  pop     r15
0x18000ad00  pop     r14
0x18000ad02  pop     rdi
0x18000ad03  pop     rsi
0x18000ad04  pop     rbp
0x18000ad05  retn
```
