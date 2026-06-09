# Srv2DereferenceWorkItem

- ea: `0x140006ad0`
- end: `0x140007089`
- name: `Srv2DereferenceWorkItem`
- size: `1465`
- prototype: ``
- caller_count: `28`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004e50`
- `0x1400054c8`
- `0x1400055b0`
- `0x140006580`
- `0x140006a30`
- `0x140006ad0`
- `0x140007090`
- `0x140008410`
- `0x14000b3f0`
- `0x14001fb2c`
- `0x140029660`
- `0x140034780`
- `0x14005d3d0`
- `0x1400656fc`
- `0x140065d34`
- `0x140066474`
- `0x14006ba80`
- `0x14007197c`
- `0x140071c9c`
- `0x140074970`
- `0x14007e340`
- `0x14007ea50`
- `0x1400800c4`
- `0x140082ae0`
- `0x140086f00`
- `0x140088cf0`
- `0x14008d640`
- `0x1400921f0`

## callees

- `0x1400014d0`
- `0x140004960`
- `0x140005070`
- `0x140005470`
- `0x140006ad0`
- `0x14000ab3c`
- `0x140022a10`
- `0x140038490`
- `0x1400384d0`
- `0x1400602d0`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140006f46`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140006fd2`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140006f46`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140006fd2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006caf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006e52`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006caf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006e52`
- `ntoskrnl!KeGetCurrentIrql` at `0x140006b2f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140007061`
- `ntoskrnl!KeGetCurrentIrql` at `0x140006b2f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140007061`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140006d61`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140006d61`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006cf7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006e8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006cf7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006e8d`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000702a`
- `ntoskrnl!MmUnmapLockedPages` at `0x140007049`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000702a`
- `ntoskrnl!MmUnmapLockedPages` at `0x140007049`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006dc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006dc7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006d6d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006d6d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006b43`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006b43`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003a70c`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003a70c`
- `ntoskrnl!IoFreeIrp` at `0x140006db6`
- `ntoskrnl!IoFreeIrp` at `0x140006db6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140006f62`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140006fed`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140006f62`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140006fed`
- `srvnet!SrvNetFreeBuffer` at `0x140006c0e`
- `srvnet!SrvNetFreeBuffer` at `0x140006df3`
- `srvnet!SrvNetFreeBuffer` at `0x140006e15`
- `srvnet!SrvNetFreeBuffer` at `0x140006c0e`
- `srvnet!SrvNetFreeBuffer` at `0x140006df3`
- `srvnet!SrvNetFreeBuffer` at `0x140006e15`

## string_xrefs

- `0x140006f27`: `Srv2PostToThreadPool`
- `0x140006fb3`: `Srv2PostToThreadPool`

## pseudocode

```c
void __fastcall Srv2DereferenceWorkItem(__int64 a1)
{
  signed __int64 v2; // rdi
  __int64 v3; // rdx
  unsigned int (__fastcall *v4)(__int64); // rax
  __int64 v5; // rcx
  _QWORD *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // r14
  __int64 v9; // rdi
  KIRQL v10; // al
  __int64 v11; // r8
  _QWORD *v12; // rdx
  int v13; // edi
  signed __int64 v14; // rsi
  struct _LOOKASIDE_LIST_EX *v15; // rdi
  IRP *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 *v19; // rdi
  __int64 *v20; // rax
  KIRQL v21; // al
  __int64 *v22; // rdx
  __int64 **v23; // rcx
  bool v24; // zf
  __int64 v25; // rdi
  __int64 v26; // rdi
  __int64 v27; // rdi
  __int64 v28; // rdi
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // [rsp+20h] [rbp-88h]
  PVOID BackTrace[2]; // [rsp+60h] [rbp-48h] BYREF
  __int128 v33; // [rsp+70h] [rbp-38h]
  __int64 v34; // [rsp+80h] [rbp-28h]

  v2 = _InterlockedDecrement64((volatile signed __int64 *)a1);
  if ( v2 == -1 )
    __int2c();
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v34 = 0;
    *(_OWORD *)BackTrace = 0;
    v33 = 0;
    RtlCaptureStackBackTrace(0, 5u, BackTrace, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qPPqqqqq(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_1f56813514af312e5a39176f5ad11993_Traceguids,
        a1,
        v2 + 1,
        v2,
        BackTrace[0],
        BackTrace[1],
        v33,
        *((_QWORD *)&v33 + 1),
        v34);
    }
  }
  if ( !v2 )
  {
    if ( !KeGetCurrentIrql() )
    {
      KeEnterCriticalRegion();
      if ( (Microsoft_Windows_SMBServerEnableBits & 2) != 0 )
        Smb2OutputWorkItemResponseEtw(a1);
      v4 = *(unsigned int (__fastcall **)(__int64))(a1 + 528);
      if ( v4 && v4(a1) == 259 )
        goto LABEL_30;
      _InterlockedAdd64(
        (volatile signed __int64 *)Srv2HotGlobals + 16 * (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) + 4,
        *(unsigned int *)(a1 + 400));
      v5 = *(_QWORD *)(a1 + 416);
      *(_QWORD *)(a1 + 200) = 0;
      *(_QWORD *)(a1 + 208) = 0;
      *(_QWORD *)(a1 + 216) = 0;
      *(_QWORD *)(a1 + 232) = 0;
      *(_QWORD *)(a1 + 240) = 0;
      *(_QWORD *)(a1 + 248) = 0;
      *(_QWORD *)(a1 + 256) = -1;
      if ( v5 )
      {
        if ( v5 == a1 )
        {
          v18 = *(_QWORD *)(a1 + 456);
          if ( v18 )
          {
            SrvNetFreeBuffer(v18);
            *(_QWORD *)(a1 + 456) = 0;
            *(_DWORD *)(a1 + 464) = 0;
          }
          *(_QWORD *)(a1 + 416) = 0;
        }
        else
        {
          v19 = (__int64 *)(a1 + 432);
          v20 = *(__int64 **)(a1 + 432);
          if ( v20 && v20 != v19 )
          {
            v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 80));
            v22 = (__int64 *)*v19;
            if ( *(__int64 **)(*v19 + 8) != v19 )
              goto LABEL_63;
            v23 = *(__int64 ***)(a1 + 440);
            if ( *v23 != v19 )
              goto LABEL_63;
            *v23 = v22;
            v22[1] = (__int64)v23;
            KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 416) + 80LL), v21);
            *(_QWORD *)(a1 + 440) = a1 + 432;
            *v19 = (__int64)v19;
          }
          Srv2DereferenceWorkItem(*(_QWORD *)(a1 + 416));
          *(_QWORD *)(a1 + 416) = 0;
        }
      }
      if ( (*(_DWORD *)(a1 + 484) & 1) != 0 )
      {
        v17 = *(_QWORD *)(a1 + 312);
        if ( *(_QWORD *)(a1 + 304) != v17 )
          SrvNetFreeBuffer(v17);
      }
      if ( (*(_DWORD *)(a1 + 484) & 2) != 0 )
        SrvNetFreeBuffer(*(_QWORD *)(a1 + 304));
      v6 = *(_QWORD **)(a1 + 296);
      if ( v6 )
      {
        v16 = (IRP *)v6[5];
        if ( v16 )
          IoFreeIrp(v16);
        ExFreePoolWithTag(v6, 0);
        *(_QWORD *)(a1 + 296) = 0;
      }
      v7 = *(_QWORD *)(a1 + 848);
      if ( (*(_BYTE *)(v7 + 10) & 0x20) != 0 )
        MmUnmapLockedPages(*(PVOID *)(v7 + 24), *(PMDL *)(a1 + 848));
      **(_QWORD **)(a1 + 848) = 0;
      *(_WORD *)(a1 + 790) = 0;
      if ( (*(_BYTE *)(a1 + 330) & 0x20) != 0 )
        MmUnmapLockedPages(*(PVOID *)(a1 + 344), (PMDL)(a1 + 320));
      *(_DWORD *)(a1 + 484) &= 0xFFFFFFBC;
      *(_QWORD *)(a1 + 312) = a1 + 768;
      *(_QWORD *)(a1 + 304) = a1 + 768;
      *(_QWORD *)(a1 + 320) = 0;
      *(_DWORD *)(a1 + 12) = 220;
      *(_QWORD *)(a1 + 720) = 0;
      if ( *(_BYTE *)(a1 + 600) )
      {
        if ( (Microsoft_Windows_SMBServerEnableBits & 8) != 0 )
          McTemplateK0x_EtwWriteTransfer(v7, SMB2_EVENT_WORKITEM_END, a1 + 584, a1 + 584);
        *(_BYTE *)(a1 + 600) = 0;
      }
      v8 = *(_QWORD *)(a1 + 96);
      if ( !v8 )
        goto LABEL_27;
      v9 = a1 + 104;
      v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 184));
      v11 = *(_QWORD *)(a1 + 104);
      if ( *(_QWORD *)(*(_QWORD *)v9 + 8LL) == v9 )
      {
        v12 = *(_QWORD **)(a1 + 112);
        if ( *v12 == v9 )
        {
          *v12 = v11;
          *(_QWORD *)(v11 + 8) = v12;
          v13 = *(_DWORD *)(v8 + 208);
          *(_DWORD *)(v8 + 208) = v13 - 1;
          KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 184), v10);
          if ( v13 == 1 )
          {
            v14 = _InterlockedDecrement64((volatile signed __int64 *)v8);
            if ( v14 == -1 )
            {
              __int2c();
            }
            else if ( !v14 )
            {
              if ( KeGetCurrentIrql() )
              {
                v24 = *(_DWORD *)(v8 + 8) == 5;
                *(_QWORD *)(v8 + 48) = Srv2FreeConnection;
                *(_DWORD *)(v8 + 72) = 0;
                if ( v24 )
                {
                  LOBYTE(v31) = 1;
                  LOBYTE(v29) = 1;
                  SRV2_PERF_ENTER_EX(v8 + 584, v29, 391, "Srv2PostToThreadPool", v31);
                }
                v27 = *(_QWORD *)(*(_QWORD *)(v8 + 64) + 136LL);
                v28 = *(_QWORD *)(v27 + 8LL * KeGetCurrentNodeNumber() + 8);
                if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v28, (PSLIST_ENTRY)(v8 + 32)) && *(_WORD *)(v28 + 66) )
                  RfspThreadPoolNodeWakeIdleWorker(v28);
              }
              else
              {
                Srv2FreeConnection((char *)v8, v29, v30);
              }
            }
          }
          *(_QWORD *)(a1 + 96) = 0;
          *(_QWORD *)(a1 + 64) = 0;
LABEL_27:
          *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) = 0;
          v15 = (struct _LOOKASIDE_LIST_EX *)((char *)qword_140058148
                                            + 128 * (unsigned __int64)*(unsigned __int16 *)(a1 + 396));
          if ( !LOBYTE(v15[3].L.Depth) )
            PplpLazyInitializeLookasideList(qword_140058148, &v15[2]);
          ExFreeToLookasideListEx(v15 + 2, (PVOID)a1);
LABEL_30:
          KeLeaveCriticalRegion();
          return;
        }
      }
LABEL_63:
      __fastfail(3u);
    }
    v24 = *(_DWORD *)(a1 + 8) == 5;
    *(_QWORD *)(a1 + 48) = Srv2FreeWorkItem;
    *(_DWORD *)(a1 + 72) = 0;
    if ( v24 )
    {
      LOBYTE(v31) = 1;
      LOBYTE(v3) = 1;
      SRV2_PERF_ENTER_EX(a1 + 584, v3, 391, "Srv2PostToThreadPool", v31);
    }
    v25 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
    v26 = *(_QWORD *)(v25 + 8LL * KeGetCurrentNodeNumber() + 8);
    if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v26 + 16), (PSLIST_ENTRY)(a1 + 32)) && *(_WORD *)(v26 + 66) )
      RfspThreadPoolNodeWakeIdleWorker(v26);
  }
}

```

## disassembly

```asm
0x140006ad0  push    rbx
0x140006ad2  push    rsi
0x140006ad3  push    rdi
0x140006ad4  sub     rsp, 90h
0x140006adb  mov     rax, cs:__security_cookie
0x140006ae2  xor     rax, rsp
0x140006ae5  mov     [rsp+0A8h+var_20], rax
0x140006aed  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x140006af4  mov     rbx, rcx
0x140006af7  mov     rdi, rsi
0x140006afa  lock xadd [rcx], rdi
0x140006aff  dec     rdi
0x140006b02  cmp     rdi, rsi
0x140006b05  jnb     loc_14000701C
0x140006b0b  mov     rax, cs:WPP_GLOBAL_Control
0x140006b12  mov     ecx, [rax+2Ch]
0x140006b15  test    cl, 1
0x140006b18  jnz     loc_14003A6E6
0x140006b1e  test    rdi, rdi
0x140006b21  jnz     loc_140006D91
0x140006b27  mov     [rsp+0A8h+arg_8], rbp
0x140006b2f  call    cs:__imp_KeGetCurrentIrql
0x140006b36  nop     dword ptr [rax+rax+00h]
0x140006b3b  cmp     al, 1
0x140006b3d  jnb     loc_140006F05
0x140006b43  call    cs:__imp_KeEnterCriticalRegion
0x140006b4a  nop     dword ptr [rax+rax+00h]
0x140006b4f  test    cs:Microsoft_Windows_SMBServerEnableBits, 2
0x140006b56  jnz     loc_140006EB8
0x140006b5c  mov     rax, [rbx+210h]
0x140006b63  mov     [rsp+0A8h+arg_10], r14
0x140006b6b  mov     [rsp+0A8h+arg_18], r15
0x140006b73  test    rax, rax
0x140006b76  jz      short loc_140006B8B
0x140006b78  mov     rcx, rbx
0x140006b7b  call    _guard_dispatch_icall
0x140006b80  cmp     eax, 103h
0x140006b85  jz      loc_140006D6D
0x140006b8b  mov     eax, gs:1A4h
0x140006b93  mov     edx, [rbx+190h]
0x140006b99  mov     ecx, eax
0x140006b9b  mov     rax, cs:Srv2HotGlobals
0x140006ba2  shl     rcx, 7
0x140006ba6  lock add [rcx+rax+20h], rdx
0x140006bac  mov     rcx, [rbx+1A0h]
0x140006bb3  xor     ebp, ebp
0x140006bb5  mov     [rbx+0C8h], rbp
0x140006bbc  mov     [rbx+0D0h], rbp
0x140006bc3  mov     [rbx+0D8h], rbp
0x140006bca  mov     [rbx+0E8h], rbp
0x140006bd1  mov     [rbx+0F0h], rbp
0x140006bd8  mov     [rbx+0F8h], rbp
0x140006bdf  mov     [rbx+100h], rsi
0x140006be6  test    rcx, rcx
0x140006be9  jnz     loc_140006E04
0x140006bef  mov     eax, [rbx+1E4h]
0x140006bf5  test    al, 1
0x140006bf7  jnz     loc_140006DDF
0x140006bfd  mov     eax, [rbx+1E4h]
0x140006c03  test    al, 2
0x140006c05  jz      short loc_140006C1A
0x140006c07  mov     rcx, [rbx+130h]
0x140006c0e  call    cs:__imp_SrvNetFreeBuffer
0x140006c15  nop     dword ptr [rax+rax+00h]
0x140006c1a  mov     rdi, [rbx+128h]
0x140006c21  test    rdi, rdi
0x140006c24  jnz     loc_140006DAD
0x140006c2a  mov     rcx, [rbx+350h]
0x140006c31  test    byte ptr [rcx+0Ah], 20h
0x140006c35  jnz     loc_140007023
0x140006c3b  mov     rax, [rbx+350h]
0x140006c42  mov     [rax], rbp
0x140006c45  mov     [rbx+316h], bp
0x140006c4c  test    byte ptr [rbx+14Ah], 20h
0x140006c53  jnz     loc_14000703B
0x140006c59  and     dword ptr [rbx+1E4h], 0FFFFFFBCh
0x140006c60  lea     rax, [rbx+300h]
0x140006c67  mov     [rbx+138h], rax
0x140006c6e  mov     [rbx+130h], rax
0x140006c75  mov     [rbx+140h], rbp
0x140006c7c  mov     dword ptr [rbx+0Ch], 0DCh
0x140006c83  mov     [rbx+2D0h], rbp
0x140006c8a  cmp     [rbx+258h], bpl
0x140006c91  jnz     loc_140006EC5
0x140006c97  mov     r14, [rbx+60h]
0x140006c9b  test    r14, r14
0x140006c9e  jz      loc_140006D2B
0x140006ca4  lea     rcx, [r14+0B8h]; SpinLock
0x140006cab  lea     rdi, [rbx+68h]
0x140006caf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006cb6  nop     dword ptr [rax+rax+00h]
0x140006cbb  mov     r8, [rdi]
0x140006cbe  cmp     [r8+8], rdi
0x140006cc2  jnz     loc_140007082
0x140006cc8  mov     rdx, [rdi+8]
0x140006ccc  cmp     [rdx], rdi
0x140006ccf  jnz     loc_140007082
0x140006cd5  mov     [rdx], r8
0x140006cd8  lea     rcx, [r14+0B8h]; SpinLock
0x140006cdf  mov     [r8+8], rdx
0x140006ce3  mov     edi, [r14+0D0h]
0x140006cea  lea     edx, [rdi-1]
0x140006ced  mov     [r14+0D0h], edx
0x140006cf4  movzx   edx, al; NewIrql
0x140006cf7  call    cs:__imp_KeReleaseSpinLock
0x140006cfe  nop     dword ptr [rax+rax+00h]
0x140006d03  cmp     edi, 1
0x140006d06  jnz     short loc_140006D23
0x140006d08  lock xadd [r14], rsi
0x140006d0d  dec     rsi
0x140006d10  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140006d14  jnb     loc_14000705A
0x140006d1a  test    rsi, rsi
0x140006d1d  jz      loc_140007061
0x140006d23  mov     [rbx+60h], rbp
0x140006d27  mov     [rbx+40h], rbp
0x140006d2b  mov     rax, [rbx+78h]
0x140006d2f  mov     [rax+8], rbp
0x140006d33  movzx   edi, word ptr [rbx+18Ch]
0x140006d3a  mov     rcx, cs:qword_140058148
0x140006d41  shl     rdi, 7
0x140006d45  add     rdi, rcx
0x140006d48  movzx   eax, byte ptr [rdi+130h]
0x140006d4f  test    al, al
0x140006d51  jz      loc_140006EF4
0x140006d57  mov     rdx, rbx; Entry
0x140006d5a  lea     rcx, [rdi+0C0h]; Lookaside
0x140006d61  call    cs:__imp_ExFreeToLookasideListEx
0x140006d68  nop     dword ptr [rax+rax+00h]
0x140006d6d  call    cs:__imp_KeLeaveCriticalRegion
0x140006d74  nop     dword ptr [rax+rax+00h]
0x140006d79  mov     r14, [rsp+0A8h+arg_10]
0x140006d81  mov     r15, [rsp+0A8h+arg_18]
0x140006d89  mov     rbp, [rsp+0A8h+arg_8]
0x140006d91  mov     rcx, [rsp+0A8h+var_20]
0x140006d99  xor     rcx, rsp; StackCookie
0x140006d9c  call    __security_check_cookie
0x140006da1  add     rsp, 90h
0x140006da8  pop     rdi
0x140006da9  pop     rsi
0x140006daa  pop     rbx
0x140006dab  retn
0x140006dad  mov     rcx, [rdi+28h]; Irp
0x140006db1  test    rcx, rcx
0x140006db4  jz      short loc_140006DC2
0x140006db6  call    cs:__imp_IoFreeIrp
0x140006dbd  nop     dword ptr [rax+rax+00h]
0x140006dc2  xor     edx, edx; Tag
0x140006dc4  mov     rcx, rdi; P
0x140006dc7  call    cs:__imp_ExFreePoolWithTag
0x140006dce  nop     dword ptr [rax+rax+00h]
0x140006dd3  mov     [rbx+128h], rbp
0x140006dda  jmp     loc_140006C2A
0x140006ddf  mov     rcx, [rbx+138h]
0x140006de6  cmp     [rbx+130h], rcx
0x140006ded  jz      loc_140006BFD
0x140006df3  call    cs:__imp_SrvNetFreeBuffer
0x140006dfa  nop     dword ptr [rax+rax+00h]
0x140006dff  jmp     loc_140006BFD
0x140006e04  cmp     rcx, rbx
0x140006e07  jnz     short loc_140006E3A
0x140006e09  mov     rcx, [rbx+1C8h]
0x140006e10  test    rcx, rcx
0x140006e13  jz      short loc_140006E2E
0x140006e15  call    cs:__imp_SrvNetFreeBuffer
0x140006e1c  nop     dword ptr [rax+rax+00h]
0x140006e21  mov     [rbx+1C8h], rbp
0x140006e28  mov     [rbx+1D0h], ebp
0x140006e2e  mov     [rbx+1A0h], rbp
0x140006e35  jmp     loc_140006BEF
0x140006e3a  lea     rdi, [rbx+1B0h]
0x140006e41  mov     rax, [rdi]
0x140006e44  test    rax, rax
0x140006e47  jz      short loc_140006EA0
0x140006e49  cmp     rax, rdi
0x140006e4c  jz      short loc_140006EA0
0x140006e4e  add     rcx, 50h ; 'P'; SpinLock
0x140006e52  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006e59  nop     dword ptr [rax+rax+00h]
0x140006e5e  mov     rdx, [rdi]
0x140006e61  cmp     [rdx+8], rdi
0x140006e65  jnz     loc_140007082
0x140006e6b  mov     rcx, [rdi+8]
0x140006e6f  cmp     [rcx], rdi
0x140006e72  jnz     loc_140007082
0x140006e78  mov     [rcx], rdx
0x140006e7b  mov     [rdx+8], rcx
0x140006e7f  movzx   edx, al; NewIrql
0x140006e82  mov     rcx, [rbx+1A0h]
0x140006e89  add     rcx, 50h ; 'P'; SpinLock
0x140006e8d  call    cs:__imp_KeReleaseSpinLock
0x140006e94  nop     dword ptr [rax+rax+00h]
0x140006e99  mov     [rdi+8], rdi
0x140006e9d  mov     [rdi], rdi
0x140006ea0  mov     rcx, [rbx+1A0h]
0x140006ea7  call    Srv2DereferenceWorkItem
0x140006eac  mov     [rbx+1A0h], rbp
0x140006eb3  jmp     loc_140006BEF
0x140006eb8  mov     rcx, rbx
0x140006ebb  call    Smb2OutputWorkItemResponseEtw
0x140006ec0  jmp     loc_140006B5C
0x140006ec5  test    cs:Microsoft_Windows_SMBServerEnableBits, 8
0x140006ecc  jz      short loc_140006EE8
0x140006ece  lea     r9, [rbx+248h]
0x140006ed5  lea     r8, [rbx+248h]
0x140006edc  lea     rdx, SMB2_EVENT_WORKITEM_END
0x140006ee3  call    McTemplateK0x_EtwWriteTransfer
0x140006ee8  mov     [rbx+258h], bpl
0x140006eef  jmp     loc_140006C97
0x140006ef4  lea     rdx, [rdi+0C0h]
0x140006efb  call    PplpLazyInitializeLookasideList
0x140006f00  jmp     loc_140006D57
0x140006f05  xor     ebp, ebp
0x140006f07  lea     rax, Srv2FreeWorkItem
0x140006f0e  cmp     dword ptr [rbx+8], 5
0x140006f12  mov     [rbx+30h], rax
0x140006f16  mov     [rbx+48h], ebp
0x140006f19  jnz     short loc_140006F3B
0x140006f1b  lea     rcx, [rbx+248h]
0x140006f22  mov     byte ptr [rsp+0A8h+var_88], 1
0x140006f27  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140006f2e  mov     r8d, 187h
0x140006f34  mov     dl, 1
0x140006f36  call    SRV2_PERF_ENTER_EX
0x140006f3b  mov     rax, [rbx+40h]
0x140006f3f  mov     rdi, [rax+88h]
0x140006f46  call    cs:__imp_KeGetCurrentNodeNumber
0x140006f4d  nop     dword ptr [rax+rax+00h]
0x140006f52  movzx   eax, ax
0x140006f55  lea     rdx, [rbx+20h]; ListEntry
0x140006f59  mov     rdi, [rdi+rax*8+8]
0x140006f5e  lea     rcx, [rdi+10h]; ListHead
0x140006f62  call    cs:__imp_ExpInterlockedPushEntrySList
0x140006f69  nop     dword ptr [rax+rax+00h]
0x140006f6e  test    rax, rax
0x140006f71  jnz     loc_140006D89
0x140006f77  movzx   eax, word ptr [rdi+42h]
0x140006f7b  cmp     bp, ax
0x140006f7e  jz      loc_140006D89
0x140006f84  mov     rcx, rdi
0x140006f87  call    RfspThreadPoolNodeWakeIdleWorker
0x140006f8c  jmp     loc_140006D89
0x140006f91  cmp     dword ptr [r14+8], 5
0x140006f96  lea     rax, Srv2FreeConnection
0x140006f9d  mov     [r14+30h], rax
0x140006fa1  mov     [r14+48h], ebp
0x140006fa5  jnz     short loc_140006FC7
0x140006fa7  lea     rcx, [r14+248h]
0x140006fae  mov     byte ptr [rsp+0A8h+var_88], 1
0x140006fb3  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140006fba  mov     r8d, 187h
0x140006fc0  mov     dl, 1
0x140006fc2  call    SRV2_PERF_ENTER_EX
0x140006fc7  mov     rax, [r14+40h]
0x140006fcb  mov     rdi, [rax+88h]
0x140006fd2  call    cs:__imp_KeGetCurrentNodeNumber
0x140006fd9  nop     dword ptr [rax+rax+00h]
0x140006fde  movzx   eax, ax
0x140006fe1  lea     rdx, [r14+20h]; ListEntry
0x140006fe5  mov     rdi, [rdi+rax*8+8]
0x140006fea  mov     rcx, rdi; ListHead
0x140006fed  call    cs:__imp_ExpInterlockedPushEntrySList
0x140006ff4  nop     dword ptr [rax+rax+00h]
0x140006ff9  test    rax, rax
0x140006ffc  jnz     loc_140006D23
0x140007002  movzx   eax, word ptr [rdi+42h]
0x140007006  cmp     bp, ax
0x140007009  jz      loc_140006D23
0x14000700f  mov     rcx, rdi
0x140007012  call    RfspThreadPoolNodeWakeIdleWorker
0x140007017  jmp     loc_140006D23
0x14000701c  int     2Ch; Windows NT - assertion failure
0x14000701e  jmp     loc_140006B0B
0x140007023  mov     rdx, rcx; MemoryDescriptorList
0x140007026  mov     rcx, [rcx+18h]; BaseAddress
0x14000702a  call    cs:__imp_MmUnmapLockedPages
0x140007031  nop     dword ptr [rax+rax+00h]
0x140007036  jmp     loc_140006C3B
0x14000703b  mov     rcx, [rbx+158h]; BaseAddress
0x140007042  lea     rdx, [rbx+140h]; MemoryDescriptorList
0x140007049  call    cs:__imp_MmUnmapLockedPages
0x140007050  nop     dword ptr [rax+rax+00h]
0x140007055  jmp     loc_140006C59
0x14000705a  int     2Ch; Windows NT - assertion failure
0x14000705c  jmp     loc_140006D23
0x140007061  call    cs:__imp_KeGetCurrentIrql
0x140007068  nop     dword ptr [rax+rax+00h]
0x14000706d  test    al, al
0x14000706f  jnz     loc_140006F91
0x140007075  mov     rcx, r14; P
0x140007078  call    Srv2FreeConnection
0x14000707d  jmp     loc_140006D23
0x140007082  mov     ecx, 3
0x140007087  int     29h; Win8: RtlFailFast(ecx)
0x14003a6e6  xorps   xmm0, xmm0
0x14003a6e9  lea     r8, [rsp+0A8h+BackTrace]; BackTrace
0x14003a6ee  xor     eax, eax
0x14003a6f0  xor     r9d, r9d; BackTraceHash
0x14003a6f3  mov     edx, 5; FramesToCapture
0x14003a6f8  mov     [rsp+0A8h+var_28], rax
  ... truncated ...
```
