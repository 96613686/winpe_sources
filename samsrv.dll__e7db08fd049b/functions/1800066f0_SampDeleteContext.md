# SampDeleteContext

- ea: `0x1800066f0`
- end: `0x1800067ee`
- name: `SampDeleteContext`
- size: `254`
- prototype: `__int64 __fastcall(PVOID HandleId)`
- caller_count: `49`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180001760`
- `0x180005a80`
- `0x180006170`
- `0x180012d60`
- `0x180013ee0`
- `0x180015c50`
- `0x180015e90`
- `0x180028bec`
- `0x180034b6c`
- `0x1800362f0`
- `0x1800379a0`
- `0x1800510fc`
- `0x180053f9c`
- `0x180054644`
- `0x180054de0`
- `0x180056510`
- `0x180056c30`
- `0x1800573f0`
- `0x18005c2e0`
- `0x18005c4a0`
- `0x180062e58`
- `0x180063830`
- `0x180063f50`
- `0x180064380`
- `0x1800683fc`
- `0x180070b54`
- `0x180073d60`
- `0x1800799a8`
- `0x18008f330`
- `0x1800902b4`
- `0x1800908f0`
- `0x180091598`
- `0x180093454`
- `0x180095bbc`
- `0x180095e68`
- `0x18009642c`
- `0x180096d88`
- `0x1800977c8`
- `0x1800982a4`
- `0x1800985f0`
- `0x1800989d0`
- `0x18009acf8`
- `0x18009c6d4`
- `0x1800a1d78`
- `0x1800a21dc`
- `0x1800a22f4`
- `0x1800a6810`
- `0x1800aa648`
- `0x1800aad08`

## callees

- `0x1800066f0`
- `0x180008590`
- `0x180012a28`
- `0x18001cfa0`
- `0x18008ecd0`

## import_xrefs

- `ntdll!NtCloseObjectAuditAlarm` at `0x180006723`
- `ntdll!NtCloseObjectAuditAlarm` at `0x180006723`
- `ntdll!RtlLeaveCriticalSection` at `0x18000677f`
- `ntdll!RtlLeaveCriticalSection` at `0x18000677f`
- `ntdll!RtlEnterCriticalSection` at `0x18000674f`
- `ntdll!RtlEnterCriticalSection` at `0x18000674f`
- `RPCRT4!RpcRevertToSelf` at `0x180006732`
- `RPCRT4!RpcRevertToSelf` at `0x180006732`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x1800067d2`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x1800067d2`

## pseudocode

```c
__int64 __fastcall SampDeleteContext(PVOID **HandleId)
{
  int v1; // edi
  bool v2; // zf
  char v4; // al
  PVOID *v5; // rcx
  PVOID *v6; // rax
  int v8; // edi
  int v9; // [rsp+30h] [rbp+8h] BYREF

  *((_BYTE *)HandleId + 20) |= 0x10u;
  v1 = 0;
  v2 = (*((_BYTE *)HandleId + 20) & 0x20) == 0;
  v9 = 0;
  if ( v2 )
  {
    SampImpersonateClient(&v9);
    v1 = v9;
  }
  NtCloseObjectAuditAlarm(&SampSamSubsystem, HandleId, *((_BYTE *)HandleId + 208));
  if ( v1 == 2 )
  {
    RpcRevertToSelf();
  }
  else
  {
    v8 = v1 - 1;
    if ( v8 )
    {
      if ( v8 == 2 && (int)SampShouldCallNtdsaApiSet() >= 0 )
        NtdsaExtUnImpersonateAnyClient();
    }
    else
    {
      SamIRevertNullSession();
    }
  }
  *((_BYTE *)HandleId + 21) &= ~1u;
  v4 = *((_BYTE *)HandleId + 28);
  if ( ((v4 & 1) == 0 || ((_BYTE)HandleId[24] & 2) == 0) && v4 >= 0 )
  {
    RtlEnterCriticalSection(&SampContextListCritSect);
    v5 = *HandleId;
    if ( *HandleId )
    {
      v6 = HandleId[1];
      if ( v6 )
      {
        if ( v5[1] != HandleId || *v6 != HandleId )
          __fastfail(3u);
        *v6 = v5;
        v5[1] = v6;
      }
    }
    RtlLeaveCriticalSection(&SampContextListCritSect);
  }
  return SampDeReferenceContext((__int64)HandleId, 0);
}

```

## disassembly

```asm
0x1800066f0  mov     [rsp+arg_8], rbx
0x1800066f5  push    rdi
0x1800066f6  sub     rsp, 20h
0x1800066fa  or      byte ptr [rcx+14h], 10h
0x1800066fe  xor     edi, edi
0x180006700  test    byte ptr [rcx+14h], 20h
0x180006704  mov     rbx, rcx
0x180006707  mov     [rsp+28h+arg_0], edi
0x18000670b  jz      loc_1800067A4
0x180006711  movzx   r8d, byte ptr [rbx+0D0h]; GenerateOnClose
0x180006719  lea     rcx, ?SampSamSubsystem@@3U_UNICODE_STRING@@A; SubsystemName
0x180006720  mov     rdx, rbx; HandleId
0x180006723  call    cs:__imp_NtCloseObjectAuditAlarm
0x180006729  cmp     edi, 2
0x18000672c  jnz     loc_1800067B7
0x180006732  call    cs:__imp_RpcRevertToSelf
0x180006738  and     byte ptr [rbx+15h], 0FEh
0x18000673c  movzx   eax, byte ptr [rbx+1Ch]
0x180006740  test    al, 1
0x180006742  jnz     short loc_180006799
0x180006744  test    al, al
0x180006746  js      short loc_180006785
0x180006748  lea     rcx, ?SampContextListCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000674f  call    cs:__imp_RtlEnterCriticalSection
0x180006755  mov     rcx, [rbx]
0x180006758  test    rcx, rcx
0x18000675b  jz      short loc_180006778
0x18000675d  mov     rax, [rbx+8]
0x180006761  test    rax, rax
0x180006764  jz      short loc_180006778
0x180006766  cmp     [rcx+8], rbx
0x18000676a  jnz     short loc_1800067E7
0x18000676c  cmp     [rax], rbx
0x18000676f  jnz     short loc_1800067E7
0x180006771  mov     [rax], rcx
0x180006774  mov     [rcx+8], rax
0x180006778  lea     rcx, ?SampContextListCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000677f  call    cs:__imp_RtlLeaveCriticalSection
0x180006785  xor     edx, edx
0x180006787  mov     rcx, rbx
0x18000678a  mov     rbx, [rsp+28h+arg_8]
0x18000678f  add     rsp, 20h
0x180006793  pop     rdi
0x180006794  jmp     SampDeReferenceContext
0x180006799  test    byte ptr [rbx+0C0h], 2
0x1800067a0  jz      short loc_180006744
0x1800067a2  jmp     short loc_180006785
0x1800067a4  lea     rcx, [rsp+28h+arg_0]
0x1800067a9  call    SampImpersonateClient
0x1800067ae  mov     edi, [rsp+28h+arg_0]
0x1800067b2  jmp     loc_180006711
0x1800067b7  sub     edi, 1
0x1800067ba  jz      short loc_1800067DD
0x1800067bc  cmp     edi, 2
0x1800067bf  jnz     loc_180006738
0x1800067c5  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x1800067ca  test    eax, eax
0x1800067cc  js      loc_180006738
0x1800067d2  call    cs:__imp_NtdsaExtUnImpersonateAnyClient
0x1800067d8  jmp     loc_180006738
0x1800067dd  call    SamIRevertNullSession
0x1800067e2  jmp     loc_180006738
0x1800067e7  mov     ecx, 3
0x1800067ec  int     29h; Win8: RtlFailFast(ecx)
```
