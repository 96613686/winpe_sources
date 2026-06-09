# CUserProfile::AssembleThePath(ushort *,IUserName *,ushort * *)

- ea: `0x18006dc90`
- end: `0x18006df33`
- name: `?AssembleThePath@CUserProfile@@CAJPEAGPEAUIUserName@@PEAPEAG@Z`
- size: `675`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct IUserName *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006ebdc`

## callees

- `0x180009940`
- `0x180015044`
- `0x180016558`
- `0x18006dc90`
- `0x18006ea88`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18006dd69`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18006dd69`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006de27`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006de27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ded9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ded9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006def7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006df0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006def7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006df0c`

## string_xrefs

- `0x18006de02`: `CUserProfile::AssembleThePath`
- `0x18006dec2`: `CUserProfile::AssembleThePath`
- `0x18006dd4f`: `StringCchLength(wszPrePath) failed: 0x%x in %s`
- `0x18006debb`: `VerifyThePath failed: 0x%x in %s`

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
0x18006dc90  mov     [rsp-38h+arg_0], rbx
0x18006dc95  mov     [rsp-38h+arg_10], r8
0x18006dc9a  push    rbp
0x18006dc9b  push    rsi
0x18006dc9c  push    rdi
0x18006dc9d  push    r12
0x18006dc9f  push    r13
0x18006dca1  push    r14
0x18006dca3  push    r15
0x18006dca5  mov     rbp, rsp
0x18006dca8  sub     rsp, 50h
0x18006dcac  mov     rax, [rdx]
0x18006dcaf  mov     r14, rdx
0x18006dcb2  mov     rsi, rcx
0x18006dcb5  mov     [rbp+pv], 0
0x18006dcbd  lea     rdx, [rbp+pv]
0x18006dcc1  mov     [rbp+arg_18], 0
0x18006dcc9  mov     rcx, r14
0x18006dccc  mov     [rbp+var_20], 0
0x18006dcd4  mov     rax, [rax+28h]
0x18006dcd8  mov     [rbp+var_10], 0
0x18006dce0  mov     [rbp+var_18], 0
0x18006dce8  mov     qword ptr [r8], 0
0x18006dcef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dcf4  mov     ebx, eax
0x18006dcf6  test    eax, eax
0x18006dcf8  jns     short loc_18006DD09
0x18006dcfa  mov     r8d, eax
0x18006dcfd  lea     rdx, aIusernameGetus; "IUserName->GetUserStr failed: 0x%x in %"...
0x18006dd04  jmp     loc_18006DE02
0x18006dd09  mov     rax, [r14]
0x18006dd0c  lea     rdx, [rbp+arg_18]
0x18006dd10  mov     rcx, r14
0x18006dd13  mov     rax, [rax+30h]
0x18006dd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd1c  mov     ebx, eax
0x18006dd1e  test    eax, eax
0x18006dd20  jns     short loc_18006DD31
0x18006dd22  mov     r8d, eax
0x18006dd25  lea     rdx, aIusernameGetdo; "IUserName->GetDomainStr failed: 0x%x in"...
0x18006dd2c  jmp     loc_18006DE02
0x18006dd31  mov     r15d, 101h
0x18006dd37  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18006dd3b  mov     edx, r15d; unsigned __int64
0x18006dd3e  mov     rcx, rsi; unsigned __int16 *
0x18006dd41  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006dd46  mov     ebx, eax
0x18006dd48  test    eax, eax
0x18006dd4a  jns     short loc_18006DD5B
0x18006dd4c  mov     r8d, eax
0x18006dd4f  lea     rdx, aStringcchlengt_1; "StringCchLength(wszPrePath) failed: 0x%"...
0x18006dd56  jmp     loc_18006DE02
0x18006dd5b  mov     rdi, [rbp+var_20]
0x18006dd5f  test    rdi, rdi
0x18006dd62  jz      short loc_18006DD7F
0x18006dd64  movzx   ecx, word ptr [rsi+rdi*2-2]
0x18006dd69  call    cs:__imp__o_iswspace
0x18006dd70  nop     dword ptr [rax+rax+00h]
0x18006dd75  test    eax, eax
0x18006dd77  jz      short loc_18006DD7F
0x18006dd79  sub     rdi, 1
0x18006dd7d  jnz     short loc_18006DD64
0x18006dd7f  xor     eax, eax
0x18006dd81  mov     [rsi+rdi*2], ax
0x18006dd85  test    rdi, rdi
0x18006dd88  jnz     short loc_18006DD94
0x18006dd8a  mov     ebx, 80070057h
0x18006dd8f  jmp     loc_18006DEEE
0x18006dd94  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18006dd98  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18006dd9c  mov     edx, 15h; unsigned __int64
0x18006dda1  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006dda6  mov     ebx, eax
0x18006dda8  test    eax, eax
0x18006ddaa  jns     short loc_18006DDB8
0x18006ddac  mov     r8d, eax
0x18006ddaf  lea     rdx, aStringcchlengt; "StringCchLength(wszUserName) failed: 0x"...
0x18006ddb6  jmp     short loc_18006DE02
0x18006ddb8  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x18006ddbc  lea     r8, [rbp+var_18]; unsigned __int64 *
0x18006ddc0  mov     edx, 12h; unsigned __int64
0x18006ddc5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006ddca  mov     ebx, eax
0x18006ddcc  test    eax, eax
0x18006ddce  jns     short loc_18006DDDC
0x18006ddd0  mov     r8d, eax
0x18006ddd3  lea     rdx, aStringcchlengt_0; "StringCchLength(wszDomain) failed: 0x%x"...
0x18006ddda  jmp     short loc_18006DE02
0x18006dddc  mov     r12, [rbp+var_18]
0x18006dde0  mov     r13, [rbp+var_10]
0x18006dde4  add     r13, r12
0x18006dde7  add     r13, rdi
0x18006ddea  lea     rbx, [r13+3]
0x18006ddee  cmp     rbx, r15
0x18006ddf1  jbe     short loc_18006DE18
0x18006ddf3  mov     ebx, 8007000Dh
0x18006ddf8  lea     rdx, aStringSizeCalc; "string size calculation failed: 0x%x in"...
0x18006ddff  mov     r8d, ebx
0x18006de02  lea     r9, aCuserprofileAs; "CUserProfile::AssembleThePath"
0x18006de09  mov     ecx, 8; int
0x18006de0e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006de13  jmp     loc_18006DEEE
0x18006de18  movzx   r15d, word ptr [rsi+rdi*2-2]
0x18006de1e  lea     rdx, [rbx+rbx]; uBytes
0x18006de22  mov     ecx, 40h ; '@'; uFlags
0x18006de27  call    cs:__imp_LocalAlloc
0x18006de2e  nop     dword ptr [rax+rax+00h]
0x18006de33  mov     rdi, rax
0x18006de36  test    rax, rax
0x18006de39  jnz     short loc_18006DE49
0x18006de3b  mov     ebx, 8007000Eh
0x18006de40  lea     rdx, aMemoryAllocati_0; "memory allocation failed: 0x%x in %s"
0x18006de47  jmp     short loc_18006DDFF
0x18006de49  mov     rax, [rbp+arg_18]
0x18006de4d  mov     r9, rsi
0x18006de50  mov     [rsp+50h+var_28], rax
0x18006de55  mov     rdx, rbx; unsigned __int64
0x18006de58  mov     rax, [rbp+pv]
0x18006de5c  mov     rcx, rdi; unsigned __int16 *
0x18006de5f  mov     [rsp+50h+var_30], rax
0x18006de64  cmp     r15w, 5Ch ; '\'
0x18006de69  jnz     short loc_18006DE80
0x18006de6b  lea     r8, aSSS; "%s%s.%s"
0x18006de72  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006de77  mov     ebx, eax
0x18006de79  mov     eax, 1
0x18006de7e  jmp     short loc_18006DE93
0x18006de80  lea     r8, aSSS_0; "%s%\\%s.%s"
0x18006de87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006de8c  mov     ebx, eax
0x18006de8e  mov     eax, 2
0x18006de93  test    ebx, ebx
0x18006de95  jns     short loc_18006DEA0
0x18006de97  lea     rdx, aStringcchprint_0; "StringCchPrintf failed: 0x%x in %s"
0x18006de9e  jmp     short loc_18006DEC2
0x18006dea0  lea     r8d, [rax+r13]
0x18006dea4  mov     rdx, rdi; unsigned __int16 *
0x18006dea7  sub     r8d, r12d
0x18006deaa  mov     rcx, r14; struct IUserName *
0x18006dead  dec     r8d; unsigned int
0x18006deb0  call    ?VerifyThePath@CUserProfile@@CAJPEAUIUserName@@PEAGK@Z; CUserProfile::VerifyThePath(IUserName *,ushort *,ulong)
0x18006deb5  mov     ebx, eax
0x18006deb7  test    eax, eax
0x18006deb9  jns     short loc_18006DEE7
0x18006debb  lea     rdx, aVerifythepathF; "VerifyThePath failed: 0x%x in %s"
0x18006dec2  lea     r9, aCuserprofileAs; "CUserProfile::AssembleThePath"
0x18006dec9  mov     r8d, ebx
0x18006decc  mov     ecx, 8; int
0x18006ded1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006ded6  mov     rcx, rdi; hMem
0x18006ded9  call    cs:__imp_LocalFree
0x18006dee0  nop     dword ptr [rax+rax+00h]
0x18006dee5  jmp     short loc_18006DEEE
0x18006dee7  mov     rax, [rbp+arg_10]
0x18006deeb  mov     [rax], rdi
0x18006deee  mov     rcx, [rbp+pv]; pv
0x18006def2  test    rcx, rcx
0x18006def5  jz      short loc_18006DF03
0x18006def7  call    cs:__imp_CoTaskMemFree
0x18006defe  nop     dword ptr [rax+rax+00h]
0x18006df03  mov     rcx, [rbp+arg_18]; pv
0x18006df07  test    rcx, rcx
0x18006df0a  jz      short loc_18006DF18
0x18006df0c  call    cs:__imp_CoTaskMemFree
0x18006df13  nop     dword ptr [rax+rax+00h]
0x18006df18  mov     eax, ebx
0x18006df1a  mov     rbx, [rsp+50h+arg_0]
0x18006df22  add     rsp, 50h
0x18006df26  pop     r15
0x18006df28  pop     r14
0x18006df2a  pop     r13
0x18006df2c  pop     r12
0x18006df2e  pop     rdi
0x18006df2f  pop     rsi
0x18006df30  pop     rbp
0x18006df31  retn
```
