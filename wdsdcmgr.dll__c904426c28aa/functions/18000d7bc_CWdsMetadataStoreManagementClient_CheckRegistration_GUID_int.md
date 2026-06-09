# CWdsMetadataStoreManagementClient::CheckRegistration(_GUID,int *)

- ea: `0x18000d7bc`
- end: `0x18000d94b`
- name: `?CheckRegistration@CWdsMetadataStoreManagementClient@@QEAAKU_GUID@@PEAH@Z`
- size: `399`
- prototype: `unsigned int __fastcall(CWdsMetadataStoreManagementClient *__hidden this, struct _GUID *__struct_ptr, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180001e14`

## callees

- `0x18000d7bc`
- `0x180012640`
- `0x1800126f8`
- `0x1800129e4`
- `0x180012c84`
- `0x180014d58`
- `0x180015660`
- `0x180015cc0`

## string_xrefs

- `0x18000d819`: `base\eco\wds\lib\metadata\com\wdsmetadatastoremanagementclient.cpp`
- `0x18000d8ec`: `base\eco\wds\lib\metadata\com\wdsmetadatastorepacket.cpp`

## pseudocode

```c
__int64 __fastcall CWdsMetadataStoreManagementClient::CheckRegistration(
        __int64 (__fastcall **this)(int *, __int128 *),
        struct _GUID *a2,
        int *a3)
{
  unsigned int ULONG; // ebx
  const char *v7; // rdx
  int v8; // edi
  const char *v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  const char *v12; // rdx
  const char *v13; // rdx
  unsigned int v14; // r9d
  const char *v15; // rdx
  const char *v16; // rdx
  int v18; // [rsp+20h] [rbp-69h]
  int v19; // [rsp+28h] [rbp-61h]
  unsigned int v20[4]; // [rsp+40h] [rbp-49h] BYREF
  __int128 Src; // [rsp+50h] [rbp-39h] BYREF
  __int128 v22; // [rsp+60h] [rbp-29h] BYREF
  __int64 v23; // [rsp+70h] [rbp-19h]
  int v24; // [rsp+78h] [rbp-11h]
  int v25[4]; // [rsp+80h] [rbp-9h] BYREF
  __int64 v26; // [rsp+90h] [rbp+7h]
  int v27; // [rsp+98h] [rbp+Fh]

  v26 = 0;
  v27 = 0;
  v23 = 0;
  v24 = 0;
  *(_OWORD *)v25 = 0;
  v22 = 0;
  ULONG = CControlPacket::SendInitialize((CControlPacket *)v25, 0, 6u, 2u);
  v8 = 0;
  if ( !ElValidateWin32(ULONG, v7, "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp", 0x145u) )
  {
    ULONG = CControlPacket::SendInitialize((CControlPacket *)&v22, 0, 0, 2u);
    if ( !ElValidateWin32(ULONG, v9, "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp", 0x148u) )
    {
      Src = (__int128)*a2;
      ULONG = CControlPacket::AddVariable<unsigned char>((__int64)v25, (__int64)L"O", v10, v11, v18, v19, &Src);
      if ( !ElValidateWin32(
              ULONG,
              v12,
              "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
              0x14Bu) )
      {
        ULONG = this[1](v25, &v22);
        if ( !ElValidateWin32(
                ULONG,
                v13,
                "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
                0x14Eu) )
        {
          v20[0] = 0;
          ULONG = CControlPacket::GetULONG((CControlPacket *)&v22, L"ORS", 0, v14, v20);
          if ( !ElValidateWin32(ULONG, v15, "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastorepacket.cpp", 0x1CDu) )
          {
            LOBYTE(v8) = v20[0] != 0;
            *a3 = v8;
          }
          ElValidateWin32(
            ULONG,
            v16,
            "base\\eco\\wds\\lib\\metadata\\com\\wdsmetadatastoremanagementclient.cpp",
            0x151u);
        }
      }
    }
  }
  CControlPacket::~CControlPacket((CControlPacket *)&v22);
  CControlPacket::~CControlPacket((CControlPacket *)v25);
  return ULONG;
}

```

## disassembly

```asm
0x18000d7bc  push    rbp
0x18000d7be  push    rbx
0x18000d7bf  push    rsi
0x18000d7c0  push    rdi
0x18000d7c1  push    r12
0x18000d7c3  push    r14
0x18000d7c5  push    r15
0x18000d7c7  lea     rbp, [rsp-27h]
0x18000d7cc  sub     rsp, 0B0h
0x18000d7d3  mov     rax, cs:__security_cookie
0x18000d7da  xor     rax, rsp
0x18000d7dd  mov     [rbp+57h+var_40], rax
0x18000d7e1  xor     eax, eax
0x18000d7e3  xorps   xmm0, xmm0
0x18000d7e6  mov     rsi, r8
0x18000d7e9  mov     [rbp+57h+var_50], rax
0x18000d7ed  mov     r14, rdx
0x18000d7f0  mov     [rbp+57h+var_48], eax
0x18000d7f3  mov     r15, rcx
0x18000d7f6  mov     [rbp+57h+var_70], rax
0x18000d7fa  lea     r8d, [rax+6]; unsigned int
0x18000d7fe  mov     [rbp+57h+var_68], eax
0x18000d801  mov     r9b, 2; unsigned __int8
0x18000d804  lea     rcx, [rbp+57h+var_60]; this
0x18000d808  xor     edx, edx; void *
0x18000d80a  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18000d80f  movdqu  [rbp+57h+var_80], xmm0
0x18000d814  call    ?SendInitialize@CControlPacket@@QEAAKPEAXKE@Z
0x18000d819  lea     r12, aBaseEcoWdsLibM_1
0x18000d820  mov     r9d, 145h; unsigned int
0x18000d826  mov     r8, r12; char *
0x18000d829  mov     ecx, eax; unsigned int
0x18000d82b  mov     ebx, eax
0x18000d82d  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d832  xor     edi, edi
0x18000d834  test    eax, eax
0x18000d836  jnz     loc_18000D919
0x18000d83c  mov     r9b, 2; unsigned __int8
0x18000d83f  lea     rcx, [rbp+57h+var_80]; this
0x18000d843  xor     r8d, r8d; unsigned int
0x18000d846  xor     edx, edx; void *
0x18000d848  call    ?SendInitialize@CControlPacket@@QEAAKPEAXKE@Z
0x18000d84d  mov     r9d, 148h; unsigned int
0x18000d853  mov     r8, r12; char *
0x18000d856  mov     ecx, eax; unsigned int
0x18000d858  mov     ebx, eax
0x18000d85a  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d85f  test    eax, eax
0x18000d861  jnz     loc_18000D919
0x18000d867  movaps  xmm0, xmmword ptr [r14]
0x18000d86b  lea     rax, [rbp+57h+var_90]
0x18000d86f  lea     rdx, aO
0x18000d876  movdqa  [rbp+57h+var_90], xmm0
0x18000d87b  lea     rcx, [rbp+57h+var_60]; int
0x18000d87f  mov     [rsp+0E0h+Src], rax; Src
0x18000d884  call    ??$AddVariable@E@CControlPacket@@QEAAKPEBG0KKKPEAX@Z
0x18000d889  mov     r9d, 14Bh; unsigned int
0x18000d88f  mov     r8, r12; char *
0x18000d892  mov     ecx, eax; unsigned int
0x18000d894  mov     ebx, eax
0x18000d896  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d89b  test    eax, eax
0x18000d89d  jnz     short loc_18000D919
0x18000d89f  mov     rax, [r15+8]
0x18000d8a3  lea     rdx, [rbp+57h+var_80]
0x18000d8a7  lea     rcx, [rbp+57h+var_60]
0x18000d8ab  call    cs:__guard_dispatch_icall_fptr
0x18000d8b1  mov     r9d, 14Eh; unsigned int
0x18000d8b7  mov     r8, r12; char *
0x18000d8ba  mov     ecx, eax; unsigned int
0x18000d8bc  mov     ebx, eax
0x18000d8be  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d8c3  test    eax, eax
0x18000d8c5  jnz     short loc_18000D919
0x18000d8c7  lea     rax, [rbp+57h+var_A0]
0x18000d8cb  mov     [rbp+57h+var_A0], edi
0x18000d8ce  xor     r8d, r8d; unsigned __int16 *
0x18000d8d1  mov     [rsp+0E0h+var_C0], rax; unsigned int *
0x18000d8d6  lea     rdx, aOrs
0x18000d8dd  lea     rcx, [rbp+57h+var_80]; this
0x18000d8e1  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z
0x18000d8e6  mov     r9d, 1CDh; unsigned int
0x18000d8ec  lea     r8, aBaseEcoWdsLibM_4
0x18000d8f3  mov     ecx, eax; unsigned int
0x18000d8f5  mov     ebx, eax
0x18000d8f7  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d8fc  test    eax, eax
0x18000d8fe  jnz     short loc_18000D909
0x18000d900  cmp     [rbp+57h+var_A0], edi
0x18000d903  setnz   dil
0x18000d907  mov     [rsi], edi
0x18000d909  mov     r9d, 151h; unsigned int
0x18000d90f  mov     r8, r12; char *
0x18000d912  mov     ecx, ebx; unsigned int
0x18000d914  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000d919  lea     rcx, [rbp+57h+var_80]; this
0x18000d91d  call    ??1CControlPacket@@QEAA@XZ
0x18000d922  lea     rcx, [rbp+57h+var_60]; this
0x18000d926  call    ??1CControlPacket@@QEAA@XZ
0x18000d92b  mov     eax, ebx
0x18000d92d  mov     rcx, [rbp+57h+var_40]
0x18000d931  xor     rcx, rsp; StackCookie
0x18000d934  call    __security_check_cookie
0x18000d939  add     rsp, 0B0h
0x18000d940  pop     r15
0x18000d942  pop     r14
0x18000d944  pop     r12
0x18000d946  pop     rdi
0x18000d947  pop     rsi
0x18000d948  pop     rbx
0x18000d949  pop     rbp
0x18000d94a  retn
```
