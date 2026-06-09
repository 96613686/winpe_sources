# SddlAddAccessFilterAce

- ea: `0x180021930`
- end: `0x180021b50`
- name: `SddlAddAccessFilterAce`
- size: `544`
- prototype: `__int64 __usercall@<rax>(PACL Acl@<rcx>, int, int, void *Src, __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006680`

## callees

- `0x180021930`
- `0x18004f902`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180021aef`
- `ntdll!RtlCopySid` at `0x180021aef`
- `ntdll!RtlValidSid` at `0x1800219bb`
- `ntdll!RtlValidSid` at `0x1800219bb`
- `ntdll!RtlValidAcl` at `0x180021979`
- `ntdll!RtlValidAcl` at `0x180021979`
- `ntdll!RtlLengthSid` at `0x180021a8a`
- `ntdll!RtlLengthSid` at `0x180021ae0`
- `ntdll!RtlLengthSid` at `0x180021afc`
- `ntdll!RtlLengthSid` at `0x180021a8a`
- `ntdll!RtlLengthSid` at `0x180021ae0`
- `ntdll!RtlLengthSid` at `0x180021afc`
- `ntdll!RtlFirstFreeAce` at `0x180021a6f`
- `ntdll!RtlFirstFreeAce` at `0x180021a6f`

## pseudocode

```c
__int64 __fastcall SddlAddAccessFilterAce(
        PACL Acl,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        ACCESS_MASK a6,
        _DWORD *Src,
        unsigned __int16 a8)
{
  __int64 result; // rax
  BYTE AclRevision; // r15
  int v13; // ecx
  bool v14; // zf
  int v15; // ecx
  unsigned int v16; // ebx
  ULONG v17; // edx
  PACE v18; // r14
  ULONG v19; // eax
  ULONG v20; // eax
  PACE Ace; // [rsp+20h] [rbp-10h] BYREF
  BYTE v22; // [rsp+80h] [rbp+50h]

  v22 = a3;
  Ace = 0;
  if ( !Acl || !RtlValidAcl(Acl) )
    return 3221225591LL;
  if ( !Src || (unsigned __int16)(a8 - 6) > 0xFFF8u || *Src != 2020897377 )
    return 3221225485LL;
  if ( !RtlValidSid((PSID)a4) )
    return 3221225592LL;
  AclRevision = 2;
  if ( (a3 & 0x40) != 0 )
  {
    if ( *(_BYTE *)(a4 + 1) != 2 )
      return 3221225485LL;
    v13 = *(_DWORD *)(a4 + 2);
    if ( !v13 )
      v13 = *(unsigned __int16 *)(a4 + 6) - 4864;
    if ( v13 )
      return 3221225485LL;
    if ( *(_DWORD *)(a4 + 8) )
      goto LABEL_21;
    v14 = *(_DWORD *)(a4 + 12) == 0;
  }
  else
  {
    v15 = *(_DWORD *)(a4 + 2);
    if ( !v15 )
      v15 = *(unsigned __int16 *)(a4 + 6) - 256;
    if ( v15 || *(_BYTE *)(a4 + 1) != 1 )
      return 3221225485LL;
    v14 = *(_DWORD *)(a4 + 8) == 0;
  }
  if ( !v14 )
    return 3221225485LL;
LABEL_21:
  if ( Acl->AclRevision > 4u )
    return 3221225561LL;
  if ( Acl->AclRevision > 2u )
    AclRevision = Acl->AclRevision;
  if ( (a3 & 0xFFFFFFA0) != 0 || (a6 & 0xFF000000) != 0 )
    return 3221225485LL;
  if ( !RtlFirstFreeAce(Acl, &Ace) )
    return 3221225591LL;
  v16 = (a8 + 3) & 0xFFFFFFFC;
  v17 = RtlLengthSid((PSID)a4) + v16 + 8;
  if ( v17 < v16 )
    return 534;
  if ( v17 > 0xFFFF )
    return 3221225485LL;
  v18 = Ace;
  if ( !Ace || (char *)Ace + v17 > (char *)Acl + Acl->AclSize )
    return 3221225625LL;
  Ace->Header.AceFlags = v22;
  v18->Header.AceType = 21;
  v18->Header.AceSize = v17;
  v18->AccessMask = a6;
  v19 = RtlLengthSid((PSID)a4);
  RtlCopySid(v19, &v18[1], (PSID)a4);
  v20 = RtlLengthSid((PSID)a4);
  memcpy_0((char *)&v18[1] + v20, Src, a8);
  ++Acl->AceCount;
  result = 0;
  Acl->AclRevision = AclRevision;
  return result;
}

```

## disassembly

```asm
0x180021930  mov     [rsp-38h+arg_8], rbx
0x180021935  mov     [rsp-38h+arg_10], r8d
0x18002193a  push    rbp
0x18002193b  push    rsi
0x18002193c  push    rdi
0x18002193d  push    r12
0x18002193f  push    r13
0x180021941  push    r14
0x180021943  push    r15
0x180021945  mov     rbp, rsp
0x180021948  sub     rsp, 30h
0x18002194c  xor     r14d, r14d
0x18002194f  mov     [rbp+arg_1C], 100h
0x180021955  mov     [rbp+Ace], r14
0x180021959  mov     rdi, r9
0x18002195c  mov     [rbp+arg_18], r14d
0x180021960  mov     ebx, r8d
0x180021963  mov     [rbp+arg_0], r14d
0x180021967  mov     rsi, rcx
0x18002196a  mov     [rbp+arg_4], 1300h
0x180021970  test    rcx, rcx
0x180021973  jz      loc_180021B36
0x180021979  call    cs:__imp_RtlValidAcl
0x18002197f  test    al, al
0x180021981  jz      loc_180021B36
0x180021987  mov     r12, [rbp+Src]
0x18002198b  test    r12, r12
0x18002198e  jz      loc_180021B2F
0x180021994  movzx   eax, [rbp+arg_38]
0x180021998  mov     ecx, 0FFF8h
0x18002199d  sub     ax, 6
0x1800219a1  cmp     ax, cx
0x1800219a4  ja      loc_180021B2F
0x1800219aa  cmp     dword ptr [r12], 78747261h
0x1800219b2  jnz     loc_180021B2F
0x1800219b8  mov     rcx, rdi; Sid
0x1800219bb  call    cs:__imp_RtlValidSid
0x1800219c1  test    al, al
0x1800219c3  jnz     short loc_1800219CF
0x1800219c5  mov     eax, 0C0000078h
0x1800219ca  jmp     loc_180021B3B
0x1800219cf  mov     r15d, 2
0x1800219d5  test    bl, 40h
0x1800219d8  jz      short loc_180021A0A
0x1800219da  cmp     [rdi+1], r15b
0x1800219de  jnz     loc_180021B2F
0x1800219e4  mov     ecx, [rdi+2]
0x1800219e7  sub     ecx, [rbp+arg_0]
0x1800219ea  jnz     short loc_1800219F6
0x1800219ec  movzx   ecx, word ptr [rdi+6]
0x1800219f0  movzx   eax, [rbp+arg_4]
0x1800219f4  sub     ecx, eax
0x1800219f6  test    ecx, ecx
0x1800219f8  jnz     loc_180021B2F
0x1800219fe  cmp     [rdi+8], r14d
0x180021a02  jnz     short loc_180021A38
0x180021a04  cmp     [rdi+0Ch], r14d
0x180021a08  jmp     short loc_180021A32
0x180021a0a  mov     ecx, [rdi+2]
0x180021a0d  sub     ecx, [rbp+arg_18]
0x180021a10  jnz     short loc_180021A1C
0x180021a12  movzx   ecx, word ptr [rdi+6]
0x180021a16  movzx   eax, [rbp+arg_1C]
0x180021a1a  sub     ecx, eax
0x180021a1c  test    ecx, ecx
0x180021a1e  jnz     loc_180021B2F
0x180021a24  cmp     byte ptr [rdi+1], 1
0x180021a28  jnz     loc_180021B2F
0x180021a2e  cmp     [rdi+8], r14d
0x180021a32  jnz     loc_180021B2F
0x180021a38  cmp     byte ptr [rsi], 4
0x180021a3b  ja      loc_180021B28
0x180021a41  cmp     [rsi], r15b
0x180021a44  movzx   eax, byte ptr [rsi]
0x180021a47  cmova   r15d, eax
0x180021a4b  test    ebx, 0FFFFFFA0h
0x180021a51  jnz     loc_180021B2F
0x180021a57  mov     r13d, [rbp+arg_28]
0x180021a5b  test    r13d, 0FF000000h
0x180021a62  jnz     loc_180021B2F
0x180021a68  lea     rdx, [rbp+Ace]; Ace
0x180021a6c  mov     rcx, rsi; Acl
0x180021a6f  call    cs:__imp_RtlFirstFreeAce
0x180021a75  test    al, al
0x180021a77  jz      loc_180021B36
0x180021a7d  movzx   ebx, [rbp+arg_38]
0x180021a81  mov     rcx, rdi; Sid
0x180021a84  add     ebx, 3
0x180021a87  and     ebx, 0FFFFFFFCh
0x180021a8a  call    cs:__imp_RtlLengthSid
0x180021a90  lea     edx, [rbx+8]
0x180021a93  add     edx, eax
0x180021a95  cmp     edx, ebx
0x180021a97  jnb     short loc_180021AA3
0x180021a99  mov     eax, 216h
0x180021a9e  jmp     loc_180021B3B
0x180021aa3  cmp     edx, 0FFFFh
0x180021aa9  ja      loc_180021B2F
0x180021aaf  mov     r14, [rbp+Ace]
0x180021ab3  test    r14, r14
0x180021ab6  jz      short loc_180021B21
0x180021ab8  movzx   ecx, word ptr [rsi+2]
0x180021abc  mov     eax, edx
0x180021abe  add     rcx, rsi
0x180021ac1  add     rax, r14
0x180021ac4  cmp     rax, rcx
0x180021ac7  ja      short loc_180021B21
0x180021ac9  mov     eax, [rbp+arg_10]
0x180021acc  mov     rcx, rdi; Sid
0x180021acf  mov     [r14+1], al
0x180021ad3  mov     byte ptr [r14], 15h
0x180021ad7  mov     [r14+2], dx
0x180021adc  mov     [r14+4], r13d
0x180021ae0  call    cs:__imp_RtlLengthSid
0x180021ae6  mov     r8, rdi; SourceSid
0x180021ae9  lea     rdx, [r14+8]; DestinationSid
0x180021aed  mov     ecx, eax; DestinationSidLength
0x180021aef  call    cs:__imp_RtlCopySid
0x180021af5  movzx   ebx, [rbp+arg_38]
0x180021af9  mov     rcx, rdi; Sid
0x180021afc  call    cs:__imp_RtlLengthSid
0x180021b02  mov     ecx, eax
0x180021b04  mov     r8d, ebx; Size
0x180021b07  add     rcx, 8
0x180021b0b  mov     rdx, r12; Src
0x180021b0e  add     rcx, r14; void *
0x180021b11  call    memcpy_0
0x180021b16  inc     word ptr [rsi+4]
0x180021b1a  xor     eax, eax
0x180021b1c  mov     [rsi], r15b
0x180021b1f  jmp     short loc_180021B3B
0x180021b21  mov     eax, 0C0000099h
0x180021b26  jmp     short loc_180021B3B
0x180021b28  mov     eax, 0C0000059h
0x180021b2d  jmp     short loc_180021B3B
0x180021b2f  mov     eax, 0C000000Dh
0x180021b34  jmp     short loc_180021B3B
0x180021b36  mov     eax, 0C0000077h
0x180021b3b  mov     rbx, [rsp+30h+arg_8]
0x180021b40  add     rsp, 30h
0x180021b44  pop     r15
0x180021b46  pop     r14
0x180021b48  pop     r13
0x180021b4a  pop     r12
0x180021b4c  pop     rdi
0x180021b4d  pop     rsi
0x180021b4e  pop     rbp
0x180021b4f  retn
```
