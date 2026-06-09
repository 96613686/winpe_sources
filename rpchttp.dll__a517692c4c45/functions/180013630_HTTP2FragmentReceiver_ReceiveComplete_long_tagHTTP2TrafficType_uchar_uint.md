# HTTP2FragmentReceiver::ReceiveComplete(long,tagHTTP2TrafficType,uchar * *,uint *)

- ea: `0x180013630`
- end: `0x180013912`
- name: `?ReceiveComplete@HTTP2FragmentReceiver@@UEAAJJW4tagHTTP2TrafficType@@PEAPEAEPEAI@Z`
- size: `738`
- prototype: `__int64 __fastcall(__int64 *, __int64, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008d20`
- `0x180016800`
- `0x1800168a0`

## callees

- `0x18000f060`
- `0x180013630`
- `0x18002461d`
- `0x180025010`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x180013682`
- `RPCRT4!I_RpcLogEvent` at `0x1800138f2`
- `RPCRT4!I_RpcLogEvent` at `0x180013682`
- `RPCRT4!I_RpcLogEvent` at `0x1800138f2`

## pseudocode

```c
__int64 __fastcall HTTP2FragmentReceiver::ReceiveComplete(
        __int64 *a1,
        __int64 a2,
        unsigned int a3,
        _QWORD *a4,
        unsigned int *a5)
{
  unsigned int *v5; // r12
  unsigned int v6; // edi
  unsigned int v8; // r14d
  __int64 *v9; // rbx
  __int64 *v10; // r8
  unsigned int v11; // edi
  __int64 v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  bool v16; // zf
  __int64 (*v17)(void); // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  _QWORD *v20; // r15
  __int64 v21; // rdx
  unsigned __int16 v22; // ax
  int v23; // esi
  __int64 v24; // rax
  unsigned int v25; // edi
  unsigned int v26; // edi
  unsigned int v27; // ecx
  unsigned int v28; // eax
  unsigned int v29; // r14d
  void *v30; // rax
  void *v31; // rsi
  unsigned int v32; // eax
  __int64 v34; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v35; // [rsp+98h] [rbp+48h] BYREF
  unsigned int v36; // [rsp+A0h] [rbp+50h]

  v36 = a3;
  v5 = a5;
  v6 = a3;
  v8 = a2;
  v34 = 0;
  v9 = a1;
  v10 = a1;
  v35 = *a5;
  LOBYTE(a2) = 111;
  LOBYTE(a1) = 50;
  I_RpcLogEvent(a1, a2, v10, 17039385, v35, 0, 0);
  if ( v8 )
    goto LABEL_6;
  v11 = *((_DWORD *)v9 + 11) + v35;
  v35 = v11;
  if ( v11 < 0x10 )
  {
    v12 = *v9;
    *((_DWORD *)v9 + 11) = v11;
    v13 = (*(__int64 (__fastcall **)(__int64 *))(v12 + 96))(v9);
    goto LABEL_4;
  }
  v20 = v9 + 4;
  v21 = v9[4];
  v22 = *(_WORD *)(v21 + 8);
  if ( (*(_BYTE *)(v21 + 4) & 0x10) == 0 )
    v22 = __ROR2__(v22, 8);
  if ( v22 < 0x10u )
  {
    v8 = -1073606647;
    goto LABEL_5;
  }
  v23 = v22;
  if ( v11 == v22 )
  {
    v35 = v22;
    *((_DWORD *)v9 + 11) = 0;
    *v20 = 0;
    v34 = v21;
    goto LABEL_17;
  }
  if ( v11 >= v22 )
  {
    v26 = v11 - v22;
    v34 = v9[4];
    v35 = v22;
    if ( v26 >= 0x10 )
    {
      LOWORD(v27) = *(_WORD *)(v22 + v21 + 8);
      if ( (*(_BYTE *)(v22 + v21 + 4) & 0x10) == 0 )
        LOWORD(v27) = __ROR2__(v27, 8);
      v27 = (unsigned __int16)v27;
    }
    else
    {
      v27 = 1024;
    }
    v28 = v26;
    if ( v27 >= v26 )
      v28 = v27;
    v29 = v28;
    v30 = (void *)(*(__int64 (__fastcall **)(_QWORD))pRuntimeImportTable)(v28);
    v31 = v30;
    if ( !v30 )
    {
      v35 = 0;
      v8 = 14;
      goto LABEL_5;
    }
    memcpy_0(v30, (const void *)(*v20 + v35), v26);
    *v20 = v31;
    *((_DWORD *)v9 + 10) = v29;
    v8 = 0;
    *((_DWORD *)v9 + 11) = v26;
LABEL_17:
    v6 = v36;
LABEL_7:
    *a4 = v34;
    *v5 = v35;
    if ( *((_DWORD *)pRuntimeImportTable + 146) )
    {
      v16 = (unsigned int)HTTP2Channel::IsProxyChannel((HTTP2Channel *)v9[3]) == 0;
      v17 = (__int64 (*)(void))*((_QWORD *)pRuntimeImportTable + 70);
      if ( v16 )
      {
        if ( *(_DWORD *)(v17() + 16) )
        {
          v18 = (*((__int64 (**)(void))pRuntimeImportTable + 70))();
          v19 = 1;
          goto LABEL_38;
        }
      }
      else if ( *(_DWORD *)(v17() + 12) )
      {
        v18 = (*((__int64 (**)(void))pRuntimeImportTable + 70))();
        v19 = 0;
LABEL_38:
        (*(void (__fastcall **)(__int64, unsigned int *, __int64 *))(v18 + 176))(v19, &v35, &v34);
      }
    }
    v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, unsigned int))(*(_QWORD *)v9[2] + 32LL))(
            v9[2],
            v8,
            v6,
            v34,
            v35);
    v25 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v9 + 80))(v9, v32);
    goto LABEL_40;
  }
  if ( *((_DWORD *)v9 + 10) < (unsigned int)v22 )
  {
    v8 = (*((__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD, _QWORD))pRuntimeImportTable + 34))(0, v9 + 4, v11, v22);
    if ( v8 )
      goto LABEL_5;
    if ( !*((_DWORD *)pRuntimeImportTable + 144) )
      *((_DWORD *)v9 + 12) = v23;
  }
  *((_DWORD *)v9 + 11) = v35;
  v24 = *v9;
  *((_DWORD *)v9 + 10) = v23;
  v13 = (*(__int64 (__fastcall **)(__int64 *))(v24 + 96))(v9);
LABEL_4:
  v8 = v13;
  if ( v13 )
  {
LABEL_5:
    v6 = v36;
LABEL_6:
    v34 = 0;
    goto LABEL_7;
  }
  *a4 = 0;
  v25 = 0;
  *v5 = 0;
LABEL_40:
  LOBYTE(v14) = 111;
  LOBYTE(v15) = 50;
  I_RpcLogEvent(v15, v14, v9, 262169, *v5, 0, 0);
  return v25;
}

```

## disassembly

```asm
0x180013630  mov     [rsp-38h+arg_0], rbx
0x180013635  mov     [rsp-38h+arg_10], r8d
0x18001363a  push    rbp
0x18001363b  push    rsi
0x18001363c  push    rdi
0x18001363d  push    r12
0x18001363f  push    r13
0x180013641  push    r14
0x180013643  push    r15
0x180013645  mov     rbp, rsp
0x180013648  sub     rsp, 50h
0x18001364c  mov     r12, [rbp+arg_20]
0x180013650  xor     esi, esi
0x180013652  mov     edi, r8d
0x180013655  mov     [rsp+50h+var_20], esi
0x180013659  mov     r13, r9
0x18001365c  mov     [rsp+50h+var_28], esi
0x180013660  mov     r14d, edx
0x180013663  mov     [rbp+var_10], rsi
0x180013667  mov     eax, [r12]
0x18001366b  mov     rbx, rcx
0x18001366e  mov     r8, rcx
0x180013671  mov     [rbp+arg_8], eax
0x180013674  mov     r9d, 1040019h
0x18001367a  mov     [rsp+50h+var_30], eax
0x18001367e  mov     dl, 6Fh ; 'o'
0x180013680  mov     cl, 32h ; '2'
0x180013682  call    cs:__imp_I_RpcLogEvent
0x180013688  test    r14d, r14d
0x18001368b  jnz     short loc_1800136C3
0x18001368d  mov     edi, [rbp+arg_8]
0x180013690  lea     r8d, [rsi+10h]
0x180013694  add     edi, [rbx+2Ch]
0x180013697  mov     [rbp+arg_8], edi
0x18001369a  cmp     edi, r8d
0x18001369d  jnb     loc_180013730
0x1800136a3  mov     rax, [rbx]
0x1800136a6  mov     rcx, rbx
0x1800136a9  mov     [rbx+2Ch], edi
0x1800136ac  mov     rax, [rax+60h]
0x1800136b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136b5  mov     r14d, eax
0x1800136b8  test    eax, eax
0x1800136ba  jz      loc_1800137D9
0x1800136c0  mov     edi, [rbp+arg_10]
0x1800136c3  mov     [rbp+var_10], rsi
0x1800136c7  mov     rax, [rbp+var_10]
0x1800136cb  mov     [r13+0], rax
0x1800136cf  mov     eax, [rbp+arg_8]
0x1800136d2  mov     [r12], eax
0x1800136d6  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800136dd  cmp     [rax+248h], esi
0x1800136e3  jz      loc_18001389D
0x1800136e9  mov     rcx, [rbx+18h]; this
0x1800136ed  call    ?IsProxyChannel@HTTP2Channel@@QEAAHXZ; HTTP2Channel::IsProxyChannel(void)
0x1800136f2  test    eax, eax
0x1800136f4  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800136fb  mov     rax, [rax+230h]
0x180013702  jz      loc_180013867
0x180013708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001370d  cmp     [rax+0Ch], esi
0x180013710  jz      loc_18001389D
0x180013716  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18001371d  mov     rax, [rax+230h]
0x180013724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013729  xor     ecx, ecx
0x18001372b  jmp     loc_180013889
0x180013730  lea     r15, [rbx+20h]
0x180013734  mov     rdx, [r15]
0x180013737  movzx   eax, word ptr [rdx+8]
0x18001373b  test    [rdx+4], r8b
0x18001373f  jnz     short loc_180013745
0x180013741  ror     ax, 8
0x180013745  cmp     ax, r8w
0x180013749  jnb     short loc_180013756
0x18001374b  mov     r14d, 0C0021009h
0x180013751  jmp     loc_1800136C0
0x180013756  movzx   esi, ax
0x180013759  cmp     edi, esi
0x18001375b  jnz     short loc_180013774
0x18001375d  mov     [rbp+arg_8], esi
0x180013760  xor     esi, esi
0x180013762  mov     [rbx+2Ch], esi
0x180013765  mov     [r15], rsi
0x180013768  mov     [rbp+var_10], rdx
0x18001376c  mov     edi, [rbp+arg_10]
0x18001376f  jmp     loc_1800136C7
0x180013774  jnb     short loc_1800137E8
0x180013776  cmp     [rbx+28h], esi
0x180013779  jnb     short loc_1800137B3
0x18001377b  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180013782  mov     r9d, esi
0x180013785  mov     r8d, edi
0x180013788  mov     rdx, r15
0x18001378b  xor     ecx, ecx
0x18001378d  mov     rax, [rax+110h]
0x180013794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013799  mov     r14d, eax
0x18001379c  test    eax, eax
0x18001379e  jnz     short loc_1800137D2
0x1800137a0  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800137a7  cmp     [rax+240h], r14d
0x1800137ae  jnz     short loc_1800137B3
0x1800137b0  mov     [rbx+30h], esi
0x1800137b3  mov     eax, [rbp+arg_8]
0x1800137b6  mov     rcx, rbx
0x1800137b9  mov     [rbx+2Ch], eax
0x1800137bc  mov     rax, [rbx]
0x1800137bf  mov     [rbx+28h], esi
0x1800137c2  mov     rax, [rax+60h]
0x1800137c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137cb  xor     esi, esi
0x1800137cd  jmp     loc_1800136B5
0x1800137d2  xor     esi, esi
0x1800137d4  jmp     loc_1800136C0
0x1800137d9  mov     [r13+0], rsi
0x1800137dd  mov     edi, esi
0x1800137df  mov     [r12], esi
0x1800137e3  jmp     loc_1800138D4
0x1800137e8  sub     edi, esi
0x1800137ea  mov     [rbp+var_10], rdx
0x1800137ee  mov     [rbp+arg_8], esi
0x1800137f1  cmp     edi, r8d
0x1800137f4  jnb     short loc_1800137FD
0x1800137f6  mov     ecx, 400h
0x1800137fb  jmp     short loc_180013813
0x1800137fd  movzx   eax, ax
0x180013800  movzx   ecx, word ptr [rax+rdx+8]
0x180013805  test    [rax+rdx+4], r8b
0x18001380a  jnz     short loc_180013810
0x18001380c  ror     cx, 8
0x180013810  movzx   ecx, cx
0x180013813  cmp     ecx, edi
0x180013815  mov     eax, edi
0x180013817  cmovnb  eax, ecx
0x18001381a  mov     r14d, eax
0x18001381d  mov     ecx, eax
0x18001381f  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180013826  mov     rax, [rax]
0x180013829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001382e  mov     rsi, rax
0x180013831  test    rax, rax
0x180013834  jnz     short loc_180013842
0x180013836  mov     [rbp+arg_8], esi
0x180013839  lea     r14d, [rax+0Eh]
0x18001383d  jmp     loc_1800136C0
0x180013842  mov     edx, [rbp+arg_8]
0x180013845  mov     rcx, rsi; void *
0x180013848  add     rdx, [r15]; Src
0x18001384b  mov     r8d, edi; Size
0x18001384e  call    memcpy_0
0x180013853  mov     [r15], rsi
0x180013856  xor     esi, esi
0x180013858  mov     [rbx+28h], r14d
0x18001385c  mov     r14d, esi
0x18001385f  mov     [rbx+2Ch], edi
0x180013862  jmp     loc_18001376C
0x180013867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001386c  cmp     [rax+10h], esi
0x18001386f  jz      short loc_18001389D
0x180013871  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180013878  mov     rax, [rax+230h]
0x18001387f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013884  mov     ecx, 1
0x180013889  mov     rax, [rax+0B0h]
0x180013890  lea     r8, [rbp+var_10]
0x180013894  lea     rdx, [rbp+arg_8]
0x180013898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001389d  mov     edx, [rbp+arg_8]
0x1800138a0  mov     r8d, edi
0x1800138a3  mov     rcx, [rbx+10h]
0x1800138a7  mov     r9, [rbp+var_10]
0x1800138ab  mov     [rsp+50h+var_30], edx
0x1800138af  mov     edx, r14d
0x1800138b2  mov     rax, [rcx]
0x1800138b5  mov     rax, [rax+20h]
0x1800138b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138be  mov     rcx, [rbx]
0x1800138c1  mov     edx, eax
0x1800138c3  mov     r8, [rcx+50h]
0x1800138c7  mov     rcx, rbx
0x1800138ca  mov     rax, r8
0x1800138cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138d2  mov     edi, eax
0x1800138d4  mov     r8d, [r12]
0x1800138d8  mov     r9d, 40019h
0x1800138de  mov     [rsp+50h+var_20], esi
0x1800138e2  mov     dl, 6Fh ; 'o'
0x1800138e4  mov     [rsp+50h+var_28], esi
0x1800138e8  mov     cl, 32h ; '2'
0x1800138ea  mov     [rsp+50h+var_30], r8d
0x1800138ef  mov     r8, rbx
0x1800138f2  call    cs:__imp_I_RpcLogEvent
0x1800138f8  mov     rbx, [rsp+50h+arg_0]
0x180013900  mov     eax, edi
0x180013902  add     rsp, 50h
0x180013906  pop     r15
0x180013908  pop     r14
0x18001390a  pop     r13
0x18001390c  pop     r12
0x18001390e  pop     rdi
0x18001390f  pop     rsi
0x180013910  pop     rbp
0x180013911  retn
```
