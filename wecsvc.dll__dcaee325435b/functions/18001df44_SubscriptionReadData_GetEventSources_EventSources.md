# SubscriptionReadData::GetEventSources(_EventSources &)

- ea: `0x18001df44`
- end: `0x18001e083`
- name: `?GetEventSources@SubscriptionReadData@@QEBAXAEAU_EventSources@@@Z`
- size: `319`
- prototype: `void __fastcall(SubscriptionReadData *__hidden this, struct _EventSources *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009170`
- `0x180009a10`
- `0x18001718c`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18001df44`
- `0x18001eab4`
- `0x18001ebc4`
- `0x18001ecec`
- `0x18001eeec`

## string_xrefs

- `0x18001e030`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
void __fastcall SubscriptionReadData::GetEventSources(SubscriptionReadData *this, struct _EventSources *a2)
{
  __int64 v4; // rdx
  int v5; // edx
  __int64 v6; // rcx
  void **pExceptionObject; // [rsp+20h] [rbp-68h] BYREF
  char v8; // [rsp+28h] [rbp-60h]
  const char *v9; // [rsp+30h] [rbp-58h]
  __int64 v10; // [rsp+38h] [rbp-50h]
  __int64 v11; // [rsp+40h] [rbp-48h]
  int v12; // [rsp+48h] [rbp-40h]
  int v13; // [rsp+4Ch] [rbp-3Ch]
  int v14; // [rsp+50h] [rbp-38h]

  ReadMetadataProp(*(_QWORD *)this, (__int64)a2, a2);
  ReadMetadataProp(*(_QWORD *)this, 2u, (_QWORD *)a2 + 7);
  ReadMetadataProp(*(_QWORD *)this, v4, (__int64)a2 + 24);
  ReadMetadataProp(*(_QWORD *)this, 4u, (_QWORD *)a2 + 10);
  ReadMetadataProp(*(_QWORD *)this, v5, (__int64 *)a2 + 13);
  v6 = (__int64)(*((_QWORD *)a2 + 8) - *((_QWORD *)a2 + 7)) >> 5;
  if ( v6 != (__int64)(*((_QWORD *)a2 + 1) - *(_QWORD *)a2) >> 2
    || v6 != *((_QWORD *)a2 + 6)
    || v6 != (__int64)(*((_QWORD *)a2 + 11) - *((_QWORD *)a2 + 10)) >> 5
    || v6 != 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)a2 + 14) - *((_QWORD *)a2 + 13)) >> 3) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 13);
    }
    v12 = 13;
    v8 = 0;
    v9 = "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp";
    v10 = 0;
    v11 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v13 = -1;
    v14 = 667;
    throw (wmi::GenericException *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x18001df44  push    rbx
0x18001df46  push    rbp
0x18001df47  push    rsi
0x18001df48  push    rdi
0x18001df49  push    r14
0x18001df4b  sub     rsp, 60h
0x18001df4f  mov     rdi, rcx
0x18001df52  mov     r8, rdx
0x18001df55  mov     rcx, [rcx]
0x18001df58  mov     rsi, rdx
0x18001df5b  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$vector@KV?$allocator@K@std@@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::vector<ulong> &)
0x18001df60  mov     rcx, [rdi]
0x18001df63  lea     r8, [rsi+38h]
0x18001df67  mov     edx, 2
0x18001df6c  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::vector<std::wstring> &)
0x18001df71  mov     rcx, [rdi]
0x18001df74  lea     r8, [rsi+18h]
0x18001df78  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$vector@_NV?$allocator@_N@std@@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::vector<bool> &)
0x18001df7d  mov     rcx, [rdi]
0x18001df80  lea     r8, [rsi+50h]
0x18001df84  mov     edx, 4
0x18001df89  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::vector<std::wstring> &)
0x18001df8e  mov     rcx, [rdi]
0x18001df91  lea     r8, [rsi+68h]
0x18001df95  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::vector<std::vector<ushort>> &)
0x18001df9a  mov     rcx, [rsi+40h]
0x18001df9e  sub     rcx, [rsi+38h]
0x18001dfa2  mov     rax, [rsi+8]
0x18001dfa6  sub     rax, [rsi]
0x18001dfa9  sar     rcx, 5
0x18001dfad  sar     rax, 2
0x18001dfb1  cmp     rcx, rax
0x18001dfb4  jnz     short loc_18001DFF0
0x18001dfb6  cmp     rcx, [rsi+30h]
0x18001dfba  jnz     short loc_18001DFF0
0x18001dfbc  mov     rax, [rsi+58h]
0x18001dfc0  sub     rax, [rsi+50h]
0x18001dfc4  sar     rax, 5
0x18001dfc8  cmp     rcx, rax
0x18001dfcb  jnz     short loc_18001DFF0
0x18001dfcd  mov     rax, [rsi+70h]
0x18001dfd1  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18001dfdb  sub     rax, [rsi+68h]
0x18001dfdf  sar     rax, 3
0x18001dfe3  imul    rax, rdx
0x18001dfe7  cmp     rcx, rax
0x18001dfea  jz      loc_18001E078
0x18001dff0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dff7  lea     rax, WPP_GLOBAL_Control
0x18001dffe  mov     ebx, 0Dh
0x18001e003  cmp     rcx, rax
0x18001e006  jz      short loc_18001E02A
0x18001e008  test    byte ptr [rcx+1Ch], 80h
0x18001e00c  jz      short loc_18001E02A
0x18001e00e  cmp     byte ptr [rcx+19h], 2
0x18001e012  jb      short loc_18001E02A
0x18001e014  mov     rcx, [rcx+10h]
0x18001e018  lea     edx, [rbx+9]
0x18001e01b  mov     r9d, ebx
0x18001e01e  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18001e025  call    WPP_SF_D
0x18001e02a  xor     ecx, ecx
0x18001e02c  mov     [rsp+88h+var_40], ebx
0x18001e030  lea     rax, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x18001e037  mov     [rsp+88h+var_60], cl
0x18001e03b  mov     [rsp+88h+var_58], rax
0x18001e040  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001e047  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001e04e  mov     [rsp+88h+var_50], rcx
0x18001e053  mov     [rsp+88h+var_48], rcx
0x18001e058  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18001e05d  mov     [rsp+88h+pExceptionObject], rax
0x18001e062  mov     [rsp+88h+var_3C], 0FFFFFFFFh
0x18001e06a  mov     [rsp+88h+var_38], 29Bh
0x18001e072  call    _CxxThrowException_0
0x18001e078  add     rsp, 60h
0x18001e07c  pop     r14
0x18001e07e  pop     rdi
0x18001e07f  pop     rsi
0x18001e080  pop     rbp
0x18001e081  pop     rbx
0x18001e082  retn
```
