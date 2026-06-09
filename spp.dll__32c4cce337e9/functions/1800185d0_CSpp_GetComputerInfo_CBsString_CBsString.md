# CSpp::_GetComputerInfo(CBsString *,CBsString *)

- ea: `0x1800185d0`
- end: `0x18001883b`
- name: `?_GetComputerInfo@CSpp@@AEAAJPEAVCBsString@@0@Z`
- size: `619`
- prototype: `__int64 __fastcall(CSpp *this, struct CBsString *, struct CBsString *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001176c`

## callees

- `0x1800185d0`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x18002d778`
- `0x180034f3c`
- `0x18003532c`
- `0x18003534c`
- `0x18003540c`
- `0x180035b00`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x1800186ed`
- `KERNEL32!GetComputerNameW` at `0x1800186ed`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800187f2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800187f2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001873f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001873f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001876e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001876e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800187de`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800187de`

## string_xrefs

- `0x18001862f`: `CSpp::_GetComputerInfo`

## pseudocode

```c
__int64 __fastcall CSpp::_GetComputerInfo(CSpp *this, struct CBsString *a2, struct CBsString *a3)
{
  __int16 v5; // ax
  __int64 v6; // rcx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  DWORD nSize; // [rsp+20h] [rbp-89h] BYREF
  PVOID v14; // [rsp+28h] [rbp-81h] BYREF
  PVOID PolicyHandle; // [rsp+30h] [rbp-79h] BYREF
  int LastFailureAsHRESULT; // [rsp+38h] [rbp-71h] BYREF
  __int16 v17; // [rsp+3Ch] [rbp-6Dh]
  __int16 v18; // [rsp+3Eh] [rbp-6Bh]
  _QWORD v19[2]; // [rsp+70h] [rbp-39h] BYREF
  _QWORD v20[2]; // [rsp+80h] [rbp-29h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-19h] BYREF
  WCHAR Buffer[16]; // [rsp+C0h] [rbp+17h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "CSpp::_GetComputerInfo", 3981, 1);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v14 = 0;
  PolicyHandle = 0;
  memset(Buffer, 0, sizeof(Buffer));
  nSize = 0;
  v20[0] = &FileName;
  v20[1] = 0;
  v19[0] = &FileName;
  v19[1] = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  if ( a2 )
    CBsString::Empty(a2);
  if ( a3 )
    CBsString::Empty(a3);
  v5 = 4002;
  if ( !a2 || (v17 = 4002, v5 = 4003, !a3) )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_10:
    v18 = v5;
    goto LABEL_19;
  }
  LastFailureAsHRESULT = 0;
  v17 = 4003;
  nSize = 16;
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6);
    v5 = 4006;
    goto LABEL_10;
  }
  LastFailureAsHRESULT = 0;
  v17 = 4006;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)v20, Buffer);
  v5 = 4007;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_10;
  v17 = 4007;
  v7 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  LastFailureAsHRESULT = HRESULTFromNTSTATUS(v7);
  v5 = 4009;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_10;
  v17 = 4009;
  v8 = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, &v14);
  LastFailureAsHRESULT = HRESULTFromNTSTATUS(v8);
  v5 = 4011;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_10;
  v17 = 4011;
  LastFailureAsHRESULT = CBsString::Set(
                           (CBsString *)v19,
                           *((const unsigned __int16 **)v14 + 1),
                           *(unsigned __int16 *)v14 >> 1);
  v5 = 4020;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_10;
  v17 = 4020;
  CBsString::Transfer((CBsString *)v20, a2);
  CBsString::Transfer((CBsString *)v19, a3);
LABEL_19:
  if ( v14 )
  {
    LsaFreeMemory(v14);
    v14 = 0;
  }
  if ( PolicyHandle )
  {
    LsaClose(PolicyHandle);
    PolicyHandle = 0;
  }
  v9 = LastFailureAsHRESULT;
  CBsString::_Release((CBsString *)v19);
  CBsString::_Release((CBsString *)v20);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, v10, v11);
  return v9;
}

```

## disassembly

```asm
0x1800185d0  mov     [rsp-8+arg_0], rbx
0x1800185d5  push    rbp
0x1800185d6  push    rsi
0x1800185d7  push    rdi
0x1800185d8  lea     rbp, [rsp-47h]
0x1800185dd  sub     rsp, 0F0h
0x1800185e4  mov     rax, cs:__security_cookie
0x1800185eb  xor     rax, rsp
0x1800185ee  mov     [rbp+57h+var_20], rax
0x1800185f2  mov     rbx, r8
0x1800185f5  mov     rdi, rdx
0x1800185f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185ff  lea     rax, WPP_GLOBAL_Control
0x180018606  cmp     rcx, rax
0x180018609  jz      short loc_180018629
0x18001860b  test    dword ptr [rcx+1Ch], 20000000h
0x180018612  jz      short loc_180018629
0x180018614  mov     rcx, [rcx+10h]
0x180018618  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001861f  mov     edx, 33h ; '3'
0x180018624  call    WPP_SF_
0x180018629  mov     r9d, 1; unsigned __int16
0x18001862f  lea     rdx, aCsppGetcompute; "CSpp::_GetComputerInfo"
0x180018636  mov     r8d, 0F8Dh; unsigned __int16
0x18001863c  lea     rcx, [rbp+57h+var_C8]; this
0x180018640  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180018645  xor     esi, esi
0x180018647  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001864f  mov     [rsp+100h+var_D8], rsi
0x180018654  xorps   xmm0, xmm0
0x180018657  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], rsi
0x18001865b  lea     rax, FileName
0x180018662  mov     [rbp+57h+PolicyHandle], rsi
0x180018666  xorps   xmm1, xmm1
0x180018669  mov     [rbp+57h+Buffer], si
0x18001866d  mov     [rsp+100h+nSize], esi
0x180018671  mov     [rbp+57h+var_80], rax
0x180018675  mov     [rbp+57h+var_78], rsi
0x180018679  mov     [rbp+57h+var_90], rax
0x18001867d  mov     [rbp+57h+var_88], rsi
0x180018681  movups  xmmword ptr [rbp+57h+var_3E], xmm0
0x180018685  movups  xmmword ptr [rbp+57h+var_3E+0Eh], xmm0
0x180018689  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.RootDirectory], xmm0
0x18001868e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x180018693  test    rdi, rdi
0x180018696  jz      short loc_1800186A0
0x180018698  mov     rcx, rdi; this
0x18001869b  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x1800186a0  test    rbx, rbx
0x1800186a3  jz      short loc_1800186AD
0x1800186a5  mov     rcx, rbx; this
0x1800186a8  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x1800186ad  mov     eax, 0FA2h
0x1800186b2  test    rdi, rdi
0x1800186b5  jnz     short loc_1800186C7
0x1800186b7  mov     [rbp+57h+var_C8], 80070057h
0x1800186be  mov     [rbp+57h+var_C2], ax
0x1800186c2  jmp     loc_1800187D4
0x1800186c7  mov     [rbp+57h+var_C4], ax
0x1800186cb  mov     eax, 0FA3h
0x1800186d0  test    rbx, rbx
0x1800186d3  jz      short loc_1800186B7
0x1800186d5  lea     rdx, [rsp+100h+nSize]; nSize
0x1800186da  mov     [rbp+57h+var_C8], esi
0x1800186dd  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x1800186e1  mov     [rbp+57h+var_C4], ax
0x1800186e5  mov     [rsp+100h+nSize], 10h
0x1800186ed  call    cs:__imp_GetComputerNameW
0x1800186f3  test    eax, eax
0x1800186f5  jnz     short loc_180018706
0x1800186f7  call    GetLastFailureAsHRESULT
0x1800186fc  mov     [rbp+57h+var_C8], eax
0x1800186ff  mov     eax, 0FA6h
0x180018704  jmp     short loc_1800186BE
0x180018706  mov     eax, 0FA6h
0x18001870b  mov     [rbp+57h+var_C8], esi
0x18001870e  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 *
0x180018712  mov     [rbp+57h+var_C4], ax
0x180018716  lea     rcx, [rbp+57h+var_80]; this
0x18001871a  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001871f  mov     [rbp+57h+var_C8], eax
0x180018722  test    eax, eax
0x180018724  mov     eax, 0FA7h
0x180018729  js      short loc_1800186BE
0x18001872b  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18001872f  mov     [rbp+57h+var_C4], ax
0x180018733  mov     r8d, 1; DesiredAccess
0x180018739  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001873d  xor     ecx, ecx; SystemName
0x18001873f  call    cs:__imp_LsaOpenPolicy
0x180018745  mov     ecx, eax
0x180018747  call    HRESULTFromNTSTATUS
0x18001874c  mov     [rbp+57h+var_C8], eax
0x18001874f  test    eax, eax
0x180018751  mov     eax, 0FA9h
0x180018756  js      loc_1800186BE
0x18001875c  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x180018760  lea     r8, [rsp+100h+var_D8]; Buffer
0x180018765  mov     edx, 3; InformationClass
0x18001876a  mov     [rbp+57h+var_C4], ax
0x18001876e  call    cs:__imp_LsaQueryInformationPolicy
0x180018774  mov     ecx, eax
0x180018776  call    HRESULTFromNTSTATUS
0x18001877b  mov     [rbp+57h+var_C8], eax
0x18001877e  test    eax, eax
0x180018780  mov     eax, 0FABh
0x180018785  js      loc_1800186BE
0x18001878b  mov     rdx, [rsp+100h+var_D8]
0x180018790  lea     rcx, [rbp+57h+var_90]; this
0x180018794  mov     [rbp+57h+var_C4], ax
0x180018798  movzx   r8d, word ptr [rdx]
0x18001879c  mov     rdx, [rdx+8]; unsigned __int16 *
0x1800187a0  shr     r8d, 1; unsigned int
0x1800187a3  call    ?Set@CBsString@@QEAAJPEBGK@Z; CBsString::Set(ushort const *,ulong)
0x1800187a8  mov     [rbp+57h+var_C8], eax
0x1800187ab  test    eax, eax
0x1800187ad  mov     eax, 0FB4h
0x1800187b2  js      loc_1800186BE
0x1800187b8  mov     rdx, rdi; struct CBsString *
0x1800187bb  mov     [rbp+57h+var_C4], ax
0x1800187bf  lea     rcx, [rbp+57h+var_80]; this
0x1800187c3  call    ?Transfer@CBsString@@QEAAXPEAV1@@Z; CBsString::Transfer(CBsString *)
0x1800187c8  mov     rdx, rbx; struct CBsString *
0x1800187cb  lea     rcx, [rbp+57h+var_90]; this
0x1800187cf  call    ?Transfer@CBsString@@QEAAXPEAV1@@Z; CBsString::Transfer(CBsString *)
0x1800187d4  mov     rcx, [rsp+100h+var_D8]; Buffer
0x1800187d9  test    rcx, rcx
0x1800187dc  jz      short loc_1800187E9
0x1800187de  call    cs:__imp_LsaFreeMemory
0x1800187e4  mov     [rsp+100h+var_D8], rsi
0x1800187e9  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x1800187ed  test    rcx, rcx
0x1800187f0  jz      short loc_1800187FC
0x1800187f2  call    cs:__imp_LsaClose
0x1800187f8  mov     [rbp+57h+PolicyHandle], rsi
0x1800187fc  mov     ebx, [rbp+57h+var_C8]
0x1800187ff  lea     rcx, [rbp+57h+var_90]; this
0x180018803  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180018808  lea     rcx, [rbp+57h+var_80]; this
0x18001880c  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180018811  lea     rcx, [rbp+57h+var_C8]; this
0x180018815  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001881a  mov     eax, ebx
0x18001881c  mov     rcx, [rbp+57h+var_20]
0x180018820  xor     rcx, rsp; StackCookie
0x180018823  call    __security_check_cookie
0x180018828  mov     rbx, [rsp+100h+arg_0]
0x180018830  add     rsp, 0F0h
0x180018837  pop     rdi
0x180018838  pop     rsi
0x180018839  pop     rbp
0x18001883a  retn
```
