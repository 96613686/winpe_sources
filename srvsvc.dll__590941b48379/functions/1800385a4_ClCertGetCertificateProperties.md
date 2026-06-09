# ClCertGetCertificateProperties

- ea: `0x1800385a4`
- end: `0x1800388c2`
- name: `ClCertGetCertificateProperties`
- size: `798`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x180035dec`

## callees

- `0x180020de8`
- `0x180036928`
- `0x180037510`
- `0x18003756c`
- `0x180037f58`
- `0x180038338`
- `0x1800385a4`
- `0x1800388c8`
- `0x180038d48`
- `0x18003a528`
- `0x18003a5e0`
- `0x18003b428`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800385fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800385fb`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800387f2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800387f2`
- `CRYPT32!CertCreateCertificateContext` at `0x1800385ed`
- `CRYPT32!CertCreateCertificateContext` at `0x1800385ed`
- `CRYPT32!CertFreeCertificateContext` at `0x1800388a9`
- `CRYPT32!CertFreeCertificateContext` at `0x1800388a9`

## pseudocode

```c
__int64 __fastcall ClCertGetCertificateProperties(PUCHAR pbInput, ULONG cbInput, __int64 a3, int a4, __int64 a5)
{
  PCCERT_CONTEXT CertificateContext; // rax
  const CERT_CONTEXT *v9; // rdi
  ULONG CertificateNameProperty; // ebx
  __int64 v11; // r8
  _QWORD *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  _QWORD *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r14
  int v18; // r8d
  int v19; // eax
  NTSTATUS v20; // ebx
  BCRYPT_HASH_HANDLE hHash[11]; // [rsp+40h] [rbp-58h] BYREF

  hHash[0] = 0;
  *(_OWORD *)a5 = 0;
  *(_OWORD *)(a5 + 16) = 0;
  *(_QWORD *)(a5 + 32) = 0;
  CertificateContext = CertCreateCertificateContext(1u, pbInput, cbInput);
  v9 = CertificateContext;
  if ( CertificateContext )
  {
    CertificateNameProperty = ClCertGetCertificateNameProperty(CertificateContext->pCertInfo, 0, a5 + 24);
    if ( CertificateNameProperty )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v16 = 37;
LABEL_12:
        WPP_SF_qqL(v15[2], v16, v14, v9, pbInput, cbInput);
      }
    }
    else
    {
      v17 = 0;
      do
      {
        CertificateNameProperty = ClCertCalculateBlobHash(pbInput, cbInput, *(BCRYPT_HASH_HANDLE *)(a3 + 8 * v17));
        if ( CertificateNameProperty )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_DSqL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)WPP_GLOBAL_Control,
              v18,
              CertificateNameProperty,
              (__int64)(&off_18004CD80)[v17],
              (char)pbInput,
              cbInput);
          }
          goto LABEL_43;
        }
        v17 = (unsigned int)(v17 + 1);
      }
      while ( !(_DWORD)v17 );
      if ( !a4 )
        goto LABEL_43;
      CertificateNameProperty = ClCertGetCertificateNameProperty(v9->pCertInfo, 1, a5);
      if ( CertificateNameProperty )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          v16 = 39;
          goto LABEL_12;
        }
      }
      else
      {
        CertificateNameProperty = ClCertGetCertificateSerialNumber(v9->pCertInfo, a5 + 8);
        if ( CertificateNameProperty )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            v16 = 40;
            goto LABEL_12;
          }
        }
        else
        {
          if ( (unsigned __int8)ClCertIsAlgorithmSupported(L"SHA1", 0) )
            goto LABEL_43;
          v19 = ClCertDuplicateHashHandle(&xmmword_18005C820, hHash);
          v20 = v19;
          if ( v19 >= 0 )
          {
            CertificateNameProperty = ClCertCalculateBlobHash(pbInput, cbInput, hHash[0]);
            if ( CertificateNameProperty )
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) )
              {
                v13 = 42;
                goto LABEL_6;
              }
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                41,
                WPP_053b19d310c5352633ee666709ba12ba_Traceguids,
                (unsigned int)v19);
            }
            CertificateNameProperty = RtlNtStatusToDosErrorNoTeb(v20);
          }
        }
      }
    }
  }
  else
  {
    CertificateNameProperty = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v13 = 36;
LABEL_6:
      WPP_SF_DqL(v12[2], v13, v11, CertificateNameProperty, pbInput, cbInput);
    }
  }
LABEL_43:
  ClCertDestroyHashHandle(hHash[0]);
  if ( CertificateNameProperty )
    ClCertFreeCertificateProperties(a5);
  if ( v9 )
    CertFreeCertificateContext(v9);
  return CertificateNameProperty;
}

```

## disassembly

```asm
0x1800385a4  mov     [rsp+arg_10], r8
0x1800385a9  push    rbx
0x1800385aa  push    rbp
0x1800385ab  push    rsi
0x1800385ac  push    rdi
0x1800385ad  push    r12
0x1800385af  push    r13
0x1800385b1  push    r14
0x1800385b3  push    r15
0x1800385b5  sub     rsp, 58h
0x1800385b9  mov     r15, [rsp+98h+arg_20]
0x1800385c1  xor     eax, eax
0x1800385c3  xorps   xmm0, xmm0
0x1800385c6  mov     [rsp+98h+hHash], 0
0x1800385cf  mov     esi, edx
0x1800385d1  mov     r8d, edx; cbCertEncoded
0x1800385d4  mov     rbp, rcx
0x1800385d7  mov     rdx, rcx; pbCertEncoded
0x1800385da  movups  xmmword ptr [r15], xmm0
0x1800385de  lea     ecx, [rax+1]; dwCertEncodingType
0x1800385e1  mov     r13d, r9d
0x1800385e4  movups  xmmword ptr [r15+10h], xmm0
0x1800385e9  mov     [r15+20h], rax
0x1800385ed  call    cs:__imp_CertCreateCertificateContext
0x1800385f3  mov     rdi, rax
0x1800385f6  test    rax, rax
0x1800385f9  jnz     short loc_18003864E
0x1800385fb  call    cs:__imp_GetLastError
0x180038601  mov     ebx, eax
0x180038603  mov     rax, cs:WPP_GLOBAL_Control
0x18003860a  lea     rcx, WPP_GLOBAL_Control
0x180038611  cmp     rax, rcx
0x180038614  jz      loc_18003888B
0x18003861a  test    dword ptr [rax+1Ch], 800h
0x180038621  jz      loc_18003888B
0x180038627  cmp     byte ptr [rax+19h], 1
0x18003862b  jb      loc_18003888B
0x180038631  lea     edx, [rdi+24h]
0x180038634  mov     rcx, [rax+10h]
0x180038638  mov     r9d, ebx
0x18003863b  mov     dword ptr [rsp+98h+var_70], esi
0x18003863f  mov     [rsp+98h+var_78], rbp
0x180038644  call    WPP_SF_DqL
0x180038649  jmp     loc_18003888B
0x18003864e  mov     rcx, [rax+18h]
0x180038652  lea     r8, [r15+18h]
0x180038656  xor     edx, edx
0x180038658  call    ClCertGetCertificateNameProperty
0x18003865d  mov     ebx, eax
0x18003865f  test    eax, eax
0x180038661  jz      short loc_1800386B0
0x180038663  mov     rax, cs:WPP_GLOBAL_Control
0x18003866a  lea     rcx, WPP_GLOBAL_Control
0x180038671  cmp     rax, rcx
0x180038674  jz      loc_18003888B
0x18003867a  test    dword ptr [rax+1Ch], 800h
0x180038681  jz      loc_18003888B
0x180038687  cmp     byte ptr [rax+19h], 1
0x18003868b  jb      loc_18003888B
0x180038691  mov     edx, 25h ; '%'
0x180038696  mov     rcx, [rax+10h]
0x18003869a  mov     r9, rdi
0x18003869d  mov     dword ptr [rsp+98h+var_70], esi
0x1800386a1  mov     [rsp+98h+var_78], rbp
0x1800386a6  call    WPP_SF_qqL
0x1800386ab  jmp     loc_18003888B
0x1800386b0  xor     r14d, r14d
0x1800386b3  mov     rax, [rsp+98h+arg_10]
0x1800386bb  lea     r9, [r15+20h]
0x1800386bf  lea     r9, [r9+r14*8]
0x1800386c3  mov     edx, esi; cbInput
0x1800386c5  mov     rcx, rbp; pbInput
0x1800386c8  mov     r8, [rax+r14*8]; hHash
0x1800386cc  call    ClCertCalculateBlobHash
0x1800386d1  mov     ebx, eax
0x1800386d3  test    eax, eax
0x1800386d5  jnz     loc_180038844
0x1800386db  lea     r12d, [rax+1]
0x1800386df  add     r14d, r12d
0x1800386e2  cmp     r14d, r12d
0x1800386e5  jb      short loc_1800386B3
0x1800386e7  test    r13d, r13d
0x1800386ea  jz      loc_18003888B
0x1800386f0  mov     rcx, [rdi+18h]
0x1800386f4  mov     r8, r15
0x1800386f7  mov     edx, r12d
0x1800386fa  call    ClCertGetCertificateNameProperty
0x1800386ff  mov     ebx, eax
0x180038701  test    eax, eax
0x180038703  jz      short loc_18003873D
0x180038705  mov     rax, cs:WPP_GLOBAL_Control
0x18003870c  lea     rcx, WPP_GLOBAL_Control
0x180038713  cmp     rax, rcx
0x180038716  jz      loc_18003888B
0x18003871c  test    dword ptr [rax+1Ch], 800h
0x180038723  jz      loc_18003888B
0x180038729  cmp     [rax+19h], r12b
0x18003872d  jb      loc_18003888B
0x180038733  lea     edx, [r12+26h]
0x180038738  jmp     loc_180038696
0x18003873d  mov     rcx, [rdi+18h]
0x180038741  lea     rdx, [r15+8]
0x180038745  call    ClCertGetCertificateSerialNumber
0x18003874a  mov     ebx, eax
0x18003874c  test    eax, eax
0x18003874e  jz      short loc_180038788
0x180038750  mov     rax, cs:WPP_GLOBAL_Control
0x180038757  lea     rcx, WPP_GLOBAL_Control
0x18003875e  cmp     rax, rcx
0x180038761  jz      loc_18003888B
0x180038767  test    dword ptr [rax+1Ch], 800h
0x18003876e  jz      loc_18003888B
0x180038774  cmp     [rax+19h], r12b
0x180038778  jb      loc_18003888B
0x18003877e  mov     edx, 28h ; '('
0x180038783  jmp     loc_180038696
0x180038788  xor     edx, edx
0x18003878a  lea     rcx, aSha1; "SHA1"
0x180038791  call    ClCertIsAlgorithmSupported
0x180038796  test    al, al
0x180038798  jnz     loc_18003888B
0x18003879e  lea     rdx, [rsp+98h+hHash]
0x1800387a3  lea     rcx, xmmword_18005C820
0x1800387aa  call    ClCertDuplicateHashHandle
0x1800387af  mov     ebx, eax
0x1800387b1  test    eax, eax
0x1800387b3  jns     short loc_1800387FF
0x1800387b5  mov     r10, cs:WPP_GLOBAL_Control
0x1800387bc  lea     rcx, WPP_GLOBAL_Control
0x1800387c3  cmp     r10, rcx
0x1800387c6  jz      short loc_1800387F0
0x1800387c8  test    dword ptr [r10+1Ch], 800h
0x1800387d0  jz      short loc_1800387F0
0x1800387d2  cmp     [r10+19h], r12b
0x1800387d6  jb      short loc_1800387F0
0x1800387d8  mov     rcx, [r10+10h]
0x1800387dc  lea     r8, WPP_053b19d310c5352633ee666709ba12ba_Traceguids
0x1800387e3  mov     edx, 29h ; ')'
0x1800387e8  mov     r9d, eax
0x1800387eb  call    WPP_SF_d
0x1800387f0  mov     ecx, ebx; Status
0x1800387f2  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800387f8  mov     ebx, eax
0x1800387fa  jmp     loc_18003888B
0x1800387ff  mov     r8, [rsp+98h+hHash]; hHash
0x180038804  lea     r9, [r15+10h]
0x180038808  mov     edx, esi; cbInput
0x18003880a  mov     rcx, rbp; pbInput
0x18003880d  call    ClCertCalculateBlobHash
0x180038812  mov     ebx, eax
0x180038814  test    eax, eax
0x180038816  jz      short loc_18003888B
0x180038818  mov     rax, cs:WPP_GLOBAL_Control
0x18003881f  lea     rcx, WPP_GLOBAL_Control
0x180038826  cmp     rax, rcx
0x180038829  jz      short loc_18003888B
0x18003882b  test    dword ptr [rax+1Ch], 800h
0x180038832  jz      short loc_18003888B
0x180038834  cmp     [rax+19h], r12b
0x180038838  jb      short loc_18003888B
0x18003883a  mov     edx, 2Ah ; '*'
0x18003883f  jmp     loc_180038634
0x180038844  mov     rdx, cs:WPP_GLOBAL_Control
0x18003884b  lea     rcx, WPP_GLOBAL_Control
0x180038852  cmp     rdx, rcx
0x180038855  jz      short loc_18003888B
0x180038857  test    dword ptr [rdx+1Ch], 800h
0x18003885e  jz      short loc_18003888B
0x180038860  cmp     byte ptr [rdx+19h], 1
0x180038864  jb      short loc_18003888B
0x180038866  mov     rcx, [rdx+10h]
0x18003886a  lea     rax, off_18004CD80; "SHA256"
0x180038871  mov     rax, [rax+r14*8]
0x180038875  mov     r9d, ebx
0x180038878  mov     [rsp+98h+var_68], esi
0x18003887c  mov     [rsp+98h+var_70], rbp
0x180038881  mov     [rsp+98h+var_78], rax
0x180038886  call    WPP_SF_DSqL
0x18003888b  mov     rcx, [rsp+98h+hHash]
0x180038890  call    ClCertDestroyHashHandle
0x180038895  test    ebx, ebx
0x180038897  jz      short loc_1800388A1
0x180038899  mov     rcx, r15
0x18003889c  call    ClCertFreeCertificateProperties
0x1800388a1  test    rdi, rdi
0x1800388a4  jz      short loc_1800388AF
0x1800388a6  mov     rcx, rdi; pCertContext
0x1800388a9  call    cs:__imp_CertFreeCertificateContext
0x1800388af  mov     eax, ebx
0x1800388b1  add     rsp, 58h
0x1800388b5  pop     r15
0x1800388b7  pop     r14
0x1800388b9  pop     r13
0x1800388bb  pop     r12
0x1800388bd  pop     rdi
0x1800388be  pop     rsi
0x1800388bf  pop     rbp
0x1800388c0  pop     rbx
0x1800388c1  retn
```
