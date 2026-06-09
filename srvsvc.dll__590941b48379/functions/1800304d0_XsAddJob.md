# XsAddJob

- ea: `0x1800304d0`
- end: `0x180030a3d`
- name: `XsAddJob`
- size: `1389`
- prototype: `unsigned int __fastcall(PRPC_ASYNC_STATE pAsync, RPC_BINDING_HANDLE BindingHandle, _QWORD *, unsigned __int16 *, __int64, _DWORD *, DWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180020dc0`
- `0x180020de8`
- `0x180030418`
- `0x1800304d0`
- `0x180030c18`
- `0x1800435f8`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003086b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003086b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030657`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800307c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030657`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800307c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800309ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800309ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800309ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800309ba`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180030919`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180030919`
- `ntdll!RtlFreeHeap` at `0x1800309a4`
- `ntdll!RtlFreeHeap` at `0x1800309a4`
- `ntdll!RtlAcquireResourceShared` at `0x180030589`
- `ntdll!RtlAcquireResourceShared` at `0x180030589`
- `ntdll!RtlReleaseResource` at `0x1800305d2`
- `ntdll!RtlReleaseResource` at `0x1800309cb`
- `ntdll!RtlReleaseResource` at `0x1800305d2`
- `ntdll!RtlReleaseResource` at `0x1800309cb`
- `ntdll!RtlInitUnicodeString` at `0x180030905`
- `ntdll!RtlInitUnicodeString` at `0x180030905`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180030a15`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180030a15`
- `RPCRT4!RpcAsyncAbortCall` at `0x180030534`
- `RPCRT4!RpcAsyncAbortCall` at `0x180030a1f`
- `RPCRT4!RpcAsyncAbortCall` at `0x180030534`
- `RPCRT4!RpcAsyncAbortCall` at `0x180030a1f`
- `RPCRT4!RpcImpersonateClient` at `0x1800306b1`
- `RPCRT4!RpcImpersonateClient` at `0x1800306b1`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800307b1`
- `RPCRT4!RpcRevertToSelfEx` at `0x180030807`
- `RPCRT4!RpcRevertToSelfEx` at `0x180030875`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800307b1`
- `RPCRT4!RpcRevertToSelfEx` at `0x180030807`
- `RPCRT4!RpcRevertToSelfEx` at `0x180030875`
- `RPCRT4!RpcServerTestCancel` at `0x180030522`
- `RPCRT4!RpcServerTestCancel` at `0x180030522`

## pseudocode

```c
unsigned int __fastcall XsAddJob(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        _QWORD *a3,
        unsigned __int16 *a4,
        __int64 a5,
        _DWORD *a6,
        DWORD *a7)
{
  DWORD *v7; // r12
  struct _RPC_ASYNC_STATE *v8; // r15
  unsigned int result; // eax
  DWORD LastError; // ebx
  _QWORD *v13; // r15
  unsigned int v14; // eax
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  __int64 v17; // rbx
  DWORD v18; // eax
  SIZE_T v19; // r15
  _WORD *v20; // rax
  _WORD *v21; // r12
  _QWORD *v22; // r8
  __int64 (__fastcall *v23)(_QWORD, __int64, _QWORD *, _QWORD, unsigned int *); // rax
  int v24; // r13d
  unsigned int v25; // eax
  _QWORD *v26; // rcx
  PWSTR Buffer; // rdx
  USHORT Length; // ax
  USHORT v29; // cx
  size_t v30; // r8
  void *v31; // rcx
  int v32; // edx
  int v33; // r8d
  unsigned int v34; // [rsp+30h] [rbp-50h] BYREF
  _QWORD *v35; // [rsp+38h] [rbp-48h]
  struct _UNICODE_STRING NtPathName; // [rsp+40h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-30h] BYREF
  __m128i si128; // [rsp+60h] [rbp-20h] BYREF
  __int64 v39; // [rsp+70h] [rbp-10h]

  v7 = a7;
  v8 = pAsync;
  v39 = 0;
  v34 = 0;
  *a7 = 0;
  si128 = 0;
  DestinationString = 0;
  NtPathName = 0;
  if ( !RpcServerTestCancel(BindingHandle) )
  {
    result = RpcAsyncAbortCall(v8, 0x71Au);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        return WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 17,
                 WPP_961f2129f327316bc578c2fdd21cc406_Traceguids,
                 result);
    }
    return result;
  }
  RtlAcquireResourceShared(&stru_18005E3D8, 1u);
  if ( !dword_18005E43C )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids);
    }
    RtlReleaseResource(&stru_18005E3D8);
    LastError = 5;
    goto LABEL_75;
  }
  if ( !pSpoolerResetPrinterFunction && !pSpoolerAddJobFunction && !(unsigned __int8)XsLoadPrintSpoolerFunctions() )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids);
    }
    goto LABEL_75;
  }
  v34 = 528;
  v35 = LocalAlloc(0x40u, 0x210u);
  v13 = v35;
  if ( !v35 )
  {
    LastError = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids);
    }
    goto LABEL_74;
  }
  v14 = RpcImpersonateClient(0);
  LastError = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids, v14);
    }
    goto LABEL_73;
  }
  v15 = *a3;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  LODWORD(v39) = 0;
  if ( (unsigned int)((__int64 (__fastcall *)(__int64, __m128i *))pSpoolerResetPrinterFunction)(v15, &si128) )
    goto LABEL_34;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v17 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v18 = GetLastError();
    WPP_SF_d(v17, 22, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids, v18);
LABEL_34:
    v16 = WPP_GLOBAL_Control;
  }
  if ( *a4 <= 4u )
  {
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 0x10) != 0 && *((_BYTE *)v16 + 25) )
      WPP_SF_d(v16[2], 23, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids, *a4);
    LastError = 87;
    RpcRevertToSelfEx(0);
    goto LABEL_73;
  }
  v19 = *a4;
  v20 = LocalAlloc(0x40u, v19);
  v21 = v20;
  if ( v20 )
  {
    LastError = 0;
    memcpy_0(v20, (const void *)(*((_QWORD *)a4 + 1) + 4LL), v19 - 4);
    v21[(v19 >> 1) - 2] = 0;
    v13 = v35;
    v22 = v35;
    v23 = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD *, _QWORD, unsigned int *))pSpoolerAddJobFunction;
    *v35 = v21;
    v24 = v23(*a3, 3, v22, v34, &v34);
    if ( !v24 )
      LastError = GetLastError();
    v25 = RpcRevertToSelfEx(0);
    if ( v25 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_55;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids, v25);
    }
    v26 = WPP_GLOBAL_Control;
LABEL_55:
    if ( v24 )
    {
      *a6 = *((_DWORD *)v13 + 2);
      RtlInitUnicodeString(&DestinationString, (PCWSTR)*v13);
      if ( RtlDosPathNameToNtPathName_U(DestinationString.Buffer, &NtPathName, 0, 0) )
      {
        Buffer = NtPathName.Buffer;
        Length = NtPathName.Length;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids);
        }
        Buffer = 0;
        Length = 0;
        NtPathName.Buffer = 0;
        NtPathName.Length = 0;
      }
      v29 = Length;
      if ( Length >= *(_WORD *)(a5 + 2) )
        v29 = *(_WORD *)(a5 + 2);
      v30 = v29;
      v31 = *(void **)(a5 + 8);
      *(_WORD *)a5 = v30;
      memcpy_0(v31, Buffer, v30);
      if ( NtPathName.Buffer )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    }
    else if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 0x10) != 0 && *((_BYTE *)v26 + 25) )
    {
      WPP_SF_d(v26[2], 26, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids, LastError);
    }
    LocalFree(v21);
    goto LABEL_72;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids);
  }
  LastError = 8;
  RpcRevertToSelfEx(0);
  v13 = v35;
LABEL_72:
  v7 = a7;
LABEL_73:
  LocalFree(v13);
LABEL_74:
  v8 = pAsync;
LABEL_75:
  RtlReleaseResource(&stru_18005E3D8);
  *v7 = LastError;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DdZ(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, v33, LastError, *a6, a5);
  }
  if ( LastError )
    return RpcAsyncAbortCall(v8, LastError);
  else
    return RpcAsyncCompleteCall(v8, 0);
}

```

## disassembly

```asm
0x1800304d0  mov     [rsp-28h+arg_8], rbx
0x1800304d5  mov     [rsp-28h+arg_10], r8
0x1800304da  mov     [rsp-28h+arg_0], rcx
0x1800304df  push    rbp
0x1800304e0  push    rdi
0x1800304e1  push    r12
0x1800304e3  push    r13
0x1800304e5  push    r15
0x1800304e7  mov     rbp, rsp
0x1800304ea  sub     rsp, 80h
0x1800304f1  mov     r12, [rbp+arg_30]
0x1800304f5  xorps   xmm0, xmm0
0x1800304f8  mov     r15, rcx
0x1800304fb  xor     eax, eax
0x1800304fd  xor     ebx, ebx
0x1800304ff  mov     [rbp+var_10], rax
0x180030503  xorps   xmm1, xmm1
0x180030506  mov     [rbp+var_50], ebx
0x180030509  mov     rcx, rdx; BindingHandle
0x18003050c  mov     [r12], ebx
0x180030510  mov     r13, r9
0x180030513  mov     rdi, r8
0x180030516  movups  [rbp+var_20], xmm0
0x18003051a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003051e  movups  xmmword ptr [rbp+NtPathName.Length], xmm1
0x180030522  call    cs:__imp_RpcServerTestCancel
0x180030528  test    eax, eax
0x18003052a  jnz     short loc_180030580
0x18003052c  mov     edx, 71Ah; ExceptionCode
0x180030531  mov     rcx, r15; pAsync
0x180030534  call    cs:__imp_RpcAsyncAbortCall
0x18003053a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030541  lea     rdi, WPP_GLOBAL_Control
0x180030548  cmp     rcx, rdi
0x18003054b  jz      loc_180030A25
0x180030551  test    byte ptr [rcx+1Ch], 10h
0x180030555  jz      loc_180030A25
0x18003055b  cmp     byte ptr [rcx+19h], 1
0x18003055f  jb      loc_180030A25
0x180030565  mov     rcx, [rcx+10h]
0x180030569  lea     edx, [rbx+11h]
0x18003056c  mov     r9d, eax
0x18003056f  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180030576  call    WPP_SF_d
0x18003057b  jmp     loc_180030A25
0x180030580  mov     dl, 1; Wait
0x180030582  lea     rcx, stru_18005E3D8; Resource
0x180030589  call    cs:__imp_RtlAcquireResourceShared
0x18003058f  cmp     cs:dword_18005E43C, ebx
0x180030595  jnz     short loc_1800305E2
0x180030597  mov     rcx, cs:WPP_GLOBAL_Control
0x18003059e  lea     rdi, WPP_GLOBAL_Control
0x1800305a5  cmp     rcx, rdi
0x1800305a8  jz      short loc_1800305CB
0x1800305aa  test    byte ptr [rcx+1Ch], 10h
0x1800305ae  jz      short loc_1800305CB
0x1800305b0  cmp     byte ptr [rcx+19h], 1
0x1800305b4  jb      short loc_1800305CB
0x1800305b6  mov     rcx, [rcx+10h]
0x1800305ba  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x1800305c1  mov     edx, 12h
0x1800305c6  call    WPP_SF_
0x1800305cb  lea     rcx, stru_18005E3D8; Resource
0x1800305d2  call    cs:__imp_RtlReleaseResource
0x1800305d8  mov     ebx, 5
0x1800305dd  jmp     loc_1800309C4
0x1800305e2  cmp     cs:pSpoolerResetPrinterFunction, rbx
0x1800305e9  jnz     short loc_18003064A
0x1800305eb  cmp     cs:pSpoolerAddJobFunction, rbx
0x1800305f2  jnz     short loc_18003064A
0x1800305f4  call    XsLoadPrintSpoolerFunctions
0x1800305f9  test    al, al
0x1800305fb  jnz     short loc_18003064A
0x1800305fd  call    cs:__imp_GetLastError
0x180030603  mov     ebx, eax
0x180030605  mov     rcx, cs:WPP_GLOBAL_Control
0x18003060c  lea     rdi, WPP_GLOBAL_Control
0x180030613  cmp     rcx, rdi
0x180030616  jz      loc_1800309C4
0x18003061c  test    byte ptr [rcx+1Ch], 10h
0x180030620  jz      loc_1800309C4
0x180030626  cmp     byte ptr [rcx+19h], 1
0x18003062a  jb      loc_1800309C4
0x180030630  mov     rcx, [rcx+10h]
0x180030634  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x18003063b  mov     edx, 13h
0x180030640  call    WPP_SF_
0x180030645  jmp     loc_1800309C4
0x18003064a  mov     edx, 210h; uBytes
0x18003064f  mov     ecx, 40h ; '@'; uFlags
0x180030654  mov     [rbp+var_50], edx
0x180030657  call    cs:__imp_LocalAlloc
0x18003065d  mov     [rbp+var_48], rax
0x180030661  mov     r15, rax
0x180030664  test    rax, rax
0x180030667  jnz     short loc_1800306AF
0x180030669  lea     ebx, [rax+8]
0x18003066c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030673  lea     rdi, WPP_GLOBAL_Control
0x18003067a  cmp     rcx, rdi
0x18003067d  jz      loc_1800309C0
0x180030683  test    byte ptr [rcx+1Ch], 10h
0x180030687  jz      loc_1800309C0
0x18003068d  cmp     byte ptr [rcx+19h], 1
0x180030691  jb      loc_1800309C0
0x180030697  mov     rcx, [rcx+10h]
0x18003069b  lea     edx, [rax+14h]
0x18003069e  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x1800306a5  call    WPP_SF_
0x1800306aa  jmp     loc_1800309C0
0x1800306af  xor     ecx, ecx; BindingHandle
0x1800306b1  call    cs:__imp_RpcImpersonateClient
0x1800306b7  mov     ebx, eax
0x1800306b9  test    eax, eax
0x1800306bb  jz      short loc_180030705
0x1800306bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306c4  lea     rdi, WPP_GLOBAL_Control
0x1800306cb  cmp     rcx, rdi
0x1800306ce  jz      loc_1800309B7
0x1800306d4  test    byte ptr [rcx+1Ch], 10h
0x1800306d8  jz      loc_1800309B7
0x1800306de  cmp     byte ptr [rcx+19h], 1
0x1800306e2  jb      loc_1800309B7
0x1800306e8  mov     rcx, [rcx+10h]
0x1800306ec  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x1800306f3  mov     edx, 15h
0x1800306f8  mov     r9d, eax
0x1800306fb  call    WPP_SF_d
0x180030700  jmp     loc_1800309B7
0x180030705  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18003070d  lea     rdx, [rbp+var_20]
0x180030711  mov     rcx, [rdi]
0x180030714  mov     rax, cs:pSpoolerResetPrinterFunction
0x18003071b  movdqu  [rbp+var_20], xmm0
0x180030720  mov     dword ptr [rbp+var_10], 0
0x180030727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003072c  lea     rdi, WPP_GLOBAL_Control
0x180030733  test    eax, eax
0x180030735  jnz     short loc_180030770
0x180030737  mov     rcx, cs:WPP_GLOBAL_Control
0x18003073e  cmp     rcx, rdi
0x180030741  jz      short loc_180030777
0x180030743  test    byte ptr [rcx+1Ch], 10h
0x180030747  jz      short loc_180030777
0x180030749  cmp     byte ptr [rcx+19h], 1
0x18003074d  jb      short loc_180030777
0x18003074f  mov     rbx, [rcx+10h]
0x180030753  call    cs:__imp_GetLastError
0x180030759  mov     edx, 16h
0x18003075e  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180030765  mov     r9d, eax
0x180030768  mov     rcx, rbx
0x18003076b  call    WPP_SF_d
0x180030770  mov     rcx, cs:WPP_GLOBAL_Control
0x180030777  movzx   eax, word ptr [r13+0]
0x18003077c  cmp     eax, 4
0x18003077f  ja      short loc_1800307BC
0x180030781  cmp     rcx, rdi
0x180030784  jz      short loc_1800307AA
0x180030786  test    byte ptr [rcx+1Ch], 10h
0x18003078a  jz      short loc_1800307AA
0x18003078c  cmp     byte ptr [rcx+19h], 1
0x180030790  jb      short loc_1800307AA
0x180030792  mov     rcx, [rcx+10h]
0x180030796  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x18003079d  mov     edx, 17h
0x1800307a2  mov     r9d, eax
0x1800307a5  call    WPP_SF_d
0x1800307aa  xor     ecx, ecx; BindingHandle
0x1800307ac  mov     ebx, 57h ; 'W'
0x1800307b1  call    cs:__imp_RpcRevertToSelfEx
0x1800307b7  jmp     loc_1800309B7
0x1800307bc  mov     rdx, rax; uBytes
0x1800307bf  mov     ecx, 40h ; '@'; uFlags
0x1800307c4  mov     r15, rax
0x1800307c7  call    cs:__imp_LocalAlloc
0x1800307cd  mov     r12, rax
0x1800307d0  test    rax, rax
0x1800307d3  jnz     short loc_180030816
0x1800307d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307dc  cmp     rcx, rdi
0x1800307df  jz      short loc_180030800
0x1800307e1  test    byte ptr [rcx+1Ch], 10h
0x1800307e5  jz      short loc_180030800
0x1800307e7  cmp     byte ptr [rcx+19h], 1
0x1800307eb  jb      short loc_180030800
0x1800307ed  mov     rcx, [rcx+10h]
0x1800307f1  lea     edx, [rax+18h]
0x1800307f4  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x1800307fb  call    WPP_SF_
0x180030800  xor     ecx, ecx; BindingHandle
0x180030802  mov     ebx, 8
0x180030807  call    cs:__imp_RpcRevertToSelfEx
0x18003080d  mov     r15, [rbp+var_48]
0x180030811  jmp     loc_1800309B3
0x180030816  mov     rdx, [r13+8]
0x18003081a  lea     r8, [r15-4]; Size
0x18003081e  add     rdx, 4; Src
0x180030822  mov     rcx, r12; void *
0x180030825  xor     ebx, ebx
0x180030827  call    memcpy_0
0x18003082c  mov     rcx, [rbp+arg_10]
0x180030830  lea     edx, [rbx+3]
0x180030833  xor     eax, eax
0x180030835  shr     r15, 1
0x180030838  mov     [r12+r15*2-4], ax
0x18003083e  lea     rax, [rbp+var_50]
0x180030842  mov     r15, [rbp+var_48]
0x180030846  mov     [rsp+80h+var_60], rax
0x18003084b  mov     r8, r15
0x18003084e  mov     rax, cs:pSpoolerAddJobFunction
0x180030855  mov     [r15], r12
0x180030858  mov     r9d, [rbp+var_50]
0x18003085c  mov     rcx, [rcx]
0x18003085f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030864  mov     r13d, eax
0x180030867  test    eax, eax
0x180030869  jnz     short loc_180030873
0x18003086b  call    cs:__imp_GetLastError
0x180030871  mov     ebx, eax
0x180030873  xor     ecx, ecx; BindingHandle
0x180030875  call    cs:__imp_RpcRevertToSelfEx
0x18003087b  test    eax, eax
0x18003087d  jz      short loc_1800308AF
0x18003087f  mov     rcx, cs:WPP_GLOBAL_Control
0x180030886  cmp     rcx, rdi
0x180030889  jz      short loc_1800308B6
0x18003088b  test    byte ptr [rcx+1Ch], 10h
0x18003088f  jz      short loc_1800308B6
0x180030891  cmp     byte ptr [rcx+19h], 1
0x180030895  jb      short loc_1800308B6
0x180030897  mov     rcx, [rcx+10h]
0x18003089b  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x1800308a2  mov     edx, 19h
0x1800308a7  mov     r9d, eax
0x1800308aa  call    WPP_SF_d
0x1800308af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308b6  test    r13d, r13d
0x1800308b9  jnz     short loc_1800308F4
0x1800308bb  cmp     rcx, rdi
0x1800308be  jz      loc_1800309AA
0x1800308c4  test    byte ptr [rcx+1Ch], 10h
0x1800308c8  jz      loc_1800309AA
0x1800308ce  cmp     byte ptr [rcx+19h], 1
0x1800308d2  jb      loc_1800309AA
0x1800308d8  mov     rcx, [rcx+10h]
0x1800308dc  lea     edx, [r13+1Ah]
0x1800308e0  mov     r9d, ebx
0x1800308e3  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x1800308ea  call    WPP_SF_d
0x1800308ef  jmp     loc_1800309AA
0x1800308f4  mov     rcx, [rbp+arg_28]
0x1800308f8  mov     eax, [r15+8]
0x1800308fc  mov     [rcx], eax
0x1800308fe  lea     rcx, [rbp+DestinationString]; DestinationString
0x180030902  mov     rdx, [r15]; SourceString
0x180030905  call    cs:__imp_RtlInitUnicodeString
0x18003090b  mov     rcx, [rbp+DestinationString.Buffer]; DosPathName
0x18003090f  lea     rdx, [rbp+NtPathName]; NtPathName
0x180030913  xor     r9d, r9d; DirectoryInfo
0x180030916  xor     r8d, r8d; NtFileNamePart
0x180030919  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18003091f  test    al, al
0x180030921  jnz     short loc_18003095E
0x180030923  mov     rcx, cs:WPP_GLOBAL_Control
0x18003092a  cmp     rcx, rdi
0x18003092d  jz      short loc_180030950
0x18003092f  test    byte ptr [rcx+1Ch], 10h
0x180030933  jz      short loc_180030950
0x180030935  cmp     byte ptr [rcx+19h], 1
0x180030939  jb      short loc_180030950
0x18003093b  mov     rcx, [rcx+10h]
0x18003093f  lea     r8, WPP_961f2129f327316bc578c2fdd21cc406_Traceguids
0x180030946  mov     edx, 1Bh
0x18003094b  call    WPP_SF_
0x180030950  xor     edx, edx
0x180030952  xor     eax, eax
0x180030954  mov     [rbp+NtPathName.Buffer], rdx
0x180030958  mov     [rbp+NtPathName.Length], ax
0x18003095c  jmp     short loc_180030966
0x18003095e  mov     rdx, [rbp+NtPathName.Buffer]; Src
0x180030962  movzx   eax, [rbp+NtPathName.Length]
0x180030966  mov     r9, [rbp+arg_20]
0x18003096a  movzx   ecx, ax
0x18003096d  cmp     ax, [r9+2]
0x180030972  jb      short loc_180030979
0x180030974  movzx   ecx, word ptr [r9+2]
0x180030979  movzx   r8d, cx; Size
0x18003097d  mov     rcx, [r9+8]; void *
0x180030981  mov     [r9], r8w
0x180030985  call    memcpy_0
0x18003098a  cmp     [rbp+NtPathName.Buffer], 0
0x18003098f  jz      short loc_1800309AA
0x180030991  mov     rcx, gs:60h
0x18003099a  xor     edx, edx; Flags
0x18003099c  mov     r8, [rbp+NtPathName.Buffer]; P
0x1800309a0  mov     rcx, [rcx+30h]; HeapHandle
0x1800309a4  call    cs:__imp_RtlFreeHeap
0x1800309aa  mov     rcx, r12; hMem
0x1800309ad  call    cs:__imp_LocalFree
  ... truncated ...
```
