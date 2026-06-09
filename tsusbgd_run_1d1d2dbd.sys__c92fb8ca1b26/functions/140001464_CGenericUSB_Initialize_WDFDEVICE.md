# CGenericUSB::Initialize(WDFDEVICE__ *)

- ea: `0x140001464`
- end: `0x140001992`
- name: `?Initialize@CGenericUSB@@AEAAJPEAUWDFDEVICE__@@@Z`
- size: `1326`
- prototype: `__int64 __fastcall(CGenericUSB *__hidden this, struct WDFDEVICE__ *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140001270`

## callees

- `0x140001464`
- `0x140001998`
- `0x140001ac0`
- `0x1400046dc`
- `0x140006330`
- `0x140006370`
- `0x140006440`

## pseudocode

```c
__int64 __fastcall CGenericUSB::Initialize(CGenericUSB *this, struct WDFDEVICE__ *a2)
{
  __int64 v4; // rcx
  int Instance; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v15; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v16; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+68h] [rbp-98h]
  __int64 v18; // [rsp+70h] [rbp-90h] BYREF
  __int64 v19; // [rsp+78h] [rbp-88h] BYREF
  __int128 v20; // [rsp+80h] [rbp-80h] BYREF
  __int128 v21; // [rsp+90h] [rbp-70h]
  __int128 v22; // [rsp+A0h] [rbp-60h]
  __int64 v23; // [rsp+B0h] [rbp-50h]
  _QWORD v24[12]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v25; // [rsp+120h] [rbp+20h] BYREF

  memset(v24, 0, sizeof(v24));
  *(_QWORD *)this = a2;
  v23 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v18 = 0;
  v21 = 0;
  v15 = 0;
  v22 = 0;
  v16 = 0;
  v25 = 0;
  *((_QWORD *)this + 4) = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDEVICE__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[21].Flink)(
                            WPP_MAIN_CB.Queue.ListEntry.Blink,
                            a2);
  *((_QWORD *)this + 9) = (char *)this + 64;
  *((_QWORD *)this + 8) = (char *)this + 64;
  Instance = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, char *))WPP_MAIN_CB.Queue.ListEntry.Flink[157].Blink)(
               WPP_MAIN_CB.Queue.ListEntry.Blink,
               0,
               (char *)this + 80);
  if ( Instance >= 0 )
  {
    Instance = CSimpleHash::CreateInstance(v4, (struct CSimpleHash **)this + 5);
    if ( Instance >= 0 )
    {
      Instance = CSimpleHash::CreateInstance(v8, (struct CSimpleHash **)this + 6);
      if ( Instance >= 0 )
      {
        Instance = CSimpleHash::CreateInstance(v9, (struct CSimpleHash **)this + 7);
        if ( Instance >= 0 )
        {
          memset(v24, 0, sizeof(v24));
          v24[0] = 0x200000060LL;
          v24[5] = GdEvtIoDeviceControl;
          LODWORD(v24[1]) = 2;
          v24[7] = GdEvtIoStop;
          BYTE5(v24[1]) = 1;
          LODWORD(v24[10]) = -1;
          Instance = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDEVICE__ *, _QWORD *, _QWORD, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[76].Flink)(
                       WPP_MAIN_CB.Queue.ListEntry.Blink,
                       a2,
                       v24,
                       0,
                       &v19);
          if ( Instance >= 0 )
          {
            v10 = *((_QWORD *)this + 4);
            *(_QWORD *)&v21 = 0;
            v23 = 0;
            v20 = 0;
            LODWORD(v20) = 56;
            *((_QWORD *)&v21 + 1) = 0x100000001LL;
            v22 = (unsigned __int64)a2;
            Instance = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int128 *, __int64, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[123].Blink)(
                         WPP_MAIN_CB.Queue.ListEntry.Blink,
                         &v20,
                         v10,
                         &v15);
            if ( Instance >= 0 )
            {
              v11 = *((_QWORD *)this + 4);
              *((_QWORD *)&v16 + 1) = &v25;
              *(_QWORD *)&v16 = 1;
              v17 = 16;
              Instance = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64, __int64, _QWORD, __int128 *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[94].Flink)(
                           WPP_MAIN_CB.Queue.ListEntry.Blink,
                           v11,
                           v15,
                           2245635,
                           0,
                           &v16,
                           0,
                           0);
              if ( Instance >= 0 )
              {
                v12 = v15;
                v13 = *((_QWORD *)this + 4);
                *(_OWORD *)((char *)this + 8) = v25;
                *((_QWORD *)&v16 + 1) = &v18;
                *(_QWORD *)&v16 = 1;
                v17 = 8;
                Instance = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64, __int64, _QWORD, __int128 *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[94].Flink)(
                             WPP_MAIN_CB.Queue.ListEntry.Blink,
                             v13,
                             v12,
                             2245639,
                             0,
                             &v16,
                             0,
                             0);
                if ( Instance >= 0 )
                {
                  *((_QWORD *)this + 3) = v18;
                  Instance = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDEVICE__ *, char *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[38].Blink)(
                               WPP_MAIN_CB.Queue.ListEntry.Blink,
                               a2,
                               (char *)this + 8,
                               0);
                  if ( Instance >= 0 )
                  {
                    Instance = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDEVICE__ *, GUID *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[38].Blink)(
                                 WPP_MAIN_CB.Queue.ListEntry.Blink,
                                 a2,
                                 &GUID_DEVINTERFACE_TSUSBGD,
                                 0);
                    if ( Instance >= 0 )
                    {
                      Instance = CGenericUSB::InitializeInterface(this);
                      if ( Instance >= 0 )
                      {
                        Instance = 0;
                      }
                      else
                      {
                        v6 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                        {
                          v7 = 20;
                          goto LABEL_5;
                        }
                      }
                    }
                    else
                    {
                      v6 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                      {
                        v7 = 19;
                        goto LABEL_5;
                      }
                    }
                  }
                  else
                  {
                    v6 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      v7 = 18;
                      goto LABEL_5;
                    }
                  }
                }
                else
                {
                  v6 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    v7 = 17;
                    goto LABEL_5;
                  }
                }
              }
              else
              {
                v6 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v7 = 16;
                  goto LABEL_5;
                }
              }
            }
            else
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v7 = 15;
                goto LABEL_5;
              }
            }
          }
          else
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v7 = 14;
              goto LABEL_5;
            }
          }
        }
        else
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v7 = 13;
            goto LABEL_5;
          }
        }
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v7 = 12;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v7 = 11;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v7 = 10;
LABEL_5:
      WPP_SF_d(v6->AttachedDevice, v7, &WPP_e22684400aa030ec2c531d4dcef4cab4_Traceguids, (unsigned int)Instance);
    }
  }
  if ( v15 )
    ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140001464  mov     [rsp-8+arg_10], rbx
0x140001469  push    rbp
0x14000146a  push    rsi
0x14000146b  push    rdi
0x14000146c  push    r14
0x14000146e  push    r15
0x140001470  lea     rbp, [rsp-40h]
0x140001475  sub     rsp, 140h
0x14000147c  mov     rax, cs:__security_cookie
0x140001483  xor     rax, rsp
0x140001486  mov     [rbp+60h+var_30], rax
0x14000148a  mov     rsi, rdx
0x14000148d  mov     rdi, rcx
0x140001490  mov     r14d, 60h ; '`'
0x140001496  lea     rcx, [rbp+60h+var_A0]; void *
0x14000149a  mov     r8d, r14d; Size
0x14000149d  xor     edx, edx; Val
0x14000149f  call    memset
0x1400014a4  xorps   xmm0, xmm0
0x1400014a7  mov     [rdi], rsi
0x1400014aa  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400014b1  xor     eax, eax
0x1400014b3  mov     [rbp+60h+var_B0], rax
0x1400014b7  xor     r15d, r15d
0x1400014ba  mov     [rsp+160h+var_F8], rax
0x1400014bf  mov     rdx, rsi
0x1400014c2  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400014c9  mov     [rsp+160h+var_E8], r15
0x1400014ce  movups  [rbp+60h+var_E0], xmm0
0x1400014d2  mov     [rsp+160h+var_F0], r15
0x1400014d7  movups  [rbp+60h+var_D0], xmm0
0x1400014db  mov     [rsp+160h+var_110], r15
0x1400014e0  movups  [rbp+60h+var_C0], xmm0
0x1400014e4  movups  [rsp+160h+var_108], xmm0
0x1400014e9  movups  [rbp+60h+var_40], xmm0
0x1400014ed  mov     rax, [rax+150h]
0x1400014f4  call    _guard_dispatch_icall
0x1400014f9  mov     [rdi+20h], rax
0x1400014fd  lea     r8, [rdi+50h]
0x140001501  lea     rax, [rdi+40h]
0x140001505  xor     edx, edx
0x140001507  mov     [rax+8], rax
0x14000150b  mov     [rax], rax
0x14000150e  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140001515  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000151c  mov     rax, [rax+9D8h]
0x140001523  call    _guard_dispatch_icall
0x140001528  mov     ebx, eax
0x14000152a  test    eax, eax
0x14000152c  jns     short loc_14000156B
0x14000152e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001535  lea     rax, WPP_GLOBAL_Control
0x14000153c  cmp     rcx, rax
0x14000153f  jz      loc_140001948
0x140001545  cmp     byte ptr [rcx+29h], 2
0x140001549  jb      loc_140001948
0x14000154f  lea     edx, [r14-56h]
0x140001553  mov     rcx, [rcx+18h]
0x140001557  lea     r8, WPP_e22684400aa030ec2c531d4dcef4cab4_Traceguids
0x14000155e  mov     r9d, ebx
0x140001561  call    WPP_SF_d
0x140001566  jmp     loc_140001948
0x14000156b  lea     rdx, [rdi+28h]; struct CSimpleHash **
0x14000156f  call    ?CreateInstance@CSimpleHash@@SAJKPEAPEAV1@@Z; CSimpleHash::CreateInstance(ulong,CSimpleHash * *)
0x140001574  mov     ebx, eax
0x140001576  test    eax, eax
0x140001578  jns     short loc_1400015A2
0x14000157a  mov     rcx, cs:WPP_GLOBAL_Control
0x140001581  lea     rax, WPP_GLOBAL_Control
0x140001588  cmp     rcx, rax
0x14000158b  jz      loc_140001948
0x140001591  cmp     byte ptr [rcx+29h], 2
0x140001595  jb      loc_140001948
0x14000159b  mov     edx, 0Bh
0x1400015a0  jmp     short loc_140001553
0x1400015a2  lea     rdx, [rdi+30h]; struct CSimpleHash **
0x1400015a6  call    ?CreateInstance@CSimpleHash@@SAJKPEAPEAV1@@Z; CSimpleHash::CreateInstance(ulong,CSimpleHash * *)
0x1400015ab  mov     ebx, eax
0x1400015ad  test    eax, eax
0x1400015af  jns     short loc_1400015DC
0x1400015b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400015b8  lea     rax, WPP_GLOBAL_Control
0x1400015bf  cmp     rcx, rax
0x1400015c2  jz      loc_140001948
0x1400015c8  cmp     byte ptr [rcx+29h], 2
0x1400015cc  jb      loc_140001948
0x1400015d2  mov     edx, 0Ch
0x1400015d7  jmp     loc_140001553
0x1400015dc  lea     rdx, [rdi+38h]; struct CSimpleHash **
0x1400015e0  call    ?CreateInstance@CSimpleHash@@SAJKPEAPEAV1@@Z; CSimpleHash::CreateInstance(ulong,CSimpleHash * *)
0x1400015e5  mov     ebx, eax
0x1400015e7  test    eax, eax
0x1400015e9  jns     short loc_140001616
0x1400015eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400015f2  lea     rax, WPP_GLOBAL_Control
0x1400015f9  cmp     rcx, rax
0x1400015fc  jz      loc_140001948
0x140001602  cmp     byte ptr [rcx+29h], 2
0x140001606  jb      loc_140001948
0x14000160c  mov     edx, 0Dh
0x140001611  jmp     loc_140001553
0x140001616  mov     r8, r14; Size
0x140001619  lea     rcx, [rbp+60h+var_A0]; void *
0x14000161d  xor     edx, edx; Val
0x14000161f  call    memset
0x140001624  lea     rax, GdEvtIoDeviceControl
0x14000162b  mov     [rbp+60h+var_A0], r14d
0x14000162f  mov     [rbp+60h+var_78], rax
0x140001633  lea     rcx, [rsp+160h+var_E8]
0x140001638  lea     rax, GdEvtIoStop
0x14000163f  mov     [rbp+60h+var_98], 2
0x140001646  mov     [rbp+60h+var_68], rax
0x14000164a  lea     r8, [rbp+60h+var_A0]
0x14000164e  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140001655  xor     r9d, r9d
0x140001658  mov     [rbp+60h+var_93], 1
0x14000165c  mov     rdx, rsi
0x14000165f  mov     [rbp+60h+var_9C], 2
0x140001666  mov     [rbp+60h+var_50], 0FFFFFFFFh
0x14000166d  mov     rax, [rax+4C0h]
0x140001674  mov     [rsp+160h+var_140], rcx
0x140001679  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001680  call    _guard_dispatch_icall
0x140001685  mov     ebx, eax
0x140001687  test    eax, eax
0x140001689  jns     short loc_1400016B6
0x14000168b  mov     rcx, cs:WPP_GLOBAL_Control
0x140001692  lea     rax, WPP_GLOBAL_Control
0x140001699  cmp     rcx, rax
0x14000169c  jz      loc_140001948
0x1400016a2  cmp     byte ptr [rcx+29h], 2
0x1400016a6  jb      loc_140001948
0x1400016ac  mov     edx, 0Eh
0x1400016b1  jmp     loc_140001553
0x1400016b6  mov     r8, [rdi+20h]
0x1400016ba  lea     r9, [rsp+160h+var_110]
0x1400016bf  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400016c6  lea     rdx, [rbp+60h+var_E0]
0x1400016ca  xor     eax, eax
0x1400016cc  xorps   xmm0, xmm0
0x1400016cf  movups  [rbp+60h+var_D0], xmm0
0x1400016d3  mov     [rbp+60h+var_B0], rax
0x1400016d7  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400016de  movups  [rbp+60h+var_E0], xmm0
0x1400016e2  mov     dword ptr [rbp+60h+var_E0], 38h ; '8'
0x1400016e9  movups  [rbp+60h+var_C0], xmm0
0x1400016ed  mov     dword ptr [rbp+60h+var_D0+8], 1
0x1400016f4  mov     dword ptr [rbp+60h+var_D0+0Ch], 1
0x1400016fb  mov     qword ptr [rbp+60h+var_C0], rsi
0x1400016ff  mov     rax, [rax+7B8h]
0x140001706  call    _guard_dispatch_icall
0x14000170b  mov     ebx, eax
0x14000170d  test    eax, eax
0x14000170f  jns     short loc_14000173C
0x140001711  mov     rcx, cs:WPP_GLOBAL_Control
0x140001718  lea     rax, WPP_GLOBAL_Control
0x14000171f  cmp     rcx, rax
0x140001722  jz      loc_140001948
0x140001728  cmp     byte ptr [rcx+29h], 2
0x14000172c  jb      loc_140001948
0x140001732  mov     edx, 0Fh
0x140001737  jmp     loc_140001553
0x14000173c  mov     r8, [rsp+160h+var_110]
0x140001741  lea     rax, [rbp+60h+var_40]
0x140001745  mov     rdx, [rdi+20h]
0x140001749  lea     rcx, [rsp+160h+var_108]
0x14000174e  mov     qword ptr [rsp+160h+var_108+8], rax
0x140001753  mov     r9d, 224403h
0x140001759  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140001760  mov     r14d, 10h
0x140001766  mov     [rsp+160h+var_128], r15
0x14000176b  mov     [rsp+160h+var_130], r15
0x140001770  mov     [rsp+160h+var_138], rcx
0x140001775  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000177c  mov     qword ptr [rsp+160h+var_108], 1
0x140001785  mov     [rsp+160h+var_F8], 10h
0x14000178e  mov     rax, [rax+5E0h]
0x140001795  mov     [rsp+160h+var_140], r15
0x14000179a  call    _guard_dispatch_icall
0x14000179f  mov     ebx, eax
0x1400017a1  test    eax, eax
0x1400017a3  jns     short loc_1400017CE
0x1400017a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400017ac  lea     rax, WPP_GLOBAL_Control
0x1400017b3  cmp     rcx, rax
0x1400017b6  jz      loc_140001948
0x1400017bc  cmp     byte ptr [rcx+29h], 2
0x1400017c0  jb      loc_140001948
0x1400017c6  mov     edx, r14d
0x1400017c9  jmp     loc_140001553
0x1400017ce  movups  xmm0, [rbp+60h+var_40]
0x1400017d2  mov     r8, [rsp+160h+var_110]
0x1400017d7  lea     rax, [rsp+160h+var_F0]
0x1400017dc  mov     rdx, [rdi+20h]
0x1400017e0  lea     rcx, [rsp+160h+var_108]
0x1400017e5  movdqu  xmmword ptr [rdi+8], xmm0
0x1400017ea  mov     qword ptr [rsp+160h+var_108+8], rax
0x1400017ef  mov     r9d, 224407h
0x1400017f5  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400017fc  mov     [rsp+160h+var_128], r15
0x140001801  mov     [rsp+160h+var_130], r15
0x140001806  mov     [rsp+160h+var_138], rcx
0x14000180b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001812  mov     qword ptr [rsp+160h+var_108], 1
0x14000181b  mov     [rsp+160h+var_F8], 8
0x140001824  mov     rax, [rax+5E0h]
0x14000182b  mov     [rsp+160h+var_140], r15
0x140001830  call    _guard_dispatch_icall
0x140001835  mov     ebx, eax
0x140001837  test    eax, eax
0x140001839  jns     short loc_140001866
0x14000183b  mov     rcx, cs:WPP_GLOBAL_Control
0x140001842  lea     rax, WPP_GLOBAL_Control
0x140001849  cmp     rcx, rax
0x14000184c  jz      loc_140001948
0x140001852  cmp     byte ptr [rcx+29h], 2
0x140001856  jb      loc_140001948
0x14000185c  mov     edx, 11h
0x140001861  jmp     loc_140001553
0x140001866  mov     rax, [rsp+160h+var_F0]
0x14000186b  lea     r8, [rdi+8]
0x14000186f  mov     [rdi+18h], rax
0x140001873  xor     r9d, r9d
0x140001876  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000187d  mov     rdx, rsi
0x140001880  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001887  mov     rax, [rax+268h]
0x14000188e  call    _guard_dispatch_icall
0x140001893  mov     ebx, eax
0x140001895  test    eax, eax
0x140001897  jns     short loc_1400018C4
0x140001899  mov     rcx, cs:WPP_GLOBAL_Control
0x1400018a0  lea     rax, WPP_GLOBAL_Control
0x1400018a7  cmp     rcx, rax
0x1400018aa  jz      loc_140001948
0x1400018b0  cmp     byte ptr [rcx+29h], 2
0x1400018b4  jb      loc_140001948
0x1400018ba  mov     edx, 12h
0x1400018bf  jmp     loc_140001553
0x1400018c4  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400018cb  lea     r8, GUID_DEVINTERFACE_TSUSBGD
0x1400018d2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400018d9  xor     r9d, r9d
0x1400018dc  mov     rdx, rsi
0x1400018df  mov     rax, [rax+268h]
0x1400018e6  call    _guard_dispatch_icall
0x1400018eb  mov     ebx, eax
0x1400018ed  test    eax, eax
0x1400018ef  jns     short loc_140001914
0x1400018f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400018f8  lea     rax, WPP_GLOBAL_Control
0x1400018ff  cmp     rcx, rax
0x140001902  jz      short loc_140001948
0x140001904  cmp     byte ptr [rcx+29h], 2
0x140001908  jb      short loc_140001948
0x14000190a  mov     edx, 13h
0x14000190f  jmp     loc_140001553
0x140001914  mov     rcx, rdi; this
0x140001917  call    ?InitializeInterface@CGenericUSB@@AEAAJXZ; CGenericUSB::InitializeInterface(void)
0x14000191c  mov     ebx, eax
0x14000191e  test    eax, eax
0x140001920  jns     short loc_140001945
0x140001922  mov     rcx, cs:WPP_GLOBAL_Control
0x140001929  lea     rax, WPP_GLOBAL_Control
0x140001930  cmp     rcx, rax
0x140001933  jz      short loc_140001948
0x140001935  cmp     byte ptr [rcx+29h], 2
0x140001939  jb      short loc_140001948
0x14000193b  mov     edx, 14h
0x140001940  jmp     loc_140001553
0x140001945  mov     ebx, r15d
0x140001948  mov     rdx, [rsp+160h+var_110]
0x14000194d  test    rdx, rdx
0x140001950  jz      short loc_14000196C
0x140001952  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140001959  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001960  mov     rax, [rax+680h]
0x140001967  call    _guard_dispatch_icall
0x14000196c  mov     eax, ebx
0x14000196e  mov     rcx, [rbp+60h+var_30]
0x140001972  xor     rcx, rsp; StackCookie
0x140001975  call    __security_check_cookie
0x14000197a  mov     rbx, [rsp+160h+arg_10]
0x140001982  add     rsp, 140h
0x140001989  pop     r15
0x14000198b  pop     r14
0x14000198d  pop     rdi
0x14000198e  pop     rsi
0x14000198f  pop     rbp
0x140001990  retn
```
