# ScGetServiceRegistryStateKey(CServiceRecord *,_SC_INTERNAL_REGISTRY_STATE_TYPE,ulong,void * *)

- ea: `0x1400414b8`
- end: `0x140041651`
- name: `?ScGetServiceRegistryStateKey@@YAKPEAVCServiceRecord@@W4_SC_INTERNAL_REGISTRY_STATE_TYPE@@KPEAPEAX@Z`
- size: `409`
- prototype: `unsigned int __high(struct CServiceRecord *, enum _SC_INTERNAL_REGISTRY_STATE_TYPE, unsigned int, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x1400275f0`
- `0x14007dd20`

## callees

- `0x140019014`
- `0x140029228`
- `0x1400414b8`
- `0x14004401c`
- `0x140077784`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1400415a9`
- `RPCRT4!RpcImpersonateClient` at `0x1400415a9`
- `RPCRT4!RpcRevertToSelf` at `0x140041620`
- `RPCRT4!RpcRevertToSelf` at `0x140041620`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400415d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400415d5`
- `ntdll!RtlFreeHeap` at `0x140041646`
- `ntdll!RtlFreeHeap` at `0x140041646`

## pseudocode

```c
__int64 __fastcall ScGetServiceRegistryStateKey(__int64 a1, __int64 a2, REGSAM a3, HKEY *a4)
{
  char v5; // r14
  REGSAM v7; // edi
  int v8; // eax
  unsigned int RegistryStatePath; // ebx
  RPC_STATUS v11; // eax
  LPCWSTR lpSubKey[7]; // [rsp+30h] [rbp-38h] BYREF

  lpSubKey[0] = 0;
  v5 = a2;
  v7 = a3;
  v8 = -2147352551;
  if ( (_DWORD)a2 )
    v8 = -1073610721;
  if ( (a3 & 0x2000000) != 0 )
    v7 = v8 | a3 & 0xFDFFFFFF;
  if ( (~v8 & v7) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->StubInfo, 299, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
    return 5;
  }
  if ( *(char *)(a1 + 80) < 0 || (*(_DWORD *)(a1 + 52) & 0x100000) != 0 )
    return 5;
  RegistryStatePath = CServiceRecord::GetRegistryStatePath(a1, a2, lpSubKey);
  if ( RegistryStatePath )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_SLd(
        WPP_GLOBAL_Control->StubInfo,
        300,
        (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
        *(_QWORD *)(a1 + 56),
        v5,
        RegistryStatePath);
  }
  else
  {
    v11 = RpcImpersonateClient(0);
    RegistryStatePath = v11;
    if ( v11 )
    {
      ScLogImpersonateFailureEvent(v11);
    }
    else
    {
      RegistryStatePath = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, v7, a4);
      if ( RegistryStatePath )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_SLd(
            WPP_GLOBAL_Control->StubInfo,
            301,
            (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
            *(_QWORD *)(a1 + 56),
            v5,
            RegistryStatePath);
        }
      }
      else
      {
        RegistryStatePath = 0;
      }
      RpcRevertToSelf();
    }
  }
  if ( lpSubKey[0] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)lpSubKey[0]);
  return RegistryStatePath;
}

```

## disassembly

```asm
0x1400414b8  push    rbx
0x1400414ba  push    rsi
0x1400414bb  push    rdi
0x1400414bc  push    r14
0x1400414be  push    r15
0x1400414c0  sub     rsp, 40h
0x1400414c4  mov     [rsp+68h+lpSubKey], 0
0x1400414cd  mov     r15, r9
0x1400414d0  mov     r14d, edx
0x1400414d3  mov     rsi, rcx
0x1400414d6  mov     edi, r8d
0x1400414d9  mov     eax, 80020019h
0x1400414de  test    edx, edx
0x1400414e0  jz      short loc_1400414E7
0x1400414e2  mov     eax, 0C002001Fh
0x1400414e7  bt      r8d, 19h
0x1400414ec  jnb     short loc_1400414F4
0x1400414ee  btr     edi, 19h
0x1400414f2  or      edi, eax
0x1400414f4  not     eax
0x1400414f6  test    edi, eax
0x1400414f8  jz      short loc_140041543
0x1400414fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140041501  lea     rax, WPP_GLOBAL_Control
0x140041508  cmp     rcx, rax
0x14004150b  jz      short loc_140041530
0x14004150d  test    byte ptr [rcx+1Ch], 1
0x140041511  jz      short loc_140041530
0x140041513  mov     rcx, [rcx+10h]
0x140041517  mov     r9d, r8d
0x14004151a  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140041521  mov     dword ptr [rsp+68h+phkResult], r14d
0x140041526  mov     edx, 12Bh
0x14004152b  call    WPP_SF_Dd
0x140041530  mov     ebx, 5
0x140041535  mov     eax, ebx
0x140041537  add     rsp, 40h
0x14004153b  pop     r15
0x14004153d  pop     r14
0x14004153f  pop     rdi
0x140041540  pop     rsi
0x140041541  pop     rbx
0x140041542  retn
0x140041543  test    byte ptr [rcx+50h], 80h
0x140041547  jnz     short loc_140041530
0x140041549  mov     eax, [rcx+34h]
0x14004154c  bt      eax, 14h
0x140041550  jb      short loc_140041530
0x140041552  lea     r8, [rsp+68h+lpSubKey]
0x140041557  call    ?GetRegistryStatePath@CServiceRecord@@QEAAKW4_SC_INTERNAL_REGISTRY_STATE_TYPE@@PEAPEAG@Z; CServiceRecord::GetRegistryStatePath(_SC_INTERNAL_REGISTRY_STATE_TYPE,ushort * *)
0x14004155c  mov     ebx, eax
0x14004155e  test    eax, eax
0x140041560  jz      short loc_1400415A7
0x140041562  mov     rcx, cs:WPP_GLOBAL_Control
0x140041569  lea     rax, WPP_GLOBAL_Control
0x140041570  cmp     rcx, rax
0x140041573  jz      loc_140041626
0x140041579  test    byte ptr [rcx+1Ch], 1
0x14004157d  jz      loc_140041626
0x140041583  mov     r9, [rsi+38h]
0x140041587  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14004158e  mov     rcx, [rcx+10h]
0x140041592  mov     edx, 12Ch
0x140041597  mov     [rsp+68h+var_40], ebx
0x14004159b  mov     dword ptr [rsp+68h+phkResult], r14d
0x1400415a0  call    WPP_SF_SLd
0x1400415a5  jmp     short loc_140041626
0x1400415a7  xor     ecx, ecx; BindingHandle
0x1400415a9  call    cs:__imp_RpcImpersonateClient
0x1400415af  mov     ebx, eax
0x1400415b1  test    eax, eax
0x1400415b3  jz      short loc_1400415BE
0x1400415b5  mov     ecx, eax; int
0x1400415b7  call    ?ScLogImpersonateFailureEvent@@YAXJ@Z; ScLogImpersonateFailureEvent(long)
0x1400415bc  jmp     short loc_140041626
0x1400415be  mov     rdx, [rsp+68h+lpSubKey]; lpSubKey
0x1400415c3  mov     r9d, edi; samDesired
0x1400415c6  xor     r8d, r8d; ulOptions
0x1400415c9  mov     [rsp+68h+phkResult], r15; phkResult
0x1400415ce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400415d5  call    cs:__imp_RegOpenKeyExW
0x1400415db  mov     ebx, eax
0x1400415dd  test    eax, eax
0x1400415df  jz      short loc_14004161E
0x1400415e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400415e8  lea     rax, WPP_GLOBAL_Control
0x1400415ef  cmp     rcx, rax
0x1400415f2  jz      short loc_140041620
0x1400415f4  test    byte ptr [rcx+1Ch], 1
0x1400415f8  jz      short loc_140041620
0x1400415fa  mov     r9, [rsi+38h]
0x1400415fe  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140041605  mov     rcx, [rcx+10h]
0x140041609  mov     edx, 12Dh
0x14004160e  mov     [rsp+68h+var_40], ebx
0x140041612  mov     dword ptr [rsp+68h+phkResult], r14d
0x140041617  call    WPP_SF_SLd
0x14004161c  jmp     short loc_140041620
0x14004161e  xor     ebx, ebx
0x140041620  call    cs:__imp_RpcRevertToSelf
0x140041626  cmp     [rsp+68h+lpSubKey], 0
0x14004162c  jz      loc_140041535
0x140041632  mov     rcx, gs:60h
0x14004163b  xor     edx, edx; Flags
0x14004163d  mov     r8, [rsp+68h+lpSubKey]; P
0x140041642  mov     rcx, [rcx+30h]; HeapHandle
0x140041646  call    cs:__imp_RtlFreeHeap
0x14004164c  jmp     loc_140041535
```
