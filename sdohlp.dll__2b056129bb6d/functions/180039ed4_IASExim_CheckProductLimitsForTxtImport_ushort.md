# IASExim::CheckProductLimitsForTxtImport(ushort *)

- ea: `0x180039ed4`
- end: `0x18003a15c`
- name: `?CheckProductLimitsForTxtImport@IASExim@@AEAAJPEAG@Z`
- size: `648`
- prototype: `__int64 __fastcall(IASExim *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18003cdd4`

## callees

- `0x180001a6c`
- `0x180024e34`
- `0x18002cca4`
- `0x180038828`
- `0x1800388a0`
- `0x180038ad0`
- `0x180038cb8`
- `0x180038f78`
- `0x180039740`
- `0x18003997c`
- `0x180039ed4`
- `0x18003e744`
- `0x18003f548`
- `0x18003f750`
- `0x180042a80`
- `0x180055030`

## import_xrefs

- `iassvcs!IASGetProductLimits` at `0x180039f0b`
- `iassvcs!IASGetProductLimits` at `0x180039f0b`

## string_xrefs

- `0x18003a0a3`: `Number of server groups in the config being imported is more than what is allowed by license.`
- `0x18003a0dd`: `Number of clients in the config being imported is more than what is allowed by license.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall IASExim::CheckProductLimitsForTxtImport(IASExim *this, unsigned __int16 *a2)
{
  __int64 result; // rax
  AltCodeConvert *v4; // rax
  unsigned __int64 v5; // rdx
  const struct AltCodeConvert *v6; // rbx
  const struct std::locale *v7; // rax
  unsigned int v8; // ebx
  unsigned int v9; // edi
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // ebx
  _BYTE v17[8]; // [rsp+20h] [rbp-E0h] BYREF
  AltCodeConvert *v18; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v19[34]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v21; // [rsp+148h] [rbp+48h]
  _WORD v22[8]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v23; // [rsp+160h] [rbp+60h]
  __int64 v24; // [rsp+168h] [rbp+68h]

  v20 = 0;
  v21 = 0;
  result = IASGetProductLimits(0, &v20);
  if ( !(_DWORD)result )
  {
    v4 = (AltCodeConvert *)operator new(0x40u);
    v18 = v4;
    if ( v4 )
      v6 = AltCodeConvert::AltCodeConvert(v4, v5);
    else
      v6 = 0;
    v7 = std::locale::classic();
    std::locale::locale((std::locale *)v17, v7, v6);
    std::basic_ifstream<unsigned short>::basic_ifstream<unsigned short>(v19);
    std::basic_ios<unsigned short>::imbue((char *)v19 + *(int *)(v19[0] + 4LL), &v18, v17);
    std::locale::~locale((std::locale *)&v18);
    std::basic_ifstream<unsigned short>::open(v19, a2);
    v24 = 7;
    v23 = 0;
    v22[0] = 0;
    v8 = 0;
    v9 = 0;
    while ( 1 )
    {
      v10 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v19, v22);
      v12 = v10 + *(int *)(*(_QWORD *)v10 + 4LL);
      if ( (*(_BYTE *)(v12 + 16) & 6) != 0 || !v12 )
        break;
      if ( !(unsigned __int8)std::operator==<unsigned short>(v22, L"=================================================") )
      {
        if ( (unsigned __int8)std::operator==<unsigned short>(v22, L"Client") )
        {
          ++v8;
        }
        else if ( (unsigned __int8)std::operator==<unsigned short>(v22, L"RADIUSServerGroup") )
        {
          ++v9;
        }
        std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v19, v22);
        do
        {
          v13 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v19, v22);
          v14 = v13 + *(int *)(*(_QWORD *)v13 + 4LL);
        }
        while ( (*(_BYTE *)(v14 + 16) & 6) == 0
             && v14
             && !(unsigned __int8)std::operator==<unsigned short>(
                                    v22,
                                    L"=================================================") );
      }
    }
    if ( v9 <= v21 )
    {
      if ( v8 <= (unsigned int)v20 )
      {
        v16 = 0;
        goto LABEL_33;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
LABEL_31:
        v16 = -2147023501;
LABEL_33:
        LOBYTE(v11) = 1;
        std::wstring::_Tidy(v22, v11, 0);
        std::basic_ifstream<unsigned short>::`vbase destructor'(v19);
        std::locale::~locale((std::locale *)v17);
        return v16;
      }
      WppDbgPrint("Number of clients in the config being imported is more than what is allowed by license.");
      v15 = 104;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
        goto LABEL_31;
      }
      WppDbgPrint("Number of server groups in the config being imported is more than what is allowed by license.");
      v15 = 103;
    }
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids, "NPSSDO");
    goto LABEL_31;
  }
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180039ed4  mov     [rsp-8+arg_0], rbx
0x180039ed9  mov     [rsp-8+arg_10], rdi
0x180039ede  push    rbp
0x180039edf  lea     rbp, [rsp-80h]
0x180039ee4  sub     rsp, 180h
0x180039eeb  mov     rax, cs:__security_cookie
0x180039ef2  xor     rax, rsp
0x180039ef5  mov     [rbp+80h+var_10], rax
0x180039ef9  mov     rdi, rdx
0x180039efc  xor     eax, eax
0x180039efe  mov     [rbp+80h+var_40], rax
0x180039f02  mov     [rbp+80h+var_38], eax
0x180039f05  lea     rdx, [rbp+80h+var_40]
0x180039f09  xor     ecx, ecx
0x180039f0b  call    cs:__imp_IASGetProductLimits
0x180039f11  test    eax, eax
0x180039f13  jz      short loc_180039F28
0x180039f15  jle     loc_18003A13B
0x180039f1b  movzx   eax, ax
0x180039f1e  or      eax, 80070000h
0x180039f23  jmp     loc_18003A13B
0x180039f28  mov     ecx, 40h ; '@'; Size
0x180039f2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039f32  mov     [rsp+180h+var_158], rax
0x180039f37  test    rax, rax
0x180039f3a  jz      short loc_180039F49
0x180039f3c  mov     rcx, rax; this
0x180039f3f  call    ??0AltCodeConvert@@QEAA@_K@Z; AltCodeConvert::AltCodeConvert(unsigned __int64)
0x180039f44  mov     rbx, rax
0x180039f47  jmp     short loc_180039F4B
0x180039f49  xor     ebx, ebx
0x180039f4b  call    ?classic@locale@std@@SAAEBV12@XZ; std::locale::classic(void)
0x180039f50  mov     r8, rbx; struct AltCodeConvert *
0x180039f53  mov     rdx, rax; struct std::locale *
0x180039f56  lea     rcx, [rsp+180h+var_160]; this
0x180039f5b  call    ??$?0VAltCodeConvert@@@locale@std@@QEAA@AEBV01@PEBVAltCodeConvert@@@Z; std::locale::locale(std::locale const &,AltCodeConvert const *)
0x180039f60  nop
0x180039f61  lea     rcx, [rsp+180h+var_150]
0x180039f66  call    ??0?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAA@XZ; std::basic_ifstream<ushort>::basic_ifstream<ushort>(void)
0x180039f6b  nop
0x180039f6c  mov     rax, [rsp+180h+var_150]
0x180039f71  movsxd  rcx, dword ptr [rax+4]
0x180039f75  lea     rax, [rsp+180h+var_150]
0x180039f7a  add     rcx, rax
0x180039f7d  lea     r8, [rsp+180h+var_160]
0x180039f82  lea     rdx, [rsp+180h+var_158]
0x180039f87  call    ?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z; std::basic_ios<ushort>::imbue(std::locale const &)
0x180039f8c  lea     rcx, [rsp+180h+var_158]; this
0x180039f91  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x180039f96  mov     rdx, rdi
0x180039f99  lea     rcx, [rsp+180h+var_150]
0x180039f9e  call    ?open@?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAAXPEBGHH@Z; std::basic_ifstream<ushort>::open(ushort const *,int,int)
0x180039fa3  mov     [rbp+80h+var_18], 7
0x180039fab  mov     [rbp+80h+var_20], 0
0x180039fb3  xor     eax, eax
0x180039fb5  mov     [rbp+80h+var_30], ax
0x180039fb9  xor     ebx, ebx
0x180039fbb  xor     edi, edi
0x180039fbd  lea     rdx, [rbp+80h+var_30]
0x180039fc1  lea     rcx, [rsp+180h+var_150]
0x180039fc6  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180039fcb  mov     rcx, [rax]
0x180039fce  movsxd  rcx, dword ptr [rcx+4]
0x180039fd2  add     rcx, rax
0x180039fd5  test    byte ptr [rcx+10h], 6
0x180039fd9  jnz     loc_18003A07C
0x180039fdf  test    rcx, rcx
0x180039fe2  jz      loc_18003A07C
0x180039fe8  lea     rdx, asc_180065180; "======================================="...
0x180039fef  lea     rcx, [rbp+80h+var_30]
0x180039ff3  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180039ff8  test    al, al
0x180039ffa  jnz     short loc_180039FBD
0x180039ffc  lea     rdx, aClient; "Client"
0x18003a003  lea     rcx, [rbp+80h+var_30]
0x18003a007  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x18003a00c  test    al, al
0x18003a00e  jz      short loc_18003A014
0x18003a010  inc     ebx
0x18003a012  jmp     short loc_18003A02A
0x18003a014  lea     rdx, aRadiusservergr; "RADIUSServerGroup"
0x18003a01b  lea     rcx, [rbp+80h+var_30]
0x18003a01f  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x18003a024  test    al, al
0x18003a026  jz      short loc_18003A02A
0x18003a028  inc     edi
0x18003a02a  lea     rdx, [rbp+80h+var_30]
0x18003a02e  lea     rcx, [rsp+180h+var_150]
0x18003a033  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x18003a038  lea     rdx, [rbp+80h+var_30]
0x18003a03c  lea     rcx, [rsp+180h+var_150]
0x18003a041  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x18003a046  mov     rcx, [rax]
0x18003a049  movsxd  rcx, dword ptr [rcx+4]
0x18003a04d  add     rcx, rax
0x18003a050  test    byte ptr [rcx+10h], 6
0x18003a054  jnz     loc_180039FBD
0x18003a05a  test    rcx, rcx
0x18003a05d  jz      loc_180039FBD
0x18003a063  lea     rdx, asc_180065180; "======================================="...
0x18003a06a  lea     rcx, [rbp+80h+var_30]
0x18003a06e  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x18003a073  test    al, al
0x18003a075  jz      short loc_18003A038
0x18003a077  jmp     loc_180039FBD
0x18003a07c  cmp     edi, [rbp+80h+var_38]
0x18003a07f  jbe     short loc_18003A0B6
0x18003a081  lea     rcx, WPP_GLOBAL_Control
0x18003a088  mov     rax, cs:WPP_GLOBAL_Control
0x18003a08f  cmp     rax, rcx
0x18003a092  jz      short loc_18003A10C
0x18003a094  cmp     byte ptr [rax+19h], 2
0x18003a098  jb      short loc_18003A10C
0x18003a09a  test    dword ptr [rax+1Ch], 400h
0x18003a0a1  jz      short loc_18003A10C
0x18003a0a3  lea     rcx, aNumberOfServer; "Number of server groups in the config b"...
0x18003a0aa  call    WppDbgPrint
0x18003a0af  mov     edx, 67h ; 'g'
0x18003a0b4  jmp     short loc_18003A0EE
0x18003a0b6  cmp     ebx, dword ptr [rbp+80h+var_40]
0x18003a0b9  jbe     short loc_18003A113
0x18003a0bb  lea     rcx, WPP_GLOBAL_Control
0x18003a0c2  mov     rax, cs:WPP_GLOBAL_Control
0x18003a0c9  cmp     rax, rcx
0x18003a0cc  jz      short loc_18003A10C
0x18003a0ce  cmp     byte ptr [rax+19h], 2
0x18003a0d2  jb      short loc_18003A10C
0x18003a0d4  test    dword ptr [rax+1Ch], 400h
0x18003a0db  jz      short loc_18003A10C
0x18003a0dd  lea     rcx, aNumberOfClient; "Number of clients in the config being i"...
0x18003a0e4  call    WppDbgPrint
0x18003a0e9  mov     edx, 68h ; 'h'
0x18003a0ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a0f5  lea     r9, aNpssdo; "NPSSDO"
0x18003a0fc  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003a103  mov     rcx, [rcx+10h]
0x18003a107  call    WPP_SF_s
0x18003a10c  mov     ebx, 80070573h
0x18003a111  jmp     short loc_18003A115
0x18003a113  xor     ebx, ebx
0x18003a115  xor     r8d, r8d
0x18003a118  mov     dl, 1
0x18003a11a  lea     rcx, [rbp+80h+var_30]
0x18003a11e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18003a123  nop
0x18003a124  lea     rcx, [rsp+180h+var_150]
0x18003a129  call    ??_D?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAAXXZ; std::basic_ifstream<ushort>::`vbase destructor'(void)
0x18003a12e  nop
0x18003a12f  lea     rcx, [rsp+180h+var_160]; this
0x18003a134  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x18003a139  mov     eax, ebx
0x18003a13b  mov     rcx, [rbp+80h+var_10]
0x18003a13f  xor     rcx, rsp; StackCookie
0x18003a142  call    __security_check_cookie
0x18003a147  lea     r11, [rsp+180h+var_s0]
0x18003a14f  mov     rbx, [r11+10h]
0x18003a153  mov     rdi, [r11+20h]
0x18003a157  mov     rsp, r11
0x18003a15a  pop     rbp
0x18003a15b  retn
```
