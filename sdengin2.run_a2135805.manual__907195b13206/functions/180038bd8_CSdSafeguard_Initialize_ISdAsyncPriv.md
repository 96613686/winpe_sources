# CSdSafeguard::_Initialize(ISdAsyncPriv *)

- ea: `0x180038bd8`
- end: `0x180038e6f`
- name: `?_Initialize@CSdSafeguard@@AEAAJPEAUISdAsyncPriv@@@Z`
- size: `663`
- prototype: `__int64 __fastcall(CSdSafeguard *__hidden this, struct ISdAsyncPriv *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800374e0`

## callees

- `0x180038bd8`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009e3c4`
- `0x18009e904`
- `0x18009f560`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180038dfe`
- `KERNEL32!LocalFree` at `0x180038e17`
- `KERNEL32!LocalFree` at `0x180038dfe`
- `KERNEL32!LocalFree` at `0x180038e17`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180038c8a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180038c8a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180038d1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180038d9a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180038d1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180038d9a`
- `ole32!CoTaskMemFree` at `0x180038e2b`
- `ole32!CoTaskMemFree` at `0x180038e2b`

## pseudocode

```c
__int64 __fastcall CSdSafeguard::_Initialize(CSdSafeguard *this, struct ISdAsyncPriv *a2)
{
  __int16 v4; // ax
  int v5; // ecx
  __int64 v6; // rcx
  bool v7; // sf
  __int64 v8; // rcx
  __int64 v9; // rcx
  PSECURITY_DESCRIPTOR v10; // rax
  unsigned int v11; // ebx
  PSID Sid; // [rsp+20h] [rbp-60h] BYREF
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+28h] [rbp-58h] BYREF
  _QWORD v15[2]; // [rsp+38h] [rbp-48h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-38h] BYREF
  __int16 v17; // [rsp+4Ch] [rbp-34h]
  __int16 v18; // [rsp+4Eh] [rbp-32h]
  LPCWSTR StringSid; // [rsp+A8h] [rbp+28h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+B0h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+B8h] [rbp+38h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CSdSafeguard::_Initialize",
    0x58u,
    1u);
  StringSecurityDescriptor[0] = (LPCWSTR)qword_1800EE510;
  StringSecurityDescriptor[1] = 0;
  v15[0] = qword_1800EE510;
  v15[1] = 0;
  StringSid = 0;
  hMem = 0;
  SecurityDescriptor = 0;
  Sid = 0;
  v4 = 99;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_3:
    v18 = v4;
    goto LABEL_18;
  }
  LastFailureAsHRESULT = 0;
  v17 = 99;
  v5 = (*(__int64 (__fastcall **)(struct ISdAsyncPriv *, LPCWSTR *))(*(_QWORD *)a2 + 256LL))(a2, &StringSid);
  LastFailureAsHRESULT = v5;
  v4 = 103;
  if ( v5 < 0 )
    goto LABEL_3;
  v17 = 103;
  if ( v5 )
  {
    LastFailureAsHRESULT = CBsString::Set(
                             (CBsString *)StringSecurityDescriptor,
                             L"D:AR(A;;FR;;;AU)(A;OICI;FA;;;CO)(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)");
    v4 = 115;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v17 = 115;
    LastFailureAsHRESULT = CBsString::Set((CBsString *)v15, L"D:AR(A;OICI;FA;;;CO)(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)");
    v7 = LastFailureAsHRESULT < 0;
    v4 = 116;
  }
  else
  {
    if ( !ConvertStringSidToSidW(StringSid, &Sid) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6);
      v4 = 108;
      goto LABEL_3;
    }
    LastFailureAsHRESULT = 0;
    v17 = 108;
    LastFailureAsHRESULT = CBsString::Format(
                             (CBsString *)StringSecurityDescriptor,
                             L"D:AR(A;;FR;;;AU)(A;OICI;FA;;;CO)(A;OICI;FA;;;%s)(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)",
                             StringSid);
    v4 = 109;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_3;
    v17 = 109;
    LastFailureAsHRESULT = CBsString::Format(
                             (CBsString *)v15,
                             L"D:AR(A;OICI;FA;;;CO)(A;OICI;FA;;;%s)(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)",
                             StringSid);
    v7 = LastFailureAsHRESULT < 0;
    v4 = 110;
  }
  if ( v7 )
    goto LABEL_3;
  v17 = v4;
  *((_QWORD *)this + 8) = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:SYD:P(A;OICI;FA;;;CO)(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
    v4 = 121;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v17 = 121;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor[0], 1u, &hMem, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
    v4 = 124;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v17 = 124;
  v10 = SecurityDescriptor;
  *((_QWORD *)this + 8) = SecurityDescriptor;
  SecurityDescriptor = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 6) = v10;
  *((_DWORD *)this + 10) = 24;
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 10) = hMem;
  hMem = 0;
  *((_DWORD *)this + 18) = 24;
LABEL_18:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  CoTaskMemFree((LPVOID)StringSid);
  StringSid = 0;
  v11 = LastFailureAsHRESULT;
  CBsString::_Release((CBsString *)v15);
  CBsString::_Release((CBsString *)StringSecurityDescriptor);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v11;
}

```

## disassembly

```asm
0x180038bd8  mov     [rsp-18h+arg_0], rbx
0x180038bdd  push    rbp
0x180038bde  push    rsi
0x180038bdf  push    rdi
0x180038be0  mov     rbp, rsp
0x180038be3  sub     rsp, 80h
0x180038bea  mov     rdi, rdx
0x180038bed  mov     rbx, rcx
0x180038bf0  mov     r9d, 1; unsigned __int16
0x180038bf6  lea     r8d, [r9+57h]; unsigned __int16
0x180038bfa  lea     rdx, aCsdsafeguardIn; "CSdSafeguard::_Initialize"
0x180038c01  lea     rcx, [rbp+var_38]; this
0x180038c05  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180038c0a  lea     rax, qword_1800EE510
0x180038c11  mov     [rbp+StringSecurityDescriptor], rax
0x180038c15  xor     esi, esi
0x180038c17  mov     [rbp+var_50], rsi
0x180038c1b  mov     [rbp+var_48], rax
0x180038c1f  mov     [rbp+var_40], rsi
0x180038c23  mov     [rbp+StringSid], rsi
0x180038c27  mov     [rbp+hMem], rsi
0x180038c2b  mov     [rbp+SecurityDescriptor], rsi
0x180038c2f  mov     [rbp+Sid], rsi
0x180038c33  lea     eax, [rsi+63h]
0x180038c36  test    rdi, rdi
0x180038c39  jnz     short loc_180038C4B
0x180038c3b  mov     [rbp+var_38], 80070057h
0x180038c42  mov     [rbp+var_32], ax
0x180038c46  jmp     loc_180038DF5
0x180038c4b  mov     [rbp+var_38], esi
0x180038c4e  mov     [rbp+var_34], ax
0x180038c52  mov     rax, [rdi]
0x180038c55  lea     rdx, [rbp+StringSid]
0x180038c59  mov     rcx, rdi
0x180038c5c  mov     rax, [rax+100h]
0x180038c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c68  mov     ecx, eax
0x180038c6a  mov     [rbp+var_38], eax
0x180038c6d  test    eax, eax
0x180038c6f  mov     eax, 67h ; 'g'
0x180038c74  js      short loc_180038C42
0x180038c76  mov     [rbp+var_34], ax
0x180038c7a  test    ecx, ecx
0x180038c7c  jnz     loc_180038D3D
0x180038c82  lea     rdx, [rbp+Sid]; Sid
0x180038c86  mov     rcx, [rbp+StringSid]; StringSid
0x180038c8a  call    cs:__imp_ConvertStringSidToSidW
0x180038c91  nop     dword ptr [rax+rax+00h]
0x180038c96  test    eax, eax
0x180038c98  jnz     short loc_180038CA9
0x180038c9a  call    GetLastFailureAsHRESULT
0x180038c9f  mov     [rbp+var_38], eax
0x180038ca2  mov     eax, 6Ch ; 'l'
0x180038ca7  jmp     short loc_180038C42
0x180038ca9  mov     [rbp+var_38], esi
0x180038cac  mov     eax, 6Ch ; 'l'
0x180038cb1  mov     [rbp+var_34], ax
0x180038cb5  mov     r8, [rbp+StringSid]
0x180038cb9  lea     rdx, c_wszNetEveryoneRead; "D:AR(A;;FR;;;AU)(A;OICI;FA;;;CO)(A;OICI"...
0x180038cc0  lea     rcx, [rbp+StringSecurityDescriptor]; this
0x180038cc4  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180038cc9  mov     [rbp+var_38], eax
0x180038ccc  test    eax, eax
0x180038cce  mov     eax, 6Dh ; 'm'
0x180038cd3  js      loc_180038C42
0x180038cd9  mov     [rbp+var_34], ax
0x180038cdd  mov     r8, [rbp+StringSid]
0x180038ce1  lea     rdx, c_wszNetTargetSecurity; "D:AR(A;OICI;FA;;;CO)(A;OICI;FA;;;%s)(A;"...
0x180038ce8  lea     rcx, [rbp+var_48]; this
0x180038cec  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180038cf1  mov     [rbp+var_38], eax
0x180038cf4  test    eax, eax
0x180038cf6  mov     eax, 6Eh ; 'n'
0x180038cfb  js      loc_180038C42
0x180038d01  mov     [rbp+var_34], ax
0x180038d05  mov     [rbx+40h], rsi
0x180038d09  xor     r9d, r9d; SecurityDescriptorSize
0x180038d0c  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180038d10  lea     edx, [r9+1]; StringSDRevision
0x180038d14  lea     rcx, c_wszLocalTargetSecurity; "O:SYD:P(A;OICI;FA;;;CO)(A;OICI;FA;;;BA)"...
0x180038d1b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180038d22  nop     dword ptr [rax+rax+00h]
0x180038d27  test    eax, eax
0x180038d29  jnz     short loc_180038D80
0x180038d2b  call    GetLastFailureAsHRESULT
0x180038d30  mov     [rbp+var_38], eax
0x180038d33  mov     eax, 79h ; 'y'
0x180038d38  jmp     loc_180038C42
0x180038d3d  lea     rdx, c_wszLocalEveryoneRead; "D:AR(A;;FR;;;AU)(A;OICI;FA;;;CO)(A;OICI"...
0x180038d44  lea     rcx, [rbp+StringSecurityDescriptor]; this
0x180038d48  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180038d4d  mov     [rbp+var_38], eax
0x180038d50  test    eax, eax
0x180038d52  mov     eax, 73h ; 's'
0x180038d57  js      loc_180038C42
0x180038d5d  mov     [rbp+var_34], ax
0x180038d61  lea     rdx, c_wszNetTargetNoUserSecurity; "D:AR(A;OICI;FA;;;CO)(A;OICI;FA;;;BA)(A;"...
0x180038d68  lea     rcx, [rbp+var_48]; this
0x180038d6c  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180038d71  mov     [rbp+var_38], eax
0x180038d74  test    eax, eax
0x180038d76  mov     eax, 74h ; 't'
0x180038d7b  jmp     loc_180038CFB
0x180038d80  mov     [rbp+var_38], esi
0x180038d83  mov     eax, 79h ; 'y'
0x180038d88  mov     [rbp+var_34], ax
0x180038d8c  xor     r9d, r9d; SecurityDescriptorSize
0x180038d8f  lea     r8, [rbp+hMem]; SecurityDescriptor
0x180038d93  lea     edx, [rax-78h]; StringSDRevision
0x180038d96  mov     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x180038d9a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180038da1  nop     dword ptr [rax+rax+00h]
0x180038da6  test    eax, eax
0x180038da8  jnz     short loc_180038DBC
0x180038daa  call    GetLastFailureAsHRESULT
0x180038daf  mov     [rbp+var_38], eax
0x180038db2  mov     eax, 7Ch ; '|'
0x180038db7  jmp     loc_180038C42
0x180038dbc  mov     [rbp+var_38], esi
0x180038dbf  mov     eax, 7Ch ; '|'
0x180038dc4  mov     [rbp+var_34], ax
0x180038dc8  mov     rax, [rbp+SecurityDescriptor]
0x180038dcc  mov     [rbx+40h], rax
0x180038dd0  mov     [rbp+SecurityDescriptor], rsi
0x180038dd4  mov     [rbx+38h], esi
0x180038dd7  mov     [rbx+30h], rax
0x180038ddb  mov     ecx, 18h
0x180038de0  mov     [rbx+28h], ecx
0x180038de3  mov     [rbx+58h], esi
0x180038de6  mov     rax, [rbp+hMem]
0x180038dea  mov     [rbx+50h], rax
0x180038dee  mov     [rbp+hMem], rsi
0x180038df2  mov     [rbx+48h], ecx
0x180038df5  mov     rcx, [rbp+hMem]; hMem
0x180038df9  test    rcx, rcx
0x180038dfc  jz      short loc_180038E0E
0x180038dfe  call    cs:__imp_LocalFree
0x180038e05  nop     dword ptr [rax+rax+00h]
0x180038e0a  mov     [rbp+hMem], rsi
0x180038e0e  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180038e12  test    rcx, rcx
0x180038e15  jz      short loc_180038E27
0x180038e17  call    cs:__imp_LocalFree
0x180038e1e  nop     dword ptr [rax+rax+00h]
0x180038e23  mov     [rbp+SecurityDescriptor], rsi
0x180038e27  mov     rcx, [rbp+StringSid]; pv
0x180038e2b  call    cs:__imp_CoTaskMemFree
0x180038e32  nop     dword ptr [rax+rax+00h]
0x180038e37  mov     [rbp+StringSid], rsi
0x180038e3b  mov     ebx, [rbp+var_38]
0x180038e3e  lea     rcx, [rbp+var_48]; this
0x180038e42  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180038e47  lea     rcx, [rbp+StringSecurityDescriptor]; this
0x180038e4b  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180038e50  lea     rcx, [rbp+var_38]; this
0x180038e54  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180038e59  mov     eax, ebx
0x180038e5b  mov     rbx, [rsp+80h+arg_0]
0x180038e63  add     rsp, 80h
0x180038e6a  pop     rdi
0x180038e6b  pop     rsi
0x180038e6c  pop     rbp
0x180038e6d  retn
```
