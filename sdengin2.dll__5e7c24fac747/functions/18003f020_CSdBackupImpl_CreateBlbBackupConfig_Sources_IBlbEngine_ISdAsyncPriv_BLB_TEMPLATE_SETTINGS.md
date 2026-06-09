# CSdBackupImpl::_CreateBlbBackupConfig_Sources(IBlbEngine *,ISdAsyncPriv *,_BLB_TEMPLATE_SETTINGS *)

- ea: `0x18003f020`
- end: `0x18003f2bc`
- name: `?_CreateBlbBackupConfig_Sources@CSdBackupImpl@@AEAAJPEAUIBlbEngine@@PEAUISdAsyncPriv@@PEAU_BLB_TEMPLATE_SETTINGS@@@Z`
- size: `668`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this, struct IBlbEngine *, struct ISdAsyncPriv *, struct _BLB_TEMPLATE_SETTINGS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18003ecac`

## callees

- `0x18003f020`
- `0x18003faf8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008b0a4`
- `0x1800cb010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18003f26d`
- `ole32!CoTaskMemFree` at `0x18003f27e`
- `ole32!CoTaskMemFree` at `0x18003f287`
- `ole32!CoTaskMemFree` at `0x18003f28f`
- `ole32!CoTaskMemFree` at `0x18003f26d`
- `ole32!CoTaskMemFree` at `0x18003f27e`
- `ole32!CoTaskMemFree` at `0x18003f287`
- `ole32!CoTaskMemFree` at `0x18003f28f`
- `ole32!CoTaskMemAlloc` at `0x18003f16b`
- `ole32!CoTaskMemAlloc` at `0x18003f192`
- `ole32!CoTaskMemAlloc` at `0x18003f1b7`
- `ole32!CoTaskMemAlloc` at `0x18003f16b`
- `ole32!CoTaskMemAlloc` at `0x18003f192`
- `ole32!CoTaskMemAlloc` at `0x18003f1b7`

## string_xrefs

- `0x18003f051`: `CSdBackupImpl::_CreateBlbBackupConfig_Sources`

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
    3663,
    1);
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
0x18003f020  mov     [rsp-28h+arg_0], rbx
0x18003f025  mov     [rsp-28h+arg_10], rsi
0x18003f02a  push    rbp
0x18003f02b  push    rdi
0x18003f02c  push    r12
0x18003f02e  push    r14
0x18003f030  push    r15
0x18003f032  mov     rbp, rsp
0x18003f035  sub     rsp, 60h
0x18003f039  mov     rsi, r9
0x18003f03c  mov     rbx, r8
0x18003f03f  mov     r14, rdx
0x18003f042  mov     r12, rcx
0x18003f045  mov     r9d, 1; unsigned __int16
0x18003f04b  mov     r8d, 0E4Fh; unsigned __int16
0x18003f051  lea     rdx, aCsdbackupimplC_7; "CSdBackupImpl::_CreateBlbBackupConfig_S"...
0x18003f058  lea     rcx, [rbp+var_38]; this
0x18003f05c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003f061  mov     [rbp+pv], 0
0x18003f069  mov     [rbp+arg_8], 0
0x18003f070  xor     edi, edi
0x18003f072  xor     r15d, r15d
0x18003f075  mov     eax, 0E59h
0x18003f07a  test    r14, r14
0x18003f07d  jz      loc_18003F251
0x18003f083  mov     [rbp+var_34], ax
0x18003f087  mov     eax, 0E5Ah
0x18003f08c  test    rbx, rbx
0x18003f08f  jz      loc_18003F251
0x18003f095  mov     [rbp+var_34], ax
0x18003f099  mov     eax, 0E5Bh
0x18003f09e  test    rsi, rsi
0x18003f0a1  jz      loc_18003F251
0x18003f0a7  mov     [rbp+var_38], edi
0x18003f0aa  mov     [rbp+var_34], ax
0x18003f0ae  mov     rax, [r14]
0x18003f0b1  lea     r8, [rbp+pv]
0x18003f0b5  lea     rdx, [rbp+arg_8]
0x18003f0b9  mov     rcx, r14
0x18003f0bc  mov     rax, [rax+58h]
0x18003f0c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f0c5  mov     [rbp+var_38], eax
0x18003f0c8  test    eax, eax
0x18003f0ca  mov     eax, 0E5Dh
0x18003f0cf  js      loc_18003F258
0x18003f0d5  mov     [rbp+var_34], ax
0x18003f0d9  mov     rax, [rbx]
0x18003f0dc  mov     rcx, rbx
0x18003f0df  mov     rax, [rax+78h]
0x18003f0e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f0e8  mov     [rbp+var_38], eax
0x18003f0eb  test    eax, eax
0x18003f0ed  mov     eax, 0E5Fh
0x18003f0f2  js      loc_18003F258
0x18003f0f8  mov     [rbp+var_34], ax
0x18003f0fc  mov     r8d, [rbp+arg_8]; unsigned int
0x18003f100  mov     rdx, [rbp+pv]; struct _BLB_VOLUME_INFO *
0x18003f104  mov     rcx, r12; this
0x18003f107  call    ?_EnsureValidBlbSourceVolumes@CSdBackupImpl@@AEAAJPEAU_BLB_VOLUME_INFO@@K@Z; CSdBackupImpl::_EnsureValidBlbSourceVolumes(_BLB_VOLUME_INFO *,ulong)
0x18003f10c  mov     [rbp+var_38], eax
0x18003f10f  test    eax, eax
0x18003f111  mov     eax, 0E61h
0x18003f116  js      loc_18003F258
0x18003f11c  xor     ebx, ebx
0x18003f11e  mov     [rbp+var_34], ax
0x18003f122  xor     r8d, r8d
0x18003f125  mov     r9d, [rbp+arg_8]
0x18003f129  test    r9d, r9d
0x18003f12c  jz      short loc_18003F162
0x18003f12e  mov     rdx, [rbp+pv]
0x18003f132  mov     ecx, r8d
0x18003f135  shl     rcx, 7
0x18003f139  test    byte ptr [rcx+rdx+58h], 1
0x18003f13e  jz      short loc_18003F14D
0x18003f140  mov     byte ptr [rcx+rdx+55h], 1
0x18003f145  mov     rdx, [rbp+pv]
0x18003f149  mov     r9d, [rbp+arg_8]
0x18003f14d  lea     eax, [rbx+1]
0x18003f150  cmp     [rcx+rdx+55h], dil
0x18003f155  cmovz   eax, ebx
0x18003f158  mov     ebx, eax
0x18003f15a  inc     r8d
0x18003f15d  cmp     r8d, r9d
0x18003f160  jb      short loc_18003F132
0x18003f162  mov     r14d, ebx
0x18003f165  mov     ecx, ebx
0x18003f167  shl     rcx, 4; cb
0x18003f16b  call    cs:__imp_CoTaskMemAlloc
0x18003f171  mov     rdi, rax
0x18003f174  mov     edx, 0E72h
0x18003f179  test    rax, rax
0x18003f17c  jz      loc_18003F244
0x18003f182  mov     [rbp+var_38], r15d
0x18003f186  mov     [rbp+var_34], dx
0x18003f18a  lea     rcx, ds:0[r14*4]; cb
0x18003f192  call    cs:__imp_CoTaskMemAlloc
0x18003f198  mov     r15, rax
0x18003f19b  mov     edx, 0E75h
0x18003f1a0  test    rax, rax
0x18003f1a3  jz      loc_18003F244
0x18003f1a9  mov     [rbp+var_38], 0
0x18003f1b0  mov     [rbp+var_34], dx
0x18003f1b4  mov     ecx, r14d; cb
0x18003f1b7  call    cs:__imp_CoTaskMemAlloc
0x18003f1bd  mov     r9, rax
0x18003f1c0  mov     ecx, 0E78h
0x18003f1c5  test    rax, rax
0x18003f1c8  jz      short loc_18003F237
0x18003f1ca  xor     r10d, r10d
0x18003f1cd  mov     [rbp+var_38], r10d
0x18003f1d1  mov     [rbp+var_34], cx
0x18003f1d5  xor     r8d, r8d
0x18003f1d8  mov     edx, [rbp+arg_8]
0x18003f1db  test    edx, edx
0x18003f1dd  jz      short loc_18003F221
0x18003f1df  mov     ecx, r8d
0x18003f1e2  shl     rcx, 7
0x18003f1e6  mov     r11, [rbp+pv]
0x18003f1ea  cmp     byte ptr [rcx+r11+55h], 0
0x18003f1f0  jz      short loc_18003F219
0x18003f1f2  mov     eax, r10d
0x18003f1f5  add     rax, rax
0x18003f1f8  movups  xmm0, xmmword ptr [rcx+r11]
0x18003f1fd  movdqu  xmmword ptr [rdi+rax*8], xmm0
0x18003f202  mov     rax, [rbp+pv]
0x18003f206  mov     ecx, [rcx+rax+58h]
0x18003f20a  mov     [r15+r10*4], ecx
0x18003f20e  mov     byte ptr [r10+r9], 1
0x18003f213  inc     r10d
0x18003f216  mov     edx, [rbp+arg_8]
0x18003f219  inc     r8d
0x18003f21c  cmp     r8d, edx
0x18003f21f  jb      short loc_18003F1DF
0x18003f221  mov     [rsi+50h], rdi
0x18003f225  mov     [rsi+58h], r15
0x18003f229  mov     [rsi+60h], r9
0x18003f22d  mov     [rsi+48h], ebx
0x18003f230  xor     edi, edi
0x18003f232  xor     r15d, r15d
0x18003f235  jmp     short loc_18003F25C
0x18003f237  mov     [rbp+var_38], 8007000Eh
0x18003f23e  mov     [rbp+var_32], cx
0x18003f242  jmp     short loc_18003F25C
0x18003f244  mov     [rbp+var_38], 8007000Eh
0x18003f24b  mov     [rbp+var_32], dx
0x18003f24f  jmp     short loc_18003F25C
0x18003f251  mov     [rbp+var_38], 80070057h
0x18003f258  mov     [rbp+var_32], ax
0x18003f25c  lea     rdx, [rbp+arg_8]; unsigned int *
0x18003f260  lea     rcx, [rbp+pv]; struct _BLB_VOLUME_INFO **
0x18003f264  call    ?FreeBlbVolumeInfoArray@@YAXPEAPEAU_BLB_VOLUME_INFO@@PEAK@Z; FreeBlbVolumeInfoArray(_BLB_VOLUME_INFO * *,ulong *)
0x18003f269  mov     rcx, [rbp+pv]; pv
0x18003f26d  call    cs:__imp_CoTaskMemFree
0x18003f273  mov     [rbp+pv], 0
0x18003f27b  mov     rcx, rdi; pv
0x18003f27e  call    cs:__imp_CoTaskMemFree
0x18003f284  mov     rcx, r15; pv
0x18003f287  call    cs:__imp_CoTaskMemFree
0x18003f28d  xor     ecx, ecx; pv
0x18003f28f  call    cs:__imp_CoTaskMemFree
0x18003f295  mov     ebx, [rbp+var_38]
0x18003f298  lea     rcx, [rbp+var_38]; this
0x18003f29c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003f2a1  mov     eax, ebx
0x18003f2a3  lea     r11, [rsp+60h+var_s0]
0x18003f2a8  mov     rbx, [r11+30h]
0x18003f2ac  mov     rsi, [r11+40h]
0x18003f2b0  mov     rsp, r11
0x18003f2b3  pop     r15
0x18003f2b5  pop     r14
0x18003f2b7  pop     r12
0x18003f2b9  pop     rdi
0x18003f2ba  pop     rbp
0x18003f2bb  retn
```
