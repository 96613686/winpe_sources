# AuthMgrOneXUIRequest(void *,void *,ulong,int,ulong,void *)

- ea: `0x18002b770`
- end: `0x18002bb01`
- name: `?AuthMgrOneXUIRequest@@YAKPEAX0KHK0@Z`
- size: `913`
- prototype: `unsigned int __usercall@<eax>(void *@<rcx>, void *@<rdx>, unsigned int@<r8d>, int@<r9d>, unsigned int, void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

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
- `0x18002b770`
- `0x18002bb08`
- `0x18002bb50`
- `0x18002c1cc`
- `0x180044554`

## import_xrefs

- `MobileNetworking!GetSystemTimeAsUlongLong` at `0x18002b95b`
- `MobileNetworking!GetSystemTimeAsUlongLong` at `0x18002b95b`
- `MobileNetworking!ReleaseWriteLock` at `0x18002b9c5`
- `MobileNetworking!ReleaseWriteLock` at `0x18002b9c5`

## pseudocode

```c
__int64 __fastcall AuthMgrOneXUIRequest(void *a1, void *a2, unsigned int a3, int a4, unsigned int Size, void *Src)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  PVOID *v11; // rcx
  struct MSMSEC_PORT_CONTEXT *v12; // rsi
  unsigned int *v13; // r13
  unsigned int v14; // r15d
  unsigned int MSMSecMemory; // eax
  struct MSMSEC_UI_REQUEST *v16; // rdi
  void *v17; // rbx
  unsigned int (*v18)(void *, struct _GUID *, struct _L2_UI_REQUEST *, int); // r14
  unsigned int v19; // ecx
  unsigned int v20; // eax
  struct MSMSEC_UI_REQUEST *v22; // [rsp+40h] [rbp-30h]
  struct MSMSEC_PORT_CONTEXT *v23; // [rsp+48h] [rbp-28h] BYREF
  struct MSMSEC_INTF_CONTEXT *v24; // [rsp+50h] [rbp-20h] BYREF
  __int128 v25; // [rsp+58h] [rbp-18h] BYREF
  __int64 v26; // [rsp+68h] [rbp-8h]

  v24 = 0;
  v23 = 0;
  v22 = 0;
  v26 = 0;
  v25 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 74, WPP_20060763357235bdafa6f501eee46e60_Traceguids);
  v8 = PreCallbackActions(a1, a2, &v24, &v23, (struct _AUTHMGR_LOCK_STATE *)&v25);
  v9 = v8;
  if ( !v8 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    v12 = v23;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        76,
        WPP_20060763357235bdafa6f501eee46e60_Traceguids,
        *((unsigned int *)v23 + 78));
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    v13 = (unsigned int *)v24;
    v14 = Size + 32;
    if ( Size + 32 >= Size )
    {
      MSMSecMemory = AllocateMSMSecMemory(v14);
      v9 = MSMSecMemory;
      if ( MSMSecMemory )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            78,
            WPP_20060763357235bdafa6f501eee46e60_Traceguids,
            MSMSecMemory);
      }
      else
      {
        v16 = v22;
        *(_DWORD *)v22 = 4;
        *((_DWORD *)v16 + 1) = 4;
        *((_DWORD *)v16 + 3) = *(_DWORD *)((char *)v12 + 302);
        *((_WORD *)v16 + 8) = *((_WORD *)v12 + 153);
        *((_DWORD *)v16 + 5) = Size;
        memcpy_0((char *)v16 + 32, Src, Size);
        v17 = (void *)*((_QWORD *)v12 + 4);
        v18 = (unsigned int (*)(void *, struct _GUID *, struct _L2_UI_REQUEST *, int))*((_QWORD *)v12 + 10);
        AuthMgrResetUIRespTime((struct MSMSEC_PORT_CONTEXT *)((char *)v12 + 920));
        *((_QWORD *)v12 + 124) = GetSystemTimeAsUlongLong();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids);
        TracePortId(*((_DWORD *)v12 + 78), "<<< Unlocking <<<");
        ReleaseWriteLock(v12, (char *)v12 + 320, "AuthMgrOneXUIRequest", 871);
        v19 = *((_DWORD *)v12 + 78);
        *((_QWORD *)&v25 + 1) = 0;
        TracePortId(v19, "<<< Derefing <<<");
        SecMgrDerefPortEx(v12, "AuthMgrOneXUIRequest", 875);
        TraceAdapterId(v13[624], "<<< Derefing <<<");
        SecMgrDerefAdapterEx((struct MSMSEC_INTF_CONTEXT *)v13, "AuthMgrOneXUIRequest", 879);
        DWORD1(v25) = 0;
        v20 = MSMUIRequest(v17, v14, v16, a3, a4, &g_Dot1xClsid, v18);
        v9 = v20;
        if ( v20 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 79, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v20);
      }
    }
    else
    {
      v9 = 534;
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 1) != 0 )
        WPP_SF_(v11[7], 77, WPP_20060763357235bdafa6f501eee46e60_Traceguids);
    }
    PostCallbackActions(a1, (struct MSMSEC_INTF_CONTEXT *)v13, v12, (struct _AUTHMGR_LOCK_STATE *)&v25);
    goto LABEL_28;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 75, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v8);
LABEL_28:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x100) != 0 )
    WPP_SF_d(v10[7], 80, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18002b770  mov     [rsp-38h+arg_0], rbx
0x18002b775  mov     [rsp-38h+arg_18], r9d
0x18002b77a  mov     [rsp-38h+arg_10], r8d
0x18002b77f  push    rbp
0x18002b780  push    rsi
0x18002b781  push    rdi
0x18002b782  push    r12
0x18002b784  push    r13
0x18002b786  push    r14
0x18002b788  push    r15
0x18002b78a  mov     rbp, rsp
0x18002b78d  sub     rsp, 70h
0x18002b791  xor     eax, eax
0x18002b793  mov     [rbp+var_20], 0
0x18002b79b  xor     edi, edi
0x18002b79d  mov     [rbp+var_28], 0
0x18002b7a5  xorps   xmm0, xmm0
0x18002b7a8  mov     [rbp+var_30], rdi
0x18002b7ac  mov     rbx, rdx
0x18002b7af  mov     [rbp+var_8], rax
0x18002b7b3  mov     r12, rcx
0x18002b7b6  movups  [rbp+var_18], xmm0
0x18002b7ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b7c1  lea     r14, WPP_GLOBAL_Control
0x18002b7c8  cmp     rcx, r14
0x18002b7cb  jz      short loc_18002B7E9
0x18002b7cd  test    dword ptr [rcx+44h], 100h
0x18002b7d4  jz      short loc_18002B7E9
0x18002b7d6  mov     rcx, [rcx+38h]
0x18002b7da  lea     edx, [rax+4Ah]
0x18002b7dd  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002b7e4  call    WPP_SF_
0x18002b7e9  lea     rax, [rbp+var_18]
0x18002b7ed  mov     rdx, rbx; void *
0x18002b7f0  lea     r9, [rbp+var_28]; struct MSMSEC_PORT_CONTEXT **
0x18002b7f4  mov     [rsp+70h+var_50], rax; struct _AUTHMGR_LOCK_STATE *
0x18002b7f9  lea     r8, [rbp+var_20]; struct MSMSEC_INTF_CONTEXT **
0x18002b7fd  mov     rcx, r12; void *
0x18002b800  call    ?PreCallbackActions@@YAKPEAX0PEAPEAUMSMSEC_INTF_CONTEXT@@PEAPEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z; PreCallbackActions(void *,void *,MSMSEC_INTF_CONTEXT * *,MSMSEC_PORT_CONTEXT * *,_AUTHMGR_LOCK_STATE *)
0x18002b805  mov     ebx, eax
0x18002b807  test    eax, eax
0x18002b809  jz      short loc_18002B842
0x18002b80b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b812  cmp     rcx, r14
0x18002b815  jz      loc_18002BAE6
0x18002b81b  test    byte ptr [rcx+44h], 1
0x18002b81f  jz      loc_18002BAC0
0x18002b825  mov     rcx, [rcx+38h]
0x18002b829  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002b830  mov     edx, 4Bh ; 'K'
0x18002b835  mov     r9d, eax
0x18002b838  call    WPP_SF_d
0x18002b83d  jmp     loc_18002BAB9
0x18002b842  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b849  mov     rsi, [rbp+var_28]
0x18002b84d  cmp     rcx, r14
0x18002b850  jz      short loc_18002B87B
0x18002b852  test    byte ptr [rcx+44h], 20h
0x18002b856  jz      short loc_18002B87B
0x18002b858  mov     r9d, [rsi+138h]
0x18002b85f  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002b866  mov     rcx, [rcx+38h]
0x18002b86a  mov     edx, 4Ch ; 'L'
0x18002b86f  call    WPP_SF_d
0x18002b874  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b87b  mov     r14d, dword ptr [rbp+Size]
0x18002b87f  mov     r13, [rbp+var_20]
0x18002b883  lea     r15d, [r14+20h]
0x18002b887  cmp     r15d, r14d
0x18002b88a  jnb     short loc_18002B8C5
0x18002b88c  mov     ebx, 216h
0x18002b891  lea     r14, WPP_GLOBAL_Control
0x18002b898  cmp     rcx, r14
0x18002b89b  jz      loc_18002BA99
0x18002b8a1  test    byte ptr [rcx+44h], 1
0x18002b8a5  jz      loc_18002BA99
0x18002b8ab  mov     rcx, [rcx+38h]
0x18002b8af  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002b8b6  mov     edx, 4Dh ; 'M'
0x18002b8bb  call    WPP_SF_
0x18002b8c0  jmp     loc_18002BA99
0x18002b8c5  lea     rdx, [rbp+var_30]
0x18002b8c9  mov     ecx, r15d; dwBytes
0x18002b8cc  call    AllocateMSMSecMemory
0x18002b8d1  mov     ebx, eax
0x18002b8d3  test    eax, eax
0x18002b8d5  jz      short loc_18002B911
0x18002b8d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8de  lea     r14, WPP_GLOBAL_Control
0x18002b8e5  cmp     rcx, r14
0x18002b8e8  jz      short loc_18002B908
0x18002b8ea  test    byte ptr [rcx+44h], 1
0x18002b8ee  jz      short loc_18002B908
0x18002b8f0  mov     rcx, [rcx+38h]
0x18002b8f4  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002b8fb  mov     edx, 4Eh ; 'N'
0x18002b900  mov     r9d, eax
0x18002b903  call    WPP_SF_d
0x18002b908  mov     rdi, [rbp+var_30]
0x18002b90c  jmp     loc_18002BA99
0x18002b911  mov     rdi, [rbp+var_30]
0x18002b915  mov     eax, 4
0x18002b91a  mov     rdx, [rbp+Src]; Src
0x18002b91e  mov     r8, r14; Size
0x18002b921  mov     [rdi], eax
0x18002b923  lea     rcx, [rdi+20h]; void *
0x18002b927  mov     [rdi+4], eax
0x18002b92a  mov     eax, [rsi+12Eh]
0x18002b930  mov     [rdi+0Ch], eax
0x18002b933  movzx   eax, word ptr [rsi+132h]
0x18002b93a  mov     [rdi+10h], ax
0x18002b93e  mov     [rdi+14h], r14d
0x18002b942  call    memcpy_0
0x18002b947  mov     rbx, [rsi+20h]
0x18002b94b  lea     rcx, [rsi+398h]; struct MSMSEC_PORT_AUTH_CONTEXT *
0x18002b952  mov     r14, [rsi+50h]
0x18002b956  call    ?AuthMgrResetUIRespTime@@YAXPEAUMSMSEC_PORT_AUTH_CONTEXT@@@Z; AuthMgrResetUIRespTime(MSMSEC_PORT_AUTH_CONTEXT *)
0x18002b95b  call    cs:__imp_GetSystemTimeAsUlongLong
0x18002b962  nop     dword ptr [rax+rax+00h]
0x18002b967  mov     [rsi+3E0h], rax
0x18002b96e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b975  lea     rax, WPP_GLOBAL_Control
0x18002b97c  cmp     rcx, rax
0x18002b97f  jz      short loc_18002B99C
0x18002b981  test    byte ptr [rcx+44h], 2
0x18002b985  jz      short loc_18002B99C
0x18002b987  mov     rcx, [rcx+38h]
0x18002b98b  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x18002b992  mov     edx, 11h
0x18002b997  call    WPP_SF_
0x18002b99c  mov     ecx, [rsi+138h]; unsigned int
0x18002b9a2  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18002b9a9  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x18002b9ae  lea     rdx, [rsi+140h]
0x18002b9b5  mov     r9d, 367h
0x18002b9bb  lea     r8, aAuthmgronexuir; "AuthMgrOneXUIRequest"
0x18002b9c2  mov     rcx, rsi
0x18002b9c5  call    cs:__imp_ReleaseWriteLock
0x18002b9cc  nop     dword ptr [rax+rax+00h]
0x18002b9d1  mov     ecx, [rsi+138h]; unsigned int
0x18002b9d7  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18002b9de  mov     qword ptr [rbp+var_18+8], 0
0x18002b9e6  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x18002b9eb  mov     r8d, 36Bh; int
0x18002b9f1  lea     rdx, aAuthmgronexuir; "AuthMgrOneXUIRequest"
0x18002b9f8  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x18002b9fb  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x18002ba00  mov     ecx, [r13+9C0h]; unsigned int
0x18002ba07  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18002ba0e  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18002ba13  mov     r8d, 36Fh; int
0x18002ba19  lea     rdx, aAuthmgronexuir; "AuthMgrOneXUIRequest"
0x18002ba20  mov     rcx, r13; struct MSMSEC_INTF_CONTEXT *
0x18002ba23  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x18002ba28  mov     r9d, [rbp+arg_10]; unsigned int
0x18002ba2c  lea     rax, ?g_Dot1xClsid@@3U_GUID@@A; _GUID g_Dot1xClsid
0x18002ba33  mov     [rsp+70h+var_40], r14; unsigned int (*)(void *, struct _GUID *, struct _L2_UI_REQUEST *, int)
0x18002ba38  mov     r8, rdi; struct MSMSEC_UI_REQUEST *
0x18002ba3b  mov     [rsp+70h+var_48], rax; struct _GUID *
0x18002ba40  mov     edx, r15d; unsigned int
0x18002ba43  mov     eax, [rbp+arg_18]
0x18002ba46  mov     rcx, rbx; void *
0x18002ba49  mov     dword ptr [rsp+70h+var_50], eax; int
0x18002ba4d  mov     dword ptr [rbp+var_18+4], 0
0x18002ba54  call    ?MSMUIRequest@@YAKPEAXKPEAUMSMSEC_UI_REQUEST@@KHPEAU_GUID@@P6AK02PEAU_L2_UI_REQUEST@@H@Z@Z; MSMUIRequest(void *,ulong,MSMSEC_UI_REQUEST *,ulong,int,_GUID *,ulong (*)(void *,_GUID *,_L2_UI_REQUEST *,int))
0x18002ba59  mov     ebx, eax
0x18002ba5b  test    eax, eax
0x18002ba5d  jz      short loc_18002BA92
0x18002ba5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba66  lea     r14, WPP_GLOBAL_Control
0x18002ba6d  cmp     rcx, r14
0x18002ba70  jz      short loc_18002BA99
0x18002ba72  test    byte ptr [rcx+44h], 1
0x18002ba76  jz      short loc_18002BA99
0x18002ba78  mov     rcx, [rcx+38h]
0x18002ba7c  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002ba83  mov     edx, 4Fh ; 'O'
0x18002ba88  mov     r9d, eax
0x18002ba8b  call    WPP_SF_d
0x18002ba90  jmp     short loc_18002BA99
0x18002ba92  lea     r14, WPP_GLOBAL_Control
0x18002ba99  lea     r9, [rbp+var_18]; struct _AUTHMGR_LOCK_STATE *
0x18002ba9d  mov     r8, rsi; struct MSMSEC_PORT_CONTEXT *
0x18002baa0  mov     rdx, r13; struct MSMSEC_INTF_CONTEXT *
0x18002baa3  mov     rcx, r12; void *
0x18002baa6  call    ?PostCallbackActions@@YAKPEAXPEAUMSMSEC_INTF_CONTEXT@@PEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z; PostCallbackActions(void *,MSMSEC_INTF_CONTEXT *,MSMSEC_PORT_CONTEXT *,_AUTHMGR_LOCK_STATE *)
0x18002baab  test    rdi, rdi
0x18002baae  jz      short loc_18002BAB9
0x18002bab0  lea     rcx, [rbp+var_30]
0x18002bab4  call    FreeMSMSecMemory
0x18002bab9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bac0  cmp     rcx, r14
0x18002bac3  jz      short loc_18002BAE6
0x18002bac5  test    dword ptr [rcx+44h], 100h
0x18002bacc  jz      short loc_18002BAE6
0x18002bace  mov     rcx, [rcx+38h]
0x18002bad2  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002bad9  mov     edx, 50h ; 'P'
0x18002bade  mov     r9d, ebx
0x18002bae1  call    WPP_SF_d
0x18002bae6  mov     eax, ebx
0x18002bae8  mov     rbx, [rsp+70h+arg_0]
0x18002baf0  add     rsp, 70h
0x18002baf4  pop     r15
0x18002baf6  pop     r14
0x18002baf8  pop     r13
0x18002bafa  pop     r12
0x18002bafc  pop     rdi
0x18002bafd  pop     rsi
0x18002bafe  pop     rbp
0x18002baff  retn
```
