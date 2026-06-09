# UWFUpdateAgent::install(IUpdateCollection *)

- ea: `0x180004a70`
- end: `0x180004f48`
- name: `?install@UWFUpdateAgent@@AEAAJPEAUIUpdateCollection@@@Z`
- size: `1240`
- prototype: `__int64 __fastcall(UWFUpdateAgent *__hidden this, struct IUpdateCollection *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18000399c`

## callees

- `0x180002570`
- `0x180002a20`
- `0x180004a70`
- `0x180004f50`
- `0x180005175`
- `0x1800051a0`
- `0x180006010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180004e19`
- `msvcrt!wcscat_s` at `0x180004e30`
- `msvcrt!wcscat_s` at `0x180004e19`
- `msvcrt!wcscat_s` at `0x180004e30`
- `msvcrt!swprintf_s` at `0x180004dd3`
- `msvcrt!swprintf_s` at `0x180004dd3`

## string_xrefs

- `0x180004ad4`: `Install failure`
- `0x180004ea3`: `Install failure`
- `0x180004ed7`: `UpdateInstaller instance failure`
- `0x180004eb1`: `UpdateInstaller2 instance failure`
- `0x180004b8b`: `Install: Failed to copy updates`
- `0x180004bb3`: `Install: Failed to set source prompts`
- `0x180004bfe`: `Install: Failed to get reboot required flag`
- `0x180004c57`: `Install: Memory allocation failure`
- `0x180004e9a`: `Install: Failed to get update install result`
- `0x180004e91`: `Install: Failed to get install result code`
- `0x180004e83`: `Install: Failed to get reboot flag`
- `0x180004e77`: `Install: Failed to get update item`
- `0x180004dc0`: `Installing Update `
- `0x180004e6b`: `Install: Failed to print title`

## pseudocode

```c
__int64 __fastcall UWFUpdateAgent::install(UWFUpdateAgent *this, struct IUpdateCollection *a2)
{
  struct IUpdateCollectionVtbl *lpVtbl; // rax
  int v5; // eax
  int v6; // edi
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  const wchar_t *v11; // r9
  __int64 v12; // r8
  unsigned __int64 v13; // rax
  unsigned int v14; // r14d
  int v15; // eax
  void (*v16)(void); // rax
  unsigned int v17; // eax
  UWFUpdateAgent *v18; // rcx
  int v19; // r9d
  void (*Release)(void); // rax
  __int64 v21; // r8
  unsigned int v22; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v23; // [rsp+24h] [rbp-DCh] BYREF
  _WORD v24[2]; // [rsp+28h] [rbp-D8h] BYREF
  int v25; // [rsp+2Ch] [rbp-D4h] BYREF
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  struct IUpdate *v27; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Destination[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v32[508]; // [rsp+64h] [rbp-9Ch] BYREF
  wchar_t Buffer[2]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v34[508]; // [rsp+264h] [rbp+164h] BYREF

  lpVtbl = a2->lpVtbl;
  v25 = 0;
  v5 = ((__int64 (__fastcall *)(struct IUpdateCollection *, int *))lpVtbl->get_Count)(a2, &v25);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( !v25 )
      return 0;
    v8 = *((_QWORD *)this + 1);
    v26 = 0;
    v29 = 0;
    v30 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 112LL))(v8, &v29);
    v6 = v9;
    if ( v9 < 0 || !v29 )
    {
      v11 = L"UpdateInstaller instance failure";
      goto LABEL_50;
    }
    v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v29)(v29, &IID_IUpdateInstaller2, &v26);
    v6 = v10;
    if ( v10 >= 0 && v26 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      v9 = (*(__int64 (__fastcall **)(__int64, struct IUpdateCollection *))(*(_QWORD *)v26 + 128LL))(v26, a2);
      v6 = v9;
      if ( v9 < 0 )
      {
        v11 = L"Install: Failed to copy updates";
LABEL_50:
        v12 = (unsigned int)v9;
        goto LABEL_51;
      }
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 208LL))(v26, 0);
      v6 = v9;
      if ( v9 < 0 )
      {
        v11 = L"Install: Failed to set source prompts";
        goto LABEL_50;
      }
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 232LL))(v26, 0xFFFFFFFFLL);
      v23 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v26 + 216LL))(v26, &v23);
      if ( v6 < 0 )
      {
        v11 = L"Install: Failed to get reboot required flag";
LABEL_15:
        v12 = (unsigned int)v6;
LABEL_51:
        UwfServicingLog(1, 1, v12, v11);
        goto LABEL_52;
      }
      if ( v23 )
      {
        *(_DWORD *)(*((_QWORD *)this + 2) + 16LL) = 1;
      }
      else
      {
        v13 = 4LL * v25;
        if ( !is_mul_ok(v25, 4u) )
          v13 = -1;
        *(_QWORD *)(*((_QWORD *)this + 2) + 32LL) = operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
        if ( !*(_QWORD *)(*((_QWORD *)this + 2) + 32LL) )
        {
          v11 = L"Install: Memory allocation failure";
          goto LABEL_15;
        }
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 168LL))(v26, &v30);
        v6 = v9;
        if ( v9 < 0 )
        {
          v11 = L"Install failure";
          goto LABEL_50;
        }
        v14 = 0;
        if ( v25 > 0 )
        {
          while ( 1 )
          {
            v24[0] = 0;
            v28 = 0;
            v22 = 0;
            v27 = 0;
            v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 80LL))(v30, v14, &v28);
            v6 = v15;
            if ( v15 < 0 || !v28 )
              break;
            v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 72LL))(v28, &v22);
            v16 = *(void (**)(void))(*(_QWORD *)v28 + 16LL);
            if ( v6 < 0 )
            {
              v16();
              v11 = L"Install: Failed to get install result code";
              goto LABEL_41;
            }
            v16();
            v15 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v30 + 64LL))(v30, v24);
            v6 = v15;
            if ( v15 < 0 )
            {
              v11 = L"Install: Failed to get reboot flag";
              goto LABEL_43;
            }
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 32LL) + 4LL * (int)v14) = v22;
            v17 = v22;
            if ( v22 == 2 )
            {
              ++*(_DWORD *)(*((_QWORD *)this + 2) + 12LL);
              v17 = v22;
            }
            if ( v24[0] && v17 == 2 )
              *(_DWORD *)(*((_QWORD *)this + 2) + 20LL) = 1;
            v15 = ((__int64 (__fastcall *)(struct IUpdateCollection *, _QWORD, struct IUpdate **))a2->lpVtbl->get_Item)(
                    a2,
                    v14,
                    &v27);
            v6 = v15;
            if ( v15 < 0 || !v27 )
            {
              v11 = L"Install: Failed to get update item";
              goto LABEL_43;
            }
            *(_DWORD *)Destination = 0;
            memset_0(v32, 0, sizeof(v32));
            *(_DWORD *)Buffer = 0;
            memset_0(v34, 0, sizeof(v34));
            swprintf_s(Buffer, 0x100u, L"Installing Update ");
            v6 = UWFUpdateAgent::printTitleAndKBNumber(v18, v27, Destination, v19);
            Release = (void (*)(void))v27->lpVtbl->Release;
            if ( v6 < 0 )
            {
              Release();
              v11 = L"Install: Failed to print title";
LABEL_41:
              v12 = (unsigned int)v6;
              goto LABEL_51;
            }
            Release();
            wcscat_s(Destination, 0x100u, (const wchar_t *)(&OperationResultStrings)[v22]);
            wcscat_s(Buffer, 0x100u, Destination);
            v21 = v22;
            if ( v22 == 2 )
              v21 = 0;
            UwfServicingLog(1, 0, v21, Buffer);
            if ( (int)++v14 >= v25 )
              goto LABEL_52;
          }
          v11 = L"Install: Failed to get update install result";
LABEL_43:
          v12 = (unsigned int)v15;
          goto LABEL_51;
        }
      }
    }
    else
    {
      UwfServicingLog(1, 1, (unsigned int)v10, L"UpdateInstaller2 instance failure");
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
LABEL_52:
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    return (unsigned int)v6;
  }
  UwfServicingLog(1, 1, (unsigned int)v5, L"Install failure");
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004a70  mov     [rsp-8+arg_10], rbx
0x180004a75  mov     [rsp-8+arg_18], rsi
0x180004a7a  push    rbp
0x180004a7b  push    rdi
0x180004a7c  push    r12
0x180004a7e  push    r14
0x180004a80  push    r15
0x180004a82  lea     rbp, [rsp-370h]
0x180004a8a  sub     rsp, 470h
0x180004a91  mov     rax, cs:__security_cookie
0x180004a98  xor     rax, rsp
0x180004a9b  mov     [rbp+390h+var_30], rax
0x180004aa2  mov     rax, [rdx]
0x180004aa5  mov     r15, rdx
0x180004aa8  mov     rsi, rcx
0x180004aab  lea     rdx, [rsp+490h+var_464]
0x180004ab0  xor     r12d, r12d
0x180004ab3  mov     rcx, r15
0x180004ab6  mov     [rsp+490h+var_464], r12d
0x180004abb  mov     rax, [rax+50h]
0x180004abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ac4  mov     edi, eax
0x180004ac6  test    eax, eax
0x180004ac8  jns     short loc_180004AE7
0x180004aca  lea     ebx, [r12+1]
0x180004acf  mov     r8d, eax
0x180004ad2  mov     edx, ebx
0x180004ad4  lea     r9, aInstallFailure; "Install failure"
0x180004adb  mov     ecx, ebx
0x180004add  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180004ae2  jmp     loc_180004F1B
0x180004ae7  cmp     [rsp+490h+var_464], r12d
0x180004aec  jnz     short loc_180004AF5
0x180004aee  xor     eax, eax
0x180004af0  jmp     loc_180004F1D
0x180004af5  mov     rcx, [rsi+8]
0x180004af9  lea     rdx, [rsp+490h+var_448]
0x180004afe  mov     [rsp+490h+var_460], r12
0x180004b03  mov     [rsp+490h+var_448], r12
0x180004b08  mov     [rsp+490h+var_440], r12
0x180004b0d  mov     rax, [rcx]
0x180004b10  mov     rax, [rax+70h]
0x180004b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b19  mov     edi, eax
0x180004b1b  test    eax, eax
0x180004b1d  js      loc_180004ED7
0x180004b23  mov     rcx, [rsp+490h+var_448]
0x180004b28  test    rcx, rcx
0x180004b2b  jz      loc_180004ED7
0x180004b31  mov     rax, [rcx]
0x180004b34  lea     r8, [rsp+490h+var_460]
0x180004b39  lea     rdx, IID_IUpdateInstaller2
0x180004b40  mov     rax, [rax]
0x180004b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b48  mov     edi, eax
0x180004b4a  test    eax, eax
0x180004b4c  js      loc_180004EAC
0x180004b52  cmp     [rsp+490h+var_460], r12
0x180004b57  jz      loc_180004EAC
0x180004b5d  mov     rcx, [rsp+490h+var_448]
0x180004b62  mov     rax, [rcx]
0x180004b65  mov     rax, [rax+10h]
0x180004b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b6e  mov     rcx, [rsp+490h+var_460]
0x180004b73  mov     rdx, r15
0x180004b76  mov     rax, [rcx]
0x180004b79  mov     rax, [rax+80h]
0x180004b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b85  mov     edi, eax
0x180004b87  test    eax, eax
0x180004b89  jns     short loc_180004B97
0x180004b8b  lea     r9, aInstallFailedT_1; "Install: Failed to copy updates"
0x180004b92  jmp     loc_180004EDE
0x180004b97  mov     rcx, [rsp+490h+var_460]
0x180004b9c  xor     edx, edx
0x180004b9e  mov     rax, [rcx]
0x180004ba1  mov     rax, [rax+0D0h]
0x180004ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bad  mov     edi, eax
0x180004baf  test    eax, eax
0x180004bb1  jns     short loc_180004BBF
0x180004bb3  lea     r9, aInstallFailedT_3; "Install: Failed to set source prompts"
0x180004bba  jmp     loc_180004EDE
0x180004bbf  mov     rcx, [rsp+490h+var_460]
0x180004bc4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004bc8  mov     edx, ebx
0x180004bca  mov     rax, [rcx]
0x180004bcd  mov     rax, [rax+0E8h]
0x180004bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bd9  mov     rcx, [rsp+490h+var_460]
0x180004bde  lea     rdx, [rsp+490h+var_46C]
0x180004be3  mov     [rsp+490h+var_46C], r12w
0x180004be9  mov     rax, [rcx]
0x180004bec  mov     rax, [rax+0D8h]
0x180004bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bf8  mov     edi, eax
0x180004bfa  test    eax, eax
0x180004bfc  jns     short loc_180004C0D
0x180004bfe  lea     r9, aInstallFailedT_5; "Install: Failed to get reboot required "...
0x180004c05  mov     r8d, edi
0x180004c08  jmp     loc_180004EE1
0x180004c0d  cmp     [rsp+490h+var_46C], r12w
0x180004c13  jz      short loc_180004C25
0x180004c15  mov     rax, [rsi+10h]
0x180004c19  mov     dword ptr [rax+10h], 1
0x180004c20  jmp     loc_180004EEF
0x180004c25  movsxd  rcx, [rsp+490h+var_464]
0x180004c2a  mov     eax, 4
0x180004c2f  mul     rcx
0x180004c32  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004c39  cmovb   rax, rbx
0x180004c3d  mov     rcx, rax; unsigned __int64
0x180004c40  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004c45  mov     rcx, [rsi+10h]
0x180004c49  mov     [rcx+20h], rax
0x180004c4d  mov     rax, [rsi+10h]
0x180004c51  cmp     [rax+20h], r12
0x180004c55  jnz     short loc_180004C60
0x180004c57  lea     r9, aInstallMemoryA; "Install: Memory allocation failure"
0x180004c5e  jmp     short loc_180004C05
0x180004c60  mov     rcx, [rsp+490h+var_460]
0x180004c65  lea     rdx, [rsp+490h+var_440]
0x180004c6a  mov     rax, [rcx]
0x180004c6d  mov     rax, [rax+0A8h]
0x180004c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c79  mov     edi, eax
0x180004c7b  test    eax, eax
0x180004c7d  js      loc_180004EA3
0x180004c83  mov     r14d, r12d
0x180004c86  cmp     [rsp+490h+var_464], r12d
0x180004c8b  jle     loc_180004EEF
0x180004c91  mov     ebx, 1
0x180004c96  mov     rcx, [rsp+490h+var_440]
0x180004c9b  lea     r8, [rsp+490h+var_450]
0x180004ca0  mov     [rsp+490h+var_468], r12w
0x180004ca6  mov     edx, r14d
0x180004ca9  mov     [rsp+490h+var_450], r12
0x180004cae  mov     [rsp+490h+var_470], r12d
0x180004cb3  mov     [rsp+490h+var_458], r12
0x180004cb8  mov     rax, [rcx]
0x180004cbb  mov     rax, [rax+50h]
0x180004cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc4  mov     edi, eax
0x180004cc6  test    eax, eax
0x180004cc8  js      loc_180004E9A
0x180004cce  mov     rcx, [rsp+490h+var_450]
0x180004cd3  test    rcx, rcx
0x180004cd6  jz      loc_180004E9A
0x180004cdc  mov     rax, [rcx]
0x180004cdf  lea     rdx, [rsp+490h+var_470]
0x180004ce4  mov     rax, [rax+48h]
0x180004ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ced  mov     rcx, [rsp+490h+var_450]
0x180004cf2  mov     edi, eax
0x180004cf4  test    eax, eax
0x180004cf6  mov     rax, [rcx]
0x180004cf9  mov     rax, [rax+10h]
0x180004cfd  js      loc_180004E8C
0x180004d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d08  mov     rcx, [rsp+490h+var_440]
0x180004d0d  lea     rdx, [rsp+490h+var_468]
0x180004d12  mov     rax, [rcx]
0x180004d15  mov     rax, [rax+40h]
0x180004d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d1e  mov     edi, eax
0x180004d20  test    eax, eax
0x180004d22  js      loc_180004E83
0x180004d28  mov     rax, [rsi+10h]
0x180004d2c  movsxd  rdx, r14d
0x180004d2f  mov     rcx, [rax+20h]
0x180004d33  mov     eax, [rsp+490h+var_470]
0x180004d37  mov     [rcx+rdx*4], eax
0x180004d3a  mov     eax, [rsp+490h+var_470]
0x180004d3e  cmp     eax, 2
0x180004d41  jnz     short loc_180004D4E
0x180004d43  mov     rax, [rsi+10h]
0x180004d47  add     [rax+0Ch], ebx
0x180004d4a  mov     eax, [rsp+490h+var_470]
0x180004d4e  cmp     [rsp+490h+var_468], r12w
0x180004d54  jz      short loc_180004D62
0x180004d56  cmp     eax, 2
0x180004d59  jnz     short loc_180004D62
0x180004d5b  mov     rax, [rsi+10h]
0x180004d5f  mov     [rax+14h], ebx
0x180004d62  mov     rax, [r15]
0x180004d65  lea     r8, [rsp+490h+var_458]
0x180004d6a  mov     edx, r14d
0x180004d6d  mov     rcx, r15
0x180004d70  mov     rax, [rax+38h]
0x180004d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d79  mov     edi, eax
0x180004d7b  test    eax, eax
0x180004d7d  js      loc_180004E77
0x180004d83  cmp     [rsp+490h+var_458], r12
0x180004d88  jz      loc_180004E77
0x180004d8e  xor     edx, edx; Val
0x180004d90  mov     dword ptr [rsp+490h+Destination], r12d
0x180004d95  mov     r8d, 1FCh; Size
0x180004d9b  lea     rcx, [rsp+490h+var_42C]; void *
0x180004da0  call    memset_0
0x180004da5  xor     edx, edx; Val
0x180004da7  mov     dword ptr [rbp+390h+Buffer], r12d
0x180004dae  mov     r8d, 1FCh; Size
0x180004db4  lea     rcx, [rbp+390h+var_22C]; void *
0x180004dbb  call    memset_0
0x180004dc0  lea     r8, aInstallingUpda; "Installing Update "
0x180004dc7  mov     edx, 100h; BufferCount
0x180004dcc  lea     rcx, [rbp+390h+Buffer]; Buffer
0x180004dd3  call    cs:__imp_swprintf_s
0x180004dd9  mov     rdx, [rsp+490h+var_458]; struct IUpdate *
0x180004dde  lea     r8, [rsp+490h+Destination]; unsigned __int16 *
0x180004de3  call    ?printTitleAndKBNumber@UWFUpdateAgent@@AEAAJPEAUIUpdate@@PEAGJ@Z; UWFUpdateAgent::printTitleAndKBNumber(IUpdate *,ushort *,long)
0x180004de8  mov     rcx, [rsp+490h+var_458]
0x180004ded  mov     edi, eax
0x180004def  test    eax, eax
0x180004df1  mov     rax, [rcx]
0x180004df4  mov     rax, [rax+10h]
0x180004df8  js      short loc_180004E66
0x180004dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dff  movsxd  r8, [rsp+490h+var_470]
0x180004e04  lea     rax, ?OperationResultStrings@@3PAPEBGA; ushort const * near * OperationResultStrings
0x180004e0b  mov     edx, 100h; SizeInWords
0x180004e10  lea     rcx, [rsp+490h+Destination]; Destination
0x180004e15  mov     r8, [rax+r8*8]; Source
0x180004e19  call    cs:__imp_wcscat_s
0x180004e1f  lea     r8, [rsp+490h+Destination]; Source
0x180004e24  mov     edx, 100h; SizeInWords
0x180004e29  lea     rcx, [rbp+390h+Buffer]; Destination
0x180004e30  call    cs:__imp_wcscat_s
0x180004e36  mov     r8d, [rsp+490h+var_470]
0x180004e3b  lea     r9, [rbp+390h+Buffer]
0x180004e42  cmp     r8d, 2
0x180004e46  mov     ecx, ebx
0x180004e48  cmovz   r8d, r12d
0x180004e4c  xor     edx, edx
0x180004e4e  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180004e53  add     r14d, ebx
0x180004e56  cmp     r14d, [rsp+490h+var_464]
0x180004e5b  jl      loc_180004C96
0x180004e61  jmp     loc_180004EEF
0x180004e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e6b  lea     r9, aInstallFailedT_4; "Install: Failed to print title"
0x180004e72  mov     r8d, edi
0x180004e75  jmp     short loc_180004EE6
0x180004e77  lea     r9, aInstallFailedT; "Install: Failed to get update item"
0x180004e7e  mov     r8d, eax
0x180004e81  jmp     short loc_180004EE6
0x180004e83  lea     r9, aInstallFailedT_2; "Install: Failed to get reboot flag"
0x180004e8a  jmp     short loc_180004E7E
0x180004e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e91  lea     r9, aInstallFailedT_0; "Install: Failed to get install result c"...
0x180004e98  jmp     short loc_180004E72
0x180004e9a  lea     r9, aInstallFailedT_6; "Install: Failed to get update install r"...
0x180004ea1  jmp     short loc_180004E7E
0x180004ea3  lea     r9, aInstallFailure; "Install failure"
0x180004eaa  jmp     short loc_180004EDE
0x180004eac  mov     ebx, 1
0x180004eb1  lea     r9, aUpdateinstalle_0; "UpdateInstaller2 instance failure"
0x180004eb8  mov     edx, ebx
0x180004eba  mov     ecx, ebx
0x180004ebc  mov     r8d, eax
0x180004ebf  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180004ec4  mov     rcx, [rsp+490h+var_448]
0x180004ec9  mov     rax, [rcx]
0x180004ecc  mov     rax, [rax+10h]
0x180004ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ed5  jmp     short loc_180004EEF
0x180004ed7  lea     r9, aUpdateinstalle; "UpdateInstaller instance failure"
0x180004ede  mov     r8d, eax
0x180004ee1  mov     ebx, 1
0x180004ee6  mov     edx, ebx
0x180004ee8  mov     ecx, ebx
0x180004eea  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x180004eef  mov     rcx, [rsp+490h+var_440]
0x180004ef4  test    rcx, rcx
0x180004ef7  jz      short loc_180004F05
0x180004ef9  mov     rax, [rcx]
0x180004efc  mov     rax, [rax+10h]
0x180004f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f05  mov     rcx, [rsp+490h+var_460]
0x180004f0a  test    rcx, rcx
0x180004f0d  jz      short loc_180004F1B
0x180004f0f  mov     rax, [rcx]
0x180004f12  mov     rax, [rax+10h]
0x180004f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f1b  mov     eax, edi
0x180004f1d  mov     rcx, [rbp+390h+var_30]
0x180004f24  xor     rcx, rsp; StackCookie
0x180004f27  call    __security_check_cookie
0x180004f2c  lea     r11, [rsp+490h+var_20]
0x180004f34  mov     rbx, [r11+40h]
0x180004f38  mov     rsi, [r11+48h]
0x180004f3c  mov     rsp, r11
0x180004f3f  pop     r15
0x180004f41  pop     r14
0x180004f43  pop     r12
0x180004f45  pop     rdi
0x180004f46  pop     rbp
0x180004f47  retn
```
