# LdapGetSicilyPackageList

- ea: `0x1800491d4`
- end: `0x1800494ce`
- name: `LdapGetSicilyPackageList`
- size: `762`
- prototype: `__int64 __fastcall(struct ldap_connection *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x180049d3c`

## callees

- `0x1800037a8`
- `0x180008710`
- `0x18000cad0`
- `0x18000df44`
- `0x180010ef0`
- `0x180011c80`
- `0x180014060`
- `0x180014600`
- `0x1800147f0`
- `0x180014b60`
- `0x18001fb78`
- `0x180029d28`
- `0x18002a284`
- `0x18002a9f8`
- `0x18002b020`
- `0x180034510`
- `0x18003fec8`
- `0x1800491d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049431`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049431`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004947c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049494`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004947c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049494`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800493b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800493b7`

## string_xrefs

- `0x1800493c6`: `ldapGetSicilyList thread 0x%x has connection 0x%x as down.\n`

## pseudocode

```c
__int64 __fastcall LdapGetSicilyPackageList(
        struct ldap_connection *a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned int *a4)
{
  int v4; // eax
  unsigned __int8 *v5; // r14
  __int64 Request; // rax
  __int64 v9; // rbx
  ULONG lm_returncode; // edi
  ULONG v11; // eax
  unsigned int v12; // r9d
  LDAPMessage *v13; // rcx
  DWORD CurrentThreadId; // eax
  CLdapBer *lm_ber; // rax
  struct _RTL_CRITICAL_SECTION *v16; // rcx
  LDAPMessage *res; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+58h] [rbp-A8h]
  int v23; // [rsp+60h] [rbp-A0h]
  __int64 v24; // [rsp+384h] [rbp+284h]
  char v25; // [rsp+398h] [rbp+298h]
  int v26; // [rsp+39Ch] [rbp+29Ch]
  int v27; // [rsp+3A0h] [rbp+2A0h]

  v4 = *((_DWORD *)a1 + 250) - 2;
  v19 = 0;
  v20 = 0;
  v5 = a2;
  v21 = 0;
  v24 = 0;
  v22 = 0;
  LOBYTE(a2) = 96;
  v26 = v4 != 0 ? 0xFDE9 : 0;
  v25 = 0;
  v27 = 0;
  v23 = 0;
  res = 0;
  Request = LdapCreateRequest(a1, a2);
  v9 = Request;
  if ( !Request )
  {
    lm_returncode = 90;
    goto LABEL_34;
  }
  lm_returncode = 83;
  *(_BYTE *)(Request + 185) = 0;
  if ( CLdapBer::HrStartWriteSequence((CLdapBer *)&v19, 0x30u)
    || CLdapBer::HrAddValue((CLdapBer *)&v19, *(_DWORD *)(v9 + 108), 2u)
    || CLdapBer::HrStartWriteSequence((CLdapBer *)&v19, 0x60u)
    || CLdapBer::HrAddValue((CLdapBer *)&v19, *((_DWORD *)a1 + 250), 2u)
    || CLdapBer::HrAddValue((CLdapBer *)&v19, 0, 4u)
    || CLdapBer::HrAddBinaryValue((CLdapBer *)&v19, 0, 0, 0x89u)
    || CLdapBer::HrEndWriteSequence((CLdapBer *)&v19)
    || CLdapBer::HrEndWriteSequence((CLdapBer *)&v19) )
  {
    goto LABEL_24;
  }
  AddToPendingList(v9, a1);
  lm_returncode = LdapSend(a1, (struct CLdapBer *)&v19, 0);
  if ( lm_returncode )
  {
    DecrementPendingList(v9, a1);
    goto LABEL_24;
  }
  v11 = LdapWaitForResponseFromServer(a1, (struct ldap_request *)v9, 0x7530u, 0, &res, 1);
  v13 = res;
  lm_returncode = v11;
  if ( !v11 || res )
  {
    if ( !res )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80u) != 0LL )
      {
        CurrentThreadId = GetCurrentThreadId();
        LDAPClientPrint(
          128,
          "ldapGetSicilyList thread 0x%x has connection 0x%x as down.\n",
          CurrentThreadId,
          (_DWORD)a1);
        v13 = res;
      }
      lm_returncode = 81;
      goto LABEL_25;
    }
    lm_returncode = res->lm_returncode;
    if ( lm_returncode || (lm_ber = (CLdapBer *)res->lm_ber) == 0 )
    {
LABEL_25:
      if ( v13 )
        ldap_msgfree(v13);
      goto LABEL_27;
    }
    lm_returncode = CLdapBer::HrGetBinaryValue(lm_ber, v5, 0x400u, v12, a4) != 0 ? 0x54 : 0;
LABEL_24:
    v13 = res;
    goto LABEL_25;
  }
LABEL_27:
  CloseLdapRequest(v9);
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 48));
  --*(_DWORD *)(v9 + 16);
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
    LDAPClientPrint(4, "LDAP deref req 0x%x, new count = 0x%x\n", v9, *(_DWORD *)(v9 + 16));
  v16 = (struct _RTL_CRITICAL_SECTION *)(v9 + 48);
  if ( *(_DWORD *)(v9 + 16) )
  {
    LeaveCriticalSection(v16);
  }
  else
  {
    LeaveCriticalSection(v16);
    DereferenceLdapRequest2((__int64 *)v9, 0);
  }
LABEL_34:
  CLdapBer::~CLdapBer((CLdapBer *)&v19);
  return lm_returncode;
}

```

## disassembly

```asm
0x1800491d4  push    rbp
0x1800491d6  push    rbx
0x1800491d7  push    rsi
0x1800491d8  push    rdi
0x1800491d9  push    r12
0x1800491db  push    r14
0x1800491dd  push    r15
0x1800491df  lea     rbp, [rsp-2C0h]
0x1800491e7  sub     rsp, 3C0h
0x1800491ee  mov     rax, cs:__security_cookie
0x1800491f5  xor     rax, rsp
0x1800491f8  mov     [rbp+2F0h+var_40], rax
0x1800491ff  mov     eax, [rcx+3E8h]
0x180049205  xor     r12d, r12d
0x180049208  sub     eax, 2
0x18004920b  mov     [rsp+3F0h+var_3B0], r12
0x180049210  neg     eax
0x180049212  mov     [rsp+3F0h+var_3A8], r12d
0x180049217  mov     r14, rdx
0x18004921a  mov     [rsp+3F0h+var_3A0], r12
0x18004921f  sbb     eax, eax
0x180049221  mov     [rbp+2F0h+var_6C], r12
0x180049228  and     eax, 0FDE9h
0x18004922d  mov     [rsp+3F0h+var_398], r12
0x180049232  mov     dl, 60h ; '`'
0x180049234  mov     [rbp+2F0h+var_54], eax
0x18004923a  mov     r15, r9
0x18004923d  mov     [rbp+2F0h+var_58], r12b
0x180049244  mov     rsi, rcx
0x180049247  mov     [rbp+2F0h+var_50], r12d
0x18004924e  mov     [rsp+3F0h+var_390], r12d
0x180049253  mov     [rsp+3F0h+res], r12
0x180049258  call    LdapCreateRequest
0x18004925d  mov     rbx, rax
0x180049260  test    rax, rax
0x180049263  jnz     short loc_18004926D
0x180049265  lea     edi, [rax+5Ah]
0x180049268  jmp     loc_1800494A0
0x18004926d  mov     edi, 53h ; 'S'
0x180049272  mov     [rax+0B9h], r12b
0x180049279  lea     rcx, [rsp+3F0h+var_3B0]; this
0x18004927e  lea     edx, [rdi-23h]; unsigned int
0x180049281  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x180049286  test    eax, eax
0x180049288  jnz     loc_180049413
0x18004928e  mov     edx, [rbx+6Ch]; int
0x180049291  lea     r8d, [rdi-51h]; unsigned int
0x180049295  lea     rcx, [rsp+3F0h+var_3B0]; this
0x18004929a  call    ?HrAddValue@CLdapBer@@QEAAKJK@Z; CLdapBer::HrAddValue(long,ulong)
0x18004929f  test    eax, eax
0x1800492a1  jnz     loc_180049413
0x1800492a7  lea     edx, [rdi+0Dh]; unsigned int
0x1800492aa  lea     rcx, [rsp+3F0h+var_3B0]; this
0x1800492af  call    ?HrStartWriteSequence@CLdapBer@@QEAAKK@Z; CLdapBer::HrStartWriteSequence(ulong)
0x1800492b4  test    eax, eax
0x1800492b6  jnz     loc_180049413
0x1800492bc  mov     edx, [rsi+3E8h]; int
0x1800492c2  lea     r8d, [rdi-51h]; unsigned int
0x1800492c6  lea     rcx, [rsp+3F0h+var_3B0]; this
0x1800492cb  call    ?HrAddValue@CLdapBer@@QEAAKJK@Z; CLdapBer::HrAddValue(long,ulong)
0x1800492d0  test    eax, eax
0x1800492d2  jnz     loc_180049413
0x1800492d8  xor     edx, edx; lpMultiByteStr
0x1800492da  lea     r8d, [rdi-4Fh]; unsigned int
0x1800492de  lea     rcx, [rsp+3F0h+var_3B0]; this
0x1800492e3  call    ?HrAddValue@CLdapBer@@QEAAKPEBDK@Z; CLdapBer::HrAddValue(char const *,ulong)
0x1800492e8  test    eax, eax
0x1800492ea  jnz     loc_180049413
0x1800492f0  lea     r9d, [rdi+36h]; unsigned int
0x1800492f4  xor     r8d, r8d; unsigned int
0x1800492f7  xor     edx, edx; unsigned __int8 *
0x1800492f9  lea     rcx, [rsp+3F0h+var_3B0]; this
0x1800492fe  call    ?HrAddBinaryValue@CLdapBer@@QEAAKPEAEKK@Z; CLdapBer::HrAddBinaryValue(uchar *,ulong,ulong)
0x180049303  test    eax, eax
0x180049305  jnz     loc_180049413
0x18004930b  lea     rcx, [rsp+3F0h+var_3B0]; this
0x180049310  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x180049315  test    eax, eax
0x180049317  jnz     loc_180049413
0x18004931d  lea     rcx, [rsp+3F0h+var_3B0]; this
0x180049322  call    ?HrEndWriteSequence@CLdapBer@@QEAAKXZ; CLdapBer::HrEndWriteSequence(void)
0x180049327  test    eax, eax
0x180049329  jnz     loc_180049413
0x18004932f  mov     rdx, rsi
0x180049332  mov     rcx, rbx
0x180049335  call    AddToPendingList
0x18004933a  xor     r8d, r8d; struct CLdapBer *
0x18004933d  lea     rdx, [rsp+3F0h+var_3B0]; struct CLdapBer *
0x180049342  mov     rcx, rsi; struct ldap_connection *
0x180049345  call    ?LdapSend@@YAKPEAUldap_connection@@PEAVCLdapBer@@1@Z; LdapSend(ldap_connection *,CLdapBer *,CLdapBer *)
0x18004934a  mov     edi, eax
0x18004934c  test    eax, eax
0x18004934e  jz      short loc_180049360
0x180049350  mov     rdx, rsi
0x180049353  mov     rcx, rbx
0x180049356  call    DecrementPendingList
0x18004935b  jmp     loc_180049413
0x180049360  lea     rax, [rsp+3F0h+res]
0x180049365  mov     [rsp+3F0h+var_3C8], 1; char
0x18004936a  xor     r9d, r9d; unsigned int
0x18004936d  mov     [rsp+3F0h+var_3D0], rax; struct ldapmsg **
0x180049372  mov     r8d, 7530h; unsigned int
0x180049378  mov     rdx, rbx; struct ldap_request *
0x18004937b  mov     rcx, rsi; struct ldap_connection *
0x18004937e  call    ?LdapWaitForResponseFromServer@@YAKPEAUldap_connection@@PEAUldap_request@@KKPEAPEAUldapmsg@@E@Z; LdapWaitForResponseFromServer(ldap_connection *,ldap_request *,ulong,ulong,ldapmsg * *,uchar)
0x180049383  mov     rcx, [rsp+3F0h+res]
0x180049388  mov     edi, eax
0x18004938a  test    eax, eax
0x18004938c  jz      short loc_180049397
0x18004938e  test    rcx, rcx
0x180049391  jz      loc_180049422
0x180049397  test    rcx, rcx
0x18004939a  jnz     short loc_1800493E6
0x18004939c  cmp     cs:g_fTracingOn, r12d
0x1800493a3  jz      short loc_1800493DF
0x1800493a5  cmp     cs:g_fProviderEnabled, r12d
0x1800493ac  jz      short loc_1800493DF
0x1800493ae  test    byte ptr cs:g_ulTraceFlags, 80h
0x1800493b5  jz      short loc_1800493DF
0x1800493b7  call    cs:__imp_GetCurrentThreadId
0x1800493be  nop     dword ptr [rax+rax+00h]
0x1800493c3  mov     r9, rsi
0x1800493c6  lea     rdx, aLdapgetsicilyl; "ldapGetSicilyList thread 0x%x has conne"...
0x1800493cd  mov     r8d, eax
0x1800493d0  mov     ecx, 80h
0x1800493d5  call    LDAPClientPrint
0x1800493da  mov     rcx, [rsp+3F0h+res]
0x1800493df  mov     edi, 51h ; 'Q'
0x1800493e4  jmp     short loc_180049418
0x1800493e6  mov     edi, [rcx+38h]
0x1800493e9  test    edi, edi
0x1800493eb  jnz     short loc_180049418
0x1800493ed  mov     rax, [rcx+8]
0x1800493f1  test    rax, rax
0x1800493f4  jz      short loc_180049418
0x1800493f6  mov     r8d, 400h; unsigned int
0x1800493fc  mov     [rsp+3F0h+var_3D0], r15; unsigned int *
0x180049401  mov     rdx, r14; unsigned __int8 *
0x180049404  mov     rcx, rax; this
0x180049407  call    ?HrGetBinaryValue@CLdapBer@@QEAAKPEAEKKPEAK@Z; CLdapBer::HrGetBinaryValue(uchar *,ulong,ulong,ulong *)
0x18004940c  neg     eax
0x18004940e  sbb     edi, edi
0x180049410  and     edi, 54h
0x180049413  mov     rcx, [rsp+3F0h+res]; res
0x180049418  test    rcx, rcx
0x18004941b  jz      short loc_180049422
0x18004941d  call    ldap_msgfree
0x180049422  mov     rcx, rbx
0x180049425  call    CloseLdapRequest
0x18004942a  lea     rsi, [rbx+30h]
0x18004942e  mov     rcx, rsi; lpCriticalSection
0x180049431  call    cs:__imp_EnterCriticalSection
0x180049438  nop     dword ptr [rax+rax+00h]
0x18004943d  dec     dword ptr [rbx+10h]
0x180049440  cmp     cs:g_fTracingOn, r12d
0x180049447  jz      short loc_180049473
0x180049449  cmp     cs:g_fProviderEnabled, r12d
0x180049450  jz      short loc_180049473
0x180049452  test    byte ptr cs:g_ulTraceFlags, 4
0x180049459  jz      short loc_180049473
0x18004945b  mov     r9d, [rbx+10h]
0x18004945f  lea     rdx, aLdapDerefReq0x; "LDAP deref req 0x%x, new count = 0x%x\n"
0x180049466  mov     r8, rbx
0x180049469  mov     ecx, 4
0x18004946e  call    LDAPClientPrint
0x180049473  mov     rcx, rsi; lpCriticalSection
0x180049476  cmp     [rbx+10h], r12d
0x18004947a  jnz     short loc_180049494
0x18004947c  call    cs:__imp_LeaveCriticalSection
0x180049483  nop     dword ptr [rax+rax+00h]
0x180049488  xor     edx, edx
0x18004948a  mov     rcx, rbx
0x18004948d  call    DereferenceLdapRequest2
0x180049492  jmp     short loc_1800494A0
0x180049494  call    cs:__imp_LeaveCriticalSection
0x18004949b  nop     dword ptr [rax+rax+00h]
0x1800494a0  lea     rcx, [rsp+3F0h+var_3B0]; this
0x1800494a5  call    ??1CLdapBer@@QEAA@XZ; CLdapBer::~CLdapBer(void)
0x1800494aa  mov     eax, edi
0x1800494ac  mov     rcx, [rbp+2F0h+var_40]
0x1800494b3  xor     rcx, rsp; StackCookie
0x1800494b6  call    __security_check_cookie
0x1800494bb  add     rsp, 3C0h
0x1800494c2  pop     r15
0x1800494c4  pop     r14
0x1800494c6  pop     r12
0x1800494c8  pop     rdi
0x1800494c9  pop     rsi
0x1800494ca  pop     rbx
0x1800494cb  pop     rbp
0x1800494cc  retn
```
