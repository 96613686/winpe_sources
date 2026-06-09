# SetSecurityInfo(ushort const *,void * const,_ACL * const)

- ea: `0x180089ab4`
- end: `0x180089dba`
- name: `?SetSecurityInfo@@YAJPEBGQEAXQEAU_ACL@@@Z`
- size: `774`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, PSID psidOwner, PACL pDacl)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180086220`

## callees

- `0x180008240`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180089ab4`
- `0x18008f5d0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180089d74`
- `KERNEL32!LocalFree` at `0x180089d74`
- `KERNEL32!CreateFileW` at `0x180089b82`
- `KERNEL32!CreateFileW` at `0x180089cb3`
- `KERNEL32!CreateFileW` at `0x180089b82`
- `KERNEL32!CreateFileW` at `0x180089cb3`
- `KERNEL32!CloseHandle` at `0x180089c85`
- `KERNEL32!CloseHandle` at `0x180089cc9`
- `KERNEL32!CloseHandle` at `0x180089d8e`
- `KERNEL32!CloseHandle` at `0x180089c85`
- `KERNEL32!CloseHandle` at `0x180089cc9`
- `KERNEL32!CloseHandle` at `0x180089d8e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180089c51`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180089c51`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180089c27`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180089c27`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180089bdb`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180089d14`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180089bdb`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180089d14`

## string_xrefs

- `0x180089ad7`: `SetSecurityInfo`

## pseudocode

```c
__int64 __fastcall SetSecurityInfo(LPCWSTR lpFileName, PSID psidOwner, PACL pDacl)
{
  unsigned int v6; // edi
  __int64 v7; // rcx
  __int64 FileW; // rbx
  __int16 v9; // ax
  signed int v10; // eax
  bool v11; // sf
  signed int SecurityInfo; // eax
  __int64 v13; // rcx
  HANDLE v14; // rdi
  signed int v15; // eax
  int LastFailureAsHRESULT; // [rsp+40h] [rbp-40h] BYREF
  __int16 v18; // [rsp+44h] [rbp-3Ch]
  __int16 v19; // [rsp+46h] [rbp-3Ah]
  PSECURITY_DESCRIPTOR hMem; // [rsp+C8h] [rbp+48h] BYREF
  PSID ppsidOwner; // [rsp+D8h] [rbp+58h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "SetSecurityInfo", 0x23Au, 1u);
  ppsidOwner = 0;
  hMem = 0;
  if ( !psidOwner && !pDacl )
  {
    v6 = -2147024809;
    LastFailureAsHRESULT = -2147024809;
    v19 = 577;
    goto LABEL_37;
  }
  LastFailureAsHRESULT = 0;
  v18 = 577;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_5b80c48cd33b3cec6d84be26c28b1468_Traceguids, lpFileName);
  FileW = (__int64)CreateFileW(lpFileName, 0x60000u, 3u, 0, 3u, 0x2200000u, 0);
  if ( FileW != -1 )
  {
    LastFailureAsHRESULT = 0;
    v18 = 590;
    if ( pDacl )
    {
      v10 = SetSecurityInfo((HANDLE)FileW, SE_FILE_OBJECT, 0x80000004, 0, 0, pDacl, 0);
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      LastFailureAsHRESULT = v10;
      v11 = v10 < 0;
      v9 = 601;
      if ( v11 )
        goto LABEL_9;
      v18 = 601;
    }
    if ( psidOwner )
    {
      SecurityInfo = GetSecurityInfo((HANDLE)FileW, SE_FILE_OBJECT, 1u, &ppsidOwner, 0, 0, 0, &hMem);
      if ( SecurityInfo > 0 )
        SecurityInfo = (unsigned __int16)SecurityInfo | 0x80070000;
      LastFailureAsHRESULT = SecurityInfo;
      v11 = SecurityInfo < 0;
      v9 = 607;
      if ( v11 )
        goto LABEL_9;
      v18 = 607;
      if ( !EqualSid(ppsidOwner, psidOwner) )
      {
        if ( FileW )
        {
          CloseHandle((HANDLE)FileW);
          FileW = -1;
        }
        v14 = CreateFileW(lpFileName, pDacl != 0 ? 917504 : 655360, 3u, 0, 3u, 0x2200000u, 0);
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle((HANDLE)FileW);
        FileW = (__int64)v14;
        if ( v14 == (HANDLE)-1LL )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13);
          v9 = 635;
          goto LABEL_9;
        }
        v18 = 635;
        LastFailureAsHRESULT = 0;
        v15 = SetSecurityInfo(v14, SE_FILE_OBJECT, pDacl != 0 ? -2147483643 : 1, psidOwner, 0, pDacl, 0);
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        LastFailureAsHRESULT = v15;
        v11 = v15 < 0;
        v9 = 638;
        if ( v11 )
          goto LABEL_9;
        v18 = 638;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_5b80c48cd33b3cec6d84be26c28b1468_Traceguids, lpFileName);
    goto LABEL_33;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
  v9 = 590;
LABEL_9:
  v19 = v9;
LABEL_33:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  v6 = LastFailureAsHRESULT;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
LABEL_37:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v6;
}

```

## disassembly

```asm
0x180089ab4  mov     [rsp-38h+arg_0], rbx
0x180089ab9  push    rbp
0x180089aba  push    rsi
0x180089abb  push    rdi
0x180089abc  push    r12
0x180089abe  push    r13
0x180089ac0  push    r14
0x180089ac2  push    r15
0x180089ac4  mov     rbp, rsp
0x180089ac7  sub     rsp, 80h
0x180089ace  mov     r14, r8
0x180089ad1  mov     r15, rdx
0x180089ad4  mov     r12, rcx
0x180089ad7  lea     rdx, aSetsecurityinf; "SetSecurityInfo"
0x180089ade  mov     edi, 1
0x180089ae3  lea     rcx, [rbp+var_40]; this
0x180089ae7  mov     r9d, edi; unsigned __int16
0x180089aea  mov     r8d, 23Ah; unsigned __int16
0x180089af0  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180089af5  xor     r13d, r13d
0x180089af8  mov     [rbp+ppsidOwner], r13
0x180089afc  mov     [rbp+hMem], r13
0x180089b00  test    r15, r15
0x180089b03  jnz     short loc_180089B20
0x180089b05  test    r14, r14
0x180089b08  jnz     short loc_180089B20
0x180089b0a  mov     edi, 80070057h
0x180089b0f  mov     eax, 241h
0x180089b14  mov     [rbp+var_40], edi
0x180089b17  mov     [rbp+var_3A], ax
0x180089b1b  jmp     loc_180089D94
0x180089b20  mov     eax, 241h
0x180089b25  mov     [rbp+var_40], r13d
0x180089b29  mov     [rbp+var_3C], ax
0x180089b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180089b34  lea     rax, WPP_GLOBAL_Control
0x180089b3b  cmp     rcx, rax
0x180089b3e  jz      short loc_180089B5E
0x180089b40  test    byte ptr [rcx+1Ch], 2
0x180089b44  jz      short loc_180089B5E
0x180089b46  mov     rcx, [rcx+10h]
0x180089b4a  lea     r8, WPP_5b80c48cd33b3cec6d84be26c28b1468_Traceguids
0x180089b51  mov     edx, 0Ch
0x180089b56  mov     r9, r12
0x180089b59  call    WPP_SF_S
0x180089b5e  mov     eax, 3
0x180089b63  mov     [rsp+80h+hTemplateFile], r13; hTemplateFile
0x180089b68  mov     r8d, eax; dwShareMode
0x180089b6b  mov     [rsp+80h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180089b73  xor     r9d, r9d; lpSecurityAttributes
0x180089b76  mov     [rsp+80h+dwCreationDisposition], eax; dwCreationDisposition
0x180089b7a  mov     edx, 60000h; dwDesiredAccess
0x180089b7f  mov     rcx, r12; lpFileName
0x180089b82  call    cs:__imp_CreateFileW
0x180089b88  mov     rbx, rax
0x180089b8b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180089b8f  jnz     short loc_180089BA7
0x180089b91  call    GetLastFailureAsHRESULT
0x180089b96  mov     [rbp+var_40], eax
0x180089b99  mov     eax, 24Eh
0x180089b9e  mov     [rbp+var_3A], ax
0x180089ba2  jmp     loc_180089D6B
0x180089ba7  mov     [rbp+var_40], r13d
0x180089bab  mov     eax, 24Eh
0x180089bb0  mov     [rbp+var_3C], ax
0x180089bb4  mov     esi, 80070000h
0x180089bb9  test    r14, r14
0x180089bbc  jz      short loc_180089BFA
0x180089bbe  mov     [rsp+80h+hTemplateFile], r13; pSacl
0x180089bc3  xor     r9d, r9d; psidOwner
0x180089bc6  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r14; pDacl
0x180089bcb  mov     r8d, 80000004h; SecurityInfo
0x180089bd1  mov     edx, edi; ObjectType
0x180089bd3  mov     qword ptr [rsp+80h+dwCreationDisposition], r13; psidGroup
0x180089bd8  mov     rcx, rbx; handle
0x180089bdb  call    cs:__imp_SetSecurityInfo
0x180089be1  test    eax, eax
0x180089be3  jle     short loc_180089BEA
0x180089be5  movzx   eax, ax
0x180089be8  or      eax, esi
0x180089bea  mov     [rbp+var_40], eax
0x180089bed  test    eax, eax
0x180089bef  mov     eax, 259h
0x180089bf4  js      short loc_180089B9E
0x180089bf6  mov     [rbp+var_3C], ax
0x180089bfa  test    r15, r15
0x180089bfd  jz      loc_180089D3A
0x180089c03  lea     rax, [rbp+hMem]
0x180089c07  mov     r8d, edi; SecurityInfo
0x180089c0a  mov     [rsp+80h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180089c0f  lea     r9, [rbp+ppsidOwner]; ppsidOwner
0x180089c13  mov     [rsp+80h+hTemplateFile], r13; ppSacl
0x180089c18  mov     edx, edi; ObjectType
0x180089c1a  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r13; ppDacl
0x180089c1f  mov     rcx, rbx; handle
0x180089c22  mov     qword ptr [rsp+80h+dwCreationDisposition], r13; ppsidGroup
0x180089c27  call    cs:__imp_GetSecurityInfo
0x180089c2d  test    eax, eax
0x180089c2f  jle     short loc_180089C36
0x180089c31  movzx   eax, ax
0x180089c34  or      eax, esi
0x180089c36  mov     [rbp+var_40], eax
0x180089c39  test    eax, eax
0x180089c3b  mov     eax, 25Fh
0x180089c40  js      loc_180089B9E
0x180089c46  mov     rcx, [rbp+ppsidOwner]; pSid1
0x180089c4a  mov     rdx, r15; pSid2
0x180089c4d  mov     [rbp+var_3C], ax
0x180089c51  call    cs:__imp_EqualSid
0x180089c57  test    eax, eax
0x180089c59  jnz     loc_180089D3A
0x180089c5f  mov     rax, r14
0x180089c62  neg     rax
0x180089c65  mov     rax, r14
0x180089c68  sbb     esi, esi
0x180089c6a  and     esi, 80000004h
0x180089c70  add     esi, edi
0x180089c72  neg     rax
0x180089c75  sbb     edi, edi
0x180089c77  and     edi, 40000h
0x180089c7d  test    rbx, rbx
0x180089c80  jz      short loc_180089C8F
0x180089c82  mov     rcx, rbx; hObject
0x180089c85  call    cs:__imp_CloseHandle
0x180089c8b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180089c8f  mov     [rsp+80h+hTemplateFile], r13; hTemplateFile
0x180089c94  lea     edx, [rdi+0A0000h]; dwDesiredAccess
0x180089c9a  mov     r8d, 3; dwShareMode
0x180089ca0  mov     [rsp+80h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180089ca8  xor     r9d, r9d; lpSecurityAttributes
0x180089cab  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x180089cb0  mov     rcx, r12; lpFileName
0x180089cb3  call    cs:__imp_CreateFileW
0x180089cb9  mov     rdi, rax
0x180089cbc  lea     rax, [rbx-1]
0x180089cc0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180089cc4  ja      short loc_180089CCF
0x180089cc6  mov     rcx, rbx; hObject
0x180089cc9  call    cs:__imp_CloseHandle
0x180089ccf  mov     rbx, rdi
0x180089cd2  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180089cd6  jnz     short loc_180089CEA
0x180089cd8  call    GetLastFailureAsHRESULT
0x180089cdd  mov     [rbp+var_40], eax
0x180089ce0  mov     eax, 27Bh
0x180089ce5  jmp     loc_180089B9E
0x180089cea  mov     eax, 27Bh
0x180089cef  mov     [rsp+80h+hTemplateFile], r13; pSacl
0x180089cf4  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r14; pDacl
0x180089cf9  mov     r9, r15; psidOwner
0x180089cfc  mov     r8d, esi; SecurityInfo
0x180089cff  mov     [rbp+var_3C], ax
0x180089d03  mov     edx, 1; ObjectType
0x180089d08  mov     qword ptr [rsp+80h+dwCreationDisposition], r13; psidGroup
0x180089d0d  mov     rcx, rdi; handle
0x180089d10  mov     [rbp+var_40], r13d
0x180089d14  call    cs:__imp_SetSecurityInfo
0x180089d1a  test    eax, eax
0x180089d1c  jle     short loc_180089D26
0x180089d1e  movzx   eax, ax
0x180089d21  or      eax, 80070000h
0x180089d26  mov     [rbp+var_40], eax
0x180089d29  test    eax, eax
0x180089d2b  mov     eax, 27Eh
0x180089d30  js      loc_180089B9E
0x180089d36  mov     [rbp+var_3C], ax
0x180089d3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180089d41  lea     rax, WPP_GLOBAL_Control
0x180089d48  cmp     rcx, rax
0x180089d4b  jz      short loc_180089D6B
0x180089d4d  test    byte ptr [rcx+1Ch], 2
0x180089d51  jz      short loc_180089D6B
0x180089d53  mov     rcx, [rcx+10h]
0x180089d57  lea     r8, WPP_5b80c48cd33b3cec6d84be26c28b1468_Traceguids
0x180089d5e  mov     edx, 0Dh
0x180089d63  mov     r9, r12
0x180089d66  call    WPP_SF_S
0x180089d6b  mov     rcx, [rbp+hMem]; hMem
0x180089d6f  test    rcx, rcx
0x180089d72  jz      short loc_180089D7E
0x180089d74  call    cs:__imp_LocalFree
0x180089d7a  mov     [rbp+hMem], r13
0x180089d7e  mov     edi, [rbp+var_40]
0x180089d81  lea     rcx, [rbx-1]
0x180089d85  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180089d89  ja      short loc_180089D94
0x180089d8b  mov     rcx, rbx; hObject
0x180089d8e  call    cs:__imp_CloseHandle
0x180089d94  lea     rcx, [rbp+var_40]; this
0x180089d98  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180089d9d  mov     rbx, [rsp+80h+arg_0]
0x180089da5  mov     eax, edi
0x180089da7  add     rsp, 80h
0x180089dae  pop     r15
0x180089db0  pop     r14
0x180089db2  pop     r13
0x180089db4  pop     r12
0x180089db6  pop     rdi
0x180089db7  pop     rsi
0x180089db8  pop     rbp
0x180089db9  retn
```
