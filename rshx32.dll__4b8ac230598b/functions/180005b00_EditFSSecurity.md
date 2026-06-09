# EditFSSecurity

- ea: `0x180005b00`
- end: `0x180005e22`
- name: `EditFSSecurity`
- size: `802`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, int, PSECURITY_DESCRIPTOR pSecurityDescriptor, HWND *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180005b00`
- `0x180005fd4`
- `0x1800061b0`
- `0x180009148`
- `0x180015e64`
- `0x18001654c`
- `0x18001d33a`
- `0x18001d370`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005dda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005dda`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005c52`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005c52`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180005b76`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180005b76`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005b9e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005b9e`
- `ACLUI!__imp_EditSecurity` at `0x180005dc6`
- `ACLUI!__imp_EditSecurity` at `0x180005dc6`
- `ACLUI!__imp_EditSecurityAdvanced` at `0x180005d7a`
- `ACLUI!__imp_EditSecurityAdvanced` at `0x180005d7a`

## pseudocode

```c
__int64 __fastcall EditFSSecurity(
        HWND a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        HWND *a8)
{
  unsigned __int16 *v8; // r15
  HRESULT SelfRelativeSecurityDescriptor; // ebx
  unsigned int v13; // r9d
  char v14; // al
  int v15; // ecx
  int v16; // ecx
  unsigned int v17; // edx
  CNTFSSecurity *v18; // rax
  CFSSecurity *v19; // rdi
  unsigned __int16 *v20; // rdx
  __int64 v21; // rcx
  void *v22; // rcx
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  void *v25; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  HWND hwndOwner; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v28; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v29; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v30; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v31; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v32; // [rsp+80h] [rbp-80h]
  unsigned __int16 v33[264]; // [rsp+90h] [rbp-70h] BYREF

  v8 = 0;
  v32 = a3;
  hwndOwner = a1;
  if ( a8 )
    *a8 = 0;
  if ( pSecurityDescriptor && (!a5 || !IsValidSecurityDescriptor(pSecurityDescriptor)) )
    return (unsigned int)-2147024809;
  if ( !a3 || !a4 || !a2 )
    return (unsigned int)-2147467261;
  if ( (GetFileAttributesW(a2) & 0x10) != 0 )
  {
    LODWORD(v25) = 0;
    v24 = 0;
    v26 = 0;
    v30 = 0;
    v29 = 0;
    v31 = 0;
    v28 = 0;
    memset_0(v33, 0, 0x208u);
    GetFileInfo(a2, (unsigned int *)&v25, v33, v13, (int *)&v24, &v26);
    v14 = (char)v25;
    v15 = (unsigned __int8)v25 & 2;
    v25 = 0;
    v16 = (v15 << 8) | 0x20017;
    v17 = v16 | 0x60000000;
    if ( (v14 & 0xC) != 0xC )
      v17 = v16;
    v24 = v17;
    if ( !pSecurityDescriptor
      || (SelfRelativeSecurityDescriptor = MakeSelfRelativeSecurityDescriptor(pSecurityDescriptor, &v25),
          SelfRelativeSecurityDescriptor >= 0) )
    {
      v18 = (CNTFSSecurity *)LocalAlloc(0x40u, 0x280u);
      v19 = v18;
      if ( !v18 )
        return (unsigned int)-2147024882;
      CNTFSSecurity::CNTFSSecurity(v18, SE_FILE_OBJECT, 0);
      v20 = v32;
      *(_QWORD *)v19 = &CFSSecurity::`vftable'{for `ISecurityInformation'};
      *((_QWORD *)v19 + 79) = 0;
      *((_QWORD *)v19 + 1) = &CSecurityInformation::`vftable'{for `IEffectivePermission'};
      *((_QWORD *)v19 + 2) = &CFSSecurity::`vftable'{for `IEffectivePermission2'};
      *((_QWORD *)v19 + 3) = &CNTFSSecurity::`vftable'{for `ISecurityObjectTypeInfo'};
      *((_QWORD *)v19 + 4) = &CFSSecurity::`vftable'{for `ISecurityInformation3'};
      *((_QWORD *)v19 + 5) = &CFSSecurity::`vftable'{for `ISecurityInformation4'};
      SelfRelativeSecurityDescriptor = LocalAllocString(&v30, v20);
      if ( SelfRelativeSecurityDescriptor < 0 )
        goto LABEL_33;
      SelfRelativeSecurityDescriptor = LocalAllocString(&v29, a4);
      if ( SelfRelativeSecurityDescriptor < 0 )
        goto LABEL_33;
      SelfRelativeSecurityDescriptor = LocalAllocString(&v31, a2);
      if ( SelfRelativeSecurityDescriptor < 0 )
        goto LABEL_33;
      if ( a5 )
      {
        SelfRelativeSecurityDescriptor = LocalAllocString(&v28, a5);
        if ( SelfRelativeSecurityDescriptor < 0 )
          goto LABEL_33;
        v8 = v28;
      }
      SelfRelativeSecurityDescriptor = CFSSecurity::Initialize(v19, v31, v24, v30, v29, v8, v25, v26);
      if ( SelfRelativeSecurityDescriptor )
      {
        LocalFree(v8);
      }
      else if ( a6 )
      {
        SelfRelativeSecurityDescriptor = EditSecurityAdvanced(hwndOwner, (LPSECURITYINFO)v19, (SI_PAGE_TYPE)0x10000);
        if ( !SelfRelativeSecurityDescriptor )
        {
LABEL_25:
          if ( a8 )
          {
            v21 = *((_QWORD *)v19 + 79);
            if ( v21 )
            {
              if ( *(_QWORD *)(v21 + 256) )
              {
                v22 = *(void **)(v21 + 256);
                hwndOwner = 0;
                SelfRelativeSecurityDescriptor = MakeSelfRelativeSecurityDescriptor(v22, (void **)&hwndOwner);
                if ( !SelfRelativeSecurityDescriptor )
                  *a8 = hwndOwner;
              }
            }
          }
        }
      }
      else
      {
        if ( EditSecurity(hwndOwner, (LPSECURITYINFO)v19) )
          goto LABEL_25;
        SelfRelativeSecurityDescriptor = -2147467259;
      }
LABEL_33:
      (*(void (__fastcall **)(CFSSecurity *))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)SelfRelativeSecurityDescriptor;
}

```

## disassembly

```asm
0x180005b00  push    rbp
0x180005b02  push    rbx
0x180005b03  push    rsi
0x180005b04  push    rdi
0x180005b05  push    r12
0x180005b07  push    r13
0x180005b09  push    r14
0x180005b0b  push    r15
0x180005b0d  lea     rbp, [rsp-1B8h]
0x180005b15  sub     rsp, 2B8h
0x180005b1c  mov     rax, cs:__security_cookie
0x180005b23  xor     rax, rsp
0x180005b26  mov     [rbp+1F0h+var_50], rax
0x180005b2d  mov     rsi, [rbp+1F0h+arg_38]
0x180005b34  xor     r15d, r15d
0x180005b37  mov     r12, [rbp+1F0h+arg_20]
0x180005b3e  mov     r13, r9
0x180005b41  mov     rbx, [rbp+1F0h+pSecurityDescriptor]
0x180005b48  mov     rdi, r8
0x180005b4b  mov     [rbp+1F0h+var_270], r8
0x180005b4f  mov     r14, rdx
0x180005b52  mov     [rsp+2F0h+hwndOwner], rcx
0x180005b57  test    rsi, rsi
0x180005b5a  jz      short loc_180005B5F
0x180005b5c  mov     [rsi], r15
0x180005b5f  test    rbx, rbx
0x180005b62  jz      short loc_180005B80
0x180005b64  test    r12, r12
0x180005b67  jnz     short loc_180005B73
0x180005b69  mov     ebx, 80070057h
0x180005b6e  jmp     loc_180005DFD
0x180005b73  mov     rcx, rbx; pSecurityDescriptor
0x180005b76  call    cs:__imp_IsValidSecurityDescriptor
0x180005b7c  test    eax, eax
0x180005b7e  jz      short loc_180005B69
0x180005b80  test    rdi, rdi
0x180005b83  jz      loc_180005DF8
0x180005b89  test    r13, r13
0x180005b8c  jz      loc_180005DF8
0x180005b92  test    r14, r14
0x180005b95  jz      loc_180005DF8
0x180005b9b  mov     rcx, r14; lpFileName
0x180005b9e  call    cs:__imp_GetFileAttributesW
0x180005ba4  test    al, 10h
0x180005ba6  jz      short loc_180005B69
0x180005ba8  xor     edx, edx; Val
0x180005baa  mov     dword ptr [rsp+2F0h+var_2A8], r15d
0x180005baf  mov     r8d, 208h; Size
0x180005bb5  mov     [rsp+2F0h+var_2B0], r15d
0x180005bba  lea     rcx, [rbp+1F0h+var_260]; void *
0x180005bbe  mov     [rsp+2F0h+var_2A0], r15d
0x180005bc3  mov     [rsp+2F0h+var_280], r15
0x180005bc8  mov     [rsp+2F0h+var_288], r15
0x180005bcd  mov     [rsp+2F0h+var_278], r15
0x180005bd2  mov     [rsp+2F0h+var_290], r15
0x180005bd7  call    memset_0
0x180005bdc  lea     rax, [rsp+2F0h+var_2A0]
0x180005be1  mov     rcx, r14; unsigned __int16 *
0x180005be4  mov     [rsp+2F0h+var_2C8], rax; int *
0x180005be9  lea     r8, [rbp+1F0h+var_260]; unsigned __int16 *
0x180005bed  lea     rax, [rsp+2F0h+var_2B0]
0x180005bf2  lea     rdx, [rsp+2F0h+var_2A8]; unsigned int *
0x180005bf7  mov     [rsp+2F0h+var_2D0], rax; int *
0x180005bfc  call    ?GetFileInfo@@YAXPEBGPEAKPEAGKPEAH3@Z; GetFileInfo(ushort const *,ulong *,ushort *,ulong,int *,int *)
0x180005c01  mov     eax, dword ptr [rsp+2F0h+var_2A8]
0x180005c05  mov     ecx, eax
0x180005c07  and     ecx, 2
0x180005c0a  mov     [rsp+2F0h+var_2A8], r15
0x180005c0f  shl     ecx, 8
0x180005c12  and     eax, 0Ch
0x180005c15  or      ecx, 20017h
0x180005c1b  mov     edx, ecx
0x180005c1d  or      edx, 60000000h
0x180005c23  cmp     al, 0Ch
0x180005c25  cmovnz  edx, ecx
0x180005c28  mov     [rsp+2F0h+var_2B0], edx
0x180005c2c  test    rbx, rbx
0x180005c2f  jz      short loc_180005C48
0x180005c31  lea     rdx, [rsp+2F0h+var_2A8]; void **
0x180005c36  mov     rcx, rbx; Src
0x180005c39  call    ?MakeSelfRelativeSecurityDescriptor@@YAJPEAXPEAPEAX@Z; MakeSelfRelativeSecurityDescriptor(void *,void * *)
0x180005c3e  mov     ebx, eax
0x180005c40  test    eax, eax
0x180005c42  js      loc_180005DFD
0x180005c48  mov     edx, 280h; uBytes
0x180005c4d  mov     ecx, 40h ; '@'; uFlags
0x180005c52  call    cs:__imp_LocalAlloc
0x180005c58  mov     rdi, rax
0x180005c5b  test    rax, rax
0x180005c5e  jz      loc_180005DF1
0x180005c64  xor     r8d, r8d; int
0x180005c67  mov     rcx, rax; this
0x180005c6a  lea     edx, [r8+1]; enum _SE_OBJECT_TYPE
0x180005c6e  call    ??0CNTFSSecurity@@QEAA@W4_SE_OBJECT_TYPE@@H@Z; CNTFSSecurity::CNTFSSecurity(_SE_OBJECT_TYPE,int)
0x180005c73  mov     rdx, [rbp+1F0h+var_270]; unsigned __int16 *
0x180005c77  lea     rax, ??_7CFSSecurity@@6BISecurityInformation@@@; const CFSSecurity::`vftable'{for `ISecurityInformation'}
0x180005c7e  mov     [rdi], rax
0x180005c81  lea     rcx, [rsp+2F0h+var_280]; unsigned __int16 **
0x180005c86  lea     rax, ??_7CSecurityInformation@@6BIEffectivePermission@@@; const CSecurityInformation::`vftable'{for `IEffectivePermission'}
0x180005c8d  mov     [rdi+278h], r15
0x180005c94  mov     [rdi+8], rax
0x180005c98  lea     rax, ??_7CFSSecurity@@6BIEffectivePermission2@@@; const CFSSecurity::`vftable'{for `IEffectivePermission2'}
0x180005c9f  mov     [rdi+10h], rax
0x180005ca3  lea     rax, ??_7CNTFSSecurity@@6BISecurityObjectTypeInfo@@@; const CNTFSSecurity::`vftable'{for `ISecurityObjectTypeInfo'}
0x180005caa  mov     [rdi+18h], rax
0x180005cae  lea     rax, ??_7CFSSecurity@@6BISecurityInformation3@@@; const CFSSecurity::`vftable'{for `ISecurityInformation3'}
0x180005cb5  mov     [rdi+20h], rax
0x180005cb9  lea     rax, ??_7CFSSecurity@@6BISecurityInformation4@@@; const CFSSecurity::`vftable'{for `ISecurityInformation4'}
0x180005cc0  mov     [rdi+28h], rax
0x180005cc4  call    ?LocalAllocString@@YAJPEAPEAGPEBG@Z; LocalAllocString(ushort * *,ushort const *)
0x180005cc9  mov     ebx, eax
0x180005ccb  test    eax, eax
0x180005ccd  js      loc_180005DE0
0x180005cd3  mov     rdx, r13; unsigned __int16 *
0x180005cd6  lea     rcx, [rsp+2F0h+var_288]; unsigned __int16 **
0x180005cdb  call    ?LocalAllocString@@YAJPEAPEAGPEBG@Z; LocalAllocString(ushort * *,ushort const *)
0x180005ce0  xor     r13d, r13d
0x180005ce3  mov     ebx, eax
0x180005ce5  test    eax, eax
0x180005ce7  js      loc_180005DE0
0x180005ced  mov     rdx, r14; unsigned __int16 *
0x180005cf0  lea     rcx, [rsp+2F0h+var_278]; unsigned __int16 **
0x180005cf5  call    ?LocalAllocString@@YAJPEAPEAGPEBG@Z; LocalAllocString(ushort * *,ushort const *)
0x180005cfa  mov     ebx, eax
0x180005cfc  test    eax, eax
0x180005cfe  js      loc_180005DE0
0x180005d04  test    r12, r12
0x180005d07  jz      short loc_180005D25
0x180005d09  mov     rdx, r12; unsigned __int16 *
0x180005d0c  lea     rcx, [rsp+2F0h+var_290]; unsigned __int16 **
0x180005d11  call    ?LocalAllocString@@YAJPEAPEAGPEBG@Z; LocalAllocString(ushort * *,ushort const *)
0x180005d16  mov     ebx, eax
0x180005d18  test    eax, eax
0x180005d1a  js      loc_180005DE0
0x180005d20  mov     r15, [rsp+2F0h+var_290]
0x180005d25  mov     eax, [rsp+2F0h+var_2A0]
0x180005d29  mov     rcx, rdi; this
0x180005d2c  mov     r9, [rsp+2F0h+var_280]; unsigned __int16 *
0x180005d31  mov     r8d, [rsp+2F0h+var_2B0]; unsigned int
0x180005d36  mov     rdx, [rsp+2F0h+var_278]; unsigned __int16 *
0x180005d3b  mov     [rsp+2F0h+var_2B8], eax; int
0x180005d3f  mov     rax, [rsp+2F0h+var_2A8]
0x180005d44  mov     [rsp+2F0h+var_2C0], rax; void *
0x180005d49  mov     rax, [rsp+2F0h+var_288]
0x180005d4e  mov     [rsp+2F0h+var_2C8], r15; unsigned __int16 *
0x180005d53  mov     [rsp+2F0h+var_2D0], rax; unsigned __int16 *
0x180005d58  call    ?Initialize@CFSSecurity@@QEAAJPEAGK000PEAXH@Z; CFSSecurity::Initialize(ushort *,ulong,ushort *,ushort *,ushort *,void *,int)
0x180005d5d  mov     ebx, eax
0x180005d5f  test    eax, eax
0x180005d61  jnz     short loc_180005DD7
0x180005d63  mov     rdx, rdi; psi
0x180005d66  mov     rcx, [rsp+2F0h+hwndOwner]; hwndOwner
0x180005d6b  cmp     [rbp+1F0h+arg_28], r13d
0x180005d72  jz      short loc_180005DC6
0x180005d74  mov     r8d, 10000h; uSIPage
0x180005d7a  call    cs:__imp_EditSecurityAdvanced
0x180005d80  mov     ebx, eax
0x180005d82  test    eax, eax
0x180005d84  jnz     short loc_180005DE0
0x180005d86  test    rsi, rsi
0x180005d89  jz      short loc_180005DE0
0x180005d8b  mov     rcx, [rdi+278h]
0x180005d92  test    rcx, rcx
0x180005d95  jz      short loc_180005DE0
0x180005d97  cmp     [rcx+100h], r13
0x180005d9e  jz      short loc_180005DE0
0x180005da0  mov     rcx, [rcx+100h]; Src
0x180005da7  lea     rdx, [rsp+2F0h+hwndOwner]; void **
0x180005dac  mov     [rsp+2F0h+hwndOwner], r13
0x180005db1  call    ?MakeSelfRelativeSecurityDescriptor@@YAJPEAXPEAPEAX@Z; MakeSelfRelativeSecurityDescriptor(void *,void * *)
0x180005db6  mov     ebx, eax
0x180005db8  test    eax, eax
0x180005dba  jnz     short loc_180005DE0
0x180005dbc  mov     rax, [rsp+2F0h+hwndOwner]
0x180005dc1  mov     [rsi], rax
0x180005dc4  jmp     short loc_180005DE0
0x180005dc6  call    cs:__imp_EditSecurity
0x180005dcc  test    eax, eax
0x180005dce  jnz     short loc_180005D86
0x180005dd0  mov     ebx, 80004005h
0x180005dd5  jmp     short loc_180005DE0
0x180005dd7  mov     rcx, r15; hMem
0x180005dda  call    cs:__imp_LocalFree
0x180005de0  mov     rax, [rdi]
0x180005de3  mov     rcx, rdi
0x180005de6  mov     rax, [rax+10h]
0x180005dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005def  jmp     short loc_180005DFD
0x180005df1  mov     ebx, 8007000Eh
0x180005df6  jmp     short loc_180005DFD
0x180005df8  mov     ebx, 80004003h
0x180005dfd  mov     eax, ebx
0x180005dff  mov     rcx, [rbp+1F0h+var_50]
0x180005e06  xor     rcx, rsp; StackCookie
0x180005e09  call    __security_check_cookie
0x180005e0e  add     rsp, 2B8h
0x180005e15  pop     r15
0x180005e17  pop     r14
0x180005e19  pop     r13
0x180005e1b  pop     r12
0x180005e1d  pop     rdi
0x180005e1e  pop     rsi
0x180005e1f  pop     rbx
0x180005e20  pop     rbp
0x180005e21  retn
```
