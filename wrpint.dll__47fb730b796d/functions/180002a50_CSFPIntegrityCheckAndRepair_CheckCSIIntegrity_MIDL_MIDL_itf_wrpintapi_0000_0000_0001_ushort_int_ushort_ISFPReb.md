# CSFPIntegrityCheckAndRepair::CheckCSIIntegrity(__MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *,ushort *,int,ushort *,ISFPRebootCallback *,ISFPProgressCallback *,int *,__MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *,ulong *)

- ea: `0x180002a50`
- end: `0x180002cf2`
- name: `?CheckCSIIntegrity@CSFPIntegrityCheckAndRepair@@EEAAJPEAU__MIDL___MIDL_itf_wrpintapi_0000_0000_0001@@PEAGH1PEAUISFPRebootCallback@@PEAUISFPProgressCallback@@PEAHPEAU__MIDL___MIDL_itf_wrpintapi_0000_0000_0002@@PEAK@Z`
- size: `674`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *this, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *, struct IMalloc *, unsigned int, unsigned __int16 *, struct ISFPRebootCallback *, struct ISFPProgressCallback *, int *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x1800012f4`
- `0x180001de0`
- `0x180002a50`
- `0x180006344`
- `0x1800070f0`
- `0x18001b7b0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::CheckCSIIntegrity(
        CSFPIntegrityCheckAndRepair *this,
        struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *a2,
        struct IMalloc *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        struct ISFPRebootCallback *a6,
        struct ISFPProgressCallback *a7,
        int *a8,
        struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *a9,
        unsigned int *a10)
{
  unsigned int (__fastcall *v14)(__int64); // rax
  int v15; // r14d
  int v16; // esi
  int v17; // eax
  __int64 v18; // rax
  CSFPIntegrityCheckAndRepair *v19; // rcx
  __int64 i; // rbx
  __int64 v22; // [rsp+80h] [rbp-41h] BYREF
  CSFPIntegrityCheckAndRepair *v23; // [rsp+88h] [rbp-39h] BYREF
  __int64 v24; // [rsp+90h] [rbp-31h] BYREF
  __int64 v25; // [rsp+98h] [rbp-29h] BYREF
  void *Block; // [rsp+A0h] [rbp-21h] BYREF
  int v27; // [rsp+A8h] [rbp-19h] BYREF

  v14 = (unsigned int (__fastcall *)(__int64))qword_18002B8D8;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  Block = 0;
  v27 = 0;
  *a10 = 1;
  if ( v14 && v14(1) )
  {
    v15 = 1;
    v16 = (*(__int64 (__fastcall **)(CSFPIntegrityCheckAndRepair *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *, __int64 *, CSFPIntegrityCheckAndRepair **, void **, int *, __int64 *))(*(_QWORD *)this + 40LL))(
            this,
            a2,
            &v22,
            &v23,
            &Block,
            &v27,
            &v25);
    if ( v16 < 0 )
      goto LABEL_12;
    if ( a3 )
    {
      v17 = (*(__int64 (__fastcall **)(CSFPIntegrityCheckAndRepair *, struct IMalloc *, _QWORD, struct ISFPRebootCallback *, struct ISFPProgressCallback *, __int64, CSFPIntegrityCheckAndRepair *, __int64, int *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *, unsigned int *))(*(_QWORD *)this + 104LL))(
              this,
              a3,
              a4,
              a6,
              a7,
              v22,
              v23,
              v25,
              a8,
              a9,
              a10);
    }
    else
    {
      v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v22)(
              v22,
              &GUID_f4d9decb_0250_4ad4_9500_85c7f2f281ec,
              &v24);
      if ( v16 < 0 )
        goto LABEL_12;
      v18 = *(_QWORD *)this;
      if ( a2 )
        v17 = (*(__int64 (__fastcall **)(CSFPIntegrityCheckAndRepair *, _QWORD, _QWORD, struct ISFPRebootCallback *, struct ISFPProgressCallback *, __int64, CSFPIntegrityCheckAndRepair *, __int64, int *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *, unsigned int *))(v18 + 112))(
                this,
                0,
                a4,
                a6,
                a7,
                v22,
                v23,
                v24,
                a8,
                a9,
                a10);
      else
        v17 = (*(__int64 (__fastcall **)(CSFPIntegrityCheckAndRepair *, _QWORD, _QWORD, struct ISFPRebootCallback *, struct ISFPProgressCallback *, __int64, CSFPIntegrityCheckAndRepair *, __int64, int *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *, unsigned int *))(v18 + 120))(
                this,
                0,
                a4,
                a6,
                a7,
                v22,
                v23,
                v24,
                a8,
                a9,
                a10);
    }
    v16 = v17;
  }
  else
  {
    v15 = 0;
    v16 = -2147213310;
  }
LABEL_12:
  if ( v25 )
    operator delete((void *)(v25 - 8));
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v19 = v23;
  if ( v23 )
    (*(void (__fastcall **)(CSFPIntegrityCheckAndRepair *))(*(_QWORD *)v23 + 16LL))(v23);
  if ( Block )
  {
    CSFPIntegrityCheckAndRepair::ReleaseOfflineStoreCreationParametersInternals(
      v19,
      (struct _OFFLINE_STORE_CREATION_PARAMETERS *)Block,
      a3);
    if ( Block )
      operator delete(Block);
  }
  if ( v15 && qword_18002B8D0 )
    qword_18002B8D0();
  if ( v27 )
  {
    for ( i = 0; i != 6; ++i )
      UnloadOfflineRegistryKey((char *)this + 16 * i + 8 * i + 16);
    UnloadOfflineRegistryKey((char *)this + 160);
    UnloadOfflineRegistryKey((char *)this + 184);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180002a50  push    rbp
0x180002a52  push    rbx
0x180002a53  push    rsi
0x180002a54  push    rdi
0x180002a55  push    r12
0x180002a57  push    r13
0x180002a59  push    r14
0x180002a5b  push    r15
0x180002a5d  lea     rbp, [rsp-7]
0x180002a62  sub     rsp, 0C8h
0x180002a69  mov     rax, cs:__security_cookie
0x180002a70  xor     rax, rsp
0x180002a73  mov     [rbp+3Fh+var_50], rax
0x180002a77  mov     rax, [rbp+3Fh+arg_28]
0x180002a7b  xor     esi, esi
0x180002a7d  mov     r15, [rbp+3Fh+arg_48]
0x180002a84  mov     r13d, r9d
0x180002a87  mov     [rbp+3Fh+var_88], rax
0x180002a8b  mov     rbx, r8
0x180002a8e  mov     rax, [rbp+3Fh+arg_30]
0x180002a92  mov     r12, rdx
0x180002a95  mov     [rbp+3Fh+var_90], rax
0x180002a99  mov     rdi, rcx
0x180002a9c  mov     rax, [rbp+3Fh+arg_38]
0x180002aa3  mov     [rbp+3Fh+var_98], rax
0x180002aa7  mov     rax, [rbp+3Fh+arg_40]
0x180002aae  mov     [rbp+3Fh+var_A0], rax
0x180002ab2  mov     rax, cs:qword_18002B8D8
0x180002ab9  mov     [rbp+3Fh+var_80], rsi
0x180002abd  mov     [rbp+3Fh+var_78], rsi
0x180002ac1  mov     [rbp+3Fh+var_70], rsi
0x180002ac5  mov     [rbp+3Fh+var_68], rsi
0x180002ac9  mov     [rbp+3Fh+Block], rsi
0x180002acd  mov     [rbp+3Fh+var_58], esi
0x180002ad0  mov     dword ptr [r15], 1
0x180002ad7  test    rax, rax
0x180002ada  jz      loc_180002C0B
0x180002ae0  lea     ecx, [rsi+1]
0x180002ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ae8  test    eax, eax
0x180002aea  jz      loc_180002C0B
0x180002af0  mov     rax, [rdi]
0x180002af3  lea     rcx, [rbp+3Fh+var_68]
0x180002af7  mov     [rsp+100h+var_D0], rcx
0x180002afc  lea     r9, [rbp+3Fh+var_78]
0x180002b00  lea     rcx, [rbp+3Fh+var_58]
0x180002b04  mov     rdx, r12
0x180002b07  mov     [rsp+100h+var_D8], rcx
0x180002b0c  lea     r8, [rbp+3Fh+var_80]
0x180002b10  mov     rax, [rax+28h]
0x180002b14  lea     rcx, [rbp+3Fh+Block]
0x180002b18  mov     [rsp+100h+var_E0], rcx
0x180002b1d  lea     r14d, [rsi+1]
0x180002b21  mov     rcx, rdi
0x180002b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b29  mov     esi, eax
0x180002b2b  test    eax, eax
0x180002b2d  js      loc_180002C13
0x180002b33  test    rbx, rbx
0x180002b36  jz      short loc_180002B89
0x180002b38  mov     rcx, [rbp+3Fh+var_A0]
0x180002b3c  mov     r8d, r13d
0x180002b3f  mov     rax, [rdi]
0x180002b42  mov     rdx, rbx
0x180002b45  mov     r9, [rbp+3Fh+var_88]
0x180002b49  mov     [rsp+100h+var_B0], r15
0x180002b4e  mov     [rsp+100h+var_B8], rcx
0x180002b53  mov     rcx, [rbp+3Fh+var_98]
0x180002b57  mov     rax, [rax+68h]
0x180002b5b  mov     [rsp+100h+var_C0], rcx
0x180002b60  mov     rcx, [rbp+3Fh+var_68]
0x180002b64  mov     [rsp+100h+var_C8], rcx
0x180002b69  mov     rcx, [rbp+3Fh+var_78]
0x180002b6d  mov     [rsp+100h+var_D0], rcx
0x180002b72  mov     rcx, [rbp+3Fh+var_80]
0x180002b76  mov     [rsp+100h+var_D8], rcx
0x180002b7b  mov     rcx, [rbp+3Fh+var_90]
0x180002b7f  mov     [rsp+100h+var_E0], rcx
0x180002b84  mov     rcx, rdi
0x180002b87  jmp     short loc_180002BFC
0x180002b89  mov     rcx, [rbp+3Fh+var_80]
0x180002b8d  lea     r8, [rbp+3Fh+var_70]
0x180002b91  lea     rdx, _GUID_f4d9decb_0250_4ad4_9500_85c7f2f281ec
0x180002b98  mov     rax, [rcx]
0x180002b9b  mov     rax, [rax]
0x180002b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ba3  mov     esi, eax
0x180002ba5  test    eax, eax
0x180002ba7  js      short loc_180002C13
0x180002ba9  mov     rcx, [rbp+3Fh+var_A0]
0x180002bad  xor     edx, edx
0x180002baf  mov     rax, [rdi]
0x180002bb2  mov     r8d, r13d
0x180002bb5  mov     r9, [rbp+3Fh+var_88]
0x180002bb9  mov     [rsp+100h+var_B0], r15
0x180002bbe  mov     [rsp+100h+var_B8], rcx
0x180002bc3  mov     rcx, [rbp+3Fh+var_98]
0x180002bc7  mov     [rsp+100h+var_C0], rcx
0x180002bcc  mov     rcx, [rbp+3Fh+var_70]
0x180002bd0  mov     [rsp+100h+var_C8], rcx
0x180002bd5  mov     rcx, [rbp+3Fh+var_78]
0x180002bd9  mov     [rsp+100h+var_D0], rcx
0x180002bde  mov     rcx, [rbp+3Fh+var_80]
0x180002be2  mov     [rsp+100h+var_D8], rcx
0x180002be7  mov     rcx, [rbp+3Fh+var_90]
0x180002beb  mov     [rsp+100h+var_E0], rcx
0x180002bf0  mov     rcx, rdi
0x180002bf3  test    r12, r12
0x180002bf6  jz      short loc_180002C05
0x180002bf8  mov     rax, [rax+70h]
0x180002bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c01  mov     esi, eax
0x180002c03  jmp     short loc_180002C13
0x180002c05  mov     rax, [rax+78h]
0x180002c09  jmp     short loc_180002BFC
0x180002c0b  mov     r14d, esi
0x180002c0e  mov     esi, 80042002h
0x180002c13  mov     rcx, [rbp+3Fh+var_68]
0x180002c17  test    rcx, rcx
0x180002c1a  jz      short loc_180002C25
0x180002c1c  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180002c20  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002c25  mov     rcx, [rbp+3Fh+var_70]
0x180002c29  test    rcx, rcx
0x180002c2c  jz      short loc_180002C3A
0x180002c2e  mov     rax, [rcx]
0x180002c31  mov     rax, [rax+10h]
0x180002c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c3a  mov     rcx, [rbp+3Fh+var_80]
0x180002c3e  test    rcx, rcx
0x180002c41  jz      short loc_180002C4F
0x180002c43  mov     rax, [rcx]
0x180002c46  mov     rax, [rax+10h]
0x180002c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c4f  mov     rcx, [rbp+3Fh+var_78]
0x180002c53  test    rcx, rcx
0x180002c56  jz      short loc_180002C64
0x180002c58  mov     rax, [rcx]
0x180002c5b  mov     rax, [rax+10h]
0x180002c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c64  mov     rdx, [rbp+3Fh+Block]; struct _OFFLINE_STORE_CREATION_PARAMETERS *
0x180002c68  test    rdx, rdx
0x180002c6b  jz      short loc_180002C80
0x180002c6d  call    ?ReleaseOfflineStoreCreationParametersInternals@CSFPIntegrityCheckAndRepair@@AEAAJPEAU_OFFLINE_STORE_CREATION_PARAMETERS@@PEAUIMalloc@@@Z; CSFPIntegrityCheckAndRepair::ReleaseOfflineStoreCreationParametersInternals(_OFFLINE_STORE_CREATION_PARAMETERS *,IMalloc *)
0x180002c72  mov     rcx, [rbp+3Fh+Block]; Block
0x180002c76  test    rcx, rcx
0x180002c79  jz      short loc_180002C80
0x180002c7b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002c80  test    r14d, r14d
0x180002c83  jz      short loc_180002C96
0x180002c85  mov     rax, cs:qword_18002B8D0
0x180002c8c  test    rax, rax
0x180002c8f  jz      short loc_180002C96
0x180002c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c96  cmp     [rbp+3Fh+var_58], 0
0x180002c9a  jz      short loc_180002CD0
0x180002c9c  xor     ebx, ebx
0x180002c9e  lea     rax, [rbx+1]
0x180002ca2  lea     rax, [rbx+rax*2]
0x180002ca6  lea     rcx, [rdi+rax*8]
0x180002caa  call    UnloadOfflineRegistryKey
0x180002caf  inc     rbx
0x180002cb2  cmp     rbx, 6
0x180002cb6  jnz     short loc_180002C9E
0x180002cb8  lea     rcx, [rdi+0A0h]
0x180002cbf  call    UnloadOfflineRegistryKey
0x180002cc4  lea     rcx, [rdi+0B8h]
0x180002ccb  call    UnloadOfflineRegistryKey
0x180002cd0  mov     eax, esi
0x180002cd2  mov     rcx, [rbp+3Fh+var_50]
0x180002cd6  xor     rcx, rsp; StackCookie
0x180002cd9  call    __security_check_cookie
0x180002cde  add     rsp, 0C8h
0x180002ce5  pop     r15
0x180002ce7  pop     r14
0x180002ce9  pop     r13
0x180002ceb  pop     r12
0x180002ced  pop     rdi
0x180002cee  pop     rsi
0x180002cef  pop     rbx
0x180002cf0  pop     rbp
0x180002cf1  retn
```
