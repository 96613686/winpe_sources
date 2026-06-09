# TpmSWAntiHammeringMgr::LoadConfiguration(void)

- ea: `0x140005728`
- end: `0x140005839`
- name: `?LoadConfiguration@TpmSWAntiHammeringMgr@@AEAAXXZ`
- size: `273`
- prototype: `void __fastcall(TpmSWAntiHammeringMgr *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140005698`

## callees

- `0x140005728`
- `0x140009fc8`

## pseudocode

```c
void __fastcall TpmSWAntiHammeringMgr::LoadConfiguration(TpmSWAntiHammeringMgr *this)
{
  int v2; // eax
  unsigned int v3; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 12) )
    return;
  v3 = 0;
  if ( (int)TpmRegistry::QueryValue(7, L"StandardUserAuthorizationFailureIndividualThreshold", 4, (__int64)&v3, 4u, 0) >= 0 )
  {
    if ( v3 > 0x64 )
    {
      *(_DWORD *)this = 100;
      goto LABEL_8;
    }
    if ( v3 )
    {
      *(_DWORD *)this = v3;
      goto LABEL_8;
    }
  }
  *(_DWORD *)this = 4;
LABEL_8:
  v3 = 0;
  if ( (int)TpmRegistry::QueryValue(7, L"StandardUserAuthorizationFailureTotalThreshold", 4, (__int64)&v3, 4u, 0) < 0 )
    goto LABEL_13;
  if ( v3 - 1 > 0x63 )
  {
    if ( v3 > 0x64 )
    {
      *((_DWORD *)this + 1) = 100;
      goto LABEL_14;
    }
LABEL_13:
    *((_DWORD *)this + 1) = 9;
    goto LABEL_14;
  }
  *((_DWORD *)this + 1) = v3;
LABEL_14:
  v3 = 0;
  if ( (int)TpmRegistry::QueryValue(7, L"StandardUserAuthorizationFailureDuration", 4, (__int64)&v3, 4u, 0) < 0 )
    v2 = 28800;
  else
    v2 = 60 * v3;
  *((_DWORD *)this + 2) = v2;
  *((_DWORD *)this + 12) = 1;
}

```

## disassembly

```asm
0x140005728  mov     rax, rsp
0x14000572b  mov     [rax+10h], rbx
0x14000572f  push    rbp
0x140005730  sub     rsp, 30h
0x140005734  cmp     dword ptr [rcx+30h], 0
0x140005738  mov     rbx, rcx
0x14000573b  jnz     loc_14000582D
0x140005741  mov     ebp, 4
0x140005746  mov     qword ptr [rax-10h], 0
0x14000574e  lea     r9, [rax+8]
0x140005752  mov     dword ptr [rax+8], 0
0x140005759  mov     r8d, ebp
0x14000575c  mov     [rax-18h], ebp
0x14000575f  lea     rdx, aStandarduserau_1; "StandardUserAuthorizationFailureIndivid"...
0x140005766  lea     ecx, [rbp+3]
0x140005769  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x14000576e  test    eax, eax
0x140005770  js      short loc_14000578B
0x140005772  mov     eax, [rsp+38h+arg_0]
0x140005776  cmp     eax, 64h ; 'd'
0x140005779  ja      short loc_140005783
0x14000577b  test    eax, eax
0x14000577d  jz      short loc_14000578B
0x14000577f  mov     [rbx], eax
0x140005781  jmp     short loc_14000578D
0x140005783  mov     dword ptr [rbx], 64h ; 'd'
0x140005789  jmp     short loc_14000578D
0x14000578b  mov     [rbx], ebp
0x14000578d  mov     [rsp+38h+var_10], 0
0x140005796  lea     r9, [rsp+38h+arg_0]
0x14000579b  mov     r8d, ebp
0x14000579e  mov     [rsp+38h+var_18], ebp
0x1400057a2  lea     rdx, aStandarduserau_0; "StandardUserAuthorizationFailureTotalTh"...
0x1400057a9  mov     [rsp+38h+arg_0], 0
0x1400057b1  mov     ecx, 7
0x1400057b6  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x1400057bb  test    eax, eax
0x1400057bd  js      short loc_1400057DE
0x1400057bf  mov     ecx, [rsp+38h+arg_0]
0x1400057c3  lea     eax, [rcx-1]
0x1400057c6  cmp     eax, 63h ; 'c'
0x1400057c9  ja      short loc_1400057D0
0x1400057cb  mov     [rbx+4], ecx
0x1400057ce  jmp     short loc_1400057E5
0x1400057d0  cmp     ecx, 64h ; 'd'
0x1400057d3  jbe     short loc_1400057DE
0x1400057d5  mov     dword ptr [rbx+4], 64h ; 'd'
0x1400057dc  jmp     short loc_1400057E5
0x1400057de  mov     dword ptr [rbx+4], 9
0x1400057e5  mov     [rsp+38h+var_10], 0
0x1400057ee  lea     r9, [rsp+38h+arg_0]
0x1400057f3  mov     r8d, ebp
0x1400057f6  mov     [rsp+38h+var_18], ebp
0x1400057fa  lea     rdx, aStandarduserau; "StandardUserAuthorizationFailureDuratio"...
0x140005801  mov     [rsp+38h+arg_0], 0
0x140005809  mov     ecx, 7
0x14000580e  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x140005813  test    eax, eax
0x140005815  js      short loc_14000581E
0x140005817  imul    eax, [rsp+38h+arg_0], 3Ch ; '<'
0x14000581c  jmp     short loc_140005823
0x14000581e  mov     eax, 7080h
0x140005823  mov     [rbx+8], eax
0x140005826  mov     dword ptr [rbx+30h], 1
0x14000582d  mov     rbx, [rsp+38h+arg_8]
0x140005832  add     rsp, 30h
0x140005836  pop     rbp
0x140005837  retn
```
