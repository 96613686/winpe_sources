# _lambda_f5fb84ffdd45669e6dee99532ac1a9cf_::operator()

- ea: `0x18002feac`
- end: `0x1800300ce`
- name: `_lambda_f5fb84ffdd45669e6dee99532ac1a9cf_::operator()`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002c824`

## callees

- `0x18000bc48`
- `0x180016040`
- `0x18001b1c0`
- `0x18002feac`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002feed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002feed`

## string_xrefs

- `0x18002ff27`: `Unable to create TpmVCardManager instance`
- `0x180030080`: `Unable to create TPM virtual smart card`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_f5fb84ffdd45669e6dee99532ac1a9cf_::operator()(__int64 a1)
{
  __int64 v2; // rcx
  HRESULT v3; // edi
  int v4; // r9d
  __int64 (__fastcall *v6)(LPVOID, _QWORD, _BYTE *, _BYTE *, _QWORD, _DWORD, __int64, int, __int64, int, __int64, int, __int64, int, int); // r13
  int v7; // r12d
  __int64 *v8; // rcx
  __int64 v9; // rdi
  int v10; // r10d
  __int64 *v11; // rcx
  __int64 *v12; // rcx
  __int64 v13; // rbp
  int v14; // r15d
  __int64 *v15; // rcx
  __int64 v16; // rsi
  int v17; // ecx
  _BYTE *v18; // r9
  _BYTE *v19; // r8
  __int64 v20; // rcx
  int v21; // ebx
  int v22; // r9d
  int v23; // [rsp+C8h] [rbp+10h]
  LPVOID ppv; // [rsp+D0h] [rbp+18h] BYREF
  __int64 v25; // [rsp+D8h] [rbp+20h]

  ppv = 0;
  v3 = CoCreateInstance(&CLSID_TpmVCardManager, 0, 4u, &GUID_173fd26e_b0f7_42bf_bfd0_d91df64cc298, &ppv);
  if ( v3 >= 0 )
  {
    v6 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _BYTE *, _BYTE *, _QWORD, _DWORD, __int64, int, __int64, int, __int64, int, __int64, int, int))(*(_QWORD *)ppv + 24LL);
    v7 = **(_DWORD **)(a1 + 72);
    v8 = **(__int64 ***)(a1 + 64);
    if ( v8 )
    {
      v9 = *v8;
      v10 = *((_DWORD *)v8 + 3);
    }
    else
    {
      v9 = 0;
      v10 = 0;
    }
    v11 = **(__int64 ***)(a1 + 56);
    v23 = *((_DWORD *)v11 + 3);
    v25 = *v11;
    v12 = **(__int64 ***)(a1 + 48);
    if ( v12 )
    {
      v13 = *v12;
      v14 = *((_DWORD *)v12 + 3);
    }
    else
    {
      v13 = 0;
      v14 = 0;
    }
    v15 = **(__int64 ***)(a1 + 40);
    if ( v15 )
    {
      v16 = *v15;
      v17 = *((_DWORD *)v15 + 3);
    }
    else
    {
      v16 = 0;
      v17 = 0;
    }
    v18 = *(_BYTE **)(a1 + 24);
    v19 = *(_BYTE **)(a1 + 16);
    LOBYTE(v18) = *v18;
    LOBYTE(v19) = *v19;
    v21 = v6(
            ppv,
            **(_QWORD **)(a1 + 8),
            v19,
            v18,
            ***(_QWORD ***)(a1 + 32),
            *(_DWORD *)(**(_QWORD **)(a1 + 32) + 12LL),
            v16,
            v17,
            v13,
            v14,
            v25,
            v23,
            v9,
            v10,
            v7);
    if ( v21 >= 0 )
    {
      v21 = 0;
    }
    else
    {
      WppTraceIndent(v20, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          129,
          (unsigned int)WPP_19641971e2e2383bda07edbd33517adf_Traceguids,
          v22,
          v21,
          (__int64)"Unable to create TPM virtual smart card");
      }
    }
    wil::com_ptr_t<ITpmVCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVCardManager,wil::err_exception_policy>((__int64 *)&ppv);
    return (unsigned int)v21;
  }
  else
  {
    WppTraceIndent(v2, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        128,
        (unsigned int)WPP_19641971e2e2383bda07edbd33517adf_Traceguids,
        v4,
        v3,
        (__int64)"Unable to create TpmVCardManager instance");
    }
    wil::com_ptr_t<ITpmVCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVCardManager,wil::err_exception_policy>((__int64 *)&ppv);
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x18002feac  mov     rax, rsp
0x18002feaf  mov     [rax+8], rbx
0x18002feb3  push    rbp
0x18002feb4  push    rsi
0x18002feb5  push    rdi
0x18002feb6  push    r12
0x18002feb8  push    r13
0x18002feba  push    r14
0x18002febc  push    r15
0x18002febe  sub     rsp, 80h
0x18002fec5  mov     rbx, rcx
0x18002fec8  mov     qword ptr [rax+18h], 0
0x18002fed0  lea     rax, [rax+18h]
0x18002fed4  mov     [rsp+0B8h+ppv], rax; ppv
0x18002fed9  lea     r9, _GUID_173fd26e_b0f7_42bf_bfd0_d91df64cc298; riid
0x18002fee0  xor     edx, edx; pUnkOuter
0x18002fee2  lea     r8d, [rdx+4]; dwClsContext
0x18002fee6  lea     rcx, CLSID_TpmVCardManager; rclsid
0x18002feed  call    cs:__imp_CoCreateInstance
0x18002fef3  mov     edi, eax
0x18002fef5  test    eax, eax
0x18002fef7  jns     short loc_18002FF5C
0x18002fef9  mov     edx, 2
0x18002fefe  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002ff03  lea     rdx, WPP_GLOBAL_Control
0x18002ff0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff11  cmp     rcx, rdx
0x18002ff14  jz      short loc_18002FF48
0x18002ff16  test    byte ptr [rcx+1Ch], 1
0x18002ff1a  jz      short loc_18002FF48
0x18002ff1c  cmp     byte ptr [rcx+19h], 2
0x18002ff20  jb      short loc_18002FF48
0x18002ff22  mov     edx, 80h
0x18002ff27  lea     rax, aUnableToCreate_6; "Unable to create TpmVCardManager instan"...
0x18002ff2e  mov     [rsp+0B8h+var_90], rax
0x18002ff33  mov     dword ptr [rsp+0B8h+ppv], edi
0x18002ff37  lea     r8, WPP_19641971e2e2383bda07edbd33517adf_Traceguids
0x18002ff3e  mov     rcx, [rcx+10h]
0x18002ff42  call    WPP_SF_sds
0x18002ff47  nop
0x18002ff48  lea     rcx, [rsp+0B8h+arg_10]
0x18002ff50  call    ??1?$com_ptr_t@UITpmVCardManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITpmVCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVCardManager,wil::err_exception_policy>(void)
0x18002ff55  mov     eax, edi
0x18002ff57  jmp     loc_1800300B3
0x18002ff5c  mov     r14, [rsp+0B8h+arg_10]
0x18002ff64  mov     rax, [r14]
0x18002ff67  mov     r13, [rax+18h]
0x18002ff6b  mov     rax, [rbx+48h]
0x18002ff6f  mov     r12d, [rax]
0x18002ff72  mov     rax, [rbx+40h]
0x18002ff76  mov     rcx, [rax]
0x18002ff79  test    rcx, rcx
0x18002ff7c  jz      short loc_18002FF87
0x18002ff7e  mov     rdi, [rcx]
0x18002ff81  mov     r10d, [rcx+0Ch]
0x18002ff85  jmp     short loc_18002FF8C
0x18002ff87  xor     edi, edi
0x18002ff89  xor     r10d, r10d
0x18002ff8c  mov     rax, [rbx+38h]
0x18002ff90  mov     rcx, [rax]
0x18002ff93  mov     eax, [rcx+0Ch]
0x18002ff96  mov     [rsp+0B8h+arg_8], eax
0x18002ff9d  mov     rax, [rcx]
0x18002ffa0  mov     [rsp+0B8h+arg_18], rax
0x18002ffa8  mov     rax, [rbx+30h]
0x18002ffac  mov     rcx, [rax]
0x18002ffaf  test    rcx, rcx
0x18002ffb2  jz      short loc_18002FFBD
0x18002ffb4  mov     rbp, [rcx]
0x18002ffb7  mov     r15d, [rcx+0Ch]
0x18002ffbb  jmp     short loc_18002FFC2
0x18002ffbd  xor     ebp, ebp
0x18002ffbf  xor     r15d, r15d
0x18002ffc2  mov     rax, [rbx+28h]
0x18002ffc6  mov     rcx, [rax]
0x18002ffc9  test    rcx, rcx
0x18002ffcc  jz      short loc_18002FFD6
0x18002ffce  mov     rsi, [rcx]
0x18002ffd1  mov     ecx, [rcx+0Ch]
0x18002ffd4  jmp     short loc_18002FFDA
0x18002ffd6  xor     esi, esi
0x18002ffd8  xor     ecx, ecx
0x18002ffda  mov     rax, [rbx+20h]
0x18002ffde  mov     r11, [rax]
0x18002ffe1  mov     r9, [rbx+18h]
0x18002ffe5  mov     r8, [rbx+10h]
0x18002ffe9  mov     rdx, [rbx+8]
0x18002ffed  mov     [rsp+0B8h+var_48], r12d
0x18002fff2  mov     [rsp+0B8h+var_50], r10d
0x18002fff7  mov     [rsp+0B8h+var_58], rdi
0x18002fffc  mov     eax, [rsp+0B8h+arg_8]
0x180030003  mov     [rsp+0B8h+var_60], eax
0x180030007  mov     rax, [rsp+0B8h+arg_18]
0x18003000f  mov     [rsp+0B8h+var_68], rax
0x180030014  mov     [rsp+0B8h+var_70], r15d
0x180030019  mov     [rsp+0B8h+var_78], rbp
0x18003001e  mov     [rsp+0B8h+var_80], ecx
0x180030022  mov     [rsp+0B8h+var_88], rsi
0x180030027  mov     r10d, [r11+0Ch]
0x18003002b  mov     dword ptr [rsp+0B8h+var_90], r10d
0x180030030  mov     r10, [r11]
0x180030033  mov     [rsp+0B8h+ppv], r10
0x180030038  mov     r9b, [r9]
0x18003003b  mov     r8b, [r8]
0x18003003e  mov     rdx, [rdx]
0x180030041  mov     rcx, r14
0x180030044  mov     rax, r13
0x180030047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003004c  mov     ebx, eax
0x18003004e  test    eax, eax
0x180030050  jns     short loc_1800300A2
0x180030052  mov     edx, 2
0x180030057  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003005c  lea     rdx, WPP_GLOBAL_Control
0x180030063  mov     rcx, cs:WPP_GLOBAL_Control
0x18003006a  cmp     rcx, rdx
0x18003006d  jz      short loc_1800300A4
0x18003006f  test    byte ptr [rcx+1Ch], 1
0x180030073  jz      short loc_1800300A4
0x180030075  cmp     byte ptr [rcx+19h], 2
0x180030079  jb      short loc_1800300A4
0x18003007b  mov     edx, 81h
0x180030080  lea     rax, aUnableToCreate_8; "Unable to create TPM virtual smart card"
0x180030087  mov     [rsp+0B8h+var_90], rax
0x18003008c  mov     dword ptr [rsp+0B8h+ppv], ebx
0x180030090  lea     r8, WPP_19641971e2e2383bda07edbd33517adf_Traceguids
0x180030097  mov     rcx, [rcx+10h]
0x18003009b  call    WPP_SF_sds
0x1800300a0  jmp     short loc_1800300A4
0x1800300a2  xor     ebx, ebx
0x1800300a4  lea     rcx, [rsp+0B8h+arg_10]
0x1800300ac  call    ??1?$com_ptr_t@UITpmVCardManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITpmVCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVCardManager,wil::err_exception_policy>(void)
0x1800300b1  mov     eax, ebx
0x1800300b3  mov     rbx, [rsp+0B8h+arg_0]
0x1800300bb  add     rsp, 80h
0x1800300c2  pop     r15
0x1800300c4  pop     r14
0x1800300c6  pop     r13
0x1800300c8  pop     r12
0x1800300ca  pop     rdi
0x1800300cb  pop     rsi
0x1800300cc  pop     rbp
0x1800300cd  retn
```
