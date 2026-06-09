# PreCallbackActions(void *,void *,MSMSEC_INTF_CONTEXT * *,MSMSEC_PORT_CONTEXT * *,_AUTHMGR_LOCK_STATE *)

- ea: `0x18002a638`
- end: `0x18002aa3f`
- name: `?PreCallbackActions@@YAKPEAX0PEAPEAUMSMSEC_INTF_CONTEXT@@PEAPEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z`
- size: `1031`
- prototype: `unsigned int __fastcall(void *, void *, struct MSMSEC_INTF_CONTEXT **, struct MSMSEC_PORT_CONTEXT **, struct _AUTHMGR_LOCK_STATE *)`
- caller_count: `11`
- callee_count: `13`
- tags: ``

## callers

- `0x180028750`
- `0x180029660`
- `0x18002a040`
- `0x18002a390`
- `0x18002b770`
- `0x18002be40`
- `0x180072f00`
- `0x1800733b0`
- `0x180073760`
- `0x180075140`
- `0x180075390`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000a26c`
- `0x1800125b0`
- `0x1800148d0`
- `0x180014998`
- `0x1800169c0`
- `0x180016a08`
- `0x18002a638`
- `0x18002abec`
- `0x18002b170`
- `0x18002b3f8`
- `0x1800558c0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18002a7b6`
- `MobileNetworking!ReleaseWriteLock` at `0x18002a7b6`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18002a6de`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18002a6de`

## pseudocode

```c
__int64 __fastcall PreCallbackActions(
        void *a1,
        void *a2,
        struct MSMSEC_INTF_CONTEXT **a3,
        struct MSMSEC_PORT_CONTEXT **a4,
        struct _AUTHMGR_LOCK_STATE *a5)
{
  struct MSMSEC_INTF_CONTEXT *v6; // rdi
  struct MSMSEC_PORT_CONTEXT *v7; // rsi
  struct _AUTHMGR_LOCK_STATE *v10; // r14
  unsigned int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // eax
  void ***v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // ecx
  __int64 v18; // rdx
  int v19; // r8d
  void *v20; // rax
  PVOID *v21; // rcx
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  const wchar_t *v26; // rax
  unsigned int v27; // r10d
  __int64 v28; // rdx
  int v29; // eax
  __int64 v30; // r11
  __int64 v31; // r8
  char v32; // r10
  unsigned __int8 (*v33)[6]; // [rsp+40h] [rbp-10h] BYREF
  struct MSMSEC_INTF_CONTEXT *v35; // [rsp+A0h] [rbp+50h] BYREF
  struct MSMSEC_PORT_CONTEXT *v36; // [rsp+A8h] [rbp+58h] BYREF

  v6 = 0;
  v35 = 0;
  v7 = 0;
  v36 = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, WPP_20060763357235bdafa6f501eee46e60_Traceguids);
  v10 = a5;
  *a3 = 0;
  *a4 = 0;
  *(_QWORD *)v10 = 0;
  *((_QWORD *)v10 + 1) = 0;
  *((_DWORD *)v10 + 4) = 1;
  v11 = IncThreadCountAndCheckInitializedEx("PreCallbackActions", 158);
  v12 = v11;
  if ( v11 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_10;
    v24 = 20;
    goto LABEL_30;
  }
  v13 = HtReferenceHandleWithTag(qword_1800AEFA8, a1, 2, 0, 1, &v33);
  v12 = v13;
  if ( v33 )
  {
    if ( !v13 )
    {
      v14 = *(void ****)&(*v33)[8];
      *((_DWORD *)v10 + 5) = 1;
      v15 = SecMgrValidateRefAndLockAdapter(v14, &v35);
      v12 = v15;
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v15);
        v6 = v35;
        goto LABEL_10;
      }
      *((_DWORD *)v10 + 1) = 1;
      *(_DWORD *)v10 = 1;
      v6 = v35;
      if ( !(unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v35 + 681), 7) )
      {
        v12 = 5023;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v26 = IntfActionStr(7);
          v29 = IntfSecStateStr(v27, v28, v26);
          WPP_SF_SLSL(
            *(_QWORD *)(v30 + 56),
            23,
            (unsigned int)WPP_20060763357235bdafa6f501eee46e60_Traceguids,
            v29,
            v32,
            v31,
            7);
        }
        goto LABEL_10;
      }
      v16 = SecMgrValidateAndRefPort(v6, v33, &v36);
      v12 = v16;
      if ( v16 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v16);
        v7 = v36;
        goto LABEL_10;
      }
      v17 = *((_DWORD *)v6 + 624);
      *((_DWORD *)v10 + 3) = 1;
      TraceAdapterId(v17, "<<< Unlocking <<<");
      ReleaseWriteLock(v6, (char *)v6 + 2512, "PreCallbackActions", 206);
      *(_DWORD *)v10 = 0;
      v7 = v36;
      v11 = SecMgrLockAndCheckPortActive(v36, v18, v19);
      v12 = v11;
      if ( !v11 )
      {
        v20 = (void *)*((unsigned int *)v7 + 234);
        *((_DWORD *)v10 + 2) = 1;
        if ( a2 == v20 )
        {
          *a4 = v7;
          *a3 = v6;
          goto LABEL_14;
        }
        v12 = 1003;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        {
LABEL_10:
          PostCallbackActions(a1, v6, v7, v10);
LABEL_14:
          v21 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_20;
        }
        v24 = 26;
        v25 = 1003;
LABEL_45:
        WPP_SF_d(v23[7], v24, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v25);
        goto LABEL_10;
      }
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_10;
      v24 = 25;
LABEL_30:
      v25 = v11;
      goto LABEL_45;
    }
  }
  else
  {
    v12 = 1168;
  }
  v21 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v12);
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 )
    goto LABEL_10;
LABEL_20:
  if ( v21 != &WPP_GLOBAL_Control && (*((_DWORD *)v21 + 17) & 0x100) != 0 )
    WPP_SF_d(v21[7], 27, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x18002a638  mov     [rsp-38h+arg_8], rbx
0x18002a63d  mov     [rsp-38h+arg_0], rcx
0x18002a642  push    rbp
0x18002a643  push    rsi
0x18002a644  push    rdi
0x18002a645  push    r12
0x18002a647  push    r13
0x18002a649  push    r14
0x18002a64b  push    r15
0x18002a64d  mov     rbp, rsp
0x18002a650  sub     rsp, 50h
0x18002a654  xor     ebx, ebx
0x18002a656  mov     r15, r9
0x18002a659  mov     edi, ebx
0x18002a65b  mov     [rbp+arg_10], rbx
0x18002a65f  mov     esi, ebx
0x18002a661  mov     [rbp+arg_18], rbx
0x18002a665  mov     [rbp+var_10], rbx
0x18002a669  mov     r12, r8
0x18002a66c  mov     r13, rdx
0x18002a66f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a676  lea     rax, WPP_GLOBAL_Control
0x18002a67d  cmp     rcx, rax
0x18002a680  jnz     loc_18002A829
0x18002a686  mov     r14, [rbp+arg_20]
0x18002a68a  lea     rcx, aPrecallbackact; "PreCallbackActions"
0x18002a691  mov     edx, 9Eh; int
0x18002a696  mov     [r12], rbx
0x18002a69a  mov     [r15], rbx
0x18002a69d  mov     [r14], rbx
0x18002a6a0  mov     [r14+8], rbx
0x18002a6a4  mov     dword ptr [r14+10h], 1
0x18002a6ac  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x18002a6b1  mov     ebx, eax
0x18002a6b3  test    eax, eax
0x18002a6b5  jnz     loc_18002A89B
0x18002a6bb  mov     rdx, [rbp+arg_0]
0x18002a6bf  lea     rax, [rbp+var_10]
0x18002a6c3  mov     rcx, cs:qword_1800AEFA8
0x18002a6ca  lea     r8d, [rbx+2]
0x18002a6ce  mov     [rsp+50h+var_28], rax
0x18002a6d3  xor     r9d, r9d
0x18002a6d6  mov     [rsp+50h+var_30], 1
0x18002a6de  call    cs:__imp_HtReferenceHandleWithTag
0x18002a6e5  nop     dword ptr [rax+rax+00h]
0x18002a6ea  mov     rcx, [rbp+var_10]
0x18002a6ee  mov     ebx, eax
0x18002a6f0  test    rcx, rcx
0x18002a6f3  jz      loc_18002A8F1
0x18002a6f9  test    eax, eax
0x18002a6fb  jnz     loc_18002A8F6
0x18002a701  mov     rcx, [rcx+8]; void *
0x18002a705  lea     edi, [rax+1]
0x18002a708  lea     rdx, [rbp+arg_10]; struct MSMSEC_INTF_CONTEXT **
0x18002a70c  mov     [r14+14h], edi
0x18002a710  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x18002a715  mov     ebx, eax
0x18002a717  test    eax, eax
0x18002a719  jnz     loc_18002A809
0x18002a71f  mov     [r14+4], edi
0x18002a723  lea     edx, [rax+7]
0x18002a726  mov     [r14], edi
0x18002a729  mov     rdi, [rbp+arg_10]
0x18002a72d  mov     ecx, [rdi+0AA4h]
0x18002a733  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x18002a738  test    eax, eax
0x18002a73a  jz      loc_18002A962
0x18002a740  mov     rdx, [rbp+var_10]; unsigned __int8 (*)[6]
0x18002a744  lea     r8, [rbp+arg_18]; struct MSMSEC_PORT_CONTEXT **
0x18002a748  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x18002a74b  call    ?SecMgrValidateAndRefPort@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAY05EPEAPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrValidateAndRefPort(MSMSEC_INTF_CONTEXT *,uchar (*)[6],MSMSEC_PORT_CONTEXT * *)
0x18002a750  mov     ebx, eax
0x18002a752  test    eax, eax
0x18002a754  jz      short loc_18002A785
0x18002a756  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a75d  lea     r15, WPP_GLOBAL_Control
0x18002a764  cmp     rcx, r15
0x18002a767  jnz     loc_18002A9D5
0x18002a76d  mov     rsi, [rbp+arg_18]
0x18002a771  mov     rcx, [rbp+arg_0]; void *
0x18002a775  mov     r9, r14; struct _AUTHMGR_LOCK_STATE *
0x18002a778  mov     r8, rsi; struct MSMSEC_PORT_CONTEXT *
0x18002a77b  mov     rdx, rdi; struct MSMSEC_INTF_CONTEXT *
0x18002a77e  call    ?PostCallbackActions@@YAKPEAXPEAUMSMSEC_INTF_CONTEXT@@PEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z; PostCallbackActions(void *,MSMSEC_INTF_CONTEXT *,MSMSEC_PORT_CONTEXT *,_AUTHMGR_LOCK_STATE *)
0x18002a783  jmp     short loc_18002A800
0x18002a785  mov     ecx, [rdi+9C0h]; unsigned int
0x18002a78b  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18002a792  mov     dword ptr [r14+0Ch], 1
0x18002a79a  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18002a79f  lea     rdx, [rdi+9D0h]
0x18002a7a6  mov     r9d, 0CEh
0x18002a7ac  lea     r8, aPrecallbackact; "PreCallbackActions"
0x18002a7b3  mov     rcx, rdi
0x18002a7b6  call    cs:__imp_ReleaseWriteLock
0x18002a7bd  nop     dword ptr [rax+rax+00h]
0x18002a7c2  mov     [r14], esi
0x18002a7c5  mov     rsi, [rbp+arg_18]
0x18002a7c9  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x18002a7cc  call    ?SecMgrLockAndCheckPortActive@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrLockAndCheckPortActive(MSMSEC_PORT_CONTEXT *)
0x18002a7d1  mov     ebx, eax
0x18002a7d3  test    eax, eax
0x18002a7d5  jnz     loc_18002A8C3
0x18002a7db  mov     eax, [rsi+3A8h]
0x18002a7e1  mov     dword ptr [r14+8], 1
0x18002a7e9  cmp     r13, rax
0x18002a7ec  jnz     loc_18002A9FC
0x18002a7f2  mov     [r15], rsi
0x18002a7f5  lea     r15, WPP_GLOBAL_Control
0x18002a7fc  mov     [r12], rdi
0x18002a800  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a807  jmp     short loc_18002A858
0x18002a809  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a810  lea     r15, WPP_GLOBAL_Control
0x18002a817  cmp     rcx, r15
0x18002a81a  jnz     loc_18002A93B
0x18002a820  mov     rdi, [rbp+arg_10]
0x18002a824  jmp     loc_18002A771
0x18002a829  test    dword ptr [rcx+44h], 100h
0x18002a830  jz      loc_18002A686
0x18002a836  mov     rcx, [rcx+38h]
0x18002a83a  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002a841  mov     edx, 13h
0x18002a846  call    WPP_SF_
0x18002a84b  jmp     loc_18002A686
0x18002a850  test    ebx, ebx
0x18002a852  jnz     loc_18002A771
0x18002a858  cmp     rcx, r15
0x18002a85b  jnz     short loc_18002A878
0x18002a85d  mov     eax, ebx
0x18002a85f  mov     rbx, [rsp+50h+arg_8]
0x18002a867  add     rsp, 50h
0x18002a86b  pop     r15
0x18002a86d  pop     r14
0x18002a86f  pop     r13
0x18002a871  pop     r12
0x18002a873  pop     rdi
0x18002a874  pop     rsi
0x18002a875  pop     rbp
0x18002a876  retn
0x18002a878  test    dword ptr [rcx+44h], 100h
0x18002a87f  jz      short loc_18002A85D
0x18002a881  mov     rcx, [rcx+38h]
0x18002a885  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002a88c  mov     edx, 1Bh
0x18002a891  mov     r9d, ebx
0x18002a894  call    WPP_SF_d
0x18002a899  jmp     short loc_18002A85D
0x18002a89b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8a2  lea     r15, WPP_GLOBAL_Control
0x18002a8a9  cmp     rcx, r15
0x18002a8ac  jz      loc_18002A771
0x18002a8b2  test    byte ptr [rcx+44h], 1
0x18002a8b6  jz      loc_18002A771
0x18002a8bc  mov     edx, 14h
0x18002a8c1  jmp     short loc_18002A8E9
0x18002a8c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8ca  lea     r15, WPP_GLOBAL_Control
0x18002a8d1  cmp     rcx, r15
0x18002a8d4  jz      loc_18002A771
0x18002a8da  test    byte ptr [rcx+44h], 1
0x18002a8de  jz      loc_18002A771
0x18002a8e4  mov     edx, 19h
0x18002a8e9  mov     r9d, eax
0x18002a8ec  jmp     loc_18002AA2A
0x18002a8f1  mov     ebx, 490h
0x18002a8f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8fd  lea     r15, WPP_GLOBAL_Control
0x18002a904  cmp     rcx, r15
0x18002a907  jz      loc_18002A850
0x18002a90d  test    byte ptr [rcx+44h], 1
0x18002a911  jz      loc_18002A850
0x18002a917  mov     rcx, [rcx+38h]
0x18002a91b  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002a922  mov     edx, 15h
0x18002a927  mov     r9d, ebx
0x18002a92a  call    WPP_SF_d
0x18002a92f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a936  jmp     loc_18002A850
0x18002a93b  test    [rcx+44h], dil
0x18002a93f  jz      loc_18002A820
0x18002a945  mov     rcx, [rcx+38h]
0x18002a949  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002a950  mov     edx, 16h
0x18002a955  mov     r9d, eax
0x18002a958  call    WPP_SF_d
0x18002a95d  jmp     loc_18002A820
0x18002a962  mov     ebx, 139Fh
0x18002a967  mov     r11, cs:WPP_GLOBAL_Control
0x18002a96e  lea     r15, WPP_GLOBAL_Control
0x18002a975  cmp     r11, r15
0x18002a978  jz      loc_18002A771
0x18002a97e  test    byte ptr [r11+44h], 1
0x18002a983  jz      loc_18002A771
0x18002a989  mov     r10d, [rdi+0AA4h]
0x18002a990  mov     r12d, 7
0x18002a996  mov     ecx, r12d
0x18002a999  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x18002a99e  mov     ecx, r10d
0x18002a9a1  mov     r8, rax
0x18002a9a4  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x18002a9a9  mov     rcx, [r11+38h]
0x18002a9ad  lea     edx, [r12+10h]
0x18002a9b2  mov     [rsp+50h+var_20], r12d
0x18002a9b7  mov     r9, rax
0x18002a9ba  mov     [rsp+50h+var_28], r8
0x18002a9bf  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002a9c6  mov     [rsp+50h+var_30], r10d
0x18002a9cb  call    WPP_SF_SLSL
0x18002a9d0  jmp     loc_18002A771
0x18002a9d5  test    byte ptr [rcx+44h], 1
0x18002a9d9  jz      loc_18002A76D
0x18002a9df  mov     rcx, [rcx+38h]
0x18002a9e3  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002a9ea  mov     edx, 18h
0x18002a9ef  mov     r9d, eax
0x18002a9f2  call    WPP_SF_d
0x18002a9f7  jmp     loc_18002A76D
0x18002a9fc  mov     ebx, 3EBh
0x18002aa01  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa08  lea     r15, WPP_GLOBAL_Control
0x18002aa0f  cmp     rcx, r15
0x18002aa12  jz      loc_18002A771
0x18002aa18  test    byte ptr [rcx+44h], 1
0x18002aa1c  jz      loc_18002A771
0x18002aa22  mov     edx, 1Ah
0x18002aa27  mov     r9d, ebx
0x18002aa2a  mov     rcx, [rcx+38h]
0x18002aa2e  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002aa35  call    WPP_SF_d
0x18002aa3a  jmp     loc_18002A771
```
