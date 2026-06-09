# CUserProfile::AssembleThePath(ushort *,IUserName *,ushort * *)

- ea: `0x18006a9d0`
- end: `0x18006ac54`
- name: `?AssembleThePath@CUserProfile@@CAJPEAGPEAUIUserName@@PEAPEAG@Z`
- size: `644`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct IUserName *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006b838`

## callees

- `0x18000a210`
- `0x180014a2c`
- `0x180015ab0`
- `0x18006a9d0`
- `0x18006b704`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18006aaa9`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18006aaa9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ab61`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ab61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ac0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ac0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ac25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ac34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ac25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ac34`

## string_xrefs

- `0x18006ab3c`: `CUserProfile::AssembleThePath`
- `0x18006abf6`: `CUserProfile::AssembleThePath`
- `0x18006aa8f`: `StringCchLength(wszPrePath) failed: 0x%x in %s`
- `0x18006abef`: `VerifyThePath failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUserProfile::AssembleThePath(unsigned __int16 *a1, struct IUserName *a2, unsigned __int16 **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct IUserName *, LPVOID *); // rax
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  int v10; // eax
  unsigned __int64 i; // rdi
  int v12; // eax
  int v13; // eax
  int v14; // r12d
  unsigned __int64 v15; // r13
  const char *v16; // rdx
  unsigned __int16 v17; // r15
  unsigned __int16 *v18; // rdi
  unsigned __int64 v19; // rdx
  int v20; // eax
  unsigned __int64 v22; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int64 v24; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int16 **v26; // [rsp+A0h] [rbp+50h]
  unsigned __int16 *v27; // [rsp+A8h] [rbp+58h] BYREF

  v26 = a3;
  v3 = *(_QWORD *)a2;
  pv = 0;
  v27 = 0;
  v22 = 0;
  v6 = *(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(v3 + 40);
  v24 = 0;
  v23 = 0;
  *a3 = 0;
  v7 = v6(a2, &pv);
  v8 = v7;
  if ( v7 < 0 )
  {
    _DbgPrintMessage(8, "IUserName->GetUserStr failed: 0x%x in %s", (unsigned int)v7, "CUserProfile::AssembleThePath");
    goto LABEL_31;
  }
  v9 = (*(__int64 (__fastcall **)(struct IUserName *, unsigned __int16 **))(*(_QWORD *)a2 + 48LL))(a2, &v27);
  v8 = v9;
  if ( v9 < 0 )
  {
    _DbgPrintMessage(8, "IUserName->GetDomainStr failed: 0x%x in %s", (unsigned int)v9, "CUserProfile::AssembleThePath");
    goto LABEL_31;
  }
  v10 = StringCchLengthW(a1, 0x101u, &v22);
  v8 = v10;
  if ( v10 < 0 )
  {
    _DbgPrintMessage(
      8,
      "StringCchLength(wszPrePath) failed: 0x%x in %s",
      (unsigned int)v10,
      "CUserProfile::AssembleThePath");
    goto LABEL_31;
  }
  for ( i = v22; i; --i )
  {
    if ( !(unsigned int)_o_iswspace(a1[i - 1]) )
      break;
  }
  a1[i] = 0;
  if ( !i )
  {
    v8 = -2147024809;
    goto LABEL_31;
  }
  v12 = StringCchLengthW((const unsigned __int16 *)pv, 0x15u, &v24);
  v8 = v12;
  if ( v12 < 0 )
  {
    _DbgPrintMessage(
      8,
      "StringCchLength(wszUserName) failed: 0x%x in %s",
      (unsigned int)v12,
      "CUserProfile::AssembleThePath");
    goto LABEL_31;
  }
  v13 = StringCchLengthW(v27, 0x12u, &v23);
  v8 = v13;
  if ( v13 < 0 )
  {
    _DbgPrintMessage(
      8,
      "StringCchLength(wszDomain) failed: 0x%x in %s",
      (unsigned int)v13,
      "CUserProfile::AssembleThePath");
    goto LABEL_31;
  }
  v14 = v23;
  v15 = i + v23 + v24;
  if ( v15 + 3 <= 0x101 )
  {
    v17 = a1[i - 1];
    v18 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v15 + 3));
    if ( v18 )
    {
      v19 = v15 + 3;
      if ( v17 == 92 )
      {
        v8 = StringCchPrintfW(v18, v19, L"%s%s.%s", a1, pv, v27);
        v20 = 1;
      }
      else
      {
        v8 = StringCchPrintfW(v18, v19, L"%s%\\%s.%s", a1, pv, v27);
        v20 = 2;
      }
      if ( v8 >= 0 )
      {
        v8 = CUserProfile::VerifyThePath(a2, v18, v20 + (int)v15 - v14 - 1);
        if ( v8 >= 0 )
        {
          *v26 = v18;
          goto LABEL_31;
        }
        _DbgPrintMessage(8, "VerifyThePath failed: 0x%x in %s", (unsigned int)v8, "CUserProfile::AssembleThePath");
      }
      else
      {
        _DbgPrintMessage(8, "StringCchPrintf failed: 0x%x in %s", (unsigned int)v8, "CUserProfile::AssembleThePath");
      }
      LocalFree(v18);
      goto LABEL_31;
    }
    v8 = -2147024882;
    v16 = "memory allocation failed: 0x%x in %s";
  }
  else
  {
    v8 = -2147024883;
    v16 = "string size calculation failed: 0x%x in %s";
  }
  _DbgPrintMessage(8, v16, (unsigned int)v8, "CUserProfile::AssembleThePath");
LABEL_31:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v27 )
    CoTaskMemFree(v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006a9d0  mov     [rsp-38h+arg_0], rbx
0x18006a9d5  mov     [rsp-38h+arg_10], r8
0x18006a9da  push    rbp
0x18006a9db  push    rsi
0x18006a9dc  push    rdi
0x18006a9dd  push    r12
0x18006a9df  push    r13
0x18006a9e1  push    r14
0x18006a9e3  push    r15
0x18006a9e5  mov     rbp, rsp
0x18006a9e8  sub     rsp, 50h
0x18006a9ec  mov     rax, [rdx]
0x18006a9ef  mov     r14, rdx
0x18006a9f2  mov     rsi, rcx
0x18006a9f5  mov     [rbp+pv], 0
0x18006a9fd  lea     rdx, [rbp+pv]
0x18006aa01  mov     [rbp+arg_18], 0
0x18006aa09  mov     rcx, r14
0x18006aa0c  mov     [rbp+var_20], 0
0x18006aa14  mov     rax, [rax+28h]
0x18006aa18  mov     [rbp+var_10], 0
0x18006aa20  mov     [rbp+var_18], 0
0x18006aa28  mov     qword ptr [r8], 0
0x18006aa2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa34  mov     ebx, eax
0x18006aa36  test    eax, eax
0x18006aa38  jns     short loc_18006AA49
0x18006aa3a  mov     r8d, eax
0x18006aa3d  lea     rdx, aIusernameGetus; "IUserName->GetUserStr failed: 0x%x in %"...
0x18006aa44  jmp     loc_18006AB3C
0x18006aa49  mov     rax, [r14]
0x18006aa4c  lea     rdx, [rbp+arg_18]
0x18006aa50  mov     rcx, r14
0x18006aa53  mov     rax, [rax+30h]
0x18006aa57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa5c  mov     ebx, eax
0x18006aa5e  test    eax, eax
0x18006aa60  jns     short loc_18006AA71
0x18006aa62  mov     r8d, eax
0x18006aa65  lea     rdx, aIusernameGetdo; "IUserName->GetDomainStr failed: 0x%x in"...
0x18006aa6c  jmp     loc_18006AB3C
0x18006aa71  mov     r15d, 101h
0x18006aa77  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18006aa7b  mov     edx, r15d; unsigned __int64
0x18006aa7e  mov     rcx, rsi; unsigned __int16 *
0x18006aa81  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006aa86  mov     ebx, eax
0x18006aa88  test    eax, eax
0x18006aa8a  jns     short loc_18006AA9B
0x18006aa8c  mov     r8d, eax
0x18006aa8f  lea     rdx, aStringcchlengt_1; "StringCchLength(wszPrePath) failed: 0x%"...
0x18006aa96  jmp     loc_18006AB3C
0x18006aa9b  mov     rdi, [rbp+var_20]
0x18006aa9f  test    rdi, rdi
0x18006aaa2  jz      short loc_18006AAB9
0x18006aaa4  movzx   ecx, word ptr [rsi+rdi*2-2]
0x18006aaa9  call    cs:__imp__o_iswspace
0x18006aaaf  test    eax, eax
0x18006aab1  jz      short loc_18006AAB9
0x18006aab3  sub     rdi, 1
0x18006aab7  jnz     short loc_18006AAA4
0x18006aab9  xor     eax, eax
0x18006aabb  mov     [rsi+rdi*2], ax
0x18006aabf  test    rdi, rdi
0x18006aac2  jnz     short loc_18006AACE
0x18006aac4  mov     ebx, 80070057h
0x18006aac9  jmp     loc_18006AC1C
0x18006aace  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18006aad2  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18006aad6  mov     edx, 15h; unsigned __int64
0x18006aadb  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006aae0  mov     ebx, eax
0x18006aae2  test    eax, eax
0x18006aae4  jns     short loc_18006AAF2
0x18006aae6  mov     r8d, eax
0x18006aae9  lea     rdx, aStringcchlengt; "StringCchLength(wszUserName) failed: 0x"...
0x18006aaf0  jmp     short loc_18006AB3C
0x18006aaf2  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x18006aaf6  lea     r8, [rbp+var_18]; unsigned __int64 *
0x18006aafa  mov     edx, 12h; unsigned __int64
0x18006aaff  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006ab04  mov     ebx, eax
0x18006ab06  test    eax, eax
0x18006ab08  jns     short loc_18006AB16
0x18006ab0a  mov     r8d, eax
0x18006ab0d  lea     rdx, aStringcchlengt_0; "StringCchLength(wszDomain) failed: 0x%x"...
0x18006ab14  jmp     short loc_18006AB3C
0x18006ab16  mov     r12, [rbp+var_18]
0x18006ab1a  mov     r13, [rbp+var_10]
0x18006ab1e  add     r13, r12
0x18006ab21  add     r13, rdi
0x18006ab24  lea     rbx, [r13+3]
0x18006ab28  cmp     rbx, r15
0x18006ab2b  jbe     short loc_18006AB52
0x18006ab2d  mov     ebx, 8007000Dh
0x18006ab32  lea     rdx, aStringSizeCalc; "string size calculation failed: 0x%x in"...
0x18006ab39  mov     r8d, ebx
0x18006ab3c  lea     r9, aCuserprofileAs; "CUserProfile::AssembleThePath"
0x18006ab43  mov     ecx, 8; int
0x18006ab48  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006ab4d  jmp     loc_18006AC1C
0x18006ab52  movzx   r15d, word ptr [rsi+rdi*2-2]
0x18006ab58  lea     rdx, [rbx+rbx]; uBytes
0x18006ab5c  mov     ecx, 40h ; '@'; uFlags
0x18006ab61  call    cs:__imp_LocalAlloc
0x18006ab67  mov     rdi, rax
0x18006ab6a  test    rax, rax
0x18006ab6d  jnz     short loc_18006AB7D
0x18006ab6f  mov     ebx, 8007000Eh
0x18006ab74  lea     rdx, aMemoryAllocati_0; "memory allocation failed: 0x%x in %s"
0x18006ab7b  jmp     short loc_18006AB39
0x18006ab7d  mov     rax, [rbp+arg_18]
0x18006ab81  mov     r9, rsi
0x18006ab84  mov     [rsp+50h+var_28], rax
0x18006ab89  mov     rdx, rbx; unsigned __int64
0x18006ab8c  mov     rax, [rbp+pv]
0x18006ab90  mov     rcx, rdi; unsigned __int16 *
0x18006ab93  mov     [rsp+50h+var_30], rax
0x18006ab98  cmp     r15w, 5Ch ; '\'
0x18006ab9d  jnz     short loc_18006ABB4
0x18006ab9f  lea     r8, aSSS; "%s%s.%s"
0x18006aba6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006abab  mov     ebx, eax
0x18006abad  mov     eax, 1
0x18006abb2  jmp     short loc_18006ABC7
0x18006abb4  lea     r8, aSSS_0; "%s%\\%s.%s"
0x18006abbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006abc0  mov     ebx, eax
0x18006abc2  mov     eax, 2
0x18006abc7  test    ebx, ebx
0x18006abc9  jns     short loc_18006ABD4
0x18006abcb  lea     rdx, aStringcchprint_0; "StringCchPrintf failed: 0x%x in %s"
0x18006abd2  jmp     short loc_18006ABF6
0x18006abd4  lea     r8d, [rax+r13]
0x18006abd8  mov     rdx, rdi; unsigned __int16 *
0x18006abdb  sub     r8d, r12d
0x18006abde  mov     rcx, r14; struct IUserName *
0x18006abe1  dec     r8d; unsigned int
0x18006abe4  call    ?VerifyThePath@CUserProfile@@CAJPEAUIUserName@@PEAGK@Z; CUserProfile::VerifyThePath(IUserName *,ushort *,ulong)
0x18006abe9  mov     ebx, eax
0x18006abeb  test    eax, eax
0x18006abed  jns     short loc_18006AC15
0x18006abef  lea     rdx, aVerifythepathF; "VerifyThePath failed: 0x%x in %s"
0x18006abf6  lea     r9, aCuserprofileAs; "CUserProfile::AssembleThePath"
0x18006abfd  mov     r8d, ebx
0x18006ac00  mov     ecx, 8; int
0x18006ac05  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006ac0a  mov     rcx, rdi; hMem
0x18006ac0d  call    cs:__imp_LocalFree
0x18006ac13  jmp     short loc_18006AC1C
0x18006ac15  mov     rax, [rbp+arg_10]
0x18006ac19  mov     [rax], rdi
0x18006ac1c  mov     rcx, [rbp+pv]; pv
0x18006ac20  test    rcx, rcx
0x18006ac23  jz      short loc_18006AC2B
0x18006ac25  call    cs:__imp_CoTaskMemFree
0x18006ac2b  mov     rcx, [rbp+arg_18]; pv
0x18006ac2f  test    rcx, rcx
0x18006ac32  jz      short loc_18006AC3A
0x18006ac34  call    cs:__imp_CoTaskMemFree
0x18006ac3a  mov     eax, ebx
0x18006ac3c  mov     rbx, [rsp+50h+arg_0]
0x18006ac44  add     rsp, 50h
0x18006ac48  pop     r15
0x18006ac4a  pop     r14
0x18006ac4c  pop     r13
0x18006ac4e  pop     r12
0x18006ac50  pop     rdi
0x18006ac51  pop     rsi
0x18006ac52  pop     rbp
0x18006ac53  retn
```
