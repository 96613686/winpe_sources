# RtmGetDestInfo

- ea: `0x180007050`
- end: `0x1800070c0`
- name: `RtmGetDestInfo`
- size: `112`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, RTM_DEST_HANDLE DestHandle, ULONG ProtocolId, RTM_VIEW_SET TargetViews, PRTM_DEST_INFO DestInfo)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006e38`
- `0x180007050`
- `0x180014bfc`
- `0x180015100`

## pseudocode

```c
DWORD __stdcall RtmGetDestInfo(
        RTM_ENTITY_HANDLE RtmRegHandle,
        RTM_DEST_HANDLE DestHandle,
        ULONG ProtocolId,
        RTM_VIEW_SET TargetViews,
        PRTM_DEST_INFO DestInfo)
{
  unsigned int v5; // esi
  unsigned __int64 v8; // rdi

  v5 = (unsigned int)RtmRegHandle ^ 0x7754DF32;
  if ( (unsigned __int64)RtmRegHandle == 0x7754DF32 )
    return 6;
  if ( *(_DWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x30) == 1 )
    return 6;
  v8 = (unsigned __int64)DestHandle ^ 0x7754DF32;
  if ( (unsigned __int64)DestHandle == 0x7754DF32 )
    return 6;
  AcquireReadLock((_QWORD *)(v8 + 32));
  GetDestInfo(v5, v8, ProtocolId, TargetViews, (__int64)DestInfo);
  ReleaseReadLock(v8 + 32);
  return 0;
}

```

## disassembly

```asm
0x180007050  push    rbx
0x180007052  push    rbp
0x180007053  push    rsi
0x180007054  push    rdi
0x180007055  push    r14
0x180007057  sub     rsp, 30h
0x18000705b  mov     rsi, rcx
0x18000705e  mov     eax, 7754DF32h
0x180007063  xor     rsi, rax
0x180007066  mov     ebp, r9d
0x180007069  mov     r14d, r8d
0x18000706c  mov     rdi, rdx
0x18000706f  jz      short loc_1800070B0
0x180007071  cmp     dword ptr [rsi+30h], 1
0x180007075  jz      short loc_1800070B0
0x180007077  xor     rdi, rax
0x18000707a  jz      short loc_1800070B0
0x18000707c  lea     rcx, [rdi+20h]
0x180007080  call    AcquireReadLock
0x180007085  mov     rax, [rsp+58h+DestInfo]
0x18000708d  mov     r9d, ebp
0x180007090  mov     r8d, r14d
0x180007093  mov     [rsp+58h+var_38], rax
0x180007098  mov     rdx, rdi
0x18000709b  mov     rcx, rsi
0x18000709e  call    GetDestInfo
0x1800070a3  lea     rcx, [rdi+20h]
0x1800070a7  call    ReleaseReadLock
0x1800070ac  xor     eax, eax
0x1800070ae  jmp     short loc_1800070B5
0x1800070b0  mov     eax, 6
0x1800070b5  add     rsp, 30h
0x1800070b9  pop     r14
0x1800070bb  pop     rdi
0x1800070bc  pop     rsi
0x1800070bd  pop     rbp
0x1800070be  pop     rbx
0x1800070bf  retn
```
