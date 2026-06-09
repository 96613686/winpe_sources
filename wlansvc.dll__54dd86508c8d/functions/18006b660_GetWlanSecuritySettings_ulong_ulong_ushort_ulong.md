# GetWlanSecuritySettings(ulong,ulong *,ushort * *,ulong *)

- ea: `0x18006b660`
- end: `0x18006bac5`
- name: `?GetWlanSecuritySettings@@YAKKPEAKPEAPEAG0@Z`
- size: `1125`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006b4b0`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18006b660`
- `0x1800c6774`
- `0x180107318`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b84c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b84c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b864`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b864`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b93b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ba93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b93b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ba93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b8c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b8c3`
- `MobileNetworking!GetSDDetailsFromObjectID` at `0x18006b6e3`
- `MobileNetworking!GetSDDetailsFromObjectID` at `0x18006b6e3`
- `MobileNetworking!FreeSecurityDescriptor` at `0x18006b8aa`
- `MobileNetworking!FreeSecurityDescriptor` at `0x18006b8aa`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x18006b737`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x18006b796`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x18006b7f1`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x18006b737`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x18006b796`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x18006b7f1`

## pseudocode

```c
__int64 __fastcall GetWlanSecuritySettings(unsigned int a1, unsigned int *a2, unsigned __int16 **a3, unsigned int *a4)
{
  PVOID v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned int SDDetailsFromObjectID; // ebx
  __int64 v12; // r8
  __int64 v13; // rbx
  unsigned int v14; // eax
  PVOID *v15; // rcx
  __int64 v16; // rbx
  unsigned int v17; // eax
  __int64 v18; // rbx
  unsigned int v19; // eax
  unsigned __int16 *v20; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v23; // [rsp+70h] [rbp+40h] BYREF
  void *Src; // [rsp+78h] [rbp+48h] BYREF

  v23 = 0;
  Src = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 29, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids);
  }
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, a2, a3);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, a2, a3);
  *a4 = 0;
  if ( a1 >= 0x11 )
  {
    SDDetailsFromObjectID = 87;
    goto LABEL_47;
  }
  SDDetailsFromObjectID = GetSDDetailsFromObjectID(a1, a2, &v23, &Src);
  if ( SDDetailsFromObjectID )
  {
LABEL_47:
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_48;
  }
  if ( !v23 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v12);
  if ( !Src )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v12);
  MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v12);
  v13 = v23;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids);
  }
  v14 = VerifyRpcClientAccessToSecurityDescriptor(v13, 131073);
  SDDetailsFromObjectID = 0;
  if ( v14 != 5 )
    SDDetailsFromObjectID = v14;
  if ( !SDDetailsFromObjectID && v14 != 5 )
    *a4 |= 0x20001u;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      28,
      WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids,
      SDDetailsFromObjectID);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !SDDetailsFromObjectID )
  {
    v16 = v23;
    if ( v15 != &WPP_GLOBAL_Control && *((_BYTE *)v15 + 105) >= 4u && (*((_BYTE *)v15 + 108) & 1) != 0 )
      WPP_SF_(v15[12], 27, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids);
    v17 = VerifyRpcClientAccessToSecurityDescriptor(v16, 131105);
    SDDetailsFromObjectID = 0;
    if ( v17 != 5 )
      SDDetailsFromObjectID = v17;
    if ( !SDDetailsFromObjectID && v17 != 5 )
      *a4 |= 0x20021u;
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        28,
        WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids,
        SDDetailsFromObjectID);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !SDDetailsFromObjectID )
    {
      v18 = v23;
      if ( v15 != &WPP_GLOBAL_Control && *((_BYTE *)v15 + 105) >= 4u && (*((_BYTE *)v15 + 108) & 1) != 0 )
        WPP_SF_(v15[12], 27, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids);
      v19 = VerifyRpcClientAccessToSecurityDescriptor(v18, 458787);
      SDDetailsFromObjectID = 0;
      if ( v19 != 5 )
        SDDetailsFromObjectID = v19;
      if ( !SDDetailsFromObjectID && v19 != 5 )
        *a4 |= 0x70023u;
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          28,
          WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids,
          SDDetailsFromObjectID);
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !SDDetailsFromObjectID )
      {
        v20 = 0;
        ProcessHeap = GetProcessHeap();
        if ( ProcessHeap )
        {
          v20 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2u);
          if ( !v20 )
            SetLastError(8u);
        }
        *a3 = v20;
        if ( v20 )
          memcpy_0(v20, Src, sizeof(unsigned __int16));
        else
          SDDetailsFromObjectID = 14;
        goto LABEL_47;
      }
    }
  }
LABEL_48:
  if ( v23 )
  {
    FreeSecurityDescriptor(&v23);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( Src )
  {
    LocalFree(Src);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && *((_BYTE *)v15 + 105) >= 4u && (*((_BYTE *)v15 + 108) & 1) != 0 )
    WPP_SF_d(v15[12], 30, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids, SDDetailsFromObjectID);
  return SDDetailsFromObjectID;
}

```

## disassembly

```asm
0x18006b660  mov     [rsp-28h+arg_8], rbx
0x18006b665  push    rbp
0x18006b666  push    rsi
0x18006b667  push    rdi
0x18006b668  push    r12
0x18006b66a  push    r14
0x18006b66c  mov     rbp, rsp
0x18006b66f  sub     rsp, 30h
0x18006b673  mov     rdi, r9
0x18006b676  mov     [rbp+arg_0], 0
0x18006b67d  mov     r14, r8
0x18006b680  mov     [rbp+arg_10], 0
0x18006b688  mov     rsi, rdx
0x18006b68b  mov     [rbp+Src], 0
0x18006b693  mov     ebx, ecx
0x18006b695  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b69c  lea     r12, WPP_GLOBAL_Control
0x18006b6a3  cmp     rcx, r12
0x18006b6a6  jnz     loc_18006B8F2
0x18006b6ac  test    r14, r14
0x18006b6af  jz      loc_18006B952
0x18006b6b5  test    rdi, rdi
0x18006b6b8  jz      loc_18006B95C
0x18006b6be  mov     dword ptr [rdi], 0
0x18006b6c4  cmp     ebx, 11h
0x18006b6c7  jnb     loc_18006B920
0x18006b6cd  lea     rax, [rbp+arg_0]
0x18006b6d1  mov     rdx, rsi
0x18006b6d4  lea     r9, [rbp+Src]
0x18006b6d8  mov     [rsp+30h+var_10], rax
0x18006b6dd  lea     r8, [rbp+arg_10]
0x18006b6e1  mov     ecx, ebx
0x18006b6e3  call    cs:__imp_GetSDDetailsFromObjectID
0x18006b6e9  mov     ebx, eax
0x18006b6eb  test    eax, eax
0x18006b6ed  jnz     loc_18006B898
0x18006b6f3  cmp     [rbp+arg_10], 0
0x18006b6f8  jz      loc_18006B966
0x18006b6fe  cmp     [rbp+Src], 0
0x18006b703  jz      loc_18006B970
0x18006b709  cmp     [rbp+arg_0], 0
0x18006b70d  jz      loc_18006B97A
0x18006b713  mov     rbx, [rbp+arg_10]
0x18006b717  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b71e  cmp     rcx, r12
0x18006b721  jz      short loc_18006B72D
0x18006b723  cmp     byte ptr [rcx+69h], 4
0x18006b727  jnb     loc_18006B984
0x18006b72d  mov     esi, 20001h
0x18006b732  mov     rcx, rbx
0x18006b735  mov     edx, esi
0x18006b737  call    cs:__imp_VerifyRpcClientAccessToSecurityDescriptor
0x18006b73d  xor     ebx, ebx
0x18006b73f  lea     r12d, [rbx+5]
0x18006b743  cmp     eax, r12d
0x18006b746  cmovnz  ebx, eax
0x18006b749  test    ebx, ebx
0x18006b74b  jnz     short loc_18006B754
0x18006b74d  cmp     eax, r12d
0x18006b750  jz      short loc_18006B754
0x18006b752  or      [rdi], esi
0x18006b754  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b75b  lea     rsi, WPP_GLOBAL_Control
0x18006b762  cmp     rcx, rsi
0x18006b765  jz      short loc_18006B771
0x18006b767  cmp     byte ptr [rcx+69h], 4
0x18006b76b  jnb     loc_18006B9A8
0x18006b771  test    ebx, ebx
0x18006b773  jnz     loc_18006B92A
0x18006b779  mov     rbx, [rbp+arg_10]
0x18006b77d  cmp     rcx, rsi
0x18006b780  jz      short loc_18006B78C
0x18006b782  cmp     byte ptr [rcx+69h], 4
0x18006b786  jnb     loc_18006B9D6
0x18006b78c  mov     esi, 20021h
0x18006b791  mov     rcx, rbx
0x18006b794  mov     edx, esi
0x18006b796  call    cs:__imp_VerifyRpcClientAccessToSecurityDescriptor
0x18006b79c  xor     ebx, ebx
0x18006b79e  cmp     eax, r12d
0x18006b7a1  cmovnz  ebx, eax
0x18006b7a4  test    ebx, ebx
0x18006b7a6  jnz     short loc_18006B7AF
0x18006b7a8  cmp     eax, r12d
0x18006b7ab  jz      short loc_18006B7AF
0x18006b7ad  or      [rdi], esi
0x18006b7af  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b7b6  lea     rax, WPP_GLOBAL_Control
0x18006b7bd  cmp     rcx, rax
0x18006b7c0  jz      short loc_18006B7CC
0x18006b7c2  cmp     byte ptr [rcx+69h], 4
0x18006b7c6  jnb     loc_18006B9FA
0x18006b7cc  test    ebx, ebx
0x18006b7ce  jnz     loc_18006B92A
0x18006b7d4  mov     rbx, [rbp+arg_10]
0x18006b7d8  cmp     rcx, rax
0x18006b7db  jz      short loc_18006B7E7
0x18006b7dd  cmp     byte ptr [rcx+69h], 4
0x18006b7e1  jnb     loc_18006BA2F
0x18006b7e7  mov     esi, 70023h
0x18006b7ec  mov     rcx, rbx
0x18006b7ef  mov     edx, esi
0x18006b7f1  call    cs:__imp_VerifyRpcClientAccessToSecurityDescriptor
0x18006b7f7  xor     ebx, ebx
0x18006b7f9  cmp     eax, r12d
0x18006b7fc  cmovnz  ebx, eax
0x18006b7ff  test    ebx, ebx
0x18006b801  jnz     short loc_18006B80A
0x18006b803  cmp     eax, r12d
0x18006b806  jz      short loc_18006B80A
0x18006b808  or      [rdi], esi
0x18006b80a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b811  lea     r12, WPP_GLOBAL_Control
0x18006b818  cmp     rcx, r12
0x18006b81b  jz      short loc_18006B827
0x18006b81d  cmp     byte ptr [rcx+69h], 4
0x18006b821  jnb     loc_18006BA53
0x18006b827  test    ebx, ebx
0x18006b829  jnz     short loc_18006B89F
0x18006b82b  mov     eax, [rbp+arg_0]
0x18006b82e  cmp     eax, 7D0h
0x18006b833  ja      loc_18006BA81
0x18006b839  lea     eax, ds:2[rax*2]
0x18006b840  mov     esi, eax
0x18006b842  test    eax, eax
0x18006b844  jz      loc_18006B936
0x18006b84a  xor     edi, edi
0x18006b84c  call    cs:__imp_GetProcessHeap
0x18006b852  test    rax, rax
0x18006b855  jz      short loc_18006B87D
0x18006b857  lea     r12d, [rbx+8]
0x18006b85b  mov     r8d, esi; dwBytes
0x18006b85e  mov     edx, r12d; dwFlags
0x18006b861  mov     rcx, rax; hHeap
0x18006b864  call    cs:__imp_HeapAlloc
0x18006b86a  mov     rdi, rax
0x18006b86d  test    rax, rax
0x18006b870  jz      loc_18006BA90
0x18006b876  lea     r12, WPP_GLOBAL_Control
0x18006b87d  mov     [r14], rdi
0x18006b880  test    rdi, rdi
0x18006b883  jz      loc_18006B948
0x18006b889  mov     rdx, [rbp+Src]; Src
0x18006b88d  mov     r8, rsi; Size
0x18006b890  mov     rcx, rdi; void *
0x18006b893  call    memcpy_0
0x18006b898  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b89f  cmp     [rbp+arg_10], 0
0x18006b8a4  jz      short loc_18006B8B7
0x18006b8a6  lea     rcx, [rbp+arg_10]
0x18006b8aa  call    cs:__imp_FreeSecurityDescriptor
0x18006b8b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b8b7  mov     rax, [rbp+Src]
0x18006b8bb  test    rax, rax
0x18006b8be  jz      short loc_18006B8D0
0x18006b8c0  mov     rcx, rax; hMem
0x18006b8c3  call    cs:__imp_LocalFree
0x18006b8c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b8d0  cmp     rcx, r12
0x18006b8d3  jz      short loc_18006B8DF
0x18006b8d5  cmp     byte ptr [rcx+69h], 4
0x18006b8d9  jnb     loc_18006BA9E
0x18006b8df  mov     eax, ebx
0x18006b8e1  mov     rbx, [rsp+30h+arg_8]
0x18006b8e6  add     rsp, 30h
0x18006b8ea  pop     r14
0x18006b8ec  pop     r12
0x18006b8ee  pop     rdi
0x18006b8ef  pop     rsi
0x18006b8f0  pop     rbp
0x18006b8f1  retn
0x18006b8f2  cmp     byte ptr [rcx+69h], 4
0x18006b8f6  jb      loc_18006B6AC
0x18006b8fc  test    byte ptr [rcx+6Ch], 1
0x18006b900  jz      loc_18006B6AC
0x18006b906  mov     rcx, [rcx+60h]
0x18006b90a  lea     r8, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids
0x18006b911  mov     edx, 1Dh
0x18006b916  call    WPP_SF_
0x18006b91b  jmp     loc_18006B6AC
0x18006b920  mov     ebx, 57h ; 'W'
0x18006b925  jmp     loc_18006B898
0x18006b92a  lea     r12, WPP_GLOBAL_Control
0x18006b931  jmp     loc_18006B89F
0x18006b936  mov     ecx, 57h ; 'W'; dwErrCode
0x18006b93b  call    cs:__imp_SetLastError
0x18006b941  mov     qword ptr [r14], 0
0x18006b948  mov     ebx, 0Eh
0x18006b94d  jmp     loc_18006B898
0x18006b952  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "ppszCurrentSDDL")
0x18006b957  jmp     loc_18006B6B5
0x18006b95c  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pdwGrantedAccess")
0x18006b961  jmp     loc_18006B6BE
0x18006b966  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pSecDesc")
0x18006b96b  jmp     loc_18006B6FE
0x18006b970  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pszSDDL")
0x18006b975  jmp     loc_18006B709
0x18006b97a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "dwStringLen")
0x18006b97f  jmp     loc_18006B713
0x18006b984  test    byte ptr [rcx+6Ch], 1
0x18006b988  jz      loc_18006B72D
0x18006b98e  mov     rcx, [rcx+60h]
0x18006b992  lea     r8, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids
0x18006b999  mov     edx, 1Bh
0x18006b99e  call    WPP_SF_
0x18006b9a3  jmp     loc_18006B72D
0x18006b9a8  test    byte ptr [rcx+6Ch], 1
0x18006b9ac  jz      loc_18006B771
0x18006b9b2  mov     rcx, [rcx+60h]
0x18006b9b6  lea     r8, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids
0x18006b9bd  mov     edx, 1Ch
0x18006b9c2  mov     r9d, ebx
0x18006b9c5  call    WPP_SF_d
0x18006b9ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b9d1  jmp     loc_18006B771
0x18006b9d6  test    byte ptr [rcx+6Ch], 1
0x18006b9da  jz      loc_18006B78C
0x18006b9e0  mov     rcx, [rcx+60h]
0x18006b9e4  lea     r8, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids
0x18006b9eb  mov     edx, 1Bh
0x18006b9f0  call    WPP_SF_
0x18006b9f5  jmp     loc_18006B78C
0x18006b9fa  test    byte ptr [rcx+6Ch], 1
0x18006b9fe  jz      loc_18006B7CC
0x18006ba04  mov     rcx, [rcx+60h]
0x18006ba08  lea     r8, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids
0x18006ba0f  mov     edx, 1Ch
0x18006ba14  mov     r9d, ebx
0x18006ba17  call    WPP_SF_d
0x18006ba1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ba23  lea     rax, WPP_GLOBAL_Control
0x18006ba2a  jmp     loc_18006B7CC
0x18006ba2f  test    byte ptr [rcx+6Ch], 1
0x18006ba33  jz      loc_18006B7E7
0x18006ba39  mov     rcx, [rcx+60h]
0x18006ba3d  lea     r8, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids
0x18006ba44  mov     edx, 1Bh
0x18006ba49  call    WPP_SF_
0x18006ba4e  jmp     loc_18006B7E7
0x18006ba53  test    byte ptr [rcx+6Ch], 1
0x18006ba57  jz      loc_18006B827
0x18006ba5d  mov     rcx, [rcx+60h]
0x18006ba61  lea     r8, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids
0x18006ba68  mov     edx, 1Ch
0x18006ba6d  mov     r9d, ebx
0x18006ba70  call    WPP_SF_d
0x18006ba75  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ba7c  jmp     loc_18006B827
0x18006ba81  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "0")
0x18006ba86  mov     ebx, 139Fh
0x18006ba8b  jmp     loc_18006B898
0x18006ba90  mov     ecx, r12d; dwErrCode
0x18006ba93  call    cs:__imp_SetLastError
0x18006ba99  jmp     loc_18006B876
0x18006ba9e  test    byte ptr [rcx+6Ch], 1
0x18006baa2  jz      loc_18006B8DF
0x18006baa8  mov     rcx, [rcx+60h]
0x18006baac  lea     r8, WPP_3a6abbfbb6653e334b912cc02283798e_Traceguids
0x18006bab3  mov     edx, 1Eh
0x18006bab8  mov     r9d, ebx
0x18006babb  call    WPP_SF_d
0x18006bac0  jmp     loc_18006B8DF
```
