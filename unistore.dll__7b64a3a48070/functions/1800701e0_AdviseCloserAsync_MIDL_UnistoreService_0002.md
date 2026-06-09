# _AdviseCloserAsync(__MIDL_UnistoreService_0002 *)

- ea: `0x1800701e0`
- end: `0x18007034b`
- name: `?_AdviseCloserAsync@@YAJPEAU__MIDL_UnistoreService_0002@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(struct __MIDL_UnistoreService_0002 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x180023c30`
- `0x180066f38`

## callees

- `0x1800068f0`
- `0x180023f9c`
- `0x1800243ac`
- `0x1800701e0`
- `0x180070354`
- `0x1800703a0`
- `0x180078a34`
- `0x180078a4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800702b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800702f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800702b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800702f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800702ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800702ab`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180070280`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180070280`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800702de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800702de`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800702d5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800702d5`

## string_xrefs

- `0x180070246`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\clientobjects.cpp`
- `0x18007030f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\clientobjects.cpp`

## pseudocode

```c
__int64 __fastcall _AdviseCloserAsync(struct __MIDL_UnistoreService_0002 *a1)
{
  int v1; // eax
  unsigned int v2; // edi
  __int64 v3; // r9
  __int64 v4; // rdx
  __int64 v5; // rcx
  HMODULE *v6; // rbx
  struct _TP_WORK *ThreadpoolWork; // rdi
  signed int LastError; // eax
  __int64 v9; // r9
  signed int v10; // eax
  struct __MIDL_UnistoreService_0002 **v12; // [rsp+30h] [rbp-20h] BYREF
  char v13; // [rsp+38h] [rbp-18h]
  _BYTE v14[16]; // [rsp+40h] [rbp-10h] BYREF
  struct __MIDL_UnistoreService_0002 *v15; // [rsp+60h] [rbp+10h] BYREF
  struct _TP_WORK *v16; // [rsp+68h] [rbp+18h] BYREF

  v15 = a1;
  v16 = 0;
  v12 = &v15;
  v13 = 1;
  v1 = InitializeUSCloserThreadpool();
  v2 = v1;
  if ( v1 >= 0 )
  {
    v6 = (HMODULE *)operator new(0x20u);
    if ( v6 )
    {
      *v6 = (HMODULE)v15;
      *(_OWORD *)(v6 + 1) = *(_OWORD *)GetClientThreadInfo(v14);
      ThreadpoolWork = CreateThreadpoolWork(_TP_AdviseCloser, v6, pcbe);
      if ( ThreadpoolWork )
      {
        tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&void CloseThreadpoolWork(_TP_WORK *),0>::_Delete(&v16);
        v16 = ThreadpoolWork;
        if ( GetModuleHandleExW(4u, (LPCWSTR)_AdviseCloserAsync, v6 + 3) )
        {
          SubmitThreadpoolWork(ThreadpoolWork);
          CloseThreadpoolWork(ThreadpoolWork);
          v2 = 0;
          v16 = 0;
          v13 = 0;
          goto LABEL_16;
        }
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        v9 = 351;
      }
      else
      {
        v10 = GetLastError();
        v2 = v10;
        if ( v10 > 0 )
          v2 = (unsigned __int16)v10 | 0x80070000;
        v9 = 345;
      }
      Log_UnistoreHREvent_0(
        v2,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\clientobjects.cpp",
        v9);
      operator delete(v6);
      goto LABEL_16;
    }
    v2 = -2147024882;
    v3 = 335;
    v5 = 2147942414LL;
    v4 = 0;
  }
  else
  {
    v3 = 332;
    v4 = 1;
    v5 = (unsigned int)v1;
  }
  Log_UnistoreHREvent_0(
    v5,
    v4,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\clientobjects.cpp",
    v3);
LABEL_16:
  tlx::_UndoSolo__lambda_ce5fbef0b83ff89955beadd624ba0f6d___::__UndoSolo__lambda_ce5fbef0b83ff89955beadd624ba0f6d___(&v12);
  tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&void CloseThreadpoolWork(_TP_WORK *),0>::_Delete(&v16);
  return v2;
}

```

## disassembly

```asm
0x1800701e0  mov     [rsp-8+arg_10], rbx
0x1800701e5  mov     [rsp-8+arg_18], rdi
0x1800701ea  mov     [rsp-8+arg_0], rcx
0x1800701ef  push    rbp
0x1800701f0  mov     rbp, rsp
0x1800701f3  sub     rsp, 50h
0x1800701f7  lea     rax, [rbp+arg_0]
0x1800701fb  mov     [rbp+arg_8], 0
0x180070203  mov     [rbp+var_20], rax
0x180070207  mov     [rbp+var_18], 1
0x18007020b  call    ?InitializeUSCloserThreadpool@@YAJXZ; InitializeUSCloserThreadpool(void)
0x180070210  mov     edi, eax
0x180070212  test    eax, eax
0x180070214  jns     short loc_180070225
0x180070216  mov     r9d, 14Ch
0x18007021c  mov     edx, 1
0x180070221  mov     ecx, eax
0x180070223  jmp     short loc_180070246
0x180070225  mov     ecx, 20h ; ' '; Size
0x18007022a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007022f  mov     rbx, rax
0x180070232  test    rax, rax
0x180070235  jnz     short loc_180070257
0x180070237  mov     edi, 8007000Eh
0x18007023c  mov     r9d, 14Fh
0x180070242  mov     ecx, edi
0x180070244  xor     edx, edx
0x180070246  lea     r8, aOnecoreuapBase_59; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007024d  call    Log_UnistoreHREvent_0
0x180070252  jmp     loc_180070327
0x180070257  mov     rax, [rbp+arg_0]
0x18007025b  lea     rcx, [rbp+var_10]
0x18007025f  mov     [rbx], rax
0x180070262  call    ?GetClientThreadInfo@@YA?AU_CLIENT_THREAD_INFO@@XZ; GetClientThreadInfo(void)
0x180070267  mov     rdx, rbx; pv
0x18007026a  lea     rcx, ?_TP_AdviseCloser@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180070271  movups  xmm0, xmmword ptr [rax]
0x180070274  movdqu  xmmword ptr [rbx+8], xmm0
0x180070279  mov     r8, cs:pcbe; pcbe
0x180070280  call    cs:__imp_CreateThreadpoolWork
0x180070286  mov     rdi, rax
0x180070289  test    rax, rax
0x18007028c  jz      short loc_1800702F4
0x18007028e  lea     rcx, [rbp+arg_8]
0x180070292  call    ?_Delete@?$auto_xxx@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?CloseThreadpoolWork@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&CloseThreadpoolWork(_TP_WORK *),0>::_Delete(void)
0x180070297  lea     r8, [rbx+18h]; phModule
0x18007029b  mov     [rbp+arg_8], rdi
0x18007029f  lea     rdx, ?_AdviseCloserAsync@@YAJPEAU__MIDL_UnistoreService_0002@@@Z; lpModuleName
0x1800702a6  mov     ecx, 4; dwFlags
0x1800702ab  call    cs:__imp_GetModuleHandleExW
0x1800702b1  test    eax, eax
0x1800702b3  jnz     short loc_1800702D2
0x1800702b5  call    cs:__imp_GetLastError
0x1800702bb  mov     edi, eax
0x1800702bd  test    eax, eax
0x1800702bf  jle     short loc_1800702CA
0x1800702c1  movzx   edi, ax
0x1800702c4  or      edi, 80070000h
0x1800702ca  mov     r9d, 15Fh
0x1800702d0  jmp     short loc_18007030F
0x1800702d2  mov     rcx, rdi; pwk
0x1800702d5  call    cs:__imp_SubmitThreadpoolWork
0x1800702db  mov     rcx, rdi; pwk
0x1800702de  call    cs:__imp_CloseThreadpoolWork
0x1800702e4  xor     edi, edi
0x1800702e6  mov     [rbp+arg_8], 0
0x1800702ee  mov     [rbp+var_18], 0
0x1800702f2  jmp     short loc_180070327
0x1800702f4  call    cs:__imp_GetLastError
0x1800702fa  mov     edi, eax
0x1800702fc  test    eax, eax
0x1800702fe  jle     short loc_180070309
0x180070300  movzx   edi, ax
0x180070303  or      edi, 80070000h
0x180070309  mov     r9d, 159h
0x18007030f  lea     r8, aOnecoreuapBase_59; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180070316  xor     edx, edx
0x180070318  mov     ecx, edi
0x18007031a  call    Log_UnistoreHREvent_0
0x18007031f  mov     rcx, rbx; Block
0x180070322  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180070327  lea     rcx, [rbp+var_20]
0x18007032b  call    tlx___UndoSolo__lambda_ce5fbef0b83ff89955beadd624ba0f6d_______UndoSolo__lambda_ce5fbef0b83ff89955beadd624ba0f6d___
0x180070330  lea     rcx, [rbp+arg_8]
0x180070334  call    ?_Delete@?$auto_xxx@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?CloseThreadpoolWork@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&CloseThreadpoolWork(_TP_WORK *),0>::_Delete(void)
0x180070339  mov     rbx, [rsp+50h+arg_10]
0x18007033e  mov     eax, edi
0x180070340  mov     rdi, [rsp+50h+arg_18]
0x180070345  add     rsp, 50h
0x180070349  pop     rbp
0x18007034a  retn
```
