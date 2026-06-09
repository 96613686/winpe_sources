# CSGetAccountPropertyStore

- ea: `0x180002bf0`
- end: `0x180002f7b`
- name: `CSGetAccountPropertyStore`
- size: `907`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002bc0`
- `0x18000fe00`
- `0x1800115a0`
- `0x180011e80`

## callees

- `0x180002bf0`
- `0x180002f90`
- `0x180002ff0`
- `0x1800037e0`
- `0x18000d740`
- `0x180012f18`
- `0x180013130`
- `0x18001656c`
- `0x1800165f0`
- `0x180017010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180002d7e`
- `ntdll!RtlInitUnicodeString` at `0x180002d7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002d4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002d4b`
- `SAMLIB!SamLookupNamesInDomain2` at `0x180002d9d`
- `SAMLIB!SamLookupNamesInDomain2` at `0x180002d9d`
- `SAMLIB!SamOpenDomain` at `0x180002cbd`
- `SAMLIB!SamOpenDomain` at `0x180002cbd`
- `SAMLIB!SamConnect` at `0x180002c9d`
- `SAMLIB!SamConnect` at `0x180002c9d`
- `SAMLIB!SamCloseHandle` at `0x180002cdd`
- `SAMLIB!SamCloseHandle` at `0x180002e33`
- `SAMLIB!SamCloseHandle` at `0x180002e3d`
- `SAMLIB!SamCloseHandle` at `0x180002cdd`
- `SAMLIB!SamCloseHandle` at `0x180002e33`
- `SAMLIB!SamCloseHandle` at `0x180002e3d`
- `SAMLIB!SamFreeMemory` at `0x180002dd9`
- `SAMLIB!SamFreeMemory` at `0x180002de3`
- `SAMLIB!SamFreeMemory` at `0x180002dd9`
- `SAMLIB!SamFreeMemory` at `0x180002de3`

## pseudocode

```c
__int64 __fastcall CSGetAccountPropertyStore(void *a1, const WCHAR *a2, int a3, unsigned int a4, _QWORD *a5)
{
  _QWORD *v5; // r13
  char v7; // al
  __int64 v9; // r12
  void *v10; // rdi
  int v11; // eax
  int v12; // ebx
  int v13; // r14d
  int v14; // ebx
  int v15; // ebx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  int v19; // r8d
  unsigned int v20; // edi
  int v21; // r14d
  CSamPropStore *v23; // rax
  CSamPropStore *v24; // rax
  CSamPropStore *v25; // rbx
  int v26; // edx
  int v27; // edi
  int v28; // r8d
  int v29; // eax
  _DWORD *v30; // [rsp+48h] [rbp-41h] BYREF
  __int64 v31; // [rsp+50h] [rbp-39h] BYREF
  unsigned int *v32; // [rsp+58h] [rbp-31h] BYREF
  LPVOID v33; // [rsp+60h] [rbp-29h]
  _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v35[4]; // [rsp+78h] [rbp-11h] BYREF
  __int128 v36; // [rsp+98h] [rbp+Fh]
  LPVOID pv; // [rsp+F0h] [rbp+67h] BYREF
  int v38; // [rsp+F8h] [rbp+6Fh]
  unsigned int v39; // [rsp+100h] [rbp+77h]

  v39 = a4;
  v38 = a3;
  v5 = a5;
  v7 = a3;
  *a5 = 0;
  if ( !a2 )
  {
    v16 = WPP_GLOBAL_Control;
    v12 = -2147467261;
    goto LABEL_51;
  }
  v9 = 0;
  v39 = 0;
  v10 = a1;
  LODWORD(a5) = 0;
  pv = a1;
  v33 = 0;
  if ( a1 )
  {
    v13 = 0;
    goto LABEL_6;
  }
  v11 = CSGetAccountDomainSid(&pv);
  v10 = pv;
  v12 = v11;
  v13 = 1;
  if ( v11 >= 0 )
  {
LABEL_6:
    pv = 0;
    memset(&v35[1], 0, 24);
    v35[0] = 48;
    v36 = 0;
    v14 = SamConnect(0, &pv, 131105, v35);
    if ( v14 < 0 )
    {
      v12 = v14 | 0x10000000;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v17 = 35;
        goto LABEL_15;
      }
    }
    else
    {
      v31 = 0;
      v15 = SamOpenDomain(pv, 131973, v10, &v31);
      if ( v15 >= 0 )
      {
        v12 = 0;
        v9 = v31;
        v33 = pv;
LABEL_16:
        v16 = WPP_GLOBAL_Control;
        goto LABEL_17;
      }
      SamCloseHandle(pv);
      v12 = v15 | 0x10000000;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v17 = 34;
LABEL_15:
        WPP_SF_d(v16[2], v17, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, (unsigned int)v12);
        goto LABEL_16;
      }
    }
LABEL_17:
    if ( !v13 )
      goto LABEL_19;
  }
  CoTaskMemFree(v10);
  v16 = WPP_GLOBAL_Control;
LABEL_19:
  if ( v12 < 0 )
  {
    v20 = v39;
    goto LABEL_36;
  }
  v32 = 0;
  v30 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  v18 = SamLookupNamesInDomain2(v9, 1, &DestinationString, &v32, &v30);
  if ( v18 < 0 )
  {
    if ( v18 == -1073741709 )
    {
      v12 = -2147023728;
    }
    else
    {
      v12 = v18 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, v19, (_DWORD)a2, v18);
    }
    v20 = v39;
    goto LABEL_34;
  }
  if ( *v30 == 4 )
  {
    LODWORD(a5) = 2;
  }
  else
  {
    if ( *v30 != 1 )
    {
      v20 = v39;
      v12 = -805306230;
      goto LABEL_27;
    }
    LODWORD(a5) = 1;
  }
  v20 = *v32;
  v39 = *v32;
LABEL_27:
  SamFreeMemory(v32);
  SamFreeMemory(v30);
LABEL_34:
  SamCloseHandle(v9);
  SamCloseHandle(v33);
  v16 = WPP_GLOBAL_Control;
LABEL_36:
  if ( v12 >= 0 )
  {
    v21 = v38;
    if ( (_DWORD)a5 != v38 )
      return 3489661066LL;
    v23 = (CSamPropStore *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v23 )
      return 2147942414LL;
    v24 = CSamPropStore::CSamPropStore(v23);
    v25 = v24;
    if ( !v24 )
      return 2147942414LL;
    v27 = CSamPropStore::_Init((__int64)v24, a1, a2, v20, v21, 0);
    if ( v27 >= 0 )
    {
      v29 = (**(__int64 (__fastcall ***)(CSamPropStore *, GUID *, _QWORD *))v25)(
              v25,
              &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
              v5);
      if ( v29 < 0 )
        v27 = v29;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_SddD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, v28, (_DWORD)a2, v21, v39, v27);
    }
    (*(void (__fastcall **)(CSamPropStore *))(*(_QWORD *)v25 + 16LL))(v25);
    return (unsigned int)v27;
  }
  v7 = v38;
LABEL_51:
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 2) != 0 )
    WPP_SF_Sd(v16[2], (unsigned int)&WPP_GLOBAL_Control, a3, (_DWORD)a2, v7);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180002bf0  mov     r11, rsp
0x180002bf3  mov     [r11+20h], r9d
0x180002bf7  mov     [r11+18h], r8d
0x180002bfb  push    rbp
0x180002bfc  push    rbx
0x180002bfd  push    rsi
0x180002bfe  push    rdi
0x180002bff  push    r13
0x180002c01  push    r14
0x180002c03  push    r15
0x180002c05  lea     rbp, [r11-57h]
0x180002c09  sub     rsp, 0A0h
0x180002c10  mov     r13, [rbp+4Fh+arg_20]
0x180002c14  mov     rsi, rcx
0x180002c17  xor     ecx, ecx
0x180002c19  mov     eax, r8d
0x180002c1c  mov     r15, rdx
0x180002c1f  mov     [r13+0], rcx
0x180002c23  test    rdx, rdx
0x180002c26  jz      loc_180002F39
0x180002c2c  mov     [r11+8], r12
0x180002c30  mov     r12d, ecx
0x180002c33  mov     [rbp+4Fh+arg_18], ecx
0x180002c36  mov     rdi, rsi
0x180002c39  mov     dword ptr [rbp+4Fh+arg_20], ecx
0x180002c3c  mov     [rbp+4Fh+pv], rsi
0x180002c40  mov     [rbp+4Fh+var_78], rcx
0x180002c44  test    rsi, rsi
0x180002c47  jnz     short loc_180002C6A
0x180002c49  lea     rcx, [rbp+4Fh+pv]
0x180002c4d  call    CSGetAccountDomainSid
0x180002c52  mov     rdi, [rbp+4Fh+pv]
0x180002c56  mov     ebx, eax
0x180002c58  mov     r14d, 1
0x180002c5e  test    eax, eax
0x180002c60  js      loc_180002D48
0x180002c66  xor     ecx, ecx
0x180002c68  jmp     short loc_180002C6D
0x180002c6a  mov     r14d, ecx
0x180002c6d  mov     [rbp+4Fh+pv], rcx
0x180002c71  lea     r9, [rbp+4Fh+var_60]
0x180002c75  mov     [rbp+4Fh+var_58], rcx
0x180002c79  lea     rdx, [rbp+4Fh+pv]
0x180002c7d  mov     [rbp+4Fh+var_50], rcx
0x180002c81  xorps   xmm0, xmm0
0x180002c84  xor     ecx, ecx
0x180002c86  mov     [rbp+4Fh+var_60], 30h ; '0'
0x180002c8e  mov     r8d, 20021h
0x180002c94  mov     [rbp+4Fh+var_48], r12
0x180002c98  movdqu  [rbp+4Fh+var_40], xmm0
0x180002c9d  call    cs:__imp_SamConnect
0x180002ca3  mov     ebx, eax
0x180002ca5  test    eax, eax
0x180002ca7  js      short loc_180002D07
0x180002ca9  mov     rcx, [rbp+4Fh+pv]
0x180002cad  lea     r9, [rbp+4Fh+var_88]
0x180002cb1  mov     r8, rdi
0x180002cb4  mov     [rbp+4Fh+var_88], r12
0x180002cb8  mov     edx, 20385h
0x180002cbd  call    cs:__imp_SamOpenDomain
0x180002cc3  mov     ebx, eax
0x180002cc5  test    eax, eax
0x180002cc7  js      short loc_180002CD9
0x180002cc9  mov     rax, [rbp+4Fh+pv]
0x180002ccd  xor     ebx, ebx
0x180002ccf  mov     r12, [rbp+4Fh+var_88]
0x180002cd3  mov     [rbp+4Fh+var_78], rax
0x180002cd7  jmp     short loc_180002D3C
0x180002cd9  mov     rcx, [rbp+4Fh+pv]
0x180002cdd  call    cs:__imp_SamCloseHandle
0x180002ce3  bts     ebx, 1Ch
0x180002ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cee  lea     rax, WPP_GLOBAL_Control
0x180002cf5  cmp     rcx, rax
0x180002cf8  jz      short loc_180002D43
0x180002cfa  test    byte ptr [rcx+1Ch], 2
0x180002cfe  jz      short loc_180002D43
0x180002d00  mov     edx, 22h ; '"'
0x180002d05  jmp     short loc_180002D29
0x180002d07  bts     ebx, 1Ch
0x180002d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d12  lea     rax, WPP_GLOBAL_Control
0x180002d19  cmp     rcx, rax
0x180002d1c  jz      short loc_180002D43
0x180002d1e  test    byte ptr [rcx+1Ch], 2
0x180002d22  jz      short loc_180002D43
0x180002d24  mov     edx, 23h ; '#'
0x180002d29  mov     rcx, [rcx+10h]
0x180002d2d  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180002d34  mov     r9d, ebx
0x180002d37  call    WPP_SF_d
0x180002d3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d43  test    r14d, r14d
0x180002d46  jz      short loc_180002D58
0x180002d48  mov     rcx, rdi; pv
0x180002d4b  call    cs:__imp_CoTaskMemFree
0x180002d51  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d58  test    ebx, ebx
0x180002d5a  js      loc_180002E4C
0x180002d60  xorps   xmm0, xmm0
0x180002d63  mov     [rbp+4Fh+var_80], 0
0x180002d6b  mov     rdx, r15; SourceString
0x180002d6e  mov     [rbp+4Fh+var_90], 0
0x180002d76  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x180002d7a  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x180002d7e  call    cs:__imp_RtlInitUnicodeString
0x180002d84  lea     rax, [rbp+4Fh+var_90]
0x180002d88  mov     edx, 1
0x180002d8d  lea     r9, [rbp+4Fh+var_80]
0x180002d91  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180002d96  lea     r8, [rbp+4Fh+DestinationString]
0x180002d9a  mov     rcx, r12
0x180002d9d  call    cs:__imp_SamLookupNamesInDomain2
0x180002da3  test    eax, eax
0x180002da5  js      short loc_180002DEB
0x180002da7  mov     rax, [rbp+4Fh+var_90]
0x180002dab  mov     ecx, [rax]
0x180002dad  mov     rax, [rbp+4Fh+var_80]
0x180002db1  cmp     ecx, 4
0x180002db4  jnz     short loc_180002DBF
0x180002db6  mov     dword ptr [rbp+4Fh+arg_20], 2
0x180002dbd  jmp     short loc_180002DC7
0x180002dbf  cmp     ecx, 1
0x180002dc2  jnz     short loc_180002DCE
0x180002dc4  mov     dword ptr [rbp+4Fh+arg_20], ecx
0x180002dc7  mov     edi, [rax]
0x180002dc9  mov     [rbp+4Fh+arg_18], edi
0x180002dcc  jmp     short loc_180002DD6
0x180002dce  mov     edi, [rbp+4Fh+arg_18]
0x180002dd1  mov     ebx, 0D000008Ah
0x180002dd6  mov     rcx, rax
0x180002dd9  call    cs:__imp_SamFreeMemory
0x180002ddf  mov     rcx, [rbp+4Fh+var_90]
0x180002de3  call    cs:__imp_SamFreeMemory
0x180002de9  jmp     short loc_180002E30
0x180002deb  cmp     eax, 0C0000073h
0x180002df0  jnz     short loc_180002DF9
0x180002df2  mov     ebx, 80070490h
0x180002df7  jmp     short loc_180002E2D
0x180002df9  mov     ebx, eax
0x180002dfb  bts     ebx, 1Ch
0x180002dff  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e06  lea     rax, WPP_GLOBAL_Control
0x180002e0d  cmp     rcx, rax
0x180002e10  jz      short loc_180002E2D
0x180002e12  test    byte ptr [rcx+1Ch], 2
0x180002e16  jz      short loc_180002E2D
0x180002e18  mov     rcx, [rcx+10h]
0x180002e1c  mov     edx, 42h ; 'B'
0x180002e21  mov     r9, r15
0x180002e24  mov     [rsp+0D0h+var_B0], ebx
0x180002e28  call    WPP_SF_SD
0x180002e2d  mov     edi, [rbp+4Fh+arg_18]
0x180002e30  mov     rcx, r12
0x180002e33  call    cs:__imp_SamCloseHandle
0x180002e39  mov     rcx, [rbp+4Fh+var_78]
0x180002e3d  call    cs:__imp_SamCloseHandle
0x180002e43  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e4a  jmp     short loc_180002E4F
0x180002e4c  mov     edi, [rbp+4Fh+arg_18]
0x180002e4f  mov     r12, [rsp+0D0h+arg_0]
0x180002e57  test    ebx, ebx
0x180002e59  js      loc_180002F34
0x180002e5f  mov     r14d, [rbp+4Fh+arg_10]
0x180002e63  cmp     dword ptr [rbp+4Fh+arg_20], r14d
0x180002e67  jz      short loc_180002E73
0x180002e69  mov     eax, 0D000008Ah
0x180002e6e  jmp     loc_180002F69
0x180002e73  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002e7a  mov     ecx, 70h ; 'p'; unsigned __int64
0x180002e7f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002e84  test    rax, rax
0x180002e87  jz      loc_180002F2D
0x180002e8d  mov     rcx, rax; this
0x180002e90  call    ??0CSamPropStore@@QEAA@XZ; CSamPropStore::CSamPropStore(void)
0x180002e95  mov     rbx, rax
0x180002e98  test    rax, rax
0x180002e9b  jz      loc_180002F2D
0x180002ea1  mov     [rsp+0D0h+var_A8], 0
0x180002ea9  mov     r9d, edi
0x180002eac  mov     r8, r15
0x180002eaf  mov     [rsp+0D0h+var_B0], r14d
0x180002eb4  mov     rdx, rsi
0x180002eb7  mov     rcx, rax
0x180002eba  call    ?_Init@CSamPropStore@@QEAAJPEAXPEBGKW4_ACCOUNT_OBJECT_TYPE@@H@Z; CSamPropStore::_Init(void *,ushort const *,ulong,_ACCOUNT_OBJECT_TYPE,int)
0x180002ebf  mov     edi, eax
0x180002ec1  test    eax, eax
0x180002ec3  jns     short loc_180002EFC
0x180002ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ecc  lea     rax, WPP_GLOBAL_Control
0x180002ed3  cmp     rcx, rax
0x180002ed6  jz      short loc_180002F1A
0x180002ed8  test    byte ptr [rcx+1Ch], 2
0x180002edc  jz      short loc_180002F1A
0x180002ede  mov     eax, [rbp+4Fh+arg_18]
0x180002ee1  mov     r9, r15
0x180002ee4  mov     rcx, [rcx+10h]
0x180002ee8  mov     [rsp+30h], edi
0x180002eec  mov     [rsp+0D0h+var_A8], eax
0x180002ef0  mov     [rsp+0D0h+var_B0], r14d
0x180002ef5  call    WPP_SF_SddD
0x180002efa  jmp     short loc_180002F1A
0x180002efc  mov     rax, [rbx]
0x180002eff  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180002f06  mov     r8, r13
0x180002f09  mov     rcx, rbx
0x180002f0c  mov     rax, [rax]
0x180002f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f14  test    eax, eax
0x180002f16  jns     short loc_180002F1A
0x180002f18  mov     edi, eax
0x180002f1a  mov     rax, [rbx]
0x180002f1d  mov     rcx, rbx
0x180002f20  mov     rax, [rax+10h]
0x180002f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f29  mov     eax, edi
0x180002f2b  jmp     short loc_180002F69
0x180002f2d  mov     eax, 8007000Eh
0x180002f32  jmp     short loc_180002F69
0x180002f34  mov     eax, [rbp+4Fh+arg_10]
0x180002f37  jmp     short loc_180002F45
0x180002f39  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f40  mov     ebx, 80004003h
0x180002f45  lea     rdx, WPP_GLOBAL_Control
0x180002f4c  cmp     rcx, rdx
0x180002f4f  jz      short loc_180002F67
0x180002f51  test    byte ptr [rcx+1Ch], 2
0x180002f55  jz      short loc_180002F67
0x180002f57  mov     rcx, [rcx+10h]
0x180002f5b  mov     r9, r15
0x180002f5e  mov     [rsp+0D0h+var_B0], eax
0x180002f62  call    WPP_SF_Sd
0x180002f67  mov     eax, ebx
0x180002f69  add     rsp, 0A0h
0x180002f70  pop     r15
0x180002f72  pop     r14
0x180002f74  pop     r13
0x180002f76  pop     rdi
0x180002f77  pop     rsi
0x180002f78  pop     rbx
0x180002f79  pop     rbp
0x180002f7a  retn
```
