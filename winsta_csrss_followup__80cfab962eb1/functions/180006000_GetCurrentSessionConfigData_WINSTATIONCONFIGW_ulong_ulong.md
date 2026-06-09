# GetCurrentSessionConfigData(_WINSTATIONCONFIGW *,ulong,ulong *)

- ea: `0x180006000`
- end: `0x180006474`
- name: `?GetCurrentSessionConfigData@@YAJPEAU_WINSTATIONCONFIGW@@KPEAK@Z`
- size: `1140`
- prototype: `__int64 __fastcall(struct _WINSTATIONCONFIGW *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x1800095b0`
- `0x1800096c0`

## callees

- `0x1800032b4`
- `0x180004558`
- `0x180005b40`
- `0x180006000`
- `0x180006480`
- `0x1800066d0`
- `0x180020c90`
- `0x1800249e8`
- `0x180024a1c`
- `0x180025cc6`
- `0x18002e180`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800062da`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800062da`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006272`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006272`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006406`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006242`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006242`
- `RPCRT4!RpcBindingFree` at `0x180006288`
- `RPCRT4!RpcBindingFree` at `0x18000629f`
- `RPCRT4!RpcBindingFree` at `0x180006448`
- `RPCRT4!RpcBindingFree` at `0x180006459`
- `RPCRT4!RpcBindingFree` at `0x180006288`
- `RPCRT4!RpcBindingFree` at `0x18000629f`
- `RPCRT4!RpcBindingFree` at `0x180006448`
- `RPCRT4!RpcBindingFree` at `0x180006459`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032fde`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032fde`
- `RPCRT4!NdrClientCall3` at `0x18000618a`
- `RPCRT4!NdrClientCall3` at `0x18000618a`

## string_xrefs

- `0x18000630d`: `StringCchCopy failed: %x`
- `0x1800061b9`: `RpcGetCurrentSessionConfigData threw an exception: 0x%x`
- `0x180006428`: `GetCurrentSessionConfigData`
- `0x180006432`: `RpcGetCurrentSessionConfigData failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall GetCurrentSessionConfigData(struct _WINSTATIONCONFIGW *a1, unsigned int a2, unsigned int *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // r12
  int v8; // r13d
  _WORD *v9; // rcx
  __int64 v10; // rax
  int *v11; // r8
  __int64 v12; // rdx
  __int16 v13; // r9
  int v14; // ebx
  _WORD *v15; // rax
  _QWORD *v16; // rbx
  void *UnifiedRpcBinding; // rax
  void *RCMBinding; // rax
  CLIENT_CALL_RETURN v19; // rbx
  __int64 v20; // rax
  _BYTE *v21; // rax
  __int64 v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  __int64 v26; // rax
  char *v27; // rdi
  signed int LastError; // eax
  int v29; // [rsp+30h] [rbp-58h]
  HLOCAL hMem; // [rsp+38h] [rbp-50h] BYREF
  _QWORD *v31; // [rsp+40h] [rbp-48h]
  CLIENT_CALL_RETURN v32; // [rsp+48h] [rbp-40h]
  size_t Size; // [rsp+A8h] [rbp+20h] BYREF

  hMem = 0;
  LODWORD(Size) = 0;
  v6 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  v8 = 1;
  if ( v6 )
  {
    *v6 = 0;
    v6[1] = 0;
    v6[2] = 0;
    v6[3] = 0;
    v6[4] = 0;
    v6[5] = 0;
    v6[6] = 1;
    v6[7] = 0;
    v9 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
    v7[5] = v9;
    if ( v9 )
    {
      v10 = 2147483646;
      v11 = &dword_18003FF34;
      v12 = 1;
      do
      {
        if ( !v10 )
          break;
        v13 = *(_WORD *)v11;
        if ( !*(_WORD *)v11 )
          break;
        v11 = (int *)((char *)v11 + 2);
        *v9++ = v13;
        --v10;
        --v12;
      }
      while ( v12 );
      v14 = -2147024774;
      if ( v12 )
        v14 = 0;
      v15 = v9 - 1;
      if ( v12 )
        v15 = v9;
      *v15 = 0;
      if ( v12 )
      {
        if ( !v7[3] && !*((_DWORD *)v7 + 12) )
        {
          if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((CPublicBinding *)v7) == -2147023174 )
            *((_DWORD *)v7 + 13) = 1;
          CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v7);
        }
      }
      else
      {
        ConvertHRESULT2WIN32(v14);
        _DbgPrintMessage(8, "StringCchCopy failed: %x", v14);
      }
    }
    v31 = v7;
  }
  else
  {
    v7 = 0;
    v31 = 0;
  }
  if ( v7 )
  {
    v29 = 1;
  }
  else
  {
    v8 = 0;
    v29 = 0;
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  *a3 = 0;
  if ( a2 < 0xA68 )
  {
    LODWORD(v19.Pointer) = -2147024809;
  }
  else
  {
    v16 = v7 + 3;
    if ( v7 )
    {
      if ( *v16 )
        UnifiedRpcBinding = CPublicBinding::GetUnifiedRpcBinding((CPublicBinding *)v7);
      else
        UnifiedRpcBinding = CPublicBinding::GetRCMBinding((CPublicBinding *)v7);
    }
    else
    {
      UnifiedRpcBinding = 0;
    }
    if ( UnifiedRpcBinding )
    {
      if ( v7 )
      {
        if ( *v16 )
          RCMBinding = CPublicBinding::GetUnifiedRpcBinding((CPublicBinding *)v7);
        else
          RCMBinding = CPublicBinding::GetRCMBinding((CPublicBinding *)v7);
      }
      else
      {
        RCMBinding = 0;
      }
      v32.Simple = 0;
      v19.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035018, 2u, 0, RCMBinding, &hMem, &Size, v29).Pointer;
      v32.Pointer = v19.Pointer;
      if ( LODWORD(v19.Pointer) == -2147022646
        || LODWORD(v19.Pointer) == -2147023174
        || LODWORD(v19.Pointer) == -2147023179 )
      {
        *a3 = a2;
        v20 = a2;
        do
        {
          *(_BYTE *)a1 = 0;
          a1 = (struct _WINSTATIONCONFIGW *)((char *)a1 + 1);
          --v20;
        }
        while ( v20 );
        LODWORD(v19.Pointer) = 0;
      }
      else if ( SLODWORD(v19.Simple) < 0 )
      {
        _DbgPrintMessage(
          8,
          "RpcGetCurrentSessionConfigData failed: 0x%x in %s",
          LODWORD(v19.Pointer),
          "GetCurrentSessionConfigData");
      }
      else
      {
        if ( (unsigned int)Size < a2 )
          a2 = Size;
        memcpy_0(a1, hMem, a2);
        v26 = 30;
        v27 = (char *)a1 + 210;
        do
        {
          *v27++ = 0;
          --v26;
        }
        while ( v26 );
        *a3 = Size;
      }
    }
    else
    {
      LastError = GetLastError();
      LODWORD(v19.Pointer) = LastError;
      if ( LastError > 0 )
        LODWORD(v19.Pointer) = (unsigned __int16)LastError | 0x80070000;
    }
  }
  v21 = hMem;
  if ( hMem )
  {
    v22 = (unsigned int)Size;
    if ( (_DWORD)Size )
    {
      do
      {
        *v21++ = 0;
        --v22;
      }
      while ( v22 );
    }
    LocalFree(hMem);
  }
  if ( v8 && v7 )
  {
    CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v7);
    v23 = (void *)v7[5];
    if ( v23 )
      operator delete[](v23);
    if ( *v7 )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7);
    if ( v7[1] )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7 + 1);
    if ( v7[2] )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7 + 2);
    if ( v7[3] )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7 + 3);
    v24 = (void *)v7[4];
    if ( v24 )
      Legacy_WinStationCloseServer(v24);
    operator delete(v7);
  }
  return LODWORD(v19.Pointer);
}

```

## disassembly

```asm
0x180006000  mov     rax, rsp
0x180006003  mov     [rax+18h], r8
0x180006007  mov     [rax+10h], edx
0x18000600a  mov     [rax+8], rcx
0x18000600e  push    rbx
0x18000600f  push    rsi
0x180006010  push    rdi
0x180006011  push    r12
0x180006013  push    r13
0x180006015  push    r14
0x180006017  push    r15
0x180006019  sub     rsp, 50h
0x18000601d  mov     r14, r8
0x180006020  mov     esi, edx
0x180006022  mov     rdi, rcx
0x180006025  xor     r15d, r15d
0x180006028  mov     [rax-50h], r15
0x18000602c  mov     [rax+20h], r15d
0x180006030  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006037  mov     ecx, 40h ; '@'; unsigned __int64
0x18000603c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006041  mov     r12, rax
0x180006044  mov     r13d, 1
0x18000604a  test    rax, rax
0x18000604d  jz      loc_1800063EC
0x180006053  mov     [rax], r15
0x180006056  mov     [rax+8], r15
0x18000605a  mov     [rax+10h], r15
0x18000605e  mov     [rax+18h], r15
0x180006062  mov     [rax+20h], r15
0x180006066  mov     [rax+28h], r15
0x18000606a  mov     [rax+30h], r13
0x18000606e  mov     [rax+38h], r15
0x180006072  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006079  mov     ecx, 2; unsigned __int64
0x18000607e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006083  mov     rcx, rax
0x180006086  mov     [r12+28h], rax
0x18000608b  test    rax, rax
0x18000608e  jz      short loc_1800060F3
0x180006090  mov     eax, 7FFFFFFEh
0x180006095  lea     r8, dword_18003FF34
0x18000609c  mov     edx, r13d
0x18000609f  nop
0x1800060a0  test    rax, rax
0x1800060a3  jz      short loc_1800060C3
0x1800060a5  movzx   r9d, word ptr [r8]
0x1800060a9  test    r9w, r9w
0x1800060ad  jz      short loc_1800060C3
0x1800060af  add     r8, 2
0x1800060b3  mov     [rcx], r9w
0x1800060b7  add     rcx, 2
0x1800060bb  dec     rax
0x1800060be  sub     rdx, r13
0x1800060c1  jnz     short loc_1800060A0
0x1800060c3  mov     ebx, 8007007Ah
0x1800060c8  test    rdx, rdx
0x1800060cb  cmovnz  ebx, r15d
0x1800060cf  lea     rax, [rcx-2]
0x1800060d3  cmovnz  rax, rcx
0x1800060d7  mov     [rax], r15w
0x1800060db  jz      loc_180006303
0x1800060e1  cmp     [r12+18h], r15
0x1800060e6  jnz     short loc_1800060F3
0x1800060e8  cmp     [r12+30h], r15d
0x1800060ed  jz      loc_180006323
0x1800060f3  mov     [rsp+88h+var_48], r12
0x1800060f8  test    r12, r12
0x1800060fb  jz      loc_1800063F9
0x180006101  mov     [rsp+88h+var_58], r13d
0x180006106  mov     [r14], r15d
0x180006109  cmp     esi, 0A68h
0x18000610f  jb      loc_1800063B4
0x180006115  lea     rbx, [r12+18h]
0x18000611a  test    r12, r12
0x18000611d  jz      loc_1800063AC
0x180006123  mov     rcx, r12; this
0x180006126  cmp     [rbx], r15
0x180006129  jz      loc_1800062F9
0x18000612f  call    ?GetUnifiedRpcBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetUnifiedRpcBinding(void)
0x180006134  test    rax, rax
0x180006137  jz      loc_1800063BE
0x18000613d  test    r12, r12
0x180006140  jz      short loc_180006159
0x180006142  mov     rcx, r12; this
0x180006145  cmp     qword ptr [rbx], 0
0x180006149  jz      short loc_180006152
0x18000614b  call    ?GetUnifiedRpcBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetUnifiedRpcBinding(void)
0x180006150  jmp     short loc_18000615C
0x180006152  call    ?GetRCMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetRCMBinding(void)
0x180006157  jmp     short loc_18000615C
0x180006159  mov     rax, r15
0x18000615c  mov     [rsp+88h+var_40], r15
0x180006161  lea     rcx, [rsp+88h+Size]
0x180006169  mov     [rsp+88h+var_60], rcx
0x18000616e  lea     rcx, [rsp+88h+hMem]
0x180006173  mov     [rsp+88h+var_68], rcx
0x180006178  mov     r9, rax
0x18000617b  xor     r8d, r8d; pReturnValue
0x18000617e  mov     edx, 2; nProcNum
0x180006183  lea     rcx, stru_180035018; pProxyInfo
0x18000618a  call    cs:__imp_NdrClientCall3
0x180006191  nop     dword ptr [rax+rax+00h]
0x180006196  mov     rbx, rax
0x180006199  mov     [rsp+88h+var_40], rax
0x18000619e  mov     [rsp+88h+var_54], eax
0x1800061a2  jmp     short loc_1800061EE
0x1800061a4  test    eax, eax
0x1800061a6  jle     short loc_1800061B0
0x1800061a8  movzx   eax, ax
0x1800061ab  or      eax, 80070000h
0x1800061b0  mov     ebx, eax
0x1800061b2  mov     [rsp+88h+var_54], eax
0x1800061b6  mov     r8d, eax
0x1800061b9  lea     rdx, aRpcgetcurrents_2; "RpcGetCurrentSessionConfigData threw an"...
0x1800061c0  mov     ecx, 8; int
0x1800061c5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800061ca  xor     r15d, r15d
0x1800061cd  mov     r14, [rsp+88h+arg_10]
0x1800061d5  mov     esi, [rsp+88h+arg_8]
0x1800061dc  mov     rdi, [rsp+88h+arg_0]
0x1800061e4  mov     r13d, [rsp+88h+var_58]
0x1800061e9  mov     r12, [rsp+88h+var_48]
0x1800061ee  cmp     ebx, 800708CAh
0x1800061f4  jnz     loc_180006343
0x1800061fa  mov     [r14], esi
0x1800061fd  mov     eax, esi
0x1800061ff  test    esi, esi
0x180006201  jz      short loc_180006210
0x180006203  mov     byte ptr [rdi], 0
0x180006206  lea     rdi, [rdi+1]
0x18000620a  sub     rax, 1
0x18000620e  jnz     short loc_180006203
0x180006210  mov     ebx, r15d
0x180006213  mov     rax, [rsp+88h+hMem]
0x180006218  test    rax, rax
0x18000621b  jz      short loc_18000624E
0x18000621d  mov     ecx, dword ptr [rsp+88h+Size]
0x180006224  test    rcx, rcx
0x180006227  jz      short loc_18000623D
0x180006229  nop     dword ptr [rax+00000000h]
0x180006230  mov     byte ptr [rax], 0
0x180006233  lea     rax, [rax+1]
0x180006237  sub     rcx, 1
0x18000623b  jnz     short loc_180006230
0x18000623d  mov     rcx, [rsp+88h+hMem]; hMem
0x180006242  call    cs:__imp_LocalFree
0x180006249  nop     dword ptr [rax+rax+00h]
0x18000624e  test    r13d, r13d
0x180006251  jz      loc_1800062E6
0x180006257  test    r12, r12
0x18000625a  jz      loc_1800062E6
0x180006260  mov     rcx, r12; this
0x180006263  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180006268  mov     rcx, [r12+28h]
0x18000626d  test    rcx, rcx
0x180006270  jz      short loc_18000627E
0x180006272  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006279  nop     dword ptr [rax+rax+00h]
0x18000627e  cmp     qword ptr [r12], 0
0x180006283  jz      short loc_180006294
0x180006285  mov     rcx, r12; Binding
0x180006288  call    cs:__imp_RpcBindingFree
0x18000628f  nop     dword ptr [rax+rax+00h]
0x180006294  lea     rcx, [r12+8]; Binding
0x180006299  cmp     qword ptr [rcx], 0
0x18000629d  jz      short loc_1800062AB
0x18000629f  call    cs:__imp_RpcBindingFree
0x1800062a6  nop     dword ptr [rax+rax+00h]
0x1800062ab  lea     rcx, [r12+10h]; Binding
0x1800062b0  cmp     qword ptr [rcx], 0
0x1800062b4  jnz     loc_180006448
0x1800062ba  lea     rcx, [r12+18h]; Binding
0x1800062bf  cmp     qword ptr [rcx], 0
0x1800062c3  jnz     loc_180006459
0x1800062c9  mov     rcx, [r12+20h]; void *
0x1800062ce  test    rcx, rcx
0x1800062d1  jnz     loc_18000646A
0x1800062d7  mov     rcx, r12
0x1800062da  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800062e1  nop     dword ptr [rax+rax+00h]
0x1800062e6  mov     eax, ebx
0x1800062e8  add     rsp, 50h
0x1800062ec  pop     r15
0x1800062ee  pop     r14
0x1800062f0  pop     r13
0x1800062f2  pop     r12
0x1800062f4  pop     rdi
0x1800062f5  pop     rsi
0x1800062f6  pop     rbx
0x1800062f7  retn
0x1800062f9  call    ?GetRCMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetRCMBinding(void)
0x1800062fe  jmp     loc_180006134
0x180006303  mov     ecx, ebx; int
0x180006305  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000630a  mov     r8d, ebx
0x18000630d  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x180006314  mov     ecx, 8; int
0x180006319  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000631e  jmp     loc_1800060F3
0x180006323  mov     rcx, r12; this
0x180006326  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x18000632b  cmp     eax, 800706BAh
0x180006330  jz      loc_1800063E2
0x180006336  mov     rcx, r12; this
0x180006339  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x18000633e  jmp     loc_1800060F3
0x180006343  cmp     ebx, 800706BAh
0x180006349  jz      loc_1800061FA
0x18000634f  cmp     ebx, 800706B5h
0x180006355  jz      loc_1800061FA
0x18000635b  test    ebx, ebx
0x18000635d  js      loc_180006428
0x180006363  cmp     dword ptr [rsp+88h+Size], esi
0x18000636a  cmovb   esi, dword ptr [rsp+88h+Size]
0x180006372  mov     r8d, esi; Size
0x180006375  mov     rdx, [rsp+88h+hMem]; Src
0x18000637a  mov     rcx, rdi; void *
0x18000637d  call    memcpy_0
0x180006382  mov     eax, 1Eh
0x180006387  add     rdi, 0D2h
0x18000638e  xchg    ax, ax
0x180006390  mov     byte ptr [rdi], 0
0x180006393  lea     rdi, [rdi+1]
0x180006397  sub     rax, 1
0x18000639b  jnz     short loc_180006390
0x18000639d  mov     eax, dword ptr [rsp+88h+Size]
0x1800063a4  mov     [r14], eax
0x1800063a7  jmp     loc_180006213
0x1800063ac  mov     rax, r15
0x1800063af  jmp     loc_180006134
0x1800063b4  mov     ebx, 80070057h
0x1800063b9  jmp     loc_180006213
0x1800063be  call    cs:__imp_GetLastError
0x1800063c5  nop     dword ptr [rax+rax+00h]
0x1800063ca  mov     ebx, eax
0x1800063cc  test    eax, eax
0x1800063ce  jle     loc_180006213
0x1800063d4  movzx   ebx, ax
0x1800063d7  or      ebx, 80070000h
0x1800063dd  jmp     loc_180006213
0x1800063e2  mov     [r12+34h], r13d
0x1800063e7  jmp     loc_180006336
0x1800063ec  mov     r12, r15
0x1800063ef  mov     [rsp+88h+var_48], r15
0x1800063f4  jmp     loc_1800060F8
0x1800063f9  mov     r13d, r15d
0x1800063fc  mov     [rsp+88h+var_58], r15d
0x180006401  mov     ecx, 0Eh; dwErrCode
0x180006406  call    cs:__imp_SetLastError
0x18000640d  nop     dword ptr [rax+rax+00h]
0x180006412  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180006419  mov     ecx, 8; int
0x18000641e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006423  jmp     loc_180006106
0x180006428  lea     r9, aGetcurrentsess_3; "GetCurrentSessionConfigData"
0x18000642f  mov     r8d, ebx
0x180006432  lea     rdx, aRpcgetcurrents_8; "RpcGetCurrentSessionConfigData failed: "...
0x180006439  mov     ecx, 8; int
0x18000643e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006443  jmp     loc_180006213
0x180006448  call    cs:__imp_RpcBindingFree
0x18000644f  nop     dword ptr [rax+rax+00h]
0x180006454  jmp     loc_1800062BA
0x180006459  call    cs:__imp_RpcBindingFree
0x180006460  nop     dword ptr [rax+rax+00h]
0x180006465  jmp     loc_1800062C9
0x18000646a  call    ?Legacy_WinStationCloseServer@@YAEPEAX@Z; Legacy_WinStationCloseServer(void *)
0x18000646f  jmp     loc_1800062D7
0x180032fd0  push    rbp
0x180032fd2  sub     rsp, 30h
0x180032fd6  mov     rbp, rdx
0x180032fd9  mov     rcx, [rcx]
0x180032fdc  mov     ecx, [rcx]; ExceptionCode
0x180032fde  call    cs:__imp_I_RpcExceptionFilter
0x180032fe5  nop     dword ptr [rax+rax+00h]
0x180032fea  nop
0x180032feb  add     rsp, 30h
0x180032fef  pop     rbp
0x180032ff0  retn
```
