# SNI_Conn::AllocAndSetName(wchar_t * *,wchar_t *,bool)

- ea: `0x100423460`
- end: `0x10042373f`
- name: `?AllocAndSetName@SNI_Conn@@AEAAKPEAPEA_WPEA_W_N@Z`
- size: `735`
- prototype: `unsigned int __fastcall(SNI_Conn *__hidden this, wchar_t **, wchar_t *, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x100423310`
- `0x10044d800`

## callees

- `0x100423460`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100423692`
- `KERNEL32!GetLastError` at `0x100423692`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004235e9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004235e9`
- `sqldk!SystemThread_TlsIndex` at `0x10042357c`
- `sqldk!SystemThread_TlsOffset` at `0x100423585`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004235a0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004235a0`

## string_xrefs

- `0x10042348f`: `sql\common\dk\sni\src\sni.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SNI_Conn::AllocAndSetName(SNI_Conn *this, wchar_t **a2, wchar_t *a3, unsigned __int8 a4)
{
  char v7; // al
  unsigned int v8; // ebx
  int v9; // r8d
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  unsigned int v12; // edi
  int v13; // ebp
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rbx
  unsigned __int64 v18; // rax
  wchar_t *v19; // rcx
  const wchar_t *v20; // r9
  char *v21; // rsi
  wchar_t v22; // ax
  wchar_t *v23; // rax
  DWORD LastError; // eax
  __int64 v26; // [rsp+20h] [rbp-58h]
  __int64 v27; // [rsp+28h] [rbp-50h]
  __int64 v28; // [rsp+30h] [rbp-48h]

  v7 = g_XeSniPkg_enabledBitmap;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
  {
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNI_Conn::AllocAndSetName",
      1282,
      L"API|SNIpwszTarget: %p{WCHAR**}, szSource: \"%s\", fFailEmptySource: %d{bool}\n",
      a2,
      a3,
      a4);
    v7 = g_XeSniPkg_enabledBitmap;
  }
  if ( !*a3 && a4 )
  {
    if ( (v7 & 2) != 0 )
    {
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni.cpp",
        "SNI_Conn::AllocAndSetName",
        1292,
        L"ERR|SNIszSource : empty string encounted\n");
      v7 = g_XeSniPkg_enabledBitmap;
    }
    v8 = 87;
    if ( (v7 & 2) == 0 )
      goto LABEL_37;
    LODWORD(v28) = 87;
    v9 = 1294;
    goto LABEL_36;
  }
  v10 = 255;
  v11 = a3;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  v12 = 0;
  if ( !v10 )
  {
    v8 = 87;
    if ( (v7 & 2) != 0 )
    {
      LODWORD(v28) = 87;
      v9 = 1302;
LABEL_36:
      LODWORD(v27) = 0;
      LODWORD(v26) = 10;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni.cpp",
        "SNI_Conn::AllocAndSetName",
        v9,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v26,
        v27,
        v28);
      goto LABEL_37;
    }
    goto LABEL_37;
  }
  v13 = 255 - v10 + 1;
  v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v15 = *(_QWORD *)(v14 + 256);
  if ( !v15 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v15 = *(_QWORD *)(v14 + 256);
  }
  v16 = *(_QWORD *)(*(_QWORD *)(v15 + 992) + 56LL);
  v17 = v13;
  v18 = 2LL * v13;
  if ( !is_mul_ok(v13, 2u) )
    v18 = -1;
  v19 = (wchar_t *)operator new[](v18, *(struct IMemObj **)(v16 + 8), 1, "sql\\common\\dk\\sni\\src\\sni.cpp", 1313, 6u);
  *a2 = v19;
  if ( !v19 )
  {
    v8 = 14;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v28) = 14;
      v9 = 1318;
      goto LABEL_36;
    }
LABEL_37:
    SNISetLastError(0xAu, v8, 0xC3B4u);
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v26) = v8;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni.cpp",
        "SNI_Conn::AllocAndSetName",
        1338,
        L"ERR|SNI%d{WINERR}\n",
        v26);
    }
    v12 = v8;
    goto LABEL_40;
  }
  if ( (unsigned __int64)(v13 - 1LL) > 0x7FFFFFFE )
  {
    if ( v13 )
      *v19 = 0;
LABEL_34:
    LastError = GetLastError();
    v8 = LastError;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v28) = LastError;
      v9 = 1327;
      goto LABEL_36;
    }
    goto LABEL_37;
  }
  v21 = (char *)((char *)a3 - (char *)v19);
  do
  {
    if ( !(2147483646LL - v13 + v17) )
      break;
    v22 = *(wchar_t *)((char *)v19 + (_QWORD)v21);
    if ( !v22 )
      break;
    *v19++ = v22;
    --v17;
  }
  while ( v17 );
  v23 = v19 - 1;
  if ( v17 )
    v23 = v19;
  *v23 = 0;
  if ( !v17 )
    goto LABEL_34;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "SNI_Conn::AllocAndSetName",
      1332,
      L"RET|SNI%d{WINERR}\n",
      0);
LABEL_40:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNI_Conn::AllocAndSetName", 1282, v20);
  return v12;
}

```

## disassembly

```asm
0x100423460  mov     r11, rsp
0x100423463  push    r12
0x100423465  push    r14
0x100423467  push    r15
0x100423469  sub     rsp, 60h
0x10042346d  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x100423475  mov     [r11+8], rbx
0x100423479  mov     [r11+10h], rbp
0x10042347d  mov     [r11+18h], rsi
0x100423481  mov     [r11+20h], rdi
0x100423485  movzx   ebx, r9b
0x100423489  mov     rsi, r8
0x10042348c  mov     r14, rdx
0x10042348f  lea     r15, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x100423496  mov     [r11-30h], r15
0x10042349a  lea     r12, aSniConnAllocan; "SNI_Conn::AllocAndSetName"
0x1004234a1  mov     [r11-28h], r12
0x1004234a5  mov     [rsp+78h+var_20], 502h
0x1004234ad  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004234b3  test    al, 40h
0x1004234b5  jz      short loc_1004234E1
0x1004234b7  mov     dword ptr [rsp+78h+var_48], ebx
0x1004234bb  mov     [r11-50h], r8
0x1004234bf  mov     [r11-58h], rdx
0x1004234c3  lea     r9, aApiSnipwsztarg; "API|SNIpwszTarget: %p{WCHAR**}, szSourc"...
0x1004234ca  mov     r8d, 502h; int
0x1004234d0  mov     rdx, r12; char *
0x1004234d3  mov     rcx, r15; char *
0x1004234d6  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004234db  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004234e1  cmp     word ptr [rsi], 0
0x1004234e5  jnz     short loc_10042352B
0x1004234e7  test    bl, bl
0x1004234e9  jz      short loc_10042352B
0x1004234eb  test    al, 2
0x1004234ed  jz      short loc_10042350D
0x1004234ef  lea     r9, aErrSniszsource; "ERR|SNIszSource : empty string encounte"...
0x1004234f6  mov     r8d, 50Ch; int
0x1004234fc  mov     rdx, r12; char *
0x1004234ff  mov     rcx, r15; char *
0x100423502  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100423507  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042350d  mov     ebx, 57h ; 'W'
0x100423512  test    al, 2
0x100423514  jz      loc_1004236CB
0x10042351a  mov     dword ptr [rsp+78h+var_48], ebx
0x10042351e  xor     edi, edi
0x100423520  mov     r8d, 50Eh
0x100423526  jmp     loc_1004236AD
0x10042352b  mov     r8d, 0FFh
0x100423531  mov     edx, r8d
0x100423534  mov     rcx, rsi
0x100423537  cmp     word ptr [rcx], 0
0x10042353b  jz      short loc_100423547
0x10042353d  add     rcx, 2
0x100423541  sub     rdx, 1
0x100423545  jnz     short loc_100423537
0x100423547  sub     r8, rdx
0x10042354a  xor     edi, edi
0x10042354c  test    rdx, rdx
0x10042354f  cmovz   r8, rdi
0x100423553  jnz     short loc_10042356F
0x100423555  lea     ebx, [rdi+57h]
0x100423558  test    al, 2
0x10042355a  jz      loc_1004236CB
0x100423560  mov     dword ptr [rsp+78h+var_48], ebx
0x100423564  mov     r8d, 516h
0x10042356a  jmp     loc_1004236AD
0x10042356f  lea     ebp, [r8+1]
0x100423573  mov     rdx, gs:58h
0x10042357c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100423583  mov     ecx, [rax]
0x100423585  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10042358c  mov     ebx, [rax]
0x10042358e  add     rbx, [rdx+rcx*8]
0x100423592  mov     rax, [rbx+100h]
0x100423599  test    rax, rax
0x10042359c  jnz     short loc_1004235AD
0x10042359e  xor     ecx, ecx
0x1004235a0  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004235a6  mov     rax, [rbx+100h]
0x1004235ad  mov     rax, [rax+3E0h]
0x1004235b4  mov     rcx, [rax+38h]
0x1004235b8  movsxd  rbx, ebp
0x1004235bb  mov     eax, 2
0x1004235c0  mul     rbx
0x1004235c3  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1004235ca  cmovo   rax, rdx
0x1004235ce  mov     byte ptr [rsp+78h+var_50], 6
0x1004235d3  mov     dword ptr [rsp+78h+var_58], 521h
0x1004235db  mov     r9, r15
0x1004235de  lea     r8d, [rdx+2]
0x1004235e2  mov     rdx, [rcx+8]
0x1004235e6  mov     rcx, rax
0x1004235e9  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1004235ef  mov     rcx, rax
0x1004235f2  mov     [r14], rax
0x1004235f5  test    rax, rax
0x1004235f8  jnz     short loc_100423619
0x1004235fa  lea     ebx, [rax+0Eh]
0x1004235fd  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100423604  jz      loc_1004236CB
0x10042360a  mov     dword ptr [rsp+78h+var_48], ebx
0x10042360e  mov     r8d, 526h
0x100423614  jmp     loc_1004236AD
0x100423619  lea     rax, [rbx-1]
0x10042361d  mov     edx, 7FFFFFFEh
0x100423622  cmp     rax, rdx
0x100423625  ja      short loc_10042368B
0x100423627  sub     rdx, rbx
0x10042362a  sub     rsi, rcx
0x10042362d  nop     dword ptr [rax]
0x100423630  lea     rax, [rdx+rbx]
0x100423634  test    rax, rax
0x100423637  jz      short loc_10042364F
0x100423639  movzx   eax, word ptr [rsi+rcx]
0x10042363d  test    ax, ax
0x100423640  jz      short loc_10042364F
0x100423642  mov     [rcx], ax
0x100423645  add     rcx, 2
0x100423649  sub     rbx, 1
0x10042364d  jnz     short loc_100423630
0x10042364f  lea     rax, [rcx-2]
0x100423653  test    rbx, rbx
0x100423656  cmovnz  rax, rcx
0x10042365a  mov     [rax], di
0x10042365d  jz      short loc_100423692
0x10042365f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100423666  jz      loc_100423704
0x10042366c  mov     [rsp+78h+var_58], rdi
0x100423671  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100423678  mov     r8d, 534h; int
0x10042367e  mov     rdx, r12; char *
0x100423681  mov     rcx, r15; char *
0x100423684  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100423689  jmp     short loc_100423704
0x10042368b  test    ebp, ebp
0x10042368d  jz      short loc_100423692
0x10042368f  mov     [rcx], di
0x100423692  call    cs:__imp_GetLastError
0x100423698  mov     ebx, eax
0x10042369a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004236a1  jz      short loc_1004236CB
0x1004236a3  mov     dword ptr [rsp+78h+var_48], eax
0x1004236a7  mov     r8d, 52Fh; int
0x1004236ad  mov     dword ptr [rsp+78h+var_50], edi
0x1004236b1  mov     dword ptr [rsp+78h+var_58], 0Ah
0x1004236b9  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x1004236c0  mov     rdx, r12; char *
0x1004236c3  mov     rcx, r15; char *
0x1004236c6  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004236cb  mov     r8d, 0C3B4h
0x1004236d1  mov     edx, ebx
0x1004236d3  mov     ecx, 0Ah
0x1004236d8  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004236dd  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004236e4  jz      short loc_100423702
0x1004236e6  mov     dword ptr [rsp+78h+var_58], ebx
0x1004236ea  lea     r9, aErrSniDWinerr; "ERR|SNI%d{WINERR}\n"
0x1004236f1  mov     r8d, 53Ah; int
0x1004236f7  mov     rdx, r12; char *
0x1004236fa  mov     rcx, r15; char *
0x1004236fd  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100423702  mov     edi, ebx
0x100423704  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10042370b  jz      short loc_10042371E
0x10042370d  mov     r8d, 502h; int
0x100423713  mov     rdx, r12; char *
0x100423716  mov     rcx, r15; char *
0x100423719  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10042371e  mov     eax, edi
0x100423720  lea     r11, [rsp+78h+var_18]
0x100423725  mov     rbx, [r11+20h]
0x100423729  mov     rbp, [r11+28h]
0x10042372d  mov     rsi, [r11+30h]
0x100423731  mov     rdi, [r11+38h]
0x100423735  mov     rsp, r11
0x100423738  pop     r15
0x10042373a  pop     r14
0x10042373c  pop     r12
0x10042373e  retn
```
