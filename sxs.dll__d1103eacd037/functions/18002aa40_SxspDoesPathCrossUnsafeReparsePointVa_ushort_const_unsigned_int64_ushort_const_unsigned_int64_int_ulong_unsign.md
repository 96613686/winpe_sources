# SxspDoesPathCrossUnsafeReparsePointVa(ushort const *,unsigned __int64,ushort const *,unsigned __int64,int &,ulong &,unsigned __int64,char *)

- ea: `0x18002aa40`
- end: `0x18002ae2f`
- name: `?SxspDoesPathCrossUnsafeReparsePointVa@@YAHPEBG_K01AEAHAEAK1PEAD@Z`
- size: `1007`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, unsigned __int64@<rdx>, const unsigned __int16 *@<r8>, unsigned __int64@<r9>, int *, unsigned int *, unsigned __int64, char *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18002b63c`

## callees

- `0x1800075a0`
- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x180013150`
- `0x180013af0`
- `0x180014260`
- `0x18001c270`
- `0x18001e5d0`
- `0x180020820`
- `0x180029380`
- `0x18002a7b4`
- `0x18002aa40`
- `0x18002ae38`
- `0x180033b50`
- `0x180057b54`
- `0x18005d2b0`
- `0x18005d38c`
- `0x1800607ac`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ab05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ab67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aba1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002abfe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ac2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ac55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ad54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ad62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002adcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ab05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ab67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aba1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002abfe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ac2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ac55`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ad54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ad62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002adcc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002ac7e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002ac7e`

## pseudocode

```c
__int64 __fastcall SxspDoesPathCrossUnsafeReparsePointVa(
        WCHAR *a1,
        unsigned __int64 a2,
        WCHAR *a3,
        unsigned __int64 a4,
        int *a5,
        unsigned int *a6,
        unsigned __int64 a7,
        char *a8)
{
  const char *v12; // rcx
  char **v13; // rcx
  char **v14; // rcx
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  char *v17; // rcx
  unsigned __int64 j; // rdx
  DWORD v19; // eax
  char **v20; // rcx
  char *v21; // rcx
  unsigned __int64 i; // rdx
  DWORD v23; // eax
  unsigned int v24; // ebx
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h]
  __int64 *v28; // [rsp+40h] [rbp-C0h]
  __int64 v29; // [rsp+48h] [rbp-B8h]
  int v30; // [rsp+50h] [rbp-B0h]
  unsigned int *v31; // [rsp+58h] [rbp-A8h]
  int v32; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v33[2]; // [rsp+70h] [rbp-90h] BYREF
  char *v34; // [rsp+80h] [rbp-80h]
  __int64 v35; // [rsp+90h] [rbp-70h]
  char v36; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v37[16]; // [rsp+120h] [rbp+20h] BYREF
  LPCWSTR lpFileName; // [rsp+130h] [rbp+30h]
  __int64 v39; // [rsp+140h] [rbp+40h]
  _BYTE v40[32]; // [rsp+350h] [rbp+250h] BYREF
  __int64 v41; // [rsp+370h] [rbp+270h]

  v28 = &qword_180070170;
  v26 = 1;
  v31 = (unsigned int *)&v32;
  v32 = 0;
  v27 = 0;
  v29 = 544438355;
  v30 = 2975;
  CFrame::BaseEnter((CFrame *)&v26);
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v37);
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v40);
  *a5 = 0;
  *a6 = 0;
  if ( !a1 && a2 )
  {
    v30 = 2987;
LABEL_4:
    FusionpTraceParameterCheck(v12);
    SetLastError(0x57u);
    *v31 = 0;
    goto LABEL_47;
  }
  if ( !a3 )
  {
    v30 = 2988;
    goto LABEL_4;
  }
  if ( a2 > a4 )
  {
    v30 = 2989;
    goto LABEL_4;
  }
  if ( a1 && FusionpCompareStrings(a1, a2, a3, a2, 1u) )
  {
    v30 = 3004;
    goto LABEL_4;
  }
  SetLastError(0);
  if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(v37, a1, a2) )
  {
    v13 = off_180075470;
LABEL_14:
    *v31 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v13);
    goto LABEL_47;
  }
  SetLastError(0);
  if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(v40, &a3[a2], a4 - a2) )
  {
    v13 = off_180075450;
    goto LABEL_14;
  }
  CGenericBaseStringBuffer<CUnicodeCharTraits>::RemoveLeadingPathSeparators(v40);
  while ( v41 && !*a5 )
  {
    CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v33);
    SetLastError(0);
    if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32GetFirstPathElement(v40, v33) )
    {
      v14 = off_180075430;
      goto LABEL_44;
    }
    if ( v39 )
    {
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32AppendPathElement(v37, v34, v35) )
      {
        v14 = off_1800753F0;
        goto LABEL_44;
      }
    }
    else
    {
      SetLastError(0);
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(v37, v33) )
      {
        v14 = off_180075410;
LABEL_44:
        *v31 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v14);
        goto LABEL_45;
      }
    }
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      v21 = a8;
      for ( i = a7; i; --i )
      {
        if ( LastError == *(_DWORD *)v21 )
        {
LABEL_39:
          *a6 = LastError;
          SetLastError(0);
          SetLastError(0);
          *v31 = 1;
          goto LABEL_45;
        }
        v21 += 8;
      }
      v23 = GetLastError();
      CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v26, v23);
      v20 = off_1800753D0;
LABEL_41:
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)v20);
LABEL_45:
      CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v33);
      goto LABEL_47;
    }
    if ( (FileAttributesW & 0x400) != 0 && !(unsigned int)SxspIsReparsePointUnsafe(lpFileName, a5) )
    {
      LastError = GetLastError();
      v17 = a8;
      for ( j = a7; j; --j )
      {
        if ( LastError == *(_DWORD *)v17 )
          goto LABEL_39;
        v17 += 8;
      }
      v19 = GetLastError();
      CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v26, v19);
      v20 = off_1800753B0;
      goto LABEL_41;
    }
    v33[0] = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
    if ( v34 != &v36 )
      CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(v33);
  }
  SetLastError(0);
  *v31 = 1;
LABEL_47:
  v24 = *v31;
  CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v40);
  CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v37);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v26);
  return v24;
}

```

## disassembly

```asm
0x18002aa40  push    rbp
0x18002aa42  push    rbx
0x18002aa43  push    rsi
0x18002aa44  push    rdi
0x18002aa45  push    r12
0x18002aa47  push    r13
0x18002aa49  push    r14
0x18002aa4b  push    r15
0x18002aa4d  lea     rbp, [rsp-498h]
0x18002aa55  sub     rsp, 598h
0x18002aa5c  mov     rax, cs:__security_cookie
0x18002aa63  xor     rax, rsp
0x18002aa66  mov     [rbp+4D0h+var_50], rax
0x18002aa6d  mov     r15, [rbp+4D0h+arg_20]
0x18002aa74  lea     rax, qword_180070170
0x18002aa7b  mov     r12, [rbp+4D0h+arg_28]
0x18002aa82  mov     rsi, rcx
0x18002aa85  mov     [rsp+5D0h+var_590], rax
0x18002aa8a  lea     rcx, [rsp+5D0h+var_5A0]; this
0x18002aa8f  lea     rax, [rsp+5D0h+var_570]
0x18002aa94  mov     [rsp+5D0h+var_5A0], 1
0x18002aa9c  xor     r13d, r13d
0x18002aa9f  mov     [rsp+5D0h+var_578], rax
0x18002aaa4  mov     rdi, r9
0x18002aaa7  mov     [rsp+5D0h+var_570], r13d
0x18002aaac  mov     r14, r8
0x18002aaaf  mov     [rsp+5D0h+var_598], r13
0x18002aab4  mov     rbx, rdx
0x18002aab7  mov     [rsp+5D0h+var_588], 20737853h
0x18002aac0  mov     [rsp+5D0h+var_580], 0B9Fh
0x18002aac8  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18002aacd  lea     rcx, [rbp+4D0h+var_4B0]; void *
0x18002aad1  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18002aad6  lea     rcx, [rbp+4D0h+var_280]; void *
0x18002aadd  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18002aae2  mov     [r15], r13d
0x18002aae5  mov     [r12], r13d
0x18002aae9  test    rsi, rsi
0x18002aaec  jnz     short loc_18002AB1E
0x18002aaee  test    rbx, rbx
0x18002aaf1  jz      short loc_18002AB1E
0x18002aaf3  mov     [rsp+5D0h+var_580], 0BABh
0x18002aafb  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18002ab00  mov     ecx, 57h ; 'W'; dwErrCode
0x18002ab05  call    cs:__imp_SetLastError
0x18002ab0c  nop     dword ptr [rax+rax+00h]
0x18002ab11  mov     rax, [rsp+5D0h+var_578]
0x18002ab16  mov     [rax], r13d
0x18002ab19  jmp     loc_18002ADE3
0x18002ab1e  test    r14, r14
0x18002ab21  jnz     short loc_18002AB2D
0x18002ab23  mov     [rsp+5D0h+var_580], 0BACh
0x18002ab2b  jmp     short loc_18002AAFB
0x18002ab2d  cmp     rbx, rdi
0x18002ab30  jbe     short loc_18002AB3C
0x18002ab32  mov     [rsp+5D0h+var_580], 0BADh
0x18002ab3a  jmp     short loc_18002AAFB
0x18002ab3c  test    rsi, rsi
0x18002ab3f  jz      short loc_18002AB65
0x18002ab41  mov     r9, rbx; unsigned __int64
0x18002ab44  mov     [rsp+5D0h+var_5B0], 1; bool
0x18002ab49  mov     r8, r14; unsigned __int16 *
0x18002ab4c  mov     rdx, rbx; unsigned __int64
0x18002ab4f  mov     rcx, rsi; unsigned __int16 *
0x18002ab52  call    ?FusionpCompareStrings@@YAHPEBG_K01_N@Z; FusionpCompareStrings(ushort const *,unsigned __int64,ushort const *,unsigned __int64,bool)
0x18002ab57  test    eax, eax
0x18002ab59  jz      short loc_18002AB65
0x18002ab5b  mov     [rsp+5D0h+var_580], 0BBCh
0x18002ab63  jmp     short loc_18002AAFB
0x18002ab65  xor     ecx, ecx; dwErrCode
0x18002ab67  call    cs:__imp_SetLastError
0x18002ab6e  nop     dword ptr [rax+rax+00h]
0x18002ab73  mov     r8, rbx
0x18002ab76  lea     rcx, [rbp+4D0h+var_4B0]
0x18002ab7a  mov     rdx, rsi
0x18002ab7d  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)
0x18002ab82  test    eax, eax
0x18002ab84  jnz     short loc_18002AB9F
0x18002ab86  lea     rcx, off_180075470; struct _CALL_SITE_INFO *
0x18002ab8d  mov     rax, [rsp+5D0h+var_578]
0x18002ab92  mov     [rax], r13d
0x18002ab95  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002ab9a  jmp     loc_18002ADE3
0x18002ab9f  xor     ecx, ecx; dwErrCode
0x18002aba1  call    cs:__imp_SetLastError
0x18002aba8  nop     dword ptr [rax+rax+00h]
0x18002abad  sub     rdi, rbx
0x18002abb0  lea     rdx, [r14+rbx*2]
0x18002abb4  mov     r8, rdi
0x18002abb7  lea     rcx, [rbp+4D0h+var_280]
0x18002abbe  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)
0x18002abc3  test    eax, eax
0x18002abc5  jnz     short loc_18002ABD0
0x18002abc7  lea     rcx, off_180075450; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18002abce  jmp     short loc_18002AB8D
0x18002abd0  lea     rcx, [rbp+4D0h+var_280]
0x18002abd7  call    ?RemoveLeadingPathSeparators@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::RemoveLeadingPathSeparators(void)
0x18002abdc  cmp     [rbp+4D0h+var_260], r13
0x18002abe3  jz      loc_18002ADCA
0x18002abe9  cmp     [r15], r13d
0x18002abec  jnz     loc_18002ADCA
0x18002abf2  lea     rcx, [rsp+5D0h+var_560]
0x18002abf7  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18002abfc  xor     ecx, ecx; dwErrCode
0x18002abfe  call    cs:__imp_SetLastError
0x18002ac05  nop     dword ptr [rax+rax+00h]
0x18002ac0a  lea     rdx, [rsp+5D0h+var_560]
0x18002ac0f  lea     rcx, [rbp+4D0h+var_280]
0x18002ac16  call    ?Win32GetFirstPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHAEAV1@H@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32GetFirstPathElement(CGenericBaseStringBuffer<CUnicodeCharTraits> &,int)
0x18002ac1b  test    eax, eax
0x18002ac1d  jz      loc_18002ADAA
0x18002ac23  xor     ecx, ecx; dwErrCode
0x18002ac25  cmp     [rbp+4D0h+var_490], r13
0x18002ac29  jnz     short loc_18002AC55
0x18002ac2b  call    cs:__imp_SetLastError
0x18002ac32  nop     dword ptr [rax+rax+00h]
0x18002ac37  lea     rdx, [rsp+5D0h+var_560]
0x18002ac3c  lea     rcx, [rbp+4D0h+var_4B0]
0x18002ac40  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHAEBV1@@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(CGenericBaseStringBuffer<CUnicodeCharTraits> const &)
0x18002ac45  test    eax, eax
0x18002ac47  jnz     short loc_18002AC7A
0x18002ac49  lea     rcx, off_180075410; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18002ac50  jmp     loc_18002ADB1
0x18002ac55  call    cs:__imp_SetLastError
0x18002ac5c  nop     dword ptr [rax+rax+00h]
0x18002ac61  mov     r8, [rbp+4D0h+var_540]
0x18002ac65  lea     rcx, [rbp+4D0h+var_4B0]
0x18002ac69  mov     rdx, [rbp+4D0h+var_550]
0x18002ac6d  call    ?Win32AppendPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32AppendPathElement(ushort const *,unsigned __int64)
0x18002ac72  test    eax, eax
0x18002ac74  jz      loc_18002ADA1
0x18002ac7a  mov     rcx, [rbp+4D0h+lpFileName]; lpFileName
0x18002ac7e  call    cs:__imp_GetFileAttributesW
0x18002ac85  nop     dword ptr [rax+rax+00h]
0x18002ac8a  cmp     eax, 0FFFFFFFFh
0x18002ac8d  jz      loc_18002AD22
0x18002ac93  bt      eax, 0Ah
0x18002ac97  jnb     short loc_18002ACA9
0x18002ac99  mov     rcx, [rbp+4D0h+lpFileName]; lpFileName
0x18002ac9d  mov     rdx, r15; int *
0x18002aca0  call    ?SxspIsReparsePointUnsafe@@YAHPEBGPEAH@Z; SxspIsReparsePointUnsafe(ushort const *,int *)
0x18002aca5  test    eax, eax
0x18002aca7  jz      short loc_18002ACD5
0x18002aca9  mov     rdx, [rbp+4D0h+var_550]
0x18002acad  lea     rax, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x18002acb4  mov     [rsp+5D0h+var_560], rax
0x18002acb9  lea     rax, [rbp+4D0h+var_538]
0x18002acbd  cmp     rdx, rax
0x18002acc0  jz      loc_18002ABDC
0x18002acc6  lea     rcx, [rsp+5D0h+var_560]
0x18002accb  call    ?DeallocateBuffer@?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@MEBAXPEAG@Z; CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(ushort *)
0x18002acd0  jmp     loc_18002ABDC
0x18002acd5  call    cs:__imp_GetLastError
0x18002acdc  nop     dword ptr [rax+rax+00h]
0x18002ace1  mov     rcx, [rbp+4D0h+arg_38]
0x18002ace8  mov     rdx, [rbp+4D0h+arg_30]
0x18002acef  test    rdx, rdx
0x18002acf2  jz      short loc_18002AD01
0x18002acf4  cmp     eax, [rcx]
0x18002acf6  jz      short loc_18002AD4E
0x18002acf8  add     rcx, 8
0x18002acfc  dec     rdx
0x18002acff  jmp     short loc_18002ACEF
0x18002ad01  call    cs:__imp_GetLastError
0x18002ad08  nop     dword ptr [rax+rax+00h]
0x18002ad0d  mov     edx, eax; unsigned int
0x18002ad0f  lea     rcx, [rsp+5D0h+var_5A0]; this
0x18002ad14  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x18002ad19  lea     rcx, off_1800753B0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18002ad20  jmp     short loc_18002AD9A
0x18002ad22  call    cs:__imp_GetLastError
0x18002ad29  nop     dword ptr [rax+rax+00h]
0x18002ad2e  mov     rcx, [rbp+4D0h+arg_38]
0x18002ad35  mov     rdx, [rbp+4D0h+arg_30]
0x18002ad3c  test    rdx, rdx
0x18002ad3f  jz      short loc_18002AD7B
0x18002ad41  cmp     eax, [rcx]
0x18002ad43  jz      short loc_18002AD4E
0x18002ad45  add     rcx, 8
0x18002ad49  dec     rdx
0x18002ad4c  jmp     short loc_18002AD3C
0x18002ad4e  xor     ecx, ecx; dwErrCode
0x18002ad50  mov     [r12], eax
0x18002ad54  call    cs:__imp_SetLastError
0x18002ad5b  nop     dword ptr [rax+rax+00h]
0x18002ad60  xor     ecx, ecx; dwErrCode
0x18002ad62  call    cs:__imp_SetLastError
0x18002ad69  nop     dword ptr [rax+rax+00h]
0x18002ad6e  mov     rax, [rsp+5D0h+var_578]
0x18002ad73  mov     dword ptr [rax], 1
0x18002ad79  jmp     short loc_18002ADBE
0x18002ad7b  call    cs:__imp_GetLastError
0x18002ad82  nop     dword ptr [rax+rax+00h]
0x18002ad87  mov     edx, eax; unsigned int
0x18002ad89  lea     rcx, [rsp+5D0h+var_5A0]; this
0x18002ad8e  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x18002ad93  lea     rcx, off_1800753D0; struct _CALL_SITE_INFO *
0x18002ad9a  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18002ad9f  jmp     short loc_18002ADBE
0x18002ada1  lea     rcx, off_1800753F0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18002ada8  jmp     short loc_18002ADB1
0x18002adaa  lea     rcx, off_180075430; struct _CALL_SITE_INFO *
0x18002adb1  mov     rax, [rsp+5D0h+var_578]
0x18002adb6  mov     [rax], r13d
0x18002adb9  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002adbe  lea     rcx, [rsp+5D0h+var_560]
0x18002adc3  call    ??1?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18002adc8  jmp     short loc_18002ADE3
0x18002adca  xor     ecx, ecx; dwErrCode
0x18002adcc  call    cs:__imp_SetLastError
0x18002add3  nop     dword ptr [rax+rax+00h]
0x18002add8  mov     rax, [rsp+5D0h+var_578]
0x18002addd  mov     dword ptr [rax], 1
0x18002ade3  mov     rax, [rsp+5D0h+var_578]
0x18002ade8  lea     rcx, [rbp+4D0h+var_280]; void *
0x18002adef  mov     ebx, [rax]
0x18002adf1  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18002adf6  lea     rcx, [rbp+4D0h+var_4B0]; void *
0x18002adfa  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x18002adff  lea     rcx, [rsp+5D0h+var_5A0]; this
0x18002ae04  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18002ae09  mov     eax, ebx
0x18002ae0b  mov     rcx, [rbp+4D0h+var_50]
0x18002ae12  xor     rcx, rsp; StackCookie
0x18002ae15  call    __security_check_cookie
0x18002ae1a  add     rsp, 598h
0x18002ae21  pop     r15
0x18002ae23  pop     r14
0x18002ae25  pop     r13
0x18002ae27  pop     r12
0x18002ae29  pop     rdi
0x18002ae2a  pop     rsi
0x18002ae2b  pop     rbx
0x18002ae2c  pop     rbp
0x18002ae2d  retn
```
