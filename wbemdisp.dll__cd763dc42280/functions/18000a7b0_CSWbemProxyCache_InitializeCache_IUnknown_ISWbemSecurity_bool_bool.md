# CSWbemProxyCache::InitializeCache(IUnknown *,ISWbemSecurity *,bool,bool)

- ea: `0x18000a7b0`
- end: `0x18000aea4`
- name: `?InitializeCache@CSWbemProxyCache@@AEAAXPEAUIUnknown@@PEAUISWbemSecurity@@_N2@Z`
- size: `1780`
- prototype: `void __usercall(CSWbemProxyCache *__hidden this@<rcx>, struct IUnknown *@<rdx>, struct ISWbemSecurity *@<r8>, bool@<r9b>, bool)`
- caller_count: `4`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180009c20`
- `0x18000a150`
- `0x18000a270`
- `0x18001cc78`

## callees

- `0x180006550`
- `0x180008de0`
- `0x18000a7b0`
- `0x18000b0f0`
- `0x18000b30c`
- `0x18000b70c`
- `0x180019c20`
- `0x180033abc`
- `0x180033b34`
- `0x180033d68`
- `0x180033ed4`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000ad27`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ad27`
- `OLEAUT32!__imp_SysFreeString` at `0x18000acf7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad3b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae0d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae41`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae50`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae67`
- `OLEAUT32!__imp_SysFreeString` at `0x18000acf7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad3b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae0d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae41`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae50`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa53`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSWbemProxyCache::InitializeCache(
        CSWbemProxyCache *this,
        struct IUnknown *a2,
        struct ISWbemSecurity *a3,
        char a4,
        bool a5)
{
  unsigned int *v9; // r14
  bool v10; // zf
  unsigned int *v11; // r15
  int v12; // eax
  unsigned int v13; // r12d
  unsigned int v14; // r14d
  struct IUnknown *v15; // rsi
  struct _COAUTHIDENTITY *v16; // rdx
  unsigned int v17; // eax
  void (*AddRef)(void); // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  unsigned int Capabilities; // ecx
  __int64 v22; // r9
  unsigned int v23; // r10d
  const unsigned __int16 *v24; // rdi
  const unsigned __int16 *v25; // r13
  __int64 v26; // r15
  char v27; // r8
  int v28; // r15d
  struct _COAUTHIDENTITY *v29; // r15
  unsigned int v30; // r13d
  int v31; // eax
  unsigned __int16 *v32; // rdi
  unsigned __int16 *v33; // rsi
  OLECHAR *v34; // rcx
  BSTR v35; // rdi
  struct _COAUTHIDENTITY *v36; // rax
  unsigned __int16 *v37; // rcx
  unsigned __int16 v38; // cx
  int v39; // edi
  unsigned __int16 *v40; // rax
  OLECHAR *v41; // rcx
  unsigned int *v42; // [rsp+40h] [rbp-71h]
  unsigned int v43; // [rsp+50h] [rbp-61h] BYREF
  struct _COAUTHIDENTITY *pv; // [rsp+58h] [rbp-59h] BYREF
  int v45; // [rsp+60h] [rbp-51h] BYREF
  unsigned int v46; // [rsp+64h] [rbp-4Dh] BYREF
  unsigned int v47; // [rsp+68h] [rbp-49h] BYREF
  BSTR v48; // [rsp+70h] [rbp-41h] BYREF
  unsigned __int16 *v49; // [rsp+78h] [rbp-39h]
  BSTR bstrString; // [rsp+80h] [rbp-31h] BYREF
  struct IUnknown *v51; // [rsp+88h] [rbp-29h] BYREF
  __int64 v52; // [rsp+90h] [rbp-21h] BYREF
  __int64 v53; // [rsp+98h] [rbp-19h]
  unsigned __int16 *v54; // [rsp+A0h] [rbp-11h]
  const unsigned __int16 *v55; // [rsp+A8h] [rbp-9h]
  LPCRITICAL_SECTION lpCriticalSection[10]; // [rsp+B0h] [rbp-1h] BYREF
  int v57; // [rsp+118h] [rbp+67h] BYREF

  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  v57 = 2;
  v45 = 3;
  if ( !a2 )
  {
    *((_DWORD *)this + 81) = 2;
    *((_DWORD *)this + 82) = 3;
    return;
  }
  v48 = 0;
  if ( !((__int64 (__fastcall *)(struct IUnknown *, GUID *, BSTR *))a2->lpVtbl->QueryInterface)(
          a2,
          &IID_IClientSecurity,
          &v48) )
  {
    v43 = 0;
    v46 = 0;
    v47 = 0;
    v42 = &v47;
    if ( (*(unsigned int (__fastcall **)(BSTR, struct IUnknown *, unsigned int *, unsigned int *, _QWORD, int *, int *, _QWORD))(*(_QWORD *)v48 + 24LL))(
           v48,
           a2,
           &v43,
           &v46,
           0,
           &v57,
           &v45,
           0) == -2147023150 )
    {
      v57 = 1;
      v45 = 2;
    }
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v48 + 16LL))(v48);
  }
  if ( !a3 )
  {
    v19 = v57;
    *((_DWORD *)this + 81) = v57;
    v20 = v45;
    *((_DWORD *)this + 82) = v45;
    goto LABEL_28;
  }
  v9 = (unsigned int *)((char *)this + 328);
  if ( !a5
    || ((int (__fastcall *)(struct ISWbemSecurity *, char *))a3->lpVtbl->get_ImpersonationLevel)(a3, (char *)this + 328) < 0 )
  {
    *v9 = v45;
  }
  v10 = a4 == 0;
  v11 = (unsigned int *)((char *)this + 324);
  if ( v10
    || ((int (__fastcall *)(struct ISWbemSecurity *, char *))a3->lpVtbl->get_AuthenticationLevel)(
         a3,
         (char *)this + 324) < 0 )
  {
    v12 = v57;
    *v11 = v57;
  }
  else
  {
    v12 = v57;
  }
  if ( v45 == *v9 && v12 == *v11 )
  {
    CSWbemProxyCache::SecureProxy(this, a2, *v11, *v9);
    v19 = (int)*v11;
    v20 = (int)*v9;
LABEL_28:
    *((_QWORD *)this + 4 * v19 + v20 + 6) = a2;
    AddRef = (void (*)(void))a2->lpVtbl->AddRef;
    goto LABEL_24;
  }
  v52 = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IClientSecurity,
         &v52) )
  {
    return;
  }
  v51 = 0;
  if ( !(*(unsigned int (__fastcall **)(__int64, struct IUnknown *, struct IUnknown **))(*(_QWORD *)v52 + 40LL))(
          v52,
          a2,
          &v51) )
  {
    v13 = *v9;
    v14 = *v11;
    v15 = v51;
    CInCritSec::CInCritSec((CInCritSec *)lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)this + 16));
    if ( v15 )
    {
      v16 = (struct _COAUTHIDENTITY *)*((_QWORD *)this + 35);
      if ( v16 )
      {
        v17 = 0;
        if ( CSWbemSecurity::s_bIsNT && CSWbemSecurity::s_dwNTMajorVersion > 4 && !*((_BYTE *)this + 321) )
          v17 = 32;
        SetInterfaceSecurityEx(v15, v16, *((unsigned __int16 **)this + 36), v14, v13, v17, *((_BYTE *)this + 320));
      }
      else
      {
        v53 = 9;
        v43 = 9;
        v47 = 0;
        v48 = 0;
        bstrString = 0;
        Capabilities = CSWbemProxyCache::GetCapabilities(this);
        v46 = Capabilities;
        v24 = (const unsigned __int16 *)*((_QWORD *)this + 39);
        v55 = v24;
        v25 = (const unsigned __int16 *)*((_QWORD *)this + 38);
        v26 = *((_QWORD *)this + 37);
        if ( v27 )
        {
          pv = 0;
          if ( !((unsigned __int64 (__fastcall *)(struct IUnknown *, GUID *, struct _COAUTHIDENTITY **))v15->lpVtbl->QueryInterface)(
                  v15,
                  &IID_IClientSecurity,
                  &pv) )
          {
            LOBYTE(v42) = 0;
            (*((void (__fastcall **)(struct _COAUTHIDENTITY *, struct IUnknown *, unsigned int *, unsigned int *, _QWORD, _QWORD, _QWORD, _QWORD))pv->User
             + 3))(
              pv,
              v15,
              &v43,
              &v47,
              0,
              0,
              0,
              0);
            (*((void (__fastcall **)(struct _COAUTHIDENTITY *))pv->User + 2))(pv);
          }
          v22 = 9;
          Capabilities = v46;
          v23 = v43;
        }
        if ( (unsigned __int64)(v26 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && *(_WORD *)v26 || v25 && *v25 || v24 && *v24 )
        {
          v49 = 0;
          if ( v26 )
          {
            v36 = (struct _COAUTHIDENTITY *)L"KERBEROS:";
            v37 = (unsigned __int16 *)v26;
            while ( 1 )
            {
              v54 = v37;
              pv = v36;
              if ( !v22 )
                break;
              v38 = *v37;
              if ( !v38 && !LOWORD(v36->User) )
                break;
              v39 = wbem_towlower(v38);
              if ( v39 != wbem_towlower((unsigned __int16)pv->User) )
              {
                v24 = v55;
                goto LABEL_41;
              }
              v22 = --v53;
              v37 = v54 + 1;
              v36 = (struct _COAUTHIDENTITY *)((char *)&pv->User + 2);
            }
            if ( !(unsigned int)IsKerberosAvailable() )
              goto LABEL_22;
            v35 = SysAllocString((const OLECHAR *)(v26 + 18));
            if ( !v35 )
            {
              SysFreeString(0);
              goto LABEL_22;
            }
            v28 = DetermineLoginType(&v48, &bstrString, 0, v25);
            v40 = v49;
            if ( !v28 )
              v40 = v35;
            v49 = v40;
            v41 = 0;
            if ( v28 )
              v41 = v35;
            SysFreeString(v41);
            v24 = v55;
          }
          else
          {
LABEL_41:
            v28 = DetermineLoginType(&v48, &bstrString, (const unsigned __int16 *)v26, v25);
          }
          if ( v28 >= 0 )
          {
            v29 = 0;
            pv = 0;
            v30 = v46;
            if ( (v46 & 0x60) == 0 && v14 != 1 )
            {
              v31 = WbemAllocAuthIdentity(bstrString, v24, v48, &pv);
              v29 = pv;
              if ( v31 < 0 )
                goto LABEL_78;
            }
            v32 = v49;
            if ( !v49 )
            {
              if ( v43 == 16 )
                v32 = (unsigned __int16 *)-1LL;
              v49 = v32;
              v29 = pv;
            }
            if ( (int)WbemSetProxyBlanket(v15, v43, v47, v32, v14, v13, v29, v30, (bool)v42) >= 0 )
            {
              *((_QWORD *)this + 35) = v29;
              v33 = 0;
            }
            else
            {
LABEL_78:
              v32 = 0;
              if ( v29 )
                WbemFreeAuthIdentity(v29);
              v33 = v49;
            }
            if ( bstrString )
              SysFreeString(bstrString);
            if ( v48 )
              SysFreeString(v48);
            if ( (unsigned __int64)v33 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
              SysFreeString(v33);
            if ( (unsigned __int64)v32 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            {
              v34 = (OLECHAR *)*((_QWORD *)this + 36);
              if ( v34 )
                SysFreeString(v34);
              *((_QWORD *)this + 36) = v32;
            }
          }
        }
        else
        {
          if ( v23 == 16 && !v26 )
            v26 = -1;
          WbemSetProxyBlanket(v15, v23, v47, (unsigned __int16 *)v26, v14, v13, 0, Capabilities, (bool)v42);
        }
      }
    }
LABEL_22:
    LeaveCriticalSection(lpCriticalSection[0]);
    *((_QWORD *)this + 4 * *((int *)this + 81) + *((int *)this + 82) + 6) = v51;
  }
  AddRef = *(void (**)(void))(*(_QWORD *)v52 + 16LL);
LABEL_24:
  AddRef();
}

```

## disassembly

```asm
0x18000a7b0  push    rbp
0x18000a7b2  push    rbx
0x18000a7b3  push    rsi
0x18000a7b4  push    rdi
0x18000a7b5  push    r12
0x18000a7b7  push    r13
0x18000a7b9  push    r14
0x18000a7bb  push    r15
0x18000a7bd  lea     rbp, [rsp-17h]
0x18000a7c2  sub     rsp, 0C8h
0x18000a7c9  movzx   r15d, r9b
0x18000a7cd  mov     rsi, r8
0x18000a7d0  mov     rdi, rdx
0x18000a7d3  mov     rbx, rcx
0x18000a7d6  xor     r13d, r13d
0x18000a7d9  mov     [rcx+38h], r13
0x18000a7dd  mov     [rcx+40h], r13
0x18000a7e1  mov     [rcx+48h], r13
0x18000a7e5  mov     [rcx+50h], r13
0x18000a7e9  mov     [rcx+58h], r13
0x18000a7ed  mov     [rcx+60h], r13
0x18000a7f1  mov     [rcx+68h], r13
0x18000a7f5  mov     [rcx+70h], r13
0x18000a7f9  mov     [rcx+78h], r13
0x18000a7fd  mov     [rcx+80h], r13
0x18000a804  mov     [rcx+88h], r13
0x18000a80b  mov     [rcx+90h], r13
0x18000a812  mov     [rcx+98h], r13
0x18000a819  mov     [rcx+0A0h], r13
0x18000a820  mov     [rcx+0A8h], r13
0x18000a827  mov     [rcx+0B0h], r13
0x18000a82e  mov     [rcx+0B8h], r13
0x18000a835  mov     [rcx+0C0h], r13
0x18000a83c  mov     [rcx+0C8h], r13
0x18000a843  mov     [rcx+0D0h], r13
0x18000a84a  mov     [rcx+0D8h], r13
0x18000a851  mov     [rcx+0E0h], r13
0x18000a858  mov     [rcx+0E8h], r13
0x18000a85f  mov     [rcx+0F0h], r13
0x18000a866  mov     [rcx+0F8h], r13
0x18000a86d  mov     [rcx+100h], r13
0x18000a874  mov     [rcx+108h], r13
0x18000a87b  mov     [rcx+110h], r13
0x18000a882  mov     [rbp+4Fh+arg_8], 2
0x18000a889  mov     [rbp+4Fh+var_A0], 3
0x18000a890  test    rdx, rdx
0x18000a893  jz      loc_18000AE8B
0x18000a899  mov     [rbp+4Fh+var_90], r13
0x18000a89d  mov     rax, [rdx]
0x18000a8a0  lea     r8, [rbp+4Fh+var_90]
0x18000a8a4  lea     rdx, IID_IClientSecurity
0x18000a8ab  mov     rcx, rdi
0x18000a8ae  mov     rax, [rax]
0x18000a8b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8b6  test    eax, eax
0x18000a8b8  jnz     short loc_18000A921
0x18000a8ba  mov     [rbp+4Fh+var_B0], r13d
0x18000a8be  mov     [rbp+4Fh+var_9C], r13d
0x18000a8c2  mov     [rbp+4Fh+var_98], r13d
0x18000a8c6  mov     rcx, [rbp+4Fh+var_90]
0x18000a8ca  mov     rax, [rcx]
0x18000a8cd  lea     rdx, [rbp+4Fh+var_98]
0x18000a8d1  mov     qword ptr [rsp+100h+var_C0], rdx
0x18000a8d6  mov     qword ptr [rsp+100h+var_C8], r13
0x18000a8db  lea     rdx, [rbp+4Fh+var_A0]
0x18000a8df  mov     [rsp+100h+var_D0], rdx
0x18000a8e4  lea     rdx, [rbp+4Fh+arg_8]
0x18000a8e8  mov     qword ptr [rsp+100h+var_D8], rdx
0x18000a8ed  mov     qword ptr [rsp+100h+var_E0], r13
0x18000a8f2  lea     r9, [rbp+4Fh+var_9C]
0x18000a8f6  lea     r8, [rbp+4Fh+var_B0]
0x18000a8fa  mov     rdx, rdi
0x18000a8fd  mov     rax, [rax+18h]
0x18000a901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a906  cmp     eax, 800706D2h
0x18000a90b  jz      loc_18000AD46
0x18000a911  mov     rcx, [rbp+4Fh+var_90]
0x18000a915  mov     rax, [rcx]
0x18000a918  mov     rax, [rax+10h]
0x18000a91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a921  test    rsi, rsi
0x18000a924  jz      loc_18000AE72
0x18000a92a  lea     r14, [rbx+148h]
0x18000a931  cmp     [rbp+4Fh+arg_20], r13b
0x18000a935  jz      loc_18000AD59
0x18000a93b  mov     rax, [rsi]
0x18000a93e  mov     rdx, r14
0x18000a941  mov     rcx, rsi
0x18000a944  mov     rax, [rax+38h]
0x18000a948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a94d  test    eax, eax
0x18000a94f  js      loc_18000AD59
0x18000a955  test    r15b, r15b
0x18000a958  lea     r15, [rbx+144h]
0x18000a95f  jz      loc_18000AACA
0x18000a965  mov     rax, [rsi]
0x18000a968  mov     rdx, r15
0x18000a96b  mov     rcx, rsi
0x18000a96e  mov     rax, [rax+48h]
0x18000a972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a977  test    eax, eax
0x18000a979  js      loc_18000AACA
0x18000a97f  mov     eax, [rbp+4Fh+arg_8]
0x18000a982  mov     r9d, [r14]; enum WbemImpersonationLevelEnum
0x18000a985  cmp     [rbp+4Fh+var_A0], r9d
0x18000a989  jz      loc_18000AA98
0x18000a98f  mov     [rbp+4Fh+var_70], r13
0x18000a993  mov     rax, [rdi]
0x18000a996  lea     r8, [rbp+4Fh+var_70]
0x18000a99a  lea     rdx, IID_IClientSecurity
0x18000a9a1  mov     rcx, rdi
0x18000a9a4  mov     rax, [rax]
0x18000a9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9ac  test    eax, eax
0x18000a9ae  jnz     loc_18000AA84
0x18000a9b4  mov     [rbp+4Fh+var_78], r13
0x18000a9b8  mov     rcx, [rbp+4Fh+var_70]
0x18000a9bc  mov     rax, [rcx]
0x18000a9bf  lea     r8, [rbp+4Fh+var_78]
0x18000a9c3  mov     rdx, rdi
0x18000a9c6  mov     rax, [rax+28h]
0x18000a9ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9cf  test    eax, eax
0x18000a9d1  jnz     loc_18000AA74
0x18000a9d7  mov     r12d, [r14]
0x18000a9da  mov     r14d, [r15]
0x18000a9dd  mov     rsi, [rbp+4Fh+var_78]
0x18000a9e1  lea     rdx, [rbx+10h]; struct _RTL_CRITICAL_SECTION *
0x18000a9e5  lea     rcx, [rbp+4Fh+lpCriticalSection]; this
0x18000a9e9  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18000a9ee  nop
0x18000a9ef  test    rsi, rsi
0x18000a9f2  jz      short loc_18000AA4F
0x18000a9f4  mov     rdx, [rbx+118h]; struct _COAUTHIDENTITY *
0x18000a9fb  movzx   r8d, byte ptr [rbx+140h]
0x18000aa03  test    rdx, rdx
0x18000aa06  jz      loc_18000AAD5
0x18000aa0c  mov     eax, r13d
0x18000aa0f  cmp     cs:?s_bIsNT@CSWbemSecurity@@0_NA, al; bool CSWbemSecurity::s_bIsNT
0x18000aa15  jz      short loc_18000AA2E
0x18000aa17  cmp     cs:?s_dwNTMajorVersion@CSWbemSecurity@@0KA, 4; ulong CSWbemSecurity::s_dwNTMajorVersion
0x18000aa1e  jbe     short loc_18000AA2E
0x18000aa20  mov     ecx, 20h ; ' '
0x18000aa25  cmp     [rbx+141h], al
0x18000aa2b  cmovz   eax, ecx
0x18000aa2e  mov     byte ptr [rsp+100h+var_D0], r8b; bool
0x18000aa33  mov     [rsp+100h+var_D8], eax; unsigned int
0x18000aa37  mov     [rsp+100h+var_E0], r12d; unsigned int
0x18000aa3c  mov     r9d, r14d; unsigned int
0x18000aa3f  mov     r8, [rbx+120h]; unsigned __int16 *
0x18000aa46  mov     rcx, rsi; struct IUnknown *
0x18000aa49  call    ?SetInterfaceSecurityEx@@YAJPEAUIUnknown@@PEAU_COAUTHIDENTITY@@PEAGKKK_N@Z; SetInterfaceSecurityEx(IUnknown *,_COAUTHIDENTITY *,ushort *,ulong,ulong,ulong,bool)
0x18000aa4e  nop
0x18000aa4f  mov     rcx, [rbp+4Fh+lpCriticalSection]; lpCriticalSection
0x18000aa53  call    cs:__imp_LeaveCriticalSection
0x18000aa59  movsxd  rcx, dword ptr [rbx+144h]
0x18000aa60  movsxd  rax, dword ptr [rbx+148h]
0x18000aa67  lea     rdx, [rax+rcx*4]
0x18000aa6b  mov     rax, [rbp+4Fh+var_78]
0x18000aa6f  mov     [rbx+rdx*8+30h], rax
0x18000aa74  mov     rcx, [rbp+4Fh+var_70]
0x18000aa78  mov     rax, [rcx]
0x18000aa7b  mov     rax, [rax+10h]
0x18000aa7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa84  add     rsp, 0C8h
0x18000aa8b  pop     r15
0x18000aa8d  pop     r14
0x18000aa8f  pop     r13
0x18000aa91  pop     r12
0x18000aa93  pop     rdi
0x18000aa94  pop     rsi
0x18000aa95  pop     rbx
0x18000aa96  pop     rbp
0x18000aa97  retn
0x18000aa98  mov     r8d, [r15]; enum WbemAuthenticationLevelEnum
0x18000aa9b  cmp     eax, r8d
0x18000aa9e  jnz     loc_18000A98F
0x18000aaa4  mov     rdx, rdi; struct IUnknown *
0x18000aaa7  mov     rcx, rbx; this
0x18000aaaa  call    ?SecureProxy@CSWbemProxyCache@@QEAAXPEAUIUnknown@@W4WbemAuthenticationLevelEnum@@W4WbemImpersonationLevelEnum@@@Z; CSWbemProxyCache::SecureProxy(IUnknown *,WbemAuthenticationLevelEnum,WbemImpersonationLevelEnum)
0x18000aaaf  movsxd  rcx, dword ptr [r15]
0x18000aab2  movsxd  rax, dword ptr [r14]
0x18000aab5  lea     rcx, [rax+rcx*4]
0x18000aab9  mov     [rbx+rcx*8+30h], rdi
0x18000aabe  mov     rax, [rdi]
0x18000aac1  mov     rcx, rdi
0x18000aac4  mov     rax, [rax+8]
0x18000aac8  jmp     short loc_18000AA7F
0x18000aaca  mov     eax, [rbp+4Fh+arg_8]
0x18000aacd  mov     [r15], eax
0x18000aad0  jmp     loc_18000A982
0x18000aad5  mov     r9d, 9
0x18000aadb  mov     [rbp+4Fh+var_68], r9
0x18000aadf  mov     r10d, r9d
0x18000aae2  mov     [rbp+4Fh+var_B0], r9d
0x18000aae6  mov     [rbp+4Fh+var_98], r13d
0x18000aaea  mov     [rbp+4Fh+var_90], r13
0x18000aaee  mov     [rbp+4Fh+bstrString], r13
0x18000aaf2  mov     rcx, rbx; this
0x18000aaf5  call    ?GetCapabilities@CSWbemProxyCache@@AEAAKXZ; CSWbemProxyCache::GetCapabilities(void)
0x18000aafa  mov     ecx, eax
0x18000aafc  mov     [rbp+4Fh+var_9C], eax
0x18000aaff  mov     rdi, [rbx+138h]
0x18000ab06  mov     [rbp+4Fh+var_58], rdi
0x18000ab0a  mov     r13, [rbx+130h]
0x18000ab11  mov     r15, [rbx+128h]
0x18000ab18  test    r8b, r8b
0x18000ab1b  jz      loc_18000ABAB
0x18000ab21  mov     [rbp+4Fh+pv], 0
0x18000ab29  mov     rcx, [rsi]
0x18000ab2c  mov     rax, [rcx]
0x18000ab2f  lea     r8, [rbp+4Fh+pv]
0x18000ab33  lea     rdx, IID_IClientSecurity
0x18000ab3a  mov     rcx, rsi
0x18000ab3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab42  test    eax, eax
0x18000ab44  jnz     short loc_18000AB9E
0x18000ab46  mov     rcx, [rbp+4Fh+pv]
0x18000ab4a  mov     rax, [rcx]
0x18000ab4d  mov     qword ptr [rsp+100h+var_C0], 0; bool
0x18000ab56  mov     qword ptr [rsp+100h+var_C8], 0
0x18000ab5f  mov     [rsp+100h+var_D0], 0
0x18000ab68  mov     qword ptr [rsp+100h+var_D8], 0
0x18000ab71  mov     qword ptr [rsp+100h+var_E0], 0
0x18000ab7a  lea     r9, [rbp+4Fh+var_98]
0x18000ab7e  lea     r8, [rbp+4Fh+var_B0]
0x18000ab82  mov     rdx, rsi
0x18000ab85  mov     rax, [rax+18h]
0x18000ab89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab8e  mov     rcx, [rbp+4Fh+pv]
0x18000ab92  mov     rax, [rcx]
0x18000ab95  mov     rax, [rax+10h]
0x18000ab99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab9e  mov     r9d, 9
0x18000aba4  mov     ecx, [rbp+4Fh+var_9C]
0x18000aba7  mov     r10d, [rbp+4Fh+var_B0]
0x18000abab  lea     rax, [r15-1]
0x18000abaf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000abb3  jbe     short loc_18000ABFF
0x18000abb5  test    r13, r13
0x18000abb8  jnz     loc_18000AD64
0x18000abbe  test    rdi, rdi
0x18000abc1  jnz     loc_18000AD75
0x18000abc7  cmp     r10d, 10h
0x18000abcb  jz      loc_18000ACC8
0x18000abd1  mov     [rsp+100h+var_C8], ecx; unsigned int
0x18000abd5  mov     [rsp+100h+var_D0], 0; struct _COAUTHIDENTITY *
0x18000abde  mov     [rsp+100h+var_D8], r12d; unsigned int
0x18000abe3  mov     [rsp+100h+var_E0], r14d; unsigned int
0x18000abe8  mov     r9, r15; unsigned __int16 *
0x18000abeb  mov     r8d, [rbp+4Fh+var_98]; unsigned int
0x18000abef  mov     edx, r10d; unsigned int
0x18000abf2  mov     rcx, rsi; struct IUnknown *
0x18000abf5  call    ?WbemSetProxyBlanket@@YAJPEAUIUnknown@@KKPEAGKKPEAXK_N@Z; WbemSetProxyBlanket(IUnknown *,ulong,ulong,ushort *,ulong,ulong,void *,ulong,bool)
0x18000abfa  jmp     loc_18000AA4F
0x18000abff  cmp     word ptr [r15], 0
0x18000ac04  jz      short loc_18000ABB5
0x18000ac06  mov     [rbp+4Fh+var_88], 0
0x18000ac0e  test    r15, r15
0x18000ac11  jnz     loc_18000AD84
0x18000ac17  mov     r9, r13; unsigned __int16 *
0x18000ac1a  mov     r8, r15; unsigned __int16 *
0x18000ac1d  lea     rdx, [rbp+4Fh+bstrString]; unsigned __int16 **
0x18000ac21  lea     rcx, [rbp+4Fh+var_90]; unsigned __int16 **
0x18000ac25  call    ?DetermineLoginType@@YAJAEAPEAG0PEBG1@Z; DetermineLoginType(ushort * &,ushort * &,ushort const *,ushort const *)
0x18000ac2a  mov     r15d, eax
0x18000ac2d  test    r15d, r15d
0x18000ac30  js      loc_18000AA4F
0x18000ac36  xor     r15d, r15d
0x18000ac39  mov     [rbp+4Fh+pv], r15
0x18000ac3d  mov     r13d, [rbp+4Fh+var_9C]
0x18000ac41  test    r13b, 60h
0x18000ac45  jnz     short loc_18000AC6D
0x18000ac47  cmp     r14d, 1
0x18000ac4b  jz      short loc_18000AC6D
0x18000ac4d  lea     r9, [rbp+4Fh+pv]; struct _COAUTHIDENTITY **
0x18000ac51  mov     r8, [rbp+4Fh+var_90]; unsigned __int16 *
0x18000ac55  mov     rdx, rdi; unsigned __int16 *
0x18000ac58  mov     rcx, [rbp+4Fh+bstrString]; unsigned __int16 *
0x18000ac5c  call    ?WbemAllocAuthIdentity@@YAJPEBG00PEAPEAU_COAUTHIDENTITY@@@Z; WbemAllocAuthIdentity(ushort const *,ushort const *,ushort const *,_COAUTHIDENTITY * *)
0x18000ac61  mov     r15, [rbp+4Fh+pv]
0x18000ac65  test    eax, eax
0x18000ac67  js      loc_18000AE25
0x18000ac6d  mov     edx, [rbp+4Fh+var_B0]; unsigned int
0x18000ac70  mov     rdi, [rbp+4Fh+var_88]
0x18000ac74  test    rdi, rdi
0x18000ac77  jnz     short loc_18000AC8F
0x18000ac79  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18000ac80  cmp     edx, 10h
0x18000ac83  cmovz   rdi, r15
0x18000ac87  mov     [rbp+4Fh+var_88], rdi
0x18000ac8b  mov     r15, [rbp+4Fh+pv]
0x18000ac8f  mov     [rsp+100h+var_C8], r13d; unsigned int
0x18000ac94  mov     [rsp+100h+var_D0], r15; struct _COAUTHIDENTITY *
0x18000ac99  mov     [rsp+100h+var_D8], r12d; unsigned int
0x18000ac9e  mov     [rsp+100h+var_E0], r14d; unsigned int
0x18000aca3  mov     r9, rdi; unsigned __int16 *
0x18000aca6  mov     r8d, [rbp+4Fh+var_98]; unsigned int
0x18000acaa  mov     rcx, rsi; struct IUnknown *
0x18000acad  call    ?WbemSetProxyBlanket@@YAJPEAUIUnknown@@KKPEAGKKPEAXK_N@Z; WbemSetProxyBlanket(IUnknown *,ulong,ulong,ushort *,ulong,ulong,void *,ulong,bool)
  ... truncated ...
```
