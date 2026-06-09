# CGroupPolicy::ProcessGPForDevices(int *)

- ea: `0x1800106e0`
- end: `0x180010bb8`
- name: `?ProcessGPForDevices@CGroupPolicy@@IEAAXPEAH@Z`
- size: `1240`
- prototype: `void __fastcall(CGroupPolicy *__hidden this, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800069d0`

## callees

- `0x180001730`
- `0x180002fa0`
- `0x1800059d0`
- `0x180007160`
- `0x1800097d0`
- `0x18000eda4`
- `0x18000f390`
- `0x1800106e0`
- `0x1800154fc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010850`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010b3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010b47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010b50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010850`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010b3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010b47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010b50`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180010813`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180010813`

## string_xrefs

- `0x180010b74`: `Access Code`

## pseudocode

```c
void __fastcall CGroupPolicy::ProcessGPForDevices(CGroupPolicy *this, int *a2)
{
  _QWORD *v3; // r12
  __int64 v4; // rdx
  void *v5; // rcx
  __int64 *v6; // r12
  int *v7; // r15
  bool v8; // zf
  __m128i v9; // xmm1
  unsigned __int64 v10; // xmm0_8
  CGroupPolicy *v11; // rcx
  int v12; // ebx
  BOOL v13; // eax
  CGroupPolicy *v14; // rcx
  HLOCAL *v15; // rbx
  HLOCAL *v16; // rsi
  HLOCAL *v17; // rdi
  int v18; // [rsp+28h] [rbp-D8h]
  ULONG StringSecurityDescriptorLen; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR StringSecurityDescriptor[2]; // [rsp+78h] [rbp-88h] BYREF
  int *v21; // [rsp+88h] [rbp-78h]
  unsigned __int16 v22[64]; // [rsp+90h] [rbp-70h] BYREF

  AccessCode = 1;
  v3 = (_QWORD *)*((_QWORD *)this + 1);
  v21 = a2;
  while ( v3 )
  {
    v22[0] = 0;
    StringSecurityDescriptor[0] = 0;
    StringSecurityDescriptorLen = 0;
    if ( (unsigned int)*(_QWORD *)((char *)v3 + 28) )
    {
      StringCchPrintfW(v22, 0x40u, L"%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x");
      v5 = (void *)v3[2];
      if ( v5 )
      {
        if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
               v5,
               1u,
               4u,
               StringSecurityDescriptor,
               &StringSecurityDescriptorLen) )
        {
          WPDLibSetRegistryValue(
            0,
            a2,
            L"SYSTEM\\CurrentControlSet\\Control\\Storage\\Test",
            v22,
            1,
            StringSecurityDescriptor[0],
            2 * StringSecurityDescriptorLen);
          LocalFree(StringSecurityDescriptor[0]);
        }
      }
      else
      {
        WPDLibDeleteRegistryValue(0, v4, L"SYSTEM\\CurrentControlSet\\Control\\Storage\\Test", v22);
      }
    }
    v3 = (_QWORD *)*v3;
  }
  v6 = (__int64 *)*((_QWORD *)this + 1);
  if ( v6 )
  {
    v7 = v21;
    do
    {
      v8 = *((_DWORD *)v6 + 12) == 0;
      v9 = *(__m128i *)((char *)v6 + 28);
      *(__m128i *)StringSecurityDescriptor = v9;
      if ( v8 )
      {
        GPDebugPrintX(
          8u,
          "Will NOT enumerate GUID {%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}\n",
          v9.m128i_i32[0],
          _mm_extract_epi16(v9, 2),
          _mm_extract_epi16(v9, 3),
          _mm_srli_si128(v9, 8).m128i_u8[0],
          (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v9, 9)),
          (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v9, 10)),
          (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v9, 11)),
          (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v9, 12)),
          (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v9, 13)),
          (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v9, 14)),
          (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v9, 15)));
        if ( !memcmp_0(StringSecurityDescriptor, &GUID_DEVINTERFACE_WPD, 0x10u) && !*((_DWORD *)v6 + 15) )
          CGroupPolicy::ApplyGroupPolicyForDevices(
            v14,
            (struct _GUID *)StringSecurityDescriptor,
            (struct _ACL *)v6[1],
            (void *)v6[2],
            *((_DWORD *)v6 + 6),
            1,
            *((_DWORD *)v6 + 13),
            0,
            v7);
      }
      else
      {
        v10 = _mm_srli_si128(v9, 8).m128i_u64[0];
        GPDebugPrintX(
          8u,
          "Will enumerate GUID {%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}\n",
          _mm_cvtsi128_si32(v9),
          v9.m128i_u16[2],
          HIWORD(v9.m128i_i64[0]),
          (unsigned __int8)v10,
          BYTE1(v10),
          BYTE2(v10),
          BYTE3(v10),
          BYTE4(v10),
          BYTE5(v10),
          BYTE6(v10),
          HIBYTE(v10));
        if ( !memcmp_0(StringSecurityDescriptor, &GUID_DEVINTERFACE_VOLUME, 0x10u) )
        {
          v7 = v21;
          CGroupPolicy::ApplyGroupPolicyForDiskDevices(
            v11,
            (struct _ACL *)v6[1],
            (void *)v6[2],
            *((_DWORD *)v6 + 6),
            v21,
            v18,
            *((_DWORD *)v6 + 14));
        }
        else
        {
          v12 = *((_DWORD *)v6 + 13);
          v13 = !*((_DWORD *)v6 + 15) && !memcmp_0(StringSecurityDescriptor, &GUID_DEVINTERFACE_WPD, 0x10u);
          v7 = v21;
          CGroupPolicy::ApplyGroupPolicyForDevices(
            v11,
            (struct _GUID *)StringSecurityDescriptor,
            (struct _ACL *)v6[1],
            (void *)v6[2],
            *((_DWORD *)v6 + 6),
            v13,
            v12,
            1,
            v21);
        }
      }
      v6 = (__int64 *)*v6;
    }
    while ( v6 );
  }
  v15 = (HLOCAL *)*((_QWORD *)this + 1);
  v16 = 0;
  while ( v15 )
  {
    v17 = v15;
    v15 = (HLOCAL *)*v15;
    if ( v17[1] || v17[2] )
    {
      v16 = v17;
    }
    else
    {
      if ( v17 == *((HLOCAL **)this + 1) )
      {
        *((_QWORD *)this + 1) = v15;
      }
      else if ( v16 )
      {
        *v16 = v15;
      }
      LocalFree(v17[1]);
      LocalFree(v17[2]);
      LocalFree(v17);
    }
  }
  WPDLibSetRegistryValue(0, a2, L"SYSTEM\\CurrentControlSet\\Control\\Storage\\Test", L"Access Code", 4, &AccessCode, 4);
}

```

## disassembly

```asm
0x1800106e0  mov     [rsp-8+arg_10], rbx
0x1800106e5  push    rbp
0x1800106e6  push    rsi
0x1800106e7  push    rdi
0x1800106e8  push    r12
0x1800106ea  push    r13
0x1800106ec  push    r14
0x1800106ee  push    r15
0x1800106f0  lea     rbp, [rsp-20h]
0x1800106f5  sub     rsp, 120h
0x1800106fc  mov     rax, cs:__security_cookie
0x180010703  xor     rax, rsp
0x180010706  mov     [rbp+50h+var_40], rax
0x18001070a  mov     cs:?AccessCode@@3KA, 1; ulong AccessCode
0x180010714  mov     r13, rcx
0x180010717  mov     r12, [rcx+8]
0x18001071b  mov     [rbp+50h+var_C8], rdx
0x18001071f  test    r12, r12
0x180010722  jz      loc_180010871
0x180010728  xor     eax, eax
0x18001072a  mov     [rbp+50h+var_C0], ax
0x18001072e  mov     [rsp+150h+StringSecurityDescriptor], rax
0x180010733  mov     [rsp+150h+var_E0], eax
0x180010737  movups  xmm0, xmmword ptr [r12+1Ch]
0x18001073d  movq    r9, xmm0
0x180010742  test    r9d, r9d
0x180010745  jz      loc_180010868
0x18001074b  psrldq  xmm0, 8
0x180010750  mov     r10, r9
0x180010753  movq    rcx, xmm0
0x180010758  shr     r10, 30h
0x18001075c  mov     rax, rcx
0x18001075f  movzx   r8d, cl
0x180010763  shr     rax, 30h
0x180010767  mov     r15, rcx
0x18001076a  movzx   r14d, al
0x18001076e  mov     rax, rcx
0x180010771  shr     rax, 28h
0x180010775  movzx   esi, al
0x180010778  mov     rax, rcx
0x18001077b  shr     rax, 20h
0x18001077f  movzx   edi, al
0x180010782  mov     rax, rcx
0x180010785  shr     rax, 18h
0x180010789  movzx   ebx, al
0x18001078c  mov     rax, rcx
0x18001078f  shr     rax, 10h
0x180010793  movzx   r11d, al
0x180010797  mov     rax, rcx
0x18001079a  shr     rax, 8
0x18001079e  movzx   edx, al
0x1800107a1  mov     rax, r9
0x1800107a4  shr     rax, 20h
0x1800107a8  movzx   ecx, ax
0x1800107ab  shr     r15, 38h
0x1800107af  mov     [rsp+150h+var_E8], r15d
0x1800107b4  mov     [rsp+150h+var_F0], r14d
0x1800107b9  mov     [rsp+150h+var_F8], esi
0x1800107bd  mov     [rsp+150h+var_100], edi
0x1800107c1  mov     [rsp+150h+var_108], ebx
0x1800107c5  mov     dword ptr [rsp+150h+var_110], r11d
0x1800107ca  mov     [rsp+150h+var_118], edx
0x1800107ce  mov     edx, 40h ; '@'; unsigned __int64
0x1800107d3  mov     [rsp+150h+var_120], r8d
0x1800107d8  lea     r8, a08x04x04x02x02_0; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x1800107df  mov     [rsp+150h+var_128], r10d
0x1800107e4  mov     dword ptr [rsp+150h+StringSecurityDescriptorLen], ecx
0x1800107e8  lea     rcx, [rbp+50h+var_C0]; unsigned __int16 *
0x1800107ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800107f1  mov     rcx, [r12+10h]; SecurityDescriptor
0x1800107f6  test    rcx, rcx
0x1800107f9  jz      short loc_180010858
0x1800107fb  mov     edx, 1; RequestedStringSDRevision
0x180010800  lea     rax, [rsp+150h+var_E0]
0x180010805  lea     r9, [rsp+150h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18001080a  mov     [rsp+150h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x18001080f  lea     r8d, [rdx+3]; SecurityInformation
0x180010813  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180010819  test    eax, eax
0x18001081b  jz      short loc_180010868
0x18001081d  mov     eax, [rsp+150h+var_E0]
0x180010821  lea     r9, [rbp+50h+var_C0]
0x180010825  add     eax, eax
0x180010827  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Sto"...
0x18001082e  mov     [rsp+150h+var_120], eax
0x180010832  xor     ecx, ecx
0x180010834  mov     rax, [rsp+150h+StringSecurityDescriptor]
0x180010839  mov     qword ptr [rsp+150h+var_128], rax
0x18001083e  mov     dword ptr [rsp+150h+StringSecurityDescriptorLen], 1
0x180010846  call    WPDLibSetRegistryValue
0x18001084b  mov     rcx, [rsp+150h+StringSecurityDescriptor]; hMem
0x180010850  call    cs:__imp_LocalFree
0x180010856  jmp     short loc_180010868
0x180010858  lea     r9, [rbp+50h+var_C0]
0x18001085c  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Sto"...
0x180010863  call    WPDLibDeleteRegistryValue
0x180010868  mov     r12, [r12]
0x18001086c  jmp     loc_18001071F
0x180010871  mov     r12, [r13+8]
0x180010875  test    r12, r12
0x180010878  jz      loc_180010B09
0x18001087e  mov     r15, [rbp+50h+var_C8]
0x180010882  cmp     dword ptr [r12+30h], 0
0x180010888  movups  xmm1, xmmword ptr [r12+1Ch]
0x18001088e  movups  xmmword ptr [rsp+150h+StringSecurityDescriptor], xmm1
0x180010893  movdqa  xmm0, xmm1
0x180010897  jz      loc_1800109D9
0x18001089d  psrldq  xmm0, 8
0x1800108a2  movq    rcx, xmm0
0x1800108a7  movzx   r8d, cl
0x1800108ab  mov     rax, rcx
0x1800108ae  shr     rax, 30h
0x1800108b2  mov     r15, rcx
0x1800108b5  movzx   r14d, al
0x1800108b9  mov     rax, rcx
0x1800108bc  shr     rax, 28h
0x1800108c0  movzx   esi, al
0x1800108c3  mov     rax, rcx
0x1800108c6  shr     rax, 20h
0x1800108ca  movzx   edi, al
0x1800108cd  mov     rax, rcx
0x1800108d0  shr     rax, 18h
0x1800108d4  movzx   ebx, al
0x1800108d7  mov     rax, rcx
0x1800108da  shr     rax, 10h
0x1800108de  movzx   r11d, al
0x1800108e2  mov     rax, rcx
0x1800108e5  shr     rax, 8
0x1800108e9  movq    rcx, xmm1
0x1800108ee  movzx   edx, al
0x1800108f1  movq    rax, xmm1
0x1800108f6  shr     rcx, 30h
0x1800108fa  shr     rax, 20h
0x1800108fe  shr     r15, 38h
0x180010902  mov     [rsp+150h+var_F0], r15d
0x180010907  mov     [rsp+150h+var_F8], r14d
0x18001090c  mov     [rsp+150h+var_100], esi
0x180010910  mov     [rsp+150h+var_108], edi
0x180010914  mov     dword ptr [rsp+150h+var_110], ebx
0x180010918  mov     [rsp+150h+var_118], r11d
0x18001091d  mov     [rsp+150h+var_120], edx
0x180010921  lea     rdx, aWillEnumerateG; "Will enumerate GUID {%08x-%04x-%04x-%02"...
0x180010928  mov     [rsp+150h+var_128], r8d; int
0x18001092d  mov     dword ptr [rsp+150h+StringSecurityDescriptorLen], ecx
0x180010931  mov     ecx, 8; unsigned int
0x180010936  movd    r8d, xmm1
0x18001093b  movzx   r9d, ax
0x18001093f  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180010944  mov     r8d, 10h; Size
0x18001094a  lea     rdx, GUID_DEVINTERFACE_VOLUME; Buf2
0x180010951  lea     rcx, [rsp+150h+StringSecurityDescriptor]; Buf1
0x180010956  call    memcmp_0
0x18001095b  test    eax, eax
0x18001095d  jnz     short loc_18001098A
0x18001095f  mov     eax, [r12+38h]
0x180010964  mov     r15, [rbp+50h+var_C8]
0x180010968  mov     r9d, [r12+18h]; unsigned int
0x18001096d  mov     r8, [r12+10h]; void *
0x180010972  mov     rdx, [r12+8]; struct _ACL *
0x180010977  mov     [rsp+150h+var_120], eax; int
0x18001097b  mov     [rsp+150h+StringSecurityDescriptorLen], r15; int *
0x180010980  call    ?ApplyGroupPolicyForDiskDevices@CGroupPolicy@@IEAAXPEAU_ACL@@PEAXKPEAHHH@Z; CGroupPolicy::ApplyGroupPolicyForDiskDevices(_ACL *,void *,ulong,int *,int,int)
0x180010985  jmp     loc_180010AFC
0x18001098a  cmp     dword ptr [r12+3Ch], 0
0x180010990  mov     ebx, [r12+34h]
0x180010995  jnz     short loc_1800109B9
0x180010997  mov     r8d, 10h; Size
0x18001099d  lea     rdx, GUID_DEVINTERFACE_WPD; Buf2
0x1800109a4  lea     rcx, [rsp+150h+StringSecurityDescriptor]; Buf1
0x1800109a9  call    memcmp_0
0x1800109ae  test    eax, eax
0x1800109b0  jnz     short loc_1800109B9
0x1800109b2  mov     eax, 1
0x1800109b7  jmp     short loc_1800109BB
0x1800109b9  xor     eax, eax
0x1800109bb  mov     r15, [rbp+50h+var_C8]
0x1800109bf  mov     [rsp+150h+var_110], r15
0x1800109c4  mov     [rsp+150h+var_118], 1
0x1800109cc  mov     [rsp+150h+var_120], ebx
0x1800109d0  mov     [rsp+150h+var_128], eax
0x1800109d4  jmp     loc_180010ADF
0x1800109d9  psrldq  xmm0, 0Fh
0x1800109de  movd    eax, xmm0
0x1800109e2  movdqa  xmm0, xmm1
0x1800109e6  psrldq  xmm0, 0Eh
0x1800109eb  pextrw  ecx, xmm1, 3
0x1800109f0  movzx   r14d, al
0x1800109f4  movd    eax, xmm0
0x1800109f8  movdqa  xmm0, xmm1
0x1800109fc  psrldq  xmm0, 0Dh
0x180010a01  mov     [rsp+150h+var_F0], r14d
0x180010a06  movzx   esi, al
0x180010a09  movd    eax, xmm0
0x180010a0d  movdqa  xmm0, xmm1
0x180010a11  psrldq  xmm0, 0Ch
0x180010a16  mov     [rsp+150h+var_F8], esi
0x180010a1a  movzx   edi, al
0x180010a1d  movd    eax, xmm0
0x180010a21  movdqa  xmm0, xmm1
0x180010a25  psrldq  xmm0, 0Bh
0x180010a2a  mov     [rsp+150h+var_100], edi
0x180010a2e  movzx   ebx, al
0x180010a31  movd    eax, xmm0
0x180010a35  movdqa  xmm0, xmm1
0x180010a39  psrldq  xmm0, 0Ah
0x180010a3e  mov     [rsp+150h+var_108], ebx
0x180010a42  movzx   r11d, al
0x180010a46  movd    eax, xmm0
0x180010a4a  movdqa  xmm0, xmm1
0x180010a4e  mov     dword ptr [rsp+150h+var_110], r11d
0x180010a53  psrldq  xmm0, 9
0x180010a58  movzx   r10d, al
0x180010a5c  movd    eax, xmm0
0x180010a60  movdqa  xmm0, xmm1
0x180010a64  mov     [rsp+150h+var_118], r10d
0x180010a69  psrldq  xmm0, 8
0x180010a6e  movzx   r8d, al
0x180010a72  movq    rax, xmm0
0x180010a77  mov     [rsp+150h+var_120], r8d
0x180010a7c  movq    r8, xmm1
0x180010a81  movzx   edx, al
0x180010a84  mov     [rsp+150h+var_128], edx
0x180010a88  lea     rdx, aWillNotEnumera; "Will NOT enumerate GUID {%08x-%04x-%04x"...
0x180010a8f  mov     dword ptr [rsp+150h+StringSecurityDescriptorLen], ecx
0x180010a93  mov     ecx, 8; unsigned int
0x180010a98  pextrw  r9d, xmm1, 2
0x180010a9e  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180010aa3  mov     r8d, 10h; Size
0x180010aa9  lea     rdx, GUID_DEVINTERFACE_WPD; Buf2
0x180010ab0  lea     rcx, [rsp+150h+StringSecurityDescriptor]; Buf1
0x180010ab5  call    memcmp_0
0x180010aba  test    eax, eax
0x180010abc  jnz     short loc_180010AFC
0x180010abe  cmp     [r12+3Ch], eax
0x180010ac3  jnz     short loc_180010AFC
0x180010ac5  mov     [rsp+150h+var_110], r15; int *
0x180010aca  mov     [rsp+150h+var_118], eax; int
0x180010ace  mov     eax, [r12+34h]
0x180010ad3  mov     [rsp+150h+var_120], eax; int
0x180010ad7  mov     [rsp+150h+var_128], 1; int
0x180010adf  mov     eax, [r12+18h]
0x180010ae4  lea     rdx, [rsp+150h+StringSecurityDescriptor]; struct _GUID *
0x180010ae9  mov     r9, [r12+10h]; void *
0x180010aee  mov     r8, [r12+8]; struct _ACL *
0x180010af3  mov     dword ptr [rsp+150h+StringSecurityDescriptorLen], eax; unsigned int
0x180010af7  call    ?ApplyGroupPolicyForDevices@CGroupPolicy@@IEAAXPEAU_GUID@@PEAU_ACL@@PEAXKHHHPEAH@Z; CGroupPolicy::ApplyGroupPolicyForDevices(_GUID *,_ACL *,void *,ulong,int,int,int,int *)
0x180010afc  mov     r12, [r12]
0x180010b00  test    r12, r12
0x180010b03  jnz     loc_180010882
0x180010b09  mov     rbx, [r13+8]
0x180010b0d  xor     esi, esi
0x180010b0f  jmp     short loc_180010B5B
0x180010b11  mov     rdi, rbx
0x180010b14  mov     rbx, [rbx]
0x180010b17  cmp     qword ptr [rdi+8], 0
0x180010b1c  jnz     short loc_180010B58
0x180010b1e  cmp     qword ptr [rdi+10h], 0
0x180010b23  jnz     short loc_180010B58
0x180010b25  cmp     rdi, [r13+8]
0x180010b29  jnz     short loc_180010B31
0x180010b2b  mov     [r13+8], rbx
0x180010b2f  jmp     short loc_180010B39
0x180010b31  test    rsi, rsi
0x180010b34  jz      short loc_180010B39
0x180010b36  mov     [rsi], rbx
0x180010b39  mov     rcx, [rdi+8]; hMem
0x180010b3d  call    cs:__imp_LocalFree
0x180010b43  mov     rcx, [rdi+10h]; hMem
0x180010b47  call    cs:__imp_LocalFree
0x180010b4d  mov     rcx, rdi; hMem
0x180010b50  call    cs:__imp_LocalFree
0x180010b56  jmp     short loc_180010B5B
0x180010b58  mov     rsi, rdi
0x180010b5b  test    rbx, rbx
0x180010b5e  jnz     short loc_180010B11
0x180010b60  lea     rax, ?AccessCode@@3KA; ulong AccessCode
0x180010b67  mov     [rsp+150h+var_120], 4
0x180010b6f  mov     qword ptr [rsp+150h+var_128], rax
0x180010b74  lea     r9, aAccessCode; "Access Code"
0x180010b7b  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Sto"...
0x180010b82  mov     dword ptr [rsp+150h+StringSecurityDescriptorLen], 4
0x180010b8a  xor     ecx, ecx
0x180010b8c  call    WPDLibSetRegistryValue
0x180010b91  mov     rcx, [rbp+50h+var_40]
0x180010b95  xor     rcx, rsp; StackCookie
0x180010b98  call    __security_check_cookie
0x180010b9d  mov     rbx, [rsp+150h+arg_10]
0x180010ba5  add     rsp, 120h
0x180010bac  pop     r15
0x180010bae  pop     r14
0x180010bb0  pop     r13
0x180010bb2  pop     r12
0x180010bb4  pop     rdi
0x180010bb5  pop     rsi
0x180010bb6  pop     rbp
0x180010bb7  retn
```
