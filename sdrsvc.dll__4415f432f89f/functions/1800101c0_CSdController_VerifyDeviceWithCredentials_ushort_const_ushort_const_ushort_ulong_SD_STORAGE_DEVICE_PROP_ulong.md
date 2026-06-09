# CSdController::VerifyDeviceWithCredentials(ushort const *,ushort const *,ushort *,ulong,_SD_STORAGE_DEVICE_PROP *,ulong *)

- ea: `0x1800101c0`
- end: `0x18001052b`
- name: `?VerifyDeviceWithCredentials@CSdController@@UEAAJPEBG0PEAGKPEAU_SD_STORAGE_DEVICE_PROP@@PEAK@Z`
- size: `875`
- prototype: `__int64 __fastcall(CSdController *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, char, struct _SD_STORAGE_DEVICE_PROP *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800101c0`
- `0x18001445c`
- `0x18001586c`
- `0x180015974`
- `0x180015fc4`
- `0x180017c20`
- `0x180017e08`
- `0x18001b0e4`
- `0x18002170a`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800104ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800104ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800104ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800104d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800104ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800104d8`

## pseudocode

```c
__int64 __fastcall CSdController::VerifyDeviceWithCredentials(
        CSdController *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        char a5,
        struct _SD_STORAGE_DEVICE_PROP *a6,
        unsigned int *a7)
{
  char *v9; // rbx
  unsigned __int16 *v10; // r12
  unsigned __int16 *v11; // r14
  __int64 v12; // rcx
  struct _SD_STORAGE_DEVICE_PROP *v13; // rax
  __int64 v14; // rsi
  __int16 v15; // ax
  bool v16; // zf
  __int64 v17; // rax
  __int64 i; // rax
  HANDLE v19; // rdx
  int NetworkCredentials; // eax
  bool v21; // sf
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  unsigned int v30; // eax
  __int64 j; // rax
  unsigned int v32; // edi
  unsigned int v34; // [rsp+30h] [rbp-D0h] BYREF
  int v35; // [rsp+34h] [rbp-CCh] BYREF
  int v36; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v37; // [rsp+3Ch] [rbp-C4h]
  __int16 v38; // [rsp+3Eh] [rbp-C2h]
  unsigned __int16 *v39; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v40; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hToken; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v42; // [rsp+88h] [rbp-78h]
  unsigned int *v43; // [rsp+90h] [rbp-70h]
  _OWORD v44[9]; // [rsp+A0h] [rbp-60h] BYREF
  _SID v45; // [rsp+130h] [rbp+30h] BYREF

  v42 = a2;
  v43 = a7;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v36,
    "CSdController::VerifyDeviceWithCredentials",
    0xBE1u,
    1u);
  v9 = 0;
  hToken = 0;
  memset_0(&v45, 0, 0x48u);
  memset_0(v44, 0, sizeof(v44));
  v39 = 0;
  v10 = 0;
  v40 = 0;
  v11 = 0;
  v35 = 0;
  v34 = 0;
  if ( a6 )
  {
    v12 = 144;
    v13 = a6;
    do
    {
      *(_BYTE *)v13 = 0;
      v13 = (struct _SD_STORAGE_DEVICE_PROP *)((char *)v13 + 1);
      --v12;
    }
    while ( v12 );
  }
  if ( a7 )
    *a7 = 0;
  v14 = -1;
  v15 = 3055;
  if ( !v42 )
    goto LABEL_7;
  v37 = 3055;
  v15 = 3056;
  if ( !a3 )
    goto LABEL_7;
  v37 = 3056;
  v15 = 3057;
  if ( !a4
    || (v37 = 3057, v15 = 3058, !a6)
    || (v37 = 3058, v15 = 3059, !v43)
    || (v16 = *a4 == 0, v37 = 3059, v15 = 3060, (*a3 == 0) != v16) )
  {
LABEL_7:
    v36 = -2147024809;
    goto LABEL_8;
  }
  v36 = 0;
  v37 = 3060;
  v36 = VerifyCallerAdmin();
  v15 = 3063;
  if ( v36 < 0 )
    goto LABEL_8;
  v37 = 3063;
  if ( (a5 & 1) != 0 )
  {
    if ( (int)ReadCredsFromRegistry(&v39, &v40) < 0 )
    {
      v10 = v39;
      v11 = v40;
      v38 = 3070;
      v36 = -2130706431;
      goto LABEL_31;
    }
    v17 = -1;
    do
      ++v17;
    while ( a4[v17] );
    for ( i = 2 * v17; i; --i )
    {
      *(_BYTE *)a4 = 0;
      a4 = (unsigned __int16 *)((char *)a4 + 1);
    }
    v10 = v39;
    v11 = v40;
    a3 = v39;
    a4 = v40;
  }
  v19 = 0;
  if ( *a3 && *a4 )
  {
    NetworkCredentials = GetNetworkCredentials(v42, a3, a4, &hToken, &v45, &v35);
    v9 = (char *)hToken;
    v21 = NetworkCredentials < 0;
    v36 = NetworkCredentials;
    v15 = 3085;
    if ( !v21 )
    {
      v37 = 3085;
      v19 = hToken;
      goto LABEL_27;
    }
LABEL_8:
    v38 = v15;
    goto LABEL_31;
  }
LABEL_27:
  v36 = CSdController::_VerifyDeviceWithCreds(v42, v19, &v45, (struct _SD_STORAGE_DEVICE_PROP *)v44, &v34);
  v15 = 3094;
  if ( v36 < 0 )
    goto LABEL_8;
  v22 = v44[1];
  *(_OWORD *)a6 = v44[0];
  v37 = 3094;
  v23 = v44[2];
  *((_OWORD *)a6 + 1) = v22;
  v24 = v44[3];
  *((_OWORD *)a6 + 2) = v23;
  v25 = v44[4];
  *((_OWORD *)a6 + 3) = v24;
  v26 = v44[5];
  *((_OWORD *)a6 + 4) = v25;
  v27 = v44[6];
  *((_OWORD *)a6 + 5) = v26;
  v28 = v44[7];
  *((_OWORD *)a6 + 6) = v27;
  v29 = v44[8];
  *((_OWORD *)a6 + 7) = v28;
  *((_OWORD *)a6 + 8) = v29;
  memset_0(v44, 0, sizeof(v44));
  v30 = v34;
  if ( !v35 )
  {
    v30 = v34 | 1;
    v34 |= 1u;
  }
  *v43 = v30;
LABEL_31:
  CleanupStorageDeviceProp((struct _SD_STORAGE_DEVICE_PROP *)v44);
  if ( a4 )
  {
    do
      ++v14;
    while ( a4[v14] );
    for ( j = 2 * v14; j; --j )
    {
      *(_BYTE *)a4 = 0;
      a4 = (unsigned __int16 *)((char *)a4 + 1);
    }
  }
  if ( v10 )
    CoTaskMemFree(v10);
  if ( v11 )
    CoTaskMemFree(v11);
  v32 = v36;
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v36);
  return v32;
}

```

## disassembly

```asm
0x1800101c0  mov     [rsp-8+arg_0], rbx
0x1800101c5  push    rbp
0x1800101c6  push    rsi
0x1800101c7  push    rdi
0x1800101c8  push    r12
0x1800101ca  push    r13
0x1800101cc  push    r14
0x1800101ce  push    r15
0x1800101d0  lea     rbp, [rsp-90h]
0x1800101d8  sub     rsp, 190h
0x1800101df  mov     rax, cs:__security_cookie
0x1800101e6  xor     rax, rsp
0x1800101e9  mov     [rbp+0C0h+var_40], rax
0x1800101f0  mov     rsi, [rbp+0C0h+arg_30]
0x1800101f7  lea     rcx, [rsp+1C0h+var_188]; this
0x1800101fc  mov     r13, [rbp+0C0h+arg_28]
0x180010203  mov     rdi, r9
0x180010206  mov     r15, r8
0x180010209  mov     [rbp+0C0h+var_138], rdx
0x18001020d  mov     r9d, 1; unsigned __int16
0x180010213  mov     [rbp+0C0h+var_130], rsi
0x180010217  mov     r8d, 0BE1h; unsigned __int16
0x18001021d  lea     rdx, aCsdcontrollerV_0; "CSdController::VerifyDeviceWithCredenti"...
0x180010224  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180010229  xor     ebx, ebx
0x18001022b  lea     rcx, [rbp+0C0h+var_90]; void *
0x18001022f  xor     edx, edx; Val
0x180010231  mov     [rbp+0C0h+hToken], rbx
0x180010235  lea     r8d, [rbx+48h]; Size
0x180010239  call    memset_0
0x18001023e  xor     edx, edx; Val
0x180010240  lea     rcx, [rbp+0C0h+var_120]; void *
0x180010244  mov     r8d, 90h; Size
0x18001024a  call    memset_0
0x18001024f  xor     edx, edx
0x180010251  mov     [rsp+1C0h+var_150], rdx
0x180010256  mov     r12d, edx
0x180010259  mov     [rsp+1C0h+var_148], rdx
0x18001025e  mov     r14d, edx
0x180010261  mov     [rsp+1C0h+var_18C], edx
0x180010265  mov     [rsp+1C0h+var_190], edx
0x180010269  test    r13, r13
0x18001026c  jz      short loc_180010281
0x18001026e  mov     ecx, 90h
0x180010273  mov     rax, r13
0x180010276  mov     [rax], dl
0x180010278  inc     rax
0x18001027b  sub     rcx, 1
0x18001027f  jnz     short loc_180010276
0x180010281  test    rsi, rsi
0x180010284  jz      short loc_180010288
0x180010286  mov     [rsi], edx
0x180010288  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001028c  mov     eax, 0BEFh
0x180010291  cmp     [rbp+0C0h+var_138], rdx
0x180010295  jnz     short loc_1800102A9
0x180010297  mov     [rsp+1C0h+var_188], 80070057h
0x18001029f  mov     [rsp+1C0h+var_182], ax
0x1800102a4  jmp     loc_180010495
0x1800102a9  mov     [rsp+1C0h+var_184], ax
0x1800102ae  mov     eax, 0BF0h
0x1800102b3  test    r15, r15
0x1800102b6  jz      short loc_180010297
0x1800102b8  mov     [rsp+1C0h+var_184], ax
0x1800102bd  mov     eax, 0BF1h
0x1800102c2  test    rdi, rdi
0x1800102c5  jz      short loc_180010297
0x1800102c7  mov     [rsp+1C0h+var_184], ax
0x1800102cc  mov     eax, 0BF2h
0x1800102d1  test    r13, r13
0x1800102d4  jz      short loc_180010297
0x1800102d6  mov     [rsp+1C0h+var_184], ax
0x1800102db  mov     eax, 0BF3h
0x1800102e0  cmp     [rbp+0C0h+var_130], rdx
0x1800102e4  jz      short loc_180010297
0x1800102e6  cmp     [rdi], dx
0x1800102e9  mov     ecx, edx
0x1800102eb  mov     [rsp+1C0h+var_184], ax
0x1800102f0  mov     eax, edx
0x1800102f2  setz    cl
0x1800102f5  cmp     [r15], dx
0x1800102f9  setz    al
0x1800102fc  cmp     eax, ecx
0x1800102fe  mov     eax, 0BF4h
0x180010303  jnz     short loc_180010297
0x180010305  mov     [rsp+1C0h+var_188], edx
0x180010309  mov     [rsp+1C0h+var_184], ax
0x18001030e  call    ?VerifyCallerAdmin@@YAJXZ; VerifyCallerAdmin(void)
0x180010313  xor     ecx, ecx
0x180010315  mov     [rsp+1C0h+var_188], eax
0x180010319  test    eax, eax
0x18001031b  mov     eax, 0BF7h
0x180010320  js      loc_18001029F
0x180010326  test    [rbp+0C0h+arg_20], 1
0x18001032d  mov     [rsp+1C0h+var_184], ax
0x180010332  jz      short loc_180010396
0x180010334  lea     rdx, [rsp+1C0h+var_148]; unsigned __int16 **
0x180010339  lea     rcx, [rsp+1C0h+var_150]; unsigned __int16 **
0x18001033e  call    ?ReadCredsFromRegistry@@YAJPEAPEAG0@Z; ReadCredsFromRegistry(ushort * *,ushort * *)
0x180010343  xor     ecx, ecx
0x180010345  test    eax, eax
0x180010347  jns     short loc_18001036A
0x180010349  mov     r12, [rsp+1C0h+var_150]
0x18001034e  mov     eax, 0BFEh
0x180010353  mov     r14, [rsp+1C0h+var_148]
0x180010358  mov     [rsp+1C0h+var_182], ax
0x18001035d  mov     [rsp+1C0h+var_188], 81000001h
0x180010365  jmp     loc_180010495
0x18001036a  mov     rax, rsi
0x18001036d  inc     rax
0x180010370  cmp     [rdi+rax*2], cx
0x180010374  jnz     short loc_18001036D
0x180010376  add     rax, rax
0x180010379  jz      short loc_180010386
0x18001037b  mov     [rdi], cl
0x18001037d  inc     rdi
0x180010380  sub     rax, 1
0x180010384  jnz     short loc_18001037B
0x180010386  mov     r12, [rsp+1C0h+var_150]
0x18001038b  mov     r14, [rsp+1C0h+var_148]
0x180010390  mov     r15, r12
0x180010393  mov     rdi, r14
0x180010396  mov     rdx, rcx
0x180010399  cmp     [r15], cx
0x18001039d  jz      short loc_1800103E7
0x18001039f  cmp     [rdi], cx
0x1800103a2  jz      short loc_1800103E7
0x1800103a4  mov     rcx, [rbp+0C0h+var_138]; unsigned __int16 *
0x1800103a8  lea     rax, [rsp+1C0h+var_18C]
0x1800103ad  mov     [rsp+1C0h+var_198], rax; int *
0x1800103b2  lea     r9, [rbp+0C0h+hToken]; void **
0x1800103b6  lea     rax, [rbp+0C0h+var_90]
0x1800103ba  mov     r8, rdi; lpszPassword
0x1800103bd  mov     rdx, r15; Str
0x1800103c0  mov     [rsp+1C0h+var_1A0], rax; struct _SID *
0x1800103c5  call    ?GetNetworkCredentials@@YAJPEBG00PEAPEAXPEAU_SID@@PEAH@Z; GetNetworkCredentials(ushort const *,ushort const *,ushort const *,void * *,_SID *,int *)
0x1800103ca  mov     rbx, [rbp+0C0h+hToken]
0x1800103ce  test    eax, eax
0x1800103d0  mov     [rsp+1C0h+var_188], eax
0x1800103d4  mov     eax, 0C0Dh
0x1800103d9  js      loc_18001029F
0x1800103df  mov     [rsp+1C0h+var_184], ax
0x1800103e4  mov     rdx, rbx; hToken
0x1800103e7  mov     rcx, [rbp+0C0h+var_138]; unsigned __int16 *
0x1800103eb  lea     rax, [rsp+1C0h+var_190]
0x1800103f0  lea     r9, [rbp+0C0h+var_120]; struct _SD_STORAGE_DEVICE_PROP *
0x1800103f4  mov     [rsp+1C0h+var_1A0], rax; unsigned int *
0x1800103f9  lea     r8, [rbp+0C0h+var_90]; struct _SID *
0x1800103fd  call    ?_VerifyDeviceWithCreds@CSdController@@CAJPEBGPEAXPEAU_SID@@PEAU_SD_STORAGE_DEVICE_PROP@@PEAK@Z; CSdController::_VerifyDeviceWithCreds(ushort const *,void *,_SID *,_SD_STORAGE_DEVICE_PROP *,ulong *)
0x180010402  mov     [rsp+1C0h+var_188], eax
0x180010406  test    eax, eax
0x180010408  mov     eax, 0C16h
0x18001040d  js      loc_18001029F
0x180010413  movaps  xmm0, [rbp+0C0h+var_120]
0x180010417  lea     rcx, [rbp+0C0h+var_120]; void *
0x18001041b  movaps  xmm1, [rbp+0C0h+var_110]
0x18001041f  xor     edx, edx; Val
0x180010421  movups  xmmword ptr [r13+0], xmm0
0x180010426  mov     r8d, 90h; Size
0x18001042c  mov     [rsp+1C0h+var_184], ax
0x180010431  movaps  xmm0, [rbp+0C0h+var_100]
0x180010435  movups  xmmword ptr [r13+10h], xmm1
0x18001043a  movaps  xmm1, [rbp+0C0h+var_F0]
0x18001043e  movups  xmmword ptr [r13+20h], xmm0
0x180010443  movaps  xmm0, [rbp+0C0h+var_E0]
0x180010447  movups  xmmword ptr [r13+30h], xmm1
0x18001044c  movaps  xmm1, [rbp+0C0h+var_D0]
0x180010450  movups  xmmword ptr [r13+40h], xmm0
0x180010455  movaps  xmm0, [rbp+0C0h+var_C0]
0x180010459  movups  xmmword ptr [r13+50h], xmm1
0x18001045e  movaps  xmm1, [rbp+0C0h+var_B0]
0x180010462  movups  xmmword ptr [r13+60h], xmm0
0x180010467  movaps  xmm0, [rbp+0C0h+var_A0]
0x18001046b  movups  xmmword ptr [r13+70h], xmm1
0x180010470  movups  xmmword ptr [r13+80h], xmm0
0x180010478  call    memset_0
0x18001047d  cmp     [rsp+1C0h+var_18C], 0
0x180010482  mov     eax, [rsp+1C0h+var_190]
0x180010486  jnz     short loc_18001048F
0x180010488  or      eax, 1
0x18001048b  mov     [rsp+1C0h+var_190], eax
0x18001048f  mov     rcx, [rbp+0C0h+var_130]
0x180010493  mov     [rcx], eax
0x180010495  lea     rcx, [rbp+0C0h+var_120]; struct _SD_STORAGE_DEVICE_PROP *
0x180010499  call    ?CleanupStorageDeviceProp@@YAXPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)
0x18001049e  xor     ecx, ecx
0x1800104a0  test    rdi, rdi
0x1800104a3  jz      short loc_1800104C2
0x1800104a5  inc     rsi
0x1800104a8  cmp     [rdi+rsi*2], cx
0x1800104ac  jnz     short loc_1800104A5
0x1800104ae  lea     rax, [rsi+rsi]
0x1800104b2  test    rax, rax
0x1800104b5  jz      short loc_1800104C2
0x1800104b7  mov     [rdi], cl
0x1800104b9  inc     rdi
0x1800104bc  sub     rax, 1
0x1800104c0  jnz     short loc_1800104B7
0x1800104c2  test    r12, r12
0x1800104c5  jz      short loc_1800104D0
0x1800104c7  mov     rcx, r12; pv
0x1800104ca  call    cs:__imp_CoTaskMemFree
0x1800104d0  test    r14, r14
0x1800104d3  jz      short loc_1800104DE
0x1800104d5  mov     rcx, r14; pv
0x1800104d8  call    cs:__imp_CoTaskMemFree
0x1800104de  mov     edi, [rsp+1C0h+var_188]
0x1800104e2  lea     rcx, [rbx-1]
0x1800104e6  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800104ea  ja      short loc_1800104F5
0x1800104ec  mov     rcx, rbx; hObject
0x1800104ef  call    cs:__imp_CloseHandle
0x1800104f5  lea     rcx, [rsp+1C0h+var_188]; this
0x1800104fa  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800104ff  mov     eax, edi
0x180010501  mov     rcx, [rbp+0C0h+var_40]
0x180010508  xor     rcx, rsp; StackCookie
0x18001050b  call    __security_check_cookie
0x180010510  mov     rbx, [rsp+1C0h+arg_0]
0x180010518  add     rsp, 190h
0x18001051f  pop     r15
0x180010521  pop     r14
0x180010523  pop     r13
0x180010525  pop     r12
0x180010527  pop     rdi
0x180010528  pop     rsi
0x180010529  pop     rbp
0x18001052a  retn
```
