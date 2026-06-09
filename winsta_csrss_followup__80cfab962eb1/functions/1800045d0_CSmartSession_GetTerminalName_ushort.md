# CSmartSession::GetTerminalName(ushort *)

- ea: `0x1800045d0`
- end: `0x180004990`
- name: `?GetTerminalName@CSmartSession@@QEAAJPEAG@Z`
- size: `960`
- prototype: `__int64 __fastcall(CSmartSession *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002114`
- `0x1800049a0`

## callees

- `0x1800045d0`
- `0x180005b40`
- `0x18000daa0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004674`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004674`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000478f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000497f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000478f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000497f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800047bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000485d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800047bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000485d`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032f2e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032f2e`
- `RPCRT4!NdrClientCall3` at `0x1800047fc`
- `RPCRT4!NdrClientCall3` at `0x1800047fc`

## string_xrefs

- `0x180004966`: `StringCchCopy failed: 0x%x in %s`
- `0x180004713`: `SafeStringCopy failed: 0x%x in %s`
- `0x1800048ee`: `SafeStringCopy failed: 0x%x in %s`
- `0x18000489b`: `CSmartSession::SafeCopyString`
- `0x18000491d`: `CSmartSession::SafeCopyString`
- `0x18000495c`: `CSmartSession::SafeCopyString`

## pseudocode

```c
__int64 __fastcall CSmartSession::GetTerminalName(CSmartSession *this, unsigned __int16 *a2)
{
  unsigned __int16 *v2; // rsi
  CSmartSession *v3; // rbx
  int v4; // r14d
  _WORD *v5; // rbx
  _WORD *v6; // r12
  __int64 v7; // rcx
  _WORD *v8; // rax
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rax
  _WORD *v14; // rdx
  __int16 v15; // r8
  _WORD *v16; // rax
  int v17; // r13d
  CLIENT_CALL_RETURN v18; // rbx
  unsigned __int16 *v19; // rax
  __int64 v20; // rcx
  unsigned __int16 v21; // dx
  unsigned __int16 *v22; // rax
  DWORD TickCount; // r14d
  DWORD v25; // eax
  int v26; // eax
  HLOCAL hMem; // [rsp+90h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v29; // [rsp+98h] [rbp+20h]

  v2 = a2;
  v3 = this;
  hMem = 0;
  *a2 = 0;
  v4 = -2147467263;
  if ( *((_DWORD *)this + 71) == 1 )
  {
    if ( *((_DWORD *)this + 18) == 1 )
    {
      v26 = CSmartSession::SafeCopyString(this, (const unsigned __int16 *)this + 44, (unsigned __int16 **)&hMem);
      v4 = v26;
      if ( v26 < 0 )
        _DbgPrintMessage(
          8,
          "SafeStringCopy failed: 0x%x in %s",
          v26,
          "CSmartSession::GetTerminalNameFromSessionInformation");
    }
    goto LABEL_48;
  }
  if ( *((_DWORD *)this + 70) != 1 )
  {
LABEL_48:
    v12 = 2147483646;
    v17 = -2147024774;
    goto LABEL_27;
  }
  v5 = (_WORD *)*((_QWORD *)this + 4);
  v6 = 0;
  if ( v5 )
  {
    v7 = 0x7FFFFFFF;
    v8 = v5;
    do
    {
      if ( !*v8 )
        break;
      ++v8;
      --v7;
    }
    while ( v7 );
    v4 = -2147024809;
    if ( v7 )
    {
      v4 = 0;
      v9 = 0x7FFFFFFF - v7;
    }
    else
    {
      v9 = 0;
    }
    if ( !v7 )
    {
      _DbgPrintMessage(8, "StringCchLength failed: 0x%x in %s", v4, "CSmartSession::SafeCopyString");
      v12 = 2147483646;
      v17 = -2147024774;
      goto LABEL_22;
    }
    v6 = LocalAlloc(0x40u, 2 * v9 + 2);
    if ( v6 )
    {
      v10 = v9 + 1;
      v11 = v9;
      v12 = 2147483646;
      if ( v11 > 0x7FFFFFFE )
      {
        v4 = -2147024809;
        v17 = -2147024774;
        if ( v10 )
          *v6 = 0;
      }
      else
      {
        v13 = 2147483646;
        v14 = v6;
        do
        {
          if ( !v13 )
            break;
          v15 = *v5;
          if ( !*v5 )
            break;
          ++v5;
          *v14++ = v15;
          --v13;
          --v10;
        }
        while ( v10 );
        v16 = v14 - 1;
        if ( v10 )
          v16 = v14;
        *v16 = 0;
        v17 = -2147024774;
        v4 = -2147024774;
        if ( v10 )
          v4 = 0;
      }
      if ( v4 < 0 )
      {
        _DbgPrintMessage(8, "StringCchCopy failed: 0x%x in %s", v4, "CSmartSession::SafeCopyString");
      }
      else
      {
        hMem = v6;
        v6 = 0;
      }
      goto LABEL_22;
    }
    v4 = -2147024882;
    _DbgPrintMessage(8, "MIDL_user_allocate failed: 0x%x in %s", -2147024882, "CSmartSession::SafeCopyString");
  }
  else
  {
    v4 = 0;
  }
  v12 = 2147483646;
  v17 = -2147024774;
LABEL_22:
  if ( v6 )
    LocalFree(v6);
  if ( v4 < 0 )
    _DbgPrintMessage(8, "SafeStringCopy failed: 0x%x in %s", v4, "CSmartSession::GetTerminalNameFromSessionInformation");
  v3 = this;
LABEL_27:
  if ( v4 < 0 )
  {
    _DbgPrintMessage(1, "Invoke RpcGetTerminalName");
    TickCount = GetTickCount();
    v29.Simple = 0;
    v18.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 6u, 0, *(_QWORD *)v3, &hMem).Pointer;
    v29.Pointer = v18.Pointer;
    v25 = GetTickCount();
    _DbgPrintMessage(1, "RpcGetTerminalName() takes %d", v25 - TickCount);
  }
  else
  {
    LODWORD(v18.Pointer) = v4;
  }
  if ( SLODWORD(v18.Simple) >= 0 )
  {
    v19 = (unsigned __int16 *)hMem;
    if ( hMem )
    {
      v20 = 32;
      do
      {
        if ( !v12 )
          break;
        v21 = *v19;
        if ( !*v19 )
          break;
        ++v19;
        *v2++ = v21;
        --v12;
        --v20;
      }
      while ( v20 );
      v22 = v2 - 1;
      if ( v20 )
        v22 = v2;
      *v22 = 0;
      if ( v20 )
        v17 = 0;
      LODWORD(v18.Pointer) = v17;
      LocalFree(hMem);
    }
  }
  return LODWORD(v18.Pointer);
}

```

## disassembly

```asm
0x1800045d0  mov     [rsp+arg_8], rdx
0x1800045d5  mov     [rsp+arg_0], rcx
0x1800045da  push    rbx
0x1800045db  push    rsi
0x1800045dc  push    rdi
0x1800045dd  push    r12
0x1800045df  push    r13
0x1800045e1  push    r14
0x1800045e3  push    r15
0x1800045e5  sub     rsp, 40h
0x1800045e9  mov     rsi, rdx
0x1800045ec  mov     rbx, rcx
0x1800045ef  xor     r15d, r15d
0x1800045f2  mov     [rsp+78h+hMem], r15
0x1800045fa  mov     [rdx], r15w
0x1800045fe  mov     r14d, 80004001h
0x180004604  cmp     dword ptr [rcx+11Ch], 1
0x18000460b  jz      loc_1800048C6
0x180004611  cmp     dword ptr [rcx+118h], 1
0x180004618  jnz     loc_1800048FF
0x18000461e  mov     rbx, [rcx+20h]
0x180004622  mov     r12d, r15d
0x180004625  test    rbx, rbx
0x180004628  jz      loc_180004885
0x18000462e  mov     edi, 7FFFFFFFh
0x180004633  mov     ecx, edi
0x180004635  mov     rax, rbx
0x180004638  cmp     [rax], r12w
0x18000463c  jz      short loc_180004648
0x18000463e  add     rax, 2
0x180004642  sub     rcx, 1
0x180004646  jnz     short loc_180004638
0x180004648  mov     r14d, 80070057h
0x18000464e  test    rcx, rcx
0x180004651  cmovnz  r14d, r15d
0x180004655  jz      loc_18000490F
0x18000465b  sub     rdi, rcx
0x18000465e  test    rcx, rcx
0x180004661  jz      loc_180004898
0x180004667  lea     rdx, ds:2[rdi*2]; uBytes
0x18000466f  mov     ecx, 40h ; '@'; uFlags
0x180004674  call    cs:__imp_LocalAlloc
0x18000467b  nop     dword ptr [rax+rax+00h]
0x180004680  mov     r12, rax
0x180004683  test    rax, rax
0x180004686  jz      loc_180004917
0x18000468c  lea     rcx, [rdi+1]
0x180004690  lea     rax, [rcx-1]
0x180004694  mov     edi, 7FFFFFFEh
0x180004699  cmp     rax, rdi
0x18000469c  ja      loc_18000493D
0x1800046a2  mov     eax, edi
0x1800046a4  mov     rdx, r12
0x1800046a7  test    rax, rax
0x1800046aa  jz      short loc_1800046CB
0x1800046ac  movzx   r8d, word ptr [rbx]
0x1800046b0  test    r8w, r8w
0x1800046b4  jz      short loc_1800046CB
0x1800046b6  add     rbx, 2
0x1800046ba  mov     [rdx], r8w
0x1800046be  add     rdx, 2
0x1800046c2  dec     rax
0x1800046c5  sub     rcx, 1
0x1800046c9  jnz     short loc_1800046A7
0x1800046cb  lea     rax, [rdx-2]
0x1800046cf  test    rcx, rcx
0x1800046d2  cmovnz  rax, rdx
0x1800046d6  mov     [rax], r15w
0x1800046da  mov     r13d, 8007007Ah
0x1800046e0  mov     r14d, r13d
0x1800046e3  cmovnz  r14d, r15d
0x1800046e7  test    r14d, r14d
0x1800046ea  js      loc_18000495C
0x1800046f0  mov     [rsp+78h+hMem], r12
0x1800046f8  mov     r12, r15
0x1800046fb  test    r12, r12
0x1800046fe  jnz     loc_18000497C
0x180004704  test    r14d, r14d
0x180004707  jns     short loc_180004724
0x180004709  lea     r9, aCsmartsessionG; "CSmartSession::GetTerminalNameFromSessi"...
0x180004710  mov     r8d, r14d
0x180004713  lea     rdx, aSafestringcopy; "SafeStringCopy failed: 0x%x in %s"
0x18000471a  mov     ecx, 8; int
0x18000471f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180004724  mov     rbx, [rsp+78h+arg_0]
0x18000472c  test    r14d, r14d
0x18000472f  js      loc_1800047AE
0x180004735  mov     ebx, r14d
0x180004738  test    ebx, ebx
0x18000473a  js      short loc_18000479B
0x18000473c  mov     rax, [rsp+78h+hMem]
0x180004744  test    rax, rax
0x180004747  jz      short loc_18000479B
0x180004749  mov     ecx, 20h ; ' '
0x18000474e  xchg    ax, ax
0x180004750  test    rdi, rdi
0x180004753  jz      short loc_180004771
0x180004755  movzx   edx, word ptr [rax]
0x180004758  test    dx, dx
0x18000475b  jz      short loc_180004771
0x18000475d  add     rax, 2
0x180004761  mov     [rsi], dx
0x180004764  add     rsi, 2
0x180004768  dec     rdi
0x18000476b  sub     rcx, 1
0x18000476f  jnz     short loc_180004750
0x180004771  lea     rax, [rsi-2]
0x180004775  test    rcx, rcx
0x180004778  cmovnz  rax, rsi
0x18000477c  mov     [rax], r15w
0x180004780  cmovnz  r13d, r15d
0x180004784  mov     ebx, r13d
0x180004787  mov     rcx, [rsp+78h+hMem]; hMem
0x18000478f  call    cs:__imp_LocalFree
0x180004796  nop     dword ptr [rax+rax+00h]
0x18000479b  mov     eax, ebx
0x18000479d  add     rsp, 40h
0x1800047a1  pop     r15
0x1800047a3  pop     r14
0x1800047a5  pop     r13
0x1800047a7  pop     r12
0x1800047a9  pop     rdi
0x1800047aa  pop     rsi
0x1800047ab  pop     rbx
0x1800047ac  retn
0x1800047ae  lea     rdx, aInvokeRpcgette; "Invoke RpcGetTerminalName"
0x1800047b5  mov     ecx, 1; int
0x1800047ba  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800047bf  call    cs:__imp_GetTickCount
0x1800047c6  nop     dword ptr [rax+rax+00h]
0x1800047cb  mov     r14d, eax
0x1800047ce  mov     dword ptr [rsp+78h+arg_0], eax
0x1800047d5  mov     [rsp+78h+arg_18], r15
0x1800047dd  lea     rax, [rsp+78h+hMem]
0x1800047e5  mov     [rsp+78h+var_58], rax
0x1800047ea  mov     r9, [rbx]
0x1800047ed  xor     r8d, r8d; pReturnValue
0x1800047f0  mov     edx, 6; nProcNum
0x1800047f5  lea     rcx, pProxyInfo; pProxyInfo
0x1800047fc  call    cs:__imp_NdrClientCall3
0x180004803  nop     dword ptr [rax+rax+00h]
0x180004808  mov     rbx, rax
0x18000480b  mov     [rsp+78h+arg_18], rax
0x180004813  mov     [rsp+78h+var_48], eax
0x180004817  jmp     short loc_18000485D
0x180004819  test    eax, eax
0x18000481b  jle     short loc_180004825
0x18000481d  movzx   eax, ax
0x180004820  or      eax, 80070000h
0x180004825  mov     ebx, eax
0x180004827  mov     [rsp+78h+var_48], eax
0x18000482b  mov     r8d, eax
0x18000482e  lea     rdx, aRpcgetterminal_0; "RpcGetTerminalName threw an exception: "...
0x180004835  mov     ecx, 8; int
0x18000483a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000483f  xor     r15d, r15d
0x180004842  mov     edi, 7FFFFFFEh
0x180004847  mov     r13d, 8007007Ah
0x18000484d  mov     rsi, [rsp+78h+arg_8]
0x180004855  mov     r14d, dword ptr [rsp+78h+arg_0]
0x18000485d  call    cs:__imp_GetTickCount
0x180004864  nop     dword ptr [rax+rax+00h]
0x180004869  sub     eax, r14d
0x18000486c  mov     r8d, eax
0x18000486f  lea     rdx, aRpcgetterminal; "RpcGetTerminalName() takes %d"
0x180004876  mov     ecx, 1; int
0x18000487b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180004880  jmp     loc_180004738
0x180004885  mov     r14d, r15d
0x180004888  mov     edi, 7FFFFFFEh
0x18000488d  mov     r13d, 8007007Ah
0x180004893  jmp     loc_1800046FB
0x180004898  mov     rdi, r15
0x18000489b  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x1800048a2  mov     r8d, r14d
0x1800048a5  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x1800048ac  mov     ecx, 8; int
0x1800048b1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800048b6  mov     edi, 7FFFFFFEh
0x1800048bb  mov     r13d, 8007007Ah
0x1800048c1  jmp     loc_1800046FB
0x1800048c6  cmp     dword ptr [rcx+48h], 1
0x1800048ca  jnz     short loc_1800048FF
0x1800048cc  lea     rdx, [rcx+58h]; unsigned __int16 *
0x1800048d0  lea     r8, [rsp+78h+hMem]; unsigned __int16 **
0x1800048d8  call    ?SafeCopyString@CSmartSession@@AEAAJPEBGPEAPEAG@Z; CSmartSession::SafeCopyString(ushort const *,ushort * *)
0x1800048dd  mov     r14d, eax
0x1800048e0  test    eax, eax
0x1800048e2  jns     short loc_1800048FF
0x1800048e4  lea     r9, aCsmartsessionG; "CSmartSession::GetTerminalNameFromSessi"...
0x1800048eb  mov     r8d, eax
0x1800048ee  lea     rdx, aSafestringcopy; "SafeStringCopy failed: 0x%x in %s"
0x1800048f5  mov     ecx, 8; int
0x1800048fa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800048ff  mov     edi, 7FFFFFFEh
0x180004904  mov     r13d, 8007007Ah
0x18000490a  jmp     loc_18000472C
0x18000490f  mov     rdi, r15
0x180004912  jmp     loc_18000465E
0x180004917  mov     r14d, 8007000Eh
0x18000491d  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x180004924  mov     r8d, r14d
0x180004927  lea     rdx, aMidlUserAlloca; "MIDL_user_allocate failed: 0x%x in %s"
0x18000492e  mov     ecx, 8; int
0x180004933  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180004938  jmp     loc_180004888
0x18000493d  mov     r14d, 80070057h
0x180004943  mov     r13d, 8007007Ah
0x180004949  test    rcx, rcx
0x18000494c  jz      loc_1800046E7
0x180004952  mov     [r12], r15w
0x180004957  jmp     loc_1800046E7
0x18000495c  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x180004963  mov     r8d, r14d
0x180004966  lea     rdx, aStringcchcopyF_0; "StringCchCopy failed: 0x%x in %s"
0x18000496d  mov     ecx, 8; int
0x180004972  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180004977  jmp     loc_1800046FB
0x18000497c  mov     rcx, r12; hMem
0x18000497f  call    cs:__imp_LocalFree
0x180004986  nop     dword ptr [rax+rax+00h]
0x18000498b  jmp     loc_180004704
0x180032f20  push    rbp
0x180032f22  sub     rsp, 30h
0x180032f26  mov     rbp, rdx
0x180032f29  mov     rcx, [rcx]
0x180032f2c  mov     ecx, [rcx]; ExceptionCode
0x180032f2e  call    cs:__imp_I_RpcExceptionFilter
0x180032f35  nop     dword ptr [rax+rax+00h]
0x180032f3a  nop
0x180032f3b  add     rsp, 30h
0x180032f3f  pop     rbp
0x180032f40  retn
```
