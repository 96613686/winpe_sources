# WlanSetProfileEapXmlUserData

- ea: `0x180020d40`
- end: `0x1800213cf`
- name: `WlanSetProfileEapXmlUserData`
- size: `1679`
- prototype: `DWORD __stdcall(HANDLE hClientHandle, const GUID *pInterfaceGuid, LPCWSTR strProfileName, DWORD dwFlags, LPCWSTR strEapXmlUserData, PVOID pReserved)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task`

## callees

- `0x1800038d0`
- `0x1800053c0`
- `0x180005610`
- `0x1800063a0`
- `0x180006934`
- `0x18000f450`
- `0x180010160`
- `0x180020d40`
- `0x180026db8`
- `0x18004bd7c`
- `0x18004dd84`
- `0x18006013c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210cd`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18002134e`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18002134e`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180020e61`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180020e61`

## pseudocode

```c
DWORD __stdcall WlanSetProfileEapXmlUserData(
        HANDLE hClientHandle,
        const GUID *pInterfaceGuid,
        LPCWSTR strProfileName,
        DWORD dwFlags,
        LPCWSTR strEapXmlUserData,
        PVOID pReserved)
{
  HANDLE v8; // rax
  DWORD v9; // r15d
  void *v10; // r12
  union DOT11_OUI_HEADER *v11; // r10
  DWORD LastError; // eax
  DWORD v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // r9
  DWORD Profile; // eax
  __int64 v17; // r14
  struct _EAP_METHOD_TYPE v18; // xmm6
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // r9
  __int64 v24; // r9
  __int64 v25; // r10
  __int64 v26; // r9
  __int64 v27; // r10
  int v28; // eax
  __int64 v29; // r9
  __int64 v30; // r9
  __int64 v31; // r10
  __int64 v32; // r9
  __int64 v33; // r10
  unsigned int v35; // [rsp+40h] [rbp-C8h]
  unsigned int v36[3]; // [rsp+44h] [rbp-C4h] BYREF
  struct _EAP_METHOD_TYPE v37; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD *v38; // [rsp+60h] [rbp-A8h] BYREF
  struct _EAP_METHOD_TYPE v39; // [rsp+70h] [rbp-98h] BYREF
  int v40; // [rsp+80h] [rbp-88h] BYREF
  _DWORD v41[3]; // [rsp+84h] [rbp-84h] BYREF
  void *v42; // [rsp+90h] [rbp-78h]
  void *v43; // [rsp+98h] [rbp-70h] BYREF
  OLECHAR *psz; // [rsp+A0h] [rbp-68h] BYREF
  struct _EAP_METHOD_TYPE v45; // [rsp+B0h] [rbp-58h] BYREF
  int v47; // [rsp+118h] [rbp+10h]

  v47 = (int)pInterfaceGuid;
  v8 = hClientHandle;
  v38 = 0;
  v36[0] = 0;
  v43 = 0;
  psz = 0;
  v40 = 0;
  *(_QWORD *)&v37.eapType.type = 0;
  v9 = 0;
  v41[1] = 0;
  v10 = 0;
  v42 = 0;
  v41[0] = 0;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 133, WPP_797f1b088bb039a5f91226960c081484_Traceguids);
    v11 = WPP_GLOBAL_Control;
    v8 = hClientHandle;
  }
  if ( v8 && pInterfaceGuid && !pReserved && strProfileName && strEapXmlUserData )
  {
    LastError = HtReferenceHandleWithTag(g_hHandleTable, v8, 1129074260, 0, 1, &v38);
    v13 = LastError;
    if ( LastError )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
      {
        goto LABEL_72;
      }
      v14 = 135;
      goto LABEL_15;
    }
    Profile = RpcGetProfile(
                *v38,
                (_DWORD)pInterfaceGuid,
                (_DWORD)strProfileName,
                (unsigned int)&psz,
                (__int64)v41,
                (__int64)&v40);
    v13 = Profile;
    if ( Profile )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 136, WPP_797f1b088bb039a5f91226960c081484_Traceguids, Profile);
        v11 = WPP_GLOBAL_Control;
      }
      v8 = hClientHandle;
      goto LABEL_73;
    }
    LastError = WpParseProfileXml(psz, &v37, 0, 0);
    v13 = LastError;
    if ( LastError )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
      {
        goto LABEL_72;
      }
      v14 = 138;
      goto LABEL_15;
    }
    v17 = 0;
    v18 = 0;
    v45 = 0;
    v19 = *(_QWORD *)(*(_QWORD *)&v37.eapType.type + 552LL);
    if ( v19 )
    {
      v20 = *(_QWORD *)(v19 + 32);
      if ( v20 )
      {
        v21 = *(_QWORD *)(v20 + 424);
        if ( v21 )
        {
          v22 = *(_QWORD *)(v21 + 48);
          if ( v22 )
          {
            v18 = *(struct _EAP_METHOD_TYPE *)(*(unsigned int *)(v22 + 64) + v22 + 4);
            v45 = v18;
            v17 = v22;
          }
        }
      }
    }
    if ( !v17 )
    {
      v13 = 87;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
      {
        goto LABEL_72;
      }
      v14 = 140;
LABEL_55:
      v15 = v13;
      goto LABEL_16;
    }
    v23 = v17 + *(unsigned int *)(v17 + 64);
    if ( (*(_BYTE *)(v23 + 20) & 1) == 0
      || (v37 = v18, v39 = *(struct _EAP_METHOD_TYPE *)(v23 + 4), (unsigned int)AreDifferentEapTypes(&v39, &v37)) )
    {
      v13 = 1168;
    }
    else
    {
      v25 = *(unsigned int *)(v24 + 28);
      v39 = v18;
      v37 = *(struct _EAP_METHOD_TYPE *)(v25 + v24);
      v13 = 1168;
      if ( !(unsigned int)AreDifferentEapTypes(&v37, &v39) )
      {
        v9 = *(_DWORD *)(v27 + v26 + 16);
        v28 = 234;
        goto LABEL_40;
      }
    }
    v28 = 1168;
LABEL_40:
    if ( v28 == 234 )
    {
      v10 = (void *)AllocWLMem(v9);
      v42 = v10;
      if ( !v10 )
      {
        LastError = GetLastError();
        v13 = LastError;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
        {
          goto LABEL_72;
        }
        v14 = 141;
LABEL_15:
        v15 = LastError;
LABEL_16:
        WPP_SF_d(*((_QWORD *)v11 + 12), v14, WPP_797f1b088bb039a5f91226960c081484_Traceguids, v15);
LABEL_71:
        v11 = WPP_GLOBAL_Control;
        goto LABEL_72;
      }
      v29 = v17 + *(unsigned int *)(v17 + 64);
      if ( (*(_BYTE *)(v29 + 20) & 1) == 0 )
        goto LABEL_51;
      v39 = v18;
      v37 = *(struct _EAP_METHOD_TYPE *)(v29 + 4);
      if ( (unsigned int)AreDifferentEapTypes(&v37, &v39) )
        goto LABEL_51;
      v31 = *(unsigned int *)(v30 + 28);
      v39 = v18;
      v37 = *(struct _EAP_METHOD_TYPE *)(v31 + v30);
      if ( (unsigned int)AreDifferentEapTypes(&v37, &v39) )
        goto LABEL_51;
      if ( v9 < *(_DWORD *)(v33 + v32 + 16) )
      {
        v13 = 122;
LABEL_51:
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
        {
          goto LABEL_72;
        }
        v14 = 142;
        goto LABEL_55;
      }
      memcpy_0(v10, (const void *)(v33 + v32 + 20), *(unsigned int *)(v33 + v32 + 16));
    }
    LastError = EapHlpGetEapBlobFromXmlUserData(strEapXmlUserData, v9, (unsigned __int8 *)v10, &v45, v36, &v43);
    v13 = LastError;
    if ( !LastError )
    {
      v39 = v45;
      v35 = RpcSetProfileEapUserData(
              *v38,
              v47,
              (_DWORD)strProfileName,
              (unsigned int)&v39,
              dwFlags,
              v36[0],
              (__int64)v43);
      v13 = ServiceStatus(v35);
LABEL_72:
      v8 = hClientHandle;
      goto LABEL_73;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 105)
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) == 0 )
    {
      goto LABEL_72;
    }
    v14 = 143;
    goto LABEL_15;
  }
  v13 = 87;
  if ( v11 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control && *((_BYTE *)v11 + 105) && (*((_BYTE *)v11 + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)v11 + 12), 134, WPP_797f1b088bb039a5f91226960c081484_Traceguids);
    goto LABEL_71;
  }
LABEL_73:
  if ( v38 )
  {
    HtDereferenceHandleWithTag(g_hHandleTable, v8, 0, 1);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v10 )
  {
    FreeWLMem(v10);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v43 )
  {
    FreeWLMem(v43);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v11 + 105) >= 4u
    && (*((_BYTE *)v11 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v11 + 12), 145, WPP_797f1b088bb039a5f91226960c081484_Traceguids, v13);
  }
  return v13;
}

```

## disassembly

```asm
0x180020d40  mov     r11, rsp
0x180020d43  mov     [r11+20h], r9d
0x180020d47  mov     [r11+18h], r8
0x180020d4b  mov     [r11+10h], rdx
0x180020d4f  mov     [r11+8], rcx
0x180020d53  push    rbx
0x180020d54  push    rsi
0x180020d55  push    r12
0x180020d57  push    r13
0x180020d59  push    r14
0x180020d5b  push    r15
0x180020d5d  sub     rsp, 0D8h
0x180020d64  movaps  xmmword ptr [r11-48h], xmm6
0x180020d69  mov     r13, r8
0x180020d6c  mov     r14, rdx
0x180020d6f  mov     rax, rcx
0x180020d72  mov     [rsp+108h+var_A8], 0
0x180020d7b  mov     [rsp+108h+var_C4], 0
0x180020d83  mov     qword ptr [r11-70h], 0
0x180020d8b  mov     qword ptr [r11-68h], 0
0x180020d93  mov     [rsp+108h+var_88], 0
0x180020d9e  mov     qword ptr [rsp+108h+var_B8], 0
0x180020da7  xor     r15d, r15d
0x180020daa  mov     [r11-80h], r15d
0x180020dae  xor     r12d, r12d
0x180020db1  mov     [rsp+108h+var_78], r12
0x180020db9  mov     [r11-84h], r12d
0x180020dc0  lea     rsi, WPP_GLOBAL_Control
0x180020dc7  mov     r10, cs:WPP_GLOBAL_Control
0x180020dce  cmp     r10, rsi
0x180020dd1  jz      short loc_180020E05
0x180020dd3  cmp     byte ptr [r10+69h], 4
0x180020dd8  jb      short loc_180020E05
0x180020dda  test    byte ptr [r10+6Ch], 2
0x180020ddf  jz      short loc_180020E05
0x180020de1  mov     edx, 85h
0x180020de6  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x180020ded  mov     rcx, [r10+60h]
0x180020df1  call    WPP_SF_
0x180020df6  mov     r10, cs:WPP_GLOBAL_Control
0x180020dfd  mov     rax, [rsp+108h+arg_0]
0x180020e05  test    rax, rax
0x180020e08  jz      loc_1800212F9
0x180020e0e  test    r14, r14
0x180020e11  jz      loc_1800212F9
0x180020e17  cmp     [rsp+108h+pReserved], r12
0x180020e1f  jnz     loc_1800212F9
0x180020e25  test    r13, r13
0x180020e28  jz      loc_1800212F9
0x180020e2e  cmp     [rsp+108h+strEapXmlUserData], r12
0x180020e36  jz      loc_1800212F9
0x180020e3c  lea     rcx, [rsp+108h+var_A8]
0x180020e41  mov     [rsp+108h+var_E0], rcx
0x180020e46  mov     dword ptr [rsp+108h+var_E8], 1
0x180020e4e  xor     r9d, r9d
0x180020e51  mov     r8d, 434C4E54h
0x180020e57  mov     rdx, rax
0x180020e5a  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180020e61  call    cs:__imp_HtReferenceHandleWithTag
0x180020e67  mov     ebx, eax
0x180020e69  test    eax, eax
0x180020e6b  jz      short loc_180020EB0
0x180020e6d  mov     r10, cs:WPP_GLOBAL_Control
0x180020e74  cmp     r10, rsi
0x180020e77  jz      loc_18002132B
0x180020e7d  cmp     byte ptr [r10+69h], 1
0x180020e82  jb      loc_18002132B
0x180020e88  test    byte ptr [r10+6Ch], 2
0x180020e8d  jz      loc_18002132B
0x180020e93  mov     edx, 87h
0x180020e98  mov     r9d, eax
0x180020e9b  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x180020ea2  mov     rcx, [r10+60h]
0x180020ea6  call    WPP_SF_d
0x180020eab  jmp     loc_180021324
0x180020eb0  lea     rax, [rsp+108h+var_88]
0x180020eb8  mov     [rsp+108h+var_E0], rax
0x180020ebd  lea     rax, [rsp+108h+var_84]
0x180020ec5  mov     [rsp+108h+var_E8], rax
0x180020eca  lea     r9, [rsp+108h+psz]
0x180020ed2  mov     r8, r13
0x180020ed5  mov     rdx, r14
0x180020ed8  mov     rcx, [rsp+108h+var_A8]
0x180020edd  mov     rcx, [rcx]
0x180020ee0  call    RpcGetProfile
0x180020ee5  mov     ebx, eax
0x180020ee7  mov     [rsp+108h+var_C8], eax
0x180020eeb  test    eax, eax
0x180020eed  jz      short loc_180020F35
0x180020eef  mov     r10, cs:WPP_GLOBAL_Control
0x180020ef6  cmp     r10, rsi
0x180020ef9  jz      short loc_180020F28
0x180020efb  cmp     byte ptr [r10+69h], 1
0x180020f00  jb      short loc_180020F28
0x180020f02  test    byte ptr [r10+6Ch], 2
0x180020f07  jz      short loc_180020F28
0x180020f09  mov     edx, 88h
0x180020f0e  mov     r9d, eax
0x180020f11  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x180020f18  mov     rcx, [r10+60h]
0x180020f1c  call    WPP_SF_d
0x180020f21  mov     r10, cs:WPP_GLOBAL_Control
0x180020f28  mov     rax, [rsp+108h+arg_0]
0x180020f30  jmp     loc_180021333
0x180020f35  jmp     short loc_180020F91
0x180020f37  mov     [rsp+108h+var_C8], eax
0x180020f3b  lea     rdx, WPP_GLOBAL_Control
0x180020f42  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f49  cmp     rcx, rdx
0x180020f4c  jz      short loc_180020F72
0x180020f4e  cmp     byte ptr [rcx+69h], 1
0x180020f52  jb      short loc_180020F72
0x180020f54  test    byte ptr [rcx+6Ch], 2
0x180020f58  jz      short loc_180020F72
0x180020f5a  mov     edx, 89h
0x180020f5f  mov     r9d, eax
0x180020f62  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x180020f69  mov     rcx, [rcx+60h]
0x180020f6d  call    WPP_SF_d
0x180020f72  lea     rsi, WPP_GLOBAL_Control
0x180020f79  mov     r13, [rsp+108h+arg_10]
0x180020f81  mov     r15d, [rsp+108h+var_80]
0x180020f89  mov     r12, [rsp+108h+var_78]
0x180020f91  xor     r9d, r9d
0x180020f94  xor     r8d, r8d
0x180020f97  lea     rdx, [rsp+108h+var_B8]
0x180020f9c  mov     rcx, [rsp+108h+psz]; psz
0x180020fa4  call    WpParseProfileXml
0x180020fa9  mov     ebx, eax
0x180020fab  test    eax, eax
0x180020fad  jz      short loc_180020FDF
0x180020faf  mov     r10, cs:WPP_GLOBAL_Control
0x180020fb6  cmp     r10, rsi
0x180020fb9  jz      loc_18002132B
0x180020fbf  cmp     byte ptr [r10+69h], 1
0x180020fc4  jb      loc_18002132B
0x180020fca  test    byte ptr [r10+6Ch], 2
0x180020fcf  jz      loc_18002132B
0x180020fd5  mov     edx, 8Ah
0x180020fda  jmp     loc_180020E98
0x180020fdf  xor     r14d, r14d
0x180020fe2  xorps   xmm6, xmm6
0x180020fe5  movaps  xmmword ptr [rsp+108h+var_58.eapType.type], xmm6
0x180020fed  mov     rax, qword ptr [rsp+108h+var_B8]
0x180020ff2  mov     rax, [rax+228h]
0x180020ff9  test    rax, rax
0x180020ffc  jz      short loc_18002102F
0x180020ffe  mov     rax, [rax+20h]
0x180021002  test    rax, rax
0x180021005  jz      short loc_18002102F
0x180021007  mov     rcx, [rax+1A8h]
0x18002100e  test    rcx, rcx
0x180021011  jz      short loc_18002102F
0x180021013  mov     rcx, [rcx+30h]
0x180021017  test    rcx, rcx
0x18002101a  jz      short loc_18002102F
0x18002101c  mov     eax, [rcx+40h]
0x18002101f  movups  xmm6, xmmword ptr [rax+rcx+4]
0x180021024  movaps  xmmword ptr [rsp+108h+var_58.eapType.type], xmm6
0x18002102c  mov     r14, rcx
0x18002102f  test    r14, r14
0x180021032  jz      loc_1800212D2
0x180021038  mov     r9d, [r14+40h]
0x18002103c  add     r9, r14
0x18002103f  test    byte ptr [r9+14h], 1
0x180021044  jz      short loc_1800210A3
0x180021046  movdqa  [rsp+108h+var_B8], xmm6
0x18002104c  movups  xmm0, xmmword ptr [r9+4]
0x180021051  movdqu  [rsp+108h+var_98], xmm0
0x180021057  lea     rdx, [rsp+108h+var_B8]
0x18002105c  lea     rcx, [rsp+108h+var_98]
0x180021061  call    AreDifferentEapTypes
0x180021066  test    eax, eax
0x180021068  jnz     short loc_1800210A3
0x18002106a  mov     r10d, [r9+1Ch]
0x18002106e  movdqa  [rsp+108h+var_98], xmm6
0x180021074  movups  xmm0, xmmword ptr [r10+r9]
0x180021079  movdqu  [rsp+108h+var_B8], xmm0
0x18002107f  lea     rdx, [rsp+108h+var_98]
0x180021084  lea     rcx, [rsp+108h+var_B8]
0x180021089  call    AreDifferentEapTypes
0x18002108e  mov     ebx, 490h
0x180021093  test    eax, eax
0x180021095  jnz     short loc_1800210A8
0x180021097  mov     r15d, [r10+r9+10h]
0x18002109c  mov     eax, 0EAh
0x1800210a1  jmp     short loc_1800210AA
0x1800210a3  mov     ebx, 490h
0x1800210a8  mov     eax, ebx
0x1800210aa  cmp     eax, 0EAh
0x1800210af  jnz     loc_1800211B0
0x1800210b5  mov     ecx, r15d; dwBytes
0x1800210b8  call    AllocWLMem
0x1800210bd  mov     r12, rax
0x1800210c0  mov     [rsp+108h+var_78], rax
0x1800210c8  test    rax, rax
0x1800210cb  jnz     short loc_180021105
0x1800210cd  call    cs:__imp_GetLastError
0x1800210d3  mov     ebx, eax
0x1800210d5  mov     r10, cs:WPP_GLOBAL_Control
0x1800210dc  cmp     r10, rsi
0x1800210df  jz      loc_18002132B
0x1800210e5  cmp     byte ptr [r10+69h], 1
0x1800210ea  jb      loc_18002132B
0x1800210f0  test    byte ptr [r10+6Ch], 2
0x1800210f5  jz      loc_18002132B
0x1800210fb  mov     edx, 8Dh
0x180021100  jmp     loc_180020E98
0x180021105  mov     r9d, [r14+40h]
0x180021109  add     r9, r14
0x18002110c  test    byte ptr [r9+14h], 1
0x180021111  jz      short loc_180021169
0x180021113  movdqa  [rsp+108h+var_98], xmm6
0x180021119  movups  xmm0, xmmword ptr [r9+4]
0x18002111e  movdqu  [rsp+108h+var_B8], xmm0
0x180021124  lea     rdx, [rsp+108h+var_98]
0x180021129  lea     rcx, [rsp+108h+var_B8]
0x18002112e  call    AreDifferentEapTypes
0x180021133  test    eax, eax
0x180021135  jnz     short loc_180021169
0x180021137  mov     r10d, [r9+1Ch]
0x18002113b  movdqa  [rsp+108h+var_98], xmm6
0x180021141  movups  xmm0, xmmword ptr [r10+r9]
0x180021146  movdqu  [rsp+108h+var_B8], xmm0
0x18002114c  lea     rdx, [rsp+108h+var_98]
0x180021151  lea     rcx, [rsp+108h+var_B8]
0x180021156  call    AreDifferentEapTypes
0x18002115b  test    eax, eax
0x18002115d  jnz     short loc_180021169
0x18002115f  cmp     r15d, [r10+r9+10h]
0x180021164  jnb     short loc_18002119C
0x180021166  lea     ebx, [rax+7Ah]
0x180021169  mov     r10, cs:WPP_GLOBAL_Control
0x180021170  cmp     r10, rsi
0x180021173  jz      loc_18002132B
0x180021179  cmp     byte ptr [r10+69h], 1
0x18002117e  jb      loc_18002132B
0x180021184  test    byte ptr [r10+6Ch], 2
0x180021189  jz      loc_18002132B
0x18002118f  mov     edx, 8Eh
0x180021194  mov     r9d, ebx
0x180021197  jmp     loc_180020E9B
0x18002119c  mov     r8d, [r10+r9+10h]; Size
0x1800211a1  lea     rdx, [r9+14h]
0x1800211a5  add     rdx, r10; Src
0x1800211a8  mov     rcx, r12; void *
0x1800211ab  call    memcpy_0
0x1800211b0  lea     rax, [rsp+108h+var_70]
0x1800211b8  mov     [rsp+108h+var_E0], rax; void **
0x1800211bd  lea     rax, [rsp+108h+var_C4]
0x1800211c2  mov     [rsp+108h+var_E8], rax; unsigned int *
0x1800211c7  lea     r9, [rsp+108h+var_58]; struct _EAP_METHOD_TYPE *
0x1800211cf  mov     r8, r12; unsigned __int8 *
0x1800211d2  mov     edx, r15d; unsigned int
0x1800211d5  mov     rcx, [rsp+108h+strEapXmlUserData]; unsigned __int16 *
0x1800211dd  call    ?EapHlpGetEapBlobFromXmlUserData@@YAKPEBGKPEAEPEAU_EAP_METHOD_TYPE@@PEAKPEAPEAX@Z; EapHlpGetEapBlobFromXmlUserData(ushort const *,ulong,uchar *,_EAP_METHOD_TYPE *,ulong *,void * *)
0x1800211e2  mov     ebx, eax
0x1800211e4  test    eax, eax
0x1800211e6  jz      short loc_180021218
0x1800211e8  mov     r10, cs:WPP_GLOBAL_Control
0x1800211ef  cmp     r10, rsi
0x1800211f2  jz      loc_18002132B
0x1800211f8  cmp     byte ptr [r10+69h], 1
0x1800211fd  jb      loc_18002132B
0x180021203  test    byte ptr [r10+6Ch], 2
0x180021208  jz      loc_18002132B
0x18002120e  mov     edx, 8Fh
0x180021213  jmp     loc_180020E98
0x180021218  movaps  xmm0, xmmword ptr [rsp+108h+var_58.eapType.type]
0x180021220  movdqa  [rsp+108h+var_98], xmm0
0x180021226  mov     rax, [rsp+108h+var_70]
0x18002122e  mov     [rsp+108h+var_D8], rax
0x180021233  mov     eax, [rsp+108h+var_C4]
0x180021237  mov     dword ptr [rsp+108h+var_E0], eax
0x18002123b  mov     eax, [rsp+108h+arg_18]
0x180021242  mov     dword ptr [rsp+108h+var_E8], eax
0x180021246  lea     r9, [rsp+108h+var_98]
0x18002124b  mov     r8, r13
0x18002124e  mov     rdx, [rsp+108h+arg_8]
0x180021256  mov     rcx, [rsp+108h+var_A8]
0x18002125b  mov     rcx, [rcx]
0x18002125e  call    RpcSetProfileEapUserData
0x180021263  mov     ebx, eax
0x180021265  mov     [rsp+108h+var_C8], eax
0x180021269  mov     r10, cs:WPP_GLOBAL_Control
0x180021270  jmp     short loc_1800212C7
0x180021272  mov     ebx, eax
0x180021274  mov     [rsp+108h+var_C8], eax
0x180021278  lea     rax, WPP_GLOBAL_Control
0x18002127f  mov     r10, cs:WPP_GLOBAL_Control
0x180021286  cmp     r10, rax
0x180021289  jz      short loc_1800212B8
0x18002128b  cmp     byte ptr [r10+69h], 1
0x180021290  jb      short loc_1800212B8
0x180021292  test    byte ptr [r10+6Ch], 2
0x180021297  jz      short loc_1800212B8
0x180021299  mov     edx, 90h
0x18002129e  mov     r9d, ebx
0x1800212a1  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x1800212a8  mov     rcx, [r10+60h]
  ... truncated ...
```
