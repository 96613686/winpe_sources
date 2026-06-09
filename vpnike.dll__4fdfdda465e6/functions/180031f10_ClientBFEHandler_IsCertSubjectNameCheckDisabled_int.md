# ClientBFEHandler::IsCertSubjectNameCheckDisabled(int *)

- ea: `0x180031f10`
- end: `0x1800322ac`
- name: `?IsCertSubjectNameCheckDisabled@ClientBFEHandler@@IEAAKPEAH@Z`
- size: `924`
- prototype: `__int64 __fastcall(ClientBFEHandler *this, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180039278`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180031f10`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003221b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003221b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032022`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032022`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031fd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031fd6`

## string_xrefs

- `0x180031f99`: `System\CurrentControlSet\Services\Rasman\Parameters`
- `0x180032082`: `IsCertSubjectNameCheckDisabled: DisableIKENameEkuCheck value as read from the registry is: %d`

## pseudocode

```c
__int64 __fastcall ClientBFEHandler::IsCertSubjectNameCheckDisabled(ClientBFEHandler *this, int *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rcx
  __int128 *v13; // r9
  PVOID *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rcx
  _QWORD *v19; // rax
  __int64 v20; // rcx
  __int128 *v21; // r9
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v27; // [rsp+48h] [rbp-B8h] BYREF
  int v28; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v29; // [rsp+5Ch] [rbp-A4h]
  __int128 v30; // [rsp+6Ch] [rbp-94h]
  int v31; // [rsp+7Ch] [rbp-84h]
  int v32; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v33[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
  }
  hKey = 0;
  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  v28 = 0;
  v31 = 0;
  *a2 = 0;
  v29 = 0;
  v30 = 0;
  v27 = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Rasman\\Parameters", 0, 0x20019u, &hKey);
  v5 = v4;
  if ( !v4 )
  {
    Type = 0;
    *(_DWORD *)Data = 1;
    cbData = 4;
    LODWORD(v6) = RegQueryValueExW(hKey, L"DisableIKENameEkuCheck", 0, &Type, Data, &cbData);
    v5 = v6;
    if ( (_DWORD)v6 )
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_30:
        if ( (byte_1800AA941 & 4) == 0 )
          goto LABEL_47;
        v15 = *((_QWORD *)this + 6);
        LOWORD(v32) = 0;
        LOWORD(v28) = 0;
        if ( v15 && (v16 = *(_QWORD *)(v15 + 112)) != 0 && *(_QWORD *)(v16 + 16) )
          v17 = *(unsigned int *)(v16 + 16);
        else
          v17 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v28, v17);
        FormatRRASErrorString(
          &v32,
          L"IsCertSubjectNameCheckDisabled failed: RegQueryValueEx for DisableIKENameEkuCheck failed with %d",
          v5);
        if ( (byte_1800AA941 & 4) == 0 )
        {
LABEL_46:
          v14 = (PVOID *)WPP_GLOBAL_Control;
LABEL_47:
          if ( hKey )
          {
            RegCloseKey(hKey);
LABEL_53:
            v14 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_54;
          }
          goto LABEL_54;
        }
        v18 = *((_QWORD *)this + 6);
        v19 = (_QWORD *)(v18 + 112);
        if ( v18 )
        {
          if ( *v19 )
            v20 = *v19 + 2686LL;
          else
            v20 = 0;
          if ( *v19 )
          {
            v21 = (__int128 *)(*v19 + 2120LL);
LABEL_45:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v32,
              (_DWORD)v21,
              v20,
              (__int64)&v28);
            goto LABEL_46;
          }
        }
        else
        {
          v20 = 0;
        }
        v21 = &v27;
        goto LABEL_45;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        173,
        &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
        (unsigned int)v6);
    }
    else if ( Type == 4 )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_24;
      v7 = *((_QWORD *)this + 6);
      LOWORD(v32) = 0;
      LOWORD(v28) = 0;
      if ( v7 && (v8 = *(_QWORD *)(v7 + 112)) != 0 && *(_QWORD *)(v8 + 16) != v6 )
        v9 = *(unsigned int *)(v8 + 16);
      else
        v9 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v28, v9);
      FormatRRASErrorString(
        &v32,
        L"IsCertSubjectNameCheckDisabled: DisableIKENameEkuCheck value as read from the registry is: %d",
        *(unsigned int *)Data);
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_24;
      v10 = *((_QWORD *)this + 6);
      v11 = (_QWORD *)(v10 + 112);
      if ( v10 )
      {
        if ( *v11 )
          v12 = *v11 + 2686LL;
        else
          v12 = 0;
        if ( *v11 )
        {
          v13 = (__int128 *)(*v11 + 2120LL);
LABEL_23:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v32,
            (_DWORD)v13,
            v12,
            (__int64)&v28);
LABEL_24:
          *a2 = *(_DWORD *)Data == 1;
          goto LABEL_46;
        }
      }
      else
      {
        v12 = 0;
      }
      v13 = &v27;
      goto LABEL_23;
    }
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_30;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v4);
    goto LABEL_53;
  }
LABEL_54:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 6u )
    WPP_SF_d(v14[2], 175, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180031f10  mov     [rsp-8+arg_10], rbx
0x180031f15  mov     [rsp-8+arg_18], rsi
0x180031f1a  push    rbp
0x180031f1b  push    rdi
0x180031f1c  push    r13
0x180031f1e  lea     rbp, [rsp-790h]
0x180031f26  sub     rsp, 890h
0x180031f2d  mov     rax, cs:__security_cookie
0x180031f34  xor     rax, rsp
0x180031f37  mov     [rbp+7A0h+var_20], rax
0x180031f3e  mov     rsi, rdx
0x180031f41  mov     rdi, rcx
0x180031f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180031f4b  lea     r13, WPP_GLOBAL_Control
0x180031f52  cmp     rcx, r13
0x180031f55  jz      short loc_180031F78
0x180031f57  test    byte ptr [rcx+1Ch], 1
0x180031f5b  jz      short loc_180031F78
0x180031f5d  cmp     byte ptr [rcx+19h], 6
0x180031f61  jb      short loc_180031F78
0x180031f63  mov     rcx, [rcx+10h]
0x180031f67  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180031f6e  mov     edx, 0ACh
0x180031f73  call    WPP_SF_
0x180031f78  xor     eax, eax
0x180031f7a  mov     [rsp+8A0h+hKey], 0
0x180031f83  xor     edx, edx; Val
0x180031f85  mov     [rbp+7A0h+var_820], eax
0x180031f88  mov     r8d, 7FCh; Size
0x180031f8e  lea     rcx, [rbp+7A0h+var_81C]; void *
0x180031f92  call    memset_0
0x180031f97  xor     eax, eax
0x180031f99  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\Ra"...
0x180031fa0  xorps   xmm0, xmm0
0x180031fa3  mov     [rsp+8A0h+var_848], eax
0x180031fa7  mov     [rsp+8A0h+var_824], eax
0x180031fab  mov     r9d, 20019h; samDesired
0x180031fb1  mov     [rsi], eax
0x180031fb3  xor     r8d, r8d; ulOptions
0x180031fb6  lea     rax, [rsp+8A0h+hKey]
0x180031fbb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031fc2  mov     [rsp+8A0h+phkResult], rax; phkResult
0x180031fc7  movups  [rsp+8A0h+var_844], xmm0
0x180031fcc  movups  [rsp+8A0h+var_834], xmm0
0x180031fd1  movups  [rsp+8A0h+var_858], xmm0
0x180031fd6  call    cs:__imp_RegOpenKeyExW
0x180031fdc  mov     ebx, eax
0x180031fde  test    eax, eax
0x180031fe0  jnz     loc_180032223
0x180031fe6  mov     rcx, [rsp+8A0h+hKey]; hKey
0x180031feb  lea     r9, [rsp+8A0h+Type]; lpType
0x180031ff0  mov     [rsp+8A0h+Type], eax
0x180031ff4  lea     rdx, aDisableikename; "DisableIKENameEkuCheck"
0x180031ffb  lea     rax, [rsp+8A0h+cbData]
0x180032000  mov     dword ptr [rsp+8A0h+Data], 1
0x180032008  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18003200d  xor     r8d, r8d; lpReserved
0x180032010  lea     rax, [rsp+8A0h+Data]
0x180032015  mov     [rsp+8A0h+cbData], 4
0x18003201d  mov     [rsp+8A0h+phkResult], rax; lpData
0x180032022  call    cs:__imp_RegQueryValueExW
0x180032028  mov     ebx, eax
0x18003202a  test    eax, eax
0x18003202c  jnz     loc_18003210F
0x180032032  cmp     [rsp+8A0h+Type], 4
0x180032037  jnz     loc_18003213F
0x18003203d  test    cs:byte_1800AA941, 4
0x180032044  jz      loc_1800320FE
0x18003204a  mov     rdx, [rdi+30h]
0x18003204e  mov     word ptr [rbp+7A0h+var_820], ax
0x180032052  mov     word ptr [rsp+8A0h+var_848], ax
0x180032057  test    rdx, rdx
0x18003205a  jz      short loc_180032070
0x18003205c  mov     rdx, [rdx+70h]
0x180032060  test    rdx, rdx
0x180032063  jz      short loc_180032070
0x180032065  cmp     [rdx+10h], rax
0x180032069  jz      short loc_180032070
0x18003206b  mov     edx, [rdx+10h]
0x18003206e  jmp     short loc_180032073
0x180032070  or      edx, 0FFFFFFFFh
0x180032073  lea     rcx, [rsp+8A0h+var_848]
0x180032078  call    ConvertPortNoToString
0x18003207d  mov     r8d, dword ptr [rsp+8A0h+Data]
0x180032082  lea     rdx, aIscertsubjectn; "IsCertSubjectNameCheckDisabled: Disable"...
0x180032089  lea     rcx, [rbp+7A0h+var_820]
0x18003208d  call    FormatRRASErrorString
0x180032092  test    cs:byte_1800AA941, 4
0x180032099  jz      short loc_1800320FE
0x18003209b  mov     rcx, [rdi+30h]
0x18003209f  lea     rax, [rcx+70h]
0x1800320a3  test    rcx, rcx
0x1800320a6  jz      short loc_1800320D1
0x1800320a8  mov     rdx, [rax]
0x1800320ab  test    rdx, rdx
0x1800320ae  jz      short loc_1800320B9
0x1800320b0  lea     rcx, [rdx+0A7Eh]
0x1800320b7  jmp     short loc_1800320C0
0x1800320b9  test    rcx, rcx
0x1800320bc  jz      short loc_1800320D1
0x1800320be  xor     ecx, ecx
0x1800320c0  mov     rdx, [rax]
0x1800320c3  test    rdx, rdx
0x1800320c6  jz      short loc_1800320D3
0x1800320c8  lea     r9, [rdx+848h]
0x1800320cf  jmp     short loc_1800320D8
0x1800320d1  xor     ecx, ecx
0x1800320d3  lea     r9, [rsp+8A0h+var_858]
0x1800320d8  lea     rax, [rsp+8A0h+var_848]
0x1800320dd  mov     [rsp+8A0h+lpcbData], rax
0x1800320e2  lea     r8, [rbp+7A0h+var_820]
0x1800320e6  mov     [rsp+8A0h+phkResult], rcx
0x1800320eb  lea     rdx, RasVpnIkeParamTraceError
0x1800320f2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800320f9  call    McTemplateU0zjzz_EventWriteTransfer
0x1800320fe  xor     eax, eax
0x180032100  cmp     dword ptr [rsp+8A0h+Data], 1
0x180032105  setz    al
0x180032108  mov     [rsi], eax
0x18003210a  jmp     loc_180032207
0x18003210f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032116  cmp     rcx, r13
0x180032119  jz      short loc_180032146
0x18003211b  test    byte ptr [rcx+1Ch], 1
0x18003211f  jz      short loc_180032146
0x180032121  cmp     byte ptr [rcx+19h], 2
0x180032125  jb      short loc_180032146
0x180032127  mov     rcx, [rcx+10h]
0x18003212b  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180032132  mov     edx, 0ADh
0x180032137  mov     r9d, ebx
0x18003213a  call    WPP_SF_d
0x18003213f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032146  test    cs:byte_1800AA941, 4
0x18003214d  jz      loc_18003220E
0x180032153  mov     rdx, [rdi+30h]
0x180032157  xor     eax, eax
0x180032159  mov     word ptr [rbp+7A0h+var_820], ax
0x18003215d  mov     word ptr [rsp+8A0h+var_848], ax
0x180032162  test    rdx, rdx
0x180032165  jz      short loc_18003217B
0x180032167  mov     rdx, [rdx+70h]
0x18003216b  test    rdx, rdx
0x18003216e  jz      short loc_18003217B
0x180032170  cmp     [rdx+10h], rax
0x180032174  jz      short loc_18003217B
0x180032176  mov     edx, [rdx+10h]
0x180032179  jmp     short loc_18003217E
0x18003217b  or      edx, 0FFFFFFFFh
0x18003217e  lea     rcx, [rsp+8A0h+var_848]
0x180032183  call    ConvertPortNoToString
0x180032188  mov     r8d, ebx
0x18003218b  lea     rdx, aIscertsubjectn_0; "IsCertSubjectNameCheckDisabled failed: "...
0x180032192  lea     rcx, [rbp+7A0h+var_820]
0x180032196  call    FormatRRASErrorString
0x18003219b  test    cs:byte_1800AA941, 4
0x1800321a2  jz      short loc_180032207
0x1800321a4  mov     rcx, [rdi+30h]
0x1800321a8  lea     rax, [rcx+70h]
0x1800321ac  test    rcx, rcx
0x1800321af  jz      short loc_1800321DA
0x1800321b1  mov     rdx, [rax]
0x1800321b4  test    rdx, rdx
0x1800321b7  jz      short loc_1800321C2
0x1800321b9  lea     rcx, [rdx+0A7Eh]
0x1800321c0  jmp     short loc_1800321C9
0x1800321c2  test    rcx, rcx
0x1800321c5  jz      short loc_1800321DA
0x1800321c7  xor     ecx, ecx
0x1800321c9  mov     rdx, [rax]
0x1800321cc  test    rdx, rdx
0x1800321cf  jz      short loc_1800321DC
0x1800321d1  lea     r9, [rdx+848h]
0x1800321d8  jmp     short loc_1800321E1
0x1800321da  xor     ecx, ecx
0x1800321dc  lea     r9, [rsp+8A0h+var_858]
0x1800321e1  lea     rax, [rsp+8A0h+var_848]
0x1800321e6  mov     [rsp+8A0h+lpcbData], rax
0x1800321eb  lea     r8, [rbp+7A0h+var_820]
0x1800321ef  mov     [rsp+8A0h+phkResult], rcx
0x1800321f4  lea     rdx, RasVpnIkeParamTraceError
0x1800321fb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180032202  call    McTemplateU0zjzz_EventWriteTransfer
0x180032207  mov     rcx, cs:WPP_GLOBAL_Control
0x18003220e  mov     rax, [rsp+8A0h+hKey]
0x180032213  test    rax, rax
0x180032216  jz      short loc_18003225A
0x180032218  mov     rcx, rax; hKey
0x18003221b  call    cs:__imp_RegCloseKey
0x180032221  jmp     short loc_180032253
0x180032223  mov     rcx, cs:WPP_GLOBAL_Control
0x18003222a  cmp     rcx, r13
0x18003222d  jz      short loc_180032283
0x18003222f  test    byte ptr [rcx+1Ch], 1
0x180032233  jz      short loc_18003225A
0x180032235  cmp     byte ptr [rcx+19h], 2
0x180032239  jb      short loc_18003225A
0x18003223b  mov     rcx, [rcx+10h]
0x18003223f  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180032246  mov     edx, 0AEh
0x18003224b  mov     r9d, eax
0x18003224e  call    WPP_SF_d
0x180032253  mov     rcx, cs:WPP_GLOBAL_Control
0x18003225a  cmp     rcx, r13
0x18003225d  jz      short loc_180032283
0x18003225f  test    byte ptr [rcx+1Ch], 1
0x180032263  jz      short loc_180032283
0x180032265  cmp     byte ptr [rcx+19h], 6
0x180032269  jb      short loc_180032283
0x18003226b  mov     rcx, [rcx+10h]
0x18003226f  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180032276  mov     edx, 0AFh
0x18003227b  mov     r9d, ebx
0x18003227e  call    WPP_SF_d
0x180032283  mov     eax, ebx
0x180032285  mov     rcx, [rbp+7A0h+var_20]
0x18003228c  xor     rcx, rsp; StackCookie
0x18003228f  call    __security_check_cookie
0x180032294  lea     r11, [rsp+8A0h+var_10]
0x18003229c  mov     rbx, [r11+30h]
0x1800322a0  mov     rsi, [r11+38h]
0x1800322a4  mov     rsp, r11
0x1800322a7  pop     r13
0x1800322a9  pop     rdi
0x1800322aa  pop     rbp
0x1800322ab  retn
```
