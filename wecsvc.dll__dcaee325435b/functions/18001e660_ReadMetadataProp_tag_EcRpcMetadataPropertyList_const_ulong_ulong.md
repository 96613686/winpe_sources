# ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)

- ea: `0x18001e660`
- end: `0x18001e72d`
- name: `?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z`
- size: `205`
- prototype: `char __fastcall(const struct tag_EcRpcMetadataPropertyList *, unsigned int, unsigned int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008828`
- `0x180009a10`
- `0x18000a938`
- `0x1800165c0`
- `0x180017b8c`
- `0x18001de6c`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18001e660`

## string_xrefs

- `0x18001e6c2`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
char __fastcall ReadMetadataProp(const struct tag_EcRpcMetadataPropertyList *a1, unsigned int a2, unsigned int *a3)
{
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // rax
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v8; // [rsp+28h] [rbp-40h]
  const char *v9; // [rsp+30h] [rbp-38h]
  __int64 v10; // [rsp+38h] [rbp-30h]
  __int64 v11; // [rsp+40h] [rbp-28h]
  int v12; // [rsp+48h] [rbp-20h]
  int v13; // [rsp+4Ch] [rbp-1Ch]
  int v14; // [rsp+50h] [rbp-18h]

  if ( a2 >= *(_DWORD *)a1 )
    return 0;
  v3 = a2;
  v4 = *((_QWORD *)a1 + 1);
  v5 = 3 * v3;
  if ( !*(_DWORD *)(v4 + 8 * v5) )
    return 0;
  if ( *(_DWORD *)(v4 + 8 * v5) != 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 87);
    }
    v8 = 0;
    v9 = "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp";
    v10 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v11 = 0;
    v12 = 87;
    v13 = -1;
    v14 = 241;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  *a3 = *(_DWORD *)(v4 + 8 * v5 + 8);
  return 1;
}

```

## disassembly

```asm
0x18001e660  sub     rsp, 68h
0x18001e664  cmp     edx, [rcx]
0x18001e666  jnb     loc_18001E726
0x18001e66c  mov     eax, edx
0x18001e66e  mov     rdx, [rcx+8]
0x18001e672  lea     rax, [rax+rax*2]
0x18001e676  cmp     dword ptr [rdx+rax*8], 0
0x18001e67a  jz      loc_18001E726
0x18001e680  cmp     dword ptr [rdx+rax*8], 2
0x18001e684  jz      loc_18001E71B
0x18001e68a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e691  lea     rax, WPP_GLOBAL_Control
0x18001e698  cmp     rcx, rax
0x18001e69b  jz      short loc_18001E6C2
0x18001e69d  test    byte ptr [rcx+1Ch], 80h
0x18001e6a1  jz      short loc_18001E6C2
0x18001e6a3  cmp     byte ptr [rcx+19h], 2
0x18001e6a7  jb      short loc_18001E6C2
0x18001e6a9  mov     rcx, [rcx+10h]
0x18001e6ad  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18001e6b4  mov     edx, 0Ch
0x18001e6b9  lea     r9d, [rdx+4Bh]
0x18001e6bd  call    WPP_SF_D
0x18001e6c2  lea     rax, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x18001e6c9  mov     [rsp+68h+var_40], 0
0x18001e6ce  mov     [rsp+68h+var_38], rax
0x18001e6d3  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001e6da  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001e6e1  mov     [rsp+68h+var_30], 0
0x18001e6ea  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001e6ef  mov     [rsp+68h+pExceptionObject], rax
0x18001e6f4  mov     [rsp+68h+var_28], 0
0x18001e6fd  mov     [rsp+68h+var_20], 57h ; 'W'
0x18001e705  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x18001e70d  mov     [rsp+68h+var_18], 0F1h
0x18001e715  call    _CxxThrowException_0
0x18001e71b  mov     eax, [rdx+rax*8+8]
0x18001e71f  mov     [r8], eax
0x18001e722  mov     al, 1
0x18001e724  jmp     short loc_18001E728
0x18001e726  xor     al, al
0x18001e728  add     rsp, 68h
0x18001e72c  retn
```
