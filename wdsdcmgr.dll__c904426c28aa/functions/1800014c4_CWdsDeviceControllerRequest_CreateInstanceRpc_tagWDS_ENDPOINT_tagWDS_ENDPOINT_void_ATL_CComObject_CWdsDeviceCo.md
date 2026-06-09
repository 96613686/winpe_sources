# CWdsDeviceControllerRequest::CreateInstanceRpc(tagWDS_ENDPOINT *,tagWDS_ENDPOINT *,void *,ATL::CComObject<CWdsDeviceControllerRequest> * *)

- ea: `0x1800014c4`
- end: `0x18000164c`
- name: `?CreateInstanceRpc@CWdsDeviceControllerRequest@@SAJPEAUtagWDS_ENDPOINT@@0PEAXPEAPEAV?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800026ac`
- `0x18000294c`
- `0x180003508`

## callees

- `0x1800014c4`
- `0x180001be0`
- `0x180014ee0`
- `0x180015cc0`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerRequest::CreateInstanceRpc(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  unsigned int Instance; // ebp
  const char *v9; // rdx
  int v10; // eax
  __int64 v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int128 v15; // xmm1
  __int64 v16; // rcx
  __int128 v17; // xmm1
  _QWORD v19[5]; // [rsp+20h] [rbp-28h] BYREF

  v19[0] = 0;
  Instance = ATL::CComObject<CWdsDeviceControllerRequest>::CreateInstance(v19);
  v10 = ElValidateHr(Instance, v9, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollerrequest.cpp", 0xC2u);
  v11 = v19[0];
  if ( v10 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19[0] + 8LL))(v19[0]);
    v12 = 8;
    *(_DWORD *)(v11 + 104) = 1;
    v13 = v11 + 116;
    v14 = 8;
    do
    {
      *(_OWORD *)v13 = *(_OWORD *)a1;
      *(_OWORD *)(v13 + 16) = *(_OWORD *)(a1 + 16);
      *(_OWORD *)(v13 + 32) = *(_OWORD *)(a1 + 32);
      *(_OWORD *)(v13 + 48) = *(_OWORD *)(a1 + 48);
      *(_OWORD *)(v13 + 64) = *(_OWORD *)(a1 + 64);
      *(_OWORD *)(v13 + 80) = *(_OWORD *)(a1 + 80);
      *(_OWORD *)(v13 + 96) = *(_OWORD *)(a1 + 96);
      v13 += 128;
      v15 = *(_OWORD *)(a1 + 112);
      a1 += 128;
      *(_OWORD *)(v13 - 16) = v15;
      --v14;
    }
    while ( v14 );
    *(_OWORD *)v13 = *(_OWORD *)a1;
    *(_QWORD *)(v13 + 16) = *(_QWORD *)(a1 + 16);
    *(_DWORD *)(v13 + 24) = *(_DWORD *)(a1 + 24);
    v16 = v11 + 1168;
    do
    {
      *(_OWORD *)v16 = *(_OWORD *)a2;
      *(_OWORD *)(v16 + 16) = *(_OWORD *)(a2 + 16);
      *(_OWORD *)(v16 + 32) = *(_OWORD *)(a2 + 32);
      *(_OWORD *)(v16 + 48) = *(_OWORD *)(a2 + 48);
      *(_OWORD *)(v16 + 64) = *(_OWORD *)(a2 + 64);
      *(_OWORD *)(v16 + 80) = *(_OWORD *)(a2 + 80);
      *(_OWORD *)(v16 + 96) = *(_OWORD *)(a2 + 96);
      v16 += 128;
      v17 = *(_OWORD *)(a2 + 112);
      a2 += 128;
      *(_OWORD *)(v16 - 16) = v17;
      --v12;
    }
    while ( v12 );
    *(_OWORD *)v16 = *(_OWORD *)a2;
    *(_QWORD *)(v16 + 16) = *(_QWORD *)(a2 + 16);
    *(_DWORD *)(v16 + 24) = *(_DWORD *)(a2 + 24);
    *(_QWORD *)(v11 + 2224) = a3;
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v11 + 8LL))(v11, 0, 128);
    *a4 = v11;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return Instance;
}

```

## disassembly

```asm
0x1800014c4  mov     rax, rsp
0x1800014c7  mov     [rax+8], rbx
0x1800014cb  mov     [rax+10h], rbp
0x1800014cf  mov     [rax+18h], rsi
0x1800014d3  push    rdi
0x1800014d4  push    r14
0x1800014d6  push    r15
0x1800014d8  sub     rsp, 30h
0x1800014dc  and     qword ptr [rax-28h], 0
0x1800014e1  mov     rsi, rcx
0x1800014e4  lea     rcx, [rax-28h]
0x1800014e8  mov     r14, r9
0x1800014eb  mov     r15, r8
0x1800014ee  mov     rdi, rdx
0x1800014f1  call    ?CreateInstance@?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWdsDeviceControllerRequest>::CreateInstance(ATL::CComObject<CWdsDeviceControllerRequest> * *)
0x1800014f6  mov     r9d, 0C2h; unsigned int
0x1800014fc  lea     r8, aBaseEcoWdsWdss_3; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180001503  mov     ecx, eax; int
0x180001505  mov     ebp, eax
0x180001507  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000150c  mov     rbx, [rsp+48h+var_28]
0x180001511  test    eax, eax
0x180001513  js      loc_18000161C
0x180001519  mov     rcx, [rbx]
0x18000151c  mov     rax, [rcx+8]
0x180001520  mov     rcx, rbx
0x180001523  call    cs:__guard_dispatch_icall_fptr
0x180001529  mov     edx, 8
0x18000152e  mov     dword ptr [rbx+68h], 1
0x180001535  lea     rcx, [rbx+74h]
0x180001539  mov     eax, edx
0x18000153b  lea     r8d, [rdx+78h]
0x18000153f  movups  xmm0, xmmword ptr [rsi]
0x180001542  movups  xmmword ptr [rcx], xmm0
0x180001545  movups  xmm1, xmmword ptr [rsi+10h]
0x180001549  movups  xmmword ptr [rcx+10h], xmm1
0x18000154d  movups  xmm0, xmmword ptr [rsi+20h]
0x180001551  movups  xmmword ptr [rcx+20h], xmm0
0x180001555  movups  xmm1, xmmword ptr [rsi+30h]
0x180001559  movups  xmmword ptr [rcx+30h], xmm1
0x18000155d  movups  xmm0, xmmword ptr [rsi+40h]
0x180001561  movups  xmmword ptr [rcx+40h], xmm0
0x180001565  movups  xmm1, xmmword ptr [rsi+50h]
0x180001569  movups  xmmword ptr [rcx+50h], xmm1
0x18000156d  movups  xmm0, xmmword ptr [rsi+60h]
0x180001571  movups  xmmword ptr [rcx+60h], xmm0
0x180001575  add     rcx, r8
0x180001578  movups  xmm1, xmmword ptr [rsi+70h]
0x18000157c  add     rsi, r8
0x18000157f  movups  xmmword ptr [rcx-10h], xmm1
0x180001583  sub     rax, 1
0x180001587  jnz     short loc_18000153F
0x180001589  movups  xmm0, xmmword ptr [rsi]
0x18000158c  movups  xmmword ptr [rcx], xmm0
0x18000158f  mov     rax, [rsi+10h]
0x180001593  mov     [rcx+10h], rax
0x180001597  mov     eax, [rsi+18h]
0x18000159a  mov     [rcx+18h], eax
0x18000159d  lea     rcx, [rbx+490h]
0x1800015a4  movups  xmm0, xmmword ptr [rdi]
0x1800015a7  movups  xmmword ptr [rcx], xmm0
0x1800015aa  movups  xmm1, xmmword ptr [rdi+10h]
0x1800015ae  movups  xmmword ptr [rcx+10h], xmm1
0x1800015b2  movups  xmm0, xmmword ptr [rdi+20h]
0x1800015b6  movups  xmmword ptr [rcx+20h], xmm0
0x1800015ba  movups  xmm1, xmmword ptr [rdi+30h]
0x1800015be  movups  xmmword ptr [rcx+30h], xmm1
0x1800015c2  movups  xmm0, xmmword ptr [rdi+40h]
0x1800015c6  movups  xmmword ptr [rcx+40h], xmm0
0x1800015ca  movups  xmm1, xmmword ptr [rdi+50h]
0x1800015ce  movups  xmmword ptr [rcx+50h], xmm1
0x1800015d2  movups  xmm0, xmmword ptr [rdi+60h]
0x1800015d6  movups  xmmword ptr [rcx+60h], xmm0
0x1800015da  add     rcx, r8
0x1800015dd  movups  xmm1, xmmword ptr [rdi+70h]
0x1800015e1  add     rdi, r8
0x1800015e4  movups  xmmword ptr [rcx-10h], xmm1
0x1800015e8  sub     rdx, 1
0x1800015ec  jnz     short loc_1800015A4
0x1800015ee  movups  xmm0, xmmword ptr [rdi]
0x1800015f1  movups  xmmword ptr [rcx], xmm0
0x1800015f4  mov     rax, [rdi+10h]
0x1800015f8  mov     [rcx+10h], rax
0x1800015fc  mov     eax, [rdi+18h]
0x1800015ff  mov     [rcx+18h], eax
0x180001602  mov     rcx, rbx
0x180001605  mov     [rbx+8B0h], r15
0x18000160c  mov     rax, [rbx]
0x18000160f  mov     rax, [rax+8]
0x180001613  call    cs:__guard_dispatch_icall_fptr
0x180001619  mov     [r14], rbx
0x18000161c  test    rbx, rbx
0x18000161f  jz      short loc_180001631
0x180001621  mov     rax, [rbx]
0x180001624  mov     rcx, rbx
0x180001627  mov     rax, [rax+10h]
0x18000162b  call    cs:__guard_dispatch_icall_fptr
0x180001631  mov     rbx, [rsp+48h+arg_0]
0x180001636  mov     eax, ebp
0x180001638  mov     rbp, [rsp+48h+arg_8]
0x18000163d  mov     rsi, [rsp+48h+arg_10]
0x180001642  add     rsp, 30h
0x180001646  pop     r15
0x180001648  pop     r14
0x18000164a  pop     rdi
0x18000164b  retn
```
