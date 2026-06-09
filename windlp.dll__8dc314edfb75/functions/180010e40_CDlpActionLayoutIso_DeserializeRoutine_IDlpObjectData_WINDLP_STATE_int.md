# CDlpActionLayoutIso::DeserializeRoutine(IDlpObjectData *,WINDLP_STATE,int *)

- ea: `0x180010e40`
- end: `0x180011164`
- name: `?DeserializeRoutine@CDlpActionLayoutIso@@EEAAJPEAVIDlpObjectData@@W4WINDLP_STATE@@PEAH@Z`
- size: `804`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x18000aba4`
- `0x180010e40`
- `0x180012f5c`
- `0x18001fd60`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800110f2`
- `OLEAUT32!__imp_SysFreeString` at `0x180011105`
- `OLEAUT32!__imp_SysFreeString` at `0x180011118`
- `OLEAUT32!__imp_SysFreeString` at `0x18001112b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001113e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800110f2`
- `OLEAUT32!__imp_SysFreeString` at `0x180011105`
- `OLEAUT32!__imp_SysFreeString` at `0x180011118`
- `OLEAUT32!__imp_SysFreeString` at `0x18001112b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001113e`

## string_xrefs

- `0x180010f56`: `LayoutPath`
- `0x180010eb9`: `CDlpActionLayoutIso::DeserializeRoutine`
- `0x180010f18`: `IsoPath`
- `0x180010f94`: `BootFilePath`
- `0x180010fe4`: `EfiBootFilePath`

## pseudocode

```c
__int64 __fastcall CDlpActionLayoutIso::DeserializeRoutine(_QWORD *a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rsi
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v16; // [rsp+20h] [rbp-69h]
  int v17; // [rsp+28h] [rbp-61h]
  BSTR v18; // [rsp+30h] [rbp-59h] BYREF
  BSTR v19; // [rsp+38h] [rbp-51h] BYREF
  BSTR v20; // [rsp+40h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-41h] BYREF
  BSTR v22[2]; // [rsp+50h] [rbp-39h] BYREF
  __int128 v23; // [rsp+60h] [rbp-29h] BYREF
  BSTR v24; // [rsp+70h] [rbp-19h]
  BSTR v25; // [rsp+78h] [rbp-11h]
  __int64 v26; // [rsp+80h] [rbp-9h]
  BSTR v27; // [rsp+88h] [rbp-1h]
  BSTR v28; // [rsp+90h] [rbp+7h]
  __int64 v29; // [rsp+98h] [rbp+Fh]

  v22[0] = 0;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  bstrString = 0;
  memset_0(&v23, 0, 0x40u);
  if ( a2 )
  {
    if ( a4 )
    {
      v11 = a2 + 8;
      v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v11 + 16LL))(v11, L"IsoPath", v22);
      v7 = v12;
      if ( v12 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v11 + 16LL))(
                v11,
                L"LayoutPath",
                &v20);
        v7 = v13;
        if ( v13 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v11 + 16LL))(
                 v11,
                 L"BootFilePath",
                 &v19);
          if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147023728 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v11 + 16LL))(
                   v11,
                   L"EfiBootFilePath",
                   &v18);
            if ( ((v7 + 0x80000000) & 0x80000000) != 0 || v7 == -2147023728 )
            {
              v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, BSTR *))(*(_QWORD *)v11 + 16LL))(
                     v11,
                     L"VolumeLabel",
                     &bstrString);
              if ( ((v7 + 0x80000000) & 0x80000000) != 0 || v7 == -2147023728 )
              {
                v26 = 0;
                v29 = 0;
                v23 = WINDLP_ACTION_LAYOUTISO;
                v24 = v20;
                v25 = v22[0];
                v27 = v19;
                v28 = v18;
                v14 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *, __int64))(*a1 + 32LL))(a1, &v23, 64);
                v7 = v14;
                if ( v14 >= 0 )
                {
                  *a4 = 0;
                  goto LABEL_32;
                }
                v8 = a1[11];
                if ( !v8 )
                  goto LABEL_32;
                v17 = v14;
                v16 = 274;
              }
              else
              {
                v8 = a1[11];
                if ( !v8 )
                  goto LABEL_32;
                v17 = v7;
                v16 = 263;
              }
            }
            else
            {
              v8 = a1[11];
              if ( !v8 )
                goto LABEL_32;
              v17 = v7;
              v16 = 259;
            }
          }
          else
          {
            v8 = a1[11];
            if ( !v8 )
              goto LABEL_32;
            v17 = v7;
            v16 = 255;
          }
        }
        else
        {
          v8 = a1[11];
          if ( !v8 )
            goto LABEL_32;
          v17 = v13;
          v16 = 251;
        }
      }
      else
      {
        v8 = a1[11];
        if ( !v8 )
          goto LABEL_32;
        v17 = v12;
        v16 = 250;
      }
    }
    else
    {
      v7 = -2147024809;
      v8 = a1[11];
      if ( !v8 )
        goto LABEL_32;
      v17 = -2147024809;
      v16 = 248;
    }
  }
  else
  {
    v7 = -2147024809;
    v8 = a1[11];
    if ( !v8 )
      goto LABEL_32;
    v17 = -2147024809;
    v16 = 246;
  }
  v9 = CDlpLogT<CEmptyType>::DlpLogFormat(
         v8,
         4,
         L"%s(%d): Result = 0x%X",
         L"CDlpActionLayoutIso::DeserializeRoutine",
         v16,
         v17);
  v10 = (unsigned int)v9;
  if ( v9 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
LABEL_32:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v18 )
  {
    SysFreeString(v18);
    v18 = 0;
  }
  if ( v19 )
  {
    SysFreeString(v19);
    v19 = 0;
  }
  if ( v20 )
  {
    SysFreeString(v20);
    v20 = 0;
  }
  if ( v22[0] )
    SysFreeString(v22[0]);
  return v7;
}

```

## disassembly

```asm
0x180010e40  push    rbp
0x180010e42  push    rbx
0x180010e43  push    rsi
0x180010e44  push    rdi
0x180010e45  push    r13
0x180010e47  push    r14
0x180010e49  push    r15
0x180010e4b  lea     rbp, [rsp-27h]
0x180010e50  sub     rsp, 0B0h
0x180010e57  mov     rax, cs:__security_cookie
0x180010e5e  xor     rax, rsp
0x180010e61  mov     [rbp+57h+var_40], rax
0x180010e65  mov     r14, r9
0x180010e68  mov     rsi, rdx
0x180010e6b  mov     rdi, rcx
0x180010e6e  xor     r15d, r15d
0x180010e71  mov     [rbp+57h+var_90], r15
0x180010e75  mov     [rbp+57h+var_A0], r15
0x180010e79  mov     [rbp+57h+var_A8], r15
0x180010e7d  mov     [rbp+57h+var_B0], r15
0x180010e81  mov     [rbp+57h+bstrString], r15
0x180010e85  xor     edx, edx; Val
0x180010e87  lea     r8d, [r15+40h]; Size
0x180010e8b  lea     rcx, [rbp+57h+var_80]; void *
0x180010e8f  call    memset_0
0x180010e94  test    rsi, rsi
0x180010e97  jnz     short loc_180010EE6
0x180010e99  mov     eax, 80070057h
0x180010e9e  mov     ebx, eax
0x180010ea0  mov     rcx, [rdi+58h]
0x180010ea4  test    rcx, rcx
0x180010ea7  jz      loc_1800110E1
0x180010ead  mov     [rsp+0E0h+var_B8], eax
0x180010eb1  mov     [rsp+0E0h+var_C0], 0F6h
0x180010eb9  lea     r9, aCdlpactionlayo_34; "CDlpActionLayoutIso::DeserializeRoutine"
0x180010ec0  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180010ec7  mov     edx, 4
0x180010ecc  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180010ed1  test    eax, eax
0x180010ed3  mov     ecx, eax
0x180010ed5  jns     short loc_180010EDC
0x180010ed7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180010edc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180010ee1  jmp     loc_1800110E1
0x180010ee6  test    r14, r14
0x180010ee9  jnz     short loc_180010F0D
0x180010eeb  mov     eax, 80070057h
0x180010ef0  mov     ebx, eax
0x180010ef2  mov     rcx, [rdi+58h]
0x180010ef6  test    rcx, rcx
0x180010ef9  jz      loc_1800110E1
0x180010eff  mov     [rsp+0E0h+var_B8], eax
0x180010f03  mov     [rsp+0E0h+var_C0], 0F8h
0x180010f0b  jmp     short loc_180010EB9
0x180010f0d  add     rsi, 8
0x180010f11  mov     rax, [rsi]
0x180010f14  lea     r8, [rbp+57h+var_90]
0x180010f18  lea     rdx, aIsopath; "IsoPath"
0x180010f1f  mov     rcx, rsi
0x180010f22  mov     rax, [rax+10h]
0x180010f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f2b  mov     ebx, eax
0x180010f2d  test    eax, eax
0x180010f2f  jns     short loc_180010F4F
0x180010f31  mov     rcx, [rdi+58h]
0x180010f35  test    rcx, rcx
0x180010f38  jz      loc_1800110E1
0x180010f3e  mov     [rsp+0E0h+var_B8], eax
0x180010f42  mov     [rsp+0E0h+var_C0], 0FAh
0x180010f4a  jmp     loc_180010EB9
0x180010f4f  mov     rax, [rsi]
0x180010f52  lea     r8, [rbp+57h+var_A0]
0x180010f56  lea     rdx, aLayoutpath; "LayoutPath"
0x180010f5d  mov     rcx, rsi
0x180010f60  mov     rax, [rax+10h]
0x180010f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f69  mov     ebx, eax
0x180010f6b  test    eax, eax
0x180010f6d  jns     short loc_180010F8D
0x180010f6f  mov     rcx, [rdi+58h]
0x180010f73  test    rcx, rcx
0x180010f76  jz      loc_1800110E1
0x180010f7c  mov     [rsp+0E0h+var_B8], eax
0x180010f80  mov     [rsp+0E0h+var_C0], 0FBh
0x180010f88  jmp     loc_180010EB9
0x180010f8d  mov     rax, [rsi]
0x180010f90  lea     r8, [rbp+57h+var_A8]
0x180010f94  lea     rdx, aBootfilepath; "BootFilePath"
0x180010f9b  mov     rcx, rsi
0x180010f9e  mov     rax, [rax+10h]
0x180010fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fa7  mov     ebx, eax
0x180010fa9  mov     r13d, 80000000h
0x180010faf  add     eax, r13d
0x180010fb2  test    r13d, eax
0x180010fb5  jnz     short loc_180010FDD
0x180010fb7  cmp     ebx, 80070490h
0x180010fbd  jz      short loc_180010FDD
0x180010fbf  mov     rcx, [rdi+58h]
0x180010fc3  test    rcx, rcx
0x180010fc6  jz      loc_1800110E1
0x180010fcc  mov     [rsp+0E0h+var_B8], ebx
0x180010fd0  mov     [rsp+0E0h+var_C0], 0FFh
0x180010fd8  jmp     loc_180010EB9
0x180010fdd  mov     rax, [rsi]
0x180010fe0  lea     r8, [rbp+57h+var_B0]
0x180010fe4  lea     rdx, aEfibootfilepat; "EfiBootFilePath"
0x180010feb  mov     rcx, rsi
0x180010fee  mov     rax, [rax+10h]
0x180010ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ff7  mov     ebx, eax
0x180010ff9  add     eax, r13d
0x180010ffc  test    r13d, eax
0x180010fff  jnz     short loc_180011027
0x180011001  cmp     ebx, 80070490h
0x180011007  jz      short loc_180011027
0x180011009  mov     rcx, [rdi+58h]
0x18001100d  test    rcx, rcx
0x180011010  jz      loc_1800110E1
0x180011016  mov     [rsp+0E0h+var_B8], ebx
0x18001101a  mov     [rsp+0E0h+var_C0], 103h
0x180011022  jmp     loc_180010EB9
0x180011027  mov     rax, [rsi]
0x18001102a  lea     r8, [rbp+57h+bstrString]
0x18001102e  lea     rdx, aVolumelabel; "VolumeLabel"
0x180011035  mov     rcx, rsi
0x180011038  mov     rax, [rax+10h]
0x18001103c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011041  mov     ebx, eax
0x180011043  add     eax, r13d
0x180011046  test    r13d, eax
0x180011049  jnz     short loc_180011071
0x18001104b  cmp     ebx, 80070490h
0x180011051  jz      short loc_180011071
0x180011053  mov     rcx, [rdi+58h]
0x180011057  test    rcx, rcx
0x18001105a  jz      loc_1800110E1
0x180011060  mov     [rsp+0E0h+var_B8], ebx
0x180011064  mov     [rsp+0E0h+var_C0], 107h
0x18001106c  jmp     loc_180010EB9
0x180011071  mov     [rbp+57h+var_60], r15
0x180011075  mov     [rbp+57h+var_48], r15
0x180011079  movups  xmm0, cs:WINDLP_ACTION_LAYOUTISO
0x180011080  movdqu  [rbp+57h+var_80], xmm0
0x180011085  mov     rax, [rbp+57h+var_A0]
0x180011089  mov     [rbp+57h+var_70], rax
0x18001108d  mov     rax, [rbp+57h+var_90]
0x180011091  mov     [rbp+57h+var_68], rax
0x180011095  mov     rax, [rbp+57h+var_A8]
0x180011099  mov     [rbp+57h+var_58], rax
0x18001109d  mov     rax, [rbp+57h+var_B0]
0x1800110a1  mov     [rbp+57h+var_50], rax
0x1800110a5  mov     rax, [rdi]
0x1800110a8  mov     r8d, 40h ; '@'
0x1800110ae  lea     rdx, [rbp+57h+var_80]
0x1800110b2  mov     rcx, rdi
0x1800110b5  mov     rax, [rax+20h]
0x1800110b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110be  mov     ebx, eax
0x1800110c0  test    eax, eax
0x1800110c2  jns     short loc_1800110DE
0x1800110c4  mov     rcx, [rdi+58h]
0x1800110c8  test    rcx, rcx
0x1800110cb  jz      short loc_1800110E1
0x1800110cd  mov     [rsp+0E0h+var_B8], eax
0x1800110d1  mov     [rsp+0E0h+var_C0], 112h
0x1800110d9  jmp     loc_180010EB9
0x1800110de  mov     [r14], r15d
0x1800110e1  mov     ecx, ebx
0x1800110e3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800110e8  nop
0x1800110e9  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800110ed  test    rcx, rcx
0x1800110f0  jz      short loc_1800110FC
0x1800110f2  call    cs:__imp_SysFreeString
0x1800110f8  mov     [rbp+57h+bstrString], r15
0x1800110fc  mov     rcx, [rbp+57h+var_B0]; bstrString
0x180011100  test    rcx, rcx
0x180011103  jz      short loc_18001110F
0x180011105  call    cs:__imp_SysFreeString
0x18001110b  mov     [rbp+57h+var_B0], r15
0x18001110f  mov     rcx, [rbp+57h+var_A8]; bstrString
0x180011113  test    rcx, rcx
0x180011116  jz      short loc_180011122
0x180011118  call    cs:__imp_SysFreeString
0x18001111e  mov     [rbp+57h+var_A8], r15
0x180011122  mov     rcx, [rbp+57h+var_A0]; bstrString
0x180011126  test    rcx, rcx
0x180011129  jz      short loc_180011135
0x18001112b  call    cs:__imp_SysFreeString
0x180011131  mov     [rbp+57h+var_A0], r15
0x180011135  mov     rcx, [rbp+57h+var_90]; bstrString
0x180011139  test    rcx, rcx
0x18001113c  jz      short loc_180011144
0x18001113e  call    cs:__imp_SysFreeString
0x180011144  mov     eax, ebx
0x180011146  mov     rcx, [rbp+57h+var_40]
0x18001114a  xor     rcx, rsp; StackCookie
0x18001114d  call    __security_check_cookie
0x180011152  add     rsp, 0B0h
0x180011159  pop     r15
0x18001115b  pop     r14
0x18001115d  pop     r13
0x18001115f  pop     rdi
0x180011160  pop     rsi
0x180011161  pop     rbx
0x180011162  pop     rbp
0x180011163  retn
```
