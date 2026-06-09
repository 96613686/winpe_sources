# ClientBFEHandler::DeletePolicy(void)

- ea: `0x180031788`
- end: `0x180031b3c`
- name: `?DeletePolicy@ClientBFEHandler@@QEAAKXZ`
- size: `948`
- prototype: `__int64 __fastcall(void **this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800177a0`
- `0x18001bd20`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18002e6f4`
- `0x180031788`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x1800319a7`
- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x1800319a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031ac6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031ac6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031ab8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031ab8`

## string_xrefs

- `0x18003185d`: `ClientBFEHandler::DeletePolicy`
- `0x180031a32`: `FwpmIPsecTunnelDeleteByKey failed: %d`

## pseudocode

```c
__int64 __fastcall ClientBFEHandler::DeletePolicy(void **this)
{
  unsigned int v2; // r15d
  unsigned int BfeHandle; // eax
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  _QWORD *v6; // rax
  __int64 v7; // rax
  char *v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rcx
  __int128 *v11; // r9
  char *v12; // rsi
  DWORD v13; // ebx
  _QWORD *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  char *v17; // rcx
  _QWORD *v18; // rax
  __int64 v19; // rcx
  __int128 *v20; // r9
  HANDLE ProcessHeap; // rax
  HANDLE engineHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v25; // [rsp+40h] [rbp-C0h]
  __int128 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+68h] [rbp-98h]
  int v29; // [rsp+6Ch] [rbp-94h]
  __int128 v30; // [rsp+70h] [rbp-90h] BYREF
  int v31; // [rsp+80h] [rbp-80h] BYREF
  __int128 v32; // [rsp+84h] [rbp-7Ch]
  __int128 v33; // [rsp+94h] [rbp-6Ch]
  int v34; // [rsp+A4h] [rbp-5Ch]
  int v35; // [rsp+B0h] [rbp-50h] BYREF
  char v36[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
  }
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v30 = 0;
  v25 = 0;
  v24 = 0;
  v26 = 0;
  v27 = 0;
  v2 = -1;
  v28 = -1;
  v29 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v24,
      L"ClientBFEHandler::DeletePolicy",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithConnObj,
      this[6]);
  engineHandle = 0;
  BfeHandle = BFEHandler::GetBfeHandle(&engineHandle);
  v4 = BfeHandle;
  if ( engineHandle )
  {
    while ( 1 )
    {
      v12 = (char *)this[7];
      if ( !v12 )
        goto LABEL_52;
      v13 = FwpmIPsecTunnelDeleteByKey0(engineHandle, (const GUID *)(v12 + 44));
      if ( v13 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v13);
        }
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v35) = 0;
          LOWORD(v31) = 0;
          v14 = this[6];
          if ( v14 && (v15 = v14[14]) != 0 && *(_QWORD *)(v15 + 16) )
            v16 = *(unsigned int *)(v15 + 16);
          else
            v16 = 0xFFFFFFFFLL;
          ConvertPortNoToString(&v31, v16);
          FormatRRASErrorString(&v35, L"FwpmIPsecTunnelDeleteByKey failed: %d", v13);
          if ( (byte_1800AA941 & 4) != 0 )
            break;
        }
      }
LABEL_51:
      this[7] = *(void **)this[7];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
    }
    v17 = (char *)this[6];
    v18 = v17 + 112;
    if ( v17 )
    {
      if ( *v18 )
        v19 = *v18 + 2686LL;
      else
        v19 = 0;
      if ( *v18 )
      {
        v20 = (__int128 *)(*v18 + 2120LL);
LABEL_50:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v35,
          (_DWORD)v20,
          v19,
          (__int64)&v31);
        goto LABEL_51;
      }
    }
    else
    {
      v19 = 0;
    }
    v20 = &v30;
    goto LABEL_50;
  }
  if ( !BfeHandle )
  {
LABEL_13:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_14;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, BfeHandle);
    goto LABEL_13;
  }
LABEL_14:
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v35) = 0;
    LOWORD(v31) = 0;
    v6 = this[6];
    if ( v6 )
    {
      v7 = v6[14];
      if ( v7 )
      {
        if ( *(_QWORD *)(v7 + 16) )
          v2 = *(_DWORD *)(v7 + 16);
      }
    }
    ConvertPortNoToString(&v31, v2);
    FormatRRASErrorString(&v35, L"GetBfeHandle failed: %d", v4);
    if ( (byte_1800AA941 & 4) == 0 )
      goto LABEL_52;
    v8 = (char *)this[6];
    v9 = v8 + 112;
    if ( v8 )
    {
      if ( *v9 )
        v10 = *v9 + 2686LL;
      else
        v10 = 0;
      if ( *v9 )
      {
        v11 = (__int128 *)(*v9 + 2120LL);
LABEL_28:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)&v35,
          (_DWORD)v11,
          v10,
          (__int64)&v31);
LABEL_52:
        v5 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_53;
      }
    }
    else
    {
      v10 = 0;
    }
    v11 = &v30;
    goto LABEL_28;
  }
LABEL_53:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 163, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, 0);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v24);
  return 0;
}

```

## disassembly

```asm
0x180031788  mov     [rsp-8+arg_8], rbx
0x18003178d  mov     [rsp-8+arg_10], rsi
0x180031792  push    rbp
0x180031793  push    rdi
0x180031794  push    r15
0x180031796  lea     rbp, [rsp-7C0h]
0x18003179e  sub     rsp, 8C0h
0x1800317a5  mov     rax, cs:__security_cookie
0x1800317ac  xor     rax, rsp
0x1800317af  mov     [rbp+7D0h+var_20], rax
0x1800317b6  mov     rdi, rcx
0x1800317b9  lea     rsi, WPP_GLOBAL_Control
0x1800317c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800317c7  cmp     rcx, rsi
0x1800317ca  jz      short loc_1800317ED
0x1800317cc  test    byte ptr [rcx+1Ch], 1
0x1800317d0  jz      short loc_1800317ED
0x1800317d2  cmp     byte ptr [rcx+19h], 6
0x1800317d6  jb      short loc_1800317ED
0x1800317d8  mov     edx, 0A0h
0x1800317dd  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x1800317e4  mov     rcx, [rcx+10h]
0x1800317e8  call    WPP_SF_
0x1800317ed  xor     eax, eax
0x1800317ef  mov     [rbp+7D0h+var_820], eax
0x1800317f2  xor     edx, edx; Val
0x1800317f4  mov     r8d, 7FCh; Size
0x1800317fa  lea     rcx, [rbp+7D0h+var_81C]; void *
0x1800317fe  call    memset_0
0x180031803  xor     eax, eax
0x180031805  mov     [rbp+7D0h+var_850], eax
0x180031808  xorps   xmm0, xmm0
0x18003180b  movups  [rbp+7D0h+var_84C], xmm0
0x18003180f  movups  [rbp+7D0h+var_83C], xmm0
0x180031813  mov     [rbp+7D0h+var_82C], eax
0x180031816  movups  [rsp+8D0h+var_860], xmm0
0x18003181b  xorps   xmm1, xmm1
0x18003181e  movdqu  [rsp+8D0h+var_890], xmm1
0x180031824  mov     [rsp+8D0h+var_898], rax
0x180031829  movdqu  [rsp+8D0h+var_880], xmm0
0x18003182f  mov     [rsp+8D0h+var_870], rax
0x180031834  or      r15d, 0FFFFFFFFh
0x180031838  mov     [rsp+8D0h+var_868], r15d
0x18003183d  mov     [rsp+8D0h+var_864], eax
0x180031841  test    cs:byte_1800AA941, 8
0x180031848  jz      short loc_18003186E
0x18003184a  mov     rax, [rdi+30h]
0x18003184e  mov     [rsp+8D0h+var_8B0], rax; void *
0x180031853  lea     r9, ?RasVpnIkeTraceFunctionWithConnObj@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18003185a  xor     r8d, r8d; unsigned int *
0x18003185d  lea     rdx, aClientbfehandl_5; "ClientBFEHandler::DeletePolicy"
0x180031864  lea     rcx, [rsp+8D0h+var_898]; this
0x180031869  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18003186e  mov     [rsp+8D0h+engineHandle], 0
0x180031877  lea     rcx, [rsp+8D0h+engineHandle]; void **
0x18003187c  call    ?GetBfeHandle@BFEHandler@@SAKPEAPEAX@Z; BFEHandler::GetBfeHandle(void * *)
0x180031881  mov     ebx, eax
0x180031883  cmp     [rsp+8D0h+engineHandle], 0
0x180031889  jnz     loc_180031991
0x18003188f  test    eax, eax
0x180031891  jz      short loc_1800318C3
0x180031893  mov     rcx, cs:WPP_GLOBAL_Control
0x18003189a  cmp     rcx, rsi
0x18003189d  jz      short loc_1800318CA
0x18003189f  test    byte ptr [rcx+1Ch], 1
0x1800318a3  jz      short loc_1800318CA
0x1800318a5  cmp     byte ptr [rcx+19h], 2
0x1800318a9  jb      short loc_1800318CA
0x1800318ab  mov     edx, 0A1h
0x1800318b0  mov     r9d, eax
0x1800318b3  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x1800318ba  mov     rcx, [rcx+10h]
0x1800318be  call    WPP_SF_d
0x1800318c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800318ca  test    cs:byte_1800AA941, 4
0x1800318d1  jz      loc_180031ADF
0x1800318d7  xor     eax, eax
0x1800318d9  mov     word ptr [rbp+7D0h+var_820], ax
0x1800318dd  mov     word ptr [rbp+7D0h+var_850], ax
0x1800318e1  mov     rax, [rdi+30h]
0x1800318e5  test    rax, rax
0x1800318e8  jz      short loc_1800318FE
0x1800318ea  mov     rax, [rax+70h]
0x1800318ee  test    rax, rax
0x1800318f1  jz      short loc_1800318FE
0x1800318f3  cmp     qword ptr [rax+10h], 0
0x1800318f8  jz      short loc_1800318FE
0x1800318fa  mov     r15d, [rax+10h]
0x1800318fe  mov     edx, r15d
0x180031901  lea     rcx, [rbp+7D0h+var_850]
0x180031905  call    ConvertPortNoToString
0x18003190a  mov     r8d, ebx
0x18003190d  lea     rdx, aGetbfehandleFa; "GetBfeHandle failed: %d"
0x180031914  lea     rcx, [rbp+7D0h+var_820]
0x180031918  call    FormatRRASErrorString
0x18003191d  test    cs:byte_1800AA941, 4
0x180031924  jz      loc_180031AD8
0x18003192a  mov     rcx, [rdi+30h]
0x18003192e  lea     rax, [rcx+70h]
0x180031932  test    rcx, rcx
0x180031935  jz      short loc_180031960
0x180031937  mov     rdx, [rax]
0x18003193a  test    rdx, rdx
0x18003193d  jz      short loc_180031948
0x18003193f  lea     rcx, [rdx+0A7Eh]
0x180031946  jmp     short loc_18003194F
0x180031948  test    rcx, rcx
0x18003194b  jz      short loc_180031960
0x18003194d  xor     ecx, ecx
0x18003194f  mov     rdx, [rax]
0x180031952  test    rdx, rdx
0x180031955  jz      short loc_180031962
0x180031957  lea     r9, [rdx+848h]
0x18003195e  jmp     short loc_180031967
0x180031960  xor     ecx, ecx
0x180031962  lea     r9, [rsp+8D0h+var_860]
0x180031967  lea     rax, [rbp+7D0h+var_850]
0x18003196b  mov     [rsp+8D0h+var_8A8], rax
0x180031970  mov     [rsp+8D0h+var_8B0], rcx
0x180031975  lea     r8, [rbp+7D0h+var_820]
0x180031979  lea     rdx, RasVpnIkeParamTraceError
0x180031980  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180031987  call    McTemplateU0zjzz_EventWriteTransfer
0x18003198c  jmp     loc_180031AD8
0x180031991  mov     rsi, [rdi+38h]
0x180031995  test    rsi, rsi
0x180031998  jz      loc_180031AD1
0x18003199e  lea     rdx, [rsi+2Ch]; key
0x1800319a2  mov     rcx, [rsp+8D0h+engineHandle]; engineHandle
0x1800319a7  call    cs:__imp_FwpmIPsecTunnelDeleteByKey0
0x1800319ad  mov     ebx, eax
0x1800319af  test    eax, eax
0x1800319b1  jz      loc_180031AAD
0x1800319b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319be  lea     rax, WPP_GLOBAL_Control
0x1800319c5  cmp     rcx, rax
0x1800319c8  jz      short loc_1800319EE
0x1800319ca  test    byte ptr [rcx+1Ch], 1
0x1800319ce  jz      short loc_1800319EE
0x1800319d0  cmp     byte ptr [rcx+19h], 2
0x1800319d4  jb      short loc_1800319EE
0x1800319d6  mov     edx, 0A2h
0x1800319db  mov     r9d, ebx
0x1800319de  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x1800319e5  mov     rcx, [rcx+10h]
0x1800319e9  call    WPP_SF_d
0x1800319ee  test    cs:byte_1800AA941, 4
0x1800319f5  jz      loc_180031AAD
0x1800319fb  xor     eax, eax
0x1800319fd  mov     word ptr [rbp+7D0h+var_820], ax
0x180031a01  mov     word ptr [rbp+7D0h+var_850], ax
0x180031a05  mov     rax, [rdi+30h]
0x180031a09  test    rax, rax
0x180031a0c  jz      short loc_180031A23
0x180031a0e  mov     rax, [rax+70h]
0x180031a12  test    rax, rax
0x180031a15  jz      short loc_180031A23
0x180031a17  cmp     qword ptr [rax+10h], 0
0x180031a1c  jz      short loc_180031A23
0x180031a1e  mov     edx, [rax+10h]
0x180031a21  jmp     short loc_180031A26
0x180031a23  mov     edx, r15d
0x180031a26  lea     rcx, [rbp+7D0h+var_850]
0x180031a2a  call    ConvertPortNoToString
0x180031a2f  mov     r8d, ebx
0x180031a32  lea     rdx, aFwpmipsectunne_0; "FwpmIPsecTunnelDeleteByKey failed: %d"
0x180031a39  lea     rcx, [rbp+7D0h+var_820]
0x180031a3d  call    FormatRRASErrorString
0x180031a42  test    cs:byte_1800AA941, 4
0x180031a49  jz      short loc_180031AAD
0x180031a4b  mov     rcx, [rdi+30h]
0x180031a4f  lea     rax, [rcx+70h]
0x180031a53  test    rcx, rcx
0x180031a56  jz      short loc_180031A81
0x180031a58  mov     rdx, [rax]
0x180031a5b  test    rdx, rdx
0x180031a5e  jz      short loc_180031A69
0x180031a60  lea     rcx, [rdx+0A7Eh]
0x180031a67  jmp     short loc_180031A70
0x180031a69  test    rcx, rcx
0x180031a6c  jz      short loc_180031A81
0x180031a6e  xor     ecx, ecx
0x180031a70  mov     rdx, [rax]
0x180031a73  test    rdx, rdx
0x180031a76  jz      short loc_180031A83
0x180031a78  lea     r9, [rdx+848h]
0x180031a7f  jmp     short loc_180031A88
0x180031a81  xor     ecx, ecx
0x180031a83  lea     r9, [rsp+8D0h+var_860]
0x180031a88  lea     rax, [rbp+7D0h+var_850]
0x180031a8c  mov     [rsp+8D0h+var_8A8], rax
0x180031a91  mov     [rsp+8D0h+var_8B0], rcx
0x180031a96  lea     r8, [rbp+7D0h+var_820]
0x180031a9a  lea     rdx, RasVpnIkeParamTraceError
0x180031aa1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180031aa8  call    McTemplateU0zjzz_EventWriteTransfer
0x180031aad  mov     rax, [rdi+38h]
0x180031ab1  mov     rcx, [rax]
0x180031ab4  mov     [rdi+38h], rcx
0x180031ab8  call    cs:__imp_GetProcessHeap
0x180031abe  mov     rcx, rax; hHeap
0x180031ac1  mov     r8, rsi; lpMem
0x180031ac4  xor     edx, edx; dwFlags
0x180031ac6  call    cs:__imp_HeapFree
0x180031acc  jmp     loc_180031991
0x180031ad1  lea     rsi, WPP_GLOBAL_Control
0x180031ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x180031adf  cmp     rcx, rsi
0x180031ae2  jz      short loc_180031B09
0x180031ae4  test    byte ptr [rcx+1Ch], 1
0x180031ae8  jz      short loc_180031B09
0x180031aea  cmp     byte ptr [rcx+19h], 6
0x180031aee  jb      short loc_180031B09
0x180031af0  mov     edx, 0A3h
0x180031af5  xor     r9d, r9d
0x180031af8  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180031aff  mov     rcx, [rcx+10h]
0x180031b03  call    WPP_SF_d
0x180031b08  nop
0x180031b09  lea     rcx, [rsp+8D0h+var_898]; this
0x180031b0e  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180031b13  xor     eax, eax
0x180031b15  mov     rcx, [rbp+7D0h+var_20]
0x180031b1c  xor     rcx, rsp; StackCookie
0x180031b1f  call    __security_check_cookie
0x180031b24  lea     r11, [rsp+8D0h+var_10]
0x180031b2c  mov     rbx, [r11+28h]
0x180031b30  mov     rsi, [r11+30h]
0x180031b34  mov     rsp, r11
0x180031b37  pop     r15
0x180031b39  pop     rdi
0x180031b3a  pop     rbp
0x180031b3b  retn
```
