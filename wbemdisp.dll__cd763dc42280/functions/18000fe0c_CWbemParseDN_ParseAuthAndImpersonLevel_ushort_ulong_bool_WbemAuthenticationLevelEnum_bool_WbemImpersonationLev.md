# CWbemParseDN::ParseAuthAndImpersonLevel(ushort *,ulong *,bool &,WbemAuthenticationLevelEnum *,bool &,WbemImpersonationLevelEnum *,CSWbemPrivilegeSet &,ushort * &)

- ea: `0x18000fe0c`
- end: `0x180010180`
- name: `?ParseAuthAndImpersonLevel@CWbemParseDN@@CA_NPEAGPEAKAEA_NPEAW4WbemAuthenticationLevelEnum@@2PEAW4WbemImpersonationLevelEnum@@AEAVCSWbemPrivilegeSet@@AEAPEAG@Z`
- size: `884`
- prototype: `bool __usercall@<al>(unsigned __int16 *@<rcx>, unsigned int *@<rdx>, bool *@<r8>, enum WbemAuthenticationLevelEnum *@<r9>, bool *, enum WbemImpersonationLevelEnum *, struct CSWbemPrivilegeSet *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000e9a0`
- `0x18001051c`

## callees

- `0x18000fe0c`
- `0x180010bbc`
- `0x180024acc`
- `0x180024c04`
- `0x180024d68`

## import_xrefs

- `msvcrt!iswspace` at `0x18000fe88`
- `msvcrt!iswspace` at `0x18000ff56`
- `msvcrt!iswspace` at `0x180010089`
- `msvcrt!iswspace` at `0x180010105`
- `msvcrt!iswspace` at `0x18000fe88`
- `msvcrt!iswspace` at `0x18000ff56`
- `msvcrt!iswspace` at `0x180010089`
- `msvcrt!iswspace` at `0x180010105`
- `msvcrt!_wcsnicmp` at `0x18000fe37`
- `msvcrt!_wcsnicmp` at `0x18000fea9`
- `msvcrt!_wcsnicmp` at `0x18000fefa`
- `msvcrt!_wcsnicmp` at `0x18000ff77`
- `msvcrt!_wcsnicmp` at `0x18000ff94`
- `msvcrt!_wcsnicmp` at `0x18000ffe8`
- `msvcrt!_wcsnicmp` at `0x180010022`
- `msvcrt!_wcsnicmp` at `0x18001005f`
- `msvcrt!_wcsnicmp` at `0x1800100e7`
- `msvcrt!_wcsnicmp` at `0x18000fe37`
- `msvcrt!_wcsnicmp` at `0x18000fea9`
- `msvcrt!_wcsnicmp` at `0x18000fefa`
- `msvcrt!_wcsnicmp` at `0x18000ff77`
- `msvcrt!_wcsnicmp` at `0x18000ff94`
- `msvcrt!_wcsnicmp` at `0x18000ffe8`
- `msvcrt!_wcsnicmp` at `0x180010022`
- `msvcrt!_wcsnicmp` at `0x18001005f`
- `msvcrt!_wcsnicmp` at `0x1800100e7`

## string_xrefs

- `0x18000ffd7`: `impersonationLevel`

## pseudocode

```c
char __fastcall CWbemParseDN::ParseAuthAndImpersonLevel(
        unsigned __int16 *a1,
        unsigned int *a2,
        bool *a3,
        enum WbemAuthenticationLevelEnum *a4,
        bool *a5,
        enum WbemImpersonationLevelEnum *a6,
        struct CSWbemPrivilegeSet *a7,
        unsigned __int16 **a8)
{
  char v11; // si
  bool *v13; // r13
  char v14; // r15
  char v15; // al
  __int64 v16; // rcx
  char v17; // bp
  char i; // r14
  __int64 v19; // rcx
  unsigned __int16 *v20; // rcx
  __int64 j; // rcx
  __int64 k; // rcx
  int v23; // eax
  __int64 v24; // rcx
  bool v25; // zf
  char v26; // [rsp+20h] [rbp-58h]
  char v27; // [rsp+21h] [rbp-57h]
  unsigned int v28[21]; // [rsp+24h] [rbp-54h] BYREF

  v11 = 0;
  if ( _wcsnicmp(a1, L"{", 1u) )
    return 0;
  v13 = a5;
  v14 = 0;
  v27 = 0;
  v15 = 0;
LABEL_4:
  ++*a2;
LABEL_5:
  v26 = v15;
  while ( 1 )
  {
    if ( v15 )
      return 1;
    v16 = *a2;
    v17 = 0;
    for ( i = 0; a1[v16]; v16 = ++*a2 )
    {
      if ( !iswspace(a1[v16]) )
        break;
    }
    if ( !_wcsnicmp(&a1[*a2], L"authenticationLevel", 0x13u) )
    {
      if ( *a3 || v14 )
        break;
      *a2 += 19;
      v17 = 1;
      goto LABEL_13;
    }
    if ( !_wcsnicmp(&a1[*a2], L"impersonationLevel", 0x12u) )
    {
      if ( *v13 || v14 )
        break;
      *a2 += 18;
      goto LABEL_13;
    }
    if ( !_wcsnicmp(&a1[*a2], L"authority", 9u) )
    {
      if ( v27 || v14 )
        break;
      *a2 += 9;
      i = 1;
      goto LABEL_13;
    }
    if ( _wcsnicmp(&a1[*a2], L"(", 1u) || v14 )
      break;
    ++*a2;
    v11 = 1;
LABEL_13:
    v19 = *a2;
    if ( a1[v19] )
    {
      do
      {
        if ( !iswspace(a1[v19]) )
          break;
        v19 = ++*a2;
      }
      while ( a1[v19] );
      v13 = a5;
    }
    v20 = &a1[*a2];
    if ( v11 )
    {
      v11 = 0;
      v28[0] = 0;
      if ( !CWbemParseDN::ParsePrivilegeSet(v20, v28, a7) )
        break;
      *a2 += v28[0];
      v14 = 1;
      v25 = _wcsnicmp(&a1[*a2], L"}", 1u) == 0;
      v15 = v26;
      if ( v25 )
      {
        v15 = 1;
        goto LABEL_4;
      }
    }
    else
    {
      v11 = 0;
      if ( _wcsnicmp(v20, L"=", 1u) )
        break;
      for ( j = ++*a2; a1[j]; j = ++*a2 )
      {
        if ( !iswspace(a1[j]) )
          break;
      }
      if ( v17 )
      {
        if ( !CWbemParseDN::ParseAuthenticationLevel(a1, a2, a4) )
          break;
        *a3 = 1;
      }
      else if ( i )
      {
        if ( !CWbemParseDN::ParseAuthority(a1, a2, a8) )
          break;
        v27 = 1;
      }
      else
      {
        if ( !CWbemParseDN::ParseImpersonationLevel(a1, a2, a6) )
          break;
        *v13 = 1;
      }
      for ( k = *a2; a1[k]; k = ++*a2 )
      {
        if ( !iswspace(a1[k]) )
          break;
      }
      v23 = _wcsnicmp(&a1[*a2], L"}", 1u);
      v24 = *a2;
      if ( !v23 )
      {
        *a2 = v24 + 1;
        v15 = 1;
        goto LABEL_5;
      }
      if ( _wcsnicmp(&a1[v24], L",", 1u) )
        break;
      ++*a2;
      v15 = v26;
    }
  }
  *a3 = 0;
  *v13 = 0;
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x18000fe0c  mov     [rsp+arg_18], r9
0x18000fe11  push    rbx
0x18000fe12  push    rbp
0x18000fe13  push    rsi
0x18000fe14  push    rdi
0x18000fe15  push    r12
0x18000fe17  push    r13
0x18000fe19  push    r14
0x18000fe1b  push    r15
0x18000fe1d  sub     rsp, 38h
0x18000fe21  mov     r12, r8
0x18000fe24  mov     rbx, rdx
0x18000fe27  mov     r8d, 1; MaxCount
0x18000fe2d  lea     rdx, asc_18003AEF0; "{"
0x18000fe34  mov     rdi, rcx
0x18000fe37  call    cs:__imp__wcsnicmp
0x18000fe3d  xor     esi, esi
0x18000fe3f  test    eax, eax
0x18000fe41  jz      short loc_18000FE56
0x18000fe43  xor     al, al
0x18000fe45  add     rsp, 38h
0x18000fe49  pop     r15
0x18000fe4b  pop     r14
0x18000fe4d  pop     r13
0x18000fe4f  pop     r12
0x18000fe51  pop     rdi
0x18000fe52  pop     rsi
0x18000fe53  pop     rbp
0x18000fe54  pop     rbx
0x18000fe55  retn
0x18000fe56  mov     r13, [rsp+78h+arg_20]
0x18000fe5e  mov     r15b, sil
0x18000fe61  mov     [rsp+78h+var_57], sil
0x18000fe66  mov     al, sil
0x18000fe69  inc     dword ptr [rbx]
0x18000fe6b  mov     [rsp+78h+var_58], al
0x18000fe6f  test    al, al
0x18000fe71  jnz     loc_18000FFAD
0x18000fe77  mov     ecx, [rbx]
0x18000fe79  xor     ebp, ebp
0x18000fe7b  mov     r14b, bpl
0x18000fe7e  cmp     [rdi+rcx*2], bp
0x18000fe82  jz      short loc_18000FE96
0x18000fe84  movzx   ecx, word ptr [rdi+rcx*2]; C
0x18000fe88  call    cs:__imp_iswspace
0x18000fe8e  test    eax, eax
0x18000fe90  jnz     loc_18000FFC0
0x18000fe96  mov     eax, [rbx]
0x18000fe98  lea     rdx, aAuthentication; "authenticationLevel"
0x18000fe9f  mov     r8d, 13h; MaxCount
0x18000fea5  lea     rcx, [rdi+rax*2]; String1
0x18000fea9  call    cs:__imp__wcsnicmp
0x18000feaf  test    eax, eax
0x18000feb1  jnz     loc_18000FFD5
0x18000feb7  cmp     [r12], bpl
0x18000febb  jnz     loc_18001016F
0x18000fec1  test    r15b, r15b
0x18000fec4  jnz     loc_18001016F
0x18000feca  add     dword ptr [rbx], 13h
0x18000fecd  mov     bpl, 1
0x18000fed0  xor     edx, edx
0x18000fed2  mov     ecx, [rbx]
0x18000fed4  cmp     [rdi+rcx*2], dx
0x18000fed8  jnz     loc_180010082
0x18000fede  mov     eax, [rbx]
0x18000fee0  lea     rcx, [rdi+rax*2]; unsigned __int16 *
0x18000fee4  test    sil, sil
0x18000fee7  jnz     loc_1800100AD
0x18000feed  mov     r8d, 1; MaxCount
0x18000fef3  lea     rdx, asc_18003AEEC; "="
0x18000fefa  call    cs:__imp__wcsnicmp
0x18000ff00  xor     esi, esi
0x18000ff02  test    eax, eax
0x18000ff04  jnz     loc_180010171
0x18000ff0a  inc     dword ptr [rbx]
0x18000ff0c  mov     ecx, [rbx]
0x18000ff0e  cmp     [rdi+rcx*2], si
0x18000ff12  jnz     loc_180010101
0x18000ff18  mov     rdx, rbx; unsigned int *
0x18000ff1b  mov     rcx, rdi; unsigned __int16 *
0x18000ff1e  test    bpl, bpl
0x18000ff21  jnz     loc_180010124
0x18000ff27  test    r14b, r14b
0x18000ff2a  jnz     loc_18001013F
0x18000ff30  mov     r8, [rsp+78h+arg_28]; enum WbemImpersonationLevelEnum *
0x18000ff38  call    ?ParseImpersonationLevel@CWbemParseDN@@CA_NPEAGPEAKPEAW4WbemImpersonationLevelEnum@@@Z; CWbemParseDN::ParseImpersonationLevel(ushort *,ulong *,WbemImpersonationLevelEnum *)
0x18000ff3d  test    al, al
0x18000ff3f  jz      loc_180010171
0x18000ff45  mov     byte ptr [r13+0], 1
0x18000ff4a  mov     ecx, [rbx]
0x18000ff4c  cmp     [rdi+rcx*2], si
0x18000ff50  jz      short loc_18000FF64
0x18000ff52  movzx   ecx, word ptr [rdi+rcx*2]; C
0x18000ff56  call    cs:__imp_iswspace
0x18000ff5c  test    eax, eax
0x18000ff5e  jnz     loc_18001015A
0x18000ff64  mov     eax, [rbx]
0x18000ff66  lea     rdx, asc_18003AF2C; "}"
0x18000ff6d  mov     r8d, 1; MaxCount
0x18000ff73  lea     rcx, [rdi+rax*2]; String1
0x18000ff77  call    cs:__imp__wcsnicmp
0x18000ff7d  mov     ecx, [rbx]
0x18000ff7f  test    eax, eax
0x18000ff81  jz      short loc_18000FFB4
0x18000ff83  lea     rcx, [rdi+rcx*2]; String1
0x18000ff87  mov     r8d, 1; MaxCount
0x18000ff8d  lea     rdx, asc_18003AFB8; ","
0x18000ff94  call    cs:__imp__wcsnicmp
0x18000ff9a  test    eax, eax
0x18000ff9c  jnz     loc_180010171
0x18000ffa2  inc     dword ptr [rbx]
0x18000ffa4  mov     al, [rsp+78h+var_58]
0x18000ffa8  jmp     loc_18000FE6F
0x18000ffad  mov     al, 1
0x18000ffaf  jmp     loc_18000FE45
0x18000ffb4  lea     eax, [rcx+1]
0x18000ffb7  mov     [rbx], eax
0x18000ffb9  mov     al, 1
0x18000ffbb  jmp     loc_18000FE6B
0x18000ffc0  inc     dword ptr [rbx]
0x18000ffc2  mov     eax, [rbx]
0x18000ffc4  mov     ecx, eax
0x18000ffc6  cmp     [rdi+rax*2], bp
0x18000ffca  jnz     loc_18000FE84
0x18000ffd0  jmp     loc_18000FE96
0x18000ffd5  mov     eax, [rbx]
0x18000ffd7  lea     rdx, aImpersonationl; "impersonationLevel"
0x18000ffde  mov     r8d, 12h; MaxCount
0x18000ffe4  lea     rcx, [rdi+rax*2]; String1
0x18000ffe8  call    cs:__imp__wcsnicmp
0x18000ffee  xor     edx, edx
0x18000fff0  test    eax, eax
0x18000fff2  jnz     short loc_18001000F
0x18000fff4  cmp     [r13+0], dl
0x18000fff8  jnz     loc_18001016F
0x18000fffe  test    r15b, r15b
0x180010001  jnz     loc_18001016F
0x180010007  add     dword ptr [rbx], 12h
0x18001000a  jmp     loc_18000FED2
0x18001000f  mov     eax, [rbx]
0x180010011  lea     rdx, aAuthority; "authority"
0x180010018  mov     r8d, 9; MaxCount
0x18001001e  lea     rcx, [rdi+rax*2]; String1
0x180010022  call    cs:__imp__wcsnicmp
0x180010028  xor     ecx, ecx
0x18001002a  test    eax, eax
0x18001002c  jnz     short loc_18001004C
0x18001002e  cmp     [rsp+78h+var_57], cl
0x180010032  jnz     loc_18001016F
0x180010038  test    r15b, r15b
0x18001003b  jnz     loc_18001016F
0x180010041  add     dword ptr [rbx], 9
0x180010044  mov     r14b, 1
0x180010047  jmp     loc_18000FED0
0x18001004c  mov     eax, [rbx]
0x18001004e  lea     rdx, asc_18003CED4; "("
0x180010055  mov     r8d, 1; MaxCount
0x18001005b  lea     rcx, [rdi+rax*2]; String1
0x18001005f  call    cs:__imp__wcsnicmp
0x180010065  xor     esi, esi
0x180010067  test    eax, eax
0x180010069  jnz     loc_180010171
0x18001006f  test    r15b, r15b
0x180010072  jnz     loc_180010171
0x180010078  inc     dword ptr [rbx]
0x18001007a  mov     sil, 1
0x18001007d  jmp     loc_18000FED0
0x180010082  xor     r13d, r13d
0x180010085  movzx   ecx, word ptr [rdi+rcx*2]; C
0x180010089  call    cs:__imp_iswspace
0x18001008f  test    eax, eax
0x180010091  jz      short loc_1800100A0
0x180010093  inc     dword ptr [rbx]
0x180010095  mov     eax, [rbx]
0x180010097  mov     ecx, eax
0x180010099  cmp     [rdi+rax*2], r13w
0x18001009e  jnz     short loc_180010085
0x1800100a0  mov     r13, [rsp+78h+arg_20]
0x1800100a8  jmp     loc_18000FEDE
0x1800100ad  mov     r8, [rsp+78h+arg_30]; struct CSWbemPrivilegeSet *
0x1800100b5  lea     rdx, [rsp+78h+var_54]; unsigned int *
0x1800100ba  xor     esi, esi
0x1800100bc  mov     [rsp+78h+var_54], esi
0x1800100c0  call    ?ParsePrivilegeSet@CWbemParseDN@@CA_NPEAGPEAKAEAVCSWbemPrivilegeSet@@@Z; CWbemParseDN::ParsePrivilegeSet(ushort *,ulong *,CSWbemPrivilegeSet &)
0x1800100c5  test    al, al
0x1800100c7  jz      loc_180010171
0x1800100cd  mov     eax, [rsp+78h+var_54]
0x1800100d1  lea     r8d, [rsi+1]; MaxCount
0x1800100d5  add     [rbx], eax
0x1800100d7  lea     rdx, asc_18003AF2C; "}"
0x1800100de  mov     eax, [rbx]
0x1800100e0  mov     r15b, 1
0x1800100e3  lea     rcx, [rdi+rax*2]; String1
0x1800100e7  call    cs:__imp__wcsnicmp
0x1800100ed  test    eax, eax
0x1800100ef  mov     al, [rsp+78h+var_58]
0x1800100f3  jnz     loc_18000FE6F
0x1800100f9  mov     al, r15b
0x1800100fc  jmp     loc_18000FE69
0x180010101  movzx   ecx, word ptr [rdi+rcx*2]; C
0x180010105  call    cs:__imp_iswspace
0x18001010b  test    eax, eax
0x18001010d  jz      loc_18000FF18
0x180010113  inc     dword ptr [rbx]
0x180010115  mov     eax, [rbx]
0x180010117  mov     ecx, eax
0x180010119  cmp     [rdi+rax*2], si
0x18001011d  jnz     short loc_180010101
0x18001011f  jmp     loc_18000FF18
0x180010124  mov     r8, [rsp+78h+arg_18]; enum WbemAuthenticationLevelEnum *
0x18001012c  call    ?ParseAuthenticationLevel@CWbemParseDN@@CA_NPEAGPEAKPEAW4WbemAuthenticationLevelEnum@@@Z; CWbemParseDN::ParseAuthenticationLevel(ushort *,ulong *,WbemAuthenticationLevelEnum *)
0x180010131  test    al, al
0x180010133  jz      short loc_180010171
0x180010135  mov     byte ptr [r12], 1
0x18001013a  jmp     loc_18000FF4A
0x18001013f  mov     r8, [rsp+78h+arg_38]; unsigned __int16 **
0x180010147  call    ?ParseAuthority@CWbemParseDN@@CA_NPEAGPEAKAEAPEAG@Z; CWbemParseDN::ParseAuthority(ushort *,ulong *,ushort * &)
0x18001014c  test    al, al
0x18001014e  jz      short loc_180010171
0x180010150  mov     [rsp+78h+var_57], 1
0x180010155  jmp     loc_18000FF4A
0x18001015a  inc     dword ptr [rbx]
0x18001015c  mov     eax, [rbx]
0x18001015e  mov     ecx, eax
0x180010160  cmp     [rdi+rax*2], si
0x180010164  jnz     loc_18000FF52
0x18001016a  jmp     loc_18000FF64
0x18001016f  xor     esi, esi
0x180010171  mov     [r12], sil
0x180010175  mov     [r13+0], sil
0x180010179  mov     [rbx], esi
0x18001017b  jmp     loc_18000FE43
```
