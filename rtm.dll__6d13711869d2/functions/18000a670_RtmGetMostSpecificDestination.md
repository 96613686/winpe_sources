# RtmGetMostSpecificDestination

- ea: `0x18000a670`
- end: `0x18000a75f`
- name: `RtmGetMostSpecificDestination`
- size: `239`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, PRTM_NET_ADDRESS DestAddress, ULONG ProtocolId, RTM_VIEW_SET TargetViews, PRTM_DEST_INFO DestInfo)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016d00`
- `0x180017a44`
- `0x18001958c`
- `0x18001decc`

## callees

- `0x180002560`
- `0x180006e38`
- `0x18000a670`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000a739`
- `ntdll!RtlReleaseResource` at `0x18000a739`
- `ntdll!RtlAcquireResourceShared` at `0x18000a6c7`
- `ntdll!RtlAcquireResourceShared` at `0x18000a6c7`

## pseudocode

```c
DWORD __stdcall RtmGetMostSpecificDestination(
        RTM_ENTITY_HANDLE RtmRegHandle,
        PRTM_NET_ADDRESS DestAddress,
        ULONG ProtocolId,
        RTM_VIEW_SET TargetViews,
        PRTM_DEST_INFO DestInfo)
{
  unsigned int v5; // edi
  __int64 v9; // rbx
  DWORD v10; // ebp
  __int64 **i; // rax
  __int64 **v12; // rdx
  __int64 v13; // rax
  __int64 **v15; // [rsp+60h] [rbp+8h] BYREF

  v15 = 0;
  v5 = (unsigned int)RtmRegHandle ^ 0x7754DF32;
  if ( (unsigned __int64)RtmRegHandle == 0x7754DF32
    || *(_DWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x30) == 1 )
  {
    return 6;
  }
  v9 = *(_QWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x10);
  v10 = 1168;
  RtlAcquireResourceShared((PRTL_RESOURCE)(v9 + 608), 1u);
  SearchInTable(*(_QWORD *)(v9 + 712), DestAddress->NumBits, (_DWORD)DestAddress + 4, 0, (__int64)&v15);
  for ( i = v15; i; i = *(__int64 ***)(v13 + 24) )
  {
    v12 = i - 2;
    if ( !TargetViews || (TargetViews & (_DWORD)v12[14]) != 0 )
    {
      GetDestInfo(v5, (_DWORD)v12, ProtocolId, TargetViews, (__int64)DestInfo);
      v10 = 0;
      break;
    }
    v13 = **i;
    if ( !v13 )
      break;
  }
  RtlReleaseResource((PRTL_RESOURCE)(v9 + 608));
  return v10;
}

```

## disassembly

```asm
0x18000a670  mov     [rsp+arg_8], rbx
0x18000a675  mov     [rsp+arg_10], rbp
0x18000a67a  push    rsi
0x18000a67b  push    rdi
0x18000a67c  push    r12
0x18000a67e  push    r14
0x18000a680  push    r15
0x18000a682  sub     rsp, 30h
0x18000a686  mov     rdi, rcx
0x18000a689  mov     [rsp+58h+arg_0], 0
0x18000a692  xor     rdi, 7754DF32h
0x18000a699  mov     esi, r9d
0x18000a69c  mov     r12d, r8d
0x18000a69f  mov     r15, rdx
0x18000a6a2  jz      loc_18000A743
0x18000a6a8  cmp     dword ptr [rdi+30h], 1
0x18000a6ac  jz      loc_18000A743
0x18000a6b2  mov     rbx, [rdi+10h]
0x18000a6b6  mov     dl, 1; Wait
0x18000a6b8  mov     ebp, 490h
0x18000a6bd  lea     r14, [rbx+260h]
0x18000a6c4  mov     rcx, r14; Resource
0x18000a6c7  call    cs:__imp_RtlAcquireResourceShared
0x18000a6cd  movzx   edx, word ptr [r15+2]
0x18000a6d2  lea     rax, [rsp+58h+arg_0]
0x18000a6d7  mov     rcx, [rbx+2C8h]
0x18000a6de  lea     r8, [r15+4]
0x18000a6e2  xor     r9d, r9d
0x18000a6e5  mov     [rsp+58h+var_38], rax
0x18000a6ea  call    SearchInTable
0x18000a6ef  mov     rax, [rsp+58h+arg_0]
0x18000a6f4  jmp     short loc_18000A712
0x18000a6f6  lea     rdx, [rax-10h]
0x18000a6fa  test    esi, esi
0x18000a6fc  jz      short loc_18000A719
0x18000a6fe  test    [rdx+70h], esi
0x18000a701  jnz     short loc_18000A719
0x18000a703  mov     rax, [rax]
0x18000a706  mov     rax, [rax]
0x18000a709  test    rax, rax
0x18000a70c  jz      short loc_18000A736
0x18000a70e  mov     rax, [rax+18h]
0x18000a712  test    rax, rax
0x18000a715  jnz     short loc_18000A6F6
0x18000a717  jmp     short loc_18000A736
0x18000a719  mov     rax, [rsp+58h+DestInfo]
0x18000a721  mov     r9d, esi
0x18000a724  mov     r8d, r12d
0x18000a727  mov     [rsp+58h+var_38], rax
0x18000a72c  mov     rcx, rdi
0x18000a72f  call    GetDestInfo
0x18000a734  xor     ebp, ebp
0x18000a736  mov     rcx, r14; Resource
0x18000a739  call    cs:__imp_RtlReleaseResource
0x18000a73f  mov     eax, ebp
0x18000a741  jmp     short loc_18000A748
0x18000a743  mov     eax, 6
0x18000a748  mov     rbx, [rsp+58h+arg_8]
0x18000a74d  mov     rbp, [rsp+58h+arg_10]
0x18000a752  add     rsp, 30h
0x18000a756  pop     r15
0x18000a758  pop     r14
0x18000a75a  pop     r12
0x18000a75c  pop     rdi
0x18000a75d  pop     rsi
0x18000a75e  retn
```
