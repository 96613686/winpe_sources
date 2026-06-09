# SddlAddProcessTrustLabelAce

- ea: `0x1800172e4`
- end: `0x180017427`
- name: `SddlAddProcessTrustLabelAce`
- size: `323`
- prototype: `__int64 __usercall@<rax>(PACL Acl@<rcx>, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006680`

## callees

- `0x1800172e4`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800173eb`
- `ntdll!RtlCopySid` at `0x1800173eb`
- `ntdll!RtlValidSid` at `0x18001732e`
- `ntdll!RtlValidSid` at `0x18001732e`
- `ntdll!RtlValidAcl` at `0x18001731d`
- `ntdll!RtlValidAcl` at `0x18001731d`
- `ntdll!RtlLengthSid` at `0x1800173a3`
- `ntdll!RtlLengthSid` at `0x1800173dc`
- `ntdll!RtlLengthSid` at `0x1800173a3`
- `ntdll!RtlLengthSid` at `0x1800173dc`
- `ntdll!RtlFirstFreeAce` at `0x180017396`
- `ntdll!RtlFirstFreeAce` at `0x180017396`

## pseudocode

```c
__int64 __fastcall SddlAddProcessTrustLabelAce(PACL Acl, __int64 a2, int a3, __int64 a4, int a5, int a6)
{
  __int64 result; // rax
  int v10; // ecx
  BYTE AclRevision; // bp
  int v12; // r14d
  __int16 v13; // ax
  PACE v14; // rbx
  __int64 v15; // rdx
  ULONG v16; // eax
  PACE Ace; // [rsp+68h] [rbp+20h] BYREF

  Ace = 0;
  if ( !Acl || !RtlValidAcl(Acl) )
    return 3221225591LL;
  if ( !RtlValidSid((PSID)a4) )
    return 3221225592LL;
  v10 = *(_DWORD *)(a4 + 2);
  if ( !v10 )
    v10 = *(unsigned __int16 *)(a4 + 6) - 4864;
  if ( v10 )
    return 3221225485LL;
  if ( Acl->AclRevision > 4u )
    return 3221225561LL;
  AclRevision = 2;
  if ( Acl->AclRevision > 2u )
    AclRevision = Acl->AclRevision;
  if ( (a3 & 0xFFFFFFE0) != 0 )
    return 3221225485LL;
  v12 = a6;
  if ( (a6 & 0xFF000000) != 0 )
    return 3221225485LL;
  if ( !RtlFirstFreeAce(Acl, &Ace) )
    return 3221225591LL;
  v13 = RtlLengthSid((PSID)a4);
  v14 = Ace;
  if ( !Ace )
    return 3221225625LL;
  v15 = (unsigned __int16)(v13 + 8);
  if ( (char *)Ace + v15 > (char *)Acl + Acl->AclSize )
    return 3221225625LL;
  Ace->Header.AceFlags = a3;
  v14->Header.AceType = 20;
  v14->Header.AceSize = v15;
  v14->AccessMask = v12;
  v16 = RtlLengthSid((PSID)a4);
  RtlCopySid(v16, &v14[1], (PSID)a4);
  ++Acl->AceCount;
  result = 0;
  Acl->AclRevision = AclRevision;
  return result;
}

```

## disassembly

```asm
0x1800172e4  mov     rax, rsp
0x1800172e7  mov     [rax+10h], rbx
0x1800172eb  push    rbp
0x1800172ec  push    rsi
0x1800172ed  push    rdi
0x1800172ee  push    r14
0x1800172f0  push    r15
0x1800172f2  sub     rsp, 20h
0x1800172f6  mov     qword ptr [rax+20h], 0
0x1800172fe  mov     rsi, r9
0x180017301  mov     dword ptr [rax+8], 0
0x180017308  mov     r15d, r8d
0x18001730b  mov     word ptr [rax+0Ch], 1300h
0x180017311  mov     rdi, rcx
0x180017314  test    rcx, rcx
0x180017317  jz      loc_180017411
0x18001731d  call    cs:__imp_RtlValidAcl
0x180017323  test    al, al
0x180017325  jz      loc_180017411
0x18001732b  mov     rcx, rsi; Sid
0x18001732e  call    cs:__imp_RtlValidSid
0x180017334  test    al, al
0x180017336  jnz     short loc_180017342
0x180017338  mov     eax, 0C0000078h
0x18001733d  jmp     loc_180017416
0x180017342  mov     ecx, [rsi+2]
0x180017345  sub     ecx, [rsp+48h+arg_0]
0x180017349  jnz     short loc_180017356
0x18001734b  movzx   ecx, word ptr [rsi+6]
0x18001734f  movzx   eax, [rsp+48h+arg_4]
0x180017354  sub     ecx, eax
0x180017356  test    ecx, ecx
0x180017358  jnz     loc_18001740A
0x18001735e  cmp     byte ptr [rdi], 4
0x180017361  ja      loc_180017403
0x180017367  movzx   eax, byte ptr [rdi]
0x18001736a  lea     ebp, [rcx+2]
0x18001736d  cmp     [rdi], bpl
0x180017370  cmova   ebp, eax
0x180017373  test    r15d, 0FFFFFFE0h
0x18001737a  jnz     loc_18001740A
0x180017380  mov     r14d, [rsp+48h+arg_28]
0x180017385  test    r14d, 0FF000000h
0x18001738c  jnz     short loc_18001740A
0x18001738e  lea     rdx, [rsp+48h+Ace]; Ace
0x180017393  mov     rcx, rdi; Acl
0x180017396  call    cs:__imp_RtlFirstFreeAce
0x18001739c  test    al, al
0x18001739e  jz      short loc_180017411
0x1800173a0  mov     rcx, rsi; Sid
0x1800173a3  call    cs:__imp_RtlLengthSid
0x1800173a9  mov     rbx, [rsp+48h+Ace]
0x1800173ae  test    rbx, rbx
0x1800173b1  jz      short loc_1800173FC
0x1800173b3  movzx   ecx, word ptr [rdi+2]
0x1800173b7  add     ax, 8
0x1800173bb  movzx   edx, ax
0x1800173be  add     rcx, rdi
0x1800173c1  lea     rax, [rbx+rdx]
0x1800173c5  cmp     rax, rcx
0x1800173c8  ja      short loc_1800173FC
0x1800173ca  mov     rcx, rsi; Sid
0x1800173cd  mov     [rbx+1], r15b
0x1800173d1  mov     byte ptr [rbx], 14h
0x1800173d4  mov     [rbx+2], dx
0x1800173d8  mov     [rbx+4], r14d
0x1800173dc  call    cs:__imp_RtlLengthSid
0x1800173e2  mov     r8, rsi; SourceSid
0x1800173e5  lea     rdx, [rbx+8]; DestinationSid
0x1800173e9  mov     ecx, eax; DestinationSidLength
0x1800173eb  call    cs:__imp_RtlCopySid
0x1800173f1  inc     word ptr [rdi+4]
0x1800173f5  xor     eax, eax
0x1800173f7  mov     [rdi], bpl
0x1800173fa  jmp     short loc_180017416
0x1800173fc  mov     eax, 0C0000099h
0x180017401  jmp     short loc_180017416
0x180017403  mov     eax, 0C0000059h
0x180017408  jmp     short loc_180017416
0x18001740a  mov     eax, 0C000000Dh
0x18001740f  jmp     short loc_180017416
0x180017411  mov     eax, 0C0000077h
0x180017416  mov     rbx, [rsp+48h+arg_8]
0x18001741b  add     rsp, 20h
0x18001741f  pop     r15
0x180017421  pop     r14
0x180017423  pop     rdi
0x180017424  pop     rsi
0x180017425  pop     rbp
0x180017426  retn
```
