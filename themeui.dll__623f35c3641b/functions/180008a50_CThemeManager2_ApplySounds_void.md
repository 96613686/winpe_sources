# CThemeManager2::_ApplySounds(void)

- ea: `0x180008a50`
- end: `0x180008dd2`
- name: `?_ApplySounds@CThemeManager2@@AEAAJXZ`
- size: `898`
- prototype: `__int64 __fastcall(CThemeManager2 *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004f044`

## callees

- `0x1800082f0`
- `0x1800089c0`
- `0x180008a50`
- `0x180008dd8`
- `0x180012ea0`
- `0x180016ca0`
- `0x1800179e0`
- `0x1800197c8`
- `0x18001987c`
- `0x1800199d0`
- `0x18001e3ec`
- `0x1800211c4`
- `0x1800358c0`
- `0x180042900`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008c7e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008c7e`
- `OLEAUT32!__imp_SysFreeString` at `0x180008b7f`
- `OLEAUT32!__imp_SysFreeString` at `0x180008be5`
- `OLEAUT32!__imp_SysFreeString` at `0x180008c92`
- `OLEAUT32!__imp_SysFreeString` at `0x180008b7f`
- `OLEAUT32!__imp_SysFreeString` at `0x180008be5`
- `OLEAUT32!__imp_SysFreeString` at `0x180008c92`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180008dc6`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180008dc6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CThemeManager2::_ApplySounds(CThemeManager2 *this)
{
  unsigned int v2; // r8d
  int SoundSchemeShortName; // ebx
  bool v4; // di
  struct _DPA *v5; // rax
  int AllRegSoundEvents; // r12d
  int v7; // edi
  struct _DPA *v8; // rbx
  const unsigned __int16 *Ptr; // rax
  const unsigned __int16 *v10; // r15
  __int64 v11; // r14
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64, BSTR *); // rsi
  _QWORD *v13; // rax
  BSTR v14; // rsi
  const unsigned __int16 *v15; // rdx
  WCHAR v17; // r9
  WCHAR *v18; // rcx
  const WCHAR *v19; // r8
  WCHAR *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  const BYTE *v23; // r9
  bool v24; // [rsp+30h] [rbp-D0h]
  BSTR v25; // [rsp+38h] [rbp-C8h] BYREF
  HDPA hdpa; // [rsp+40h] [rbp-C0h] BYREF
  BSTR v27; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String1[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v30[264]; // [rsp+270h] [rbp+170h] BYREF

  v27 = 0;
  if ( (*(int (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)this + 266) + 320LL))(*((_QWORD *)this + 266), &v27) >= 0 )
  {
    SoundSchemeShortName = GetSoundSchemeShortName(v27, String1, v2);
    if ( SoundSchemeShortName >= 0 )
    {
      if ( !String1[0] )
      {
        v21 = 2147483646;
        v19 = L"Custom";
        v22 = 260;
        v20 = String1;
        do
        {
          if ( !v21 )
            break;
          v17 = *v19;
          if ( !*v19 )
            break;
          ++v19;
          *v20++ = v17;
          --v21;
          --v22;
        }
        while ( v22 );
        v18 = v20 - 1;
        if ( v22 )
          v18 = v20;
        *v18 = 0;
        SoundSchemeShortName = -2147024774;
        if ( v22 )
          SoundSchemeShortName = 0;
      }
      v4 = IsInboxSoundScheme(String1);
      v24 = v4;
      if ( SoundSchemeShortName >= 0 )
      {
        v5 = g_pfn_DPA_Create(16);
        hdpa = v5;
        if ( v5 )
        {
          AllRegSoundEvents = GetAllRegSoundEvents(&hdpa);
          v7 = 0;
          if ( AllRegSoundEvents > 0 )
          {
            v8 = hdpa;
            do
            {
              Ptr = (const unsigned __int16 *)g_pfn_DPA_GetPtr(v8, (unsigned int)v7);
              v10 = Ptr;
              if ( Ptr )
              {
                v25 = 0;
                v11 = *((_QWORD *)this + 266);
                v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, BSTR *))(*(_QWORD *)v11 + 336LL);
                v13 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, Ptr);
                LODWORD(v12) = v12(v11, *v13, 0xFFFFFFFFLL, &v25);
                SysFreeString(bstrString[0]);
                if ( (int)v12 >= 0 )
                {
                  if ( !v24 )
                  {
                    SetSystemSoundSchemeSetting(v10, String1, v25);
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    {
                      WPP_SF_SSS(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        71,
                        (unsigned int)WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
                        (_DWORD)v10,
                        (__int64)String1,
                        (__int64)v25);
                    }
                  }
                  v14 = v25;
                  if ( (int)StringCchPrintfW(v30, 0x104u, L"%s\\%s", v10, L".Current") >= 0 )
                  {
                    v23 = (const BYTE *)v14;
                    if ( !v14 )
                      v23 = (const BYTE *)&Default;
                    SHRegSetString(HKEY_CURRENT_USER, v30, 0, v23);
                  }
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  {
                    WPP_SF_SSS(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      72,
                      (unsigned int)WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids,
                      (_DWORD)v10,
                      (__int64)L".Current",
                      (__int64)v25);
                  }
                }
                SysFreeString(v25);
              }
              ++v7;
            }
            while ( v7 < AllRegSoundEvents );
          }
          CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>::Destroy(&hdpa);
          v5 = hdpa;
          v4 = v24;
        }
        if ( v5 )
          CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>::Destroy(&hdpa);
      }
      if ( v4 )
        v15 = 0;
      else
        v15 = v27;
      SetSystemSoundScheme(String1, v15);
      if ( CompareStringOrdinal(String1, -1, L"Custom", -1, 1) != 2 )
        RegDeleteKeyW(HKEY_CURRENT_USER, L"AppEvents\\Schemes\\Names\\Custom");
    }
  }
  SysFreeString(v27);
  return 0;
}

```

## disassembly

```asm
0x180008a50  push    rbp
0x180008a52  push    rbx
0x180008a53  push    rsi
0x180008a54  push    rdi
0x180008a55  push    r12
0x180008a57  push    r13
0x180008a59  push    r14
0x180008a5b  push    r15
0x180008a5d  lea     rbp, [rsp-398h]
0x180008a65  sub     rsp, 498h
0x180008a6c  mov     rax, cs:__security_cookie
0x180008a73  xor     rax, rsp
0x180008a76  mov     [rbp+3D0h+var_50], rax
0x180008a7d  mov     r13, rcx
0x180008a80  mov     [rsp+4D0h+var_488], 0
0x180008a89  mov     rcx, [rcx+850h]
0x180008a90  mov     rax, [rcx]
0x180008a93  lea     rdx, [rsp+4D0h+var_488]
0x180008a98  mov     rax, [rax+140h]
0x180008a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aa4  test    eax, eax
0x180008aa6  js      loc_180008C8D
0x180008aac  lea     rdx, [rsp+4D0h+String1]; unsigned __int16 *
0x180008ab1  mov     rcx, [rsp+4D0h+var_488]; unsigned __int16 *
0x180008ab6  call    ?GetSoundSchemeShortName@@YAJPEBGPEAGI@Z; GetSoundSchemeShortName(ushort const *,ushort *,uint)
0x180008abb  mov     ebx, eax
0x180008abd  test    eax, eax
0x180008abf  js      loc_180008C8D
0x180008ac5  cmp     [rsp+4D0h+String1], 0
0x180008acb  jz      loc_180008D03
0x180008ad1  lea     rcx, [rsp+4D0h+String1]; lpString2
0x180008ad6  call    ?IsInboxSoundScheme@@YA_NPEBG@Z; IsInboxSoundScheme(ushort const *)
0x180008adb  movzx   edi, al
0x180008ade  mov     [rsp+4D0h+var_4A0], al
0x180008ae2  test    ebx, ebx
0x180008ae4  js      loc_180008C13
0x180008aea  mov     ecx, 10h; cItemGrow
0x180008aef  call    cs:g_pfn_DPA_Create
0x180008af5  mov     [rsp+4D0h+hdpa], rax
0x180008afa  test    rax, rax
0x180008afd  jz      loc_180008C0A
0x180008b03  lea     rcx, [rsp+4D0h+hdpa]
0x180008b08  call    ?GetAllRegSoundEvents@@YAHPEAV?$CDPACoTaskMem@G@@@Z; GetAllRegSoundEvents(CDPACoTaskMem<ushort> *)
0x180008b0d  mov     r12d, eax
0x180008b10  xor     edi, edi
0x180008b12  test    eax, eax
0x180008b14  jle     loc_180008BF6
0x180008b1a  mov     rbx, [rsp+4D0h+hdpa]
0x180008b1f  nop
0x180008b20  mov     edx, edi; i
0x180008b22  mov     rcx, rbx; hdpa
0x180008b25  call    cs:g_pfn_DPA_GetPtr
0x180008b2b  mov     r15, rax
0x180008b2e  test    rax, rax
0x180008b31  jz      loc_180008BEB
0x180008b37  mov     [rsp+4D0h+var_498], 0
0x180008b40  mov     r14, [r13+850h]
0x180008b47  mov     rdx, [r14]
0x180008b4a  mov     rsi, [rdx+150h]
0x180008b51  mov     rdx, rax; unsigned __int16 *
0x180008b54  lea     rcx, [rsp+4D0h+bstrString]; this
0x180008b59  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180008b5e  nop
0x180008b5f  lea     r9, [rsp+4D0h+var_498]
0x180008b64  mov     r8d, 0FFFFFFFFh
0x180008b6a  mov     rdx, [rax]
0x180008b6d  mov     rcx, r14
0x180008b70  mov     rax, rsi
0x180008b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b78  mov     esi, eax
0x180008b7a  mov     rcx, [rsp+4D0h+bstrString]; bstrString
0x180008b7f  call    cs:__imp_SysFreeString
0x180008b85  shr     esi, 1Fh
0x180008b88  xor     sil, 1
0x180008b8c  jz      short loc_180008BE0
0x180008b8e  cmp     [rsp+4D0h+var_4A0], 0
0x180008b93  jz      loc_180008D1B
0x180008b99  lea     r14, WPP_GLOBAL_Control
0x180008ba0  mov     rsi, [rsp+4D0h+var_498]
0x180008ba5  lea     rax, aCurrent; ".Current"
0x180008bac  mov     qword ptr [rsp+4D0h+bIgnoreCase], rax
0x180008bb1  mov     r9, r15
0x180008bb4  lea     r8, aSS; "%s\\%s"
0x180008bbb  mov     edx, 104h; unsigned __int64
0x180008bc0  lea     rcx, [rbp+3D0h+var_260]; unsigned __int16 *
0x180008bc7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008bcc  test    eax, eax
0x180008bce  jns     loc_180008D7F
0x180008bd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bdb  cmp     rcx, r14
0x180008bde  jnz     short loc_180008C24
0x180008be0  mov     rcx, [rsp+4D0h+var_498]; bstrString
0x180008be5  call    cs:__imp_SysFreeString
0x180008beb  inc     edi
0x180008bed  cmp     edi, r12d
0x180008bf0  jl      loc_180008B20
0x180008bf6  lea     rcx, [rsp+4D0h+hdpa]
0x180008bfb  call    ?Destroy@?$CDPA_Base@GVCTContainer_PolicyCoTaskMem@@@@QEAAHXZ; CDPA_Base<ushort,CTContainer_PolicyCoTaskMem>::Destroy(void)
0x180008c00  mov     rax, [rsp+4D0h+hdpa]
0x180008c05  movzx   edi, [rsp+4D0h+var_4A0]
0x180008c0a  test    rax, rax
0x180008c0d  jnz     loc_180008DA9
0x180008c13  lea     rcx, [rsp+4D0h+String1]; unsigned __int16 *
0x180008c18  test    dil, dil
0x180008c1b  jnz     short loc_180008C5A
0x180008c1d  mov     rdx, [rsp+4D0h+var_488]
0x180008c22  jmp     short loc_180008C5C
0x180008c24  test    byte ptr [rcx+1Ch], 8
0x180008c28  jz      short loc_180008BE0
0x180008c2a  mov     edx, 48h ; 'H'
0x180008c2f  mov     rax, [rsp+4D0h+var_498]
0x180008c34  mov     [rsp+4D0h+var_4A8], rax
0x180008c39  lea     rax, aCurrent; ".Current"
0x180008c40  mov     qword ptr [rsp+4D0h+bIgnoreCase], rax
0x180008c45  mov     r9, r15
0x180008c48  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x180008c4f  mov     rcx, [rcx+10h]
0x180008c53  call    WPP_SF_SSS
0x180008c58  jmp     short loc_180008BE0
0x180008c5a  xor     edx, edx; unsigned __int16 *
0x180008c5c  call    ?SetSystemSoundScheme@@YAJPEBG0@Z; SetSystemSoundScheme(ushort const *,ushort const *)
0x180008c61  mov     [rsp+4D0h+bIgnoreCase], 1; bIgnoreCase
0x180008c69  mov     r9d, 0FFFFFFFFh; cchCount2
0x180008c6f  lea     r8, aCustom; "Custom"
0x180008c76  mov     edx, r9d; cchCount1
0x180008c79  lea     rcx, [rsp+4D0h+String1]; lpString1
0x180008c7e  call    cs:__imp_CompareStringOrdinal
0x180008c84  cmp     eax, 2
0x180008c87  jnz     loc_180008DB8
0x180008c8d  mov     rcx, [rsp+4D0h+var_488]; bstrString
0x180008c92  call    cs:__imp_SysFreeString
0x180008c98  xor     eax, eax
0x180008c9a  mov     rcx, [rbp+3D0h+var_50]
0x180008ca1  xor     rcx, rsp; StackCookie
0x180008ca4  call    __security_check_cookie
0x180008ca9  add     rsp, 498h
0x180008cb0  pop     r15
0x180008cb2  pop     r14
0x180008cb4  pop     r13
0x180008cb6  pop     r12
0x180008cb8  pop     rdi
0x180008cb9  pop     rsi
0x180008cba  pop     rbx
0x180008cbb  pop     rbp
0x180008cbc  retn
0x180008cbd  test    rcx, rcx
0x180008cc0  jz      short loc_180008CCC
0x180008cc2  movzx   r9d, word ptr [r8]
0x180008cc6  test    r9w, r9w
0x180008cca  jnz     short loc_180008CEC
0x180008ccc  lea     rcx, [rax-2]
0x180008cd0  test    rdx, rdx
0x180008cd3  cmovnz  rcx, rax
0x180008cd7  xor     eax, eax
0x180008cd9  mov     [rcx], ax
0x180008cdc  mov     ebx, 8007007Ah
0x180008ce1  test    rdx, rdx
0x180008ce4  cmovnz  ebx, eax
0x180008ce7  jmp     loc_180008AD1
0x180008cec  add     r8, 2
0x180008cf0  mov     [rax], r9w
0x180008cf4  add     rax, 2
0x180008cf8  dec     rcx
0x180008cfb  sub     rdx, 1
0x180008cff  jnz     short loc_180008CBD
0x180008d01  jmp     short loc_180008CCC
0x180008d03  mov     ecx, 7FFFFFFEh
0x180008d08  lea     r8, aCustom; "Custom"
0x180008d0f  mov     edx, 104h
0x180008d14  lea     rax, [rsp+4D0h+String1]
0x180008d19  jmp     short loc_180008CBD
0x180008d1b  mov     r8, [rsp+4D0h+var_498]; unsigned __int16 *
0x180008d20  lea     rdx, [rsp+4D0h+String1]; unsigned __int16 *
0x180008d25  mov     rcx, r15; unsigned __int16 *
0x180008d28  call    ?SetSystemSoundSchemeSetting@@YAJPEBG00@Z; SetSystemSoundSchemeSetting(ushort const *,ushort const *,ushort const *)
0x180008d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d34  lea     r14, WPP_GLOBAL_Control
0x180008d3b  cmp     rcx, r14
0x180008d3e  jz      loc_180008BA0
0x180008d44  test    byte ptr [rcx+1Ch], 8
0x180008d48  jz      loc_180008BA0
0x180008d4e  mov     edx, 47h ; 'G'
0x180008d53  mov     rax, [rsp+4D0h+var_498]
0x180008d58  mov     [rsp+4D0h+var_4A8], rax
0x180008d5d  lea     rax, [rsp+4D0h+String1]
0x180008d62  mov     qword ptr [rsp+4D0h+bIgnoreCase], rax
0x180008d67  mov     r9, r15
0x180008d6a  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x180008d71  mov     rcx, [rcx+10h]
0x180008d75  call    WPP_SF_SSS
0x180008d7a  jmp     loc_180008BA0
0x180008d7f  xor     r8d, r8d; unsigned __int16 *
0x180008d82  lea     rdx, [rbp+3D0h+var_260]; unsigned __int16 *
0x180008d89  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180008d90  test    rsi, rsi
0x180008d93  mov     r9, rsi
0x180008d96  jnz     short loc_180008D9F
0x180008d98  lea     r9, Default; unsigned __int16 *
0x180008d9f  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180008da4  jmp     loc_180008BD4
0x180008da9  lea     rcx, [rsp+4D0h+hdpa]
0x180008dae  call    ?Destroy@?$CDPA_Base@GVCTContainer_PolicyCoTaskMem@@@@QEAAHXZ; CDPA_Base<ushort,CTContainer_PolicyCoTaskMem>::Destroy(void)
0x180008db3  jmp     loc_180008C13
0x180008db8  lea     rdx, aAppeventsSchem_32; "AppEvents\\Schemes\\Names\\Custom"
0x180008dbf  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180008dc6  call    cs:__imp_RegDeleteKeyW
0x180008dcc  jmp     loc_180008C8D
```
