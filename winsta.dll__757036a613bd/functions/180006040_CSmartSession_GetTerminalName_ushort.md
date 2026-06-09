# CSmartSession::GetTerminalName(ushort *)

- ea: `0x180006040`
- end: `0x1800063d9`
- name: `?GetTerminalName@CSmartSession@@QEAAJPEAG@Z`
- size: `921`
- prototype: `__int64 __fastcall(CSmartSession *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800046ec`
- `0x1800067b0`

## callees

- `0x180006040`
- `0x180007890`
- `0x18000bf20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800060e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800060e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800061f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800063ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800061f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800063ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006220`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800062b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006220`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800062b2`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800301de`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800301de`
- `RPCRT4!NdrClientCall3` at `0x180006257`
- `RPCRT4!NdrClientCall3` at `0x180006257`

## string_xrefs

- `0x1800063b5`: `StringCchCopy failed: 0x%x in %s`
- `0x18000617d`: `SafeStringCopy failed: 0x%x in %s`
- `0x18000633d`: `SafeStringCopy failed: 0x%x in %s`
- `0x1800062ea`: `CSmartSession::SafeCopyString`
- `0x18000636c`: `CSmartSession::SafeCopyString`
- `0x1800063ab`: `CSmartSession::SafeCopyString`

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
    v18.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032200, 6u, 0, *(_QWORD *)v3, &hMem).Pointer;
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
0x180006040  mov     [rsp+arg_8], rdx
0x180006045  mov     [rsp+arg_0], rcx
0x18000604a  push    rbx
0x18000604b  push    rsi
0x18000604c  push    rdi
0x18000604d  push    r12
0x18000604f  push    r13
0x180006051  push    r14
0x180006053  push    r15
0x180006055  sub     rsp, 40h
0x180006059  mov     rsi, rdx
0x18000605c  mov     rbx, rcx
0x18000605f  xor     r15d, r15d
0x180006062  mov     [rsp+78h+hMem], r15
0x18000606a  mov     [rdx], r15w
0x18000606e  mov     r14d, 80004001h
0x180006074  cmp     dword ptr [rcx+11Ch], 1
0x18000607b  jz      loc_180006315
0x180006081  cmp     dword ptr [rcx+118h], 1
0x180006088  jnz     loc_18000634E
0x18000608e  mov     rbx, [rcx+20h]
0x180006092  mov     r12d, r15d
0x180006095  test    rbx, rbx
0x180006098  jz      loc_1800062D4
0x18000609e  mov     edi, 7FFFFFFFh
0x1800060a3  mov     ecx, edi
0x1800060a5  mov     rax, rbx
0x1800060a8  cmp     [rax], r12w
0x1800060ac  jz      short loc_1800060B8
0x1800060ae  add     rax, 2
0x1800060b2  sub     rcx, 1
0x1800060b6  jnz     short loc_1800060A8
0x1800060b8  mov     r14d, 80070057h
0x1800060be  test    rcx, rcx
0x1800060c1  cmovnz  r14d, r15d
0x1800060c5  jz      loc_18000635E
0x1800060cb  sub     rdi, rcx
0x1800060ce  test    rcx, rcx
0x1800060d1  jz      loc_1800062E7
0x1800060d7  lea     rdx, ds:2[rdi*2]; uBytes
0x1800060df  mov     ecx, 40h ; '@'; uFlags
0x1800060e4  call    cs:__imp_LocalAlloc
0x1800060ea  mov     r12, rax
0x1800060ed  test    rax, rax
0x1800060f0  jz      loc_180006366
0x1800060f6  lea     rcx, [rdi+1]
0x1800060fa  lea     rax, [rcx-1]
0x1800060fe  mov     edi, 7FFFFFFEh
0x180006103  cmp     rax, rdi
0x180006106  ja      loc_18000638C
0x18000610c  mov     eax, edi
0x18000610e  mov     rdx, r12
0x180006111  test    rax, rax
0x180006114  jz      short loc_180006135
0x180006116  movzx   r8d, word ptr [rbx]
0x18000611a  test    r8w, r8w
0x18000611e  jz      short loc_180006135
0x180006120  add     rbx, 2
0x180006124  mov     [rdx], r8w
0x180006128  add     rdx, 2
0x18000612c  dec     rax
0x18000612f  sub     rcx, 1
0x180006133  jnz     short loc_180006111
0x180006135  lea     rax, [rdx-2]
0x180006139  test    rcx, rcx
0x18000613c  cmovnz  rax, rdx
0x180006140  mov     [rax], r15w
0x180006144  mov     r13d, 8007007Ah
0x18000614a  mov     r14d, r13d
0x18000614d  cmovnz  r14d, r15d
0x180006151  test    r14d, r14d
0x180006154  js      loc_1800063AB
0x18000615a  mov     [rsp+78h+hMem], r12
0x180006162  mov     r12, r15
0x180006165  test    r12, r12
0x180006168  jnz     loc_1800063CB
0x18000616e  test    r14d, r14d
0x180006171  jns     short loc_18000618E
0x180006173  lea     r9, aCsmartsessionG; "CSmartSession::GetTerminalNameFromSessi"...
0x18000617a  mov     r8d, r14d
0x18000617d  lea     rdx, aSafestringcopy; "SafeStringCopy failed: 0x%x in %s"
0x180006184  mov     ecx, 8; int
0x180006189  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000618e  mov     rbx, [rsp+78h+arg_0]
0x180006196  test    r14d, r14d
0x180006199  js      loc_18000620F
0x18000619f  mov     ebx, r14d
0x1800061a2  test    ebx, ebx
0x1800061a4  js      short loc_1800061FD
0x1800061a6  mov     rax, [rsp+78h+hMem]
0x1800061ae  test    rax, rax
0x1800061b1  jz      short loc_1800061FD
0x1800061b3  mov     ecx, 20h ; ' '
0x1800061b8  test    rdi, rdi
0x1800061bb  jz      short loc_1800061D9
0x1800061bd  movzx   edx, word ptr [rax]
0x1800061c0  test    dx, dx
0x1800061c3  jz      short loc_1800061D9
0x1800061c5  add     rax, 2
0x1800061c9  mov     [rsi], dx
0x1800061cc  add     rsi, 2
0x1800061d0  dec     rdi
0x1800061d3  sub     rcx, 1
0x1800061d7  jnz     short loc_1800061B8
0x1800061d9  lea     rax, [rsi-2]
0x1800061dd  test    rcx, rcx
0x1800061e0  cmovnz  rax, rsi
0x1800061e4  mov     [rax], r15w
0x1800061e8  cmovnz  r13d, r15d
0x1800061ec  mov     ebx, r13d
0x1800061ef  mov     rcx, [rsp+78h+hMem]; hMem
0x1800061f7  call    cs:__imp_LocalFree
0x1800061fd  mov     eax, ebx
0x1800061ff  add     rsp, 40h
0x180006203  pop     r15
0x180006205  pop     r14
0x180006207  pop     r13
0x180006209  pop     r12
0x18000620b  pop     rdi
0x18000620c  pop     rsi
0x18000620d  pop     rbx
0x18000620e  retn
0x18000620f  lea     rdx, aInvokeRpcgette; "Invoke RpcGetTerminalName"
0x180006216  mov     ecx, 1; int
0x18000621b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006220  call    cs:__imp_GetTickCount
0x180006226  mov     r14d, eax
0x180006229  mov     dword ptr [rsp+78h+arg_0], eax
0x180006230  mov     [rsp+78h+arg_18], r15
0x180006238  lea     rax, [rsp+78h+hMem]
0x180006240  mov     [rsp+78h+var_58], rax
0x180006245  mov     r9, [rbx]
0x180006248  xor     r8d, r8d; pReturnValue
0x18000624b  mov     edx, 6; nProcNum
0x180006250  lea     rcx, stru_180032200; pProxyInfo
0x180006257  call    cs:__imp_NdrClientCall3
0x18000625d  mov     rbx, rax
0x180006260  mov     [rsp+78h+arg_18], rax
0x180006268  mov     [rsp+78h+var_48], eax
0x18000626c  jmp     short loc_1800062B2
0x18000626e  test    eax, eax
0x180006270  jle     short loc_18000627A
0x180006272  movzx   eax, ax
0x180006275  or      eax, 80070000h
0x18000627a  mov     ebx, eax
0x18000627c  mov     [rsp+78h+var_48], eax
0x180006280  mov     r8d, eax
0x180006283  lea     rdx, aRpcgetterminal_0; "RpcGetTerminalName threw an exception: "...
0x18000628a  mov     ecx, 8; int
0x18000628f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006294  xor     r15d, r15d
0x180006297  mov     edi, 7FFFFFFEh
0x18000629c  mov     r13d, 8007007Ah
0x1800062a2  mov     rsi, [rsp+78h+arg_8]
0x1800062aa  mov     r14d, dword ptr [rsp+78h+arg_0]
0x1800062b2  call    cs:__imp_GetTickCount
0x1800062b8  sub     eax, r14d
0x1800062bb  mov     r8d, eax
0x1800062be  lea     rdx, aRpcgetterminal; "RpcGetTerminalName() takes %d"
0x1800062c5  mov     ecx, 1; int
0x1800062ca  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800062cf  jmp     loc_1800061A2
0x1800062d4  mov     r14d, r15d
0x1800062d7  mov     edi, 7FFFFFFEh
0x1800062dc  mov     r13d, 8007007Ah
0x1800062e2  jmp     loc_180006165
0x1800062e7  mov     rdi, r15
0x1800062ea  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x1800062f1  mov     r8d, r14d
0x1800062f4  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x1800062fb  mov     ecx, 8; int
0x180006300  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006305  mov     edi, 7FFFFFFEh
0x18000630a  mov     r13d, 8007007Ah
0x180006310  jmp     loc_180006165
0x180006315  cmp     dword ptr [rcx+48h], 1
0x180006319  jnz     short loc_18000634E
0x18000631b  lea     rdx, [rcx+58h]; unsigned __int16 *
0x18000631f  lea     r8, [rsp+78h+hMem]; unsigned __int16 **
0x180006327  call    ?SafeCopyString@CSmartSession@@AEAAJPEBGPEAPEAG@Z; CSmartSession::SafeCopyString(ushort const *,ushort * *)
0x18000632c  mov     r14d, eax
0x18000632f  test    eax, eax
0x180006331  jns     short loc_18000634E
0x180006333  lea     r9, aCsmartsessionG; "CSmartSession::GetTerminalNameFromSessi"...
0x18000633a  mov     r8d, eax
0x18000633d  lea     rdx, aSafestringcopy; "SafeStringCopy failed: 0x%x in %s"
0x180006344  mov     ecx, 8; int
0x180006349  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000634e  mov     edi, 7FFFFFFEh
0x180006353  mov     r13d, 8007007Ah
0x180006359  jmp     loc_180006196
0x18000635e  mov     rdi, r15
0x180006361  jmp     loc_1800060CE
0x180006366  mov     r14d, 8007000Eh
0x18000636c  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x180006373  mov     r8d, r14d
0x180006376  lea     rdx, aMidlUserAlloca; "MIDL_user_allocate failed: 0x%x in %s"
0x18000637d  mov     ecx, 8; int
0x180006382  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006387  jmp     loc_1800062D7
0x18000638c  mov     r14d, 80070057h
0x180006392  mov     r13d, 8007007Ah
0x180006398  test    rcx, rcx
0x18000639b  jz      loc_180006151
0x1800063a1  mov     [r12], r15w
0x1800063a6  jmp     loc_180006151
0x1800063ab  lea     r9, aCsmartsessionS; "CSmartSession::SafeCopyString"
0x1800063b2  mov     r8d, r14d
0x1800063b5  lea     rdx, aStringcchcopyF_0; "StringCchCopy failed: 0x%x in %s"
0x1800063bc  mov     ecx, 8; int
0x1800063c1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800063c6  jmp     loc_180006165
0x1800063cb  mov     rcx, r12; hMem
0x1800063ce  call    cs:__imp_LocalFree
0x1800063d4  jmp     loc_18000616E
0x1800301d0  push    rbp
0x1800301d2  sub     rsp, 30h
0x1800301d6  mov     rbp, rdx
0x1800301d9  mov     rcx, [rcx]
0x1800301dc  mov     ecx, [rcx]; ExceptionCode
0x1800301de  call    cs:__imp_I_RpcExceptionFilter
0x1800301e4  nop
0x1800301e5  add     rsp, 30h
0x1800301e9  pop     rbp
0x1800301ea  retn
```
