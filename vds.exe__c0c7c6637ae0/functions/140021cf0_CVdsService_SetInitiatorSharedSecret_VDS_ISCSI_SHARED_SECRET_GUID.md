# CVdsService::SetInitiatorSharedSecret(_VDS_ISCSI_SHARED_SECRET *,_GUID)

- ea: `0x140021cf0`
- end: `0x140021e58`
- name: `?SetInitiatorSharedSecret@CVdsService@@UEAAJPEAU_VDS_ISCSI_SHARED_SECRET@@U_GUID@@@Z`
- size: `360`
- prototype: `int(CVdsService *__hidden this, struct _VDS_ISCSI_SHARED_SECRET *, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callees

- `0x140021cf0`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140021d4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140021d4b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140021d13`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140021d13`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140021e47`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140021e47`
- `vdsutil!VdsTraceW` at `0x140021dea`
- `vdsutil!VdsTraceW` at `0x140021e08`
- `vdsutil!VdsTraceW` at `0x140021e26`
- `vdsutil!VdsTraceW` at `0x140021e37`
- `vdsutil!VdsTraceW` at `0x140021dea`
- `vdsutil!VdsTraceW` at `0x140021e08`
- `vdsutil!VdsTraceW` at `0x140021e26`
- `vdsutil!VdsTraceW` at `0x140021e37`

## string_xrefs

- `0x140021e1d`: `CVdsService::SetInitiatorSharedSecret, 1, hr=%lX`
- `0x140021d02`: `CVdsService::SetInitiatorSharedSecret()`
- `0x140021e2e`: `CVdsService::SetInitiatorSharedSecret: Could not access necessary function in iSCSI library.`
- `0x140021db0`: `CVdsService::SetInitiatorSharedSecret, 2, %X`
- `0x140021de1`: `CVdsService::SetInitiatorSharedSecret, 3, %X`
- `0x140021dff`: `CVdsService::SetInitiatorSharedSecret, 4, status=%X`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsService::SetInitiatorSharedSecret(
        CVdsService *this,
        struct _VDS_ISCSI_SHARED_SECRET *a2,
        struct _GUID *a3)
{
  int v6; // esi
  FARPROC ProcAddress; // rbx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  _BYTE v12[56]; // [rsp+20h] [rbp-38h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v12, 0x5Eu, "CVdsService::SetInitiatorSharedSecret()");
  v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 2) + 32LL))((char *)this - 16);
  if ( v6 >= 0 )
  {
    if ( !CVdsService::m_hIscsidscModule
      || (ProcAddress = GetProcAddress(CVdsService::m_hIscsidscModule, "SetIScsiInitiatorCHAPSharedSecret")) == 0 )
    {
      VdsTraceW(0, L"CVdsService::SetInitiatorSharedSecret: Could not access necessary function in iSCSI library.");
      v6 = -2147212288;
      goto LABEL_19;
    }
    if ( memcmp_0(&GUID_NULL, a3, 0x10u) )
    {
      v6 = -2147211514;
      VdsTraceW(0, L"CVdsService::SetInitiatorSharedSecret, 1, hr=%lX", 2147755782LL);
      goto LABEL_19;
    }
    v6 = 0;
    if ( a2 )
    {
      v10 = ((__int64 (__fastcall *)(_QWORD, UCHAR *))ProcAddress)(a2->ulSharedSecretSize, a2->pSharedSecret);
      v9 = v10;
      if ( !v10 )
        goto LABEL_19;
      if ( (v10 & 0xFFF0000) == 0 || (v10 & 0xC0000000) == 0xC0000000 )
        VdsTraceW(0, L"CVdsService::SetInitiatorSharedSecret, 3, %X", v10);
    }
    else
    {
      v8 = ((__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress)(0, 0);
      v9 = v8;
      if ( !v8 )
        goto LABEL_19;
      if ( (v8 & 0xFFF0000) == 0 || (v8 & 0xC0000000) == 0xC0000000 )
        VdsTraceW(0, L"CVdsService::SetInitiatorSharedSecret, 2, %X", v8);
    }
    if ( (v9 & 0xFFF0000) == 0 || (v9 & 0xC0000000) == 0xC0000000 )
    {
      VdsTraceW(0, L"CVdsService::SetInitiatorSharedSecret, 4, status=%X", v9);
      v6 = -2147210998;
    }
  }
LABEL_19:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v12);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140021cf0  push    rbx
0x140021cf2  push    rbp
0x140021cf3  push    rsi
0x140021cf4  push    rdi
0x140021cf5  sub     rsp, 38h
0x140021cf9  mov     rbp, r8
0x140021cfc  mov     rdi, rdx
0x140021cff  mov     rbx, rcx
0x140021d02  lea     r8, aCvdsserviceSet_15; "CVdsService::SetInitiatorSharedSecret()"
0x140021d09  mov     edx, 5Eh ; '^'
0x140021d0e  lea     rcx, [rsp+58h+var_38]
0x140021d13  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140021d19  nop
0x140021d1a  lea     rcx, [rbx-10h]
0x140021d1e  mov     rax, [rcx]
0x140021d21  mov     rax, [rax+20h]
0x140021d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021d2a  mov     esi, eax
0x140021d2c  test    eax, eax
0x140021d2e  js      loc_140021E42
0x140021d34  mov     rcx, cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x140021d3b  test    rcx, rcx
0x140021d3e  jz      loc_140021E2E
0x140021d44  lea     rdx, aSetiscsiinitia; "SetIScsiInitiatorCHAPSharedSecret"
0x140021d4b  call    cs:__imp_GetProcAddress
0x140021d51  mov     rbx, rax
0x140021d54  test    rax, rax
0x140021d57  jz      loc_140021E2E
0x140021d5d  mov     r8d, 10h; Size
0x140021d63  mov     rdx, rbp; Buf2
0x140021d66  lea     rcx, GUID_NULL; Buf1
0x140021d6d  call    memcmp_0
0x140021d72  test    eax, eax
0x140021d74  jnz     loc_140021E15
0x140021d7a  xor     esi, esi
0x140021d7c  mov     rax, rbx
0x140021d7f  test    rdi, rdi
0x140021d82  jnz     short loc_140021DB9
0x140021d84  xor     edx, edx
0x140021d86  xor     ecx, ecx
0x140021d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021d8d  mov     ebx, eax
0x140021d8f  test    eax, eax
0x140021d91  jz      loc_140021E42
0x140021d97  mov     edi, 0C0000000h
0x140021d9c  mov     ebp, 0FFF0000h
0x140021da1  test    ebp, eax
0x140021da3  jz      short loc_140021DAD
0x140021da5  mov     ecx, eax
0x140021da7  and     ecx, edi
0x140021da9  cmp     ecx, edi
0x140021dab  jnz     short loc_140021DF0
0x140021dad  mov     r8d, eax
0x140021db0  lea     rdx, aCvdsserviceSet_8; "CVdsService::SetInitiatorSharedSecret, "...
0x140021db7  jmp     short loc_140021DE8
0x140021db9  mov     rdx, [rdi]
0x140021dbc  mov     ecx, [rdi+8]
0x140021dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021dc4  mov     ebx, eax
0x140021dc6  test    eax, eax
0x140021dc8  jz      short loc_140021E42
0x140021dca  mov     edi, 0C0000000h
0x140021dcf  mov     ebp, 0FFF0000h
0x140021dd4  test    ebp, eax
0x140021dd6  jz      short loc_140021DDE
0x140021dd8  and     eax, edi
0x140021dda  cmp     eax, edi
0x140021ddc  jnz     short loc_140021DF0
0x140021dde  mov     r8d, ebx
0x140021de1  lea     rdx, aCvdsserviceSet; "CVdsService::SetInitiatorSharedSecret, "...
0x140021de8  xor     ecx, ecx
0x140021dea  call    cs:__imp_VdsTraceW
0x140021df0  test    ebp, ebx
0x140021df2  jz      short loc_140021DFC
0x140021df4  mov     eax, ebx
0x140021df6  and     eax, edi
0x140021df8  cmp     eax, edi
0x140021dfa  jnz     short loc_140021E42
0x140021dfc  mov     r8d, ebx
0x140021dff  lea     rdx, aCvdsserviceSet_2; "CVdsService::SetInitiatorSharedSecret, "...
0x140021e06  xor     ecx, ecx
0x140021e08  call    cs:__imp_VdsTraceW
0x140021e0e  mov     esi, 8004290Ah
0x140021e13  jmp     short loc_140021E42
0x140021e15  mov     esi, 80042706h
0x140021e1a  mov     r8d, esi
0x140021e1d  lea     rdx, aCvdsserviceSet_13; "CVdsService::SetInitiatorSharedSecret, "...
0x140021e24  xor     ecx, ecx
0x140021e26  call    cs:__imp_VdsTraceW
0x140021e2c  jmp     short loc_140021E42
0x140021e2e  lea     rdx, aCvdsserviceSet_3; "CVdsService::SetInitiatorSharedSecret: "...
0x140021e35  xor     ecx, ecx
0x140021e37  call    cs:__imp_VdsTraceW
0x140021e3d  mov     esi, 80042400h
0x140021e42  lea     rcx, [rsp+58h+var_38]
0x140021e47  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140021e4d  mov     eax, esi
0x140021e4f  add     rsp, 38h
0x140021e53  pop     rdi
0x140021e54  pop     rsi
0x140021e55  pop     rbp
0x140021e56  pop     rbx
0x140021e57  retn
```
