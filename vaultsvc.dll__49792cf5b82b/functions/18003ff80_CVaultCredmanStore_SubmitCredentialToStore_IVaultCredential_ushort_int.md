# CVaultCredmanStore::SubmitCredentialToStore(IVaultCredential *,ushort *,int)

- ea: `0x18003ff80`
- end: `0x1800400c1`
- name: `?SubmitCredentialToStore@CVaultCredmanStore@@UEAAKPEAUIVaultCredential@@PEAGH@Z`
- size: `321`
- prototype: `__int64 __fastcall(struct _RTL_RESOURCE *this, struct IVaultCredential *, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180003140`
- `0x18003b7d8`
- `0x18003e5cc`
- `0x18003ff80`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004005b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004005b`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180040051`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180040051`
- `ntdll!RtlReleaseResource` at `0x1800400b0`
- `ntdll!RtlReleaseResource` at `0x1800400b0`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003ffd6`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003ffd6`

## pseudocode

```c
__int64 __fastcall CVaultCredmanStore::SubmitCredentialToStore(
        struct _RTL_RESOURCE *this,
        struct IVaultCredential *a2,
        unsigned __int16 *a3,
        int a4)
{
  struct _RTL_RESOURCE *v6; // rdi
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  DWORD LastError; // eax
  __int64 v12; // [rsp+30h] [rbp-28h] BYREF
  PCREDENTIALW Credential; // [rsp+38h] [rbp-20h] BYREF
  int v14; // [rsp+40h] [rbp-18h]

  v6 = this + 2;
  Credential = 0;
  v14 = 0;
  v12 = 0;
  if ( a4 )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v12);
    return 50;
  }
  RtlAcquireResourceExclusive(this + 2, 1u);
  v8 = CVaultCredmanStore::ConvertVaultToCredmanCredential((CVaultCredmanStore *)this, a2, &Credential);
  v9 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, v8);
  }
  else
  {
    v10 = (*(__int64 (__fastcall **)(struct IVaultCredential *))(*(_QWORD *)a2 + 160LL))(a2);
    if ( CredWriteW(Credential, (v10 >> 28) & 1) )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v12);
      v9 = 0;
      goto LABEL_14;
    }
    LastError = GetLastError();
    v9 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, LastError);
  }
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v12);
LABEL_14:
  RtlReleaseResource(v6);
  return v9;
}

```

## disassembly

```asm
0x18003ff80  push    rbp
0x18003ff82  push    rbx
0x18003ff83  push    rsi
0x18003ff84  push    rdi
0x18003ff85  mov     rbp, rsp
0x18003ff88  sub     rsp, 58h
0x18003ff8c  mov     rsi, rdx
0x18003ff8f  mov     rbx, rcx
0x18003ff92  lea     rdi, [rcx+0C0h]
0x18003ff99  mov     [rbp+var_38], rdi
0x18003ff9d  mov     [rbp+var_30], 0
0x18003ffa1  mov     [rbp+Credential], 0
0x18003ffa9  mov     [rbp+var_18], 0
0x18003ffb0  mov     [rbp+var_28], 0
0x18003ffb8  test    r9d, r9d
0x18003ffbb  jz      short loc_18003FFD1
0x18003ffbd  lea     rcx, [rbp+var_28]
0x18003ffc1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003ffc6  nop
0x18003ffc7  mov     eax, 32h ; '2'
0x18003ffcc  jmp     loc_1800400B8
0x18003ffd1  mov     dl, 1; Wait
0x18003ffd3  mov     rcx, rdi; Resource
0x18003ffd6  call    cs:__imp_RtlAcquireResourceExclusive
0x18003ffdc  mov     [rbp+var_30], 1
0x18003ffe0  lea     r8, [rbp+Credential]; struct _CREDENTIALW **
0x18003ffe4  mov     rdx, rsi; struct IVaultCredential *
0x18003ffe7  mov     rcx, rbx; this
0x18003ffea  call    ?ConvertVaultToCredmanCredential@CVaultCredmanStore@@AEAAKPEAUIVaultCredential@@PEAPEAU_CREDENTIALW@@@Z; CVaultCredmanStore::ConvertVaultToCredmanCredential(IVaultCredential *,_CREDENTIALW * *)
0x18003ffef  mov     ebx, eax
0x18003fff1  test    eax, eax
0x18003fff3  jz      short loc_180040033
0x18003fff5  lea     rdx, WPP_GLOBAL_Control
0x18003fffc  mov     rcx, cs:WPP_GLOBAL_Control
0x180040003  cmp     rcx, rdx
0x180040006  jz      short loc_180040027
0x180040008  test    byte ptr [rcx+1Ch], 2
0x18004000c  jz      short loc_180040027
0x18004000e  mov     edx, 20h ; ' '
0x180040013  mov     r9d, eax
0x180040016  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x18004001d  mov     rcx, [rcx+10h]
0x180040021  call    WPP_SF_d
0x180040026  nop
0x180040027  lea     rcx, [rbp+var_28]
0x18004002b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180040030  nop
0x180040031  jmp     short loc_1800400AD
0x180040033  mov     rax, [rsi]
0x180040036  mov     rcx, rsi
0x180040039  mov     rax, [rax+0A0h]
0x180040040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040045  shr     eax, 1Ch
0x180040048  and     eax, 1
0x18004004b  mov     edx, eax; Flags
0x18004004d  mov     rcx, [rbp+Credential]; Credential
0x180040051  call    cs:__imp_CredWriteW
0x180040057  test    eax, eax
0x180040059  jnz     short loc_1800400A1
0x18004005b  call    cs:__imp_GetLastError
0x180040061  mov     ebx, eax
0x180040063  lea     rdx, WPP_GLOBAL_Control
0x18004006a  mov     rcx, cs:WPP_GLOBAL_Control
0x180040071  cmp     rcx, rdx
0x180040074  jz      short loc_180040095
0x180040076  test    byte ptr [rcx+1Ch], 2
0x18004007a  jz      short loc_180040095
0x18004007c  mov     edx, 21h ; '!'
0x180040081  mov     r9d, eax
0x180040084  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x18004008b  mov     rcx, [rcx+10h]
0x18004008f  call    WPP_SF_d
0x180040094  nop
0x180040095  lea     rcx, [rbp+var_28]
0x180040099  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18004009e  nop
0x18004009f  jmp     short loc_1800400AD
0x1800400a1  lea     rcx, [rbp+var_28]
0x1800400a5  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800400aa  nop
0x1800400ab  xor     ebx, ebx
0x1800400ad  mov     rcx, rdi; Resource
0x1800400b0  call    cs:__imp_RtlReleaseResource
0x1800400b6  mov     eax, ebx
0x1800400b8  add     rsp, 58h
0x1800400bc  pop     rdi
0x1800400bd  pop     rsi
0x1800400be  pop     rbx
0x1800400bf  pop     rbp
0x1800400c0  retn
```
