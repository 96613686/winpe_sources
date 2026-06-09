# CElevateWlanUi::SetProfile(_GUID const &,ulong,ushort *,ushort *,int,ulong *)

- ea: `0x180011890`
- end: `0x18001193a`
- name: `?SetProfile@CElevateWlanUi@@UEAAJAEBU_GUID@@KPEAG1HPEAK@Z`
- size: `170`
- prototype: `__int64 __fastcall(CElevateWlanUi *this, const struct _GUID *, DWORD, unsigned __int16 *, unsigned __int16 *strAllUserProfileSecurity, BOOL bOverwrite, unsigned int *pdwReasonCode)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011890`

## import_xrefs

- `wlanapi!WlanOpenHandle` at `0x1800118c0`
- `wlanapi!WlanOpenHandle` at `0x1800118c0`
- `wlanapi!WlanCloseHandle` at `0x18001191c`
- `wlanapi!WlanCloseHandle` at `0x18001191c`
- `wlanapi!WlanSetProfile` at `0x180011908`
- `wlanapi!WlanSetProfile` at `0x180011908`

## pseudocode

```c
__int64 __fastcall CElevateWlanUi::SetProfile(
        CElevateWlanUi *this,
        const struct _GUID *a2,
        DWORD a3,
        unsigned __int16 *a4,
        unsigned __int16 *strAllUserProfileSecurity,
        BOOL bOverwrite,
        unsigned int *pdwReasonCode)
{
  signed int v10; // ebx
  DWORD v12; // [rsp+40h] [rbp-38h] BYREF
  HANDLE hClientHandle; // [rsp+48h] [rbp-30h] BYREF

  v12 = 0;
  hClientHandle = 0;
  v10 = WlanOpenHandle(2u, 0, &v12, &hClientHandle);
  if ( !v10 )
    v10 = WlanSetProfile(hClientHandle, a2, a3, a4, strAllUserProfileSecurity, bOverwrite, 0, pdwReasonCode);
  if ( hClientHandle )
    WlanCloseHandle(hClientHandle, 0);
  if ( v10 > 0 )
    return (unsigned __int16)v10 | 0x80070000;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180011890  mov     rax, rsp
0x180011893  push    rbx
0x180011894  push    rbp
0x180011895  push    rsi
0x180011896  push    rdi
0x180011897  sub     rsp, 58h
0x18001189b  mov     rbp, rdx
0x18001189e  mov     dword ptr [rax-38h], 0
0x1800118a5  xor     edx, edx; pReserved
0x1800118a7  mov     qword ptr [rax-30h], 0
0x1800118af  mov     rdi, r9
0x1800118b2  mov     esi, r8d
0x1800118b5  lea     r9, [rax-30h]; phClientHandle
0x1800118b9  lea     r8, [rax-38h]; pdwNegotiatedVersion
0x1800118bd  lea     ecx, [rdx+2]; dwClientVersion
0x1800118c0  call    cs:__imp_WlanOpenHandle
0x1800118c6  mov     ebx, eax
0x1800118c8  test    eax, eax
0x1800118ca  jnz     short loc_180011910
0x1800118cc  mov     rax, [rsp+78h+arg_30]
0x1800118d4  mov     r9, rdi; strProfileXml
0x1800118d7  mov     rcx, [rsp+78h+hClientHandle]; hClientHandle
0x1800118dc  mov     r8d, esi; dwFlags
0x1800118df  mov     [rsp+78h+pdwReasonCode], rax; pdwReasonCode
0x1800118e4  mov     rdx, rbp; pInterfaceGuid
0x1800118e7  mov     eax, [rsp+78h+arg_28]
0x1800118ee  mov     [rsp+78h+pReserved], 0; pReserved
0x1800118f7  mov     [rsp+78h+bOverwrite], eax; bOverwrite
0x1800118fb  mov     rax, [rsp+78h+arg_20]
0x180011903  mov     [rsp+78h+strAllUserProfileSecurity], rax; strAllUserProfileSecurity
0x180011908  call    cs:__imp_WlanSetProfile
0x18001190e  mov     ebx, eax
0x180011910  mov     rcx, [rsp+78h+hClientHandle]; hClientHandle
0x180011915  test    rcx, rcx
0x180011918  jz      short loc_180011922
0x18001191a  xor     edx, edx; pReserved
0x18001191c  call    cs:__imp_WlanCloseHandle
0x180011922  test    ebx, ebx
0x180011924  jle     short loc_18001192F
0x180011926  movzx   ebx, bx
0x180011929  or      ebx, 80070000h
0x18001192f  mov     eax, ebx
0x180011931  add     rsp, 58h
0x180011935  pop     rdi
0x180011936  pop     rsi
0x180011937  pop     rbp
0x180011938  pop     rbx
0x180011939  retn
```
