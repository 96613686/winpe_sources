# MpCheckForAmHardening

- ea: `0x140046e30`
- end: `0x1400471a9`
- name: `MpCheckForAmHardening`
- size: `889`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14003dd40`
- `0x140044e6c`
- `0x140045670`
- `0x140046090`
- `0x14007ab88`

## callees

- `0x1400051bc`
- `0x1400118d0`
- `0x140046e30`

## import_xrefs

- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140047016`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140047016`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140046ffc`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140046ffc`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140047083`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400470bc`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140047083`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400470bc`
- `FLTMGR!FltReleaseContext` at `0x14004706e`
- `FLTMGR!FltReleaseContext` at `0x140047198`
- `FLTMGR!FltReleaseContext` at `0x14004706e`
- `FLTMGR!FltReleaseContext` at `0x140047198`
- `FLTMGR!FltGetInstanceContext` at `0x140047041`
- `FLTMGR!FltGetInstanceContext` at `0x140047041`

## pseudocode

```c
char __fastcall MpCheckForAmHardening(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  _DWORD *v9; // rax
  __int64 v10; // rcx
  char v11; // bl
  char v12; // dl
  __int64 v13; // rcx
  bool v14; // dl
  char v15; // al
  char v16; // al
  bool v17; // al
  __int64 v19; // rcx
  ULONG_PTR v20; // rdx
  PACCESS_TOKEN v21; // rax
  NTSTATUS InstanceContext; // eax
  unsigned __int64 v23; // rbx
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rbx
  ULONG TimeIncrement; // eax
  int v27; // edx
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int8 CopyOnOpen[3]; // [rsp+39h] [rbp-3Fh] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+3Ch] [rbp-3Ch] BYREF

  Context = 0;
  if ( *(_DWORD *)(MpData + 2444) )
    return 0;
  v9 = (_DWORD *)MpData;
  if ( !*(_QWORD *)(MpData + 232) )
  {
    v23 = MEMORY[0xFFFFF78000000320];
    v24 = 0x861C46800uLL / KeQueryTimeIncrement();
    v9 = (_DWORD *)MpData;
    if ( *(_QWORD *)(MpData + 4032) + v24 < v23 )
      return 0;
  }
  if ( (v9[978] & 1) != 0 )
    return 0;
  if ( v9[1043] || (v19 = *(_QWORD *)(a1 + 16), *(_BYTE *)(v19 + 4)) )
  {
    v10 = *(_QWORD *)(a1 + 16);
    v11 = 0;
    if ( *(_BYTE *)(v10 + 4) == 13 )
    {
      v27 = *(_DWORD *)(v10 + 40);
      if ( v27 == 590039 || v27 == 590043 )
      {
        v12 = 1;
        goto LABEL_7;
      }
    }
  }
  else
  {
    if ( (*(_DWORD *)(v19 + 32) & 1) != 0 )
      return 0;
    v11 = 0;
  }
  v12 = 0;
LABEL_7:
  if ( (v9[1013] & 1) != 0 )
  {
    if ( v12 )
    {
      CopyOnOpen[0] = 0;
      EffectiveOnly = 0;
      ImpersonationLevel = SecurityAnonymous;
      v21 = PsReferenceImpersonationToken(KeGetCurrentThread(), CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
      if ( v21 )
      {
        v11 = 1;
        PsDereferenceImpersonationToken(v21);
      }
    }
  }
  v13 = *(_QWORD *)(a1 + 16);
  v14 = 0;
  v15 = *(_BYTE *)(v13 + 4);
  if ( v15 )
  {
    if ( v15 == 13 && *(_DWORD *)(v13 + 40) == 623112 )
    {
      v16 = 1;
      goto LABEL_11;
    }
  }
  else
  {
    v14 = (*(_BYTE *)(v13 + 6) & 2) != 0;
  }
  v16 = 0;
LABEL_11:
  v17 = dword_140026A20 && *(_DWORD *)(a4 + 240) == 21 && v16;
  if ( !v11 && !v14 && !v17 )
  {
    if ( !a4 )
      return 0;
    if ( *(_DWORD *)(MpData + 2444) )
      return 0;
    v20 = MpData;
    if ( !*(_QWORD *)(MpData + 232) )
    {
      v25 = MEMORY[0xFFFFF78000000320];
      TimeIncrement = KeQueryTimeIncrement();
      v20 = MpData;
      if ( *(_QWORD *)(MpData + 4032) + 0x861C46800uLL / TimeIncrement < v25 )
        return 0;
    }
    if ( (*(_DWORD *)(a4 + 240) != 21 || *(_QWORD *)(v20 + 232)) && (*(_DWORD *)(a4 + 288) & 0x10) != 0 )
      return 0;
  }
  if ( a5 )
    return 1;
  if ( !a3 )
  {
    InstanceContext = FltGetInstanceContext(*(PFLT_INSTANCE *)(a2 + 24), &Context);
    if ( InstanceContext < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        90,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        *(_QWORD *)(a1 + 8),
        InstanceContext);
    }
    if ( Context )
    {
      if ( (*((_DWORD *)Context + 20) & 1) == 0 )
      {
        FltReleaseContext(Context);
        return 0;
      }
      FltReleaseContext(Context);
    }
    return 1;
  }
  return *(_BYTE *)(a3 + 80) & 1;
}

```

## disassembly

```asm
0x140046e30  mov     [rsp+arg_10], rbx
0x140046e35  mov     [rsp+arg_18], rbp
0x140046e3a  push    rsi
0x140046e3b  push    rdi
0x140046e3c  push    r12
0x140046e3e  push    r13
0x140046e40  push    r14
0x140046e42  sub     rsp, 50h
0x140046e46  mov     rax, cs:__security_cookie
0x140046e4d  xor     rax, rsp
0x140046e50  mov     [rsp+78h+var_38], rax
0x140046e55  mov     rax, cs:MpData
0x140046e5c  mov     rdi, rcx
0x140046e5f  mov     [rsp+78h+Context], 0
0x140046e68  mov     rsi, r9
0x140046e6b  mov     rbp, r8
0x140046e6e  mov     r14, rdx
0x140046e71  mov     ecx, [rax+98Ch]
0x140046e77  test    ecx, ecx
0x140046e79  jnz     loc_140046F3D
0x140046e7f  mov     rax, cs:MpData
0x140046e86  mov     r13, 0FFFFF78000000320h
0x140046e90  mov     r12, 861C46800h
0x140046e9a  cmp     qword ptr [rax+0E8h], 0
0x140046ea2  jz      loc_14004707F
0x140046ea8  mov     ecx, [rax+0F48h]
0x140046eae  test    cl, 1
0x140046eb1  jnz     loc_140046F3D
0x140046eb7  cmp     dword ptr [rax+104Ch], 0
0x140046ebe  jz      short loc_140046F27
0x140046ec0  mov     rcx, [rdi+10h]
0x140046ec4  xor     bl, bl
0x140046ec6  cmp     byte ptr [rcx+4], 0Dh
0x140046eca  jz      loc_1400470F5
0x140046ed0  xor     dl, dl
0x140046ed2  mov     ecx, [rax+0FD4h]
0x140046ed8  test    cl, 1
0x140046edb  jnz     loc_140046FCA
0x140046ee1  mov     rcx, [rdi+10h]
0x140046ee5  xor     dl, dl
0x140046ee7  movzx   eax, byte ptr [rcx+4]
0x140046eeb  test    al, al
0x140046eed  jz      loc_140047027
0x140046ef3  cmp     al, 0Dh
0x140046ef5  jz      loc_140047113
0x140046efb  xor     al, al
0x140046efd  cmp     cs:dword_140026A20, 0
0x140046f04  jz      short loc_140046F13
0x140046f06  cmp     dword ptr [rsi+0F0h], 15h
0x140046f0d  jz      loc_140047127
0x140046f13  xor     al, al
0x140046f15  test    bl, bl
0x140046f17  jz      short loc_140046F77
0x140046f19  cmp     [rsp+78h+arg_20], 0
0x140046f21  jz      short loc_140046F66
0x140046f23  mov     al, 1
0x140046f25  jmp     short loc_140046F3F
0x140046f27  mov     rcx, [rdi+10h]
0x140046f2b  cmp     byte ptr [rcx+4], 0
0x140046f2f  jnz     short loc_140046EC0
0x140046f31  mov     ecx, [rcx+20h]
0x140046f34  test    cl, 1
0x140046f37  jz      loc_1400470EE
0x140046f3d  xor     al, al
0x140046f3f  mov     rcx, [rsp+78h+var_38]
0x140046f44  xor     rcx, rsp; StackCookie
0x140046f47  call    __security_check_cookie
0x140046f4c  lea     r11, [rsp+78h+var_28]
0x140046f51  mov     rbx, [r11+40h]
0x140046f55  mov     rbp, [r11+48h]
0x140046f59  mov     rsp, r11
0x140046f5c  pop     r14
0x140046f5e  pop     r13
0x140046f60  pop     r12
0x140046f62  pop     rdi
0x140046f63  pop     rsi
0x140046f64  retn
0x140046f66  test    rbp, rbp
0x140046f69  jz      loc_140047038
0x140046f6f  movzx   eax, byte ptr [rbp+50h]
0x140046f73  and     al, 1
0x140046f75  jmp     short loc_140046F3F
0x140046f77  test    dl, dl
0x140046f79  jnz     short loc_140046F19
0x140046f7b  test    al, al
0x140046f7d  jnz     short loc_140046F19
0x140046f7f  test    rsi, rsi
0x140046f82  jz      short loc_140046F3D
0x140046f84  mov     rcx, cs:MpData
0x140046f8b  mov     edx, [rcx+98Ch]
0x140046f91  test    edx, edx
0x140046f93  jnz     short loc_140046F3D
0x140046f95  mov     rdx, cs:MpData
0x140046f9c  cmp     qword ptr [rdx+0E8h], 0
0x140046fa4  jz      loc_1400470B8
0x140046faa  cmp     dword ptr [rsi+0F0h], 15h
0x140046fb1  jz      loc_140047136
0x140046fb7  mov     eax, [rsi+120h]
0x140046fbd  test    al, 10h
0x140046fbf  jnz     loc_140046F3D
0x140046fc5  jmp     loc_140046F19
0x140046fca  test    dl, dl
0x140046fcc  jz      loc_140046EE1
0x140046fd2  mov     [rsp+78h+CopyOnOpen], 0
0x140046fd7  lea     r9, [rsp+78h+ImpersonationLevel]; ImpersonationLevel
0x140046fdc  mov     [rsp+78h+EffectiveOnly], 0
0x140046fe1  lea     r8, [rsp+78h+EffectiveOnly]; EffectiveOnly
0x140046fe6  mov     [rsp+78h+ImpersonationLevel], 0
0x140046fee  lea     rdx, [rsp+78h+CopyOnOpen]; CopyOnOpen
0x140046ff3  mov     rcx, gs:188h; Thread
0x140046ffc  call    cs:__imp_PsReferenceImpersonationToken
0x140047003  nop     dword ptr [rax+rax+00h]
0x140047008  test    rax, rax
0x14004700b  jz      loc_140046EE1
0x140047011  mov     rcx, rax; ImpersonationToken
0x140047014  mov     bl, 1
0x140047016  call    cs:__imp_PsDereferenceImpersonationToken
0x14004701d  nop     dword ptr [rax+rax+00h]
0x140047022  jmp     loc_140046EE1
0x140047027  test    byte ptr [rcx+6], 2
0x14004702b  jz      loc_140046EFB
0x140047031  mov     dl, 1
0x140047033  jmp     loc_140046EFB
0x140047038  mov     rcx, [r14+18h]; Instance
0x14004703c  lea     rdx, [rsp+78h+Context]; Context
0x140047041  call    cs:__imp_FltGetInstanceContext
0x140047048  nop     dword ptr [rax+rax+00h]
0x14004704d  test    eax, eax
0x14004704f  js      loc_140047149
0x140047055  mov     rcx, [rsp+78h+Context]; Context
0x14004705a  test    rcx, rcx
0x14004705d  jz      loc_140046F23
0x140047063  mov     eax, [rcx+50h]
0x140047066  test    al, 1
0x140047068  jz      loc_140047198
0x14004706e  call    cs:__imp_FltReleaseContext
0x140047075  nop     dword ptr [rax+rax+00h]
0x14004707a  jmp     loc_140046F23
0x14004707f  mov     rbx, [r13+0]
0x140047083  call    cs:__imp_KeQueryTimeIncrement
0x14004708a  nop     dword ptr [rax+rax+00h]
0x14004708f  xor     edx, edx
0x140047091  mov     ecx, eax
0x140047093  mov     rax, r12
0x140047096  div     rcx
0x140047099  mov     rdx, rax
0x14004709c  mov     rax, cs:MpData
0x1400470a3  add     rdx, [rax+0FC0h]
0x1400470aa  cmp     rdx, rbx
0x1400470ad  jnb     loc_140046EA8
0x1400470b3  jmp     loc_140046F3D
0x1400470b8  mov     rbx, [r13+0]
0x1400470bc  call    cs:__imp_KeQueryTimeIncrement
0x1400470c3  nop     dword ptr [rax+rax+00h]
0x1400470c8  mov     ecx, eax
0x1400470ca  xor     edx, edx
0x1400470cc  mov     rax, r12
0x1400470cf  div     rcx
0x1400470d2  mov     rdx, cs:MpData
0x1400470d9  add     rax, [rdx+0FC0h]
0x1400470e0  cmp     rax, rbx
0x1400470e3  jnb     loc_140046FAA
0x1400470e9  jmp     loc_140046F3D
0x1400470ee  xor     bl, bl
0x1400470f0  jmp     loc_140046ED0
0x1400470f5  mov     edx, [rcx+28h]
0x1400470f8  cmp     edx, 900D7h
0x1400470fe  jz      short loc_14004710C
0x140047100  cmp     edx, 900DBh
0x140047106  jnz     loc_140046ED0
0x14004710c  mov     dl, 1
0x14004710e  jmp     loc_140046ED2
0x140047113  cmp     dword ptr [rcx+28h], 98208h
0x14004711a  jnz     loc_140046EFB
0x140047120  mov     al, 1
0x140047122  jmp     loc_140046EFD
0x140047127  test    al, al
0x140047129  jz      loc_140046F13
0x14004712f  mov     al, 1
0x140047131  jmp     loc_140046F15
0x140047136  cmp     qword ptr [rdx+0E8h], 0
0x14004713e  jz      loc_140046F19
0x140047144  jmp     loc_140046FB7
0x140047149  mov     rcx, cs:WPP_GLOBAL_Control
0x140047150  lea     rdx, WPP_GLOBAL_Control
0x140047157  cmp     rcx, rdx
0x14004715a  jz      loc_140047055
0x140047160  mov     ecx, [rcx+2Ch]
0x140047163  test    cl, 1
0x140047166  jz      loc_140047055
0x14004716c  lfence
0x14004716f  mov     rcx, cs:WPP_GLOBAL_Control
0x140047176  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x14004717d  mov     r9, [rdi+8]
0x140047181  mov     edx, 5Ah ; 'Z'
0x140047186  mov     [rsp+78h+var_58], eax
0x14004718a  mov     rcx, [rcx+18h]
0x14004718e  call    WPP_SF_qD
0x140047193  jmp     loc_140047055
0x140047198  call    cs:__imp_FltReleaseContext
0x14004719f  nop     dword ptr [rax+rax+00h]
0x1400471a4  jmp     loc_140046F3D
```
