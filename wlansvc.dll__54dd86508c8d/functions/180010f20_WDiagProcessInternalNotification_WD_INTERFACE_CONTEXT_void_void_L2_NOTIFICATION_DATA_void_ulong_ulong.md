# WDiagProcessInternalNotification(_WD_INTERFACE_CONTEXT *,void *,void *,_L2_NOTIFICATION_DATA *,void *,ulong,ulong)

- ea: `0x180010f20`
- end: `0x1800113b3`
- name: `?WDiagProcessInternalNotification@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAX1PEAU_L2_NOTIFICATION_DATA@@1KK@Z`
- size: `1171`
- prototype: `unsigned int __usercall@<eax>(struct _WD_INTERFACE_CONTEXT *@<rcx>, void *@<rdx>, void *@<r8>, struct _L2_NOTIFICATION_DATA *@<r9>, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180011558`

## callees

- `0x18000aa0c`
- `0x1800108f0`
- `0x180010f20`
- `0x180011530`
- `0x180011b98`
- `0x18001226c`
- `0x18002be58`
- `0x18003fda0`
- `0x1801c6ac8`
- `0x1801c81ac`
- `0x1801c82e4`
- `0x1801ce4d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011067`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011067`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010ff2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010ff2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011001`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011001`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010fe5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800112f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010fe5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800112f6`

## pseudocode

```c
__int64 __fastcall WDiagProcessInternalNotification(
        struct _WD_INTERFACE_CONTEXT *a1,
        void *a2,
        void *a3,
        struct _L2_NOTIFICATION_DATA *a4,
        void *a5,
        unsigned int a6,
        unsigned int a7)
{
  PVOID *v11; // rcx
  DWORD CurrentThreadId; // r15d
  __int64 NotificationSource; // r9
  unsigned int v14; // eax
  unsigned int v15; // ebx
  char v17; // al
  unsigned int v18; // [rsp+20h] [rbp-68h]
  int v19; // [rsp+28h] [rbp-60h]

  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 56, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 225) >= 3u && (*((_BYTE *)v11 + 228) & 4) != 0 )
    {
      WPP_SF__guid_(v11[27], 57, &WPP_fec73b95d5a537674450248f38664378_Traceguids, (char *)a1 + 3488);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( a5 )
  {
    CurrentThreadId = GetCurrentThreadId();
    EnterCriticalSection((LPCRITICAL_SECTION)a1 + 84);
    WaitForSingleObject(*((HANDLE *)a1 + 430), 0xFFFFFFFF);
    if ( (*((_BYTE *)a1 + 3448) & 4) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      WPP_SF_qqdsddsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_BYTE)a1 + 24,
        *((_DWORD *)a1 + 864),
        *((_QWORD *)a1 + 433),
        *((_DWORD *)a1 + 865),
        CurrentThreadId,
        (__int64)"WDiagProcessInternalNotification",
        157);
    }
    *((_DWORD *)a1 + 862) |= 4u;
    *((_DWORD *)a1 + 864) = CurrentThreadId;
    *((_DWORD *)a1 + 865) = 925;
    *((_QWORD *)a1 + 433) = "WDiagProcessInternalNotification";
    *((_DWORD *)a1 + 1010) = a6;
    if ( (*((_BYTE *)a1 + 3448) & 4) == 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225)
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x40) != 0 )
    {
      v17 = GetCurrentThreadId();
      WPP_SF_qqDsdDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        (_BYTE)a1 + 24,
        v19,
        *((_QWORD *)a1 + 435),
        *((_DWORD *)a1 + 868),
        v17,
        (__int64)"WDiagProcessInternalNotification",
        159);
    }
    *((_DWORD *)a1 + 862) &= ~4u;
    *((_DWORD *)a1 + 868) = 927;
    *((_QWORD *)a1 + 435) = "WDiagProcessInternalNotification";
    *((_DWORD *)a1 + 864) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 84);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  NotificationSource = a4->NotificationSource;
  switch ( (_DWORD)NotificationSource )
  {
    case 8:
      v14 = WDiagProcessInternalAcmNotification(a1, a2, a4, 8u, v18);
LABEL_14:
      v15 = v14;
LABEL_15:
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_16;
    case 0x10:
      v14 = WDiagProcessInternalMsmNotification(a1, a2, a3, a4, a6, a7);
      goto LABEL_14;
    case 0x40:
      if ( v11 != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)v11 + 57) & 0x200) != 0 )
        {
          WPP_SF_(v11[27], 52, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
          v11 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v11 != &WPP_GLOBAL_Control )
        {
          if ( *((_BYTE *)v11 + 225) && (*((_BYTE *)v11 + 228) & 4) != 0 )
          {
            WPP_SF_d(v11[27], 53, &WPP_fec73b95d5a537674450248f38664378_Traceguids, a4->NotificationCode);
            v11 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v11 != &WPP_GLOBAL_Control )
          {
            if ( *((_BYTE *)v11 + 225) >= 4u && (*((_BYTE *)v11 + 228) & 4) != 0 )
            {
              WPP_SF_S(v11[27], 54, &WPP_fec73b95d5a537674450248f38664378_Traceguids, L"Unknown");
              v11 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 57) & 0x200) != 0 )
            {
              WPP_SF_(v11[27], 55, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
              v11 = (PVOID *)WPP_GLOBAL_Control;
            }
          }
        }
      }
      v15 = 0;
      goto LABEL_16;
    case 2:
      v14 = WDiagSecurityNotification((__int64)a1, a3, a4->NotificationCode, (__int64)a4->pData);
      goto LABEL_14;
    case 4:
      v14 = WDiagOneXNotification(a1, a3, (enum _ONEX_NOTIFICATION_TYPE)a4->NotificationCode, a4->pData, a4->dwDataSize);
      goto LABEL_14;
    case 0x20:
      v14 = WDiagProcessInternalSecNotification((struct _WD_INTERFACE_CONTEXT *)v11, a2, a4, 0x20u, v18);
      goto LABEL_14;
  }
  v15 = 0;
  if ( v11 == &WPP_GLOBAL_Control )
    return v15;
  if ( *((_BYTE *)v11 + 225) && (*((_BYTE *)v11 + 228) & 4) != 0 )
  {
    WPP_SF_d(v11[27], 58, &WPP_fec73b95d5a537674450248f38664378_Traceguids, NotificationSource);
    goto LABEL_15;
  }
LABEL_16:
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 57) & 0x200) != 0 )
    WPP_SF_(v11[27], 59, &WPP_fec73b95d5a537674450248f38664378_Traceguids);
  return v15;
}

```

## disassembly

```asm
0x180010f20  mov     [rsp+arg_10], rbp
0x180010f25  push    rsi
0x180010f26  push    rdi
0x180010f27  push    r12
0x180010f29  push    r13
0x180010f2b  push    r14
0x180010f2d  sub     rsp, 60h
0x180010f31  mov     r14, r9
0x180010f34  mov     r12, r8
0x180010f37  mov     r13, rdx
0x180010f3a  mov     rdi, rcx
0x180010f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f44  lea     rsi, WPP_GLOBAL_Control
0x180010f4b  cmp     rcx, rsi
0x180010f4e  jz      short loc_180010FB8
0x180010f50  test    dword ptr [rcx+0E4h], 200h
0x180010f5a  jz      short loc_180010F7B
0x180010f5c  mov     rcx, [rcx+0D8h]
0x180010f63  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x180010f6a  mov     edx, 38h ; '8'
0x180010f6f  call    WPP_SF_
0x180010f74  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f7b  cmp     rcx, rsi
0x180010f7e  jz      short loc_180010FB8
0x180010f80  cmp     byte ptr [rcx+0E1h], 3
0x180010f87  jb      short loc_180010FB8
0x180010f89  test    byte ptr [rcx+0E4h], 4
0x180010f90  jz      short loc_180010FB8
0x180010f92  mov     rcx, [rcx+0D8h]
0x180010f99  lea     r9, [rdi+0DA0h]
0x180010fa0  mov     edx, 39h ; '9'
0x180010fa5  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x180010fac  call    WPP_SF__guid_
0x180010fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180010fb8  cmp     [rsp+88h+arg_20], 0
0x180010fc1  mov     ebp, [rsp+88h+arg_28]
0x180010fc8  mov     [rsp+88h+arg_0], rbx
0x180010fd0  jz      loc_18001107B
0x180010fd6  mov     [rsp+88h+arg_8], r15
0x180010fde  lea     rbx, [rdi+0D18h]
0x180010fe5  call    cs:__imp_GetCurrentThreadId
0x180010feb  lea     rcx, [rbx+8]; lpCriticalSection
0x180010fef  mov     r15d, eax
0x180010ff2  call    cs:__imp_EnterCriticalSection
0x180010ff8  mov     rcx, [rbx+58h]; hHandle
0x180010ffc  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180011001  call    cs:__imp_WaitForSingleObject
0x180011007  test    byte ptr [rbx+60h], 4
0x18001100b  lea     r8, aWdiagprocessin_0; "WDiagProcessInternalNotification"
0x180011012  jnz     loc_180011252
0x180011018  lea     rdx, WPP_GLOBAL_Control
0x18001101f  or      dword ptr [rbx+60h], 4
0x180011023  mov     [rbx+68h], r15d
0x180011027  mov     r15, [rsp+88h+arg_8]
0x18001102f  mov     dword ptr [rbx+6Ch], 39Dh
0x180011036  mov     [rbx+70h], r8
0x18001103a  mov     [rdi+0FC8h], ebp
0x180011040  test    byte ptr [rbx+60h], 4
0x180011044  jz      loc_1800112CC
0x18001104a  and     dword ptr [rbx+60h], 0FFFFFFFBh
0x18001104e  lea     rcx, [rbx+8]; lpCriticalSection
0x180011052  mov     dword ptr [rbx+78h], 39Fh
0x180011059  mov     [rbx+80h], r8
0x180011060  mov     dword ptr [rbx+68h], 0
0x180011067  call    cs:__imp_LeaveCriticalSection
0x18001106d  mov     rcx, cs:WPP_GLOBAL_Control; struct _WD_INTERFACE_CONTEXT *
0x180011074  lea     rsi, WPP_GLOBAL_Control
0x18001107b  mov     r9d, [r14]; unsigned int
0x18001107e  cmp     r9d, 8
0x180011082  jnz     short loc_1800110E0
0x180011084  mov     r8, r14; struct _L2_NOTIFICATION_DATA *
0x180011087  mov     rcx, rdi; struct _WD_INTERFACE_CONTEXT *
0x18001108a  call    ?WDiagProcessInternalAcmNotification@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAXPEAU_L2_NOTIFICATION_DATA@@KK@Z; WDiagProcessInternalAcmNotification(_WD_INTERFACE_CONTEXT *,void *,_L2_NOTIFICATION_DATA *,ulong,ulong)
0x18001108f  mov     ebx, eax
0x180011091  mov     rcx, cs:WPP_GLOBAL_Control
0x180011098  cmp     rcx, rsi
0x18001109b  jz      short loc_1800110C1
0x18001109d  test    dword ptr [rcx+0E4h], 200h
0x1800110a7  jz      short loc_1800110C1
0x1800110a9  mov     rcx, [rcx+0D8h]
0x1800110b0  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x1800110b7  mov     edx, 3Bh ; ';'
0x1800110bc  call    WPP_SF_
0x1800110c1  mov     rbp, [rsp+88h+arg_10]
0x1800110c9  mov     eax, ebx
0x1800110cb  mov     rbx, [rsp+88h+arg_0]
0x1800110d3  add     rsp, 60h
0x1800110d7  pop     r14
0x1800110d9  pop     r13
0x1800110db  pop     r12
0x1800110dd  pop     rdi
0x1800110de  pop     rsi
0x1800110df  retn
0x1800110e0  cmp     r9d, 10h
0x1800110e4  jnz     short loc_180011108
0x1800110e6  mov     eax, [rsp+88h+arg_30]
0x1800110ed  mov     r9, r14; struct _L2_NOTIFICATION_DATA *
0x1800110f0  mov     dword ptr [rsp+88h+var_60], eax; unsigned int
0x1800110f4  mov     r8, r12; void *
0x1800110f7  mov     rdx, r13; void *
0x1800110fa  mov     dword ptr [rsp+88h+var_68], ebp; unsigned int
0x1800110fe  mov     rcx, rdi; struct _WD_INTERFACE_CONTEXT *
0x180011101  call    ?WDiagProcessInternalMsmNotification@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAX1PEAU_L2_NOTIFICATION_DATA@@KK@Z; WDiagProcessInternalMsmNotification(_WD_INTERFACE_CONTEXT *,void *,void *,_L2_NOTIFICATION_DATA *,ulong,ulong)
0x180011106  jmp     short loc_18001108F
0x180011108  cmp     r9d, 40h ; '@'
0x18001110c  jnz     short loc_18001114E
0x18001110e  cmp     rcx, rsi
0x180011111  jz      short loc_180011147
0x180011113  test    dword ptr [rcx+0E4h], 200h
0x18001111d  jz      short loc_18001113E
0x18001111f  mov     rcx, [rcx+0D8h]
0x180011126  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x18001112d  mov     edx, 34h ; '4'
0x180011132  call    WPP_SF_
0x180011137  mov     rcx, cs:WPP_GLOBAL_Control
0x18001113e  cmp     rcx, rsi
0x180011141  jnz     loc_1800111CA
0x180011147  xor     ebx, ebx
0x180011149  jmp     loc_180011098
0x18001114e  cmp     r9d, 2
0x180011152  jz      short loc_1800111AA
0x180011154  cmp     r9d, 4
0x180011158  jz      loc_180011393
0x18001115e  cmp     r9d, 20h ; ' '
0x180011162  jz      loc_180011386
0x180011168  xor     ebx, ebx
0x18001116a  cmp     rcx, rsi
0x18001116d  jz      loc_1800110C1
0x180011173  cmp     byte ptr [rcx+0E1h], 1
0x18001117a  jb      loc_180011098
0x180011180  test    byte ptr [rcx+0E4h], 4
0x180011187  jz      loc_180011098
0x18001118d  mov     rcx, [rcx+0D8h]
0x180011194  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x18001119b  mov     edx, 3Ah ; ':'
0x1800111a0  call    WPP_SF_d
0x1800111a5  jmp     loc_180011091
0x1800111aa  mov     eax, [r14+18h]
0x1800111ae  mov     rdx, r12
0x1800111b1  mov     r9, [r14+20h]
0x1800111b5  mov     rcx, rdi
0x1800111b8  mov     r8d, [r14+4]
0x1800111bc  mov     dword ptr [rsp+88h+var_68], eax
0x1800111c0  call    ?WDiagSecurityNotification@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAXW4MSMSEC_NOTIFICATION_TYPE@@1K@Z; WDiagSecurityNotification(_WD_INTERFACE_CONTEXT *,void *,MSMSEC_NOTIFICATION_TYPE,void *,ulong)
0x1800111c5  jmp     loc_18001108F
0x1800111ca  cmp     byte ptr [rcx+0E1h], 1
0x1800111d1  jb      short loc_1800111FF
0x1800111d3  test    byte ptr [rcx+0E4h], 4
0x1800111da  jz      short loc_1800111FF
0x1800111dc  mov     r9d, [r14+4]
0x1800111e0  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x1800111e7  mov     rcx, [rcx+0D8h]
0x1800111ee  mov     edx, 35h ; '5'
0x1800111f3  call    WPP_SF_d
0x1800111f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111ff  cmp     rcx, rsi
0x180011202  jz      loc_180011147
0x180011208  cmp     byte ptr [rcx+0E1h], 4
0x18001120f  jnb     loc_18001134E
0x180011215  cmp     rcx, rsi
0x180011218  jz      loc_180011147
0x18001121e  test    dword ptr [rcx+0E4h], 200h
0x180011228  jz      loc_180011147
0x18001122e  mov     rcx, [rcx+0D8h]
0x180011235  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x18001123c  mov     edx, 37h ; '7'
0x180011241  call    WPP_SF_
0x180011246  mov     rcx, cs:WPP_GLOBAL_Control
0x18001124d  jmp     loc_180011147
0x180011252  mov     rcx, cs:WPP_GLOBAL_Control
0x180011259  lea     rdx, WPP_GLOBAL_Control
0x180011260  cmp     rcx, rdx
0x180011263  jz      loc_18001101F
0x180011269  cmp     byte ptr [rcx+0E1h], 1
0x180011270  jb      loc_18001101F
0x180011276  test    byte ptr [rcx+0E4h], 40h
0x18001127d  jz      loc_18001101F
0x180011283  mov     eax, [rbx+6Ch]
0x180011286  mov     r9, rdi
0x180011289  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180011290  mov     dword ptr [rsp+88h+var_38], 39Dh; char
0x180011298  mov     [rsp+88h+var_40], r8; __int64
0x18001129d  mov     dword ptr [rsp+88h+var_48], r15d; char
0x1800112a2  mov     dword ptr [rsp+88h+var_50], eax; char
0x1800112a6  mov     rax, [rbx+70h]
0x1800112aa  mov     [rsp+88h+var_58], rax; __int64
0x1800112af  mov     eax, [rbx+68h]
0x1800112b2  mov     dword ptr [rsp+88h+var_60], eax; char
0x1800112b6  mov     qword ptr [rsp+88h+var_68], rbx; char
0x1800112bb  call    WPP_SF_qqdsddsd
0x1800112c0  lea     r8, aWdiagprocessin_0; "WDiagProcessInternalNotification"
0x1800112c7  jmp     loc_180011018
0x1800112cc  mov     rax, cs:WPP_GLOBAL_Control
0x1800112d3  cmp     rax, rdx
0x1800112d6  jz      loc_18001104A
0x1800112dc  cmp     byte ptr [rax+0E1h], 1
0x1800112e3  jb      loc_18001104A
0x1800112e9  test    byte ptr [rax+0E4h], 40h
0x1800112f0  jz      loc_18001104A
0x1800112f6  call    cs:__imp_GetCurrentThreadId
0x1800112fc  mov     dword ptr [rsp+88h+var_38], 39Fh; char
0x180011304  lea     rcx, aWdiagprocessin_0; "WDiagProcessInternalNotification"
0x18001130b  mov     [rsp+88h+var_40], rcx; __int64
0x180011310  mov     r9, rdi
0x180011313  mov     rcx, cs:WPP_GLOBAL_Control
0x18001131a  mov     dword ptr [rsp+88h+var_48], eax; char
0x18001131e  mov     eax, [rbx+78h]
0x180011321  mov     dword ptr [rsp+88h+var_50], eax; char
0x180011325  mov     rax, [rbx+80h]
0x18001132c  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180011333  mov     [rsp+88h+var_58], rax; __int64
0x180011338  mov     qword ptr [rsp+88h+var_68], rbx; char
0x18001133d  call    WPP_SF_qqDsdDsd
0x180011342  lea     r8, aWdiagprocessin_0; "WDiagProcessInternalNotification"
0x180011349  jmp     loc_18001104A
0x18001134e  test    byte ptr [rcx+0E4h], 4
0x180011355  jz      loc_180011215
0x18001135b  mov     rcx, [rcx+0D8h]
0x180011362  lea     r9, aUnknown_1; "Unknown"
0x180011369  mov     edx, 36h ; '6'
0x18001136e  lea     r8, WPP_fec73b95d5a537674450248f38664378_Traceguids
0x180011375  call    WPP_SF_S
0x18001137a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011381  jmp     loc_180011215
0x180011386  mov     r8, r14; struct _L2_NOTIFICATION_DATA *
0x180011389  call    ?WDiagProcessInternalSecNotification@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAXPEAU_L2_NOTIFICATION_DATA@@KK@Z; WDiagProcessInternalSecNotification(_WD_INTERFACE_CONTEXT *,void *,_L2_NOTIFICATION_DATA *,ulong,ulong)
0x18001138e  jmp     loc_18001108F
0x180011393  mov     eax, [r14+18h]
0x180011397  mov     rdx, r12; void *
0x18001139a  mov     r9, [r14+20h]; void *
0x18001139e  mov     rcx, rdi; struct _WD_INTERFACE_CONTEXT *
0x1800113a1  mov     r8d, [r14+4]; enum _ONEX_NOTIFICATION_TYPE
0x1800113a5  mov     dword ptr [rsp+88h+var_68], eax; unsigned int
0x1800113a9  call    ?WDiagOneXNotification@@YAKPEAU_WD_INTERFACE_CONTEXT@@PEAXW4_ONEX_NOTIFICATION_TYPE@@1K@Z; WDiagOneXNotification(_WD_INTERFACE_CONTEXT *,void *,_ONEX_NOTIFICATION_TYPE,void *,ulong)
0x1800113ae  jmp     loc_18001108F
```
