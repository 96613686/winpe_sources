# CSpp::FinalConstruct(void)

- ea: `0x180008b10`
- end: `0x180008c6b`
- name: `?FinalConstruct@CSpp@@AEAAJXZ`
- size: `347`
- prototype: `__int64 __fastcall(CSpp *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006eb8`

## callees

- `0x180007490`
- `0x180008b10`
- `0x18000e2c8`
- `0x18001c940`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x18002d8f4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180008c44`
- `KERNEL32!LocalFree` at `0x180008c44`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180008b87`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180008b87`

## pseudocode

```c
__int64 __fastcall CSpp::FinalConstruct(CSpp *this)
{
  __int64 v2; // rcx
  __int16 v3; // ax
  CSxDiagnostics *v4; // rcx
  unsigned __int16 *v5; // rdx
  CSxDiagnostics *v6; // rcx
  CSxDiagnostics *v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  int LastFailureAsHRESULT; // [rsp+20h] [rbp-40h] BYREF
  __int16 v13; // [rsp+24h] [rbp-3Ch]
  __int16 v14; // [rsp+26h] [rbp-3Ah]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "CSpp::FinalConstruct", 2085, 1);
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v2);
    v3 = 2092;
LABEL_6:
    v14 = v3;
    goto LABEL_14;
  }
  LastFailureAsHRESULT = 0;
  v13 = 2092;
  *((_QWORD *)this + 8) = SecurityDescriptor;
  *((_DWORD *)this + 14) = 24;
  *((_DWORD *)this + 18) = 0;
  SecurityDescriptor = 0;
  LastFailureAsHRESULT = CSpp::_LoadConfig(this);
  v3 = 2105;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_6;
  v4 = (CSxDiagnostics *)*((_QWORD *)this + 13);
  v13 = 2105;
  if ( v4 )
  {
    *((_QWORD *)this + 13) = 0;
    CSxDiagnostics::Release(v4);
  }
  LastFailureAsHRESULT = CSxDiagnostics::CreateInstance((struct CSxDiagnostics **)this + 13);
  v3 = 2110;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_6;
  v6 = (CSxDiagnostics *)*((_QWORD *)this + 13);
  v13 = 2110;
  if ( (unsigned int)CSxDiagnostics::Initialize(v6, v5) == 1 )
  {
    v7 = (CSxDiagnostics *)*((_QWORD *)this + 13);
    if ( v7 )
    {
      *((_QWORD *)this + 13) = 0;
      CSxDiagnostics::Release(v7);
    }
  }
LABEL_14:
  LocalFree(SecurityDescriptor);
  SecurityDescriptor = 0;
  v8 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, v9, v10);
  return v8;
}

```

## disassembly

```asm
0x180008b10  mov     [rsp-8+arg_0], rbx
0x180008b15  push    rbp
0x180008b16  mov     rbp, rsp
0x180008b19  sub     rsp, 60h
0x180008b1d  mov     rbx, rcx
0x180008b20  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b27  lea     rax, WPP_GLOBAL_Control
0x180008b2e  cmp     rcx, rax
0x180008b31  jz      short loc_180008B51
0x180008b33  test    dword ptr [rcx+1Ch], 20000000h
0x180008b3a  jz      short loc_180008B51
0x180008b3c  mov     rcx, [rcx+10h]
0x180008b40  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180008b47  mov     edx, 10h
0x180008b4c  call    WPP_SF_
0x180008b51  mov     r9d, 1; unsigned __int16
0x180008b57  lea     rdx, aCsppFinalconst; "CSpp::FinalConstruct"
0x180008b5e  mov     r8d, 825h; unsigned __int16
0x180008b64  lea     rcx, [rbp+var_40]; this
0x180008b68  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180008b6d  xor     r9d, r9d; SecurityDescriptorSize
0x180008b70  mov     [rbp+SecurityDescriptor], 0
0x180008b78  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180008b7c  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;"...
0x180008b83  lea     edx, [r9+1]; StringSDRevision
0x180008b87  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180008b8d  test    eax, eax
0x180008b8f  jnz     short loc_180008BA7
0x180008b91  call    GetLastFailureAsHRESULT
0x180008b96  mov     [rbp+var_40], eax
0x180008b99  mov     eax, 82Ch
0x180008b9e  mov     [rbp+var_3A], ax
0x180008ba2  jmp     loc_180008C40
0x180008ba7  mov     eax, 82Ch
0x180008bac  mov     [rbp+var_40], 0
0x180008bb3  mov     [rbp+var_3C], ax
0x180008bb7  mov     rcx, rbx; this
0x180008bba  mov     rax, [rbp+SecurityDescriptor]
0x180008bbe  mov     [rbx+40h], rax
0x180008bc2  mov     dword ptr [rbx+38h], 18h
0x180008bc9  mov     dword ptr [rbx+48h], 0
0x180008bd0  mov     [rbp+SecurityDescriptor], 0
0x180008bd8  call    ?_LoadConfig@CSpp@@AEAAJXZ; CSpp::_LoadConfig(void)
0x180008bdd  mov     [rbp+var_40], eax
0x180008be0  test    eax, eax
0x180008be2  mov     eax, 839h
0x180008be7  js      short loc_180008B9E
0x180008be9  mov     rcx, [rbx+68h]; this
0x180008bed  mov     [rbp+var_3C], ax
0x180008bf1  test    rcx, rcx
0x180008bf4  jz      short loc_180008C03
0x180008bf6  mov     qword ptr [rbx+68h], 0
0x180008bfe  call    ?Release@CSxDiagnostics@@QEAAKXZ; CSxDiagnostics::Release(void)
0x180008c03  lea     rcx, [rbx+68h]; struct CSxDiagnostics **
0x180008c07  call    ?CreateInstance@CSxDiagnostics@@SAJPEAPEAV1@@Z; CSxDiagnostics::CreateInstance(CSxDiagnostics * *)
0x180008c0c  mov     [rbp+var_40], eax
0x180008c0f  test    eax, eax
0x180008c11  mov     eax, 83Eh
0x180008c16  js      short loc_180008B9E
0x180008c18  mov     rcx, [rbx+68h]; this
0x180008c1c  mov     [rbp+var_3C], ax
0x180008c20  call    ?Initialize@CSxDiagnostics@@QEAAJPEBG@Z; CSxDiagnostics::Initialize(ushort const *)
0x180008c25  cmp     eax, 1
0x180008c28  jnz     short loc_180008C40
0x180008c2a  mov     rcx, [rbx+68h]; this
0x180008c2e  test    rcx, rcx
0x180008c31  jz      short loc_180008C40
0x180008c33  mov     qword ptr [rbx+68h], 0
0x180008c3b  call    ?Release@CSxDiagnostics@@QEAAKXZ; CSxDiagnostics::Release(void)
0x180008c40  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180008c44  call    cs:__imp_LocalFree
0x180008c4a  mov     [rbp+SecurityDescriptor], 0
0x180008c52  mov     ebx, [rbp+var_40]
0x180008c55  lea     rcx, [rbp+var_40]; this
0x180008c59  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180008c5e  mov     eax, ebx
0x180008c60  mov     rbx, [rsp+60h+arg_0]
0x180008c65  add     rsp, 60h
0x180008c69  pop     rbp
0x180008c6a  retn
```
