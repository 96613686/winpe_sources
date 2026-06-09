# CSecurityHelper::ResolveSid(CSecurityHelper::CSid const &,ulong,void *)

- ea: `0x180060d38`
- end: `0x180060e7b`
- name: `?ResolveSid@CSecurityHelper@@CAXAEBUCSid@1@KPEAX@Z`
- size: `323`
- prototype: `static void(const struct CSecurityHelper::CSid *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180060850`

## callees

- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180011314`
- `0x180060d38`

## import_xrefs

- `ADVAPI32!CreateWellKnownSid` at `0x180060de3`
- `ADVAPI32!CreateWellKnownSid` at `0x180060de3`
- `ADVAPI32!CopySid` at `0x180060e23`
- `ADVAPI32!CopySid` at `0x180060e23`

## string_xrefs

- `0x180060db9`: `CSecurityHelper::ResolveSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSecurityHelper::ResolveSid(PSID *a1, int a2, void *a3)
{
  _BYTE *v5; // rax
  char v6; // cl
  WELL_KNOWN_SID_TYPE v7; // ecx
  __int16 v8; // cx
  DWORD cbSid; // [rsp+20h] [rbp-30h] BYREF
  int LastFailureAsHRESULT; // [rsp+28h] [rbp-28h] BYREF
  int v11; // [rsp+2Ch] [rbp-24h]
  char v12; // [rsp+30h] [rbp-20h]
  const char *v13; // [rsp+38h] [rbp-18h]
  __int64 v14; // [rsp+40h] [rbp-10h]
  int pExceptionObject; // [rsp+68h] [rbp+18h] BYREF

  pExceptionObject = a2;
  cbSid = 68;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, WPP_4342751f50db37403eb675fae9cba500_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
  }
  if ( (v5[68] & 2) != 0 && v5[65] >= 6u )
  {
    v6 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v6 = 0;
LABEL_9:
  LastFailureAsHRESULT = 0;
  v11 = 459;
  v12 = v6;
  v13 = "CSecurityHelper::ResolveSid";
  v14 = 0;
  v7 = *(_DWORD *)a1;
  LastFailureAsHRESULT = 0;
  if ( v7 )
  {
    if ( !CreateWellKnownSid(v7, a1[1], a3, &cbSid) )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      HIWORD(v11) = 467;
      pExceptionObject = LastFailureAsHRESULT;
      throw (long *)&pExceptionObject;
    }
    v8 = 467;
  }
  else
  {
    if ( !CopySid(cbSid, a3, a1[1]) )
    {
      HIWORD(v11) = 475;
      pExceptionObject = EcsGetLastFailureAsHRESULT();
      throw (long *)&pExceptionObject;
    }
    v8 = 475;
  }
  LOWORD(v11) = v8;
  LastFailureAsHRESULT = 0;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
}

```

## disassembly

```asm
0x180060d38  mov     [rsp-8+arg_0], rbx
0x180060d3d  mov     [rsp-8+arg_10], rdi
0x180060d42  mov     [rsp-8+pExceptionObject], edx
0x180060d46  push    rbp
0x180060d47  mov     rbp, rsp
0x180060d4a  sub     rsp, 50h
0x180060d4e  mov     rdi, r8
0x180060d51  mov     rbx, rcx
0x180060d54  mov     [rbp+cbSid], 44h ; 'D'
0x180060d5b  lea     rcx, WPP_GLOBAL_Control
0x180060d62  mov     rax, cs:WPP_GLOBAL_Control
0x180060d69  cmp     rax, rcx
0x180060d6c  jz      short loc_180060D96
0x180060d6e  test    byte ptr [rax+44h], 2
0x180060d72  jz      short loc_180060DA6
0x180060d74  cmp     byte ptr [rax+41h], 6
0x180060d78  jb      short loc_180060D96
0x180060d7a  mov     edx, 13h
0x180060d7f  lea     r8, WPP_4342751f50db37403eb675fae9cba500_Traceguids
0x180060d86  mov     rcx, [rax+38h]
0x180060d8a  call    WPP_SF_
0x180060d8f  mov     rax, cs:WPP_GLOBAL_Control
0x180060d96  test    byte ptr [rax+44h], 2
0x180060d9a  jz      short loc_180060DA6
0x180060d9c  cmp     byte ptr [rax+41h], 6
0x180060da0  jb      short loc_180060DA6
0x180060da2  mov     cl, 1
0x180060da4  jmp     short loc_180060DA8
0x180060da6  xor     cl, cl
0x180060da8  mov     [rbp+var_28], 0
0x180060daf  mov     [rbp+var_24], 1CBh
0x180060db6  mov     [rbp+var_20], cl
0x180060db9  lea     rax, aCsecurityhelpe_0; "CSecurityHelper::ResolveSid"
0x180060dc0  mov     [rbp+var_18], rax
0x180060dc4  mov     [rbp+var_10], 0
0x180060dcc  mov     ecx, [rbx]; WellKnownSidType
0x180060dce  mov     eax, [rbp+var_28]
0x180060dd1  mov     [rbp+var_28], eax
0x180060dd4  test    ecx, ecx
0x180060dd6  jz      short loc_180060E19
0x180060dd8  lea     r9, [rbp+cbSid]; cbSid
0x180060ddc  mov     r8, rdi; pSid
0x180060ddf  mov     rdx, [rbx+8]; DomainSid
0x180060de3  call    cs:__imp_CreateWellKnownSid
0x180060de9  test    eax, eax
0x180060deb  jnz     short loc_180060E12
0x180060ded  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180060df2  mov     [rbp+var_28], eax
0x180060df5  mov     ecx, 1D3h
0x180060dfa  mov     word ptr [rbp+var_24+2], cx
0x180060dfe  mov     [rbp+pExceptionObject], eax
0x180060e01  lea     rdx, _TI1J; pThrowInfo
0x180060e08  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180060e0c  call    _CxxThrowException_0
0x180060e12  mov     ecx, 1D3h
0x180060e17  jmp     short loc_180060E57
0x180060e19  mov     r8, [rbx+8]; pSourceSid
0x180060e1d  mov     rdx, rdi; pDestinationSid
0x180060e20  mov     ecx, [rbp+cbSid]; nDestinationSidLength
0x180060e23  call    cs:__imp_CopySid
0x180060e29  test    eax, eax
0x180060e2b  jnz     short loc_180060E52
0x180060e2d  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180060e32  mov     [rbp+var_28], eax
0x180060e35  mov     ecx, 1DBh
0x180060e3a  mov     word ptr [rbp+var_24+2], cx
0x180060e3e  mov     [rbp+pExceptionObject], eax
0x180060e41  lea     rdx, _TI1J; pThrowInfo
0x180060e48  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180060e4c  call    _CxxThrowException_0
0x180060e52  mov     ecx, 1DBh
0x180060e57  mov     word ptr [rbp+var_24], cx
0x180060e5b  mov     [rbp+var_28], 0
0x180060e62  lea     rcx, [rbp+var_28]; this
0x180060e66  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180060e6b  mov     rbx, [rsp+50h+arg_0]
0x180060e70  mov     rdi, [rsp+50h+arg_10]
0x180060e75  add     rsp, 50h
0x180060e79  pop     rbp
0x180060e7a  retn
```
