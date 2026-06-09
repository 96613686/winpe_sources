# SecMgrReviveCacheEntryAction(PORT_EVENT *,ulong *)

- ea: `0x180023fc0`
- end: `0x180024322`
- name: `?SecMgrReviveCacheEntryAction@@YAKPEAUPORT_EVENT@@PEAK@Z`
- size: `866`
- prototype: `unsigned int __fastcall(struct PORT_EVENT *, unsigned int *)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000c444`
- `0x18000c730`
- `0x1800169c0`
- `0x18001f1d4`
- `0x18001f29c`
- `0x18001f2b8`
- `0x18002244c`
- `0x180023fc0`
- `0x180024328`
- `0x18002da24`
- `0x18003acd4`
- `0x180041b90`
- `0x180044554`
- `0x180056a44`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180024311`
- `MobileNetworking!ReleaseWriteLock` at `0x180024311`
- `MobileNetworking!AcquireWriteLock` at `0x1800242c7`
- `MobileNetworking!AcquireWriteLock` at `0x1800242c7`

## string_xrefs

- `0x1800242b3`: `SecMgrReviveCacheEntryAction`
- `0x1800242fd`: `SecMgrReviveCacheEntryAction`

## pseudocode

```c
__int64 __fastcall SecMgrReviveCacheEntryAction(struct PORT_EVENT *a1, unsigned int *a2)
{
  PVOID *v3; // rcx
  __int64 v4; // rbx
  unsigned int MSMSecMemory; // eax
  unsigned int v6; // esi
  PVOID *v7; // r10
  void *v9; // rbp
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // esi
  int v13; // eax
  _QWORD *v14; // r10
  __int64 v15; // rdx
  struct MSMSEC_PORT_CONTEXT *v16; // rcx
  int v17; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int8 *v18; // [rsp+70h] [rbp+18h]
  void *v19; // [rsp+78h] [rbp+20h]

  v19 = 0;
  v18 = 0;
  v17 = 0;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 43, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  v4 = *((_QWORD *)a1 + 3);
  if ( *((_DWORD *)a1 + 8) < 3u || *((_DWORD *)a1 + 10) != 3 || *((_DWORD *)a1 + 14) != 3 || *((_DWORD *)a1 + 18) != 3 )
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 68) & 2) != 0 )
      WPP_SF_(v3[7], 47, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
    goto LABEL_4;
  }
  MSMSecMemory = AllocateMSMSecMemory(*((unsigned int *)a1 + 11));
  v6 = MSMSecMemory;
  if ( !MSMSecMemory )
  {
    v9 = v19;
    memcpy_0(v19, *((const void **)a1 + 6), *((unsigned int *)a1 + 11));
    v12 = *((_DWORD *)a1 + 11);
    v13 = 0;
    v19 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
    {
      WPP_SF_LdL(*((_QWORD *)WPP_GLOBAL_Control + 7), v10, v11, *(unsigned int *)(v4 + 312), 0, v12);
      v13 = (int)v19;
    }
    *(_DWORD *)(v4 + 512) = v12;
    *(_DWORD *)(v4 + 516) = v13;
    *(_QWORD *)(v4 + 520) = v9;
    MSMSecMemory = AllocateMSMSecMemory(*((unsigned int *)a1 + 15));
    v6 = MSMSecMemory;
    if ( MSMSecMemory )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v15 = 45;
        goto LABEL_35;
      }
      goto LABEL_36;
    }
    memcpy_0(v18, *((const void **)a1 + 8), *((unsigned int *)a1 + 15));
    SetPortRecvKey((struct MSMSEC_PORT_CONTEXT *)v4, *((_DWORD *)a1 + 15), v18);
    MSMSecMemory = SecMgrProcessAuthParams(
                     (struct MSMSEC_PORT_CONTEXT *)v4,
                     *((_DWORD *)a1 + 19),
                     *((_DWORD **)a1 + 10),
                     &v17,
                     1);
    v6 = MSMSecMemory;
    if ( MSMSecMemory )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v15 = 46;
LABEL_35:
        WPP_SF_d(v14[7], v15, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids, MSMSecMemory);
        goto LABEL_36;
      }
      goto LABEL_36;
    }
LABEL_4:
    MSMSecMemory = CreateAndQueuePortEvent(v4, 24, 0);
    v6 = MSMSecMemory;
    if ( !MSMSecMemory )
    {
LABEL_5:
      v7 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_6;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v15 = 48;
      goto LABEL_35;
    }
    goto LABEL_36;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v15 = 44;
    goto LABEL_35;
  }
LABEL_36:
  if ( *(_DWORD *)(v4 + 504) )
    FreePortSendKeys((struct MSMSEC_PORT_CONTEXT *)v4);
  if ( (unsigned int)RawDataIsNonEmpty(v4 + 640) )
    FreePortRecvKey((struct MSMSEC_PORT_CONTEXT *)v4);
  if ( (unsigned int)IsPortAuthParamsAvailable((struct MSMSEC_PORT_CONTEXT *)v4) )
  {
    FreePortAuthParams(v16);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v17 )
  {
    TraceAdapterId(*(_DWORD *)(*(_QWORD *)(v4 + 24) + 2496LL), ">>> Locking >>>");
    AcquireWriteLock(*(_QWORD *)(v4 + 24), *(_QWORD *)(v4 + 24) + 2512LL, "SecMgrReviveCacheEntryAction", 567);
    PmkCacheInvalidate((struct MSMSEC_PMKCACHE_CONTEXT *)(*(_QWORD *)(v4 + 24) + 3000LL));
    TraceAdapterId(*(_DWORD *)(*(_QWORD *)(v4 + 24) + 2496LL), "<<< Unlocking <<<");
    ReleaseWriteLock(*(_QWORD *)(v4 + 24), *(_QWORD *)(v4 + 24) + 2512LL, "SecMgrReviveCacheEntryAction", 569);
    goto LABEL_5;
  }
LABEL_6:
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x100) != 0 )
    WPP_SF_d(v7[7], 49, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180023fc0  mov     rax, rsp
0x180023fc3  mov     [rax+10h], rbx
0x180023fc7  push    rbp
0x180023fc8  push    rsi
0x180023fc9  push    rdi
0x180023fca  push    r12
0x180023fcc  push    r15
0x180023fce  sub     rsp, 30h
0x180023fd2  mov     rdi, rcx
0x180023fd5  mov     qword ptr [rax+20h], 0
0x180023fdd  mov     qword ptr [rax+18h], 0
0x180023fe5  mov     dword ptr [rax+8], 0
0x180023fec  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ff3  lea     r15, WPP_GLOBAL_Control
0x180023ffa  lea     r12, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x180024001  cmp     rcx, r15
0x180024004  jnz     loc_18002408F
0x18002400a  cmp     dword ptr [rdi+20h], 3
0x18002400e  mov     rbx, [rdi+18h]
0x180024012  jnb     loc_1800240B9
0x180024018  cmp     rcx, r15
0x18002401b  jnz     short loc_180024076
0x18002401d  xor     r8d, r8d
0x180024020  mov     rcx, rbx
0x180024023  lea     edx, [r8+18h]
0x180024027  call    ?CreateAndQueuePortEvent@@YAKPEAUMSMSEC_PORT_CONTEXT@@W4MSMSEC_PORT_EVENT_TYPE@@H@Z; CreateAndQueuePortEvent(MSMSEC_PORT_CONTEXT *,MSMSEC_PORT_EVENT_TYPE,int)
0x18002402c  mov     esi, eax
0x18002402e  test    eax, eax
0x180024030  jnz     loc_180024211
0x180024036  mov     r10, cs:WPP_GLOBAL_Control
0x18002403d  cmp     r10, r15
0x180024040  jnz     short loc_180024056
0x180024042  mov     rbx, [rsp+58h+arg_8]
0x180024047  mov     eax, esi
0x180024049  add     rsp, 30h
0x18002404d  pop     r15
0x18002404f  pop     r12
0x180024051  pop     rdi
0x180024052  pop     rsi
0x180024053  pop     rbp
0x180024054  retn
0x180024056  test    dword ptr [r10+44h], 100h
0x18002405e  jz      short loc_180024042
0x180024060  mov     rcx, [r10+38h]
0x180024064  mov     edx, 31h ; '1'
0x180024069  mov     r9d, esi
0x18002406c  mov     r8, r12
0x18002406f  call    WPP_SF_d
0x180024074  jmp     short loc_180024042
0x180024076  test    byte ptr [rcx+44h], 2
0x18002407a  jz      short loc_18002401D
0x18002407c  mov     rcx, [rcx+38h]
0x180024080  mov     edx, 2Fh ; '/'
0x180024085  mov     r8, r12
0x180024088  call    WPP_SF_
0x18002408d  jmp     short loc_18002401D
0x18002408f  test    dword ptr [rcx+44h], 100h
0x180024096  jz      loc_18002400A
0x18002409c  mov     rcx, [rcx+38h]
0x1800240a0  mov     edx, 2Bh ; '+'
0x1800240a5  mov     r8, r12
0x1800240a8  call    WPP_SF_
0x1800240ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800240b4  jmp     loc_18002400A
0x1800240b9  cmp     dword ptr [rdi+28h], 3
0x1800240bd  jnz     loc_180024018
0x1800240c3  cmp     dword ptr [rdi+38h], 3
0x1800240c7  jnz     loc_180024018
0x1800240cd  cmp     dword ptr [rdi+48h], 3
0x1800240d1  jnz     loc_180024018
0x1800240d7  mov     ecx, [rdi+2Ch]; dwBytes
0x1800240da  lea     rdx, [rsp+58h+arg_18]
0x1800240df  call    AllocateMSMSecMemory
0x1800240e4  mov     esi, eax
0x1800240e6  test    eax, eax
0x1800240e8  jnz     loc_1800241DD
0x1800240ee  mov     rbp, [rsp+58h+arg_18]
0x1800240f3  mov     r8d, [rdi+2Ch]; Size
0x1800240f7  mov     rcx, rbp; void *
0x1800240fa  mov     rdx, [rdi+30h]; Src
0x1800240fe  call    memcpy_0
0x180024103  mov     esi, [rdi+2Ch]
0x180024106  xor     eax, eax
0x180024108  mov     [rsp+58h+arg_18], rax
0x18002410d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024114  cmp     rcx, r15
0x180024117  jnz     loc_1800241B1
0x18002411d  mov     [rbx+200h], esi
0x180024123  lea     rdx, [rsp+58h+arg_10]
0x180024128  mov     [rbx+204h], eax
0x18002412e  mov     [rbx+208h], rbp
0x180024135  mov     ecx, [rdi+3Ch]; dwBytes
0x180024138  call    AllocateMSMSecMemory
0x18002413d  mov     esi, eax
0x18002413f  test    eax, eax
0x180024141  jnz     loc_1800241F7
0x180024147  mov     r8d, [rdi+3Ch]; Size
0x18002414b  mov     rdx, [rdi+40h]; Src
0x18002414f  mov     rcx, [rsp+58h+arg_10]; void *
0x180024154  call    memcpy_0
0x180024159  mov     r8, [rsp+58h+arg_10]; unsigned __int8 *
0x18002415e  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x180024161  mov     edx, [rdi+3Ch]; unsigned int
0x180024164  call    ?SetPortRecvKey@@YAXPEAUMSMSEC_PORT_CONTEXT@@KPEAE@Z; SetPortRecvKey(MSMSEC_PORT_CONTEXT *,ulong,uchar *)
0x180024169  mov     r8, [rdi+50h]; void *
0x18002416d  lea     r9, [rsp+58h+arg_0]; int *
0x180024172  mov     edx, [rdi+4Ch]; unsigned int
0x180024175  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x180024178  mov     [rsp+58h+var_38], 1; int
0x180024180  call    ?SecMgrProcessAuthParams@@YAKPEAUMSMSEC_PORT_CONTEXT@@KPEAXPEAHH@Z; SecMgrProcessAuthParams(MSMSEC_PORT_CONTEXT *,ulong,void *,int *,int)
0x180024185  mov     esi, eax
0x180024187  test    eax, eax
0x180024189  jz      loc_18002401D
0x18002418f  mov     r10, cs:WPP_GLOBAL_Control
0x180024196  cmp     r10, r15
0x180024199  jz      loc_18002423F
0x18002419f  test    byte ptr [r10+44h], 1
0x1800241a4  jz      loc_18002423F
0x1800241aa  mov     edx, 2Eh ; '.'
0x1800241af  jmp     short loc_180024229
0x1800241b1  test    byte ptr [rcx+44h], 2
0x1800241b5  jz      loc_18002411D
0x1800241bb  mov     r9d, [rbx+138h]
0x1800241c2  mov     rcx, [rcx+38h]
0x1800241c6  mov     [rsp+58h+var_30], esi
0x1800241ca  mov     [rsp+58h+var_38], eax
0x1800241ce  call    WPP_SF_LdL
0x1800241d3  mov     rax, [rsp+58h+arg_18]
0x1800241d8  jmp     loc_18002411D
0x1800241dd  mov     r10, cs:WPP_GLOBAL_Control
0x1800241e4  cmp     r10, r15
0x1800241e7  jz      short loc_18002423F
0x1800241e9  test    byte ptr [r10+44h], 1
0x1800241ee  jz      short loc_18002423F
0x1800241f0  mov     edx, 2Ch ; ','
0x1800241f5  jmp     short loc_180024229
0x1800241f7  mov     r10, cs:WPP_GLOBAL_Control
0x1800241fe  cmp     r10, r15
0x180024201  jz      short loc_18002423F
0x180024203  test    byte ptr [r10+44h], 1
0x180024208  jz      short loc_18002423F
0x18002420a  mov     edx, 2Dh ; '-'
0x18002420f  jmp     short loc_180024229
0x180024211  mov     r10, cs:WPP_GLOBAL_Control
0x180024218  cmp     r10, r15
0x18002421b  jz      short loc_18002423F
0x18002421d  test    byte ptr [r10+44h], 1
0x180024222  jz      short loc_18002423F
0x180024224  mov     edx, 30h ; '0'
0x180024229  mov     rcx, [r10+38h]
0x18002422d  mov     r9d, eax
0x180024230  mov     r8, r12
0x180024233  call    WPP_SF_d
0x180024238  mov     r10, cs:WPP_GLOBAL_Control
0x18002423f  cmp     dword ptr [rbx+1F8h], 0
0x180024246  jz      short loc_180024257
0x180024248  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x18002424b  call    ?FreePortSendKeys@@YAXPEAUMSMSEC_PORT_CONTEXT@@@Z; FreePortSendKeys(MSMSEC_PORT_CONTEXT *)
0x180024250  mov     r10, cs:WPP_GLOBAL_Control
0x180024257  lea     rcx, [rbx+280h]
0x18002425e  call    RawDataIsNonEmpty
0x180024263  test    eax, eax
0x180024265  jz      short loc_180024276
0x180024267  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x18002426a  call    ?FreePortRecvKey@@YAXPEAUMSMSEC_PORT_CONTEXT@@@Z; FreePortRecvKey(MSMSEC_PORT_CONTEXT *)
0x18002426f  mov     r10, cs:WPP_GLOBAL_Control
0x180024276  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x180024279  call    ?IsPortAuthParamsAvailable@@YAHPEAUMSMSEC_PORT_CONTEXT@@@Z; IsPortAuthParamsAvailable(MSMSEC_PORT_CONTEXT *)
0x18002427e  test    eax, eax
0x180024280  jz      short loc_18002428E
0x180024282  call    ?FreePortAuthParams@@YAXPEAUMSMSEC_PORT_CONTEXT@@@Z; FreePortAuthParams(MSMSEC_PORT_CONTEXT *)
0x180024287  mov     r10, cs:WPP_GLOBAL_Control
0x18002428e  cmp     [rsp+58h+arg_0], 0
0x180024293  jz      loc_18002403D
0x180024299  mov     rcx, [rbx+18h]
0x18002429d  lea     rdx, aLocking; ">>> Locking >>>"
0x1800242a4  mov     ecx, [rcx+9C0h]; unsigned int
0x1800242aa  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800242af  mov     rcx, [rbx+18h]
0x1800242b3  lea     r8, aSecmgrreviveca; "SecMgrReviveCacheEntryAction"
0x1800242ba  mov     r9d, 237h
0x1800242c0  lea     rdx, [rcx+9D0h]
0x1800242c7  call    cs:__imp_AcquireWriteLock
0x1800242ce  nop     dword ptr [rax+rax+00h]
0x1800242d3  mov     rcx, [rbx+18h]
0x1800242d7  add     rcx, 0BB8h; struct MSMSEC_PMKCACHE_CONTEXT *
0x1800242de  call    ?PmkCacheInvalidate@@YAXPEAUMSMSEC_PMKCACHE_CONTEXT@@@Z; PmkCacheInvalidate(MSMSEC_PMKCACHE_CONTEXT *)
0x1800242e3  mov     rcx, [rbx+18h]
0x1800242e7  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800242ee  mov     ecx, [rcx+9C0h]; unsigned int
0x1800242f4  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800242f9  mov     rcx, [rbx+18h]
0x1800242fd  lea     r8, aSecmgrreviveca; "SecMgrReviveCacheEntryAction"
0x180024304  mov     r9d, 239h
0x18002430a  lea     rdx, [rcx+9D0h]
0x180024311  call    cs:__imp_ReleaseWriteLock
0x180024318  nop     dword ptr [rax+rax+00h]
0x18002431d  jmp     loc_180024036
```
