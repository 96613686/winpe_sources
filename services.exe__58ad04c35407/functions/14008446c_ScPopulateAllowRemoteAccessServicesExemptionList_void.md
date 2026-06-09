# ScPopulateAllowRemoteAccessServicesExemptionList(void)

- ea: `0x14008446c`
- end: `0x1400846c9`
- name: `?ScPopulateAllowRemoteAccessServicesExemptionList@@YAXXZ`
- size: `605`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400137d0`

## callees

- `0x140004c58`
- `0x14000c310`
- `0x14001c1e0`
- `0x14001f99c`
- `0x14002193c`
- `0x14008446c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400844c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400844c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14008467c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14008467c`
- `ntdll!RtlFreeHeap` at `0x140084699`
- `ntdll!RtlFreeHeap` at `0x1400846b6`
- `ntdll!RtlFreeHeap` at `0x140084699`
- `ntdll!RtlFreeHeap` at `0x1400846b6`
- `ntdll!RtlAllocateHeap` at `0x1400845f1`
- `ntdll!RtlAllocateHeap` at `0x1400845f1`

## string_xrefs

- `0x1400844e5`: `RemoteAccessCheckExemptionList`

## pseudocode

```c
void ScPopulateAllowRemoteAccessServicesExemptionList(void)
{
  unsigned __int16 *v0; // rbx
  int v1; // esi
  unsigned int v2; // eax
  unsigned int v3; // edi
  unsigned int ConfigValue; // eax
  unsigned int v5; // eax
  int Token; // eax
  int v7; // ecx
  _QWORD *Heap; // rsi
  int v9; // r10d
  unsigned __int16 *i; // [rsp+70h] [rbp+38h] BYREF
  PVOID P; // [rsp+78h] [rbp+40h] BYREF
  unsigned __int16 *v12; // [rsp+80h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+50h] BYREF

  v0 = 0;
  P = 0;
  hKey = 0;
  LODWORD(i) = 0;
  v12 = 0;
  if ( !g_AllowRemoteAccessServices )
  {
    v1 = 0;
    v2 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\SecurePipeServers\\SCM",
           0,
           0x20019u,
           &hKey);
    v3 = v2;
    if ( v2 )
    {
      if ( v2 != 2
        && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 13, WPP_73e763182c4133cee281a4c48659d989_Traceguids, v2);
      }
    }
    else
    {
      ConfigValue = ScAllocateAndReadConfigValue(
                      hKey,
                      L"RemoteAccessCheckExemptionList",
                      (unsigned __int16 **)&P,
                      (unsigned int *)&i);
      v3 = ConfigValue;
      if ( ConfigValue )
      {
        if ( ConfigValue != 2
          && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 12, WPP_73e763182c4133cee281a4c48659d989_Traceguids, ConfigValue);
        }
        v0 = (unsigned __int16 *)P;
      }
      else
      {
        v0 = (unsigned __int16 *)P;
        v5 = ScValidateMultiSZ(P, (unsigned int)i);
        v3 = v5;
        if ( v5 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 11, WPP_73e763182c4133cee281a4c48659d989_Traceguids, v5);
          }
        }
        else
        {
          for ( i = v0; *i; v1 = v7 )
          {
            Token = ScGetToken(&i, &v12);
            v7 = v1 + 1;
            if ( !Token )
              v7 = v1;
          }
        }
      }
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 8LL * (unsigned int)(v1 + 1));
    if ( Heap )
    {
      if ( !v3 )
      {
        i = v0;
        while ( *i )
        {
          if ( (unsigned int)ScGetToken(&i, &v12) )
            Heap[v9] = v12;
        }
      }
      if ( !_InterlockedCompareExchange64(
              (volatile signed __int64 *)&g_AllowRemoteAccessServices,
              (signed __int64)Heap,
              0) )
      {
        Heap = 0;
        v0 = 0;
      }
    }
    else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
           && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 14, WPP_73e763182c4133cee281a4c48659d989_Traceguids);
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( Heap )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    if ( v0 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v0);
  }
}

```

## disassembly

```asm
0x14008446c  push    rbp
0x14008446e  push    rbx
0x14008446f  push    rsi
0x140084470  push    rdi
0x140084471  push    r14
0x140084473  push    r15
0x140084475  mov     rbp, rsp
0x140084478  sub     rsp, 38h
0x14008447c  xor     r14d, r14d
0x14008447f  cmp     cs:?g_AllowRemoteAccessServices@@3PEAPEAGEA, r14; ushort * * g_AllowRemoteAccessServices
0x140084486  mov     ebx, r14d
0x140084489  mov     [rbp+P], rbx
0x14008448d  mov     [rbp+hKey], r14
0x140084491  mov     dword ptr [rbp+arg_0], r14d
0x140084495  mov     [rbp+arg_10], r14
0x140084499  jnz     loc_1400846BC
0x14008449f  lea     rax, [rbp+hKey]
0x1400844a3  mov     r9d, 20019h; samDesired
0x1400844a9  xor     r8d, r8d; ulOptions
0x1400844ac  mov     [rsp+38h+phkResult], rax; phkResult
0x1400844b1  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Control\\Sec"...
0x1400844b8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400844bf  mov     esi, r14d
0x1400844c2  call    cs:__imp_RegOpenKeyExW
0x1400844c8  lea     r15, WPP_GLOBAL_Control
0x1400844cf  mov     edi, eax
0x1400844d1  test    eax, eax
0x1400844d3  jnz     loc_1400845A8
0x1400844d9  mov     rcx, [rbp+hKey]; KeyHandle
0x1400844dd  lea     r9, [rbp+arg_0]; unsigned int *
0x1400844e1  lea     r8, [rbp+P]; unsigned __int16 **
0x1400844e5  lea     rdx, aRemoteaccessch; "RemoteAccessCheckExemptionList"
0x1400844ec  call    ?ScAllocateAndReadConfigValue@@YAKPEAUHKEY__@@PEBGPEAPEAGPEAK@Z; ScAllocateAndReadConfigValue(HKEY__ *,ushort const *,ushort * *,ulong *)
0x1400844f1  mov     edi, eax
0x1400844f3  test    eax, eax
0x1400844f5  jnz     short loc_140084573
0x1400844f7  mov     rbx, [rbp+P]
0x1400844fb  mov     edx, dword ptr [rbp+arg_0]
0x1400844fe  mov     rcx, rbx
0x140084501  call    ScValidateMultiSZ
0x140084506  mov     edi, eax
0x140084508  test    eax, eax
0x14008450a  jz      short loc_140084542
0x14008450c  mov     rcx, cs:WPP_GLOBAL_Control
0x140084513  cmp     rcx, r15
0x140084516  jz      loc_1400845D7
0x14008451c  test    byte ptr [rcx+1Ch], 1
0x140084520  jz      loc_1400845D7
0x140084526  mov     rcx, [rcx+10h]
0x14008452a  lea     edx, [r14+0Bh]
0x14008452e  mov     r9d, eax
0x140084531  lea     r8, WPP_73e763182c4133cee281a4c48659d989_Traceguids
0x140084538  call    WPP_SF_d
0x14008453d  jmp     loc_1400845D7
0x140084542  mov     [rbp+arg_0], rbx
0x140084546  cmp     [rbx], r14w
0x14008454a  jz      loc_1400845D7
0x140084550  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x140084554  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x140084558  call    ?ScGetToken@@YAHPEAPEAG0@Z; ScGetToken(ushort * *,ushort * *)
0x14008455d  test    eax, eax
0x14008455f  lea     ecx, [rsi+1]
0x140084562  mov     rax, [rbp+arg_0]
0x140084566  cmovz   ecx, esi
0x140084569  mov     esi, ecx
0x14008456b  cmp     [rax], r14w
0x14008456f  jnz     short loc_140084550
0x140084571  jmp     short loc_1400845D7
0x140084573  cmp     eax, 2
0x140084576  jz      short loc_1400845A2
0x140084578  mov     rcx, cs:WPP_GLOBAL_Control
0x14008457f  cmp     rcx, r15
0x140084582  jz      short loc_1400845A2
0x140084584  test    byte ptr [rcx+1Ch], 1
0x140084588  jz      short loc_1400845A2
0x14008458a  mov     rcx, [rcx+10h]
0x14008458e  lea     r8, WPP_73e763182c4133cee281a4c48659d989_Traceguids
0x140084595  mov     edx, 0Ch
0x14008459a  mov     r9d, eax
0x14008459d  call    WPP_SF_d
0x1400845a2  mov     rbx, [rbp+P]
0x1400845a6  jmp     short loc_1400845D7
0x1400845a8  cmp     eax, 2
0x1400845ab  jz      short loc_1400845D7
0x1400845ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400845b4  cmp     rcx, r15
0x1400845b7  jz      short loc_1400845D7
0x1400845b9  test    byte ptr [rcx+1Ch], 1
0x1400845bd  jz      short loc_1400845D7
0x1400845bf  mov     rcx, [rcx+10h]
0x1400845c3  lea     r8, WPP_73e763182c4133cee281a4c48659d989_Traceguids
0x1400845ca  mov     edx, 0Dh
0x1400845cf  mov     r9d, eax
0x1400845d2  call    WPP_SF_d
0x1400845d7  mov     rcx, gs:60h
0x1400845e0  lea     r8d, [rsi+1]
0x1400845e4  shl     r8, 3; Size
0x1400845e8  mov     edx, 8; Flags
0x1400845ed  mov     rcx, [rcx+30h]; HeapHandle
0x1400845f1  call    cs:__imp_RtlAllocateHeap
0x1400845f7  mov     rsi, rax
0x1400845fa  test    rax, rax
0x1400845fd  jnz     short loc_140084626
0x1400845ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140084606  cmp     rcx, r15
0x140084609  jz      short loc_140084673
0x14008460b  test    byte ptr [rcx+1Ch], 1
0x14008460f  jz      short loc_140084673
0x140084611  mov     rcx, [rcx+10h]
0x140084615  lea     edx, [rax+0Eh]
0x140084618  lea     r8, WPP_73e763182c4133cee281a4c48659d989_Traceguids
0x14008461f  call    WPP_SF_
0x140084624  jmp     short loc_140084673
0x140084626  test    edi, edi
0x140084628  jnz     short loc_140084660
0x14008462a  mov     r10d, r14d
0x14008462d  mov     [rbp+arg_0], rbx
0x140084631  cmp     [rbx], r14w
0x140084635  jz      short loc_140084660
0x140084637  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x14008463b  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x14008463f  call    ?ScGetToken@@YAHPEAPEAG0@Z; ScGetToken(ushort * *,ushort * *)
0x140084644  test    eax, eax
0x140084646  jz      short loc_140084656
0x140084648  mov     rax, [rbp+arg_10]
0x14008464c  mov     ecx, r10d
0x14008464f  inc     r10d
0x140084652  mov     [rsi+rcx*8], rax
0x140084656  mov     rax, [rbp+arg_0]
0x14008465a  cmp     [rax], r14w
0x14008465e  jnz     short loc_140084637
0x140084660  xor     eax, eax
0x140084662  lock cmpxchg cs:?g_AllowRemoteAccessServices@@3PEAPEAGEA, rsi; ushort * * g_AllowRemoteAccessServices
0x14008466b  jnz     short loc_140084673
0x14008466d  mov     rsi, r14
0x140084670  mov     rbx, r14
0x140084673  mov     rcx, [rbp+hKey]; hKey
0x140084677  test    rcx, rcx
0x14008467a  jz      short loc_140084682
0x14008467c  call    cs:__imp_RegCloseKey
0x140084682  test    rsi, rsi
0x140084685  jz      short loc_14008469F
0x140084687  mov     rcx, gs:60h
0x140084690  mov     r8, rsi; P
0x140084693  xor     edx, edx; Flags
0x140084695  mov     rcx, [rcx+30h]; HeapHandle
0x140084699  call    cs:__imp_RtlFreeHeap
0x14008469f  test    rbx, rbx
0x1400846a2  jz      short loc_1400846BC
0x1400846a4  mov     rcx, gs:60h
0x1400846ad  mov     r8, rbx; P
0x1400846b0  xor     edx, edx; Flags
0x1400846b2  mov     rcx, [rcx+30h]; HeapHandle
0x1400846b6  call    cs:__imp_RtlFreeHeap
0x1400846bc  add     rsp, 38h
0x1400846c0  pop     r15
0x1400846c2  pop     r14
0x1400846c4  pop     rdi
0x1400846c5  pop     rsi
0x1400846c6  pop     rbx
0x1400846c7  pop     rbp
0x1400846c8  retn
```
