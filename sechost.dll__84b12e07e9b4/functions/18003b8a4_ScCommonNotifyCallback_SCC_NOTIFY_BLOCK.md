# ScCommonNotifyCallback(_SCC_NOTIFY_BLOCK *)

- ea: `0x18003b8a4`
- end: `0x18003ba6e`
- name: `?ScCommonNotifyCallback@@YAXPEAU_SCC_NOTIFY_BLOCK@@@Z`
- size: `458`
- prototype: `void __fastcall(struct _SCC_NOTIFY_BLOCK *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003b770`

## callees

- `0x18003b560`
- `0x18003b69c`
- `0x18003b8a4`
- `0x18003bccc`
- `0x18003c49c`
- `0x18004abac`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003b8eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003b8eb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003ba5f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003ba5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ba02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ba02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ba20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ba20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ba44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ba4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ba44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ba4f`
- `RPCRT4!RpcSmDestroyClientContext` at `0x18003b9c8`
- `RPCRT4!RpcSmDestroyClientContext` at `0x18003b9c8`

## pseudocode

```c
void __fastcall ScCommonNotifyCallback(struct _SCC_NOTIFY_BLOCK *a1)
{
  BOOL ModuleHandle; // esi
  __int64 v3; // rdx
  void **v4; // r14
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rcx
  int v8; // esi
  HMODULE hLibModule[6]; // [rsp+28h] [rbp-30h] BYREF
  struct _SCC_PENDING_CALLBACK_BLOCK *v10; // [rsp+60h] [rbp+8h] BYREF
  int v11; // [rsp+68h] [rbp+10h]
  int v12; // [rsp+70h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+20h] BYREF

  v10 = a1;
  hLibModule[0] = 0;
  ModuleHandle = 1;
  v11 = 1;
  hMem = 0;
  v12 = 0;
  if ( (*((_BYTE *)a1 + 4) & 8) == 0 )
  {
    ModuleHandle = GetModuleHandleExW(4u, *(LPCWSTR *)(*((_QWORD *)a1 + 1) + 8LL), hLibModule);
    v11 = ModuleHandle;
  }
  v3 = *((_QWORD *)a1 + 4);
  if ( (*(_BYTE *)(v3 + 60) & 1) != 0 )
  {
    v4 = (void **)((char *)a1 + 48);
    hLibModule[1] = (HMODULE)((char *)a1 + 48);
    if ( *((_QWORD *)a1 + 6) )
    {
      if ( ModuleHandle )
      {
        *(_DWORD *)(*((_QWORD *)a1 + 1) + 24LL) = ScGetNotifyResults(
                                                    *v4,
                                                    *(void **)(v3 + 64),
                                                    (struct _SC_RPC_NOTIFY_PARAMS_LIST **)&hMem);
        v5 = *((_QWORD *)a1 + 1);
        if ( !*(_DWORD *)(v5 + 24) )
        {
          *(_DWORD *)(v5 + 24) = *(_DWORD *)(*((_QWORD *)hMem + 2) + 80LL);
          v6 = *((_QWORD *)hMem + 2);
          v7 = *((_QWORD *)a1 + 1);
          *(_OWORD *)(v7 + 28) = *(_OWORD *)(v6 + 44);
          *(_OWORD *)(v7 + 44) = *(_OWORD *)(v6 + 60);
          *(_DWORD *)(v7 + 60) = *(_DWORD *)(v6 + 76);
          if ( *((_DWORD *)hMem + 2) == 2 )
            ScAddCreatedDeletedServiceNames(
              a1,
              (unsigned __int16 **)(*((_QWORD *)hMem + 2) + 96LL),
              *(_DWORD *)(*((_QWORD *)hMem + 2) + 88LL));
        }
      }
      if ( (unsigned int)RCloseNotifyHandle((char *)a1 + 48, &v12) )
        RpcSmDestroyClientContext(v4);
      *v4 = 0;
    }
  }
  if ( ModuleHandle )
  {
    v10 = 0;
    v8 = ScAddRemoveCallbackPendingBlock(a1, &v10, 1);
    if ( v8 )
      LeaveCriticalSection(&SccCritsec);
    (*(void (__fastcall **)(_QWORD))(*((_QWORD *)a1 + 1) + 8LL))(*((_QWORD *)a1 + 1));
    if ( v8 )
    {
      EnterCriticalSection(&SccCritsec);
      ScAddRemoveCallbackPendingBlock(a1, &v10, 0);
    }
  }
  if ( hMem )
  {
    LocalFree(*((HLOCAL *)hMem + 2));
    LocalFree(hMem);
  }
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
}

```

## disassembly

```asm
0x18003b8a4  mov     rax, rsp
0x18003b8a7  mov     [rax+8], rcx
0x18003b8ab  push    rsi
0x18003b8ac  push    rdi
0x18003b8ad  push    r14
0x18003b8af  sub     rsp, 40h
0x18003b8b3  mov     rdi, rcx
0x18003b8b6  mov     qword ptr [rax-30h], 0
0x18003b8be  mov     esi, 1
0x18003b8c3  mov     [rsp+58h+arg_8], esi
0x18003b8c7  mov     qword ptr [rax+20h], 0
0x18003b8cf  mov     dword ptr [rax+18h], 0
0x18003b8d6  test    byte ptr [rcx+4], 8
0x18003b8da  jnz     short loc_18003B8FB
0x18003b8dc  mov     rdx, [rcx+8]
0x18003b8e0  lea     r8, [rax-30h]; phModule
0x18003b8e4  mov     rdx, [rdx+8]; lpModuleName
0x18003b8e8  lea     ecx, [rsi+3]; dwFlags
0x18003b8eb  call    cs:__imp_GetModuleHandleExW
0x18003b8f1  neg     eax
0x18003b8f3  sbb     ecx, ecx
0x18003b8f5  and     esi, ecx
0x18003b8f7  mov     [rsp+58h+arg_8], esi
0x18003b8fb  mov     rdx, [rdi+20h]
0x18003b8ff  test    byte ptr [rdx+3Ch], 1
0x18003b903  jz      loc_18003B9D5
0x18003b909  lea     r14, [rdi+30h]
0x18003b90d  mov     [rsp+58h+var_28], r14
0x18003b912  cmp     qword ptr [r14], 0
0x18003b916  jz      loc_18003B9D5
0x18003b91c  test    esi, esi
0x18003b91e  jz      short loc_18003B995
0x18003b920  lea     r8, [rsp+58h+hMem]; struct _SC_RPC_NOTIFY_PARAMS_LIST **
0x18003b925  mov     rdx, [rdx+40h]; void *
0x18003b929  mov     rcx, [r14]; void *
0x18003b92c  call    ?ScGetNotifyResults@@YAKPEAX0PEAPEAU_SC_RPC_NOTIFY_PARAMS_LIST@@@Z; ScGetNotifyResults(void *,void *,_SC_RPC_NOTIFY_PARAMS_LIST * *)
0x18003b931  mov     rcx, [rdi+8]
0x18003b935  mov     [rcx+18h], eax
0x18003b938  mov     rdx, [rdi+8]
0x18003b93c  cmp     dword ptr [rdx+18h], 0
0x18003b940  jnz     short loc_18003B995
0x18003b942  mov     rax, [rsp+58h+hMem]
0x18003b947  mov     rcx, [rax+10h]
0x18003b94b  mov     eax, [rcx+50h]
0x18003b94e  mov     [rdx+18h], eax
0x18003b951  mov     rax, [rsp+58h+hMem]
0x18003b956  mov     rax, [rax+10h]
0x18003b95a  mov     rcx, [rdi+8]
0x18003b95e  movups  xmm0, xmmword ptr [rax+2Ch]
0x18003b962  movups  xmmword ptr [rcx+1Ch], xmm0
0x18003b966  movups  xmm1, xmmword ptr [rax+3Ch]
0x18003b96a  movups  xmmword ptr [rcx+2Ch], xmm1
0x18003b96e  mov     eax, [rax+4Ch]
0x18003b971  mov     [rcx+3Ch], eax
0x18003b974  mov     r8, [rsp+58h+hMem]
0x18003b979  cmp     dword ptr [r8+8], 2
0x18003b97e  jnz     short loc_18003B995
0x18003b980  mov     r8, [r8+10h]
0x18003b984  lea     rdx, [r8+60h]; unsigned __int16 **
0x18003b988  mov     r8d, [r8+58h]; unsigned int
0x18003b98c  mov     rcx, rdi; struct _SCC_NOTIFY_BLOCK *
0x18003b98f  call    ?ScAddCreatedDeletedServiceNames@@YAXPEAU_SCC_NOTIFY_BLOCK@@PEAPEAGK@Z; ScAddCreatedDeletedServiceNames(_SCC_NOTIFY_BLOCK *,ushort * *,ulong)
0x18003b994  nop
0x18003b995  lea     rdx, [rsp+58h+arg_10]
0x18003b99a  mov     rcx, r14
0x18003b99d  call    RCloseNotifyHandle
0x18003b9a2  mov     [rsp+58h+var_38], eax
0x18003b9a6  jmp     short loc_18003B9C1
0x18003b9a8  mov     ecx, eax; unsigned int
0x18003b9aa  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x18003b9af  mov     [rsp+58h+var_38], eax
0x18003b9b3  mov     rdi, [rsp+58h+arg_0]
0x18003b9b8  mov     esi, [rsp+58h+arg_8]
0x18003b9bc  mov     r14, [rsp+58h+var_28]
0x18003b9c1  test    eax, eax
0x18003b9c3  jz      short loc_18003B9CE
0x18003b9c5  mov     rcx, r14; ContextHandle
0x18003b9c8  call    cs:__imp_RpcSmDestroyClientContext
0x18003b9ce  mov     qword ptr [r14], 0
0x18003b9d5  test    esi, esi
0x18003b9d7  jz      short loc_18003BA36
0x18003b9d9  mov     [rsp+58h+arg_0], 0
0x18003b9e2  mov     r8d, 1; int
0x18003b9e8  lea     rdx, [rsp+58h+arg_0]; struct _SCC_PENDING_CALLBACK_BLOCK **
0x18003b9ed  mov     rcx, rdi; struct _SCC_NOTIFY_BLOCK *
0x18003b9f0  call    ?ScAddRemoveCallbackPendingBlock@@YAHPEAU_SCC_NOTIFY_BLOCK@@PEAPEAU_SCC_PENDING_CALLBACK_BLOCK@@H@Z; ScAddRemoveCallbackPendingBlock(_SCC_NOTIFY_BLOCK *,_SCC_PENDING_CALLBACK_BLOCK * *,int)
0x18003b9f5  mov     esi, eax
0x18003b9f7  test    eax, eax
0x18003b9f9  jz      short loc_18003BA08
0x18003b9fb  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003ba02  call    cs:__imp_LeaveCriticalSection
0x18003ba08  mov     rcx, [rdi+8]
0x18003ba0c  mov     rax, [rcx+8]
0x18003ba10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba15  test    esi, esi
0x18003ba17  jz      short loc_18003BA36
0x18003ba19  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003ba20  call    cs:__imp_EnterCriticalSection
0x18003ba26  xor     r8d, r8d; int
0x18003ba29  lea     rdx, [rsp+58h+arg_0]; struct _SCC_PENDING_CALLBACK_BLOCK **
0x18003ba2e  mov     rcx, rdi; struct _SCC_NOTIFY_BLOCK *
0x18003ba31  call    ?ScAddRemoveCallbackPendingBlock@@YAHPEAU_SCC_NOTIFY_BLOCK@@PEAPEAU_SCC_PENDING_CALLBACK_BLOCK@@H@Z; ScAddRemoveCallbackPendingBlock(_SCC_NOTIFY_BLOCK *,_SCC_PENDING_CALLBACK_BLOCK * *,int)
0x18003ba36  mov     rcx, [rsp+58h+hMem]
0x18003ba3b  test    rcx, rcx
0x18003ba3e  jz      short loc_18003BA55
0x18003ba40  mov     rcx, [rcx+10h]; hMem
0x18003ba44  call    cs:__imp_LocalFree
0x18003ba4a  mov     rcx, [rsp+58h+hMem]; hMem
0x18003ba4f  call    cs:__imp_LocalFree
0x18003ba55  mov     rcx, [rsp+58h+hLibModule]; hLibModule
0x18003ba5a  test    rcx, rcx
0x18003ba5d  jz      short loc_18003BA65
0x18003ba5f  call    cs:__imp_FreeLibrary
0x18003ba65  add     rsp, 40h
0x18003ba69  pop     r14
0x18003ba6b  pop     rdi
0x18003ba6c  pop     rsi
0x18003ba6d  retn
0x1800504ac  push    rbp
0x1800504ae  sub     rsp, 20h
0x1800504b2  mov     rbp, rdx
0x1800504b5  mov     rcx, [rcx]
0x1800504b8  mov     ecx, [rcx]; ExceptionCode
0x1800504ba  call    cs:__imp_I_RpcExceptionFilter
0x1800504c0  nop
0x1800504c1  add     rsp, 20h
0x1800504c5  pop     rbp
0x1800504c6  retn
```
