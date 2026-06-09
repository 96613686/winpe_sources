# AuthMgrOneXSetConnectionProfile(void *,void *,ulong,void *)

- ea: `0x180072f00`
- end: `0x1800733a4`
- name: `?AuthMgrOneXSetConnectionProfile@@YAKPEAX0K0@Z`
- size: `1188`
- prototype: `unsigned int __fastcall(void *, void *, SIZE_T dwBytes, void *Src)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x1800045b8`
- `0x18000892c`
- `0x180008998`
- `0x18000c730`
- `0x18000d5e4`
- `0x18000e620`
- `0x180013600`
- `0x180013bc0`
- `0x1800169c0`
- `0x18002a638`
- `0x18002b170`
- `0x18002bb08`
- `0x180038914`
- `0x180038a7c`
- `0x180044554`
- `0x180072f00`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18007317e`
- `MobileNetworking!ReleaseWriteLock` at `0x1800731cc`
- `MobileNetworking!ReleaseWriteLock` at `0x18007317e`
- `MobileNetworking!ReleaseWriteLock` at `0x1800731cc`
- `MobileNetworking!AcquireWriteLock` at `0x1800730e2`
- `MobileNetworking!AcquireWriteLock` at `0x1800730e2`

## pseudocode

```c
__int64 __fastcall AuthMgrOneXSetConnectionProfile(void *a1, void *a2, SIZE_T dwBytes, void *Src)
{
  size_t v4; // r14
  struct DOT11_MSMSEC_CONNECTION_PROFILE *v8; // rsi
  unsigned int v9; // eax
  unsigned int v10; // ebx
  struct MSMSEC_PORT_CONTEXT *v11; // r15
  unsigned int MSMSecMemory; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  void *v15; // rbx
  struct MSMSEC_INTF_CONTEXT *v16; // rsi
  __int64 v17; // rcx
  __int64 v18; // rax
  void *v19; // rcx
  unsigned int v20; // ecx
  unsigned int (*v21)(void *, void *, struct DOT11_MSMSEC_CONNECTION_PROFILE **); // rdi
  void (*v22)(void *); // rbx
  unsigned int v23; // ecx
  unsigned int v24; // eax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  void *v27; // rdi
  unsigned int (*v28)(void *, void *, struct DOT11_MSMSEC_CONNECTION_PROFILE *, int); // r9
  struct MSMSEC_PORT_CONTEXT *v29; // rdx
  void *v30; // rcx
  struct DOT11_MSMSEC_CONNECTION_PROFILE *v32; // [rsp+30h] [rbp-49h] BYREF
  void *v33; // [rsp+38h] [rbp-41h] BYREF
  struct MSMSEC_PORT_CONTEXT *v34; // [rsp+40h] [rbp-39h] BYREF
  void *v35; // [rsp+48h] [rbp-31h] BYREF
  struct MSMSEC_INTF_CONTEXT *v36; // [rsp+50h] [rbp-29h] BYREF
  void *v37; // [rsp+58h] [rbp-21h]
  void *v38; // [rsp+60h] [rbp-19h]
  __int128 v39; // [rsp+68h] [rbp-11h] BYREF
  __int64 v40; // [rsp+78h] [rbp-1h]
  unsigned int (*v41)(void *, void *, struct DOT11_MSMSEC_CONNECTION_PROFILE *, int); // [rsp+80h] [rbp+7h]

  v4 = (unsigned int)dwBytes;
  v36 = 0;
  v40 = 0;
  v34 = 0;
  v32 = 0;
  v37 = 0;
  v39 = 0;
  v8 = 0;
  v33 = 0;
  v35 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 81, WPP_20060763357235bdafa6f501eee46e60_Traceguids);
  v9 = PreCallbackActions(a1, a2, &v36, &v34, (struct _AUTHMGR_LOCK_STATE *)&v39);
  v10 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 82, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v9);
    goto LABEL_36;
  }
  v11 = v34;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      83,
      WPP_20060763357235bdafa6f501eee46e60_Traceguids,
      *((unsigned int *)v34 + 78));
  MSMSecMemory = AllocateMSMSecMemory((unsigned int)v4);
  v10 = MSMSecMemory;
  if ( MSMSecMemory )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v14 = 84;
LABEL_15:
      WPP_SF_d(v13[7], v14, WPP_20060763357235bdafa6f501eee46e60_Traceguids, MSMSecMemory);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  memcpy_0(v33, Src, v4);
  MSMSecMemory = AllocateMSMSecMemory((unsigned int)v4);
  v10 = MSMSecMemory;
  if ( !MSMSecMemory )
  {
    v15 = v35;
    memcpy_0(v35, Src, v4);
    v16 = v36;
    TraceAdapterId(*((_DWORD *)v36 + 624), ">>> Locking >>>");
    AcquireWriteLock(v16, (char *)v16 + 2512, "AuthMgrOneXSetConnectionProfile", 936);
    v17 = *((_QWORD *)v16 + 348) + 40LL;
    v34 = (struct MSMSEC_PORT_CONTEXT *)*((_QWORD *)v16 + 328);
    FreeRawData(v17);
    FreeRawData(*((_QWORD *)v16 + 349) + 40LL);
    v18 = *((_QWORD *)v16 + 348);
    v19 = v33;
    v33 = 0;
    v35 = 0;
    *(_QWORD *)(v18 + 48) = v19;
    *(_DWORD *)(*((_QWORD *)v16 + 348) + 40LL) = v4;
    *(_QWORD *)(*((_QWORD *)v16 + 349) + 48LL) = v15;
    *(_DWORD *)(*((_QWORD *)v16 + 349) + 40LL) = v4;
    TraceAdapterId(*((_DWORD *)v16 + 624), "<<< Unlocking <<<");
    ReleaseWriteLock(v16, (char *)v16 + 2512, "AuthMgrOneXSetConnectionProfile", 953);
    v20 = *((_DWORD *)v11 + 78);
    v21 = (unsigned int (*)(void *, void *, struct DOT11_MSMSEC_CONNECTION_PROFILE **))*((_QWORD *)v11 + 9);
    v22 = (void (*)(void *))*((_QWORD *)v11 + 5);
    v38 = (void *)*((_QWORD *)v11 + 4);
    v41 = (unsigned int (*)(void *, void *, struct DOT11_MSMSEC_CONNECTION_PROFILE *, int))*((_QWORD *)v11 + 8);
    TracePortId(v20, "<<< Unlocking <<<");
    ReleaseWriteLock(v11, (char *)v11 + 320, "AuthMgrOneXSetConnectionProfile", 962);
    v23 = *((_DWORD *)v11 + 78);
    *((_QWORD *)&v39 + 1) = 0;
    TracePortId(v23, "<<< Derefing <<<");
    SecMgrDerefPortEx(v11, "AuthMgrOneXSetConnectionProfile", 966);
    TraceAdapterId(*((_DWORD *)v16 + 624), "<<< Derefing <<<");
    SecMgrDerefAdapterEx(v16, "AuthMgrOneXSetConnectionProfile", 970);
    DWORD1(v39) = 0;
    v24 = MSMGetConnectionProfile(v38, v34, &v32, v21, v22);
    v10 = v24;
    if ( v24 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_25;
      v26 = 86;
    }
    else
    {
      v24 = AllocateMSMSecMemory((unsigned int)v4);
      v10 = v24;
      if ( !v24 )
      {
        v27 = v37;
        memcpy_0(v37, Src, v4);
        v8 = v32;
        FreeRawData((char *)v32 + 40);
        v28 = v41;
        v29 = v34;
        v30 = v38;
        *((_QWORD *)v8 + 6) = v27;
        *((_DWORD *)v8 + 10) = v4;
        MSMSecMemory = MSMSetConnectionProfile(v30, v29, v8, v28);
        v10 = MSMSecMemory;
        if ( MSMSecMemory )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            v14 = 88;
            goto LABEL_15;
          }
        }
        goto LABEL_34;
      }
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
LABEL_25:
        v8 = v32;
        goto LABEL_34;
      }
      v26 = 87;
    }
    WPP_SF_d(v25[7], v26, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v24);
    goto LABEL_25;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v14 = 85;
    goto LABEL_15;
  }
LABEL_34:
  PostCallbackActions(a1, v36, v11, (struct _AUTHMGR_LOCK_STATE *)&v39);
  if ( v8 )
    FreeMSMSecConfig(&v32);
LABEL_36:
  FreeMSMSecMemory(&v33);
  FreeMSMSecMemory(&v35);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 89, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180072f00  mov     [rsp-8+arg_0], rcx
0x180072f05  push    rbp
0x180072f06  push    rbx
0x180072f07  push    rsi
0x180072f08  push    rdi
0x180072f09  push    r12
0x180072f0b  push    r13
0x180072f0d  push    r14
0x180072f0f  push    r15
0x180072f11  lea     rbp, [rsp-1Fh]
0x180072f16  sub     rsp, 98h
0x180072f1d  xor     r15d, r15d
0x180072f20  mov     r14d, r8d
0x180072f23  xor     eax, eax
0x180072f25  mov     [rbp+57h+var_80], r15
0x180072f29  xorps   xmm0, xmm0
0x180072f2c  mov     [rbp+57h+var_58], rax
0x180072f30  mov     r13, r9
0x180072f33  mov     [rbp+57h+var_90], r15
0x180072f37  mov     rdi, rdx
0x180072f3a  mov     [rbp+57h+var_A0], r15
0x180072f3e  mov     rbx, rcx
0x180072f41  mov     [rbp+57h+var_78], r15
0x180072f45  movups  [rbp+57h+var_68], xmm0
0x180072f49  mov     esi, r15d
0x180072f4c  mov     [rbp+57h+var_98], r15
0x180072f50  mov     [rbp+57h+var_88], r15
0x180072f54  mov     rcx, cs:WPP_GLOBAL_Control
0x180072f5b  lea     r12, WPP_GLOBAL_Control
0x180072f62  cmp     rcx, r12
0x180072f65  jz      short loc_180072F83
0x180072f67  test    dword ptr [rcx+44h], 100h
0x180072f6e  jz      short loc_180072F83
0x180072f70  mov     rcx, [rcx+38h]
0x180072f74  lea     edx, [rax+51h]
0x180072f77  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180072f7e  call    WPP_SF_
0x180072f83  lea     rax, [rbp+57h+var_68]
0x180072f87  mov     rdx, rdi; void *
0x180072f8a  lea     r9, [rbp+57h+var_90]; struct MSMSEC_PORT_CONTEXT **
0x180072f8e  mov     [rsp+0D0h+var_B0], rax; struct _AUTHMGR_LOCK_STATE *
0x180072f93  lea     r8, [rbp+57h+var_80]; struct MSMSEC_INTF_CONTEXT **
0x180072f97  mov     rcx, rbx; void *
0x180072f9a  call    ?PreCallbackActions@@YAKPEAX0PEAPEAUMSMSEC_INTF_CONTEXT@@PEAPEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z; PreCallbackActions(void *,void *,MSMSEC_INTF_CONTEXT * *,MSMSEC_PORT_CONTEXT * *,_AUTHMGR_LOCK_STATE *)
0x180072f9f  mov     ebx, eax
0x180072fa1  test    eax, eax
0x180072fa3  jz      short loc_180072FDC
0x180072fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180072fac  cmp     rcx, r12
0x180072faf  jz      loc_18007334E
0x180072fb5  test    byte ptr [rcx+44h], 1
0x180072fb9  jz      loc_18007334E
0x180072fbf  mov     rcx, [rcx+38h]
0x180072fc3  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180072fca  mov     edx, 52h ; 'R'
0x180072fcf  mov     r9d, eax
0x180072fd2  call    WPP_SF_d
0x180072fd7  jmp     loc_18007334E
0x180072fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180072fe3  mov     r15, [rbp+57h+var_90]
0x180072fe7  cmp     rcx, r12
0x180072fea  jz      short loc_18007300E
0x180072fec  test    byte ptr [rcx+44h], 20h
0x180072ff0  jz      short loc_18007300E
0x180072ff2  mov     r9d, [r15+138h]
0x180072ff9  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180073000  mov     rcx, [rcx+38h]
0x180073004  mov     edx, 53h ; 'S'
0x180073009  call    WPP_SF_d
0x18007300e  lea     rdx, [rbp+57h+var_98]
0x180073012  mov     ecx, r14d; dwBytes
0x180073015  call    AllocateMSMSecMemory
0x18007301a  mov     ebx, eax
0x18007301c  test    eax, eax
0x18007301e  jz      short loc_180073057
0x180073020  mov     rcx, cs:WPP_GLOBAL_Control
0x180073027  cmp     rcx, r12
0x18007302a  jz      loc_18007332C
0x180073030  test    byte ptr [rcx+44h], 1
0x180073034  jz      loc_18007332C
0x18007303a  mov     edx, 54h ; 'T'
0x18007303f  mov     rcx, [rcx+38h]
0x180073043  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18007304a  mov     r9d, eax
0x18007304d  call    WPP_SF_d
0x180073052  jmp     loc_18007332C
0x180073057  mov     rcx, [rbp+57h+var_98]; void *
0x18007305b  mov     r8, r14; Size
0x18007305e  mov     rdx, r13; Src
0x180073061  call    memcpy_0
0x180073066  lea     rdx, [rbp+57h+var_88]
0x18007306a  mov     ecx, r14d; dwBytes
0x18007306d  call    AllocateMSMSecMemory
0x180073072  mov     ebx, eax
0x180073074  test    eax, eax
0x180073076  jz      short loc_1800730A0
0x180073078  mov     rcx, cs:WPP_GLOBAL_Control
0x18007307f  lea     r12, WPP_GLOBAL_Control
0x180073086  cmp     rcx, r12
0x180073089  jz      loc_18007332C
0x18007308f  test    byte ptr [rcx+44h], 1
0x180073093  jz      loc_18007332C
0x180073099  mov     edx, 55h ; 'U'
0x18007309e  jmp     short loc_18007303F
0x1800730a0  mov     rbx, [rbp+57h+var_88]
0x1800730a4  mov     r8, r14; Size
0x1800730a7  mov     rcx, rbx; void *
0x1800730aa  mov     rdx, r13; Src
0x1800730ad  call    memcpy_0
0x1800730b2  mov     rsi, [rbp+57h+var_80]
0x1800730b6  lea     rdx, aLocking; ">>> Locking >>>"
0x1800730bd  mov     ecx, [rsi+9C0h]; unsigned int
0x1800730c3  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800730c8  lea     rdi, [rsi+9D0h]
0x1800730cf  mov     r9d, 3A8h
0x1800730d5  mov     rdx, rdi
0x1800730d8  lea     r8, aAuthmgronexset_0; "AuthMgrOneXSetConnectionProfile"
0x1800730df  mov     rcx, rsi
0x1800730e2  call    cs:__imp_AcquireWriteLock
0x1800730e9  nop     dword ptr [rax+rax+00h]
0x1800730ee  mov     rcx, [rsi+0AE0h]
0x1800730f5  mov     rax, [rsi+0A40h]
0x1800730fc  add     rcx, 28h ; '('
0x180073100  mov     [rbp+57h+var_90], rax
0x180073104  call    FreeRawData
0x180073109  mov     rcx, [rsi+0AE8h]
0x180073110  add     rcx, 28h ; '('
0x180073114  call    FreeRawData
0x180073119  mov     rax, [rsi+0AE0h]
0x180073120  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180073127  mov     rcx, [rbp+57h+var_98]
0x18007312b  mov     [rbp+57h+var_98], 0
0x180073133  mov     [rbp+57h+var_88], 0
0x18007313b  mov     [rax+30h], rcx
0x18007313f  mov     rax, [rsi+0AE0h]
0x180073146  mov     [rax+28h], r14d
0x18007314a  mov     rax, [rsi+0AE8h]
0x180073151  mov     [rax+30h], rbx
0x180073155  mov     rax, [rsi+0AE8h]
0x18007315c  mov     [rax+28h], r14d
0x180073160  mov     ecx, [rsi+9C0h]; unsigned int
0x180073166  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18007316b  mov     r9d, 3B9h
0x180073171  lea     r8, aAuthmgronexset_0; "AuthMgrOneXSetConnectionProfile"
0x180073178  mov     rdx, rdi
0x18007317b  mov     rcx, rsi
0x18007317e  call    cs:__imp_ReleaseWriteLock
0x180073185  nop     dword ptr [rax+rax+00h]
0x18007318a  mov     rax, [r15+20h]
0x18007318e  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180073195  mov     ecx, [r15+138h]; unsigned int
0x18007319c  mov     rdi, [r15+48h]
0x1800731a0  mov     rbx, [r15+28h]
0x1800731a4  mov     [rbp+57h+var_70], rax
0x1800731a8  mov     rax, [r15+40h]
0x1800731ac  mov     [rbp+57h+var_50], rax
0x1800731b0  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x1800731b5  lea     rdx, [r15+140h]
0x1800731bc  mov     r9d, 3C2h
0x1800731c2  lea     r8, aAuthmgronexset_0; "AuthMgrOneXSetConnectionProfile"
0x1800731c9  mov     rcx, r15
0x1800731cc  call    cs:__imp_ReleaseWriteLock
0x1800731d3  nop     dword ptr [rax+rax+00h]
0x1800731d8  mov     ecx, [r15+138h]; unsigned int
0x1800731df  lea     rdx, aDerefing; "<<< Derefing <<<"
0x1800731e6  mov     qword ptr [rbp+57h+var_68+8], 0
0x1800731ee  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x1800731f3  mov     r8d, 3C6h; int
0x1800731f9  lea     rdx, aAuthmgronexset_0; "AuthMgrOneXSetConnectionProfile"
0x180073200  mov     rcx, r15; struct MSMSEC_PORT_CONTEXT *
0x180073203  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x180073208  mov     ecx, [rsi+9C0h]; unsigned int
0x18007320e  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180073215  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18007321a  mov     r8d, 3CAh; int
0x180073220  lea     rdx, aAuthmgronexset_0; "AuthMgrOneXSetConnectionProfile"
0x180073227  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x18007322a  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x18007322f  mov     rdx, [rbp+57h+var_90]; void *
0x180073233  lea     r8, [rbp+57h+var_A0]; struct DOT11_MSMSEC_CONNECTION_PROFILE **
0x180073237  mov     rcx, [rbp+57h+var_70]; void *
0x18007323b  mov     r9, rdi; unsigned int (*)(void *, void *, struct DOT11_MSMSEC_CONNECTION_PROFILE **)
0x18007323e  mov     dword ptr [rbp+57h+var_68+4], 0
0x180073245  mov     [rsp+0D0h+var_B0], rbx; void (*)(void *)
0x18007324a  call    ?MSMGetConnectionProfile@@YAKPEAX0PEAPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@P6AK001@ZP6AX0@Z@Z; MSMGetConnectionProfile(void *,void *,DOT11_MSMSEC_CONNECTION_PROFILE * *,ulong (*)(void *,void *,DOT11_MSMSEC_CONNECTION_PROFILE * *),void (*)(void *))
0x18007324f  mov     ebx, eax
0x180073251  test    eax, eax
0x180073253  jz      short loc_18007328F
0x180073255  mov     rcx, cs:WPP_GLOBAL_Control
0x18007325c  lea     r12, WPP_GLOBAL_Control
0x180073263  cmp     rcx, r12
0x180073266  jz      short loc_180073286
0x180073268  test    byte ptr [rcx+44h], 1
0x18007326c  jz      short loc_180073286
0x18007326e  mov     edx, 56h ; 'V'
0x180073273  mov     rcx, [rcx+38h]
0x180073277  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18007327e  mov     r9d, eax
0x180073281  call    WPP_SF_d
0x180073286  mov     rsi, [rbp+57h+var_A0]
0x18007328a  jmp     loc_18007332C
0x18007328f  lea     rdx, [rbp+57h+var_78]
0x180073293  mov     ecx, r14d; dwBytes
0x180073296  call    AllocateMSMSecMemory
0x18007329b  mov     ebx, eax
0x18007329d  test    eax, eax
0x18007329f  jz      short loc_1800732C1
0x1800732a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800732a8  lea     r12, WPP_GLOBAL_Control
0x1800732af  cmp     rcx, r12
0x1800732b2  jz      short loc_180073286
0x1800732b4  test    byte ptr [rcx+44h], 1
0x1800732b8  jz      short loc_180073286
0x1800732ba  mov     edx, 57h ; 'W'
0x1800732bf  jmp     short loc_180073273
0x1800732c1  mov     rdi, [rbp+57h+var_78]
0x1800732c5  mov     r8, r14; Size
0x1800732c8  mov     rcx, rdi; void *
0x1800732cb  mov     rdx, r13; Src
0x1800732ce  call    memcpy_0
0x1800732d3  mov     rsi, [rbp+57h+var_A0]
0x1800732d7  lea     rcx, [rsi+28h]
0x1800732db  call    FreeRawData
0x1800732e0  mov     r9, [rbp+57h+var_50]; unsigned int (*)(void *, void *, struct DOT11_MSMSEC_CONNECTION_PROFILE *, int)
0x1800732e4  mov     r8, rsi; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x1800732e7  mov     rdx, [rbp+57h+var_90]; void *
0x1800732eb  mov     rcx, [rbp+57h+var_70]; void *
0x1800732ef  mov     [rsi+30h], rdi
0x1800732f3  mov     [rsi+28h], r14d
0x1800732f7  call    ?MSMSetConnectionProfile@@YAKPEAX0PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@P6AK001H@Z@Z; MSMSetConnectionProfile(void *,void *,DOT11_MSMSEC_CONNECTION_PROFILE *,ulong (*)(void *,void *,DOT11_MSMSEC_CONNECTION_PROFILE *,int))
0x1800732fc  mov     ebx, eax
0x1800732fe  test    eax, eax
0x180073300  jz      short loc_180073325
0x180073302  mov     rcx, cs:WPP_GLOBAL_Control
0x180073309  lea     r12, WPP_GLOBAL_Control
0x180073310  cmp     rcx, r12
0x180073313  jz      short loc_18007332C
0x180073315  test    byte ptr [rcx+44h], 1
0x180073319  jz      short loc_18007332C
0x18007331b  mov     edx, 58h ; 'X'
0x180073320  jmp     loc_18007303F
0x180073325  lea     r12, WPP_GLOBAL_Control
0x18007332c  mov     rdx, [rbp+57h+var_80]; struct MSMSEC_INTF_CONTEXT *
0x180073330  lea     r9, [rbp+57h+var_68]; struct _AUTHMGR_LOCK_STATE *
0x180073334  mov     rcx, [rbp+57h+arg_0]; void *
0x180073338  mov     r8, r15; struct MSMSEC_PORT_CONTEXT *
0x18007333b  call    ?PostCallbackActions@@YAKPEAXPEAUMSMSEC_INTF_CONTEXT@@PEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z; PostCallbackActions(void *,MSMSEC_INTF_CONTEXT *,MSMSEC_PORT_CONTEXT *,_AUTHMGR_LOCK_STATE *)
0x180073340  test    rsi, rsi
0x180073343  jz      short loc_18007334E
0x180073345  lea     rcx, [rbp+57h+var_A0]
0x180073349  call    FreeMSMSecConfig
0x18007334e  lea     rcx, [rbp+57h+var_98]
0x180073352  call    FreeMSMSecMemory
0x180073357  lea     rcx, [rbp+57h+var_88]
0x18007335b  call    FreeMSMSecMemory
0x180073360  mov     rcx, cs:WPP_GLOBAL_Control
0x180073367  cmp     rcx, r12
0x18007336a  jz      short loc_18007338D
0x18007336c  test    dword ptr [rcx+44h], 100h
0x180073373  jz      short loc_18007338D
0x180073375  mov     rcx, [rcx+38h]
0x180073379  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x180073380  mov     edx, 59h ; 'Y'
0x180073385  mov     r9d, ebx
0x180073388  call    WPP_SF_d
0x18007338d  mov     eax, ebx
0x18007338f  add     rsp, 98h
0x180073396  pop     r15
0x180073398  pop     r14
0x18007339a  pop     r13
0x18007339c  pop     r12
0x18007339e  pop     rdi
0x18007339f  pop     rsi
0x1800733a0  pop     rbx
0x1800733a1  pop     rbp
0x1800733a2  retn
```
