# AuthMgrOneXQueryUserProfile(void *,void *,void *,ulong *,void * *)

- ea: `0x18002be40`
- end: `0x18002c1c6`
- name: `?AuthMgrOneXQueryUserProfile@@YAKPEAX00PEAKPEAPEAX@Z`
- size: `902`
- prototype: `unsigned int __usercall@<eax>(void *@<rcx>, void *@<rdx>, void *@<r8>, unsigned int *@<r9>, void **)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000c730`
- `0x18000e620`
- `0x180013600`
- `0x180013bc0`
- `0x1800169c0`
- `0x18002a638`
- `0x18002b170`
- `0x18002bb08`
- `0x18002be40`
- `0x18002c21c`
- `0x18003ac5c`
- `0x180044554`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18002bfc5`
- `MobileNetworking!ReleaseWriteLock` at `0x18002c007`
- `MobileNetworking!ReleaseWriteLock` at `0x18002bfc5`
- `MobileNetworking!ReleaseWriteLock` at `0x18002c007`
- `MobileNetworking!AcquireWriteLock` at `0x18002bf8d`
- `MobileNetworking!AcquireWriteLock` at `0x18002bf8d`

## pseudocode

```c
__int64 __fastcall AuthMgrOneXQueryUserProfile(void *a1, void *a2, void *a3, unsigned int *a4, void **a5)
{
  void *v8; // r15
  unsigned int v9; // eax
  unsigned int MSMSecMemory; // ebx
  PVOID *v11; // rcx
  struct MSMSEC_PORT_CONTEXT *v12; // r13
  struct MSMSEC_INTF_CONTEXT *v13; // rdi
  void *v14; // r14
  void *v15; // rsi
  unsigned int (*v16)(void *, void *, void *, unsigned int *, void **); // rdi
  void (*v17)(void *); // rbx
  unsigned int v18; // ecx
  unsigned int v19; // eax
  struct MSMSEC_USER_PROFILE *v20; // rdi
  SIZE_T v21; // rcx
  struct MSMSEC_INTF_CONTEXT *v23; // [rsp+30h] [rbp-40h] BYREF
  void *v24; // [rsp+38h] [rbp-38h] BYREF
  struct MSMSEC_USER_PROFILE *v25; // [rsp+40h] [rbp-30h] BYREF
  struct MSMSEC_PORT_CONTEXT *v26; // [rsp+48h] [rbp-28h] BYREF
  __int128 v27; // [rsp+50h] [rbp-20h] BYREF
  __int64 v28; // [rsp+60h] [rbp-10h]

  v23 = 0;
  v28 = 0;
  v26 = 0;
  v25 = 0;
  v27 = 0;
  v8 = 0;
  v24 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 63, WPP_20060763357235bdafa6f501eee46e60_Traceguids);
  *a4 = 0;
  *a5 = 0;
  v9 = PreCallbackActions(a1, a2, &v23, &v26, (struct _AUTHMGR_LOCK_STATE *)&v27);
  MSMSecMemory = v9;
  if ( !v9 )
  {
    v12 = v26;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        65,
        WPP_20060763357235bdafa6f501eee46e60_Traceguids,
        *((unsigned int *)v26 + 78));
    v13 = v23;
    TraceAdapterId(*((_DWORD *)v23 + 624), ">>> Locking >>>");
    AcquireWriteLock(v13, (char *)v13 + 2512, "AuthMgrOneXQueryUserProfile", 672);
    v14 = (void *)*((_QWORD *)v13 + 328);
    TraceAdapterId(*((_DWORD *)v13 + 624), "<<< Unlocking <<<");
    ReleaseWriteLock(v13, (char *)v13 + 2512, "AuthMgrOneXQueryUserProfile", 674);
    v15 = (void *)*((_QWORD *)v12 + 4);
    v16 = (unsigned int (*)(void *, void *, void *, unsigned int *, void **))*((_QWORD *)v12 + 7);
    v17 = (void (*)(void *))*((_QWORD *)v12 + 5);
    TracePortId(*((_DWORD *)v12 + 78), "<<< Unlocking <<<");
    ReleaseWriteLock(v12, (char *)v12 + 320, "AuthMgrOneXQueryUserProfile", 682);
    v18 = *((_DWORD *)v12 + 78);
    *((_QWORD *)&v27 + 1) = 0;
    TracePortId(v18, "<<< Derefing <<<");
    SecMgrDerefPortEx(v12, "AuthMgrOneXQueryUserProfile", 686);
    TraceAdapterId(*((_DWORD *)v23 + 624), "<<< Derefing <<<");
    SecMgrDerefAdapterEx(v23, "AuthMgrOneXQueryUserProfile", 690);
    DWORD1(v27) = 0;
    v19 = MSMGetUserProfile(v15, a3, v14, &v25, v16, v17);
    v20 = v25;
    MSMSecMemory = v19;
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 66, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v19);
      goto LABEL_23;
    }
    v21 = *(unsigned int *)v25;
    if ( (_DWORD)v21 )
    {
      MSMSecMemory = AllocateMSMSecMemory(v21);
      if ( MSMSecMemory )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            67,
            WPP_20060763357235bdafa6f501eee46e60_Traceguids,
            MSMSecMemory);
        v8 = v24;
LABEL_23:
        PostCallbackActions(a1, v23, v12, (struct _AUTHMGR_LOCK_STATE *)&v27);
        if ( v20 )
          FreeMSMSecUserProfile(&v25);
        if ( !MSMSecMemory )
          goto LABEL_29;
        goto LABEL_26;
      }
      v8 = v24;
      memcpy_0(v24, *((const void **)v20 + 1), *(unsigned int *)v20);
    }
    *a5 = v8;
    *a4 = *(_DWORD *)v20;
    goto LABEL_23;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 64, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v9);
LABEL_26:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    FreeMSMSecMemory(&v24);
LABEL_29:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x100) != 0 )
    WPP_SF_d(v11[7], 68, WPP_20060763357235bdafa6f501eee46e60_Traceguids, MSMSecMemory);
  return MSMSecMemory;
}

```

## disassembly

```asm
0x18002be40  mov     rax, rsp
0x18002be43  mov     [rax+10h], rbx
0x18002be47  mov     [rax+20h], r9
0x18002be4b  mov     [rax+18h], r8
0x18002be4f  mov     [rax+8], rcx
0x18002be53  push    rbp
0x18002be54  push    rsi
0x18002be55  push    rdi
0x18002be56  push    r12
0x18002be58  push    r13
0x18002be5a  push    r14
0x18002be5c  push    r15
0x18002be5e  mov     rbp, rsp
0x18002be61  sub     rsp, 70h
0x18002be65  xor     r14d, r14d
0x18002be68  xorps   xmm0, xmm0
0x18002be6b  xor     eax, eax
0x18002be6d  mov     [rbp+var_40], r14
0x18002be71  mov     [rbp+var_10], rax
0x18002be75  mov     rbx, r9
0x18002be78  mov     rsi, rdx
0x18002be7b  mov     [rbp+var_28], r14
0x18002be7f  mov     rdi, rcx
0x18002be82  mov     [rbp+var_30], r14
0x18002be86  movups  [rbp+var_20], xmm0
0x18002be8a  mov     r15d, r14d
0x18002be8d  mov     [rbp+var_38], r14
0x18002be91  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be98  lea     r13, WPP_GLOBAL_Control
0x18002be9f  cmp     rcx, r13
0x18002bea2  jz      short loc_18002BEC0
0x18002bea4  test    dword ptr [rcx+44h], 100h
0x18002beab  jz      short loc_18002BEC0
0x18002bead  mov     rcx, [rcx+38h]
0x18002beb1  lea     edx, [rax+3Fh]
0x18002beb4  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002bebb  call    WPP_SF_
0x18002bec0  mov     r12, [rbp+arg_20]
0x18002bec4  lea     rax, [rbp+var_20]
0x18002bec8  mov     [rbx], r14d
0x18002becb  lea     r9, [rbp+var_28]; struct MSMSEC_PORT_CONTEXT **
0x18002becf  lea     r8, [rbp+var_40]; struct MSMSEC_INTF_CONTEXT **
0x18002bed3  mov     [rsp+70h+var_50], rax; struct _AUTHMGR_LOCK_STATE *
0x18002bed8  mov     rdx, rsi; void *
0x18002bedb  mov     rcx, rdi; void *
0x18002bede  mov     [r12], r14
0x18002bee2  call    ?PreCallbackActions@@YAKPEAX0PEAPEAUMSMSEC_INTF_CONTEXT@@PEAPEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z; PreCallbackActions(void *,void *,MSMSEC_INTF_CONTEXT * *,MSMSEC_PORT_CONTEXT * *,_AUTHMGR_LOCK_STATE *)
0x18002bee7  mov     ebx, eax
0x18002bee9  test    eax, eax
0x18002beeb  jz      short loc_18002BF24
0x18002beed  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bef4  cmp     rcx, r13
0x18002bef7  jz      loc_18002C169
0x18002befd  test    byte ptr [rcx+44h], 1
0x18002bf01  jz      loc_18002C169
0x18002bf07  mov     rcx, [rcx+38h]
0x18002bf0b  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002bf12  mov     edx, 40h ; '@'
0x18002bf17  mov     r9d, eax
0x18002bf1a  call    WPP_SF_d
0x18002bf1f  jmp     loc_18002C162
0x18002bf24  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf2b  lea     rax, WPP_GLOBAL_Control
0x18002bf32  mov     r13, [rbp+var_28]
0x18002bf36  cmp     rcx, rax
0x18002bf39  jz      short loc_18002BF5D
0x18002bf3b  test    byte ptr [rcx+44h], 20h
0x18002bf3f  jz      short loc_18002BF5D
0x18002bf41  mov     r9d, [r13+138h]
0x18002bf48  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002bf4f  mov     rcx, [rcx+38h]
0x18002bf53  mov     edx, 41h ; 'A'
0x18002bf58  call    WPP_SF_d
0x18002bf5d  mov     rdi, [rbp+var_40]
0x18002bf61  lea     rdx, aLocking; ">>> Locking >>>"
0x18002bf68  mov     ecx, [rdi+9C0h]; unsigned int
0x18002bf6e  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18002bf73  lea     rbx, [rdi+9D0h]
0x18002bf7a  mov     r9d, 2A0h
0x18002bf80  mov     rdx, rbx
0x18002bf83  lea     r8, aAuthmgronexque; "AuthMgrOneXQueryUserProfile"
0x18002bf8a  mov     rcx, rdi
0x18002bf8d  call    cs:__imp_AcquireWriteLock
0x18002bf94  nop     dword ptr [rax+rax+00h]
0x18002bf99  mov     ecx, [rdi+9C0h]; unsigned int
0x18002bf9f  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18002bfa6  mov     r14, [rdi+0A40h]
0x18002bfad  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18002bfb2  mov     r9d, 2A2h
0x18002bfb8  lea     r8, aAuthmgronexque; "AuthMgrOneXQueryUserProfile"
0x18002bfbf  mov     rdx, rbx
0x18002bfc2  mov     rcx, rdi
0x18002bfc5  call    cs:__imp_ReleaseWriteLock
0x18002bfcc  nop     dword ptr [rax+rax+00h]
0x18002bfd1  mov     ecx, [r13+138h]; unsigned int
0x18002bfd8  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18002bfdf  mov     rsi, [r13+20h]
0x18002bfe3  mov     rdi, [r13+38h]
0x18002bfe7  mov     rbx, [r13+28h]
0x18002bfeb  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x18002bff0  lea     rdx, [r13+140h]
0x18002bff7  mov     r9d, 2AAh
0x18002bffd  lea     r8, aAuthmgronexque; "AuthMgrOneXQueryUserProfile"
0x18002c004  mov     rcx, r13
0x18002c007  call    cs:__imp_ReleaseWriteLock
0x18002c00e  nop     dword ptr [rax+rax+00h]
0x18002c013  mov     ecx, [r13+138h]; unsigned int
0x18002c01a  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18002c021  mov     qword ptr [rbp+var_20+8], r15
0x18002c025  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x18002c02a  mov     r8d, 2AEh; int
0x18002c030  lea     rdx, aAuthmgronexque; "AuthMgrOneXQueryUserProfile"
0x18002c037  mov     rcx, r13; struct MSMSEC_PORT_CONTEXT *
0x18002c03a  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x18002c03f  mov     rcx, [rbp+var_40]
0x18002c043  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18002c04a  mov     ecx, [rcx+9C0h]; unsigned int
0x18002c050  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18002c055  mov     rcx, [rbp+var_40]; struct MSMSEC_INTF_CONTEXT *
0x18002c059  lea     rdx, aAuthmgronexque; "AuthMgrOneXQueryUserProfile"
0x18002c060  mov     r8d, 2B2h; int
0x18002c066  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x18002c06b  mov     rdx, [rbp+arg_10]; void *
0x18002c06f  lea     r9, [rbp+var_30]; struct MSMSEC_USER_PROFILE **
0x18002c073  mov     r8, r14; void *
0x18002c076  mov     [rsp+70h+var_48], rbx; void (*)(void *)
0x18002c07b  mov     rcx, rsi; void *
0x18002c07e  mov     dword ptr [rbp+var_20+4], r15d
0x18002c082  mov     [rsp+70h+var_50], rdi; unsigned int (*)(void *, void *, void *, unsigned int *, void **)
0x18002c087  call    ?MSMGetUserProfile@@YAKPEAX00PEAPEAUMSMSEC_USER_PROFILE@@P6AK000PEAKPEAPEAX@ZP6AX0@Z@Z; MSMGetUserProfile(void *,void *,void *,MSMSEC_USER_PROFILE * *,ulong (*)(void *,void *,void *,ulong *,void * *),void (*)(void *))
0x18002c08c  mov     rdi, [rbp+var_30]
0x18002c090  mov     ebx, eax
0x18002c092  test    eax, eax
0x18002c094  jz      short loc_18002C0D1
0x18002c096  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c09d  lea     rax, WPP_GLOBAL_Control
0x18002c0a4  cmp     rcx, rax
0x18002c0a7  jz      loc_18002C13C
0x18002c0ad  test    byte ptr [rcx+44h], 1
0x18002c0b1  jz      loc_18002C13C
0x18002c0b7  mov     rcx, [rcx+38h]
0x18002c0bb  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002c0c2  mov     edx, 42h ; 'B'
0x18002c0c7  mov     r9d, ebx
0x18002c0ca  call    WPP_SF_d
0x18002c0cf  jmp     short loc_18002C13C
0x18002c0d1  mov     ecx, [rdi]; dwBytes
0x18002c0d3  test    ecx, ecx
0x18002c0d5  jz      short loc_18002C130
0x18002c0d7  lea     rdx, [rbp+var_38]
0x18002c0db  call    AllocateMSMSecMemory
0x18002c0e0  mov     ebx, eax
0x18002c0e2  test    eax, eax
0x18002c0e4  jz      short loc_18002C11D
0x18002c0e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0ed  lea     rax, WPP_GLOBAL_Control
0x18002c0f4  cmp     rcx, rax
0x18002c0f7  jz      short loc_18002C117
0x18002c0f9  test    byte ptr [rcx+44h], 1
0x18002c0fd  jz      short loc_18002C117
0x18002c0ff  mov     rcx, [rcx+38h]
0x18002c103  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002c10a  mov     edx, 43h ; 'C'
0x18002c10f  mov     r9d, ebx
0x18002c112  call    WPP_SF_d
0x18002c117  mov     r15, [rbp+var_38]
0x18002c11b  jmp     short loc_18002C13C
0x18002c11d  mov     r15, [rbp+var_38]
0x18002c121  mov     r8d, [rdi]; Size
0x18002c124  mov     rcx, r15; void *
0x18002c127  mov     rdx, [rdi+8]; Src
0x18002c12b  call    memcpy_0
0x18002c130  mov     rcx, [rbp+arg_18]
0x18002c134  mov     [r12], r15
0x18002c138  mov     eax, [rdi]
0x18002c13a  mov     [rcx], eax
0x18002c13c  mov     rdx, [rbp+var_40]; struct MSMSEC_INTF_CONTEXT *
0x18002c140  lea     r9, [rbp+var_20]; struct _AUTHMGR_LOCK_STATE *
0x18002c144  mov     rcx, [rbp+arg_0]; void *
0x18002c148  mov     r8, r13; struct MSMSEC_PORT_CONTEXT *
0x18002c14b  call    ?PostCallbackActions@@YAKPEAXPEAUMSMSEC_INTF_CONTEXT@@PEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z; PostCallbackActions(void *,MSMSEC_INTF_CONTEXT *,MSMSEC_PORT_CONTEXT *,_AUTHMGR_LOCK_STATE *)
0x18002c150  test    rdi, rdi
0x18002c153  jz      short loc_18002C15E
0x18002c155  lea     rcx, [rbp+var_30]
0x18002c159  call    FreeMSMSecUserProfile
0x18002c15e  test    ebx, ebx
0x18002c160  jz      short loc_18002C177
0x18002c162  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c169  test    r15, r15
0x18002c16c  jz      short loc_18002C17E
0x18002c16e  lea     rcx, [rbp+var_38]
0x18002c172  call    FreeMSMSecMemory
0x18002c177  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c17e  lea     rax, WPP_GLOBAL_Control
0x18002c185  cmp     rcx, rax
0x18002c188  jz      short loc_18002C1AB
0x18002c18a  test    dword ptr [rcx+44h], 100h
0x18002c191  jz      short loc_18002C1AB
0x18002c193  mov     rcx, [rcx+38h]
0x18002c197  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002c19e  mov     edx, 44h ; 'D'
0x18002c1a3  mov     r9d, ebx
0x18002c1a6  call    WPP_SF_d
0x18002c1ab  mov     eax, ebx
0x18002c1ad  mov     rbx, [rsp+70h+arg_8]
0x18002c1b5  add     rsp, 70h
0x18002c1b9  pop     r15
0x18002c1bb  pop     r14
0x18002c1bd  pop     r13
0x18002c1bf  pop     r12
0x18002c1c1  pop     rdi
0x18002c1c2  pop     rsi
0x18002c1c3  pop     rbp
0x18002c1c4  retn
```
