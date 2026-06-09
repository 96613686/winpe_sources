# CSsl3TlsServerContext::RsaGenerateServerExchangeValue(uchar *,ulong *)

- ea: `0x18004ab48`
- end: `0x18004ae70`
- name: `?RsaGenerateServerExchangeValue@CSsl3TlsServerContext@@AEAAKPEAEPEAK@Z`
- size: `808`
- prototype: `unsigned int __fastcall(CSsl3TlsServerContext *__hidden this, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004ab04`

## callees

- `0x180014240`
- `0x1800214f0`
- `0x180039560`
- `0x18003f740`
- `0x180040280`
- `0x180049910`
- `0x18004ab48`
- `0x1800597b0`
- `0x180088a54`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004ae2d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004ae2d`
- `ncrypt!SslSignHash` at `0x18004adf8`
- `ncrypt!SslSignHash` at `0x18004adf8`
- `ncrypt!SslCreateEphemeralKey` at `0x18004ac73`
- `ncrypt!SslCreateEphemeralKey` at `0x18004ac73`

## pseudocode

```c
unsigned int __fastcall CSsl3TlsServerContext::RsaGenerateServerExchangeValue(
        CSsl3TlsServerContext *this,
        unsigned __int8 *a2,
        unsigned int *a3)
{
  __int64 v4; // r8
  unsigned int result; // eax
  __int64 v8; // rcx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  unsigned int v13; // ebx
  int v14; // r13d
  __int64 *v15; // rax
  __int64 v16; // r9
  __int64 v17; // rcx
  unsigned int EphemeralKey; // eax
  __int64 v19; // r9
  unsigned int v20; // ebx
  unsigned __int64 *v21; // rax
  unsigned __int64 v22; // rcx
  unsigned int EphemBlobFromKey; // eax
  __int64 v24; // r9
  unsigned int *v25; // r14
  unsigned __int8 *v26; // rbx
  __int64 v27; // rcx
  unsigned int v28; // eax
  unsigned __int8 *v29; // rbx
  __int64 v30; // rcx
  unsigned __int8 *v31; // rsi
  void *v32; // rcx
  unsigned int v33; // eax
  __int64 v34; // r9
  __int64 v35; // rdx
  int v36; // r13d
  _QWORD *v37; // rcx
  int v38; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v39; // [rsp+54h] [rbp-35h] BYREF
  int v40; // [rsp+58h] [rbp-31h] BYREF
  unsigned __int8 *v41; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v42; // [rsp+68h] [rbp-21h] BYREF
  __int64 v43; // [rsp+70h] [rbp-19h]
  unsigned __int8 v44[40]; // [rsp+78h] [rbp-11h] BYREF

  v4 = *((_QWORD *)this + 3);
  v40 = 0;
  v42 = 0;
  v41 = 0;
  v38 = 0;
  v39 = 0;
  if ( !v4 )
    return -2146893043;
  if ( (*((_BYTE *)this + 32) & 1) == 0 )
    goto LABEL_44;
  v8 = *((_QWORD *)this + 1);
  if ( !v8 )
    goto LABEL_44;
  v9 = *(_DWORD *)(v8 + 28) - 3;
  if ( !v9 )
  {
LABEL_10:
    v13 = 64;
    goto LABEL_11;
  }
  v10 = v9 - 95;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        if ( v12 == 131100 )
          goto LABEL_10;
LABEL_44:
        *a3 = 0;
        return 0;
      }
    }
  }
  v13 = 128;
LABEL_11:
  v14 = *a3;
  result = GetRsaKeyModulus(*(_QWORD *)(v4 + 8), &v39);
  if ( result )
    return result;
  if ( v39 <= v13 )
    goto LABEL_44;
  if ( a2 )
  {
    v15 = (__int64 *)*((_QWORD *)this + 1);
    if ( (*((_BYTE *)this + 32) & 1) != 0 && v15 )
      v16 = *((unsigned int *)v15 + 7);
    else
      v16 = 0;
    if ( v15 )
      v17 = *v15;
    else
      v17 = 0;
    EphemeralKey = SslCreateEphemeralKey(
                     v17,
                     (char *)this + 136,
                     *((unsigned __int16 *)this + 17),
                     v16,
                     0,
                     8 * v13,
                     0,
                     0,
                     0);
    v20 = EphemeralKey;
    if ( EphemeralKey )
    {
      LOBYTE(v19) = 51;
      CSslContext::SetErrorAndFatalAlert(this, 818, EphemeralKey, v19);
      return v20;
    }
    v21 = (unsigned __int64 *)*((_QWORD *)this + 1);
    if ( v21 )
      v22 = *v21;
    else
      v22 = 0;
    EphemBlobFromKey = GetEphemBlobFromKey(v22, *((_QWORD *)this + 17), L"RSAPUBLICBLOB", &v42, &v41);
    v25 = (unsigned int *)v41;
    v20 = EphemBlobFromKey;
    if ( EphemBlobFromKey )
    {
      LOBYTE(v24) = 51;
      CSslContext::SetErrorAndFatalAlert(this, 819, EphemBlobFromKey, v24);
LABEL_41:
      if ( v25 )
        SPExternalFree(v25);
      return v20;
    }
    v26 = a2 + 2;
    *a2 = BYTE1(*((_DWORD *)v41 + 3));
    a2[1] = *((_BYTE *)v25 + 12);
    memcpy_0(a2 + 2, (char *)v25 + v25[2] + 24, v25[3]);
    v27 = v25[3];
    v28 = v25[2] >> 8;
    v43 = v27;
    v26[v27] = v28;
    v26[v27 + 1] = *((_BYTE *)v25 + 8);
    v29 = &a2[v27 + 4];
    memcpy_0(v29, v25 + 6, v25[2]);
    v30 = *((_QWORD *)this + 13);
    v41 = (unsigned __int8 *)v25[2];
    v31 = &v29[(_QWORD)v41];
    v32 = *(void **)(v30 + 816);
    v39 = v25[3];
    v20 = SslImpersonateClient(v32, &v40);
    if ( !v20 )
    {
      v33 = CSsl3TlsContext::ComputeRsaServerExchangeHashes(this, a2, (_DWORD)v41 + 4 + v39, v44);
      v20 = v33;
      if ( v33 )
      {
        v35 = 815;
LABEL_33:
        LOBYTE(v34) = 80;
        CSslContext::SetErrorAndFatalAlert(this, v35, v33, v34);
        goto LABEL_39;
      }
      v36 = v14 - (_DWORD)v41 - v43;
      v37 = (_QWORD *)*((_QWORD *)this + 1);
      if ( v37 )
        v37 = (_QWORD *)*v37;
      v33 = SslSignHash(v37, *(_QWORD *)(*((_QWORD *)this + 3) + 8LL), v44, 36, v31 + 2, v36 - 6, &v38, 0);
      v20 = v33;
      if ( v33 )
      {
        v35 = 820;
        goto LABEL_33;
      }
      *v31 = BYTE1(v38);
      v31[1] = v38;
      *a3 = (_DWORD)v31 - (_DWORD)a2 + v38 + 2;
    }
LABEL_39:
    if ( v40 )
      RevertToSelf();
    goto LABEL_41;
  }
  *a3 = v13 + v39 + 10;
  return 0;
}

```

## disassembly

```asm
0x18004ab48  mov     [rsp-8+arg_18], rbx
0x18004ab4d  push    rbp
0x18004ab4e  push    rsi
0x18004ab4f  push    rdi
0x18004ab50  push    r12
0x18004ab52  push    r13
0x18004ab54  push    r14
0x18004ab56  push    r15
0x18004ab58  lea     rbp, [rsp-27h]
0x18004ab5d  sub     rsp, 0B0h
0x18004ab64  mov     rax, cs:__security_cookie
0x18004ab6b  xor     rax, rsp
0x18004ab6e  mov     [rbp+57h+var_40], rax
0x18004ab72  xor     r14d, r14d
0x18004ab75  mov     r15, r8
0x18004ab78  mov     r8, [rcx+18h]
0x18004ab7c  mov     r12, rdx
0x18004ab7f  mov     [rbp+57h+var_88], r14d
0x18004ab83  mov     rdi, rcx
0x18004ab86  mov     [rbp+57h+var_78], r14d
0x18004ab8a  mov     [rbp+57h+var_80], r14
0x18004ab8e  mov     [rbp+57h+var_90], r14d
0x18004ab92  mov     [rbp+57h+var_8C], r14d
0x18004ab96  test    r8, r8
0x18004ab99  jnz     short loc_18004ABA5
0x18004ab9b  mov     eax, 8009030Dh
0x18004aba0  jmp     loc_18004AE49
0x18004aba5  test    byte ptr [rcx+20h], 1
0x18004aba9  jz      loc_18004AE44
0x18004abaf  mov     rcx, [rcx+8]
0x18004abb3  test    rcx, rcx
0x18004abb6  jz      loc_18004AE44
0x18004abbc  mov     ecx, [rcx+1Ch]
0x18004abbf  sub     ecx, 3
0x18004abc2  jz      short loc_18004ABDF
0x18004abc4  sub     ecx, 5Fh ; '_'
0x18004abc7  jz      short loc_18004AC19
0x18004abc9  sub     ecx, 1
0x18004abcc  jz      short loc_18004AC19
0x18004abce  sub     ecx, 1
0x18004abd1  jz      short loc_18004AC19
0x18004abd3  cmp     ecx, 2001Ch
0x18004abd9  jnz     loc_18004AE44
0x18004abdf  mov     ebx, 40h ; '@'
0x18004abe4  mov     rcx, [r8+8]; unsigned __int64
0x18004abe8  lea     rdx, [rbp+57h+var_8C]; unsigned int *
0x18004abec  mov     r13d, [r15]
0x18004abef  call    ?GetRsaKeyModulus@@YAK_KPEAK@Z; GetRsaKeyModulus(unsigned __int64,ulong *)
0x18004abf4  test    eax, eax
0x18004abf6  jnz     loc_18004AE49
0x18004abfc  mov     eax, [rbp+57h+var_8C]
0x18004abff  cmp     eax, ebx
0x18004ac01  jbe     loc_18004AE44
0x18004ac07  test    r12, r12
0x18004ac0a  jnz     short loc_18004AC20
0x18004ac0c  add     eax, 0Ah
0x18004ac0f  add     eax, ebx
0x18004ac11  mov     [r15], eax
0x18004ac14  jmp     loc_18004AE47
0x18004ac19  mov     ebx, 80h
0x18004ac1e  jmp     short loc_18004ABE4
0x18004ac20  test    byte ptr [rdi+20h], 1
0x18004ac24  mov     rax, [rdi+8]
0x18004ac28  jz      short loc_18004AC35
0x18004ac2a  test    rax, rax
0x18004ac2d  jz      short loc_18004AC35
0x18004ac2f  mov     r9d, [rax+1Ch]
0x18004ac33  jmp     short loc_18004AC38
0x18004ac35  mov     r9d, r14d
0x18004ac38  movzx   r8d, word ptr [rdi+22h]
0x18004ac3d  test    rax, rax
0x18004ac40  jz      short loc_18004AC47
0x18004ac42  mov     rcx, [rax]
0x18004ac45  jmp     short loc_18004AC4A
0x18004ac47  mov     rcx, r14
0x18004ac4a  mov     [rsp+0E0h+var_A0], r14d
0x18004ac4f  lea     eax, ds:0[rbx*8]
0x18004ac56  mov     [rsp+0E0h+var_A8], r14d
0x18004ac5b  lea     rsi, [rdi+88h]
0x18004ac62  mov     [rsp+0E0h+var_B0], r14
0x18004ac67  mov     rdx, rsi
0x18004ac6a  mov     [rsp+0E0h+var_B8], eax
0x18004ac6e  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x18004ac73  call    cs:__imp_SslCreateEphemeralKey
0x18004ac79  mov     ebx, eax
0x18004ac7b  test    eax, eax
0x18004ac7d  jz      short loc_18004AC97
0x18004ac7f  mov     r9b, 33h ; '3'
0x18004ac82  mov     r8d, eax
0x18004ac85  mov     edx, 332h
0x18004ac8a  mov     rcx, rdi
0x18004ac8d  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18004ac92  jmp     loc_18004AE40
0x18004ac97  mov     rax, [rdi+8]
0x18004ac9b  test    rax, rax
0x18004ac9e  jz      short loc_18004ACA5
0x18004aca0  mov     rcx, [rax]
0x18004aca3  jmp     short loc_18004ACA8
0x18004aca5  mov     rcx, r14; unsigned __int64
0x18004aca8  mov     rdx, [rsi]; unsigned __int64
0x18004acab  lea     rax, [rbp+57h+var_80]
0x18004acaf  lea     r9, [rbp+57h+var_78]; unsigned int *
0x18004acb3  mov     [rsp+0E0h+var_C0], rax; unsigned __int8 **
0x18004acb8  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x18004acbf  call    ?GetEphemBlobFromKey@@YAK_K0PEBGPEAKPEAPEAE@Z; GetEphemBlobFromKey(unsigned __int64,unsigned __int64,ushort const *,ulong *,uchar * *)
0x18004acc4  mov     r14, [rbp+57h+var_80]
0x18004acc8  mov     ebx, eax
0x18004acca  test    eax, eax
0x18004accc  jz      short loc_18004ACE6
0x18004acce  mov     r9b, 33h ; '3'
0x18004acd1  mov     r8d, eax
0x18004acd4  mov     edx, 333h
0x18004acd9  mov     rcx, rdi
0x18004acdc  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18004ace1  jmp     loc_18004AE33
0x18004ace6  mov     eax, [r14+0Ch]
0x18004acea  lea     rbx, [r12+2]
0x18004acef  shr     eax, 8
0x18004acf2  mov     rcx, rbx; void *
0x18004acf5  mov     [r12], al
0x18004acf9  mov     al, [r14+0Ch]
0x18004acfd  mov     [r12+1], al
0x18004ad02  mov     edx, [r14+8]
0x18004ad06  mov     r8d, [r14+0Ch]; Size
0x18004ad0a  add     rdx, 18h
0x18004ad0e  add     rdx, r14; Src
0x18004ad11  call    memcpy_0
0x18004ad16  mov     ecx, [r14+0Ch]
0x18004ad1a  lea     rdx, [r14+18h]; Src
0x18004ad1e  mov     eax, [r14+8]
0x18004ad22  shr     eax, 8
0x18004ad25  mov     [rbp+57h+var_70], rcx
0x18004ad29  mov     [rcx+rbx], al
0x18004ad2c  mov     al, [r14+8]
0x18004ad30  mov     [rcx+rbx+1], al
0x18004ad34  add     rcx, 2
0x18004ad38  mov     r8d, [r14+8]; Size
0x18004ad3c  add     rbx, rcx
0x18004ad3f  mov     rcx, rbx; void *
0x18004ad42  call    memcpy_0
0x18004ad47  mov     eax, [r14+8]
0x18004ad4b  lea     rdx, [rbp+57h+var_88]; int *
0x18004ad4f  mov     rcx, [rdi+68h]
0x18004ad53  mov     [rbp+57h+var_80], rax
0x18004ad57  lea     rsi, [rax+rbx]
0x18004ad5b  mov     eax, [r14+0Ch]
0x18004ad5f  mov     rcx, [rcx+330h]; void *
0x18004ad66  mov     [rbp+57h+var_8C], eax
0x18004ad69  call    ?SslImpersonateClient@@YAKPEAXPEAH@Z; SslImpersonateClient(void *,int *)
0x18004ad6e  mov     ebx, eax
0x18004ad70  test    eax, eax
0x18004ad72  jnz     loc_18004AE27
0x18004ad78  mov     rax, [rbp+57h+var_80]
0x18004ad7c  lea     r9, [rbp+57h+var_68]; unsigned __int8 *
0x18004ad80  mov     r8d, [rbp+57h+var_8C]
0x18004ad84  add     eax, 4
0x18004ad87  add     r8d, eax; unsigned int
0x18004ad8a  mov     rdx, r12; unsigned __int8 *
0x18004ad8d  mov     rcx, rdi; this
0x18004ad90  call    ?ComputeRsaServerExchangeHashes@CSsl3TlsContext@@QEAAKPEAEK0@Z; CSsl3TlsContext::ComputeRsaServerExchangeHashes(uchar *,ulong,uchar *)
0x18004ad95  mov     ebx, eax
0x18004ad97  test    eax, eax
0x18004ad99  jz      short loc_18004ADB0
0x18004ad9b  mov     edx, 32Fh
0x18004ada0  mov     r8d, eax
0x18004ada3  mov     r9b, 50h ; 'P'
0x18004ada6  mov     rcx, rdi
0x18004ada9  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x18004adae  jmp     short loc_18004AE27
0x18004adb0  sub     r13d, dword ptr [rbp+57h+var_80]
0x18004adb4  mov     rax, [rdi+18h]
0x18004adb8  sub     r13d, dword ptr [rbp+57h+var_70]
0x18004adbc  mov     rcx, [rdi+8]
0x18004adc0  mov     rdx, [rax+8]
0x18004adc4  test    rcx, rcx
0x18004adc7  jz      short loc_18004ADCC
0x18004adc9  mov     rcx, [rcx]
0x18004adcc  lea     r9, [rbp+57h+var_90]
0x18004add0  mov     [rsp+0E0h+var_A8], 0
0x18004add8  mov     [rsp+0E0h+var_B0], r9
0x18004addd  lea     eax, [r13-6]
0x18004ade1  lea     r8, [rsi+2]
0x18004ade5  mov     [rsp+0E0h+var_B8], eax
0x18004ade9  mov     [rsp+0E0h+var_C0], r8
0x18004adee  mov     r9d, 24h ; '$'
0x18004adf4  lea     r8, [rbp+57h+var_68]
0x18004adf8  call    cs:__imp_SslSignHash
0x18004adfe  mov     ebx, eax
0x18004ae00  test    eax, eax
0x18004ae02  jz      short loc_18004AE0B
0x18004ae04  mov     edx, 334h
0x18004ae09  jmp     short loc_18004ADA0
0x18004ae0b  mov     eax, [rbp+57h+var_90]
0x18004ae0e  shr     eax, 8
0x18004ae11  mov     [rsi], al
0x18004ae13  mov     al, byte ptr [rbp+57h+var_90]
0x18004ae16  mov     [rsi+1], al
0x18004ae19  sub     esi, r12d
0x18004ae1c  mov     edx, [rbp+57h+var_90]
0x18004ae1f  add     edx, 2
0x18004ae22  add     edx, esi
0x18004ae24  mov     [r15], edx
0x18004ae27  cmp     [rbp+57h+var_88], 0
0x18004ae2b  jz      short loc_18004AE33
0x18004ae2d  call    cs:__imp_RevertToSelf
0x18004ae33  test    r14, r14
0x18004ae36  jz      short loc_18004AE40
0x18004ae38  mov     rcx, r14; void *
0x18004ae3b  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18004ae40  mov     eax, ebx
0x18004ae42  jmp     short loc_18004AE49
0x18004ae44  mov     [r15], r14d
0x18004ae47  xor     eax, eax
0x18004ae49  mov     rcx, [rbp+57h+var_40]
0x18004ae4d  xor     rcx, rsp; StackCookie
0x18004ae50  call    __security_check_cookie
0x18004ae55  mov     rbx, [rsp+0E0h+arg_18]
0x18004ae5d  add     rsp, 0B0h
0x18004ae64  pop     r15
0x18004ae66  pop     r14
0x18004ae68  pop     r13
0x18004ae6a  pop     r12
0x18004ae6c  pop     rdi
0x18004ae6d  pop     rsi
0x18004ae6e  pop     rbp
0x18004ae6f  retn
```
