# VsmmHvMemPartpGetNumaNodeConfigPageCount

- ea: `0x1400c3a88`
- end: `0x1400c3dc4`
- name: `VsmmHvMemPartpGetNumaNodeConfigPageCount`
- size: `828`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x1400c53ac`
- `0x1400c54d8`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140018530`
- `0x140021650`
- `0x1400217a0`
- `0x1400248f0`
- `0x14002f524`
- `0x140090b0c`
- `0x140090c48`
- `0x140090cfc`
- `0x1400c3a88`
- `0x1400c44a4`
- `0x1400c5610`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400c3adb`
- `ntoskrnl!ExAllocatePool2` at `0x1400c3b2c`
- `ntoskrnl!ExAllocatePool2` at `0x1400c3adb`
- `ntoskrnl!ExAllocatePool2` at `0x1400c3b2c`

## string_xrefs

- `0x1400c3b09`: `VsmmHvMemPartpGetNumaNodeConfigPageCount`
- `0x1400c3b5a`: `VsmmHvMemPartpGetNumaNodeConfigPageCount`
- `0x1400c3b8b`: `VsmmHvMemPartpGetNumaNodeConfigPageCount`
- `0x1400c3ca7`: `VsmmHvMemPartpGetNumaNodeConfigPageCount`
- `0x1400c3d2b`: `VsmmHvMemPartpGetNumaNodeConfigPageCount`

## pseudocode

```c
__int64 __fastcall VsmmHvMemPartpGetNumaNodeConfigPageCount(__int64 a1)
{
  _BYTE *v1; // r15
  __int64 Pool2; // rax
  int v4; // ebx
  __int64 v5; // rax
  unsigned __int8 v6; // si
  __int64 UINT64WithDefault; // rbx
  __int64 v8; // rbx
  unsigned __int8 v10; // [rsp+30h] [rbp-99h] BYREF
  __int64 v11; // [rsp+38h] [rbp-91h] BYREF
  __int64 v12; // [rsp+40h] [rbp-89h] BYREF
  __int64 v13; // [rsp+48h] [rbp-81h] BYREF
  char v14[32]; // [rsp+50h] [rbp-79h] BYREF
  char v15[16]; // [rsp+70h] [rbp-59h] BYREF
  char v16[16]; // [rsp+80h] [rbp-49h] BYREF
  __int64 *v17; // [rsp+90h] [rbp-39h]
  __int64 v18; // [rsp+98h] [rbp-31h]
  char *v19; // [rsp+A0h] [rbp-29h]
  __int64 v20; // [rsp+A8h] [rbp-21h]
  __int64 *v21; // [rsp+B0h] [rbp-19h]
  __int64 v22; // [rsp+B8h] [rbp-11h]
  wchar_t pszDest[20]; // [rsp+C0h] [rbp-9h] BYREF

  v1 = VidDeviceExtension;
  v12 = 0;
  Pool2 = ExAllocatePool2(256, 8LL * *((unsigned __int8 *)VidDeviceExtension + 256), 1833788502);
  *(_QWORD *)(a1 + 392) = Pool2;
  if ( !Pool2 )
  {
    v4 = -1073741670;
    VidTraceErrorStatusInternal0(
      "VsmmHvMemPartpGetNumaNodeConfigPageCount",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c",
      1232);
    goto LABEL_19;
  }
  v5 = ExAllocatePool2(256, 8LL * (unsigned __int8)v1[256], 1833788502);
  *(_QWORD *)(a1 + 384) = v5;
  if ( !v5 )
  {
    v4 = -1073741670;
    VidTraceErrorStatusInternal0(
      "VsmmHvMemPartpGetNumaNodeConfigPageCount",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c",
      1244);
    goto LABEL_19;
  }
  if ( (int)VsmmHvMemPartpOpenHvMemPartKey(131097, &v12) < 0 )
  {
    VidTraceInfoInternal0(
      "VsmmHvMemPartpGetNumaNodeConfigPageCount",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c",
      1251);
    v4 = 0;
    goto LABEL_16;
  }
  v6 = 0;
  *(_DWORD *)(a1 + 160) = *(_DWORD *)(a1 + 160) & 0xFFFFFFEF
                        | ((unsigned int)VidRegistryQueryUINT32WithDefault(v12, L"AllowNumaSpanning", 0) != 0 ? 0x10 : 0);
  if ( !v1[256] )
  {
LABEL_14:
    v4 = 0;
    if ( !*(_QWORD *)(a1 + 400) )
      VidTraceInfoInternal0(
        "VsmmHvMemPartpGetNumaNodeConfigPageCount",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c",
        1335);
    goto LABEL_16;
  }
  while ( 1 )
  {
    v11 = 0;
    if ( RtlStringCchPrintfW(pszDest, 0x11u, L"Node%u", v6) < 0 )
      goto LABEL_13;
    if ( (int)VidRegistryOpenSubkey(v12, pszDest, 131097, &v11) < 0 )
      goto LABEL_13;
    UINT64WithDefault = VidRegistryQueryUINT64WithDefault(v11, L"SizeInMB", 0);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1848))(WdfDriverGlobals, v11);
    if ( !UINT64WithDefault )
      goto LABEL_13;
    v8 = UINT64WithDefault << 8;
    if ( (v8 & 0x1FF) != 0 )
      break;
    *(_QWORD *)(*(_QWORD *)(a1 + 392) + 8LL * v6) = v8;
    *(_QWORD *)(a1 + 400) += v8;
LABEL_13:
    if ( ++v6 >= v1[256] )
      goto LABEL_14;
  }
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v15, "VsmmHvMemPartpGetNumaNodeConfigPageCount");
    tlgCreate1Sz_char(v16, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmempart.c");
    LODWORD(v11) = 1322;
    v17 = &v11;
    v18 = 4;
    v19 = (char *)&v10;
    v10 = v6;
    v21 = &v13;
    v20 = 1;
    v13 = v8;
    v22 = 8;
    tlgWriteTransfer_EtwWriteTransfer(
      (__int64)&dword_140064110,
      (unsigned __int8 *)byte_14005278F,
      0,
      0,
      7u,
      (PEVENT_DATA_DESCRIPTOR)v14);
  }
  v4 = -1073741811;
LABEL_16:
  if ( v12 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1848))(WdfDriverGlobals, v12);
  if ( v4 < 0 )
LABEL_19:
    VsmmHvMemPartpTeardownLocked(a1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400c3a88  push    rbp
0x1400c3a8a  push    rbx
0x1400c3a8b  push    rsi
0x1400c3a8c  push    rdi
0x1400c3a8d  push    r13
0x1400c3a8f  push    r15
0x1400c3a91  lea     rbp, [rsp-2Fh]
0x1400c3a96  sub     rsp, 0F8h
0x1400c3a9d  mov     rax, cs:__security_cookie
0x1400c3aa4  xor     rax, rsp
0x1400c3aa7  mov     [rbp+57h+var_38], rax
0x1400c3aab  mov     r15, cs:VidDeviceExtension
0x1400c3ab2  mov     rdi, rcx
0x1400c3ab5  mov     ebx, 6D4D6456h
0x1400c3aba  mov     [rsp+120h+var_E0], 0
0x1400c3ac3  mov     r13d, 100h
0x1400c3ac9  mov     r8d, ebx
0x1400c3acc  mov     ecx, r13d
0x1400c3acf  movzx   edx, byte ptr [r15+100h]
0x1400c3ad7  shl     rdx, 3
0x1400c3adb  call    cs:__imp_ExAllocatePool2
0x1400c3ae2  nop     dword ptr [rax+rax+00h]
0x1400c3ae7  mov     [rdi+188h], rax
0x1400c3aee  test    rax, rax
0x1400c3af1  jnz     short loc_1400C3B1A
0x1400c3af3  mov     r9d, 0C000009Ah
0x1400c3af9  mov     ebx, r9d
0x1400c3afc  mov     r8d, 4D0h
0x1400c3b02  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c3b09  lea     rcx, aVsmmhvmempartp; "VsmmHvMemPartpGetNumaNodeConfigPageCoun"...
0x1400c3b10  call    VidTraceErrorStatusInternal0
0x1400c3b15  jmp     loc_1400C3CDE
0x1400c3b1a  movzx   edx, byte ptr [r15+100h]
0x1400c3b22  mov     r8d, ebx
0x1400c3b25  shl     rdx, 3
0x1400c3b29  mov     rcx, r13
0x1400c3b2c  call    cs:__imp_ExAllocatePool2
0x1400c3b33  nop     dword ptr [rax+rax+00h]
0x1400c3b38  mov     [rdi+180h], rax
0x1400c3b3f  test    rax, rax
0x1400c3b42  jnz     short loc_1400C3B6B
0x1400c3b44  mov     r9d, 0C000009Ah
0x1400c3b4a  mov     ebx, r9d
0x1400c3b4d  mov     r8d, 4DCh
0x1400c3b53  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c3b5a  lea     rcx, aVsmmhvmempartp; "VsmmHvMemPartpGetNumaNodeConfigPageCoun"...
0x1400c3b61  call    VidTraceErrorStatusInternal0
0x1400c3b66  jmp     loc_1400C3CDE
0x1400c3b6b  lea     rdx, [rsp+120h+var_E0]
0x1400c3b70  mov     ecx, 20019h
0x1400c3b75  call    VsmmHvMemPartpOpenHvMemPartKey
0x1400c3b7a  test    eax, eax
0x1400c3b7c  jns     short loc_1400C3B9E
0x1400c3b7e  mov     r8d, 4E3h
0x1400c3b84  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c3b8b  lea     rcx, aVsmmhvmempartp; "VsmmHvMemPartpGetNumaNodeConfigPageCoun"...
0x1400c3b92  call    VidTraceInfoInternal0
0x1400c3b97  xor     ebx, ebx
0x1400c3b99  jmp     loc_1400C3CB3
0x1400c3b9e  mov     rcx, [rsp+120h+var_E0]
0x1400c3ba3  lea     rdx, aAllownumaspann; "AllowNumaSpanning"
0x1400c3baa  xor     r8d, r8d
0x1400c3bad  call    VidRegistryQueryUINT32WithDefault
0x1400c3bb2  neg     eax
0x1400c3bb4  mov     eax, [rdi+0A0h]
0x1400c3bba  sbb     ecx, ecx
0x1400c3bbc  and     eax, 0FFFFFFEFh
0x1400c3bbf  and     ecx, 10h
0x1400c3bc2  xor     sil, sil
0x1400c3bc5  or      ecx, eax
0x1400c3bc7  mov     [rdi+0A0h], ecx
0x1400c3bcd  cmp     [r15+100h], sil
0x1400c3bd4  jbe     loc_1400C3C8F
0x1400c3bda  movzx   r9d, sil
0x1400c3bde  lea     r8, aNodeU; "Node%u"
0x1400c3be5  mov     edx, 11h; cchDest
0x1400c3bea  mov     [rsp+120h+var_E8], 0
0x1400c3bf3  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1400c3bf7  call    RtlStringCchPrintfW
0x1400c3bfc  test    eax, eax
0x1400c3bfe  js      short loc_1400C3C7F
0x1400c3c00  mov     rcx, [rsp+120h+var_E0]
0x1400c3c05  lea     r9, [rsp+120h+var_E8]
0x1400c3c0a  mov     r8d, 20019h
0x1400c3c10  lea     rdx, [rbp+57h+pszDest]
0x1400c3c14  call    VidRegistryOpenSubkey
0x1400c3c19  test    eax, eax
0x1400c3c1b  js      short loc_1400C3C7F
0x1400c3c1d  mov     rcx, [rsp+120h+var_E8]
0x1400c3c22  lea     rdx, aSizeinmb; "SizeInMB"
0x1400c3c29  xor     r8d, r8d
0x1400c3c2c  call    VidRegistryQueryUINT64WithDefault
0x1400c3c31  mov     rcx, cs:WdfFunctions_01015
0x1400c3c38  mov     rbx, rax
0x1400c3c3b  mov     rdx, [rsp+120h+var_E8]
0x1400c3c40  mov     rax, [rcx+738h]
0x1400c3c47  mov     rcx, cs:WdfDriverGlobals
0x1400c3c4e  call    _guard_dispatch_icall
0x1400c3c53  test    rbx, rbx
0x1400c3c56  jz      short loc_1400C3C7F
0x1400c3c58  shl     rbx, 8
0x1400c3c5c  test    rbx, 1FFh
0x1400c3c63  jnz     loc_1400C3D05
0x1400c3c69  mov     rax, [rdi+188h]
0x1400c3c70  movzx   ecx, sil
0x1400c3c74  mov     [rax+rcx*8], rbx
0x1400c3c78  add     [rdi+190h], rbx
0x1400c3c7f  inc     sil
0x1400c3c82  cmp     sil, [r15+100h]
0x1400c3c89  jb      loc_1400C3BDA
0x1400c3c8f  xor     ebx, ebx
0x1400c3c91  cmp     [rdi+190h], rbx
0x1400c3c98  jnz     short loc_1400C3CB3
0x1400c3c9a  mov     r8d, 537h
0x1400c3ca0  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c3ca7  lea     rcx, aVsmmhvmempartp; "VsmmHvMemPartpGetNumaNodeConfigPageCoun"...
0x1400c3cae  call    VidTraceInfoInternal0
0x1400c3cb3  cmp     [rsp+120h+var_E0], 0
0x1400c3cb9  jz      short loc_1400C3CDA
0x1400c3cbb  mov     rax, cs:WdfFunctions_01015
0x1400c3cc2  mov     rdx, [rsp+120h+var_E0]
0x1400c3cc7  mov     rcx, cs:WdfDriverGlobals
0x1400c3cce  mov     rax, [rax+738h]
0x1400c3cd5  call    _guard_dispatch_icall
0x1400c3cda  test    ebx, ebx
0x1400c3cdc  jns     short loc_1400C3CE6
0x1400c3cde  mov     rcx, rdi
0x1400c3ce1  call    VsmmHvMemPartpTeardownLocked
0x1400c3ce6  mov     eax, ebx
0x1400c3ce8  mov     rcx, [rbp+57h+var_38]
0x1400c3cec  xor     rcx, rsp; StackCookie
0x1400c3cef  call    __security_check_cookie
0x1400c3cf4  add     rsp, 0F8h
0x1400c3cfb  pop     r15
0x1400c3cfd  pop     r13
0x1400c3cff  pop     rdi
0x1400c3d00  pop     rsi
0x1400c3d01  pop     rbx
0x1400c3d02  pop     rbp
0x1400c3d03  retn
0x1400c3d05  mov     eax, cs:dword_140064110
0x1400c3d0b  cmp     eax, 2
0x1400c3d0e  jbe     loc_1400C3DBA
0x1400c3d14  mov     rdx, r13
0x1400c3d17  lea     rcx, dword_140064110
0x1400c3d1e  call    _tlgKeywordOn
0x1400c3d23  test    al, al
0x1400c3d25  jz      loc_1400C3DBA
0x1400c3d2b  lea     rdx, aVsmmhvmempartp; "VsmmHvMemPartpGetNumaNodeConfigPageCoun"...
0x1400c3d32  lea     rcx, [rbp+57h+var_B0]
0x1400c3d36  call    _tlgCreate1Sz_char
0x1400c3d3b  lea     rdx, aOnecoreVmVidSy_41; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhvmemp"...
0x1400c3d42  lea     rcx, [rbp+57h+var_A0]
0x1400c3d46  call    _tlgCreate1Sz_char
0x1400c3d4b  lea     rax, [rsp+120h+var_E8]
0x1400c3d50  mov     dword ptr [rsp+120h+var_E8], 52Ah
0x1400c3d58  mov     [rbp+57h+var_90], rax
0x1400c3d5c  lea     rdx, byte_14005278F
0x1400c3d63  lea     rax, [rsp+120h+var_F0]
0x1400c3d68  mov     [rbp+57h+var_88], 4
0x1400c3d70  mov     [rbp+57h+var_80], rax
0x1400c3d74  lea     rcx, dword_140064110
0x1400c3d7b  lea     rax, [rsp+120h+var_D8]
0x1400c3d80  mov     [rsp+120h+var_F0], sil
0x1400c3d85  mov     [rbp+57h+var_70], rax
0x1400c3d89  xor     r9d, r9d
0x1400c3d8c  lea     rax, [rbp+57h+var_D0]
0x1400c3d90  mov     [rbp+57h+var_78], 1
0x1400c3d98  mov     [rsp+120h+var_F8], rax
0x1400c3d9d  xor     r8d, r8d
0x1400c3da0  mov     [rsp+120h+var_100], 7
0x1400c3da8  mov     [rsp+120h+var_D8], rbx
0x1400c3dad  mov     [rbp+57h+var_68], 8
0x1400c3db5  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400c3dba  mov     ebx, 0C000000Dh
0x1400c3dbf  jmp     loc_1400C3CB3
```
