# Sm::OpenNpBasedYukon(Sni_Consumer_Info *,SNI_Conn * *,ProtElem *,SNI_Provider * *,int)

- ea: `0x100453cd0`
- end: `0x100454168`
- name: `?OpenNpBasedYukon@Sm@@CAKPEAUSni_Consumer_Info@@PEAPEAVSNI_Conn@@PEAVProtElem@@PEAPEAVSNI_Provider@@H@Z`
- size: `1176`
- prototype: `static unsigned int(struct Sni_Consumer_Info *, struct SNI_Conn **, struct ProtElem *, struct SNI_Provider **, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x100425000`

## callees

- `0x100403b90`
- `0x100421400`
- `0x100422710`
- `0x100422bc0`
- `0x100423130`
- `0x100423310`
- `0x100427e60`
- `0x10042b7f0`
- `0x10042c270`
- `0x10042c430`
- `0x10043b510`
- `0x100453cd0`
- `0x100486af0`

## import_xrefs

- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100454008`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100454008`
- `USER32!CharNextW` at `0x100453fb2`
- `USER32!CharNextW` at `0x100453fb2`

## string_xrefs

- `0x100453d12`: `sql\common\dk\sni\src\sm.cpp`
- `0x100453f11`: `sql\common\dk\sni\src\sm.cpp`
- `0x100453f62`: `sql\common\dk\sni\src\sm.cpp`
- `0x10045407f`: `sql\common\dk\sni\src\sm.cpp`
- `0x1004540a2`: `sql\common\dk\sni\src\sm.cpp`
- `0x100454132`: `sql\common\dk\sni\src\sm.cpp`
- `0x100454155`: `sql\common\dk\sni\src\sm.cpp`
- `0x100453d1e`: `Sm::OpenNpBasedYukon`
- `0x100454078`: `Sm::OpenNpBasedYukon`
- `0x10045409b`: `Sm::OpenNpBasedYukon`
- `0x10045412b`: `Sm::OpenNpBasedYukon`
- `0x10045414e`: `Sm::OpenNpBasedYukon`
- `0x100453f0a`: `Sm::CreateSNIConn`
- `0x100453f5b`: `Sm::CreateSNIConn`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Sm::OpenNpBasedYukon(
        struct Sni_Consumer_Info *a1,
        struct SNI_Conn **a2,
        wchar_t *a3,
        struct SNI_Provider **a4,
        int a5)
{
  unsigned int inited; // ebx
  const wchar_t *v10; // r9
  unsigned int v11; // edx
  __int64 *v12; // rax
  struct SNI_Conn *v13; // r14
  char *v14; // rsi
  __int64 v15; // rbx
  const WCHAR *v16; // rcx
  int v17; // edi
  LPWSTR v18; // rax
  __int64 v19; // rax
  const wchar_t *v20; // rdi
  struct __crt_locale_pointers *DefaultLocale; // rax
  __int64 v23; // [rsp+20h] [rbp-E0h]
  __int64 v24; // [rsp+30h] [rbp-D0h]
  _BYTE v25[8]; // [rsp+50h] [rbp-B0h] BYREF
  struct SNI_Conn *v26[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v27; // [rsp+78h] [rbp-88h]
  int v28; // [rsp+80h] [rbp-80h] BYREF
  int v29; // [rsp+84h] [rbp-7Ch]
  __int16 v30; // [rsp+88h] [rbp-78h]
  __int16 v31; // [rsp+288h] [rbp+188h]
  wchar_t Buffer[512]; // [rsp+488h] [rbp+388h] BYREF
  __int64 v33; // [rsp+888h] [rbp+788h]

  v26[1] = (struct SNI_Conn *)-2LL;
  v26[2] = (struct SNI_Conn *)"sql\\common\\dk\\sni\\src\\sm.cpp";
  v26[3] = (struct SNI_Conn *)"Sm::OpenNpBasedYukon";
  v27 = 545;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sm.cpp",
      "Sm::OpenNpBasedYukon",
      545,
      L"API|SNIpConsumerInfo: %p{SNI_CONSUMER_INFO*}, ppConn: %p{SNI_Conn**}, pProtElem: %p{ProtElem*}, ppProv: %p{SNI_Pro"
       "vider**}, fSync: %d{BOOL}\n",
      a1,
      a2,
      a3,
      a4,
      a5);
  v28 = 10;
  v29 = 10;
  v30 = 0;
  v31 = 0;
  v33 = 0;
  v26[0] = 0;
  inited = SNI_Conn::InitObject(v26, 0);
  if ( inited
    || (*((_BYTE *)v26[0] + 12804) |= 2u,
        *((_BYTE *)v26[0] + 12804) ^= (*((_BYTE *)v26[0] + 12804) ^ (4 * *((_BYTE *)a1 + 92))) & 4,
        *((_BYTE *)v26[0] + 12804) = *((_BYTE *)v26[0] + 12804) & 0xFE | (a5 != 0),
        (inited = SNI_Conn::SetServerName(v26[0], a3 + 4, a3 + 260)) != 0) )
  {
    if ( v26[0] )
    {
      v25[0] = 0;
      SNI_Conn::ReleaseUnderForceCloseLock(v26[0], 0, v25);
      v26[0] = 0;
    }
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v23) = inited;
      SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sm.cpp", "Sm::CreateSNIConn", 715, L"RET|SNI%d{WINERR}\n", v23);
    }
    goto LABEL_30;
  }
  SNISetInfo(v26[0], 1, a1);
  IncrementConnBufSize(v26[0], (struct SNI_PROVIDER_INFO *)((char *)&rgProvInfo + 20 * *(int *)a3));
  v11 = 0;
  v12 = qword_1004912A0;
  while ( (unsigned int)(*((_DWORD *)v26[0] + 3188) + *((_DWORD *)v26[0] + 3189)) > *(_DWORD *)v12 )
  {
    ++v11;
    v12 = (__int64 *)((char *)v12 + 4);
    if ( v11 > 7 )
    {
      v11 = 7;
      break;
    }
  }
  *((_DWORD *)v26[0] + 3200) = v11;
  SNISetInfo(v26[0], 2, *((_QWORD *)a1 + 1));
  *((_QWORD *)v26[0] + 1580) = *((_QWORD *)a1 + 2);
  *((_QWORD *)v26[0] + 1581) = *((_QWORD *)a1 + 3);
  *((_QWORD *)v26[0] + 1583) = *((_QWORD *)a1 + 5);
  *((_QWORD *)v26[0] + 1584) = *((_QWORD *)a1 + 6);
  *((_QWORD *)v26[0] + 1582) = *((_QWORD *)a1 + 4);
  v13 = v26[0];
  v26[0] = 0;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sm.cpp", "Sm::CreateSNIConn", 702, L"RET|SNI%d{WINERR}\n", 0);
  v14 = (char *)(a3 + 516);
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)&v14[2 * v15] );
  v16 = a3 + 516;
  v17 = 0;
  if ( (int)v15 > 0 )
  {
    while ( *v16 )
    {
      if ( *v16 == 92 )
      {
        v20 = v16 + 1;
        goto LABEL_25;
      }
      v18 = CharNextW(v16);
      v16 = v18;
      if ( v18 )
      {
        v19 = ((char *)v18 - v14) >> 1;
        if ( (int)v19 > v17 )
        {
          v17 = v19;
          if ( (int)v19 < (int)v15 )
            continue;
        }
      }
      break;
    }
  }
  v20 = L"MSSQLSERVER";
LABEL_25:
  v28 = 1;
  v29 = 4;
  inited = ProtElem::Init((ProtElem *)&v28, a3 + 4, a3 + 260);
  if ( inited )
    goto LABEL_28;
  Buffer[260] = 0;
  DefaultLocale = GetDefaultLocale();
  if ( (int)StringCchPrintf_lW(Buffer, 0x105u, L"%s%s", DefaultLocale, L"\\\\.\\pipe\\SQLLocal\\", v20) < 0 )
  {
    inited = 111;
    goto LABEL_28;
  }
  inited = Np::Open(v13, (struct ProtElem *)&v28, a4);
  if ( inited )
  {
LABEL_28:
    if ( v13 )
    {
      v25[0] = 0;
      SNI_Conn::ReleaseUnderForceCloseLock(v13, 0, v25);
    }
LABEL_30:
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v23) = inited;
      SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sm.cpp", "Sm::OpenNpBasedYukon", 628, L"RET|SNI%d{WINERR}\n", v23);
    }
    if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
      SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sm.cpp", "Sm::OpenNpBasedYukon", 545, v10);
    return inited;
  }
  *((_DWORD *)v13 + 3191) = *(_DWORD *)a3;
  *a2 = v13;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v24) = 0;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sm.cpp",
      "Sm::OpenNpBasedYukon",
      617,
      L"RET|SNI*ppConn: %p{SNI_Conn*}, *ppProv: %p{SNI_Provider*}, %d{WINERR}\n",
      v13,
      *a4,
      v24);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sm.cpp", "Sm::OpenNpBasedYukon", 545, v10);
  return 0;
}

```

## disassembly

```asm
0x100453cd0  push    rbp
0x100453cd2  push    rbx
0x100453cd3  push    rsi
0x100453cd4  push    rdi
0x100453cd5  push    r12
0x100453cd7  push    r13
0x100453cd9  push    r14
0x100453cdb  push    r15
0x100453cdd  lea     rbp, [rsp-7A8h]
0x100453ce5  sub     rsp, 8A8h
0x100453cec  mov     [rsp+8E0h+var_880], 0FFFFFFFFFFFFFFFEh
0x100453cf5  mov     rax, cs:__security_cookie
0x100453cfc  xor     rax, rsp
0x100453cff  mov     [rbp+7E0h+var_50], rax
0x100453d06  mov     r12, r9
0x100453d09  mov     r15, r8
0x100453d0c  mov     r13, rdx
0x100453d0f  mov     rdi, rcx
0x100453d12  lea     rax, aSqlCommonDkSni_2; "sql\\common\\dk\\sni\\src\\sm.cpp"
0x100453d19  mov     [rsp+8E0h+var_878], rax
0x100453d1e  lea     rcx, aSmOpennpbasedy; "Sm::OpenNpBasedYukon"
0x100453d25  mov     [rsp+8E0h+var_870], rcx
0x100453d2a  mov     [rsp+8E0h+var_868], 221h
0x100453d32  mov     esi, [rbp+7E0h+arg_20]
0x100453d38  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100453d3f  jz      short loc_100453D71
0x100453d41  mov     [rsp+8E0h+var_8A0], esi
0x100453d45  mov     [rsp+8E0h+var_8A8], r9
0x100453d4a  mov     [rsp+8E0h+var_8B0], r8
0x100453d4f  mov     [rsp+8E0h+var_8B8], rdx
0x100453d54  mov     [rsp+8E0h+var_8C0], rdi
0x100453d59  lea     r9, aApiSnipconsume; "API|SNIpConsumerInfo: %p{SNI_CONSUMER_I"...
0x100453d60  mov     r8d, 221h; int
0x100453d66  mov     rdx, rcx; char *
0x100453d69  mov     rcx, rax; char *
0x100453d6c  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100453d71  mov     [rbp+7E0h+var_860], 0Ah
0x100453d78  mov     [rbp+7E0h+var_85C], 0Ah
0x100453d7f  xor     eax, eax
0x100453d81  mov     [rbp+7E0h+var_858], ax
0x100453d85  mov     [rbp+7E0h+var_658], ax
0x100453d8c  mov     [rbp+7E0h+var_58], rax
0x100453d93  mov     [rsp+8E0h+var_888], rax
0x100453d98  mov     r14d, eax
0x100453d9b  xor     edx, edx; int
0x100453d9d  lea     rcx, [rsp+8E0h+var_888]; struct SNI_Conn **
0x100453da2  call    ?InitObject@SNI_Conn@@SAKPEAPEAV1@H@Z; SNI_Conn::InitObject(SNI_Conn * *,int)
0x100453da7  mov     ebx, eax
0x100453da9  test    eax, eax
0x100453dab  jnz     loc_100453F1F
0x100453db1  mov     rax, [rsp+8E0h+var_888]
0x100453db6  or      byte ptr [rax+3204h], 2
0x100453dbd  mov     rcx, [rsp+8E0h+var_888]
0x100453dc2  movzx   eax, byte ptr [rdi+5Ch]
0x100453dc6  shl     al, 2
0x100453dc9  xor     al, [rcx+3204h]
0x100453dcf  and     al, 4
0x100453dd1  xor     [rcx+3204h], al
0x100453dd7  mov     rdx, [rsp+8E0h+var_888]
0x100453ddc  test    esi, esi
0x100453dde  setnz   cl
0x100453de1  movzx   eax, byte ptr [rdx+3204h]
0x100453de8  and     al, 0FEh
0x100453dea  or      cl, al
0x100453dec  mov     [rdx+3204h], cl
0x100453df2  lea     r8, [r15+208h]; wchar_t *
0x100453df9  lea     rdx, [r15+8]; wchar_t *
0x100453dfd  mov     rcx, [rsp+8E0h+var_888]; this
0x100453e02  call    ?SetServerName@SNI_Conn@@QEAAKPEA_W0@Z; SNI_Conn::SetServerName(wchar_t *,wchar_t *)
0x100453e07  mov     ebx, eax
0x100453e09  test    eax, eax
0x100453e0b  jnz     loc_100453F1F
0x100453e11  mov     r8, rdi
0x100453e14  lea     edx, [rax+1]
0x100453e17  mov     rcx, [rsp+8E0h+var_888]
0x100453e1c  call    SNISetInfo
0x100453e21  movsxd  rax, dword ptr [r15]
0x100453e24  lea     rcx, [rax+rax*4]
0x100453e28  lea     rax, ?rgProvInfo@@3PAUSNI_PROVIDER_INFO@@A; SNI_PROVIDER_INFO near * rgProvInfo
0x100453e2f  lea     rdx, [rax+rcx*4]; struct SNI_PROVIDER_INFO *
0x100453e33  mov     rcx, [rsp+8E0h+var_888]; struct SNI_Conn *
0x100453e38  call    ?IncrementConnBufSize@@YAXPEAVSNI_Conn@@PEAUSNI_PROVIDER_INFO@@@Z; IncrementConnBufSize(SNI_Conn *,SNI_PROVIDER_INFO *)
0x100453e3d  xor     esi, esi
0x100453e3f  mov     edx, esi
0x100453e41  mov     r9, [rsp+8E0h+var_888]
0x100453e46  mov     r8d, [r9+31D4h]
0x100453e4d  add     r8d, [r9+31D0h]
0x100453e54  lea     rax, qword_1004912A0
0x100453e5b  nop     dword ptr [rax+rax+00h]
0x100453e60  cmp     r8d, [rax]
0x100453e63  jbe     short loc_100453E75
0x100453e65  inc     edx
0x100453e67  add     rax, 4
0x100453e6b  cmp     edx, 7
0x100453e6e  jbe     short loc_100453E60
0x100453e70  mov     edx, 7
0x100453e75  mov     [r9+3200h], edx
0x100453e7c  mov     r8, [rdi+8]
0x100453e80  mov     edx, 2
0x100453e85  mov     rcx, [rsp+8E0h+var_888]
0x100453e8a  call    SNISetInfo
0x100453e8f  mov     rcx, [rdi+10h]
0x100453e93  mov     rax, [rsp+8E0h+var_888]
0x100453e98  mov     [rax+3160h], rcx
0x100453e9f  mov     rcx, [rdi+18h]
0x100453ea3  mov     rax, [rsp+8E0h+var_888]
0x100453ea8  mov     [rax+3168h], rcx
0x100453eaf  mov     rcx, [rdi+28h]
0x100453eb3  mov     rax, [rsp+8E0h+var_888]
0x100453eb8  mov     [rax+3178h], rcx
0x100453ebf  mov     rcx, [rdi+30h]
0x100453ec3  mov     rax, [rsp+8E0h+var_888]
0x100453ec8  mov     [rax+3180h], rcx
0x100453ecf  mov     rcx, [rdi+20h]
0x100453ed3  mov     rax, [rsp+8E0h+var_888]
0x100453ed8  mov     [rax+3170h], rcx
0x100453edf  mov     r14, [rsp+8E0h+var_888]
0x100453ee4  xor     eax, eax
0x100453ee6  mov     [rsp+8E0h+var_888], rax
0x100453eeb  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100453ef2  jz      loc_100453F78
0x100453ef8  mov     [rsp+8E0h+var_8C0], rax
0x100453efd  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100453f04  mov     r8d, 2BEh; int
0x100453f0a  lea     rdx, aSmCreatesnicon; "Sm::CreateSNIConn"
0x100453f11  lea     rcx, aSqlCommonDkSni_2; "sql\\common\\dk\\sni\\src\\sm.cpp"
0x100453f18  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100453f1d  jmp     short loc_100453F76
0x100453f1f  mov     rcx, [rsp+8E0h+var_888]
0x100453f24  test    rcx, rcx
0x100453f27  jz      short loc_100453F41
0x100453f29  mov     [rsp+8E0h+var_890], r14b
0x100453f2e  lea     r8, [rsp+8E0h+var_890]
0x100453f33  xor     edx, edx
0x100453f35  call    ?ReleaseUnderForceCloseLock@SNI_Conn@@QEAAJW4SNI_REF@@AEA_N@Z; SNI_Conn::ReleaseUnderForceCloseLock(SNI_REF,bool &)
0x100453f3a  xor     esi, esi
0x100453f3c  mov     [rsp+8E0h+var_888], rsi
0x100453f41  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100453f48  jz      short loc_100453F6E
0x100453f4a  mov     dword ptr [rsp+8E0h+var_8C0], ebx
0x100453f4e  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100453f55  mov     r8d, 2CBh; int
0x100453f5b  lea     rdx, aSmCreatesnicon; "Sm::CreateSNIConn"
0x100453f62  lea     rcx, aSqlCommonDkSni_2; "sql\\common\\dk\\sni\\src\\sm.cpp"
0x100453f69  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100453f6e  test    ebx, ebx
0x100453f70  jnz     loc_10045405E
0x100453f76  xor     eax, eax
0x100453f78  lea     rsi, [r15+408h]
0x100453f7f  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x100453f86  inc     rbx
0x100453f89  cmp     word ptr [rsi+rbx*2], 0
0x100453f8e  jnz     short loc_100453F86
0x100453f90  mov     rcx, rsi; lpsz
0x100453f93  mov     edi, eax
0x100453f95  test    ebx, ebx
0x100453f97  jle     short loc_100453FD0
0x100453f99  nop     dword ptr [rax+00000000h]
0x100453fa0  movzx   eax, word ptr [rcx]
0x100453fa3  test    ax, ax
0x100453fa6  jz      short loc_100453FD0
0x100453fa8  cmp     ax, 5Ch ; '\'
0x100453fac  jz      loc_1004540D3
0x100453fb2  call    cs:__imp_CharNextW
0x100453fb8  mov     rcx, rax
0x100453fbb  test    rax, rax
0x100453fbe  jz      short loc_100453FD0
0x100453fc0  sub     rax, rsi
0x100453fc3  sar     rax, 1
0x100453fc6  cmp     eax, edi
0x100453fc8  jle     short loc_100453FD0
0x100453fca  mov     edi, eax
0x100453fcc  cmp     eax, ebx
0x100453fce  jl      short loc_100453FA0
0x100453fd0  lea     rdi, aMssqlserver_0; "MSSQLSERVER"
0x100453fd7  mov     [rbp+7E0h+var_860], 1
0x100453fde  mov     [rbp+7E0h+var_85C], 4
0x100453fe5  lea     r8, [r15+208h]; wchar_t *
0x100453fec  lea     rdx, [r15+8]; wchar_t *
0x100453ff0  lea     rcx, [rbp+7E0h+var_860]; this
0x100453ff4  call    ?Init@ProtElem@@QEAAKQEB_W0@Z; ProtElem::Init(wchar_t const * const,wchar_t const * const)
0x100453ff9  mov     ebx, eax
0x100453ffb  test    eax, eax
0x100453ffd  jnz     short loc_100454045
0x100453fff  xor     esi, esi
0x100454001  mov     [rbp+7E0h+var_250], si
0x100454008  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10045400e  mov     r9, rax; struct __crt_locale_pointers *
0x100454011  mov     [rsp+8E0h+var_8B8], rdi
0x100454016  lea     rax, aPipeSqllocal; "\\\\.\\pipe\\SQLLocal\\"
0x10045401d  mov     [rsp+8E0h+var_8C0], rax
0x100454022  lea     r8, aSS_0; "%s%s"
0x100454029  mov     edx, 105h; unsigned __int64
0x10045402e  lea     rcx, [rbp+7E0h+Buffer]; Buffer
0x100454035  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x10045403a  test    eax, eax
0x10045403c  jns     loc_1004540DC
0x100454042  lea     ebx, [rsi+6Fh]
0x100454045  test    r14, r14
0x100454048  jz      short loc_10045405E
0x10045404a  mov     [rsp+8E0h+var_890], 0
0x10045404f  lea     r8, [rsp+8E0h+var_890]
0x100454054  xor     edx, edx
0x100454056  mov     rcx, r14
0x100454059  call    ?ReleaseUnderForceCloseLock@SNI_Conn@@QEAAJW4SNI_REF@@AEA_N@Z; SNI_Conn::ReleaseUnderForceCloseLock(SNI_REF,bool &)
0x10045405e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100454065  jz      short loc_10045408C
0x100454067  mov     dword ptr [rsp+8E0h+var_8C0], ebx
0x10045406b  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100454072  mov     r8d, 274h; int
0x100454078  lea     rdx, aSmOpennpbasedy; "Sm::OpenNpBasedYukon"
0x10045407f  lea     rcx, aSqlCommonDkSni_2; "sql\\common\\dk\\sni\\src\\sm.cpp"
0x100454086  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10045408b  nop
0x10045408c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100454093  jz      short loc_1004540AE
0x100454095  mov     r8d, 221h; int
0x10045409b  lea     rdx, aSmOpennpbasedy; "Sm::OpenNpBasedYukon"
0x1004540a2  lea     rcx, aSqlCommonDkSni_2; "sql\\common\\dk\\sni\\src\\sm.cpp"
0x1004540a9  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x1004540ae  mov     eax, ebx
0x1004540b0  mov     rcx, [rbp+7E0h+var_50]
0x1004540b7  xor     rcx, rsp; StackCookie
0x1004540ba  call    __security_check_cookie
0x1004540bf  add     rsp, 8A8h
0x1004540c6  pop     r15
0x1004540c8  pop     r14
0x1004540ca  pop     r13
0x1004540cc  pop     r12
0x1004540ce  pop     rdi
0x1004540cf  pop     rsi
0x1004540d0  pop     rbx
0x1004540d1  pop     rbp
0x1004540d2  retn
0x1004540d3  lea     rdi, [rcx+2]
0x1004540d7  jmp     loc_100453FD7
0x1004540dc  mov     r8, r12; struct SNI_Provider **
0x1004540df  lea     rdx, [rbp+7E0h+var_860]; struct ProtElem *
0x1004540e3  mov     rcx, r14; struct SNI_Conn *
0x1004540e6  call    ?Open@Np@@SAKPEAVSNI_Conn@@PEAVProtElem@@PEAPEAVSNI_Provider@@@Z; Np::Open(SNI_Conn *,ProtElem *,SNI_Provider * *)
0x1004540eb  mov     ebx, eax
0x1004540ed  test    eax, eax
0x1004540ef  jnz     loc_100454045
0x1004540f5  mov     eax, [r15]
0x1004540f8  mov     [r14+31DCh], eax
0x1004540ff  mov     [r13+0], r14
0x100454103  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045410a  jz      short loc_10045413F
0x10045410c  mov     dword ptr [rsp+8E0h+var_8B0], esi
0x100454110  mov     rax, [r12]
0x100454114  mov     [rsp+8E0h+var_8B8], rax
0x100454119  mov     [rsp+8E0h+var_8C0], r14
0x10045411e  lea     r9, aRetSniPpconnPS; "RET|SNI*ppConn: %p{SNI_Conn*}, *ppProv:"...
0x100454125  mov     r8d, 269h; int
0x10045412b  lea     rdx, aSmOpennpbasedy; "Sm::OpenNpBasedYukon"
0x100454132  lea     rcx, aSqlCommonDkSni_2; "sql\\common\\dk\\sni\\src\\sm.cpp"
0x100454139  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10045413e  nop
0x10045413f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100454146  jz      short loc_100454161
0x100454148  mov     r8d, 221h; int
0x10045414e  lea     rdx, aSmOpennpbasedy; "Sm::OpenNpBasedYukon"
0x100454155  lea     rcx, aSqlCommonDkSni_2; "sql\\common\\dk\\sni\\src\\sm.cpp"
0x10045415c  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100454161  xor     eax, eax
0x100454163  jmp     loc_1004540B0
```
