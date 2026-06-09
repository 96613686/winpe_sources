# ScReadGlobalStartType(_SERVICE_CONFIG_ROOT *,HKEY__ *,ushort const *,int,int,ulong *)

- ea: `0x1400250c8`
- end: `0x140025303`
- name: `?ScReadGlobalStartType@@YAKPEAU_SERVICE_CONFIG_ROOT@@PEAUHKEY__@@PEBGHHPEAK@Z`
- size: `571`
- prototype: `unsigned int(struct _SERVICE_CONFIG_ROOT *, HKEY, const unsigned __int16 *, int, int, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x14000b2e4`
- `0x14000c988`
- `0x140068b60`

## callees

- `0x140019014`
- `0x14001f99c`
- `0x1400250c8`
- `0x140079578`
- `0x140092420`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1400251cb`
- `ntdll!RtlNtStatusToDosError` at `0x1400251cb`
- `ntdll!RtlInitUnicodeString` at `0x140025128`
- `ntdll!RtlInitUnicodeString` at `0x140025128`
- `ntdll!RtlFreeHeap` at `0x1400251c3`
- `ntdll!RtlFreeHeap` at `0x1400251c3`
- `ntdll!NtQueryValueKey` at `0x140025185`
- `ntdll!NtQueryValueKey` at `0x140025185`
- `ntdll!RtlAllocateHeap` at `0x14002514e`
- `ntdll!RtlAllocateHeap` at `0x14002514e`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x140025257`
- `api-ms-win-core-state-helpers-l1-1-0!GetRegistryValueWithFallbackW` at `0x140025257`

## pseudocode

```c
__int64 __fastcall ScReadGlobalStartType(
        struct _SERVICE_CONFIG_ROOT *a1,
        HKEY a2,
        const unsigned __int16 *a3,
        int a4,
        int a5,
        unsigned int *Length)
{
  unsigned int *v6; // r14
  ULONG v9; // ebx
  _DWORD *Heap; // rax
  _DWORD *v11; // rdi
  int v12; // ebx
  unsigned int v13; // eax
  HKEY RegistryStateRootHandle; // rax
  __int64 v16; // r10
  int v17; // r11d
  ULONG v18; // eax
  PRPC_ASYNC_STATE v19; // rcx
  int v20; // [rsp+50h] [rbp-20h] BYREF
  int v21; // [rsp+54h] [rbp-1Ch] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-18h] BYREF

  v6 = Length;
  v20 = 0;
  v21 = 0;
  *Length = 4;
  if ( g_StateSeparationEnabled && a5 )
  {
    RegistryStateRootHandle = ScGetRegistryStateRootHandle((__int64)a1, 0, a4);
    v18 = ((__int64 (__fastcall *)(HKEY, const unsigned __int16 *, _QWORD, const unsigned __int16 *, const WCHAR *, int, int *, unsigned int *, int, int *))GetRegistryValueWithFallbackW)(
            RegistryStateRootHandle,
            a3,
            *(_QWORD *)(v16 + 32),
            a3,
            L"Start",
            16,
            &v21,
            v6,
            v17,
            &v20);
    v9 = v18;
    if ( (v18 & 0xFFFFFFFD) != 0
      && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      WPP_SF_SLd(
        WPP_GLOBAL_Control->StubInfo,
        311,
        (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
        (_DWORD)a3,
        v20,
        v18);
    }
    return v9;
  }
  v20 = 4;
  LODWORD(Length) = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"Start");
  v9 = 8;
  LODWORD(Length) = 16;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
  v11 = Heap;
  if ( !Heap )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
      return v9;
    if ( (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_19;
    WPP_SF_(WPP_GLOBAL_Control->StubInfo, 113, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
LABEL_18:
    v19 = WPP_GLOBAL_Control;
LABEL_19:
    if ( v19 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v19->UserInfo) & 1) != 0 )
      WPP_SF_SLd(v19->StubInfo, 312, (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, (_DWORD)a3, v20, v9);
    return v9;
  }
  v12 = NtQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, Heap, (ULONG)Length, (PULONG)&Length);
  if ( (int)(v12 + 0x80000000) < 0 || v12 == -2147483643 )
  {
    v13 = v11[2];
    v20 = v13;
    v21 = v11[1];
    if ( v12 >= 0 && v11[2] <= v13 )
      memmove(v6, v11 + 3, (unsigned int)v11[2]);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  v9 = RtlNtStatusToDosError(v12);
  if ( (v9 & 0xFFFFFFFD) != 0 )
    goto LABEL_18;
  return v9;
}

```

## disassembly

```asm
0x1400250c8  push    rbp
0x1400250ca  push    rbx
0x1400250cb  push    rsi
0x1400250cc  push    rdi
0x1400250cd  push    r12
0x1400250cf  push    r14
0x1400250d1  push    r15
0x1400250d3  mov     rbp, rsp
0x1400250d6  sub     rsp, 70h
0x1400250da  mov     r14, qword ptr [rbp+arg_28]
0x1400250de  mov     r11d, 4
0x1400250e4  mov     r15, r8
0x1400250e7  mov     [rbp+var_20], 0
0x1400250ee  mov     r12, rdx
0x1400250f1  mov     [rbp+var_1C], 0
0x1400250f8  mov     r10, rcx
0x1400250fb  mov     [r14], r11d
0x1400250fe  cmp     cs:?g_StateSeparationEnabled@@3HA, 0; int g_StateSeparationEnabled
0x140025105  jnz     loc_140025206
0x14002510b  xorps   xmm0, xmm0
0x14002510e  mov     [rbp+var_20], r11d
0x140025112  lea     rdx, aStart; "Start"
0x140025119  mov     [rbp+arg_28], 0
0x140025120  lea     rcx, [rbp+DestinationString]; DestinationString
0x140025124  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140025128  call    cs:__imp_RtlInitUnicodeString
0x14002512e  mov     eax, [rbp+var_20]
0x140025131  mov     ebx, 8
0x140025136  add     eax, 0Ch
0x140025139  mov     edx, ebx; Flags
0x14002513b  mov     [rbp+arg_28], eax
0x14002513e  mov     rcx, gs:60h
0x140025147  mov     r8d, eax; Size
0x14002514a  mov     rcx, [rcx+30h]; HeapHandle
0x14002514e  call    cs:__imp_RtlAllocateHeap
0x140025154  lea     rsi, WPP_GLOBAL_Control
0x14002515b  mov     rdi, rax
0x14002515e  test    rax, rax
0x140025161  jz      loc_140025296
0x140025167  lea     rax, [rbp+arg_28]
0x14002516b  mov     r9, rdi; KeyValueInformation
0x14002516e  mov     [rsp+70h+ResultLength], rax; ResultLength
0x140025173  lea     r8d, [rbx-6]; KeyValueInformationClass
0x140025177  mov     eax, [rbp+arg_28]
0x14002517a  lea     rdx, [rbp+DestinationString]; ValueName
0x14002517e  mov     rcx, r12; KeyHandle
0x140025181  mov     [rsp+70h+Length], eax; Length
0x140025185  call    cs:__imp_NtQueryValueKey
0x14002518b  mov     ebx, eax
0x14002518d  mov     eax, 80000000h
0x140025192  lea     ecx, [rbx+rax]
0x140025195  test    eax, ecx
0x140025197  jnz     short loc_1400251A1
0x140025199  cmp     ebx, 80000005h
0x14002519f  jnz     short loc_1400251B1
0x1400251a1  mov     eax, [rdi+8]
0x1400251a4  mov     [rbp+var_20], eax
0x1400251a7  mov     edx, [rdi+4]
0x1400251aa  mov     [rbp+var_1C], edx
0x1400251ad  test    ebx, ebx
0x1400251af  jns     short loc_1400251EF
0x1400251b1  mov     rcx, gs:60h
0x1400251ba  mov     r8, rdi; P
0x1400251bd  xor     edx, edx; Flags
0x1400251bf  mov     rcx, [rcx+30h]; HeapHandle
0x1400251c3  call    cs:__imp_RtlFreeHeap
0x1400251c9  mov     ecx, ebx; Status
0x1400251cb  call    cs:__imp_RtlNtStatusToDosError
0x1400251d1  mov     ebx, eax
0x1400251d3  test    eax, 0FFFFFFFDh
0x1400251d8  jnz     loc_1400252C1
0x1400251de  mov     eax, ebx
0x1400251e0  add     rsp, 70h
0x1400251e4  pop     r15
0x1400251e6  pop     r14
0x1400251e8  pop     r12
0x1400251ea  pop     rdi
0x1400251eb  pop     rsi
0x1400251ec  pop     rbx
0x1400251ed  pop     rbp
0x1400251ee  retn
0x1400251ef  cmp     [rdi+8], eax
0x1400251f2  ja      short loc_1400251B1
0x1400251f4  mov     r8d, [rdi+8]; Size
0x1400251f8  lea     rdx, [rdi+0Ch]; Src
0x1400251fc  mov     rcx, r14; void *
0x1400251ff  call    memmove
0x140025204  jmp     short loc_1400251B1
0x140025206  cmp     [rbp+arg_20], 0
0x14002520a  jz      loc_14002510B
0x140025210  mov     r8d, r9d
0x140025213  xor     edx, edx
0x140025215  call    ?ScGetRegistryStateRootHandle@@YAPEAUHKEY__@@PEAU_SERVICE_CONFIG_ROOT@@HHW4_SC_INTERNAL_REGISTRY_STATE_TYPE@@@Z; ScGetRegistryStateRootHandle(_SERVICE_CONFIG_ROOT *,int,int,_SC_INTERNAL_REGISTRY_STATE_TYPE)
0x14002521a  mov     r8, [r10+20h]
0x14002521e  lea     rdx, aStart; "Start"
0x140025225  mov     rcx, rax
0x140025228  mov     r9, r15
0x14002522b  lea     rax, [rbp+var_20]
0x14002522f  mov     [rsp+70h+var_28], rax
0x140025234  lea     rax, [rbp+var_1C]
0x140025238  mov     [rsp+70h+var_30], r11d
0x14002523d  mov     [rsp+70h+var_38], r14
0x140025242  mov     [rsp+70h+var_40], rax
0x140025247  mov     dword ptr [rsp+70h+ResultLength], 10h
0x14002524f  mov     qword ptr [rsp+70h+Length], rdx
0x140025254  mov     rdx, r15
0x140025257  call    cs:__imp_GetRegistryValueWithFallbackW
0x14002525d  mov     ebx, eax
0x14002525f  test    eax, 0FFFFFFFDh
0x140025264  jz      loc_1400251DE
0x14002526a  mov     rcx, cs:WPP_GLOBAL_Control
0x140025271  lea     rsi, WPP_GLOBAL_Control
0x140025278  cmp     rcx, rsi
0x14002527b  jz      loc_1400251DE
0x140025281  test    byte ptr [rcx+1Ch], 1
0x140025285  jz      loc_1400251DE
0x14002528b  mov     edx, 137h
0x140025290  mov     dword ptr [rsp+70h+ResultLength], eax
0x140025294  jmp     short loc_1400252E4
0x140025296  mov     rcx, cs:WPP_GLOBAL_Control
0x14002529d  cmp     rcx, rsi
0x1400252a0  jz      loc_1400251DE
0x1400252a6  test    byte ptr [rcx+1Ch], 1
0x1400252aa  jz      short loc_1400252C8
0x1400252ac  mov     rcx, [rcx+10h]
0x1400252b0  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x1400252b7  mov     edx, 71h ; 'q'
0x1400252bc  call    WPP_SF_
0x1400252c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400252c8  cmp     rcx, rsi
0x1400252cb  jz      loc_1400251DE
0x1400252d1  test    byte ptr [rcx+1Ch], 1
0x1400252d5  jz      loc_1400251DE
0x1400252db  mov     edx, 138h
0x1400252e0  mov     dword ptr [rsp+70h+ResultLength], ebx
0x1400252e4  mov     eax, [rbp+var_20]
0x1400252e7  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x1400252ee  mov     rcx, [rcx+10h]
0x1400252f2  mov     r9, r15
0x1400252f5  mov     [rsp+70h+Length], eax
0x1400252f9  call    WPP_SF_SLd
0x1400252fe  jmp     loc_1400251DE
```
