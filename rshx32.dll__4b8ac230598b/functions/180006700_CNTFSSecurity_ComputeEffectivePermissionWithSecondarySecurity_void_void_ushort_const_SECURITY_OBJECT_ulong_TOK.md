# CNTFSSecurity::ComputeEffectivePermissionWithSecondarySecurity(void *,void *,ushort const *,_SECURITY_OBJECT *,ulong,_TOKEN_GROUPS *,AUTHZ_SID_OPERATION *,_TOKEN_GROUPS *,AUTHZ_SID_OPERATION *,_AUTHZ_SECURITY_ATTRIBUTES_INFORMATION *,AUTHZ_SECURITY_ATTRIBUTE_OPERATION *,_AUTHZ_SECURITY_ATTRIBUTES_INFORMATION *,AUTHZ_SECURITY_ATTRIBUTE_OPERATION *,_EFFPERM_RESULT_LIST *)

- ea: `0x180006700`
- end: `0x1800069b2`
- name: `?ComputeEffectivePermissionWithSecondarySecurity@CNTFSSecurity@@UEAAJPEAX0PEBGPEAU_SECURITY_OBJECT@@KPEAU_TOKEN_GROUPS@@PEAW4AUTHZ_SID_OPERATION@@34PEAU_AUTHZ_SECURITY_ATTRIBUTES_INFORMATION@@PEAW4AUTHZ_SECURITY_ATTRIBUTE_OPERATION@@56PEAU_EFFPERM_RESULT_LIST@@@Z`
- size: `690`
- prototype: `__int64 __fastcall(CNTFSSecurity *this, void *, void *, const unsigned __int16 *, struct _SECURITY_OBJECT *, unsigned int, struct _TOKEN_GROUPS *, enum AUTHZ_SID_OPERATION *, struct _TOKEN_GROUPS *, enum AUTHZ_SID_OPERATION *, struct _AUTHZ_SECURITY_ATTRIBUTES_INFORMATION *, enum AUTHZ_SECURITY_ATTRIBUTE_OPERATION *, struct _AUTHZ_SECURITY_ATTRIBUTES_INFORMATION *, enum AUTHZ_SECURITY_ATTRIBUTE_OPERATION *, struct _EFFPERM_RESULT_LIST *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006700`

## import_xrefs

- `msvcrt!wcsnlen` at `0x180006808`
- `msvcrt!wcsnlen` at `0x180006808`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800067e5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800067e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800067b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800067b6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000674e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180006764`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000674e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180006764`
- `AUTHZ!AuthzInitializeResourceManager` at `0x1800068ba`
- `AUTHZ!AuthzInitializeResourceManager` at `0x1800068ba`
- `AUTHZ!AuthzInitializeRemoteResourceManager` at `0x18000688b`
- `AUTHZ!AuthzInitializeRemoteResourceManager` at `0x18000688b`
- `AUTHZ!AuthzComputeEffectivePermission` at `0x18000696d`
- `AUTHZ!AuthzComputeEffectivePermission` at `0x18000696d`

## pseudocode

```c
__int64 __fastcall CNTFSSecurity::ComputeEffectivePermissionWithSecondarySecurity(
        CNTFSSecurity *this,
        void *a2,
        void *a3,
        const unsigned __int16 *a4,
        struct _SECURITY_OBJECT *a5,
        unsigned int a6,
        struct _TOKEN_GROUPS *a7,
        enum AUTHZ_SID_OPERATION *a8,
        struct _TOKEN_GROUPS *a9,
        enum AUTHZ_SID_OPERATION *a10,
        struct _AUTHZ_SECURITY_ATTRIBUTES_INFORMATION *a11,
        enum AUTHZ_SECURITY_ATTRIBUTE_OPERATION *a12,
        struct _AUTHZ_SECURITY_ATTRIBUTES_INFORMATION *a13,
        enum AUTHZ_SECURITY_ATTRIBUTE_OPERATION *a14,
        struct _EFFPERM_RESULT_LIST *a15)
{
  __int64 v19; // rax
  __int64 v20; // rbx
  WCHAR *v21; // rax
  __int64 result; // rax
  _BYTE *v23; // rbx
  signed int LastError; // eax
  bool v25; // sf
  __int16 v26; // [rsp+80h] [rbp-88h] BYREF
  int v27; // [rsp+82h] [rbp-86h]
  __int16 v28; // [rsp+86h] [rbp-82h]
  const wchar_t *v29; // [rsp+88h] [rbp-80h]
  const wchar_t *v30; // [rsp+90h] [rbp-78h]
  const unsigned __int16 *v31; // [rsp+98h] [rbp-70h]
  __int128 v32; // [rsp+A0h] [rbp-68h]
  __int64 v33; // [rsp+B0h] [rbp-58h]

  if ( !a2 || !a5 || !a15 || !IsValidSid(a2) || a3 && !IsValidSid(a3) )
    return 2147942487LL;
  v19 = 0;
  if ( a6 )
  {
    while ( 1 )
    {
      v20 = 6 * v19;
      if ( *((_BYTE *)a5 + 48 * v19 + 40) )
      {
        if ( *((_DWORD *)a5 + 12 * v19 + 9) == 1 )
          break;
      }
      if ( ++v19 >= (unsigned __int64)a6 )
        goto LABEL_15;
    }
    LocalFree(*((HLOCAL *)a5 + 6 * v19));
    v21 = (WCHAR *)LocalAlloc(0x40u, 0x208u);
    *((_QWORD *)a5 + v20) = v21;
    if ( !v21 || LoadStringW(g_hInstance, 0x3Cu, v21, 260) <= 0 )
      return 2147942414LL;
  }
LABEL_15:
  if ( *((_QWORD *)this + 50) )
    goto LABEL_26;
  if ( (unsigned int)wcsnlen(a4, 0x104u) > 2 && *a4 == 92 && a4[1] == 92 )
    a4 += 2;
  v31 = a4;
  v26 = 1;
  v33 = 0;
  v27 = 0;
  v28 = 0;
  v29 = L"9a81c2bd-a525-471d-a4ed-49907c0b23da";
  v30 = L"ncacn_ip_tcp";
  v32 = 0;
  if ( (unsigned int)AuthzInitializeRemoteResourceManager(&v26, (char *)this + 400) )
    goto LABEL_26;
  v23 = (char *)this + 408;
  *((_BYTE *)this + 408) = 1;
  if ( AuthzInitializeResourceManager(1u, 0, 0, 0, L"WithCap", (PAUTHZ_RESOURCE_MANAGER_HANDLE)this + 50) )
    goto LABEL_26;
  LastError = GetLastError();
  v25 = LastError < 0;
  if ( LastError > 0 )
    v25 = 1;
  if ( !v25 )
  {
LABEL_26:
    result = AuthzComputeEffectivePermission(
               a2,
               a3,
               a4,
               a5,
               a6,
               a7,
               a8,
               a9,
               a10,
               a11,
               a12,
               a13,
               a14,
               a15,
               *((_QWORD *)this + 50));
    if ( (int)result < 0 )
      return result;
    v23 = (char *)this + 408;
  }
  else
  {
    result = 0;
  }
  if ( *v23 && (*((_DWORD *)this + 73) || !*((_DWORD *)this + 22)) )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180006700  push    rbx
0x180006702  push    rbp
0x180006703  push    rsi
0x180006704  push    rdi
0x180006705  push    r12
0x180006707  push    r13
0x180006709  push    r14
0x18000670b  push    r15
0x18000670d  sub     rsp, 0C8h
0x180006714  mov     rdi, r9
0x180006717  mov     r15, r8
0x18000671a  mov     r12, rdx
0x18000671d  mov     rsi, rcx
0x180006720  test    rdx, rdx
0x180006723  jz      loc_180006999
0x180006729  mov     rbp, [rsp+108h+arg_20]
0x180006731  test    rbp, rbp
0x180006734  jz      loc_180006999
0x18000673a  mov     r13, [rsp+108h+arg_70]
0x180006742  test    r13, r13
0x180006745  jz      loc_180006999
0x18000674b  mov     rcx, rdx; pSid
0x18000674e  call    cs:__imp_IsValidSid
0x180006754  test    eax, eax
0x180006756  jz      loc_180006999
0x18000675c  test    r15, r15
0x18000675f  jz      short loc_180006772
0x180006761  mov     rcx, r15; pSid
0x180006764  call    cs:__imp_IsValidSid
0x18000676a  test    eax, eax
0x18000676c  jz      loc_180006999
0x180006772  mov     ecx, [rsp+108h+arg_28]
0x180006779  xor     eax, eax
0x18000677b  lea     edx, [rax+1]
0x18000677e  test    rcx, rcx
0x180006781  jz      short loc_1800067EF
0x180006783  lea     rbx, [rax+rax*2]
0x180006787  add     rbx, rbx
0x18000678a  cmp     byte ptr [rbp+rbx*8+28h], 0
0x18000678f  jz      short loc_180006797
0x180006791  cmp     [rbp+rbx*8+24h], edx
0x180006795  jz      short loc_1800067A1
0x180006797  add     rax, rdx
0x18000679a  cmp     rax, rcx
0x18000679d  jb      short loc_180006783
0x18000679f  jmp     short loc_1800067EF
0x1800067a1  mov     rcx, [rbp+rbx*8+0]; hMem
0x1800067a6  call    cs:__imp_LocalFree
0x1800067ac  mov     edx, 208h; uBytes
0x1800067b1  mov     ecx, 40h ; '@'; uFlags
0x1800067b6  call    cs:__imp_LocalAlloc
0x1800067bc  mov     [rbp+rbx*8+0], rax
0x1800067c1  test    rax, rax
0x1800067c4  jnz     short loc_1800067D0
0x1800067c6  mov     eax, 8007000Eh
0x1800067cb  jmp     loc_18000699E
0x1800067d0  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800067d7  mov     r9d, 104h; cchBufferMax
0x1800067dd  mov     r8, rax; lpBuffer
0x1800067e0  mov     edx, 3Ch ; '<'; uID
0x1800067e5  call    cs:__imp_LoadStringW
0x1800067eb  test    eax, eax
0x1800067ed  jle     short loc_1800067C6
0x1800067ef  lea     r14, [rsi+190h]
0x1800067f6  cmp     qword ptr [r14], 0
0x1800067fa  jnz     loc_1800068E1
0x180006800  mov     edx, 104h; MaxCount
0x180006805  mov     rcx, rdi; Source
0x180006808  call    cs:__imp_wcsnlen
0x18000680e  cmp     eax, 2
0x180006811  jbe     short loc_180006824
0x180006813  cmp     word ptr [rdi], 5Ch ; '\'
0x180006817  jnz     short loc_180006824
0x180006819  cmp     word ptr [rdi+2], 5Ch ; '\'
0x18000681e  jnz     short loc_180006824
0x180006820  add     rdi, 4
0x180006824  mov     eax, 1
0x180006829  mov     [rsp+108h+var_70], rdi
0x180006831  mov     [rsp+108h+var_88], ax
0x180006839  lea     rcx, [rsp+108h+var_88]
0x180006841  xor     eax, eax
0x180006843  mov     [rsp+108h+var_58], 0
0x18000684f  mov     [rsp+108h+var_86], eax
0x180006856  xorps   xmm0, xmm0
0x180006859  mov     [rsp+108h+var_82], ax
0x180006861  mov     rdx, r14
0x180006864  lea     rax, a9a81c2bdA52547; "9a81c2bd-a525-471d-a4ed-49907c0b23da"
0x18000686b  mov     [rsp+108h+var_80], rax
0x180006873  lea     rax, aNcacnIpTcp; "ncacn_ip_tcp"
0x18000687a  mov     [rsp+108h+var_78], rax
0x180006882  movdqu  [rsp+108h+var_68], xmm0
0x18000688b  call    cs:__imp_AuthzInitializeRemoteResourceManager
0x180006891  test    eax, eax
0x180006893  jnz     short loc_1800068E1
0x180006895  lea     ecx, [rax+1]; Flags
0x180006898  mov     [rsp+108h+phAuthzResourceManager], r14; phAuthzResourceManager
0x18000689d  lea     rax, szResourceManagerName; "WithCap"
0x1800068a4  xor     r9d, r9d; pfnFreeDynamicGroups
0x1800068a7  lea     rbx, [rsi+198h]
0x1800068ae  mov     [rsp+108h+szResourceManagerName], rax; szResourceManagerName
0x1800068b3  xor     r8d, r8d; pfnComputeDynamicGroups
0x1800068b6  mov     [rbx], cl
0x1800068b8  xor     edx, edx; pfnDynamicAccessCheck
0x1800068ba  call    cs:__imp_AuthzInitializeResourceManager
0x1800068c0  test    eax, eax
0x1800068c2  jnz     short loc_1800068E1
0x1800068c4  call    cs:__imp_GetLastError
0x1800068ca  test    eax, eax
0x1800068cc  jle     short loc_1800068D8
0x1800068ce  movzx   eax, ax
0x1800068d1  or      eax, 80070000h
0x1800068d6  test    eax, eax
0x1800068d8  jns     short loc_1800068E1
0x1800068da  xor     eax, eax
0x1800068dc  jmp     loc_18000697E
0x1800068e1  mov     rax, [r14]
0x1800068e4  mov     r9, rbp
0x1800068e7  mov     [rsp+108h+var_98], rax
0x1800068ec  mov     r8, rdi
0x1800068ef  mov     rax, [rsp+108h+arg_68]
0x1800068f7  mov     rdx, r15
0x1800068fa  mov     [rsp+108h+var_A0], r13
0x1800068ff  mov     rcx, r12
0x180006902  mov     [rsp+108h+var_A8], rax
0x180006907  mov     rax, [rsp+108h+arg_60]
0x18000690f  mov     [rsp+108h+var_B0], rax
0x180006914  mov     rax, [rsp+108h+arg_58]
0x18000691c  mov     [rsp+108h+var_B8], rax
0x180006921  mov     rax, [rsp+108h+arg_50]
0x180006929  mov     [rsp+108h+var_C0], rax
0x18000692e  mov     rax, [rsp+108h+arg_48]
0x180006936  mov     [rsp+108h+var_C8], rax
0x18000693b  mov     rax, [rsp+108h+arg_40]
0x180006943  mov     [rsp+108h+var_D0], rax
0x180006948  mov     rax, [rsp+108h+arg_38]
0x180006950  mov     [rsp+108h+var_D8], rax
0x180006955  mov     rax, [rsp+108h+arg_30]
0x18000695d  mov     [rsp+108h+phAuthzResourceManager], rax
0x180006962  mov     eax, [rsp+108h+arg_28]
0x180006969  mov     dword ptr [rsp+108h+szResourceManagerName], eax
0x18000696d  call    cs:__imp_AuthzComputeEffectivePermission
0x180006973  test    eax, eax
0x180006975  js      short loc_18000699E
0x180006977  lea     rbx, [rsi+198h]
0x18000697e  cmp     byte ptr [rbx], 0
0x180006981  jz      short loc_18000699E
0x180006983  cmp     dword ptr [rsi+124h], 0
0x18000698a  jnz     short loc_180006992
0x18000698c  cmp     dword ptr [rsi+58h], 0
0x180006990  jnz     short loc_18000699E
0x180006992  mov     eax, 1
0x180006997  jmp     short loc_18000699E
0x180006999  mov     eax, 80070057h
0x18000699e  add     rsp, 0C8h
0x1800069a5  pop     r15
0x1800069a7  pop     r14
0x1800069a9  pop     r13
0x1800069ab  pop     r12
0x1800069ad  pop     rdi
0x1800069ae  pop     rsi
0x1800069af  pop     rbp
0x1800069b0  pop     rbx
0x1800069b1  retn
```
