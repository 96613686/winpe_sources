# _ObjectCloserAsync(__MIDL_UnistoreService_0001 *)

- ea: `0x180024220`
- end: `0x1800243a6`
- name: `?_ObjectCloserAsync@@YAJPEAU__MIDL_UnistoreService_0001@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(struct __MIDL_UnistoreService_0001 *)`
- caller_count: `17`
- callee_count: `10`
- tags: `file_ops, service_task`

## callers

- `0x180023fec`
- `0x1800390c0`
- `0x180057b64`
- `0x1800644a0`
- `0x180072c34`
- `0x180073228`
- `0x1800745ec`
- `0x1800746c8`
- `0x1800766f4`
- `0x180076a9c`
- `0x180076d08`
- `0x180076de4`
- `0x180078660`
- `0x18007873c`
- `0x1800a1724`
- `0x1800a1750`
- `0x1800a1784`

## callees

- `0x1800068f0`
- `0x180023f9c`
- `0x180024220`
- `0x1800243ac`
- `0x1800703a0`
- `0x18007407c`
- `0x180074390`
- `0x180078a34`
- `0x180078a4c`
- `0x1800aaeb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024337`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002432d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002432d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180024315`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002438e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180024315`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002438e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180024384`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180024384`

## string_xrefs

- `0x18002425c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\clientobjects.cpp`
- `0x180024296`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\clientobjects.cpp`
- `0x1800242e8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\clientobjects.cpp`
- `0x180024352`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\clientobjects.cpp`

## pseudocode

```c
__int64 __fastcall _ObjectCloserAsync(struct __MIDL_UnistoreService_0001 *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  HMODULE *v4; // rbx
  unsigned int v5; // edi
  void (*v6)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *); // rcx
  int v7; // eax
  signed int LastError; // eax
  struct __MIDL_UnistoreService_0001 **v9; // [rsp+30h] [rbp-20h] BYREF
  char v10; // [rsp+38h] [rbp-18h]
  _BYTE v11[16]; // [rsp+40h] [rbp-10h] BYREF
  struct __MIDL_UnistoreService_0001 *v12; // [rsp+60h] [rbp+10h] BYREF
  PTP_WORK pwk; // [rsp+68h] [rbp+18h] BYREF

  v12 = a1;
  pwk = 0;
  v9 = &v12;
  v10 = 1;
  v1 = InitializeUSCloserThreadpool();
  v2 = v1;
  if ( v1 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v1,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\clientobjects.cpp",
      277);
    _ObjectCloser(v12);
    return v2;
  }
  v4 = (HMODULE *)operator new(0x20u);
  if ( !v4 )
  {
    v5 = -2147024882;
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\clientobjects.cpp",
      280);
LABEL_12:
    tlx::_UndoSolo__lambda_a0f3180cc556f0985a2cfb22a9e22e33___::__UndoSolo__lambda_a0f3180cc556f0985a2cfb22a9e22e33___(&v9);
    tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&void CloseThreadpoolWork(_TP_WORK *),0>::_Delete(&pwk);
    return v5;
  }
  *v4 = (HMODULE)v12;
  *(_OWORD *)(v4 + 1) = *(_OWORD *)GetClientThreadInfo(v11);
  v7 = _CreateThreadpoolWorkHelper(v6, v4, pcbe, &pwk);
  v5 = v7;
  if ( v7 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v7,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\clientobjects.cpp",
      290);
    operator delete(v4);
    _ObjectCloser(v12);
    if ( pwk )
      CloseThreadpoolWork(pwk);
    return v5;
  }
  if ( !GetModuleHandleExW(4u, (LPCWSTR)_ObjectCloserAsync, v4 + 3) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    Log_UnistoreHREvent_0(
      v5,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\clientobjects.cpp",
      296);
    operator delete(v4);
    goto LABEL_12;
  }
  SubmitThreadpoolWork(pwk);
  CloseThreadpoolWork(pwk);
  return 0;
}

```

## disassembly

```asm
0x180024220  mov     [rsp-8+arg_10], rbx
0x180024225  mov     [rsp-8+arg_18], rdi
0x18002422a  mov     [rsp-8+arg_0], rcx
0x18002422f  push    rbp
0x180024230  mov     rbp, rsp
0x180024233  sub     rsp, 50h
0x180024237  lea     rax, [rbp+arg_0]
0x18002423b  mov     [rbp+pwk], 0
0x180024243  mov     [rbp+var_20], rax
0x180024247  mov     [rbp+var_18], 1
0x18002424b  call    ?InitializeUSCloserThreadpool@@YAJXZ; InitializeUSCloserThreadpool(void)
0x180024250  mov     ebx, eax
0x180024252  test    eax, eax
0x180024254  jns     short loc_18002427F
0x180024256  mov     r9d, 115h
0x18002425c  lea     r8, aOnecoreuapBase_59; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180024263  mov     edx, 1
0x180024268  mov     ecx, eax
0x18002426a  call    Log_UnistoreHREvent_0
0x18002426f  mov     rcx, [rbp+arg_0]; struct __MIDL_UnistoreService_0001 *
0x180024273  call    ?_ObjectCloser@@YAXPEAU__MIDL_UnistoreService_0001@@@Z; _ObjectCloser(__MIDL_UnistoreService_0001 *)
0x180024278  mov     eax, ebx
0x18002427a  jmp     loc_180024396
0x18002427f  mov     ecx, 20h ; ' '; Size
0x180024284  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024289  mov     rbx, rax
0x18002428c  test    rax, rax
0x18002428f  jnz     short loc_1800242B1
0x180024291  mov     edi, 8007000Eh
0x180024296  lea     r8, aOnecoreuapBase_59; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002429d  mov     ecx, edi
0x18002429f  mov     r9d, 118h
0x1800242a5  xor     edx, edx
0x1800242a7  call    Log_UnistoreHREvent_0
0x1800242ac  jmp     loc_18002436A
0x1800242b1  mov     rax, [rbp+arg_0]
0x1800242b5  lea     rcx, [rbp+var_10]
0x1800242b9  mov     [rbx], rax
0x1800242bc  call    ?GetClientThreadInfo@@YA?AU_CLIENT_THREAD_INFO@@XZ; GetClientThreadInfo(void)
0x1800242c1  lea     r9, [rbp+pwk]; struct _TP_WORK **
0x1800242c5  mov     rdx, rbx; void *
0x1800242c8  movups  xmm0, xmmword ptr [rax]
0x1800242cb  movdqu  xmmword ptr [rbx+8], xmm0
0x1800242d0  mov     r8, cs:pcbe; struct _TP_CALLBACK_ENVIRON_V3 *
0x1800242d7  call    ?_CreateThreadpoolWorkHelper@@YAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1PEAU_TP_CALLBACK_ENVIRON_V3@@PEAPEAU2@@Z; _CreateThreadpoolWorkHelper(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *,_TP_CALLBACK_ENVIRON_V3 *,_TP_WORK * *)
0x1800242dc  mov     edi, eax
0x1800242de  test    eax, eax
0x1800242e0  jns     short loc_18002431D
0x1800242e2  mov     r9d, 122h
0x1800242e8  lea     r8, aOnecoreuapBase_59; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800242ef  mov     edx, 1
0x1800242f4  mov     ecx, eax
0x1800242f6  call    Log_UnistoreHREvent_0
0x1800242fb  mov     rcx, rbx; Block
0x1800242fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024303  mov     rcx, [rbp+arg_0]; struct __MIDL_UnistoreService_0001 *
0x180024307  call    ?_ObjectCloser@@YAXPEAU__MIDL_UnistoreService_0001@@@Z; _ObjectCloser(__MIDL_UnistoreService_0001 *)
0x18002430c  mov     rcx, [rbp+pwk]; pwk
0x180024310  test    rcx, rcx
0x180024313  jz      short loc_18002437C
0x180024315  call    cs:__imp_CloseThreadpoolWork
0x18002431b  jmp     short loc_18002437C
0x18002431d  lea     r8, [rbx+18h]; phModule
0x180024321  mov     ecx, 4; dwFlags
0x180024326  lea     rdx, ?_ObjectCloserAsync@@YAJPEAU__MIDL_UnistoreService_0001@@@Z; lpModuleName
0x18002432d  call    cs:__imp_GetModuleHandleExW
0x180024333  test    eax, eax
0x180024335  jnz     short loc_180024380
0x180024337  call    cs:__imp_GetLastError
0x18002433d  mov     edi, eax
0x18002433f  test    eax, eax
0x180024341  jle     short loc_18002434C
0x180024343  movzx   edi, ax
0x180024346  or      edi, 80070000h
0x18002434c  mov     r9d, 128h
0x180024352  lea     r8, aOnecoreuapBase_59; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180024359  xor     edx, edx
0x18002435b  mov     ecx, edi
0x18002435d  call    Log_UnistoreHREvent_0
0x180024362  mov     rcx, rbx; Block
0x180024365  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002436a  lea     rcx, [rbp+var_20]
0x18002436e  call    tlx___UndoSolo__lambda_a0f3180cc556f0985a2cfb22a9e22e33_______UndoSolo__lambda_a0f3180cc556f0985a2cfb22a9e22e33___
0x180024373  lea     rcx, [rbp+pwk]
0x180024377  call    ?_Delete@?$auto_xxx@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?CloseThreadpoolWork@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_WORK *,void (*)(_TP_WORK *),&CloseThreadpoolWork(_TP_WORK *),0>::_Delete(void)
0x18002437c  mov     eax, edi
0x18002437e  jmp     short loc_180024396
0x180024380  mov     rcx, [rbp+pwk]; pwk
0x180024384  call    cs:__imp_SubmitThreadpoolWork
0x18002438a  mov     rcx, [rbp+pwk]; pwk
0x18002438e  call    cs:__imp_CloseThreadpoolWork
0x180024394  xor     eax, eax
0x180024396  mov     rbx, [rsp+50h+arg_10]
0x18002439b  mov     rdi, [rsp+50h+arg_18]
0x1800243a0  add     rsp, 50h
0x1800243a4  pop     rbp
0x1800243a5  retn
```
