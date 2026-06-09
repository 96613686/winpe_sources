# SampEncryptClearPasswordWithSessionKeyAES(void *,_UNICODE_STRING *,_SAMPR_ENCRYPTED_PASSWORD_AES *)

- ea: `0x18000a10c`
- end: `0x18000a30a`
- name: `?SampEncryptClearPasswordWithSessionKeyAES@@YAJPEAXPEAU_UNICODE_STRING@@PEAU_SAMPR_ENCRYPTED_PASSWORD_AES@@@Z`
- size: `510`
- prototype: `int(void *, struct _UNICODE_STRING *, struct _SAMPR_ENCRYPTED_PASSWORD_AES *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800040e0`

## callees

- `0x180006620`
- `0x18000807c`
- `0x180009b38`
- `0x18000a10c`
- `0x180014a50`

## import_xrefs

- `CRYPTBASE!SystemFunction028` at `0x18000a1ac`
- `CRYPTBASE!SystemFunction028` at `0x18000a1ac`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000a2bd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000a2bd`
- `bcrypt!BCryptGenRandom` at `0x18000a1ee`
- `bcrypt!BCryptGenRandom` at `0x18000a1ee`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a231`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a231`

## pseudocode

```c
__int64 __fastcall SampEncryptClearPasswordWithSessionKeyAES(
        void *a1,
        struct _UNICODE_STRING *a2,
        struct _SAMPR_ENCRYPTED_PASSWORD_AES *a3)
{
  __int64 v6; // rcx
  struct _SAMPR_ENCRYPTED_PASSWORD_AES *v7; // rax
  unsigned int v8; // ebx
  NTSTATUS v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // edx
  unsigned int v13; // r9d
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int8 v16[16]; // [rsp+48h] [rbp-40h] BYREF
  UCHAR pbBuffer[16]; // [rsp+58h] [rbp-30h] BYREF

  phAlgorithm = 0;
  *(_OWORD *)v16 = 0;
  *(_OWORD *)pbBuffer = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 250, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
  v6 = 104;
  v7 = a3;
  do
  {
    *(_BYTE *)v7 = 0;
    v7 = (struct _SAMPR_ENCRYPTED_PASSWORD_AES *)((char *)v7 + 1);
    --v6;
  }
  while ( v6 );
  *((_QWORD *)a3 + 11) = 0;
  if ( a2->Length > 0x200u )
  {
    v8 = -1073741716;
LABEL_25:
    v10 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  v9 = SystemFunction028(a1, v16);
  v8 = v9;
  if ( v9 >= 0 )
  {
    v9 = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
    v8 = v9;
    if ( v9 >= 0 )
    {
      v9 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA512", 0, 8u);
      v8 = v9;
      if ( v9 >= 0 )
      {
        v9 = SampEncryptClearPasswordAESWorker(v16, v12, pbBuffer, v13, phAlgorithm, a2, a3);
        v8 = v9;
        if ( v9 >= 0 )
          goto LABEL_25;
        v10 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = 254;
          goto LABEL_24;
        }
      }
      else
      {
        v10 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = 253;
          goto LABEL_24;
        }
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 252;
        goto LABEL_24;
      }
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 251;
LABEL_24:
      WPP_SF_D(v10[2], v11, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, (unsigned int)v9);
      goto LABEL_25;
    }
  }
LABEL_26:
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    v10 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v10 + 28) & 2) != 0 && *((_BYTE *)v10 + 25) >= 4u )
    WPP_SF_D(v10[2], 255, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18000a10c  mov     [rsp+arg_18], rbx
0x18000a111  push    rsi
0x18000a112  push    rdi
0x18000a113  push    r15
0x18000a115  sub     rsp, 70h
0x18000a119  mov     rax, cs:__security_cookie
0x18000a120  xor     rax, rsp
0x18000a123  mov     [rsp+88h+var_20], rax
0x18000a128  xorps   xmm0, xmm0
0x18000a12b  mov     [rsp+88h+phAlgorithm], 0
0x18000a134  xorps   xmm1, xmm1
0x18000a137  mov     rdi, r8
0x18000a13a  movups  xmmword ptr [rsp+88h+var_40], xmm0
0x18000a13f  mov     rsi, rdx
0x18000a142  mov     rbx, rcx
0x18000a145  movups  xmmword ptr [rsp+88h+pbBuffer], xmm1
0x18000a14a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a151  lea     r15, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000a158  test    byte ptr [rcx+1Ch], 2
0x18000a15c  jz      short loc_18000A178
0x18000a15e  cmp     byte ptr [rcx+19h], 4
0x18000a162  jb      short loc_18000A178
0x18000a164  mov     rcx, [rcx+10h]
0x18000a168  mov     edx, 0FAh
0x18000a16d  mov     r9, rbx
0x18000a170  mov     r8, r15
0x18000a173  call    WPP_SF_q
0x18000a178  mov     ecx, 68h ; 'h'
0x18000a17d  mov     rax, rdi
0x18000a180  mov     byte ptr [rax], 0
0x18000a183  inc     rax
0x18000a186  sub     rcx, 1
0x18000a18a  jnz     short loc_18000A180
0x18000a18c  mov     eax, 200h
0x18000a191  mov     [rdi+58h], rcx
0x18000a195  cmp     [rsi], ax
0x18000a198  jbe     short loc_18000A1A4
0x18000a19a  mov     ebx, 0C000006Ch
0x18000a19f  jmp     loc_18000A2A7
0x18000a1a4  lea     rdx, [rsp+88h+var_40]
0x18000a1a9  mov     rcx, rbx
0x18000a1ac  call    cs:__imp_SystemFunction028
0x18000a1b2  mov     ebx, eax
0x18000a1b4  test    eax, eax
0x18000a1b6  jns     short loc_18000A1DD
0x18000a1b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1bf  test    byte ptr [rcx+1Ch], 2
0x18000a1c3  jz      loc_18000A2AE
0x18000a1c9  cmp     byte ptr [rcx+19h], 2
0x18000a1cd  jb      loc_18000A2AE
0x18000a1d3  mov     edx, 0FBh
0x18000a1d8  jmp     loc_18000A298
0x18000a1dd  mov     r9d, 2; dwFlags
0x18000a1e3  lea     rdx, [rsp+88h+pbBuffer]; pbBuffer
0x18000a1e8  xor     ecx, ecx; hAlgorithm
0x18000a1ea  lea     r8d, [r9+0Eh]; cbBuffer
0x18000a1ee  call    cs:__imp_BCryptGenRandom
0x18000a1f4  mov     ebx, eax
0x18000a1f6  test    eax, eax
0x18000a1f8  jns     short loc_18000A21C
0x18000a1fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a201  test    byte ptr [rcx+1Ch], 2
0x18000a205  jz      loc_18000A2AE
0x18000a20b  cmp     byte ptr [rcx+19h], 2
0x18000a20f  jb      loc_18000A2AE
0x18000a215  mov     edx, 0FCh
0x18000a21a  jmp     short loc_18000A298
0x18000a21c  mov     r9d, 8; dwFlags
0x18000a222  lea     rdx, pszAlgId; "SHA512"
0x18000a229  xor     r8d, r8d; pszImplementation
0x18000a22c  lea     rcx, [rsp+88h+phAlgorithm]; phAlgorithm
0x18000a231  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000a237  mov     ebx, eax
0x18000a239  test    eax, eax
0x18000a23b  jns     short loc_18000A257
0x18000a23d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a244  test    byte ptr [rcx+1Ch], 2
0x18000a248  jz      short loc_18000A2AE
0x18000a24a  cmp     byte ptr [rcx+19h], 2
0x18000a24e  jb      short loc_18000A2AE
0x18000a250  mov     edx, 0FDh
0x18000a255  jmp     short loc_18000A298
0x18000a257  mov     rax, [rsp+88h+phAlgorithm]
0x18000a25c  lea     r8, [rsp+88h+pbBuffer]; unsigned __int8 *
0x18000a261  mov     [rsp+88h+var_58], rdi; struct _SAMPR_ENCRYPTED_PASSWORD_AES *
0x18000a266  lea     rcx, [rsp+88h+var_40]; unsigned __int8 *
0x18000a26b  mov     [rsp+88h+var_60], rsi; struct _UNICODE_STRING *
0x18000a270  mov     [rsp+88h+hAlgorithm], rax; hAlgorithm
0x18000a275  call    ?SampEncryptClearPasswordAESWorker@@YAJPEAEK0KPEAXPEAU_UNICODE_STRING@@PEAU_SAMPR_ENCRYPTED_PASSWORD_AES@@@Z; SampEncryptClearPasswordAESWorker(uchar *,ulong,uchar *,ulong,void *,_UNICODE_STRING *,_SAMPR_ENCRYPTED_PASSWORD_AES *)
0x18000a27a  mov     ebx, eax
0x18000a27c  test    eax, eax
0x18000a27e  jns     short loc_18000A2A7
0x18000a280  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a287  test    byte ptr [rcx+1Ch], 2
0x18000a28b  jz      short loc_18000A2AE
0x18000a28d  cmp     byte ptr [rcx+19h], 2
0x18000a291  jb      short loc_18000A2AE
0x18000a293  mov     edx, 0FEh
0x18000a298  mov     rcx, [rcx+10h]
0x18000a29c  mov     r9d, eax
0x18000a29f  mov     r8, r15
0x18000a2a2  call    WPP_SF_D
0x18000a2a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2ae  mov     rax, [rsp+88h+phAlgorithm]
0x18000a2b3  test    rax, rax
0x18000a2b6  jz      short loc_18000A2CA
0x18000a2b8  xor     edx, edx; dwFlags
0x18000a2ba  mov     rcx, rax; hAlgorithm
0x18000a2bd  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000a2c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2ca  test    byte ptr [rcx+1Ch], 2
0x18000a2ce  jz      short loc_18000A2EA
0x18000a2d0  cmp     byte ptr [rcx+19h], 4
0x18000a2d4  jb      short loc_18000A2EA
0x18000a2d6  mov     rcx, [rcx+10h]
0x18000a2da  mov     edx, 0FFh
0x18000a2df  mov     r9d, ebx
0x18000a2e2  mov     r8, r15
0x18000a2e5  call    WPP_SF_D
0x18000a2ea  mov     eax, ebx
0x18000a2ec  mov     rcx, [rsp+88h+var_20]
0x18000a2f1  xor     rcx, rsp; StackCookie
0x18000a2f4  call    __security_check_cookie
0x18000a2f9  mov     rbx, [rsp+88h+arg_18]
0x18000a301  add     rsp, 70h
0x18000a305  pop     r15
0x18000a307  pop     rdi
0x18000a308  pop     rsi
0x18000a309  retn
```
