# CLocalAccounts::GetAt(ulong,IPropertyStore * *)

- ea: `0x180005f40`
- end: `0x18000639b`
- name: `?GetAt@CLocalAccounts@@UEAAJKPEAPEAUIPropertyStore@@@Z`
- size: `1115`
- prototype: `__int64 __fastcall(CLocalAccounts *__hidden this, unsigned int, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005f40`
- `0x18000c240`
- `0x180012f18`
- `0x180013130`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006095`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006095`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061fe`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000607f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800061e8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000607f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800061e8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000604f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006071`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800061b2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800061d6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000604f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006071`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800061b2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800061d6`
- `ntdll!RtlSubAuthoritySid` at `0x18000619f`
- `ntdll!RtlSubAuthoritySid` at `0x18000619f`
- `ntdll!RtlInitializeSid` at `0x180006190`
- `ntdll!RtlInitializeSid` at `0x180006190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000608c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800061f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000633d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000636a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000608c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800061f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000633d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000636a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800061ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006268`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800061ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006268`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180006007`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180006007`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800060ba`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800060e6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180006124`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800060ba`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800060e6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180006124`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180006026`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180006026`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800060af`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800060db`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800060af`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800060db`

## pseudocode

```c
__int64 __fastcall CLocalAccounts::GetAt(CLocalAccounts *this, unsigned int a2, struct IPropertyStore **a3)
{
  __int64 v3; // rbx
  __int64 result; // rax
  unsigned int v7; // edx
  __int64 v8; // rax
  __int64 v9; // rdi
  void *v10; // r15
  NTSTATUS v11; // ebx
  NTSTATUS v12; // ebx
  void *v13; // rcx
  DWORD v14; // eax
  void *v15; // rbx
  DWORD v16; // eax
  signed int v17; // eax
  int v18; // ebx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  DWORD LengthSid; // eax
  DWORD v22; // eax
  signed int LastError; // eax
  unsigned __int16 *v24; // rbx
  __int64 v25; // rdi
  LPVOID v26; // rax
  void *v27; // rbp
  unsigned __int64 v28; // r8
  unsigned __int64 v29; // rcx
  _WORD *v30; // r9
  _WORD *v31; // rdx
  unsigned __int64 v32; // rcx
  int v33; // eax
  int v34; // r8d
  PVOID PolicyHandle; // [rsp+30h] [rbp-88h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-80h] BYREF
  PVOID Buffer; // [rsp+68h] [rbp-50h] BYREF

  v3 = a2;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  result = (*(__int64 (__fastcall **)(CLocalAccounts *))(*(_QWORD *)this + 112LL))(this);
  if ( (int)result >= 0 )
  {
    v7 = *((_DWORD *)this + 6);
    if ( (unsigned int)v3 >= v7 + *((_DWORD *)this + 3) )
      return 2147942487LL;
    if ( (unsigned int)v3 >= v7 )
    {
      v9 = *((_QWORD *)this + 2) + 24LL * ((unsigned int)v3 - v7);
      if ( !byte_1800204C0 )
      {
        LODWORD(Buffer) = 0;
        WORD2(Buffer) = 1280;
        RtlInitializeSid(&byte_1800204C0, (PSID_IDENTIFIER_AUTHORITY)&Buffer, 1u);
        *RtlSubAuthoritySid(&byte_1800204C0, 0) = 32;
      }
      LengthSid = GetLengthSid(&byte_1800204C0);
      v10 = CoTaskMemAlloc(LengthSid);
      if ( v10 )
      {
        v22 = GetLengthSid(&byte_1800204C0);
        if ( CopySid(v22, v10, &byte_1800204C0) )
        {
          v18 = 0;
          goto LABEL_39;
        }
        CoTaskMemFree(v10);
        v10 = 0;
        LastError = GetLastError();
        v18 = LastError;
        if ( LastError > 0 )
          v18 = (unsigned __int16)LastError | 0x80070000;
        if ( v18 >= 0 )
          goto LABEL_40;
      }
      else
      {
        v18 = -2147024882;
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_39:
        if ( v18 < 0 )
        {
LABEL_58:
          if ( v10 )
            CoTaskMemFree(v10);
          return (unsigned int)v18;
        }
LABEL_40:
        v24 = (unsigned __int16 *)(v9 + 8);
        v25 = *(unsigned __int16 *)(v9 + 8);
        v26 = CoTaskMemAlloc(v25 + 2);
        v27 = v26;
        if ( v26 )
        {
          if ( v24 )
          {
            v28 = (unsigned __int64)(unsigned int)(v25 + 2) >> 1;
            if ( v28 )
            {
              v29 = *v24;
              v30 = v26;
              v31 = (_WORD *)*((_QWORD *)v24 + 1);
              v18 = 0;
              v32 = v29 >> 1;
              while ( v32 && *v31 )
              {
                *v30++ = *v31++;
                --v32;
                if ( !--v28 )
                {
                  v18 = -2147024774;
                  *(v30 - 1) = 0;
                  goto LABEL_50;
                }
              }
              *v30 = 0;
            }
            else
            {
              v18 = -2147024809;
            }
LABEL_50:
            if ( v18 >= 0 )
            {
              v33 = (*(__int64 (__fastcall **)(CLocalAccounts *, void *, LPVOID, struct IPropertyStore **))(*(_QWORD *)this + 120LL))(
                      this,
                      v10,
                      v26,
                      a3);
              v18 = v33;
              if ( v33 < 0
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v34, (_DWORD)v27, v33);
              }
            }
          }
          else
          {
            v18 = -2147467261;
          }
          CoTaskMemFree(v27);
        }
        else
        {
          v18 = -2147024882;
        }
        goto LABEL_58;
      }
      v20 = 31;
    }
    else
    {
      v8 = *((_QWORD *)this + 4);
      PolicyHandle = 0;
      Buffer = 0;
      v9 = v8 + 24 * v3;
      v10 = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      v11 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
      if ( v11 >= 0 )
      {
        v12 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
        if ( v12 < 0 )
        {
          v18 = v12 | 0x10000000;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
              (unsigned int)v18);
          LsaClose(PolicyHandle);
        }
        else
        {
          v13 = (void *)*((_QWORD *)Buffer + 2);
          if ( v13 )
          {
            v14 = GetLengthSid(v13);
            v10 = CoTaskMemAlloc(v14);
            if ( v10 )
            {
              v15 = (void *)*((_QWORD *)Buffer + 2);
              v16 = GetLengthSid(v15);
              if ( CopySid(v16, v10, v15) )
              {
                v18 = 0;
              }
              else
              {
                CoTaskMemFree(v10);
                v10 = 0;
                v17 = GetLastError();
                v18 = v17;
                if ( v17 > 0 )
                {
                  v18 = (unsigned __int16)v17 | 0x80070000;
                  LsaFreeMemory(Buffer);
                  LsaClose(PolicyHandle);
                  goto LABEL_39;
                }
              }
            }
            else
            {
              v18 = -2147024882;
            }
          }
          else
          {
            v18 = -2147467259;
          }
          LsaFreeMemory(Buffer);
          LsaClose(PolicyHandle);
        }
        goto LABEL_39;
      }
      v18 = v11 | 0x10000000;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_39;
      v20 = 30;
    }
    WPP_SF_d(v19[2], v20, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, (unsigned int)v18);
    goto LABEL_39;
  }
  return result;
}

```

## disassembly

```asm
0x180005f40  push    rbx
0x180005f42  push    rsi
0x180005f43  push    r14
0x180005f45  sub     rsp, 0A0h
0x180005f4c  mov     rax, cs:__security_cookie
0x180005f53  xor     rax, rsp
0x180005f56  mov     [rsp+0B8h+var_48], rax
0x180005f5b  mov     ebx, edx
0x180005f5d  mov     r14, r8
0x180005f60  mov     rsi, rcx
0x180005f63  test    r8, r8
0x180005f66  jnz     short loc_180005F72
0x180005f68  mov     eax, 80004003h
0x180005f6d  jmp     loc_180006382
0x180005f72  mov     [rsp+0B8h+var_30], r13
0x180005f7a  xor     r13d, r13d
0x180005f7d  mov     [r8], r13
0x180005f80  mov     rax, [rcx]
0x180005f83  mov     rax, [rax+70h]
0x180005f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f8c  test    eax, eax
0x180005f8e  js      loc_18000637A
0x180005f94  mov     ecx, [rsi+0Ch]
0x180005f97  mov     edx, [rsi+18h]
0x180005f9a  add     ecx, edx
0x180005f9c  cmp     ebx, ecx
0x180005f9e  jb      short loc_180005FAA
0x180005fa0  mov     eax, 80070057h
0x180005fa5  jmp     loc_18000637A
0x180005faa  mov     [rsp+0B8h+var_20], rdi
0x180005fb2  mov     [rsp+0B8h+var_28], r12
0x180005fba  mov     [rsp+0B8h+var_38], r15
0x180005fc2  cmp     ebx, edx
0x180005fc4  jnb     loc_18000615E
0x180005fca  mov     rax, [rsi+20h]
0x180005fce  lea     rcx, [rbx+rbx*2]
0x180005fd2  xorps   xmm0, xmm0
0x180005fd5  mov     [rsp+0B8h+PolicyHandle], r13
0x180005fda  lea     r9, [rsp+0B8h+PolicyHandle]; PolicyHandle
0x180005fdf  mov     [rsp+0B8h+Buffer], r13
0x180005fe4  mov     r8d, 1; DesiredAccess
0x180005fea  lea     rdx, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x180005fef  lea     rdi, [rax+rcx*8]
0x180005ff3  mov     r15, r13
0x180005ff6  xor     ecx, ecx; SystemName
0x180005ff8  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.Length], xmm0
0x180005ffd  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.ObjectName], xmm0
0x180006002  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006007  call    cs:__imp_LsaOpenPolicy
0x18000600d  mov     ebx, eax
0x18000600f  test    eax, eax
0x180006011  js      loc_18000612F
0x180006017  mov     rcx, [rsp+0B8h+PolicyHandle]; PolicyHandle
0x18000601c  lea     r8, [rsp+0B8h+Buffer]; Buffer
0x180006021  mov     edx, 5; InformationClass
0x180006026  call    cs:__imp_LsaQueryInformationPolicy
0x18000602c  lea     r12, WPP_GLOBAL_Control
0x180006033  mov     ebx, eax
0x180006035  test    eax, eax
0x180006037  js      loc_1800060F1
0x18000603d  mov     rax, [rsp+0B8h+Buffer]
0x180006042  mov     rcx, [rax+10h]; pSid
0x180006046  test    rcx, rcx
0x180006049  jz      loc_1800060D1
0x18000604f  call    cs:__imp_GetLengthSid
0x180006055  mov     ecx, eax; cb
0x180006057  call    cs:__imp_CoTaskMemAlloc
0x18000605d  mov     r15, rax
0x180006060  test    rax, rax
0x180006063  jz      short loc_1800060CA
0x180006065  mov     rax, [rsp+0B8h+Buffer]
0x18000606a  mov     rbx, [rax+10h]
0x18000606e  mov     rcx, rbx; pSid
0x180006071  call    cs:__imp_GetLengthSid
0x180006077  mov     r8, rbx; pSourceSid
0x18000607a  mov     rdx, r15; pDestinationSid
0x18000607d  mov     ecx, eax; nDestinationSidLength
0x18000607f  call    cs:__imp_CopySid
0x180006085  test    eax, eax
0x180006087  jnz     short loc_1800060C5
0x180006089  mov     rcx, r15; pv
0x18000608c  call    cs:__imp_CoTaskMemFree
0x180006092  mov     r15, r13
0x180006095  call    cs:__imp_GetLastError
0x18000609b  mov     ebx, eax
0x18000609d  test    eax, eax
0x18000609f  jle     short loc_1800060D6
0x1800060a1  mov     rcx, [rsp+0B8h+Buffer]; Buffer
0x1800060a6  movzx   ebx, ax
0x1800060a9  or      ebx, 80070000h
0x1800060af  call    cs:__imp_LsaFreeMemory
0x1800060b5  mov     rcx, [rsp+0B8h+PolicyHandle]; ObjectHandle
0x1800060ba  call    cs:__imp_LsaClose
0x1800060c0  jmp     loc_18000624D
0x1800060c5  mov     ebx, r13d
0x1800060c8  jmp     short loc_1800060D6
0x1800060ca  mov     ebx, 8007000Eh
0x1800060cf  jmp     short loc_1800060D6
0x1800060d1  mov     ebx, 80004005h
0x1800060d6  mov     rcx, [rsp+0B8h+Buffer]; Buffer
0x1800060db  call    cs:__imp_LsaFreeMemory
0x1800060e1  mov     rcx, [rsp+0B8h+PolicyHandle]; ObjectHandle
0x1800060e6  call    cs:__imp_LsaClose
0x1800060ec  jmp     loc_18000624D
0x1800060f1  bts     ebx, 1Ch
0x1800060f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060fc  cmp     rcx, r12
0x1800060ff  jz      short loc_18000611F
0x180006101  test    byte ptr [rcx+1Ch], 2
0x180006105  jz      short loc_18000611F
0x180006107  mov     rcx, [rcx+10h]
0x18000610b  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180006112  mov     edx, 1Dh
0x180006117  mov     r9d, ebx
0x18000611a  call    WPP_SF_d
0x18000611f  mov     rcx, [rsp+0B8h+PolicyHandle]; ObjectHandle
0x180006124  call    cs:__imp_LsaClose
0x18000612a  jmp     loc_18000624D
0x18000612f  bts     ebx, 1Ch
0x180006133  mov     rcx, cs:WPP_GLOBAL_Control
0x18000613a  lea     r12, WPP_GLOBAL_Control
0x180006141  cmp     rcx, r12
0x180006144  jz      loc_18000624D
0x18000614a  test    byte ptr [rcx+1Ch], 2
0x18000614e  jz      loc_18000624D
0x180006154  mov     edx, 1Eh
0x180006159  jmp     loc_18000623A
0x18000615e  mov     rax, [rsi+10h]
0x180006162  sub     ebx, edx
0x180006164  cmp     cs:byte_1800204C0, r13b
0x18000616b  lea     rcx, [rbx+rbx*2]
0x18000616f  lea     rdi, [rax+rcx*8]
0x180006173  jnz     short loc_1800061AB
0x180006175  mov     r8b, 1; SubAuthorityCount
0x180006178  mov     dword ptr [rsp+0B8h+Buffer], r13d
0x18000617d  lea     rdx, [rsp+0B8h+Buffer]; IdentifierAuthority
0x180006182  mov     word ptr [rsp+0B8h+Buffer+4], 500h
0x180006189  lea     rcx, byte_1800204C0; Sid
0x180006190  call    cs:__imp_RtlInitializeSid
0x180006196  xor     edx, edx; SubAuthority
0x180006198  lea     rcx, byte_1800204C0; Sid
0x18000619f  call    cs:__imp_RtlSubAuthoritySid
0x1800061a5  mov     dword ptr [rax], 20h ; ' '
0x1800061ab  lea     rcx, byte_1800204C0; pSid
0x1800061b2  call    cs:__imp_GetLengthSid
0x1800061b8  mov     ecx, eax; cb
0x1800061ba  call    cs:__imp_CoTaskMemAlloc
0x1800061c0  lea     r12, WPP_GLOBAL_Control
0x1800061c7  mov     r15, rax
0x1800061ca  test    rax, rax
0x1800061cd  jz      short loc_18000621E
0x1800061cf  lea     rcx, byte_1800204C0; pSid
0x1800061d6  call    cs:__imp_GetLengthSid
0x1800061dc  lea     r8, byte_1800204C0; pSourceSid
0x1800061e3  mov     rdx, r15; pDestinationSid
0x1800061e6  mov     ecx, eax; nDestinationSidLength
0x1800061e8  call    cs:__imp_CopySid
0x1800061ee  test    eax, eax
0x1800061f0  jnz     short loc_180006219
0x1800061f2  mov     rcx, r15; pv
0x1800061f5  call    cs:__imp_CoTaskMemFree
0x1800061fb  mov     r15, r13
0x1800061fe  call    cs:__imp_GetLastError
0x180006204  mov     ebx, eax
0x180006206  test    eax, eax
0x180006208  jle     short loc_180006213
0x18000620a  movzx   ebx, ax
0x18000620d  or      ebx, 80070000h
0x180006213  test    ebx, ebx
0x180006215  js      short loc_180006223
0x180006217  jmp     short loc_180006255
0x180006219  mov     ebx, r13d
0x18000621c  jmp     short loc_18000624D
0x18000621e  mov     ebx, 8007000Eh
0x180006223  mov     rcx, cs:WPP_GLOBAL_Control
0x18000622a  cmp     rcx, r12
0x18000622d  jz      short loc_18000624D
0x18000622f  test    byte ptr [rcx+1Ch], 2
0x180006233  jz      short loc_18000624D
0x180006235  mov     edx, 1Fh
0x18000623a  mov     rcx, [rcx+10h]
0x18000623e  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180006245  mov     r9d, ebx
0x180006248  call    WPP_SF_d
0x18000624d  test    ebx, ebx
0x18000624f  js      loc_180006352
0x180006255  lea     rbx, [rdi+8]
0x180006259  mov     [rsp+0B8h+arg_18], rbp
0x180006261  movzx   edi, word ptr [rbx]
0x180006264  lea     rcx, [rdi+2]; cb
0x180006268  call    cs:__imp_CoTaskMemAlloc
0x18000626e  mov     rbp, rax
0x180006271  test    rax, rax
0x180006274  jz      loc_180006345
0x18000627a  test    rbx, rbx
0x18000627d  jz      loc_180006335
0x180006283  lea     r8d, [rdi+2]
0x180006287  shr     r8, 1
0x18000628a  jz      short loc_1800062E5
0x18000628c  movzx   ecx, word ptr [rbx]
0x18000628f  mov     r9, rax
0x180006292  mov     rdx, [rbx+8]
0x180006296  mov     ebx, r13d
0x180006299  shr     rcx, 1
0x18000629c  nop     dword ptr [rax+00h]
0x1800062a0  test    rcx, rcx
0x1800062a3  jz      short loc_1800062DF
0x1800062a5  movzx   eax, word ptr [rdx]
0x1800062a8  test    ax, ax
0x1800062ab  jz      short loc_1800062D1
0x1800062ad  mov     [r9], ax
0x1800062b1  add     rdx, 2
0x1800062b5  add     r9, 2
0x1800062b9  dec     rcx
0x1800062bc  sub     r8, 1
0x1800062c0  jnz     short loc_1800062A0
0x1800062c2  sub     r9, 2
0x1800062c6  mov     ebx, 8007007Ah
0x1800062cb  mov     [r9], r13w
0x1800062cf  jmp     short loc_1800062EA
0x1800062d1  test    r8, r8
0x1800062d4  jnz     short loc_1800062DF
0x1800062d6  sub     r9, 2
0x1800062da  mov     ebx, 8007007Ah
0x1800062df  mov     [r9], r13w
0x1800062e3  jmp     short loc_1800062EA
0x1800062e5  mov     ebx, 80070057h
0x1800062ea  test    ebx, ebx
0x1800062ec  js      short loc_18000633A
0x1800062ee  mov     rax, [rsi]
0x1800062f1  mov     r9, r14
0x1800062f4  mov     r8, rbp
0x1800062f7  mov     rdx, r15
0x1800062fa  mov     rcx, rsi
0x1800062fd  mov     rax, [rax+78h]
0x180006301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006306  mov     ebx, eax
0x180006308  test    eax, eax
0x18000630a  jns     short loc_18000633A
0x18000630c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006313  cmp     rcx, r12
0x180006316  jz      short loc_18000633A
0x180006318  test    byte ptr [rcx+1Ch], 2
0x18000631c  jz      short loc_18000633A
0x18000631e  mov     rcx, [rcx+10h]
0x180006322  mov     edx, 0Ah
0x180006327  mov     r9, rbp
0x18000632a  mov     [rsp+0B8h+var_98], eax
0x18000632e  call    WPP_SF_SD
0x180006333  jmp     short loc_18000633A
0x180006335  mov     ebx, 80004003h
0x18000633a  mov     rcx, rbp; pv
0x18000633d  call    cs:__imp_CoTaskMemFree
0x180006343  jmp     short loc_18000634A
0x180006345  mov     ebx, 8007000Eh
0x18000634a  mov     rbp, [rsp+0B8h+arg_18]
0x180006352  mov     r12, [rsp+0B8h+var_28]
0x18000635a  mov     rdi, [rsp+0B8h+var_20]
0x180006362  test    r15, r15
0x180006365  jz      short loc_180006370
0x180006367  mov     rcx, r15; pv
0x18000636a  call    cs:__imp_CoTaskMemFree
0x180006370  mov     r15, [rsp+0B8h+var_38]
0x180006378  mov     eax, ebx
0x18000637a  mov     r13, [rsp+0B8h+var_30]
0x180006382  mov     rcx, [rsp+0B8h+var_48]
0x180006387  xor     rcx, rsp; StackCookie
0x18000638a  call    __security_check_cookie
0x18000638f  add     rsp, 0A0h
0x180006396  pop     r14
0x180006398  pop     rsi
0x180006399  pop     rbx
0x18000639a  retn
```
