# _lambda_dbcd06aed7c5bf915b743e226768c441_::operator()

- ea: `0x18002f818`
- end: `0x18002f91d`
- name: `_lambda_dbcd06aed7c5bf915b743e226768c441_::operator()`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002c7c4`

## callees

- `0x18000bc48`
- `0x180016040`
- `0x18001b1c0`
- `0x18002f818`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f84b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f84b`

## string_xrefs

- `0x18002f88d`: `Unable to create TpmVCardManager instance`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_dbcd06aed7c5bf915b743e226768c441_::operator()(__int64 a1)
{
  __int64 v2; // rcx
  HRESULT v3; // ebx
  int v4; // r9d
  _QWORD *v5; // rcx
  int v6; // edx
  const char *v7; // rax
  __int64 v8; // rcx
  LPVOID v10; // [rsp+48h] [rbp+10h] BYREF

  v10 = 0;
  v3 = CoCreateInstance(&CLSID_TpmVCardManager, 0, 4u, &GUID_173fd26e_b0f7_42bf_bfd0_d91df64cc298, &v10);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v10 + 32LL))(v10, **(_QWORD **)(a1 + 8));
    if ( v3 >= 0 )
    {
      v3 = 0;
      goto LABEL_13;
    }
    WppTraceIndent(v8, 2u);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 138;
      v7 = "Unable to destroy TPM virtual smart card";
      goto LABEL_11;
    }
  }
  else
  {
    WppTraceIndent(v2, 2u);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 137;
      v7 = "Unable to create TpmVCardManager instance";
LABEL_11:
      WPP_SF_sds(v5[2], v6, (unsigned int)WPP_19641971e2e2383bda07edbd33517adf_Traceguids, v4, v3, (__int64)v7);
    }
  }
LABEL_13:
  wil::com_ptr_t<ITpmVCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVCardManager,wil::err_exception_policy>((__int64 *)&v10);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002f818  mov     r11, rsp
0x18002f81b  mov     [r11+8], rbx
0x18002f81f  push    rdi
0x18002f820  sub     rsp, 30h
0x18002f824  mov     rdi, rcx
0x18002f827  mov     qword ptr [r11+10h], 0
0x18002f82f  lea     rax, [r11+10h]
0x18002f833  mov     [r11-18h], rax
0x18002f837  lea     r9, _GUID_173fd26e_b0f7_42bf_bfd0_d91df64cc298; riid
0x18002f83e  xor     edx, edx; pUnkOuter
0x18002f840  lea     r8d, [rdx+4]; dwClsContext
0x18002f844  lea     rcx, CLSID_TpmVCardManager; rclsid
0x18002f84b  call    cs:__imp_CoCreateInstance
0x18002f851  mov     ebx, eax
0x18002f853  test    eax, eax
0x18002f855  jns     short loc_18002F896
0x18002f857  mov     edx, 2
0x18002f85c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002f861  lea     rdx, WPP_GLOBAL_Control
0x18002f868  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f86f  cmp     rcx, rdx
0x18002f872  jz      loc_18002F906
0x18002f878  test    byte ptr [rcx+1Ch], 1
0x18002f87c  jz      loc_18002F906
0x18002f882  cmp     byte ptr [rcx+19h], 2
0x18002f886  jb      short loc_18002F906
0x18002f888  mov     edx, 89h
0x18002f88d  lea     rax, aUnableToCreate_6; "Unable to create TpmVCardManager instan"...
0x18002f894  jmp     short loc_18002F8E9
0x18002f896  mov     rcx, [rsp+38h+arg_8]
0x18002f89b  mov     rax, [rcx]
0x18002f89e  mov     rdx, [rdi+8]
0x18002f8a2  mov     rdx, [rdx]
0x18002f8a5  mov     rax, [rax+20h]
0x18002f8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8ae  mov     ebx, eax
0x18002f8b0  test    eax, eax
0x18002f8b2  jns     short loc_18002F904
0x18002f8b4  mov     edx, 2
0x18002f8b9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002f8be  lea     rdx, WPP_GLOBAL_Control
0x18002f8c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f8cc  cmp     rcx, rdx
0x18002f8cf  jz      short loc_18002F906
0x18002f8d1  test    byte ptr [rcx+1Ch], 1
0x18002f8d5  jz      short loc_18002F906
0x18002f8d7  cmp     byte ptr [rcx+19h], 2
0x18002f8db  jb      short loc_18002F906
0x18002f8dd  mov     edx, 8Ah
0x18002f8e2  lea     rax, aUnableToDestro_0; "Unable to destroy TPM virtual smart car"...
0x18002f8e9  mov     [rsp+38h+var_10], rax
0x18002f8ee  mov     [rsp+38h+var_18], ebx
0x18002f8f2  lea     r8, WPP_19641971e2e2383bda07edbd33517adf_Traceguids
0x18002f8f9  mov     rcx, [rcx+10h]
0x18002f8fd  call    WPP_SF_sds
0x18002f902  jmp     short loc_18002F906
0x18002f904  xor     ebx, ebx
0x18002f906  lea     rcx, [rsp+38h+arg_8]
0x18002f90b  call    ??1?$com_ptr_t@UITpmVCardManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITpmVCardManager,wil::err_exception_policy>::~com_ptr_t<ITpmVCardManager,wil::err_exception_policy>(void)
0x18002f910  mov     eax, ebx
0x18002f912  mov     rbx, [rsp+38h+arg_0]
0x18002f917  add     rsp, 30h
0x18002f91b  pop     rdi
0x18002f91c  retn
```
