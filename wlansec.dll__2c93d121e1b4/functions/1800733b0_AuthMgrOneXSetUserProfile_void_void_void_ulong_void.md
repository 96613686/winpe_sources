# AuthMgrOneXSetUserProfile(void *,void *,void *,ulong,void *)

- ea: `0x1800733b0`
- end: `0x18007374d`
- name: `?AuthMgrOneXSetUserProfile@@YAKPEAX00K0@Z`
- size: `925`
- prototype: `unsigned int __fastcall(void *, void *, void *, SIZE_T dwBytes, void *Src)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000c730`
- `0x18000d5e4`
- `0x180013600`
- `0x180013bc0`
- `0x1800169c0`
- `0x18002a638`
- `0x18002b170`
- `0x18002bb08`
- `0x18002c21c`
- `0x180039338`
- `0x18003ac5c`
- `0x180044554`
- `0x1800733b0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18007352b`
- `MobileNetworking!ReleaseWriteLock` at `0x180073579`
- `MobileNetworking!ReleaseWriteLock` at `0x18007352b`
- `MobileNetworking!ReleaseWriteLock` at `0x180073579`
- `MobileNetworking!AcquireWriteLock` at `0x1800734ef`
- `MobileNetworking!AcquireWriteLock` at `0x1800734ef`

## pseudocode

```c
__int64 __fastcall AuthMgrOneXSetUserProfile(void *a1, void *a2, void *a3, SIZE_T dwBytes, void *Src)
{
  size_t v5; // rsi
  void *v9; // r14
  unsigned int v10; // eax
  unsigned int MSMSecMemory; // ebx
  PVOID *v12; // rcx
  struct MSMSEC_PORT_CONTEXT *v13; // r15
  struct MSMSEC_INTF_CONTEXT *v14; // rdi
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int (*v17)(void *, void *, void *, unsigned int *, void **); // rdi
  void (*v18)(void *); // rbx
  unsigned int v19; // ecx
  unsigned int v20; // eax
  struct MSMSEC_USER_PROFILE *v21; // rdi
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  unsigned int (*v24)(void *, void *, void *, unsigned int, void *); // rax
  struct MSMSEC_PORT_CONTEXT *v25; // r8
  void *v26; // rcx
  struct MSMSEC_INTF_CONTEXT *v28; // [rsp+30h] [rbp-41h] BYREF
  struct MSMSEC_USER_PROFILE *v29; // [rsp+38h] [rbp-39h] BYREF
  struct MSMSEC_PORT_CONTEXT *v30; // [rsp+40h] [rbp-31h] BYREF
  void *v31; // [rsp+48h] [rbp-29h]
  void *v32; // [rsp+50h] [rbp-21h]
  unsigned int (*v33)(void *, void *, void *, unsigned int, void *); // [rsp+58h] [rbp-19h]
  __int128 v34; // [rsp+60h] [rbp-11h] BYREF
  __int64 v35; // [rsp+70h] [rbp-1h]

  v5 = (unsigned int)dwBytes;
  v28 = 0;
  v35 = 0;
  v30 = 0;
  v29 = 0;
  v31 = 0;
  v34 = 0;
  v9 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 90, WPP_20060763357235bdafa6f501eee46e60_Traceguids);
  v10 = PreCallbackActions(a1, a2, &v28, &v30, (struct _AUTHMGR_LOCK_STATE *)&v34);
  MSMSecMemory = v10;
  if ( !v10 )
  {
    v13 = v30;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        92,
        WPP_20060763357235bdafa6f501eee46e60_Traceguids,
        *((unsigned int *)v30 + 78));
    v14 = v28;
    TraceAdapterId(*((_DWORD *)v28 + 624), ">>> Locking >>>");
    AcquireWriteLock(v14, (char *)v14 + 2512, "AuthMgrOneXSetUserProfile", 1039);
    v15 = *((_DWORD *)v14 + 624);
    v30 = (struct MSMSEC_PORT_CONTEXT *)*((_QWORD *)v14 + 328);
    TraceAdapterId(v15, "<<< Unlocking <<<");
    ReleaseWriteLock(v14, (char *)v14 + 2512, "AuthMgrOneXSetUserProfile", 1041);
    v16 = *((_DWORD *)v13 + 78);
    v17 = (unsigned int (*)(void *, void *, void *, unsigned int *, void **))*((_QWORD *)v13 + 7);
    v18 = (void (*)(void *))*((_QWORD *)v13 + 5);
    v32 = (void *)*((_QWORD *)v13 + 4);
    v33 = (unsigned int (*)(void *, void *, void *, unsigned int, void *))*((_QWORD *)v13 + 6);
    TracePortId(v16, "<<< Unlocking <<<");
    ReleaseWriteLock(v13, (char *)v13 + 320, "AuthMgrOneXSetUserProfile", 1050);
    v19 = *((_DWORD *)v13 + 78);
    *((_QWORD *)&v34 + 1) = 0;
    TracePortId(v19, "<<< Derefing <<<");
    SecMgrDerefPortEx(v13, "AuthMgrOneXSetUserProfile", 1054);
    TraceAdapterId(*((_DWORD *)v28 + 624), "<<< Derefing <<<");
    SecMgrDerefAdapterEx(v28, "AuthMgrOneXSetUserProfile", 1058);
    DWORD1(v34) = 0;
    v20 = MSMGetUserProfile(v32, a3, v30, &v29, v17, v18);
    v21 = v29;
    MSMSecMemory = v20;
    if ( v20 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v23 = 93;
LABEL_25:
        WPP_SF_d(v22[7], v23, WPP_20060763357235bdafa6f501eee46e60_Traceguids, MSMSecMemory);
        goto LABEL_26;
      }
      goto LABEL_26;
    }
    if ( (_DWORD)v5 )
    {
      MSMSecMemory = AllocateMSMSecMemory((unsigned int)v5);
      if ( MSMSecMemory )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v23 = 94;
          goto LABEL_25;
        }
LABEL_26:
        PostCallbackActions(a1, v28, v13, (struct _AUTHMGR_LOCK_STATE *)&v34);
        if ( v21 )
          FreeMSMSecUserProfile(&v29);
        goto LABEL_28;
      }
      v9 = v31;
      memcpy_0(v31, Src, v5);
    }
    FreeRawData(v21);
    v24 = v33;
    v25 = v30;
    v26 = v32;
    *((_QWORD *)v21 + 1) = v9;
    *(_DWORD *)v21 = v5;
    MSMSecMemory = MSMSetUserProfile(v26, a3, v25, v21, v24);
    if ( MSMSecMemory )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v23 = 95;
        goto LABEL_25;
      }
    }
    goto LABEL_26;
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return MSMSecMemory;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 91, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v10);
LABEL_28:
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x100) != 0 )
    WPP_SF_d(v12[7], 96, WPP_20060763357235bdafa6f501eee46e60_Traceguids, MSMSecMemory);
  return MSMSecMemory;
}

```

## disassembly

```asm
0x1800733b0  push    rbp
0x1800733b2  push    rbx
0x1800733b3  push    rsi
0x1800733b4  push    rdi
0x1800733b5  push    r12
0x1800733b7  push    r13
0x1800733b9  push    r14
0x1800733bb  push    r15
0x1800733bd  lea     rbp, [rsp-17h]
0x1800733c2  sub     rsp, 88h
0x1800733c9  xor     edi, edi
0x1800733cb  mov     esi, r9d
0x1800733ce  xor     eax, eax
0x1800733d0  mov     [rbp+4Fh+var_90], rdi
0x1800733d4  xorps   xmm0, xmm0
0x1800733d7  mov     [rbp+4Fh+var_50], rax
0x1800733db  mov     r13, r8
0x1800733de  mov     [rbp+4Fh+var_80], rdi
0x1800733e2  mov     rbx, rdx
0x1800733e5  mov     [rbp+4Fh+var_88], rdi
0x1800733e9  mov     r12, rcx
0x1800733ec  mov     [rbp+4Fh+var_78], rdi
0x1800733f0  movups  [rbp+4Fh+var_60], xmm0
0x1800733f4  mov     r14d, edi
0x1800733f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800733fe  lea     rax, WPP_GLOBAL_Control
0x180073405  cmp     rcx, rax
0x180073408  jz      short loc_180073426
0x18007340a  test    dword ptr [rcx+44h], 100h
0x180073411  jz      short loc_180073426
0x180073413  mov     rcx, [rcx+38h]
0x180073417  lea     edx, [rdi+5Ah]
0x18007341a  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180073421  call    WPP_SF_
0x180073426  lea     rax, [rbp+4Fh+var_60]
0x18007342a  mov     rdx, rbx; void *
0x18007342d  lea     r9, [rbp+4Fh+var_80]; struct MSMSEC_PORT_CONTEXT **
0x180073431  mov     [rsp+0C0h+var_A0], rax; struct _AUTHMGR_LOCK_STATE *
0x180073436  lea     r8, [rbp+4Fh+var_90]; struct MSMSEC_INTF_CONTEXT **
0x18007343a  mov     rcx, r12; void *
0x18007343d  call    ?PreCallbackActions@@YAKPEAX0PEAPEAUMSMSEC_INTF_CONTEXT@@PEAPEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z; PreCallbackActions(void *,void *,MSMSEC_INTF_CONTEXT * *,MSMSEC_PORT_CONTEXT * *,_AUTHMGR_LOCK_STATE *)
0x180073442  mov     ebx, eax
0x180073444  test    eax, eax
0x180073446  jz      short loc_180073486
0x180073448  mov     rcx, cs:WPP_GLOBAL_Control
0x18007344f  lea     rdi, WPP_GLOBAL_Control
0x180073456  cmp     rcx, rdi
0x180073459  jz      loc_180073736
0x18007345f  test    byte ptr [rcx+44h], 1
0x180073463  jz      loc_180073710
0x180073469  mov     rcx, [rcx+38h]
0x18007346d  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180073474  mov     edx, 5Bh ; '['
0x180073479  mov     r9d, eax
0x18007347c  call    WPP_SF_d
0x180073481  jmp     loc_180073709
0x180073486  mov     rcx, cs:WPP_GLOBAL_Control
0x18007348d  lea     rax, WPP_GLOBAL_Control
0x180073494  mov     r15, [rbp+4Fh+var_80]
0x180073498  cmp     rcx, rax
0x18007349b  jz      short loc_1800734BF
0x18007349d  test    byte ptr [rcx+44h], 20h
0x1800734a1  jz      short loc_1800734BF
0x1800734a3  mov     r9d, [r15+138h]
0x1800734aa  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x1800734b1  mov     rcx, [rcx+38h]
0x1800734b5  mov     edx, 5Ch ; '\'
0x1800734ba  call    WPP_SF_d
0x1800734bf  mov     rdi, [rbp+4Fh+var_90]
0x1800734c3  lea     rdx, aLocking; ">>> Locking >>>"
0x1800734ca  mov     ecx, [rdi+9C0h]; unsigned int
0x1800734d0  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800734d5  lea     rbx, [rdi+9D0h]
0x1800734dc  mov     r9d, 40Fh
0x1800734e2  mov     rdx, rbx
0x1800734e5  lea     r8, aAuthmgronexset; "AuthMgrOneXSetUserProfile"
0x1800734ec  mov     rcx, rdi
0x1800734ef  call    cs:__imp_AcquireWriteLock
0x1800734f6  nop     dword ptr [rax+rax+00h]
0x1800734fb  mov     rax, [rdi+0A40h]
0x180073502  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180073509  mov     ecx, [rdi+9C0h]; unsigned int
0x18007350f  mov     [rbp+4Fh+var_80], rax
0x180073513  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180073518  mov     r9d, 411h
0x18007351e  lea     r8, aAuthmgronexset; "AuthMgrOneXSetUserProfile"
0x180073525  mov     rdx, rbx
0x180073528  mov     rcx, rdi
0x18007352b  call    cs:__imp_ReleaseWriteLock
0x180073532  nop     dword ptr [rax+rax+00h]
0x180073537  mov     rax, [r15+20h]
0x18007353b  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180073542  mov     ecx, [r15+138h]; unsigned int
0x180073549  mov     rdi, [r15+38h]
0x18007354d  mov     rbx, [r15+28h]
0x180073551  mov     [rbp+4Fh+var_70], rax
0x180073555  mov     rax, [r15+30h]
0x180073559  mov     [rbp+4Fh+var_68], rax
0x18007355d  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180073562  lea     rdx, [r15+140h]
0x180073569  mov     r9d, 41Ah
0x18007356f  lea     r8, aAuthmgronexset; "AuthMgrOneXSetUserProfile"
0x180073576  mov     rcx, r15
0x180073579  call    cs:__imp_ReleaseWriteLock
0x180073580  nop     dword ptr [rax+rax+00h]
0x180073585  mov     ecx, [r15+138h]; unsigned int
0x18007358c  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180073593  mov     qword ptr [rbp+4Fh+var_60+8], r14
0x180073597  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x18007359c  mov     r8d, 41Eh; int
0x1800735a2  lea     rdx, aAuthmgronexset; "AuthMgrOneXSetUserProfile"
0x1800735a9  mov     rcx, r15; struct MSMSEC_PORT_CONTEXT *
0x1800735ac  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x1800735b1  mov     rcx, [rbp+4Fh+var_90]
0x1800735b5  lea     rdx, aDerefing; "<<< Derefing <<<"
0x1800735bc  mov     ecx, [rcx+9C0h]; unsigned int
0x1800735c2  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800735c7  mov     rcx, [rbp+4Fh+var_90]; struct MSMSEC_INTF_CONTEXT *
0x1800735cb  lea     rdx, aAuthmgronexset; "AuthMgrOneXSetUserProfile"
0x1800735d2  mov     r8d, 422h; int
0x1800735d8  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x1800735dd  mov     r8, [rbp+4Fh+var_80]; void *
0x1800735e1  lea     r9, [rbp+4Fh+var_88]; struct MSMSEC_USER_PROFILE **
0x1800735e5  mov     rcx, [rbp+4Fh+var_70]; void *
0x1800735e9  mov     rdx, r13; void *
0x1800735ec  mov     [rsp+0C0h+var_98], rbx; void (*)(void *)
0x1800735f1  mov     dword ptr [rbp+4Fh+var_60+4], r14d
0x1800735f5  mov     [rsp+0C0h+var_A0], rdi; unsigned int (*)(void *, void *, void *, unsigned int *, void **)
0x1800735fa  call    ?MSMGetUserProfile@@YAKPEAX00PEAPEAUMSMSEC_USER_PROFILE@@P6AK000PEAKPEAPEAX@ZP6AX0@Z@Z; MSMGetUserProfile(void *,void *,void *,MSMSEC_USER_PROFILE * *,ulong (*)(void *,void *,void *,ulong *,void * *),void (*)(void *))
0x1800735ff  mov     rdi, [rbp+4Fh+var_88]
0x180073603  mov     ebx, eax
0x180073605  test    eax, eax
0x180073607  jz      short loc_180073634
0x180073609  mov     rcx, cs:WPP_GLOBAL_Control
0x180073610  lea     rax, WPP_GLOBAL_Control
0x180073617  cmp     rcx, rax
0x18007361a  jz      loc_1800736E1
0x180073620  test    byte ptr [rcx+44h], 1
0x180073624  jz      loc_1800736E1
0x18007362a  mov     edx, 5Dh ; ']'
0x18007362f  jmp     loc_1800736CE
0x180073634  test    esi, esi
0x180073636  jz      short loc_180073680
0x180073638  lea     rdx, [rbp+4Fh+var_78]
0x18007363c  mov     ecx, esi; dwBytes
0x18007363e  call    AllocateMSMSecMemory
0x180073643  mov     ebx, eax
0x180073645  test    eax, eax
0x180073647  jz      short loc_18007366D
0x180073649  mov     rcx, cs:WPP_GLOBAL_Control
0x180073650  lea     rax, WPP_GLOBAL_Control
0x180073657  cmp     rcx, rax
0x18007365a  jz      loc_1800736E1
0x180073660  test    byte ptr [rcx+44h], 1
0x180073664  jz      short loc_1800736E1
0x180073666  mov     edx, 5Eh ; '^'
0x18007366b  jmp     short loc_1800736CE
0x18007366d  mov     r14, [rbp+4Fh+var_78]
0x180073671  mov     r8, rsi; Size
0x180073674  mov     rdx, [rbp+4Fh+Src]; Src
0x180073678  mov     rcx, r14; void *
0x18007367b  call    memcpy_0
0x180073680  mov     rcx, rdi
0x180073683  call    FreeRawData
0x180073688  mov     rax, [rbp+4Fh+var_68]
0x18007368c  mov     r9, rdi; struct MSMSEC_USER_PROFILE *
0x18007368f  mov     r8, [rbp+4Fh+var_80]; void *
0x180073693  mov     rdx, r13; void *
0x180073696  mov     rcx, [rbp+4Fh+var_70]; void *
0x18007369a  mov     [rdi+8], r14
0x18007369e  mov     [rsp+0C0h+var_A0], rax; unsigned int (*)(void *, void *, void *, unsigned int, void *)
0x1800736a3  mov     [rdi], esi
0x1800736a5  call    ?MSMSetUserProfile@@YAKPEAX00PEAUMSMSEC_USER_PROFILE@@P6AK000K0@Z@Z; MSMSetUserProfile(void *,void *,void *,MSMSEC_USER_PROFILE *,ulong (*)(void *,void *,void *,ulong,void *))
0x1800736aa  mov     ebx, eax
0x1800736ac  test    eax, eax
0x1800736ae  jz      short loc_1800736E1
0x1800736b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800736b7  lea     rax, WPP_GLOBAL_Control
0x1800736be  cmp     rcx, rax
0x1800736c1  jz      short loc_1800736E1
0x1800736c3  test    byte ptr [rcx+44h], 1
0x1800736c7  jz      short loc_1800736E1
0x1800736c9  mov     edx, 5Fh ; '_'
0x1800736ce  mov     rcx, [rcx+38h]
0x1800736d2  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x1800736d9  mov     r9d, ebx
0x1800736dc  call    WPP_SF_d
0x1800736e1  mov     rdx, [rbp+4Fh+var_90]; struct MSMSEC_INTF_CONTEXT *
0x1800736e5  lea     r9, [rbp+4Fh+var_60]; struct _AUTHMGR_LOCK_STATE *
0x1800736e9  mov     r8, r15; struct MSMSEC_PORT_CONTEXT *
0x1800736ec  mov     rcx, r12; void *
0x1800736ef  call    ?PostCallbackActions@@YAKPEAXPEAUMSMSEC_INTF_CONTEXT@@PEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z; PostCallbackActions(void *,MSMSEC_INTF_CONTEXT *,MSMSEC_PORT_CONTEXT *,_AUTHMGR_LOCK_STATE *)
0x1800736f4  test    rdi, rdi
0x1800736f7  jz      short loc_180073702
0x1800736f9  lea     rcx, [rbp+4Fh+var_88]
0x1800736fd  call    FreeMSMSecUserProfile
0x180073702  lea     rdi, WPP_GLOBAL_Control
0x180073709  mov     rcx, cs:WPP_GLOBAL_Control
0x180073710  cmp     rcx, rdi
0x180073713  jz      short loc_180073736
0x180073715  test    dword ptr [rcx+44h], 100h
0x18007371c  jz      short loc_180073736
0x18007371e  mov     rcx, [rcx+38h]
0x180073722  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180073729  mov     edx, 60h ; '`'
0x18007372e  mov     r9d, ebx
0x180073731  call    WPP_SF_d
0x180073736  mov     eax, ebx
0x180073738  add     rsp, 88h
0x18007373f  pop     r15
0x180073741  pop     r14
0x180073743  pop     r13
0x180073745  pop     r12
0x180073747  pop     rdi
0x180073748  pop     rsi
0x180073749  pop     rbx
0x18007374a  pop     rbp
0x18007374b  retn
```
