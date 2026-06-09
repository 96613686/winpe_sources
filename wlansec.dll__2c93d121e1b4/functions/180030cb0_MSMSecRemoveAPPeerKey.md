# MSMSecRemoveAPPeerKey

- ea: `0x180030cb0`
- end: `0x180030fe6`
- name: `MSMSecRemoveAPPeerKey`
- size: `822`
- prototype: `__int64 __fastcall(void *, unsigned __int8 (*)[6])`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000a26c`
- `0x1800125b0`
- `0x180013bc0`
- `0x1800148d0`
- `0x180014998`
- `0x1800163e0`
- `0x1800169c0`
- `0x180016a08`
- `0x18001a23c`
- `0x180030cb0`
- `0x180030fec`
- `0x1800558c0`
- `0x1800586e4`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180030f33`
- `MobileNetworking!ReleaseWriteLock` at `0x180030f33`

## string_xrefs

- `0x180030d0e`: `MSMSecRemoveAPPeerKey`
- `0x180030f29`: `MSMSecRemoveAPPeerKey`
- `0x180030f57`: `MSMSecRemoveAPPeerKey`
- `0x180030f95`: `MSMSecRemoveAPPeerKey`

## pseudocode

```c
__int64 __fastcall MSMSecRemoveAPPeerKey(void ***a1, unsigned __int8 (*a2)[6])
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  struct MSMSEC_INTF_CONTEXT *v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  unsigned int v13; // r10d
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // r11
  __int64 v17; // r8
  char v18; // r10
  struct MSMSEC_INTF_CONTEXT *v20; // [rsp+A0h] [rbp+18h] BYREF

  v20 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 283, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v4 = IncThreadCountAndCheckInitializedEx("MSMSecRemoveAPPeerKey", 2550);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v7 = 284;
LABEL_8:
      WPP_SF_d(v6[7], v7, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v4);
    }
  }
  else if ( a1 && a2 )
  {
    v4 = SecMgrValidateRefAndLockAdapter(a1, &v20);
    v5 = v4;
    if ( v4 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v7 = 286;
        goto LABEL_8;
      }
    }
    else
    {
      v8 = v20;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
        WPP_SF_LqDDDDDD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          287,
          &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
          *((unsigned int *)v20 + 624),
          a1,
          (*a2)[0],
          (*a2)[6],
          (*a2)[12],
          (*a2)[18],
          (*a2)[24],
          (*a2)[30]);
      if ( (unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v8 + 681), 17) )
      {
        if ( (unsigned int)IntfIsInAPMode(v8) )
        {
          if ( *((_QWORD *)v8 + 348) )
          {
            if ( !RemoveFromPeerKeyList(a2, (struct _LIST_ENTRY *)v8 + 169, (unsigned int *)v8 + 680) )
            {
              v5 = 1168;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 290, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
            }
          }
        }
        else
        {
          v5 = 5023;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              289,
              &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
              *((unsigned int *)v8 + 624));
        }
      }
      else
      {
        v5 = 5023;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v12 = IntfActionStr(17, v9, v10, v11);
          v15 = IntfSecStateStr(v13, v14, v12);
          WPP_SF_SLSL(
            *(_QWORD *)(v16 + 56),
            288,
            (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
            v15,
            v18,
            v17,
            17);
        }
      }
      TraceAdapterId(*((_DWORD *)v8 + 624), "<<< Unlocking <<<");
      ReleaseWriteLock(v8, (char *)v8 + 2512, "MSMSecRemoveAPPeerKey", 2608);
      TraceAdapterId(*((_DWORD *)v8 + 624), "<<< Derefing <<<");
      SecMgrDerefAdapterEx(v8, "MSMSecRemoveAPPeerKey", 2612);
    }
  }
  else
  {
    v5 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 285, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  }
  DecThreadCountEx("MSMSecRemoveAPPeerKey", 2614);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 291, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180030cb0  mov     rax, rsp
0x180030cb3  mov     [rax+8], rbx
0x180030cb7  mov     [rax+10h], rbp
0x180030cbb  push    rsi
0x180030cbc  push    rdi
0x180030cbd  push    r12
0x180030cbf  push    r14
0x180030cc1  push    r15
0x180030cc3  sub     rsp, 60h
0x180030cc7  mov     rbp, rdx
0x180030cca  mov     qword ptr [rax+18h], 0
0x180030cd2  mov     r14, rcx
0x180030cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180030cdc  lea     r15, WPP_GLOBAL_Control
0x180030ce3  lea     r12, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180030cea  cmp     rcx, r15
0x180030ced  jz      short loc_180030D09
0x180030cef  test    dword ptr [rcx+44h], 100h
0x180030cf6  jz      short loc_180030D09
0x180030cf8  mov     rcx, [rcx+38h]
0x180030cfc  mov     edx, 11Bh
0x180030d01  mov     r8, r12
0x180030d04  call    WPP_SF_
0x180030d09  mov     edx, 9F6h; int
0x180030d0e  lea     rcx, aMsmsecremoveap_0; "MSMSecRemoveAPPeerKey"
0x180030d15  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x180030d1a  mov     edi, eax
0x180030d1c  test    eax, eax
0x180030d1e  jz      short loc_180030D53
0x180030d20  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d27  cmp     rcx, r15
0x180030d2a  jz      loc_180030F90
0x180030d30  test    byte ptr [rcx+44h], 1
0x180030d34  jz      loc_180030F90
0x180030d3a  mov     edx, 11Ch
0x180030d3f  mov     rcx, [rcx+38h]
0x180030d43  mov     r9d, eax
0x180030d46  mov     r8, r12
0x180030d49  call    WPP_SF_d
0x180030d4e  jmp     loc_180030F90
0x180030d53  test    r14, r14
0x180030d56  jz      loc_180030F68
0x180030d5c  test    rbp, rbp
0x180030d5f  jz      loc_180030F68
0x180030d65  lea     rdx, [rsp+88h+arg_10]; struct MSMSEC_INTF_CONTEXT **
0x180030d6d  mov     rcx, r14; void *
0x180030d70  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x180030d75  mov     edi, eax
0x180030d77  test    eax, eax
0x180030d79  jz      short loc_180030D9C
0x180030d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d82  cmp     rcx, r15
0x180030d85  jz      loc_180030F90
0x180030d8b  test    byte ptr [rcx+44h], 1
0x180030d8f  jz      loc_180030F90
0x180030d95  mov     edx, 11Eh
0x180030d9a  jmp     short loc_180030D3F
0x180030d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030da3  mov     rsi, [rsp+88h+arg_10]
0x180030dab  cmp     rcx, r15
0x180030dae  jz      short loc_180030E0B
0x180030db0  test    byte ptr [rcx+44h], 20h
0x180030db4  jz      short loc_180030E0B
0x180030db6  movzx   r8d, byte ptr [rbp+18h]
0x180030dbb  mov     edx, 11Fh
0x180030dc0  movzx   r9d, byte ptr [rbp+12h]
0x180030dc5  movzx   eax, byte ptr [rbp+1Eh]
0x180030dc9  movzx   r10d, byte ptr [rbp+0Ch]
0x180030dce  movzx   r11d, byte ptr [rbp+6]
0x180030dd3  movzx   ebx, byte ptr [rbp+0]
0x180030dd7  mov     rcx, [rcx+38h]
0x180030ddb  mov     [rsp+88h+var_38], eax
0x180030ddf  mov     [rsp+88h+var_40], r8d
0x180030de4  mov     r8, r12
0x180030de7  mov     [rsp+88h+var_48], r9d
0x180030dec  mov     r9d, [rsi+9C0h]
0x180030df3  mov     [rsp+88h+var_50], r10d
0x180030df8  mov     [rsp+88h+var_58], r11d
0x180030dfd  mov     dword ptr [rsp+88h+var_60], ebx
0x180030e01  mov     [rsp+88h+var_68], r14
0x180030e06  call    WPP_SF_LqDDDDDD
0x180030e0b  mov     ecx, [rsi+0AA4h]
0x180030e11  mov     ebx, 11h
0x180030e16  mov     edx, ebx
0x180030e18  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x180030e1d  test    eax, eax
0x180030e1f  jnz     short loc_180030E81
0x180030e21  mov     edi, 139Fh
0x180030e26  mov     r11, cs:WPP_GLOBAL_Control
0x180030e2d  cmp     r11, r15
0x180030e30  jz      loc_180030F0A
0x180030e36  test    byte ptr [r11+44h], 1
0x180030e3b  jz      loc_180030F0A
0x180030e41  mov     r10d, [rsi+0AA4h]
0x180030e48  mov     ecx, ebx
0x180030e4a  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x180030e4f  mov     ecx, r10d
0x180030e52  mov     r8, rax
0x180030e55  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x180030e5a  mov     rcx, [r11+38h]
0x180030e5e  mov     r9, rax
0x180030e61  mov     [rsp+88h+var_58], ebx
0x180030e65  mov     edx, 120h
0x180030e6a  mov     [rsp+88h+var_60], r8
0x180030e6f  mov     r8, r12
0x180030e72  mov     dword ptr [rsp+88h+var_68], r10d
0x180030e77  call    WPP_SF_SLSL
0x180030e7c  jmp     loc_180030F0A
0x180030e81  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x180030e84  call    ?IntfIsInAPMode@@YAHPEAUMSMSEC_INTF_CONTEXT@@@Z; IntfIsInAPMode(MSMSEC_INTF_CONTEXT *)
0x180030e89  test    eax, eax
0x180030e8b  jnz     short loc_180030EBE
0x180030e8d  mov     edi, 139Fh
0x180030e92  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e99  cmp     rcx, r15
0x180030e9c  jz      short loc_180030F0A
0x180030e9e  test    byte ptr [rcx+44h], 1
0x180030ea2  jz      short loc_180030F0A
0x180030ea4  mov     r9d, [rsi+9C0h]
0x180030eab  mov     edx, 121h
0x180030eb0  mov     rcx, [rcx+38h]
0x180030eb4  mov     r8, r12
0x180030eb7  call    WPP_SF_d
0x180030ebc  jmp     short loc_180030F0A
0x180030ebe  cmp     qword ptr [rsi+0AE0h], 0
0x180030ec6  jz      short loc_180030F0A
0x180030ec8  lea     r8, [rsi+0AA0h]; unsigned int *
0x180030ecf  mov     rcx, rbp; unsigned __int8 (*)[6]
0x180030ed2  lea     rdx, [rsi+0A90h]; struct _LIST_ENTRY *
0x180030ed9  call    ?RemoveFromPeerKeyList@@YA_NAEAY05$$CBEPEAU_LIST_ENTRY@@AEAK@Z; RemoveFromPeerKeyList(uchar const (&)[6],_LIST_ENTRY *,ulong &)
0x180030ede  test    al, al
0x180030ee0  jnz     short loc_180030F0A
0x180030ee2  mov     edi, 490h
0x180030ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x180030eee  cmp     rcx, r15
0x180030ef1  jz      short loc_180030F0A
0x180030ef3  test    byte ptr [rcx+44h], 1
0x180030ef7  jz      short loc_180030F0A
0x180030ef9  mov     rcx, [rcx+38h]
0x180030efd  mov     edx, 122h
0x180030f02  mov     r8, r12
0x180030f05  call    WPP_SF_
0x180030f0a  mov     ecx, [rsi+9C0h]; unsigned int
0x180030f10  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180030f17  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180030f1c  lea     rdx, [rsi+9D0h]
0x180030f23  mov     r9d, 0A30h
0x180030f29  lea     r8, aMsmsecremoveap_0; "MSMSecRemoveAPPeerKey"
0x180030f30  mov     rcx, rsi
0x180030f33  call    cs:__imp_ReleaseWriteLock
0x180030f3a  nop     dword ptr [rax+rax+00h]
0x180030f3f  mov     ecx, [rsi+9C0h]; unsigned int
0x180030f45  lea     rdx, aDerefing; "<<< Derefing <<<"
0x180030f4c  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180030f51  mov     r8d, 0A34h; int
0x180030f57  lea     rdx, aMsmsecremoveap_0; "MSMSecRemoveAPPeerKey"
0x180030f5e  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x180030f61  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180030f66  jmp     short loc_180030F90
0x180030f68  mov     edi, 57h ; 'W'
0x180030f6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030f74  cmp     rcx, r15
0x180030f77  jz      short loc_180030F90
0x180030f79  test    byte ptr [rcx+44h], 1
0x180030f7d  jz      short loc_180030F90
0x180030f7f  mov     rcx, [rcx+38h]
0x180030f83  mov     edx, 11Dh
0x180030f88  mov     r8, r12
0x180030f8b  call    WPP_SF_
0x180030f90  mov     edx, 0A36h; int
0x180030f95  lea     rcx, aMsmsecremoveap_0; "MSMSecRemoveAPPeerKey"
0x180030f9c  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x180030fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180030fa8  cmp     rcx, r15
0x180030fab  jz      short loc_180030FCA
0x180030fad  test    dword ptr [rcx+44h], 100h
0x180030fb4  jz      short loc_180030FCA
0x180030fb6  mov     rcx, [rcx+38h]
0x180030fba  mov     edx, 123h
0x180030fbf  mov     r9d, edi
0x180030fc2  mov     r8, r12
0x180030fc5  call    WPP_SF_d
0x180030fca  lea     r11, [rsp+88h+var_28]
0x180030fcf  mov     eax, edi
0x180030fd1  mov     rbx, [r11+30h]
0x180030fd5  mov     rbp, [r11+38h]
0x180030fd9  mov     rsp, r11
0x180030fdc  pop     r15
0x180030fde  pop     r14
0x180030fe0  pop     r12
0x180030fe2  pop     rdi
0x180030fe3  pop     rsi
0x180030fe4  retn
```
