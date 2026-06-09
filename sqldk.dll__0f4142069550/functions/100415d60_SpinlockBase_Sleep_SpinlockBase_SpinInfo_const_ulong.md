# SpinlockBase::Sleep(SpinlockBase::SpinInfo const &,ulong)

- ea: `0x100415d60`
- end: `0x100415f36`
- name: `?Sleep@SpinlockBase@@IEAAXAEBVSpinInfo@1@K@Z`
- size: `470`
- prototype: `void(SpinlockBase *__hidden this, const struct SpinlockBase::SpinInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x100415c70`

## callees

- `0x100401810`
- `0x100415b10`
- `0x100415d60`
- `0x100415f40`
- `0x100424ef0`
- `0x1005848b0`

## import_xrefs

- `KERNEL32!Sleep` at `0x10043e60a`
- `KERNEL32!Sleep` at `0x1004ac5ab`
- `KERNEL32!Sleep` at `0x10043e60a`
- `KERNEL32!Sleep` at `0x1004ac5ab`
- `KERNEL32!SwitchToThread` at `0x100415ef1`
- `KERNEL32!SwitchToThread` at `0x100415ef1`
- `KERNEL32!QueryPerformanceCounter` at `0x10043e5f7`
- `KERNEL32!QueryPerformanceCounter` at `0x10043e624`
- `KERNEL32!QueryPerformanceCounter` at `0x10043e5f7`
- `KERNEL32!QueryPerformanceCounter` at `0x10043e624`

## pseudocode

```c
void __fastcall SpinlockBase::Sleep(SpinlockBase *this, const struct SpinlockBase::SpinInfo *a2, DWORD a3)
{
  SpinlockBase *v4; // rbx
  __int64 Description; // rax
  __int64 v7; // r14
  __int64 v8; // rdx
  int v9; // eax
  int v10; // ecx
  __int64 v11; // rax
  __int64 v12; // r13
  __int64 v13; // rbx
  __int64 v14; // rbx
  LARGE_INTEGER v15; // rbx
  LARGE_INTEGER v16; // rax
  LONGLONG v17; // rax
  __int64 v18; // r8
  _QWORD *v19; // r9
  __int64 v20; // r15
  __int64 v21; // r15
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // ebx
  __int64 v26; // rax
  bool v27; // zf
  __int128 v28; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v29; // [rsp+38h] [rbp-D0h]
  __int64 v30; // [rsp+40h] [rbp-C8h]
  __int64 v31; // [rsp+48h] [rbp-C0h]
  SpinlockBase *v32; // [rsp+50h] [rbp-B8h]
  __int128 v33; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-A0h]
  __int128 v35; // [rsp+70h] [rbp-98h]
  __int64 v36; // [rsp+80h] [rbp-88h]
  __int64 v37; // [rsp+88h] [rbp-80h]
  __int128 v38; // [rsp+90h] [rbp-78h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-68h]
  __int64 v40; // [rsp+A8h] [rbp-60h]
  SpinlockBase *v41; // [rsp+B0h] [rbp-58h]
  __int64 v42; // [rsp+B8h] [rbp-50h]
  DWORD v43; // [rsp+C0h] [rbp-48h]
  int v44; // [rsp+C4h] [rbp-44h]
  char v45[8]; // [rsp+C8h] [rbp-40h] BYREF
  int v46; // [rsp+D0h] [rbp-38h]
  int v47; // [rsp+D8h] [rbp-30h]
  _QWORD **v48; // [rsp+E0h] [rbp-28h]
  char *v49; // [rsp+E8h] [rbp-20h]
  __int64 v50; // [rsp+F0h] [rbp-18h]
  _QWORD *v51; // [rsp+F8h] [rbp-10h] BYREF
  int v52; // [rsp+100h] [rbp-8h]
  int v53; // [rsp+104h] [rbp-4h]
  __int64 v54; // [rsp+108h] [rbp+0h]
  int v55; // [rsp+110h] [rbp+8h]
  int v56; // [rsp+114h] [rbp+Ch]
  char v57; // [rsp+118h] [rbp+10h] BYREF
  int v58; // [rsp+1A0h] [rbp+98h]
  __int64 v59; // [rsp+1A8h] [rbp+A0h]
  __int64 v60; // [rsp+318h] [rbp+210h]
  __int64 v61; // [rsp+320h] [rbp+218h]
  _QWORD v62[3]; // [rsp+328h] [rbp+220h] BYREF
  DWORD v63; // [rsp+340h] [rbp+238h]
  __int64 v64; // [rsp+344h] [rbp+23Ch]
  __int64 v65; // [rsp+34Ch] [rbp+244h]
  _BYTE v66[216]; // [rsp+368h] [rbp+260h] BYREF
  int v67; // [rsp+440h] [rbp+338h]
  __int64 v68; // [rsp+448h] [rbp+340h]
  LARGE_INTEGER PerformanceCount; // [rsp+4B0h] [rbp+3A8h] BYREF
  int v71; // [rsp+4B8h] [rbp+3B0h]
  LARGE_INTEGER v72; // [rsp+4C0h] [rbp+3B8h] BYREF

  v4 = this;
  Description = SpinlockStat::GetDescription(*(unsigned __int16 *)a2, *((unsigned int *)a2 + 1));
  v7 = *((_QWORD *)a2 + 1);
  v8 = Description;
  if ( !v7 )
  {
    v12 = 0;
LABEL_42:
    v71 = 0;
    goto LABEL_14;
  }
  v9 = *(_DWORD *)(v7 + 616);
  if ( (v9 & 0x40) == 0 )
  {
    v10 = *(_DWORD *)(v7 + 800);
    if ( (v10 & 0x202000) == 0
      && (v9 & 0x400) == 0
      && (v10 & 0x100000) == 0
      && *(_DWORD *)(v7 + 728) == 1
      && (g_XeSosPkg_enabledBitmap & 0x10000000) != 0 )
    {
      v46 = 0x20000;
      v48 = &v51;
      v49 = &v57;
      v51 = v62;
      v64 = *(unsigned __int16 *)a2;
      v65 = *((int *)a2 + 1);
      v11 = -1;
      v47 = 0;
      v60 = 0;
      v50 = 0;
      v61 = 0;
      v52 = 52;
      v53 = 1;
      v62[0] = v4;
      do
        ++v11;
      while ( *(_BYTE *)(v8 + v11) );
      v55 = v11;
      v62[2] = *((unsigned int *)a2 + 8);
      v54 = v8;
      v56 = 6;
      v62[1] = v7;
      v63 = a3;
      XeSosPkg::spinlock_backoff::Publish((XeSosPkg::spinlock_backoff *)v45);
    }
  }
  v12 = *(_QWORD *)(v7 + 608);
  if ( !v12 )
    goto LABEL_42;
  v13 = *(_QWORD *)(v12 + 3632);
  v71 = 1;
  if ( v13 )
  {
    v30 = 0;
    v29 = 0;
    LODWORD(v31) = *(unsigned __int16 *)a2;
    v32 = this;
    v28 = 0;
    v67 = 0;
    v68 = 0;
    if ( *(_QWORD *)(v13 + 64) )
      StackFrames<24>::CaptureCurrent(v66, 1);
    SOS_RingBuffer::StoreRecordInternalWithoutEvent(v13, &v28, v66);
  }
  v4 = this;
LABEL_14:
  if ( (byte_1007149AF & 8) != 0 )
  {
    v20 = *((_QWORD *)a2 + 2);
    if ( v20 )
    {
      v21 = *(_QWORD *)(v20 + 288);
      if ( v21 )
      {
        if ( a3 == 1 )
        {
          v36 = 0;
          v34 = 0;
          v37 = 0;
          v22 = (unsigned int)(*(_DWORD *)(v21 + 48) & *(_DWORD *)(v21 + 44));
          v33 = 0;
          v35 = 0;
          ((void (__fastcall *)(__int64, __int64, __int128 *, _QWORD, _QWORD, _QWORD, __int64, __int64, _DWORD, SpinlockBase *))SOS_RingBuffer::RetrieveRecord)(
            v21,
            v22,
            &v33,
            0,
            v28,
            *((_QWORD *)&v28 + 1),
            v29,
            v30,
            v31,
            v32);
          if ( *((SpinlockBase **)&v35 + 1) == v4 )
          {
LABEL_20:
            if ( !*((_QWORD *)a2 + 3) )
            {
              Sleep(a3);
              goto LABEL_17;
            }
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&PerformanceCount);
              v15 = PerformanceCount;
            }
            else
            {
              v15.QuadPart = MEMORY[0x7FFE0008];
            }
            Sleep(a3);
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v72);
              v16 = v72;
            }
            else
            {
              v16.QuadPart = MEMORY[0x7FFE0008];
            }
            if ( v16.QuadPart < (unsigned __int64)v15.QuadPart )
              v17 = 0;
            else
              v17 = v16.QuadPart - v15.QuadPart;
            v18 = 0;
            v19 = (_QWORD *)*((_QWORD *)a2 + 3);
            switch ( *((_WORD *)a2 + 2) )
            {
              case 1:
                v18 = v19[1];
                break;
              case 2:
                *(_QWORD *)(56LL * *(unsigned __int16 *)a2 + v19[2] + 16) += v17;
                goto LABEL_17;
              case 3:
                *(_QWORD *)(56LL * *(unsigned __int16 *)a2 + v19[3] + 16) += v17;
                goto LABEL_17;
              case 4:
                *(_QWORD *)(56LL * *(unsigned __int16 *)a2 + v19[4] + 16) += v17;
                goto LABEL_17;
            }
            *(_QWORD *)(56LL * *(unsigned __int16 *)a2 + v18 + 16) += v17;
            goto LABEL_17;
          }
        }
        v23 = *((unsigned int *)a2 + 1);
        v24 = *(unsigned __int16 *)a2;
        v25 = *((_DWORD *)a2 + 8);
        v39 = 0;
        v41 = this;
        v38 = 0;
        v40 = v7;
        v26 = SpinlockStat::GetDescription(v24, v23);
        v27 = *(_QWORD *)(v21 + 64) == 0;
        v42 = v26;
        v43 = a3;
        v44 = v25;
        v67 = 0;
        v68 = 0;
        if ( !v27 )
          StackFrames<24>::CaptureCurrent(v66, 1);
        SOS_RingBuffer::StoreRecordInternalWithoutEvent(v21, &v38, v66);
      }
    }
  }
  if ( a3 )
    goto LABEL_20;
  SwitchToThread();
LABEL_17:
  if ( v71 )
  {
    v14 = *(_QWORD *)(v12 + 3632);
    if ( v14 )
    {
      v30 = 1;
      v27 = *(_QWORD *)(v14 + 64) == 0;
      v29 = 0;
      LODWORD(v31) = *(unsigned __int16 *)a2;
      v32 = this;
      v28 = 0;
      v58 = 0;
      v59 = 0;
      if ( !v27 )
        StackFrames<24>::CaptureCurrent(v45, 1);
      SOS_RingBuffer::StoreRecordInternalWithoutEvent(v14, &v28, v45);
    }
  }
}

```

## disassembly

```asm
0x100415d60  mov     rax, rsp
0x100415d63  mov     [rax+8], rcx
0x100415d67  push    rbp
0x100415d68  push    rbx
0x100415d69  push    rsi
0x100415d6a  push    rdi
0x100415d6b  push    r13
0x100415d6d  lea     rbp, [rax-398h]
0x100415d74  sub     rsp, 470h
0x100415d7b  mov     rsi, rdx
0x100415d7e  mov     [rax-30h], r12
0x100415d82  mov     edx, [rdx+4]
0x100415d85  mov     rbx, rcx
0x100415d88  mov     [rax-38h], r14
0x100415d8c  mov     r12d, r8d
0x100415d8f  movzx   ecx, word ptr [rsi]
0x100415d92  call    ?GetDescription@SpinlockStat@@SAQEBDGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetDescription(ushort,SPINLOCK_CATEGORY)
0x100415d97  mov     r14, [rsi+8]
0x100415d9b  xor     edi, edi
0x100415d9d  mov     rdx, rax
0x100415da0  mov     r8d, 1
0x100415da6  test    r14, r14
0x100415da9  jz      loc_1004AC52F
0x100415daf  mov     eax, [r14+268h]
0x100415db6  test    al, 40h
0x100415db8  jnz     loc_100415EA5
0x100415dbe  mov     ecx, [r14+320h]
0x100415dc5  test    ecx, 202000h
0x100415dcb  jnz     loc_100415EA5
0x100415dd1  bt      eax, 0Ah
0x100415dd5  jb      loc_100415EA5
0x100415ddb  bt      ecx, 14h
0x100415ddf  jb      loc_100415EA5
0x100415de5  cmp     [r14+2D8h], r8d
0x100415dec  jnz     loc_100415EA5
0x100415df2  test    cs:?g_XeSosPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$0FD@@@@@A, 10000000h; XBitmap<StaticStorage<83>> g_XeSosPkg_enabledBitmap
0x100415dfc  jz      loc_100415EA5
0x100415e02  lea     rax, [rbp+390h+var_3A0]
0x100415e06  mov     [rbp+390h+var_3C8], 20000h
0x100415e0d  mov     [rbp+390h+var_3B8], rax
0x100415e11  lea     rax, [rbp+390h+var_380]
0x100415e15  mov     [rbp+390h+var_3B0], rax
0x100415e19  lea     rax, [rbp+390h+var_170]
0x100415e20  mov     [rbp+390h+var_3A0], rax
0x100415e24  movzx   eax, word ptr [rsi]
0x100415e27  mov     [rbp+390h+var_154], rax
0x100415e2e  movsxd  rax, dword ptr [rsi+4]
0x100415e32  mov     [rbp+390h+var_14C], rax
0x100415e39  mov     rax, 0FFFFFFFFFFFFFFFFh
0x100415e40  mov     [rbp+390h+var_3C0], edi
0x100415e43  mov     [rbp+390h+var_180], rdi
0x100415e4a  mov     [rbp+390h+var_3A8], rdi
0x100415e4e  mov     [rbp+390h+var_178], rdi
0x100415e55  mov     [rbp+390h+var_398], 34h ; '4'
0x100415e5c  mov     [rbp+390h+var_394], r8d
0x100415e60  mov     [rbp+390h+var_170], rbx
0x100415e67  inc     rax
0x100415e6a  cmp     [rdx+rax], dil
0x100415e6e  jnz     short loc_100415E67
0x100415e70  mov     [rbp+390h+var_388], eax
0x100415e73  lea     rcx, [rbp+390h+var_3D0]; this
0x100415e77  mov     eax, [rsi+20h]
0x100415e7a  mov     [rbp+390h+var_160], rax
0x100415e81  mov     [rbp+390h+var_390], rdx
0x100415e85  mov     [rbp+390h+var_384], 6
0x100415e8c  mov     [rbp+390h+var_168], r14
0x100415e93  mov     [rbp+390h+var_158], r12d
0x100415e9a  call    ?Publish@spinlock_backoff@XeSosPkg@@QEAAXXZ; XeSosPkg::spinlock_backoff::Publish(void)
0x100415e9f  mov     r8d, 1
0x100415ea5  mov     r13, [r14+260h]
0x100415eac  test    r13, r13
0x100415eaf  jz      loc_1004AC532
0x100415eb5  mov     rbx, [r13+0E30h]
0x100415ebc  mov     [rbp+390h+arg_10], r8d
0x100415ec3  test    rbx, rbx
0x100415ec6  jnz     loc_1004AC3EE
0x100415ecc  mov     rbx, [rbp+390h+arg_0]
0x100415ed3  test    cs:byte_1007149AF, 8
0x100415eda  mov     [rsp+490h+var_38], r15
0x100415ee2  jnz     loc_1004AC452
0x100415ee8  test    r12d, r12d
0x100415eeb  jnz     loc_10043E5D8
0x100415ef1  call    cs:__imp_SwitchToThread
0x100415ef7  cmp     [rbp+390h+arg_10], 0
0x100415efe  mov     r15, [rsp+490h+var_38]
0x100415f06  mov     r14, [rsp+490h+var_30]
0x100415f0e  mov     r12, [rsp+468h]
0x100415f16  jz      short loc_100415F28
0x100415f18  mov     rbx, [r13+0E30h]
0x100415f1f  test    rbx, rbx
0x100415f22  jnz     loc_1004AC5B7
0x100415f28  add     rsp, 470h
0x100415f2f  pop     r13
0x100415f31  pop     rdi
0x100415f32  pop     rsi
0x100415f33  pop     rbx
0x100415f34  pop     rbp
0x100415f35  retn
0x10043e5d8  cmp     qword ptr [rsi+18h], 0
0x10043e5dd  jz      loc_1004AC5A8
0x10043e5e3  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x10043e5ea  jz      loc_1004AC53E
0x10043e5f0  lea     rcx, [rbp+390h+PerformanceCount]; lpPerformanceCount
0x10043e5f7  call    cs:__imp_QueryPerformanceCounter
0x10043e5fd  mov     rbx, qword ptr [rbp+390h+PerformanceCount]
0x10043e604  jmp     short loc_10043E607
0x10043e607  mov     ecx, r12d; dwMilliseconds
0x10043e60a  call    cs:__imp_Sleep
0x10043e610  cmp     cs:?sm_invariantTscAvailable@Base_PublicGlobals@@2HA, 0; int Base_PublicGlobals::sm_invariantTscAvailable
0x10043e617  jz      loc_1004AC54C
0x10043e61d  lea     rcx, [rbp+390h+arg_18]; lpPerformanceCount
0x10043e624  call    cs:__imp_QueryPerformanceCounter
0x10043e62a  mov     rax, qword ptr [rbp+390h+arg_18]
0x10043e631  jmp     short loc_10043E634
0x10043e634  cmp     rax, rbx
0x10043e637  jb      loc_1004AC55A
0x10043e63d  sub     rax, rbx
0x10043e640  jmp     short loc_10043E643
0x10043e643  movzx   edx, word ptr [rsi+4]
0x10043e647  mov     r8, rdi
0x10043e64a  mov     r9, [rsi+18h]
0x10043e64e  sub     edx, 1
0x10043e651  jz      loc_1004AC593
0x10043e657  sub     edx, 1
0x10043e65a  jz      loc_1004AC57E
0x10043e660  sub     edx, 1
0x10043e663  jnz     loc_1004AC563
0x10043e669  movzx   ecx, word ptr [rsi]
0x10043e66c  mov     r8, [r9+18h]
0x10043e670  imul    rdx, rcx, 38h ; '8'
0x10043e674  add     [rdx+r8+10h], rax
0x10043e679  jmp     loc_100415EF7
0x1004ac3ee  xor     eax, eax
0x1004ac3f0  mov     [rsp+490h+var_458], rdi
0x1004ac3f5  xorps   xmm0, xmm0
0x1004ac3f8  mov     [rsp+490h+var_460], rax
0x1004ac3fd  movzx   eax, word ptr [rsi]
0x1004ac400  mov     dword ptr [rsp+490h+var_450], eax
0x1004ac404  mov     rax, [rbp+390h+arg_0]
0x1004ac40b  mov     qword ptr [rsp+490h+var_448], rax
0x1004ac410  movups  [rsp+490h+var_478+8], xmm0
0x1004ac415  mov     [rbp+390h+var_58], edi
0x1004ac41b  mov     [rbp+390h+var_50], rdi
0x1004ac422  cmp     [rbx+40h], rdi
0x1004ac426  jz      short loc_1004AC437
0x1004ac428  mov     edx, r8d
0x1004ac42b  lea     rcx, [rbp+390h+var_130]
0x1004ac432  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x1004ac437  lea     r8, [rbp+390h+var_130]
0x1004ac43e  mov     rcx, rbx
0x1004ac441  lea     rdx, [rsp+490h+var_478+8]
0x1004ac446  call    ?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x1004ac44b  nop
0x1004ac44c  jmp     loc_100415ECC
0x1004ac452  mov     r15, [rsi+10h]
0x1004ac456  test    r15, r15
0x1004ac459  jz      loc_100415EE8
0x1004ac45f  mov     r15, [r15+120h]
0x1004ac466  test    r15, r15
0x1004ac469  jz      loc_100415EE8
0x1004ac46f  cmp     r12d, 1
0x1004ac473  jnz     short loc_1004AC4BB
0x1004ac475  xor     eax, eax
0x1004ac477  mov     [rsp+490h+var_418], rdi
0x1004ac47c  mov     qword ptr [rsp+490h+var_430], rax
0x1004ac481  lea     r8, [rsp+490h+var_448+8]
0x1004ac486  mov     [rbp+390h+var_410], rax
0x1004ac48a  xorps   xmm0, xmm0
0x1004ac48d  mov     eax, [r15+30h]
0x1004ac491  xorps   xmm1, xmm1
0x1004ac494  mov     edx, [r15+2Ch]
0x1004ac498  xor     r9d, r9d
0x1004ac49b  and     edx, eax
0x1004ac49d  mov     rcx, r15
0x1004ac4a0  movups  [rsp+490h+var_448+8], xmm0
0x1004ac4a5  movdqu  [rsp+490h+var_430+8], xmm1
0x1004ac4ab  call    ?RetrieveRecord@SOS_RingBuffer@@QEAAXKPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::RetrieveRecord(ulong,SOS_RingBufferRecord *,StackFrames<24> *)
0x1004ac4b0  cmp     [rsp+490h+var_420], rbx
0x1004ac4b5  jz      loc_10043E5D8
0x1004ac4bb  mov     edx, [rsi+4]
0x1004ac4be  xor     eax, eax
0x1004ac4c0  movzx   ecx, word ptr [rsi]
0x1004ac4c3  xorps   xmm0, xmm0
0x1004ac4c6  mov     ebx, [rsi+20h]
0x1004ac4c9  mov     [rbp+390h+var_3F8], rax
0x1004ac4cd  mov     rax, [rbp+390h+arg_0]
0x1004ac4d4  mov     [rbp+390h+var_3E8], rax
0x1004ac4d8  movups  [rbp+390h+var_408], xmm0
0x1004ac4dc  mov     [rbp+390h+var_3F0], r14
0x1004ac4e0  call    ?GetDescription@SpinlockStat@@SAQEBDGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetDescription(ushort,SPINLOCK_CATEGORY)
0x1004ac4e5  cmp     qword ptr [r15+40h], 0
0x1004ac4ea  mov     [rbp+390h+var_3E0], rax
0x1004ac4ee  mov     [rbp+390h+var_3D8], r12d
0x1004ac4f2  mov     [rbp+390h+var_3D4], ebx
0x1004ac4f5  mov     [rbp+390h+var_58], edi
0x1004ac4fb  mov     [rbp+390h+var_50], rdi
0x1004ac502  jz      short loc_1004AC515
0x1004ac504  mov     edx, 1
0x1004ac509  lea     rcx, [rbp+390h+var_130]
0x1004ac510  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x1004ac515  lea     r8, [rbp+390h+var_130]
0x1004ac51c  mov     rcx, r15
0x1004ac51f  lea     rdx, [rbp+390h+var_408]
0x1004ac523  call    ?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x1004ac528  nop
0x1004ac529  jmp     loc_100415EE8
0x1004ac52f  mov     r13, rdi
0x1004ac532  mov     [rbp+390h+arg_10], edi
0x1004ac538  jmp     loc_100415ED3
0x1004ac53e  mov     rbx, ds:7FFE0008h
0x1004ac546  jmp     loc_10043E607
0x1004ac54c  mov     rax, ds:7FFE0008h
0x1004ac554  jmp     loc_10043E634
0x1004ac55a  mov     rax, rdi
0x1004ac55d  jmp     loc_10043E643
0x1004ac563  cmp     edx, 1
0x1004ac566  jnz     short loc_1004AC597
0x1004ac568  movzx   ecx, word ptr [rsi]
0x1004ac56b  mov     r8, [r9+20h]
0x1004ac56f  imul    rdx, rcx, 38h ; '8'
0x1004ac573  add     [rdx+r8+10h], rax
0x1004ac578  jmp     loc_100415EF7
0x1004ac57e  movzx   ecx, word ptr [rsi]
0x1004ac581  mov     r8, [r9+10h]
0x1004ac585  imul    rdx, rcx, 38h ; '8'
0x1004ac589  add     [rdx+r8+10h], rax
0x1004ac58e  jmp     loc_100415EF7
0x1004ac593  mov     r8, [r9+8]
0x1004ac597  movzx   ecx, word ptr [rsi]
0x1004ac59a  imul    rdx, rcx, 38h ; '8'
0x1004ac59e  add     [rdx+r8+10h], rax
0x1004ac5a3  jmp     loc_100415EF7
0x1004ac5a8  mov     ecx, r12d; dwMilliseconds
0x1004ac5ab  call    cs:__imp_Sleep
0x1004ac5b1  jmp     loc_100415EF7
0x1004ac5b7  xor     eax, eax
0x1004ac5b9  mov     [rsp+490h+var_458], 1
0x1004ac5c2  cmp     qword ptr [rbx+40h], 0
0x1004ac5c7  xorps   xmm0, xmm0
0x1004ac5ca  mov     [rsp+490h+var_460], rax
0x1004ac5cf  movzx   eax, word ptr [rsi]
0x1004ac5d2  mov     dword ptr [rsp+490h+var_450], eax
0x1004ac5d6  mov     rax, [rbp+390h+arg_0]
0x1004ac5dd  mov     qword ptr [rsp+490h+var_448], rax
0x1004ac5e2  movups  [rsp+490h+var_478+8], xmm0
0x1004ac5e7  mov     [rbp+390h+var_2F8], edi
0x1004ac5ed  mov     [rbp+390h+var_2F0], rdi
0x1004ac5f4  jz      short loc_1004AC604
0x1004ac5f6  mov     edx, 1
0x1004ac5fb  lea     rcx, [rbp+390h+var_3D0]
0x1004ac5ff  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x1004ac604  lea     r8, [rbp+390h+var_3D0]
0x1004ac608  mov     rcx, rbx
0x1004ac60b  lea     rdx, [rsp+490h+var_478+8]
0x1004ac610  call    ?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x1004ac615  nop
0x1004ac616  jmp     loc_100415F28
```
