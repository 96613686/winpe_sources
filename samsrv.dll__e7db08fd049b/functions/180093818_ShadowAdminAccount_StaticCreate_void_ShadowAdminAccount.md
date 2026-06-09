# ShadowAdminAccount::StaticCreate(void *,ShadowAdminAccount * *)

- ea: `0x180093818`
- end: `0x180093b09`
- name: `?StaticCreate@ShadowAdminAccount@@SAJPEAXPEAPEAV1@@Z`
- size: `753`
- prototype: `__int64 __fastcall(void *, struct ShadowAdminAccount **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180092b08`

## callees

- `0x180021460`
- `0x180023760`
- `0x180027e24`
- `0x18002c948`
- `0x180037284`
- `0x1800372ac`
- `0x18008fcac`
- `0x1800908f0`
- `0x180090ec4`
- `0x180091338`
- `0x1800928a8`
- `0x180093818`
- `0x1800ab3e8`
- `0x1800bb5cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009389f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009389f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093a9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093aa5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093aaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093ab9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093a9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093aa5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093aaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093ab9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180093895`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180093895`

## pseudocode

```c
__int64 __fastcall ShadowAdminAccount::StaticCreate(void *a1, struct ShadowAdminAccount **a2)
{
  void *v3; // r14
  void *v4; // r15
  ShadowAdminAccount *v6; // rax
  ShadowAdminAccount *v7; // rax
  ShadowAdminAccount *v8; // rbx
  int v9; // edi
  DWORD LastError; // eax
  int v11; // eax
  PUNICODE_STRING v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // eax
  int v16; // eax
  int v17; // eax
  HLOCAL hMem; // [rsp+30h] [rbp-10h] BYREF
  void *v20; // [rsp+88h] [rbp+48h] BYREF
  void *v21; // [rsp+90h] [rbp+50h] BYREF
  LPWSTR StringSid; // [rsp+98h] [rbp+58h] BYREF

  hMem = 0;
  v3 = 0;
  StringSid = 0;
  v4 = 0;
  v20 = 0;
  v21 = 0;
  *a2 = 0;
  v6 = (ShadowAdminAccount *)operator new(0x88u);
  if ( !v6 )
  {
    v8 = 0;
    goto LABEL_43;
  }
  v7 = ShadowAdminAccount::ShadowAdminAccount(v6);
  v8 = v7;
  if ( !v7 )
  {
LABEL_43:
    v9 = -1073741801;
    goto LABEL_44;
  }
  v9 = SampCopySid((void **)v7 + 2, a1);
  if ( v9 < 0 )
    goto LABEL_44;
  if ( !ConvertSidToStringSidW(a1, &StringSid) )
  {
    LastError = GetLastError();
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 92, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, LastError);
    }
    goto LABEL_43;
  }
  v11 = SampCopyString(StringSid, (unsigned __int16 **)v8 + 3);
  v9 = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v13 = 93;
LABEL_12:
      v14 = (unsigned int)v11;
LABEL_13:
      WPP_SF_d(v12[3].Buffer, v13, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, v14);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  v15 = ShadowAdminAccount::LookupAccountSidHelper(
          a1,
          (unsigned __int16 **)v8 + 6,
          (unsigned __int16 **)v8 + 5,
          (unsigned __int16 **)v8 + 7);
  v9 = 0;
  if ( v15 != -1073741709 )
    v9 = v15;
  if ( v9 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v13 = 94;
      v14 = (unsigned int)v9;
      goto LABEL_13;
    }
    goto LABEL_44;
  }
  v16 = IsLocalUser(a1);
  *((_DWORD *)v8 + 16) = v16;
  if ( !v16 )
  {
    v11 = ShadowAdminAccount::BuildShadowAccountKeyPath((void **)v8);
    v9 = v11;
    if ( v11 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        v13 = 98;
        goto LABEL_12;
      }
      goto LABEL_44;
    }
    goto LABEL_37;
  }
  v11 = SampSplitSid(a1, &hMem, (ULONG *)v8 + 8);
  v9 = v11;
  if ( v11 >= 0 )
  {
    v17 = SampQueryShadowAccountLinks(a1, &v21, &v20);
    v9 = v17;
    if ( v17 < 0 )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 96, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, (unsigned int)v17);
      }
      v4 = v21;
LABEL_30:
      v3 = v20;
      goto LABEL_44;
    }
    v4 = v21;
    if ( v21 )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 97, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids);
      }
      v9 = -1073741811;
      goto LABEL_30;
    }
    *((_QWORD *)v8 + 11) = v20;
LABEL_37:
    *a2 = v8;
    v8 = 0;
    goto LABEL_44;
  }
  v12 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
    && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    v13 = 95;
    goto LABEL_12;
  }
LABEL_44:
  LocalFree(v3);
  LocalFree(v4);
  LocalFree(StringSid);
  LocalFree(hMem);
  if ( v8 )
    NLRefcountableObject::ReleaseReference(v8);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 99, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids, (unsigned int)v9, v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180093818  push    rbp
0x18009381a  push    rbx
0x18009381b  push    rsi
0x18009381c  push    rdi
0x18009381d  push    r12
0x18009381f  push    r14
0x180093821  push    r15
0x180093823  mov     rbp, rsp
0x180093826  sub     rsp, 40h
0x18009382a  mov     rsi, rcx
0x18009382d  mov     [rbp+hMem], 0
0x180093835  xor     r14d, r14d
0x180093838  mov     [rbp+StringSid], 0
0x180093840  xor     r15d, r15d
0x180093843  mov     [rbp+arg_8], r14
0x180093847  mov     ecx, 88h; Size
0x18009384c  mov     [rbp+arg_10], r15
0x180093850  mov     [rdx], r14
0x180093853  mov     r12, rdx
0x180093856  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009385b  test    rax, rax
0x18009385e  jz      loc_180093A92
0x180093864  mov     rcx, rax; this
0x180093867  call    ??0ShadowAdminAccount@@AEAA@XZ; ShadowAdminAccount::ShadowAdminAccount(void)
0x18009386c  mov     rbx, rax
0x18009386f  test    rax, rax
0x180093872  jz      loc_180093A94
0x180093878  lea     rcx, [rax+10h]; void **
0x18009387c  mov     rdx, rsi; void *
0x18009387f  call    ?SampCopySid@@YAJPEAPEAXPEAX@Z; SampCopySid(void * *,void *)
0x180093884  mov     edi, eax
0x180093886  test    eax, eax
0x180093888  js      loc_180093A99
0x18009388e  lea     rdx, [rbp+StringSid]; StringSid
0x180093892  mov     rcx, rsi; Sid
0x180093895  call    cs:__imp_ConvertSidToStringSidW
0x18009389b  test    eax, eax
0x18009389d  jnz     short loc_1800938DF
0x18009389f  call    cs:__imp_GetLastError
0x1800938a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800938ac  test    dword ptr [rcx+44h], 400h
0x1800938b3  jz      loc_180093A94
0x1800938b9  cmp     byte ptr [rcx+41h], 2
0x1800938bd  jb      loc_180093A94
0x1800938c3  mov     rcx, [rcx+38h]
0x1800938c7  lea     edx, [r15+5Ch]
0x1800938cb  mov     r9d, eax
0x1800938ce  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x1800938d5  call    WPP_SF_d
0x1800938da  jmp     loc_180093A94
0x1800938df  mov     rcx, [rbp+StringSid]; unsigned __int16 *
0x1800938e3  lea     rdx, [rbx+18h]; unsigned __int16 **
0x1800938e7  call    ?SampCopyString@@YAJPEAGPEAPEAG@Z; SampCopyString(ushort *,ushort * *)
0x1800938ec  mov     edi, eax
0x1800938ee  test    eax, eax
0x1800938f0  jns     short loc_18009392D
0x1800938f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800938f9  test    dword ptr [rcx+44h], 400h
0x180093900  jz      loc_180093A99
0x180093906  cmp     byte ptr [rcx+41h], 2
0x18009390a  jb      loc_180093A99
0x180093910  mov     edx, 5Dh ; ']'
0x180093915  mov     r9d, eax
0x180093918  mov     rcx, [rcx+38h]
0x18009391c  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x180093923  call    WPP_SF_d
0x180093928  jmp     loc_180093A99
0x18009392d  lea     r9, [rbx+38h]; unsigned __int16 **
0x180093931  mov     rcx, rsi; Sid
0x180093934  lea     r8, [rbx+28h]; unsigned __int16 **
0x180093938  lea     rdx, [rbx+30h]; unsigned __int16 **
0x18009393c  call    ?LookupAccountSidHelper@ShadowAdminAccount@@CAJPEAXPEAPEAG11@Z; ShadowAdminAccount::LookupAccountSidHelper(void *,ushort * *,ushort * *,ushort * *)
0x180093941  xor     edi, edi
0x180093943  cmp     eax, 0C0000073h
0x180093948  cmovnz  edi, eax
0x18009394b  test    edi, edi
0x18009394d  jns     short loc_180093977
0x18009394f  mov     rcx, cs:WPP_GLOBAL_Control
0x180093956  test    dword ptr [rcx+44h], 400h
0x18009395d  jz      loc_180093A99
0x180093963  cmp     byte ptr [rcx+41h], 2
0x180093967  jb      loc_180093A99
0x18009396d  mov     edx, 5Eh ; '^'
0x180093972  mov     r9d, edi
0x180093975  jmp     short loc_180093918
0x180093977  mov     rcx, rsi; void *
0x18009397a  call    ?IsLocalUser@@YAHPEAX@Z; IsLocalUser(void *)
0x18009397f  mov     [rbx+40h], eax
0x180093982  test    eax, eax
0x180093984  jz      loc_180093A64
0x18009398a  lea     r8, [rbx+20h]
0x18009398e  mov     rcx, rsi; Src
0x180093991  lea     rdx, [rbp+hMem]
0x180093995  call    SampSplitSid
0x18009399a  mov     edi, eax
0x18009399c  test    eax, eax
0x18009399e  jns     short loc_1800939C8
0x1800939a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800939a7  test    dword ptr [rcx+44h], 400h
0x1800939ae  jz      loc_180093A99
0x1800939b4  cmp     byte ptr [rcx+41h], 2
0x1800939b8  jb      loc_180093A99
0x1800939be  mov     edx, 5Fh ; '_'
0x1800939c3  jmp     loc_180093915
0x1800939c8  lea     r8, [rbp+arg_8]; void **
0x1800939cc  mov     rcx, rsi; void *
0x1800939cf  lea     rdx, [rbp+arg_10]; void **
0x1800939d3  call    ?SampQueryShadowAccountLinks@@YAJPEAXPEAPEAX1@Z; SampQueryShadowAccountLinks(void *,void * *,void * *)
0x1800939d8  mov     edi, eax
0x1800939da  test    eax, eax
0x1800939dc  jns     short loc_180093A19
0x1800939de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800939e5  test    dword ptr [rcx+44h], 400h
0x1800939ec  jz      short loc_180093A0C
0x1800939ee  cmp     byte ptr [rcx+41h], 2
0x1800939f2  jb      short loc_180093A0C
0x1800939f4  mov     rcx, [rcx+38h]
0x1800939f8  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x1800939ff  mov     edx, 60h ; '`'
0x180093a04  mov     r9d, eax
0x180093a07  call    WPP_SF_d
0x180093a0c  mov     r15, [rbp+arg_10]
0x180093a10  mov     r14, [rbp+arg_8]
0x180093a14  jmp     loc_180093A99
0x180093a19  mov     r15, [rbp+arg_10]
0x180093a1d  test    r15, r15
0x180093a20  jz      short loc_180093A54
0x180093a22  mov     rcx, cs:WPP_GLOBAL_Control
0x180093a29  test    dword ptr [rcx+44h], 400h
0x180093a30  jz      short loc_180093A4D
0x180093a32  cmp     byte ptr [rcx+41h], 2
0x180093a36  jb      short loc_180093A4D
0x180093a38  mov     rcx, [rcx+38h]
0x180093a3c  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x180093a43  mov     edx, 61h ; 'a'
0x180093a48  call    WPP_SF_
0x180093a4d  mov     edi, 0C000000Dh
0x180093a52  jmp     short loc_180093A10
0x180093a54  mov     rax, [rbp+arg_8]
0x180093a58  mov     [rbx+58h], rax
0x180093a5c  mov     [r12], rbx
0x180093a60  xor     ebx, ebx
0x180093a62  jmp     short loc_180093A99
0x180093a64  mov     rcx, rbx; this
0x180093a67  call    ?BuildShadowAccountKeyPath@ShadowAdminAccount@@AEAAJXZ; ShadowAdminAccount::BuildShadowAccountKeyPath(void)
0x180093a6c  mov     edi, eax
0x180093a6e  test    eax, eax
0x180093a70  jns     short loc_180093A5C
0x180093a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180093a79  test    dword ptr [rcx+44h], 400h
0x180093a80  jz      short loc_180093A99
0x180093a82  cmp     byte ptr [rcx+41h], 2
0x180093a86  jb      short loc_180093A99
0x180093a88  mov     edx, 62h ; 'b'
0x180093a8d  jmp     loc_180093915
0x180093a92  xor     ebx, ebx
0x180093a94  mov     edi, 0C0000017h
0x180093a99  mov     rcx, r14; hMem
0x180093a9c  call    cs:__imp_LocalFree
0x180093aa2  mov     rcx, r15; hMem
0x180093aa5  call    cs:__imp_LocalFree
0x180093aab  mov     rcx, [rbp+StringSid]; hMem
0x180093aaf  call    cs:__imp_LocalFree
0x180093ab5  mov     rcx, [rbp+hMem]; hMem
0x180093ab9  call    cs:__imp_LocalFree
0x180093abf  test    rbx, rbx
0x180093ac2  jz      short loc_180093ACC
0x180093ac4  mov     rcx, rbx; this
0x180093ac7  call    ?ReleaseReference@NLRefcountableObject@@QEAAXXZ; NLRefcountableObject::ReleaseReference(void)
0x180093acc  mov     rcx, cs:WPP_GLOBAL_Control
0x180093ad3  test    dword ptr [rcx+44h], 20000h
0x180093ada  jz      short loc_180093AF8
0x180093adc  mov     rcx, [rcx+38h]
0x180093ae0  lea     r8, WPP_99473abb2ee73b6c7cc9b39fb0106789_Traceguids
0x180093ae7  mov     edx, 63h ; 'c'
0x180093aec  mov     [rsp+40h+var_20], edi
0x180093af0  mov     r9d, edi
0x180093af3  call    WPP_SF_Dd
0x180093af8  mov     eax, edi
0x180093afa  add     rsp, 40h
0x180093afe  pop     r15
0x180093b00  pop     r14
0x180093b02  pop     r12
0x180093b04  pop     rdi
0x180093b05  pop     rsi
0x180093b06  pop     rbx
0x180093b07  pop     rbp
0x180093b08  retn
```
