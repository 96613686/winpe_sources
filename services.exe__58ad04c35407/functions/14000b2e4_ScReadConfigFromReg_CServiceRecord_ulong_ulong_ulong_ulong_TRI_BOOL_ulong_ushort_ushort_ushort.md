# ScReadConfigFromReg(CServiceRecord *,ulong *,ulong *,ulong *,ulong *,_TRI_BOOL *,ulong *,ushort * *,ushort * *,ushort * *)

- ea: `0x14000b2e4`
- end: `0x14000b66d`
- name: `?ScReadConfigFromReg@@YAKPEAVCServiceRecord@@PEAK111PEAW4_TRI_BOOL@@1PEAPEAG33@Z`
- size: `905`
- prototype: `unsigned int __fastcall(struct CServiceRecord *this, unsigned int *, unsigned int *, unsigned int *, unsigned int *, enum _TRI_BOOL *, unsigned int *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x140009910`
- `0x1400361ec`

## callees

- `0x140003e54`
- `0x14000b2e4`
- `0x14000b674`
- `0x14000b7e4`
- `0x14000b958`
- `0x14000bebc`
- `0x14000c120`
- `0x14000c220`
- `0x14000c310`
- `0x14000c8f0`
- `0x14000c988`
- `0x14000cee0`
- `0x14000cf60`
- `0x14000d1dc`
- `0x140013b0c`
- `0x1400188fc`
- `0x14001a350`
- `0x1400250c8`
- `0x14004401c`
- `0x140094020`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x14000b3f4`
- `RPCRT4!RpcImpersonateClient` at `0x14000b3f4`
- `RPCRT4!RpcRevertToSelf` at `0x14000b4b9`
- `RPCRT4!RpcRevertToSelf` at `0x14000b4b9`
- `ntdll!NtClose` at `0x14000b4cd`
- `ntdll!NtClose` at `0x14000b4cd`
- `ntdll!RtlNtStatusToDosError` at `0x14000b4d5`
- `ntdll!RtlNtStatusToDosError` at `0x14000b4d5`
- `ntdll!RtlFreeHeap` at `0x14000b4b0`
- `ntdll!RtlFreeHeap` at `0x14000b5da`
- `ntdll!RtlFreeHeap` at `0x14000b4b0`
- `ntdll!RtlFreeHeap` at `0x14000b5da`
- `ntdll!RtlAllocateHeap` at `0x14000b520`
- `ntdll!RtlAllocateHeap` at `0x14000b520`

## pseudocode

```c
__int64 __fastcall ScReadConfigFromReg(
        struct CServiceRecord *this,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        enum _TRI_BOOL *a6,
        unsigned int *a7,
        unsigned __int16 **a8,
        unsigned __int16 **a9,
        unsigned __int16 **a10)
{
  __int64 result; // rax
  unsigned int ServiceType; // ebx
  RPC_STATUS v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned __int16 v19; // ax
  HKEY v20; // r14
  unsigned __int16 v21; // r15
  unsigned __int16 *v22; // r14
  RPC_STATUS v23; // eax
  unsigned int v24; // edi
  NTSTATUS v25; // eax
  unsigned __int16 *JITReadDisplayName; // r14
  __int64 v27; // rax
  SIZE_T v28; // r15
  unsigned __int16 *Heap; // rax
  HANDLE Handle; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 *v31; // [rsp+38h] [rbp-10h] BYREF

  Handle = 0;
  result = CServiceRecord::OpenServiceConfigKey(this, 0x20019u, (__int64)a3, (HKEY *)&Handle);
  if ( !(_DWORD)result )
  {
    ServiceType = ScReadServiceType((HKEY)Handle, a2);
    if ( !ServiceType )
    {
      ServiceType = ScReadStartType(
                      *((struct _SERVICE_CONFIG_ROOT **)this + 27),
                      (HKEY)Handle,
                      *((const unsigned __int16 **)this + 7),
                      *a2,
                      *((_DWORD *)this + 42) & 1,
                      a3);
      if ( !ServiceType
        && (!a4
         || (ServiceType = ScReadGlobalStartType(
                             *((struct _SERVICE_CONFIG_ROOT **)this + 27),
                             (HKEY)Handle,
                             *((const unsigned __int16 **)this + 7),
                             (*(_BYTE *)a2 & 0xB) != 0,
                             *((_DWORD *)this + 42) & 1,
                             a4)) == 0) )
      {
        ServiceType = ScReadErrorControl((HKEY)Handle, a5);
        if ( !ServiceType && (!a6 || (ServiceType = ScReadServiceManagedAccount((HKEY)Handle, a6)) == 0) )
        {
          if ( ScReadTag((HKEY)Handle, a7) )
            *a7 = 0;
          if ( a8 && ScReadDependencies((HKEY)Handle, a8, *((const unsigned __int16 **)this + 7)) )
            *a8 = 0;
          if ( ScAllocateAndReadConfigValue((HKEY)Handle, L"Group", a9, 0) )
            *a9 = 0;
          if ( a10 )
          {
            v16 = RpcImpersonateClient(0);
            ServiceType = v16;
            if ( v16 )
            {
              ScLogImpersonateFailureEvent(v16);
            }
            else
            {
              if ( g_SystemLanguageId == ((unsigned __int16 (*)(void))g_pScExtFunctionPointers[7])() )
              {
                JITReadDisplayName = CServiceRecord::GetJITReadDisplayName(this, v17, v18);
                v27 = -1;
                do
                  ++v27;
                while ( JITReadDisplayName[v27] );
                v28 = (unsigned int)(2 * v27 + 2);
                Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v28);
                *a10 = Heap;
                if ( Heap )
                {
                  StringCbCopyW(Heap, (unsigned int)v28, JITReadDisplayName);
                }
                else
                {
                  ServiceType = 8;
                  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                  {
                    WPP_SF_S(
                      WPP_GLOBAL_Control->StubInfo,
                      138,
                      WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
                      *((_QWORD *)this + 7));
                  }
                }
              }
              else
              {
                v19 = (*(__int64 (__fastcall **)(struct CServiceRecord *))(*(_QWORD *)this + 48LL))(this);
                v20 = (HKEY)Handle;
                v31 = 0;
                v21 = v19;
                ServiceType = ScReadOptionalString((HKEY)Handle, L"DisplayName", a10, 0);
                if ( !ServiceType && (unsigned int)ScIsIndirectString(*a10, 0) )
                {
                  ServiceType = ScReadStringIndirect(v20, L"DisplayName", *a10, v21, &v31);
                  if ( ServiceType )
                  {
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a10);
                    *a10 = 0;
                  }
                  else
                  {
                    v22 = v31;
                    if ( v31 )
                    {
                      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a10);
                      *a10 = v22;
                    }
                  }
                }
              }
              v23 = RpcRevertToSelf();
              v24 = v23;
              if ( v23 )
              {
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                {
                  WPP_SF_Sd(
                    WPP_GLOBAL_Control->StubInfo,
                    139,
                    (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
                    *((_QWORD *)this + 7),
                    v23);
                }
                ScLogEvent(5u, L"RpcRevertToSelf", v24);
              }
            }
          }
        }
      }
    }
    v25 = NtClose(Handle);
    RtlNtStatusToDosError(v25);
    return ServiceType;
  }
  return result;
}

```

## disassembly

```asm
0x14000b2e4  push    rbp
0x14000b2e6  push    rbx
0x14000b2e7  push    rsi
0x14000b2e8  push    rdi
0x14000b2e9  push    r12
0x14000b2eb  push    r13
0x14000b2ed  push    r14
0x14000b2ef  push    r15
0x14000b2f1  mov     rbp, rsp
0x14000b2f4  sub     rsp, 48h
0x14000b2f8  mov     r14, r9
0x14000b2fb  mov     rdi, rdx
0x14000b2fe  xor     r12d, r12d
0x14000b301  lea     r9, [rbp+Handle]; HKEY *
0x14000b305  mov     edx, 20019h; unsigned int
0x14000b30a  mov     [rbp+Handle], r12
0x14000b30e  mov     r15, r8
0x14000b311  mov     rsi, rcx
0x14000b314  call    ?OpenServiceConfigKey@CServiceRecord@@QEAAKKHPEAPEAUHKEY__@@@Z; CServiceRecord::OpenServiceConfigKey(ulong,int,HKEY__ * *)
0x14000b319  test    eax, eax
0x14000b31b  jnz     loc_14000B4DD
0x14000b321  mov     rcx, [rbp+Handle]; KeyHandle
0x14000b325  mov     rdx, rdi; unsigned int *
0x14000b328  call    ?ScReadServiceType@@YAKPEAUHKEY__@@PEAK@Z; ScReadServiceType(HKEY__ *,ulong *)
0x14000b32d  mov     ebx, eax
0x14000b32f  test    eax, eax
0x14000b331  jnz     loc_14000B4C9
0x14000b337  mov     eax, [rsi+0A8h]
0x14000b33d  mov     r9d, [rdi]; unsigned int
0x14000b340  and     eax, 1
0x14000b343  mov     r8, [rsi+38h]; unsigned __int16 *
0x14000b347  mov     rdx, [rbp+Handle]; HKEY
0x14000b34b  mov     rcx, [rsi+0D8h]; struct _SERVICE_CONFIG_ROOT *
0x14000b352  mov     [rsp+48h+var_20], r15; unsigned int *
0x14000b357  mov     dword ptr [rsp+48h+var_28], eax; int
0x14000b35b  call    ?ScReadStartType@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEAUHKEY__@@PEBGKHPEAK@Z; ScReadStartType(_SERVICE_CONFIG_ROOT *,HKEY__ *,ushort const *,ulong,int,ulong *)
0x14000b360  mov     ebx, eax
0x14000b362  test    eax, eax
0x14000b364  jnz     loc_14000B4C9
0x14000b36a  test    r14, r14
0x14000b36d  jnz     loc_14000B545
0x14000b373  mov     rdx, [rbp+arg_20]; unsigned int *
0x14000b377  mov     rcx, [rbp+Handle]; KeyHandle
0x14000b37b  call    ?ScReadErrorControl@@YAKPEAUHKEY__@@PEAK@Z; ScReadErrorControl(HKEY__ *,ulong *)
0x14000b380  mov     ebx, eax
0x14000b382  test    eax, eax
0x14000b384  jnz     loc_14000B4C9
0x14000b38a  mov     rdx, [rbp+arg_28]; enum _TRI_BOOL *
0x14000b38e  test    rdx, rdx
0x14000b391  jnz     loc_14000B5A4
0x14000b397  mov     rdi, [rbp+arg_30]
0x14000b39b  mov     rcx, [rbp+Handle]; KeyHandle
0x14000b39f  mov     rdx, rdi; unsigned int *
0x14000b3a2  call    ?ScReadTag@@YAKPEAUHKEY__@@PEAK@Z; ScReadTag(HKEY__ *,ulong *)
0x14000b3a7  test    eax, eax
0x14000b3a9  jz      short loc_14000B3AE
0x14000b3ab  mov     [rdi], r12d
0x14000b3ae  mov     rdi, [rbp+arg_38]
0x14000b3b5  test    rdi, rdi
0x14000b3b8  jnz     loc_14000B584
0x14000b3be  mov     rdi, [rbp+arg_40]
0x14000b3c5  lea     rdx, aGroup; "Group"
0x14000b3cc  mov     rcx, [rbp+Handle]; KeyHandle
0x14000b3d0  mov     r8, rdi; unsigned __int16 **
0x14000b3d3  xor     r9d, r9d; unsigned int *
0x14000b3d6  call    ?ScAllocateAndReadConfigValue@@YAKPEAUHKEY__@@PEBGPEAPEAGPEAK@Z; ScAllocateAndReadConfigValue(HKEY__ *,ushort const *,ushort * *,ulong *)
0x14000b3db  test    eax, eax
0x14000b3dd  jz      short loc_14000B3E2
0x14000b3df  mov     [rdi], r12
0x14000b3e2  mov     rdi, [rbp+arg_48]
0x14000b3e9  test    rdi, rdi
0x14000b3ec  jz      loc_14000B4C9
0x14000b3f2  xor     ecx, ecx; BindingHandle
0x14000b3f4  call    cs:__imp_RpcImpersonateClient
0x14000b3fa  mov     ebx, eax
0x14000b3fc  test    eax, eax
0x14000b3fe  jnz     loc_14000B5BC
0x14000b404  mov     rax, cs:?g_pScExtFunctionPointers@@3PEAPEAXEA; void * * g_pScExtFunctionPointers
0x14000b40b  mov     rax, [rax+38h]
0x14000b40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b414  cmp     cs:?g_SystemLanguageId@@3GA, ax; ushort g_SystemLanguageId
0x14000b41b  lea     r13, WPP_GLOBAL_Control
0x14000b422  mov     rcx, rsi; this
0x14000b425  jz      loc_14000B4EE
0x14000b42b  mov     rax, [rsi]
0x14000b42e  mov     rax, [rax+30h]
0x14000b432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b437  mov     r14, [rbp+Handle]
0x14000b43b  lea     rdx, aDisplayname; "DisplayName"
0x14000b442  mov     rcx, r14; HKEY
0x14000b445  mov     [rbp+var_10], r12
0x14000b449  xor     r9d, r9d; unsigned int *
0x14000b44c  mov     r8, rdi; unsigned __int16 **
0x14000b44f  movzx   r15d, ax
0x14000b453  call    ?ScReadOptionalString@@YAKPEAUHKEY__@@PEBGPEAPEAGPEAK@Z; ScReadOptionalString(HKEY__ *,ushort const *,ushort * *,ulong *)
0x14000b458  mov     ebx, eax
0x14000b45a  test    eax, eax
0x14000b45c  jnz     short loc_14000B4B9
0x14000b45e  mov     rcx, [rdi]; Str
0x14000b461  xor     edx, edx; int *
0x14000b463  call    ?ScIsIndirectString@@YAHPEAGPEAH@Z; ScIsIndirectString(ushort *,int *)
0x14000b468  test    eax, eax
0x14000b46a  jz      short loc_14000B4B9
0x14000b46c  mov     r8, [rdi]; unsigned __int16 *
0x14000b46f  lea     rax, [rbp+var_10]
0x14000b473  movzx   r9d, r15w; unsigned __int16
0x14000b477  mov     [rsp+48h+var_28], rax; unsigned __int16 **
0x14000b47c  lea     rdx, aDisplayname; "DisplayName"
0x14000b483  mov     rcx, r14; hKey
0x14000b486  call    ?ScReadStringIndirect@@YAKPEAUHKEY__@@PEAG1GPEAPEAG@Z; ScReadStringIndirect(HKEY__ *,ushort *,ushort *,ushort,ushort * *)
0x14000b48b  mov     ebx, eax
0x14000b48d  test    eax, eax
0x14000b48f  jnz     loc_14000B5C8
0x14000b495  mov     r14, [rbp+var_10]
0x14000b499  test    r14, r14
0x14000b49c  jz      short loc_14000B4B9
0x14000b49e  mov     rcx, gs:60h
0x14000b4a7  xor     edx, edx; Flags
0x14000b4a9  mov     r8, [rdi]; P
0x14000b4ac  mov     rcx, [rcx+30h]; HeapHandle
0x14000b4b0  call    cs:__imp_RtlFreeHeap
0x14000b4b6  mov     [rdi], r14
0x14000b4b9  call    cs:__imp_RpcRevertToSelf
0x14000b4bf  mov     edi, eax
0x14000b4c1  test    eax, eax
0x14000b4c3  jnz     loc_14000B625
0x14000b4c9  mov     rcx, [rbp+Handle]; Handle
0x14000b4cd  call    cs:__imp_NtClose
0x14000b4d3  mov     ecx, eax; Status
0x14000b4d5  call    cs:__imp_RtlNtStatusToDosError
0x14000b4db  mov     eax, ebx
0x14000b4dd  add     rsp, 48h
0x14000b4e1  pop     r15
0x14000b4e3  pop     r14
0x14000b4e5  pop     r13
0x14000b4e7  pop     r12
0x14000b4e9  pop     rdi
0x14000b4ea  pop     rsi
0x14000b4eb  pop     rbx
0x14000b4ec  pop     rbp
0x14000b4ed  retn
0x14000b4ee  call    ?GetJITReadDisplayName@CServiceRecord@@QEAAPEAGXZ; CServiceRecord::GetJITReadDisplayName(void)
0x14000b4f3  mov     r14, rax
0x14000b4f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000b4fa  inc     rax
0x14000b4fd  cmp     [r14+rax*2], r12w
0x14000b502  jnz     short loc_14000B4FA
0x14000b504  mov     rcx, gs:60h
0x14000b50d  lea     eax, ds:2[rax*2]
0x14000b514  mov     r8d, eax; Size
0x14000b517  xor     edx, edx; Flags
0x14000b519  mov     r15d, eax
0x14000b51c  mov     rcx, [rcx+30h]; HeapHandle
0x14000b520  call    cs:__imp_RtlAllocateHeap
0x14000b526  mov     [rdi], rax
0x14000b529  test    rax, rax
0x14000b52c  jz      loc_14000B5E8
0x14000b532  mov     r8, r14; unsigned __int16 *
0x14000b535  mov     edx, r15d; unsigned __int64
0x14000b538  mov     rcx, rax; unsigned __int16 *
0x14000b53b  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14000b540  jmp     loc_14000B4B9
0x14000b545  mov     eax, [rsi+0A8h]
0x14000b54b  mov     r9d, r12d
0x14000b54e  mov     r8, [rsi+38h]; unsigned __int16 *
0x14000b552  and     eax, 1
0x14000b555  test    byte ptr [rdi], 0Bh
0x14000b558  mov     rdx, [rbp+Handle]; HKEY
0x14000b55c  mov     rcx, [rsi+0D8h]; struct _SERVICE_CONFIG_ROOT *
0x14000b563  setnz   r9b; int
0x14000b567  mov     [rsp+48h+var_20], r14; unsigned int *
0x14000b56c  mov     dword ptr [rsp+48h+var_28], eax; int
0x14000b570  call    ?ScReadGlobalStartType@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEAUHKEY__@@PEBGHHPEAK@Z; ScReadGlobalStartType(_SERVICE_CONFIG_ROOT *,HKEY__ *,ushort const *,int,int,ulong *)
0x14000b575  mov     ebx, eax
0x14000b577  test    eax, eax
0x14000b579  jz      loc_14000B373
0x14000b57f  jmp     loc_14000B4C9
0x14000b584  mov     r8, [rsi+38h]; unsigned __int16 *
0x14000b588  mov     rdx, rdi; unsigned __int16 **
0x14000b58b  mov     rcx, [rbp+Handle]; KeyHandle
0x14000b58f  call    ?ScReadDependencies@@YAKPEAUHKEY__@@PEAPEAGPEBG@Z; ScReadDependencies(HKEY__ *,ushort * *,ushort const *)
0x14000b594  test    eax, eax
0x14000b596  jz      loc_14000B3BE
0x14000b59c  mov     [rdi], r12
0x14000b59f  jmp     loc_14000B3BE
0x14000b5a4  mov     rcx, [rbp+Handle]; KeyHandle
0x14000b5a8  call    ?ScReadServiceManagedAccount@@YAKPEAUHKEY__@@PEAW4_TRI_BOOL@@@Z; ScReadServiceManagedAccount(HKEY__ *,_TRI_BOOL *)
0x14000b5ad  mov     ebx, eax
0x14000b5af  test    eax, eax
0x14000b5b1  jz      loc_14000B397
0x14000b5b7  jmp     loc_14000B4C9
0x14000b5bc  mov     ecx, eax; int
0x14000b5be  call    ?ScLogImpersonateFailureEvent@@YAXJ@Z; ScLogImpersonateFailureEvent(long)
0x14000b5c3  jmp     loc_14000B4C9
0x14000b5c8  mov     rcx, gs:60h
0x14000b5d1  xor     edx, edx; Flags
0x14000b5d3  mov     r8, [rdi]; P
0x14000b5d6  mov     rcx, [rcx+30h]; HeapHandle
0x14000b5da  call    cs:__imp_RtlFreeHeap
0x14000b5e0  mov     [rdi], r12
0x14000b5e3  jmp     loc_14000B4B9
0x14000b5e8  mov     ebx, 8
0x14000b5ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b5f4  cmp     rcx, r13
0x14000b5f7  jz      loc_14000B4B9
0x14000b5fd  test    byte ptr [rcx+1Ch], 1
0x14000b601  jz      loc_14000B4B9
0x14000b607  mov     r9, [rsi+38h]
0x14000b60b  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14000b612  mov     rcx, [rcx+10h]
0x14000b616  mov     edx, 8Ah
0x14000b61b  call    WPP_SF_S
0x14000b620  jmp     loc_14000B4B9
0x14000b625  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b62c  cmp     rcx, r13
0x14000b62f  jz      short loc_14000B654
0x14000b631  test    byte ptr [rcx+1Ch], 1
0x14000b635  jz      short loc_14000B654
0x14000b637  mov     r9, [rsi+38h]
0x14000b63b  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14000b642  mov     rcx, [rcx+10h]
0x14000b646  mov     edx, 8Bh
0x14000b64b  mov     dword ptr [rsp+48h+var_28], edi
0x14000b64f  call    WPP_SF_Sd
0x14000b654  mov     r8d, edi
0x14000b657  lea     rdx, aRpcreverttosel; "RpcRevertToSelf"
0x14000b65e  mov     ecx, 5; unsigned int
0x14000b663  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x14000b668  jmp     loc_14000B4C9
```
