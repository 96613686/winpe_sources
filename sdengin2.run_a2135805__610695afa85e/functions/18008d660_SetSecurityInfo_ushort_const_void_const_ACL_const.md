# SetSecurityInfo(ushort const *,void * const,_ACL * const)

- ea: `0x18008d660`
- end: `0x18008d9a3`
- name: `?SetSecurityInfo@@YAJPEBGQEAXQEAU_ACL@@@Z`
- size: `835`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, PSID psidOwner, PACL pDacl)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180089b20`

## callees

- `0x1800083e4`
- `0x180072e08`
- `0x180072f14`
- `0x18008d660`
- `0x1800935fc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18008d950`
- `KERNEL32!LocalFree` at `0x18008d950`
- `KERNEL32!CreateFileW` at `0x18008d72e`
- `KERNEL32!CreateFileW` at `0x18008d87d`
- `KERNEL32!CreateFileW` at `0x18008d72e`
- `KERNEL32!CreateFileW` at `0x18008d87d`
- `KERNEL32!CloseHandle` at `0x18008d849`
- `KERNEL32!CloseHandle` at `0x18008d899`
- `KERNEL32!CloseHandle` at `0x18008d970`
- `KERNEL32!CloseHandle` at `0x18008d849`
- `KERNEL32!CloseHandle` at `0x18008d899`
- `KERNEL32!CloseHandle` at `0x18008d970`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008d80f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008d80f`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18008d7df`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18008d7df`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18008d78d`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18008d8ea`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18008d78d`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18008d8ea`

## string_xrefs

- `0x18008d683`: `SetSecurityInfo`

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
0x18008d660  mov     [rsp-38h+arg_0], rbx
0x18008d665  push    rbp
0x18008d666  push    rsi
0x18008d667  push    rdi
0x18008d668  push    r12
0x18008d66a  push    r13
0x18008d66c  push    r14
0x18008d66e  push    r15
0x18008d670  mov     rbp, rsp
0x18008d673  sub     rsp, 80h
0x18008d67a  mov     r14, r8
0x18008d67d  mov     r15, rdx
0x18008d680  mov     r12, rcx
0x18008d683  lea     rdx, aSetsecurityinf; "SetSecurityInfo"
0x18008d68a  mov     edi, 1
0x18008d68f  lea     rcx, [rbp+var_40]; this
0x18008d693  mov     r9d, edi; unsigned __int16
0x18008d696  mov     r8d, 23Ah; unsigned __int16
0x18008d69c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008d6a1  xor     r13d, r13d
0x18008d6a4  mov     [rbp+ppsidOwner], r13
0x18008d6a8  mov     [rbp+hMem], r13
0x18008d6ac  test    r15, r15
0x18008d6af  jnz     short loc_18008D6CC
0x18008d6b1  test    r14, r14
0x18008d6b4  jnz     short loc_18008D6CC
0x18008d6b6  mov     edi, 80070057h
0x18008d6bb  mov     eax, 241h
0x18008d6c0  mov     [rbp+var_40], edi
0x18008d6c3  mov     [rbp+var_3A], ax
0x18008d6c7  jmp     loc_18008D97C
0x18008d6cc  mov     eax, 241h
0x18008d6d1  mov     [rbp+var_40], r13d
0x18008d6d5  mov     [rbp+var_3C], ax
0x18008d6d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d6e0  lea     rax, WPP_GLOBAL_Control
0x18008d6e7  cmp     rcx, rax
0x18008d6ea  jz      short loc_18008D70A
0x18008d6ec  test    byte ptr [rcx+1Ch], 2
0x18008d6f0  jz      short loc_18008D70A
0x18008d6f2  mov     rcx, [rcx+10h]
0x18008d6f6  lea     r8, WPP_5b80c48cd33b3cec6d84be26c28b1468_Traceguids
0x18008d6fd  mov     edx, 0Ch
0x18008d702  mov     r9, r12
0x18008d705  call    WPP_SF_S
0x18008d70a  mov     eax, 3
0x18008d70f  mov     [rsp+80h+hTemplateFile], r13; hTemplateFile
0x18008d714  mov     r8d, eax; dwShareMode
0x18008d717  mov     [rsp+80h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18008d71f  xor     r9d, r9d; lpSecurityAttributes
0x18008d722  mov     [rsp+80h+dwCreationDisposition], eax; dwCreationDisposition
0x18008d726  mov     edx, 60000h; dwDesiredAccess
0x18008d72b  mov     rcx, r12; lpFileName
0x18008d72e  call    cs:__imp_CreateFileW
0x18008d735  nop     dword ptr [rax+rax+00h]
0x18008d73a  mov     rbx, rax
0x18008d73d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008d741  jnz     short loc_18008D759
0x18008d743  call    GetLastFailureAsHRESULT
0x18008d748  mov     [rbp+var_40], eax
0x18008d74b  mov     eax, 24Eh
0x18008d750  mov     [rbp+var_3A], ax
0x18008d754  jmp     loc_18008D947
0x18008d759  mov     [rbp+var_40], r13d
0x18008d75d  mov     eax, 24Eh
0x18008d762  mov     [rbp+var_3C], ax
0x18008d766  mov     esi, 80070000h
0x18008d76b  test    r14, r14
0x18008d76e  jz      short loc_18008D7B2
0x18008d770  mov     [rsp+80h+hTemplateFile], r13; pSacl
0x18008d775  xor     r9d, r9d; psidOwner
0x18008d778  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r14; pDacl
0x18008d77d  mov     r8d, 80000004h; SecurityInfo
0x18008d783  mov     edx, edi; ObjectType
0x18008d785  mov     qword ptr [rsp+80h+dwCreationDisposition], r13; psidGroup
0x18008d78a  mov     rcx, rbx; handle
0x18008d78d  call    cs:__imp_SetSecurityInfo
0x18008d794  nop     dword ptr [rax+rax+00h]
0x18008d799  test    eax, eax
0x18008d79b  jle     short loc_18008D7A2
0x18008d79d  movzx   eax, ax
0x18008d7a0  or      eax, esi
0x18008d7a2  mov     [rbp+var_40], eax
0x18008d7a5  test    eax, eax
0x18008d7a7  mov     eax, 259h
0x18008d7ac  js      short loc_18008D750
0x18008d7ae  mov     [rbp+var_3C], ax
0x18008d7b2  test    r15, r15
0x18008d7b5  jz      loc_18008D916
0x18008d7bb  lea     rax, [rbp+hMem]
0x18008d7bf  mov     r8d, edi; SecurityInfo
0x18008d7c2  mov     [rsp+80h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18008d7c7  lea     r9, [rbp+ppsidOwner]; ppsidOwner
0x18008d7cb  mov     [rsp+80h+hTemplateFile], r13; ppSacl
0x18008d7d0  mov     edx, edi; ObjectType
0x18008d7d2  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r13; ppDacl
0x18008d7d7  mov     rcx, rbx; handle
0x18008d7da  mov     qword ptr [rsp+80h+dwCreationDisposition], r13; ppsidGroup
0x18008d7df  call    cs:__imp_GetSecurityInfo
0x18008d7e6  nop     dword ptr [rax+rax+00h]
0x18008d7eb  test    eax, eax
0x18008d7ed  jle     short loc_18008D7F4
0x18008d7ef  movzx   eax, ax
0x18008d7f2  or      eax, esi
0x18008d7f4  mov     [rbp+var_40], eax
0x18008d7f7  test    eax, eax
0x18008d7f9  mov     eax, 25Fh
0x18008d7fe  js      loc_18008D750
0x18008d804  mov     rcx, [rbp+ppsidOwner]; pSid1
0x18008d808  mov     rdx, r15; pSid2
0x18008d80b  mov     [rbp+var_3C], ax
0x18008d80f  call    cs:__imp_EqualSid
0x18008d816  nop     dword ptr [rax+rax+00h]
0x18008d81b  test    eax, eax
0x18008d81d  jnz     loc_18008D916
0x18008d823  mov     rax, r14
0x18008d826  neg     rax
0x18008d829  mov     rax, r14
0x18008d82c  sbb     esi, esi
0x18008d82e  and     esi, 80000004h
0x18008d834  add     esi, edi
0x18008d836  neg     rax
0x18008d839  sbb     edi, edi
0x18008d83b  and     edi, 40000h
0x18008d841  test    rbx, rbx
0x18008d844  jz      short loc_18008D859
0x18008d846  mov     rcx, rbx; hObject
0x18008d849  call    cs:__imp_CloseHandle
0x18008d850  nop     dword ptr [rax+rax+00h]
0x18008d855  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008d859  mov     [rsp+80h+hTemplateFile], r13; hTemplateFile
0x18008d85e  lea     edx, [rdi+0A0000h]; dwDesiredAccess
0x18008d864  mov     r8d, 3; dwShareMode
0x18008d86a  mov     [rsp+80h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18008d872  xor     r9d, r9d; lpSecurityAttributes
0x18008d875  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x18008d87a  mov     rcx, r12; lpFileName
0x18008d87d  call    cs:__imp_CreateFileW
0x18008d884  nop     dword ptr [rax+rax+00h]
0x18008d889  mov     rdi, rax
0x18008d88c  lea     rax, [rbx-1]
0x18008d890  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008d894  ja      short loc_18008D8A5
0x18008d896  mov     rcx, rbx; hObject
0x18008d899  call    cs:__imp_CloseHandle
0x18008d8a0  nop     dword ptr [rax+rax+00h]
0x18008d8a5  mov     rbx, rdi
0x18008d8a8  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18008d8ac  jnz     short loc_18008D8C0
0x18008d8ae  call    GetLastFailureAsHRESULT
0x18008d8b3  mov     [rbp+var_40], eax
0x18008d8b6  mov     eax, 27Bh
0x18008d8bb  jmp     loc_18008D750
0x18008d8c0  mov     eax, 27Bh
0x18008d8c5  mov     [rsp+80h+hTemplateFile], r13; pSacl
0x18008d8ca  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r14; pDacl
0x18008d8cf  mov     r9, r15; psidOwner
0x18008d8d2  mov     r8d, esi; SecurityInfo
0x18008d8d5  mov     [rbp+var_3C], ax
0x18008d8d9  mov     edx, 1; ObjectType
0x18008d8de  mov     qword ptr [rsp+80h+dwCreationDisposition], r13; psidGroup
0x18008d8e3  mov     rcx, rdi; handle
0x18008d8e6  mov     [rbp+var_40], r13d
0x18008d8ea  call    cs:__imp_SetSecurityInfo
0x18008d8f1  nop     dword ptr [rax+rax+00h]
0x18008d8f6  test    eax, eax
0x18008d8f8  jle     short loc_18008D902
0x18008d8fa  movzx   eax, ax
0x18008d8fd  or      eax, 80070000h
0x18008d902  mov     [rbp+var_40], eax
0x18008d905  test    eax, eax
0x18008d907  mov     eax, 27Eh
0x18008d90c  js      loc_18008D750
0x18008d912  mov     [rbp+var_3C], ax
0x18008d916  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d91d  lea     rax, WPP_GLOBAL_Control
0x18008d924  cmp     rcx, rax
0x18008d927  jz      short loc_18008D947
0x18008d929  test    byte ptr [rcx+1Ch], 2
0x18008d92d  jz      short loc_18008D947
0x18008d92f  mov     rcx, [rcx+10h]
0x18008d933  lea     r8, WPP_5b80c48cd33b3cec6d84be26c28b1468_Traceguids
0x18008d93a  mov     edx, 0Dh
0x18008d93f  mov     r9, r12
0x18008d942  call    WPP_SF_S
0x18008d947  mov     rcx, [rbp+hMem]; hMem
0x18008d94b  test    rcx, rcx
0x18008d94e  jz      short loc_18008D960
0x18008d950  call    cs:__imp_LocalFree
0x18008d957  nop     dword ptr [rax+rax+00h]
0x18008d95c  mov     [rbp+hMem], r13
0x18008d960  mov     edi, [rbp+var_40]
0x18008d963  lea     rcx, [rbx-1]
0x18008d967  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18008d96b  ja      short loc_18008D97C
0x18008d96d  mov     rcx, rbx; hObject
0x18008d970  call    cs:__imp_CloseHandle
0x18008d977  nop     dword ptr [rax+rax+00h]
0x18008d97c  lea     rcx, [rbp+var_40]; this
0x18008d980  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008d985  mov     rbx, [rsp+80h+arg_0]
0x18008d98d  mov     eax, edi
0x18008d98f  add     rsp, 80h
0x18008d996  pop     r15
0x18008d998  pop     r14
0x18008d99a  pop     r13
0x18008d99c  pop     r12
0x18008d99e  pop     rdi
0x18008d99f  pop     rsi
0x18008d9a0  pop     rbp
0x18008d9a1  retn
```
