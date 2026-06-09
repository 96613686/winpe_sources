# CSUpdateOrCreateUser

- ea: `0x180012acc`
- end: `0x180012ee2`
- name: `CSUpdateOrCreateUser`
- size: `1046`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, struct _UNICODE_STRING *@<rdx>, unsigned int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18000fe00`
- `0x180014d90`

## callees

- `0x180001e70`
- `0x180003660`
- `0x180003a60`
- `0x18000b9e0`
- `0x18000f168`
- `0x18000f64c`
- `0x180012acc`
- `0x180012f58`
- `0x180013240`
- `0x1800132b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012cf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012ea6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012cf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012ea6`
- `SAMLIB!SamSetInformationUser` at `0x180012dbb`
- `SAMLIB!SamSetInformationUser` at `0x180012e0b`
- `SAMLIB!SamSetInformationUser` at `0x180012dbb`
- `SAMLIB!SamSetInformationUser` at `0x180012e0b`
- `SAMLIB!SamOpenUser` at `0x180012bba`
- `SAMLIB!SamOpenUser` at `0x180012bd8`
- `SAMLIB!SamOpenUser` at `0x180012bba`
- `SAMLIB!SamOpenUser` at `0x180012bd8`
- `SAMLIB!SamLookupNamesInDomain2` at `0x180012b7b`
- `SAMLIB!SamLookupNamesInDomain2` at `0x180012b7b`
- `SAMLIB!SamCloseHandle` at `0x180012eb5`
- `SAMLIB!SamCloseHandle` at `0x180012ebf`
- `SAMLIB!SamCloseHandle` at `0x180012ec9`
- `SAMLIB!SamCloseHandle` at `0x180012eb5`
- `SAMLIB!SamCloseHandle` at `0x180012ebf`
- `SAMLIB!SamCloseHandle` at `0x180012ec9`
- `SAMLIB!SamCreateUserInDomain` at `0x180012c8f`
- `SAMLIB!SamCreateUserInDomain` at `0x180012c8f`
- `SAMLIB!SamFreeMemory` at `0x180012c2b`
- `SAMLIB!SamFreeMemory` at `0x180012c35`
- `SAMLIB!SamFreeMemory` at `0x180012c2b`
- `SAMLIB!SamFreeMemory` at `0x180012c35`

## pseudocode

```c
__int64 __fastcall CSUpdateOrCreateUser(
        void *a1,
        struct _UNICODE_STRING *a2,
        __int64 a3,
        _DWORD *a4,
        unsigned int a5,
        char a6)
{
  int v10; // ebx
  int v11; // eax
  __int64 v12; // r8
  int v13; // r14d
  int v14; // ebx
  int v15; // r8d
  int v16; // ebx
  unsigned int v17; // r9d
  int v18; // eax
  int v19; // r8d
  _QWORD *v20; // rcx
  int v21; // edx
  char v22; // r14
  struct _UNICODE_STRING *v23; // rdx
  int v24; // eax
  int v25; // r8d
  int v26; // eax
  int v27; // r8d
  int v28; // eax
  int v29; // r8d
  void *v31; // [rsp+30h] [rbp-38h] BYREF
  __int64 v32; // [rsp+38h] [rbp-30h] BYREF
  unsigned int *v33; // [rsp+40h] [rbp-28h] BYREF
  _DWORD *v34; // [rsp+48h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-18h] BYREF
  void *v36[2]; // [rsp+58h] [rbp-10h] BYREF
  unsigned int v37; // [rsp+B8h] [rbp+50h] BYREF

  v37 = 0;
  if ( !a2 )
    return (unsigned int)-2147467261;
  v36[0] = 0;
  v31 = 0;
  v10 = SamHandleForDomain(a1, 0x20031u, 0x25Eu, v36, &v31);
  if ( v10 >= 0 || (v10 = SamHandleForDomain(a1, 0x20031u, 0x20200u, v36, &v31), v10 >= 0) )
  {
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v11 = SamLookupNamesInDomain2(v31, 1, a2, &v33, &v34);
    if ( v11 >= 0 )
    {
      if ( *v34 == 1 )
      {
        v13 = v10;
        if ( (int)SamOpenUser(v31, 985087, *v33, &v32) < 0 )
        {
          v14 = SamOpenUser(v31, 131140, *v33, &v32);
          if ( v14 >= 0 )
          {
            v10 = v13;
          }
          else
          {
            v10 = v14 | 0x10000000;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, v15, (_DWORD)a2, v10);
            if ( v10 < 0 )
              goto LABEL_17;
          }
        }
        v37 = *v33;
      }
      else
      {
        v10 = -805306230;
      }
LABEL_17:
      SamFreeMemory(v34);
      SamFreeMemory(v33);
      goto LABEL_36;
    }
    if ( v11 == -1073741709 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, v12, a2);
      v16 = SamCreateUserInDomain(v31, a2, 985087, &v32, &v37);
      if ( v16 >= 0 )
      {
        pv = 0;
        v10 = CSGetBuiltInDomainSid(&pv);
        if ( v10 < 0 )
        {
LABEL_61:
          if ( v32 )
            SamCloseHandle(v32);
          SamCloseHandle(v31);
          SamCloseHandle(v36[0]);
          return (unsigned int)v10;
        }
        v18 = AddUserToGroup(a2, a1, pv, v17);
        v10 = v18;
        if ( v18 < 0
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, v19, (_DWORD)a2, v18);
        }
        CoTaskMemFree(pv);
LABEL_36:
        if ( v10 >= 0 && (a3 || a4) && v37 )
        {
          v22 = a6;
          if ( (a6 & 2) != 0 )
          {
            *(_DWORD *)(a3 + 284) &= 0x2BF827FBu;
            v23 = (struct _UNICODE_STRING *)(a3 + 48);
            if ( !*(_WORD *)(a3 + 48) )
            {
              v23->Length = a2->Length;
              *(_WORD *)(a3 + 50) = a2->MaximumLength;
              v10 = CopyUnicodeStringAlloc(a2, v23);
            }
            if ( *(_DWORD *)(a3 + 284) )
            {
              v24 = SamSetInformationUser(v32, 21, a3);
              if ( v24 < 0 )
              {
                v10 = v24 | 0x10000000;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, v25, (_DWORD)a2, v24);
                }
              }
            }
          }
          if ( (v22 & 4) != 0 )
          {
            if ( *a4 )
            {
              v26 = SamSetInformationUser(v32, 28, a4);
              if ( v26 < 0 )
              {
                v10 = v26 | 0x10000000;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, v27, (_DWORD)a2, v26);
                }
              }
            }
          }
          if ( (v22 & 1) != 0 )
          {
            pv = 0;
            v10 = CSGetAccountSIDByRID(a1, v37, &pv);
            if ( v10 >= 0 )
            {
              v28 = CSSetAccountRights(pv, a5);
              v10 = v28;
              if ( v28 < 0
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_DZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, v29, a5, (__int64)a2, v28);
              }
              CoTaskMemFree(pv);
            }
          }
        }
        goto LABEL_61;
      }
      v10 = v16 | 0x10000000;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_36;
      v21 = 76;
    }
    else
    {
      v10 = v11 | 0x10000000;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_36;
      v21 = 77;
    }
    WPP_SF_ZD(v20[2], v21, v12, (_DWORD)a2, v10);
    goto LABEL_36;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180012acc  push    rbp
0x180012ace  push    rbx
0x180012acf  push    rsi
0x180012ad0  push    rdi
0x180012ad1  push    r12
0x180012ad3  push    r13
0x180012ad5  push    r14
0x180012ad7  push    r15
0x180012ad9  mov     rbp, rsp
0x180012adc  sub     rsp, 68h
0x180012ae0  xor     r14d, r14d
0x180012ae3  mov     r13, r9
0x180012ae6  mov     [rbp+arg_8], r14d
0x180012aea  mov     r15, r8
0x180012aed  mov     rdi, rdx
0x180012af0  mov     r12, rcx
0x180012af3  test    rdx, rdx
0x180012af6  jnz     short loc_180012B02
0x180012af8  mov     ebx, 80004003h
0x180012afd  jmp     loc_180012ECF
0x180012b02  lea     rax, [rbp+var_38]
0x180012b06  mov     [rbp+var_10], r14
0x180012b0a  mov     esi, 20031h
0x180012b0f  mov     [rbp+var_38], r14
0x180012b13  mov     edx, esi; unsigned int
0x180012b15  mov     [rsp+68h+var_48], rax; void **
0x180012b1a  lea     r9, [rbp+var_10]; void **
0x180012b1e  mov     r8d, 25Eh; unsigned int
0x180012b24  call    ?SamHandleForDomain@@YAJPEAXKKPEAPEAX1@Z; SamHandleForDomain(void *,ulong,ulong,void * *,void * *)
0x180012b29  mov     ebx, eax
0x180012b2b  test    eax, eax
0x180012b2d  jns     short loc_180012B56
0x180012b2f  lea     rax, [rbp+var_38]
0x180012b33  mov     r8d, 20200h; unsigned int
0x180012b39  lea     r9, [rbp+var_10]; void **
0x180012b3d  mov     [rsp+68h+var_48], rax; void **
0x180012b42  mov     edx, esi; unsigned int
0x180012b44  mov     rcx, r12; void *
0x180012b47  call    ?SamHandleForDomain@@YAJPEAXKKPEAPEAX1@Z; SamHandleForDomain(void *,ulong,ulong,void * *,void * *)
0x180012b4c  mov     ebx, eax
0x180012b4e  test    eax, eax
0x180012b50  js      loc_180012ECF
0x180012b56  mov     rcx, [rbp+var_38]
0x180012b5a  lea     rax, [rbp+var_20]
0x180012b5e  lea     r9, [rbp+var_28]
0x180012b62  mov     [rsp+68h+var_48], rax
0x180012b67  mov     r8, rdi
0x180012b6a  mov     [rbp+var_30], r14
0x180012b6e  mov     edx, 1
0x180012b73  mov     [rbp+var_28], r14
0x180012b77  mov     [rbp+var_20], r14
0x180012b7b  call    cs:__imp_SamLookupNamesInDomain2
0x180012b81  test    eax, eax
0x180012b83  js      loc_180012C40
0x180012b89  mov     rax, [rbp+var_20]
0x180012b8d  lea     rsi, WPP_GLOBAL_Control
0x180012b94  cmp     dword ptr [rax], 1
0x180012b97  jz      short loc_180012BA3
0x180012b99  mov     ebx, 0D000008Ah
0x180012b9e  jmp     loc_180012C27
0x180012ba3  mov     r8, [rbp+var_28]
0x180012ba7  lea     r9, [rbp+var_30]
0x180012bab  mov     rcx, [rbp+var_38]
0x180012baf  mov     edx, 0F07FFh
0x180012bb4  mov     r14d, ebx
0x180012bb7  mov     r8d, [r8]
0x180012bba  call    cs:__imp_SamOpenUser
0x180012bc0  test    eax, eax
0x180012bc2  jns     short loc_180012C1B
0x180012bc4  mov     r8, [rbp+var_28]
0x180012bc8  lea     r9, [rbp+var_30]
0x180012bcc  mov     rcx, [rbp+var_38]
0x180012bd0  mov     edx, 20044h
0x180012bd5  mov     r8d, [r8]
0x180012bd8  call    cs:__imp_SamOpenUser
0x180012bde  mov     ebx, eax
0x180012be0  test    eax, eax
0x180012be2  jns     short loc_180012C18
0x180012be4  bts     ebx, 1Ch
0x180012be8  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bef  cmp     rcx, rsi
0x180012bf2  jz      short loc_180012C0F
0x180012bf4  test    byte ptr [rcx+1Ch], 2
0x180012bf8  jz      short loc_180012C0F
0x180012bfa  mov     rcx, [rcx+10h]
0x180012bfe  mov     edx, 49h ; 'I'
0x180012c03  mov     r9, rdi
0x180012c06  mov     dword ptr [rsp+68h+var_48], ebx
0x180012c0a  call    WPP_SF_ZD
0x180012c0f  xor     r14d, r14d
0x180012c12  test    ebx, ebx
0x180012c14  jns     short loc_180012C1E
0x180012c16  jmp     short loc_180012C27
0x180012c18  mov     ebx, r14d
0x180012c1b  xor     r14d, r14d
0x180012c1e  mov     rax, [rbp+var_28]
0x180012c22  mov     ecx, [rax]
0x180012c24  mov     [rbp+arg_8], ecx
0x180012c27  mov     rcx, [rbp+var_20]
0x180012c2b  call    cs:__imp_SamFreeMemory
0x180012c31  mov     rcx, [rbp+var_28]
0x180012c35  call    cs:__imp_SamFreeMemory
0x180012c3b  jmp     loc_180012D4B
0x180012c40  cmp     eax, 0C0000073h
0x180012c45  jnz     loc_180012D17
0x180012c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c52  lea     rsi, WPP_GLOBAL_Control
0x180012c59  cmp     rcx, rsi
0x180012c5c  jz      short loc_180012C75
0x180012c5e  test    byte ptr [rcx+1Ch], 8
0x180012c62  jz      short loc_180012C75
0x180012c64  mov     rcx, [rcx+10h]
0x180012c68  mov     edx, 4Ah ; 'J'
0x180012c6d  mov     r9, rdi
0x180012c70  call    WPP_SF_Z
0x180012c75  mov     rcx, [rbp+var_38]
0x180012c79  lea     rax, [rbp+arg_8]
0x180012c7d  lea     r9, [rbp+var_30]
0x180012c81  mov     [rsp+68h+var_48], rax
0x180012c86  mov     r8d, 0F07FFh
0x180012c8c  mov     rdx, rdi
0x180012c8f  call    cs:__imp_SamCreateUserInDomain
0x180012c95  mov     ebx, eax
0x180012c97  test    eax, eax
0x180012c99  js      short loc_180012CFA
0x180012c9b  lea     rcx, [rbp+pv]
0x180012c9f  mov     [rbp+pv], r14
0x180012ca3  call    CSGetBuiltInDomainSid
0x180012ca8  mov     ebx, eax
0x180012caa  test    eax, eax
0x180012cac  js      loc_180012EAC
0x180012cb2  mov     r8, [rbp+pv]; void *
0x180012cb6  mov     rdx, r12; void *
0x180012cb9  mov     rcx, rdi; struct _UNICODE_STRING *
0x180012cbc  call    ?AddUserToGroup@@YAJPEAU_UNICODE_STRING@@PEAX1K@Z; AddUserToGroup(_UNICODE_STRING *,void *,void *,ulong)
0x180012cc1  mov     ebx, eax
0x180012cc3  test    eax, eax
0x180012cc5  jns     short loc_180012CEE
0x180012cc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cce  cmp     rcx, rsi
0x180012cd1  jz      short loc_180012CEE
0x180012cd3  test    byte ptr [rcx+1Ch], 4
0x180012cd7  jz      short loc_180012CEE
0x180012cd9  mov     rcx, [rcx+10h]
0x180012cdd  mov     edx, 4Bh ; 'K'
0x180012ce2  mov     r9, rdi
0x180012ce5  mov     dword ptr [rsp+68h+var_48], eax
0x180012ce9  call    WPP_SF_ZD
0x180012cee  mov     rcx, [rbp+pv]; pv
0x180012cf2  call    cs:__imp_CoTaskMemFree
0x180012cf8  jmp     short loc_180012D4B
0x180012cfa  bts     ebx, 1Ch
0x180012cfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d05  cmp     rcx, rsi
0x180012d08  jz      short loc_180012D4B
0x180012d0a  test    byte ptr [rcx+1Ch], 2
0x180012d0e  jz      short loc_180012D4B
0x180012d10  mov     edx, 4Ch ; 'L'
0x180012d15  jmp     short loc_180012D3B
0x180012d17  mov     ebx, eax
0x180012d19  bts     ebx, 1Ch
0x180012d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d24  lea     rsi, WPP_GLOBAL_Control
0x180012d2b  cmp     rcx, rsi
0x180012d2e  jz      short loc_180012D4B
0x180012d30  test    byte ptr [rcx+1Ch], 2
0x180012d34  jz      short loc_180012D4B
0x180012d36  mov     edx, 4Dh ; 'M'
0x180012d3b  mov     rcx, [rcx+10h]
0x180012d3f  mov     r9, rdi
0x180012d42  mov     dword ptr [rsp+68h+var_48], ebx
0x180012d46  call    WPP_SF_ZD
0x180012d4b  test    ebx, ebx
0x180012d4d  js      loc_180012EAC
0x180012d53  test    r15, r15
0x180012d56  jnz     short loc_180012D61
0x180012d58  test    r13, r13
0x180012d5b  jz      loc_180012EAC
0x180012d61  cmp     [rbp+arg_8], r14d
0x180012d65  jz      loc_180012EAC
0x180012d6b  mov     r14d, [rbp+arg_28]
0x180012d6f  test    r14b, 2
0x180012d73  jz      short loc_180012DF2
0x180012d75  and     dword ptr [r15+11Ch], 2BF827FBh
0x180012d80  lea     rdx, [r15+30h]; struct _UNICODE_STRING *
0x180012d84  xor     eax, eax
0x180012d86  cmp     [rdx], ax
0x180012d89  jnz     short loc_180012DA6
0x180012d8b  movzx   eax, word ptr [rdi]
0x180012d8e  mov     rcx, rdi; struct _UNICODE_STRING *
0x180012d91  mov     [rdx], ax
0x180012d94  movzx   eax, word ptr [rdi+2]
0x180012d98  mov     [r15+32h], ax
0x180012d9d  call    ?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z; CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)
0x180012da2  mov     ebx, eax
0x180012da4  xor     eax, eax
0x180012da6  cmp     [r15+11Ch], eax
0x180012dad  jz      short loc_180012DF2
0x180012daf  mov     rcx, [rbp+var_30]
0x180012db3  mov     r8, r15
0x180012db6  mov     edx, 15h
0x180012dbb  call    cs:__imp_SamSetInformationUser
0x180012dc1  test    eax, eax
0x180012dc3  jns     short loc_180012DF2
0x180012dc5  mov     ebx, eax
0x180012dc7  bts     ebx, 1Ch
0x180012dcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180012dd2  cmp     rcx, rsi
0x180012dd5  jz      short loc_180012DF2
0x180012dd7  test    byte ptr [rcx+1Ch], 2
0x180012ddb  jz      short loc_180012DF2
0x180012ddd  mov     rcx, [rcx+10h]
0x180012de1  mov     edx, 4Eh ; 'N'
0x180012de6  mov     r9, rdi
0x180012de9  mov     dword ptr [rsp+68h+var_48], ebx
0x180012ded  call    WPP_SF_ZD
0x180012df2  test    r14b, 4
0x180012df6  jz      short loc_180012E42
0x180012df8  cmp     dword ptr [r13+0], 0
0x180012dfd  jz      short loc_180012E42
0x180012dff  mov     rcx, [rbp+var_30]
0x180012e03  mov     r8, r13
0x180012e06  mov     edx, 1Ch
0x180012e0b  call    cs:__imp_SamSetInformationUser
0x180012e11  test    eax, eax
0x180012e13  jns     short loc_180012E42
0x180012e15  mov     ebx, eax
0x180012e17  bts     ebx, 1Ch
0x180012e1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e22  cmp     rcx, rsi
0x180012e25  jz      short loc_180012E42
0x180012e27  test    byte ptr [rcx+1Ch], 2
0x180012e2b  jz      short loc_180012E42
0x180012e2d  mov     rcx, [rcx+10h]
0x180012e31  mov     edx, 4Fh ; 'O'
0x180012e36  mov     r9, rdi
0x180012e39  mov     dword ptr [rsp+68h+var_48], ebx
0x180012e3d  call    WPP_SF_ZD
0x180012e42  test    r14b, 1
0x180012e46  jz      short loc_180012EAC
0x180012e48  mov     edx, [rbp+arg_8]
0x180012e4b  lea     r8, [rbp+pv]
0x180012e4f  xor     r14d, r14d
0x180012e52  mov     rcx, r12
0x180012e55  mov     [rbp+pv], r14
0x180012e59  call    CSGetAccountSIDByRID
0x180012e5e  mov     ebx, eax
0x180012e60  test    eax, eax
0x180012e62  js      short loc_180012EAC
0x180012e64  mov     edx, [rbp+arg_20]; unsigned int
0x180012e67  mov     rcx, [rbp+pv]; void *
0x180012e6b  call    ?CSSetAccountRights@@YAJPEAXK@Z; CSSetAccountRights(void *,ulong)
0x180012e70  mov     ebx, eax
0x180012e72  test    eax, eax
0x180012e74  jns     short loc_180012EA2
0x180012e76  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e7d  cmp     rcx, rsi
0x180012e80  jz      short loc_180012EA2
0x180012e82  test    byte ptr [rcx+1Ch], 2
0x180012e86  jz      short loc_180012EA2
0x180012e88  mov     r9d, [rbp+arg_20]
0x180012e8c  lea     edx, [r14+50h]
0x180012e90  mov     rcx, [rcx+10h]
0x180012e94  mov     [rsp+68h+var_40], eax
0x180012e98  mov     [rsp+68h+var_48], rdi
0x180012e9d  call    WPP_SF_DZD
0x180012ea2  mov     rcx, [rbp+pv]; pv
0x180012ea6  call    cs:__imp_CoTaskMemFree
0x180012eac  mov     rcx, [rbp+var_30]
0x180012eb0  test    rcx, rcx
0x180012eb3  jz      short loc_180012EBB
0x180012eb5  call    cs:__imp_SamCloseHandle
0x180012ebb  mov     rcx, [rbp+var_38]
0x180012ebf  call    cs:__imp_SamCloseHandle
0x180012ec5  mov     rcx, [rbp+var_10]
0x180012ec9  call    cs:__imp_SamCloseHandle
0x180012ecf  mov     eax, ebx
0x180012ed1  add     rsp, 68h
0x180012ed5  pop     r15
0x180012ed7  pop     r14
0x180012ed9  pop     r13
0x180012edb  pop     r12
0x180012edd  pop     rdi
0x180012ede  pop     rsi
0x180012edf  pop     rbx
0x180012ee0  pop     rbp
0x180012ee1  retn
```
