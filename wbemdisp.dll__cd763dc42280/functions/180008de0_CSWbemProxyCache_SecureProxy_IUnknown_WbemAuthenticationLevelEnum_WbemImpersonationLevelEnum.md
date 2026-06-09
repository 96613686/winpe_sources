# CSWbemProxyCache::SecureProxy(IUnknown *,WbemAuthenticationLevelEnum,WbemImpersonationLevelEnum)

- ea: `0x180008de0`
- end: `0x18000930e`
- name: `?SecureProxy@CSWbemProxyCache@@QEAAXPEAUIUnknown@@W4WbemAuthenticationLevelEnum@@W4WbemImpersonationLevelEnum@@@Z`
- size: `1326`
- prototype: `void(CSWbemProxyCache *__hidden this, struct IUnknown *, enum WbemAuthenticationLevelEnum, enum WbemImpersonationLevelEnum)`
- caller_count: `10`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180003420`
- `0x180006710`
- `0x180006850`
- `0x180007bd0`
- `0x180008230`
- `0x180009320`
- `0x180009b14`
- `0x180009c20`
- `0x18000a270`
- `0x18000a7b0`

## callees

- `0x180006550`
- `0x180008de0`
- `0x18000b0f0`
- `0x18000b2e0`
- `0x18000b30c`
- `0x180019c20`
- `0x180033abc`
- `0x180033b34`
- `0x180033d68`
- `0x180033ed4`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180009185`
- `OLEAUT32!__imp_SysAllocString` at `0x180009185`
- `OLEAUT32!__imp_SysFreeString` at `0x180009151`
- `OLEAUT32!__imp_SysFreeString` at `0x18000919a`
- `OLEAUT32!__imp_SysFreeString` at `0x180009246`
- `OLEAUT32!__imp_SysFreeString` at `0x18000927c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000928b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800092a2`
- `OLEAUT32!__imp_SysFreeString` at `0x180009151`
- `OLEAUT32!__imp_SysFreeString` at `0x18000919a`
- `OLEAUT32!__imp_SysFreeString` at `0x180009246`
- `OLEAUT32!__imp_SysFreeString` at `0x18000927c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000928b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800092a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008e92`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSWbemProxyCache::SecureProxy(
        CSWbemProxyCache *this,
        struct IUnknown *a2,
        unsigned int a3,
        unsigned int a4)
{
  struct _COAUTHIDENTITY *v8; // rdx
  char v9; // al
  unsigned __int16 *v10; // r14
  unsigned int v11; // r13d
  unsigned int v12; // edi
  __int64 v13; // rcx
  struct _COAUTHIDENTITY *v14; // rax
  __int64 v15; // rbx
  int v16; // edi
  struct _COAUTHIDENTITY *v17; // rax
  unsigned __int16 *v18; // rdi
  OLECHAR *v19; // rcx
  const wchar_t *v20; // rdx
  __int64 v21; // rax
  unsigned __int16 v22; // cx
  int v23; // edi
  unsigned __int16 *v24; // rax
  OLECHAR *v25; // rcx
  _BOOL8 v26; // [rsp+40h] [rbp-39h]
  unsigned __int16 *v27; // [rsp+50h] [rbp-29h] BYREF
  struct _COAUTHIDENTITY *pv; // [rsp+58h] [rbp-21h] BYREF
  BSTR v29; // [rsp+60h] [rbp-19h] BYREF
  __int64 v30; // [rsp+68h] [rbp-11h]
  BSTR v31; // [rsp+70h] [rbp-9h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-1h]
  unsigned __int16 *v33; // [rsp+80h] [rbp+7h]
  __int64 v34; // [rsp+88h] [rbp+Fh]
  unsigned __int16 *v35; // [rsp+90h] [rbp+17h]
  LPCRITICAL_SECTION v36[7]; // [rsp+98h] [rbp+1Fh] BYREF
  unsigned int v37; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v38; // [rsp+E8h] [rbp+6Fh] BYREF

  CInCritSec::CInCritSec((CInCritSec *)v36, (struct _RTL_CRITICAL_SECTION *)((char *)this + 16));
  if ( !a2 )
    goto LABEL_8;
  v8 = (struct _COAUTHIDENTITY *)*((_QWORD *)this + 35);
  v9 = *((_BYTE *)this + 320);
  v10 = 0;
  if ( v8 )
  {
    if ( CSWbemSecurity::s_bIsNT && CSWbemSecurity::s_dwNTMajorVersion > 4 && !*((_BYTE *)this + 321) )
      LODWORD(v10) = 32;
    SetInterfaceSecurityEx(a2, v8, *((unsigned __int16 **)this + 36), a3, a4, (unsigned int)v10, *((_BYTE *)this + 320));
    goto LABEL_8;
  }
  v11 = 0;
  if ( CSWbemSecurity::s_bIsNT && CSWbemSecurity::s_dwNTMajorVersion > 4 && !*((_BYTE *)this + 321) )
    v11 = 32;
  v34 = 9;
  v12 = 9;
  v37 = 9;
  v38 = 0;
  v31 = 0;
  v29 = 0;
  v35 = (unsigned __int16 *)*((_QWORD *)this + 39);
  pv = (struct _COAUTHIDENTITY *)*((_QWORD *)this + 38);
  v13 = *((_QWORD *)this + 37);
  v30 = v13;
  if ( v9 )
  {
    v27 = 0;
    if ( !((__int64 (__fastcall *)(struct IUnknown *, GUID *, unsigned __int16 **))a2->lpVtbl->QueryInterface)(
            a2,
            &IID_IClientSecurity,
            &v27) )
    {
      v26 = 0;
      (*(void (__fastcall **)(unsigned __int16 *, struct IUnknown *, unsigned int *, unsigned int *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v27 + 24LL))(
        v27,
        a2,
        &v37,
        &v38,
        0,
        0,
        0,
        0);
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v13 = v30;
    v12 = v37;
  }
  if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && *(_WORD *)v13 )
  {
    v14 = pv;
  }
  else
  {
    v14 = pv;
    if ( (!pv || !LOWORD(pv->User)) && (!v35 || !*v35) )
    {
      if ( v12 == 16 )
      {
        if ( !v13 )
          v13 = -1;
        v30 = v13;
      }
      LODWORD(v29) = v38;
      pv = 0;
      v27 = 0;
      if ( !((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct _COAUTHIDENTITY **))a2->lpVtbl->QueryInterface)(
              a2,
              &IID_IUnknown,
              &pv) )
      {
        if ( !((__int64 (__fastcall *)(struct IUnknown *, GUID *, unsigned __int16 **))a2->lpVtbl->QueryInterface)(
                a2,
                &IID_IClientSecurity,
                &v27) )
        {
          LODWORD(v26) = v11;
          v15 = v30;
          (*(void (__fastcall **)(unsigned __int16 *, struct IUnknown *, _QWORD, _QWORD, __int64, unsigned int, unsigned int, _QWORD, _BOOL8))(*(_QWORD *)v27 + 32LL))(
            v27,
            a2,
            v12,
            (unsigned int)v29,
            v30,
            a3,
            a4,
            0,
            v26);
          (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v27 + 16LL))(v27);
          v27 = 0;
          if ( (unsigned int)DoesContainCredentials(0) )
          {
            if ( !(*(unsigned int (__fastcall **)(struct _COAUTHIDENTITY *, GUID *, unsigned __int16 **))pv->User)(
                    pv,
                    &IID_IClientSecurity,
                    &v27) )
            {
              (*(void (__fastcall **)(unsigned __int16 *, struct _COAUTHIDENTITY *, _QWORD, _QWORD, __int64, unsigned int, unsigned int, _QWORD, unsigned int))(*(_QWORD *)v27 + 32LL))(
                v27,
                pv,
                v12,
                (unsigned int)v29,
                v15,
                a3,
                a4,
                0,
                v11);
              (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v27 + 16LL))(v27);
            }
          }
        }
        (*((void (__fastcall **)(struct _COAUTHIDENTITY *))pv->User + 2))(pv);
      }
      goto LABEL_8;
    }
  }
  v27 = 0;
  if ( v13 )
  {
    v20 = L"KERBEROS:";
    v21 = 9;
    while ( 1 )
    {
      bstrString = (BSTR)v13;
      v33 = (unsigned __int16 *)v20;
      if ( !v21 )
        break;
      v22 = *(_WORD *)v13;
      if ( !v22 && !*v20 )
        break;
      v23 = wbem_towlower(v22);
      if ( v23 != wbem_towlower(*v33) )
      {
        v13 = v30;
        v14 = pv;
        goto LABEL_30;
      }
      v21 = --v34;
      v13 = (__int64)(bstrString + 1);
      v20 = v33 + 1;
    }
    if ( !(unsigned int)IsKerberosAvailable() )
      goto LABEL_8;
    bstrString = SysAllocString((const OLECHAR *)(v30 + 18));
    if ( !bstrString )
    {
      SysFreeString(0);
      goto LABEL_8;
    }
    v16 = DetermineLoginType(&v31, &v29, 0, (const unsigned __int16 *)pv);
    v24 = 0;
    if ( !v16 )
      v24 = bstrString;
    v27 = v24;
    v25 = 0;
    if ( v16 )
      v25 = bstrString;
    SysFreeString(v25);
  }
  else
  {
LABEL_30:
    v16 = DetermineLoginType(&v31, &v29, (const unsigned __int16 *)v13, (const unsigned __int16 *)v14);
  }
  if ( v16 >= 0 )
  {
    v17 = 0;
    pv = 0;
    if ( !v11 && a3 != 1 )
    {
      if ( (int)WbemAllocAuthIdentity(v29, v35, v31, &pv) < 0 )
        goto LABEL_65;
      v17 = pv;
    }
    v18 = v27;
    if ( !v27 )
    {
      if ( v37 == 16 )
        v18 = (unsigned __int16 *)-1LL;
      v27 = v18;
    }
    if ( (int)WbemSetProxyBlanket(a2, v37, v38, v18, a3, a4, v17, v11, v26) >= 0 )
    {
      *((_QWORD *)this + 35) = pv;
LABEL_68:
      if ( v29 )
        SysFreeString(v29);
      if ( v31 )
        SysFreeString(v31);
      if ( (unsigned __int64)v10 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        SysFreeString(v10);
      if ( (unsigned __int64)v18 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v19 = (OLECHAR *)*((_QWORD *)this + 36);
        if ( v19 )
          SysFreeString(v19);
        *((_QWORD *)this + 36) = v18;
      }
      goto LABEL_8;
    }
LABEL_65:
    v18 = 0;
    if ( pv )
      WbemFreeAuthIdentity(pv);
    v10 = v27;
    goto LABEL_68;
  }
LABEL_8:
  LeaveCriticalSection(v36[0]);
}

```

## disassembly

```asm
0x180008de0  mov     [rsp-8+arg_10], rbx
0x180008de5  push    rbp
0x180008de6  push    rsi
0x180008de7  push    rdi
0x180008de8  push    r12
0x180008dea  push    r13
0x180008dec  push    r14
0x180008dee  push    r15
0x180008df0  lea     rbp, [rsp-27h]
0x180008df5  sub     rsp, 0A0h
0x180008dfc  mov     r12d, r9d
0x180008dff  mov     r15d, r8d
0x180008e02  mov     rsi, rdx
0x180008e05  mov     rbx, rcx
0x180008e08  lea     rdx, [rcx+10h]; struct _RTL_CRITICAL_SECTION *
0x180008e0c  lea     rcx, [rbp+57h+var_38]; this
0x180008e10  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180008e15  nop
0x180008e16  test    rsi, rsi
0x180008e19  jz      short loc_180008E74
0x180008e1b  mov     rdx, [rbx+118h]; struct _COAUTHIDENTITY *
0x180008e22  movzx   eax, byte ptr [rbx+140h]
0x180008e29  xor     r14d, r14d
0x180008e2c  test    rdx, rdx
0x180008e2f  jz      short loc_180008E99
0x180008e31  cmp     cs:?s_bIsNT@CSWbemSecurity@@0_NA, r14b; bool CSWbemSecurity::s_bIsNT
0x180008e38  jz      short loc_180008E53
0x180008e3a  cmp     cs:?s_dwNTMajorVersion@CSWbemSecurity@@0KA, 4; ulong CSWbemSecurity::s_dwNTMajorVersion
0x180008e41  jbe     short loc_180008E53
0x180008e43  mov     ecx, 20h ; ' '
0x180008e48  cmp     [rbx+141h], r14b
0x180008e4f  cmovz   r14d, ecx
0x180008e53  mov     byte ptr [rsp+0D0h+var_A0], al; bool
0x180008e57  mov     [rsp+0D0h+var_A8], r14d; unsigned int
0x180008e5c  mov     [rsp+0D0h+var_B0], r12d; unsigned int
0x180008e61  mov     r9d, r15d; unsigned int
0x180008e64  mov     r8, [rbx+120h]; unsigned __int16 *
0x180008e6b  mov     rcx, rsi; struct IUnknown *
0x180008e6e  call    ?SetInterfaceSecurityEx@@YAJPEAUIUnknown@@PEAU_COAUTHIDENTITY@@PEAGKKK_N@Z; SetInterfaceSecurityEx(IUnknown *,_COAUTHIDENTITY *,ushort *,ulong,ulong,ulong,bool)
0x180008e73  nop
0x180008e74  mov     rcx, [rbp+57h+var_38]
0x180008e78  mov     rbx, [rsp+0D0h+arg_10]
0x180008e80  add     rsp, 0A0h
0x180008e87  pop     r15
0x180008e89  pop     r14
0x180008e8b  pop     r13
0x180008e8d  pop     r12
0x180008e8f  pop     rdi
0x180008e90  pop     rsi
0x180008e91  pop     rbp
0x180008e92  jmp     cs:__imp_LeaveCriticalSection
0x180008e99  mov     r13d, r14d
0x180008e9c  cmp     cs:?s_bIsNT@CSWbemSecurity@@0_NA, r13b; bool CSWbemSecurity::s_bIsNT
0x180008ea3  jz      short loc_180008EBE
0x180008ea5  cmp     cs:?s_dwNTMajorVersion@CSWbemSecurity@@0KA, 4; ulong CSWbemSecurity::s_dwNTMajorVersion
0x180008eac  jbe     short loc_180008EBE
0x180008eae  mov     ecx, 20h ; ' '
0x180008eb3  cmp     [rbx+141h], r13b
0x180008eba  cmovz   r13d, ecx
0x180008ebe  mov     ecx, 9
0x180008ec3  mov     [rbp+57h+var_48], rcx
0x180008ec7  mov     edi, ecx
0x180008ec9  mov     [rbp+57h+arg_0], ecx
0x180008ecc  mov     [rbp+57h+arg_8], r14d
0x180008ed0  mov     [rbp+57h+var_60], r14
0x180008ed4  mov     [rbp+57h+var_70], r14
0x180008ed8  mov     rcx, [rbx+138h]
0x180008edf  mov     [rbp+57h+var_40], rcx
0x180008ee3  mov     rcx, [rbx+130h]
0x180008eea  mov     [rbp+57h+pv], rcx
0x180008eee  mov     rcx, [rbx+128h]
0x180008ef5  mov     [rbp+57h+var_68], rcx
0x180008ef9  test    al, al
0x180008efb  jz      short loc_180008F69
0x180008efd  mov     [rbp+57h+var_80], r14
0x180008f01  mov     rax, [rsi]
0x180008f04  lea     r8, [rbp+57h+var_80]
0x180008f08  lea     rdx, IID_IClientSecurity
0x180008f0f  mov     rcx, rsi
0x180008f12  mov     rax, [rax]
0x180008f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f1a  test    eax, eax
0x180008f1c  jnz     short loc_180008F62
0x180008f1e  mov     rcx, [rbp+57h+var_80]
0x180008f22  mov     rax, [rcx]
0x180008f25  mov     qword ptr [rsp+0D0h+var_90], r14; bool
0x180008f2a  mov     qword ptr [rsp+0D0h+var_98], r14
0x180008f2f  mov     [rsp+0D0h+var_A0], r14
0x180008f34  mov     qword ptr [rsp+0D0h+var_A8], r14
0x180008f39  mov     qword ptr [rsp+0D0h+var_B0], r14
0x180008f3e  lea     r9, [rbp+57h+arg_8]
0x180008f42  lea     r8, [rbp+57h+arg_0]
0x180008f46  mov     rdx, rsi
0x180008f49  mov     rax, [rax+18h]
0x180008f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f52  mov     rcx, [rbp+57h+var_80]
0x180008f56  mov     rax, [rcx]
0x180008f59  mov     rax, [rax+10h]
0x180008f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f62  mov     rcx, [rbp+57h+var_68]
0x180008f66  mov     edi, [rbp+57h+arg_0]
0x180008f69  lea     rax, [rcx-1]
0x180008f6d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008f71  jbe     loc_180009073
0x180008f77  mov     rax, [rbp+57h+pv]
0x180008f7b  test    rax, rax
0x180008f7e  jnz     loc_1800091A5
0x180008f84  mov     rdx, [rbp+57h+var_40]
0x180008f88  test    rdx, rdx
0x180008f8b  jnz     loc_1800091B4
0x180008f91  cmp     edi, 10h
0x180008f94  jz      loc_1800092AD
0x180008f9a  mov     eax, [rbp+57h+arg_8]
0x180008f9d  mov     dword ptr [rbp+57h+var_70], eax
0x180008fa0  mov     [rbp+57h+pv], r14
0x180008fa4  mov     [rbp+57h+var_80], r14
0x180008fa8  mov     rax, [rsi]
0x180008fab  lea     r8, [rbp+57h+pv]
0x180008faf  lea     rdx, IID_IUnknown
0x180008fb6  mov     rcx, rsi
0x180008fb9  mov     rax, [rax]
0x180008fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fc1  test    eax, eax
0x180008fc3  jnz     loc_180008E74
0x180008fc9  mov     rax, [rsi]
0x180008fcc  lea     r8, [rbp+57h+var_80]
0x180008fd0  lea     rdx, IID_IClientSecurity
0x180008fd7  mov     rcx, rsi
0x180008fda  mov     rax, [rax]
0x180008fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fe2  test    eax, eax
0x180008fe4  jnz     short loc_18000905E
0x180008fe6  mov     rcx, [rbp+57h+var_80]
0x180008fea  mov     rax, [rcx]
0x180008fed  mov     dword ptr [rsp+0D0h+var_90], r13d
0x180008ff2  mov     qword ptr [rsp+0D0h+var_98], r14
0x180008ff7  mov     dword ptr [rsp+0D0h+var_A0], r12d
0x180008ffc  mov     [rsp+0D0h+var_A8], r15d
0x180009001  mov     rbx, [rbp+57h+var_68]
0x180009005  mov     qword ptr [rsp+0D0h+var_B0], rbx
0x18000900a  mov     r9d, dword ptr [rbp+57h+var_70]
0x18000900e  mov     r8d, edi
0x180009011  mov     rdx, rsi
0x180009014  mov     rax, [rax+20h]
0x180009018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000901d  mov     rcx, [rbp+57h+var_80]
0x180009021  mov     rax, [rcx]
0x180009024  mov     rax, [rax+10h]
0x180009028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000902d  mov     [rbp+57h+var_80], r14
0x180009031  xor     ecx, ecx; struct _COAUTHIDENTITY *
0x180009033  call    ?DoesContainCredentials@@YAHPEAU_COAUTHIDENTITY@@@Z; DoesContainCredentials(_COAUTHIDENTITY *)
0x180009038  test    eax, eax
0x18000903a  jz      short loc_18000905E
0x18000903c  mov     rcx, [rbp+57h+pv]
0x180009040  mov     rax, [rcx]
0x180009043  lea     r8, [rbp+57h+var_80]
0x180009047  lea     rdx, IID_IClientSecurity
0x18000904e  mov     rax, [rax]
0x180009051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009056  test    eax, eax
0x180009058  jz      loc_1800092C4
0x18000905e  mov     rcx, [rbp+57h+pv]
0x180009062  mov     rax, [rcx]
0x180009065  mov     rax, [rax+10h]
0x180009069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000906e  jmp     loc_180008E74
0x180009073  cmp     [rcx], r14w
0x180009077  jz      loc_180008F77
0x18000907d  mov     rax, [rbp+57h+pv]
0x180009081  mov     [rbp+57h+var_80], r14
0x180009085  test    rcx, rcx
0x180009088  jnz     loc_1800091C3
0x18000908e  mov     r9, rax; unsigned __int16 *
0x180009091  mov     r8, rcx; unsigned __int16 *
0x180009094  lea     rdx, [rbp+57h+var_70]; unsigned __int16 **
0x180009098  lea     rcx, [rbp+57h+var_60]; unsigned __int16 **
0x18000909c  call    ?DetermineLoginType@@YAJAEAPEAG0PEBG1@Z; DetermineLoginType(ushort * &,ushort * &,ushort const *,ushort const *)
0x1800090a1  mov     edi, eax
0x1800090a3  test    edi, edi
0x1800090a5  js      loc_180008E74
0x1800090ab  mov     rax, r14
0x1800090ae  mov     [rbp+57h+pv], rax
0x1800090b2  test    r13d, r13d
0x1800090b5  jnz     short loc_1800090DE
0x1800090b7  cmp     r15d, 1
0x1800090bb  jz      short loc_1800090DE
0x1800090bd  lea     r9, [rbp+57h+pv]; struct _COAUTHIDENTITY **
0x1800090c1  mov     r8, [rbp+57h+var_60]; unsigned __int16 *
0x1800090c5  mov     rdx, [rbp+57h+var_40]; unsigned __int16 *
0x1800090c9  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x1800090cd  call    ?WbemAllocAuthIdentity@@YAJPEBG00PEAPEAU_COAUTHIDENTITY@@@Z; WbemAllocAuthIdentity(ushort const *,ushort const *,ushort const *,_COAUTHIDENTITY * *)
0x1800090d2  test    eax, eax
0x1800090d4  js      loc_18000925E
0x1800090da  mov     rax, [rbp+57h+pv]
0x1800090de  mov     edx, [rbp+57h+arg_0]; unsigned int
0x1800090e1  mov     rdi, [rbp+57h+var_80]
0x1800090e5  test    rdi, rdi
0x1800090e8  jnz     short loc_1800090FC
0x1800090ea  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800090f1  cmp     edx, 10h
0x1800090f4  cmovz   rdi, r8
0x1800090f8  mov     [rbp+57h+var_80], rdi
0x1800090fc  mov     [rsp+0D0h+var_98], r13d; unsigned int
0x180009101  mov     [rsp+0D0h+var_A0], rax; struct _COAUTHIDENTITY *
0x180009106  mov     [rsp+0D0h+var_A8], r12d; unsigned int
0x18000910b  mov     [rsp+0D0h+var_B0], r15d; unsigned int
0x180009110  mov     r9, rdi; unsigned __int16 *
0x180009113  mov     r8d, [rbp+57h+arg_8]; unsigned int
0x180009117  mov     rcx, rsi; struct IUnknown *
0x18000911a  call    ?WbemSetProxyBlanket@@YAJPEAUIUnknown@@KKPEAGKKPEAXK_N@Z; WbemSetProxyBlanket(IUnknown *,ulong,ulong,ushort *,ulong,ulong,void *,ulong,bool)
0x18000911f  test    eax, eax
0x180009121  js      loc_18000925E
0x180009127  mov     rcx, [rbp+57h+pv]
0x18000912b  mov     [rbx+118h], rcx
0x180009132  jmp     loc_180009273
0x180009137  lea     rax, [rdi-1]
0x18000913b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000913f  ja      loc_180008E74
0x180009145  mov     rcx, [rbx+120h]; bstrString
0x18000914c  test    rcx, rcx
0x18000914f  jz      short loc_180009157
0x180009151  call    cs:__imp_SysFreeString
0x180009157  mov     [rbx+120h], rdi
0x18000915e  jmp     loc_180008E74
0x180009163  mov     [rbp+57h+bstrString], rcx
0x180009167  mov     [rbp+57h+var_50], rdx
0x18000916b  test    rax, rax
0x18000916e  jnz     short loc_1800091D1
0x180009170  call    ?IsKerberosAvailable@@YAHXZ; IsKerberosAvailable(void)
0x180009175  test    eax, eax
0x180009177  jz      loc_180008E74
0x18000917d  mov     rcx, [rbp+57h+var_68]
0x180009181  add     rcx, 12h; psz
0x180009185  call    cs:__imp_SysAllocString
0x18000918b  mov     [rbp+57h+bstrString], rax
0x18000918f  test    rax, rax
0x180009192  jnz     loc_18000921A
0x180009198  xor     ecx, ecx; bstrString
0x18000919a  call    cs:__imp_SysFreeString
0x1800091a0  jmp     loc_180008E74
0x1800091a5  cmp     [rax], r14w
0x1800091a9  jnz     loc_180009081
0x1800091af  jmp     loc_180008F84
0x1800091b4  cmp     [rdx], r14w
0x1800091b8  jz      loc_180008F91
0x1800091be  jmp     loc_180009081
0x1800091c3  lea     rdx, aKerberos; "KERBEROS:"
0x1800091ca  mov     eax, 9
0x1800091cf  jmp     short loc_180009163
0x1800091d1  movzx   ecx, word ptr [rcx]; unsigned __int16
0x1800091d4  test    cx, cx
0x1800091d7  jnz     short loc_1800091DF
0x1800091d9  cmp     [rdx], r14w
0x1800091dd  jz      short loc_180009170
0x1800091df  call    ?wbem_towlower@@YAGG@Z; wbem_towlower(ushort)
0x1800091e4  movzx   edi, ax
0x1800091e7  mov     rcx, [rbp+57h+var_50]
0x1800091eb  movzx   ecx, word ptr [rcx]; unsigned __int16
0x1800091ee  call    ?wbem_towlower@@YAGG@Z; wbem_towlower(ushort)
0x1800091f3  movzx   eax, ax
0x1800091f6  cmp     edi, eax
0x1800091f8  jnz     short loc_180009251
0x1800091fa  mov     rax, [rbp+57h+var_48]
0x1800091fe  dec     rax
0x180009201  mov     [rbp+57h+var_48], rax
0x180009205  mov     rcx, [rbp+57h+bstrString]
0x180009209  add     rcx, 2
0x18000920d  mov     rdx, [rbp+57h+var_50]
0x180009211  add     rdx, 2
0x180009215  jmp     loc_180009163
0x18000921a  mov     r9, [rbp+57h+pv]; unsigned __int16 *
0x18000921e  xor     r8d, r8d; unsigned __int16 *
0x180009221  lea     rdx, [rbp+57h+var_70]; unsigned __int16 **
0x180009225  lea     rcx, [rbp+57h+var_60]; unsigned __int16 **
0x180009229  call    ?DetermineLoginType@@YAJAEAPEAG0PEBG1@Z; DetermineLoginType(ushort * &,ushort * &,ushort const *,ushort const *)
0x18000922e  mov     edi, eax
0x180009230  mov     rax, r14
0x180009233  test    edi, edi
0x180009235  cmovz   rax, [rbp+57h+bstrString]
0x18000923a  mov     [rbp+57h+var_80], rax
0x18000923e  mov     rcx, r14
0x180009241  cmovnz  rcx, [rbp+57h+bstrString]; bstrString
0x180009246  call    cs:__imp_SysFreeString
0x18000924c  jmp     loc_1800090A3
0x180009251  mov     rcx, [rbp+57h+var_68]
0x180009255  mov     rax, [rbp+57h+pv]
0x180009259  jmp     loc_18000908E
0x18000925e  mov     rdi, r14
0x180009261  mov     rcx, [rbp+57h+pv]; pv
0x180009265  test    rcx, rcx
0x180009268  jz      short loc_18000926F
0x18000926a  call    ?WbemFreeAuthIdentity@@YAJPEAU_COAUTHIDENTITY@@@Z; WbemFreeAuthIdentity(_COAUTHIDENTITY *)
0x18000926f  mov     r14, [rbp+57h+var_80]
0x180009273  mov     rcx, [rbp+57h+var_70]; bstrString
0x180009277  test    rcx, rcx
0x18000927a  jz      short loc_180009282
0x18000927c  call    cs:__imp_SysFreeString
0x180009282  mov     rcx, [rbp+57h+var_60]; bstrString
0x180009286  test    rcx, rcx
  ... truncated ...
```
