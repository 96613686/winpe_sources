# CInfraConnectPage::SetElevatedObject(void)

- ea: `0x1800222dc`
- end: `0x180022481`
- name: `?SetElevatedObject@CInfraConnectPage@@AEAAJXZ`
- size: `421`
- prototype: `__int64 __fastcall(CInfraConnectPage *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021c98`

## callees

- `0x18000d578`
- `0x180014ef8`
- `0x1800222dc`
- `0x180022488`
- `0x180023054`

## import_xrefs

- `wlanapi!WlanCloseHandle` at `0x1800223b0`
- `wlanapi!WlanCloseHandle` at `0x1800223b0`
- `wlanapi!WlanGetSecuritySettings` at `0x18002238b`
- `wlanapi!WlanGetSecuritySettings` at `0x18002238b`
- `wlanapi!WlanFreeMemory` at `0x1800223bf`
- `wlanapi!WlanFreeMemory` at `0x1800223bf`
- `wlanapi!WlanOpenHandle` at `0x180022368`
- `wlanapi!WlanOpenHandle` at `0x180022368`

## pseudocode

```c
__int64 __fastcall CInfraConnectPage::SetElevatedObject(
        CInfraConnectPage *this,
        const struct _GUID *a2,
        const struct _GUID *a3)
{
  bool v4; // di
  signed int SecuritySettings; // ebx
  struct IWlanPrefLUA **v6; // rdi
  DWORD pdwGrantedAccess; // [rsp+60h] [rbp+30h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+68h] [rbp+38h] BYREF
  void *phClientHandle; // [rsp+70h] [rbp+40h] BYREF
  LPWSTR pstrCurrentSDDL; // [rsp+78h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 26, WPP_1064fdabddc73196039d87943bb008b3_Traceguids);
  }
  v4 = 1;
  if ( *((_BYTE *)this + 1502) )
  {
    pstrCurrentSDDL = 0;
    phClientHandle = 0;
    pdwGrantedAccess = 0;
    v4 = 0;
    pdwNegotiatedVersion = 0;
    SecuritySettings = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
    if ( !SecuritySettings )
    {
      SecuritySettings = WlanGetSecuritySettings(
                           phClientHandle,
                           wlan_secure_add_new_all_user_profiles,
                           0,
                           &pstrCurrentSDDL,
                           &pdwGrantedAccess);
      if ( !SecuritySettings )
        v4 = (~pdwGrantedAccess & 0x70023) == 0;
    }
    if ( phClientHandle )
      WlanCloseHandle(phClientHandle, 0);
    if ( pstrCurrentSDDL )
      WlanFreeMemory(pstrCurrentSDDL);
    if ( SecuritySettings )
    {
      if ( SecuritySettings > 0 )
        SecuritySettings = (unsigned __int16)SecuritySettings | 0x80070000;
      v6 = (struct IWlanPrefLUA **)((char *)this + 264);
LABEL_21:
      if ( SecuritySettings >= 0 )
        goto LABEL_24;
      goto LABEL_22;
    }
  }
  SecuritySettings = 0;
  *(_BYTE *)(*((_QWORD *)this + 189) + 56LL) = !v4;
  if ( v4 || *(_DWORD *)(*((_QWORD *)this + 189) + 64LL) )
    goto LABEL_24;
  v6 = (struct IWlanPrefLUA **)((char *)this + 264);
  SecuritySettings = NtlCoCreateInstanceAsNetConfigOpOrAdmin(*((HWND *)this + 13), a2, a3, (void **)this + 33);
  if ( SecuritySettings >= 0 )
  {
    SecuritySettings = ProfileInfo::SetElevatedObject(*((ProfileInfo **)this + 189), *v6);
    goto LABEL_21;
  }
LABEL_22:
  if ( *v6 )
    ATL::AtlComPtrAssign((struct IUnknown **)v6, 0);
LABEL_24:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 27, WPP_1064fdabddc73196039d87943bb008b3_Traceguids);
  }
  return (unsigned int)SecuritySettings;
}

```

## disassembly

```asm
0x1800222dc  push    rbp
0x1800222de  push    rbx
0x1800222df  push    rsi
0x1800222e0  push    rdi
0x1800222e1  push    r12
0x1800222e3  mov     rbp, rsp
0x1800222e6  sub     rsp, 30h
0x1800222ea  mov     rsi, rcx
0x1800222ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222f4  lea     r12, WPP_GLOBAL_Control
0x1800222fb  cmp     rcx, r12
0x1800222fe  jz      short loc_18002232A
0x180022300  cmp     byte ptr [rcx+91h], 4
0x180022307  jb      short loc_18002232A
0x180022309  test    byte ptr [rcx+94h], 1
0x180022310  jz      short loc_18002232A
0x180022312  mov     rcx, [rcx+88h]
0x180022319  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x180022320  mov     edx, 1Ah
0x180022325  call    WPP_SF_
0x18002232a  cmp     byte ptr [rsi+5DEh], 0
0x180022331  mov     dil, 1
0x180022334  jz      loc_1800223DD
0x18002233a  xor     edx, edx; pReserved
0x18002233c  mov     [rbp+pstrCurrentSDDL], 0
0x180022344  lea     r9, [rbp+phClientHandle]; phClientHandle
0x180022348  mov     [rbp+phClientHandle], 0
0x180022350  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180022354  mov     [rbp+arg_0], 0
0x18002235b  xor     dil, dil
0x18002235e  mov     [rbp+pdwNegotiatedVersion], 0
0x180022365  lea     ecx, [rdx+2]; dwClientVersion
0x180022368  call    cs:__imp_WlanOpenHandle
0x18002236e  mov     ebx, eax
0x180022370  test    eax, eax
0x180022372  jnz     short loc_1800223A5
0x180022374  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180022378  lea     rax, [rbp+arg_0]
0x18002237c  lea     r9, [rbp+pstrCurrentSDDL]; pstrCurrentSDDL
0x180022380  mov     [rsp+30h+pdwGrantedAccess], rax; pdwGrantedAccess
0x180022385  xor     r8d, r8d; pValueType
0x180022388  lea     edx, [rbx+9]; SecurableObject
0x18002238b  call    cs:__imp_WlanGetSecuritySettings
0x180022391  mov     ebx, eax
0x180022393  test    eax, eax
0x180022395  jnz     short loc_1800223A5
0x180022397  mov     eax, [rbp+arg_0]
0x18002239a  not     eax
0x18002239c  test    eax, 70023h
0x1800223a1  setz    dil
0x1800223a5  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x1800223a9  test    rcx, rcx
0x1800223ac  jz      short loc_1800223B6
0x1800223ae  xor     edx, edx; pReserved
0x1800223b0  call    cs:__imp_WlanCloseHandle
0x1800223b6  mov     rcx, [rbp+pstrCurrentSDDL]; pMemory
0x1800223ba  test    rcx, rcx
0x1800223bd  jz      short loc_1800223C5
0x1800223bf  call    cs:__imp_WlanFreeMemory
0x1800223c5  test    ebx, ebx
0x1800223c7  jz      short loc_1800223DD
0x1800223c9  jle     short loc_1800223D4
0x1800223cb  movzx   ebx, bx
0x1800223ce  or      ebx, 80070000h
0x1800223d4  lea     rdi, [rsi+108h]
0x1800223db  jmp     short loc_18002242A
0x1800223dd  mov     rax, [rsi+5E8h]
0x1800223e4  mov     cl, dil
0x1800223e7  xor     cl, 1
0x1800223ea  xor     ebx, ebx
0x1800223ec  mov     [rax+38h], cl
0x1800223ef  test    dil, dil
0x1800223f2  jnz     short loc_18002243E
0x1800223f4  mov     rax, [rsi+5E8h]
0x1800223fb  cmp     [rax+40h], ebx
0x1800223fe  jnz     short loc_18002243E
0x180022400  mov     rcx, [rsi+68h]; HWND
0x180022404  lea     rdi, [rsi+108h]
0x18002240b  mov     r9, rdi; void **
0x18002240e  call    ?NtlCoCreateInstanceAsNetConfigOpOrAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; NtlCoCreateInstanceAsNetConfigOpOrAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x180022413  mov     ebx, eax
0x180022415  test    eax, eax
0x180022417  js      short loc_18002242E
0x180022419  mov     rdx, [rdi]; struct IWlanPrefLUA *
0x18002241c  mov     rcx, [rsi+5E8h]; this
0x180022423  call    ?SetElevatedObject@ProfileInfo@@QEAAJPEAUIWlanPrefLUA@@@Z; ProfileInfo::SetElevatedObject(IWlanPrefLUA *)
0x180022428  mov     ebx, eax
0x18002242a  test    ebx, ebx
0x18002242c  jns     short loc_18002243E
0x18002242e  cmp     qword ptr [rdi], 0
0x180022432  jz      short loc_18002243E
0x180022434  xor     edx, edx; struct IUnknown *
0x180022436  mov     rcx, rdi; struct IUnknown **
0x180022439  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002243e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022445  cmp     rcx, r12
0x180022448  jz      short loc_180022474
0x18002244a  cmp     byte ptr [rcx+91h], 4
0x180022451  jb      short loc_180022474
0x180022453  test    byte ptr [rcx+94h], 1
0x18002245a  jz      short loc_180022474
0x18002245c  mov     rcx, [rcx+88h]
0x180022463  lea     r8, WPP_1064fdabddc73196039d87943bb008b3_Traceguids
0x18002246a  mov     edx, 1Bh
0x18002246f  call    WPP_SF_
0x180022474  mov     eax, ebx
0x180022476  add     rsp, 30h
0x18002247a  pop     r12
0x18002247c  pop     rdi
0x18002247d  pop     rsi
0x18002247e  pop     rbx
0x18002247f  pop     rbp
0x180022480  retn
```
