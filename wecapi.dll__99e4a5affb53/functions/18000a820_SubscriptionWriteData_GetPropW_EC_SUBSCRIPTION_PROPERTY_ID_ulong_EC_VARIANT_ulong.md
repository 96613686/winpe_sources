# SubscriptionWriteData::GetPropW(_EC_SUBSCRIPTION_PROPERTY_ID,ulong,_EC_VARIANT *,ulong &)

- ea: `0x18000a820`
- end: `0x18000aa35`
- name: `?GetPropW@SubscriptionWriteData@@QEAAKW4_EC_SUBSCRIPTION_PROPERTY_ID@@KPEAU_EC_VARIANT@@AEAK@Z`
- size: `533`
- prototype: `__int64 __fastcall(SubscriptionWriteData *this, unsigned int, unsigned int, struct _EC_VARIANT *, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800066c4`
- `0x180007aa0`

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x1800027ac`
- `0x1800098f8`
- `0x18000a820`
- `0x18000aea4`
- `0x18000b514`

## string_xrefs

- `0x18000a9af`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`
- `0x18000aa12`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
__int64 __fastcall SubscriptionWriteData::GetPropW(
        SubscriptionWriteData *this,
        unsigned int a2,
        unsigned int a3,
        struct _EC_VARIANT *a4,
        unsigned int *a5)
{
  __int64 v6; // r8
  __int64 v7; // rax
  unsigned __int64 v8; // rdx
  unsigned int v9; // eax
  unsigned int v10; // eax
  void **pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  unsigned int v13; // [rsp+28h] [rbp-38h]
  struct _EC_VARIANT *v14; // [rsp+30h] [rbp-30h]
  unsigned int v15; // [rsp+38h] [rbp-28h]
  char v16; // [rsp+40h] [rbp-20h]

  if ( a2 >= **(_DWORD **)this )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 87);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)&pExceptionObject,
      0x57u,
      "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp",
      1046);
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v6 = *(_QWORD *)(*(_QWORD *)this + 8LL) + 24LL * (int)a2;
  if ( *(_DWORD *)v6 != 4 )
  {
    *a5 = 16;
    if ( a3 < 0x10 )
      return 122;
  }
  switch ( *(_DWORD *)v6 )
  {
    case 0:
      a4->Type = 0;
      return 0;
    case 1:
      a4->BooleanVal = *(unsigned __int8 *)(v6 + 8);
      a4->Type = 1;
      return 0;
    case 2:
      a4->BooleanVal = *(_DWORD *)(v6 + 8);
      a4->Type = 2;
      return 0;
    case 3:
      a4->DateTimeVal = *(_QWORD *)(v6 + 8);
      a4->Type = 3;
      return 0;
  }
  if ( *(_DWORD *)v6 != 4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 87);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)&pExceptionObject,
      0x57u,
      "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp",
      1122);
    throw (wmi::GenericException *)&pExceptionObject;
  }
  if ( a2 - 28 <= 2 )
  {
    pExceptionObject = &Buffer::`vftable';
    v15 = 0;
    v16 = 0;
    v14 = a4;
    v13 = a3;
    WriteCommaDelimitedStringToVariantBuffer((struct Buffer *)&pExceptionObject, (struct tag_EcRpcMetadataProperty *)v6);
    v10 = v15;
    *a5 = v15;
    if ( a3 >= v10 )
    {
      Buffer::~Buffer((Buffer *)&pExceptionObject);
      return 0;
    }
    Buffer::~Buffer((Buffer *)&pExceptionObject);
    return 122;
  }
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(*(_QWORD *)(v6 + 8) + 2 * v7) );
  v8 = (unsigned int)(v7 + 1);
  v9 = 2 * v8 + 16;
  *a5 = v9;
  if ( a3 < v9 )
    return 122;
  a4->DateTimeVal = (ULONGLONG)&a4[1];
  a4->Type = 4;
  StringCchCopyW((unsigned __int16 *)&a4[1], v8, *(const unsigned __int16 **)(v6 + 8));
  return 0;
}

```

## disassembly

```asm
0x18000a820  mov     [rsp-8+arg_0], rbx
0x18000a825  mov     [rsp-8+arg_8], rdi
0x18000a82a  push    rbp
0x18000a82b  mov     rbp, rsp
0x18000a82e  sub     rsp, 60h
0x18000a832  mov     ebx, r8d
0x18000a835  mov     r8, [rcx]
0x18000a838  cmp     edx, [r8]
0x18000a83b  jnb     loc_18000A9D2
0x18000a841  movsxd  rax, edx
0x18000a844  lea     rcx, [rax+rax*2]
0x18000a848  mov     rax, [r8+8]
0x18000a84c  lea     r8, [rax+rcx*8]
0x18000a850  mov     rdi, [rbp+arg_20]
0x18000a854  cmp     dword ptr [r8], 4
0x18000a858  jz      short loc_18000A869
0x18000a85a  mov     dword ptr [rdi], 10h
0x18000a860  cmp     ebx, 10h
0x18000a863  jb      loc_18000A917
0x18000a869  mov     ecx, [r8]
0x18000a86c  xor     r10d, r10d
0x18000a86f  test    ecx, ecx
0x18000a871  jz      loc_18000A959
0x18000a877  sub     ecx, 1
0x18000a87a  jz      loc_18000A947
0x18000a880  sub     ecx, 1
0x18000a883  jz      loc_18000A936
0x18000a889  sub     ecx, 1
0x18000a88c  jz      loc_18000A925
0x18000a892  cmp     ecx, 1
0x18000a895  jnz     loc_18000A96F
0x18000a89b  lea     eax, [rdx-1Ch]
0x18000a89e  cmp     eax, 2
0x18000a8a1  jbe     short loc_18000A8DF
0x18000a8a3  mov     rcx, [r8+8]
0x18000a8a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a8ab  inc     rax
0x18000a8ae  cmp     [rcx+rax*2], r10w
0x18000a8b3  jnz     short loc_18000A8AB
0x18000a8b5  lea     edx, [rax+1]; unsigned __int64
0x18000a8b8  lea     eax, ds:10h[rdx*2]
0x18000a8bf  mov     [rdi], eax
0x18000a8c1  cmp     ebx, eax
0x18000a8c3  jb      short loc_18000A917
0x18000a8c5  lea     rcx, [r9+10h]; unsigned __int16 *
0x18000a8c9  mov     [r9], rcx
0x18000a8cc  mov     dword ptr [r9+0Ch], 4
0x18000a8d4  mov     r8, [r8+8]; unsigned __int16 *
0x18000a8d8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a8dd  jmp     short loc_18000A95D
0x18000a8df  lea     rax, ??_7Buffer@@6B@; const Buffer::`vftable'
0x18000a8e6  mov     [rbp+pExceptionObject], rax
0x18000a8ea  mov     [rbp+var_28], r10d
0x18000a8ee  mov     [rbp+var_20], r10b
0x18000a8f2  mov     [rbp+var_30], r9
0x18000a8f6  mov     [rbp+var_38], ebx
0x18000a8f9  mov     rdx, r8; struct tag_EcRpcMetadataProperty *
0x18000a8fc  lea     rcx, [rbp+pExceptionObject]; struct Buffer *
0x18000a900  call    ?WriteCommaDelimitedStringToVariantBuffer@@YAXAEAVBuffer@@AEAUtag_EcRpcMetadataProperty@@@Z; WriteCommaDelimitedStringToVariantBuffer(Buffer &,tag_EcRpcMetadataProperty &)
0x18000a905  mov     eax, [rbp+var_28]
0x18000a908  mov     [rdi], eax
0x18000a90a  lea     rcx, [rbp+pExceptionObject]; this
0x18000a90e  cmp     ebx, eax
0x18000a910  jnb     short loc_18000A91E
0x18000a912  call    ??1Buffer@@QEAA@XZ; Buffer::~Buffer(void)
0x18000a917  mov     eax, 7Ah ; 'z'
0x18000a91c  jmp     short loc_18000A95F
0x18000a91e  call    ??1Buffer@@QEAA@XZ; Buffer::~Buffer(void)
0x18000a923  jmp     short loc_18000A95D
0x18000a925  mov     rax, [r8+8]
0x18000a929  mov     [r9], rax
0x18000a92c  mov     dword ptr [r9+0Ch], 3
0x18000a934  jmp     short loc_18000A95D
0x18000a936  mov     eax, [r8+8]
0x18000a93a  mov     [r9], eax
0x18000a93d  mov     dword ptr [r9+0Ch], 2
0x18000a945  jmp     short loc_18000A95D
0x18000a947  movzx   eax, byte ptr [r8+8]
0x18000a94c  mov     [r9], eax
0x18000a94f  mov     dword ptr [r9+0Ch], 1
0x18000a957  jmp     short loc_18000A95D
0x18000a959  mov     [r9+0Ch], r10d
0x18000a95d  xor     eax, eax
0x18000a95f  mov     rbx, [rsp+60h+arg_0]
0x18000a964  mov     rdi, [rsp+60h+arg_8]
0x18000a969  add     rsp, 60h
0x18000a96d  pop     rbp
0x18000a96e  retn
0x18000a96f  lea     rax, WPP_GLOBAL_Control
0x18000a976  mov     ebx, 57h ; 'W'
0x18000a97b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a982  cmp     rcx, rax
0x18000a985  jz      short loc_18000A9A9
0x18000a987  test    byte ptr [rcx+1Ch], 80h
0x18000a98b  jz      short loc_18000A9A9
0x18000a98d  cmp     byte ptr [rcx+19h], 2
0x18000a991  jb      short loc_18000A9A9
0x18000a993  lea     edx, [rbx-3Dh]
0x18000a996  mov     r9d, ebx
0x18000a999  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18000a9a0  mov     rcx, [rcx+10h]
0x18000a9a4  call    WPP_SF_D
0x18000a9a9  mov     r9d, 462h; int
0x18000a9af  lea     r8, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\collect"...
0x18000a9b6  mov     edx, ebx; unsigned int
0x18000a9b8  lea     rcx, [rbp+pExceptionObject]; this
0x18000a9bc  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000a9c1  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000a9c8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000a9cc  call    _CxxThrowException_0
0x18000a9d2  lea     rax, WPP_GLOBAL_Control
0x18000a9d9  mov     ebx, 57h ; 'W'
0x18000a9de  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9e5  cmp     rcx, rax
0x18000a9e8  jz      short loc_18000AA0C
0x18000a9ea  test    byte ptr [rcx+1Ch], 80h
0x18000a9ee  jz      short loc_18000AA0C
0x18000a9f0  cmp     byte ptr [rcx+19h], 2
0x18000a9f4  jb      short loc_18000AA0C
0x18000a9f6  lea     edx, [rbx-3Eh]
0x18000a9f9  mov     r9d, ebx
0x18000a9fc  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18000aa03  mov     rcx, [rcx+10h]
0x18000aa07  call    WPP_SF_D
0x18000aa0c  mov     r9d, 416h; int
0x18000aa12  lea     r8, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\collect"...
0x18000aa19  mov     edx, ebx; unsigned int
0x18000aa1b  lea     rcx, [rbp+pExceptionObject]; this
0x18000aa1f  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000aa24  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000aa2b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000aa2f  call    _CxxThrowException_0
```
