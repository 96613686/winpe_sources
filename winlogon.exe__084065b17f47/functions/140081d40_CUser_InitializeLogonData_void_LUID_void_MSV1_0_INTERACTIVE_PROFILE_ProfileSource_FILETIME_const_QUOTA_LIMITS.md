# CUser::InitializeLogonData(void *,_LUID,void *,_MSV1_0_INTERACTIVE_PROFILE *,ProfileSource,_FILETIME const &,_QUOTA_LIMITS *)

- ea: `0x140081d40`
- end: `0x1400820e3`
- name: `?InitializeLogonData@CUser@@QEAAKPEAXU_LUID@@0PEAU_MSV1_0_INTERACTIVE_PROFILE@@W4ProfileSource@@AEBU_FILETIME@@PEAU_QUOTA_LIMITS@@@Z`
- size: `931`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x140044c90`
- `0x14006cf20`

## callees

- `0x1400057f4`
- `0x140006704`
- `0x14000fd40`
- `0x140039b10`
- `0x14003bb98`
- `0x140041c34`
- `0x14004f03c`
- `0x140081d40`
- `0x140082dc8`
- `0x140099588`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140081dfc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140081dfc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400820ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14009fddf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400820ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14009fddf`
- `ntdll!NtQueryInformationToken` at `0x140081d8f`
- `ntdll!NtQueryInformationToken` at `0x140081e73`
- `ntdll!NtQueryInformationToken` at `0x140081d8f`
- `ntdll!NtQueryInformationToken` at `0x140081e73`
- `ntdll!RtlNtStatusToDosError` at `0x140081da2`
- `ntdll!RtlNtStatusToDosError` at `0x140081e7f`
- `ntdll!RtlNtStatusToDosError` at `0x140081da2`
- `ntdll!RtlNtStatusToDosError` at `0x140081e7f`

## pseudocode

```c
__int64 __fastcall CUser::InitializeLogonData(
        __int64 a1,
        void *a2,
        __int64 a3,
        void *a4,
        __int64 a5,
        int a6,
        _DWORD *a7,
        _OWORD *a8)
{
  PSID *v12; // r14
  int InformationToken; // eax
  unsigned int IsAdminFlag; // edi
  CUser *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  int v18; // eax
  void *v19; // rax
  void *v20; // rax
  ULONG dwBytes[9]; // [rsp+34h] [rbp-24h] BYREF

  dwBytes[0] = 0;
  v12 = 0;
  *(_QWORD *)&dwBytes[1] = 0;
  InformationToken = NtQueryInformationToken(a4, TokenUser, 0, 0, dwBytes);
  if ( InformationToken == -1073741789 )
  {
    v12 = (PSID *)HeapAlloc(*(HANDLE *)(a1 + 8), 8u, dwBytes[0]);
    *(_QWORD *)&dwBytes[1] = v12;
    if ( !v12 )
    {
      IsAdminFlag = 14;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v17);
      }
      goto LABEL_47;
    }
    v18 = NtQueryInformationToken(a4, TokenUser, v12, dwBytes[0], dwBytes);
    if ( v18 >= 0 )
    {
      v19 = DuplicateSID(*v12);
      *(_QWORD *)(a1 + 160) = v19;
      if ( v19 )
      {
        *(_QWORD *)(a1 + 136) = a4;
        IsAdminFlag = CUser::SetIsAdminFlag((CUser *)a1);
        if ( IsAdminFlag )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v16 = 19;
            goto LABEL_46;
          }
          goto LABEL_47;
        }
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
        {
          IsAdminFlag = CUser::SetElevatedToken((CUser *)a1);
          if ( IsAdminFlag )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v16 = 20;
              goto LABEL_46;
            }
            goto LABEL_47;
          }
        }
        if ( (unsigned int)LUAIsShadowAdminEnabled() )
        {
          IsAdminFlag = CUser::SetElevatedSID((CUser *)a1);
          if ( IsAdminFlag )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v16 = 21;
              goto LABEL_46;
            }
            goto LABEL_47;
          }
        }
        v20 = DuplicateSID(a2);
        *(_QWORD *)(a1 + 120) = v20;
        if ( v20 )
        {
          *(_QWORD *)(a1 + 128) = a3;
          *(_QWORD *)(a1 + 240) = a5;
          *(_DWORD *)(a1 + 248) = a6;
          *(_DWORD *)(a1 + 252) = *a7;
          *(_DWORD *)(a1 + 256) = a7[1];
          if ( a8 )
          {
            *(_OWORD *)(a1 + 176) = *a8;
            *(_OWORD *)(a1 + 192) = a8[1];
            *(_OWORD *)(a1 + 208) = a8[2];
          }
          IsAdminFlag = CUser::UpdateUserNames((CUser *)a1);
          if ( IsAdminFlag )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v16 = 22;
              goto LABEL_46;
            }
          }
          goto LABEL_47;
        }
      }
      IsAdminFlag = 14;
      goto LABEL_47;
    }
    IsAdminFlag = RtlNtStatusToDosError(v18);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 18;
      goto LABEL_46;
    }
  }
  else
  {
    if ( InformationToken >= 0 )
      IsAdminFlag = 13;
    else
      IsAdminFlag = RtlNtStatusToDosError(InformationToken);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 16;
LABEL_46:
      WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, IsAdminFlag);
    }
  }
LABEL_47:
  if ( v12 )
    HeapFree(*(HANDLE *)(a1 + 8), 0, v12);
  if ( IsAdminFlag )
  {
    *(_QWORD *)(a1 + 136) = 0;
    *(_QWORD *)(a1 + 240) = 0;
  }
  return IsAdminFlag;
}

```

## disassembly

```asm
0x140081d40  mov     rax, rsp
0x140081d43  mov     [rax+10h], rbx
0x140081d47  mov     [rax+18h], rsi
0x140081d4b  mov     [rax+8], rcx
0x140081d4f  push    rdi
0x140081d50  push    r14
0x140081d52  push    r15
0x140081d54  sub     rsp, 40h
0x140081d58  mov     rdi, r9
0x140081d5b  mov     rbx, r8
0x140081d5e  mov     r15, rdx
0x140081d61  mov     rsi, rcx
0x140081d64  mov     dword ptr [rax-28h], 0
0x140081d6b  mov     dword ptr [rax-24h], 0
0x140081d72  xor     r14d, r14d
0x140081d75  mov     [rax-20h], r14
0x140081d79  lea     rax, [rax-24h]
0x140081d7d  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x140081d82  xor     r9d, r9d; TokenInformationLength
0x140081d85  xor     r8d, r8d; TokenInformation
0x140081d88  lea     edx, [r14+1]; TokenInformationClass
0x140081d8c  mov     rcx, rdi; TokenHandle
0x140081d8f  call    cs:__imp_NtQueryInformationToken
0x140081d95  cmp     eax, 0C0000023h
0x140081d9a  jz      short loc_140081DEE
0x140081d9c  test    eax, eax
0x140081d9e  jns     short loc_140081DB0
0x140081da0  mov     ecx, eax; Status
0x140081da2  call    cs:__imp_RtlNtStatusToDosError
0x140081da8  mov     edi, eax
0x140081daa  mov     [rsp+58h+var_28], eax
0x140081dae  jmp     short loc_140081DB9
0x140081db0  mov     edi, 0Dh
0x140081db5  mov     [rsp+58h+var_28], edi
0x140081db9  lea     rax, WPP_GLOBAL_Control
0x140081dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x140081dc7  cmp     rcx, rax
0x140081dca  jz      loc_14008209F
0x140081dd0  test    byte ptr [rcx+1Ch], 20h
0x140081dd4  jz      loc_14008209F
0x140081dda  cmp     byte ptr [rcx+19h], 2
0x140081dde  jb      loc_14008209F
0x140081de4  mov     edx, 10h
0x140081de9  jmp     loc_14008208B
0x140081dee  mov     r8d, [rsp+58h+dwBytes]; dwBytes
0x140081df3  mov     edx, 8; dwFlags
0x140081df8  mov     rcx, [rsi+8]; hHeap
0x140081dfc  call    cs:__imp_HeapAlloc
0x140081e02  mov     r14, rax
0x140081e05  mov     qword ptr [rsp+58h+dwBytes+4], rax
0x140081e0a  test    rax, rax
0x140081e0d  jnz     short loc_140081E59
0x140081e0f  lea     edi, [rax+0Eh]
0x140081e12  mov     [rsp+58h+var_28], edi
0x140081e16  lea     rax, WPP_GLOBAL_Control
0x140081e1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140081e24  cmp     rcx, rax
0x140081e27  jz      loc_14008209F
0x140081e2d  test    byte ptr [rcx+1Ch], 20h
0x140081e31  jz      loc_14008209F
0x140081e37  cmp     byte ptr [rcx+19h], 2
0x140081e3b  jb      loc_14008209F
0x140081e41  lea     edx, [rdi+3]
0x140081e44  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140081e4b  mov     rcx, [rcx+10h]
0x140081e4f  call    WPP_SF_
0x140081e54  jmp     loc_14008209F
0x140081e59  lea     rax, [rsp+58h+dwBytes]
0x140081e5e  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x140081e63  mov     r9d, [rsp+58h+dwBytes]; TokenInformationLength
0x140081e68  mov     r8, r14; TokenInformation
0x140081e6b  mov     edx, 1; TokenInformationClass
0x140081e70  mov     rcx, rdi; TokenHandle
0x140081e73  call    cs:__imp_NtQueryInformationToken
0x140081e79  test    eax, eax
0x140081e7b  jns     short loc_140081EC0
0x140081e7d  mov     ecx, eax; Status
0x140081e7f  call    cs:__imp_RtlNtStatusToDosError
0x140081e85  mov     edi, eax
0x140081e87  mov     [rsp+58h+var_28], eax
0x140081e8b  lea     rax, WPP_GLOBAL_Control
0x140081e92  mov     rcx, cs:WPP_GLOBAL_Control
0x140081e99  cmp     rcx, rax
0x140081e9c  jz      loc_14008209F
0x140081ea2  test    byte ptr [rcx+1Ch], 20h
0x140081ea6  jz      loc_14008209F
0x140081eac  cmp     byte ptr [rcx+19h], 2
0x140081eb0  jb      loc_14008209F
0x140081eb6  mov     edx, 12h
0x140081ebb  jmp     loc_14008208B
0x140081ec0  mov     rcx, [r14]; SourceSid
0x140081ec3  call    DuplicateSID
0x140081ec8  mov     [rsi+0A0h], rax
0x140081ecf  test    rax, rax
0x140081ed2  jnz     short loc_140081EE2
0x140081ed4  mov     edi, 0Eh
0x140081ed9  mov     [rsp+58h+var_28], edi
0x140081edd  jmp     loc_14008209F
0x140081ee2  mov     [rsi+88h], rdi
0x140081ee9  mov     rcx, rsi; this
0x140081eec  call    ?SetIsAdminFlag@CUser@@AEAAKXZ; CUser::SetIsAdminFlag(void)
0x140081ef1  mov     edi, eax
0x140081ef3  mov     [rsp+58h+var_28], eax
0x140081ef7  test    eax, eax
0x140081ef9  jz      short loc_140081F30
0x140081efb  lea     rax, WPP_GLOBAL_Control
0x140081f02  mov     rcx, cs:WPP_GLOBAL_Control
0x140081f09  cmp     rcx, rax
0x140081f0c  jz      loc_14008209F
0x140081f12  test    byte ptr [rcx+1Ch], 20h
0x140081f16  jz      loc_14008209F
0x140081f1c  cmp     byte ptr [rcx+19h], 2
0x140081f20  jb      loc_14008209F
0x140081f26  mov     edx, 13h
0x140081f2b  jmp     loc_14008208B
0x140081f30  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x140081f37  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x140081f3c  test    al, al
0x140081f3e  jnz     short loc_140081F87
0x140081f40  mov     rcx, rsi; this
0x140081f43  call    ?SetElevatedToken@CUser@@AEAAKXZ; CUser::SetElevatedToken(void)
0x140081f48  mov     edi, eax
0x140081f4a  mov     [rsp+58h+var_28], eax
0x140081f4e  test    eax, eax
0x140081f50  jz      short loc_140081F87
0x140081f52  lea     rax, WPP_GLOBAL_Control
0x140081f59  mov     rcx, cs:WPP_GLOBAL_Control
0x140081f60  cmp     rcx, rax
0x140081f63  jz      loc_14008209F
0x140081f69  test    byte ptr [rcx+1Ch], 20h
0x140081f6d  jz      loc_14008209F
0x140081f73  cmp     byte ptr [rcx+19h], 2
0x140081f77  jb      loc_14008209F
0x140081f7d  mov     edx, 14h
0x140081f82  jmp     loc_14008208B
0x140081f87  call    LUAIsShadowAdminEnabled
0x140081f8c  test    eax, eax
0x140081f8e  jz      short loc_140081FD7
0x140081f90  mov     rcx, rsi; this
0x140081f93  call    ?SetElevatedSID@CUser@@AEAAKXZ; CUser::SetElevatedSID(void)
0x140081f98  mov     edi, eax
0x140081f9a  mov     [rsp+58h+var_28], eax
0x140081f9e  test    eax, eax
0x140081fa0  jz      short loc_140081FD7
0x140081fa2  lea     rax, WPP_GLOBAL_Control
0x140081fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x140081fb0  cmp     rcx, rax
0x140081fb3  jz      loc_14008209F
0x140081fb9  test    byte ptr [rcx+1Ch], 20h
0x140081fbd  jz      loc_14008209F
0x140081fc3  cmp     byte ptr [rcx+19h], 2
0x140081fc7  jb      loc_14008209F
0x140081fcd  mov     edx, 15h
0x140081fd2  jmp     loc_14008208B
0x140081fd7  mov     rcx, r15; SourceSid
0x140081fda  call    DuplicateSID
0x140081fdf  mov     [rsi+78h], rax
0x140081fe3  test    rax, rax
0x140081fe6  jz      loc_140081ED4
0x140081fec  mov     [rsi+80h], rbx
0x140081ff3  mov     rax, [rsp+58h+arg_20]
0x140081ffb  mov     [rsi+0F0h], rax
0x140082002  mov     eax, [rsp+58h+arg_28]
0x140082009  mov     [rsi+0F8h], eax
0x14008200f  mov     rcx, [rsp+58h+arg_30]
0x140082017  mov     eax, [rcx]
0x140082019  mov     [rsi+0FCh], eax
0x14008201f  mov     eax, [rcx+4]
0x140082022  mov     [rsi+100h], eax
0x140082028  mov     rax, [rsp+58h+arg_38]
0x140082030  test    rax, rax
0x140082033  jz      short loc_140082055
0x140082035  movups  xmm0, xmmword ptr [rax]
0x140082038  movups  xmmword ptr [rsi+0B0h], xmm0
0x14008203f  movups  xmm1, xmmword ptr [rax+10h]
0x140082043  movups  xmmword ptr [rsi+0C0h], xmm1
0x14008204a  movups  xmm0, xmmword ptr [rax+20h]
0x14008204e  movups  xmmword ptr [rsi+0D0h], xmm0
0x140082055  mov     rcx, rsi; this
0x140082058  call    ?UpdateUserNames@CUser@@AEAAKXZ; CUser::UpdateUserNames(void)
0x14008205d  mov     edi, eax
0x14008205f  mov     [rsp+58h+var_28], eax
0x140082063  test    eax, eax
0x140082065  jz      short loc_14008209F
0x140082067  lea     rax, WPP_GLOBAL_Control
0x14008206e  mov     rcx, cs:WPP_GLOBAL_Control
0x140082075  cmp     rcx, rax
0x140082078  jz      short loc_14008209F
0x14008207a  test    byte ptr [rcx+1Ch], 20h
0x14008207e  jz      short loc_14008209F
0x140082080  cmp     byte ptr [rcx+19h], 2
0x140082084  jb      short loc_14008209F
0x140082086  mov     edx, 16h
0x14008208b  mov     r9d, edi
0x14008208e  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140082095  mov     rcx, [rcx+10h]
0x140082099  call    WPP_SF_d
0x14008209e  nop
0x14008209f  test    r14, r14
0x1400820a2  jz      short loc_1400820B3
0x1400820a4  mov     r8, r14; lpMem
0x1400820a7  xor     edx, edx; dwFlags
0x1400820a9  mov     rcx, [rsi+8]; hHeap
0x1400820ad  call    cs:__imp_HeapFree
0x1400820b3  test    edi, edi
0x1400820b5  jz      short loc_1400820CD
0x1400820b7  mov     qword ptr [rsi+88h], 0
0x1400820c2  mov     qword ptr [rsi+0F0h], 0
0x1400820cd  mov     eax, edi
0x1400820cf  mov     rbx, [rsp+58h+arg_8]
0x1400820d4  mov     rsi, [rsp+58h+arg_10]
0x1400820d9  add     rsp, 40h
0x1400820dd  pop     r15
0x1400820df  pop     r14
0x1400820e1  pop     rdi
0x1400820e2  retn
0x14009fdc3  push    rbp
0x14009fdc5  sub     rsp, 30h
0x14009fdc9  mov     rbp, rdx
0x14009fdcc  mov     r8, [rbp+38h]; lpMem
0x14009fdd0  test    r8, r8
0x14009fdd3  jz      short loc_14009FDED
0x14009fdd5  xor     edx, edx; dwFlags
0x14009fdd7  mov     rcx, [rbp+60h]
0x14009fddb  mov     rcx, [rcx+8]; hHeap
0x14009fddf  call    cs:__imp_HeapFree
0x14009fde5  mov     qword ptr [rbp+38h], 0
0x14009fded  cmp     dword ptr [rbp+30h], 0
0x14009fdf1  jz      short loc_14009FE0D
0x14009fdf3  mov     rax, [rbp+60h]
0x14009fdf7  mov     qword ptr [rax+88h], 0
0x14009fe02  mov     qword ptr [rax+0F0h], 0
0x14009fe0d  add     rsp, 30h
0x14009fe11  pop     rbp
0x14009fe12  retn
```
