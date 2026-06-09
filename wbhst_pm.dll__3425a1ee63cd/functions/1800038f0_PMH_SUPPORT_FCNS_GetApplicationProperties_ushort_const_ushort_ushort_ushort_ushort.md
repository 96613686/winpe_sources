# PMH_SUPPORT_FCNS::GetApplicationProperties(ushort const *,ushort * *,ushort * *,ushort * *,ushort * *)

- ea: `0x1800038f0`
- end: `0x180003b76`
- name: `?GetApplicationProperties@PMH_SUPPORT_FCNS@@UEAAJPEBGPEAPEAG111@Z`
- size: `646`
- prototype: `__int64 __fastcall(PMH_SUPPORT_FCNS *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800038f0`
- `0x1800042e0`
- `0x1800045fc`
- `0x180004842`
- `0x180004880`
- `0x180005010`

## import_xrefs

- `msvcrt!_ultow` at `0x180003a8b`
- `msvcrt!_ultow` at `0x180003a8b`
- `OLEAUT32!__imp_SysAllocString` at `0x180003a46`
- `OLEAUT32!__imp_SysAllocString` at `0x180003a98`
- `OLEAUT32!__imp_SysAllocString` at `0x180003ab2`
- `OLEAUT32!__imp_SysAllocString` at `0x180003ae7`
- `OLEAUT32!__imp_SysAllocString` at `0x180003a46`
- `OLEAUT32!__imp_SysAllocString` at `0x180003a98`
- `OLEAUT32!__imp_SysAllocString` at `0x180003ab2`
- `OLEAUT32!__imp_SysAllocString` at `0x180003ae7`
- `OLEAUT32!__imp_SysFreeString` at `0x180003afd`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b08`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b14`
- `OLEAUT32!__imp_SysFreeString` at `0x180003afd`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b08`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b14`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003a30`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003a30`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003b40`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003b40`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003b4b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003b4b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000399b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000399b`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800039e5`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800039e5`

## pseudocode

```c
__int64 __fastcall PMH_SUPPORT_FCNS::GetApplicationProperties(
        PMH_SUPPORT_FCNS *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6)
{
  unsigned __int16 *v8; // rdi
  OLECHAR *v9; // rsi
  OLECHAR *v10; // r14
  BSTR v11; // r12
  __int64 v12; // rcx
  int ApplicationSiteName; // ebx
  __int64 v14; // rcx
  OLECHAR *v15; // rcx
  unsigned int Value; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int16 **v19; // [rsp+38h] [rbp-C8h]
  unsigned __int16 **v20; // [rsp+40h] [rbp-C0h]
  unsigned __int16 **v21; // [rsp+48h] [rbp-B8h]
  unsigned __int16 **v22; // [rsp+50h] [rbp-B0h]
  _BYTE v23[32]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR *v24; // [rsp+78h] [rbp-88h]
  int v25; // [rsp+80h] [rbp-80h]
  __int16 v26; // [rsp+84h] [rbp-7Ch]
  _BYTE v27[32]; // [rsp+88h] [rbp-78h] BYREF
  OLECHAR *psz; // [rsp+A8h] [rbp-58h]
  int v29; // [rsp+B0h] [rbp-50h]
  int v30; // [rsp+B8h] [rbp-48h]
  char v31; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v32[255]; // [rsp+C1h] [rbp-3Fh] BYREF
  wchar_t Buffer[16]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v34[256]; // [rsp+1E0h] [rbp+E0h] BYREF

  v20 = a5;
  v19 = a3;
  v21 = a6;
  v22 = a4;
  memset_0(v32, 0, sizeof(v32));
  v31 = 0;
  v24 = (OLECHAR *)&v31;
  v25 = 256;
  v26 = 256;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  memset_0(v34, 0, sizeof(v34));
  STRU::STRU((STRU *)v27, v34, 0x100u);
  v12 = *((_QWORD *)this + 6);
  v18 = v29;
  Value = 0;
  ApplicationSiteName = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, OLECHAR *, int *, unsigned int *))(*(_QWORD *)v12 + 16LL))(
                          v12,
                          a2,
                          psz,
                          &v18,
                          &Value);
  if ( ApplicationSiteName == -2147024774 )
  {
    ApplicationSiteName = STRU::Resize((STRU *)v27, 2 * v18);
    if ( ApplicationSiteName < 0 )
      goto LABEL_20;
    v14 = *((_QWORD *)this + 6);
    v18 = v29;
    ApplicationSiteName = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, OLECHAR *, int *, unsigned int *))(*(_QWORD *)v14 + 16LL))(
                            v14,
                            a2,
                            psz,
                            &v18,
                            &Value);
  }
  if ( ApplicationSiteName >= 0 )
  {
    STRU::SyncWithBuffer((STRU *)v27);
    v15 = L"/";
    if ( v30 )
      v15 = psz;
    v8 = SysAllocString(v15);
    if ( v8 )
    {
      ApplicationSiteName = GetApplicationSiteName(
                              *((struct INativeConfigurationSystem **)this + 4),
                              Value,
                              (struct BUFFER *)v23);
      if ( ApplicationSiteName >= 0 )
      {
        _ultow(Value, Buffer, 10);
        v10 = SysAllocString(Buffer);
        if ( v10 )
        {
          v9 = SysAllocString(v24);
          if ( v9 )
          {
            ApplicationSiteName = MapPath(
                                    *((struct INativeConfigurationSystem **)this + 4),
                                    Value,
                                    v8,
                                    (struct BUFFER *)v23);
            if ( ApplicationSiteName >= 0 )
            {
              v11 = SysAllocString(v24);
              if ( v11 )
                goto LABEL_20;
              ApplicationSiteName = -2147024888;
            }
            SysFreeString(v9);
            v9 = 0;
          }
          else
          {
            ApplicationSiteName = -2147024888;
          }
          SysFreeString(v10);
          v10 = 0;
        }
        else
        {
          ApplicationSiteName = -2147024888;
        }
      }
      SysFreeString(v8);
      v8 = 0;
      goto LABEL_20;
    }
    ApplicationSiteName = -2147024888;
  }
LABEL_20:
  *v19 = v8;
  *v20 = v9;
  *v21 = v10;
  *v22 = v11;
  STRU::~STRU((STRU *)v27);
  BUFFER::~BUFFER((BUFFER *)v23);
  return (unsigned int)ApplicationSiteName;
}

```

## disassembly

```asm
0x1800038f0  push    rbp
0x1800038f2  push    rbx
0x1800038f3  push    rsi
0x1800038f4  push    rdi
0x1800038f5  push    r12
0x1800038f7  push    r13
0x1800038f9  push    r14
0x1800038fb  push    r15
0x1800038fd  lea     rbp, [rsp-2F8h]
0x180003905  sub     rsp, 3F8h
0x18000390c  mov     rax, cs:__security_cookie
0x180003913  xor     rax, rsp
0x180003916  mov     [rbp+330h+var_50], rax
0x18000391d  mov     rax, [rbp+330h+arg_20]
0x180003924  mov     r13, rdx
0x180003927  mov     [rsp+430h+var_3F0], rax
0x18000392c  mov     r15, rcx
0x18000392f  mov     rax, [rbp+330h+arg_28]
0x180003936  lea     rcx, [rbp+330h+var_36F]; void *
0x18000393a  mov     [rsp+430h+var_3F8], r8
0x18000393f  xor     edx, edx; Val
0x180003941  mov     r8d, 0FFh; Size
0x180003947  mov     [rsp+430h+var_3E8], rax
0x18000394c  mov     [rsp+430h+var_3E0], r9
0x180003951  call    memset_0
0x180003956  lea     rax, [rbp+330h+var_370]
0x18000395a  mov     [rbp+330h+var_370], 0
0x18000395e  mov     ebx, 100h
0x180003963  mov     [rsp+430h+var_3B8], rax
0x180003968  xor     edx, edx; Val
0x18000396a  mov     [rbp+330h+var_3B0], ebx
0x18000396d  mov     r8d, 200h; Size
0x180003973  mov     [rbp+330h+var_3AC], bx
0x180003977  lea     rcx, [rbp+330h+var_250]; void *
0x18000397e  xor     edi, edi
0x180003980  xor     esi, esi
0x180003982  xor     r14d, r14d
0x180003985  xor     r12d, r12d
0x180003988  call    memset_0
0x18000398d  mov     r8d, ebx
0x180003990  lea     rdx, [rbp+330h+var_250]
0x180003997  lea     rcx, [rbp+330h+var_3A8]
0x18000399b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800039a1  mov     eax, [rbp+330h+var_380]
0x1800039a4  lea     rdx, [rsp+430h+Value]
0x1800039a9  mov     rcx, [r15+30h]
0x1800039ad  lea     r9, [rsp+430h+var_3FC]
0x1800039b2  mov     r8, [rbp+330h+psz]
0x1800039b6  mov     [rsp+430h+var_3FC], eax
0x1800039ba  mov     [rsp+430h+Value], esi
0x1800039be  mov     rax, [rcx]
0x1800039c1  mov     [rsp+430h+var_410], rdx
0x1800039c6  mov     rdx, r13
0x1800039c9  mov     rax, [rax+10h]
0x1800039cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d2  mov     ebx, eax
0x1800039d4  cmp     eax, 8007007Ah
0x1800039d9  jnz     short loc_180003A24
0x1800039db  mov     edx, [rsp+430h+var_3FC]
0x1800039df  lea     rcx, [rbp+330h+var_3A8]
0x1800039e3  add     edx, edx
0x1800039e5  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x1800039eb  mov     ebx, eax
0x1800039ed  test    eax, eax
0x1800039ef  js      loc_180003B1C
0x1800039f5  mov     eax, [rbp+330h+var_380]
0x1800039f8  lea     rdx, [rsp+430h+Value]
0x1800039fd  mov     rcx, [r15+30h]
0x180003a01  lea     r9, [rsp+430h+var_3FC]
0x180003a06  mov     r8, [rbp+330h+psz]
0x180003a0a  mov     [rsp+430h+var_3FC], eax
0x180003a0e  mov     [rsp+430h+var_410], rdx
0x180003a13  mov     rdx, r13
0x180003a16  mov     rax, [rcx]
0x180003a19  mov     rax, [rax+10h]
0x180003a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a22  mov     ebx, eax
0x180003a24  test    ebx, ebx
0x180003a26  js      loc_180003B1C
0x180003a2c  lea     rcx, [rbp+330h+var_3A8]
0x180003a30  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180003a36  lea     rcx, asc_1800066D0; "/"
0x180003a3d  cmp     [rbp+330h+var_378], esi
0x180003a40  jz      short loc_180003A46
0x180003a42  mov     rcx, [rbp+330h+psz]; psz
0x180003a46  call    cs:__imp_SysAllocString
0x180003a4c  mov     rdi, rax
0x180003a4f  test    rax, rax
0x180003a52  jnz     short loc_180003A5E
0x180003a54  mov     ebx, 80070008h
0x180003a59  jmp     loc_180003B1C
0x180003a5e  mov     edx, [rsp+430h+Value]; unsigned int
0x180003a62  lea     r8, [rsp+430h+var_3D8]; struct BUFFER *
0x180003a67  mov     rcx, [r15+20h]; struct INativeConfigurationSystem *
0x180003a6b  call    ?GetApplicationSiteName@@YAJPEAVINativeConfigurationSystem@@KPEAVBUFFER@@@Z; GetApplicationSiteName(INativeConfigurationSystem *,ulong,BUFFER *)
0x180003a70  mov     ebx, eax
0x180003a72  test    eax, eax
0x180003a74  js      loc_180003B11
0x180003a7a  mov     ecx, [rsp+430h+Value]; Value
0x180003a7e  lea     rdx, [rbp+330h+Buffer]; Buffer
0x180003a85  mov     r8d, 0Ah; Radix
0x180003a8b  call    cs:__imp__ultow
0x180003a91  lea     rcx, [rbp+330h+Buffer]; psz
0x180003a98  call    cs:__imp_SysAllocString
0x180003a9e  mov     r14, rax
0x180003aa1  test    rax, rax
0x180003aa4  jnz     short loc_180003AAD
0x180003aa6  mov     ebx, 80070008h
0x180003aab  jmp     short loc_180003B11
0x180003aad  mov     rcx, [rsp+430h+var_3B8]; psz
0x180003ab2  call    cs:__imp_SysAllocString
0x180003ab8  mov     rsi, rax
0x180003abb  test    rax, rax
0x180003abe  jnz     short loc_180003AC7
0x180003ac0  mov     ebx, 80070008h
0x180003ac5  jmp     short loc_180003B05
0x180003ac7  mov     edx, [rsp+430h+Value]; unsigned int
0x180003acb  lea     r9, [rsp+430h+var_3D8]; struct BUFFER *
0x180003ad0  mov     rcx, [r15+20h]; struct INativeConfigurationSystem *
0x180003ad4  mov     r8, rdi; unsigned __int16 *
0x180003ad7  call    ?MapPath@@YAJPEAVINativeConfigurationSystem@@KPEBGPEAVBUFFER@@@Z; MapPath(INativeConfigurationSystem *,ulong,ushort const *,BUFFER *)
0x180003adc  mov     ebx, eax
0x180003ade  test    eax, eax
0x180003ae0  js      short loc_180003AFA
0x180003ae2  mov     rcx, [rsp+430h+var_3B8]; psz
0x180003ae7  call    cs:__imp_SysAllocString
0x180003aed  mov     r12, rax
0x180003af0  test    rax, rax
0x180003af3  jnz     short loc_180003B1C
0x180003af5  mov     ebx, 80070008h
0x180003afa  mov     rcx, rsi; bstrString
0x180003afd  call    cs:__imp_SysFreeString
0x180003b03  xor     esi, esi
0x180003b05  mov     rcx, r14; bstrString
0x180003b08  call    cs:__imp_SysFreeString
0x180003b0e  xor     r14d, r14d
0x180003b11  mov     rcx, rdi; bstrString
0x180003b14  call    cs:__imp_SysFreeString
0x180003b1a  xor     edi, edi
0x180003b1c  mov     rax, [rsp+430h+var_3F8]
0x180003b21  lea     rcx, [rbp+330h+var_3A8]
0x180003b25  mov     [rax], rdi
0x180003b28  mov     rax, [rsp+430h+var_3F0]
0x180003b2d  mov     [rax], rsi
0x180003b30  mov     rax, [rsp+430h+var_3E8]
0x180003b35  mov     [rax], r14
0x180003b38  mov     rax, [rsp+430h+var_3E0]
0x180003b3d  mov     [rax], r12
0x180003b40  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003b46  lea     rcx, [rsp+430h+var_3D8]
0x180003b4b  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003b51  mov     eax, ebx
0x180003b53  mov     rcx, [rbp+330h+var_50]
0x180003b5a  xor     rcx, rsp; StackCookie
0x180003b5d  call    __security_check_cookie
0x180003b62  add     rsp, 3F8h
0x180003b69  pop     r15
0x180003b6b  pop     r14
0x180003b6d  pop     r13
0x180003b6f  pop     r12
0x180003b71  pop     rdi
0x180003b72  pop     rsi
0x180003b73  pop     rbx
0x180003b74  pop     rbp
0x180003b75  retn
```
