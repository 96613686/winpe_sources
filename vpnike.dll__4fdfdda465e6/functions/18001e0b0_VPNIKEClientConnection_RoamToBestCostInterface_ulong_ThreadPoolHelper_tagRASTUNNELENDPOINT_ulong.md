# VPNIKEClientConnection::RoamToBestCostInterface(ulong,ThreadPoolHelper *,tagRASTUNNELENDPOINT *,ulong)

- ea: `0x18001e0b0`
- end: `0x18001e43b`
- name: `?RoamToBestCostInterface@VPNIKEClientConnection@@QEAAXKPEAVThreadPoolHelper@@PEAUtagRASTUNNELENDPOINT@@K@Z`
- size: `907`
- prototype: `void __fastcall(VPNIKEClientConnection *this, __int64, struct ThreadPoolHelper *, struct tagRASTUNNELENDPOINT *, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006738`
- `0x180007070`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18001e0b0`
- `0x180020e04`
- `0x18005d9ac`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e3d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e3d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e16a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e16a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e158`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e3cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e158`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e3cb`

## string_xrefs

- `0x18001e323`: `ThreadPool->QueueWorkItem(DispatchUpdateConnection) failed: %!WINERROR!`

## pseudocode

```c
void __fastcall VPNIKEClientConnection::RoamToBestCostInterface(
        VPNIKEClientConnection *this,
        __int64 a2,
        struct ThreadPoolHelper *a3,
        struct tagRASTUNNELENDPOINT *a4,
        unsigned int a5)
{
  int v7; // r14d
  HANDLE ProcessHeap; // rax
  char *v10; // rax
  char *v11; // rdi
  PVOID *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int128 *v16; // r9
  unsigned int v17; // esi
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int128 *v21; // r9
  HANDLE v22; // rax
  __int128 v23; // [rsp+30h] [rbp-D0h] BYREF
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v25; // [rsp+44h] [rbp-BCh]
  __int128 v26; // [rsp+54h] [rbp-ACh]
  int v27; // [rsp+64h] [rbp-9Ch]
  int v28; // [rsp+70h] [rbp-90h] BYREF
  char v29[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v7 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_dDc(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (unsigned int)a2, a5, *((_BYTE *)this + 16));
  }
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v24 = 0;
  v25 = 0;
  v27 = 0;
  v26 = 0;
  v23 = 0;
  ProcessHeap = GetProcessHeap();
  v10 = (char *)HeapAlloc(ProcessHeap, 8u, 0x48u);
  v11 = v10;
  if ( v10 )
  {
    memset_0(v10, 0, 0x48u);
    *(_QWORD *)v11 = *(_QWORD *)(*((_QWORD *)this + 14) + 24LL);
    _InterlockedIncrement((volatile signed __int32 *)this + 51);
    *((_DWORD *)v11 + 6) |= 1u;
    *((_QWORD *)v11 + 1) = this;
    *((_DWORD *)v11 + 4) = 4;
    *((_DWORD *)v11 + 5) = 56;
    *((_DWORD *)v11 + 7) = v7;
    if ( *((_BYTE *)this + 16) )
      *((_DWORD *)v11 + 9) = a4->ipv4.S_un.S_addr;
    else
      *(union tagRASTUNNELENDPOINT::$4A9C1D26ADB9873768D25EB8D6E43E7F *)(v11 + 36) = a4->4;
    v17 = (*(__int64 (__fastcall **)(struct ThreadPoolHelper *, __int64 (__fastcall *)(struct _TP_CALLBACK_INSTANCE *, _QWORD *, struct _TP_WORK *), char *, _QWORD))(*(_QWORD *)a3 + 16LL))(
            a3,
            VPNIKEClientConnection::DispatchUpdateConnection,
            v11,
            0);
    if ( v17 )
    {
      BaseConnection::DeleteRef(this);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v18 = *((_QWORD *)this + 14);
        LOWORD(v28) = 0;
        LOWORD(v24) = 0;
        if ( v18 && *(_QWORD *)(v18 + 16) )
          v19 = *(unsigned int *)(v18 + 16);
        else
          v19 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v24, v19);
        FormatRRASErrorString(&v28, L"ThreadPool->QueueWorkItem(DispatchUpdateConnection) failed: %!WINERROR!", v17);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v20 = *((_QWORD *)this + 14);
          LODWORD(v21) = v20 + 2120;
          if ( !v20 )
            v21 = &v23;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v28,
            (_DWORD)v21,
            (v20 + 2686) & -(__int64)(*((_QWORD *)this + 14) != 0),
            (__int64)&v24);
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids, v17);
      }
      BaseConnection::DeleteRef(this);
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v11);
    }
    goto LABEL_37;
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (byte_1800AA941 & 4) != 0 )
  {
    v13 = *((_QWORD *)this + 14);
    LOWORD(v28) = 0;
    LOWORD(v24) = 0;
    if ( v13 && *(_QWORD *)(v13 + 16) )
      v14 = *(unsigned int *)(v13 + 16);
    else
      v14 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v24, v14);
    FormatRRASErrorString(&v28, L"VPNIKE_MALLOC returned: %!WINERROR!", 8);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v15 = *((_QWORD *)this + 14);
      LODWORD(v16) = v15 + 2120;
      if ( !v15 )
        v16 = &v23;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceError,
        (unsigned int)&v28,
        (_DWORD)v16,
        (v15 + 2686) & -(__int64)(*((_QWORD *)this + 14) != 0),
        (__int64)&v24);
    }
LABEL_37:
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 6u )
    WPP_SF_(v12[2], 85, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
}

```

## disassembly

```asm
0x18001e0b0  mov     [rsp-8+arg_18], rbx
0x18001e0b5  push    rbp
0x18001e0b6  push    rsi
0x18001e0b7  push    rdi
0x18001e0b8  push    r14
0x18001e0ba  push    r15
0x18001e0bc  lea     rbp, [rsp-780h]
0x18001e0c4  sub     rsp, 880h
0x18001e0cb  mov     rax, cs:__security_cookie
0x18001e0d2  xor     rax, rsp
0x18001e0d5  mov     [rbp+7A0h+var_30], rax
0x18001e0dc  mov     rsi, r9
0x18001e0df  mov     r15, r8
0x18001e0e2  mov     r14d, edx
0x18001e0e5  mov     rbx, rcx
0x18001e0e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0ef  lea     rax, WPP_GLOBAL_Control
0x18001e0f6  cmp     rcx, rax
0x18001e0f9  jz      short loc_18001E124
0x18001e0fb  test    byte ptr [rcx+1Ch], 1
0x18001e0ff  jz      short loc_18001E124
0x18001e101  cmp     byte ptr [rcx+19h], 6
0x18001e105  jb      short loc_18001E124
0x18001e107  mov     al, [rbx+10h]
0x18001e10a  mov     r9d, edx
0x18001e10d  mov     rcx, [rcx+10h]
0x18001e111  mov     byte ptr [rsp+8A0h+var_878], al
0x18001e115  mov     eax, [rbp+7A0h+arg_20]
0x18001e11b  mov     dword ptr [rsp+8A0h+var_880], eax
0x18001e11f  call    WPP_SF_dDc
0x18001e124  xor     eax, eax
0x18001e126  lea     rcx, [rsp+8A0h+var_82C]; void *
0x18001e12b  xor     edx, edx; Val
0x18001e12d  mov     [rsp+8A0h+var_830], eax
0x18001e131  mov     r8d, 7FCh; Size
0x18001e137  call    memset_0
0x18001e13c  xorps   xmm0, xmm0
0x18001e13f  xor     eax, eax
0x18001e141  mov     [rsp+8A0h+var_860], eax
0x18001e145  movups  [rsp+8A0h+var_85C], xmm0
0x18001e14a  mov     [rsp+8A0h+var_83C], eax
0x18001e14e  movups  [rsp+8A0h+var_84C], xmm0
0x18001e153  movups  [rsp+8A0h+var_870], xmm0
0x18001e158  call    cs:__imp_GetProcessHeap
0x18001e15e  mov     edx, 8; dwFlags
0x18001e163  mov     rcx, rax; hHeap
0x18001e166  lea     r8d, [rdx+40h]; dwBytes
0x18001e16a  call    cs:__imp_HeapAlloc
0x18001e170  mov     rdi, rax
0x18001e173  test    rax, rax
0x18001e176  jnz     loc_18001E267
0x18001e17c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e183  lea     r14, WPP_GLOBAL_Control
0x18001e18a  cmp     rcx, r14
0x18001e18d  jz      short loc_18001E1B5
0x18001e18f  test    byte ptr [rcx+1Ch], 1
0x18001e193  jz      short loc_18001E1B5
0x18001e195  cmp     byte ptr [rcx+19h], 2
0x18001e199  jb      short loc_18001E1B5
0x18001e19b  mov     rcx, [rcx+10h]
0x18001e19f  lea     edx, [rax+53h]
0x18001e1a2  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001e1a9  call    WPP_SF_
0x18001e1ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e1b5  test    cs:byte_1800AA941, 4
0x18001e1bc  jz      loc_18001E3EF
0x18001e1c2  mov     rdx, [rbx+70h]
0x18001e1c6  xor     eax, eax
0x18001e1c8  mov     word ptr [rsp+8A0h+var_830], ax
0x18001e1cd  mov     word ptr [rsp+8A0h+var_860], ax
0x18001e1d2  test    rdx, rdx
0x18001e1d5  jz      short loc_18001E1E2
0x18001e1d7  cmp     [rdx+10h], rax
0x18001e1db  jz      short loc_18001E1E2
0x18001e1dd  mov     edx, [rdx+10h]
0x18001e1e0  jmp     short loc_18001E1E5
0x18001e1e2  or      edx, 0FFFFFFFFh
0x18001e1e5  lea     rcx, [rsp+8A0h+var_860]
0x18001e1ea  call    ConvertPortNoToString
0x18001e1ef  mov     r8d, 8
0x18001e1f5  lea     rdx, aVpnikeMallocRe; "VPNIKE_MALLOC returned: %!WINERROR!"
0x18001e1fc  lea     rcx, [rsp+8A0h+var_830]
0x18001e201  call    FormatRRASErrorString
0x18001e206  test    cs:byte_1800AA941, 4
0x18001e20d  jz      loc_18001E3E8
0x18001e213  mov     rdx, [rbx+70h]
0x18001e217  mov     rax, rdx
0x18001e21a  neg     rax
0x18001e21d  sbb     r8, r8
0x18001e220  lea     rcx, [rdx+0A7Eh]
0x18001e227  and     r8, rcx
0x18001e22a  lea     r9, [rdx+848h]
0x18001e231  test    rdx, rdx
0x18001e234  jnz     short loc_18001E23B
0x18001e236  lea     r9, [rsp+8A0h+var_870]
0x18001e23b  lea     rax, [rsp+8A0h+var_860]
0x18001e240  mov     [rsp+8A0h+var_878], rax
0x18001e245  lea     rdx, RasVpnIkeParamTraceError
0x18001e24c  mov     [rsp+8A0h+var_880], r8
0x18001e251  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001e258  lea     r8, [rsp+8A0h+var_830]
0x18001e25d  call    McTemplateU0zjzz_EventWriteTransfer
0x18001e262  jmp     loc_18001E3E8
0x18001e267  xor     edx, edx; Val
0x18001e269  mov     rcx, rdi; void *
0x18001e26c  lea     r8d, [rdx+48h]; Size
0x18001e270  call    memset_0
0x18001e275  mov     rax, [rbx+70h]
0x18001e279  mov     rcx, [rax+18h]
0x18001e27d  mov     [rdi], rcx
0x18001e280  lock inc dword ptr [rbx+0CCh]
0x18001e287  or      dword ptr [rdi+18h], 1
0x18001e28b  mov     [rdi+8], rbx
0x18001e28f  mov     dword ptr [rdi+10h], 4
0x18001e296  mov     dword ptr [rdi+14h], 38h ; '8'
0x18001e29d  mov     [rdi+1Ch], r14d
0x18001e2a1  cmp     byte ptr [rbx+10h], 0
0x18001e2a5  jz      short loc_18001E2AF
0x18001e2a7  mov     eax, [rsi+4]
0x18001e2aa  mov     [rdi+24h], eax
0x18001e2ad  jmp     short loc_18001E2B8
0x18001e2af  movups  xmm0, xmmword ptr [rsi+4]
0x18001e2b3  movdqu  xmmword ptr [rdi+24h], xmm0
0x18001e2b8  mov     rax, [r15]
0x18001e2bb  lea     rdx, ?DispatchUpdateConnection@VPNIKEClientConnection@@KAKPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; VPNIKEClientConnection::DispatchUpdateConnection(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x18001e2c2  xor     r9d, r9d
0x18001e2c5  mov     r8, rdi
0x18001e2c8  mov     rcx, r15
0x18001e2cb  mov     rax, [rax+10h]
0x18001e2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2d4  mov     esi, eax
0x18001e2d6  test    eax, eax
0x18001e2d8  jz      loc_18001E3E1
0x18001e2de  mov     rcx, rbx; this
0x18001e2e1  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x18001e2e6  test    cs:byte_1800AA941, 4
0x18001e2ed  jz      loc_18001E38C
0x18001e2f3  mov     rdx, [rbx+70h]
0x18001e2f7  xor     ecx, ecx
0x18001e2f9  mov     word ptr [rsp+8A0h+var_830], cx
0x18001e2fe  mov     word ptr [rsp+8A0h+var_860], cx
0x18001e303  test    rdx, rdx
0x18001e306  jz      short loc_18001E313
0x18001e308  cmp     [rdx+10h], rcx
0x18001e30c  jz      short loc_18001E313
0x18001e30e  mov     edx, [rdx+10h]
0x18001e311  jmp     short loc_18001E316
0x18001e313  or      edx, 0FFFFFFFFh
0x18001e316  lea     rcx, [rsp+8A0h+var_860]
0x18001e31b  call    ConvertPortNoToString
0x18001e320  mov     r8d, esi
0x18001e323  lea     rdx, aThreadpoolQueu_0; "ThreadPool->QueueWorkItem(DispatchUpdat"...
0x18001e32a  lea     rcx, [rsp+8A0h+var_830]
0x18001e32f  call    FormatRRASErrorString
0x18001e334  test    cs:byte_1800AA941, 4
0x18001e33b  jz      short loc_18001E38C
0x18001e33d  mov     rdx, [rbx+70h]
0x18001e341  mov     rax, rdx
0x18001e344  neg     rax
0x18001e347  sbb     r8, r8
0x18001e34a  lea     rcx, [rdx+0A7Eh]
0x18001e351  and     r8, rcx
0x18001e354  lea     r9, [rdx+848h]
0x18001e35b  test    rdx, rdx
0x18001e35e  jnz     short loc_18001E365
0x18001e360  lea     r9, [rsp+8A0h+var_870]
0x18001e365  lea     rax, [rsp+8A0h+var_860]
0x18001e36a  mov     [rsp+8A0h+var_878], rax
0x18001e36f  lea     rdx, RasVpnIkeParamTraceError
0x18001e376  mov     [rsp+8A0h+var_880], r8
0x18001e37b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001e382  lea     r8, [rsp+8A0h+var_830]
0x18001e387  call    McTemplateU0zjzz_EventWriteTransfer
0x18001e38c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e393  lea     r14, WPP_GLOBAL_Control
0x18001e39a  cmp     rcx, r14
0x18001e39d  jz      short loc_18001E3C3
0x18001e39f  test    byte ptr [rcx+1Ch], 1
0x18001e3a3  jz      short loc_18001E3C3
0x18001e3a5  cmp     byte ptr [rcx+19h], 2
0x18001e3a9  jb      short loc_18001E3C3
0x18001e3ab  mov     rcx, [rcx+10h]
0x18001e3af  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001e3b6  mov     edx, 54h ; 'T'
0x18001e3bb  mov     r9d, esi
0x18001e3be  call    WPP_SF_d
0x18001e3c3  mov     rcx, rbx; this
0x18001e3c6  call    ?DeleteRef@BaseConnection@@QEAAJXZ; BaseConnection::DeleteRef(void)
0x18001e3cb  call    cs:__imp_GetProcessHeap
0x18001e3d1  mov     r8, rdi; lpMem
0x18001e3d4  xor     edx, edx; dwFlags
0x18001e3d6  mov     rcx, rax; hHeap
0x18001e3d9  call    cs:__imp_HeapFree
0x18001e3df  jmp     short loc_18001E3E8
0x18001e3e1  lea     r14, WPP_GLOBAL_Control
0x18001e3e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3ef  cmp     rcx, r14
0x18001e3f2  jz      short loc_18001E415
0x18001e3f4  test    byte ptr [rcx+1Ch], 1
0x18001e3f8  jz      short loc_18001E415
0x18001e3fa  cmp     byte ptr [rcx+19h], 6
0x18001e3fe  jb      short loc_18001E415
0x18001e400  mov     rcx, [rcx+10h]
0x18001e404  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001e40b  mov     edx, 55h ; 'U'
0x18001e410  call    WPP_SF_
0x18001e415  mov     rcx, [rbp+7A0h+var_30]
0x18001e41c  xor     rcx, rsp; StackCookie
0x18001e41f  call    __security_check_cookie
0x18001e424  mov     rbx, [rsp+8A0h+arg_18]
0x18001e42c  add     rsp, 880h
0x18001e433  pop     r15
0x18001e435  pop     r14
0x18001e437  pop     rdi
0x18001e438  pop     rsi
0x18001e439  pop     rbp
0x18001e43a  retn
```
