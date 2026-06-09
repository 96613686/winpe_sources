# SxspGenerateManifestPathOnAssemblyIdentity(ushort const *,ushort *,ulong *,_ASSEMBLY_IDENTITY * *)

- ea: `0x180060390`
- end: `0x1800605cb`
- name: `?SxspGenerateManifestPathOnAssemblyIdentity@@YAHPEBGPEAGPEAKPEAPEAU_ASSEMBLY_IDENTITY@@@Z`
- size: `571`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int *, struct _ASSEMBLY_IDENTITY **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180014260`
- `0x18001c270`
- `0x180022d40`
- `0x180029380`
- `0x18002cc78`
- `0x18002d3dc`
- `0x180030950`
- `0x18005d2b0`
- `0x180060390`
- `0x180060cc0`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006044e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006047b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800604bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800604df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006053e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006044e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006047b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800604bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800604df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006053e`

## pseudocode

```c
__int64 __fastcall SxspGenerateManifestPathOnAssemblyIdentity(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int *a3,
        struct _ASSEMBLY_IDENTITY **a4)
{
  const char *v8; // rcx
  char **v9; // rcx
  struct _ASSEMBLY_IDENTITY *v10; // rbx
  char **v11; // rcx
  unsigned int v12; // ebx
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h]
  __int64 *v18; // [rsp+60h] [rbp-A0h]
  __int64 v19; // [rsp+68h] [rbp-98h]
  int v20; // [rsp+70h] [rbp-90h]
  int *v21; // [rsp+78h] [rbp-88h]
  _BYTE v22[16]; // [rsp+80h] [rbp-80h] BYREF
  int v23[2]; // [rsp+90h] [rbp-70h]
  int v24[2]; // [rsp+A0h] [rbp-60h]
  __int64 v25[70]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v15 = 0;
  v18 = &qword_180074CB0;
  v16 = 1;
  v21 = &v15;
  v17 = 0;
  v19 = 544438355;
  v20 = 4574;
  CFrame::BaseEnter((CFrame *)&v16);
  lpMem = 0;
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v25);
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v22);
  if ( a4 )
    *a4 = 0;
  if ( !a1 )
  {
    v20 = 4582;
LABEL_5:
    FusionpTraceParameterCheck(v8);
    SetLastError(0x57u);
    *v21 = 0;
    goto LABEL_23;
  }
  if ( !a3 )
  {
    v20 = 4583;
    goto LABEL_5;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspCreateAssemblyIdentityFromTextualString(a1, (struct _ASSEMBLY_IDENTITY **)&lpMem) )
  {
    v9 = off_180074C90;
LABEL_10:
    *v21 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v9);
    v10 = (struct _ASSEMBLY_IDENTITY *)lpMem;
    goto LABEL_21;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspGetAssemblyRootDirectory((__int64)v22) )
  {
    v9 = off_180074C70;
    goto LABEL_10;
  }
  SetLastError(0);
  v10 = (struct _ASSEMBLY_IDENTITY *)lpMem;
  if ( (unsigned int)SxspGenerateSxsPath(
                       1,
                       2,
                       *(const void **)v23,
                       *(size_t *)v24,
                       (struct _ASSEMBLY_IDENTITY *)lpMem,
                       0,
                       (__int64)v25) )
  {
    SetLastError(0);
    if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyStringOut(v25, a2, a3) )
    {
      if ( a4 )
      {
        *a4 = v10;
        v10 = 0;
      }
      v15 = 1;
      goto LABEL_21;
    }
    v11 = off_180074C30;
  }
  else
  {
    v11 = off_180074C50;
  }
  *v21 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v11);
LABEL_21:
  if ( v10 )
    SxsDestroyAssemblyIdentity(v10);
LABEL_23:
  v12 = v15;
  CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v22);
  CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v25);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v16);
  return v12;
}

```

## disassembly

```asm
0x180060390  push    rbp
0x180060392  push    rbx
0x180060393  push    rsi
0x180060394  push    rdi
0x180060395  push    r14
0x180060397  lea     rbp, [rsp-3F0h]
0x18006039f  sub     rsp, 4F0h
0x1800603a6  mov     rax, cs:__security_cookie
0x1800603ad  xor     rax, rsp
0x1800603b0  mov     [rbp+410h+var_30], rax
0x1800603b7  lea     rax, qword_180074CB0
0x1800603be  mov     [rsp+510h+var_4C8], 0
0x1800603c6  mov     [rsp+510h+var_4B0], rax
0x1800603cb  mov     rbx, rcx
0x1800603ce  lea     rax, [rsp+510h+var_4C8]
0x1800603d3  mov     [rsp+510h+var_4C0], 1
0x1800603db  lea     rcx, [rsp+510h+var_4C0]; this
0x1800603e0  mov     [rsp+510h+var_498], rax
0x1800603e5  mov     rdi, r9
0x1800603e8  mov     [rsp+510h+var_4B8], 0
0x1800603f1  mov     rsi, r8
0x1800603f4  mov     [rsp+510h+var_4A8], 20737853h
0x1800603fd  mov     r14, rdx
0x180060400  mov     [rsp+510h+var_4A0], 11DEh
0x180060408  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18006040d  lea     rcx, [rbp+410h+var_260]; void *
0x180060414  mov     [rsp+510h+lpMem], 0
0x18006041d  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x180060422  lea     rcx, [rbp+410h+var_490]; void *
0x180060426  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18006042b  test    rdi, rdi
0x18006042e  jz      short loc_180060437
0x180060430  mov     qword ptr [rdi], 0
0x180060437  test    rbx, rbx
0x18006043a  jnz     short loc_18006046A
0x18006043c  mov     [rsp+510h+var_4A0], 11E6h
0x180060444  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180060449  mov     ecx, 57h ; 'W'; dwErrCode
0x18006044e  call    cs:__imp_SetLastError
0x180060455  nop     dword ptr [rax+rax+00h]
0x18006045a  mov     rax, [rsp+510h+var_498]
0x18006045f  mov     dword ptr [rax], 0
0x180060465  jmp     loc_180060588
0x18006046a  test    rsi, rsi
0x18006046d  jnz     short loc_180060479
0x18006046f  mov     [rsp+510h+var_4A0], 11E7h
0x180060477  jmp     short loc_180060444
0x180060479  xor     ecx, ecx; dwErrCode
0x18006047b  call    cs:__imp_SetLastError
0x180060482  nop     dword ptr [rax+rax+00h]
0x180060487  lea     rdx, [rsp+510h+lpMem]
0x18006048c  mov     rcx, rbx
0x18006048f  call    SxspCreateAssemblyIdentityFromTextualString
0x180060494  test    eax, eax
0x180060496  jnz     short loc_1800604B9
0x180060498  lea     rcx, off_180074C90; struct _CALL_SITE_INFO *
0x18006049f  mov     rax, [rsp+510h+var_498]
0x1800604a4  mov     dword ptr [rax], 0
0x1800604aa  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x1800604af  mov     rbx, [rsp+510h+lpMem]
0x1800604b4  jmp     loc_18006057B
0x1800604b9  xor     ecx, ecx; dwErrCode
0x1800604bb  call    cs:__imp_SetLastError
0x1800604c2  nop     dword ptr [rax+rax+00h]
0x1800604c7  lea     rcx, [rbp+410h+var_490]
0x1800604cb  call    ?SxspGetAssemblyRootDirectory@@YAHAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspGetAssemblyRootDirectory(CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x1800604d0  test    eax, eax
0x1800604d2  jnz     short loc_1800604DD
0x1800604d4  lea     rcx, off_180074C70; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x1800604db  jmp     short loc_18006049F
0x1800604dd  xor     ecx, ecx; dwErrCode
0x1800604df  call    cs:__imp_SetLastError
0x1800604e6  nop     dword ptr [rax+rax+00h]
0x1800604eb  mov     rbx, [rsp+510h+lpMem]
0x1800604f0  lea     rax, [rbp+410h+var_260]
0x1800604f7  mov     r9, qword ptr [rbp+410h+var_470]; int
0x1800604fb  mov     edx, 2; int
0x180060500  mov     r8, qword ptr [rbp+410h+var_480]; int
0x180060504  mov     [rsp+510h+var_4E0], rax; __int64
0x180060509  mov     qword ptr [rsp+510h+var_4E8], 0; int
0x180060512  lea     ecx, [rdx-1]; int
0x180060515  mov     [rsp+510h+var_4F0], rbx; struct _ASSEMBLY_IDENTITY *
0x18006051a  call    ?SxspGenerateSxsPath@@YAHKKPEBG_KPEBU_ASSEMBLY_IDENTITY@@PEAU_PROBING_ATTRIBUTE_CACHE@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspGenerateSxsPath(ulong,ulong,ushort const *,unsigned __int64,_ASSEMBLY_IDENTITY const *,_PROBING_ATTRIBUTE_CACHE *,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18006051f  test    eax, eax
0x180060521  jnz     short loc_18006053C
0x180060523  lea     rcx, off_180074C50; struct _CALL_SITE_INFO *
0x18006052a  mov     rax, [rsp+510h+var_498]
0x18006052f  mov     dword ptr [rax], 0
0x180060535  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18006053a  jmp     short loc_18006057B
0x18006053c  xor     ecx, ecx; dwErrCode
0x18006053e  call    cs:__imp_SetLastError
0x180060545  nop     dword ptr [rax+rax+00h]
0x18006054a  mov     r8, rsi
0x18006054d  lea     rcx, [rbp+410h+var_260]
0x180060554  mov     rdx, r14
0x180060557  call    ?Win32CopyStringOut@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEAGPEAK@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyStringOut(ushort *,ulong *)
0x18006055c  test    eax, eax
0x18006055e  jnz     short loc_180060569
0x180060560  lea     rcx, off_180074C30; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x180060567  jmp     short loc_18006052A
0x180060569  test    rdi, rdi
0x18006056c  jz      short loc_180060573
0x18006056e  mov     [rdi], rbx
0x180060571  xor     ebx, ebx
0x180060573  mov     [rsp+510h+var_4C8], 1
0x18006057b  test    rbx, rbx
0x18006057e  jz      short loc_180060588
0x180060580  mov     rcx, rbx; lpMem
0x180060583  call    SxsDestroyAssemblyIdentity
0x180060588  mov     ebx, [rsp+510h+var_4C8]
0x18006058c  lea     rcx, [rbp+410h+var_490]; void *
0x180060590  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x180060595  lea     rcx, [rbp+410h+var_260]; void *
0x18006059c  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x1800605a1  lea     rcx, [rsp+510h+var_4C0]; this
0x1800605a6  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x1800605ab  mov     eax, ebx
0x1800605ad  mov     rcx, [rbp+410h+var_30]
0x1800605b4  xor     rcx, rsp; StackCookie
0x1800605b7  call    __security_check_cookie
0x1800605bc  add     rsp, 4F0h
0x1800605c3  pop     r14
0x1800605c5  pop     rdi
0x1800605c6  pop     rsi
0x1800605c7  pop     rbx
0x1800605c8  pop     rbp
0x1800605c9  retn
```
