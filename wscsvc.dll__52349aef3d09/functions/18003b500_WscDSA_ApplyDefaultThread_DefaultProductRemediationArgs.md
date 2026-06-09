# WscDSA_ApplyDefaultThread(_DefaultProductRemediationArgs *)

- ea: `0x18003b500`
- end: `0x18003b713`
- name: `?WscDSA_ApplyDefaultThread@@YAKPEAU_DefaultProductRemediationArgs@@@Z`
- size: `531`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18000760c`
- `0x180008e48`
- `0x1800202e8`
- `0x18003b500`
- `0x18003b904`
- `0x18003b9c4`
- `0x18003c47c`
- `0x18003c5ec`
- `0x18003c708`
- `0x180042010`

## import_xrefs

- `msvcrt!free` at `0x18003b6b4`
- `msvcrt!free` at `0x18003b6b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b6ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b6ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b571`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b571`

## pseudocode

```c
__int64 __fastcall WscDSA_ApplyDefaultThread(PVOID Parameter)
{
  struct CWmiEventManagerAvFw *v2; // r14
  struct CThirdPartyManager *v3; // rbp
  int v4; // eax
  struct CExternalBase *v5; // rdi
  int v6; // ebx
  int v7; // eax
  int v9; // [rsp+70h] [rbp+8h] BYREF
  struct CExternalBase *v10; // [rsp+78h] [rbp+10h] BYREF

  v10 = 0;
  v9 = 0;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
  v2 = *(struct CWmiEventManagerAvFw **)Parameter;
  v3 = (struct CThirdPartyManager *)*((_QWORD *)Parameter + 1);
  if ( dword_1800540C0 )
    EnterCriticalSection(&s_RemediationLock);
  v4 = WscDSA_CloneDefaultProduct(v3, &v10);
  v5 = v10;
  v6 = v4;
  if ( v4 >= 0 && v10 )
  {
    if ( (((unsigned int)CExternalBase::GetProductState((__int64)v10) - 4096) & 0xFFFFEFFF) != 0 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
      }
      v6 = WscDSA_RemediateProduct(v2, v3, 0, *((wchar_t **)v5 + 1), *((const WCHAR **)v5 + 3), 0x3Cu, &v9);
      if ( v6 < 0 )
        goto LABEL_26;
      v7 = v9;
    }
    else
    {
      v7 = 1;
    }
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
      }
      if ( (*((_BYTE *)Parameter + 16) & 1) != 0 )
        WscDSA_PublishNotification(7, *((_QWORD *)v5 + 2));
LABEL_25:
      v6 = WscDSA_DisableNonDefault(v2, v3, *((_DWORD *)Parameter + 4));
      goto LABEL_26;
    }
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
    }
    v6 = WscDSA_ResetDefault(v2, v3, *((_DWORD *)Parameter + 4));
    if ( v6 >= 0 )
      goto LABEL_25;
  }
LABEL_26:
  if ( dword_1800540C0 )
    LeaveCriticalSection(&s_RemediationLock);
  free(Parameter);
  if ( v5 )
    (**(void (__fastcall ***)(struct CExternalBase *, __int64))v5)(v5, 1);
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_728c66c465713f49a85befae87578f6c_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003b500  mov     rax, rsp
0x18003b503  mov     [rax+18h], rbx
0x18003b507  mov     [rax+20h], rbp
0x18003b50b  push    rsi
0x18003b50c  push    rdi
0x18003b50d  push    r12
0x18003b50f  push    r13
0x18003b511  push    r14
0x18003b513  sub     rsp, 40h
0x18003b517  mov     rsi, rcx
0x18003b51a  mov     qword ptr [rax+10h], 0
0x18003b522  mov     dword ptr [rax+8], 0
0x18003b529  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b530  lea     r12, WPP_GLOBAL_Control
0x18003b537  lea     r13, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003b53e  cmp     rcx, r12
0x18003b541  jz      short loc_18003B55A
0x18003b543  test    byte ptr [rcx+1Ch], 8
0x18003b547  jz      short loc_18003B55A
0x18003b549  mov     rcx, [rcx+10h]
0x18003b54d  mov     edx, 4Ah ; 'J'
0x18003b552  mov     r8, r13
0x18003b555  call    WPP_SF_
0x18003b55a  cmp     cs:dword_1800540C0, 0
0x18003b561  mov     r14, [rsi]
0x18003b564  mov     rbp, [rsi+8]
0x18003b568  jz      short loc_18003B577
0x18003b56a  lea     rcx, ?s_RemediationLock@@3VCCriticalSection@@A; lpCriticalSection
0x18003b571  call    cs:__imp_EnterCriticalSection
0x18003b577  lea     rdx, [rsp+68h+arg_8]; struct CExternalBase **
0x18003b57c  mov     rcx, rbp; this
0x18003b57f  call    ?WscDSA_CloneDefaultProduct@@YAJPEAVCThirdPartyManager@@PEAPEAVCExternalBase@@@Z; WscDSA_CloneDefaultProduct(CThirdPartyManager *,CExternalBase * *)
0x18003b584  mov     rdi, [rsp+68h+arg_8]
0x18003b589  mov     ebx, eax
0x18003b58b  test    eax, eax
0x18003b58d  js      loc_18003B69B
0x18003b593  test    rdi, rdi
0x18003b596  jz      loc_18003B69B
0x18003b59c  mov     rcx, rdi
0x18003b59f  call    ?GetProductState@CExternalBase@@QEAA?AW4ProductState@@XZ; CExternalBase::GetProductState(void)
0x18003b5a4  add     eax, 0FFFFF000h
0x18003b5a9  test    eax, 0FFFFEFFFh
0x18003b5ae  jz      short loc_18003B610
0x18003b5b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b5b7  cmp     rcx, r12
0x18003b5ba  jz      short loc_18003B5D3
0x18003b5bc  test    byte ptr [rcx+1Ch], 4
0x18003b5c0  jz      short loc_18003B5D3
0x18003b5c2  mov     rcx, [rcx+10h]
0x18003b5c6  mov     edx, 4Bh ; 'K'
0x18003b5cb  mov     r8, r13
0x18003b5ce  call    WPP_SF_
0x18003b5d3  mov     r9, [rdi+8]
0x18003b5d7  lea     rax, [rsp+68h+arg_0]
0x18003b5dc  mov     [rsp+68h+var_38], rax
0x18003b5e1  xor     r8d, r8d
0x18003b5e4  mov     rax, [rdi+18h]
0x18003b5e8  mov     rdx, rbp
0x18003b5eb  mov     [rsp+68h+var_40], 3Ch ; '<'
0x18003b5f3  mov     rcx, r14
0x18003b5f6  mov     [rsp+68h+var_48], rax
0x18003b5fb  call    ?WscDSA_RemediateProduct@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@W4RemediationAction@@PEBG3KPEAH@Z; WscDSA_RemediateProduct(CWmiEventManagerAvFw *,CThirdPartyManager *,RemediationAction,ushort const *,ushort const *,ulong,int *)
0x18003b600  mov     ebx, eax
0x18003b602  test    eax, eax
0x18003b604  js      loc_18003B69B
0x18003b60a  mov     eax, [rsp+68h+arg_0]
0x18003b60e  jmp     short loc_18003B615
0x18003b610  mov     eax, 1
0x18003b615  test    eax, eax
0x18003b617  jz      short loc_18003B652
0x18003b619  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b620  cmp     rcx, r12
0x18003b623  jz      short loc_18003B63C
0x18003b625  test    byte ptr [rcx+1Ch], 4
0x18003b629  jz      short loc_18003B63C
0x18003b62b  mov     rcx, [rcx+10h]
0x18003b62f  mov     edx, 4Ch ; 'L'
0x18003b634  mov     r8, r13
0x18003b637  call    WPP_SF_
0x18003b63c  test    byte ptr [rsi+10h], 1
0x18003b640  jz      short loc_18003B68A
0x18003b642  mov     rdx, [rdi+10h]
0x18003b646  mov     ecx, 7
0x18003b64b  call    ?WscDSA_PublishNotification@@YAJW4WnfNotificationType@@PEBG@Z; WscDSA_PublishNotification(WnfNotificationType,ushort const *)
0x18003b650  jmp     short loc_18003B68A
0x18003b652  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b659  cmp     rcx, r12
0x18003b65c  jz      short loc_18003B675
0x18003b65e  test    byte ptr [rcx+1Ch], 4
0x18003b662  jz      short loc_18003B675
0x18003b664  mov     rcx, [rcx+10h]
0x18003b668  mov     edx, 4Dh ; 'M'
0x18003b66d  mov     r8, r13
0x18003b670  call    WPP_SF_
0x18003b675  mov     r8d, [rsi+10h]; unsigned int
0x18003b679  mov     rdx, rbp; struct CThirdPartyManager *
0x18003b67c  mov     rcx, r14; this
0x18003b67f  call    ?WscDSA_ResetDefault@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@K@Z; WscDSA_ResetDefault(CWmiEventManagerAvFw *,CThirdPartyManager *,ulong)
0x18003b684  mov     ebx, eax
0x18003b686  test    eax, eax
0x18003b688  js      short loc_18003B69B
0x18003b68a  mov     r8d, [rsi+10h]; unsigned int
0x18003b68e  mov     rdx, rbp; struct CThirdPartyManager *
0x18003b691  mov     rcx, r14; struct CWmiEventManagerAvFw *
0x18003b694  call    ?WscDSA_DisableNonDefault@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@K@Z; WscDSA_DisableNonDefault(CWmiEventManagerAvFw *,CThirdPartyManager *,ulong)
0x18003b699  mov     ebx, eax
0x18003b69b  cmp     cs:dword_1800540C0, 0
0x18003b6a2  jz      short loc_18003B6B1
0x18003b6a4  lea     rcx, ?s_RemediationLock@@3VCCriticalSection@@A; lpCriticalSection
0x18003b6ab  call    cs:__imp_LeaveCriticalSection
0x18003b6b1  mov     rcx, rsi; Block
0x18003b6b4  call    cs:__imp_free
0x18003b6ba  test    rdi, rdi
0x18003b6bd  jz      short loc_18003B6D2
0x18003b6bf  mov     rax, [rdi]
0x18003b6c2  mov     edx, 1
0x18003b6c7  mov     rcx, rdi
0x18003b6ca  mov     rax, [rax]
0x18003b6cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b6d9  cmp     rcx, r12
0x18003b6dc  jz      short loc_18003B6F8
0x18003b6de  test    byte ptr [rcx+1Ch], 8
0x18003b6e2  jz      short loc_18003B6F8
0x18003b6e4  mov     rcx, [rcx+10h]
0x18003b6e8  mov     edx, 4Eh ; 'N'
0x18003b6ed  mov     r9d, ebx
0x18003b6f0  mov     r8, r13
0x18003b6f3  call    WPP_SF_d
0x18003b6f8  lea     r11, [rsp+68h+var_28]
0x18003b6fd  mov     eax, ebx
0x18003b6ff  mov     rbx, [r11+40h]
0x18003b703  mov     rbp, [r11+48h]
0x18003b707  mov     rsp, r11
0x18003b70a  pop     r14
0x18003b70c  pop     r13
0x18003b70e  pop     r12
0x18003b710  pop     rdi
0x18003b711  pop     rsi
0x18003b712  retn
```
