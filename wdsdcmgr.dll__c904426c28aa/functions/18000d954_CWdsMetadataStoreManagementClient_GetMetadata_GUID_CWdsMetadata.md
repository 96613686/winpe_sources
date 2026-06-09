# CWdsMetadataStoreManagementClient::GetMetadata(_GUID,CWdsMetadata *)

- ea: `0x18000d954`
- end: `0x18000daae`
- name: `?GetMetadata@CWdsMetadataStoreManagementClient@@QEAAKU_GUID@@PEAVCWdsMetadata@@@Z`
- size: `346`
- prototype: `unsigned int(CWdsMetadataStoreManagementClient *__hidden this, struct _GUID *__struct_ptr, struct CWdsMetadata *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180002268`

## callees

- `0x18000d954`
- `0x1800115e4`
- `0x180012640`
- `0x1800126f8`
- `0x180012c84`
- `0x180014d58`
- `0x180015660`
- `0x180015cc0`

## string_xrefs

- `0x18000d9b2`: `base\eco\wds\lib\metadata\com\wdsmetadatastoremanagementclient.cpp`

## pseudocode

```c
__int64 __fastcall CWdsMetadataStoreManagementClient::GetMetadata(
        __int64 (__fastcall **this)(int *, __int128 *),
        struct _GUID *a2,
        struct CWdsMetadata *a3)
{
  unsigned int Metadata; // ebx
  const char *v7; // rdx
  const char *v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  const char *v11; // rdx
  const char *v12; // rdx
  const unsigned __int16 *v13; // rdx
  unsigned int v14; // r9d
  const char *v15; // rdx
  int v17; // [rsp+20h] [rbp-49h]
  int v18; // [rsp+28h] [rbp-41h]
  __int128 Src; // [rsp+40h] [rbp-29h] BYREF
  __int128 v20; // [rsp+50h] [rbp-19h] BYREF
  __int64 v21; // [rsp+60h] [rbp-9h]
  int v22; // [rsp+68h] [rbp-1h]
  int v23[4]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v24; // [rsp+80h] [rbp+17h]
  int v25; // [rsp+88h] [rbp+1Fh]

  v24 = 0;
  v25 = 0;
  v21 = 0;
  v22 = 0;
  *(_OWORD *)v23 = 0;
  v20 = 0;
  Metadata = CControlPacket::SendInitialize((CControlPacket *)v23, 0, 0xBu, 2u);
  if ( !ElValidateWin32(
          Metadata,
          v7,
          "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
          0x25Du) )
  {
    Metadata = CControlPacket::SendInitialize((CControlPacket *)&v20, 0, 0, 2u);
    if ( !ElValidateWin32(
            Metadata,
            v8,
            "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
            0x260u) )
    {
      Src = (__int128)*a2;
      Metadata = CControlPacket::AddVariable<unsigned char>((__int64)v23, (__int64)L"O", v9, v10, v17, v18, &Src);
      if ( !ElValidateWin32(
              Metadata,
              v11,
              "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
              0x263u) )
      {
        Metadata = this[1](v23, &v20);
        if ( !ElValidateWin32(
                Metadata,
                v12,
                "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
                0x266u) )
        {
          Metadata = CWdsMetadataStorePacket::GetMetadata((CWdsMetadataStorePacket *)&v20, v13, a3, v14);
          ElValidateWin32(
            Metadata,
            v15,
            "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
            0x269u);
        }
      }
    }
  }
  CControlPacket::~CControlPacket((CControlPacket *)&v20);
  CControlPacket::~CControlPacket((CControlPacket *)v23);
  return Metadata;
}

```

## disassembly

```asm
0x18000d954  mov     [rsp-8+arg_18], rbx
0x18000d959  push    rbp
0x18000d95a  push    rsi
0x18000d95b  push    rdi
0x18000d95c  push    r14
0x18000d95e  push    r15
0x18000d960  lea     rbp, [rsp-37h]
0x18000d965  sub     rsp, 0A0h
0x18000d96c  mov     rax, cs:__security_cookie
0x18000d973  xor     rax, rsp
0x18000d976  mov     [rbp+57h+var_30], rax
0x18000d97a  xor     eax, eax
0x18000d97c  xorps   xmm0, xmm0
0x18000d97f  mov     rdi, r8
0x18000d982  mov     [rbp+57h+var_40], rax
0x18000d986  mov     rsi, rdx
0x18000d989  mov     [rbp+57h+var_38], eax
0x18000d98c  mov     r14, rcx
0x18000d98f  mov     [rbp+57h+var_60], rax
0x18000d993  lea     r8d, [rax+0Bh]; unsigned int
0x18000d997  mov     [rbp+57h+var_58], eax
0x18000d99a  mov     r9b, 2; unsigned __int8
0x18000d99d  lea     rcx, [rbp+57h+var_50]; this
0x18000d9a1  xor     edx, edx; void *
0x18000d9a3  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x18000d9a8  movdqu  [rbp+57h+var_70], xmm0
0x18000d9ad  call    ?SendInitialize@CControlPacket@@QEAAKPEAXKE@Z
0x18000d9b2  lea     r15, aBaseEcoWdsLibM_1
0x18000d9b9  mov     r9d, 25Dh; unsigned int
0x18000d9bf  mov     r8, r15; char *
0x18000d9c2  mov     ecx, eax; unsigned int
0x18000d9c4  mov     ebx, eax
0x18000d9c6  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d9cb  test    eax, eax
0x18000d9cd  jnz     loc_18000DA77
0x18000d9d3  mov     r9b, 2; unsigned __int8
0x18000d9d6  lea     rcx, [rbp+57h+var_70]; this
0x18000d9da  xor     r8d, r8d; unsigned int
0x18000d9dd  xor     edx, edx; void *
0x18000d9df  call    ?SendInitialize@CControlPacket@@QEAAKPEAXKE@Z
0x18000d9e4  mov     r9d, 260h; unsigned int
0x18000d9ea  mov     r8, r15; char *
0x18000d9ed  mov     ecx, eax; unsigned int
0x18000d9ef  mov     ebx, eax
0x18000d9f1  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d9f6  test    eax, eax
0x18000d9f8  jnz     short loc_18000DA77
0x18000d9fa  movaps  xmm0, xmmword ptr [rsi]
0x18000d9fd  lea     rax, [rbp+57h+var_80]
0x18000da01  lea     rdx, aO
0x18000da08  movdqa  [rbp+57h+var_80], xmm0
0x18000da0d  lea     rcx, [rbp+57h+var_50]; int
0x18000da11  mov     [rsp+0C0h+Src], rax; Src
0x18000da16  call    ??$AddVariable@E@CControlPacket@@QEAAKPEBG0KKKPEAX@Z
0x18000da1b  mov     r9d, 263h; unsigned int
0x18000da21  mov     r8, r15; char *
0x18000da24  mov     ecx, eax; unsigned int
0x18000da26  mov     ebx, eax
0x18000da28  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000da2d  test    eax, eax
0x18000da2f  jnz     short loc_18000DA77
0x18000da31  mov     rax, [r14+8]
0x18000da35  lea     rdx, [rbp+57h+var_70]
0x18000da39  lea     rcx, [rbp+57h+var_50]
0x18000da3d  call    cs:__guard_dispatch_icall_fptr
0x18000da43  mov     r9d, 266h; unsigned int
0x18000da49  mov     r8, r15; char *
0x18000da4c  mov     ecx, eax; unsigned int
0x18000da4e  mov     ebx, eax
0x18000da50  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000da55  test    eax, eax
0x18000da57  jnz     short loc_18000DA77
0x18000da59  mov     r8, rdi; struct CWdsMetadata *
0x18000da5c  lea     rcx, [rbp+57h+var_70]; this
0x18000da60  call    ?GetMetadata@CWdsMetadataStorePacket@@QEAAKPEBGPEAVCWdsMetadata@@@Z
0x18000da65  mov     r9d, 269h; unsigned int
0x18000da6b  mov     r8, r15; char *
0x18000da6e  mov     ecx, eax; unsigned int
0x18000da70  mov     ebx, eax
0x18000da72  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000da77  lea     rcx, [rbp+57h+var_70]; this
0x18000da7b  call    ??1CControlPacket@@QEAA@XZ
0x18000da80  lea     rcx, [rbp+57h+var_50]; this
0x18000da84  call    ??1CControlPacket@@QEAA@XZ
0x18000da89  mov     eax, ebx
0x18000da8b  mov     rcx, [rbp+57h+var_30]
0x18000da8f  xor     rcx, rsp; StackCookie
0x18000da92  call    __security_check_cookie
0x18000da97  mov     rbx, [rsp+0C0h+arg_18]
0x18000da9f  add     rsp, 0A0h
0x18000daa6  pop     r15
0x18000daa8  pop     r14
0x18000daaa  pop     rdi
0x18000daab  pop     rsi
0x18000daac  pop     rbp
0x18000daad  retn
```
