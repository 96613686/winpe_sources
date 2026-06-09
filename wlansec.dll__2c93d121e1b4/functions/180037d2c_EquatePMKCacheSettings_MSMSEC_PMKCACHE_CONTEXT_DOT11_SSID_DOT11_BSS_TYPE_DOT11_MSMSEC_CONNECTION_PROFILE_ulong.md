# EquatePMKCacheSettings(MSMSEC_PMKCACHE_CONTEXT *,_DOT11_SSID *,_DOT11_BSS_TYPE,DOT11_MSMSEC_CONNECTION_PROFILE *,ulong,void *,int *)

- ea: `0x180037d2c`
- end: `0x180037fb5`
- name: `?EquatePMKCacheSettings@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@PEAU_DOT11_SSID@@W4_DOT11_BSS_TYPE@@PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@KPEAXPEAH@Z`
- size: `649`
- prototype: `unsigned int __fastcall(struct MSMSEC_PMKCACHE_CONTEXT *, struct _DOT11_SSID *, enum _DOT11_BSS_TYPE, struct DOT11_MSMSEC_CONNECTION_PROFILE *, unsigned int, void *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180037b68`

## callees

- `0x18000431c`
- `0x18000892c`
- `0x180008998`
- `0x18002ddd4`
- `0x180037d2c`
- `0x180044548`

## import_xrefs

- `OneX!OneXCompareAuthParams` at `0x180037ec6`
- `OneX!OneXCompareAuthParams` at `0x180037ec6`

## pseudocode

```c
__int64 __fastcall EquatePMKCacheSettings(
        struct MSMSEC_PMKCACHE_CONTEXT *a1,
        struct _DOT11_SSID *a2,
        enum _DOT11_BSS_TYPE a3,
        struct DOT11_MSMSEC_CONNECTION_PROFILE *a4,
        unsigned int a5,
        void *a6,
        int *a7)
{
  int v7; // esi
  PVOID *v12; // rbx
  __int64 v13; // r9
  unsigned int v14; // edi
  __int64 v15; // rdx
  __int64 v16; // r9
  int *v17; // rax
  __int64 v18; // r9
  int v19; // ecx
  __int64 v20; // rdx
  unsigned int v21; // eax
  const char *v22; // r9
  int v24; // [rsp+90h] [rbp+8h] BYREF

  v7 = 1;
  v24 = 1;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 106, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  v13 = *((unsigned int *)a1 + 36);
  if ( (_DWORD)v13 != a2->uSSIDLength )
  {
    v14 = 0;
    v7 = 0;
    if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 68) & 2) == 0 )
      goto LABEL_36;
    WPP_SF_dd(v12[7], 107, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, v13, a2->uSSIDLength);
LABEL_35:
    v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_36:
    *a7 = v7;
    if ( v12 == &WPP_GLOBAL_Control )
      return v14;
    if ( (*((_BYTE *)v12 + 68) & 2) == 0 )
      goto LABEL_42;
    v22 = "SAME";
    if ( !v7 )
      v22 = "NOT SAME";
    WPP_SF_s(v12[7], 114, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, v22);
    goto LABEL_41;
  }
  if ( memcmp_0((char *)a1 + 148, a2->ucSSID, a2->uSSIDLength) )
  {
    v14 = 0;
    v7 = 0;
    if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 68) & 2) == 0 )
      goto LABEL_36;
    v15 = 108;
    goto LABEL_34;
  }
  v16 = *((unsigned int *)a1 + 45);
  if ( a3 != (_DWORD)v16 )
  {
    v14 = 0;
    v7 = 0;
    if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 68) & 2) == 0 )
      goto LABEL_36;
    WPP_SF_dd(v12[7], 109, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, v16, a3);
    goto LABEL_35;
  }
  v17 = (int *)*((_QWORD *)a4 + 3);
  v18 = *((unsigned int *)a1 + 46);
  v19 = *v17;
  if ( *v17 != (_DWORD)v18 )
  {
    v14 = 0;
    v7 = 0;
    if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 68) & 2) == 0 )
      goto LABEL_36;
    v20 = 110;
    goto LABEL_21;
  }
  v19 = v17[1];
  v18 = *((unsigned int *)a1 + 47);
  if ( v19 != (_DWORD)v18 )
  {
    v14 = 0;
    v7 = 0;
    if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 68) & 2) == 0 )
      goto LABEL_36;
    v20 = 111;
LABEL_21:
    WPP_SF_dd(v12[7], v20, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, v18, v19);
    goto LABEL_35;
  }
  v21 = OneXCompareAuthParams(1, *((unsigned int *)a1 + 48), *((_QWORD *)a1 + 25), a5, a6, &v24, 0);
  v14 = v21;
  if ( !v21 )
  {
    if ( !v24 )
      goto LABEL_35;
    v14 = 0;
    v7 = 0;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      goto LABEL_36;
    v15 = 113;
LABEL_34:
    WPP_SF_(v12[7], v15, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids);
    goto LABEL_35;
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v14;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 112, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, v21);
LABEL_41:
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_42:
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x100) != 0 )
    WPP_SF_d(v12[7], 115, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x180037d2c  mov     rax, rsp
0x180037d2f  push    rbx
0x180037d30  push    rbp
0x180037d31  push    rsi
0x180037d32  push    rdi
0x180037d33  push    r12
0x180037d35  push    r13
0x180037d37  push    r14
0x180037d39  push    r15
0x180037d3b  sub     rsp, 48h
0x180037d3f  mov     esi, 1
0x180037d44  mov     r15, r9
0x180037d47  mov     [rax+8], esi
0x180037d4a  mov     ebp, r8d
0x180037d4d  mov     r14, rdx
0x180037d50  mov     rdi, rcx
0x180037d53  mov     rbx, cs:WPP_GLOBAL_Control
0x180037d5a  lea     r12, WPP_GLOBAL_Control
0x180037d61  lea     r13, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x180037d68  cmp     rbx, r12
0x180037d6b  jz      short loc_180037D8C
0x180037d6d  test    dword ptr [rbx+44h], 100h
0x180037d74  jz      short loc_180037D8C
0x180037d76  mov     rcx, [rbx+38h]
0x180037d7a  lea     edx, [rsi+69h]
0x180037d7d  mov     r8, r13
0x180037d80  call    WPP_SF_
0x180037d85  mov     rbx, cs:WPP_GLOBAL_Control
0x180037d8c  mov     eax, [r14]
0x180037d8f  mov     r9d, [rdi+90h]
0x180037d96  cmp     r9d, eax
0x180037d99  jz      short loc_180037DCA
0x180037d9b  xor     edi, edi
0x180037d9d  xor     esi, esi
0x180037d9f  cmp     rbx, r12
0x180037da2  jz      loc_180037F3E
0x180037da8  test    byte ptr [rbx+44h], 2
0x180037dac  jz      loc_180037F3E
0x180037db2  lea     edx, [rdi+6Bh]
0x180037db5  mov     dword ptr [rsp+88h+var_68], eax
0x180037db9  mov     rcx, [rbx+38h]
0x180037dbd  mov     r8, r13
0x180037dc0  call    WPP_SF_dd
0x180037dc5  jmp     loc_180037F37
0x180037dca  mov     r8, rax; Size
0x180037dcd  lea     rdx, [r14+4]; Buf2
0x180037dd1  lea     rcx, [rdi+94h]; Buf1
0x180037dd8  call    memcmp_0
0x180037ddd  test    eax, eax
0x180037ddf  jz      short loc_180037E00
0x180037de1  xor     edi, edi
0x180037de3  xor     esi, esi
0x180037de5  cmp     rbx, r12
0x180037de8  jz      loc_180037F3E
0x180037dee  test    byte ptr [rbx+44h], 2
0x180037df2  jz      loc_180037F3E
0x180037df8  lea     edx, [rdi+6Ch]
0x180037dfb  jmp     loc_180037F2B
0x180037e00  mov     r9d, [rdi+0B4h]
0x180037e07  cmp     ebp, r9d
0x180037e0a  jz      short loc_180037E2C
0x180037e0c  xor     edi, edi
0x180037e0e  xor     esi, esi
0x180037e10  cmp     rbx, r12
0x180037e13  jz      loc_180037F3E
0x180037e19  test    byte ptr [rbx+44h], 2
0x180037e1d  jz      loc_180037F3E
0x180037e23  lea     edx, [rdi+6Dh]
0x180037e26  mov     dword ptr [rsp+88h+var_68], ebp
0x180037e2a  jmp     short loc_180037DB9
0x180037e2c  mov     rax, [r15+18h]
0x180037e30  mov     r9d, [rdi+0B8h]
0x180037e37  mov     ecx, [rax]
0x180037e39  cmp     ecx, r9d
0x180037e3c  jz      short loc_180037E61
0x180037e3e  xor     edi, edi
0x180037e40  xor     esi, esi
0x180037e42  cmp     rbx, r12
0x180037e45  jz      loc_180037F3E
0x180037e4b  test    byte ptr [rbx+44h], 2
0x180037e4f  jz      loc_180037F3E
0x180037e55  lea     edx, [rdi+6Eh]
0x180037e58  mov     dword ptr [rsp+88h+var_68], ecx
0x180037e5c  jmp     loc_180037DB9
0x180037e61  mov     ecx, [rax+4]
0x180037e64  mov     r9d, [rdi+0BCh]
0x180037e6b  cmp     ecx, r9d
0x180037e6e  jz      short loc_180037E8C
0x180037e70  xor     edi, edi
0x180037e72  xor     esi, esi
0x180037e74  cmp     rbx, r12
0x180037e77  jz      loc_180037F3E
0x180037e7d  test    byte ptr [rbx+44h], 2
0x180037e81  jz      loc_180037F3E
0x180037e87  lea     edx, [rdi+6Fh]
0x180037e8a  jmp     short loc_180037E58
0x180037e8c  mov     r9d, [rsp+88h+arg_20]
0x180037e94  lea     rax, [rsp+88h+arg_0]
0x180037e9c  mov     r8, [rdi+0C8h]
0x180037ea3  mov     ecx, esi
0x180037ea5  mov     edx, [rdi+0C0h]
0x180037eab  mov     [rsp+88h+var_58], 0
0x180037eb4  mov     [rsp+88h+var_60], rax
0x180037eb9  mov     rax, [rsp+88h+arg_28]
0x180037ec1  mov     [rsp+88h+var_68], rax
0x180037ec6  call    cs:__imp_OneXCompareAuthParams
0x180037ecd  nop     dword ptr [rax+rax+00h]
0x180037ed2  mov     edi, eax
0x180037ed4  test    eax, eax
0x180037ed6  jz      short loc_180037F08
0x180037ed8  mov     rbx, cs:WPP_GLOBAL_Control
0x180037edf  cmp     rbx, r12
0x180037ee2  jz      loc_180037FA1
0x180037ee8  test    [rbx+44h], sil
0x180037eec  jz      loc_180037F7F
0x180037ef2  mov     rcx, [rbx+38h]
0x180037ef6  mov     edx, 70h ; 'p'
0x180037efb  mov     r9d, eax
0x180037efe  mov     r8, r13
0x180037f01  call    WPP_SF_d
0x180037f06  jmp     short loc_180037F78
0x180037f08  cmp     [rsp+88h+arg_0], 0
0x180037f10  jz      short loc_180037F37
0x180037f12  xor     edi, edi
0x180037f14  xor     esi, esi
0x180037f16  mov     rbx, cs:WPP_GLOBAL_Control
0x180037f1d  cmp     rbx, r12
0x180037f20  jz      short loc_180037F3E
0x180037f22  test    byte ptr [rbx+44h], 2
0x180037f26  jz      short loc_180037F3E
0x180037f28  lea     edx, [rdi+71h]
0x180037f2b  mov     rcx, [rbx+38h]
0x180037f2f  mov     r8, r13
0x180037f32  call    WPP_SF_
0x180037f37  mov     rbx, cs:WPP_GLOBAL_Control
0x180037f3e  mov     rax, [rsp+88h+arg_30]
0x180037f46  mov     [rax], esi
0x180037f48  cmp     rbx, r12
0x180037f4b  jz      short loc_180037FA1
0x180037f4d  test    byte ptr [rbx+44h], 2
0x180037f51  jz      short loc_180037F7F
0x180037f53  mov     rcx, [rbx+38h]
0x180037f57  lea     rax, aNotSame; "NOT SAME"
0x180037f5e  test    esi, esi
0x180037f60  lea     r9, aSame; "SAME"
0x180037f67  mov     edx, 72h ; 'r'
0x180037f6c  mov     r8, r13
0x180037f6f  cmovz   r9, rax
0x180037f73  call    WPP_SF_s
0x180037f78  mov     rbx, cs:WPP_GLOBAL_Control
0x180037f7f  cmp     rbx, r12
0x180037f82  jz      short loc_180037FA1
0x180037f84  test    dword ptr [rbx+44h], 100h
0x180037f8b  jz      short loc_180037FA1
0x180037f8d  mov     rcx, [rbx+38h]
0x180037f91  mov     edx, 73h ; 's'
0x180037f96  mov     r9d, edi
0x180037f99  mov     r8, r13
0x180037f9c  call    WPP_SF_d
0x180037fa1  mov     eax, edi
0x180037fa3  add     rsp, 48h
0x180037fa7  pop     r15
0x180037fa9  pop     r14
0x180037fab  pop     r13
0x180037fad  pop     r12
0x180037faf  pop     rdi
0x180037fb0  pop     rsi
0x180037fb1  pop     rbp
0x180037fb2  pop     rbx
0x180037fb3  retn
```
