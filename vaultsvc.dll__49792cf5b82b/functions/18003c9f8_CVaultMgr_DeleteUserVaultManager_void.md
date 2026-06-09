# CVaultMgr::DeleteUserVaultManager(void *)

- ea: `0x18003c9f8`
- end: `0x18003cb02`
- name: `?DeleteUserVaultManager@CVaultMgr@@QEAAKPEAX@Z`
- size: `266`
- prototype: `unsigned int(CVaultMgr *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180027980`

## callees

- `0x180003140`
- `0x180012210`
- `0x18002e6a0`
- `0x18003c9f8`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18003ca86`
- `ntdll!RtlEqualSid` at `0x18003ca86`
- `ntdll!RtlReleaseResource` at `0x18003cab8`
- `ntdll!RtlReleaseResource` at `0x18003cadb`
- `ntdll!RtlReleaseResource` at `0x18003cab8`
- `ntdll!RtlReleaseResource` at `0x18003cadb`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003ca5f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003ca5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVaultMgr::DeleteUserVaultManager(CVaultMgr *this, void *a2)
{
  unsigned int SidHashId; // ebx
  PSID **v5; // rsi
  PSID *i; // rdi
  PSID **v7; // r14
  PSID v8; // rbx
  __int64 (__fastcall *v9)(_QWORD); // [rsp+20h] [rbp-38h] BYREF
  PSID v10; // [rsp+28h] [rbp-30h]
  int v11; // [rsp+30h] [rbp-28h]
  unsigned int v12; // [rsp+60h] [rbp+8h] BYREF
  int v13; // [rsp+64h] [rbp+Ch]

  v13 = HIDWORD(this);
  v12 = 0;
  v9 = AutoDereference<IVaultKeyManager>;
  v10 = 0;
  v11 = 0;
  SidHashId = CVaultMgr::GetSidHashId(this, a2, &v12);
  if ( SidHashId )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v9);
    return SidHashId;
  }
  else
  {
    RtlAcquireResourceExclusive(&Resource, 1u);
    v5 = (PSID **)&VaultGlobals::g_VaultMgr[v12];
    for ( i = *v5; i; i = *v7 )
    {
      v7 = (PSID **)(i + 2);
      if ( RtlEqualSid(a2, *i) )
      {
        v8 = i[1];
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v9);
        v10 = v8;
        *v5 = *v7;
        RtlReleaseResource(&Resource);
        VaultFreeInternal(i);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v9);
        return 0;
      }
      v5 = (PSID **)(i + 2);
    }
    RtlReleaseResource(&Resource);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v9);
    return 0;
  }
}

```

## disassembly

```asm
0x18003c9f8  mov     r11, rsp
0x18003c9fb  mov     [r11+10h], rbx
0x18003c9ff  mov     [r11+18h], rbp
0x18003ca03  mov     [r11+8], rcx
0x18003ca07  push    rsi
0x18003ca08  push    rdi
0x18003ca09  push    r14
0x18003ca0b  sub     rsp, 40h
0x18003ca0f  mov     rbp, rdx
0x18003ca12  mov     [rsp+58h+arg_0], 0
0x18003ca1a  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18003ca21  mov     [r11-38h], rax
0x18003ca25  mov     qword ptr [r11-30h], 0
0x18003ca2d  mov     [rsp+58h+var_28], 0
0x18003ca35  lea     r8, [r11+8]; unsigned int *
0x18003ca39  call    ?GetSidHashId@CVaultMgr@@AEAAKPEAXPEAK@Z; CVaultMgr::GetSidHashId(void *,ulong *)
0x18003ca3e  mov     ebx, eax
0x18003ca40  test    eax, eax
0x18003ca42  jz      short loc_18003CA56
0x18003ca44  lea     rcx, [rsp+58h+var_38]
0x18003ca49  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003ca4e  nop
0x18003ca4f  mov     eax, ebx
0x18003ca51  jmp     loc_18003CAEF
0x18003ca56  mov     dl, 1; Wait
0x18003ca58  lea     rcx, Resource; Resource
0x18003ca5f  call    cs:__imp_RtlAcquireResourceExclusive
0x18003ca65  mov     eax, [rsp+58h+arg_0]
0x18003ca69  lea     rcx, ?g_VaultMgr@VaultGlobals@@3VCVaultMgr@@A; CVaultMgr VaultGlobals::g_VaultMgr
0x18003ca70  lea     rsi, [rcx+rax*8]
0x18003ca74  mov     rdi, [rsi]
0x18003ca77  test    rdi, rdi
0x18003ca7a  jz      short loc_18003CAD4
0x18003ca7c  lea     r14, [rdi+10h]
0x18003ca80  mov     rdx, [rdi]; Sid2
0x18003ca83  mov     rcx, rbp; Sid1
0x18003ca86  call    cs:__imp_RtlEqualSid
0x18003ca8c  test    al, al
0x18003ca8e  jnz     short loc_18003CA98
0x18003ca90  mov     rsi, r14
0x18003ca93  mov     rdi, [r14]
0x18003ca96  jmp     short loc_18003CA77
0x18003ca98  mov     rbx, [rdi+8]
0x18003ca9c  lea     rcx, [rsp+58h+var_38]
0x18003caa1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003caa6  mov     [rsp+58h+var_30], rbx
0x18003caab  mov     rax, [r14]
0x18003caae  mov     [rsi], rax
0x18003cab1  lea     rcx, Resource; Resource
0x18003cab8  call    cs:__imp_RtlReleaseResource
0x18003cabe  mov     rcx, rdi; hMem
0x18003cac1  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18003cac6  nop
0x18003cac7  lea     rcx, [rsp+58h+var_38]
0x18003cacc  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003cad1  nop
0x18003cad2  jmp     short loc_18003CAED
0x18003cad4  lea     rcx, Resource; Resource
0x18003cadb  call    cs:__imp_RtlReleaseResource
0x18003cae1  nop
0x18003cae2  lea     rcx, [rsp+58h+var_38]
0x18003cae7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003caec  nop
0x18003caed  xor     eax, eax
0x18003caef  mov     rbx, [rsp+58h+arg_8]
0x18003caf4  mov     rbp, [rsp+58h+arg_10]
0x18003caf9  add     rsp, 40h
0x18003cafd  pop     r14
0x18003caff  pop     rdi
0x18003cb00  pop     rsi
0x18003cb01  retn
```
