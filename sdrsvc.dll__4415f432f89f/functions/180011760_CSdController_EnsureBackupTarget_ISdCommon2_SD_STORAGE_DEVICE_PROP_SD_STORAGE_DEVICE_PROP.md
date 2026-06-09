# CSdController::_EnsureBackupTarget(ISdCommon2 *,_SD_STORAGE_DEVICE_PROP *,_SD_STORAGE_DEVICE_PROP *)

- ea: `0x180011760`
- end: `0x180011995`
- name: `?_EnsureBackupTarget@CSdController@@AEAAJPEAUISdCommon2@@PEAU_SD_STORAGE_DEVICE_PROP@@1@Z`
- size: `565`
- prototype: `__int64 __fastcall(HANDLE *this, struct ISdCommon2 *, const unsigned __int16 **, struct _SD_STORAGE_DEVICE_PROP *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012948`

## callees

- `0x180011760`
- `0x18001199c`
- `0x18001445c`
- `0x18001586c`
- `0x180015974`
- `0x180015fc4`
- `0x1800171f4`
- `0x18002170a`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011967`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001196f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011967`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001196f`

## pseudocode

```c
__int64 __fastcall CSdController::_EnsureBackupTarget(
        HANDLE *this,
        struct ISdCommon2 *a2,
        const unsigned __int16 **a3,
        struct _SD_STORAGE_DEVICE_PROP *a4)
{
  __int64 v8; // rcx
  struct _SD_STORAGE_DEVICE_PROP *v9; // rax
  __int16 v10; // ax
  __int64 v11; // rax
  int v12; // eax
  CSdController *v13; // rcx
  bool v14; // sf
  int IsPathUNC; // ecx
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  unsigned int v24; // ebx
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v27; // [rsp+34h] [rbp-CCh]
  __int16 v28; // [rsp+36h] [rbp-CAh]
  _OWORD v29[7]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v30; // [rsp+E0h] [rbp-20h]
  __int128 v31; // [rsp+F0h] [rbp-10h]
  unsigned int v32; // [rsp+148h] [rbp+48h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v26, "CSdController::_EnsureBackupTarget", 0x6A3u, 0);
  memset_0(v29, 0, 0x90u);
  v32 = 0;
  if ( a4 )
  {
    v8 = 144;
    v9 = a4;
    do
    {
      *(_BYTE *)v9 = 0;
      v9 = (struct _SD_STORAGE_DEVICE_PROP *)((char *)v9 + 1);
      --v8;
    }
    while ( v8 );
  }
  v10 = 1707;
  if ( a2 && (v27 = 1707, v10 = 1708, a3) && (v27 = 1708, v10 = 1709, a4) )
  {
    v27 = 1709;
    v11 = *(_QWORD *)a2;
    v26 = 0;
    v12 = (*(__int64 (__fastcall **)(struct ISdCommon2 *, const unsigned __int16 **, _OWORD *))(v11 + 128))(a2, a3, v29);
    v13 = (CSdController *)(unsigned int)v12;
    v26 = v12;
    v14 = v12 < 0;
    v10 = 1715;
    if ( !v14 )
    {
      v27 = 1715;
      v10 = 1716;
      if ( (_DWORD)v13 )
      {
        v26 = -2130706426;
      }
      else
      {
        v26 = 0;
        v27 = 1716;
        v26 = CSdController::_EnsureTargetNotBlockedByGP(v13, (struct _SD_STORAGE_DEVICE_PROP *)v29);
        v10 = 1723;
        if ( v26 >= 0 )
        {
          v27 = 1723;
          if ( HIDWORD(v30) )
          {
            v26 = -2130706424;
            v10 = 1732;
          }
          else
          {
            IsPathUNC = SdIsPathUNC(a3[1]);
            v26 = IsPathUNC;
            v10 = 1740;
            if ( IsPathUNC >= 0 )
            {
              v27 = 1740;
              if ( !IsPathUNC )
              {
                CleanupStorageDeviceProp((struct _SD_STORAGE_DEVICE_PROP *)v29);
                v26 = CSdController::_VerifyDeviceWithCreds(
                        a3[1],
                        this[19],
                        0,
                        (struct _SD_STORAGE_DEVICE_PROP *)v29,
                        &v32);
                v10 = 1746;
                if ( v26 < 0 )
                  goto LABEL_6;
                v27 = 1746;
              }
              v16 = v29[1];
              *(_OWORD *)a4 = v29[0];
              v17 = v29[2];
              *((_OWORD *)a4 + 1) = v16;
              v18 = v29[3];
              *((_OWORD *)a4 + 2) = v17;
              v19 = v29[4];
              *((_OWORD *)a4 + 3) = v18;
              v20 = v29[5];
              *((_OWORD *)a4 + 4) = v19;
              v21 = v29[6];
              *((_OWORD *)a4 + 5) = v20;
              v22 = v30;
              *((_OWORD *)a4 + 6) = v21;
              v23 = v31;
              *((_OWORD *)a4 + 7) = v22;
              *((_OWORD *)a4 + 8) = v23;
              memset_0(v29, 0, 0x90u);
              goto LABEL_20;
            }
          }
        }
      }
    }
  }
  else
  {
    v26 = -2147024809;
  }
LABEL_6:
  v28 = v10;
LABEL_20:
  CleanupStorageDeviceProp((struct _SD_STORAGE_DEVICE_PROP *)v29);
  CoTaskMemFree(0);
  CoTaskMemFree(0);
  v24 = v26;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v26);
  return v24;
}

```

## disassembly

```asm
0x180011760  push    rbp
0x180011762  push    rbx
0x180011763  push    rsi
0x180011764  push    rdi
0x180011765  push    r12
0x180011767  push    r14
0x180011769  lea     rbp, [rsp-8]
0x18001176e  sub     rsp, 108h
0x180011775  mov     rbx, r9
0x180011778  mov     rdi, r8
0x18001177b  mov     rsi, rdx
0x18001177e  mov     r14, rcx
0x180011781  xor     r9d, r9d; unsigned __int16
0x180011784  lea     rdx, aCsdcontrollerE; "CSdController::_EnsureBackupTarget"
0x18001178b  mov     r8d, 6A3h; unsigned __int16
0x180011791  lea     rcx, [rsp+130h+var_100]; this
0x180011796  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001179b  mov     r12d, 90h
0x1800117a1  lea     rcx, [rsp+130h+var_C0]; void *
0x1800117a6  mov     r8d, r12d; Size
0x1800117a9  xor     edx, edx; Val
0x1800117ab  call    memset_0
0x1800117b0  mov     [rbp+30h+arg_8], 0
0x1800117b7  test    rbx, rbx
0x1800117ba  jz      short loc_1800117CE
0x1800117bc  mov     ecx, r12d
0x1800117bf  mov     rax, rbx
0x1800117c2  mov     byte ptr [rax], 0
0x1800117c5  inc     rax
0x1800117c8  sub     rcx, 1
0x1800117cc  jnz     short loc_1800117C2
0x1800117ce  mov     eax, 6ABh
0x1800117d3  test    rsi, rsi
0x1800117d6  jnz     short loc_1800117EA
0x1800117d8  mov     [rsp+130h+var_100], 80070057h
0x1800117e0  mov     [rsp+130h+var_FA], ax
0x1800117e5  jmp     loc_18001195B
0x1800117ea  mov     [rsp+130h+var_FC], ax
0x1800117ef  mov     eax, 6ACh
0x1800117f4  test    rdi, rdi
0x1800117f7  jz      short loc_1800117D8
0x1800117f9  mov     [rsp+130h+var_FC], ax
0x1800117fe  mov     eax, 6ADh
0x180011803  test    rbx, rbx
0x180011806  jz      short loc_1800117D8
0x180011808  mov     [rsp+130h+var_FC], ax
0x18001180d  lea     r8, [rsp+130h+var_C0]
0x180011812  mov     rax, [rsi]
0x180011815  mov     rdx, rdi
0x180011818  mov     rcx, rsi
0x18001181b  mov     [rsp+130h+var_100], 0
0x180011823  mov     rax, [rax+80h]
0x18001182a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001182f  mov     ecx, eax; this
0x180011831  mov     [rsp+130h+var_100], eax
0x180011835  test    eax, eax
0x180011837  mov     eax, 6B3h
0x18001183c  js      short loc_1800117E0
0x18001183e  mov     [rsp+130h+var_FC], ax
0x180011843  mov     eax, 6B4h
0x180011848  test    ecx, ecx
0x18001184a  jz      short loc_180011856
0x18001184c  mov     [rsp+130h+var_100], 81000006h
0x180011854  jmp     short loc_1800117E0
0x180011856  lea     rdx, [rsp+130h+var_C0]; struct _SD_STORAGE_DEVICE_PROP *
0x18001185b  mov     [rsp+130h+var_100], 0
0x180011863  mov     [rsp+130h+var_FC], ax
0x180011868  call    ?_EnsureTargetNotBlockedByGP@CSdController@@AEAAJPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CSdController::_EnsureTargetNotBlockedByGP(_SD_STORAGE_DEVICE_PROP *)
0x18001186d  mov     [rsp+130h+var_100], eax
0x180011871  test    eax, eax
0x180011873  mov     eax, 6BBh
0x180011878  js      loc_1800117E0
0x18001187e  cmp     [rbp+30h+var_44], 0
0x180011882  mov     [rsp+130h+var_FC], ax
0x180011887  jz      short loc_18001189B
0x180011889  mov     [rsp+130h+var_100], 81000008h
0x180011891  mov     eax, 6C4h
0x180011896  jmp     loc_1800117E0
0x18001189b  mov     rcx, [rdi+8]; unsigned __int16 *
0x18001189f  call    ?SdIsPathUNC@@YAJPEBG@Z; SdIsPathUNC(ushort const *)
0x1800118a4  mov     ecx, eax
0x1800118a6  mov     [rsp+130h+var_100], eax
0x1800118aa  test    eax, eax
0x1800118ac  mov     eax, 6CCh
0x1800118b1  js      loc_1800117E0
0x1800118b7  mov     [rsp+130h+var_FC], ax
0x1800118bc  test    ecx, ecx
0x1800118be  jnz     short loc_180011901
0x1800118c0  lea     rcx, [rsp+130h+var_C0]; struct _SD_STORAGE_DEVICE_PROP *
0x1800118c5  call    ?CleanupStorageDeviceProp@@YAXPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)
0x1800118ca  mov     rdx, [r14+98h]; hToken
0x1800118d1  lea     rax, [rbp+30h+arg_8]
0x1800118d5  mov     rcx, [rdi+8]; unsigned __int16 *
0x1800118d9  lea     r9, [rsp+130h+var_C0]; struct _SD_STORAGE_DEVICE_PROP *
0x1800118de  xor     r8d, r8d; struct _SID *
0x1800118e1  mov     [rsp+130h+var_110], rax; unsigned int *
0x1800118e6  call    ?_VerifyDeviceWithCreds@CSdController@@CAJPEBGPEAXPEAU_SID@@PEAU_SD_STORAGE_DEVICE_PROP@@PEAK@Z; CSdController::_VerifyDeviceWithCreds(ushort const *,void *,_SID *,_SD_STORAGE_DEVICE_PROP *,ulong *)
0x1800118eb  mov     [rsp+130h+var_100], eax
0x1800118ef  test    eax, eax
0x1800118f1  mov     eax, 6D2h
0x1800118f6  js      loc_1800117E0
0x1800118fc  mov     [rsp+130h+var_FC], ax
0x180011901  movaps  xmm0, [rsp+130h+var_C0]
0x180011906  lea     rcx, [rsp+130h+var_C0]; void *
0x18001190b  movaps  xmm1, [rbp+30h+var_B0]
0x18001190f  mov     r8, r12; Size
0x180011912  movups  xmmword ptr [rbx], xmm0
0x180011915  xor     edx, edx; Val
0x180011917  movaps  xmm0, [rbp+30h+var_A0]
0x18001191b  movups  xmmword ptr [rbx+10h], xmm1
0x18001191f  movaps  xmm1, [rbp+30h+var_90]
0x180011923  movups  xmmword ptr [rbx+20h], xmm0
0x180011927  movaps  xmm0, [rbp+30h+var_80]
0x18001192b  movups  xmmword ptr [rbx+30h], xmm1
0x18001192f  movaps  xmm1, [rbp+30h+var_70]
0x180011933  movups  xmmword ptr [rbx+40h], xmm0
0x180011937  movaps  xmm0, [rbp+30h+var_60]
0x18001193b  movups  xmmword ptr [rbx+50h], xmm1
0x18001193f  movaps  xmm1, xmmword ptr [rbp-20h]
0x180011943  movups  xmmword ptr [rbx+60h], xmm0
0x180011947  movaps  xmm0, [rbp+30h+var_40]
0x18001194b  movups  xmmword ptr [rbx+70h], xmm1
0x18001194f  movups  xmmword ptr [rbx+80h], xmm0
0x180011956  call    memset_0
0x18001195b  lea     rcx, [rsp+130h+var_C0]; struct _SD_STORAGE_DEVICE_PROP *
0x180011960  call    ?CleanupStorageDeviceProp@@YAXPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)
0x180011965  xor     ecx, ecx; pv
0x180011967  call    cs:__imp_CoTaskMemFree
0x18001196d  xor     ecx, ecx; pv
0x18001196f  call    cs:__imp_CoTaskMemFree
0x180011975  mov     ebx, [rsp+130h+var_100]
0x180011979  lea     rcx, [rsp+130h+var_100]; this
0x18001197e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180011983  mov     eax, ebx
0x180011985  add     rsp, 108h
0x18001198c  pop     r14
0x18001198e  pop     r12
0x180011990  pop     rdi
0x180011991  pop     rsi
0x180011992  pop     rbx
0x180011993  pop     rbp
0x180011994  retn
```
