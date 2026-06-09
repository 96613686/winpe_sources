# CreateIndirectData(SIP_SUBJECTINFO_ *,ulong *,SIP_INDIRECT_DATA_ *)

- ea: `0x1800093c0`
- end: `0x180009700`
- name: `?CreateIndirectData@@YAHPEAUSIP_SUBJECTINFO_@@PEAKPEAUSIP_INDIRECT_DATA_@@@Z`
- size: `832`
- prototype: `__int64 __fastcall(struct SIP_SUBJECTINFO_ *, unsigned int *, struct SIP_INDIRECT_DATA_ *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x180001220`
- `0x180001300`
- `0x180001940`
- `0x180001fd0`
- `0x1800021d0`
- `0x180002e40`
- `0x1800031f4`
- `0x180003200`
- `0x1800093c0`
- `0x1800098d0`
- `0x18000d172`
- `0x18000d1c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009436`
- `KERNEL32!GetLastError` at `0x18000947a`
- `KERNEL32!GetLastError` at `0x1800094bb`
- `KERNEL32!GetLastError` at `0x1800094e5`
- `KERNEL32!GetLastError` at `0x180009436`
- `KERNEL32!GetLastError` at `0x18000947a`
- `KERNEL32!GetLastError` at `0x1800094bb`
- `KERNEL32!GetLastError` at `0x1800094e5`
- `KERNEL32!SetLastError` at `0x1800096d1`
- `KERNEL32!SetLastError` at `0x1800096d1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800096b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800096c2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800096b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800096c2`
- `ADVAPI32!CryptReleaseContext` at `0x180009695`
- `ADVAPI32!CryptReleaseContext` at `0x180009695`
- `CRYPT32!CryptEncodeObject` at `0x180009565`
- `CRYPT32!CryptEncodeObject` at `0x1800095a4`
- `CRYPT32!CryptEncodeObject` at `0x180009565`
- `CRYPT32!CryptEncodeObject` at `0x1800095a4`

## pseudocode

```c
__int64 __fastcall CreateIndirectData(struct SIP_SUBJECTINFO_ *a1, unsigned int *a2, struct SIP_INDIRECT_DATA_ *a3)
{
  OLECHAR *v3; // r13
  OLECHAR *v4; // r15
  DWORD LastError; // esi
  void *v9; // r12
  unsigned int v10; // eax
  unsigned int v11; // esi
  DWORD v12; // eax
  DWORD v13; // eax
  OLECHAR *Insertion; // rax
  __int64 v15; // rax
  size_t v16; // rdx
  unsigned int v17; // ecx
  struct SIP_INDIRECT_DATA_ *v18; // rax
  char *v19; // rdi
  size_t v20; // rbx
  struct SIP_INDIRECT_DATA_ *v21; // rax
  DWORD v22; // ecx
  char *v23; // rdi
  __int64 v24; // rbx
  struct SIP_INDIRECT_DATA_ *v25; // r14
  char *v26; // rbx
  void *v27; // rdx
  size_t v28; // r8
  unsigned int v29; // ebx
  DWORD pcbEncoded; // [rsp+30h] [rbp-49h] BYREF
  size_t v32; // [rsp+34h] [rbp-45h] BYREF
  size_t Size; // [rsp+40h] [rbp-39h] BYREF
  BYTE *pbData; // [rsp+48h] [rbp-31h] BYREF
  struct SIP_INDIRECT_DATA_ *v35; // [rsp+50h] [rbp-29h]
  void *Src; // [rsp+58h] [rbp-21h] BYREF
  HCRYPTPROV v37; // [rsp+60h] [rbp-19h] BYREF
  HCRYPTPROV hProv; // [rsp+68h] [rbp-11h] BYREF
  _OWORD pvStructInfo[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v40; // [rsp+90h] [rbp+17h]

  v35 = a3;
  v37 = 0;
  v32 = 0;
  memset(pvStructInfo, 0, sizeof(pvStructInfo));
  v40 = 0;
  v3 = 0;
  pcbEncoded = 0;
  v4 = 0;
  Size = 0;
  pbData = 0;
  hProv = 0;
  Src = 0;
  if ( !(unsigned int)VerifySubjectInfo() )
  {
    LastError = GetLastError();
    goto LABEL_33;
  }
  if ( !a2 )
  {
    LastError = 87;
    goto LABEL_33;
  }
  v9 = 0;
  v10 = ClassifyGuid(a1->pgSubjectType);
  a1->dwIntVersion = 512;
  v11 = v10;
  if ( (unsigned int)GetProviderHandleFromSubject(a1, &v37, &hProv) )
  {
    memset(pvStructInfo, 0, sizeof(pvStructInfo));
    LODWORD(pvStructInfo[0]) = 1;
    v40 = 0;
    *(GUID *)((char *)pvStructInfo + 4) = *a1->pgSubjectType;
    if ( !(unsigned int)SubjectToBstr(a1, &Size) )
    {
      v12 = GetLastError();
      v3 = (OLECHAR *)Size;
      LastError = v12;
      goto LABEL_27;
    }
    v3 = (OLECHAR *)Size;
    if ( !(unsigned int)StripSignature((unsigned __int16 *)Size, v11, (OLECHAR **)&pbData, 0) )
    {
      v13 = GetLastError();
      v4 = (OLECHAR *)pbData;
      LastError = v13;
      goto LABEL_27;
    }
    v4 = (OLECHAR *)pbData;
    Insertion = FindInsertion(v11, (OLECHAR *)pbData);
    if ( !Insertion )
    {
      LastError = 11;
      goto LABEL_27;
    }
    if ( (unsigned int)HashFile(v4, Insertion - v4, v37, a1->DigestAlgorithm.pszObjId, (BYTE **)&Src, &v32) )
    {
      pcbEncoded = 0;
      if ( CryptEncodeObject(0x10001u, "1.3.6.1.4.1.311.2.1.30", pvStructInfo, 0, &pcbEncoded) )
      {
        v9 = operator new(pcbEncoded);
        if ( !v9 )
        {
          LastError = 8;
          goto LABEL_27;
        }
        if ( CryptEncodeObject(0x10001u, "1.3.6.1.4.1.311.2.1.30", pvStructInfo, (BYTE *)v9, &pcbEncoded) )
        {
          v15 = -1;
          do
            ++v15;
          while ( a1->DigestAlgorithm.pszObjId[v15] );
          v16 = pcbEncoded;
          LODWORD(Size) = v15 + 1;
          v17 = pcbEncoded + v15 + 1 + v32 + 87;
          if ( a3 && *a2 < v17 || v17 < 0x40 )
          {
            *a2 = v17;
            LastError = 122;
          }
          else
          {
            LastError = 0;
            *a2 = v17;
            if ( a3 )
            {
              v18 = v35;
              v19 = (char *)&a3[1];
              v20 = v16;
              strcpy(v19, "1.3.6.1.4.1.311.2.1.30");
              v18->Data.pszObjId = v19;
              v19 += 23;
              memcpy_0(v19, v9, v16);
              v21 = v35;
              v22 = pcbEncoded;
              v35->Data.Value.pbData = (BYTE *)v19;
              v23 = &v19[v20];
              v24 = (unsigned int)Size;
              v21->Data.Value.cbData = v22;
              memcpy_0(v23, a1->DigestAlgorithm.pszObjId, (unsigned int)v24);
              v25 = v35;
              v26 = &v23[v24];
              v27 = Src;
              v35->DigestAlgorithm.pszObjId = v23;
              LODWORD(v23) = v32;
              v28 = (unsigned int)v32;
              v25->DigestAlgorithm.Parameters.cbData = 0;
              v25->DigestAlgorithm.Parameters.pbData = 0;
              memcpy_0(v26, v27, v28);
              v25->Digest.pbData = (BYTE *)v26;
              v25->Digest.cbData = (unsigned int)v23;
            }
            HIDWORD(v32) = 1;
          }
          goto LABEL_27;
        }
      }
    }
  }
  LastError = GetLastError();
LABEL_27:
  if ( hProv )
    CryptReleaseContext(hProv, 0);
  if ( Src )
    operator delete(Src);
  if ( v9 )
    operator delete(v9);
LABEL_33:
  SysFreeString(v3);
  SysFreeString(v4);
  v29 = HIDWORD(v32);
  if ( !HIDWORD(v32) )
    SetLastError(LastError);
  return v29;
}

```

## disassembly

```asm
0x1800093c0  mov     [rsp-8+arg_18], rbx
0x1800093c5  push    rbp
0x1800093c6  push    rsi
0x1800093c7  push    rdi
0x1800093c8  push    r12
0x1800093ca  push    r13
0x1800093cc  push    r14
0x1800093ce  push    r15
0x1800093d0  lea     rbp, [rsp-27h]
0x1800093d5  sub     rsp, 0A0h
0x1800093dc  mov     rax, cs:__security_cookie
0x1800093e3  xor     rax, rsp
0x1800093e6  mov     [rbp+57h+var_38], rax
0x1800093ea  xor     esi, esi
0x1800093ec  mov     [rbp+57h+var_80], r8
0x1800093f0  xorps   xmm0, xmm0
0x1800093f3  mov     [rbp+57h+var_70], rsi
0x1800093f7  xor     eax, eax
0x1800093f9  mov     dword ptr [rbp+57h+var_9C], esi
0x1800093fc  movups  [rbp+57h+pvStructInfo], xmm0
0x180009400  mov     [rbp+57h+var_40], rax
0x180009404  mov     r13d, esi
0x180009407  movups  [rbp+57h+var_50], xmm0
0x18000940b  mov     [rbp+57h+var_A0], esi
0x18000940e  mov     r15d, esi
0x180009411  mov     [rbp+57h+Size], rsi
0x180009415  mov     rdi, r8
0x180009418  mov     [rbp+57h+pbData], rsi
0x18000941c  mov     rbx, rdx
0x18000941f  mov     [rbp+57h+hProv], rsi
0x180009423  mov     r14, rcx
0x180009426  mov     [rbp+57h+Src], rsi
0x18000942a  mov     dword ptr [rbp+57h+var_9C+4], esi
0x18000942d  call    VerifySubjectInfo
0x180009432  test    eax, eax
0x180009434  jnz     short loc_180009443
0x180009436  call    cs:__imp_GetLastError
0x18000943c  mov     esi, eax
0x18000943e  jmp     loc_1800096B6
0x180009443  test    rbx, rbx
0x180009446  jnz     short loc_180009450
0x180009448  lea     esi, [rbx+57h]
0x18000944b  jmp     loc_1800096B6
0x180009450  mov     rcx, [r14+8]
0x180009454  mov     r12, rsi
0x180009457  call    ClassifyGuid
0x18000945c  lea     rdx, [rbp+57h+var_70]
0x180009460  mov     dword ptr [r14+2Ch], 200h
0x180009468  mov     rcx, r14
0x18000946b  lea     r8, [rbp+57h+hProv]
0x18000946f  mov     esi, eax
0x180009471  call    GetProviderHandleFromSubject
0x180009476  test    eax, eax
0x180009478  jnz     short loc_180009487
0x18000947a  call    cs:__imp_GetLastError
0x180009480  mov     esi, eax
0x180009482  jmp     loc_18000968A
0x180009487  xorps   xmm0, xmm0
0x18000948a  lea     rdx, [rbp+57h+Size]
0x18000948e  movups  [rbp+57h+pvStructInfo], xmm0
0x180009492  xor     eax, eax
0x180009494  mov     dword ptr [rbp+57h+pvStructInfo], 1
0x18000949b  mov     [rbp+57h+var_40], rax
0x18000949f  mov     rcx, r14
0x1800094a2  mov     rax, [r14+8]
0x1800094a6  movups  [rbp+57h+var_50], xmm0
0x1800094aa  movups  xmm0, xmmword ptr [rax]
0x1800094ad  movdqu  [rbp+57h+pvStructInfo+4], xmm0
0x1800094b2  call    SubjectToBstr
0x1800094b7  test    eax, eax
0x1800094b9  jnz     short loc_1800094CC
0x1800094bb  call    cs:__imp_GetLastError
0x1800094c1  mov     r13, [rbp+57h+Size]
0x1800094c5  mov     esi, eax
0x1800094c7  jmp     loc_18000968A
0x1800094cc  mov     r13, [rbp+57h+Size]
0x1800094d0  lea     r8, [rbp+57h+pbData]
0x1800094d4  mov     rcx, r13; unsigned __int16 *
0x1800094d7  xor     r9d, r9d
0x1800094da  mov     edx, esi
0x1800094dc  call    StripSignature
0x1800094e1  test    eax, eax
0x1800094e3  jnz     short loc_1800094F6
0x1800094e5  call    cs:__imp_GetLastError
0x1800094eb  mov     r15, [rbp+57h+pbData]
0x1800094ef  mov     esi, eax
0x1800094f1  jmp     loc_18000968A
0x1800094f6  mov     r15, [rbp+57h+pbData]
0x1800094fa  mov     ecx, esi
0x1800094fc  mov     rdx, r15
0x1800094ff  call    FindInsertion
0x180009504  test    rax, rax
0x180009507  jnz     short loc_180009511
0x180009509  lea     esi, [rax+0Bh]
0x18000950c  jmp     loc_18000968A
0x180009511  mov     r9, [r14+38h]
0x180009515  lea     rcx, [rbp+57h+var_9C]
0x180009519  mov     r8, [rbp+57h+var_70]
0x18000951d  sub     rax, r15
0x180009520  mov     [rsp+0D0h+var_A8], rcx; __int64
0x180009525  lea     rcx, [rbp+57h+Src]
0x180009529  sar     rax, 1
0x18000952c  mov     [rsp+0D0h+pcbEncoded], rcx; __int64
0x180009531  mov     edx, eax
0x180009533  mov     rcx, r15; pbData
0x180009536  call    HashFile
0x18000953b  test    eax, eax
0x18000953d  jz      loc_18000947A
0x180009543  lea     rax, [rbp+57h+var_A0]
0x180009547  mov     [rbp+57h+var_A0], r12d
0x18000954b  mov     esi, 10001h
0x180009550  mov     [rsp+0D0h+pcbEncoded], rax; pcbEncoded
0x180009555  mov     ecx, esi; dwCertEncodingType
0x180009557  lea     r8, [rbp+57h+pvStructInfo]; pvStructInfo
0x18000955b  xor     r9d, r9d; pbEncoded
0x18000955e  lea     rdx, szStructType; "1.3.6.1.4.1.311.2.1.30"
0x180009565  call    cs:__imp_CryptEncodeObject
0x18000956b  test    eax, eax
0x18000956d  jz      loc_18000947A
0x180009573  mov     ecx, [rbp+57h+var_A0]; Size
0x180009576  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000957b  mov     r12, rax
0x18000957e  test    rax, rax
0x180009581  jnz     short loc_18000958B
0x180009583  lea     esi, [rax+8]
0x180009586  jmp     loc_18000968A
0x18000958b  lea     rax, [rbp+57h+var_A0]
0x18000958f  mov     r9, r12; pbEncoded
0x180009592  lea     r8, [rbp+57h+pvStructInfo]; pvStructInfo
0x180009596  mov     [rsp+0D0h+pcbEncoded], rax; pcbEncoded
0x18000959b  lea     rdx, szStructType; "1.3.6.1.4.1.311.2.1.30"
0x1800095a2  mov     ecx, esi; dwCertEncodingType
0x1800095a4  call    cs:__imp_CryptEncodeObject
0x1800095aa  test    eax, eax
0x1800095ac  jz      loc_18000947A
0x1800095b2  mov     rcx, [r14+38h]
0x1800095b6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800095ba  inc     rax
0x1800095bd  cmp     byte ptr [rcx+rax], 0
0x1800095c1  jnz     short loc_1800095BA
0x1800095c3  mov     edx, [rbp+57h+var_A0]
0x1800095c6  inc     eax
0x1800095c8  mov     ecx, dword ptr [rbp+57h+var_9C]
0x1800095cb  add     ecx, 57h ; 'W'
0x1800095ce  mov     dword ptr [rbp+57h+Size], eax
0x1800095d1  add     eax, edx
0x1800095d3  add     ecx, eax
0x1800095d5  test    rdi, rdi
0x1800095d8  jz      short loc_1800095DE
0x1800095da  cmp     [rbx], ecx
0x1800095dc  jb      short loc_1800095E3
0x1800095de  cmp     ecx, 40h ; '@'
0x1800095e1  jnb     short loc_1800095EF
0x1800095e3  mov     [rbx], ecx
0x1800095e5  mov     esi, 7Ah ; 'z'
0x1800095ea  jmp     loc_18000968A
0x1800095ef  xor     esi, esi
0x1800095f1  mov     [rbx], ecx
0x1800095f3  test    rdi, rdi
0x1800095f6  jz      loc_180009683
0x1800095fc  movups  xmm0, xmmword ptr cs:szStructType; "1.3.6.1.4.1.311.2.1.30"
0x180009603  mov     rax, [rbp+57h+var_80]
0x180009607  add     rdi, 40h ; '@'
0x18000960b  mov     rbx, rdx
0x18000960e  mov     r8, rdx; Size
0x180009611  mov     rdx, r12; Src
0x180009614  movups  xmmword ptr [rdi], xmm0
0x180009617  movsd   xmm1, qword ptr cs:szStructType+0Fh; ".2.1.30"
0x18000961f  movsd   qword ptr [rdi+0Fh], xmm1
0x180009624  mov     [rax], rdi
0x180009627  add     rdi, 17h
0x18000962b  mov     rcx, rdi; void *
0x18000962e  call    memcpy_0
0x180009633  mov     rax, [rbp+57h+var_80]
0x180009637  mov     ecx, [rbp+57h+var_A0]
0x18000963a  mov     [rax+10h], rdi
0x18000963e  add     rdi, rbx
0x180009641  mov     ebx, dword ptr [rbp+57h+Size]
0x180009644  mov     [rax+8], ecx
0x180009647  mov     r8d, ebx; Size
0x18000964a  mov     rdx, [r14+38h]; Src
0x18000964e  mov     rcx, rdi; void *
0x180009651  call    memcpy_0
0x180009656  mov     r14, [rbp+57h+var_80]
0x18000965a  add     rbx, rdi
0x18000965d  mov     rdx, [rbp+57h+Src]; Src
0x180009661  mov     rcx, rbx; void *
0x180009664  mov     [r14+18h], rdi
0x180009668  mov     edi, dword ptr [rbp+57h+var_9C]
0x18000966b  mov     r8d, edi; Size
0x18000966e  mov     [r14+20h], esi
0x180009672  mov     [r14+28h], rsi
0x180009676  call    memcpy_0
0x18000967b  mov     [r14+38h], rbx
0x18000967f  mov     [r14+30h], edi
0x180009683  mov     dword ptr [rbp+57h+var_9C+4], 1
0x18000968a  mov     rcx, [rbp+57h+hProv]; hProv
0x18000968e  test    rcx, rcx
0x180009691  jz      short loc_18000969B
0x180009693  xor     edx, edx; dwFlags
0x180009695  call    cs:__imp_CryptReleaseContext
0x18000969b  mov     rcx, [rbp+57h+Src]; Block
0x18000969f  test    rcx, rcx
0x1800096a2  jz      short loc_1800096A9
0x1800096a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800096a9  test    r12, r12
0x1800096ac  jz      short loc_1800096B6
0x1800096ae  mov     rcx, r12; Block
0x1800096b1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800096b6  mov     rcx, r13; bstrString
0x1800096b9  call    cs:__imp_SysFreeString
0x1800096bf  mov     rcx, r15; bstrString
0x1800096c2  call    cs:__imp_SysFreeString
0x1800096c8  mov     ebx, dword ptr [rbp+57h+var_9C+4]
0x1800096cb  test    ebx, ebx
0x1800096cd  jnz     short loc_1800096D7
0x1800096cf  mov     ecx, esi; dwErrCode
0x1800096d1  call    cs:__imp_SetLastError
0x1800096d7  mov     eax, ebx
0x1800096d9  mov     rcx, [rbp+57h+var_38]
0x1800096dd  xor     rcx, rsp; StackCookie
0x1800096e0  call    __security_check_cookie
0x1800096e5  mov     rbx, [rsp+0D0h+arg_18]
0x1800096ed  add     rsp, 0A0h
0x1800096f4  pop     r15
0x1800096f6  pop     r14
0x1800096f8  pop     r13
0x1800096fa  pop     r12
0x1800096fc  pop     rdi
0x1800096fd  pop     rsi
0x1800096fe  pop     rbp
0x1800096ff  retn
```
