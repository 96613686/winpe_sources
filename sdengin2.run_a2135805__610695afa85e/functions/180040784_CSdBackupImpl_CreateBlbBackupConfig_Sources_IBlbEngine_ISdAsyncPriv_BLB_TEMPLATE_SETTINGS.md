# CSdBackupImpl::_CreateBlbBackupConfig_Sources(IBlbEngine *,ISdAsyncPriv *,_BLB_TEMPLATE_SETTINGS *)

- ea: `0x180040784`
- end: `0x180040a4b`
- name: `?_CreateBlbBackupConfig_Sources@CSdBackupImpl@@AEAAJPEAUIBlbEngine@@PEAUISdAsyncPriv@@PEAU_BLB_TEMPLATE_SETTINGS@@@Z`
- size: `711`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this, struct IBlbEngine *, struct ISdAsyncPriv *, struct _BLB_TEMPLATE_SETTINGS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180040404`

## callees

- `0x180040784`
- `0x1800412b0`
- `0x180072e08`
- `0x180072f14`
- `0x18008ee18`
- `0x1800d1010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800409e3`
- `ole32!CoTaskMemFree` at `0x1800409fa`
- `ole32!CoTaskMemFree` at `0x180040a09`
- `ole32!CoTaskMemFree` at `0x180040a17`
- `ole32!CoTaskMemFree` at `0x1800409e3`
- `ole32!CoTaskMemFree` at `0x1800409fa`
- `ole32!CoTaskMemFree` at `0x180040a09`
- `ole32!CoTaskMemFree` at `0x180040a17`
- `ole32!CoTaskMemAlloc` at `0x1800408cf`
- `ole32!CoTaskMemAlloc` at `0x1800408fc`
- `ole32!CoTaskMemAlloc` at `0x180040927`
- `ole32!CoTaskMemAlloc` at `0x1800408cf`
- `ole32!CoTaskMemAlloc` at `0x1800408fc`
- `ole32!CoTaskMemAlloc` at `0x180040927`

## string_xrefs

- `0x1800407b5`: `CSdBackupImpl::_CreateBlbBackupConfig_Sources`

## pseudocode

```c
__int64 __fastcall CSdBackupImpl::_CreateBlbBackupConfig_Sources(
        CSdBackupImpl *this,
        struct IBlbEngine *a2,
        struct ISdAsyncPriv *a3,
        struct _BLB_TEMPLATE_SETTINGS *a4)
{
  _OWORD *v8; // rdi
  _DWORD *v9; // r15
  __int16 v10; // ax
  unsigned int v11; // ebx
  unsigned int v12; // r8d
  unsigned int v13; // r9d
  _BYTE *v14; // rdx
  unsigned __int64 v15; // rcx
  unsigned int v16; // eax
  __int16 v17; // dx
  _BYTE *v18; // r9
  __int64 v19; // r10
  unsigned int v20; // r8d
  unsigned int i; // edx
  unsigned __int64 v22; // rcx
  unsigned int v23; // ebx
  LPVOID pv; // [rsp+20h] [rbp-40h] BYREF
  int valid; // [rsp+28h] [rbp-38h] BYREF
  __int16 v27; // [rsp+2Ch] [rbp-34h]
  __int16 v28; // [rsp+2Eh] [rbp-32h]
  unsigned int v29; // [rsp+98h] [rbp+38h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&valid,
    "CSdBackupImpl::_CreateBlbBackupConfig_Sources",
    0xE4Fu,
    1u);
  pv = 0;
  v29 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 3673;
  if ( !a2 || (v27 = 3673, v10 = 3674, !a3) || (v27 = 3674, v10 = 3675, !a4) )
  {
    valid = -2147024809;
LABEL_25:
    v28 = v10;
    goto LABEL_26;
  }
  valid = 0;
  v27 = 3675;
  valid = (*(__int64 (__fastcall **)(struct IBlbEngine *, unsigned int *, LPVOID *))(*(_QWORD *)a2 + 88LL))(
            a2,
            &v29,
            &pv);
  v10 = 3677;
  if ( valid < 0 )
    goto LABEL_25;
  v27 = 3677;
  valid = (*(__int64 (__fastcall **)(struct ISdAsyncPriv *))(*(_QWORD *)a3 + 120LL))(a3);
  v10 = 3679;
  if ( valid < 0 )
    goto LABEL_25;
  v27 = 3679;
  valid = CSdBackupImpl::_EnsureValidBlbSourceVolumes(this, (struct _BLB_VOLUME_INFO *)pv, v29);
  v10 = 3681;
  if ( valid < 0 )
    goto LABEL_25;
  v11 = 0;
  v27 = 3681;
  v12 = 0;
  v13 = v29;
  if ( v29 )
  {
    v14 = pv;
    do
    {
      v15 = (unsigned __int64)v12 << 7;
      if ( (v14[v15 + 88] & 1) != 0 )
      {
        v14[v15 + 85] = 1;
        v14 = pv;
        v13 = v29;
      }
      v16 = v11 + 1;
      if ( !v14[v15 + 85] )
        v16 = v11;
      v11 = v16;
      ++v12;
    }
    while ( v12 < v13 );
  }
  v8 = CoTaskMemAlloc(16LL * v11);
  v17 = 3698;
  if ( v8 && (valid = 0, v27 = 3698, v9 = CoTaskMemAlloc(4LL * v11), v17 = 3701, v9) )
  {
    valid = 0;
    v27 = 3701;
    v18 = CoTaskMemAlloc(v11);
    if ( v18 )
    {
      v19 = 0;
      valid = 0;
      v27 = 3704;
      v20 = 0;
      for ( i = v29; v20 < i; ++v20 )
      {
        v22 = (unsigned __int64)v20 << 7;
        if ( *((_BYTE *)pv + v22 + 85) )
        {
          v8[(unsigned int)v19] = *(_OWORD *)((char *)pv + v22);
          v9[v19] = *(_DWORD *)((char *)pv + v22 + 88);
          v18[v19] = 1;
          v19 = (unsigned int)(v19 + 1);
          i = v29;
        }
      }
      *((_QWORD *)a4 + 10) = v8;
      *((_QWORD *)a4 + 11) = v9;
      *((_QWORD *)a4 + 12) = v18;
      *((_DWORD *)a4 + 18) = v11;
      v8 = 0;
      v9 = 0;
    }
    else
    {
      valid = -2147024882;
      v28 = 3704;
    }
  }
  else
  {
    valid = -2147024882;
    v28 = v17;
  }
LABEL_26:
  FreeBlbVolumeInfoArray((struct _BLB_VOLUME_INFO **)&pv, &v29);
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v8);
  CoTaskMemFree(v9);
  CoTaskMemFree(0);
  v23 = valid;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&valid);
  return v23;
}

```

## disassembly

```asm
0x180040784  mov     [rsp-28h+arg_0], rbx
0x180040789  mov     [rsp-28h+arg_10], rsi
0x18004078e  push    rbp
0x18004078f  push    rdi
0x180040790  push    r12
0x180040792  push    r14
0x180040794  push    r15
0x180040796  mov     rbp, rsp
0x180040799  sub     rsp, 60h
0x18004079d  mov     rsi, r9
0x1800407a0  mov     rbx, r8
0x1800407a3  mov     r14, rdx
0x1800407a6  mov     r12, rcx
0x1800407a9  mov     r9d, 1; unsigned __int16
0x1800407af  mov     r8d, 0E4Fh; unsigned __int16
0x1800407b5  lea     rdx, aCsdbackupimplC_7; "CSdBackupImpl::_CreateBlbBackupConfig_S"...
0x1800407bc  lea     rcx, [rbp+var_38]; this
0x1800407c0  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800407c5  mov     [rbp+pv], 0
0x1800407cd  mov     [rbp+arg_8], 0
0x1800407d4  xor     edi, edi
0x1800407d6  xor     r15d, r15d
0x1800407d9  mov     eax, 0E59h
0x1800407de  test    r14, r14
0x1800407e1  jz      loc_1800409C7
0x1800407e7  mov     [rbp+var_34], ax
0x1800407eb  mov     eax, 0E5Ah
0x1800407f0  test    rbx, rbx
0x1800407f3  jz      loc_1800409C7
0x1800407f9  mov     [rbp+var_34], ax
0x1800407fd  mov     eax, 0E5Bh
0x180040802  test    rsi, rsi
0x180040805  jz      loc_1800409C7
0x18004080b  mov     [rbp+var_38], edi
0x18004080e  mov     [rbp+var_34], ax
0x180040812  mov     rax, [r14]
0x180040815  lea     r8, [rbp+pv]
0x180040819  lea     rdx, [rbp+arg_8]
0x18004081d  mov     rcx, r14
0x180040820  mov     rax, [rax+58h]
0x180040824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040829  mov     [rbp+var_38], eax
0x18004082c  test    eax, eax
0x18004082e  mov     eax, 0E5Dh
0x180040833  js      loc_1800409CE
0x180040839  mov     [rbp+var_34], ax
0x18004083d  mov     rax, [rbx]
0x180040840  mov     rcx, rbx
0x180040843  mov     rax, [rax+78h]
0x180040847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004084c  mov     [rbp+var_38], eax
0x18004084f  test    eax, eax
0x180040851  mov     eax, 0E5Fh
0x180040856  js      loc_1800409CE
0x18004085c  mov     [rbp+var_34], ax
0x180040860  mov     r8d, [rbp+arg_8]; unsigned int
0x180040864  mov     rdx, [rbp+pv]; struct _BLB_VOLUME_INFO *
0x180040868  mov     rcx, r12; this
0x18004086b  call    ?_EnsureValidBlbSourceVolumes@CSdBackupImpl@@AEAAJPEAU_BLB_VOLUME_INFO@@K@Z; CSdBackupImpl::_EnsureValidBlbSourceVolumes(_BLB_VOLUME_INFO *,ulong)
0x180040870  mov     [rbp+var_38], eax
0x180040873  test    eax, eax
0x180040875  mov     eax, 0E61h
0x18004087a  js      loc_1800409CE
0x180040880  xor     ebx, ebx
0x180040882  mov     [rbp+var_34], ax
0x180040886  xor     r8d, r8d
0x180040889  mov     r9d, [rbp+arg_8]
0x18004088d  test    r9d, r9d
0x180040890  jz      short loc_1800408C6
0x180040892  mov     rdx, [rbp+pv]
0x180040896  mov     ecx, r8d
0x180040899  shl     rcx, 7
0x18004089d  test    byte ptr [rcx+rdx+58h], 1
0x1800408a2  jz      short loc_1800408B1
0x1800408a4  mov     byte ptr [rcx+rdx+55h], 1
0x1800408a9  mov     rdx, [rbp+pv]
0x1800408ad  mov     r9d, [rbp+arg_8]
0x1800408b1  lea     eax, [rbx+1]
0x1800408b4  cmp     [rcx+rdx+55h], dil
0x1800408b9  cmovz   eax, ebx
0x1800408bc  mov     ebx, eax
0x1800408be  inc     r8d
0x1800408c1  cmp     r8d, r9d
0x1800408c4  jb      short loc_180040896
0x1800408c6  mov     r14d, ebx
0x1800408c9  mov     ecx, ebx
0x1800408cb  shl     rcx, 4; cb
0x1800408cf  call    cs:__imp_CoTaskMemAlloc
0x1800408d6  nop     dword ptr [rax+rax+00h]
0x1800408db  mov     rdi, rax
0x1800408de  mov     edx, 0E72h
0x1800408e3  test    rax, rax
0x1800408e6  jz      loc_1800409BA
0x1800408ec  mov     [rbp+var_38], r15d
0x1800408f0  mov     [rbp+var_34], dx
0x1800408f4  lea     rcx, ds:0[r14*4]; cb
0x1800408fc  call    cs:__imp_CoTaskMemAlloc
0x180040903  nop     dword ptr [rax+rax+00h]
0x180040908  mov     r15, rax
0x18004090b  mov     edx, 0E75h
0x180040910  test    rax, rax
0x180040913  jz      loc_1800409BA
0x180040919  mov     [rbp+var_38], 0
0x180040920  mov     [rbp+var_34], dx
0x180040924  mov     ecx, r14d; cb
0x180040927  call    cs:__imp_CoTaskMemAlloc
0x18004092e  nop     dword ptr [rax+rax+00h]
0x180040933  mov     r9, rax
0x180040936  mov     ecx, 0E78h
0x18004093b  test    rax, rax
0x18004093e  jz      short loc_1800409AD
0x180040940  xor     r10d, r10d
0x180040943  mov     [rbp+var_38], r10d
0x180040947  mov     [rbp+var_34], cx
0x18004094b  xor     r8d, r8d
0x18004094e  mov     edx, [rbp+arg_8]
0x180040951  test    edx, edx
0x180040953  jz      short loc_180040997
0x180040955  mov     ecx, r8d
0x180040958  shl     rcx, 7
0x18004095c  mov     r11, [rbp+pv]
0x180040960  cmp     byte ptr [rcx+r11+55h], 0
0x180040966  jz      short loc_18004098F
0x180040968  mov     eax, r10d
0x18004096b  add     rax, rax
0x18004096e  movups  xmm0, xmmword ptr [rcx+r11]
0x180040973  movdqu  xmmword ptr [rdi+rax*8], xmm0
0x180040978  mov     rax, [rbp+pv]
0x18004097c  mov     ecx, [rcx+rax+58h]
0x180040980  mov     [r15+r10*4], ecx
0x180040984  mov     byte ptr [r10+r9], 1
0x180040989  inc     r10d
0x18004098c  mov     edx, [rbp+arg_8]
0x18004098f  inc     r8d
0x180040992  cmp     r8d, edx
0x180040995  jb      short loc_180040955
0x180040997  mov     [rsi+50h], rdi
0x18004099b  mov     [rsi+58h], r15
0x18004099f  mov     [rsi+60h], r9
0x1800409a3  mov     [rsi+48h], ebx
0x1800409a6  xor     edi, edi
0x1800409a8  xor     r15d, r15d
0x1800409ab  jmp     short loc_1800409D2
0x1800409ad  mov     [rbp+var_38], 8007000Eh
0x1800409b4  mov     [rbp+var_32], cx
0x1800409b8  jmp     short loc_1800409D2
0x1800409ba  mov     [rbp+var_38], 8007000Eh
0x1800409c1  mov     [rbp+var_32], dx
0x1800409c5  jmp     short loc_1800409D2
0x1800409c7  mov     [rbp+var_38], 80070057h
0x1800409ce  mov     [rbp+var_32], ax
0x1800409d2  lea     rdx, [rbp+arg_8]; unsigned int *
0x1800409d6  lea     rcx, [rbp+pv]; struct _BLB_VOLUME_INFO **
0x1800409da  call    ?FreeBlbVolumeInfoArray@@YAXPEAPEAU_BLB_VOLUME_INFO@@PEAK@Z; FreeBlbVolumeInfoArray(_BLB_VOLUME_INFO * *,ulong *)
0x1800409df  mov     rcx, [rbp+pv]; pv
0x1800409e3  call    cs:__imp_CoTaskMemFree
0x1800409ea  nop     dword ptr [rax+rax+00h]
0x1800409ef  mov     [rbp+pv], 0
0x1800409f7  mov     rcx, rdi; pv
0x1800409fa  call    cs:__imp_CoTaskMemFree
0x180040a01  nop     dword ptr [rax+rax+00h]
0x180040a06  mov     rcx, r15; pv
0x180040a09  call    cs:__imp_CoTaskMemFree
0x180040a10  nop     dword ptr [rax+rax+00h]
0x180040a15  xor     ecx, ecx; pv
0x180040a17  call    cs:__imp_CoTaskMemFree
0x180040a1e  nop     dword ptr [rax+rax+00h]
0x180040a23  mov     ebx, [rbp+var_38]
0x180040a26  lea     rcx, [rbp+var_38]; this
0x180040a2a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180040a2f  mov     eax, ebx
0x180040a31  lea     r11, [rsp+60h+var_s0]
0x180040a36  mov     rbx, [r11+30h]
0x180040a3a  mov     rsi, [r11+40h]
0x180040a3e  mov     rsp, r11
0x180040a41  pop     r15
0x180040a43  pop     r14
0x180040a45  pop     r12
0x180040a47  pop     rdi
0x180040a48  pop     rbp
0x180040a49  retn
```
