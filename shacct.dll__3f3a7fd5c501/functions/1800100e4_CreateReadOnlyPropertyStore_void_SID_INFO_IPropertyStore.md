# CreateReadOnlyPropertyStore(void *,_SID_INFO,IPropertyStore * *)

- ea: `0x1800100e4`
- end: `0x180010229`
- name: `?CreateReadOnlyPropertyStore@@YAJPEAXU_SID_INFO@@PEAPEAUIPropertyStore@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(PSID pSid, struct _SID_INFO *__struct_ptr, struct IPropertyStore **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000ed10`
- `0x180011e80`

## callees

- `0x180008230`
- `0x1800100e4`
- `0x180016944`
- `0x180016984`
- `0x180017010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180010170`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180010170`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180010107`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180010107`

## pseudocode

```c
__int64 __fastcall CreateReadOnlyPropertyStore(PSID pSid, struct _SID_INFO *a2, struct IPropertyStore **a3)
{
  HRESULT v6; // ebx
  void *v7; // rbx
  unsigned int v8; // eax
  __int128 v10; // [rsp+20h] [rbp-48h] BYREF
  PSID v11; // [rsp+30h] [rbp-38h]

  *a3 = 0;
  v6 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (void **)a3);
  if ( v6 >= 0 )
  {
    v6 = IPropertyStore_SetString(*a3, &PKEY_SAM_Name, a2->pwzClass);
    if ( v6 < 0 )
      goto LABEL_12;
    v6 = IPropertyStore_SetString(*a3, &PKEY_SAM_Domain, a2->pwzCommonName);
    if ( v6 < 0 )
      goto LABEL_12;
    v7 = *a3;
    v10 = 0;
    LOWORD(v10) = 65;
    v11 = pSid;
    DWORD2(v10) = GetLengthSid(pSid);
    v6 = (*(__int64 (__fastcall **)(void *, __int128 *, __int128 *))(*(_QWORD *)v7 + 48LL))(
           v7,
           &PKEY_SAM_SecurityID,
           &v10);
    if ( v6 < 0 )
      goto LABEL_12;
    v8 = RIDFromSID(pSid);
    v6 = IPropertyStore_SetUInt32(*a3, &PKEY_SAM_ResidualID, v8);
    if ( v6 < 0 )
      goto LABEL_12;
    if ( LODWORD(a2->pSid) == 1 )
      v6 = IPropertyStore_SetUInt32(*a3, &PKEY_SAM_Type, 1);
    if ( ((LODWORD(a2->pSid) - 2) & 0xFFFFFFFC) == 0 && LODWORD(a2->pSid) != 3 )
      v6 = IPropertyStore_SetUInt32(*a3, &PKEY_SAM_Type, 2);
    if ( v6 < 0 )
    {
LABEL_12:
      ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
      *a3 = 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800100e4  push    rbx
0x1800100e6  push    rbp
0x1800100e7  push    rsi
0x1800100e8  push    rdi
0x1800100e9  sub     rsp, 48h
0x1800100ed  mov     rsi, rdx
0x1800100f0  mov     qword ptr [r8], 0
0x1800100f7  mov     rbp, rcx
0x1800100fa  mov     rdx, r8; ppv
0x1800100fd  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180010104  mov     rdi, r8
0x180010107  call    cs:__imp_PSCreateMemoryPropertyStore
0x18001010d  mov     ebx, eax
0x18001010f  test    eax, eax
0x180010111  js      loc_18001021E
0x180010117  mov     r8, [rsi+10h]
0x18001011b  lea     rdx, PKEY_SAM_Name
0x180010122  mov     rcx, [rdi]
0x180010125  call    IPropertyStore_SetString
0x18001012a  mov     ebx, eax
0x18001012c  test    eax, eax
0x18001012e  js      loc_180010208
0x180010134  mov     r8, [rsi+8]
0x180010138  lea     rdx, PKEY_SAM_Domain
0x18001013f  mov     rcx, [rdi]
0x180010142  call    IPropertyStore_SetString
0x180010147  mov     ebx, eax
0x180010149  test    eax, eax
0x18001014b  js      loc_180010208
0x180010151  mov     rbx, [rdi]
0x180010154  xor     eax, eax
0x180010156  mov     [rsp+68h+var_38], rax
0x18001015b  xorps   xmm0, xmm0
0x18001015e  mov     eax, 41h ; 'A'
0x180010163  mov     rcx, rbp; pSid
0x180010166  movups  [rsp+68h+var_48], xmm0
0x18001016b  mov     word ptr [rsp+68h+var_48], ax
0x180010170  call    cs:__imp_GetLengthSid
0x180010176  lea     r8, [rsp+68h+var_48]
0x18001017b  mov     [rsp+68h+var_38], rbp
0x180010180  mov     dword ptr [rsp+68h+var_48+8], eax
0x180010184  lea     rdx, PKEY_SAM_SecurityID
0x18001018b  mov     rax, [rbx]
0x18001018e  mov     rcx, rbx
0x180010191  mov     rax, [rax+30h]
0x180010195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001019a  mov     ebx, eax
0x18001019c  test    eax, eax
0x18001019e  js      short loc_180010208
0x1800101a0  mov     rcx, rbp; pSid
0x1800101a3  call    ?RIDFromSID@@YAKQEAX@Z; RIDFromSID(void * const)
0x1800101a8  mov     rcx, [rdi]
0x1800101ab  lea     rdx, PKEY_SAM_ResidualID
0x1800101b2  mov     r8d, eax
0x1800101b5  call    IPropertyStore_SetUInt32
0x1800101ba  mov     ebx, eax
0x1800101bc  test    eax, eax
0x1800101be  js      short loc_180010208
0x1800101c0  mov     r8d, 1
0x1800101c6  cmp     [rsi], r8d
0x1800101c9  jnz     short loc_1800101DC
0x1800101cb  mov     rcx, [rdi]
0x1800101ce  lea     rdx, PKEY_SAM_Type
0x1800101d5  call    IPropertyStore_SetUInt32
0x1800101da  mov     ebx, eax
0x1800101dc  mov     ecx, [rsi]
0x1800101de  lea     eax, [rcx-2]
0x1800101e1  test    eax, 0FFFFFFFCh
0x1800101e6  jnz     short loc_180010204
0x1800101e8  cmp     ecx, 3
0x1800101eb  jz      short loc_180010204
0x1800101ed  mov     rcx, [rdi]
0x1800101f0  lea     rdx, PKEY_SAM_Type
0x1800101f7  mov     r8d, 2
0x1800101fd  call    IPropertyStore_SetUInt32
0x180010202  mov     ebx, eax
0x180010204  test    ebx, ebx
0x180010206  jns     short loc_18001021E
0x180010208  mov     rcx, [rdi]
0x18001020b  mov     rax, [rcx]
0x18001020e  mov     rax, [rax+10h]
0x180010212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010217  mov     qword ptr [rdi], 0
0x18001021e  mov     eax, ebx
0x180010220  add     rsp, 48h
0x180010224  pop     rdi
0x180010225  pop     rsi
0x180010226  pop     rbp
0x180010227  pop     rbx
0x180010228  retn
```
