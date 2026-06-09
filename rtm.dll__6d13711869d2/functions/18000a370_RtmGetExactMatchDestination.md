# RtmGetExactMatchDestination

- ea: `0x18000a370`
- end: `0x18000a43c`
- name: `RtmGetExactMatchDestination`
- size: `204`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, PRTM_NET_ADDRESS DestAddress, ULONG ProtocolId, RTM_VIEW_SET TargetViews, PRTM_DEST_INFO DestInfo)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002560`
- `0x180006e38`
- `0x18000a370`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000a420`
- `ntdll!RtlReleaseResource` at `0x18000a420`
- `ntdll!RtlAcquireResourceShared` at `0x18000a3b9`
- `ntdll!RtlAcquireResourceShared` at `0x18000a3b9`

## pseudocode

```c
DWORD __stdcall RtmGetExactMatchDestination(
        RTM_ENTITY_HANDLE RtmRegHandle,
        PRTM_NET_ADDRESS DestAddress,
        ULONG ProtocolId,
        RTM_VIEW_SET TargetViews,
        PRTM_DEST_INFO DestInfo)
{
  unsigned int v5; // edi
  __int64 v9; // rbx
  struct _RTL_RESOURCE *v10; // rbp
  DWORD v11; // ebx
  __int64 v12; // rdx
  __int64 v14; // [rsp+70h] [rbp+8h] BYREF

  v14 = 0;
  v5 = (unsigned int)RtmRegHandle ^ 0x7754DF32;
  if ( (unsigned __int64)RtmRegHandle == 0x7754DF32
    || *(_DWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x30) == 1 )
  {
    return 6;
  }
  v9 = *(_QWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x10);
  v10 = (struct _RTL_RESOURCE *)(v9 + 608);
  RtlAcquireResourceShared((PRTL_RESOURCE)(v9 + 608), 1u);
  v11 = SearchInTable(*(_QWORD *)(v9 + 712), DestAddress->NumBits, (int)DestAddress + 4, 0, (__int64)&v14);
  if ( !v11 )
  {
    v12 = v14 - 16;
    if ( !TargetViews || (TargetViews & *(_DWORD *)(v12 + 112)) != 0 )
    {
      GetDestInfo(v5, v12, ProtocolId, TargetViews, (__int64)DestInfo);
      v11 = 0;
    }
    else
    {
      v11 = 1168;
    }
  }
  RtlReleaseResource(v10);
  return v11;
}

```

## disassembly

```asm
0x18000a370  push    rbx
0x18000a372  push    rbp
0x18000a373  push    rsi
0x18000a374  push    rdi
0x18000a375  push    r14
0x18000a377  push    r15
0x18000a379  sub     rsp, 38h
0x18000a37d  mov     rdi, rcx
0x18000a380  mov     [rsp+68h+arg_0], 0
0x18000a389  xor     rdi, 7754DF32h
0x18000a390  mov     esi, r9d
0x18000a393  mov     r15d, r8d
0x18000a396  mov     r14, rdx
0x18000a399  jz      loc_18000A42A
0x18000a39f  cmp     dword ptr [rdi+30h], 1
0x18000a3a3  jz      loc_18000A42A
0x18000a3a9  mov     rbx, [rdi+10h]
0x18000a3ad  mov     dl, 1; Wait
0x18000a3af  lea     rbp, [rbx+260h]
0x18000a3b6  mov     rcx, rbp; Resource
0x18000a3b9  call    cs:__imp_RtlAcquireResourceShared
0x18000a3bf  movzx   edx, word ptr [r14+2]
0x18000a3c4  lea     rax, [rsp+68h+arg_0]
0x18000a3c9  mov     rcx, [rbx+2C8h]
0x18000a3d0  lea     r8, [r14+4]
0x18000a3d4  xor     r9d, r9d
0x18000a3d7  mov     [rsp+68h+var_48], rax
0x18000a3dc  call    SearchInTable
0x18000a3e1  mov     ebx, eax
0x18000a3e3  test    eax, eax
0x18000a3e5  jnz     short loc_18000A41D
0x18000a3e7  mov     rdx, [rsp+68h+arg_0]
0x18000a3ec  add     rdx, 0FFFFFFFFFFFFFFF0h
0x18000a3f0  test    esi, esi
0x18000a3f2  jz      short loc_18000A400
0x18000a3f4  test    [rdx+70h], esi
0x18000a3f7  jnz     short loc_18000A400
0x18000a3f9  mov     ebx, 490h
0x18000a3fe  jmp     short loc_18000A41D
0x18000a400  mov     rax, [rsp+68h+DestInfo]
0x18000a408  mov     r9d, esi
0x18000a40b  mov     r8d, r15d
0x18000a40e  mov     [rsp+68h+var_48], rax
0x18000a413  mov     rcx, rdi
0x18000a416  call    GetDestInfo
0x18000a41b  xor     ebx, ebx
0x18000a41d  mov     rcx, rbp; Resource
0x18000a420  call    cs:__imp_RtlReleaseResource
0x18000a426  mov     eax, ebx
0x18000a428  jmp     short loc_18000A42F
0x18000a42a  mov     eax, 6
0x18000a42f  add     rsp, 38h
0x18000a433  pop     r15
0x18000a435  pop     r14
0x18000a437  pop     rdi
0x18000a438  pop     rsi
0x18000a439  pop     rbp
0x18000a43a  pop     rbx
0x18000a43b  retn
```
