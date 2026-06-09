# SampSetUserAccountControl

- ea: `0x1800a56d0`
- end: `0x1800a5d2c`
- name: `SampSetUserAccountControl`
- size: `1628`
- prototype: `__int64 __usercall@<rax>(struct _SAMP_OBJECT *@<rcx>, struct _DOMAIN_PASSWORD_INFORMATION *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800291c0`

## callees

- `0x180012a28`
- `0x1800198a0`
- `0x180020aa0`
- `0x180022678`
- `0x180027d08`
- `0x180027e24`
- `0x180028370`
- `0x18002cd80`
- `0x1800372ac`
- `0x180053278`
- `0x180072ff0`
- `0x180076b14`
- `0x18007780c`
- `0x1800a0a58`
- `0x1800a4b00`
- `0x1800a56d0`
- `0x1800a81a4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a5c1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a5c1f`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtEnforceComputerClassForDomainController` at `0x1800a583b`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtEnforceComputerClassForDomainController` at `0x1800a583b`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtEnforceObjectClassAndSamAccountTypeMatch` at `0x1800a57d4`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtEnforceObjectClassAndSamAccountTypeMatch` at `0x1800a57d4`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtValidatePrivilegedAccountControlFlags` at `0x1800a5789`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtValidatePrivilegedAccountControlFlags` at `0x1800a5789`
- `CRYPTSP!SystemFunction007` at `0x1800a5ae5`
- `CRYPTSP!SystemFunction007` at `0x1800a5ae5`

## pseudocode

```c
__int64 __fastcall SampSetUserAccountControl(
        struct _SAMP_OBJECT *a1,
        int a2,
        __int64 a3,
        char a4,
        struct _DOMAIN_PASSWORD_INFORMATION *a5,
        _BYTE *a6,
        _BYTE *a7,
        void *a8)
{
  unsigned int v9; // edi
  int IsUserAccountControlValid; // eax
  char v13; // r9
  signed int updated; // ebx
  int v15; // eax
  int v16; // eax
  __int64 v17; // r8
  char v18; // cl
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rcx
  char *v23; // rax
  int UnicodeStringAttribute; // eax
  struct _SAMP_OBJECT *v25; // rcx
  HLOCAL *v26; // rax
  __int64 v27; // r14
  __int64 v28; // rcx
  UCHAR *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rcx
  UCHAR *v32; // rax
  __int128 *v33; // rax
  bool v34; // zf
  unsigned int v35; // eax
  PUNICODE_STRING v36; // rcx
  int v37; // edx
  int v38; // r8d
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+28h] [rbp-D8h]
  unsigned int v42; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v44; // [rsp+88h] [rbp-78h] BYREF
  UCHAR pbBuffer[528]; // [rsp+A0h] [rbp-60h] BYREF

  v9 = a2 & 0xFFFDFFFF;
  hMem[0] = a8;
  v42 = *(_DWORD *)(a3 + 56);
  *a7 = 0;
  IsUserAccountControlValid = SampIsUserAccountControlValid(a1, a2 & 0xFFFDFFFF, a5);
  v13 = 0;
  updated = IsUserAccountControlValid;
  if ( IsUserAccountControlValid < 0 )
    goto LABEL_83;
  if ( (*((_BYTE *)a1 + 20) & 0x20) == 0 )
  {
    if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
    {
      v15 = SampShouldCallNtdsaApiSet();
      v13 = 0;
      updated = v15;
      if ( v15 == -1073741637 )
      {
        updated = 0;
      }
      else if ( v15 >= 0 )
      {
        updated = NtdsaExtValidatePrivilegedAccountControlFlags(a1, v9, a3, 0);
        v13 = 0;
      }
      if ( updated < 0 )
        goto LABEL_83;
    }
    if ( (*((_BYTE *)a1 + 20) & 0x20) == 0 && (*((_BYTE *)a1 + 192) & 2) != 0 && *((_DWORD *)a1 + 4) == 4 )
    {
      v16 = SampShouldCallNtdsaApiSet();
      v13 = 0;
      updated = v16;
      if ( v16 == -1073741637 )
      {
        updated = 0;
      }
      else if ( v16 >= 0 )
      {
        updated = NtdsaExtEnforceObjectClassAndSamAccountTypeMatch(a1, v9, v17, 0);
        v13 = 0;
      }
      if ( updated < 0 )
        goto LABEL_83;
    }
  }
  if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
  {
    v18 = 0;
    if ( (*(_DWORD *)(a3 + 56) & 0x100100) == 0 )
      v18 = ~(*((_BYTE *)a1 + 20) >> 5) & ((v9 & 0x100100) != 0);
    if ( v18 )
    {
      v19 = SampShouldCallNtdsaApiSet();
      v13 = 0;
      updated = v19;
      if ( v19 == -1073741637 )
      {
        updated = 0;
      }
      else if ( v19 >= 0 )
      {
        updated = NtdsaExtEnforceComputerClassForDomainController(a1, v20, v21, 0);
        v13 = 0;
      }
      if ( updated < 0 )
        goto LABEL_83;
    }
  }
  if ( ((*(_DWORD *)(a3 + 56) ^ v9) & 0x1001C0) != 0 )
  {
    *a7 = 1;
    if ( (v9 & 0x100100) != 0 && *(char *)(a3 + 56) < 0 )
      *((_BYTE *)a1 + 28) |= 0x20u;
    if ( (*(_DWORD *)(a3 + 56) & 0x100100) != 0 && (v9 & 0x80u) != 0 )
      *((_BYTE *)a1 + 28) |= 0x20u;
  }
  if ( (*((_BYTE *)a1 + 20) & 0x20) != 0 )
    goto LABEL_48;
  if ( (*(_DWORD *)(a3 + 56) & 0x400) == 0 )
  {
    v9 &= ~0x400u;
    goto LABEL_48;
  }
  if ( (v9 & 0x400) != 0 )
    goto LABEL_48;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x800) != 0
    && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control[3].Buffer,
      36,
      WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
      *(unsigned int *)(a3 + 48));
  }
  *(_WORD *)(a3 + 64) = 0;
  if ( (*((_BYTE *)a1 + 192) & 2) == 0 )
    goto LABEL_96;
  v22 = 8;
  v23 = (char *)a1 + 272;
  do
  {
    *v23++ = 0;
    --v22;
  }
  while ( v22 );
  updated = SampExtUpdateLockoutTimeExDs(a1, 0);
  if ( updated >= 0 )
  {
LABEL_96:
    if ( SampSuccessAccountAuditingEnabled == 1 && !*a6 )
    {
      v44 = 0;
      UnicodeStringAttribute = SampGetUnicodeStringAttribute(a1);
      v13 = 0;
      if ( UnicodeStringAttribute < 0 )
        goto LABEL_47;
      SampAuditAnyEvent(
        a1,
        0,
        671,
        0,
        *((_QWORD *)SampDefinedDomains + 170 * *((unsigned int *)a1 + 50) + 1),
        0,
        0,
        0,
        &v44,
        (char *)SampDefinedDomains + 1360 * *((unsigned int *)a1 + 50) + 16,
        (char *)a1 + 248,
        0,
        0,
        0);
    }
  }
  v13 = 0;
LABEL_47:
  *a6 = 1;
  if ( updated < 0 )
  {
LABEL_83:
    v36 = WPP_GLOBAL_Control;
    goto LABEL_84;
  }
LABEL_48:
  if ( *a7 && (*((_BYTE *)a1 + 192) & 2) != 0 )
  {
    if ( (v9 & 0x100100) != 0 )
    {
      if ( *(_DWORD *)(a3 + 52) != SampDefaultPrimaryGroup(a1, *(_DWORD *)(a3 + 56)) )
        *(_BYTE *)hMem[0] = 1;
      goto LABEL_55;
    }
    if ( a4 && *(_DWORD *)(a3 + 52) == SampDefaultPrimaryGroup(a1, *(_DWORD *)(a3 + 56)) )
LABEL_55:
      *(_DWORD *)(a3 + 52) = SampDefaultPrimaryGroup(v25, v9);
  }
  if ( (v9 & 0x1000) != 0 && (*(_DWORD *)(a3 + 56) & 0x1000) == 0 )
  {
    v26 = hMem;
    v27 = 16;
    v44 = 0;
    v28 = 16;
    *(_OWORD *)hMem = 0;
    do
    {
      *(_BYTE *)v26 = v13;
      v26 = (HLOCAL *)((char *)v26 + 1);
      --v28;
    }
    while ( v28 );
    updated = SampGenerateRandomPassword(pbBuffer);
    if ( updated >= 0 )
    {
      v29 = pbBuffer;
      *(_OWORD *)hMem = 0;
      v30 = 0x7FFF;
      do
      {
        if ( !*(_WORD *)v29 )
          break;
        v29 += 2;
        --v30;
      }
      while ( v30 );
      updated = v30 == 0 ? 0xC000000D : 0;
      if ( v30 )
      {
        LOWORD(hMem[0]) = -2 - 2 * v30;
        WORD1(hMem[0]) = -2 * v30;
        hMem[1] = pbBuffer;
        updated = SystemFunction007(hMem, &v44);
        if ( updated >= 0 )
        {
          LOBYTE(v41) = 0;
          LOBYTE(v40) = 1;
          updated = SampStoreUserPasswords(a1, 0, 0, &v44, v40, v41, 2, 0, hMem, 0, 0, 0);
        }
      }
    }
    v31 = 514;
    v32 = pbBuffer;
    do
    {
      *v32++ = 0;
      --v31;
    }
    while ( v31 );
    v33 = &v44;
    do
    {
      *(_BYTE *)v33 = 0;
      v33 = (__int128 *)((char *)v33 + 1);
      --v27;
    }
    while ( v27 );
    if ( updated < 0 )
      goto LABEL_83;
    updated = SampComputePasswordExpired(0, a3 + 24);
    if ( updated < 0 )
      goto LABEL_83;
  }
  v34 = SampSuccessAccountAuditingEnabled == 1;
  *(_DWORD *)(a3 + 56) = v9;
  if ( !v34 )
    goto LABEL_83;
  v35 = v42 & 0xFFFDFBFF;
  v42 &= 0xFFFDFBFF;
  v36 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x1000) != 0
    && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 37, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, v35, v9 & 0xFFFDFBFF);
    v35 = v42;
    v36 = WPP_GLOBAL_Control;
  }
  if ( v35 != (v9 & 0xFFFDFBFF) )
  {
    hMem[0] = 0;
    updated = SampCreateAccountSid(a1, hMem);
    if ( updated >= 0 )
    {
      updated = SampExtAuditUpdateAuditNotificationDs(1, hMem[0], &v42);
      LocalFree(hMem[0]);
    }
    v36 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x1000) == 0 )
      goto LABEL_91;
    if ( HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      WPP_SF_DdD(
        WPP_GLOBAL_Control[3].Buffer,
        38,
        WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
        v42,
        v9 & 0xFFFDFBFF,
        updated);
      goto LABEL_83;
    }
  }
LABEL_84:
  if ( (*(_DWORD *)(&v36[4].MaximumLength + 1) & 0x1000) != 0 && HIBYTE(v36[4].Length) >= 4u )
  {
    v44 = 0;
    if ( (int)SampGetUnicodeStringAttribute(a1) < 0 )
    {
LABEL_90:
      v36 = WPP_GLOBAL_Control;
      goto LABEL_91;
    }
    v36 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x1000) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      WPP_SF_ZdDD(WPP_GLOBAL_Control[3].Buffer, v37, v38, (unsigned int)&v44, *(_DWORD *)(a3 + 48), v9, updated);
      goto LABEL_90;
    }
  }
LABEL_91:
  if ( (*(_DWORD *)(&v36[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v36[3].Buffer, 40, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, (unsigned int)updated, updated);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800a56d0  mov     [rsp-8+arg_18], rbx
0x1800a56d5  push    rbp
0x1800a56d6  push    rsi
0x1800a56d7  push    rdi
0x1800a56d8  push    r12
0x1800a56da  push    r13
0x1800a56dc  push    r14
0x1800a56de  push    r15
0x1800a56e0  lea     rbp, [rsp-1C0h]
0x1800a56e8  sub     rsp, 2C0h
0x1800a56ef  mov     rax, cs:__security_cookie
0x1800a56f6  xor     rax, rsp
0x1800a56f9  mov     [rbp+1F0h+var_40], rax
0x1800a5700  mov     rax, [rbp+1F0h+arg_38]
0x1800a5707  mov     r15, r8
0x1800a570a  mov     r12, [rbp+1F0h+arg_30]
0x1800a5711  mov     edi, edx
0x1800a5713  mov     r8, [rbp+1F0h+arg_20]; struct _DOMAIN_PASSWORD_INFORMATION *
0x1800a571a  btr     edi, 11h
0x1800a571e  mov     r14, [rbp+1F0h+arg_28]
0x1800a5725  mov     edx, edi; unsigned int
0x1800a5727  mov     [rsp+2F0h+hMem], rax
0x1800a572c  mov     r13b, r9b
0x1800a572f  mov     eax, [r15+38h]
0x1800a5733  mov     rsi, rcx
0x1800a5736  mov     [rsp+2F0h+var_280], eax
0x1800a573a  mov     byte ptr [r12], 0
0x1800a573f  call    ?SampIsUserAccountControlValid@@YAJPEAU_SAMP_OBJECT@@KPEAU_DOMAIN_PASSWORD_INFORMATION@@@Z; SampIsUserAccountControlValid(_SAMP_OBJECT *,ulong,_DOMAIN_PASSWORD_INFORMATION *)
0x1800a5744  xor     r9d, r9d
0x1800a5747  mov     ebx, eax
0x1800a5749  test    eax, eax
0x1800a574b  js      loc_1800A5C64
0x1800a5751  test    byte ptr [rsi+14h], 20h
0x1800a5755  lea     eax, [r9+2]
0x1800a5759  jnz     loc_1800A57E7
0x1800a575f  test    [rsi+0C0h], al
0x1800a5765  jz      short loc_1800A57A1
0x1800a5767  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x1800a576c  xor     r9d, r9d
0x1800a576f  mov     ebx, eax
0x1800a5771  cmp     eax, 0C00000BBh
0x1800a5776  jnz     short loc_1800A577D
0x1800a5778  mov     ebx, r9d
0x1800a577b  jmp     short loc_1800A5794
0x1800a577d  test    eax, eax
0x1800a577f  js      short loc_1800A5794
0x1800a5781  mov     r8, r15
0x1800a5784  mov     edx, edi
0x1800a5786  mov     rcx, rsi
0x1800a5789  call    cs:__imp_NtdsaExtValidatePrivilegedAccountControlFlags
0x1800a578f  mov     ebx, eax
0x1800a5791  xor     r9d, r9d
0x1800a5794  test    ebx, ebx
0x1800a5796  js      loc_1800A5C64
0x1800a579c  mov     eax, 2
0x1800a57a1  test    byte ptr [rsi+14h], 20h
0x1800a57a5  jnz     short loc_1800A57E7
0x1800a57a7  test    [rsi+0C0h], al
0x1800a57ad  jz      short loc_1800A57E7
0x1800a57af  cmp     dword ptr [rsi+10h], 4
0x1800a57b3  jnz     short loc_1800A57E7
0x1800a57b5  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x1800a57ba  xor     r9d, r9d
0x1800a57bd  mov     ebx, eax
0x1800a57bf  cmp     eax, 0C00000BBh
0x1800a57c4  jnz     short loc_1800A57CB
0x1800a57c6  mov     ebx, r9d
0x1800a57c9  jmp     short loc_1800A57DF
0x1800a57cb  test    eax, eax
0x1800a57cd  js      short loc_1800A57DF
0x1800a57cf  mov     edx, edi
0x1800a57d1  mov     rcx, rsi
0x1800a57d4  call    cs:__imp_NtdsaExtEnforceObjectClassAndSamAccountTypeMatch
0x1800a57da  mov     ebx, eax
0x1800a57dc  xor     r9d, r9d
0x1800a57df  test    ebx, ebx
0x1800a57e1  js      loc_1800A5C64
0x1800a57e7  test    byte ptr [rsi+0C0h], 2
0x1800a57ee  mov     edx, 100100h
0x1800a57f3  jz      short loc_1800A5853
0x1800a57f5  mov     al, [rsi+14h]
0x1800a57f8  mov     ecx, r9d
0x1800a57fb  mov     r8d, [r15+38h]
0x1800a57ff  and     r8d, edx
0x1800a5802  test    edx, edi
0x1800a5804  setnz   dl
0x1800a5807  shr     al, 5
0x1800a580a  not     al
0x1800a580c  and     dl, al
0x1800a580e  and     dl, 1
0x1800a5811  test    r8d, r8d
0x1800a5814  movzx   eax, dl
0x1800a5817  cmovz   ecx, eax
0x1800a581a  test    cl, cl
0x1800a581c  jz      short loc_1800A584E
0x1800a581e  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x1800a5823  xor     r9d, r9d
0x1800a5826  mov     ebx, eax
0x1800a5828  cmp     eax, 0C00000BBh
0x1800a582d  jnz     short loc_1800A5834
0x1800a582f  mov     ebx, r9d
0x1800a5832  jmp     short loc_1800A5846
0x1800a5834  test    eax, eax
0x1800a5836  js      short loc_1800A5846
0x1800a5838  mov     rcx, rsi
0x1800a583b  call    cs:__imp_NtdsaExtEnforceComputerClassForDomainController
0x1800a5841  mov     ebx, eax
0x1800a5843  xor     r9d, r9d
0x1800a5846  test    ebx, ebx
0x1800a5848  js      loc_1800A5C64
0x1800a584e  mov     edx, 100100h
0x1800a5853  mov     eax, edi
0x1800a5855  xor     eax, [r15+38h]
0x1800a5859  test    eax, 1001C0h
0x1800a585e  jz      short loc_1800A5890
0x1800a5860  test    edx, edi
0x1800a5862  mov     byte ptr [r12], 1
0x1800a5867  setnz   cl
0x1800a586a  test    byte ptr [r15+38h], 80h
0x1800a586f  setnz   al
0x1800a5872  test    al, cl
0x1800a5874  jz      short loc_1800A587A
0x1800a5876  or      byte ptr [rsi+1Ch], 20h
0x1800a587a  test    [r15+38h], edx
0x1800a587e  setnz   cl
0x1800a5881  test    dil, 80h
0x1800a5885  setnz   al
0x1800a5888  test    al, cl
0x1800a588a  jz      short loc_1800A5890
0x1800a588c  or      byte ptr [rsi+1Ch], 20h
0x1800a5890  test    byte ptr [rsi+14h], 20h
0x1800a5894  jnz     loc_1800A59D1
0x1800a589a  mov     eax, 400h
0x1800a589f  test    [r15+38h], eax
0x1800a58a3  jnz     short loc_1800A58AE
0x1800a58a5  btr     edi, 0Ah
0x1800a58a9  jmp     loc_1800A59D1
0x1800a58ae  test    eax, edi
0x1800a58b0  jnz     loc_1800A59D1
0x1800a58b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a58bd  test    dword ptr [rcx+44h], 800h
0x1800a58c4  jz      short loc_1800A58E5
0x1800a58c6  cmp     byte ptr [rcx+41h], 4
0x1800a58ca  jb      short loc_1800A58E5
0x1800a58cc  mov     r9d, [r15+30h]
0x1800a58d0  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x1800a58d7  mov     rcx, [rcx+38h]
0x1800a58db  mov     edx, 24h ; '$'
0x1800a58e0  call    WPP_SF_d
0x1800a58e5  xor     edx, edx; unsigned __int8
0x1800a58e7  mov     [r15+40h], dx
0x1800a58ec  test    byte ptr [rsi+0C0h], 2
0x1800a58f3  jz      short loc_1800A591E
0x1800a58f5  lea     ecx, [rdx+8]
0x1800a58f8  lea     rax, [rsi+110h]
0x1800a58ff  mov     [rax], dl
0x1800a5901  inc     rax
0x1800a5904  sub     rcx, 1
0x1800a5908  jnz     short loc_1800A58FF
0x1800a590a  mov     rcx, rsi; struct _SAMP_OBJECT *
0x1800a590d  call    ?SampExtUpdateLockoutTimeExDs@@YAJPEAU_SAMP_OBJECT@@E@Z; SampExtUpdateLockoutTimeExDs(_SAMP_OBJECT *,uchar)
0x1800a5912  xor     edx, edx
0x1800a5914  mov     ebx, eax
0x1800a5916  test    eax, eax
0x1800a5918  js      loc_1800A59C2
0x1800a591e  cmp     cs:?SampSuccessAccountAuditingEnabled@@3EA, 1; uchar SampSuccessAccountAuditingEnabled
0x1800a5925  jnz     loc_1800A59C2
0x1800a592b  cmp     [r14], dl
0x1800a592e  jnz     loc_1800A59C2
0x1800a5934  xor     r8d, r8d
0x1800a5937  lea     r9, [rbp+1F0h+var_268]
0x1800a593b  xorps   xmm0, xmm0
0x1800a593e  mov     rcx, rsi; struct _SAMP_OBJECT *
0x1800a5941  movups  [rbp+1F0h+var_268], xmm0
0x1800a5945  lea     edx, [r8+1]
0x1800a5949  call    SampGetUnicodeStringAttribute
0x1800a594e  xor     r9d, r9d
0x1800a5951  test    eax, eax
0x1800a5953  js      short loc_1800A59C5
0x1800a5955  mov     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800a595c  mov     eax, [rsi+0C8h]
0x1800a5962  mov     [rsp+2F0h+var_288], r9
0x1800a5967  mov     [rsp+2F0h+var_290], r9
0x1800a596c  mov     [rsp+2F0h+var_298], r9
0x1800a5971  lea     rcx, [rdx+10h]
0x1800a5975  imul    r8, rax, 550h
0x1800a597c  lea     rax, [rsi+0F8h]
0x1800a5983  mov     [rsp+2F0h+var_2A0], rax
0x1800a5988  add     rcx, r8
0x1800a598b  mov     [rsp+2F0h+var_2A8], rcx
0x1800a5990  lea     rax, [rbp+1F0h+var_268]
0x1800a5994  mov     [rsp+2F0h+var_2B0], rax
0x1800a5999  mov     rcx, rsi
0x1800a599c  mov     rax, [r8+rdx+8]
0x1800a59a1  xor     edx, edx
0x1800a59a3  mov     [rsp+2F0h+var_2B8], r9
0x1800a59a8  mov     r8d, 29Fh
0x1800a59ae  mov     [rsp+2F0h+var_2C0], r9
0x1800a59b3  mov     [rsp+2F0h+var_2C8], r9
0x1800a59b8  mov     [rsp+2F0h+var_2D0], rax
0x1800a59bd  call    SampAuditAnyEvent
0x1800a59c2  xor     r9d, r9d
0x1800a59c5  mov     byte ptr [r14], 1
0x1800a59c9  test    ebx, ebx
0x1800a59cb  js      loc_1800A5C64
0x1800a59d1  cmp     [r12], r9b
0x1800a59d5  mov     r12d, 2
0x1800a59db  jz      short loc_1800A5A2C
0x1800a59dd  test    [rsi+0C0h], r12b
0x1800a59e4  jz      short loc_1800A5A2C
0x1800a59e6  test    edi, 100100h
0x1800a59ec  jz      short loc_1800A5A0A
0x1800a59ee  mov     edx, [r15+38h]; unsigned int
0x1800a59f2  mov     rcx, rsi; struct _SAMP_OBJECT *
0x1800a59f5  call    ?SampDefaultPrimaryGroup@@YAKPEAU_SAMP_OBJECT@@K@Z; SampDefaultPrimaryGroup(_SAMP_OBJECT *,ulong)
0x1800a59fa  cmp     [r15+34h], eax
0x1800a59fe  jz      short loc_1800A5A21
0x1800a5a00  mov     rax, [rsp+2F0h+hMem]
0x1800a5a05  mov     byte ptr [rax], 1
0x1800a5a08  jmp     short loc_1800A5A21
0x1800a5a0a  test    r13b, r13b
0x1800a5a0d  jz      short loc_1800A5A2C
0x1800a5a0f  mov     edx, [r15+38h]; unsigned int
0x1800a5a13  mov     rcx, rsi; struct _SAMP_OBJECT *
0x1800a5a16  call    ?SampDefaultPrimaryGroup@@YAKPEAU_SAMP_OBJECT@@K@Z; SampDefaultPrimaryGroup(_SAMP_OBJECT *,ulong)
0x1800a5a1b  cmp     [r15+34h], eax
0x1800a5a1f  jnz     short loc_1800A5A2C
0x1800a5a21  mov     edx, edi; unsigned int
0x1800a5a23  call    ?SampDefaultPrimaryGroup@@YAKPEAU_SAMP_OBJECT@@K@Z; SampDefaultPrimaryGroup(_SAMP_OBJECT *,ulong)
0x1800a5a28  mov     [r15+34h], eax
0x1800a5a2c  bt      edi, 0Ch
0x1800a5a30  jnb     loc_1800A5B79
0x1800a5a36  test    dword ptr [r15+38h], 1000h
0x1800a5a3e  jnz     loc_1800A5B79
0x1800a5a44  xorps   xmm0, xmm0
0x1800a5a47  lea     rax, [rsp+2F0h+hMem]
0x1800a5a4c  mov     r14d, 10h
0x1800a5a52  movdqu  [rbp+1F0h+var_268], xmm0
0x1800a5a57  mov     ecx, r14d
0x1800a5a5a  movups  xmmword ptr [rsp+2F0h+hMem], xmm0
0x1800a5a5f  mov     [rax], r9b
0x1800a5a62  inc     rax
0x1800a5a65  sub     rcx, 1
0x1800a5a69  jnz     short loc_1800A5A5F
0x1800a5a6b  mov     edx, 101h
0x1800a5a70  lea     rcx, [rbp+1F0h+pbBuffer]; pbBuffer
0x1800a5a74  call    SampGenerateRandomPassword
0x1800a5a79  xor     r9d, r9d
0x1800a5a7c  mov     ebx, eax
0x1800a5a7e  test    eax, eax
0x1800a5a80  js      loc_1800A5B37
0x1800a5a86  xorps   xmm0, xmm0
0x1800a5a89  lea     rax, [rbp+1F0h+pbBuffer]
0x1800a5a8d  movups  xmmword ptr [rsp+2F0h+hMem], xmm0
0x1800a5a92  mov     ecx, 7FFFh
0x1800a5a97  cmp     [rax], r9w
0x1800a5a9b  jz      short loc_1800A5AA6
0x1800a5a9d  add     rax, r12
0x1800a5aa0  sub     rcx, 1
0x1800a5aa4  jnz     short loc_1800A5A97
0x1800a5aa6  mov     rax, rcx
0x1800a5aa9  neg     rax
0x1800a5aac  sbb     ebx, ebx
0x1800a5aae  not     ebx
0x1800a5ab0  and     ebx, 0C000000Dh
0x1800a5ab6  test    rcx, rcx
0x1800a5ab9  jz      short loc_1800A5B37
0x1800a5abb  add     cx, cx
0x1800a5abe  lea     rdx, [rbp+1F0h+var_268]
0x1800a5ac2  mov     eax, 0FFFEh
0x1800a5ac7  sub     ax, cx
0x1800a5aca  lea     rcx, [rsp+2F0h+hMem]
0x1800a5acf  mov     word ptr [rsp+2F0h+hMem], ax
0x1800a5ad4  add     ax, r12w
0x1800a5ad8  mov     word ptr [rsp+2F0h+hMem+2], ax
0x1800a5add  lea     rax, [rbp+1F0h+pbBuffer]
0x1800a5ae1  mov     [rbp+1F0h+hMem+8], rax
0x1800a5ae5  call    cs:__imp_SystemFunction007
0x1800a5aeb  xor     r9d, r9d
0x1800a5aee  mov     ebx, eax
0x1800a5af0  test    eax, eax
0x1800a5af2  js      short loc_1800A5B37
0x1800a5af4  mov     [rsp+2F0h+var_298], r9
0x1800a5af9  lea     rax, [rsp+2F0h+hMem]
0x1800a5afe  mov     [rsp+2F0h+var_2A0], r9
0x1800a5b03  xor     r8d, r8d
0x1800a5b06  mov     [rsp+2F0h+var_2A8], r9
0x1800a5b0b  xor     edx, edx
0x1800a5b0d  mov     [rsp+2F0h+var_2B0], rax
0x1800a5b12  mov     rcx, rsi
0x1800a5b15  mov     [rsp+2F0h+var_2B8], r9
0x1800a5b1a  mov     dword ptr [rsp+2F0h+var_2C0], r12d
0x1800a5b1f  mov     byte ptr [rsp+2F0h+var_2C8], r9b
0x1800a5b24  lea     r9, [rbp+1F0h+var_268]
0x1800a5b28  mov     byte ptr [rsp+2F0h+var_2D0], 1
0x1800a5b2d  call    ?SampStoreUserPasswords@@YAJPEAU_SAMP_OBJECT@@PEAU_LM_OWF_PASSWORD@@E1EEW4_SAMP_STORE_PASSWORD_CALLER_TYPE@@PEAU_DOMAIN_PASSWORD_INFORMATION@@PEAU_UNICODE_STRING@@PEAK4PEAU_USER_PWD_CHANGE_FAILURE_INFORMATION@@@Z; SampStoreUserPasswords(_SAMP_OBJECT *,_LM_OWF_PASSWORD *,uchar,_LM_OWF_PASSWORD *,uchar,uchar,_SAMP_STORE_PASSWORD_CALLER_TYPE,_DOMAIN_PASSWORD_INFORMATION *,_UNICODE_STRING *,ulong *,_UNICODE_STRING *,_USER_PWD_CHANGE_FAILURE_INFORMATION *)
0x1800a5b32  mov     ebx, eax
0x1800a5b34  xor     r9d, r9d
0x1800a5b37  mov     ecx, 202h
0x1800a5b3c  lea     rax, [rbp+1F0h+pbBuffer]
  ... truncated ...
```
