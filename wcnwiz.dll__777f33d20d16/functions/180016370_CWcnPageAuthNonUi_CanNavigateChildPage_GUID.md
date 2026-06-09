# CWcnPageAuthNonUi::CanNavigateChildPage(_GUID *)

- ea: `0x180016370`
- end: `0x18001647e`
- name: `?CanNavigateChildPage@CWcnPageAuthNonUi@@UEAAJPEAU_GUID@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(CWcnPageAuthNonUi *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180016370`

## import_xrefs

- `KERNEL32!RegGetValueW` at `0x1800163f9`
- `KERNEL32!RegGetValueW` at `0x1800163f9`

## string_xrefs

- `0x1800163a7`: `OverrideConfigMethods`

## pseudocode

```c
__int64 __fastcall CWcnPageAuthNonUi::CanNavigateChildPage(CWcnPageAuthNonUi *this, struct _GUID *a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  int v6; // edi
  __int64 v7; // rcx
  int v8; // eax
  GUID v9; // xmm0
  int v10; // eax
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+18h] BYREF

  if ( *((_BYTE *)this + 152) )
  {
    result = 0;
    *a2 = GUID_NULL;
    return result;
  }
  v5 = *((_QWORD *)this + 18);
  *((_BYTE *)this + 152) = 1;
  v6 = *(_DWORD *)(v5 + 120);
  pvData = 0;
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\WCN",
          L"OverrideConfigMethods",
          0x10u,
          0,
          &pvData,
          &pcbData)
    && pvData )
  {
    LOBYTE(v6) = pvData;
  }
  *(_DWORD *)(*((_QWORD *)this + 18) + 12LL) &= 0xFFFFFFF8;
  v7 = *((_QWORD *)this + 18);
  if ( *(_BYTE *)(v7 + 132) && (*(_BYTE *)(v7 + 136) & 1) != 0 )
  {
    *(_DWORD *)(v7 + 12) |= 2u;
LABEL_15:
    v9 = CLSID_WcnPageConfiguredPinMaster;
    goto LABEL_16;
  }
  v8 = *(_DWORD *)(v7 + 12);
  if ( (v6 & 0x80u) == 0 )
  {
    if ( (v6 & 8) != 0 )
      v10 = v8 | 2;
    else
      v10 = v8 | 4;
    *(_DWORD *)(v7 + 12) = v10;
    goto LABEL_15;
  }
  v9 = CLSID_WcnPageConfiguredPbcMaster;
  *(_DWORD *)(v7 + 12) = v8 | 1;
LABEL_16:
  *a2 = v9;
  return 1;
}

```

## disassembly

```asm
0x180016370  mov     [rsp+arg_8], rbx
0x180016375  mov     [rsp+arg_18], rsi
0x18001637a  push    rdi
0x18001637b  sub     rsp, 40h
0x18001637f  cmp     byte ptr [rcx+98h], 0
0x180016386  mov     rbx, rdx
0x180016389  mov     rsi, rcx
0x18001638c  jz      short loc_1800163A0
0x18001638e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180016395  xor     eax, eax
0x180016397  movdqu  xmmword ptr [rdx], xmm0
0x18001639b  jmp     loc_18001646E
0x1800163a0  mov     rax, [rcx+90h]
0x1800163a7  lea     r8, Value; "OverrideConfigMethods"
0x1800163ae  mov     byte ptr [rcx+98h], 1
0x1800163b5  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800163bc  mov     r9d, 10h; dwFlags
0x1800163c2  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800163c9  mov     edi, [rax+78h]
0x1800163cc  lea     rax, [rsp+48h+arg_10]
0x1800163d1  mov     [rsp+48h+pcbData], rax; pcbData
0x1800163d6  lea     rax, [rsp+48h+arg_0]
0x1800163db  mov     [rsp+48h+pvData], rax; pvData
0x1800163e0  mov     [rsp+48h+pdwType], 0; pdwType
0x1800163e9  mov     [rsp+48h+arg_0], 0
0x1800163f1  mov     [rsp+48h+arg_10], 4
0x1800163f9  call    cs:__imp_RegGetValueW
0x1800163ff  test    eax, eax
0x180016401  jnz     short loc_18001640C
0x180016403  mov     eax, [rsp+48h+arg_0]
0x180016407  test    eax, eax
0x180016409  cmovnz  edi, eax
0x18001640c  mov     rax, [rsi+90h]
0x180016413  and     dword ptr [rax+0Ch], 0FFFFFFF8h
0x180016417  mov     rcx, [rsi+90h]
0x18001641e  cmp     byte ptr [rcx+84h], 0
0x180016425  jz      short loc_180016436
0x180016427  test    byte ptr [rcx+88h], 1
0x18001642e  jz      short loc_180016436
0x180016430  or      dword ptr [rcx+0Ch], 2
0x180016434  jmp     short loc_18001645E
0x180016436  mov     eax, [rcx+0Ch]
0x180016439  test    dil, dil
0x18001643c  jns     short loc_18001644D
0x18001643e  movups  xmm0, xmmword ptr cs:CLSID_WcnPageConfiguredPbcMaster.Data1
0x180016445  or      eax, 1
0x180016448  mov     [rcx+0Ch], eax
0x18001644b  jmp     short loc_180016465
0x18001644d  test    dil, 8
0x180016451  jz      short loc_180016458
0x180016453  or      eax, 2
0x180016456  jmp     short loc_18001645B
0x180016458  or      eax, 4
0x18001645b  mov     [rcx+0Ch], eax
0x18001645e  movups  xmm0, xmmword ptr cs:CLSID_WcnPageConfiguredPinMaster.Data1
0x180016465  movdqu  xmmword ptr [rbx], xmm0
0x180016469  mov     eax, 1
0x18001646e  mov     rbx, [rsp+48h+arg_8]
0x180016473  mov     rsi, [rsp+48h+arg_18]
0x180016478  add     rsp, 40h
0x18001647c  pop     rdi
0x18001647d  retn
```
