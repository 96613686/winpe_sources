# CDeliveryAgent::SendUpdateEnd(void)

- ea: `0x1800053a4`
- end: `0x18000566b`
- name: `?SendUpdateEnd@CDeliveryAgent@@AEAAXXZ`
- size: `711`
- prototype: `void __fastcall(CDeliveryAgent *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x180004e10`
- `0x180005674`

## callees

- `0x180003950`
- `0x18000501c`
- `0x1800053a4`
- `0x180018d98`
- `0x18001dbdc`
- `0x18001dc84`
- `0x18001dcc4`
- `0x18001dd34`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetLocalTime` at `0x180005412`
- `KERNEL32!GetLocalTime` at `0x180005412`
- `USER32!LoadStringW` at `0x18000553c`
- `USER32!LoadStringW` at `0x18000553c`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180005422`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180005422`

## pseudocode

```c
void __fastcall CDeliveryAgent::SendUpdateEnd(CDeliveryAgent *this, const unsigned __int16 *a2)
{
  int v2; // r8d
  struct ISubscriptionItem *v4; // rcx
  unsigned __int16 *v5; // r14
  const unsigned __int16 *v6; // rdx
  int v7; // eax
  struct ISubscriptionItem *v8; // rdi
  __int64 v9; // r8
  struct ISubscriptionItem *v10; // rdx
  int v11; // eax
  UINT uID; // [rsp+30h] [rbp-D0h] BYREF
  DOUBLE pvtime; // [rsp+38h] [rbp-C8h] BYREF
  struct ISubscriptionItem *v14; // [rsp+40h] [rbp-C0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v16[128]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[128]; // [rsp+160h] [rbp+60h] BYREF

  v2 = *((_DWORD *)this + 27);
  v4 = (struct ISubscriptionItem *)*((_QWORD *)this + 10);
  v5 = 0;
  uID = 0;
  v14 = 0;
  WriteSCODE(v4, a2, v2);
  if ( *((int *)this + 27) >= 0 )
  {
    pvtime = 0.0;
    SystemTime = 0;
    GetLocalTime(&SystemTime);
    if ( SystemTimeToVariantTime(&SystemTime, &pvtime) )
      WriteDATE(*((struct ISubscriptionItem **)this + 10), v6, &pvtime);
    else
      *((_DWORD *)this + 27) = -2147467259;
  }
  v7 = *((_DWORD *)this + 27);
  switch ( v7 )
  {
    case 790526:
      *((_DWORD *)this + 27) = 0;
LABEL_7:
      uID = 8154;
      break;
    case -2147467260:
      uID = 8148;
      break;
    case -2147024882:
      uID = 8155;
      break;
    case -2147024809:
      uID = 8150;
      break;
    case -2146697207:
      uID = 8149;
      break;
    case -2146693248:
      uID = 8014;
      break;
    case -2146693246:
      uID = 8013;
      break;
    case -2146693245:
      uID = 8152;
      break;
    case 1:
      uID = 8156;
      break;
    default:
      if ( v7 >= 0 )
        goto LABEL_7;
      uID = 8153;
      break;
  }
  DoCloneSubscriptionItem(*((struct ISubscriptionItem **)this + 10), 0, &v14);
  v8 = v14;
  (*(void (__fastcall **)(CDeliveryAgent *, struct ISubscriptionItem *, UINT *))(*(_QWORD *)this + 96LL))(
    this,
    v14,
    &uID);
  if ( uID != -1 )
  {
    if ( LoadStringW(g_hinstMUI, uID, Buffer, 128) )
    {
      StringCchCopyW(v16, 0x80u, Buffer);
      if ( v8 )
        WriteOLESTR(v8, L"StatusString", v16);
      WriteOLESTR(*((struct ISubscriptionItem **)this + 10), L"StatusString", v16);
      v5 = v16;
    }
    else
    {
      WriteEMPTY(*((struct ISubscriptionItem **)this + 10), L"StatusString");
    }
  }
  v9 = *((unsigned int *)this + 27);
  if ( (int)v9 < 0 )
    (*(void (__fastcall **)(_QWORD, char *, __int64, unsigned __int16 *))(**((_QWORD **)this + 9) + 48LL))(
      *((_QWORD *)this + 9),
      (char *)this + 88,
      v9,
      v5);
  (*(void (__fastcall **)(_QWORD, char *, _QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 9) + 40LL))(
    *((_QWORD *)this + 9),
    (char *)this + 88,
    *((unsigned int *)this + 26),
    *((unsigned int *)this + 27),
    v5);
  if ( (*((_BYTE *)this + 44) & 4) == 0 )
  {
    v10 = v8;
    if ( !v8 )
      v10 = (struct ISubscriptionItem *)*((_QWORD *)this + 10);
    CDeliveryAgent::ProcessEndItem(this, v10);
  }
  if ( (*((_DWORD *)this + 11) & 0x100000) == 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 72LL))(*((_QWORD *)this + 10));
  if ( v8 )
    ((void (__fastcall *)(struct ISubscriptionItem *))v8->lpVtbl->Release)(v8);
  v11 = *((_DWORD *)this + 11);
  if ( (v11 & 0x10000) != 0 )
  {
    *((_DWORD *)this + 11) = v11 & 0xFFFEFFFF;
    (*(void (__fastcall **)(CDeliveryAgent *))(*(_QWORD *)this + 16LL))(this);
  }
}

```

## disassembly

```asm
0x1800053a4  mov     [rsp-8+arg_8], rbx
0x1800053a9  mov     [rsp-8+arg_10], rsi
0x1800053ae  push    rbp
0x1800053af  push    rdi
0x1800053b0  push    r14
0x1800053b2  lea     rbp, [rsp-170h]
0x1800053ba  sub     rsp, 270h
0x1800053c1  mov     rax, cs:__security_cookie
0x1800053c8  xor     rax, rsp
0x1800053cb  mov     [rbp+180h+var_20], rax
0x1800053d2  mov     r8d, [rcx+6Ch]; int
0x1800053d6  mov     rbx, rcx
0x1800053d9  mov     rcx, [rcx+50h]; struct ISubscriptionItem *
0x1800053dd  xor     r14d, r14d
0x1800053e0  mov     [rsp+280h+uID], 0
0x1800053e8  mov     [rsp+280h+var_240], 0
0x1800053f1  call    ?WriteSCODE@@YAJPEAUISubscriptionItem@@PEBGJ@Z; WriteSCODE(ISubscriptionItem *,ushort const *,long)
0x1800053f6  cmp     [rbx+6Ch], r14d
0x1800053fa  jl      short loc_180005443
0x1800053fc  xorps   xmm0, xmm0
0x1800053ff  lea     rcx, [rsp+280h+SystemTime]; lpSystemTime
0x180005404  xorps   xmm1, xmm1
0x180005407  movsd   [rsp+280h+pvtime], xmm1
0x18000540d  movups  xmmword ptr [rsp+280h+SystemTime.wYear], xmm0
0x180005412  call    cs:__imp_GetLocalTime
0x180005418  lea     rdx, [rsp+280h+pvtime]; pvtime
0x18000541d  lea     rcx, [rsp+280h+SystemTime]; lpSystemTime
0x180005422  call    cs:__imp_SystemTimeToVariantTime
0x180005428  test    eax, eax
0x18000542a  jz      short loc_18000543C
0x18000542c  mov     rcx, [rbx+50h]; struct ISubscriptionItem *
0x180005430  lea     r8, [rsp+280h+pvtime]; double *
0x180005435  call    ?WriteDATE@@YAJPEAUISubscriptionItem@@PEBGPEAN@Z; WriteDATE(ISubscriptionItem *,ushort const *,double *)
0x18000543a  jmp     short loc_180005443
0x18000543c  mov     dword ptr [rbx+6Ch], 80004005h
0x180005443  mov     eax, [rbx+6Ch]
0x180005446  cmp     eax, 0C0FFEh
0x18000544b  jnz     short loc_18000545E
0x18000544d  mov     [rbx+6Ch], r14d
0x180005451  mov     [rsp+280h+uID], 1FDAh
0x180005459  jmp     loc_1800054F4
0x18000545e  cmp     eax, 80004004h
0x180005463  jz      loc_1800054EC
0x180005469  cmp     eax, 8007000Eh
0x18000546e  jz      short loc_1800054E2
0x180005470  cmp     eax, 80070057h
0x180005475  jz      short loc_1800054D8
0x180005477  cmp     eax, 800C0009h
0x18000547c  jz      short loc_1800054CE
0x18000547e  cmp     eax, 800C0F80h
0x180005483  jz      short loc_1800054C4
0x180005485  cmp     eax, 800C0F82h
0x18000548a  jz      short loc_1800054BA
0x18000548c  cmp     eax, 800C0F83h
0x180005491  jz      short loc_1800054B0
0x180005493  cmp     eax, 1
0x180005496  jz      short loc_1800054A6
0x180005498  test    eax, eax
0x18000549a  jns     short loc_180005451
0x18000549c  mov     [rsp+280h+uID], 1FD9h
0x1800054a4  jmp     short loc_1800054F4
0x1800054a6  mov     [rsp+280h+uID], 1FDCh
0x1800054ae  jmp     short loc_1800054F4
0x1800054b0  mov     [rsp+280h+uID], 1FD8h
0x1800054b8  jmp     short loc_1800054F4
0x1800054ba  mov     [rsp+280h+uID], 1F4Dh
0x1800054c2  jmp     short loc_1800054F4
0x1800054c4  mov     [rsp+280h+uID], 1F4Eh
0x1800054cc  jmp     short loc_1800054F4
0x1800054ce  mov     [rsp+280h+uID], 1FD5h
0x1800054d6  jmp     short loc_1800054F4
0x1800054d8  mov     [rsp+280h+uID], 1FD6h
0x1800054e0  jmp     short loc_1800054F4
0x1800054e2  mov     [rsp+280h+uID], 1FDBh
0x1800054ea  jmp     short loc_1800054F4
0x1800054ec  mov     [rsp+280h+uID], 1FD4h
0x1800054f4  mov     rcx, [rbx+50h]; struct ISubscriptionItem *
0x1800054f8  lea     r8, [rsp+280h+var_240]; struct ISubscriptionItem **
0x1800054fd  xor     edx, edx; struct _GUID *
0x1800054ff  call    ?DoCloneSubscriptionItem@@YAJPEAUISubscriptionItem@@PEAU_GUID@@PEAPEAU1@@Z; DoCloneSubscriptionItem(ISubscriptionItem *,_GUID *,ISubscriptionItem * *)
0x180005504  mov     rax, [rbx]
0x180005507  lea     r8, [rsp+280h+uID]
0x18000550c  mov     rdi, [rsp+280h+var_240]
0x180005511  mov     rcx, rbx
0x180005514  mov     rdx, rdi
0x180005517  mov     rax, [rax+60h]
0x18000551b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005520  mov     edx, [rsp+280h+uID]; uID
0x180005524  cmp     edx, 0FFFFFFFFh
0x180005527  jz      short loc_18000559B
0x180005529  mov     rcx, cs:g_hinstMUI; hInstance
0x180005530  lea     r8, [rbp+180h+Buffer]; lpBuffer
0x180005534  mov     esi, 80h
0x180005539  mov     r9d, esi; cchBufferMax
0x18000553c  call    cs:__imp_LoadStringW
0x180005542  test    eax, eax
0x180005544  jz      short loc_18000558B
0x180005546  lea     r8, [rbp+180h+Buffer]; unsigned __int16 *
0x18000554a  mov     edx, esi; unsigned __int64
0x18000554c  lea     rcx, [rsp+280h+var_220]; unsigned __int16 *
0x180005551  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005556  test    rdi, rdi
0x180005559  jz      short loc_18000556F
0x18000555b  lea     r8, [rsp+280h+var_220]; unsigned __int16 *
0x180005560  mov     rcx, rdi; struct ISubscriptionItem *
0x180005563  lea     rdx, ?c_szPropStatusString@@3QBGB; "StatusString"
0x18000556a  call    ?WriteOLESTR@@YAJPEAUISubscriptionItem@@PEBG1@Z; WriteOLESTR(ISubscriptionItem *,ushort const *,ushort const *)
0x18000556f  mov     rcx, [rbx+50h]; struct ISubscriptionItem *
0x180005573  lea     r8, [rsp+280h+var_220]; unsigned __int16 *
0x180005578  lea     rdx, ?c_szPropStatusString@@3QBGB; "StatusString"
0x18000557f  call    ?WriteOLESTR@@YAJPEAUISubscriptionItem@@PEBG1@Z; WriteOLESTR(ISubscriptionItem *,ushort const *,ushort const *)
0x180005584  lea     r14, [rsp+280h+var_220]
0x180005589  jmp     short loc_18000559B
0x18000558b  mov     rcx, [rbx+50h]; struct ISubscriptionItem *
0x18000558f  lea     rdx, ?c_szPropStatusString@@3QBGB; "StatusString"
0x180005596  call    ?WriteEMPTY@@YAJPEAUISubscriptionItem@@PEBG@Z; WriteEMPTY(ISubscriptionItem *,ushort const *)
0x18000559b  mov     r8d, [rbx+6Ch]
0x18000559f  lea     rsi, [rbx+58h]
0x1800055a3  test    r8d, r8d
0x1800055a6  jns     short loc_1800055BE
0x1800055a8  mov     rcx, [rbx+48h]
0x1800055ac  mov     r9, r14
0x1800055af  mov     rdx, rsi
0x1800055b2  mov     rax, [rcx]
0x1800055b5  mov     rax, [rax+30h]
0x1800055b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055be  mov     rcx, [rbx+48h]
0x1800055c2  mov     rdx, rsi
0x1800055c5  mov     r9d, [rbx+6Ch]
0x1800055c9  mov     r8d, [rbx+68h]
0x1800055cd  mov     [rsp+280h+var_260], r14
0x1800055d2  mov     rax, [rcx]
0x1800055d5  mov     rax, [rax+28h]
0x1800055d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055de  test    byte ptr [rbx+2Ch], 4
0x1800055e2  jnz     short loc_1800055F8
0x1800055e4  mov     rcx, rbx; this
0x1800055e7  mov     rdx, rdi
0x1800055ea  test    rdi, rdi
0x1800055ed  jnz     short loc_1800055F3
0x1800055ef  mov     rdx, [rbx+50h]; struct ISubscriptionItem *
0x1800055f3  call    ?ProcessEndItem@CDeliveryAgent@@AEAAJPEAUISubscriptionItem@@@Z; CDeliveryAgent::ProcessEndItem(ISubscriptionItem *)
0x1800055f8  test    dword ptr [rbx+2Ch], 100000h
0x1800055ff  jnz     short loc_180005611
0x180005601  mov     rcx, [rbx+50h]
0x180005605  mov     rax, [rcx]
0x180005608  mov     rax, [rax+48h]
0x18000560c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005611  test    rdi, rdi
0x180005614  jz      short loc_180005625
0x180005616  mov     rax, [rdi]
0x180005619  mov     rcx, rdi
0x18000561c  mov     rax, [rax+10h]
0x180005620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005625  mov     eax, [rbx+2Ch]
0x180005628  bt      eax, 10h
0x18000562c  jnb     short loc_180005644
0x18000562e  btr     eax, 10h
0x180005632  mov     rcx, rbx
0x180005635  mov     [rbx+2Ch], eax
0x180005638  mov     rax, [rbx]
0x18000563b  mov     rax, [rax+10h]
0x18000563f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005644  mov     rcx, [rbp+180h+var_20]
0x18000564b  xor     rcx, rsp; StackCookie
0x18000564e  call    __security_check_cookie
0x180005653  lea     r11, [rsp+280h+var_10]
0x18000565b  mov     rbx, [r11+28h]
0x18000565f  mov     rsi, [r11+30h]
0x180005663  mov     rsp, r11
0x180005666  pop     r14
0x180005668  pop     rdi
0x180005669  pop     rbp
0x18000566a  retn
```
