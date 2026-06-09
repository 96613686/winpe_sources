# RtmGetLessSpecificDestination

- ea: `0x18000a5b0`
- end: `0x18000a664`
- name: `RtmGetLessSpecificDestination`
- size: `180`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, RTM_DEST_HANDLE DestHandle, ULONG ProtocolId, RTM_VIEW_SET TargetViews, PRTM_DEST_INFO DestInfo)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015f54`

## callees

- `0x180006e38`
- `0x18000a5b0`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000a64a`
- `ntdll!RtlReleaseResource` at `0x18000a64a`
- `ntdll!RtlAcquireResourceShared` at `0x18000a5f8`
- `ntdll!RtlAcquireResourceShared` at `0x18000a5f8`

## pseudocode

```c
DWORD __stdcall RtmGetLessSpecificDestination(
        RTM_ENTITY_HANDLE RtmRegHandle,
        RTM_DEST_HANDLE DestHandle,
        ULONG ProtocolId,
        RTM_VIEW_SET TargetViews,
        PRTM_DEST_INFO DestInfo)
{
  unsigned int v5; // edi
  unsigned __int64 v8; // rdx
  __int64 v9; // rbp
  __int64 **v10; // rbx
  __int64 v11; // rbx
  __int64 **v12; // rdx
  DWORD v13; // ebx

  v5 = (unsigned int)RtmRegHandle ^ 0x7754DF32;
  if ( (unsigned __int64)RtmRegHandle == 0x7754DF32 )
    return 6;
  if ( *(_DWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x30) == 1 )
    return 6;
  v8 = (unsigned __int64)DestHandle ^ 0x7754DF32;
  if ( !v8 || *(_WORD *)(v8 + 108) == 1 )
    return 6;
  v9 = *(_QWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x10);
  v10 = (__int64 **)(v8 + 16);
  RtlAcquireResourceShared((PRTL_RESOURCE)(v9 + 608), 1u);
  while ( 1 )
  {
    v11 = **v10;
    if ( !v11 )
      break;
    v10 = *(__int64 ***)(v11 + 24);
    if ( !v10 )
      break;
    v12 = v10 - 2;
    if ( !TargetViews || (TargetViews & (_DWORD)v12[14]) != 0 )
    {
      GetDestInfo(v5, (_DWORD)v12, ProtocolId, TargetViews, (__int64)DestInfo);
      v13 = 0;
      goto LABEL_12;
    }
  }
  v13 = 1168;
LABEL_12:
  RtlReleaseResource((PRTL_RESOURCE)(v9 + 608));
  return v13;
}

```

## disassembly

```asm
0x18000a5b0  push    rbx
0x18000a5b2  push    rbp
0x18000a5b3  push    rsi
0x18000a5b4  push    rdi
0x18000a5b5  push    r14
0x18000a5b7  sub     rsp, 30h
0x18000a5bb  mov     rdi, rcx
0x18000a5be  mov     eax, 7754DF32h
0x18000a5c3  xor     rdi, rax
0x18000a5c6  mov     esi, r9d
0x18000a5c9  mov     r14d, r8d
0x18000a5cc  jz      loc_18000A654
0x18000a5d2  mov     ecx, 1
0x18000a5d7  cmp     [rdi+30h], ecx
0x18000a5da  jz      short loc_18000A654
0x18000a5dc  xor     rdx, rax
0x18000a5df  jz      short loc_18000A654
0x18000a5e1  cmp     [rdx+6Ch], cx
0x18000a5e5  jz      short loc_18000A654
0x18000a5e7  mov     rbp, [rdi+10h]
0x18000a5eb  lea     rbx, [rdx+10h]
0x18000a5ef  mov     dl, cl; Wait
0x18000a5f1  lea     rcx, [rbp+260h]; Resource
0x18000a5f8  call    cs:__imp_RtlAcquireResourceShared
0x18000a5fe  mov     rax, [rbx]
0x18000a601  mov     rbx, [rax]
0x18000a604  test    rbx, rbx
0x18000a607  jz      short loc_18000A63E
0x18000a609  mov     rbx, [rbx+18h]
0x18000a60d  test    rbx, rbx
0x18000a610  jz      short loc_18000A63E
0x18000a612  lea     rdx, [rbx-10h]
0x18000a616  test    esi, esi
0x18000a618  jz      short loc_18000A61F
0x18000a61a  test    [rdx+70h], esi
0x18000a61d  jz      short loc_18000A5FE
0x18000a61f  mov     rax, [rsp+58h+DestInfo]
0x18000a627  mov     r9d, esi
0x18000a62a  mov     r8d, r14d
0x18000a62d  mov     [rsp+58h+var_38], rax
0x18000a632  mov     rcx, rdi
0x18000a635  call    GetDestInfo
0x18000a63a  xor     ebx, ebx
0x18000a63c  jmp     short loc_18000A643
0x18000a63e  mov     ebx, 490h
0x18000a643  lea     rcx, [rbp+260h]; Resource
0x18000a64a  call    cs:__imp_RtlReleaseResource
0x18000a650  mov     eax, ebx
0x18000a652  jmp     short loc_18000A659
0x18000a654  mov     eax, 6
0x18000a659  add     rsp, 30h
0x18000a65d  pop     r14
0x18000a65f  pop     rdi
0x18000a660  pop     rsi
0x18000a661  pop     rbp
0x18000a662  pop     rbx
0x18000a663  retn
```
