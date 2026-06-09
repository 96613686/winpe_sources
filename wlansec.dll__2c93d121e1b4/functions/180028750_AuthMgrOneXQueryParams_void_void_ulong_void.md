# AuthMgrOneXQueryParams(void *,void *,ulong *,void * *)

- ea: `0x180028750`
- end: `0x180028ad6`
- name: `?AuthMgrOneXQueryParams@@YAKPEAX0PEAKPEAPEAX@Z`
- size: `902`
- prototype: `unsigned int __fastcall(void *, void *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000c730`
- `0x18000d5e4`
- `0x18000e620`
- `0x180013600`
- `0x180013bc0`
- `0x1800169c0`
- `0x180028750`
- `0x18002a638`
- `0x18002b170`
- `0x18002bb08`
- `0x1800378dc`
- `0x180044554`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800288d0`
- `MobileNetworking!ReleaseWriteLock` at `0x180028915`
- `MobileNetworking!ReleaseWriteLock` at `0x1800288d0`
- `MobileNetworking!ReleaseWriteLock` at `0x180028915`
- `MobileNetworking!AcquireWriteLock` at `0x180028898`
- `MobileNetworking!AcquireWriteLock` at `0x180028898`

## pseudocode

```c
__int64 __fastcall AuthMgrOneXQueryParams(void *a1, void *a2, unsigned int *a3, void **a4)
{
  void *v8; // r15
  unsigned int v9; // eax
  unsigned int MSMSecMemory; // ebx
  PVOID *v11; // rcx
  struct MSMSEC_PORT_CONTEXT *v12; // r13
  struct MSMSEC_INTF_CONTEXT *v13; // rdi
  void *v14; // r14
  void *v15; // rsi
  unsigned int (*v16)(void *, void *, unsigned int *, void **); // rdi
  void (*v17)(void *); // rbx
  unsigned int v18; // ecx
  unsigned int v19; // eax
  struct MSMSEC_GLOBAL_PARAMS *v20; // rdi
  SIZE_T v21; // rcx
  void *v23; // [rsp+30h] [rbp-30h] BYREF
  struct MSMSEC_GLOBAL_PARAMS *v24; // [rsp+38h] [rbp-28h] BYREF
  struct MSMSEC_PORT_CONTEXT *v25; // [rsp+40h] [rbp-20h] BYREF
  __int128 v26; // [rsp+48h] [rbp-18h] BYREF
  __int64 v27; // [rsp+58h] [rbp-8h]
  struct MSMSEC_INTF_CONTEXT *v30; // [rsp+B8h] [rbp+58h] BYREF

  v30 = 0;
  v27 = 0;
  v25 = 0;
  v23 = 0;
  v24 = 0;
  v26 = 0;
  v8 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 110, WPP_20060763357235bdafa6f501eee46e60_Traceguids);
  *a3 = 0;
  *a4 = 0;
  v9 = PreCallbackActions(a1, a2, &v30, &v25, (struct _AUTHMGR_LOCK_STATE *)&v26);
  MSMSecMemory = v9;
  if ( !v9 )
  {
    v12 = v25;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        112,
        WPP_20060763357235bdafa6f501eee46e60_Traceguids,
        *((unsigned int *)v25 + 78));
    v13 = v30;
    TraceAdapterId(*((_DWORD *)v30 + 624), ">>> Locking >>>");
    AcquireWriteLock(v13, (char *)v13 + 2512, "AuthMgrOneXQueryParams", 1254);
    v14 = (void *)*((_QWORD *)v13 + 328);
    TraceAdapterId(*((_DWORD *)v13 + 624), "<<< Unlocking <<<");
    ReleaseWriteLock(v13, (char *)v13 + 2512, "AuthMgrOneXQueryParams", 1256);
    v15 = (void *)*((_QWORD *)v12 + 4);
    v16 = (unsigned int (*)(void *, void *, unsigned int *, void **))*((_QWORD *)v12 + 29);
    v17 = (void (*)(void *))*((_QWORD *)v12 + 5);
    TracePortId(*((_DWORD *)v12 + 78), "<<< Unlocking <<<");
    ReleaseWriteLock(v12, (char *)v12 + 320, "AuthMgrOneXQueryParams", 1264);
    v18 = *((_DWORD *)v12 + 78);
    *((_QWORD *)&v26 + 1) = 0;
    TracePortId(v18, "<<< Derefing <<<");
    SecMgrDerefPortEx(v12, "AuthMgrOneXQueryParams", 1268);
    TraceAdapterId(*((_DWORD *)v30 + 624), "<<< Derefing <<<");
    SecMgrDerefAdapterEx(v30, "AuthMgrOneXQueryParams", 1272);
    DWORD1(v26) = 0;
    v19 = MSMGetGlobalParams(v15, v14, &v24, v16, v17);
    v20 = v24;
    MSMSecMemory = v19;
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 113, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v19);
      goto LABEL_23;
    }
    v21 = *(unsigned int *)v24;
    if ( (_DWORD)v21 )
    {
      MSMSecMemory = AllocateMSMSecMemory(v21);
      if ( MSMSecMemory )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            114,
            WPP_20060763357235bdafa6f501eee46e60_Traceguids,
            MSMSecMemory);
        v8 = v23;
LABEL_23:
        PostCallbackActions(a1, v30, v12, (struct _AUTHMGR_LOCK_STATE *)&v26);
        if ( v20 )
        {
          FreeRawData(v20);
          FreeMSMSecMemory(&v24);
        }
        if ( !MSMSecMemory )
          goto LABEL_29;
        goto LABEL_26;
      }
      v8 = v23;
      memcpy_0(v23, *((const void **)v20 + 1), *(unsigned int *)v20);
    }
    *a4 = v8;
    *a3 = *(_DWORD *)v20;
    goto LABEL_23;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 111, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v9);
LABEL_26:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    FreeMSMSecMemory(&v23);
LABEL_29:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x100) != 0 )
    WPP_SF_d(v11[7], 115, WPP_20060763357235bdafa6f501eee46e60_Traceguids, MSMSecMemory);
  return MSMSecMemory;
}

```

## disassembly

```asm
0x180028750  mov     [rsp-38h+arg_8], rbx
0x180028755  mov     [rsp-38h+arg_10], r8
0x18002875a  mov     [rsp-38h+arg_0], rcx
0x18002875f  push    rbp
0x180028760  push    rsi
0x180028761  push    rdi
0x180028762  push    r12
0x180028764  push    r13
0x180028766  push    r14
0x180028768  push    r15
0x18002876a  mov     rbp, rsp
0x18002876d  sub     rsp, 60h
0x180028771  xor     r14d, r14d
0x180028774  xorps   xmm0, xmm0
0x180028777  xor     eax, eax
0x180028779  mov     [rbp+arg_18], r14
0x18002877d  mov     [rbp+var_8], rax
0x180028781  mov     r12, r9
0x180028784  mov     rbx, r8
0x180028787  mov     [rbp+var_20], r14
0x18002878b  mov     rsi, rdx
0x18002878e  mov     [rbp+var_30], r14
0x180028792  mov     rdi, rcx
0x180028795  mov     [rbp+var_28], r14
0x180028799  movups  [rbp+var_18], xmm0
0x18002879d  mov     r15d, r14d
0x1800287a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287a7  lea     r13, WPP_GLOBAL_Control
0x1800287ae  cmp     rcx, r13
0x1800287b1  jz      short loc_1800287CF
0x1800287b3  test    dword ptr [rcx+44h], 100h
0x1800287ba  jz      short loc_1800287CF
0x1800287bc  mov     rcx, [rcx+38h]
0x1800287c0  lea     edx, [rax+6Eh]
0x1800287c3  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x1800287ca  call    WPP_SF_
0x1800287cf  lea     rax, [rbp+var_18]
0x1800287d3  mov     [rbx], r14d
0x1800287d6  lea     r9, [rbp+var_20]; struct MSMSEC_PORT_CONTEXT **
0x1800287da  mov     [rsp+60h+var_40], rax; struct _AUTHMGR_LOCK_STATE *
0x1800287df  lea     r8, [rbp+arg_18]; struct MSMSEC_INTF_CONTEXT **
0x1800287e3  mov     [r12], r14
0x1800287e7  mov     rdx, rsi; void *
0x1800287ea  mov     rcx, rdi; void *
0x1800287ed  call    ?PreCallbackActions@@YAKPEAX0PEAPEAUMSMSEC_INTF_CONTEXT@@PEAPEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z; PreCallbackActions(void *,void *,MSMSEC_INTF_CONTEXT * *,MSMSEC_PORT_CONTEXT * *,_AUTHMGR_LOCK_STATE *)
0x1800287f2  mov     ebx, eax
0x1800287f4  test    eax, eax
0x1800287f6  jz      short loc_18002882F
0x1800287f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287ff  cmp     rcx, r13
0x180028802  jz      loc_180028A79
0x180028808  test    byte ptr [rcx+44h], 1
0x18002880c  jz      loc_180028A79
0x180028812  mov     rcx, [rcx+38h]
0x180028816  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002881d  mov     edx, 6Fh ; 'o'
0x180028822  mov     r9d, eax
0x180028825  call    WPP_SF_d
0x18002882a  jmp     loc_180028A72
0x18002882f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028836  lea     rax, WPP_GLOBAL_Control
0x18002883d  mov     r13, [rbp+var_20]
0x180028841  cmp     rcx, rax
0x180028844  jz      short loc_180028868
0x180028846  test    byte ptr [rcx+44h], 20h
0x18002884a  jz      short loc_180028868
0x18002884c  mov     r9d, [r13+138h]
0x180028853  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002885a  mov     rcx, [rcx+38h]
0x18002885e  mov     edx, 70h ; 'p'
0x180028863  call    WPP_SF_d
0x180028868  mov     rdi, [rbp+arg_18]
0x18002886c  lea     rdx, aLocking; ">>> Locking >>>"
0x180028873  mov     ecx, [rdi+9C0h]; unsigned int
0x180028879  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18002887e  lea     rbx, [rdi+9D0h]
0x180028885  mov     r9d, 4E6h
0x18002888b  mov     rdx, rbx
0x18002888e  lea     r8, aAuthmgronexque_0; "AuthMgrOneXQueryParams"
0x180028895  mov     rcx, rdi
0x180028898  call    cs:__imp_AcquireWriteLock
0x18002889f  nop     dword ptr [rax+rax+00h]
0x1800288a4  mov     ecx, [rdi+9C0h]; unsigned int
0x1800288aa  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800288b1  mov     r14, [rdi+0A40h]
0x1800288b8  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800288bd  mov     r9d, 4E8h
0x1800288c3  lea     r8, aAuthmgronexque_0; "AuthMgrOneXQueryParams"
0x1800288ca  mov     rdx, rbx
0x1800288cd  mov     rcx, rdi
0x1800288d0  call    cs:__imp_ReleaseWriteLock
0x1800288d7  nop     dword ptr [rax+rax+00h]
0x1800288dc  mov     ecx, [r13+138h]; unsigned int
0x1800288e3  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800288ea  mov     rsi, [r13+20h]
0x1800288ee  mov     rdi, [r13+0E8h]
0x1800288f5  mov     rbx, [r13+28h]
0x1800288f9  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x1800288fe  lea     rdx, [r13+140h]
0x180028905  mov     r9d, 4F0h
0x18002890b  lea     r8, aAuthmgronexque_0; "AuthMgrOneXQueryParams"
0x180028912  mov     rcx, r13
0x180028915  call    cs:__imp_ReleaseWriteLock
0x18002891c  nop     dword ptr [rax+rax+00h]
0x180028921  mov     ecx, [r13+138h]; unsigned int
0x180028928  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18002892f  mov     qword ptr [rbp+var_18+8], r15
0x180028933  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180028938  mov     r8d, 4F4h; int
0x18002893e  lea     rdx, aAuthmgronexque_0; "AuthMgrOneXQueryParams"
0x180028945  mov     rcx, r13; struct MSMSEC_PORT_CONTEXT *
0x180028948  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x18002894d  mov     rcx, [rbp+arg_18]
0x180028951  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180028958  mov     ecx, [rcx+9C0h]; unsigned int
0x18002895e  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180028963  mov     rcx, [rbp+arg_18]; struct MSMSEC_INTF_CONTEXT *
0x180028967  lea     rdx, aAuthmgronexque_0; "AuthMgrOneXQueryParams"
0x18002896e  mov     r8d, 4F8h; int
0x180028974  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180028979  mov     r9, rdi; unsigned int (*)(void *, void *, unsigned int *, void **)
0x18002897c  mov     dword ptr [rbp+var_18+4], r15d
0x180028980  lea     r8, [rbp+var_28]; struct MSMSEC_GLOBAL_PARAMS **
0x180028984  mov     [rsp+60h+var_40], rbx; void (*)(void *)
0x180028989  mov     rdx, r14; void *
0x18002898c  mov     rcx, rsi; void *
0x18002898f  call    ?MSMGetGlobalParams@@YAKPEAX0PEAPEAUMSMSEC_GLOBAL_PARAMS@@P6AK00PEAKPEAPEAX@ZP6AX0@Z@Z; MSMGetGlobalParams(void *,void *,MSMSEC_GLOBAL_PARAMS * *,ulong (*)(void *,void *,ulong *,void * *),void (*)(void *))
0x180028994  mov     rdi, [rbp+var_28]
0x180028998  mov     ebx, eax
0x18002899a  test    eax, eax
0x18002899c  jz      short loc_1800289D9
0x18002899e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289a5  lea     rax, WPP_GLOBAL_Control
0x1800289ac  cmp     rcx, rax
0x1800289af  jz      loc_180028A44
0x1800289b5  test    byte ptr [rcx+44h], 1
0x1800289b9  jz      loc_180028A44
0x1800289bf  mov     rcx, [rcx+38h]
0x1800289c3  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x1800289ca  mov     edx, 71h ; 'q'
0x1800289cf  mov     r9d, ebx
0x1800289d2  call    WPP_SF_d
0x1800289d7  jmp     short loc_180028A44
0x1800289d9  mov     ecx, [rdi]; dwBytes
0x1800289db  test    ecx, ecx
0x1800289dd  jz      short loc_180028A38
0x1800289df  lea     rdx, [rbp+var_30]
0x1800289e3  call    AllocateMSMSecMemory
0x1800289e8  mov     ebx, eax
0x1800289ea  test    eax, eax
0x1800289ec  jz      short loc_180028A25
0x1800289ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289f5  lea     rax, WPP_GLOBAL_Control
0x1800289fc  cmp     rcx, rax
0x1800289ff  jz      short loc_180028A1F
0x180028a01  test    byte ptr [rcx+44h], 1
0x180028a05  jz      short loc_180028A1F
0x180028a07  mov     rcx, [rcx+38h]
0x180028a0b  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180028a12  mov     edx, 72h ; 'r'
0x180028a17  mov     r9d, ebx
0x180028a1a  call    WPP_SF_d
0x180028a1f  mov     r15, [rbp+var_30]
0x180028a23  jmp     short loc_180028A44
0x180028a25  mov     r15, [rbp+var_30]
0x180028a29  mov     r8d, [rdi]; Size
0x180028a2c  mov     rcx, r15; void *
0x180028a2f  mov     rdx, [rdi+8]; Src
0x180028a33  call    memcpy_0
0x180028a38  mov     rcx, [rbp+arg_10]
0x180028a3c  mov     [r12], r15
0x180028a40  mov     eax, [rdi]
0x180028a42  mov     [rcx], eax
0x180028a44  mov     rdx, [rbp+arg_18]; struct MSMSEC_INTF_CONTEXT *
0x180028a48  lea     r9, [rbp+var_18]; struct _AUTHMGR_LOCK_STATE *
0x180028a4c  mov     rcx, [rbp+arg_0]; void *
0x180028a50  mov     r8, r13; struct MSMSEC_PORT_CONTEXT *
0x180028a53  call    ?PostCallbackActions@@YAKPEAXPEAUMSMSEC_INTF_CONTEXT@@PEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z; PostCallbackActions(void *,MSMSEC_INTF_CONTEXT *,MSMSEC_PORT_CONTEXT *,_AUTHMGR_LOCK_STATE *)
0x180028a58  test    rdi, rdi
0x180028a5b  jz      short loc_180028A6E
0x180028a5d  mov     rcx, rdi
0x180028a60  call    FreeRawData
0x180028a65  lea     rcx, [rbp+var_28]
0x180028a69  call    FreeMSMSecMemory
0x180028a6e  test    ebx, ebx
0x180028a70  jz      short loc_180028A87
0x180028a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a79  test    r15, r15
0x180028a7c  jz      short loc_180028A8E
0x180028a7e  lea     rcx, [rbp+var_30]
0x180028a82  call    FreeMSMSecMemory
0x180028a87  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a8e  lea     rax, WPP_GLOBAL_Control
0x180028a95  cmp     rcx, rax
0x180028a98  jz      short loc_180028ABB
0x180028a9a  test    dword ptr [rcx+44h], 100h
0x180028aa1  jz      short loc_180028ABB
0x180028aa3  mov     rcx, [rcx+38h]
0x180028aa7  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180028aae  mov     edx, 73h ; 's'
0x180028ab3  mov     r9d, ebx
0x180028ab6  call    WPP_SF_d
0x180028abb  mov     eax, ebx
0x180028abd  mov     rbx, [rsp+60h+arg_8]
0x180028ac5  add     rsp, 60h
0x180028ac9  pop     r15
0x180028acb  pop     r14
0x180028acd  pop     r13
0x180028acf  pop     r12
0x180028ad1  pop     rdi
0x180028ad2  pop     rsi
0x180028ad3  pop     rbp
0x180028ad4  retn
```
