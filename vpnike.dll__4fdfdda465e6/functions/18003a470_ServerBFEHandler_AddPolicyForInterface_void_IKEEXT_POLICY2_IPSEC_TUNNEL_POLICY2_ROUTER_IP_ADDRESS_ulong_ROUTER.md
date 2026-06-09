# ServerBFEHandler::AddPolicyForInterface(void *,IKEEXT_POLICY2_ *,IPSEC_TUNNEL_POLICY2_ *,_ROUTER_IP_ADDRESS *,ulong,_ROUTER_IP_ADDRESS *)

- ea: `0x18003a470`
- end: `0x18003a829`
- name: `?AddPolicyForInterface@ServerBFEHandler@@KAKPEAXPEAUIKEEXT_POLICY2_@@PEAUIPSEC_TUNNEL_POLICY2_@@PEAU_ROUTER_IP_ADDRESS@@K3@Z`
- size: `953`
- prototype: `__int64 __fastcall(void *, struct IKEEXT_POLICY2_ *, struct IPSEC_TUNNEL_POLICY2_ *, struct _ROUTER_IP_ADDRESS *, unsigned int, struct _ROUTER_IP_ADDRESS *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003a830`
- `0x18003ac84`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x18003a470`
- `0x18003d434`
- `0x18003fd14`
- `0x18003fed8`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a79b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a7b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a79b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a7b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a5c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a611`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a5c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a611`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a5b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a5fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a78d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a7a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a5b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a5fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a78d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a7a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a702`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a702`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a727`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a727`

## string_xrefs

- `0x18003a57c`: `AddPolicyForInterface: RemovePolicyForInterface failed: %d`

## pseudocode

```c
__int64 __fastcall ServerBFEHandler::AddPolicyForInterface(
        void *a1,
        struct IKEEXT_POLICY2_ *a2,
        struct IPSEC_TUNNEL_POLICY2_ *a3,
        struct _ROUTER_IP_ADDRESS *a4,
        unsigned int a5,
        struct _ROUTER_IP_ADDRESS *a6)
{
  _QWORD *v8; // rdi
  unsigned int v9; // esi
  unsigned int v10; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v12; // rax
  LPVOID v13; // rax
  __int64 v14; // rbx
  struct IPSEC_TUNNEL_POLICY2_ *v15; // r14
  _WORD *v16; // r10
  struct _GUID *v17; // rdx
  struct _GUID *v18; // r8
  struct _GUID *v19; // rcx
  struct _GUID *v20; // rax
  unsigned int v21; // ebx
  __int64 v22; // rdx
  __int64 v23; // r8
  GUID *v24; // rcx
  __int64 v25; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  HANDLE v28; // rax
  unsigned int v29; // ebx
  unsigned int v31; // [rsp+40h] [rbp-C0h] BYREF
  struct IPSEC_TUNNEL_POLICY2_ *v32; // [rsp+48h] [rbp-B8h]
  struct _ROUTER_IP_ADDRESS *v33; // [rsp+50h] [rbp-B0h]
  __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v35; // [rsp+60h] [rbp-A0h]
  __int128 v36; // [rsp+70h] [rbp-90h]
  __int64 v37; // [rsp+80h] [rbp-80h]
  int v38; // [rsp+88h] [rbp-78h]
  int v39; // [rsp+8Ch] [rbp-74h]
  int v40; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v41[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v33 = a4;
  v32 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
  }
  v8 = 0;
  v31 = 0;
  v9 = 0;
  v40 = 0;
  memset_0(v41, 0, sizeof(v41));
  v35 = 0;
  v34 = 0;
  v36 = 0;
  v37 = 0;
  v38 = -1;
  v39 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v34,
      L"ServerBFEHandler::AddPolicyForInterface",
      &v31,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  v10 = ServerBFEHandler::RemovePolicyForInterface(a1);
  v31 = v10;
  if ( v10 )
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v40) = 0;
      FormatRRASErrorString(&v40, L"AddPolicyForInterface: RemovePolicyForInterface failed: %d", v10);
      goto LABEL_10;
    }
    goto LABEL_34;
  }
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 8u, 0x20u);
  if ( !v8 || (v12 = GetProcessHeap(), v13 = HeapAlloc(v12, 8u, 32LL * a5), (v8[3] = v13) == 0) )
  {
    v31 = 8;
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v40) = 0;
      FormatRRASErrorString(&v40, L"AddPolicyForInterface: VPNIKE_MALLOC failed: %d", 8);
      goto LABEL_10;
    }
    goto LABEL_35;
  }
  v8[1] = a1;
  *v8 = 0;
  *((_DWORD *)a2 + 8) |= 0x10u;
  v14 = 0;
  v15 = v32;
  while ( 1 )
  {
    if ( (unsigned int)v14 >= a5 )
    {
      *((_DWORD *)v8 + 4) = v9;
      EnterCriticalSection(&ServerBFEHandler::csInterfacePolicyMapping);
      if ( ServerBFEHandler::interfacePolicyMapping )
        *v8 = ServerBFEHandler::interfacePolicyMapping;
      ServerBFEHandler::interfacePolicyMapping = (struct ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP *)v8;
      v8 = 0;
      LeaveCriticalSection(&ServerBFEHandler::csInterfacePolicyMapping);
      goto LABEL_34;
    }
    v16 = (_WORD *)((char *)a6 + 20 * v14);
    if ( *v16 == 23 )
    {
      v17 = (struct _GUID *)(v8[3] + 16LL * (v9 + 3));
    }
    else
    {
      v17 = 0;
      if ( *v16 == 2 )
      {
        v18 = (struct _GUID *)(v8[3] + 16LL * (v9 + 2));
        goto LABEL_27;
      }
    }
    v18 = 0;
    if ( *v16 == 23 )
    {
      v19 = (struct _GUID *)(v8[3] + 16LL * (v9 + 1));
LABEL_22:
      v20 = 0;
      goto LABEL_23;
    }
LABEL_27:
    v19 = 0;
    if ( *v16 != 2 )
      goto LABEL_22;
    v20 = (struct _GUID *)(v8[3] + 16LL * v9);
LABEL_23:
    v31 = ServerBFEHandler::PlumbPolicyForRemoteIpAddr(
            v33,
            (struct _ROUTER_IP_ADDRESS *)((char *)a6 + 20 * v14),
            a2,
            v15,
            v20,
            v19,
            v18,
            v17);
    v9 += 4;
    if ( v31 )
      break;
    v14 = (unsigned int)(v14 + 1);
  }
  if ( (byte_1800AA941 & 4) == 0 )
    goto LABEL_34;
  LOWORD(v40) = 0;
  FormatRRASErrorString(&v40, L"AddPolicyForInterface: PlumbPolicyForRemoteIpAddr failed: %d", v31);
LABEL_10:
  if ( (byte_1800AA941 & 4) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v40);
LABEL_34:
  if ( v31 )
  {
LABEL_35:
    v21 = 0;
    if ( v9 )
    {
      v22 = *(_QWORD *)GUID_NULL.Data4;
      v23 = *(_QWORD *)&GUID_NULL.Data1;
      do
      {
        v24 = (GUID *)(v8[3] + 16LL * v21);
        v25 = *(_QWORD *)&v24->Data1 - v23;
        if ( *(_QWORD *)&v24->Data1 == v23 )
          v25 = *(_QWORD *)v24->Data4 - v22;
        if ( v25 )
        {
          ServerBFEHandler::RemovePolicy(v24);
          v22 = *(_QWORD *)GUID_NULL.Data4;
          v23 = *(_QWORD *)&GUID_NULL.Data1;
        }
        ++v21;
      }
      while ( v21 < v9 );
    }
  }
  if ( v8 )
  {
    v26 = (void *)v8[3];
    if ( v26 )
    {
      v27 = GetProcessHeap();
      HeapFree(v27, 0, v26);
      v8[3] = 0;
    }
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v8);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids, v31);
  }
  v29 = v31;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v34);
  return v29;
}

```

## disassembly

```asm
0x18003a470  push    rbp
0x18003a472  push    rbx
0x18003a473  push    rsi
0x18003a474  push    rdi
0x18003a475  push    r12
0x18003a477  push    r13
0x18003a479  push    r14
0x18003a47b  push    r15
0x18003a47d  lea     rbp, [rsp-7A8h]
0x18003a485  sub     rsp, 8A8h
0x18003a48c  mov     rax, cs:__security_cookie
0x18003a493  xor     rax, rsp
0x18003a496  mov     [rbp+7E0h+var_50], rax
0x18003a49d  mov     [rsp+8E0h+var_890], r9
0x18003a4a2  mov     [rsp+8E0h+var_898], r8
0x18003a4a7  mov     r15, rdx
0x18003a4aa  mov     r14, rcx
0x18003a4ad  mov     r12d, [rbp+7E0h+arg_20]
0x18003a4b4  mov     r13, [rbp+7E0h+arg_28]
0x18003a4bb  lea     rax, WPP_GLOBAL_Control
0x18003a4c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a4c9  cmp     rcx, rax
0x18003a4cc  jz      short loc_18003A4EF
0x18003a4ce  test    byte ptr [rcx+1Ch], 1
0x18003a4d2  jz      short loc_18003A4EF
0x18003a4d4  cmp     byte ptr [rcx+19h], 6
0x18003a4d8  jb      short loc_18003A4EF
0x18003a4da  mov     edx, 3Eh ; '>'
0x18003a4df  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x18003a4e6  mov     rcx, [rcx+10h]
0x18003a4ea  call    WPP_SF_
0x18003a4ef  xor     edi, edi
0x18003a4f1  mov     [rsp+8E0h+var_8A0], edi
0x18003a4f5  mov     esi, edi
0x18003a4f7  mov     [rbp+7E0h+var_850], edi
0x18003a4fa  xor     edx, edx; Val
0x18003a4fc  mov     r8d, 7FCh; Size
0x18003a502  lea     rcx, [rbp+7E0h+var_84C]; void *
0x18003a506  call    memset_0
0x18003a50b  xorps   xmm0, xmm0
0x18003a50e  movdqu  [rsp+8E0h+var_880], xmm0
0x18003a514  mov     [rsp+8E0h+var_888], rdi
0x18003a519  xorps   xmm1, xmm1
0x18003a51c  movdqu  [rsp+8E0h+var_870], xmm1
0x18003a522  mov     [rbp+7E0h+var_860], rdi
0x18003a526  mov     [rbp+7E0h+var_858], 0FFFFFFFFh
0x18003a52d  mov     [rbp+7E0h+var_854], edi
0x18003a530  lea     ebx, [rdi+8]
0x18003a533  test    cs:byte_1800AA941, bl
0x18003a539  jz      short loc_18003A558
0x18003a53b  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18003a542  lea     r8, [rsp+8E0h+var_8A0]; unsigned int *
0x18003a547  lea     rdx, aServerbfehandl_0; "ServerBFEHandler::AddPolicyForInterface"
0x18003a54e  lea     rcx, [rsp+8E0h+var_888]; this
0x18003a553  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18003a558  mov     rcx, r14; void *
0x18003a55b  call    ?RemovePolicyForInterface@ServerBFEHandler@@KAKPEAX@Z; ServerBFEHandler::RemovePolicyForInterface(void *)
0x18003a560  mov     r8d, eax
0x18003a563  mov     [rsp+8E0h+var_8A0], eax
0x18003a567  test    eax, eax
0x18003a569  jz      short loc_18003A5B5
0x18003a56b  test    cs:byte_1800AA941, 4
0x18003a572  jz      loc_18003A72D
0x18003a578  mov     word ptr [rbp+7E0h+var_850], di
0x18003a57c  lea     rdx, aAddpolicyforin_0; "AddPolicyForInterface: RemovePolicyForI"...
0x18003a583  lea     rcx, [rbp+7E0h+var_850]
0x18003a587  call    FormatRRASErrorString
0x18003a58c  test    cs:byte_1800AA941, 4
0x18003a593  jz      loc_18003A72D
0x18003a599  lea     r8, [rbp+7E0h+var_850]
0x18003a59d  lea     rdx, RasVpnIkeTraceError
0x18003a5a4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003a5ab  call    McTemplateU0z_EventWriteTransfer
0x18003a5b0  jmp     loc_18003A72D
0x18003a5b5  call    cs:__imp_GetProcessHeap
0x18003a5bb  mov     rcx, rax; hHeap
0x18003a5be  mov     r8d, 20h ; ' '; dwBytes
0x18003a5c4  mov     edx, ebx; dwFlags
0x18003a5c6  call    cs:__imp_HeapAlloc
0x18003a5cc  mov     rdi, rax
0x18003a5cf  test    rax, rax
0x18003a5d2  jnz     short loc_18003A5F7
0x18003a5d4  mov     [rsp+8E0h+var_8A0], ebx
0x18003a5d8  test    cs:byte_1800AA941, 4
0x18003a5df  jz      loc_18003A734
0x18003a5e5  xor     eax, eax
0x18003a5e7  mov     word ptr [rbp+7E0h+var_850], ax
0x18003a5eb  mov     r8d, ebx
0x18003a5ee  lea     rdx, aAddpolicyforin; "AddPolicyForInterface: VPNIKE_MALLOC fa"...
0x18003a5f5  jmp     short loc_18003A583
0x18003a5f7  mov     rbx, r12
0x18003a5fa  shl     rbx, 5
0x18003a5fe  call    cs:__imp_GetProcessHeap
0x18003a604  mov     rcx, rax; hHeap
0x18003a607  mov     r8, rbx; dwBytes
0x18003a60a  mov     ebx, 8
0x18003a60f  mov     edx, ebx; dwFlags
0x18003a611  call    cs:__imp_HeapAlloc
0x18003a617  mov     [rdi+18h], rax
0x18003a61b  test    rax, rax
0x18003a61e  jz      short loc_18003A5D4
0x18003a620  mov     [rdi+8], r14
0x18003a624  mov     qword ptr [rdi], 0
0x18003a62b  or      dword ptr [r15+20h], 10h
0x18003a630  xor     ebx, ebx
0x18003a632  mov     r14, [rsp+8E0h+var_898]
0x18003a637  cmp     ebx, r12d
0x18003a63a  jnb     loc_18003A6F8
0x18003a640  lea     rcx, [rbx+rbx*4]
0x18003a644  lea     r10, ds:0[rcx*4]
0x18003a64c  add     r10, r13
0x18003a64f  cmp     word ptr [r10], 17h
0x18003a654  jnz     short loc_18003A6AE
0x18003a656  lea     edx, [rsi+3]
0x18003a659  shl     rdx, 4
0x18003a65d  add     rdx, [rdi+18h]
0x18003a661  xor     r8d, r8d
0x18003a664  cmp     word ptr [r10], 17h
0x18003a669  jnz     short loc_18003A6C3
0x18003a66b  lea     ecx, [rsi+1]
0x18003a66e  shl     rcx, 4
0x18003a672  add     rcx, [rdi+18h]
0x18003a676  xor     eax, eax
0x18003a678  mov     [rsp+8E0h+var_8A8], rdx; struct _GUID *
0x18003a67d  mov     [rsp+8E0h+var_8B0], r8; struct _GUID *
0x18003a682  mov     [rsp+8E0h+var_8B8], rcx; struct _GUID *
0x18003a687  mov     [rsp+8E0h+var_8C0], rax; struct _GUID *
0x18003a68c  mov     r9, r14; struct IPSEC_TUNNEL_POLICY2_ *
0x18003a68f  mov     r8, r15; struct IKEEXT_POLICY2_ *
0x18003a692  mov     rdx, r10; struct _ROUTER_IP_ADDRESS *
0x18003a695  mov     rcx, [rsp+8E0h+var_890]; struct _ROUTER_IP_ADDRESS *
0x18003a69a  call    ?PlumbPolicyForRemoteIpAddr@ServerBFEHandler@@KAKPEAU_ROUTER_IP_ADDRESS@@0PEAUIKEEXT_POLICY2_@@PEAUIPSEC_TUNNEL_POLICY2_@@PEAU_GUID@@333@Z; ServerBFEHandler::PlumbPolicyForRemoteIpAddr(_ROUTER_IP_ADDRESS *,_ROUTER_IP_ADDRESS *,IKEEXT_POLICY2_ *,IPSEC_TUNNEL_POLICY2_ *,_GUID *,_GUID *,_GUID *,_GUID *)
0x18003a69f  mov     [rsp+8E0h+var_8A0], eax
0x18003a6a3  add     esi, 4
0x18003a6a6  test    eax, eax
0x18003a6a8  jnz     short loc_18003A6D8
0x18003a6aa  inc     ebx
0x18003a6ac  jmp     short loc_18003A637
0x18003a6ae  xor     edx, edx
0x18003a6b0  cmp     word ptr [r10], 2
0x18003a6b5  jnz     short loc_18003A661
0x18003a6b7  lea     r8d, [rsi+2]
0x18003a6bb  shl     r8, 4
0x18003a6bf  add     r8, [rdi+18h]
0x18003a6c3  xor     ecx, ecx
0x18003a6c5  cmp     word ptr [r10], 2
0x18003a6ca  jnz     short loc_18003A676
0x18003a6cc  mov     eax, esi
0x18003a6ce  shl     rax, 4
0x18003a6d2  add     rax, [rdi+18h]
0x18003a6d6  jmp     short loc_18003A678
0x18003a6d8  test    cs:byte_1800AA941, 4
0x18003a6df  jz      short loc_18003A72D
0x18003a6e1  xor     eax, eax
0x18003a6e3  mov     word ptr [rbp+7E0h+var_850], ax
0x18003a6e7  mov     r8d, [rsp+8E0h+var_8A0]
0x18003a6ec  lea     rdx, aAddpolicyforin_2; "AddPolicyForInterface: PlumbPolicyForRe"...
0x18003a6f3  jmp     loc_18003A583
0x18003a6f8  mov     [rdi+10h], esi
0x18003a6fb  lea     rcx, ?csInterfacePolicyMapping@ServerBFEHandler@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a702  call    cs:__imp_EnterCriticalSection
0x18003a708  mov     rax, cs:?interfacePolicyMapping@ServerBFEHandler@@1PEAU_VPNIKE_INTERFACE_POLICY_MAP@1@EA; ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP * ServerBFEHandler::interfacePolicyMapping
0x18003a70f  test    rax, rax
0x18003a712  jz      short loc_18003A717
0x18003a714  mov     [rdi], rax
0x18003a717  mov     cs:?interfacePolicyMapping@ServerBFEHandler@@1PEAU_VPNIKE_INTERFACE_POLICY_MAP@1@EA, rdi; ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP * ServerBFEHandler::interfacePolicyMapping
0x18003a71e  xor     edi, edi
0x18003a720  lea     rcx, ?csInterfacePolicyMapping@ServerBFEHandler@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a727  call    cs:__imp_LeaveCriticalSection
0x18003a72d  cmp     [rsp+8E0h+var_8A0], 0
0x18003a732  jz      short loc_18003A77F
0x18003a734  xor     ebx, ebx
0x18003a736  test    esi, esi
0x18003a738  jz      short loc_18003A77F
0x18003a73a  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x18003a741  mov     r8, qword ptr cs:GUID_NULL.Data1
0x18003a748  mov     ecx, ebx
0x18003a74a  shl     rcx, 4
0x18003a74e  add     rcx, [rdi+18h]; key
0x18003a752  mov     rax, [rcx]
0x18003a755  sub     rax, r8
0x18003a758  jnz     short loc_18003A761
0x18003a75a  mov     rax, [rcx+8]
0x18003a75e  sub     rax, rdx
0x18003a761  test    rax, rax
0x18003a764  jz      short loc_18003A779
0x18003a766  call    ?RemovePolicy@ServerBFEHandler@@KAKAEAU_GUID@@@Z; ServerBFEHandler::RemovePolicy(_GUID &)
0x18003a76b  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x18003a772  mov     r8, qword ptr cs:GUID_NULL.Data1
0x18003a779  inc     ebx
0x18003a77b  cmp     ebx, esi
0x18003a77d  jb      short loc_18003A748
0x18003a77f  test    rdi, rdi
0x18003a782  jz      short loc_18003A7BD
0x18003a784  mov     rbx, [rdi+18h]
0x18003a788  test    rbx, rbx
0x18003a78b  jz      short loc_18003A7A9
0x18003a78d  call    cs:__imp_GetProcessHeap
0x18003a793  mov     r8, rbx; lpMem
0x18003a796  xor     edx, edx; dwFlags
0x18003a798  mov     rcx, rax; hHeap
0x18003a79b  call    cs:__imp_HeapFree
0x18003a7a1  mov     qword ptr [rdi+18h], 0
0x18003a7a9  call    cs:__imp_GetProcessHeap
0x18003a7af  mov     rcx, rax; hHeap
0x18003a7b2  mov     r8, rdi; lpMem
0x18003a7b5  xor     edx, edx; dwFlags
0x18003a7b7  call    cs:__imp_HeapFree
0x18003a7bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a7c4  lea     rax, WPP_GLOBAL_Control
0x18003a7cb  cmp     rcx, rax
0x18003a7ce  jz      short loc_18003A7F6
0x18003a7d0  test    byte ptr [rcx+1Ch], 1
0x18003a7d4  jz      short loc_18003A7F6
0x18003a7d6  cmp     byte ptr [rcx+19h], 6
0x18003a7da  jb      short loc_18003A7F6
0x18003a7dc  mov     edx, 3Fh ; '?'
0x18003a7e1  mov     r9d, [rsp+8E0h+var_8A0]
0x18003a7e6  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x18003a7ed  mov     rcx, [rcx+10h]
0x18003a7f1  call    WPP_SF_d
0x18003a7f6  mov     ebx, [rsp+8E0h+var_8A0]
0x18003a7fa  lea     rcx, [rsp+8E0h+var_888]; this
0x18003a7ff  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003a804  mov     eax, ebx
0x18003a806  mov     rcx, [rbp+7E0h+var_50]
0x18003a80d  xor     rcx, rsp; StackCookie
0x18003a810  call    __security_check_cookie
0x18003a815  add     rsp, 8A8h
0x18003a81c  pop     r15
0x18003a81e  pop     r14
0x18003a820  pop     r13
0x18003a822  pop     r12
0x18003a824  pop     rdi
0x18003a825  pop     rsi
0x18003a826  pop     rbx
0x18003a827  pop     rbp
0x18003a828  retn
```
