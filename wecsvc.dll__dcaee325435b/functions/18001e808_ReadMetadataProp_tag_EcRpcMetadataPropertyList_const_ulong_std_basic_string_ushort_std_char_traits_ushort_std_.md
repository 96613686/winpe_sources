# ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001e808`
- end: `0x18001e8e9`
- name: `?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `225`
- prototype: `char __fastcall(__int64, unsigned int, __int64)`
- caller_count: `14`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800165c0`
- `0x18001dd2c`
- `0x18001dd6c`
- `0x18001ddac`
- `0x18001de2c`
- `0x18001dec4`
- `0x18001df04`
- `0x18001e08c`
- `0x18001e0cc`
- `0x18001e10c`
- `0x18001e14c`
- `0x18001e18c`
- `0x18001e1cc`
- `0x18001e20c`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18000669c`
- `0x18001e808`

## string_xrefs

- `0x18001e86a`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
char __fastcall ReadMetadataProp(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // rax
  const wchar_t *v6; // rax
  const wchar_t *v7; // rdx
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v10; // [rsp+28h] [rbp-40h]
  const char *v11; // [rsp+30h] [rbp-38h]
  __int64 v12; // [rsp+38h] [rbp-30h]
  __int64 v13; // [rsp+40h] [rbp-28h]
  int v14; // [rsp+48h] [rbp-20h]
  int v15; // [rsp+4Ch] [rbp-1Ch]
  int v16; // [rsp+50h] [rbp-18h]

  if ( a2 >= *(_DWORD *)a1 )
    return 0;
  v3 = a2;
  v4 = *(_QWORD *)(a1 + 8);
  v5 = 3 * v3;
  if ( !*(_DWORD *)(v4 + 8 * v5) )
    return 0;
  if ( *(_DWORD *)(v4 + 8 * v5) != 4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 87);
    }
    v10 = 0;
    v11 = "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp";
    v12 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v13 = 0;
    v14 = 87;
    v15 = -1;
    v16 = 259;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v6 = *(const wchar_t **)(v4 + 8 * v5 + 8);
  v7 = &word_180026AD8;
  if ( v6 )
    v7 = v6;
  std::wstring::assign(a3, v7);
  return 1;
}

```

## disassembly

```asm
0x18001e808  sub     rsp, 68h
0x18001e80c  cmp     edx, [rcx]
0x18001e80e  jnb     loc_18001E8E2
0x18001e814  mov     eax, edx
0x18001e816  mov     rdx, [rcx+8]
0x18001e81a  lea     rax, [rax+rax*2]
0x18001e81e  cmp     dword ptr [rdx+rax*8], 0
0x18001e822  jz      loc_18001E8E2
0x18001e828  cmp     dword ptr [rdx+rax*8], 4
0x18001e82c  jz      loc_18001E8C3
0x18001e832  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e839  lea     rax, WPP_GLOBAL_Control
0x18001e840  cmp     rcx, rax
0x18001e843  jz      short loc_18001E86A
0x18001e845  test    byte ptr [rcx+1Ch], 80h
0x18001e849  jz      short loc_18001E86A
0x18001e84b  cmp     byte ptr [rcx+19h], 2
0x18001e84f  jb      short loc_18001E86A
0x18001e851  mov     rcx, [rcx+10h]
0x18001e855  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18001e85c  mov     edx, 0Dh
0x18001e861  lea     r9d, [rdx+4Ah]
0x18001e865  call    WPP_SF_D
0x18001e86a  lea     rax, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x18001e871  mov     [rsp+68h+var_40], 0
0x18001e876  mov     [rsp+68h+var_38], rax
0x18001e87b  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001e882  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001e889  mov     [rsp+68h+var_30], 0
0x18001e892  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001e897  mov     [rsp+68h+pExceptionObject], rax
0x18001e89c  mov     [rsp+68h+var_28], 0
0x18001e8a5  mov     [rsp+68h+var_20], 57h ; 'W'
0x18001e8ad  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x18001e8b5  mov     [rsp+68h+var_18], 103h
0x18001e8bd  call    _CxxThrowException_0
0x18001e8c3  mov     rax, [rdx+rax*8+8]
0x18001e8c8  mov     rcx, r8
0x18001e8cb  test    rax, rax
0x18001e8ce  lea     rdx, word_180026AD8
0x18001e8d5  cmovnz  rdx, rax
0x18001e8d9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001e8de  mov     al, 1
0x18001e8e0  jmp     short loc_18001E8E4
0x18001e8e2  xor     al, al
0x18001e8e4  add     rsp, 68h
0x18001e8e8  retn
```
