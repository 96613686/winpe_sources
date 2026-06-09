# ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,_FILETIME &)

- ea: `0x18001e734`
- end: `0x18001e802`
- name: `?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAU_FILETIME@@@Z`
- size: `206`
- prototype: `char __fastcall(const struct tag_EcRpcMetadataPropertyList *, __int64, struct _FILETIME *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008828`
- `0x180009170`
- `0x180009a10`
- `0x1800165c0`
- `0x180017b8c`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18001e734`

## string_xrefs

- `0x18001e794`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
char __fastcall ReadMetadataProp(const struct tag_EcRpcMetadataPropertyList *a1, __int64 a2, struct _FILETIME *a3)
{
  struct _FILETIME *v3; // rax
  DWORD dwLowDateTime; // ecx
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v7; // [rsp+28h] [rbp-40h]
  const char *v8; // [rsp+30h] [rbp-38h]
  __int64 v9; // [rsp+38h] [rbp-30h]
  __int64 v10; // [rsp+40h] [rbp-28h]
  int v11; // [rsp+48h] [rbp-20h]
  int v12; // [rsp+4Ch] [rbp-1Ch]
  int v13; // [rsp+50h] [rbp-18h]

  if ( *(_DWORD *)a1 <= 9u )
    return 0;
  v3 = (struct _FILETIME *)*((_QWORD *)a1 + 1);
  dwLowDateTime = v3[27].dwLowDateTime;
  if ( !dwLowDateTime )
    return 0;
  if ( dwLowDateTime != 3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 87);
    }
    v7 = 0;
    v8 = "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp";
    v9 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v10 = 0;
    v11 = 87;
    v12 = -1;
    v13 = 311;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  *a3 = v3[28];
  return 1;
}

```

## disassembly

```asm
0x18001e734  sub     rsp, 68h
0x18001e738  cmp     dword ptr [rcx], 9
0x18001e73b  jbe     loc_18001E7FB
0x18001e741  mov     rax, [rcx+8]
0x18001e745  mov     ecx, [rax+0D8h]
0x18001e74b  test    ecx, ecx
0x18001e74d  jz      loc_18001E7FB
0x18001e753  cmp     ecx, 3
0x18001e756  jz      loc_18001E7ED
0x18001e75c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e763  lea     rax, WPP_GLOBAL_Control
0x18001e76a  cmp     rcx, rax
0x18001e76d  jz      short loc_18001E794
0x18001e76f  test    byte ptr [rcx+1Ch], 80h
0x18001e773  jz      short loc_18001E794
0x18001e775  cmp     byte ptr [rcx+19h], 2
0x18001e779  jb      short loc_18001E794
0x18001e77b  mov     rcx, [rcx+10h]
0x18001e77f  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18001e786  mov     edx, 10h
0x18001e78b  lea     r9d, [rdx+47h]
0x18001e78f  call    WPP_SF_D
0x18001e794  lea     rax, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x18001e79b  mov     [rsp+68h+var_40], 0
0x18001e7a0  mov     [rsp+68h+var_38], rax
0x18001e7a5  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001e7ac  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001e7b3  mov     [rsp+68h+var_30], 0
0x18001e7bc  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001e7c1  mov     [rsp+68h+pExceptionObject], rax
0x18001e7c6  mov     [rsp+68h+var_28], 0
0x18001e7cf  mov     [rsp+68h+var_20], 57h ; 'W'
0x18001e7d7  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x18001e7df  mov     [rsp+68h+var_18], 137h
0x18001e7e7  call    _CxxThrowException_0
0x18001e7ed  mov     rax, [rax+0E0h]
0x18001e7f4  mov     [r8], rax
0x18001e7f7  mov     al, 1
0x18001e7f9  jmp     short loc_18001E7FD
0x18001e7fb  xor     al, al
0x18001e7fd  add     rsp, 68h
0x18001e801  retn
```
