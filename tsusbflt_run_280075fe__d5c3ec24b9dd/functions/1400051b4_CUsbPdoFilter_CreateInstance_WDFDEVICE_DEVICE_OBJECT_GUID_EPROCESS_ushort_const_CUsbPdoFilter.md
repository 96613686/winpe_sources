# CUsbPdoFilter::CreateInstance(WDFDEVICE__ *,_DEVICE_OBJECT *,_GUID *,_EPROCESS *,ushort const *,CUsbPdoFilter * *)

- ea: `0x1400051b4`
- end: `0x14000551a`
- name: `?CreateInstance@CUsbPdoFilter@@SAJPEAUWDFDEVICE__@@PEAU_DEVICE_OBJECT@@PEAU_GUID@@PEAU_EPROCESS@@PEBGPEAPEAV1@@Z`
- size: `870`
- prototype: `static int(struct WDFDEVICE__ *, struct _DEVICE_OBJECT *, struct _GUID *, struct _EPROCESS *, const unsigned __int16 *, struct CUsbPdoFilter **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140003258`

## callees

- `0x140004f18`
- `0x140004f48`
- `0x1400051b4`
- `0x140005754`
- `0x14000aa30`

## pseudocode

```c
__int64 __fastcall CUsbPdoFilter::CreateInstance(
        struct WDFDEVICE__ *a1,
        struct _DEVICE_OBJECT *a2,
        struct _GUID *a3,
        struct _EPROCESS *a4,
        unsigned __int16 *a5,
        struct CUsbPdoFilter **a6)
{
  __int64 v9; // rax
  int v10; // ebx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  char v16; // si
  struct CUsbPdoFilter *v17; // rax
  struct CUsbPdoFilter *v18; // rsi
  __int64 v20; // [rsp+40h] [rbp-39h] BYREF
  struct WDFDEVICE__ *v21; // [rsp+48h] [rbp-31h] BYREF
  __int128 v22; // [rsp+50h] [rbp-29h] BYREF
  __int128 v23; // [rsp+60h] [rbp-19h]
  __int128 v24; // [rsp+70h] [rbp-9h]
  __int64 *v25; // [rsp+80h] [rbp+7h]

  v25 = 0;
  v22 = 0;
  v21 = 0;
  v23 = 0;
  v20 = 0;
  v24 = 0;
  v9 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDEVICE__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[19].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a1);
  v21 = 0;
  v20 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, const UNICODE_STRING *))WPP_MAIN_CB.Queue.ListEntry.Flink[12].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          v9,
          &SDDL_DEVOBJ_KERNEL_ONLY);
  if ( v20 )
  {
    ((void (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[30].Blink)(
      WPP_MAIN_CB.Queue.ListEntry.Blink,
      v20,
      2);
    v10 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[33].Blink)(
            WPP_MAIN_CB.Queue.ListEntry.Blink,
            v20,
            0);
    if ( v10 >= 0 )
    {
      v25 = off_14000F090;
      v16 = 0;
      *(_QWORD *)&v22 = 56;
      *((_QWORD *)&v22 + 1) = PfEvtDeviceContextCleanup;
      *(_QWORD *)&v23 = 0;
      v24 = 0;
      *((_QWORD *)&v23 + 1) = 0x400000002LL;
      while ( 1 )
      {
        LOBYTE(v13) = v16;
        v10 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, void *, __int64, _QWORD, _DWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[36].Blink)(
                WPP_MAIN_CB.Queue.ListEntry.Blink,
                v20,
                &PfEvtWdmIrpPreprocessCallback,
                v13,
                0,
                0);
        if ( v10 < 0 )
          break;
        if ( (unsigned __int8)++v16 > 0x1Bu )
        {
          v10 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64 *, __int128 *, struct WDFDEVICE__ **))WPP_MAIN_CB.Queue.ListEntry.Flink[37].Blink)(
                  WPP_MAIN_CB.Queue.ListEntry.Blink,
                  &v20,
                  &v22,
                  &v21);
          if ( v10 >= 0 )
          {
            v17 = (struct CUsbPdoFilter *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDEVICE__ *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                                            WPP_MAIN_CB.Queue.ListEntry.Blink,
                                            v21,
                                            off_14000F090);
            v18 = v17;
            if ( v17 )
            {
              *(_QWORD *)v17 = 0;
              *((_QWORD *)v17 + 1) = 0;
              *((_QWORD *)v17 + 4) = 0;
              *((_QWORD *)v17 + 5) = 0;
              *((_QWORD *)v17 + 6) = 0;
              v10 = CUsbPdoFilter::Initialize(v17, v21, a2, a3, a4, a5);
              if ( v10 >= 0 )
              {
                v10 = 0;
                v21 = 0;
                *a6 = v18;
              }
              else
              {
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v15 = 15;
                  goto LABEL_29;
                }
              }
            }
            else
            {
              v10 = -1073741801;
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v12 = 14;
                goto LABEL_5;
              }
            }
          }
          else
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v15 = 13;
              goto LABEL_29;
            }
          }
          goto LABEL_30;
        }
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v15 = 12;
        goto LABEL_29;
      }
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v15 = 11;
LABEL_29:
        WPP_SF_d(v14->AttachedDevice, v15, WPP_be851031edc93d18f2bbe38844c4b0c7_Traceguids, (unsigned int)v10);
      }
    }
  }
  else
  {
    v10 = -1073741670;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v12 = 10;
LABEL_5:
      WPP_SF_(v11->AttachedDevice, v12, WPP_be851031edc93d18f2bbe38844c4b0c7_Traceguids);
    }
  }
LABEL_30:
  if ( v20 )
    ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[27].Flink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
  if ( v21 )
    ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400051b4  push    rbp
0x1400051b6  push    rbx
0x1400051b7  push    rsi
0x1400051b8  push    r12
0x1400051ba  push    r13
0x1400051bc  push    r14
0x1400051be  push    r15
0x1400051c0  lea     rbp, [rsp-17h]
0x1400051c5  sub     rsp, 90h
0x1400051cc  xor     eax, eax
0x1400051ce  xorps   xmm0, xmm0
0x1400051d1  mov     [rbp+47h+var_40], rax
0x1400051d5  xor     r13d, r13d
0x1400051d8  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400051df  mov     r12, rdx
0x1400051e2  movups  [rbp+47h+var_70], xmm0
0x1400051e6  mov     [rbp+47h+var_78], r13
0x1400051ea  mov     rdx, rcx
0x1400051ed  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400051f4  mov     r14, r9
0x1400051f7  movups  [rbp+47h+var_60], xmm0
0x1400051fb  mov     [rbp+47h+var_80], r13
0x1400051ff  mov     r15, r8
0x140005202  movups  [rbp+47h+var_50], xmm0
0x140005206  mov     rax, [rax+138h]
0x14000520d  call    _guard_dispatch_icall
0x140005212  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140005219  lea     r8, SDDL_DEVOBJ_KERNEL_ONLY
0x140005220  mov     rdx, rax
0x140005223  mov     [rbp+47h+var_78], r13
0x140005227  mov     rax, [rcx+0C8h]
0x14000522e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140005235  call    _guard_dispatch_icall
0x14000523a  mov     [rbp+47h+var_80], rax
0x14000523e  test    rax, rax
0x140005241  jnz     short loc_140005282
0x140005243  mov     ebx, 0C000009Ah
0x140005248  mov     rcx, cs:WPP_GLOBAL_Control
0x14000524f  lea     rax, WPP_GLOBAL_Control
0x140005256  cmp     rcx, rax
0x140005259  jz      loc_1400054BE
0x14000525f  cmp     byte ptr [rcx+29h], 2
0x140005263  jb      loc_1400054BE
0x140005269  lea     edx, [r13+0Ah]
0x14000526d  mov     rcx, [rcx+18h]
0x140005271  lea     r8, WPP_be851031edc93d18f2bbe38844c4b0c7_Traceguids
0x140005278  call    WPP_SF_
0x14000527d  jmp     loc_1400054BE
0x140005282  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140005289  mov     r8d, 2
0x14000528f  mov     rdx, [rbp+47h+var_80]
0x140005293  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000529a  mov     rax, [rax+1E8h]
0x1400052a1  call    _guard_dispatch_icall
0x1400052a6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400052ad  xor     r8d, r8d
0x1400052b0  mov     rdx, [rbp+47h+var_80]
0x1400052b4  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400052bb  mov     rax, [rax+218h]
0x1400052c2  call    _guard_dispatch_icall
0x1400052c7  mov     ebx, eax
0x1400052c9  test    eax, eax
0x1400052cb  jns     short loc_1400052F8
0x1400052cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400052d4  lea     rax, WPP_GLOBAL_Control
0x1400052db  cmp     rcx, rax
0x1400052de  jz      loc_1400054BE
0x1400052e4  cmp     byte ptr [rcx+29h], 2
0x1400052e8  jb      loc_1400054BE
0x1400052ee  mov     edx, 0Bh
0x1400052f3  jmp     loc_1400054AB
0x1400052f8  mov     rax, cs:off_14000F090
0x1400052ff  xorps   xmm0, xmm0
0x140005302  mov     [rbp+47h+var_40], rax
0x140005306  mov     sil, r13b
0x140005309  lea     rax, PfEvtDeviceContextCleanup
0x140005310  mov     qword ptr [rbp+47h+var_70], 38h ; '8'
0x140005318  mov     qword ptr [rbp+47h+var_70+8], rax
0x14000531c  mov     qword ptr [rbp+47h+var_60], r13
0x140005320  movdqu  [rbp+47h+var_50], xmm0
0x140005325  mov     dword ptr [rbp+47h+var_60+8], 2
0x14000532c  mov     dword ptr [rbp+47h+var_60+0Ch], 4
0x140005333  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000533a  lea     r8, PfEvtWdmIrpPreprocessCallback
0x140005341  mov     rdx, [rbp+47h+var_80]
0x140005345  mov     r9b, sil
0x140005348  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000534f  mov     dword ptr [rsp+0C0h+var_98], r13d
0x140005354  mov     rax, [rax+248h]
0x14000535b  mov     [rsp+0C0h+var_A0], r13
0x140005360  call    _guard_dispatch_icall
0x140005365  mov     ebx, eax
0x140005367  test    eax, eax
0x140005369  js      loc_14000548D
0x14000536f  inc     sil
0x140005372  cmp     sil, 1Bh
0x140005376  jbe     short loc_140005333
0x140005378  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000537f  lea     r9, [rbp+47h+var_78]
0x140005383  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000538a  lea     r8, [rbp+47h+var_70]
0x14000538e  lea     rdx, [rbp+47h+var_80]
0x140005392  mov     rax, [rax+258h]
0x140005399  call    _guard_dispatch_icall
0x14000539e  mov     ebx, eax
0x1400053a0  test    eax, eax
0x1400053a2  jns     short loc_1400053CF
0x1400053a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400053ab  lea     rax, WPP_GLOBAL_Control
0x1400053b2  cmp     rcx, rax
0x1400053b5  jz      loc_1400054BE
0x1400053bb  cmp     byte ptr [rcx+29h], 2
0x1400053bf  jb      loc_1400054BE
0x1400053c5  mov     edx, 0Dh
0x1400053ca  jmp     loc_1400054AB
0x1400053cf  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400053d6  mov     r8, cs:off_14000F090
0x1400053dd  mov     rdx, [rbp+47h+var_78]
0x1400053e1  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400053e8  mov     rax, [rax+650h]
0x1400053ef  call    _guard_dispatch_icall
0x1400053f4  mov     rsi, rax
0x1400053f7  test    rax, rax
0x1400053fa  jz      short loc_140005465
0x1400053fc  mov     rcx, [rbp+47h+arg_20]
0x140005400  mov     r9, r15; struct _GUID *
0x140005403  mov     [rsp+0C0h+var_98], rcx; unsigned __int16 *
0x140005408  mov     r8, r12; struct _DEVICE_OBJECT *
0x14000540b  mov     [rax], r13
0x14000540e  mov     rcx, rax; this
0x140005411  mov     [rax+8], r13
0x140005415  mov     [rax+20h], r13
0x140005419  mov     [rax+28h], r13
0x14000541d  mov     [rax+30h], r13
0x140005421  mov     rdx, [rbp+47h+var_78]; struct WDFDEVICE__ *
0x140005425  mov     [rsp+0C0h+var_A0], r14; struct _EPROCESS *
0x14000542a  call    ?Initialize@CUsbPdoFilter@@AEAAJPEAUWDFDEVICE__@@PEAU_DEVICE_OBJECT@@PEAU_GUID@@PEAU_EPROCESS@@PEBG@Z; CUsbPdoFilter::Initialize(WDFDEVICE__ *,_DEVICE_OBJECT *,_GUID *,_EPROCESS *,ushort const *)
0x14000542f  mov     ebx, eax
0x140005431  test    eax, eax
0x140005433  jns     short loc_140005455
0x140005435  mov     rcx, cs:WPP_GLOBAL_Control
0x14000543c  lea     rax, WPP_GLOBAL_Control
0x140005443  cmp     rcx, rax
0x140005446  jz      short loc_1400054BE
0x140005448  cmp     byte ptr [rcx+29h], 2
0x14000544c  jb      short loc_1400054BE
0x14000544e  mov     edx, 0Fh
0x140005453  jmp     short loc_1400054AB
0x140005455  mov     rax, [rbp+47h+arg_28]
0x140005459  mov     ebx, r13d
0x14000545c  mov     [rbp+47h+var_78], r13
0x140005460  mov     [rax], rsi
0x140005463  jmp     short loc_1400054BE
0x140005465  mov     ebx, 0C0000017h
0x14000546a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005471  lea     rax, WPP_GLOBAL_Control
0x140005478  cmp     rcx, rax
0x14000547b  jz      short loc_1400054BE
0x14000547d  cmp     byte ptr [rcx+29h], 2
0x140005481  jb      short loc_1400054BE
0x140005483  mov     edx, 0Eh
0x140005488  jmp     loc_14000526D
0x14000548d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005494  lea     rax, WPP_GLOBAL_Control
0x14000549b  cmp     rcx, rax
0x14000549e  jz      short loc_1400054BE
0x1400054a0  cmp     byte ptr [rcx+29h], 2
0x1400054a4  jb      short loc_1400054BE
0x1400054a6  mov     edx, 0Ch
0x1400054ab  mov     rcx, [rcx+18h]
0x1400054af  lea     r8, WPP_be851031edc93d18f2bbe38844c4b0c7_Traceguids
0x1400054b6  mov     r9d, ebx
0x1400054b9  call    WPP_SF_d
0x1400054be  mov     rdx, [rbp+47h+var_80]
0x1400054c2  test    rdx, rdx
0x1400054c5  jz      short loc_1400054E1
0x1400054c7  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400054ce  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400054d5  mov     rax, [rax+1B0h]
0x1400054dc  call    _guard_dispatch_icall
0x1400054e1  mov     rdx, [rbp+47h+var_78]
0x1400054e5  test    rdx, rdx
0x1400054e8  jz      short loc_140005504
0x1400054ea  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400054f1  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400054f8  mov     rax, [rax+680h]
0x1400054ff  call    _guard_dispatch_icall
0x140005504  mov     eax, ebx
0x140005506  add     rsp, 90h
0x14000550d  pop     r15
0x14000550f  pop     r14
0x140005511  pop     r13
0x140005513  pop     r12
0x140005515  pop     rsi
0x140005516  pop     rbx
0x140005517  pop     rbp
0x140005518  retn
```
