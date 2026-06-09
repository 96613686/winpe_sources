# SubscriptionWriteData::SetDeliveryMode(_EC_SUBSCRIPTION_DELIVERY_MODE)

- ea: `0x18001f198`
- end: `0x18001f252`
- name: `?SetDeliveryMode@SubscriptionWriteData@@QEAAXW4_EC_SUBSCRIPTION_DELIVERY_MODE@@@Z`
- size: `186`
- prototype: `void __fastcall(SubscriptionWriteData *__hidden this, enum _EC_SUBSCRIPTION_DELIVERY_MODE)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001483c`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18001f198`

## string_xrefs

- `0x18001f1ea`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
void __fastcall SubscriptionWriteData::SetDeliveryMode(
        SubscriptionWriteData *this,
        enum _EC_SUBSCRIPTION_DELIVERY_MODE a2)
{
  __int64 v2; // rcx
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v4; // [rsp+28h] [rbp-40h]
  const char *v5; // [rsp+30h] [rbp-38h]
  __int64 v6; // [rsp+38h] [rbp-30h]
  __int64 v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]
  int v10; // [rsp+50h] [rbp-18h]

  if ( (unsigned int)(a2 - 1) > 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 13);
    }
    v8 = 13;
    v4 = 0;
    v5 = "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp";
    v6 = 0;
    v7 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v9 = -1;
    v10 = 1344;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v2 = *(_QWORD *)this;
  *(_DWORD *)(*(_QWORD *)(v2 + 8) + 320LL) = a2;
  *(_DWORD *)(*(_QWORD *)(v2 + 8) + 312LL) = 2;
}

```

## disassembly

```asm
0x18001f198  sub     rsp, 68h
0x18001f19c  lea     eax, [rdx-1]
0x18001f19f  cmp     eax, 1
0x18001f1a2  jbe     loc_18001F232
0x18001f1a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1af  lea     rax, WPP_GLOBAL_Control
0x18001f1b6  cmp     rcx, rax
0x18001f1b9  jz      short loc_18001F1E0
0x18001f1bb  test    byte ptr [rcx+1Ch], 80h
0x18001f1bf  jz      short loc_18001F1E0
0x18001f1c1  cmp     byte ptr [rcx+19h], 2
0x18001f1c5  jb      short loc_18001F1E0
0x18001f1c7  mov     rcx, [rcx+10h]
0x18001f1cb  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18001f1d2  mov     edx, 1Ch
0x18001f1d7  lea     r9d, [rdx-0Fh]
0x18001f1db  call    WPP_SF_D
0x18001f1e0  xor     ecx, ecx
0x18001f1e2  mov     [rsp+68h+var_20], 0Dh
0x18001f1ea  lea     rax, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x18001f1f1  mov     [rsp+68h+var_40], cl
0x18001f1f5  mov     [rsp+68h+var_38], rax
0x18001f1fa  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001f201  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001f208  mov     [rsp+68h+var_30], rcx
0x18001f20d  mov     [rsp+68h+var_28], rcx
0x18001f212  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001f217  mov     [rsp+68h+pExceptionObject], rax
0x18001f21c  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x18001f224  mov     [rsp+68h+var_18], 540h
0x18001f22c  call    _CxxThrowException_0
0x18001f232  mov     rcx, [rcx]
0x18001f235  mov     rax, [rcx+8]
0x18001f239  mov     [rax+140h], edx
0x18001f23f  mov     rax, [rcx+8]
0x18001f243  mov     dword ptr [rax+138h], 2
0x18001f24d  add     rsp, 68h
0x18001f251  retn
```
