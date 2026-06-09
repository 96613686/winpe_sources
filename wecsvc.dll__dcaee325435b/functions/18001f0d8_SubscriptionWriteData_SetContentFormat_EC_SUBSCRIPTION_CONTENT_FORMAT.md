# SubscriptionWriteData::SetContentFormat(_EC_SUBSCRIPTION_CONTENT_FORMAT)

- ea: `0x18001f0d8`
- end: `0x18001f192`
- name: `?SetContentFormat@SubscriptionWriteData@@QEAAXW4_EC_SUBSCRIPTION_CONTENT_FORMAT@@@Z`
- size: `186`
- prototype: `void __fastcall(SubscriptionWriteData *__hidden this, enum _EC_SUBSCRIPTION_CONTENT_FORMAT)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001483c`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18001f0d8`

## string_xrefs

- `0x18001f12a`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
void __fastcall SubscriptionWriteData::SetContentFormat(
        SubscriptionWriteData *this,
        enum _EC_SUBSCRIPTION_CONTENT_FORMAT a2)
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
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 87);
    }
    v8 = 87;
    v4 = 0;
    v5 = "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp";
    v6 = 0;
    v7 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v9 = -1;
    v10 = 1377;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v2 = *(_QWORD *)this;
  *(_DWORD *)(*(_QWORD *)(v2 + 8) + 440LL) = a2;
  *(_DWORD *)(*(_QWORD *)(v2 + 8) + 432LL) = 2;
}

```

## disassembly

```asm
0x18001f0d8  sub     rsp, 68h
0x18001f0dc  lea     eax, [rdx-1]
0x18001f0df  cmp     eax, 1
0x18001f0e2  jbe     loc_18001F172
0x18001f0e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0ef  lea     rax, WPP_GLOBAL_Control
0x18001f0f6  cmp     rcx, rax
0x18001f0f9  jz      short loc_18001F120
0x18001f0fb  test    byte ptr [rcx+1Ch], 80h
0x18001f0ff  jz      short loc_18001F120
0x18001f101  cmp     byte ptr [rcx+19h], 2
0x18001f105  jb      short loc_18001F120
0x18001f107  mov     rcx, [rcx+10h]
0x18001f10b  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18001f112  mov     edx, 1Dh
0x18001f117  lea     r9d, [rdx+3Ah]
0x18001f11b  call    WPP_SF_D
0x18001f120  xor     ecx, ecx
0x18001f122  mov     [rsp+68h+var_20], 57h ; 'W'
0x18001f12a  lea     rax, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x18001f131  mov     [rsp+68h+var_40], cl
0x18001f135  mov     [rsp+68h+var_38], rax
0x18001f13a  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001f141  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001f148  mov     [rsp+68h+var_30], rcx
0x18001f14d  mov     [rsp+68h+var_28], rcx
0x18001f152  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001f157  mov     [rsp+68h+pExceptionObject], rax
0x18001f15c  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x18001f164  mov     [rsp+68h+var_18], 561h
0x18001f16c  call    _CxxThrowException_0
0x18001f172  mov     rcx, [rcx]
0x18001f175  mov     rax, [rcx+8]
0x18001f179  mov     [rax+1B8h], edx
0x18001f17f  mov     rax, [rcx+8]
0x18001f183  mov     dword ptr [rax+1B0h], 2
0x18001f18d  add     rsp, 68h
0x18001f191  retn
```
