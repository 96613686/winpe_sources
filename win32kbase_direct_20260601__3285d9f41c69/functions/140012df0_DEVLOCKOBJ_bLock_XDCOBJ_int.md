# DEVLOCKOBJ::bLock(XDCOBJ &,int)

- ea: `0x140012df0`
- end: `0x1400134b7`
- name: `?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z`
- size: `1735`
- prototype: `__int64 __fastcall(DEVLOCKOBJ *__hidden this, struct XDCOBJ *, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140012a60`

## callees

- `0x14000f870`
- `0x140012df0`
- `0x140018fb4`
- `0x14001cdd0`
- `0x14001ceac`
- `0x14001d160`
- `0x140025668`
- `0x140025990`
- `0x140025b90`
- `0x1400263d4`
- `0x1400264ac`
- `0x140028590`
- `0x140034110`
- `0x140047bc0`
- `0x140064190`
- `0x140064204`
- `0x1400ed2c0`
- `0x140110520`
- `0x140190760`
- `0x1401e2090`
- `0x1401e5814`
- `0x140238240`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140012f4b`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140012f4b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140012f11`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140013012`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140013049`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001307e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400130f4`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001312b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140012f11`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140013012`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140013049`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001307e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400130f4`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001312b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140012e40`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140012e65`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140012e40`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140012e65`

## pseudocode

```c
__int64 __fastcall DEVLOCKOBJ::bLock(DEVLOCKOBJ *this, struct XDCOBJ *a2, int a3)
{
  int (*v6)(void); // rax
  __int64 (__fastcall *v7)(struct XDCOBJ *, char *, char *, char *); // rax
  int v8; // eax
  __int64 result; // rax
  __int64 v10; // rdi
  int v11; // r12d
  _QWORD *v12; // rax
  __int64 v13; // rdx
  bool v14; // zf
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // edx
  _QWORD *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  _QWORD *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  _QWORD *CurrentThreadWin32Thread; // rax
  __int64 v29; // rdx
  __int64 v30; // rax
  _QWORD *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  int v37; // edx
  struct _GRETHREAD *CurrentThread; // rax
  struct _GRETHREAD *v39; // rbp
  HSEMAPHORE v40; // r15
  struct _GRETHREAD *v41; // rax
  int v42; // ecx
  __int64 v43; // r8
  struct _GRETHREAD *v44; // r14
  int v45; // edx
  unsigned __int64 i; // rcx
  int v47; // eax
  struct _GRETHREAD *v48; // rax
  int v49; // ecx
  bool v50; // cc
  __int64 v51; // rcx
  SURFACE *v52; // rcx
  __int64 v53; // [rsp+70h] [rbp+8h] BYREF

  *((_DWORD *)this + 6) = 1;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 19) = **(_QWORD **)a2;
  if ( a3 )
  {
    DEVLOCKOBJ::bPrepareTrgDco(this, 0);
    if ( a3 == 1 )
      *((_DWORD *)this + 6) |= 0x20000u;
  }
  else
  {
    v6 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24) + 2032LL);
    if ( !v6
      || v6() < 0
      || ((v7 = *(__int64 (__fastcall **)(struct XDCOBJ *, char *, char *, char *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable()
                                                                                              + 24)
                                                                                  + 2040LL)) == 0
        ? (v8 = 0)
        : (v8 = v7(a2, (char *)this + 144, (char *)this + 136, (char *)this + 28)),
          v8 != 1) )
    {
      *((_DWORD *)this + 6) &= ~1u;
      return 0;
    }
    DEVLOCKOBJ::bPrepareTrgDco(this, 0);
  }
  v10 = *((_QWORD *)a2 + 2);
  v11 = 0;
  if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x200) == 0 )
  {
    CurrentThreadWin32Thread = (_QWORD *)PsGetCurrentThreadWin32Thread();
    if ( !CurrentThreadWin32Thread )
      goto LABEL_59;
    v29 = 0;
    v14 = *CurrentThreadWin32Thread == 0;
    v30 = *CurrentThreadWin32Thread + 8LL;
    if ( !v14 )
      v29 = v30;
    if ( !v29 || !*(_DWORD *)(v29 + 340) )
    {
LABEL_59:
      *((_DWORD *)this + 6) |= 0x80000u;
      v31 = (_QWORD *)PsGetCurrentThreadWin32Thread();
      if ( v31 )
      {
        v32 = 0;
        v14 = *v31 == 0;
        v33 = *v31 + 8LL;
        if ( !v14 )
          v32 = v33;
        if ( v32 )
          ++*(_DWORD *)(v32 + 340);
      }
    }
    goto LABEL_64;
  }
  *((_QWORD *)this + 1) = *(_QWORD *)v10 + 624LL;
  GreAcquireSemaphoreShared<1,>(v10);
  *((_DWORD *)this + 6) |= 8u;
  v12 = (_QWORD *)PsGetCurrentThreadWin32Thread();
  if ( !v12 )
    goto LABEL_141;
  v13 = 0;
  v14 = *v12 == 0;
  v15 = *v12 + 8LL;
  if ( !v14 )
    v13 = v15;
  if ( !v13 || !*(_DWORD *)(v13 + 340) )
  {
LABEL_141:
    if ( !ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)v10 + 1144LL)) )
    {
      GreAcquireSemaphoreShared<2,>(v10);
      v11 = 1;
    }
  }
  v16 = *(_QWORD *)a2;
  v53 = *(_QWORD *)(*(_QWORD *)a2 + 48LL);
  if ( (**(_DWORD **)(v16 + 976) & 1) != 0 || (*(_DWORD *)(v16 + 36) & 0x8000) != 0 )
  {
    if ( (unsigned int)PDEVOBJ::bAllowShareAccess((PDEVOBJ *)&v53) )
      goto LABEL_33;
    v16 = *(_QWORD *)a2;
  }
  v17 = *(_QWORD *)(v16 + 64);
  *(_QWORD *)this = v17;
  *((_QWORD *)this + 2) = *(_QWORD *)(*(_QWORD *)a2 + 48LL);
  if ( v11 == 1 && v17 == *(_QWORD *)v10 + 1144LL )
  {
    GreReleaseSemaphoreShared<2,>(v10);
    v11 = 0;
  }
  if ( *(_QWORD *)this == *(_QWORD *)v10 + 1144LL )
  {
    *((_DWORD *)this + 6) |= 0x100000u;
    GreAcquireSemaphore<2,>(v10);
  }
  else
  {
    GreAcquireSemaphore<8,PDEVOBJ>(*((_QWORD *)this + 2));
  }
  v18 = *((_DWORD *)this + 6);
  if ( (v18 & 0x200) == 0 && (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x4000) != 0 )
    *((_DWORD *)this + 6) = v18 | 0x200;
LABEL_33:
  v19 = (_QWORD *)PsGetCurrentThreadWin32Thread();
  if ( !v19 )
    goto LABEL_38;
  v20 = 0;
  v14 = *v19 == 0;
  v21 = *v19 + 8LL;
  if ( !v14 )
    v20 = v21;
  if ( !v20 || !*(_DWORD *)(v20 + 340) )
  {
LABEL_38:
    *((_DWORD *)this + 6) |= 0x1000u;
    v22 = (_QWORD *)PsGetCurrentThreadWin32Thread();
    if ( v22 )
    {
      v23 = 0;
      v14 = *v22 == 0;
      v24 = *v22 + 8LL;
      if ( !v14 )
        v23 = v24;
      if ( v23 )
      {
        *(_QWORD *)(v23 + 304) = 0;
        *(_QWORD *)(v23 + 296) = 0;
      }
    }
    v25 = (_QWORD *)PsGetCurrentThreadWin32Thread();
    if ( v25 )
    {
      v26 = 0;
      v14 = *v25 == 0;
      v27 = *v25 + 8LL;
      if ( !v14 )
        v26 = v27;
      if ( v26 )
        ++*(_DWORD *)(v26 + 340);
    }
    GreAcquireSemaphoreShared<3,>(v10);
  }
  if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x5000) == 0x1000 )
  {
    if ( (*((_DWORD *)this + 6) & 0x1000) != 0 )
      GreReleaseSemaphoreShared<3,>(v10);
    if ( v11 )
    {
LABEL_76:
      GreReleaseSemaphoreShared<2,>(v10);
      *((_DWORD *)this + 6) &= ~1u;
      return 0;
    }
    goto LABEL_138;
  }
LABEL_64:
  if ( (*((_DWORD *)this + 6) & 0x1000) != 0 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x80000) != 0 )
    {
      if ( *((_QWORD *)this + 1) )
        GreReleaseSemaphoreShared<3,>(v10);
      if ( v11 )
        goto LABEL_76;
      goto LABEL_138;
    }
  }
  else if ( *((_QWORD *)this + 1) )
  {
    goto LABEL_77;
  }
  if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x10) != 0 && !(unsigned int)DC::bCompute(*(DC **)a2) )
  {
    if ( *((_QWORD *)this + 1) )
      GreReleaseSemaphoreShared<3,>(v10);
    if ( v11 )
      goto LABEL_76;
    goto LABEL_138;
  }
LABEL_77:
  v34 = *(_QWORD *)a2;
  if ( *(_QWORD *)(*(_QWORD *)a2 + 1168LL)
    && (*(_DWORD *)(v34 + 40) & 2) != 0
    && (v35 = *(_QWORD *)(v34 + 496)) != 0
    && (*(_DWORD *)(v35 + 164) & 0x800) != 0
    || *(_QWORD *)(v34 + 1152)
    || *(_QWORD *)(v34 + 1160)
    && (*(_DWORD *)(v34 + 40) & 2) != 0
    && (v36 = *(_QWORD *)(v34 + 496)) != 0
    && (*(_DWORD *)(v36 + 164) & 0x800) != 0
    || *(_QWORD *)(v34 + 1144) )
  {
    v37 = *((_DWORD *)this + 6);
    if ( (v37 & 0x20000) == 0 && (*(_DWORD *)(v34 + 36) & 0x200) != 0 && (v37 & 0x1000) != 0 )
    {
      if ( !*((_QWORD *)this + 17) )
        DC::vSetRendering((DC *)v34);
      CurrentThread = GreGetCurrentThread();
      v39 = CurrentThread;
      if ( CurrentThread )
      {
        *((_QWORD *)CurrentThread + 37) = *(_QWORD *)a2;
        if ( (*(_DWORD *)(*(_QWORD *)a2 + 36LL) & 0x4000) == 0 )
        {
          *((_DWORD *)CurrentThread + 84) |= 1u;
          *(_QWORD *)(*(_QWORD *)a2 + 1976LL) = 0;
          v40 = (HSEMAPHORE)(*(_QWORD *)v10 + 832LL);
          EngAcquireSemaphoreShared(v40);
          v41 = GreGetCurrentThreadCrossSessionCheck();
          v44 = v41;
          if ( v41 )
          {
            v43 = *(_QWORD *)v41;
            if ( (*(_QWORD *)v41 & 0xFFFFFFDFFFFFC000uLL) != 0 && (v43 & 0x4000) == 0 )
            {
              v45 = 38;
              for ( i = 0; i < 0x40; ++i )
              {
                v47 = i;
                if ( ((1LL << i) & 0xFFFFFFDFFFFFFFFFuLL & v43) == 0 )
                  v47 = v45;
                v45 = v47;
              }
              if ( v47 > 14 && v47 != 38 )
                MicrosoftTelemetryAssertTriggeredNoArgsKM(i, (unsigned int)v47);
            }
            v42 = *((unsigned __int8 *)v44 + 22);
            *((_BYTE *)v44 + 22) = v42 + 1;
            if ( !(_BYTE)v42 )
              *(_QWORD *)v44 |= 0x4000uLL;
          }
          v14 = LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) == 0;
          *((_DWORD *)v39 + 87) = *(_DWORD *)(v10 + 4392);
          if ( !v14 && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
            McTemplateK0pz_EtwWriteTransfer(
              v42,
              (unsigned int)LockRelease,
              v43,
              (_DWORD)v40,
              (__int64)L"VisRgnUniqueness");
          v48 = GreGetCurrentThreadCrossSessionCheck();
          if ( v48 )
          {
            v14 = (*((_BYTE *)v48 + 22))-- == 1;
            if ( v14 )
              *(_QWORD *)v48 &= ~0x4000uLL;
          }
          GreReleaseSemaphoreSharedInternal(v40);
        }
      }
    }
    if ( *((_QWORD *)this + 1) && (*((_DWORD *)this + 6) & 0x1000) != 0 )
      GreReleaseSemaphoreShared<3,>(v10);
    if ( v11 )
      GreReleaseSemaphoreShared<2,>(v10);
    if ( (*((_DWORD *)this + 6) & 0x20000) == 0 )
    {
      result = DEVLOCKOBJ::bPrepareTrgDco(this, a2);
      v49 = *((_DWORD *)this + 6);
      if ( !(_DWORD)result )
      {
        *((_DWORD *)this + 6) = v49 & 0xFFFFFFFE;
        return result;
      }
      if ( (v49 & 0x81000) != 0 )
        DLODCOBJ::vLockForDPIScaledClipping((DEVLOCKOBJ *)((char *)this + 32), **(HDC **)a2);
    }
    v50 = dword_140293314 <= 0;
    if ( dword_140293314 < 0 )
    {
      _InterlockedCompareExchange(
        &dword_140293314,
        Feature_Servicing_SurfaceMapping_devlock__private_IsEnabledDeviceUsageNoInline() != 0,
        -1);
      v50 = dword_140293314 <= 0;
    }
    if ( v50 )
      return 1;
    v51 = *((_QWORD *)this + 4);
    if ( v51 && *((_BYTE *)this + 129) )
      v52 = *(SURFACE **)(v51 + 496);
    else
      v52 = *(_QWORD *)a2 ? *(SURFACE **)(*(_QWORD *)a2 + 496LL) : 0LL;
    v14 = *((_DWORD *)this + 40) == 2;
    *((_QWORD *)this + 21) = v52;
    if ( !v14 || !v52 )
      return 1;
    if ( (int)SURFACE::MapUserVAToKernel(v52, IoWriteAccess, 0) >= 0 )
    {
      *((_DWORD *)this + 40) = 0;
      return 1;
    }
    *((_DWORD *)this + 40) = 1;
  }
LABEL_138:
  *((_DWORD *)this + 6) &= ~1u;
  return 0;
}

```

## disassembly

```asm
0x140012df0  push    rbx
0x140012df2  push    rsi
0x140012df3  push    rdi
0x140012df4  push    r13
0x140012df6  push    r14
0x140012df8  push    r15
0x140012dfa  sub     rsp, 38h
0x140012dfe  xor     r13d, r13d
0x140012e01  mov     dword ptr [rcx+18h], 1
0x140012e08  mov     [rcx], r13
0x140012e0b  mov     rbx, rcx
0x140012e0e  mov     [rcx+8], r13
0x140012e12  mov     edi, r8d
0x140012e15  mov     [rcx+10h], r13
0x140012e19  mov     rsi, rdx
0x140012e1c  mov     [rcx+90h], r13
0x140012e23  mov     [rcx+88h], r13
0x140012e2a  mov     rax, [rdx]
0x140012e2d  mov     rcx, [rax]
0x140012e30  mov     [rbx+98h], rcx
0x140012e37  test    r8d, r8d
0x140012e3a  jnz     loc_140012EC6
0x140012e40  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140012e47  nop     dword ptr [rax+rax+00h]
0x140012e4c  mov     rcx, [rax+18h]
0x140012e50  mov     rax, [rcx+7F0h]
0x140012e57  test    rax, rax
0x140012e5a  jz      short loc_140012EB1
0x140012e5c  call    _guard_dispatch_icall
0x140012e61  test    eax, eax
0x140012e63  js      short loc_140012EB1
0x140012e65  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140012e6c  nop     dword ptr [rax+rax+00h]
0x140012e71  mov     rcx, [rax+18h]
0x140012e75  mov     rax, [rcx+7F8h]
0x140012e7c  test    rax, rax
0x140012e7f  jz      short loc_140012E9D
0x140012e81  lea     r9, [rbx+1Ch]
0x140012e85  mov     rcx, rsi
0x140012e88  lea     r8, [rbx+88h]
0x140012e8f  lea     rdx, [rbx+90h]
0x140012e96  call    _guard_dispatch_icall
0x140012e9b  jmp     short loc_140012EA0
0x140012e9d  mov     eax, r13d
0x140012ea0  cmp     eax, 1
0x140012ea3  jnz     short loc_140012EB1
0x140012ea5  xor     edx, edx; struct XDCOBJ *
0x140012ea7  mov     rcx, rbx; this
0x140012eaa  call    ?bPrepareTrgDco@DEVLOCKOBJ@@QEAAHPEAVXDCOBJ@@@Z; DEVLOCKOBJ::bPrepareTrgDco(XDCOBJ *)
0x140012eaf  jmp     short loc_140012EDC
0x140012eb1  and     dword ptr [rbx+18h], 0FFFFFFFEh
0x140012eb5  xor     eax, eax
0x140012eb7  add     rsp, 38h
0x140012ebb  pop     r15
0x140012ebd  pop     r14
0x140012ebf  pop     r13
0x140012ec1  pop     rdi
0x140012ec2  pop     rsi
0x140012ec3  pop     rbx
0x140012ec4  retn
0x140012ec6  xor     edx, edx; struct XDCOBJ *
0x140012ec8  mov     rcx, rbx; this
0x140012ecb  call    ?bPrepareTrgDco@DEVLOCKOBJ@@QEAAHPEAVXDCOBJ@@@Z; DEVLOCKOBJ::bPrepareTrgDco(XDCOBJ *)
0x140012ed0  cmp     edi, 1
0x140012ed3  jnz     short loc_140012EDC
0x140012ed5  or      dword ptr [rbx+18h], 20000h
0x140012edc  mov     rax, [rsi]
0x140012edf  mov     rdi, [rsi+10h]
0x140012ee3  mov     [rsp+68h+var_38], r12
0x140012ee8  mov     r12d, r13d
0x140012eeb  test    dword ptr [rax+24h], 200h
0x140012ef2  jz      loc_1400130F4
0x140012ef8  mov     rax, [rdi]
0x140012efb  mov     rcx, rdi
0x140012efe  add     rax, 270h
0x140012f04  mov     [rbx+8], rax
0x140012f08  call    ??$GreAcquireSemaphoreShared@$00$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<1,>(Gre::Base::SESSION_GLOBALS &)
0x140012f0d  or      dword ptr [rbx+18h], 8
0x140012f11  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140012f18  nop     dword ptr [rax+rax+00h]
0x140012f1d  test    rax, rax
0x140012f20  jz      short loc_140012F41
0x140012f22  mov     rcx, [rax]
0x140012f25  mov     rdx, r13
0x140012f28  test    rcx, rcx
0x140012f2b  lea     rax, [rcx+8]
0x140012f2f  cmovnz  rdx, rax
0x140012f33  test    rdx, rdx
0x140012f36  jz      short loc_140012F41
0x140012f38  cmp     [rdx+154h], r13d
0x140012f3f  jnz     short loc_140012F69
0x140012f41  mov     rcx, [rdi]
0x140012f44  add     rcx, 478h; Resource
0x140012f4b  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140012f52  nop     dword ptr [rax+rax+00h]
0x140012f57  test    eax, eax
0x140012f59  jnz     short loc_140012F69
0x140012f5b  mov     rcx, rdi
0x140012f5e  call    ??$GreAcquireSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x140012f63  mov     r12d, 1
0x140012f69  mov     rdx, [rsi]
0x140012f6c  mov     rax, [rdx+30h]
0x140012f70  mov     [rsp+68h+arg_0], rax
0x140012f75  mov     rax, [rdx+3D0h]
0x140012f7c  mov     ecx, [rax]
0x140012f7e  test    cl, 1
0x140012f81  jnz     short loc_140012F8C
0x140012f83  test    dword ptr [rdx+24h], 8000h
0x140012f8a  jz      short loc_140012F9D
0x140012f8c  lea     rcx, [rsp+68h+arg_0]; this
0x140012f91  call    ?bAllowShareAccess@PDEVOBJ@@QEBAHXZ; PDEVOBJ::bAllowShareAccess(void)
0x140012f96  test    eax, eax
0x140012f98  jnz     short loc_140013012
0x140012f9a  mov     rdx, [rsi]
0x140012f9d  mov     r8, [rdx+40h]
0x140012fa1  mov     [rbx], r8
0x140012fa4  mov     rax, [rsi]
0x140012fa7  mov     rcx, [rax+30h]
0x140012fab  mov     [rbx+10h], rcx
0x140012faf  cmp     r12d, 1
0x140012fb3  jnz     short loc_140012FCE
0x140012fb5  mov     rax, [rdi]
0x140012fb8  add     rax, 478h
0x140012fbe  cmp     r8, rax
0x140012fc1  jnz     short loc_140012FCE
0x140012fc3  mov     rcx, rdi
0x140012fc6  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x140012fcb  mov     r12d, r13d
0x140012fce  mov     rax, [rdi]
0x140012fd1  add     rax, 478h
0x140012fd7  cmp     [rbx], rax
0x140012fda  jnz     short loc_140012FED
0x140012fdc  or      dword ptr [rbx+18h], 100000h
0x140012fe3  mov     rcx, rdi
0x140012fe6  call    ??$GreAcquireSemaphore@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphore<2,>(Gre::Base::SESSION_GLOBALS &)
0x140012feb  jmp     short loc_140012FF6
0x140012fed  mov     rcx, [rbx+10h]
0x140012ff1  call    ??$GreAcquireSemaphore@$07VPDEVOBJ@@@@YAXVPDEVOBJ@@@Z; GreAcquireSemaphore<8,PDEVOBJ>(PDEVOBJ)
0x140012ff6  mov     edx, [rbx+18h]
0x140012ff9  bt      edx, 9
0x140012ffd  jb      short loc_140013012
0x140012fff  mov     rax, [rsi]
0x140013002  test    dword ptr [rax+24h], 4000h
0x140013009  jz      short loc_140013012
0x14001300b  bts     edx, 9
0x14001300f  mov     [rbx+18h], edx
0x140013012  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140013019  nop     dword ptr [rax+rax+00h]
0x14001301e  test    rax, rax
0x140013021  jz      short loc_140013042
0x140013023  mov     rcx, [rax]
0x140013026  mov     rdx, r13
0x140013029  test    rcx, rcx
0x14001302c  lea     rax, [rcx+8]
0x140013030  cmovnz  rdx, rax
0x140013034  test    rdx, rdx
0x140013037  jz      short loc_140013042
0x140013039  cmp     [rdx+154h], r13d
0x140013040  jnz     short loc_1400130B3
0x140013042  or      dword ptr [rbx+18h], 1000h
0x140013049  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140013050  nop     dword ptr [rax+rax+00h]
0x140013055  test    rax, rax
0x140013058  jz      short loc_14001307E
0x14001305a  mov     rcx, [rax]
0x14001305d  mov     rdx, r13
0x140013060  test    rcx, rcx
0x140013063  lea     rax, [rcx+8]
0x140013067  cmovnz  rdx, rax
0x14001306b  test    rdx, rdx
0x14001306e  jz      short loc_14001307E
0x140013070  mov     [rdx+130h], r13
0x140013077  mov     [rdx+128h], r13
0x14001307e  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140013085  nop     dword ptr [rax+rax+00h]
0x14001308a  test    rax, rax
0x14001308d  jz      short loc_1400130AB
0x14001308f  mov     rcx, [rax]
0x140013092  mov     rdx, r13
0x140013095  test    rcx, rcx
0x140013098  lea     rax, [rcx+8]
0x14001309c  cmovnz  rdx, rax
0x1400130a0  test    rdx, rdx
0x1400130a3  jz      short loc_1400130AB
0x1400130a5  inc     dword ptr [rdx+154h]
0x1400130ab  mov     rcx, rdi
0x1400130ae  call    ??$GreAcquireSemaphoreShared@$02$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreAcquireSemaphoreShared<3,>(Gre::Base::SESSION_GLOBALS &)
0x1400130b3  mov     rax, [rsi]
0x1400130b6  mov     ecx, [rax+24h]
0x1400130b9  and     ecx, 5000h
0x1400130bf  cmp     ecx, 1000h
0x1400130c5  jnz     loc_140013158
0x1400130cb  test    [rbx+18h], ecx
0x1400130ce  jz      short loc_1400130D8
0x1400130d0  mov     rcx, rdi
0x1400130d3  call    ??$GreReleaseSemaphoreShared@$02$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<3,>(Gre::Base::SESSION_GLOBALS &)
0x1400130d8  test    r12d, r12d
0x1400130db  jz      loc_1400134AF
0x1400130e1  mov     rcx, rdi
0x1400130e4  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x1400130e9  and     dword ptr [rbx+18h], 0FFFFFFFEh
0x1400130ed  xor     eax, eax
0x1400130ef  jmp     loc_140013491
0x1400130f4  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400130fb  nop     dword ptr [rax+rax+00h]
0x140013100  test    rax, rax
0x140013103  jz      short loc_140013124
0x140013105  mov     rcx, [rax]
0x140013108  mov     rdx, r13
0x14001310b  test    rcx, rcx
0x14001310e  lea     rax, [rcx+8]
0x140013112  cmovnz  rdx, rax
0x140013116  test    rdx, rdx
0x140013119  jz      short loc_140013124
0x14001311b  cmp     [rdx+154h], r13d
0x140013122  jnz     short loc_140013158
0x140013124  or      dword ptr [rbx+18h], 80000h
0x14001312b  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140013132  nop     dword ptr [rax+rax+00h]
0x140013137  test    rax, rax
0x14001313a  jz      short loc_140013158
0x14001313c  mov     rcx, [rax]
0x14001313f  mov     rdx, r13
0x140013142  test    rcx, rcx
0x140013145  lea     rax, [rcx+8]
0x140013149  cmovnz  rdx, rax
0x14001314d  test    rdx, rdx
0x140013150  jz      short loc_140013158
0x140013152  inc     dword ptr [rdx+154h]
0x140013158  test    dword ptr [rbx+18h], 1000h
0x14001315f  jz      short loc_140013197
0x140013161  mov     rax, [rsi]
0x140013164  test    dword ptr [rax+24h], 80000h
0x14001316b  jz      short loc_14001319D
0x14001316d  cmp     [rbx+8], r13
0x140013171  jz      short loc_14001317B
0x140013173  mov     rcx, rdi
0x140013176  call    ??$GreReleaseSemaphoreShared@$02$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<3,>(Gre::Base::SESSION_GLOBALS &)
0x14001317b  test    r12d, r12d
0x14001317e  jz      loc_1400134AF
0x140013184  mov     rcx, rdi
0x140013187  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x14001318c  and     dword ptr [rbx+18h], 0FFFFFFFEh
0x140013190  xor     eax, eax
0x140013192  jmp     loc_140013491
0x140013197  cmp     [rbx+8], r13
0x14001319b  jnz     short loc_1400131DA
0x14001319d  mov     rcx, [rsi]; this
0x1400131a0  mov     eax, [rcx+24h]
0x1400131a3  test    al, 10h
0x1400131a5  jz      short loc_1400131DA
0x1400131a7  call    ?bCompute@DC@@QEAAHXZ; DC::bCompute(void)
0x1400131ac  test    eax, eax
0x1400131ae  jnz     short loc_1400131DA
0x1400131b0  cmp     [rbx+8], r13
0x1400131b4  jz      short loc_1400131BE
0x1400131b6  mov     rcx, rdi
0x1400131b9  call    ??$GreReleaseSemaphoreShared@$02$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<3,>(Gre::Base::SESSION_GLOBALS &)
0x1400131be  test    r12d, r12d
0x1400131c1  jz      loc_1400134AF
0x1400131c7  mov     rcx, rdi
0x1400131ca  call    ??$GreReleaseSemaphoreShared@$01$$V@@YAXAEAUSESSION_GLOBALS@Base@Gre@@@Z; GreReleaseSemaphoreShared<2,>(Gre::Base::SESSION_GLOBALS &)
0x1400131cf  and     dword ptr [rbx+18h], 0FFFFFFFEh
0x1400131d3  xor     eax, eax
0x1400131d5  jmp     loc_140013491
0x1400131da  mov     rcx, [rsi]; this
0x1400131dd  cmp     [rcx+490h], r13
0x1400131e4  jz      short loc_140013205
0x1400131e6  mov     eax, [rcx+28h]
0x1400131e9  test    al, 2
0x1400131eb  jz      short loc_140013205
0x1400131ed  mov     rax, [rcx+1F0h]
0x1400131f4  test    rax, rax
0x1400131f7  jz      short loc_140013205
0x1400131f9  test    dword ptr [rax+0A4h], 800h
0x140013203  jnz     short loc_140013243
0x140013205  cmp     [rcx+480h], r13
0x14001320c  jnz     short loc_140013243
0x14001320e  cmp     [rcx+488h], r13
0x140013215  jz      short loc_140013236
0x140013217  mov     eax, [rcx+28h]
0x14001321a  test    al, 2
0x14001321c  jz      short loc_140013236
0x14001321e  mov     rax, [rcx+1F0h]
0x140013225  test    rax, rax
0x140013228  jz      short loc_140013236
0x14001322a  test    dword ptr [rax+0A4h], 800h
0x140013234  jnz     short loc_140013243
0x140013236  cmp     [rcx+478h], r13
0x14001323d  jz      loc_1400134AF
0x140013243  mov     edx, [rbx+18h]
0x140013246  bt      edx, 11h
0x14001324a  jb      loc_1400133A1
0x140013250  test    dword ptr [rcx+24h], 200h
0x140013257  jz      loc_1400133A1
0x14001325d  bt      edx, 0Ch
0x140013261  jnb     loc_1400133A1
0x140013267  mov     [rsp+68h+arg_8], rbp
0x14001326c  cmp     [rbx+88h], r13
0x140013273  jnz     short loc_14001327A
  ... truncated ...
```
