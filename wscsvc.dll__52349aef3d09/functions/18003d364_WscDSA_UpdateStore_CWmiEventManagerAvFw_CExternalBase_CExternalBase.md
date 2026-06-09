# WscDSA_UpdateStore(CWmiEventManagerAvFw *,CExternalBase *,CExternalBase *)

- ea: `0x18003d364`
- end: `0x18003d549`
- name: `?WscDSA_UpdateStore@@YAJPEAVCWmiEventManagerAvFw@@PEAVCExternalBase@@1@Z`
- size: `485`
- prototype: `__int64 __fastcall(struct CWmiEventManagerAvFw *this, struct CExternalBase *, struct CExternalBase *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x18003ce18`
- `0x18003d6f8`

## callees

- `0x180008e48`
- `0x180015bf0`
- `0x18001c4c0`
- `0x1800202e8`
- `0x180029158`
- `0x18003d364`
- `0x180042010`

## pseudocode

```c
__int64 __fastcall WscDSA_UpdateStore(
        struct CWmiEventManagerAvFw *this,
        struct CExternalBase *a2,
        struct CExternalBase *a3)
{
  CThirdPartyManager *v6; // rcx
  int WbemServices; // eax
  struct IWbemServices *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r9
  struct IWbemServices *v12; // [rsp+60h] [rbp+8h] BYREF

  v12 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !this )
  {
    if ( v6 == (CThirdPartyManager *)&WPP_GLOBAL_Control )
      return (unsigned int)this;
    if ( (*((_BYTE *)v6 + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)v6 + 2), 33, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
LABEL_32:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_33;
    }
    goto LABEL_33;
  }
  WbemServices = CWmiEventManager::GetWbemServices(this, (__int64)a2, &v12);
  v8 = v12;
  LODWORD(this) = WbemServices;
  if ( WbemServices >= 0 )
  {
    LODWORD(this) = CExternalBase::UpdatePersistentStore((__int64)a2, (__int64)v12, 0, -1);
    if ( (int)this >= 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          WPP_728c66c465713f49a85befae87578f6c_Traceguids,
          *((_QWORD *)a2 + 1));
        v6 = WPP_GLOBAL_Control;
      }
      if ( !a3 )
        goto LABEL_30;
      LODWORD(this) = CExternalBase::UpdatePersistentStore((__int64)a3, (__int64)v8, 0, -1);
      if ( (int)this >= 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_30;
        }
        v10 = *((_QWORD *)a3 + 1);
        v9 = 38;
LABEL_28:
        WPP_SF_S(*((_QWORD *)v6 + 2), v9, WPP_728c66c465713f49a85befae87578f6c_Traceguids, v10);
        goto LABEL_29;
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_30;
      }
      v9 = 37;
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_30;
      }
      v9 = 35;
    }
    v10 = *((_QWORD *)a2 + 1);
    goto LABEL_28;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
LABEL_29:
    v6 = WPP_GLOBAL_Control;
  }
LABEL_30:
  if ( v8 )
  {
    ((void (__fastcall *)(struct IWbemServices *))v8->lpVtbl->Release)(v8);
    goto LABEL_32;
  }
LABEL_33:
  if ( v6 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v6 + 2), 39, WPP_728c66c465713f49a85befae87578f6c_Traceguids, (unsigned int)this);
  return (unsigned int)this;
}

```

## disassembly

```asm
0x18003d364  push    rbx
0x18003d366  push    rbp
0x18003d367  push    rsi
0x18003d368  push    rdi
0x18003d369  push    r14
0x18003d36b  push    r15
0x18003d36d  sub     rsp, 28h
0x18003d371  mov     rbp, r8
0x18003d374  mov     [rsp+58h+arg_0], 0
0x18003d37d  mov     rsi, rdx
0x18003d380  mov     rbx, rcx
0x18003d383  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d38a  lea     r14, WPP_GLOBAL_Control
0x18003d391  lea     r15, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003d398  cmp     rcx, r14
0x18003d39b  jz      short loc_18003D3BB
0x18003d39d  test    byte ptr [rcx+1Ch], 8
0x18003d3a1  jz      short loc_18003D3BB
0x18003d3a3  mov     rcx, [rcx+10h]
0x18003d3a7  mov     edx, 20h ; ' '
0x18003d3ac  mov     r8, r15
0x18003d3af  call    WPP_SF_
0x18003d3b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d3bb  test    rbx, rbx
0x18003d3be  jnz     short loc_18003D3E9
0x18003d3c0  cmp     rcx, r14
0x18003d3c3  jz      loc_18003D53A
0x18003d3c9  test    byte ptr [rcx+1Ch], 1
0x18003d3cd  jz      loc_18003D51B
0x18003d3d3  mov     rcx, [rcx+10h]
0x18003d3d7  mov     edx, 21h ; '!'
0x18003d3dc  mov     r8, r15
0x18003d3df  call    WPP_SF_
0x18003d3e4  jmp     loc_18003D514
0x18003d3e9  lea     r8, [rsp+58h+arg_0]; struct IWbemServices **
0x18003d3ee  mov     rcx, rbx; this
0x18003d3f1  call    ?GetWbemServices@CWmiEventManager@@QEAAJHPEAPEAUIWbemServices@@@Z; CWmiEventManager::GetWbemServices(int,IWbemServices * *)
0x18003d3f6  mov     rdi, [rsp+58h+arg_0]
0x18003d3fb  mov     ebx, eax
0x18003d3fd  test    eax, eax
0x18003d3ff  jns     short loc_18003D431
0x18003d401  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d408  cmp     rcx, r14
0x18003d40b  jz      loc_18003D500
0x18003d411  test    byte ptr [rcx+1Ch], 1
0x18003d415  jz      loc_18003D500
0x18003d41b  mov     rcx, [rcx+10h]
0x18003d41f  mov     edx, 22h ; '"'
0x18003d424  mov     r8, r15
0x18003d427  call    WPP_SF_
0x18003d42c  jmp     loc_18003D4F9
0x18003d431  or      r9d, 0FFFFFFFFh
0x18003d435  xor     r8d, r8d
0x18003d438  mov     rdx, rdi
0x18003d43b  mov     rcx, rsi
0x18003d43e  call    ?UpdatePersistentStore@CExternalBase@@QEAAJPEAUIWbemServices@@W4_SECURITY_PRODUCT_TYPE@@W4_DATASTORE_BITMASK@@@Z; CExternalBase::UpdatePersistentStore(IWbemServices *,_SECURITY_PRODUCT_TYPE,_DATASTORE_BITMASK)
0x18003d443  mov     ebx, eax
0x18003d445  test    eax, eax
0x18003d447  jns     short loc_18003D46E
0x18003d449  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d450  cmp     rcx, r14
0x18003d453  jz      loc_18003D500
0x18003d459  test    byte ptr [rcx+1Ch], 1
0x18003d45d  jz      loc_18003D500
0x18003d463  mov     edx, 23h ; '#'
0x18003d468  mov     r9, [rsi+8]
0x18003d46c  jmp     short loc_18003D4ED
0x18003d46e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d475  cmp     rcx, r14
0x18003d478  jz      short loc_18003D49C
0x18003d47a  test    byte ptr [rcx+1Ch], 4
0x18003d47e  jz      short loc_18003D49C
0x18003d480  mov     r9, [rsi+8]
0x18003d484  mov     edx, 24h ; '$'
0x18003d489  mov     rcx, [rcx+10h]
0x18003d48d  mov     r8, r15
0x18003d490  call    WPP_SF_S
0x18003d495  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d49c  test    rbp, rbp
0x18003d49f  jz      short loc_18003D500
0x18003d4a1  or      r9d, 0FFFFFFFFh
0x18003d4a5  xor     r8d, r8d
0x18003d4a8  mov     rdx, rdi
0x18003d4ab  mov     rcx, rbp
0x18003d4ae  call    ?UpdatePersistentStore@CExternalBase@@QEAAJPEAUIWbemServices@@W4_SECURITY_PRODUCT_TYPE@@W4_DATASTORE_BITMASK@@@Z; CExternalBase::UpdatePersistentStore(IWbemServices *,_SECURITY_PRODUCT_TYPE,_DATASTORE_BITMASK)
0x18003d4b3  mov     ebx, eax
0x18003d4b5  test    eax, eax
0x18003d4b7  jns     short loc_18003D4D2
0x18003d4b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d4c0  cmp     rcx, r14
0x18003d4c3  jz      short loc_18003D500
0x18003d4c5  test    byte ptr [rcx+1Ch], 1
0x18003d4c9  jz      short loc_18003D500
0x18003d4cb  mov     edx, 25h ; '%'
0x18003d4d0  jmp     short loc_18003D468
0x18003d4d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d4d9  cmp     rcx, r14
0x18003d4dc  jz      short loc_18003D500
0x18003d4de  test    byte ptr [rcx+1Ch], 4
0x18003d4e2  jz      short loc_18003D500
0x18003d4e4  mov     r9, [rbp+8]
0x18003d4e8  mov     edx, 26h ; '&'
0x18003d4ed  mov     rcx, [rcx+10h]
0x18003d4f1  mov     r8, r15
0x18003d4f4  call    WPP_SF_S
0x18003d4f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d500  test    rdi, rdi
0x18003d503  jz      short loc_18003D51B
0x18003d505  mov     rax, [rdi]
0x18003d508  mov     rcx, rdi
0x18003d50b  mov     rax, [rax+10h]
0x18003d50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d514  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d51b  cmp     rcx, r14
0x18003d51e  jz      short loc_18003D53A
0x18003d520  test    byte ptr [rcx+1Ch], 8
0x18003d524  jz      short loc_18003D53A
0x18003d526  mov     rcx, [rcx+10h]
0x18003d52a  mov     edx, 27h ; '''
0x18003d52f  mov     r9d, ebx
0x18003d532  mov     r8, r15
0x18003d535  call    WPP_SF_d
0x18003d53a  mov     eax, ebx
0x18003d53c  add     rsp, 28h
0x18003d540  pop     r15
0x18003d542  pop     r14
0x18003d544  pop     rdi
0x18003d545  pop     rsi
0x18003d546  pop     rbp
0x18003d547  pop     rbx
0x18003d548  retn
```
