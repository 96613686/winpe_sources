# CWdsMetadataStoreManagementClient::Register(_GUID,ushort const *,int,_GUID,CWdsMetadata const *,CWdsMetadata const *,CWdsMetadata const *,CWdsMetadata const *)

- ea: `0x18000d540`
- end: `0x18000d7b6`
- name: `?Register@CWdsMetadataStoreManagementClient@@QEAAKU_GUID@@PEBGH0PEBVCWdsMetadata@@222@Z`
- size: `630`
- prototype: `unsigned int __fastcall(CWdsMetadataStoreManagementClient *__hidden this, struct _GUID *, const unsigned __int16 *, int, struct _GUID *, const struct CWdsMetadata *, const struct CWdsMetadata *, const struct CWdsMetadata *, const struct CWdsMetadata *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180001e14`

## callees

- `0x18000d540`
- `0x1800114a4`
- `0x180012640`
- `0x1800126f8`
- `0x18001284c`
- `0x180012910`
- `0x180012c84`
- `0x180014d58`
- `0x180015660`
- `0x180015cc0`

## string_xrefs

- `0x18000d5b8`: `base\eco\wds\lib\metadata\com\wdsmetadatastoremanagementclient.cpp`
- `0x18000d5e7`: `base\eco\wds\lib\metadata\com\wdsmetadatastoremanagementclient.cpp`
- `0x18000d620`: `base\eco\wds\lib\metadata\com\wdsmetadatastoremanagementclient.cpp`

## pseudocode

```c
__int64 __fastcall CWdsMetadataStoreManagementClient::Register(
        __int64 (__fastcall **this)(int *, __int128 *),
        struct _GUID *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        struct _GUID *a5,
        const struct CWdsMetadata *a6,
        const struct CWdsMetadata *a7,
        const struct CWdsMetadata *a8,
        const struct CWdsMetadata *a9)
{
  unsigned int v11; // ebx
  const char *v12; // rdx
  const char *v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  const char *v16; // rdx
  const char *v17; // rdx
  __int64 v18; // r9
  const char *v19; // rdx
  __int64 v20; // r9
  const char *v21; // rdx
  __int64 v22; // r9
  const char *v23; // rdx
  __int64 v24; // r9
  const char *v25; // rdx
  __int64 v26; // r9
  const char *v27; // rdx
  const char *v28; // rdx
  int v30; // [rsp+20h] [rbp-79h]
  int v31; // [rsp+28h] [rbp-71h]
  __int128 Src; // [rsp+40h] [rbp-59h] BYREF
  int v33[4]; // [rsp+50h] [rbp-49h] BYREF
  __int64 v34; // [rsp+60h] [rbp-39h]
  int v35; // [rsp+68h] [rbp-31h]
  __int128 v36; // [rsp+70h] [rbp-29h] BYREF
  __int64 v37; // [rsp+80h] [rbp-19h]
  int v38; // [rsp+88h] [rbp-11h]

  v34 = 0;
  v35 = 0;
  v37 = 0;
  v38 = 0;
  *(_OWORD *)v33 = 0;
  v36 = 0;
  v11 = CControlPacket::SendInitialize((CControlPacket *)v33, 0, 4u, 1u);
  if ( !ElValidateWin32(v11, v12, "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp", 0xD6u) )
  {
    v11 = CControlPacket::SendInitialize((CControlPacket *)&v36, 0, 0, 2u);
    if ( !ElValidateWin32(v11, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp", 0xD9u) )
    {
      Src = (__int128)*a2;
      v11 = CControlPacket::AddVariable<unsigned char>((__int64)v33, (__int64)L"O", v14, v15, v30, v31, &Src);
      if ( !ElValidateWin32(v11, v16, "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp", 0xDCu) )
      {
        v11 = CControlPacket::AddString((CControlPacket *)v33, (const char *)L"T", 0, -1, L"DefaultResponse");
        if ( !ElValidateWin32(
                v11,
                v17,
                "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
                0xDFu) )
        {
          v11 = CControlPacket::AddULONG((CControlPacket *)v33, L"PF", 0, v18, 0);
          if ( !ElValidateWin32(
                  v11,
                  v19,
                  "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
                  0xE2u) )
          {
            v11 = CWdsMetadataStorePacket::AddMetadata((CWdsMetadataStorePacket *)v33, L"DF", a6, v20);
            if ( !ElValidateWin32(
                    v11,
                    v21,
                    "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
                    0xEBu) )
            {
              v11 = CWdsMetadataStorePacket::AddMetadata((CWdsMetadataStorePacket *)v33, L"CU", a7, v22);
              if ( !ElValidateWin32(
                      v11,
                      v23,
                      "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
                      0xEEu) )
              {
                v11 = CWdsMetadataStorePacket::AddMetadata((CWdsMetadataStorePacket *)v33, L"WF", a8, v24);
                if ( !ElValidateWin32(
                        v11,
                        v25,
                        "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
                        0xF1u) )
                {
                  v11 = CWdsMetadataStorePacket::AddMetadata((CWdsMetadataStorePacket *)v33, L"IF", a9, v26);
                  if ( !ElValidateWin32(
                          v11,
                          v27,
                          "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
                          0xF4u) )
                  {
                    v11 = this[1](v33, &v36);
                    ElValidateWin32(
                      v11,
                      v28,
                      "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
                      0xF7u);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  CControlPacket::~CControlPacket((CControlPacket *)&v36);
  CControlPacket::~CControlPacket((CControlPacket *)v33);
  return v11;
}

```

## disassembly

```asm
0x18000d540  mov     [rsp-8+arg_10], rbx
0x18000d545  push    rbp
0x18000d546  push    rsi
0x18000d547  push    rdi
0x18000d548  push    r12
0x18000d54a  push    r13
0x18000d54c  push    r14
0x18000d54e  push    r15
0x18000d550  lea     rbp, [rsp-7]
0x18000d555  sub     rsp, 0A0h
0x18000d55c  mov     rax, cs:__security_cookie
0x18000d563  xor     rax, rsp
0x18000d566  mov     [rbp+37h+var_40], rax
0x18000d56a  mov     rsi, [rbp+37h+arg_28]
0x18000d56e  xor     eax, eax
0x18000d570  mov     r14, [rbp+37h+arg_30]
0x18000d574  xorps   xmm0, xmm0
0x18000d577  mov     r15, [rbp+37h+arg_38]
0x18000d57b  mov     rdi, rdx
0x18000d57e  mov     r12, [rbp+37h+arg_40]
0x18000d585  mov     r13, rcx
0x18000d588  lea     r8d, [rax+4]; unsigned int
0x18000d58c  mov     [rbp+37h+var_70], rax
0x18000d590  mov     r9b, 1; unsigned __int8
0x18000d593  mov     [rbp+37h+var_68], eax
0x18000d596  xor     edx, edx; void *
0x18000d598  mov     [rbp+37h+var_50], rax
0x18000d59c  lea     rcx, [rbp+37h+var_80]; this
0x18000d5a0  mov     [rbp+37h+var_48], eax
0x18000d5a3  movdqu  xmmword ptr [rbp+37h+var_80], xmm0
0x18000d5a8  movdqu  [rbp+37h+var_60], xmm0
0x18000d5ad  call    ?SendInitialize@CControlPacket@@QEAAKPEAXKE@Z
0x18000d5b2  mov     r9d, 0D6h; unsigned int
0x18000d5b8  lea     r8, aBaseEcoWdsLibM_1
0x18000d5bf  mov     ecx, eax; unsigned int
0x18000d5c1  mov     ebx, eax
0x18000d5c3  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d5c8  test    eax, eax
0x18000d5ca  jnz     loc_18000D77B
0x18000d5d0  mov     r9b, 2; unsigned __int8
0x18000d5d3  lea     rcx, [rbp+37h+var_60]; this
0x18000d5d7  xor     r8d, r8d; unsigned int
0x18000d5da  xor     edx, edx; void *
0x18000d5dc  call    ?SendInitialize@CControlPacket@@QEAAKPEAXKE@Z
0x18000d5e1  mov     r9d, 0D9h; unsigned int
0x18000d5e7  lea     r8, aBaseEcoWdsLibM_1
0x18000d5ee  mov     ecx, eax; unsigned int
0x18000d5f0  mov     ebx, eax
0x18000d5f2  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d5f7  test    eax, eax
0x18000d5f9  jnz     loc_18000D77B
0x18000d5ff  movaps  xmm0, xmmword ptr [rdi]
0x18000d602  lea     rax, [rbp+37h+var_90]
0x18000d606  lea     rdx, aO
0x18000d60d  movdqa  [rbp+37h+var_90], xmm0
0x18000d612  lea     rcx, [rbp+37h+var_80]; int
0x18000d616  mov     [rsp+0D0h+Src], rax; Src
0x18000d61b  call    ??$AddVariable@E@CControlPacket@@QEAAKPEBG0KKKPEAX@Z
0x18000d620  lea     rdi, aBaseEcoWdsLibM_1
0x18000d627  mov     r9d, 0DCh; unsigned int
0x18000d62d  mov     r8, rdi; char *
0x18000d630  mov     ecx, eax; unsigned int
0x18000d632  mov     ebx, eax
0x18000d634  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d639  test    eax, eax
0x18000d63b  jnz     loc_18000D77B
0x18000d641  lea     rax, aDefaultrespons
0x18000d648  or      r9d, 0FFFFFFFFh; unsigned int
0x18000d64c  xor     r8d, r8d; unsigned __int16 *
0x18000d64f  mov     [rsp+0D0h+var_B0], rax; unsigned int
0x18000d654  lea     rdx, aT
0x18000d65b  lea     rcx, [rbp+37h+var_80]; this
0x18000d65f  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z
0x18000d664  mov     r9d, 0DFh; unsigned int
0x18000d66a  mov     r8, rdi; char *
0x18000d66d  mov     ecx, eax; unsigned int
0x18000d66f  mov     ebx, eax
0x18000d671  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d676  test    eax, eax
0x18000d678  jnz     loc_18000D77B
0x18000d67e  and     dword ptr [rsp+0D0h+var_B0], eax
0x18000d682  lea     rdx, aPf
0x18000d689  xor     r8d, r8d; unsigned __int16 *
0x18000d68c  lea     rcx, [rbp+37h+var_80]; this
0x18000d690  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z
0x18000d695  mov     r9d, 0E2h; unsigned int
0x18000d69b  mov     r8, rdi; char *
0x18000d69e  mov     ecx, eax; unsigned int
0x18000d6a0  mov     ebx, eax
0x18000d6a2  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d6a7  test    eax, eax
0x18000d6a9  jnz     loc_18000D77B
0x18000d6af  mov     r8, rsi; struct CWdsMetadata *
0x18000d6b2  lea     rdx, aDf
0x18000d6b9  lea     rcx, [rbp+37h+var_80]; this
0x18000d6bd  call    ?AddMetadata@CWdsMetadataStorePacket@@QEAAKPEBGPEBVCWdsMetadata@@@Z
0x18000d6c2  mov     r9d, 0EBh; unsigned int
0x18000d6c8  mov     r8, rdi; char *
0x18000d6cb  mov     ecx, eax; unsigned int
0x18000d6cd  mov     ebx, eax
0x18000d6cf  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d6d4  test    eax, eax
0x18000d6d6  jnz     loc_18000D77B
0x18000d6dc  mov     r8, r14; struct CWdsMetadata *
0x18000d6df  lea     rdx, aCu
0x18000d6e6  lea     rcx, [rbp+37h+var_80]; this
0x18000d6ea  call    ?AddMetadata@CWdsMetadataStorePacket@@QEAAKPEBGPEBVCWdsMetadata@@@Z
0x18000d6ef  mov     r9d, 0EEh; unsigned int
0x18000d6f5  mov     r8, rdi; char *
0x18000d6f8  mov     ecx, eax; unsigned int
0x18000d6fa  mov     ebx, eax
0x18000d6fc  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d701  test    eax, eax
0x18000d703  jnz     short loc_18000D77B
0x18000d705  mov     r8, r15; struct CWdsMetadata *
0x18000d708  lea     rdx, aWf
0x18000d70f  lea     rcx, [rbp+37h+var_80]; this
0x18000d713  call    ?AddMetadata@CWdsMetadataStorePacket@@QEAAKPEBGPEBVCWdsMetadata@@@Z
0x18000d718  mov     r9d, 0F1h; unsigned int
0x18000d71e  mov     r8, rdi; char *
0x18000d721  mov     ecx, eax; unsigned int
0x18000d723  mov     ebx, eax
0x18000d725  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d72a  test    eax, eax
0x18000d72c  jnz     short loc_18000D77B
0x18000d72e  mov     r8, r12; struct CWdsMetadata *
0x18000d731  lea     rdx, aIf
0x18000d738  lea     rcx, [rbp+37h+var_80]; this
0x18000d73c  call    ?AddMetadata@CWdsMetadataStorePacket@@QEAAKPEBGPEBVCWdsMetadata@@@Z
0x18000d741  mov     r9d, 0F4h; unsigned int
0x18000d747  mov     r8, rdi; char *
0x18000d74a  mov     ecx, eax; unsigned int
0x18000d74c  mov     ebx, eax
0x18000d74e  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d753  test    eax, eax
0x18000d755  jnz     short loc_18000D77B
0x18000d757  mov     rax, [r13+8]
0x18000d75b  lea     rdx, [rbp+37h+var_60]
0x18000d75f  lea     rcx, [rbp+37h+var_80]
0x18000d763  call    cs:__guard_dispatch_icall_fptr
0x18000d769  mov     r9d, 0F7h; unsigned int
0x18000d76f  mov     r8, rdi; char *
0x18000d772  mov     ecx, eax; unsigned int
0x18000d774  mov     ebx, eax
0x18000d776  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d77b  lea     rcx, [rbp+37h+var_60]; this
0x18000d77f  call    ??1CControlPacket@@QEAA@XZ
0x18000d784  lea     rcx, [rbp+37h+var_80]; this
0x18000d788  call    ??1CControlPacket@@QEAA@XZ
0x18000d78d  mov     eax, ebx
0x18000d78f  mov     rcx, [rbp+37h+var_40]
0x18000d793  xor     rcx, rsp; StackCookie
0x18000d796  call    __security_check_cookie
0x18000d79b  mov     rbx, [rsp+0D0h+arg_10]
0x18000d7a3  add     rsp, 0A0h
0x18000d7aa  pop     r15
0x18000d7ac  pop     r14
0x18000d7ae  pop     r13
0x18000d7b0  pop     r12
0x18000d7b2  pop     rdi
0x18000d7b3  pop     rsi
0x18000d7b4  pop     rbp
0x18000d7b5  retn
```
