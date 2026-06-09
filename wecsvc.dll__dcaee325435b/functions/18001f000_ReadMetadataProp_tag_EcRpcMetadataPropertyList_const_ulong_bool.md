# ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,bool &)

- ea: `0x18001f000`
- end: `0x18001f0d1`
- name: `?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEA_N@Z`
- size: `209`
- prototype: `bool __fastcall(const struct tag_EcRpcMetadataPropertyList *, unsigned int, bool *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008828`
- `0x180009a10`
- `0x18000a938`
- `0x1800165c0`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18001f000`

## string_xrefs

- `0x18001f062`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
bool __fastcall ReadMetadataProp(const struct tag_EcRpcMetadataPropertyList *a1, unsigned int a2, bool *a3)
{
  __int64 v3; // rdx
  __int64 v4; // rax
  bool v5; // zf
  bool result; // al
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
  v3 = 3LL * a2;
  v4 = *((_QWORD *)a1 + 1);
  if ( !*(_DWORD *)(v4 + 8 * v3) )
    return 0;
  if ( *(_DWORD *)(v4 + 8 * v3) != 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 87);
    }
    v8 = 0;
    v9 = "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp";
    v10 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v11 = 0;
    v12 = 87;
    v13 = -1;
    v14 = 223;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v5 = *(_BYTE *)(v4 + 8 * v3 + 8) == 1;
  result = 1;
  *a3 = v5;
  return result;
}

```

## disassembly

```asm
0x18001f000  sub     rsp, 68h
0x18001f004  cmp     edx, [rcx]
0x18001f006  jnb     loc_18001F0CA
0x18001f00c  mov     eax, edx
0x18001f00e  lea     rdx, [rax+rax*2]
0x18001f012  mov     rax, [rcx+8]
0x18001f016  cmp     dword ptr [rax+rdx*8], 0
0x18001f01a  jz      loc_18001F0CA
0x18001f020  cmp     dword ptr [rax+rdx*8], 1
0x18001f024  jz      loc_18001F0BB
0x18001f02a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f031  lea     rax, WPP_GLOBAL_Control
0x18001f038  cmp     rcx, rax
0x18001f03b  jz      short loc_18001F062
0x18001f03d  test    byte ptr [rcx+1Ch], 80h
0x18001f041  jz      short loc_18001F062
0x18001f043  cmp     byte ptr [rcx+19h], 2
0x18001f047  jb      short loc_18001F062
0x18001f049  mov     rcx, [rcx+10h]
0x18001f04d  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18001f054  mov     edx, 0Bh
0x18001f059  lea     r9d, [rdx+4Ch]
0x18001f05d  call    WPP_SF_D
0x18001f062  lea     rax, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x18001f069  mov     [rsp+68h+var_40], 0
0x18001f06e  mov     [rsp+68h+var_38], rax
0x18001f073  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001f07a  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001f081  mov     [rsp+68h+var_30], 0
0x18001f08a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001f08f  mov     [rsp+68h+pExceptionObject], rax
0x18001f094  mov     [rsp+68h+var_28], 0
0x18001f09d  mov     [rsp+68h+var_20], 57h ; 'W'
0x18001f0a5  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x18001f0ad  mov     [rsp+68h+var_18], 0DFh
0x18001f0b5  call    _CxxThrowException_0
0x18001f0bb  cmp     byte ptr [rax+rdx*8+8], 1
0x18001f0c0  mov     al, 1
0x18001f0c2  setz    cl
0x18001f0c5  mov     [r8], cl
0x18001f0c8  jmp     short loc_18001F0CC
0x18001f0ca  xor     al, al
0x18001f0cc  add     rsp, 68h
0x18001f0d0  retn
```
