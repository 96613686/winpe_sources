# CContentFolder::_CheckForStgItemCollision(ushort const *,int,ushort * *)

- ea: `0x180045e64`
- end: `0x180046102`
- name: `?_CheckForStgItemCollision@CContentFolder@@AEAAJPEBGHPEAPEAG@Z`
- size: `670`
- prototype: `__int64 __fastcall(CContentFolder *__hidden this, const unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180042af0`
- `0x1800430b0`
- `0x180048924`

## callees

- `0x180004190`
- `0x1800082e0`
- `0x18002ff5c`
- `0x180035590`
- `0x180039e80`
- `0x180045e64`
- `0x180078010`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180045fab`
- `SHLWAPI!SHStrDupW` at `0x180045fab`
- `ole32!CoTaskMemFree` at `0x180045f0b`
- `ole32!CoTaskMemFree` at `0x180045feb`
- `ole32!CoTaskMemFree` at `0x18004609e`
- `ole32!CoTaskMemFree` at `0x1800460d4`
- `ole32!CoTaskMemFree` at `0x180045f0b`
- `ole32!CoTaskMemFree` at `0x180045feb`
- `ole32!CoTaskMemFree` at `0x18004609e`
- `ole32!CoTaskMemFree` at `0x1800460d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentFolder::_CheckForStgItemCollision(
        CContentFolder *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int16 **a4)
{
  char *v7; // rcx
  __int64 (__fastcall *v8)(char *, _QWORD, _QWORD, const unsigned __int16 *, _QWORD, LPVOID *, _QWORD); // rax
  int v9; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  int v12; // edx
  CContentFolder *v13; // rcx
  const struct CONTENTITEM *v14; // rax
  CContentFolder *v15; // rcx
  unsigned int v16; // r9d
  HRESULT v17; // eax
  unsigned __int16 *v18; // rax
  int v19; // eax
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR ppwsz; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR psz[264]; // [rsp+50h] [rbp-B0h] BYREF

  ppwsz = 0;
  if ( a4 )
    *a4 = 0;
  v7 = (char *)this + 16;
  v8 = *(__int64 (__fastcall **)(char *, _QWORD, _QWORD, const unsigned __int16 *, _QWORD, LPVOID *, _QWORD))(*(_QWORD *)v7 + 24LL);
  pv = 0;
  if ( !a3 )
  {
    *((_DWORD *)this + 36) = 1;
    v19 = v8(v7, 0, 0, a2, 0, &pv, 0);
    v10 = v19;
    *((_DWORD *)this + 36) = 0;
    if ( v19 < 0 )
    {
      if ( v19 == -2147024894 )
      {
        v10 = 0;
        goto LABEL_6;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          313,
          (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (_DWORD)a2,
          v19);
    }
    else
    {
      v10 = -2147286960;
    }
    goto LABEL_31;
  }
  v9 = v8(v7, 0, 0, a2, 0, &pv, 0);
  v10 = v9;
  if ( v9 == -2147024894 )
  {
LABEL_5:
    v10 = 0;
LABEL_6:
    CoTaskMemFree(pv);
    goto LABEL_34;
  }
  if ( v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 310;
LABEL_11:
      WPP_SF_Sd(v11[2], v12, (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (_DWORD)a2, v9);
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  v9 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *))(*((_QWORD *)this + 16) + 96LL))(
         (char *)this + 128,
         a2);
  v10 = v9;
  if ( v9 == -2147287038 )
    goto LABEL_5;
  if ( v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 311;
      goto LABEL_11;
    }
LABEL_31:
    CoTaskMemFree(pv);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 314, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v10);
    goto LABEL_34;
  }
  v14 = CContentFolder::_IsValid(v13, (const struct _ITEMIDLIST *)pv);
  CContentFolder::_Name(v15, v14, psz, v16);
  v17 = SHStrDupW(psz, &ppwsz);
  v10 = v17;
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        312,
        WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
        (unsigned int)v17);
    goto LABEL_31;
  }
  CoTaskMemFree(pv);
  if ( a4 )
  {
    v18 = ppwsz;
    ppwsz = 0;
    *a4 = v18;
  }
LABEL_34:
  CoTaskMemFree(ppwsz);
  return v10;
}

```

## disassembly

```asm
0x180045e64  mov     [rsp-8+arg_10], rbx
0x180045e69  push    rbp
0x180045e6a  push    rsi
0x180045e6b  push    rdi
0x180045e6c  push    r13
0x180045e6e  push    r14
0x180045e70  lea     rbp, [rsp-170h]
0x180045e78  sub     rsp, 270h
0x180045e7f  mov     rax, cs:__security_cookie
0x180045e86  xor     rax, rsp
0x180045e89  mov     [rbp+190h+var_30], rax
0x180045e90  mov     rdi, r9
0x180045e93  mov     rsi, rdx
0x180045e96  mov     r14, rcx
0x180045e99  mov     [rsp+290h+ppwsz], 0
0x180045ea2  test    r9, r9
0x180045ea5  jz      short loc_180045EAE
0x180045ea7  mov     qword ptr [r9], 0
0x180045eae  add     rcx, 10h
0x180045eb2  mov     rax, [rcx]
0x180045eb5  mov     rax, [rax+18h]
0x180045eb9  lea     r13, WPP_GLOBAL_Control
0x180045ec0  mov     [rsp+290h+pv], 0
0x180045ec9  test    r8d, r8d
0x180045ecc  jz      loc_180046010
0x180045ed2  mov     [rsp+290h+var_260], 0
0x180045edb  lea     rdx, [rsp+290h+pv]
0x180045ee0  mov     [rsp+290h+var_268], rdx
0x180045ee5  mov     [rsp+290h+var_270], 0
0x180045eee  mov     r9, rsi
0x180045ef1  xor     r8d, r8d
0x180045ef4  xor     edx, edx
0x180045ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045efb  mov     ebx, eax
0x180045efd  cmp     eax, 80070002h
0x180045f02  jnz     short loc_180045F16
0x180045f04  xor     ebx, ebx
0x180045f06  mov     rcx, [rsp+290h+pv]; pv
0x180045f0b  call    cs:__imp_CoTaskMemFree
0x180045f11  jmp     loc_1800460CF
0x180045f16  test    eax, eax
0x180045f18  jns     short loc_180045F4E
0x180045f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180045f21  cmp     rcx, r13
0x180045f24  jz      short loc_180045F49
0x180045f26  test    byte ptr [rcx+1Ch], 2
0x180045f2a  jz      short loc_180045F49
0x180045f2c  mov     edx, 136h
0x180045f31  mov     dword ptr [rsp+290h+var_270], eax
0x180045f35  mov     r9, rsi
0x180045f38  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180045f3f  mov     rcx, [rcx+10h]
0x180045f43  call    WPP_SF_Sd
0x180045f48  nop
0x180045f49  jmp     loc_180046099
0x180045f4e  lea     rcx, [r14+80h]
0x180045f55  mov     rax, [rcx]
0x180045f58  mov     rdx, rsi
0x180045f5b  mov     rax, [rax+60h]
0x180045f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f64  mov     ebx, eax
0x180045f66  cmp     eax, 80030002h
0x180045f6b  jz      short loc_180045F04
0x180045f6d  test    eax, eax
0x180045f6f  jns     short loc_180045F8A
0x180045f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180045f78  cmp     rcx, r13
0x180045f7b  jz      short loc_180045F49
0x180045f7d  test    byte ptr [rcx+1Ch], 2
0x180045f81  jz      short loc_180045F49
0x180045f83  mov     edx, 137h
0x180045f88  jmp     short loc_180045F31
0x180045f8a  mov     rdx, [rsp+290h+pv]; struct _ITEMIDLIST *
0x180045f8f  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x180045f94  lea     r8, [rsp+290h+psz]; unsigned __int16 *
0x180045f99  mov     rdx, rax; struct CONTENTITEM *
0x180045f9c  call    ?_Name@CContentFolder@@QEAAPEBGPEFBUCONTENTITEM@@PEAGI@Z; CContentFolder::_Name(CONTENTITEM const *,ushort *,uint)
0x180045fa1  lea     rdx, [rsp+290h+ppwsz]; ppwsz
0x180045fa6  lea     rcx, [rsp+290h+psz]; psz
0x180045fab  call    cs:__imp_SHStrDupW
0x180045fb1  mov     ebx, eax
0x180045fb3  test    eax, eax
0x180045fb5  jns     short loc_180045FE6
0x180045fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180045fbe  cmp     rcx, r13
0x180045fc1  jz      short loc_180045F49
0x180045fc3  test    byte ptr [rcx+1Ch], 2
0x180045fc7  jz      short loc_180045F49
0x180045fc9  mov     edx, 138h
0x180045fce  mov     r9d, eax
0x180045fd1  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180045fd8  mov     rcx, [rcx+10h]
0x180045fdc  call    WPP_SF_d
0x180045fe1  jmp     loc_180045F49
0x180045fe6  mov     rcx, [rsp+290h+pv]; pv
0x180045feb  call    cs:__imp_CoTaskMemFree
0x180045ff1  test    rdi, rdi
0x180045ff4  jz      loc_1800460CF
0x180045ffa  mov     rax, [rsp+290h+ppwsz]
0x180045fff  mov     [rsp+290h+ppwsz], 0
0x180046008  mov     [rdi], rax
0x18004600b  jmp     loc_1800460CF
0x180046010  mov     dword ptr [r14+90h], 1
0x18004601b  mov     [rsp+290h+var_260], 0
0x180046024  lea     rdx, [rsp+290h+pv]
0x180046029  mov     [rsp+290h+var_268], rdx
0x18004602e  mov     [rsp+290h+var_270], 0
0x180046037  mov     r9, rsi
0x18004603a  xor     r8d, r8d
0x18004603d  xor     edx, edx
0x18004603f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046044  mov     ebx, eax
0x180046046  mov     dword ptr [r14+90h], 0
0x180046051  test    eax, eax
0x180046053  js      short loc_18004605C
0x180046055  mov     ebx, 80030050h
0x18004605a  jmp     short loc_180046099
0x18004605c  cmp     eax, 80070002h
0x180046061  jnz     short loc_18004606A
0x180046063  xor     ebx, ebx
0x180046065  jmp     loc_180045F06
0x18004606a  mov     rcx, cs:WPP_GLOBAL_Control
0x180046071  cmp     rcx, r13
0x180046074  jz      short loc_180046099
0x180046076  test    byte ptr [rcx+1Ch], 2
0x18004607a  jz      short loc_180046099
0x18004607c  mov     edx, 139h
0x180046081  mov     dword ptr [rsp+290h+var_270], eax
0x180046085  mov     r9, rsi
0x180046088  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x18004608f  mov     rcx, [rcx+10h]
0x180046093  call    WPP_SF_Sd
0x180046098  nop
0x180046099  mov     rcx, [rsp+290h+pv]; pv
0x18004609e  call    cs:__imp_CoTaskMemFree
0x1800460a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800460ab  cmp     rcx, r13
0x1800460ae  jz      short loc_1800460CF
0x1800460b0  test    byte ptr [rcx+1Ch], 2
0x1800460b4  jz      short loc_1800460CF
0x1800460b6  mov     edx, 13Ah
0x1800460bb  mov     r9d, ebx
0x1800460be  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800460c5  mov     rcx, [rcx+10h]
0x1800460c9  call    WPP_SF_d
0x1800460ce  nop
0x1800460cf  mov     rcx, [rsp+290h+ppwsz]; pv
0x1800460d4  call    cs:__imp_CoTaskMemFree
0x1800460da  mov     eax, ebx
0x1800460dc  mov     rcx, [rbp+190h+var_30]
0x1800460e3  xor     rcx, rsp; StackCookie
0x1800460e6  call    __security_check_cookie
0x1800460eb  mov     rbx, [rsp+290h+arg_10]
0x1800460f3  add     rsp, 270h
0x1800460fa  pop     r14
0x1800460fc  pop     r13
0x1800460fe  pop     rdi
0x1800460ff  pop     rsi
0x180046100  pop     rbp
0x180046101  retn
```
