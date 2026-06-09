# WFDCreateDHPrivatePublicKeyPairLib(uchar *,ulong *,uchar *,ulong)

- ea: `0x18005c514`
- end: `0x18005c929`
- name: `?WFDCreateDHPrivatePublicKeyPairLib@@YAJPEAEPEAK0K@Z`
- size: `1045`
- prototype: `__int64 __fastcall(PUCHAR pbOutput, unsigned int *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002c380`

## callees

- `0x1800063a0`
- `0x180011bf8`
- `0x180019a20`
- `0x18001a5bc`
- `0x18005c2f4`
- `0x18005c514`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18005c5fb`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18005c5fb`
- `bcrypt!BCryptExportKey` at `0x18005c828`
- `bcrypt!BCryptExportKey` at `0x18005c884`
- `bcrypt!BCryptExportKey` at `0x18005c828`
- `bcrypt!BCryptExportKey` at `0x18005c884`
- `bcrypt!BCryptGenerateKeyPair` at `0x18005c6ab`
- `bcrypt!BCryptGenerateKeyPair` at `0x18005c6ab`
- `bcrypt!BCryptFinalizeKeyPair` at `0x18005c7bd`
- `bcrypt!BCryptFinalizeKeyPair` at `0x18005c7bd`
- `bcrypt!BCryptDestroyKey` at `0x18005c64b`
- `bcrypt!BCryptDestroyKey` at `0x18005c64b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18005c59d`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18005c59d`
- `bcrypt!BCryptSetProperty` at `0x18005c775`
- `bcrypt!BCryptSetProperty` at `0x18005c775`

## pseudocode

```c
__int64 __fastcall WFDCreateDHPrivatePublicKeyPairLib(
        PUCHAR pbOutput,
        unsigned int *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  int v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // edi
  unsigned int v13; // eax
  unsigned int v14; // edi
  unsigned int v16; // ebx
  union DOT11_OUI_HEADER *v17; // rcx
  __int64 v18; // rdx
  unsigned int v19; // edi
  union DOT11_OUI_HEADER *v20; // rcx
  __int64 v21; // rdx
  ULONG pcbResult; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+48h] [rbp-B8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD Source[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v26; // [rsp+60h] [rbp-A0h]
  UCHAR Destination[12]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v28[192]; // [rsp+7Ch] [rbp-84h] BYREF
  _BYTE v29[196]; // [rsp+13Ch] [rbp+3Ch] BYREF

  phAlgorithm = 0;
  hKey = 0;
  pcbResult = 0;
  memset_0(Destination, 0, 0x18Cu);
  if ( !a2 || !a3 )
    return 87;
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"DH", L"Microsoft Primitive Provider", 0);
  v9 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 23, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids, v8);
    }
    v10 = v9 | 0x10000000;
    goto LABEL_9;
  }
  v16 = BCryptGenerateKeyPair(phAlgorithm, &hKey, 0x600u, 0);
  if ( v16 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 105)
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
    {
      goto LABEL_32;
    }
    v18 = 24;
    goto LABEL_31;
  }
  Source[1] = 1297107012;
  Source[0] = 396;
  v26 = 192;
  memcpy_s_0(Destination, 0x18Cu, Source, 0xCu);
  memcpy_s_0(v28, 0x180u, qword_180075EC0, 0xC0u);
  memcpy_s_0(v29, 0xC0u, qword_180075E00, 0xC0u);
  v16 = BCryptSetProperty(hKey, L"DHParameters", Destination, 0x18Cu, 0);
  if ( v16 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 105)
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
    {
      goto LABEL_32;
    }
    v18 = 25;
    goto LABEL_31;
  }
  v16 = BCryptFinalizeKeyPair(hKey, 0);
  if ( v16 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 105)
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
    {
      goto LABEL_32;
    }
    v18 = 26;
LABEL_31:
    WPP_SF_d(*((_QWORD *)v17 + 12), v18, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids, v16);
LABEL_32:
    v10 = v16 | 0x10000000;
    goto LABEL_9;
  }
  v10 = 0;
  if ( pbOutput )
  {
    v19 = BCryptExportKey(hKey, 0, L"DHPRIVATEBLOB", pbOutput, *a2, &pcbResult, 0);
    if ( v19 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
      {
        goto LABEL_50;
      }
      v21 = 28;
      goto LABEL_49;
    }
    v19 = ExportPublicKeyHash(hKey, v26, a3, a4);
    if ( v19 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
      {
        goto LABEL_50;
      }
      v21 = 29;
      goto LABEL_49;
    }
  }
  else
  {
    v19 = BCryptExportKey(hKey, 0, L"DHPRIVATEBLOB", 0, 0, &pcbResult, 0);
    if ( v19 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
      {
        goto LABEL_50;
      }
      v21 = 27;
LABEL_49:
      WPP_SF_d(*((_QWORD *)v20 + 12), v21, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids, v19);
LABEL_50:
      v16 = v19;
      goto LABEL_32;
    }
    *a2 = pcbResult;
  }
LABEL_9:
  if ( phAlgorithm )
  {
    v11 = BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    v12 = v11;
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 30, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids, v11);
      }
      if ( v10 >= 0 )
        v10 = v12 | 0x10000000;
    }
  }
  if ( hKey )
  {
    v13 = BCryptDestroyKey(hKey);
    v14 = v13;
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 31, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids, v13);
      }
      if ( v10 >= 0 )
        return v14 | 0x10000000;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18005c514  push    rbp
0x18005c516  push    rbx
0x18005c517  push    rsi
0x18005c518  push    rdi
0x18005c519  push    r14
0x18005c51b  push    r15
0x18005c51d  lea     rbp, [rsp-118h]
0x18005c525  sub     rsp, 218h
0x18005c52c  mov     rax, cs:__security_cookie
0x18005c533  xor     rax, rsp
0x18005c536  mov     [rbp+140h+var_40], rax
0x18005c53d  mov     r14, r8
0x18005c540  mov     [rsp+240h+phAlgorithm], 0
0x18005c549  mov     rsi, rdx
0x18005c54c  mov     [rsp+240h+hKey], 0
0x18005c555  mov     rdi, rcx
0x18005c558  mov     [rsp+240h+var_200], 0
0x18005c560  xor     edx, edx; Val
0x18005c562  lea     rcx, [rsp+240h+Destination]; void *
0x18005c567  mov     r8d, 18Ch; Size
0x18005c56d  mov     r15d, r9d
0x18005c570  call    memset_0
0x18005c575  test    rsi, rsi
0x18005c578  jz      loc_18005C905
0x18005c57e  test    r14, r14
0x18005c581  jz      loc_18005C905
0x18005c587  xor     r9d, r9d; dwFlags
0x18005c58a  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18005c591  lea     rdx, aDh; "DH"
0x18005c598  lea     rcx, [rsp+240h+phAlgorithm]; phAlgorithm
0x18005c59d  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18005c5a3  lea     rdx, WPP_GLOBAL_Control
0x18005c5aa  mov     ebx, eax
0x18005c5ac  test    eax, eax
0x18005c5ae  jz      loc_18005C698
0x18005c5b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c5bb  cmp     rcx, rdx
0x18005c5be  jz      short loc_18005C5E4
0x18005c5c0  cmp     byte ptr [rcx+69h], 1
0x18005c5c4  jb      short loc_18005C5E4
0x18005c5c6  test    byte ptr [rcx+6Ch], 2
0x18005c5ca  jz      short loc_18005C5E4
0x18005c5cc  mov     rcx, [rcx+60h]
0x18005c5d0  lea     r8, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids
0x18005c5d7  mov     edx, 17h
0x18005c5dc  mov     r9d, eax
0x18005c5df  call    WPP_SF_d
0x18005c5e4  bts     ebx, 1Ch
0x18005c5e8  lea     rsi, WPP_GLOBAL_Control
0x18005c5ef  mov     rcx, [rsp+240h+phAlgorithm]; hAlgorithm
0x18005c5f4  test    rcx, rcx
0x18005c5f7  jz      short loc_18005C641
0x18005c5f9  xor     edx, edx; dwFlags
0x18005c5fb  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18005c601  mov     edi, eax
0x18005c603  test    eax, eax
0x18005c605  jz      short loc_18005C641
0x18005c607  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c60e  cmp     rcx, rsi
0x18005c611  jz      short loc_18005C637
0x18005c613  cmp     byte ptr [rcx+69h], 1
0x18005c617  jb      short loc_18005C637
0x18005c619  test    byte ptr [rcx+6Ch], 2
0x18005c61d  jz      short loc_18005C637
0x18005c61f  mov     rcx, [rcx+60h]
0x18005c623  lea     r8, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids
0x18005c62a  mov     edx, 1Eh
0x18005c62f  mov     r9d, eax
0x18005c632  call    WPP_SF_d
0x18005c637  test    ebx, ebx
0x18005c639  js      short loc_18005C641
0x18005c63b  mov     ebx, edi
0x18005c63d  bts     ebx, 1Ch
0x18005c641  mov     rcx, [rsp+240h+hKey]; hKey
0x18005c646  test    rcx, rcx
0x18005c649  jz      short loc_18005C691
0x18005c64b  call    cs:__imp_BCryptDestroyKey
0x18005c651  mov     edi, eax
0x18005c653  test    eax, eax
0x18005c655  jz      short loc_18005C691
0x18005c657  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c65e  cmp     rcx, rsi
0x18005c661  jz      short loc_18005C687
0x18005c663  cmp     byte ptr [rcx+69h], 1
0x18005c667  jb      short loc_18005C687
0x18005c669  test    byte ptr [rcx+6Ch], 2
0x18005c66d  jz      short loc_18005C687
0x18005c66f  mov     rcx, [rcx+60h]
0x18005c673  lea     r8, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids
0x18005c67a  mov     edx, 1Fh
0x18005c67f  mov     r9d, eax
0x18005c682  call    WPP_SF_d
0x18005c687  test    ebx, ebx
0x18005c689  js      short loc_18005C691
0x18005c68b  mov     ebx, edi
0x18005c68d  bts     ebx, 1Ch
0x18005c691  mov     eax, ebx
0x18005c693  jmp     loc_18005C90A
0x18005c698  mov     rcx, [rsp+240h+phAlgorithm]; hAlgorithm
0x18005c69d  lea     rdx, [rsp+240h+hKey]; phKey
0x18005c6a2  xor     r9d, r9d; dwFlags
0x18005c6a5  mov     r8d, 600h; dwLength
0x18005c6ab  call    cs:__imp_BCryptGenerateKeyPair
0x18005c6b1  mov     ebx, eax
0x18005c6b3  test    eax, eax
0x18005c6b5  jz      short loc_18005C6F7
0x18005c6b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c6be  lea     rsi, WPP_GLOBAL_Control
0x18005c6c5  cmp     rcx, rsi
0x18005c6c8  jz      short loc_18005C6EE
0x18005c6ca  cmp     byte ptr [rcx+69h], 1
0x18005c6ce  jb      short loc_18005C6EE
0x18005c6d0  test    byte ptr [rcx+6Ch], 2
0x18005c6d4  jz      short loc_18005C6EE
0x18005c6d6  mov     edx, 18h
0x18005c6db  mov     rcx, [rcx+60h]
0x18005c6df  lea     r8, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids
0x18005c6e6  mov     r9d, ebx
0x18005c6e9  call    WPP_SF_d
0x18005c6ee  bts     ebx, 1Ch
0x18005c6f2  jmp     loc_18005C5EF
0x18005c6f7  mov     eax, 18Ch
0x18005c6fc  mov     [rsp+240h+var_1E4], 4D504844h
0x18005c704  mov     ebx, 0C0h
0x18005c709  mov     [rsp+240h+Source], eax
0x18005c70d  mov     edx, eax; DestinationSize
0x18005c70f  mov     [rsp+240h+var_1E0], ebx
0x18005c713  mov     r9d, 0Ch; SourceSize
0x18005c719  lea     r8, [rsp+240h+Source]; Source
0x18005c71e  lea     rcx, [rsp+240h+Destination]; Destination
0x18005c723  call    memcpy_s_0
0x18005c728  mov     r9d, ebx; SourceSize
0x18005c72b  lea     r8, qword_180075EC0; Source
0x18005c732  mov     edx, 180h; DestinationSize
0x18005c737  lea     rcx, [rsp+240h+var_1C4]; Destination
0x18005c73c  call    memcpy_s_0
0x18005c741  mov     r9d, ebx; SourceSize
0x18005c744  lea     r8, qword_180075E00; Source
0x18005c74b  mov     edx, ebx; DestinationSize
0x18005c74d  lea     rcx, [rbp+140h+var_104]; Destination
0x18005c751  call    memcpy_s_0
0x18005c756  mov     rcx, [rsp+240h+hKey]; hObject
0x18005c75b  lea     r8, [rsp+240h+Destination]; pbInput
0x18005c760  mov     r9d, 18Ch; cbInput
0x18005c766  mov     [rsp+240h+dwFlags], 0; dwFlags
0x18005c76e  lea     rdx, aDhparameters; "DHParameters"
0x18005c775  call    cs:__imp_BCryptSetProperty
0x18005c77b  mov     ebx, eax
0x18005c77d  test    eax, eax
0x18005c77f  jz      short loc_18005C7B6
0x18005c781  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c788  lea     rsi, WPP_GLOBAL_Control
0x18005c78f  cmp     rcx, rsi
0x18005c792  jz      loc_18005C6EE
0x18005c798  cmp     byte ptr [rcx+69h], 1
0x18005c79c  jb      loc_18005C6EE
0x18005c7a2  test    byte ptr [rcx+6Ch], 2
0x18005c7a6  jz      loc_18005C6EE
0x18005c7ac  mov     edx, 19h
0x18005c7b1  jmp     loc_18005C6DB
0x18005c7b6  mov     rcx, [rsp+240h+hKey]; hKey
0x18005c7bb  xor     edx, edx; dwFlags
0x18005c7bd  call    cs:__imp_BCryptFinalizeKeyPair
0x18005c7c3  mov     ebx, eax
0x18005c7c5  test    eax, eax
0x18005c7c7  jz      short loc_18005C7FE
0x18005c7c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c7d0  lea     rsi, WPP_GLOBAL_Control
0x18005c7d7  cmp     rcx, rsi
0x18005c7da  jz      loc_18005C6EE
0x18005c7e0  cmp     byte ptr [rcx+69h], 1
0x18005c7e4  jb      loc_18005C6EE
0x18005c7ea  test    byte ptr [rcx+6Ch], 2
0x18005c7ee  jz      loc_18005C6EE
0x18005c7f4  mov     edx, 1Ah
0x18005c7f9  jmp     loc_18005C6DB
0x18005c7fe  mov     rcx, [rsp+240h+hKey]; hKey
0x18005c803  lea     rax, [rsp+240h+var_200]
0x18005c808  xor     ebx, ebx
0x18005c80a  lea     r8, aDhprivateblob; "DHPRIVATEBLOB"
0x18005c811  xor     edx, edx; hExportKey
0x18005c813  mov     [rsp+240h+var_210], ebx; dwFlags
0x18005c817  mov     [rsp+240h+pcbResult], rax; pcbResult
0x18005c81c  test    rdi, rdi
0x18005c81f  jnz     short loc_18005C87B
0x18005c821  xor     r9d, r9d; pbOutput
0x18005c824  mov     [rsp+240h+dwFlags], ebx; cbOutput
0x18005c828  call    cs:__imp_BCryptExportKey
0x18005c82e  mov     edi, eax
0x18005c830  test    eax, eax
0x18005c832  jz      short loc_18005C870
0x18005c834  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c83b  lea     rsi, WPP_GLOBAL_Control
0x18005c842  cmp     rcx, rsi
0x18005c845  jz      short loc_18005C869
0x18005c847  cmp     byte ptr [rcx+69h], 1
0x18005c84b  jb      short loc_18005C869
0x18005c84d  test    byte ptr [rcx+6Ch], 2
0x18005c851  jz      short loc_18005C869
0x18005c853  lea     edx, [rbx+1Bh]
0x18005c856  mov     rcx, [rcx+60h]
0x18005c85a  lea     r8, WPP_02ead5159b5b32473634c4a98e194ba7_Traceguids
0x18005c861  mov     r9d, edi
0x18005c864  call    WPP_SF_d
0x18005c869  mov     ebx, edi
0x18005c86b  jmp     loc_18005C6EE
0x18005c870  mov     eax, [rsp+240h+var_200]
0x18005c874  mov     [rsi], eax
0x18005c876  jmp     loc_18005C5E8
0x18005c87b  mov     eax, [rsi]
0x18005c87d  mov     r9, rdi; pbOutput
0x18005c880  mov     [rsp+240h+dwFlags], eax; cbOutput
0x18005c884  call    cs:__imp_BCryptExportKey
0x18005c88a  mov     edi, eax
0x18005c88c  test    eax, eax
0x18005c88e  jz      short loc_18005C8B6
0x18005c890  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c897  lea     rsi, WPP_GLOBAL_Control
0x18005c89e  cmp     rcx, rsi
0x18005c8a1  jz      short loc_18005C869
0x18005c8a3  cmp     byte ptr [rcx+69h], 1
0x18005c8a7  jb      short loc_18005C869
0x18005c8a9  test    byte ptr [rcx+6Ch], 2
0x18005c8ad  jz      short loc_18005C869
0x18005c8af  mov     edx, 1Ch
0x18005c8b4  jmp     short loc_18005C856
0x18005c8b6  mov     edx, [rsp+240h+var_1E0]; unsigned int
0x18005c8ba  mov     r9d, r15d; unsigned int
0x18005c8bd  mov     rcx, [rsp+240h+hKey]; hKey
0x18005c8c2  mov     r8, r14; unsigned __int8 *
0x18005c8c5  call    ?ExportPublicKeyHash@@YAJPEAXKPEAEK@Z; ExportPublicKeyHash(void *,ulong,uchar *,ulong)
0x18005c8ca  mov     edi, eax
0x18005c8cc  test    eax, eax
0x18005c8ce  jz      loc_18005C5E8
0x18005c8d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c8db  lea     rsi, WPP_GLOBAL_Control
0x18005c8e2  cmp     rcx, rsi
0x18005c8e5  jz      short loc_18005C869
0x18005c8e7  cmp     byte ptr [rcx+69h], 1
0x18005c8eb  jb      loc_18005C869
0x18005c8f1  test    byte ptr [rcx+6Ch], 2
0x18005c8f5  jz      loc_18005C869
0x18005c8fb  mov     edx, 1Dh
0x18005c900  jmp     loc_18005C856
0x18005c905  mov     eax, 57h ; 'W'
0x18005c90a  mov     rcx, [rbp+140h+var_40]
0x18005c911  xor     rcx, rsp; StackCookie
0x18005c914  call    __security_check_cookie
0x18005c919  add     rsp, 218h
0x18005c920  pop     r15
0x18005c922  pop     r14
0x18005c924  pop     rdi
0x18005c925  pop     rsi
0x18005c926  pop     rbx
0x18005c927  pop     rbp
0x18005c928  retn
```
