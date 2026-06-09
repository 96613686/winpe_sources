# SspiDecryptAuthIdentityEx

- ea: `0x1800090e0`
- end: `0x180009359`
- name: `SspiDecryptAuthIdentityEx`
- size: `633`
- prototype: `SECURITY_STATUS __stdcall(ULONG Options, PSEC_WINNT_AUTH_IDENTITY_OPAQUE EncryptedAuthData)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016dc0`

## callees

- `0x180005cc0`
- `0x1800078a0`
- `0x1800090e0`
- `0x18000a170`
- `0x18000a2b8`

## import_xrefs

- `CRYPTBASE!SystemFunction041` at `0x1800091d3`
- `CRYPTBASE!SystemFunction041` at `0x1800092e4`
- `CRYPTBASE!SystemFunction041` at `0x180009305`
- `CRYPTBASE!SystemFunction041` at `0x180009327`
- `CRYPTBASE!SystemFunction041` at `0x1800091d3`
- `CRYPTBASE!SystemFunction041` at `0x1800092e4`
- `CRYPTBASE!SystemFunction041` at `0x180009305`
- `CRYPTBASE!SystemFunction041` at `0x180009327`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiDecryptAuthIdentityEx(ULONG Options, PSEC_WINNT_AUTH_IDENTITY_OPAQUE EncryptedAuthData)
{
  ULONG v2; // r12d
  SECURITY_STATUS ThreadLogonContext; // eax
  __int64 v6; // rcx
  ULONG v7; // edx
  char *v8; // rcx
  char *v9; // r8
  __int64 v10; // rax
  unsigned int v11; // ecx
  bool v12; // zf
  char *v13; // r14
  unsigned int v14; // r15d
  int v15; // edi
  int v16; // ecx
  unsigned int v17; // ecx
  int v18; // edi
  int v19; // r15d
  int v20; // edx
  int v21; // edx
  ULONG OptionFlags; // [rsp+70h] [rbp+40h] BYREF
  int v24; // [rsp+78h] [rbp+48h] BYREF
  unsigned int v25; // [rsp+80h] [rbp+50h] BYREF

  v2 = 0;
  v24 = 0;
  OptionFlags = 0;
  v25 = 0;
  if ( ((Options - 1) & 0xFFFFFFFC) != 0 || Options == 3 )
    goto LABEL_46;
  ThreadLogonContext = SspiValidateAuthIdentity(EncryptedAuthData);
  if ( ThreadLogonContext < 0 )
    return SspNtStatusToSecStatus((unsigned int)ThreadLogonContext);
  if ( *(_DWORD *)EncryptedAuthData != 513 )
  {
    v12 = *(_DWORD *)EncryptedAuthData == 512;
    v13 = (char *)EncryptedAuthData + 8;
    OptionFlags = 0;
    if ( !v12 )
      v13 = (char *)EncryptedAuthData;
    v14 = *((_DWORD *)v13 + 11);
    if ( (v14 & 0x10000) == 0 )
      goto LABEL_46;
    v15 = 128;
    if ( (v14 & 0x80u) == 0 )
    {
      if ( Options == 1 )
      {
        if ( (v14 & 0x10) != 0 )
        {
          ThreadLogonContext = -1073741637;
          return SspNtStatusToSecStatus((unsigned int)ThreadLogonContext);
        }
        ThreadLogonContext = SecpGetThreadLogonContext((int *)&OptionFlags);
        if ( ThreadLogonContext < 0 )
          return SspNtStatusToSecStatus((unsigned int)ThreadLogonContext);
        if ( OptionFlags )
        {
          v15 = 32;
          v17 = v14 >> 5;
        }
        else
        {
          v15 = 64;
          v17 = v14 >> 6;
        }
        v2 = 2;
      }
      else
      {
        if ( Options != 2 )
          goto LABEL_46;
        v15 = 16;
        v17 = v14 >> 4;
      }
      v16 = v17 & 1;
    }
    else
    {
      ThreadLogonContext = SecpGetThreadLogonContext((int *)&OptionFlags);
      if ( ThreadLogonContext < 0 )
        return SspNtStatusToSecStatus((unsigned int)ThreadLogonContext);
      if ( !OptionFlags )
      {
        ThreadLogonContext = -1073741790;
        return SspNtStatusToSecStatus((unsigned int)ThreadLogonContext);
      }
      v16 = 1;
      v2 = 4;
    }
    v18 = v14 & ~v15;
    if ( !v16
      || ((v19 = ((*((_DWORD *)v13 + 11) & 1) == 0) + 1, !*((_DWORD *)v13 + 10))
       || (ThreadLogonContext = SystemFunction041(
                                  *((PVOID *)v13 + 4),
                                  (*((_DWORD *)v13 + 10) * v19 + 7) & 0xFFFFFFF8,
                                  v2),
           ThreadLogonContext >= 0))
      && ((v20 = *((_DWORD *)v13 + 2)) == 0
       || (ThreadLogonContext = SystemFunction041(*(PVOID *)v13, (v19 * v20 + 7) & 0xFFFFFFF8, v2),
           ThreadLogonContext >= 0))
      && ((v21 = *((_DWORD *)v13 + 6)) == 0
       || (ThreadLogonContext = SystemFunction041(*((PVOID *)v13 + 2), (v19 * v21 + 7) & 0xFFFFFFF8, v2),
           ThreadLogonContext >= 0)) )
    {
      *((_DWORD *)v13 + 11) = v18;
      goto LABEL_45;
    }
    return SspNtStatusToSecStatus((unsigned int)ThreadLogonContext);
  }
  ThreadLogonContext = SecpCombineAuthIdentityDecryptionFlags(
                         Options,
                         *((_DWORD *)EncryptedAuthData + 9),
                         &v25,
                         &OptionFlags,
                         &v24);
  if ( ThreadLogonContext < 0 )
    return SspNtStatusToSecStatus((unsigned int)ThreadLogonContext);
  if ( !v24 )
    goto LABEL_16;
  if ( Options == 2 )
  {
    v6 = *((unsigned __int16 *)EncryptedAuthData + 2);
    v7 = (*((_DWORD *)EncryptedAuthData + 2) - v6 + 7) & 0xFFFFFFF8;
    v8 = (char *)EncryptedAuthData + v6;
    goto LABEL_15;
  }
  if ( !*((_DWORD *)EncryptedAuthData + 7) )
  {
LABEL_16:
    *((_DWORD *)EncryptedAuthData + 9) = v25;
LABEL_45:
    ThreadLogonContext = SspiValidateAuthIdentity(EncryptedAuthData);
    return SspNtStatusToSecStatus((unsigned int)ThreadLogonContext);
  }
  v9 = (char *)EncryptedAuthData + *((unsigned int *)EncryptedAuthData + 7);
  v10 = *((unsigned int *)v9 + 5);
  v7 = (*((unsigned __int16 *)v9 + 12) + 7) & 0xFFFFFFF8;
  if ( v7 + (unsigned int)v10 < (unsigned int)v10
    || (v11 = *((unsigned __int16 *)v9 + 1), v7 + (unsigned int)v10 > v11)
    || (unsigned __int16)v11 > *((_WORD *)EncryptedAuthData + 16) )
  {
LABEL_46:
    ThreadLogonContext = -1073741811;
    return SspNtStatusToSecStatus((unsigned int)ThreadLogonContext);
  }
  if ( !(_DWORD)v10 )
    goto LABEL_16;
  v8 = &v9[v10];
LABEL_15:
  ThreadLogonContext = SystemFunction041(v8, v7, OptionFlags);
  if ( ThreadLogonContext >= 0 )
    goto LABEL_16;
  return SspNtStatusToSecStatus((unsigned int)ThreadLogonContext);
}

```

## disassembly

```asm
0x1800090e0  push    rbp
0x1800090e2  push    rbx
0x1800090e3  push    rsi
0x1800090e4  push    rdi
0x1800090e5  push    r12
0x1800090e7  push    r14
0x1800090e9  push    r15
0x1800090eb  mov     rbp, rsp
0x1800090ee  sub     rsp, 30h
0x1800090f2  xor     r12d, r12d
0x1800090f5  mov     [rbp+arg_8], 0
0x1800090fc  lea     eax, [rcx-1]
0x1800090ff  mov     [rbp+OptionFlags], r12d
0x180009103  mov     [rbp+arg_10], r12d
0x180009107  mov     rbx, rdx
0x18000910a  mov     esi, ecx
0x18000910c  test    eax, 0FFFFFFFCh
0x180009111  jnz     loc_18000933F
0x180009117  cmp     ecx, 3
0x18000911a  jz      loc_18000933F
0x180009120  mov     rcx, rdx; AuthData
0x180009123  call    SspiValidateAuthIdentity
0x180009128  test    eax, eax
0x18000912a  js      loc_180009344
0x180009130  cmp     dword ptr [rbx], 201h
0x180009136  jnz     loc_1800091EC
0x18000913c  mov     edx, [rbx+24h]; unsigned int
0x18000913f  lea     rax, [rbp+arg_8]
0x180009143  lea     r9, [rbp+OptionFlags]; unsigned int *
0x180009147  mov     [rsp+30h+var_10], rax; int *
0x18000914c  lea     r8, [rbp+arg_10]; unsigned int *
0x180009150  mov     ecx, esi; unsigned int
0x180009152  call    ?SecpCombineAuthIdentityDecryptionFlags@@YAJKKPEAK0PEAH@Z; SecpCombineAuthIdentityDecryptionFlags(ulong,ulong,ulong *,ulong *,int *)
0x180009157  test    eax, eax
0x180009159  js      loc_180009344
0x18000915f  cmp     [rbp+arg_8], r12d
0x180009163  jz      short loc_1800091E1
0x180009165  cmp     esi, 2
0x180009168  jnz     short loc_180009182
0x18000916a  movzx   ecx, word ptr [rbx+4]
0x18000916e  mov     esi, 0FFFFFFF8h
0x180009173  mov     edx, [rbx+8]
0x180009176  sub     edx, ecx
0x180009178  add     edx, 7
0x18000917b  and     edx, esi
0x18000917d  add     rcx, rbx
0x180009180  jmp     short loc_1800091CF
0x180009182  cmp     [rbx+1Ch], r12d
0x180009186  jz      short loc_1800091E1
0x180009188  mov     r8d, [rbx+1Ch]
0x18000918c  mov     esi, 0FFFFFFF8h
0x180009191  add     r8, rbx
0x180009194  mov     eax, [r8+14h]
0x180009198  movzx   edx, word ptr [r8+18h]
0x18000919d  add     edx, 7
0x1800091a0  and     edx, esi; MemorySize
0x1800091a2  lea     r9d, [rdx+rax]
0x1800091a6  cmp     r9d, eax
0x1800091a9  jb      loc_18000933F
0x1800091af  movzx   ecx, word ptr [r8+2]
0x1800091b4  cmp     r9d, ecx
0x1800091b7  ja      loc_18000933F
0x1800091bd  cmp     cx, [rbx+20h]
0x1800091c1  ja      loc_18000933F
0x1800091c7  test    eax, eax
0x1800091c9  jz      short loc_1800091E1
0x1800091cb  lea     rcx, [r8+rax]; Memory
0x1800091cf  mov     r8d, [rbp+OptionFlags]; OptionFlags
0x1800091d3  call    cs:__imp_SystemFunction041
0x1800091d9  test    eax, eax
0x1800091db  js      loc_180009344
0x1800091e1  mov     eax, [rbp+arg_10]
0x1800091e4  mov     [rbx+24h], eax
0x1800091e7  jmp     loc_180009335
0x1800091ec  cmp     dword ptr [rbx], 200h
0x1800091f2  lea     r14, [rbx+8]
0x1800091f6  mov     [rbp+OptionFlags], r12d
0x1800091fa  cmovnz  r14, rbx
0x1800091fe  mov     r15d, [r14+2Ch]
0x180009202  bt      r15d, 10h
0x180009207  jnb     loc_18000933F
0x18000920d  mov     edi, 80h
0x180009212  test    dil, r15b
0x180009215  jz      short loc_180009243
0x180009217  lea     rcx, [rbp+OptionFlags]; int *
0x18000921b  call    ?SecpGetThreadLogonContext@@YAJPEAH@Z; SecpGetThreadLogonContext(int *)
0x180009220  test    eax, eax
0x180009222  js      loc_180009344
0x180009228  cmp     [rbp+OptionFlags], r12d
0x18000922c  jnz     short loc_180009238
0x18000922e  mov     eax, 0C0000022h
0x180009233  jmp     loc_180009344
0x180009238  mov     ecx, 1
0x18000923d  lea     r12d, [rcx+3]
0x180009241  jmp     short loc_1800092A5
0x180009243  cmp     esi, 1
0x180009246  jnz     short loc_18000928E
0x180009248  lea     edi, [rsi+0Fh]
0x18000924b  test    dil, r15b
0x18000924e  jz      short loc_18000925A
0x180009250  mov     eax, 0C00000BBh
0x180009255  jmp     loc_180009344
0x18000925a  lea     rcx, [rbp+OptionFlags]; int *
0x18000925e  call    ?SecpGetThreadLogonContext@@YAJPEAH@Z; SecpGetThreadLogonContext(int *)
0x180009263  test    eax, eax
0x180009265  js      loc_180009344
0x18000926b  mov     ecx, r15d
0x18000926e  cmp     [rbp+OptionFlags], r12d
0x180009272  jz      short loc_18000927E
0x180009274  mov     edi, 20h ; ' '
0x180009279  shr     ecx, 5
0x18000927c  jmp     short loc_180009286
0x18000927e  mov     edi, 40h ; '@'
0x180009283  shr     ecx, 6
0x180009286  mov     r12d, 2
0x18000928c  jmp     short loc_1800092A2
0x18000928e  cmp     esi, 2
0x180009291  jnz     loc_18000933F
0x180009297  xor     eax, eax
0x180009299  lea     edi, [rsi+0Eh]
0x18000929c  mov     ecx, r15d
0x18000929f  shr     ecx, 4
0x1800092a2  and     ecx, 1
0x1800092a5  not     edi
0x1800092a7  and     edi, r15d
0x1800092aa  test    eax, eax
0x1800092ac  js      loc_180009344
0x1800092b2  test    ecx, ecx
0x1800092b4  jz      short loc_180009331
0x1800092b6  mov     r15d, [r14+2Ch]
0x1800092ba  mov     esi, 0FFFFFFF8h
0x1800092bf  not     r15d
0x1800092c2  and     r15d, 1
0x1800092c6  inc     r15d
0x1800092c9  cmp     dword ptr [r14+28h], 0
0x1800092ce  jz      short loc_1800092EE
0x1800092d0  mov     rcx, [r14+20h]; Memory
0x1800092d4  mov     edx, r15d
0x1800092d7  imul    edx, [r14+28h]
0x1800092dc  mov     r8d, r12d; OptionFlags
0x1800092df  add     edx, 7
0x1800092e2  and     edx, esi; MemorySize
0x1800092e4  call    cs:__imp_SystemFunction041
0x1800092ea  test    eax, eax
0x1800092ec  js      short loc_180009344
0x1800092ee  mov     edx, [r14+8]
0x1800092f2  test    edx, edx
0x1800092f4  jz      short loc_18000930F
0x1800092f6  mov     rcx, [r14]; Memory
0x1800092f9  mov     r8d, r12d; OptionFlags
0x1800092fc  imul    edx, r15d
0x180009300  add     edx, 7
0x180009303  and     edx, esi; MemorySize
0x180009305  call    cs:__imp_SystemFunction041
0x18000930b  test    eax, eax
0x18000930d  js      short loc_180009344
0x18000930f  mov     edx, [r14+18h]
0x180009313  test    edx, edx
0x180009315  jz      short loc_180009331
0x180009317  mov     rcx, [r14+10h]; Memory
0x18000931b  mov     r8d, r12d; OptionFlags
0x18000931e  imul    edx, r15d
0x180009322  add     edx, 7
0x180009325  and     edx, esi; MemorySize
0x180009327  call    cs:__imp_SystemFunction041
0x18000932d  test    eax, eax
0x18000932f  js      short loc_180009344
0x180009331  mov     [r14+2Ch], edi
0x180009335  mov     rcx, rbx; AuthData
0x180009338  call    SspiValidateAuthIdentity
0x18000933d  jmp     short loc_180009344
0x18000933f  mov     eax, 0C000000Dh
0x180009344  mov     ecx, eax
0x180009346  add     rsp, 30h
0x18000934a  pop     r15
0x18000934c  pop     r14
0x18000934e  pop     r12
0x180009350  pop     rdi
0x180009351  pop     rsi
0x180009352  pop     rbx
0x180009353  pop     rbp
0x180009354  jmp     SspNtStatusToSecStatus
```
