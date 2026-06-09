# ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)

- ea: `0x18000acec`
- end: `0x18000ad82`
- name: `?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z`
- size: `150`
- prototype: `bool __fastcall(const struct tag_EcRpcMetadataPropertyList *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007aa0`

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x1800027ac`
- `0x18000acec`

## string_xrefs

- `0x18000ad5a`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
char __fastcall ReadMetadataProp(const struct tag_EcRpcMetadataPropertyList *a1, __int64 a2, unsigned int *a3)
{
  __int64 v3; // rax
  int v4; // ecx
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF

  if ( *(_DWORD *)a1 <= 8u )
    return 0;
  v3 = *((_QWORD *)a1 + 1);
  v4 = *(_DWORD *)(v3 + 192);
  if ( !v4 )
    return 0;
  if ( v4 != 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 87);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      0x57u,
      "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp",
      241);
    throw (wmi::GenericException *)pExceptionObject;
  }
  *a3 = *(_DWORD *)(v3 + 200);
  return 1;
}

```

## disassembly

```asm
0x18000acec  sub     rsp, 68h
0x18000acf0  cmp     dword ptr [rcx], 8
0x18000acf3  jbe     short loc_18000AD15
0x18000acf5  mov     rax, [rcx+8]
0x18000acf9  mov     ecx, [rax+0C0h]
0x18000acff  test    ecx, ecx
0x18000ad01  jz      short loc_18000AD15
0x18000ad03  cmp     ecx, 2
0x18000ad06  jnz     short loc_18000AD1C
0x18000ad08  mov     eax, [rax+0C8h]
0x18000ad0e  mov     [r8], eax
0x18000ad11  mov     al, 1
0x18000ad13  jmp     short loc_18000AD17
0x18000ad15  xor     al, al
0x18000ad17  add     rsp, 68h
0x18000ad1b  retn
0x18000ad1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad23  lea     rax, WPP_GLOBAL_Control
0x18000ad2a  cmp     rcx, rax
0x18000ad2d  jz      short loc_18000AD54
0x18000ad2f  test    byte ptr [rcx+1Ch], 80h
0x18000ad33  jz      short loc_18000AD54
0x18000ad35  cmp     byte ptr [rcx+19h], 2
0x18000ad39  jb      short loc_18000AD54
0x18000ad3b  mov     rcx, [rcx+10h]
0x18000ad3f  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18000ad46  mov     edx, 0Ch
0x18000ad4b  lea     r9d, [rdx+4Bh]
0x18000ad4f  call    WPP_SF_D
0x18000ad54  mov     r9d, 0F1h; int
0x18000ad5a  lea     r8, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\collect"...
0x18000ad61  mov     edx, 57h ; 'W'; unsigned int
0x18000ad66  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000ad6b  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000ad70  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000ad77  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000ad7c  call    _CxxThrowException_0
```
