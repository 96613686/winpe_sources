# CSdSafeguard::_Initialize(ISdAsyncPriv *)

- ea: `0x1800376f4`
- end: `0x180037963`
- name: `?_Initialize@CSdSafeguard@@AEAAJPEAUISdAsyncPriv@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(CSdSafeguard *__hidden this, struct ISdAsyncPriv *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003607c`

## callees

- `0x1800376f4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x180099d58`
- `0x18009a24c`
- `0x18009ae34`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180037905`
- `KERNEL32!LocalFree` at `0x180037918`
- `KERNEL32!LocalFree` at `0x180037905`
- `KERNEL32!LocalFree` at `0x180037918`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800377a6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800377a6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180037831`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800378a7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180037831`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800378a7`
- `ole32!CoTaskMemFree` at `0x180037926`
- `ole32!CoTaskMemFree` at `0x180037926`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "CSdSafeguard::_Initialize", 88, 1);
  StringSecurityDescriptor[0] = (LPCWSTR)qword_1800E8530;
  StringSecurityDescriptor[1] = 0;
  v15[0] = qword_1800E8530;
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
0x1800376f4  mov     [rsp-18h+arg_0], rbx
0x1800376f9  push    rbp
0x1800376fa  push    rsi
0x1800376fb  push    rdi
0x1800376fc  mov     rbp, rsp
0x1800376ff  sub     rsp, 80h
0x180037706  mov     rdi, rdx
0x180037709  mov     rbx, rcx
0x18003770c  mov     r9d, 1; unsigned __int16
0x180037712  lea     r8d, [r9+57h]; unsigned __int16
0x180037716  lea     rdx, aCsdsafeguardIn; "CSdSafeguard::_Initialize"
0x18003771d  lea     rcx, [rbp+var_38]; this
0x180037721  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180037726  lea     rax, qword_1800E8530
0x18003772d  mov     [rbp+StringSecurityDescriptor], rax
0x180037731  xor     esi, esi
0x180037733  mov     [rbp+var_50], rsi
0x180037737  mov     [rbp+var_48], rax
0x18003773b  mov     [rbp+var_40], rsi
0x18003773f  mov     [rbp+StringSid], rsi
0x180037743  mov     [rbp+hMem], rsi
0x180037747  mov     [rbp+SecurityDescriptor], rsi
0x18003774b  mov     [rbp+Sid], rsi
0x18003774f  lea     eax, [rsi+63h]
0x180037752  test    rdi, rdi
0x180037755  jnz     short loc_180037767
0x180037757  mov     [rbp+var_38], 80070057h
0x18003775e  mov     [rbp+var_32], ax
0x180037762  jmp     loc_1800378FC
0x180037767  mov     [rbp+var_38], esi
0x18003776a  mov     [rbp+var_34], ax
0x18003776e  mov     rax, [rdi]
0x180037771  lea     rdx, [rbp+StringSid]
0x180037775  mov     rcx, rdi
0x180037778  mov     rax, [rax+100h]
0x18003777f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037784  mov     ecx, eax
0x180037786  mov     [rbp+var_38], eax
0x180037789  test    eax, eax
0x18003778b  mov     eax, 67h ; 'g'
0x180037790  js      short loc_18003775E
0x180037792  mov     [rbp+var_34], ax
0x180037796  test    ecx, ecx
0x180037798  jnz     loc_18003784D
0x18003779e  lea     rdx, [rbp+Sid]; Sid
0x1800377a2  mov     rcx, [rbp+StringSid]; StringSid
0x1800377a6  call    cs:__imp_ConvertStringSidToSidW
0x1800377ac  test    eax, eax
0x1800377ae  jnz     short loc_1800377BF
0x1800377b0  call    GetLastFailureAsHRESULT
0x1800377b5  mov     [rbp+var_38], eax
0x1800377b8  mov     eax, 6Ch ; 'l'
0x1800377bd  jmp     short loc_18003775E
0x1800377bf  mov     [rbp+var_38], esi
0x1800377c2  mov     eax, 6Ch ; 'l'
0x1800377c7  mov     [rbp+var_34], ax
0x1800377cb  mov     r8, [rbp+StringSid]
0x1800377cf  lea     rdx, c_wszNetEveryoneRead; "D:AR(A;;FR;;;AU)(A;OICI;FA;;;CO)(A;OICI"...
0x1800377d6  lea     rcx, [rbp+StringSecurityDescriptor]; this
0x1800377da  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800377df  mov     [rbp+var_38], eax
0x1800377e2  test    eax, eax
0x1800377e4  mov     eax, 6Dh ; 'm'
0x1800377e9  js      loc_18003775E
0x1800377ef  mov     [rbp+var_34], ax
0x1800377f3  mov     r8, [rbp+StringSid]
0x1800377f7  lea     rdx, c_wszNetTargetSecurity; "D:AR(A;OICI;FA;;;CO)(A;OICI;FA;;;%s)(A;"...
0x1800377fe  lea     rcx, [rbp+var_48]; this
0x180037802  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180037807  mov     [rbp+var_38], eax
0x18003780a  test    eax, eax
0x18003780c  mov     eax, 6Eh ; 'n'
0x180037811  js      loc_18003775E
0x180037817  mov     [rbp+var_34], ax
0x18003781b  mov     [rbx+40h], rsi
0x18003781f  xor     r9d, r9d; SecurityDescriptorSize
0x180037822  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180037826  lea     edx, [r9+1]; StringSDRevision
0x18003782a  lea     rcx, c_wszLocalTargetSecurity; "O:SYD:P(A;OICI;FA;;;CO)(A;OICI;FA;;;BA)"...
0x180037831  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180037837  test    eax, eax
0x180037839  jnz     short loc_18003788D
0x18003783b  call    GetLastFailureAsHRESULT
0x180037840  mov     [rbp+var_38], eax
0x180037843  mov     eax, 79h ; 'y'
0x180037848  jmp     loc_18003775E
0x18003784d  lea     rdx, c_wszLocalEveryoneRead; "D:AR(A;;FR;;;AU)(A;OICI;FA;;;CO)(A;OICI"...
0x180037854  lea     rcx, [rbp+StringSecurityDescriptor]; this
0x180037858  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003785d  mov     [rbp+var_38], eax
0x180037860  test    eax, eax
0x180037862  mov     eax, 73h ; 's'
0x180037867  js      loc_18003775E
0x18003786d  mov     [rbp+var_34], ax
0x180037871  lea     rdx, c_wszNetTargetNoUserSecurity; "D:AR(A;OICI;FA;;;CO)(A;OICI;FA;;;BA)(A;"...
0x180037878  lea     rcx, [rbp+var_48]; this
0x18003787c  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180037881  mov     [rbp+var_38], eax
0x180037884  test    eax, eax
0x180037886  mov     eax, 74h ; 't'
0x18003788b  jmp     short loc_180037811
0x18003788d  mov     [rbp+var_38], esi
0x180037890  mov     eax, 79h ; 'y'
0x180037895  mov     [rbp+var_34], ax
0x180037899  xor     r9d, r9d; SecurityDescriptorSize
0x18003789c  lea     r8, [rbp+hMem]; SecurityDescriptor
0x1800378a0  lea     edx, [rax-78h]; StringSDRevision
0x1800378a3  mov     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800378a7  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800378ad  test    eax, eax
0x1800378af  jnz     short loc_1800378C3
0x1800378b1  call    GetLastFailureAsHRESULT
0x1800378b6  mov     [rbp+var_38], eax
0x1800378b9  mov     eax, 7Ch ; '|'
0x1800378be  jmp     loc_18003775E
0x1800378c3  mov     [rbp+var_38], esi
0x1800378c6  mov     eax, 7Ch ; '|'
0x1800378cb  mov     [rbp+var_34], ax
0x1800378cf  mov     rax, [rbp+SecurityDescriptor]
0x1800378d3  mov     [rbx+40h], rax
0x1800378d7  mov     [rbp+SecurityDescriptor], rsi
0x1800378db  mov     [rbx+38h], esi
0x1800378de  mov     [rbx+30h], rax
0x1800378e2  mov     ecx, 18h
0x1800378e7  mov     [rbx+28h], ecx
0x1800378ea  mov     [rbx+58h], esi
0x1800378ed  mov     rax, [rbp+hMem]
0x1800378f1  mov     [rbx+50h], rax
0x1800378f5  mov     [rbp+hMem], rsi
0x1800378f9  mov     [rbx+48h], ecx
0x1800378fc  mov     rcx, [rbp+hMem]; hMem
0x180037900  test    rcx, rcx
0x180037903  jz      short loc_18003790F
0x180037905  call    cs:__imp_LocalFree
0x18003790b  mov     [rbp+hMem], rsi
0x18003790f  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180037913  test    rcx, rcx
0x180037916  jz      short loc_180037922
0x180037918  call    cs:__imp_LocalFree
0x18003791e  mov     [rbp+SecurityDescriptor], rsi
0x180037922  mov     rcx, [rbp+StringSid]; pv
0x180037926  call    cs:__imp_CoTaskMemFree
0x18003792c  mov     [rbp+StringSid], rsi
0x180037930  mov     ebx, [rbp+var_38]
0x180037933  lea     rcx, [rbp+var_48]; this
0x180037937  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18003793c  lea     rcx, [rbp+StringSecurityDescriptor]; this
0x180037940  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180037945  lea     rcx, [rbp+var_38]; this
0x180037949  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003794e  mov     eax, ebx
0x180037950  mov     rbx, [rsp+80h+arg_0]
0x180037958  add     rsp, 80h
0x18003795f  pop     rdi
0x180037960  pop     rsi
0x180037961  pop     rbp
0x180037962  retn
```
