# WpsAuthMgrSetPortParams(MSMSEC_PORT_CONTEXT *)

- ea: `0x180016bdc`
- end: `0x180016e21`
- name: `?WpsAuthMgrSetPortParams@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z`
- size: `581`
- prototype: `unsigned int __fastcall(struct MSMSEC_PORT_CONTEXT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800166b4`

## callees

- `0x180002af4`
- `0x180002c98`
- `0x18000892c`
- `0x180008998`
- `0x1800169c0`
- `0x180016bdc`
- `0x18002b078`
- `0x18002bb08`
- `0x1800747f4`
- `0x180074ea8`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180016da9`
- `MobileNetworking!ReleaseWriteLock` at `0x180016da9`
- `MobileNetworking!AcquireWriteLock` at `0x180016d5d`
- `MobileNetworking!AcquireWriteLock` at `0x180016d5d`

## pseudocode

```c
__int64 __fastcall WpsAuthMgrSetPortParams(struct MSMSEC_PORT_CONTEXT *a1)
{
  unsigned int v2; // edi
  PVOID *v3; // rcx
  unsigned int updated; // eax
  __int64 v6; // rdx
  __int64 v7; // r9
  void *v8; // rsi
  void *v9; // [rsp+50h] [rbp+8h] BYREF
  void *v10; // [rsp+58h] [rbp+10h] BYREF

  v9 = 0;
  v10 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 60, &WPP_35b9b04c1d1e363998ad79539c1c45df_Traceguids);
  if ( !*(_DWORD *)(*((_QWORD *)a1 + 3) + 2780LL)
    || !(unsigned int)WpsAuthMgrIsAssociationWCNCompatible(*((struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS **)a1 + 61)) )
  {
    v2 = 0;
    *((_DWORD *)a1 + 498) = 1;
LABEL_4:
    v3 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_5;
  }
  updated = AddHandleTableEntry(*((void **)a1 + 3), &v9);
  v2 = updated;
  if ( !updated )
  {
    v8 = v9;
    updated = UpdateHandleTableEntry(v9, (unsigned __int8 (*)[6])((char *)a1 + 302), a1);
    v2 = updated;
    if ( !updated )
    {
      TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), ">>> Locking >>>");
      AcquireWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "WpsAuthMgrSetPortParams", 552);
      v2 = WpsAuthMgrCreateOneXPort(v8, (unsigned __int8 (*)[6])((char *)a1 + 302), &v10);
      TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), "<<< Unlocking <<<");
      ReleaseWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "WpsAuthMgrSetPortParams", 556);
      if ( !v2 )
      {
        TracePortId(*((_DWORD *)a1 + 78), ">>> Refing >>>");
        SecMgrRefPortEx(a1, "WpsAuthMgrSetPortParams", 560);
        *((_QWORD *)a1 + 251) = v10;
        *((_DWORD *)a1 + 498) = 3;
        *((_QWORD *)a1 + 250) = v8;
        goto LABEL_4;
      }
      v3 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v2;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_5;
      v6 = 63;
      v7 = v2;
      goto LABEL_17;
    }
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v2;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_5;
    v6 = 62;
LABEL_16:
    v7 = updated;
LABEL_17:
    WPP_SF_d(v3[7], v6, &WPP_35b9b04c1d1e363998ad79539c1c45df_Traceguids, v7);
    goto LABEL_4;
  }
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v2;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v6 = 61;
    goto LABEL_16;
  }
LABEL_5:
  if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 17) & 0x100) != 0 )
    WPP_SF_d(v3[7], 64, &WPP_35b9b04c1d1e363998ad79539c1c45df_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180016bdc  mov     [rsp+arg_10], rbx
0x180016be1  push    rbp
0x180016be2  push    rsi
0x180016be3  push    rdi
0x180016be4  push    r12
0x180016be6  push    r15
0x180016be8  sub     rsp, 20h
0x180016bec  mov     rbx, rcx
0x180016bef  mov     [rsp+48h+arg_0], 0
0x180016bf8  mov     [rsp+48h+arg_8], 0
0x180016c01  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c08  lea     r15, WPP_GLOBAL_Control
0x180016c0f  lea     r12, WPP_35b9b04c1d1e363998ad79539c1c45df_Traceguids
0x180016c16  cmp     rcx, r15
0x180016c19  jnz     short loc_180016C54
0x180016c1b  mov     rax, [rbx+18h]
0x180016c1f  cmp     dword ptr [rax+0ADCh], 0
0x180016c26  jnz     short loc_180016C8F
0x180016c28  xor     edi, edi
0x180016c2a  mov     dword ptr [rbx+7C8h], 1
0x180016c34  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c3b  cmp     rcx, r15
0x180016c3e  jnz     short loc_180016C70
0x180016c40  mov     rbx, [rsp+48h+arg_10]
0x180016c45  mov     eax, edi
0x180016c47  add     rsp, 20h
0x180016c4b  pop     r15
0x180016c4d  pop     r12
0x180016c4f  pop     rdi
0x180016c50  pop     rsi
0x180016c51  pop     rbp
0x180016c52  retn
0x180016c54  test    dword ptr [rcx+44h], 100h
0x180016c5b  jz      short loc_180016C1B
0x180016c5d  mov     rcx, [rcx+38h]
0x180016c61  mov     edx, 3Ch ; '<'
0x180016c66  mov     r8, r12
0x180016c69  call    WPP_SF_
0x180016c6e  jmp     short loc_180016C1B
0x180016c70  test    dword ptr [rcx+44h], 100h
0x180016c77  jz      short loc_180016C40
0x180016c79  mov     rcx, [rcx+38h]
0x180016c7d  mov     edx, 40h ; '@'
0x180016c82  mov     r9d, edi
0x180016c85  mov     r8, r12
0x180016c88  call    WPP_SF_d
0x180016c8d  jmp     short loc_180016C40
0x180016c8f  mov     rcx, [rbx+1E8h]; struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *
0x180016c96  call    ?WpsAuthMgrIsAssociationWCNCompatible@@YAHPEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@@Z; WpsAuthMgrIsAssociationWCNCompatible(DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)
0x180016c9b  test    eax, eax
0x180016c9d  jz      short loc_180016C28
0x180016c9f  mov     rcx, [rbx+18h]; void *
0x180016ca3  lea     rdx, [rsp+48h+arg_0]; void **
0x180016ca8  call    ?AddHandleTableEntry@@YAKPEAXPEAPEAX@Z; AddHandleTableEntry(void *,void * *)
0x180016cad  mov     edi, eax
0x180016caf  test    eax, eax
0x180016cb1  jz      short loc_180016CF3
0x180016cb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cba  cmp     rcx, r15
0x180016cbd  jz      short loc_180016C40
0x180016cbf  test    byte ptr [rcx+44h], 1
0x180016cc3  jz      loc_180016C3B
0x180016cc9  mov     edx, 3Dh ; '='
0x180016cce  jmp     short loc_180016CD5
0x180016cd0  mov     edx, 3Eh ; '>'
0x180016cd5  mov     r9d, eax
0x180016cd8  jmp     short loc_180016CE2
0x180016cda  mov     edx, 3Fh ; '?'
0x180016cdf  mov     r9d, edi
0x180016ce2  mov     rcx, [rcx+38h]
0x180016ce6  mov     r8, r12
0x180016ce9  call    WPP_SF_d
0x180016cee  jmp     loc_180016C34
0x180016cf3  mov     rsi, [rsp+48h+arg_0]
0x180016cf8  lea     rbp, [rbx+12Eh]
0x180016cff  mov     rdx, rbp; unsigned __int8 (*)[6]
0x180016d02  mov     rcx, rsi; void *
0x180016d05  mov     r8, rbx; void *
0x180016d08  call    ?UpdateHandleTableEntry@@YAKPEAXPEAY05E0@Z; UpdateHandleTableEntry(void *,uchar (*)[6],void *)
0x180016d0d  mov     edi, eax
0x180016d0f  test    eax, eax
0x180016d11  jz      short loc_180016D2F
0x180016d13  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d1a  cmp     rcx, r15
0x180016d1d  jz      loc_180016C40
0x180016d23  test    byte ptr [rcx+44h], 1
0x180016d27  jz      loc_180016C3B
0x180016d2d  jmp     short loc_180016CD0
0x180016d2f  mov     rcx, [rbx+18h]
0x180016d33  lea     rdx, aLocking; ">>> Locking >>>"
0x180016d3a  mov     ecx, [rcx+9C0h]; unsigned int
0x180016d40  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180016d45  mov     rcx, [rbx+18h]
0x180016d49  lea     r8, aWpsauthmgrsetp; "WpsAuthMgrSetPortParams"
0x180016d50  mov     r9d, 228h
0x180016d56  lea     rdx, [rcx+9D0h]
0x180016d5d  call    cs:__imp_AcquireWriteLock
0x180016d64  nop     dword ptr [rax+rax+00h]
0x180016d69  lea     r8, [rsp+48h+arg_8]; void **
0x180016d6e  mov     rdx, rbp; unsigned __int8 (*)[6]
0x180016d71  mov     rcx, rsi; void *
0x180016d74  call    ?WpsAuthMgrCreateOneXPort@@YAKPEAXPEAY05EPEAPEAX@Z; WpsAuthMgrCreateOneXPort(void *,uchar (*)[6],void * *)
0x180016d79  mov     rcx, [rbx+18h]
0x180016d7d  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180016d84  mov     edi, eax
0x180016d86  mov     ecx, [rcx+9C0h]; unsigned int
0x180016d8c  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180016d91  mov     rcx, [rbx+18h]
0x180016d95  lea     r8, aWpsauthmgrsetp; "WpsAuthMgrSetPortParams"
0x180016d9c  mov     r9d, 22Ch
0x180016da2  lea     rdx, [rcx+9D0h]
0x180016da9  call    cs:__imp_ReleaseWriteLock
0x180016db0  nop     dword ptr [rax+rax+00h]
0x180016db5  test    edi, edi
0x180016db7  jz      short loc_180016DD8
0x180016db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180016dc0  cmp     rcx, r15
0x180016dc3  jz      loc_180016C40
0x180016dc9  test    byte ptr [rcx+44h], 1
0x180016dcd  jz      loc_180016C3B
0x180016dd3  jmp     loc_180016CDA
0x180016dd8  mov     ecx, [rbx+138h]; unsigned int
0x180016dde  lea     rdx, aRefing; ">>> Refing >>>"
0x180016de5  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180016dea  mov     r8d, 230h; int
0x180016df0  lea     rdx, aWpsauthmgrsetp; "WpsAuthMgrSetPortParams"
0x180016df7  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x180016dfa  call    ?SecMgrRefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrRefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x180016dff  mov     rax, [rsp+48h+arg_8]
0x180016e04  mov     [rbx+7D8h], rax
0x180016e0b  mov     dword ptr [rbx+7C8h], 3
0x180016e15  mov     [rbx+7D0h], rsi
0x180016e1c  jmp     loc_180016C34
```
